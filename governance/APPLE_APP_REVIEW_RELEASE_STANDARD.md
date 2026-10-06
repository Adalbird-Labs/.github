# Adalbird Labs — Apple App Review Release Standard

**Status:** Canonical / Cross-product  
**Owner:** CPO / Product Owners  
**Effective:** 2026-10-06  
**Applies to:** every Adalbird Labs product distributed through Apple App Store

## Purpose

Grzybołaz 1.0 reached App Store approval only after several review rounds. The requirements and failure modes learned there are now a reusable release standard. New products must satisfy this standard before App Store submission instead of rediscovering the same requirements during review.

This checklist complements Apple’s current guidelines. If Apple changes its rules, current Apple guidance wins and this standard must be updated.

## Mandatory pre-submission gates

### 1. Reviewer access / app completeness

If material functionality is account-gated, Apple reviewers must have a reliable review path that does not depend on the founder’s private mailbox, personal MFA or ad-hoc intervention.

Required:
- dedicated App Review access/account or another repeatable reviewer-safe path;
- credentials/access instructions live only in store/provider review fields, never in GitHub, Linear or chat;
- clean-install test of the reviewer path on the exact submitted build;
- App Review Notes explain exact navigation and any non-obvious test setup;
- destructive deletion testing uses a disposable test account, never the dedicated reviewer account.

### 2. Third-party login and Sign in with Apple

If the iOS app offers Google or another third-party/social login for the primary account, Sign in with Apple must be present and operational on the submitted iOS build.

Required:
- Sign in with Apple is clearly visible wherever equivalent login options are presented;
- iOS visibility must not disappear merely because runtime/provider discovery times out or fails transiently when Apple login is a release requirement;
- the exact submitted build completes Sign in with Apple end-to-end and returns to the app;
- Hide My Email / Apple private relay addresses work without trying to infer the hidden real mailbox;
- the login option does not request unnecessary identity data beyond the authentication/account need;
- app interaction analytics or advertising tracking is not collected through the login option without user consent;
- identity linking must not silently merge accounts only because email strings appear related.

### 3. Native authentication experience

OAuth on iOS must use an Apple-appropriate in-app/system authentication session and return to the app reliably.

Required:
- no unintended handoff to standalone Safari for the primary sign-in flow;
- callback/deep-link handling is validated on a physical iPhone;
- cancel, provider failure, timeout and callback failure produce safe recovery;
- tokens/secrets are not exposed in UI, analytics, diagnostics or review notes.

### 4. In-app account deletion

Any app that supports account creation must provide an in-app path to initiate permanent account deletion.

Required:
- deletion is easy to find from Profile/Account/Settings without support contact or external navigation;
- wording clearly distinguishes local-data deletion from account-and-cloud-data deletion;
- irreversible deletion has explicit confirmation and accidental-activation protection;
- successful deletion covers Auth identity plus applicable cloud/database/storage data and clears local account state;
- success ends the active session and returns the app to a signed-out state;
- partial failures never falsely report success;
- exact-build E2E test is performed with a disposable account and backed by server/provider evidence where possible.

### 5. Privacy and consent alignment

Before submission, implementation, privacy policy, App Privacy declarations and review notes must agree.

Verify at minimum:
- login identity data and provider behavior;
- Hide My Email support when Apple login is used;
- analytics default/consent behavior;
- no cross-app/cross-site tracking unless explicitly implemented, declared and consented as required;
- advertising/sponsor metrics classification and linkage;
- account deletion and retention behavior;
- diagnostics do not leak credentials, tokens or private content.

### 6. Reviewer evidence package

For every release where a reviewer could reasonably miss a compliance-critical path, prepare evidence before submission.

Evidence should include:
- exact version/build number and immutable source identity;
- short App Review Notes with exact navigation labels;
- a continuous physical-device video when deletion, background/device capability, reviewer access or another difficult-to-observe flow is likely to be questioned;
- the recording shows the real start state, complete flow, success/end state and relevant login options;
- credentials and personal accounts are never exposed.

### 7. Device/layout coverage

Apple may review on iPhone or iPad even when the product is primarily phone-oriented.

Before submission:
- verify compliance-critical controls are visible and usable on supported iPhone layout;
- verify iPad/iPadOS presentation sufficiently to ensure login, reviewer access and account deletion controls are discoverable and not clipped/hidden;
- never claim physical-device evidence that was not actually executed.

### 8. Exact-build release gate

No App Store submission may rely only on source-level or earlier-build evidence.

Before Submit:
- identify the exact signed/TestFlight build;
- run the Apple compliance preflight against that build;
- ensure metadata/screenshots/privacy declarations correspond to that build;
- any release-changing binary fix reopens relevant acceptance tests;
- each review rejection/question becomes a tracked issue with the exact Apple finding and evidence.

### 9. Release after approval

Approval and public release are separate states when manual release is configured.

- public release remains a founder-controlled external action;
- after release, verify public listing, version, icon, metadata, download availability and public URL after App Store propagation.

## Minimum Product Owner checklist

A Product Owner must not mark an Apple submission package ready until all applicable items are PASS:

- [ ] reviewer-safe access path works on clean install;
- [ ] Sign in with Apple is visible and completes end-to-end when required;
- [ ] Hide My Email/private relay behavior is compatible;
- [ ] login does not expand identity/advertising data collection beyond declared/consented behavior;
- [ ] iOS auth remains in an Apple-appropriate system/in-app authentication session;
- [ ] permanent account deletion is directly discoverable in-app;
- [ ] full deletion passes E2E on a disposable account;
- [ ] privacy/consent/store declarations match exact behavior;
- [ ] compliance-critical UI is verified on iPhone and iPad/iPadOS layout;
- [ ] reviewer notes and evidence/video are ready;
- [ ] exact submitted build has passed the preflight.

## Origin evidence — Grzybołaz 1.0

The standard incorporates concrete App Review findings encountered during the Grzybołaz 1.0 launch:
- reviewer access/app completeness evidence was required;
- OAuth behavior had to stay in the system/in-app authentication session instead of unexpectedly handing off to standalone Safari;
- Sign in with Apple had to be visible/equivalent when Google login was offered;
- Apple evaluated equivalent-login privacy properties including data minimization, Hide My Email and advertising interaction collection without consent;
- the reviewer had to be able to find an in-app permanent account-deletion path;
- Apple requested video evidence showing the complete deletion process;
- the accepted replacement build was physically validated before resubmission.

These are portfolio learnings, not Grzybołaz-only exceptions.
