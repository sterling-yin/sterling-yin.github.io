---
title: "基于机器学习的超高韧性水泥基复合材料板在近场爆炸荷载作用下的损伤预测"
authors:
- 银星
- 李庆华*
# author_notes:
# - "Equal contribution"
# - "Equal contribution"
date: "2025-09-01T00:00:00Z"

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ["article-journal"]

# Publication name and optional abbreviated publication name.
publication: "***工程力学***, 137, 104911"

abstract: 结合使用高保真数值分析技术和机器学习方法，对600 mm跨度的超高韧性水泥基复合材料（UHTCC）板在1 kg当量以内的近场爆炸荷载作用下的损伤模式进行研究和预测，采用流固耦合算法建立了包含300个样本的UHTCC板爆炸响应数据库，分别使用既有的经验性预测方法和可解释性机器学习方法进行分析。结果表明：既有的McVay和Morishita经验方法仅能预测贯穿失效，而UFC 3-340-02方法无法预测所有损伤模式；基于极端梯度提升（XGBoost）算法建立的机器学习模型在分层10折交叉验证中表现优秀，能够实现对UHTCC板近场爆炸损伤的快速预测；不同损伤模式下的特征重要性不同，材料的拉压强度比在层裂和弯曲损伤中较为重要，可据此优化材料和结构设计，提升防护结构抗爆性能。

tags:
- Blast Protection
- SHCC
featured: true

links:
  - type: doi
    url: "https://doi.org/10.6052/j.issn.1000-4750.2024.10.07911"

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/jdD8gXaTZsc)'
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---