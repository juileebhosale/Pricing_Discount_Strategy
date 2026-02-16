# Pricing Discount Strategy for Enterprise Identity Product Company

**Author:** Juilee B  
**Project Type:** Data-Driven Pricing Optimization Analysis

---
![](images/Problem-Statement.png)
## 📊 Executive Summary

Analyzed 3 years of company M's deals across 3 regions and 5 product lines to recommend discount optimization opportunities which unlock **$6.7B revenue impact**.

### Key Findings

- **Revenue declining faster than deal volume** while discounts increased by 22% - pointing to pricing strategy being a cause of revenue erosion vs demand weakness
- Although average discount per deal is ~30%, we are **leaking ~75% of listing revenue** concentrated in top 5-10% of high volume deals
- **Lifecycle Management is under-tapped** and represents a high-revenue upsell opportunity
- **APAC discounts are materially higher** without corresponding gains in volume or ARR, signaling mispriced regional strategy

### Recommendations

- Using data-driven models can reduce outsized discounts and unlock **$1.8B in ARR**
- Capping discounts at 50% for top 5% accounts can generate **$3.7B in additional ARR**
- Prioritize Lifecycle Management in deal bundles to drive revenue uplift without increasing discount pressure
- Recalibrating APAC discounts can bring in **$1.2B in additional ARR**

---

## 🎯 Problem Statement

**Making Company M's discount strategy more data-driven and robust**

Company M is a leading provider of Identity Access Management (IAM) solutions. Each product has a list price per user, but account executives (AEs) will often offer discounts based on deal size and other customer characteristics.

The executive team believes there is opportunity to improve how AEs discount products, and they want to build an analytical model that recommends the optimal discount for each new customer.

---

## 🔍 Key Insights

### 1. Revenue Declining Faster Than Deal Volume

![Revenue Decline Analysis](images/revenue-decline-chart.png)
*Year-over-year comparison of deal volume, ARR, and average discount trends*

- Annual recurring revenue has declined **-30%** since 2022
- Deal volume has declined only **-10%** during the same period
- List and contract prices remained flat, ruling out product repricing as the primary driver
- However, **average discounts increased 22%**, materially compressing realized revenue per deal

**Conclusion:** Discount expansion is contributing to revenue decline more than demand weakness. Without volume gains, discounting strategy will result in negative growth.

### 2. Revenue Leakage Concentrated in High-Volume Deals

![Revenue Leakage Analysis](images/revenue-leakage-chart.png)
*Average discount per deal vs actual revenue lost across product lines*

![Discount Distribution](images/discount-distribution.png)
*Distribution of revenue and deals across discount bins*

- Although majority of deals are discounted between 25-30%, a subset of high volume deals are discounted >50%
- These few large deals account for **75% of listing revenue leakage**
- **7.2% of deals** accounting for 80% of revenue have discounts greater than 50%
- Our steepest discounts (75%+) are applied to accounts generating more than 60% of revenue

**Conclusion:** Revenue erosion is concentrated in top 5-10% of high volume deals with disproportionately high discounts.

### 3. Lifecycle Management: Untapped Revenue Stream

![Product Performance](images/product-performance-bubble.png)
*Product performance analysis: deals vs ARR (bubble size = average list price)*

- Lifecycle Management generates **~23% of total revenue** despite being included in only **~45% of deals**
- In contrast, Single Sign-On appears in **83% of deals** but contributes a similar ~22% of revenue, indicating lower monetization efficiency

**Conclusion:** Prioritize lifecycle management in deal bundles—particularly for large accounts—to drive revenue lift.

### 4. APAC Over-Discounting Without ROI

![Regional Discount Heatmap](images/apac-discount-heatmap.png)
*Average discount % by region and sales segment*

- APAC exhibits the deepest average discounts, yet also delivers the lowest deal volume and ARR
- Sales Segment A receives the highest discounts globally, with APAC discounts **~13% above the global average**

**Conclusion:** Elevated discounting in APAC has not improved performance, suggesting price sensitivity is being overestimated.

---

## 📈 Discount Drivers Analysis

![Feature Importance](images/feature-importance.png)
*Feature importance in predicting discount % (Linear Regression coefficients)*

### Linear Regression Model Results

**Deal size and region are key drivers behind AE discount strategy:**

- **Deal size (quantity per deal)** is the strongest predictor of discounting, with larger customers receiving materially higher discounts
- **Region** is a key driver, with APAC consistently receiving steeper discounts even after controlling for other factors
- **Contract length and sales segment** are secondary drivers, with longer-term contracts associated with higher discounts

---

## 💡 Recommendations & Revenue Impact

### 1. Data-Driven Discount Model ($1.8B ARR)

![Revenue Gain Potential](images/revenue-gain-model.png)
*Revenue gain $ vs current discount % with average predicted discount overlay*

