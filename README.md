# Deployment

[![Build Status](https://travis-ci.org/Trace-Share/Deployment.svg?branch=master)](https://travis-ci.org/Trace-Share/Deployment)

Automated deployment of the Trace-Share environment

<br>



# <img src="https://is.muni.cz/www/325314/logo.png" width="50%"/>

Research validation and verification are fundamental principles of good scientific work. In terms of research in the area of network traffic measurement and analysis, however, these principles pose a great challenge. The research heavily depends not only on the correct processes of data usage but also on the availability of network traffic datasets that meet the common requirements and are publicly available. Without these datasets, we will never be able to reliably repeat, validate, and analyze research results.

The main idea of Trace-Share is based on annotated units of network traffic that can be synthetically generated, or derived from real-world traffic. These units typically contain only a minimum of personal data, so they can be shared and, thanks to the restrictions on the inclusion of interest-related traffic only, be easily annotated. They can be also easily normalized and combined with each other or with a real-world traffic to create semi-labeled datasets.

**Details and main ideas of the project are available in the publicly available publication [Towards Provable Network Traffic Measurement and Analysis via Semi-Labeled Trace Datasets](https://doi.org/10.23919/TMA.2018.8506498).**


## Project Organization Structure

The project is organized within the [Trace-Share](https://github.com/Trace-Share) organization distrubuted over different repositories to simplify development. Please see their individual readme's and issue trackers if you like to contribute.

- [Trace-API](https://github.com/Trace-Share/Trace-API) – REST API to support processing of packet traces
- [ID2T](https://github.com/Trace-Share/ID2T) – fork of the official ID2T repository extended by functions to modify and combine existing packet traces
- [Deployment](https://github.com/Trace-Share/Deployment) - automated deployment of the Trace-Share environment


## Get Involved

**Are you interested in research collaboration or want to contribute? Don't hesitate to contact us at [https://csirt.muni.cz](https://csirt.muni.cz/about-us/contact?lang=en)!**
