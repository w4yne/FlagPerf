### Nvidia GPU配置与运行信息参考
#### 环境配置
- ##### 硬件环境
    - 机器型号: NVIDIA DGX A100(40G) 
    - 加速卡型号: NVIDIA_A100-SXM4-40GB
    - CPU型号: AMD EPYC7742-64core@1.5G
    - 多机网络类型、带宽: InfiniBand，200Gb/s
- ##### 软件环境
   - OS版本：Ubuntu 20.04
   - OS kernel版本: 5.4.0-113-generic
   - 加速卡驱动版本：470.129.06
   - Docker 版本：20.10.16
   - 训练框架版本：pytorch-1.13.0a0+936e930
   - 依赖软件版本：
     - cuda: 11.8

### 运行情况

* 通用指标

| 指标名称       | 指标值                  | 特殊说明                              |
| -------------- | ----------------------- | ------------------------------------- |
| 任务类别       | 自然语言编码          |                                       |
| 模型           | bert-large-uncased |                                       |
| 数据集         | Wikipedia   |                                       |
| 数据精度       | precision,见“性能指标”  | 可选fp32/amp/fp16                     |
| 超参修改 | fix_hp,见“性能指标” | 跑满硬件设备评测吞吐量所需特殊超参 |
| 硬件设备简称   | nvidia A100             |                                       |
| 硬件存储使用   | mem,见“性能指标”        | 通常称为“显存”,单位为GiB              |
| 端到端时间     | e2e_time,见“性能指标”   | 总时间+Perf初始化等时间               |
| 总吞吐量       | p_whole,见“性能指标”    | 实际训练序列数除以总时间(performance_whole) |
| 训练吞吐量     | p_train,见“性能指标”    | 不包含每个epoch末尾的评估部分耗时     |
| **计算吞吐量** | **p_core,见“性能指标”** | 不包含数据IO部分的耗时      |
| 训练结果       | acc,见“性能指标”        | masked_lm任务准确率(实际/目标) |
| 额外修改项     | fp16实现方式 | nvidia使用1+8+7格式(bf16)来实现16位浮点数 |

* 性能指标

| 配置               | precision | fix_hp | e2e_time | p_whole | p_train | p_core | acc  | mem |
| ------------------ | --------- | ---- | ---- | ---- | ---- | ---- |  ---- | ---- |
| A100单机8卡（1x8） | fp32 | bs=12 | 2133.7 | 285.4 | 294.5 | 299.3 | 0.657/0.655 | 31.2/40.0 |
| A100两机8卡（1x1） | fp32 | bs=12 |  |  |     |  | |  |
| A100两机8卡（2x8） | fp32 | bs=12 |  |  |     |  | |  |

