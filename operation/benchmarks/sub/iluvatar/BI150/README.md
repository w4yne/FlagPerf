# 参评AI芯片信息

* 厂商：ILUVATAR

* 产品名称：BI150
* 产品型号：BI150
* TDP：W

# 所用服务器配置

* 服务器数量：1


* 单服务器内使用卡数：1
* 服务器型号：
* 操作系统版本：Ubuntu 20.04.6 LTS
* 操作系统内核：linux5.4.0-148-generic
* CPU：
* docker版本：20.10.25
* 内存：
* 服务器间AI芯片直连规格及带宽：此评测项不涉及服务期间AI芯片直连

# 算子库版本
FlagGems:>联系邮箱: contact-us@iluvatar.com获取版本(FlagGems-0710_pointwise_use_tid)

# 评测结果

## 核心评测结果

| 评测项  | 平均相对误差(with FP64-CPU) | TFLOPS(cpu wall clock) | TFLOPS(kernel clock) | FU(FLOPS Utilization)-cputime | FU-kerneltime |
| ---- | -------------- | -------------- | ------------ | ------ | ----- |
| flaggems | 1.63E-08    | 0.1TFLOPS       | 0.1TFLOPS        | 0.39% | 0.39% |
| nativetorch | 1.63E-08    | 0.1TFLOPS      | 0.1TFLOPS      | 0.4%      | 0.4%    |

## 其他评测结果

| 评测项  | 相对误差(with FP64-CPU)标准差 | cputime | kerneltime | cputime吞吐 | kerneltime吞吐 | 无预热时延 | 预热后时延 |
| ---- | -------------- | -------------- | ------------ | ------------ | -------------- | -------------- | ------------ |
| flaggems | 7.77E-10    | 11201.1us       | 11214.15us        | 89.28op/s | 89.17op/s | 257699.96us | 11638.84us |
| nativetorch | 7.77E-10    | 10871.35us       | 10917.02us        | 91.98op/s | 91.6op/s | 11248.25us | 11163.73us |

## 能耗监控结果

| 监控项  | 系统平均功耗  | 系统最大功耗  | 系统功耗标准差 | 单机TDP | 单卡平均功耗 | 单卡最大功耗 | 单卡功耗标准差 | 单卡TDP |
| ---- | ------- | ------- | ------- | ----- | ------------ | ------------ | ------------- | ----- |
| nativetorch监控结果 | 2074.8W | 2090.0W | 30.4W   | /     | 163.72W       | 164.0W      | 2.89W        | 350W  |
| flaggems监控结果 | 2090.0W | 2109.0W | 38.0W   | /     | 168.97W       | 169.0W      | 0.16W        | 350W  |

## 其他重要监控结果

| 监控项  | 系统平均CPU占用 | 系统平均内存占用 | 单卡平均温度 | 单卡最大显存占用 |
| ---- | --------- | -------- | ------------ | -------------- |
| nativetorch监控结果 | 39.076%    | 2.579%   | 47.91°C       | 25.739%        |
| flaggems监控结果 | 39.225%    | 2.588%   | 48.03°C       | 25.739%        |