# MRI Holo reference data, version 1

Downloadable companions to the TMF_005 MRI already hosted in this repository.

| File | Content |
| --- | --- |
| TMF_005_t1.nii.gz | Original T1 MRI, compressed without changing its voxels |
| TMF_005_t1_siam.nii.gz | Whole-head segmentation: 39 non-background labels, including eyes, nose/ears, skull/jaw, skin, muscle, nerves and brain tissue |
| TMF_005_atlas_aseg.nii.gz | Separate brain-only parcellation: 95 non-background labels, stored in the viewer's dense FreeSurfer vocabulary |

The head and brain label maps are different outputs. Their label numbers are not interchangeable. NIfTI affine geometry is preserved. These are the existing supplied outputs used by MRI Holo Viewer; this publication does not assert independent anatomical validation.

The application downloads all three verified files together, caches them for offline use, and keeps them out of the APK. `manifest.json` records SHA-256 of each compressed download. These gzip files are ordinary Git blobs, not Git LFS pointers, so a fresh installation does not require Git or a GitHub login.

## Surface caches for MRI Holo Viewer 1.34

The two `.mesh` files are derived visualization surfaces for the supplied head and brain labels, not new scans or segmentations. The head cache also aligns to the supplied T1 scan. They preserve label identity and use fine categorical surface nets followed by topology-checked quadric simplification, with at most 160,000 triangles per study. Cache keys include the native labels, grid dimensions, affine and algorithm version; files also carry a payload checksum. `surface-caches.json` records each public download checksum.

The app downloads these small geometry files beside the three NIfTI assets so reference views do not require initial mesh extraction on the headset. Missing or damaged caches are regenerated from the authoritative label map. Meshes are approximate display geometry, not a measurement or diagnostic reconstruction. Source segmentation generator versions were not recorded; the known label schemes are SIAM whole head and FreeSurfer DKT/ASEG. External files may declare their own model and names in a `.labels.json` sidecar.
