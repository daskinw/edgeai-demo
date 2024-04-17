# Edge AI Software And Development Tools



### What is Texas Instruments (TI) Edge AI?

Texas Instruments (TI) Edge AI is an advanced framework designed to facilitate the embedding of deep learning models into devices at the edge of the network. It is particularly tailored for environments where computing power is limited and efficiency is crucial. TI's Edge AI platform aims to address the high computational demands of deep learning technologies by optimizing and accelerating the inference process on TI’s embedded devices.

The platform supports a heterogeneous execution environment, allowing deep neural networks (DNNs) to run across various processing units such as Cortex-A based MPUs, TI's cutting-edge C7x digital signal processors (DSPs), and the Deep Neural Network accelerator (MMA). This execution strategy ensures that each part of the deep learning model operates on the most suitable processing unit, maximizing performance and energy efficiency.

TI's Edge AI not only makes it possible to bring the power of deep learning to edge devices but also simplifies the development process for engineers and developers. With comprehensive software products and developer-friendly resources, TI provides tools and documentation to ensure a seamless experience from development to deployment.

## Notice

Our documentation landing pages are the following:

* https://www.ti.com/edgeai : Technology page summarizing TI’s edge AI software/hardware products
* https://github.com/TexasInstruments/edgeai : Landing page for developers to understand overall software and tools offering

## Introduction

Embedded inference of Deep Learning models is quite challenging - due to high compute requirements. TI’s Edge AI comprehensive software product help to optimize and accelerate inference on TI’s embedded devices. It supports heterogeneous execution of DNNs across cortex-A based MPUs, TI’s latest generation C7x DSP and DNN accelerator (MMA).

TI's Edge AI solution simplifies the whole product life cycle of DNN development and deployment by providing a rich set of tools and optimized libraries.

## Overview

The figure below provides a high level summary of the relevant tools:\
![](assets/workblocks\_tools\_software.png)

## Details of various tools

The table below provides detailed explanation of each of the tools:

