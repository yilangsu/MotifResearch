
# SCIENCE FAIR BOARD CONTENT

## PROBLEM / QUESTION
Can a CNN's ability to repair mutated DNA sequences reveal the regulatory grammar rules of enhancers?

## HYPOTHESIS
A convolutional neural network can repair random mutations but fail to repair required patterns (motifs). Areas with <50% repair success rate will show higher matches to transcription factor binding sites versus those with >80% repair success rate.

## MATERIALS & METHODS

**Data:**
- ENCODE cCRE database: 147,707 enhancers (Human: 78,306 | Mouse: 59,424)
- Background sequences: 1,270,009 GC-matched genomic regions
- Training: 100,000 class-balanced sequences (50k enhancers, 50k background)

**Model:**
- CNN-Transformer hybrid architecture (43.6M parameters)
- Google Colab A100 GPU (80GB)
- Class-balanced sampling with WeightedRandomSampler

**Analysis Pipeline:**
1. Train model to classify enhancers vs background
2. Damage sequences with random point mutations (10%)
3. Attempt gradient-based repair
4. Flag repair failures as essential regions
5. Cross-reference with JASPAR database

## KEY DATA

**Model Performance:**
- Test AUC: 0.862
- Balanced Accuracy: 77.4%
- High-Confidence Accuracy: 96%
- Human Enhancer Recall: 88.4%

**Clinical Discrimination:**
- Pathogenic mutation repair: 14%
- Benign mutation repair: 52%
- Discrimination ratio: 3.7x

**Biological Validation:**
- Poly-A enrichment: 8.0x (p < 10⁻¹⁰⁶)
- TF binding site matches: 55%
- CAAT-box discovered: Position 77
- 3' edge consensus: AAAAA

**Lethal Mutations:**
- Single-base lethal: 17 found
- Hotspot: 100% at 3' edge
- Most lethal: Position 198 A→T (100%→8%)

**Cross-Species:**
- Human repair: 32.7%
- Mouse repair: 30.7%
- Human-Mouse correlation: r=0.59

## OBSERVATIONS

**Observation 1:** Poly-A signal (AAAAA) at 3' edge shows 8-fold enrichment in enhancers vs background (p<10⁻¹⁰⁶), independently validating known regulatory biology.

**Observation 2:** Model distinguishes pathogenic from benign mutations with 3.7x accuracy difference (14% vs 52% repair rate), demonstrating clinical variant classification potential.

**Observation 3:** All 17 lethal single-nucleotide mutations occurred at the 3' edge (positions 150-200), revealing a critical regulatory hotspot where single base changes destroy function.

## CONCLUSION

**The data supports the hypothesis:**

• CNN-Transformer achieved 86.2% AUC with 77.4% balanced accuracy, confirming learnable regulatory patterns

• Model independently discovered 8-fold Poly-A signal enrichment (p<10⁻¹⁰⁶), validating biological relevance

• Clinical discrimination: 3.7x difference between pathogenic (14%) and benign (52%) mutation repair rates

• 17 lethal single-nucleotide mutations identified, all at 3' edge, demonstrating repair-based essential element discovery

• Cross-species analysis: Human-Mouse correlation r=0.59 (p<10⁻²⁰) confirms conserved regulatory grammar

• When model confidence >90%, accuracy is 96%, enabling reliable clinical decision-making

## APPLICATIONS

1. **Clinical Variant Interpretation:** Distinguish pathogenic from benign mutations (3.7x accuracy)
2. **Gene Therapy Safety:** Map essential regulatory regions to avoid disruption
3. **Drug Target Discovery:** Identify critical regulatory elements for therapeutic intervention
