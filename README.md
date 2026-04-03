# Privacy Policy — PocketDeskies

**Last updated:** 2026-04-03
**Developer:** SudarshanTechLabs
**Contact:** sudarshantechlabs@gmail.com
**Location:** Bangkok, Bangkok, Thailand

---

## 1. Overview

PocketDeskies ("the App") is developed and maintained by SudarshanTechLabs. This Privacy Policy explains what data the App collects, how it is used, and your rights as a user.

We are committed to protecting your privacy. **PocketDeskies does not collect, store, or sell any personal data.**

---

## 2. Data Collection

PocketDeskies does **not** collect any personal data. Specifically:

- We do **not** collect your name, email, phone number, or any account information
- We do **not** collect usage analytics or crash reports via third-party services
- We do **not** collect device identifiers, advertising IDs, or location data
- We do **not** track your activity inside or outside the App

### Data stored locally on your device

The following data is stored **only on your device** using Android SharedPreferences and is never transmitted to our servers:

| Data | Purpose |
|------|---------|
| Claude API key | To authenticate requests to Anthropic's API |
| Selected theme | To restore your visual preference |
| Character positions | To restore companion positions on screen |
| Sound/vibration toggle | To restore your notification preference |
| Onboarding completion flag | To skip onboarding on subsequent launches |

This data remains on your device and is deleted when you uninstall the App.

---

## 3. Claude API & Anthropic

PocketDeskies uses the **Claude API** provided by **Anthropic, PBC**. When you send a message to a companion:

- Your message and conversation history are transmitted directly from your device to Anthropic's API servers
- This transmission is encrypted via HTTPS
- SudarshanTechLabs does **not** receive, store, or process your messages
- Your data at Anthropic is governed by **Anthropic's Privacy Policy**: https://www.anthropic.com/privacy

You use your own API key, which means you control your Anthropic account and its associated data.

---

## 4. Third-Party Services

PocketDeskies integrates with:

| Service | Provider | Purpose | Privacy Policy |
|---------|----------|---------|----------------|
| Claude API | Anthropic, PBC | AI chat responses | https://www.anthropic.com/privacy |

No other third-party analytics, advertising, or tracking SDKs are included in the App.

---

## 5. Permissions

The App requests the following Android permissions:

| Permission | Why it's needed |
|-----------|----------------|
| `SYSTEM_ALERT_WINDOW` | To display floating companions above other apps |
| `FOREGROUND_SERVICE` | To keep companions running while you use other apps |
| `FOREGROUND_SERVICE_SPECIAL_USE` | Required by Android for overlay foreground services |
| `INTERNET` | To send messages to the Claude API |
| `VIBRATE` | To vibrate briefly when Claude finishes a response |
| `POST_NOTIFICATIONS` | To show the persistent companion status notification (Android 13+) |

No permissions are used for tracking, advertising, or data collection.

---

## 6. Children's Privacy

PocketDeskies is not directed at children under the age of 13. We do not knowingly collect personal information from children. If you believe a child has provided information through the App, please contact us and we will address it promptly.

---

## 7. Data Security

- All communication with the Claude API is encrypted via HTTPS/TLS
- API keys are stored locally using Android's SharedPreferences (not in plaintext on external storage)
- We have no servers, databases, or backend — there is no server-side data to secure or breach

---

## 8. Data Retention

We do not retain any data. All preferences stored on your device are removed when you uninstall the App.

---

## 9. Your Rights

Since we do not collect personal data, there is no data for us to provide, correct, or delete. If you have concerns about data processed by Anthropic, please contact them directly at https://www.anthropic.com/privacy.

---

## 10. Changes to This Policy

We may update this Privacy Policy from time to time. Changes will be reflected in the "Last updated" date above. Continued use of the App after changes constitutes acceptance of the updated policy.

---

## 11. Contact Us

If you have any questions about this Privacy Policy, contact us at:

**SudarshanTechLabs**
📧 sudarshantechlabs@gmail.com
📍 Bangkok, Bangkok, Thailand
