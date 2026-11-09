# PocketDeskies Privacy Policy

**Effective Date:** May 17, 2026
_Last updated: November 9, 2026_
**Version:** 1.3.0

PocketDeskies ("we," "our," or "us") is an Android app. Two tiny AI companions, MiNiMe and MiNiYou, float on top of whatever else is on your screen, and you can chat with them using your own Anthropic API key. This Privacy Policy explains what information the app collects, how it is used, and the choices you have. By installing or using PocketDeskies you agree to the practices described below.

**This policy covers the Android app.** There are separate macOS and web versions of PocketDeskies; they are not covered here and each has its own policy.

## Information We Collect

### Location Data

- PocketDeskies does not collect location data.

### Account Information

- **No PocketDeskies account exists.** There is no sign-up and no server of ours to sign in to.
- If you use companion chat, you paste in your own Claude API key from Anthropic. The key is stored on your device in `EncryptedSharedPreferences`, backed by the Android Keystore, and is sent only to Anthropic, in an `x-api-key` header, with your chat requests. **If the Keystore is unavailable on your device, the app refuses to write the key to disk at all** and holds it in memory for that session only, so it is gone when the app stops.

### Device Information

- Your companion settings, chosen theme, sound preference, onboarding state and the position you dragged each companion to are stored on your device.
- **The overlay cannot read your screen.** The draw-over-other-apps permission lets the app paint its companions on top of other apps. It grants no ability to see, capture or record what is underneath, and the app does not use accessibility services or screen capture.

## How We Use Your Information

### Location Sharing

- PocketDeskies does not use your location.

### What the App Does

- Draws the floating companions and keeps them running through a foreground service.
- Remembers your settings and each companion's last position, on your device.
- Sends a chat message to Anthropic when you type one, and only then.

### Service Improvement

- Crash reports go to Firebase Crashlytics, as described under Third Parties. We use them only to find and fix bugs.
- There is **no analytics or usage tracking** — no Google Analytics, no advertising SDK, no event logging of what you tap.
- We do not sell, rent or monetize your chats or settings. Your chats never reach us at all.

## Storage and Retention

### Data Storage

- Settings and preferences are stored on your device in the app's private storage. Your Anthropic API key is stored separately, encrypted, as described above.
- **Your chat history is not saved.** Conversations live in memory while the app is running and are gone when it stops; nothing writes them to disk.
- No Sudarshan Tech Labs server is used for any PocketDeskies data.

### Data Retention

- Local settings remain until you change them, clear app data, or uninstall the app.
- Crash reports held by Firebase Crashlytics are retained under Google's policy, not ours.

### Data Security

- Your settings sit in the app's private storage, protected by Android's application sandbox. Your API key additionally sits in `EncryptedSharedPreferences` under an Android Keystore key, with the no-disk fallback described above.
- The one host the app talks to for chat is `api.anthropic.com`, over HTTPS. The app's network security configuration sets `cleartextTrafficPermitted="false"` for that domain, so an unencrypted connection to it is refused rather than silently allowed.
- **Anyone holding your unlocked phone can open the app and use your API key**, because the app has no lock of its own. Protect the device with a screen lock, and revoke the key at `console.anthropic.com` if you lose the phone.

## Data Sharing

### Sharing With Other People

- **PocketDeskies has no accounts, no pairing and no sharing features.** Your companions are yours alone; there is nobody to share a conversation with.

### Third Parties

- **Anthropic Claude API (optional chat)**: when you send a message, the app posts to `https://api.anthropic.com/v1/messages` with your message, **every earlier message in that conversation**, and the companion's own instructions — a short system prompt telling the model it is a playful tiny companion on your screen. The model requested is `claude-opus-4-5`, with a 1024-token reply limit, streamed back. Your API key travels in the `x-api-key` header. Nothing is sent until you have pasted a key and sent a message. Because the call uses your own key, Anthropic processes it under your own account and terms: https://www.anthropic.com/legal/privacy
- **Firebase Crashlytics (Google)**: if the app crashes, a crash report is sent to Firebase Crashlytics. It can include the error details and stack trace, device model, Android version, app version and a Firebase installation identifier. **It is started automatically by the Firebase library and the app offers no in-app switch to turn it off**, so the only way to stop it is not to install the app. It is used only to find and fix bugs.
- Apart from these two, no PocketDeskies data is shared with third parties by Sudarshan Tech Labs.
- Tapping the privacy-policy link in the app opens this page in your browser, which is a request you chose to make.

We do **not** share your data with:

- Data brokers
- Unrelated advertising networks, unless advertising is explicitly listed above for this app
- Third parties unrelated to the app features described in this policy

