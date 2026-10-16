---
title: Dark Neuron Privacy Policy
---

# Dark Neuron Privacy Policy

**Effective date:** October 15, 2026
**Developer:** Dark Neuron
**App:** Dark Neuron for Android (`com.darkneuron.app`)

This policy explains what information the Dark Neuron app ("the app", "we") uses, why, where it goes, and the choices you have. Dark Neuron has **no user accounts, no ads, no analytics or tracking SDKs, and no crash-reporting SDKs**, and we **do not sell or share personal data** for advertising.

## 1. Summary

| Feature | What is involved | Where it is stored | How long |
|---|---|---|---|
| Dark DM (private chat) | Random anonymous ID, a random 6-character code, messages and replies you send, likes/dislikes, a push notification token, the codes you block | Google Firebase (Cloud Firestore) | Messages expire after 24 hours and are deleted |
| Dark Chat (public room) | A separate random 6-character chat name, messages, replies, likes/dislikes, reports | Google Firebase (Cloud Firestore) | Expire after 24 hours and are deleted |
| Reports | The code or chat name you report and your own code/chat name | Google Firebase (Cloud Firestore) | Reviewed by the developer, then deleted |
| Notes, contacts, calendar, nicknames, blocked/muted names, settings | What you type into the app | Only on your device | Until you delete them or uninstall |
| News, crypto prices, weather, air quality, speed test | Network requests to public services | Not stored by us | — |

## 2. Information stored on our backend (Google Firebase)

Dark DM and Dark Chat use **Google Firebase Authentication (anonymous sign-in)** and **Cloud Firestore**, operated by Google LLC.

- **Anonymous identifier.** When you first open Dark DM or Dark Chat, the app signs in anonymously and Firebase assigns a random user ID. It is not linked to your name, email, phone number or Google account.
- **Codes and chat names.** The app generates a random 6-character Dark DM code and a separate random 6-character Dark Chat name. Each is stored with your anonymous ID so it can be restored on the same installation. Your chat name is not publicly linked to your DM code or anonymous ID.
- **Dark DM messages.** Text you send, sender code, timestamps and expiry time. Only the two participants can read a conversation.
- **Dark Chat content.** Messages and replies (sender chat name, text, timestamps, expiry time, short quoted snippet of the message being answered), like/dislike votes and abuse reports (stored under your chat name, readable only by you), and counters (replies, likes, dislikes, reports). Dark Chat messages and replies are **public to all app users**. Do not post personal information.
- **Push notification token (Dark DM).** To notify you of new Dark DM messages, the app stores a Firebase Cloud Messaging (FCM) registration identifier with your anonymous ID. A Google Cloud Function (Cloud Functions for Firebase, region us-central1, United States) uses it to send a notification that contains only the sender's 6-character code and whether it is a message or a reply - never the message text. Invalid tokens are removed automatically; uninstalling the app stops notifications.
- **Server location.** Firebase and Cloud Functions data is processed by Google on servers in the United States (us-central1 region for functions). An hourly server job deletes expired content.
- **Network information.** Like any online service, Google's servers process technical data such as your IP address and device/SDK information needed to deliver the service. See Google's privacy policy: <https://policies.google.com/privacy> and Firebase privacy information: <https://firebase.google.com/support/privacy>.

**Retention.** Messages, replies, votes and reports in Dark DM and Dark Chat expire **24 hours** after they are sent (replies expire with the message they answer). Expired data is deleted automatically on the server (usually within about an hour, at most about a day after expiry) and may also be removed manually by the developer. Items in Dark Chat that receive 3 reports are permanently deleted. Your anonymous ID, code and chat name remain until deleted on request (see Section 9).

## 3. Reports and moderation

You can report a Dark Chat message or reply, or a Dark DM code. Dark Chat reports are counted on the item; an item with 3 reports is permanently deleted. Dark DM reports store the reported code and your own code and can only be read by the developer in the Firebase console, to investigate abuse. You can also block a code or chat name. Dark Chat block lists are stored only on your device; your Dark DM block list is also saved with your anonymous ID so the server does not send you notifications from blocked codes.

## 4. Information stored only on your device

Notes, contacts and calendar entries you create in the app, nicknames you give to chats, blocked codes and names, your own votes/seen markers, theme, language, units, news topics and other settings are stored **locally on your device** and are never uploaded by us. The app does **not** read your phone's address book, calendar, photos, files or location.

## 5. Third-party services the app contacts

To show content, the app sends requests directly from your device to these public services. They receive your IP address and the request itself (e.g. a search topic or city coordinates); we do not receive or store these requests.

- **News:** Google News RSS (news.google.com) — the topics you follow are sent as search queries.
- **Crypto prices and data:** CoinGecko, Coinbase Exchange, CoinLore, Alternative.me (Fear & Greed index), Blockchain.com and Blockstream.
- **Weather and air quality:** Open-Meteo (geocoding, forecast and air-quality APIs). The city name you search and its coordinates are sent to look up the forecast. The app does **not** use your device's GPS/location.
- **Speed test:** Cloudflare (speed.cloudflare.com) — test data is downloaded/uploaded to measure your connection.

Each service has its own privacy policy.

## 6. News alerts

News alerts are **on by default** after install. The app itself checks your selected news topics in the background (by default up to 24 times a day) by requesting Google News RSS directly from your device, and shows a local notification for new headlines. No push server is involved and nothing about your topics is sent to us. You can turn alerts off, change how often they run, or choose topics in **Tools**, and you can disable notifications in Android settings at any time.

## 7. Permissions

- **Internet / network state:** to load content and use chat features.
- **Notifications** (optional, Android 13+ asks you): for news alerts (on by default; see Section 6). Dark DM also sends push notifications for new messages and replies (see Section 2). Dark Chat does **not** send push notifications.
- **Run at startup:** to keep scheduled news alerts working after a reboot.

## 8. Security

All network traffic uses HTTPS/TLS. Firestore security rules restrict who can read and write each document (for example, only DM participants can read a conversation, and report documents cannot be read by other users). No method of transmission or storage is 100% secure, but we take reasonable steps to protect data.

## 9. Your choices and data deletion

- **Local data:** delete items in the app, clear the app's storage, or uninstall the app.
- **Chat content:** you can delete your own messages and replies at any time; everything else expires after 24 hours.
- **Server data:** to request deletion of your anonymous ID, code or chat name, open an issue at <https://github.com/Dark-Neuron/dark-neuron-privacy/issues> with your 6-character code or chat name (do not post other personal information). After uninstalling, your old anonymous ID is no longer used.

## 10. Children

Dark Neuron is not directed to children under 13, and we do not knowingly collect personal information from children. If you believe a child has provided personal information, contact us and we will delete it.

## 11. Changes to this policy

We may update this policy. Changes will be posted on this page with a new effective date.

## 12. Contact

Questions or requests: <https://github.com/Dark-Neuron/dark-neuron-privacy/issues>