A simple linear regression prediction model increases ARR by **$1.8B** by improving discounts across 6K deals (>40% of total deals).

**How it works:**
- The model mainly corrects for over-discounting on high revenue deals
- Maintains deal competitiveness while optimizing pricing
- Model details available in appendix

### 2. Cap Discounts for Top Accounts ($3.7B ARR)

![Discount Cap Impact](images/discount-cap-impact.png)
*Projected ARR if discount is capped at 50% across all discount bins*

Capping discounts at 50% maximizes revenue while maintaining deal competitiveness.

**Implementation:**
- Target highest revenue generating accounts (2.6% of total) that currently have steepest discounts (>75%)
- Generates **$3.7B in additional ARR**

### 3. Recalibrate APAC Discounts ($1.2B ARR)

![APAC Revenue Opportunity](images/apac-revenue-gain.png)
*Revenue gain potential by region and year*

Reducing APAC discounts to align with performance metrics can bring in **$1.2B in additional ARR**.

**Regional breakdown:**
- 2022: $455.6M (AMER), $95.3M (APAC), $148.4M (EMEA)
- 2023: $381.8M (AMER), $101.0M (APAC), $156.2M (EMEA)
- 2024: $359.6M (AMER), $67.6M (APAC), $109.6M (EMEA)

### 4. Prioritize Lifecycle Management

Bundle Lifecycle Management—particularly for large accounts—to drive revenue uplift without increasing discount pressure.

---

## 🛠️ Technical Implementation

### Technologies Used
- **Python** for data analysis and modeling
- **Linear Regression** for discount prediction
- **Statistical Analysis** for feature importance

### Model Performance

![Model Results](images/model-performance.png)
*Training and test set: Actual vs Predicted discount % with R² values*

- **Training Set R²:** 0.4706
- **Test Set R²:** 0.5036

### Links
- [Python Notebook - GitHub](https://github.com/juileeb) *(placeholder - update with actual link)*

---

## 📁 Repository Structure

```
pricing-discount-strategy/
├── README.md
├── images/                          # Screenshots and visualizations
│   ├── revenue-decline-chart.png
│   ├── revenue-leakage-chart.png
│   ├── discount-distribution.png
│   ├── product-performance-bubble.png
│   ├── apac-discount-heatmap.png
│   ├── feature-importance.png
│   ├── revenue-gain-model.png
│   ├── discount-cap-impact.png
│   ├── apac-revenue-gain.png
│   └── model-performance.png
├── notebooks/
│   └── discount_analysis.ipynb
├── data/
│   └── [company data - not included for confidentiality]
├── models/
│   └── linear_regression_model.pkl
└── visualizations/
    └── [additional charts and graphs]
```

---

## 🖼️ How to Add Images to Your GitHub README

### Step-by-Step Guide:

1. **Create an `images` folder** in your repository root:
   ```bash
   mkdir images
   ```

2. **Save your screenshots** to the `images` folder:
   - Take screenshots of charts from your PDF or recreate them
   - Name them exactly as referenced in the README (e.g., `revenue-decline-chart.png`)
   - Recommended formats: PNG (for charts/screenshots) or JPG (for photos)

3. **Add images to your repository**:
   ```bash
   git add images/
   git commit -m "Add visualization screenshots"
   git push
   ```

4. **Image syntax in markdown**:
   ```markdown
   ![Alt text describing the image](path/to/image.png)
   *Optional caption in italics*
   ```

### Tips for Great Screenshots:

- **High resolution**: Use at least 1920x1080 for charts
- **Crop properly**: Remove unnecessary white space
- **Consistent style**: Use the same color scheme across all charts
- **File size**: Compress images to keep repo size manageable (use tools like TinyPNG)
- **Descriptive names**: Use kebab-case names that clearly describe the content

### Alternative: Using Raw GitHub URLs

If you want to reference images from a different location:
```markdown
![Image description](https://raw.githubusercontent.com/username/repo/main/images/chart.png)
```

### Using Relative Paths (Recommended):

```markdown
![Chart](images/revenue-decline-chart.png)
![Chart](./images/revenue-decline-chart.png)
```

Both work the same way on GitHub!

---

## 🎓 Skills Demonstrated

- **Data Analysis:** Multi-year, multi-region deal analysis across 5 product lines
- **Statistical Modeling:** Linear regression for pricing optimization
- **Business Strategy:** Revenue optimization and pricing strategy
- **Data Visualization:** Clear communication of complex pricing dynamics
- **Revenue Analytics:** ARR forecasting and revenue leakage analysis

---

## 📞 Contact

**Juilee B**

*Portfolio project demonstrating data-driven pricing strategy and revenue optimization analysis*

---

## 📄 License

This project is for portfolio demonstration purposes.

---

**Note:** Company M is anonymized for confidentiality. All analysis and recommendations are based on simulated enterprise IAM product data.
