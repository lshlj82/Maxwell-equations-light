# Maxwell's Equations and Light

This is an interactive, browser-based demo of Maxwell's equations, electromagnetic waves, and the wave nature of light. It comes as two separate pages, one in English and one in Korean.

Created by **Claude Opus 5.5**, based on the lecture notes by **Sang Hoon Lee (이상훈)**.

> **한국어 요약:** 자기에 대한 가우스 법칙, 유도 자기장과 변위전류, 맥스웰 방정식, 전자기파와 그 속력, 간섭, 단일 슬릿 회절, 이중 슬릿 간섭을 직접 조작해 볼 수 있는 인터랙티브 웹 데모입니다. 이상훈(Sang Hoon Lee)의 강의 노트를 바탕으로 Claude Opus 5.5가 만들었습니다. 한국어 페이지는 `maxwell-ko.html`입니다.

## Files

| File | Description |
| --- | --- |
| `maxwell-en.html` | American English version |
| `maxwell-ko.html` | Korean version (한국어) |
| `README.md` | This file |

Each page is a single self-contained HTML file with inline CSS and JavaScript. There is no build step and there are no dependencies. The only external request is to Google Fonts for IBM Plex Sans KR. If that request fails, the page falls back to system fonts. Each page links to the other language from its top bar.

## Running it

Open either file directly in a modern browser, or serve the folder locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/maxwell-en.html
```

### Publishing on GitHub Pages

1. Push these files to a repository.
2. In **Settings → Pages**, choose **Deploy from a branch**, then select your branch and the root folder.
3. Visit `https://<user>.github.io/<repo>/maxwell-en.html` or `.../maxwell-ko.html`.

These pages can share a repository with the companion demos on DC circuits (`circuits-*.html`), RC circuits (`rc-*.html`), magnetism (`magnetism-*.html`), and induction and AC (`induction-*.html`). The file names don't collide.

## What's inside

The eight sections follow the order of the lecture notes. Every value is recomputed live as you move the controls.

1. **Gauss's law for magnetism:** You drag a closed surface around a bar magnet, and the page computes the outward flux, the inward flux, and the net flux numerically. The net magnetic flux stays at zero wherever the surface is. Switch to a +q/−q pair and the net electric flux becomes q<sub>enc</sub>/ε₀ instead.
2. **Induced magnetic fields and displacement current:** This shows a charging parallel-plate capacitor. The electric field between the plates grows, and the induced field B appears both around the wires and in the gap between the plates. The page gives dΦ<sub>E</sub>/dt and the displacement current i<sub>d</sub> = i. A graph of B(r) shows the inside region (∝ r) and the outside region (μ₀i/2πr, the same as for a wire).
3. **Maxwell's equations:** The four equations are shown on cards, each with a short explanation.
4. **Electromagnetic waves:** An animated traveling wave shows **E** and **B** perpendicular to each other and to the direction of travel. A separate view shows the fields at a fixed point P. A frequency slider runs across the spectrum from radio waves to gamma rays. For each frequency the page gives λ = c/f, ω, k, and B<sub>m</sub> = E<sub>m</sub>/c, and it shows the color for visible wavelengths.
5. **Wave speed:** A crest is tracked as it moves at v = ω/k = λf. A separate calculator gives $c = 1/\sqrt{\varepsilon_0 \mu_0}$, and you can rescale ε₀ and μ₀ to see what would happen.
6. **Wavelength and interference:** Two waves are shown with an adjustable path difference, along with their sum. Readouts give the phase difference and the amplitude, and say whether the result is constructive, destructive, or in between.
7. **Single slit:** The slit geometry is drawn with rays r₁ and r₂ and their path difference. The page plots the intensity pattern I/I₀ = (sin α/α)² with the dark fringes at a sin θ = mλ marked, and it shows a colored screen strip for the chosen wavelength.
8. **Double slit:** This section shows the geometry of S₁, S₂, and point P, with the path difference ΔL = d sin θ. The fringe pattern is drawn under a single-slit envelope, and readouts identify bright fringes (d sin θ = mλ) and dark fringes (d sin θ = (m + ½)λ) and give the fringe spacing λD/d. A small plot shows the two waves arriving at P and their sum.

## Notes on the model

- In the Gauss's law section, the bar magnet's field is modeled as a 2D cross-section of a solenoid, so its field lines close. The charges are 2D line charges. Fluxes are in relative units, and a small softening near the sources keeps the numbers finite.
- The electromagnetic-wave drawing is not to scale. The real wavelength appears in the readouts.
- Wavelength-to-color conversion uses a common approximate formula.
- Intensity patterns use the far-field (Fraunhofer) formulas: I ∝ (sin α/α)² for a single slit, and cos²β · (sin α/α)² for two slits.
- The pages follow the system light or dark setting. Under `prefers-reduced-motion`, the wave animation starts paused and the header animation stays still.

## Credits

- Lecture notes: Sang Hoon Lee (이상훈)
- Demo design and code: Claude Opus 5.5

## License

No license has been chosen yet. Before publishing, add a `LICENSE` file if you want others to be able to reuse the code. Also confirm with the author of the lecture notes how their material may be shared.
