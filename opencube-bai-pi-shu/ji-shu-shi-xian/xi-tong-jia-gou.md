# 系统架构

OpenCube的系统架构如下图所示

OpenCube的系统架构主要由以下几个部分组成：

* OpenCube魔方实体：是 OpenCube的核心产品，由 54 个可单独控制发光颜色的 LED 灯、一个微型的 CPU 和一个蓝牙模块组成，可以与DApp进行无线连接和数据传输。
* DApp：是 OpenCube的辅助产品，是一个运行在手机或其他设备上的应用程序，可以与OpenCube魔方实体进行连接和交互，提供发光控制、游戏竞技、社区互动、经济激励等功能。
* 区块链网络：是 OpenCube的基础设施，是一个基于以太坊的去中心化网络，用于存储和验证 OpenCube的代币（OCT）和 MST 的发行和交易记录，以及 OpenCube的社区治理和决策结果。
* 中心化服务器：是 OpenCube的辅助设施，是一个负责提供游戏逻辑、数据分析、用户管理等服务的中心化服务器，用于支持 OpenCube的游戏竞技和社区互动等功能。

#### 主要技术方案

* OpenCube DApp: 基于Unity开发,支持iOS和Android系统。
  * DApp与会OpenCube魔方实体的通信：使用了一种基于蓝牙协议的技术方案，通过蓝牙模块来实现无线连接和数据传输。DApp可以通过蓝牙协议发送指令给OpenCube魔方实体，也可以接收OpenCube魔方实体发送的数据。
  * DApp与区块链网络的通信：使用了一种基于 Web3.js 库的技术方案，通过 Web3.js 库来实现与以太坊网络的交互。DApp可以通过 Web3.js 库调用 OpenCube的智能合约，也可以监听 OpenCube的区块链事件。
  * DApp与中心化服务器的通信：使用了一种基于 RESTful API 的技术方案，通过 RESTful API 来实现与中心化服务器的交互。DApp可以通过 RESTful API 请求中心化服务器提供的服务，也可以接收中心化服务器推送的消息。
* OpenCube魔方硬件:基于STM32微控制器,内置蓝牙模块用于与App连接。
  * 发光控制：使用了一种基于 PWM（脉冲宽度调制）的技术方案，通过调节每个 LED 灯的开关时间来控制其发光颜色和亮度。每个 LED 灯都有一个独立的地址，可以通过DApp发送指令来设置其参数。CPU 可以根据指令来控制每个 LED 灯的 PWM 信号，并将其反馈给DApp。
  * 状态监测：使用了一种基于陀螺仪和加速度计的技术方案，通过检测魔方的角速度和加速度来监测其状态和动作。CPU 可以根据陀螺仪和加速度计的数据来计算出魔方的姿态和转动，并将其反馈给DApp。
* Blockchain: 代币和MTS采用XXX公链,钱包集成小狐狸钱包。
* MTS市场:使用OpenSea进行二次开发。
* 服务器:（Amazon AWS托管,使用Kubernetes进行部署和管理）。

