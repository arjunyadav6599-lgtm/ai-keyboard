# Arjun AI Keyboard

An Android custom keyboard (IME) starter project inspired by the supplied screenshot. It includes a dark keyboard, basic typing keys, and Gemini-powered grammar correction, rewriting, translation, and reply generation.

## Requirements
- Android Studio (current stable)
- JDK 17
- Android SDK Platform 35
- Internet connection for Gemini AI actions

## Build the APK
1. Open this `ArjunAIKeyboard` folder in Android Studio.
2. Allow Gradle sync and install any requested Android SDK components.
3. Select **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
4. The debug APK will be at `app/build/outputs/apk/debug/app-debug.apk`.

Alternatively, from a terminal with Gradle installed:

```bash
gradle assembleDebug
```

## Install and enable
1. Install the generated APK on your Android phone.
2. Open **Arjun AI Keyboard** from the app list.
3. Create a Gemini API key at https://aistudio.google.com/ and paste it into the API key field, then save.
4. Tap **Enable keyboard** and enable Arjun AI Keyboard in Android settings.
5. Tap **Choose Arjun AI Keyboard**, select it, then open WhatsApp or another app and type.
6. Type text, then use **Fix**, **Rewrite**, **Translate**, or **✦ AI**.

## Privacy and security
- Ordinary key presses are handled locally by the keyboard.
- When you tap an AI action, the text before the cursor (up to 4,000 characters) is sent to Google's Gemini API using the API key you supplied.
- Do not send passwords, payment details, private identifiers, or other sensitive content to AI actions.
- The API key is stored in this app's private SharedPreferences on the device. This prototype does not include encrypted key storage, account login, or a backend proxy. For a public release, do not ship a shared API key in the app; use a secure backend with rate limits and abuse protection.
- The keyboard is a prototype. Review Android IME behavior and test across target apps/devices before publishing.

## Current prototype limitations
- English QWERTY layout with a basic symbol toggle; no swipe typing, predictive suggestions, autocorrect dictionary, multilingual layouts, or emoji panel.
- Translation targets currently include Hindi, English, French, Spanish, German, and Japanese.
- AI replacement replaces the text before the cursor in the active field. Check the result before sending.
- A working APK must be built with Android Studio/Android SDK; this environment does not have the Android build toolchain installed.
