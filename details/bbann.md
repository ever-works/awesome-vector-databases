## Overview

BBANN was the Track 2 winner in the NeurIPS'21 Billion-Scale Approximate Nearest Neighbor Search Competition. Track 2 focuses on out-of-core indices where, in addition to limited DRAM, the index can use an SSD for search. The hardware uses Azure Standard_L8s_v2 VMs with 8 vCPUs, 64GB RAM, and a local SSD constrained to 1TB.

## Competition Details

| Property | Value |
|----------|-------|
| Track | T2 (Out-of-core indices) |
| Baseline | DiskANN |
| Target QPS | 1,500 queries/sec |
| Hardware | Azure Standard_L8s_v2 (8 vCPUs + 64GB RAM + 1TB SSD) |

## Team

Xiaomeng Yi, Xiaofan Luan, Weizhi Xu, Qianya Cheng, Jigao Luo, Xiangyu Wang, Jiquan Long, Xiao Yan, Zheng Bian, Jiarui Luo, Shengjun Li, Chengming Li from Zilliz and Southern University of Science and Technology.