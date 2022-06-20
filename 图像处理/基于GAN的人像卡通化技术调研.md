摘要

> 建立卡通化3D人臉在電腦圖學領域中是一個有趣和實用的研究題目。然而，仍舊缺乏在保持重要特徵的條件下，將2D的人臉影像轉成3D卡通人臉的工具
> 大部分被提出來做卡通人臉和2D人臉影像合成的方法。在前置處理步驟，臉部特徵和輪廓通常使用影像處理的方法來擷取，例如使用邊緣檢測的方式來處理。接著，將人臉部分轉換成具有特定風格的NPR(Non-Photorealistic Rendering)圖像，例如:將人像照片轉換成水彩畫、油畫或鉛筆素描等等具有不同筆觸效果的肖像畫。
> 在這篇論文中，我們提出一個不同的方法來將2D的臉部影像轉換成3D的卡通臉部模型。這個3D的卡通模型對於製造和客製化3D Q版可愛公仔將會非常的實用。
> 我們使用DXUT (The DirectX Utility Library) 架構來開發使用者介面，而且採用了Open CV( Open Source Computer Vision Library ) 這一套電腦視覺函式庫來自動偵測臉部特徵的位置。然後，讓使用者藉由點選和移動特徵點來調整臉部的網格模型。
> 當把臉部網格模型調整到符合所輸入的臉部影像，原始基本模型就會被調整和變形為相對應的臉部模型。眼睛和嘴巴的外型也被提取出來，並使用紋理映射來合成類似卡通的影像。



参考文献



* [U-GAT-IT 论文解读](https://zhuanlan.zhihu.com/p/76936166?utm_source=wechat_session&utm_medium=social&utm_oi=697538167472947200&utm_campaign=shareopn)
* [U-GAT-IT 论文](https://arxiv.org/pdf/1907.10830.pdf)
* [Cycle-GAN 论文](https://arxiv.org/pdf/1907.01424.pdf)
* [Cycle-GAN 论文解读](https://zhuanlan.zhihu.com/p/73995207)
* [预印本论文网站 ](https://arxiv.org/)
* [卡通化3d人脸产生系统 ](https://ndltd.ncl.edu.tw/cgi-bin/gs32/gsweb.cgi/login?o=dnclcdr&s=id=%22098NCNU0392048%22.&searchmode=basic#XXX)
* [GAN原理简述](https://zhuanlan.zhihu.com/p/66489938)
* [GAN基础知识以及GAN应用](https://zhuanlan.zhihu.com/p/27663139)