# MotoDrive L298N Solution

⭐ 双路直流电机驱动 L298N 方案 ⭐

[![pipeline status](https://gitlab.soraharu.com/XiaoXi/MotoDrive-L298N-Solution/badges/master/pipeline.svg)](https://gitlab.soraharu.com/XiaoXi/MotoDrive-L298N-Solution/-/commits/master) [![Latest Release](https://gitlab.soraharu.com/XiaoXi/MotoDrive-L298N-Solution/-/badges/release.svg)](https://gitlab.soraharu.com/XiaoXi/MotoDrive-L298N-Solution/-/releases) [![vercel](https://vercelbadge.soraharu.com/?app=interactivehtmlbom)](https://interactivehtmlbom.soraharu.com/)

🔗 [GitLab (Homepage)](https://gitlab.soraharu.com/XiaoXi/MotoDrive-L298N-Solution) | 🔗 [OSHWHub](https://oshwhub.com/yanranxiaoxi/MotoDrive-L298N-Solution) | 🔗 [GitHub](https://github.com/yanranxiaoxi/MotoDrive-L298N-Solution)

![实拍图](https://downloadserver.soraharu.com:7000/MotoDrive%20L298N%20Solution/Image/Product_quality_8.jpg)

## 🤔 这是什么

这是一个使用 L298N 双 H 桥驱动芯片制作的双路直流电机驱动模块，使用 [立创 EDA](https://lceda.cn/) 进行开发。

本设计采用 L298N 作为驱动芯片，板载 7805 线性稳压器，可以为其他传感器、主控提供不大于 1.5A 的 5V 直流供电，免去独立供电的烦恼。

## 🍭 使用说明

`H1`、`H2` 为通道片选跳线，如需使用该侧通道，需使用跳线帽短接该跳线。

`H9`、`H10` 靠近板边一侧为 L298N 通道 PWM 调速引脚引出，靠近芯片一侧的排针直接接通 7805 输出的 5V 电源，这意味着，如果你使用跳线帽短接 `H9` 或 `H10`，其所对应的通道的 PWM 引脚占空比将为 100%，即满功率/全速输出。一般情况下，请不要使用跳线帽，转而使用主控芯片的 PWM 信号来驱动调速。

`H3` 为 7805 线性稳压器的开关跳线，如短接，即为启用 7805 芯片从 VIN 网络取点并输出电流至 5V 网络。如果不使用 7805，你需要为本模块的 5V 网络提供外部的 5V 电源，以驱动 L298N 的低压逻辑区。请注意：如果 VIN 网络的电压高于 35V，请断开本跳线并转而使用外部 5V 供电，因为一般的 7805 芯片的最高耐压能力为 35V。

本 PCB 设计已通过完整功能性测试，且已添加 [嘉立创](https://www.jlc.com/) SMT 定位孔，可直接进行 SMT 贴片生产。但请注意，本设计完整开源并遵循 [GNU General Public License v3.0](https://choosealicense.com/licenses/gpl-3.0/) 开源协议，开源作者不对作品的安全性、完整性作任何承诺，且不对因此产生的任何损失承担后果。

你可以使用本项目的 [焊接助手](https://interactivehtmlbom.soraharu.com/MotoDrive-L298N-Solution.html) 有效地提升手工焊接效率，本助手通过 [InteractiveHtmlBom](https://gitlab.soraharu.com/XiaoXi/InteractiveHtmlBom) 流水线自动化生成。

## 🏃 主要性能参数

- 电机驱动通道：双通道
- 最大输入电压：9.6V
- 单通道持续输出电流：1.35A
- 单通道最大峰值输出电流：2A
- 双通道持续输出电流：1A

## 🛠️ 生产电路板

本项目的 Gerber 文件可以从 [Releases](https://gitlab.soraharu.com/XiaoXi/MotoDrive-L298N-Solution/-/releases) 页面获取，并允许在开源许可范围内的商业目的使用。

*建议使用 [嘉立创](https://www.jlc.com/) 生产高品质电路板。

*It is recommended to use [JLCPCB](https://jlcpcb.com/) to produce high-quality circuit boards.

## ⚙️ 部署至 EasyEDA

1. 克隆本项目 [源代码](https://gitlab.soraharu.com/XiaoXi/MotoDrive-L298N-Solution/-/archive/master/MotoDrive-L298N-Solution-master.zip) 到本地
2. 在立创 EDA 标准版编辑器中选择 `文件` -> `打开` -> `立创EDA...`
3. 选择本项目源代码中的 `/EasyEDA/*.json` 文件并分别导入

## 📜 开源许可

基于 [GNU General Public License v3.0](https://choosealicense.com/licenses/gpl-3.0/) 许可进行开源。

本设计已在 [中国版权保护中心](https://www.ccopyright.com.cn/) 登记注册。
