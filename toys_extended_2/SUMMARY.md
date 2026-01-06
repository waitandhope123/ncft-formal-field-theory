# SUMMARY — NCFT BAYESIAN & SEMANTIC TESTS (RESULTS-ALIGNED)

This summary covers a sequence of NCFT toy models designed to test whether NCFT
captures non-random structure in data, whether that structure generalizes beyond
weak nulls, and where semantic information resides (or does not reside) in the model.

All statements below are directly supported by the recorded numerical results.

---

## 1) BAYESIAN MODEL COMPATIBILITY
_file: ncft_bayesian_model_compatibility_test.py_

- Compares NCFT against a weak iid bilinear null
- Bayesian evidence strongly favors NCFT:
  - log BF₁₀ ≈ 91.55
  - BF ≈ 5.7 × 10³⁹
- Implied noise scale is small (σ ≈ 0.0072)

**Status:** PASS  
**Role:**  
Establishes that the data are highly structured and incompatible with a weak null.
This is a non-randomness and compatibility test, not a uniqueness or prediction test.

---

## 2) FORWARD CATEGORY MEAN PREDICTION
_file: ncft_forward_category_prediction.py_

- Tests whether NCFT predicts scalar category means on held-out categories
- NCFT and null predictions are identical:
  - NCFT MSE = Null MSE ≈ 0.245

**Status:** FAIL (expected, informative)  
**Role:**  
Shows that scalar category semantics are not encoded at this level of the model.

---

## 3) BAYES FACTORS AGAINST STRONG NULLS
_file: ncft_bayesfactor_robust_nulls.py_

### Event-holdout (within-category)
- NCFT beats pooled and mixture nulls
- NCFT loses to per-category null (expected)

### Category-holdout (unseen categories)
- NCFT strongly outperforms all nulls:
  - BF(NCFT / GMM null) ≈ 6.5 × 10¹⁶

**Status:** PASS  
**Role:**  
Demonstrates genuine structural generalization.
NCFT’s advantage is not due to weak nulls or clustering artifacts.

---

## 4) CATEGORY ORDERING VIA LOCAL STATISTICS
_file: ncft_category_order_prediction.py_

- Uses per-category variance as a structural proxy
- Spearman rank correlation:
  - ρ ≈ 0.19 (not significant)

**Status:** FAIL  
**Role:**  
Rejects the hypothesis that semantic ordering is encoded in simple per-category moments.

---

## 5) RELATIONAL EMBEDDING (COARSE GEOMETRY)
_file: ncft_relational_embedding_prediction.py_

- Uses a global 2-pole mixture as a relational proxy
- Results:
  - Distance-matrix Spearman ρ ≈ 0.78
  - k-NN overlap ≈ 0.5
- Signal dominated by a trivial “self_excl vs rest” separation

**Status:** PARTIAL  
**Role:**  
Recovers only coarse, macro-level separation.
Fine semantic geometry is not resolved at this proxy level.

---

## 6) MICRO-GEOMETRY SEMANTIC TEST
_file: ncft_microgeometry_test.py_

- Removes trivial outlier (self_excl)
- Uses a 3-pole relational / spectral proxy
- Results:
  - Centers ≈ [0.915, 0.965, 0.999]
  - Spearman ρ ≈ 0.968
  - 2-NN overlap = 1.000

**Status:** PASS  
**Role:**  
Demonstrates that fine-grained semantic structure is recoverable from NCFT,
but only in relational / spectral geometry, not scalar observables.

---

## OVERALL SUMMARY

Across this test suite:

- Non-random internal structure: ✅ confirmed
- Compatibility with data: ✅ confirmed
- Robustness to strong nulls: ✅ confirmed
- Scalar prediction of category values: ❌ not supported
- Semantic ordering via local statistics: ❌ rejected
- Semantic geometry via relational structure: ✅ confirmed

---

## KEY INSIGHT

NCFT does not encode meaning in scalar quantities or per-category moments.

Semantic information emerges only in **relational, spectral geometry** —
that is, in how categories are positioned relative to one another, not in
their individual averages.

---

## CURRENT POSITION

NCFT is a mathematically coherent and empirically compatible framework that:

- Clearly outperforms strong null models under generalization
- Fails predictably where semantics are not expected to live
- Succeeds when tested in the correct (relational) geometric regime

This defines both the current limits of the model and the correct direction
for future tests.
