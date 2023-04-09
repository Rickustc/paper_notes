# Introduction：

Motivation

- task：referring image segmentation（natural linguistic expression）属于视觉图像underatanding任务
- Existing approaches use pretrained models to facilitate learning, yet separately transfer the language/vision knowledge from pretrained models, ignoring the multi-modal corresponding information.
- Inspired by CLIP

Relative Work

- pretrained models to facilitate learning（How？）
-  they mainly utilize a single-modal pretraining (e.g., the pretrained image or text encoder), which is short of multi-modal correspondence information.
- CLIP多模态学习语言监督图像，但是CLIP没法直接用到分割里(duo to the discrepancy between image-level and pixel-level prediction. The former focuses on the global information of an input image, while the latter needs to learn fine-grained visual representations for each spatial activation.)

Methods

- <img src="C:\Users\wrq\Desktop\坚果云同步\我的坚果云\Rainbell English1\Rainbell English\paper\paper_notes\image\image-20230407164541150.png" alt="image-20230407164541150" style="zoom:33%;" />


