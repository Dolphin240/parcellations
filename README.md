![alt test](images/logo2.png)

We are delighted to provide the neuroscience community with a new hierarchical MRI atlas of the human subcortex. This repository provides the new atlas for download and stores the code used to map the atlas.  

**Atlas features:** 
- Volumetric parcellation of the human subcortex representing consensus among more than 1000 healthy adults.
- Available in four hierarchical scales as well as 3 and 7 Tesla versions. 
- Personalizable to represent individual variation in regional boundaries.
- Seamlessly integratable into established cortex-only parcellation atlases.
- Includes striatum, thalamus, hippocampus, amygdala and globus pallidus. 

**Atlas scales:** The atlas is available in four scales, labeled Scales I, II, III and IV. Scale I is the coarsest atlas and recapitulates 8 well-known anatomical nuclei, while Scale IV is the finest and delineates 27 bilateral regions of the subcortex. Each scale is bilaterally symmetric and defines a self-contained parcellation atlas. 

**Downloading the atlas:** The group-consensus atlas is provided in NIFTI and CIFTI (dlabel and dscalar) format for download in the directory called *Group-Parcellation*. If you are only here to download the atlas, this is the only directory that you need to visit. Both 3 and 7 Tesla versions are delineated in 6th generation MNI space at voxel resolutions of 2 and 1.6 mm, respectively. This is the same space used by the Human Connectome Project. To facilitate whole-brain connectome mapping, the 3T version of the atlas is also integrated into several existing cortex-only parcellation atlases and the combined subcortex-cortex atlases are provided for download in CIFTI format. A naming convention (nomenclature) for all regions is provided in a text file that accompanies each atlas scale.   

    

**What atlas scale should I use?** 

**Should I use the 3 or 7 Tesla atlas?**

**How was the atlas mapped?** The guiding principle was reconciliation of two seemingly contradictory representations of brain topography: i) hard boundaries between discrete regions; and, ii) continuous gradients of spatial variation. Laplacian eigenmaps were used to represent spatial gradients in resting-state functional connectivity across the subcortical volume. An analogue of diffusion MRI tractography, called gradientography, was developed to identify and parameterize gradient magnitude peaks in these spatial gradients. Formal model selection and null hypothesis testing was then used to determine whether gradient magnitude peaks were sufficiently large to warrant boundary delineation. This process was repeated recursively for each new region delineated, until the null hypothesis of an absence of boundaries could not be rejected for any region.

**Why only four scales?** The null hypothesis of an absence of boundaries could not be rejected for any of the regions comprising the Scale IV atlas, and thus further (finer) parcellation was not warranted. Gradient magnitude peaks at Scale IV were not significantly larger than that predicted by a null model.

**Why does the subcortex volume differ slightly between the CIFTI and NIFTI files?**  To minimize partial volume effects, the volumetric mask used to define subcortical voxels is slightly more conservative than the FreeSurfer subcortical mask. However, the mask also very slightly exceeds the Freesurfer mask in striatal regions. The atlas provided in CIFTI format has been cropped to ensure that it entirely resides within the FreeSurfer mask. The atlas provided in NIFTI format is not cropped. Cropping eliminated XX voxels.  


**More about the atlas**

Data and code (MATLAB, *.m) related to:

Contact: Dr Ye Tian, Dr Andrew Zalesky

Email: yetianmed@gmail.com, azalesky@unimelb.edu.au

**demo.m** provides data description and analysis demo.

MATLAB code is provided in **functions**.

Each folder below corresponds to one of the main sections in the manuscript, containing relevant source data and computed metrics:

### MapGradient

   Map the functional connectivity gradients in the human subcortex.

### fMRI-tractoraphy

   Model the functional connectivity gradients using fMRI-tractography.

### GeoNull

   Model selection: Compare gradient magnitude with null data.

### Group-Parcellation

   **3T:** Group consensus hierarchical atlas of the human subcortex delineated using 3 Tesla functonal MRI data.  

   **7T:** Group consensus hierarchical atlas of the human subcortex delineated using 7 Tesla functonal MRI data.  

### Homogeneity

   Estimate the functional homogeneity of delineated atlas.

### Individual-Parcellation

   Personalize subcortical atlas using support-vector machine learning. 
   
### Behavior

   Decompose high dimensional behavioral data into 5 dimensions using independent component analysis (ICA).







 

 
