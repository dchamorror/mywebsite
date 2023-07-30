---
title: "Deep-learning based dispersion curve prediction from seismic shot gathers"
date: 2023-02-02
---

# Introduction

The Multi-channel Analysis of Surface Waves (MASW) is a well-known seismic method employed to analyze the near subsurface by examining its shear-wave velocities. A significant challenge in the MASW workflow is extracting dispersion curves from dispersion spectra. While some methodologies exist to automate this process, it requires expert quality control and can be quite time-intensive and subjective when dealing with large datasets.

Recently, machine learning methodologies have been proposed to address this problem. However, many of these approaches rely heavily on the information from the dispersion spectra and not the seismic shot gathers. As a result, the output can often be biased, leading to suboptimal inversion results.

In this project, I introduce a new methodology that uses a Convolutional Neural Network (CNN) guided by geophysical theory to estimate dispersion curves directly from seismic shot gathers.

## Methodology

The methodology I used in this project involved creating a set of 1D velocity models using prior geological knowledge of a site. I then numerically modelled the corresponding seismic shot gathers and their associated Rayleigh-wave phase dispersion curves. This data was used to train a simplified residual network to learn the direct mapping from shot gathers to dispersion curves.

For the neural network architecture, I used a lightweight ResNet architecture (ResNet-18), modifying it to account for the unique dimensions of the input and output data. To enhance the smoothness of the predicted curves, I introduced a secondary loss.

## Results

The proposed methodology was applied to a field dataset provided by Fugro. Initial experiments conducted on a synthetic dataset indicated that the proposed neural network model performs excellently, predicting accurately and quickly. 

When applied to field datasets, I used data pre-processing strategies to overcome challenges such as inevitable differences between synthetic and field data. After applying the proposed workflow to the entire field dataset and inverting the retrieved phase velocity dispersion curves for an S-wave velocity model, the results were consistent with the area's prior geological knowledge.

## Conclusion

By mapping seismic shot gathers to dispersion curves directly, the deep-learning-based methodology proposed in this project accelerates the extraction of dispersion curves from seismic data, a critical step in the MASW workflow. The project's successful results lay the groundwork for a fully automated MASW workflow, with potential implications for the efficiency of seismic data interpretation in the field.

---
I am grateful to KAUST for supporting this research, and to Fugro for providing the field dataset for this project.

## References

A full list of references can be found in the original paper. This includes works by leading researchers such as Park et al., Dal Moro, Alyousuf and Colombo, Rovetta et al., Kaul et al., and others who have made significant contributions to this field of study.