## Permissions Used

### Required Permissions

* **SYSTEM_ALERT_WINDOW**: Used to display floating companions over other apps after you grant overlay permission. It draws on top; it does not read what is underneath.
* **FOREGROUND_SERVICE and FOREGROUND_SERVICE_SPECIAL_USE**: Used to keep the floating companion service running while you use other apps.
* **POST_NOTIFICATIONS and VIBRATE**: Used for the companion service's own notification and for haptic feedback.
* **INTERNET**: Used to send chat messages to the Claude API and crash reports to Firebase Crashlytics.

### Permissions added by Android libraries

The app declares the six above. The finished build requests one more, declared by a Firebase library rather than by the app's own code, and it appears in the permission list you see on the Play Store:

* **ACCESS_NETWORK_STATE**: added by `firebase-installations`, which Crashlytics depends on. It lets a library *check* whether a network exists before trying to send. It grants no ability to use one — that is `INTERNET`, which this app does declare, for the two purposes named above.

Verified against the merged manifest of the release build rather than the app's own manifest file: it requests exactly these seven permissions and no others. Two further permission names appear in that merged manifest, `DUMP` and `BIND_JOB_SERVICE`, but as guards on Firebase's own service components — requirements on anything trying to call them, not permissions this app requests — so they do not appear in the app's permission list.

### Optional Permissions

* Overlay and notification permissions are yours to grant or revoke in Android settings. Companion chat is optional and additionally requires you to supply your own API key.

## Your Rights and Controls

### Location Sharing Control

- No location sharing exists in PocketDeskies.

### Account Management

- There is no account to manage. Your Anthropic key is managed in your own Anthropic account at `console.anthropic.com`, where it can be revoked at any time.

### Data Access

- You can change or delete local settings in the app, and clear everything from Android Settings.

### GDPR Rights (EU Users)

If you are in the European Union, you have additional rights:

- **Right to Access**: Request a copy of your personal data
- **Right to Rectification**: Correct inaccurate data
- **Right to Erasure**: Request deletion of your data
- **Right to Restrict Processing**: Limit how we use your data
- **Right to Data Portability**: Receive your data in a portable format
- **Right to Object**: Object to certain types of processing

The only data we can reach is what Firebase Crashlytics holds about a crash, since chats and settings never leave your device. To exercise these rights, contact us using the methods in the Contact Us section.

### Permissions

- You can revoke Android permissions in Android Settings -> Apps -> PocketDeskies -> Permissions, and the overlay permission under "Display over other apps".
- Revoking the overlay permission stops the companions appearing. Revoking notifications stops the service notification.

## Children's Privacy

- Our app is **not intended for children under 13**.
- We do not knowingly collect data from children under 13.
- If you are a parent or guardian and believe your child has provided personal information, please contact us to request deletion.
- Parents and guardians should supervise children's use of apps that store personal content.

## Security

- Local data is protected by Android's application sandbox, and the API key additionally by `EncryptedSharedPreferences` under an Android Keystore key.
- Chat traffic goes to `api.anthropic.com` over HTTPS, with cleartext to that domain refused by the app's network security configuration.
- Third-party services named in this policy provide their own security controls and privacy policies.
- You are responsible for protecting your device with a screen lock and your Anthropic API key, which anyone with your unlocked phone could use.
- We do not sell your personal data.

## Changes to This Policy

We may update this Privacy Policy to reflect new features, legal requirements, or changes in our practices. Significant changes will be:

- Noted in the app release notes or repository when applicable
- Reflected with a new "Last updated" date
- Communicated in the app or project page if the change is significant

The "Last updated" date at the top of this policy indicates when revisions occurred. Continued use of the app after changes constitutes acceptance of the updated policy.

## Contact Us

If you have questions about this Privacy Policy, wish to request data deletion, or have privacy concerns:

* **GitHub Repository:** https://github.com/SUDARSHANCHAUDHARI/pocketdeskies-privacy-policy
* **Email:** sunny.sudarshan@gmail.com
* **Main App Repository:** https://github.com/SUDARSHANCHAUDHARI/PocketDeskiesAndroid

We will respond as quickly as possible, typically within 48 hours.

## Data Deletion

### How to Delete Your Account

There is no account. Almost everything the app keeps is local, so deletion is something you do yourself:

#### Option 1: In-App Deletion

1. Open PocketDeskies
2. Clear the API key field in Settings to remove the stored key
3. Closing the app discards the conversation, which was never saved

#### Option 2: Clear or Uninstall

