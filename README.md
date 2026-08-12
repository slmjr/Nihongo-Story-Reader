# Nihongo Story Reader

Nihongo Story Reader is a standalone, no-build browser app for creating Japanese reading practice at a chosen JLPT level. It combines generated stories with contextual furigana, English translations, study notes, and paragraph-by-paragraph speech.

**[Use it online](https://slmjr.github.io/Nihongo-Story-Reader/)** · **[Download the single HTML file](https://github.com/slmjr/Nihongo-Story-Reader/releases/latest/download/index.html)**

## Features

- Choose JLPT levels N5 through N1.
- Choose **Very short**, **Short**, or **Standard** story length.
- Set a theme and select polite or casual Japanese.
- Display contextual furigana **Always**, only as a **Hint**, or keep it **Hidden**.
- Reveal English translations one paragraph at a time or all at once.
- Review generated vocabulary and grammar notes.
- Listen to individual paragraphs. Venice speech is attempted when Venice is selected and a key is available; otherwise the app falls back to Japanese speech synthesis provided by the browser.
- Load the included N3 sample story without an API key.
- Copy the current story and translations as plain text.

## Run it

There are no packages to install and no build step.

1. Download `index.html` (or download the repository).
2. Open `index.html` in a modern browser.
3. Select **Load sample story** to explore the reader without credentials.
4. To generate a new story, choose a provider, enter its API key and model where required, then select **Generate**.

The app is a single local HTML file. Some provider or browser security policies may reject requests made from a `file://` page. If that happens, use a simple local static server and open the page through `http://localhost`; no build is required. The selected provider must also permit browser requests (CORS).

## Providers

The app sends Chat Completions-style requests directly from the browser:

- **Venice** uses the endpoint and default model configured in the app.
- **OpenAI API** uses OpenAI's Chat Completions endpoint and the model shown in the app.
- **Custom API** accepts a user-supplied OpenAI-compatible Chat Completions endpoint, model, and optional bearer token.

You are responsible for credentials, provider access, usage limits, and charges. **OpenAI API usage is billed separately from a ChatGPT subscription.** Model names and provider behavior can change, so adjust the model field when needed.

## API-key safety and privacy

Keys are kept in browser `sessionStorage` by default, rather than being written into this repository. In normal browser behavior, that limits them to the current browser tab/session. Selecting **Remember the key on this device** stores that provider's key in `localStorage` until it is removed.

This is a browser-only app, so it cannot fully conceal a key from browser code, developer tools, extensions, malware, or another person using the same browser profile. Use restricted, low-limit, or easily revocable keys; avoid shared devices; and enable **Remember** only on a device you trust. Keys are sent to the provider endpoint selected in the interface. Review custom endpoint URLs carefully before sending a request.

See [SECURITY.md](SECURITY.md) for more guidance.

## Accuracy and testing notes

Generated Japanese, contextual readings, translations, vocabulary, and grammar notes can be incomplete or wrong. Check generated material before relying on it, ideally with a qualified Japanese speaker or teacher. This app is a practice aid, not an authoritative language reference.

Release preparation included JavaScript syntax checks and end-to-end browser tests against a local mock Chat Completions provider. It did **not** send live requests to Venice or OpenAI. Successful generation still depends on the provider, account, model, network, browser, endpoint compatibility, and CORS policy. Speech support also varies by browser and operating system.

## Optional support

Every feature remains free. If the app is useful, optional support is available through [Ko-fi](https://ko-fi.com/smjp53096) or the donation controls included in the app. Cryptocurrency transfers cannot be reversed; verify the network and full address before sending.

## License

Licensed under the [MIT License](LICENSE). Copyright (c) 2026 Stephen.
