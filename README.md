# Landsat Land-Cover Classification and Vegetation Mapping

## 中文概览

### Landsat 土地覆盖分类与植被分析

使用 ENVI 处理墨尔本东南部的 Landsat 8 影像，通过波段组合、影像增强、波段比值和 NDVI 分析地表特征，并完成六类土地覆盖的最大似然分类。

- **个人工作**：主要负责 ENVI 影像处理，并参与报告方法与结论部分的撰写。项目结果由团队共同完成。
- **分类结果**：所选测试区域的总体分类精度约为 **97.86%**，Kappa 为 **0.9228**；居民地类别的生产者精度（召回率）约为 **76.21%**，说明各类地物的识别效果存在差异。
- **成果展示**：提供土地覆盖分类图、NDVI 图、混淆矩阵，以及处理方法和复现步骤说明。

精度指标来自人工选取的测试 ROI（感兴趣区域），水体像元占比较高，尚不能据此推断整个地区或其他影像的分类效果。当前仓库保留报告中的结果图；重算需要原始栅格和 ROI 文件。

## English documentation

An ENVI case study using Landsat 8 imagery of southeast Melbourne. The workflow combines visual enhancement, spectral indices and supervised maximum-likelihood classification into six classes: water, forest, low vegetation, settlement, bare land and cloud.

### My contribution

The submitted team report states that I was primarily responsible for conducting the ENVI image-processing tasks, with support from all group members. I also contributed to the Methods and Conclusion. The Results, Discussion and other writing remain attributed to the team. See [contribution statement](docs/CONTRIBUTIONS.md).

### Original outputs

![Six-class land-cover output](assets/land-cover-classification.png)

![NDVI map](assets/ndvi.png)

The images are unchanged figures extracted from the team report. They are report illustrations, not georeferenced downloadable raster products. The NDVI legend in the original is small; no exact pixel values should be read from this screenshot.

### Evaluation and what it means

| Measure | Original reported result | Interpretation |
| --- | ---: | --- |
| Overall accuracy | 97.86% | Agreement with selected test ROI pixels |
| Kappa | 0.9228 | Chance-adjusted agreement on those ROIs |
| Settlement producer's accuracy | 76.21% | Recall for the selected settlement reference pixels |
| Settlement user's accuracy | 75.62% | Precision for settlement predictions on the evaluated pixels |

![Original ENVI confusion matrix](assets/confusion-matrix.png)

Water dominates the evaluated pixel population. High overall accuracy therefore coexists with weaker settlement performance. A useful follow-up is to examine settlement/bare-land/low-vegetation confusion and validate with more representative, spatially separated reference samples. No region-wide area accuracy or independent geographic generalisation is claimed.

### Workflow and reproducibility

Read the [case study](docs/CASE_STUDY.md), [manual workflow](docs/REPRODUCE.md) and [review notes](docs/REVIEW.md). ENVI was the original analysis tool; no Python reimplementation or newly trained model is claimed. Raw imagery, training/test ROI files and the ENVI project were not found in the reviewed project folder, so the processing has not been rerun.

Originally GEOM30009 Imaging the Environment, Assignment 3, University of Melbourne, 2026. This is a team coursework portfolio case study. Student numbers, course instructions and third-party reference figures are omitted. No new licence is assigned to team figures or underlying imagery.