| Category                                                | Tool/Link                                                                                                                                                                                                                                                                                                                                                 | Purpose                                                                                                                                                                                                                                                                                                                                                                                                                                                              | IS NOT                                                                                                                                                                                                                                                                                                                                                             |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Model training & associated tools**                   | [edgeai-modelzoo](https://github.com/TexasInstruments/edgeai-modelzoo)                                                                                                                                                                                                                                                                                    | <p><strong>Model Zoo</strong><br>- To provide collection of pretrained models and documemtation</p>                                                                                                                                                                                                                                                                                                                                                                  |                                                                                                                                                                                                                                                                                                                                                                    |
| ditto                                                   | [Model optimization tools](https://github.com/TexasInstruments/edgeai-modeloptimization)                                                                                                                                                                                                                                                                  | <p><strong>Model optimization tools</strong><br>- <strong>Model surgery</strong>: Modifies models with minimal loss in accuracy and makes it suitable for TI device (replaces unsupported operators)<br>- <strong>Model Pruning/sparsity</strong>: Induces sparsity during training – only applicable for specific devices<br>- <strong>QAT</strong>: <strong>Quantization Aware Training</strong> to improve accuracy with fixed point quantization<br></p>         | - Does not support Tensorflow                                                                                                                                                                                                                                                                                                                                      |
| ditto                                                   | <p><a href="https://github.com/TexasInstruments/edgeai-torchvision">edgeai-torchvision</a><br><a href="https://github.com/TexasInstruments/edgeai-mmdetection">edgeai-mmdetection</a><br><a href="https://github.com/TexasInstruments/edgeai-yolov5">edgeai-yolov5</a><br><a href="https://github.com/TexasInstruments/edgeai-yolox">edgeai-yolox</a></p> | <p>Training repositories for various tasks<br>- Provides extensions of popular training repositories (like mmdetection, yolox) with lite version of models</p>                                                                                                                                                                                                                                                                                                       | - Does not support Tensorflow                                                                                                                                                                                                                                                                                                                                      |
| **Inference (and compilation) Tools**                   | [edgeai-tidl-tools](https://github.com/TexasInstruments/edgeai-tidl-tools)                                                                                                                                                                                                                                                                                | <p>To get familiar with model compilation and inference flow<br>- <a href="https://github.com/TexasInstruments/edgeai-tidl-tools/blob/master/docs/tidl_fsg_quantization.md">Post training quantization</a><br>- Benchmark latency with out of box example models (10+)<br>- Compile user / custom model for deployment<br>- Inference of compiled models on X86_PC or TI SOC using file base input and output<br>- Docker for easy development environment setup</p> | <p>- Does not support benchmarking accuracy of models using TIDL with standard datasets, for e.g. - accuracy benchmarking using MS COCO dataset for object detection models. Please refer to edgeai-benchmark for the same.<br>- Does not support Camera, Display and inference based end-to-end pipeline development. Please refer Edge AI SDK for such usage</p> |
| ditto                                                   | [edgeai-benchmark](https://github.com/TexasInstruments/edgeai-benchmark)                                                                                                                                                                                                                                                                                  | <p>Bring your own model and compile, benchmark and generate artifacts for deployment on SDK with camera, inference and display (using edgeai-gst-apps)<br>- Comprehends inference pipeline including dataset loading, pre-processing and post-processing<br>- Benchmarking of accuracy and latency with large data sets<br>- Post training quantization<br>- Docker for easy development environment setup</p>                                                       |                                                                                                                                                                                                                                                                                                                                                                    |
| **Integrated environment for training and compilation** | [Edge AI Studio: Model Analyzer](https://www.ti.com/tool/EDGE-AI-STUDIO)                                                                                                                                                                                                                                                                                  | <p>Browser based environment to allow model evaluation with TI EVM farm<br>- Allow model evaluation without and software/hardware setup at user end<br>- User can reserve EVM from TI EVM farm and perform model evaluation using jupyter notebook<br>- <strong>Model selection tool</strong>: To provide suitable model architectures for TI devices</p>                                                                                                            | - Does not support Camera, Display and inference based end-to-end pipeline development. Please refer Edge AI SDK for such usage                                                                                                                                                                                                                                    |
| ditto                                                   | [Edge AI Studio: Model Composer](https://www.ti.com/tool/EDGE-AI-STUDIO)                                                                                                                                                                                                                                                                                  | <p>GUI based Integrated environment for data set capture, annotation, training, compilation with connectivity to TI development board<br>- Bring/Capture your own data, annotate, select a model, perform training and generate artifacts for deployment on SDK<br>- Live preview for quick feedback</p>                                                                                                                                                             | - Does not support Bring Your Own Model workflow                                                                                                                                                                                                                                                                                                                   |
| ditto                                                   | [Model Maker](https://github.com/TexasInstruments/edgeai-modelmaker)                                                                                                                                                                                                                                                                                      | <p>Command line Integrated environment for training &#x26; compilation<br>- Bring your own data, select a model, perform training and generate artifacts for deployment on SDK<br>- Backend tool for model composer (early availability of features compared to Model Composer )</p>                                                                                                                                                                                 | - Does not support Bring Your Own Model workflow                                                                                                                                                                                                                                                                                                                   |
| **Edge AI Software Development Kit**                    | [Devices & SDKs](readme\_sdk.md)                                                                                                                                                                                                                                                                                                                          | <p>SDK to develop end-to-end AI pipeline with camera, inference and display<br>- Different inference runtime: TFLiteRT, ONNXRT, NEO AI DLR, TIDL-RT<br>- Framework: openVX, gstreamer<br>- Device drivers: Camera, display, networking<br>- OS: Linux, RTOS<br>- May other software modeus: codecs, OpenCV,…</p>                                                                                                                                                     |                                                                                                                                                                                                                                                                                                                                                                    |

## Workflows

Bring your own model (BYOM) workflow:\
![](assets/workflow\_bring\_your\_own\_model.png)

Train your own model (TYOM) workflow:\
![](assets/workflow\_train\_your\_own\_model.png)

Bring your own data (BYOD) workflow:\
![](assets/workflow\_bring\_your\_own\_data.png)

***

## Publications

Read some of our [**Technical publications**](readme\_publications.md)

***

## Issue Trackers

**Issue tracker for** [**Edge AI Studio**](https://www.ti.com/tool/EDGE-AI-STUDIO) is listed in its landing page.

[**Issue tracker for TIDL**](https://e2e.ti.com/support/processors/f/791/tags/TIDL): Please include the tag **TIDL** (as you create a new issue, there is a space to enter tags, at the bottom of the page).

[**Issue tracker for edge AI SDK**](https://e2e.ti.com/support/processors/f/791/tags/EDGEAI) Please include the tag **EDGEAI** (as you create a new issue, there is a space to enter tags, at the bottom of the page).

[**Issue tracker for ModelZoo, Model Benchmark & Deep Neural Network Training Software**](https://e2e.ti.com/support/processors/f/791/tags/MODELZOO)**:** Please include the tag **MODELZOO** (as you create a new issue, there is a space to enter tags, at the bottom of the page).

***

## What is New

* \[2023-Dec] Updated link to Model Optimization Tools
* \[2023-May] Documentation update and restructure.
* \[2023-March] Several of these repositories have been updated
* \[2022-April] Several of these repositories have been updated
* \[2021-August] Several of our repositories are being moved from git.ti.com to github.com
* \[2021-December-21] Several of our repositories are being updated in preparation for the 8.1 (08\_01\_00\_xx) release. These include edgeai-tidl-tools, edgeai-benchmark, edgeai-modelzoo and edgeai-torchvision. A new version of PROCESSOR-SDK-LINUX-SK-TDA4VM that corresponds to this will be available in a few days.
* \[2022-April-5] Several of the repositories are being updated in preparation for the 8.2 (08\_02\_00\_xx) release.

***

## License

Please see the [LICENSE](LICENSE/) file for more information about the license under which this landing repository is made available. The LICENSE file of each repository mentioned here is inside that repository.
