# Heatwave Severity Classifier

An interactive web-based calculator for a multi-parameter freshwater heatwave severity classification framework, developed as part of an undergraduate dissertation investigating heatwave impacts on Lake Windermere, UK.

**Live tool:** [https://yourusername.github.io/heatwave-classifier/](https://yourusername.github.io/heatwave-classifier/)

---

## About

Existing heatwave classification systems are almost exclusively temperature-based, yet two heatwaves of identical temperature can produce very different biogeochemical responses in freshwater bodies depending on how far nutrient cycling is disrupted. This tool implements a classification framework that addresses this gap by scoring heatwave severity in terms of actual lake response rather than air or surface temperature alone.

The framework was calibrated against long-term South Basin monitoring data from Lake Windermere (1945–2018), but is designed as a transferable methodology. Each lake can be calibrated to its own correlation structure, with Windermere serving as the worked example.

## How it works

The calculator applies the equation:

**S = Σ(wᵢ × Sᵢ)**

Where:
- **S** is the overall heatwave severity score (1–5)
- **wᵢ** is the weight for each parameter, derived from the magnitude of correlation shift (Δr) between normal and heatwave conditions
- **Sᵢ** is the parameter severity score (1–5), based on percentile deviation from a month-specific baseline

Three parameters contribute to the score: phosphorus, nitrate, and chlorophyll a. Oxygen and ammonium are excluded based on their correlation-shift behaviour (see dissertation §3.4).

## Inputs

The calculator takes two sets of inputs:

1. **Lake-specific weights** (wᵢ) for each parameter, calibrated from the correlation analysis of that lake's own data. Default values loaded for Lake Windermere.
2. **Parameter severity scores** (Sᵢ) between 1 and 5, reflecting how far current values deviate from the monthly baseline.

## Outputs

- Final weighted severity score (numerical, 1.0–5.0)
- Severity band (1–5) with ecological interpretation
- Visual severity indicator with colour-coded banding

## Windermere default weights

| Parameter | Weight |
|:---|:---:|
| Phosphorus | 0.37 |
| Nitrate | 0.32 |
| Chlorophyll | 0.30 |

## Severity bands

| Band | Score range | Description |
|:---:|:---:|:---|
| 1 | 1.0–1.8 | Limited biogeochemical disruption |
| 2 | 1.8–2.6 | Mild disruption across indicator parameters |
| 3 | 2.6–3.4 | Moderate disruption, likely onset of internal loading |
| 4 | 3.4–4.2 | Severe disruption, significant ecological stress |
| 5 | 4.2–5.0 | Extreme disruption, multi-parameter thresholds exceeded |

## Use

No installation or dependencies. Open the live link, enter weights and severity scores, and the classification is calculated in real time. The tool runs entirely in the browser.

## Limitations

- The Windermere default weights are calibrated to data from the South Basin between 1945 and 2018 and should not be applied to other lakes without recalibration.
- Weights should be recalculated every five years to account for long-term ecological change.
- The tool does not automatically calculate percentile deviation from raw readings; severity scores must be derived separately and entered manually.

## Context

Developed alongside a dissertation examining heatwave-driven biogeochemical disruption in Lake Windermere. The full methodology, results, and framework justification are presented in the accompanying dissertation (§3.4).

## Licence

Open for academic and educational use.
