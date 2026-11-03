# NutriSnap 3.0

A free, mobile-first, Chinese/English food diary and nutrition-estimation PWA. No account, backend, paid API, or subscription is required.

## What's included
- Chinese / English interface and responsive mobile layout.
- Food photo upload and mobile camera capture.
- Optional in-browser image classification with the open-source Transformers.js CLIP model. The model is downloaded from a public CDN on first use and may be large.
- User confirmation of food name, portion, meal type, cooking method, ingredients and nutrition values.
- Approximate nutrition references for selected common foods; unknown foods are not silently assigned a generic nutrition value.
- Daily calorie, protein, carbohydrate and fat totals with progress bars.
- Personal profile and cautious adult nutrition-target estimates.
- Meal history by date; edit and delete meal records.
- Weight log with a trend chart; delete individual weight entries.
- Favorite foods for faster logging.
- JSON backup export and import.
- PWA install support and offline app shell.

## Deploy with GitHub Pages
1. Extract this ZIP on your phone or computer.
2. Open your public `nutrisnap` GitHub repository.
3. Upload **all files inside this folder** to the repository root, replacing files with the same names. Do not upload the outer folder itself.
4. Commit the changes to the `main` branch.
5. Wait for GitHub Pages to redeploy, then open the existing Pages URL. If an old version remains, close the installed web app and reopen it after refreshing Safari.

## Privacy and data
- Food photos are processed in the browser. The CLIP model is downloaded from jsDelivr on first use; the photo itself is not uploaded by this static app.
- Food logs, profile and weight records are stored in the current browser's localStorage. They do not sync between devices and can be lost if browser site data is cleared.
- Use **Data & Privacy → Export backup** regularly. Keep the JSON backup somewhere safe. Import is available in the same browser or another browser.
- Do not enter passwords, payment details or sensitive personal information.

## Important limitations
- CLIP is a general image classifier, not a dedicated food-recognition, ingredient-detection or portion-measurement model. Its similarity score is not a probability that the prediction is correct.
- Nutrition values are estimates, not laboratory measurements. Ingredients, sauces, oil and portion size can change values substantially. Review and edit every result.
- The built-in reference table covers only selected foods. For unmatched foods, enter nutrition values manually rather than relying on a guessed default.
- Adult calorie targets use a general equation and activity multiplier, not a clinical assessment. For users under 20, the app avoids setting a calorie deficit/surplus from adult BMI and recommends professional guidance for intentional weight change.
- This is a static client-side app: no accounts, cloud sync or server-side backup.

## Local testing
Run from a local static server (service workers do not work from `file://`):

```bash
python3 -m http.server 8000
```
Then visit `http://localhost:8000`.
