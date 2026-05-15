# Healthcare Cost Analysis — Key Insights

## 1. Distribution of Medical Charges
Medical charges are right-skewed — most people sit in a modest cost range, but a small high-cost tail pulls the average up significantly. That tail is where most of the risk lives.

---

## 2. Smoking — The Dominant Cost Driver
Smokers average ₹32,050 in charges versus ₹8,434 for non-smokers — nearly 4× higher. More strikingly, 100% of smokers fall in the high-cost category, compared to just 37% of non-smokers. Smoking status alone is essentially a perfect flag for high expenditure.

---

## 3. BMI and Smoking Together
BMI on its own has a weak correlation with charges (r = 0.19). But combined with smoking, the effect compounds sharply — obese smokers average ₹41,693, the highest of any group in the dataset. The two risk factors together are far more dangerous than either alone.

---

## 4. Age
Costs rise steadily with age (r = 0.29). Senior smokers (60+) are the most expensive segment at ~₹38,930 on average. Smoking accelerates the cost curve at every age bracket, not just among the elderly.

---

## 5. Regional Variation
Some variation in average charges exists across the four regions, though it's less pronounced than the lifestyle-driven factors. Regional differences likely reflect local pricing and risk-factor prevalence rather than any structural gap.

---

## 6. Model Performance
A Linear Regression model on age, BMI, smoking status, and region achieved R² = 0.81 with an MAE of ~$4,108. Solid performance for a simple model — the features chosen are genuinely predictive.

---

## 7. Feature Importance

| Feature | Cost Impact |
|---|---|
| Smoking status | +$19,400 |
| Obese BMI | +$6,000 |
| Overweight BMI | +$2,700 |
| Age (per year) | +$187 |
| Gender, children, region | Negligible |

Smoking is the single biggest lever — 3× the impact of obesity, and the only feature that consistently separates high-cost patients from the rest.

---

## Summary

| Finding | Magnitude | Implication |
|---|---|---|
| Smokers vs. non-smokers | 4× higher costs | Smoking cessation = highest ROI intervention |
| 100% of smokers are high-cost | Perfect predictor | Use in risk stratification |
| Obese smokers | ~₹41,693 avg charges | Dual-risk patients need priority targeting |
| Senior smokers | ~₹38,930 avg charges | Age + smoking = highest risk segment |
| Model R² = 0.81 | Strong fit | Features reliably predict cost |
| Smoking coefficient | +$19,400 | Largest cost driver in the model |
