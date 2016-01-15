# エヌビディアのディープラーニング戦略

エヌビディア合同会社　プラットフォームビジネス本部　部長　林 憲一

* Nvidia
  * !半導体ベンダー　ソリューションの提供-> ライブラリ提供
* Big Sur Facebook のオープンhardware
  https://code.facebook.com/posts/1687861518126048/facebook-to-open-source-ai-hardware-design/

## トレーニング用

* TESLA M40
  * 信頼性高め
  * 7TFLOPs

## サービス提供用

+ TESLA M4
  * 消費電力低め
  * PCIExLowProfile
  * 2.2TFLOPs

## ディープラーニングSDK

ライブラリの概要説明

### cuDNN

* LATEST version4
+ x86/ARM/Power8
* Batch normalizatin
  * http://arxiv.org/pdf/1502.03167.pdf

### cuSPARSE

* 密行列x疎ベクター

### cuBLASE

+ FP16ストレージ

### NCCL

* multiple gpu 集合ライブラリ
  * https://github.com/NVIDIA/nccl
  * MPI的な

### DIGIT

* https://github.com/NVIDIA/DIGITS/
  * ローカルで立てることは可能らしい(要登録?)
  * http://qiita.com/kendemu/items/a52e37b5e309e83a057b
  * 中身はPython
  * Hardware込みのパッケージも存在　Nvidia Digits DevBox　https://developer.nvidia.com/devbox

### Jetson X1

* Jetpack
  * Jetson向けのSDKpackage
  * OpenGL
  * cuDNN
  * visionworks
  　* https://developer.nvidia.com/embedded/visionworks
    * OpenCVへのインターフェースライブラリ
    * OpenVXというのも入っている
  * cuda
  * nsight
    * http://www.nvidia.co.jp/object/parallel-nsight-jp.html
  * nvtx
    * http://http.developer.nvidia.com/ParallelNsight/1.51/UserGuide/HTML/How_To_Use_the_NVIDIA_Tools_Extension_Library_(nvtx).html

### Chainer

* DL
  * 年1500の論文
  * 最近は100層以上のレイヤーを用いている
    * Googleが優勝した時は24層
* オンデマンドにネットワークを構築    

### TesnorFlow

* Mike Schuster(開発者)
  * 日本語で発表(昔はNTTにいたらしい)

* http://japan.cnet.com/news/service/35076183/
* Googleでも2011年までは機械学習関連のグループは存在していなかった
* TensorFlowは2世代目の機械学習システム
  * Google内部では3世代目まで行っているか... Hadoop関連でもそうだったし
  * http://tesnorflow.org
* BaseはC++
* 柔軟性が高い

### docomo Developer supportにおける画像認識API

* https://dev.smt.docomo.ne.jp/
* 画像認識用のREST APIを提供
　* SiriみたいなAPIもある
* 従来のComputer Visionを用いた名称判定とDeeplearingを用いたカテゴリ判定が行える

### Matlabでの深層学習

+ gpgpuでやるには
```
I = gpuarray(I)
CPUでするような処理
I = gather(I)
```

* CNNは載っていない．MatConvNet(OSS)を使えば可能
  * cuDNN v4に対応
* 転移学習
  * 学習済みのCNNを流用して別の判別に利用
  * デモ (40行ぐらい)

### 自動運転

* DrivePX2
  * http://www.engadget.com/2016/01/04/nvidia-drive-px2/
  * 水冷ボード
  * PASCAL arch

*
