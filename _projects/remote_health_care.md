---
layout: page
title: Remote Health Care
description: Remote health checkup using AI and by providing the data from health sensors to doctor over the Internet.
img: assets/img/remote_health_care.jpeg
importance: 2
category: Academic
---

The data were collected from ECG and other health sensors using NodeMCU as a microcontroller. The collected data was sent to a django server through Rest API. The data after it was received by the server was saved into the database. The doctor will be able to view the health record of the patient and provide the necessary prescription. The 1-D CNN model was also trained on the ECG data to predict different classes of arrhythmia. This project was presented in the 5<sup>th</sup> Internation Workshop on Effective Engineering Education during **Sakura Science Exchange Program** hosted by National Institute of Technology in Japan.

Slides: [5<sup>th</sup> IWEEE](/assets/pdf/remote_health_care.pdf)  
Github repo: [remote-health-care](https://github.com/nisheshawale/remote-health-care)

**Technologies used:** Tensorflow, Django, HTML, CSS, Bootstrap, NodeMCU
