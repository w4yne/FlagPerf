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
FlagGems:>联系邮箱: contact-us@iluvatar.com获取版本(FlagGems最新适配版本)

# 评测结果

## 核心评测结果

| 评测项  | 平均相对误差(with FP64-CPU) | TFLOPS(cpu wall clock) | TFLOPS(kernel clock) | FU(FLOPS Utilization)-cputime | FU-kerneltime |
| ---- | -------------- | -------------- | ------------ | ------ | ----- |
| flaggems | 2.06E-08    | 0.07TFLOPS       | 0.07TFLOPS        | 0.29% | 0.29% |
| nativetorch | 2.06E-08    | 0.07TFLOPS      | 0.07TFLOPS      | 0.3%      | 0.3%    |

## 其他评测结果

| 评测项  | 相对误差(with FP64-CPU)标准差 | cputime | kerneltime | cputime吞吐 | kerneltime吞吐 | 无预热时延 | 预热后时延 |
| ---- | -------------- | -------------- | ------------ | ------------ | -------------- | -------------- | ------------ |
| flaggems | 6.51E-10    | 7411.07us       | 7419.15us        | 134.93op/s | 134.79op/s | 401710.11us | 7934.4us |
| nativetorch | 6.51E-10    | 7366.03us       | 7370.8us        | 135.76op/s | 135.67op/s | 7716.18us | 7658.1us |

## 能耗监控结果

| 监控项  | 系统平均功耗  | 系统最大功耗  | 系统功耗标准差 | 单机TDP | 单卡平均功耗 | 单卡最大功耗 | 单卡功耗标准差 | 单卡TDP |
| ---- | ------- | ------- | ------- | ----- | ------------ | ------------ | ------------- | ----- |
| nativetorch监控结果 | 2080.5W | 2109.0W | 49.36W   | /     | 186.38W       | 187.0W      | 4.65W        | 350W  |
| flaggems监控结果 | 2080.5W | 2109.0W | 49.36W   | /     | 192.9W       | 193.0W      | 0.29W        | 350W  |

## 其他重要监控结果

| 监控项  | 系统平均CPU占用 | 系统平均内存占用 | 单卡平均温度 | 单卡最大显存占用 |
| ---- | --------- | -------- | ------------ | -------------- |
| nativetorch监控结果 | 44.02%    | 2.388%   | 51.99°C       | 30.432%        |
| flaggems监控结果 | 40.995%    | 2.391%   | 53.44°C       | 20.856%        |