# Overview

This repository holds a small _spherical images_ dataset used as an usage example of the _Structure from Sphere_ framework in [this repository](https://github.com/ScanVan/sfs-framework). Its contains the images dataset, the _YAML_ configuration file needed to run the framework on the image and all the obtained framework result, including the framework logs.

# ScanVan Project

The _ScanVan Project_ was funded by the Swiss National Science Foundation (SNF, PNR 76 Big Data) and won by the _DHLAB_ of _EPFL_ and the _HES-SO Valais Wallis_. The goal of the project was to demonstrate the possibility of city mass and continuous digitization using central spherical cameras. Using such device allows to simplify the 3D structures computation and to drastically decrease the complexity of images acquisition.

The _EPFL_ team realized the theoretical design of the camera and defined a new pose estimation algorithm able to be applied to the case of images acquired by such device. The _HES-SO Valais Wallis_ were in charge of translating the theoretic design of the camera into a physical device achieving the centrality. The codes implementation, validation and testing was shared between the two teams.

Summary of the _ScanVan Project_ codes :

* [Camera calibration](https://github.com/ScanVan/Calibration-CPP)
* [Camera images acquisition](https://github.com/ScanVan/CameraImageAcquisition-CPP)
* [Camera images debayering](https://github.com/ScanVan/ConvertRawToBmp)
* [Panoramic images computation](https://github.com/ScanVan/Equirectangular-CPP)
* [Structure from spheres pipeline](https://github.com/ScanVan/sfs-framework)
* [Spherical dataset example](https://github.com/ScanVan/sfs-framework-example)

These codes and the physical camera give access to a full city digitization pipeline. Other codes were implemented during the research phase and can be found [here](https://github.com/ScanVan).

# sfs-framework-example

The following images give an overview of the spherical image dataset content. The spherical image are obtained using the spherical central camera built during the _ScanVan_ project.

<br />
<p align="center">
<img src="https://github.com/ScanVan/sfs-framework/blob/master/doc/20190319-103833-344893.jpg?raw=true" width="384">
&nbsp;
<img src="https://github.com/ScanVan/sfs-framework/blob/master/doc/20190319-103833-594895.jpg?raw=true" width="384">
<br />
<i>Illustration of the spherical images dataset</i>
</p>
<br />

This repository offers a reference of the result you should get applying the pipeline of the provided spherical image dataset.

# Copyright and License

**sfs-framework-example** - Nils Hamel, Charles Papon, Marcelo Kaihara <br >
Copyright (c) 2018-2020 DHLAB, EPFL & HES-SO Valais-Wallis

Documentation, content and illustrations are licensed under the terms of the CC BY 4.0