1. Clear the app's data from Android Settings to remove the settings and the encrypted key
2. Uninstalling the app removes all of its local data
3. Revoke the API key at `console.anthropic.com` if you want it dead everywhere, not just on this phone

#### Option 3: Email Deletion Request

Send an email to: **support@sudarshantechlabs.com** or **sunny.sudarshan@gmail.com**

- Subject: "Data Deletion Request - PocketDeskies"
- The only thing we can delete is a Firebase Crashlytics crash report, so say roughly when the crash happened and on what device

### What Gets Deleted

- Your settings, companion positions and the encrypted API key, on clearing app data or uninstalling
- A Crashlytics crash report, if you ask us and we can identify it
- Nothing held by Anthropic — those requests were made with your own key, under your own account, so a deletion request for them goes to Anthropic

### Data Retention After Deletion

- **Immediate:** clearing app data removes the local settings and the stored key at once
- **Uninstall:** removes all app-private local data
- **Chats:** never stored, so nothing to delete
- **Crash reports:** retained by Google under its own policy until removed

## Third-Party Services

Two, and only one of them is optional:

- **Firebase Crashlytics (Google)**, for crash reports. Started automatically; no in-app opt-out.
- **Anthropic Claude API**, for companion chat, using an API key you supply yourself.

Floating companions and local settings need no cloud service at all. There is no advertising SDK, no analytics and no backend of ours.

Please review the relevant third-party policies:

- [Anthropic Privacy Policy](https://www.anthropic.com/legal/privacy)
- [Firebase Privacy and Security](https://firebase.google.com/support/privacy)
- [Google Privacy Policy](https://policies.google.com/privacy)
- [Google Play Terms](https://play.google.com/about/play-terms/)

## About PocketDeskies

PocketDeskies is built with privacy in mind. The app is built with:

- Kotlin and Jetpack Compose
- Android overlay and foreground service APIs, for companions that float above other apps
- `EncryptedSharedPreferences` for your API key, with no unencrypted fallback on disk
- The Anthropic Claude API for optional companion chat, using a key you supply
- Firebase Crashlytics for crash reports

What leaves your device is a chat message you typed, sent to Anthropic under your own key, and a crash report when the app breaks. Nothing else, and nothing to us.

---

**Last Updated:** November 9, 2026

---

## Recent Updates (Version 1.3.0 - November 9, 2026)

- **Removed the scaffold security claim.** The policy said data was "protected using platform security controls available on Android, the browser, Firebase, Google, GitHub, or other services" and told you to protect your "browser profile and Google/GitHub accounts". This is an Android app that uses no GitHub service and has no browser version; the real protections are the Android sandbox and `EncryptedSharedPreferences`, which are now named instead.
- **Said what the chat request actually contains**: the endpoint, the model, the token limit, the system prompt's purpose, your key in the `x-api-key` header, and the fact that **the whole conversation so far goes with every message**, not just the latest one. The previous wording said "earlier messages" without making that plain.
- **Said chats are never saved.** They live in memory and vanish when the app stops. That had never been stated, and it is the strongest privacy fact about the chat feature.
- **Said the Keystore fallback refuses to write the key to disk.** If `EncryptedSharedPreferences` cannot be created, the key is held in memory for that session only and an older build's plaintext copy is deleted — a deliberate design the policy never mentioned.
- **Said the overlay cannot read your screen.** `SYSTEM_ALERT_WINDOW` is the permission people fear most; it draws on top and grants no capture, and the app uses no accessibility service or screen recording.
- **Said Crashlytics has no in-app opt-out.** It is auto-initialized by the Firebase library and there is no toggle in the app, so the honest statement is that the only way to avoid it is not to install the app.
- **Listed the one permission a library adds.** The app declares six and the release build requests seven; `ACCESS_NETWORK_STATE` comes from `firebase-installations` and only lets a library check for a network. Verified against the merged release manifest. The names `DUMP` and `BIND_JOB_SERVICE` also appear in that file, but as guards on Firebase's service components rather than permissions the app requests, so they are not in its permission list.
- **Scoped the policy to the Android app**, and noted that the macOS and web versions are separate with their own policies.
- **Dropped the "Family Groups" heading** and the browser-app deletion steps, scaffold shared with sibling policies, for an app that has neither.

## Recent Updates (Version 1.2.0 - October 19, 2026)

- **Disclosed Firebase Crashlytics crash reporting and the optional Claude API chat feature.**

## Recent Updates (Version 1.1.0 - May 17, 2026)

- **Aligned policy with the shared privacy-policy structure.**
- **Clarified overlay behavior, local settings, and notification permissions.**
