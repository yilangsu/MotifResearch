
# FIGURES TO GENERATE FOR BOARD

## MUST-HAVE FIGURES (Top Priority)

### 1. Clinical Discrimination Bar Chart
- Two bars: "Pathogenic" (14%, red) vs "Benign" (52%, green)
- Title: "Model Distinguishes Pathogenic from Benign Mutations"
- Y-axis: "Repair Success Rate (%)"
- Add "3.7x" annotation

### 2. Poly-A Enrichment Bar Chart
- Two bars: "Enhancers" (50.5%) vs "Background" (6.3%)
- Title: "Poly-A Signal Enrichment at 3' Edge"
- Y-axis: "Sequences with Poly-A (%)"
- Add "8.0x enrichment, p<10⁻¹⁰⁶" annotation

### 3. Cross-Species Repair Rates
- Four bars: Human (32.7%), Mouse (30.7%), Chicken (20.3%), Zebrafish (13.7%)
- Color gradient: blue for mammals, orange for non-mammals
- Title: "Repair Success Across 450 Million Years of Evolution"

### 4. Confidence Calibration Curve
- X-axis: Confidence bins (50-60%, 60-70%, etc.)
- Y-axis: Accuracy (%)
- Show: 50%→41%, 60%→48%, 70%→75%, 80%→89%, 90%→96%
- Title: "Model Confidence vs Accuracy"

### 5. Lethal Mutation Hotspot
- Bar chart or heatmap showing positions 0-200
- Highlight: ALL 17 mutations at positions 150-200
- Title: "Lethal Mutations Cluster at 3' Edge"

## NICE-TO-HAVE FIGURES

### 6. Training Curves
- Dual y-axis: Loss and Accuracy vs Epoch
- Show train/val for both
- Mark best epoch (5)

### 7. Position 198 Nucleotide Specificity
- Four bars: A (83%), C (67%), G (66%), T (62%)
- Title: "Nucleotide Requirements at Position 198"

### 8. Enhancer Strength Distribution
- Pie or bar: Strong 52.5%, Medium 11%, Weak 25%, Borderline 11.6%
- Title: "Enhancer Strength Distribution"

### 9. Human vs Mouse Essential Positions
- Two overlaid line plots showing importance profiles
- Highlight shared peaks
- Title: "Conservation of Essential Positions (r=0.59)"

### 10. Disease Variant Impact
- Bar chart: Random point (1.0), Essential point (0.74), Deletion (0.58), Poly-A disruption (0.59)
- Color: green for benign, red for pathogenic
- Title: "Variant Type Impact on Function"
