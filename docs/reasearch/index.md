# Research Interests
My research interests are in the realm of radio astronomy. I am interested in the intersection of data analysis and instrumentation. Currently I am focussed on using FRBs as cosmological probes as well as comissioning the upcoming CHORD radio telescope. More details are provided below. 

# Projects 
### Canadian Hydrogen Intensity Mapping Experiment (CHIME)  
**Blazar Analysis, 2023–Present**  
*Supervisors: Matt Dobbs and Dallas Wulf*

My work with CHIME initially centered on point source analysis of blazars — highly energetic Active Galactic Nuclei (AGN) that often display significant variability, including quasi-periodic oscillations (QPOs). I led the development of an automated pipeline to detect variability signatures in a large catalog of blazars, leveraging CHIME’s broad sky coverage to provide insights into AGN dynamics and emission mechanisms. In this project, I implemented the Lomb-Scargle Periodogram and Weighted Wavelet Z-Transform from scratch, demonstrating proficiency in Python programming and signal analysis. Additionally, I employed Monte Carlo methods to quantify the significance of dominant periods, modeling blazar light curves as autoregressive processes and refining my parallelization skills to handle the dataset efficiently on compute clusters. Currently, I am co-authoring a paper on blazar variability analysis with Dallas Wulf. For details on this project you can check out the presentation I gave to the CHIME collaboration [here](../projects/presentation.md)
 

**FRB Analysis 2024-Present**   
*Supervisor: Matt Dobbs*

Fast Radio Bursts (FRBs) are a promising new tool for probing the ionization history of the universe, including the reionization of helium. Because FRBs are highly dispersed as they travel through the ionized intergalactic medium (IGM), their **dispersion measure (DM)** — the integrated column density of free electrons along the line of sight — serves as a probe of the ionization state of the IGM at different redshifts.

The reionization history of the universe involves two main phases:

- **Hydrogen Reionization:** Occurred around $z \approx 6$ when ionizing photons from early stars and galaxies fully ionized hydrogen.
- **Helium Reionization:** This second stage occurred later, at around $z \approx 3$, when high-energy radiation from quasars reionized singly ionized helium (He II), converting it into fully ionized helium (He III).

This process significantly influenced the thermal and ionization state of the IGM, especially around $z \approx 3$, leaving an imprint that can be detected by examining FRB dispersion measures at these redshifts.

The observed dispersion measure, $\mathrm{DM}_{\mathrm{IGM}}$, for an extragalactic FRB can be written as the integral of the electron density along the line of sight:

$$
\mathrm{DM}_{\mathrm{IGM}} = \int_0^z \frac{n_e(z')}{1+z'} \, d\ell.
$$

In a flat $\Lambda$CDM cosmology, the relation between proper length element $d\ell$ and redshift $z$ is given by:

$$
d\ell = \frac{1}{1+z}\frac{c}{H_0} \frac{dz}{\sqrt{\Omega_m(1+z)^3 + \Omega_\Lambda}},
$$

where $c$ is the speed of light, $H_0$ is the Hubble constant, $\Omega_m$ is the present-day matter density, and $\Omega_\Lambda = 1 - \Omega_m$ is the vacuum energy density. The electron density can be expressed as:

$$
n_e(z) = \frac{\rho_{c,0} \, \Omega_b \, f_{\mathrm{IGM}} \, X_e(z)}{m_p}(1+z)^3,
$$

where $\rho_{c,0} = \frac{3 H_0^2}{8 \pi G}$ is the critical density of the Universe, $m_p$ is the proton mass, $\Omega_b$ is the baryon density parameter, and $f_{\mathrm{IGM}} \simeq 0.83$ is the mass fraction of baryons in the IGM. The electron fraction $X_e(z)$ depends on ionization states of hydrogen and helium as follows:

$$
X_e(z) = Y_H \, X_{e,\mathrm{HII}}(z) + \frac{1}{4} Y_{\mathrm{He}} \left[X_{e,\mathrm{HeII}}(z) + 2 X_{e,\mathrm{HeIII}}(z)\right],
$$

where $Y_H = 1 - Y_{\mathrm{He}}$ and $Y_{\mathrm{He}}$ are the hydrogen and helium abundances in the Universe, respectively. The ionization fractions $X_{e,\mathrm{H}}(z)$ and $X_{e,\mathrm{He}}(z)$ change with redshift and ionization stage.

At the epoch of hydrogen reionization, both hydrogen and helium are ionized, so we assume $X_{e,\mathrm{HeII}} = X_{e,\mathrm{HII}}$. As hydrogen becomes fully ionized around $z = 6$, we have:

1. $X_{e,\mathrm{HII}} = 1$ and $X_{e,\mathrm{HeII}} = 1$ before helium reionization.
2. When He II reionization occurs around $z_{\mathrm{re}} \sim 3$, the ionization state shifts such that $X_{e,\mathrm{HII}} = 1$, $X_{e,\mathrm{HeII}} = 0$, and $X_{e,\mathrm{HeIII}} = 1$.

The electron fraction increases due to He II reionization by approximately $7.4\%$ because of the transition of He II to He III, as calculated from:

$$
X_e(z > z_{\mathrm{re}}) = 1 - \frac{3 Y_{\mathrm{He}}}{4} \approx 0.819, \quad X_e(z < z_{\mathrm{re}}) = 1 - \frac{Y_{\mathrm{He}}}{2} \approx 0.880.
$$

This reionization of He II would cause an observable change in $\mathrm{DM}_{\mathrm{IGM}}$, calculated by averaging over different lines of sight:

$$
\mathrm{DM}_{\mathrm{IGM}}(z) = \frac{3 c H_0 \, \Omega_b \, f_{\mathrm{IGM}}}{8 \pi G m_p} \int_0^z \frac{(1+z') X_e(z')}{\sqrt{\Omega_m(1+z')^3 + \Omega_\Lambda}} \, dz'.
$$

Simulations show that a significant number of FRBs with well-localized redshifts can yield valuable constraints:

- A mock catalog with $10^4$ FRBs can determine the reionization redshift $z_{\mathrm{re}}$ with an uncertainty of $\sigma(z_{\mathrm{re}}) \approx 0.22 - 0.31$, depending on redshift distribution assumptions.
- With 1,000 FRBs, the uncertainty on $z_{\mathrm{re}}$ can reduce to about $\sigma(z_{\mathrm{re}}) \approx 0.1$.

CHORD is forecasted to detect around 10-20 FRBs daily with sub-arcsecond localization, which could make constraining He II reionization realistic.



### Canadian Hydrogen Observatory and Radio-transient Detector (CHORD)  
**CHORD Commissioning, 2023–Present**  
*Supervisors: Matt Dobbs and Dallas Wulf*

Alongside my work on CHIME, I contribute to the CHORD project, a next-generation radio telescope designed to extend CHIME’s capabilities with enhanced sensitivity, spatial resolution, and frequency range. My role in CHORD focuses on instrumentation and data calibration, specifically analyzing system temperature data for the Deep Dish Development Array (D3A). Working with D3A has provided me with hands-on experience in calibration techniques critical for achieving accurate sky measurements. My responsibilities include assessing thermal noise levels, quantifying environmental effects on system stability, and ensuring consistent data quality across array elements.

This detailed, low-level data work has allowed me to develop a comprehensive understanding of radio telescope operation, positioning me to contribute effectively as CHORD moves toward full commissioning. My dual involvement in both CHIME and CHORD has given me a robust foundation in both astrophysical analysis and instrumentation, preparing me to contribute to the future of radio astronomy in Canada and beyond.
