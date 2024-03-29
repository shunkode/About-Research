# Theme - "Permanent underwater observation in the field"

## Keywords
Python, Raspberry Pi, Cloud, Dropbox API, Motion Detection, AI, YOLO, SDGs


## 1. Introduction
### 1.1. River observation
In order to improve the fish run-up and descent environment, the "Model Project for Promotion of River Creation Easy for Fish to Climb" was started in fiscal 1991 to construct or improve fish passage and ensure fish passage flow rate for river crossing facilities (Ministry of Land, Infrastructure, Transport and Tourism 2005). (2022) confirmed ayu run-up using a time-lapse camera and a deep learning model to evaluate fish passage. However, time-lapse cameras have disadvantages such as temporal discontinuity, low information content compared to video data, and the need for data recovery. In this study, we develop a quasi-real-time underwater observation system for continuous observation of underwater organisms and analysis using a deep learning model.<br><br>
魚類の遡上・降下環境の改善を目的に，河川横断施設について，魚道の新設・改善，魚道流量の確保等を実施すべく，｢魚がのぼりやすい川づくり推進モデル事業｣が平成３年度から開始された（[国土交通省 2005](https://www.mlit.go.jp/river/shishin_guideline/kankyo/kankyou/sakana_tebiki/pdf/print.pdf)）．魚道の評価として，[藩ら（2022）](https://www.jstage.jst.go.jp/article/jscejhe/78/2/78_I_127/_pdf/-char/ja)は，タイムラプスカメラと深層学習モデルを用いてアユの遡上を確認したが，タイムラプスカメラは，時間的断絶がある，動画データに比べ情報量が少ない，データの回収が必要である，といった欠点がある．

### 1.2. Purpose
This study will develop a quasi-real-time underwater observation system for continuous observation of underwater organisms and analysis using deep learning models. Observations are acquired continuously as video data, not image data. The system to be developed in this study must be universally observable, and must be able to be installed in any location. Therefore, we will use a Raspberry Pi 4 as the processing unit and work to reduce the size of the system. In addition, there are problems in conducting field observations, such as limited data capacity in the local environment, time-consuming data collection work, and the inability to check data until it has been collected. Therefore, a motion detection function is incorporated to reduce the amount of data by only capturing images when an object is moving. In addition to this, the data is transferred to the cloud to solve the problem. In addition, since there is no power source in the field, power saving and power generation using renewable energy (solar power generation) will be used to solve the problem.
In addition to field observations, the counting process will be automated. The video images taken will be analyzed for fish species using YOLOv5 to reduce the need for species identification. This analysis will be performed using a PC set up indoors.
![Problems and Solutions for Field Observation by Video Recording](https://github.com/shunkode/shunkode/assets/106649051/b1d9deb4-0694-4f42-bfee-3106471d0564)

本研究では，水中の生物の連続的観測及び深層学習モデルによる解析を行うための準リアルタイム水中観測システムを開発する．観測は画像データではなく、動画データとして連続的なデータを取得する。本研究で開発するシステムは、汎用的に観測可能であることを必須要件としており、どのような場所でも設置可能でなければならない。そこで、処理装置としてRaspberry Pi 4 を用い、小型化に取り組む。また、野外での観測を行うにあたって、ローカル環境におけるデータ容量の限界、データ回収作業の手間、データは回収するまで確認することができないといった問題がある。そこで、動体検知機能を取り入れ物体が動いた場合のみ撮影することによりデータ量を削減する。これに加え、データをクラウドへ転送することにより、問題の解決を図る。また、野外では電源が無いという問題も発生するため、省電力化及び再生可能エネルギーを用いた発電（太陽光発電）により対処する。
野外での観測に加え、計数作業においても自動化を行う。撮影した動画について、YOLOv5を用い魚種の解析を行うことで種の同定作業を軽減する。本解析は室内に設置したPCを用いて行う。
![動画撮影による野外観測の問題点と解決策](https://github.com/shunkode/shunkode/assets/106649051/e533d3a8-d49a-4251-97f3-5bda95f4657a)


## 2. System Overview
![system overview](https://github.com/shunkode/shunkode/assets/106649051/ee441338-43b6-4704-97be-0daf7a0d7aa6)
![システム概要](https://github.com/shunkode/shunkode/assets/106649051/fec67b7e-cce3-45d5-82bc-b2a0d9220b1e)

