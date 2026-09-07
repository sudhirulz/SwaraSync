# SwaraSync™

**Speech Fluency Through Carnatic Music**

SwaraSync is a personalized speech therapy web app for adolescents who stutter, built around Carnatic music: phoneme-targeted swara (note) exercises and tempo-calibrated rhythmic recitation, delivered alongside conventional speech therapy rather than replacing it.

It is a research prototype, currently in testing, submitted as a science fair project under the **Translational Medical Science** category.

---

## What it does

1. **Two-part diagnostic** — the patient reads a phonologically balanced passage, then responds unscripted to a topic prompt for about a minute. Both recordings are analyzed separately, since rehearsed and spontaneous speech don't behave the same way.
2. **Acoustic fluency analysis** — each recording is scored in short windows using pause ratio, silence duration, speech rate, and pitch/amplitude stability (jitter, shimmer). A segment only counts as dysfluent when a genuine primary signal is present, not from voice-quality noise alone.
3. **Personalized prescription** — the analysis generates an individual practice plan: which specific phonemes to target, and a starting practice tempo calculated as a percentage of the patient's own fluent speaking rate, not a fixed number.
4. **Phoneme track** — problem sounds are grouped into real articulatory families (stops, nasals, fricatives, glides, vowels), and the patient sings the actual target sound on a Carnatic scale, using the scale purely as a pitch and breath scaffold rather than a symbolic substitute.
5. **Rhythm track** — six levels of increasing rhythmic complexity grounded in Carnatic tala structure, delivered with tabla and tanpura accompaniment.
6. **Adaptive progression** — practice tempo rises automatically as fluency improves; advancing to the next level requires three passing sessions at a set threshold, not a single attempt.
7. **Progress dashboard** — saves each patient's prescription and level progress between visits, so returning users pick up where they left off instead of starting over.

## Why

Stuttering affects roughly 1% of the population persistently, and access to speech therapy remains limited, particularly in low-resource settings. A 2025 peer-reviewed pilot study found that reciting Thiruppugazh, a rhythmically structured Tamil devotional poem, reduced stuttering severity in adolescents — but that finding was never turned into a personalized, usable tool. SwaraSync is an attempt to do that: translate a validated but static intervention into something individually adaptive, and test whether it adds measurable benefit on top of conventional therapy.

## Try it

Open `index.html` directly in a browser, or visit the [GitHub Pages link](#) *(update once deployed)*.

A few things to know before testing:
- **Microphone access requires a secure context.** It works over `https://` (GitHub Pages) or `localhost`, but not when the file is opened directly (`file://`) in most browsers. If you see a mic-blocked error locally, either serve it with `python3 -m http.server 8000` or use the "Upload practice audio" option instead.
- **Progress is saved in the browser's local storage**, tied to that specific browser and file location. Clearing browser data, or moving/re-downloading the file, will lose saved progress.
- Works on both desktop and mobile browsers; no installation or account required.

## Tech notes

- Single self-contained HTML file — no backend, no build step, no external dependencies beyond one CDN script (jsPDF, for the downloadable diagnosis report) and Google Fonts.
- Audio (tabla strokes, tanpura drone) is real recorded audio, not synthesized, embedded directly in the file.
- PDF reports are generated client-side and downloaded locally; nothing is sent to a server.

## Status and limitations

This is an active pilot, not a validated clinical tool. Specifically:

- The acoustic fluency scorer is a heuristic proxy for clinical measures like the SSI-4, not a validated equivalent — it has not been benchmarked against clinician scoring.
- Testing so far has involved a small number of participants, not a randomized controlled sample.
- SwaraSync is designed to **complement**, not replace, guidance from a licensed speech-language pathologist. The generated report states this explicitly.

Planned next steps: recruiting a larger test group with a proper comparison arm (conventional therapy alone vs. therapy plus SwaraSync), adding a "Speech Bridge" track to help carry fluency gains from sung/rhythmic practice into ordinary conversation, and expanding phoneme coverage.

## Research basis

- Naachimuthu, K.P. & Savya, N. (2025). *Thiruppugazh As A Therapeutic Intervention In Reducing Stuttering Among School Children.* International Journal of Stress Management, 32(2), 35–58.
- McReynolds, L.V. & Bennett, S. (1972). Distinctive feature generalization in articulation training. *Journal of Speech and Hearing Disorders.*
- Additional references available in the full project write-up.

## License

*To be determined.* Please do not redistribute or reuse without contacting the author until a license is added here.

## Disclaimer

SwaraSync is a student research project. It is not a certified medical device and has not been reviewed or approved by any health authority. If you or someone you know stutters, please consult a licensed speech-language pathologist.
