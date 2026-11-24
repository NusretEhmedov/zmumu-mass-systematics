# Does the measured Z mass depend on how the muons were detected?

The Z boson mass is a fixed number, so the fitted peak position of the dimuon mass should not change with muon η, φ, pT or charge. A trend would point to a detector effect (for example a momentum-scale or alignment problem). This project looks for such trends in 10,000 CMS dimuon events.

## Method
1. Compute the dimuon invariant mass from pT, η, φ; keep opposite-charge pairs (9,664 events).
2. Fit the peak position (Gaussian + exponential background, 80–102 GeV) in bins of muon η, φ and pT, separately for μ⁺ and μ⁻.
3. Test each curve against a flat line with a χ² test.
4. Test a simple correction (one mass scale factor per barrel/endcap region) with cross-validation: derive it on half the events and evaluate it on the other half.

## Results
![Peak position vs muon variables](results/peak_vs_variables.png)

| Variable | μ⁺ χ²/ndof | μ⁻ χ²/ndof | Reading |
|---|---|---|---|
| η | 1.93 | 1.11 | consistent with flat |
| φ | 1.01 | 0.97 | consistent with flat |
| pT | 6.98 | 16.51 | clear dependence |

- No significant charge-dependent difference between μ⁺ and μ⁻.
- The peak position shifts with muon pT (about 90.5 GeV at low pT to above 91 GeV at high pT). Binning in one muon's pT also reshapes the mass distribution through selection and kinematics, so the cause is **not isolated** here; it may be a momentum-scale effect, a kinematic effect, or both.
- The region correction changed the barrel/endcap spread from 0.056 to 0.013 GeV, but that spread was already within the fit uncertainty (about 0.06 GeV), so this is not a significant improvement.
- The overall fitted peak (90.83 ± 0.03 GeV) is below the world-average Z mass (91.19 GeV). The Gaussian fit window and uncalibrated education-level data both contribute; this is not a precision measurement.

## Limitations
- 10,000 events allow only coarse bins (5–6 per variable).
- The dataset is meant for education and outreach, not for full physics analysis.

## Run
```bash
cd zmumu-systematics
python zmumu_systematics.py
```
Outputs go to `results/`. See `data/README.md` for the data file.

## Data and citation
CMS Collaboration, *Z to two muons from 2011*, CERN Open Data Portal, record 5208 .  Cite :  (https://opendata.cern.ch/record/5208).
This is an independent educational analysis; neither CMS nor CERN endorses it.The data are CMS Open Data released under CC0 1.0 (public domain waiver).
