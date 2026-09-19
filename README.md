# S82XL-AGN-Structural-Parameters

This repository contains the main catalog of 1378 Stripe 82XL AGNs, along with description of all the columns, for the paper "[Name TBD]" (hereafter `the paper`).

## Access to the file
File `S82XL_HSC3_z_0_1_1378AGN.fits` contains the main catalog. We recommend using an appropriate software, such as [TOPCAT](https://www.star.bris.ac.uk/mbt/topcat/), to access its contents.

## Citation Information
If you use our data in your publication, please reference `the paper` at (Link). 
(Under Construction --- paper link will be updated after the reviewing process is completed)

## Column Description
Below we provide a comprehensive description for each column contained in the catalog.

### Columns from [Peca et al. 2024](https://iopscience.iop.org/article/10.3847/1538-4357/ad6df4)
- `Seq` to `Sloan`: Please refer to [the VizieR Online Data Catalog](https://cdsarc.cds.unistra.fr/viz-bin/cat/J/ApJ/974/156) for [Peca et al. 2024](https://iopscience.iop.org/article/10.3847/1538-4357/ad6df4) for descriptions of these columns. Please note that `LFull` is the X-ray luminosity ($L_X$) and `zSpec` is the redshift ($z$) we used throughout this catalog, respectively.

### Columns from the S82XL–HSC counterpart associations
- `OutID`: X-ray source identifier in the S82XL–HSC counterpart association table. This is not the same as `Seq` (the source identifier in the published S82XL catalog).
- `RAout`: RA (J2000.0) of the X-ray source (in degree)
- `DECout`: DEC (J2000.0) of the X-ray source (in degree)
- `InID`: HSC counterpart identifier in the S82XL–HSC counterpart association table. 
- `RAin`: RA (J2000.0) of the HSC counterpart (in degree)
- `DECin`: DEC (J2000.0) of the HSC counterpart (in degree)

### Columns from HSC DR3 table [pdr3\_wide.forced](https://hsc-release.mtk.nao.ac.jp/schema/\#pdr3.pdr3_wide.forced), [pdr3\_wide.forced2](https://hsc-release.mtk.nao.ac.jp/schema/\#pdr3.pdr3_wide.forced2), [pdr3\_wide.photoz\_mizuki](https://hsc-release.mtk.nao.ac.jp/schema/\#pdr3.pdr3_wide.photoz_mizuki)
- `object_id`: Unique ID in 64bit integer. This is not the same as `InID`.
- `ra`: RA (J2000.0) of the object (in degree)
- `dec`: DEC (J2000.0) of the object (in degree)
- `tract`: Tract ID
- `patch`: Patch name as an integer
- `{band}_cmodel_flux`: Flux from the final cmodel fit (in nano-Jy)
- `{band}_cmodel_mag`: Flux from the final cmodel fit (in mag)
- `{band}_kronflux_flux`: Flux from Kron Flux algorithm (in nano-J
- `{band}_kronflux_mag`: Flux from Kron Flux algorithm (in mag)
- `photoz_best`: Redshift chosen so that the risk would be minimal
- `photoz_std_best`: Standard deviation around `photoz_best`
- `photoz_risk_best`: The risk of `photoz_best` being outside of the range z_true +-
0.15(1+z_true). It ranges from 0 (safe) to 1 (risky)
- `{band}_extendedness_value`: Set to 1 for extended sources, 0 for point sources. See [this page](https://hsc-release.mtk.nao.ac.jp/doc/index.php/star-galaxy-separation__pdr3/) for details.

### Columns from running [GaMPEN](https://ghosharitra.com/gampen.html)
Here we use $R_e$ (effective/half-light radius) as an example. Cases are similar for other structural parameters: flux, bulge-to-total flux ratio, and magnitude. Since we are using PSFGAN outputs as GaMPEN inputs, all structural parameters from GaMPEN outputs refer to the PSFGAN recovered host galaxy, not the entire AGN PS + host galaxy. 
Magnitudes are not corrected for galactic extinction.
Note that we are presenting structural parameters for each of the five HSC DR3 Wide bands: $g$, $r$, $i$, $z$ and $y$.
- `{band}_preds_R_e_asec_mean`: Mean of GaMPEN predicted distribution for parameter $R_e$ (in arcsec --- the same unit is used for most other $R_e$ columns) in the {band} band
- `{band}_preds_R_e_asec_median`: Median of GaMPEN predicted distribution for parameter $R_e$ in the {band} band
- `{band}_preds_R_e_asec_std`: Standard deviation of GaMPEN predicted distribution for parameter $R_e$ in the {band} band
- `{band}_preds_R_e_asec_skew`: Skewness of GaMPEN predicted distribution for parameter $R_e$ in the {band} band
- `{band}_preds_R_e_asec_kurtosis`: Kurtosis of GaMPEN predicted distribution for parameter $R_e$ in the {band} band
- `{band}_preds_R_e_asec_mode`: Mode of GaMPEN predicted distribution for parameter $R_e$ (i.e., the most probable value of $R_e$ in the entire predicted distribution) in the {band} band
- `{band}_preds_R_e_asec_sig_ci`: Lower and upper bounds for the $1 \sigma$ confidence interval for parameter $R_e$ in the {band} band
- `{band}_preds_R_e_asec_twosig_ci`: Lower and upper bounds for the $2 \sigma$ confidence interval for parameter $R_e$ in the {band} band
- `{band}_preds_R_e_asec_threesig_ci`: Lower and upper bounds for the $3 \sigma$ confidence interval for parameter $R_e$ in the {band} band

Note for other structural parameters, units are different. For instance, flux is in ADU (analog-to-digital units) while the bulge-to-total ratio (bt) is unitless.

### Columns from running [PSFGAN](https://academic.oup.com/mnras/article/477/2/2513/4951616)
- `{band}_contrast_ratio`: In each of the five HSC DR3 Wide bands: $g$, $r$, $i$, $z$ and $y$, after separating the AGN point source and the host galaxy, we calculated the AGN-to-host galaxy flux contrast ratio in that band.

### Columns from running image quality checks
- `{band}_image_quality_pass`: Whether GaMPEN predictions for this source in the {band} band are reliable (determined using pre- and post-PSFGAN images in that band)
- `{band}_image_quality_reason`: The reason why GaMPEN predictions for this source in the {band} band are reliable (or not)

### Columns for galactic extinction values
- `a_{band}`: Absorption for HSC {band} band (in mag)

Note that these `a_{band}` columns also come from [pdr3\_wide.forced](https://hsc-release.mtk.nao.ac.jp/schema/\#pdr3.pdr3_wide.forced). They are listed here because they are the last five columns in our main catalog.








