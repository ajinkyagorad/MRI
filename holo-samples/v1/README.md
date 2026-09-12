# MRI Holo reference data, version 1

Downloadable companions to the TMF_005 MRI already hosted in this repository.

| File | Content |
| --- | --- |
| TMF_005_t1.nii.gz | Original T1 MRI, compressed without changing its voxels |
| TMF_005_t1_siam.nii.gz | Whole-head segmentation: 39 non-background labels, including eyes, nose/ears, skull/jaw, skin, muscle, nerves and brain tissue |
| TMF_005_atlas_aseg.nii.gz | Separate brain-only parcellation: 95 non-background labels, stored in the viewer's dense FreeSurfer vocabulary |

The head and brain label maps are different outputs. Their label numbers are not interchangeable. NIfTI affine geometry is preserved. These are the existing supplied outputs used by MRI Holo Viewer; this publication does not assert independent anatomical validation.

The application downloads all three verified files together, caches them for offline use, and keeps them out of the APK. `manifest.json` records SHA-256 of each compressed download. These gzip files are ordinary Git blobs, not Git LFS pointers, so a fresh installation does not require Git or a GitHub login.
