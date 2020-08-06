# Overview

This repository provides the example dataset of _spherical images_ used to illustrate the _spherical framework_ of the _ScanVan Project_ that deduces three dimensional models from the images. Its contains the images dataset, the _YAML_ configuration file needed to run the framework on the images and all the obtained framework results, including the framework logs.

# ScanVan Project

The _ScanVan Project_ was funded by the Swiss National Science Foundation (SNF, PNR 76 Big Data) and won by the _DHLAB_ of _EPFL_ and the _HES-SO Valais Wallis_. The goal of the project was to demonstrate the possibility of city mass and continuous digitization using central spherical cameras. Using such device allows to simplify the 3D structures computation and to drastically decrease the complexity of images acquisition.

The _EPFL_ team realized the theoretical design of the camera and defined a new pose estimation algorithm able to be applied to the case of images acquired by such device. The _HES-SO Valais Wallis_ were in charge of translating the theoretic design of the camera into a physical device achieving the centrality. The codes implementation, validation and testing was shared between the two teams.

Summary of the _ScanVan Project_ codes :

* [Camera calibration](https://github.com/ScanVan/Calibration-CPP)
* [Camera images acquisition](https://github.com/ScanVan/CameraImageAcquisition-CPP)
* [Camera images debayering](https://github.com/ScanVan/ConvertRawToBmp)
* [Panoramic images computation](https://github.com/ScanVan/Equirectangular-CPP)
* [Structure from spheres framework](https://github.com/ScanVan/sfs-framework)
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

The following image gives a view of the central spherical camera built during the project and used to produce the dataset of images :

<br />
<p align="center">
<img src="https://github.com/ScanVan/sfs-framework/blob/master/doc/camera.jpg?raw=true" width="384">
<br />
<i>Central spherical camera prototype</i>
</p>
<br />

The five images of this dataset, located in the _image_ directory, are stored in portable network graphic format. The configuration _YAML_ file is located in the root directory and named _config.yaml_. The mask image, provided to the pipeline to discard the camera and vehicle related pixel is located also in the root directory and is named _mask.png_.

The _output_ directory stores all the outputs created by the framework when applied on this dataset, including the logs located in the _logs_ file. For both _sparse_ and _dense_ modes, four files are created in the _output_ directory :

* sparse/dense_constraint.dat
* sparse/dense_position.xyz
* sparse/dense_structure.xyz
* sparse/dense_transformation.dat

The _position_ model file contains the computed position of the images in the frame of the first image. The _structure_ model file contains all the point place during sparse or dense computation. The _structure_ file then contains the model itself.

The _transformation_ file contains the position and orientation of each image, line by line, expressed in the frame of the first camera. Each line contains the name of the image, the position of the image and its orientation matrix. The _constraint_ file contains all the three dimensional points placed during the computation along with their color,
the amount of image it is seen from and the index of these images, again, line by line.

Finally, in the _dense_ and _sparse_ folders, you will find this four files kept for each step of the framework. Each time an image is added, a copy of these four files is kept and stored in these two folders.

Using the provided images and the provided configuration _YAML_ file, you should obtain the following sparse model :

<br />
<p align="center">
<img src="https://github.com/ScanVan/sfs-framework/blob/master/doc/sparse-1.jpg?raw=true" width="384">
&nbsp;
<img src="https://github.com/ScanVan/sfs-framework/blob/master/doc/sparse-2.jpg?raw=true" width="384">
<br />
<i>Example of sparse model obtain with a sequence of five spherical images</i>
</p>
<br />

and the following dense model :

<br />
<p align="center">
<img src="https://github.com/ScanVan/sfs-framework/blob/master/doc/dense-1.jpg?raw=true" width="384">
&nbsp;
<img src="https://github.com/ScanVan/sfs-framework/blob/master/doc/dense-2.jpg?raw=true" width="384">
<br />
<i>Example of dense model obtain with a sequence of five spherical images</i>
</p>
<br />

This dataset should allow you to reproduce our results and train you to apply the framework on your own images.

# Copyright and License

**sfs-framework-example** - Nils Hamel, Charles Papon, Marcelo Kaihara <br >
Copyright (c) 2018-2020 DHLAB, EPFL & HES-SO Valais-Wallis

Documentation, content and illustrations are licensed under the terms of the CC BY 4.0
