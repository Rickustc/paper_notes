# Few-Shot Parameter-Efficient Fine-Tuning is Better and Cheaper than In-Context Learning

## Introduction

### Motivation：

- 微调的缺点：大模型微调high const

- in-context learning： inputt prompted examples(输入prompt实例) Few-shot prompting converts a small collection of input-target pairs into (typically) human-understandable instructions and examples（小样本prompt将下游输入变换到人类理解的指令和实例）

- ICL优点： requires no gradient-based training ，therefore allows a single model to immediately perform a wide variety of tasks（不用单独为任务训练模型，直接输不同任务的prompt对）

- ICL缺点：compute costs/worse than fintuning /由于prompt带来的unpredictable impact



- PEFT：某些PEFT方法同样允许处理多任务（为什么）

提出一种few-shot PEFT

### Methods：

- 一种新的PEFT方法
- 一种新的loss

Relative Works:



