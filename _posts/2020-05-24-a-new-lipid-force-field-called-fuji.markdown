---
title: A new lipid force-field called FUJI.
date: 2020-05-24 14:47:00 +02:00
---

Here's just a repost of an abstract on a "new" lipid force-field. One maybe should better say a new derivative force-field, or a modified existing force-field to be more accurate.  What's most interesting is the claim that a fully quantum mechanics based parametrization results in properties acceptably close to experimental values.  

Also interesting to note that the study is done with gromacs 2016.4. I wonder if the results could be reproducible using the latest version of gromacs, the practical problem being that changes in solvate and genion often result in segmentation fault errors.  


## A New Lipid Force Field (FUJI) ##

### Nozomu Kamiya, Megumi Kayanuma, Hideaki Fujitani, Keiko Shinoda  ###

*J. Chem. Theory Comput. 2020 May 21*  

**Abstract**  

To explore inhomogeneous and anisotropic systems such as lipid bilayers, the Lennard-Jones particle mesh Ewald (LJ-PME) method has been applied without a conventional isotropic dispersion correction. As the popular AMBER and CHARMM lipid force fields were developed using a cutoff scheme, their lipid bilayers unacceptably shrink when using the LJ-PME method. In this study, a new all-atom lipid force field (FUJI) was developed on the basis of the AMBER force-field scheme including the Lipid14 van der Waals parameters. Point charges were calculated using the restrained electrostatic potentials of many lipid conformers. Further, torsion energy profiles were calculated using high-level ab initio molecular orbitals (LCCSD(T)/Aug-cc-pVTZ//LMP2/Aug-cc-pVTZ), following which the molecular mechanical dihedral parameters were derived through a fast Fourier transform. By incorporation of these parameters into a new lipid force field without fitting experimental data, the desired lipid characteristics such as the area per lipid and lateral diffusion coefficients were obtained through GROMACS molecular dynamics simulations using the LJ-PME method and virtual hydrogen sites. The calculated area per lipid and lateral diffusion coefficients showed satisfactory agreement with experimental data. Furthermore, the electron-density profiles along the membrane normal were calculated for pure lipid bilayers, and the resulting membrane thicknesses agreed well with the experimental values. As the new lipid force field is compatible with FUJI for protein and small molecules, the new FUJI force field will offer accurate modeling for complex systems consisting of various membrane proteins and lipids.  

[https://doi.org/10.1021/acs.jctc.9b01195](https://doi.org/10.1021/acs.jctc.9b01195)