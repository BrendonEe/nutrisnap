# NutriSnap

A free, mobile-first food diary and calorie estimator. No account, backend, paid API, or subscription is required.

## Features
- Chinese / English interface
- Photo upload and mobile camera capture
- Optional in-browser image classification using the open-source Transformers.js CLIP model (downloaded from the public CDN on first use)
- User confirms food name and portion, then edits calorie/macronutrient estimates
- Daily calorie and macro totals, editable goal, meal history, weight log
- Local browser storage and installable PWA shell

## Run locally
Open `index.html` from a local static server (recommended):

```bash
python3 -m http.server 8000
```
Then visit `http://localhost:8000`.

## Free public deployment with GitHub Pages
1. Create a public GitHub repository named `nutrisnap`.
2. Upload all files in this folder to the repository root.
3. In **Settings → Pages**, select **Deploy from a branch**, choose `main` and `/ (root)`, then Save.
4. GitHub will publish the site at `https://YOUR-USERNAME.github.io/nutrisnap/`.

No domain purchase is required. GitHub Pages is free for public repositories. The AI model is downloaded client-side from the jsDelivr public CDN; it is not hosted by this project. Model download requires an internet connection and may be large. The site remains usable with manual food entry if the model fails to load.

## Important limitations
- CLIP is a general image classifier, not a nutrition database or precise portion detector. It may misidentify mixed dishes.
- The calorie/macronutrient values are estimates based on rough food references; the user should confirm ingredients, cooking oil, sauces and portion size.
- Records are stored in the current browser's localStorage. They do not automatically sync across devices and may be lost if browser data is cleared.
- This static version has no server-side image upload, user accounts, or cloud backup.


## Goal guide update
The site now includes an optional age, height and weight-based training-goal guide. It calculates BMI as a screening reference only. For users under 20, it does not automatically recommend cutting or bulking because BMI should be interpreted using age- and sex-specific percentiles. For adults, the suggestion is deliberately cautious because BMI cannot distinguish muscle from fat.


## Personal nutrition targets (updated)
- Profile includes age, height, weight, sex used by the adult equation, daily activity and training focus.
- For adults aged 19+, estimated maintenance calories use the Mifflin–St Jeor resting-energy equation multiplied by an activity factor; goal adjustments are modest (+5% muscle gain, 0% maintenance/recomposition, -10% fat loss).
- Protein target for adults is estimated at 1.6 g/kg/day; carbohydrate and fat targets are derived from the calorie estimate.
- For users under 19, the adult calorie equation and calorie deficit/surplus are not applied. The site shows a youth-athlete protein reference range (1.2–1.6 g/kg/day) and recommends professional guidance for intentional weight changes.
- Estimates are educational only and may be inaccurate. The site stores profile and logs locally in the current browser.
