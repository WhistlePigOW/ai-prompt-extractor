# AI Image Prompt Extractor

Drop in an AI-generated image or video and see the prompt, settings, LoRAs and workflow that made it.

**Use it online:** https://whistlepigow.github.io/ai-prompt-extractor/
(_Works entirely in your browser. Your images and videos are never uploaded, even when using the online version._)

**Or download it:** grab `AI_Image_Prompt_Extractor.html` from the [latest release](https://github.com/WhistlePigOW/ai-prompt-extractor/releases/latest), save it anywhere, and double-click it. It opens in your browser and works offline. Nothing to install.

## What it reads

| Format | Sources |
|---|---|
| PNG | ComfyUI (prompt + workflow), Automatic1111 / Forge, generic text chunks |
| JPEG | A1111 / Forge (EXIF UserComment), EXIF, XMP, comments |
| WebP (still and animated) | ComfyUI, A1111 / Forge, EXIF, XMP |
| MP4 / MOV | ComfyUI Save Video, VideoHelperSuite Video Combine |
| WebM / MKV | ComfyUI, VideoHelperSuite |

It pulls out the positive and negative prompt, seed, steps, CFG, sampler, scheduler, model, LoRAs (with strengths), resolution, and the full ComfyUI workflow JSON. You can copy the prompt or export everything as TXT or JSON.

## Privacy

Everything runs locally in your browser. Your files are never uploaded, and the page makes **no network requests at all**: no analytics, no external scripts, no fonts from the internet.

You can check this yourself: open your browser's developer tools (F12), go to the **Network** tab, then load an image. Nothing is sent anywhere.

The whole tool is one HTML file you can read top to bottom.

## Notes

- A prompt can only be recovered if the file still has its metadata. Most websites, chat apps, screenshots, editors, upscalers and video re-encodes strip it.
- ComfyUI saves WebP metadata as plain ASCII, so non-English characters in those prompts show up as `?`. PNG and video keep them.
- For VideoHelperSuite videos, `save_metadata` must be on when the video is saved.
- Works in current versions of Chrome, Edge, Firefox and Safari.

## Verify your download

Each release lists the SHA256 fingerprint of the file. On Windows, in PowerShell:

```powershell
Get-FileHash .\AI_Image_Prompt_Extractor.html -Algorithm SHA256
```

The result should match the hash shown on the release page.

## License

MIT. Free to use, share and modify. See [LICENSE](LICENSE).
