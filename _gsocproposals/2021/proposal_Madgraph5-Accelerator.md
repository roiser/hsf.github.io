---
project: MadGraph5
title: MadGraph5 - offload event execution to accelerator devices
layout: gsoc_proposal
year: 2021
organization:
  - CERN
  - UCLouvain
---

## Description
High energy physics experiments such as the Large Hadron Collider (LHC) experiments at CERN rely heavily on so called “Monte Carlo (MC) Simulations” to achieve their physics research goals. MC simulations mimic in a computer program the initial collision of particles in a high energy physics collider and their subsequent response inside a physics detector.

LHC experiments use a distributed computing environment of up to 500.000 computing cores and several exa-bytes of disk and tape storage for its data processing and the vast majority of the available CPU power (70 - 80 %) is used for MC simulations. Recently the provisioning of compute accelerators, such as General Purpose Graphics Processing Units (GPUs), has become popular in this computing infrastructure in addition to classical x86 Intel CPUs.

Looking at the workflow of a simulation program, the very first step of it is the so called “event generation” where the initial collision of the particles in the collider is simulated. These event generators are historically written for classical x86 intel compatible architectures. With the shift of the distributed computing environment towards GPUs it is essential to make MC Generators also fit for use on those architectures.

## Task ideas
The student will work with one of the most utilised MC Generators, called Madgraph5 and develop code for a Cuda/C++ port of the package. The task includes

 * Learn about a Cuda feature called Cuda Graphs
 * Apply Cuda Graphs to the most compute intensive part of the package (called matrix element calculation)
 * Measure the performance changes of the implementation
 * Document the changes and provide help with the porting of the changes upstream into the master project

## Expected results
The deliverable of the project is the implementation of cuda graphs in the Madgraph5 project and a performance study of the workflow with the new feature enabled.

## Requirements
We're seeking a candidate with high proficiency in Cuda/C++ programming. A basic understanding of NVidia profiling tools (e.g. NSight System, NSight Compute), GNU Makefiles, git and Python are a surplus. 

## Mentors
  * [Olivier Mattelaer](mailto:olivier.mattelaer@uclouvain.be) UnivLouvain
  * [Stefan Roiser](mailto:stefan.roiser@cern.ch) CERN
  * [Andrea Valassi](mailto:andrea.valassi@cern.ch) CERN

## Links
  * [MadGraph5](https://launchpad.net/mg5amcnlo)
  * [GPU Code](https://madgraph5.github.io/)
