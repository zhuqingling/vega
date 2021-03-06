# Vega

[中文](./README.cn.md)

**Vega ver1.0.0 released:**

- New algorithms: [auto-lane](./docs/en/algorithms/auto_lane.md), [AutoFIS](./docs/en/algorithms/fis-autogate.md), [AutoGroup](./docs/en/algorithms/fis-autogroup.md), [MFKD](https://arxiv.org/pdf/2006.08341.pdf).
- Feature enhancement:
  - Trainer Callbacks: The trainer supports the callback mechanism and provides nine default callbacks.
  - Report mechanism: provides a unified data collection and processing mechanism for the AutoML algorithm.
  - Multi-Backend: TensorFlow is supported.
  - Evaluator Server: Provides independent evaluation services and model evaluation of Atlas 200DK and Bolt(coming soon).
- Community Contributors: [qixiuai](https://github.com/qixiuai), [hasanirtiza](https://github.com/hasanirtiza), [cndylan](https://github.com/cndylan), [IlyaTrofimov](https://github.com/IlyaTrofimov).

## Introduction

Vega is an AutoML algorithm tool chain developed by Noah's Ark Laboratory, the main features are as follows:

1. Full pipeline capailities: The AutoML capabilities cover key functions such as Hyperparameter Optimization, Data Augmentation, Network Architecture Search (NAS), Model Compression, and Fully Train. These functions are highly decoupled and can be configured as required, construct a complete pipeline.
2. Industry-leading AutoML algorithms: provides Noah's Ark Laboratory's self-developed **[industry-leading algorithm](./docs/en/benchmark/benchmark.md)** and  **[Model Zoo](./docs/en/model_zoo/model_zoo.md)** to download the State-of-the-art (SOTA) model.
3. High-concurrency neural network training capability: Provides high-performance trainers to accelerate model training and evaluation.
4. Multi-Backend: PyTorch, TensorFlow(trial), MindSpore(coming soon)

## Algorithm list

| Category | Algorithm | Description | reference |
| :--: | :-- | :-- | :-- |
| NAS | [SM-NAS: Structural-to-Modular NAS](https://arxiv.org/abs/1911.09929) | Two-stage object detection architecture search algorithm | Coming soon |
| NAS | [CARS: Continuous Evolution for Efficient Neural Architecture Search](https://arxiv.org/abs/1909.04977) | Structure Search Method of Multi-objective Efficient Neural Network Based on Continuous Evolution | [ref](./docs/en/algorithms/cars.md) |
| NAS | SR-EA | An Automatic Network Architecture Search Method for Super Resolution | [ref](./docs/en/algorithms/sr-ea.md) |
| NAS | [ESR-EA: Efficient Residual Dense Block Search for Image Super-resolution](https://arxiv.org/abs/1909.11409) | Multi-objective image super-resolution based on network architecture search | [ref](./docs/en/algorithms/esr_ea.md) |
| NAS | [Adelaide-EA: SEGMENTATION-Adelaide-EA-NAS](https://arxiv.org/abs/1810.10804) | Network Architecture Search Algorithm for Image Segmentation | [ref](./docs/en/algorithms/Segmentation-Adelaide-EA-NAS.md) |
| NAS | [SP-NAS: Serial-to-Parallel Backbone Search for Object Detection](http://openaccess.thecvf.com/content_CVPR_2020/papers/Jiang_SP-NAS_Serial-to-Parallel_Backbone_Search_for_Object_Detection_CVPR_2020_paper.pdf) | Serial-to-Parallel Backbone Search for Object Detection Efficient Search Algorithm for Object Detection and Semantic Segmentation in Trunk Network Architecture | [ref](./docs/en/algorithms/sp-nas.md) |
| NAS | [Auto-Lane: CurveLane-NAS](https://arxiv.org/abs/2007.12147) | An End-to-End Framework Search Algorithm for Lane Lines | [ref](./docs/en/algorithms/auto_lane.md) |
| NAS | [AutoFIS](https://arxiv.org/pdf/2003.11235.pdf) | An automatic feature selection algorithm for recommender system scenes | [ref](./docs/en/algorithms/fis-autogate.md) |
| NAS | [AutoGroup](https://dl.acm.org/doi/pdf/10.1145/3397271.3401082) | An automatically learn feature interaction for recommender system scenes | [ref](./docs/en/algorithms/fis-autogroup.md) |
| Model Compression | Quant-EA: Quantization based on Evolutionary Algorithm | Automatic mixed bit quantization algorithm, using evolutionary strategy to quantize each layer of the CNN network | [ref](./docs/en/algorithms/quant_ea.md) |
| Model Compression | Prune-EA | Automatic channel pruning algorithm using evolutionary strategies | [ref](./docs/en/algorithms/prune_ea.md) |
| HPO | [ASHA: Asynchronous Successive Halving Algorithm](https://arxiv.org/abs/1810.05934) | Dynamic continuous halving algorithm | [ref](./docs/en/algorithms/hpo.md) |
| HPO | [TPE: Tree-structured Parzen Estimator Approach](https://papers.nips.cc/paper/4443-algorithms-for-hyper-parameter-optimization.pdf) | A hyperparameter optimization Algorithm Based on Tree - Structured Parzen Estimation | [ref](./docs/en/algorithms/hpo.md) |
| HPO | BO: Bayesian Optimization | Bayesian optimization algorithm | [ref](./docs/en/algorithms/hpo.md) |
| HPO | [BOHB: Hyperband with Bayesian Optimization](https://arxiv.org/abs/1807.01774) | Hyperband with Bayesian Optimization | [ref](./docs/en/algorithms/hpo.md) |
| HPO | BOSS: Bayesian Optimization via Sub-Sampling | A universal hyperparameter optimization algorithm based on Bayesian optimization framework for resource-constraint hyper-parameters search | [ref](./docs/en/algorithms/hpo.md) |
| Data Augmentation | [PBA: Population Based Augmentation: Efficient Learning of Augmentation Policy Schedules](https://arxiv.org/abs/1905.05393) | Data augmentation based on PBT optimization  | [ref](./docs/en/algorithms/pba.md) |
| Data Augmentation | [CycleSR: Unsupervised Image Super-Resolution with an Indirect Supervised Path](https://openaccess.thecvf.com/content_CVPRW_2020/papers/w31/Chen_Unsupervised_Image_Super-Resolution_With_an_Indirect_Supervised_Path_CVPRW_2020_paper.pdf) | Unsupervised style migration algorithm for low-level vision problem. | [ref](./docs/en/algorithms/cyclesr.md) |
| Fully Train | [Beyond Dropout: Feature Map Distortion to Regularize Deep Neural Networks](https://arxiv.org/abs/2002.11022) | Neural network training (regularization) based on disturbance of feature map | [ref](./docs/en/algorithms/fmd.md) |
| Fully Train | [Circumventing Outliers of AutoAugment with Knowledge Distillation](https://arxiv.org/abs/2003.11342v1) | Joint knowledge distillation and data augmentation for high performance classication model training, achieved 85.8% Top-1 accuracy on ImageNet 1k | Coming soon |

## Obtaining and Installing

The software has been released on the Releases page. Obtain the latest version and install it by following the instructions provided in the **[installation guide](./docs/en/user/install.md)** .

If you want to deploy Vega in local cluster, see the **[deployment guide](./docs/en/user/deployment.md)** .

## Usage Guide

The Vega is highly modularized. You can configure the search space, search algorithm in a pipeline way. To run the Vega application is to load the configuration file and complete the AutoML process based on the configuration.
Vega provides detailed operation examples for your reference. For details, see the **[examples](./docs/en/user/examples.md)** . Example of running CARS algorithm:

```bash
cd examples
python3 ./run_example.py ./nas/cars/cars.yml pytorch
```

Therefore, before using the Vega, you need to fully understand the meaning of the configuration items. For details, see the **[Configuration Guide](./docs/en/user/config_reference.md)**.

**Note:**

Before running an example, you need to configure the directory where the dataset and pre-trained models are located in the algorithm configuration file. Please refer to **[Example Reference](./docs/en/user/examples.md)** .

## Developer Guide

The Vega framework components are decoupled, and each functional component is combined using the registration mechanism to facilitate function and algorithm extension. For details about the Vega architecture and main mechanisms, see the **[Developer Guide](./docs/en/developer/developer_guide.md)** .

In addition, you can refer to the **[Quick Start Guide](./docs/en/developer/quick_start.md)** to implement a simple network search function and quickly enter the Vega application development through practice.

During the development of the Vega application, the first problem is how to introduce the service data set to the Vega application. For details, see the **[Dataset Guide](./docs/en/developer/datasets.md)** .

For different algorithms, you can refer doc **[Algorithm Development Guide](./docs/en/developer/new_algorithm.md)** . You can add the new algorithm to Vega step by step based on the example provided in this document.

In most Automl algorithms, the search space is closely related to the network. We try to unify the definition of the search space so that the same search space can adapt to different search algorithms. This is called the **[Fine-Grained Search Space Guide](./docs/en/developer/fine_grained_search_space.md)** . Welcome to try it.

Of course, this document cannot solve all the problems. If you have any questions, please feel free to provide feedback through the issue. We will reply to you and solve your problems in a timely manner.

## Reference List

| object | refrence |
| :--: | :-- |
| User | [Install Guide](./docs/en/user/install.md), [Deployment Guide](./docs/en/user/deployment.md), [Configuration Guide](./docs/en/user/config_reference.md), [Examples](./docs/en/user/examples.md), [Evaluate Service](./docs/en/user/evaluate_service.md) |
| Developer | [Developer Guide](./docs/en/developer/developer_guide.md), [Quick Start Guide](./docs/en/developer/quick_start.md), [Dataset Guide](./docs/en/developer/datasets.md), [Algorithm Development Guide](./docs/en/developer/new_algorithm.md), [Fine-Grained Search Space Guide](./docs/en/developer/fine_grained_search_space.md) |

## Cooperation and contribution

Welcome to use Vega. If you have any questions, ask for help, fix bugs, contribute algorithms, or improve documents, submit the issue in the community. We will reply to and communicate with you in a timely manner.
Welcome to join our QQ chatroom (Chinese): **833345709**.
