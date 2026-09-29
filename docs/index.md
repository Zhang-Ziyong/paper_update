# 计算机视觉领域最新论文 (2026.09.29)

> 每日自动更新计算机视觉领域的最新arXiv论文

> 使用说明: [点击查看](./docs/README.md#usage)

<details>
<summary>分类目录</summary>
<ol>
<li><a href='#slam'>SLAM</a></li>
<li><a href='#sfm'>SFM</a></li>
<li><a href='#image-matching'>Image Matching</a></li>
<li><a href='#sensor-calibration'>Sensor Calibration</a></li>
<li><a href='#robot-vlm'>Robot VLM</a></li>
<li><a href='#robot-visual-semantic-recognition'>Robot Visual Semantic Recognition</a></li>
<li><a href='#robot-vpr'>Robot VPR</a></li>
<li><a href='#archive'>归档</a></li>
</ol>
</details>

<h2 id='slam'>SLAM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-28</td><td>InfiniHand: Streaming World-Space Hand Motion Estimation from Egocentric Video<br><a href='http://arxiv.org/pdf/2609.35743'>论文</a></td><td>InfiniHand提出一种端到端流式前馈框架，可从无标定第一视角视频中联合估计MANO参数、相机轨迹和手部位置，避免传统手部姿态估计与SLAM级联造成的误差累积和高开销。  
◆ 将持久时空记忆与手中心视觉特征融合到统一架构，显式耦合相机运动与局部手部几何。  
◆ 采用两阶段渐进训练，先学习鲁棒相机空间手部先验，再扩展到流式世界空间重建。  
◆ 聚合约5000小时多数据集第一视角数据，构建大规模预训练语料以支撑训练。  
实验表明其在域内基准上优于现有方法，ARCTIC PA-p较ViDiHand降低21.4%，并显著缓解世界空间漂移。  
它还能泛化到野外视频，以11.19 FPS运行，吞吐量超过HaWoR两倍以上。</td></tr>
<tr><td>2026-09-28</td><td>ForVis: An In-Field Dataset and Benchmark for VIO Using Under-Canopy UAV Flights in Forests<br><a href='http://arxiv.org/pdf/2609.35482'>论文</a></td><td>ForVis提出了面向森林冠下无人机飞行的实地VI-SLAM数据集与基准，弥补真实森林环境评估不足。数据集涵盖开放草甸、冠上和冠下场景，共12次飞行，563.8秒、1096.8米轨迹，并同步采集RealSense D435i、OAK-D Pro Wide、惯性与飞控数据。  
◆ 构建覆盖多种森林飞行条件的实地多传感器同步数据集，突出冠下等挑战场景。  
◆ 提供统一基准并完成七个开源VI-SLAM系统共504次运行评测。  
◆ 揭示传感器选择对轨迹误差影响大于算法间差异，所有方法在OAK-D Pro上中位误差均低于D435i。  
该基准旨在支持森林飞行中VI-SLAM的速度、精度与鲁棒性评估。</td></tr>
<tr><td>2026-09-28</td><td>MarsLab: A Martian Rover Simulator for Planetary Rover Autonomous Navigation<br><a href='http://arxiv.org/pdf/2609.34702'>论文</a> | <a href='https://kimhoyun-robotair.github.io/MarsLab/'>代码</a></td><td>MarsLab 是面向火星车自主导航的开源、ROS2 原生模拟器，旨在弥补现有火星仿真资源在范围与接口上的差异。
◆ 它融合 HiRISE 衍生地形与程序化地形，并支持岩石、陨石坑、太阳光照和大气尘埃等参数化配置。
◆ 它在 NVIDIA Isaac Sim 中运行 Perseverance 级火星车，并通过标准 ROS2 话题发布 RGB、深度、RGB-D 点云、LiDAR、IMU、轮式里程计和 GT 位姿。
◆ 它提供跨传感模态、尘埃水平、场景几何和路线长度的 SLAM 基准，以及重复火星基地穿越下光照与尘埃变化的 VPR 基准。
◆ 借助可控场景变化和共享 GT 轨迹，可在同一模拟器中比较轨迹级估计与图像级地点识别。
MarsLab 的核心价值是为火星车自主导航算法提供可复现、可扩展且贴近火星环境的仿真评测平台。</td></tr>
<tr><td>2026-09-28</td><td>RRG-SLAM: Real-time Reflection-aware Gaussian SLAM for Indoor Scenes<br><a href='http://arxiv.org/pdf/2609.34527'>论文</a></td><td>本文提出首个面向室内场景的实时反射感知高斯SLAM系统。
◆ 设计反射感知TSDF-高斯混合表示，将漫反射场景外观与反射分量显式分离。
◆ 提出三阶段渲染流程，通过TSDF射线投射、基础高斯深度剔除渲染和按平面ID约束的反射高斯光栅化，合成最终图像。
◆ 在线重建中采用反射感知跟踪抑制反射主导区域干扰，并融合几何、语义、时间线索识别反射平面，向增强TSDF写入反射属性。
◆ 对基础高斯和反射高斯进行在线初始化、优化与剪枝，兼顾重建质量和效率。
实验表明，该方法在多种数据集上提升反射室内场景的重建质量、跟踪鲁棒性和新视角渲染，并保持实时性能。</td></tr>
<tr><td>2026-09-28</td><td>MonoEgo: Monocular Metric Egocentric Demonstration Capture with Passive Wrist Constellations and Sparse Workstation Anchors<br><a href='http://arxiv.org/pdf/2609.34512'>论文</a></td><td>MonoEgo提出一种仅用单目离线重建的自我中心度量演示采集系统，用被动腕部标记星座和稀疏工作站锚点替代主动腕部跟踪设备，并由一台90 FPS全局快门相机在统一图像时钟下观测场景与标记。
◆ 设计MonoTag SLAM，将标记角点与ORB几何结合，并用视觉证据拒绝易混淆的平面标记位姿，提高被动标记重建可靠性。
◆ 构建Metric Atlas，支持区间尺度重锚定、经验证的地图合并，以及借助最终地图对早期帧进行回溯定位。
◆ 输出相机与腕部星座结果时保留有效性和地图溯源，对不支持的快速或遮挡运动明确标记为缺失而非强行插值。
◆ 实验证明可超出连续锚点可见范围进行度量跟踪、重连受支持地图组件并恢复部分缺失相机位姿，同时通过与多传感器参考和静态星座测试比较刻画精度与残余不确定性。
这些表明被动固定装置和离线重建能降低采集端硬件与同步要求，但动态精度、实际部署及下游策略收益仍需进一步研究。</td></tr>
<tr><td>2026-09-28</td><td>NavHarness: Towards Lifelong Embodied Navigation<br><a href='http://arxiv.org/pdf/2609.34276'>论文</a></td><td>NavHarness提出一种免训练具身导航框架，将记忆处理作为导航循环的一部分，面向终身导航。◆把地图、任务记录和房屋知识引入多轮智能体会话，并与新观测交叉核验，记录修正以指导行动。◆跨新对话保留导航经验，通过结果验证和运行结束摘要支持新任务与失败恢复中的经验复用。◆在GOAT-Bench上较仅上下文独立会话分别提升s-SR 18.6和22.6个百分点，并用SLAM位姿在GOAT-Bench达到83.7 s-SR、36.9 e-SR，在IR2R-CE达到85.9 s-SR。◆发现结构化恢复交接优于等长摘要，长期部署中的经验整合也能超越仅保留地图与任务记录。这些结果表明，终身导航的关键在于连续推理会话如何基于先前经验，而非仅提升单任务能力。</td></tr>
<tr><td>2026-09-26</td><td>World SLAM Model: Joint World Modeling for SLAM and Navigation<br><a href='http://arxiv.org/pdf/2609.32626'>论文</a></td><td>本文提出World SLAM Model（WSM），一个将SLAM范式直接融入下游导航的统一框架，而非仅把SLAM当作提供位姿、地图或token的上游模块。
◆ 将SLAM的增量状态更新、持久记忆与后端误差细化机制引入导航，使智能体在交互中维持一致的世界状态。
◆ 给定当前观测和导航目标，联合预测未来视觉状态并估计相机运动与密集几何，把视觉预测锚定在不断演化的空间世界状态上。
◆ 该空间状态随新观测持续更新，并直接支撑动作生成与闭环导航。
◆ 采用端到端联合导航-SLAM目标训练，让导航直接受益于SLAM式状态维护和细化，同时保持准确几何估计。
实验表明该方法在提升导航性能的同时保持较强SLAM精度，显示SLAM可作为长时程世界建模与具身交互的内在机制。</td></tr>
<tr><td>2026-09-25</td><td>CognitiveReality: Robot-Agnostic Semantic Gaussian Mapping with an LLM Agent for Immersive Collaborative VR Teleoperation<br><a href='http://arxiv.org/pdf/2609.31418'>论文</a></td><td>CognitiveReality将机器人RGB-D流构建为实时、开放词汇语义索引的高斯-TSDF地图，并让VR遥操作员与工具调用型LLM代理共享同一场景表示。
◆ 提出机器人无关映射框架，同一mapper二进制仅靠配置即可接入机器人SLAM、关节运动学、动捕或内联视觉追踪等位姿源。
◆ 用影子追踪器和关键帧锚定PnP桥接定位中断，并以2Hz维护开放词汇实例身份及逐物体观测质量。
◆ 将语音和控制器射线通过经验证的类型化工具与操作员确认动作，接地到持久场景对象上。
◆ 在受控代理评测中，本地Qwen3-VL-8B路由器达到81.24%工具精确匹配，合并感知回放正确重定向101个被吸收对象ID。
◆ 在机器人数据上超过高斯与SDF基线2至8dB，5至40秒SLAM中断内姿态误差保持1至8cm；两只四足机器人实机完成26/30导航和20/20重观测请求，物体质量提升2至5dB。</td></tr>
<tr><td>2026-09-25</td><td>Augmented Reality Interfaces for Human-Robot Collaboration: Development of a ROS 2-Based Sensor Streaming Framework and Validation via SLAM Algorithms<br><a href='http://arxiv.org/pdf/2609.31396'>论文</a></td><td>本文面向工业4.0下HRC对双向、直观、高效通信的需求，开发并验证了连接Magic Leap 2 AR头显与ROS 2生态的传感器流传输框架，核心贡献是打通AR设备与机器人系统的实时数据通道。
◆ 构建Magic Leap 2与ROS 2之间的实时传感器流传输架构，实现AR头显多源数据向机器人生态的接入。
◆ 基于Unity和ROSTCP-Connector开发头显端应用，将姿态跟踪、相机和环境传感器数据发布到ROS 2专用话题。
◆ 采用SLAM算法对生成数据流的精度、延迟和鲁棒性进行验证，证明该框架具备稳定传输能力。
◆ 为HRC中的安全实时交互、共享空间感知以及复杂场景下机器人控制与监督提供新基础与视角。</td></tr>
<tr><td>2026-09-25</td><td>DAPEVO: Deep Adaptive Patch Frame-Event Visual Odometry<br><a href='http://arxiv.org/pdf/2609.30947'>论文</a></td><td>DAPEVO是一种学习式帧-事件视觉里程计，核心是在共享图像块位置独立估计图像与事件对应，并在运动细化前融合两种模态的相关证据。
◆ 它为每个跟踪图像块维护图像和事件描述子，并用可学习标量门逐块-帧边融合模态相关嵌入，再经共享循环细化与光束法平差更新。
◆ 它支持纯事件观测，在RGB帧稀疏或缺失时仍能持续跟踪。
◆ 它采用模态感知关键帧剔除，以保留稀缺帧约束。
在UZH-FPV仅保留六分之一RGB帧时，其绝对轨迹误差从1.00米仅升至1.36米，而DPVO和RAMP-VO分别增大约3.7倍和3.1倍。
在TartanEvent 3Hz RGB输入下其ATE仍低于1米，DPVO和RAMP-VO超过9米；退化RGB下为0.60米，优于两者超过4米及纯事件DEVO的0.87米。</td></tr>
<tr><td>2026-09-25</td><td>FMCW-LIO: A Doppler LiDAR-Inertial Odometry<br><a href='http://arxiv.org/pdf/2609.29374'>论文</a></td><td>传统LIO/SLAM主要依赖几何特征，而FMCW Doppler LiDAR能同时提供高分辨率点距离和瞬时点多普勒速度，为利用运动测量提供了新契机。  
本文提出FMCW-LIO，一种利用FMCW Doppler LiDAR内禀多普勒测量的鲁棒LIO。  
◆ 设计运动补偿方法，以正确利用多普勒速度并避免运动影响。  
◆ 引入多普勒辅助观测模型，在流形上进行状态估计。  
◆ 利用多普勒准则有效剔除动态点，从而获得更一致的几何观测。  
在结构退化等多样场景中实现准确状态估计与静态建图，实验表明其精度和鲁棒性优于其他算法。</td></tr>
<tr><td>2026-09-24</td><td>VkVIO: Cross-platform GPU Acceleration for Visual-Inertial Odometry with Vulkan<br><a href='http://arxiv.org/pdf/2609.30459'>论文</a></td><td>VkVIO 提出了首个基于 Vulkan 的跨平台 GPU 加速视觉惯性里程计系统，面向机器人、XR 等资源受限平台降低延迟与功耗。  
◆ 采用厂商无关的 Vulkan API 替代 CUDA，使 GPU 加速 VIO 可部署在嵌入式、移动端、XR 头显等多类硬件，而不再绑定单一 GPU 厂商。  
◆ 在保持实时所需的因果估计前提下实现 state-of-the-art 精度，兼顾实时性与准确性。  
◆ 在工作站、笔记本和极低成本单板机等多样设备上部署，并在相同硬件上优于基于 CUDA 的系统。  
该系统证明跨平台 GPU 加速可在低成本、低功耗设备上实现低延迟 VIO，为机器人和 XR 感知提供更广泛部署可能。</td></tr>
<tr><td>2026-09-23</td><td>PTC-Bias: Phoneme-Level Temporal Competition for Bias Retrieval and Post-Decoding Correction in Speech LLMs<br><a href='http://arxiv.org/pdf/2609.28727'>论文</a></td><td>本文提出PTC-Bias，一个基于音素级时间竞争的两阶段SpeechLLM上下文偏置框架，用于高效利用大偏置词表并提升罕见词识别。
◆ 预填充阶段执行帧同步音素解码，并让候选发音进行时间竞争，生成紧凑偏置词短名单和对应语音区间。
◆ 解码后仅在检索区间内，对候选与不匹配转写片段做局部二次竞争，选择性校正同音近音和分词错误，同时保留正确转写。
◆ 两阶段共享同一套音素后验，且不增加额外SpeechLLM前向计算，兼顾效率与准确性。
在LibriSpeech上，该方法对两个SpeechLLM及最多2000词偏置表均取得一致增益。
以Prompt-SLAM-ASR-7B和2000词为例，其B-WER相对CTC-Filter在test-clean/test-other降低23.4%/23.9%，U-WER几乎不变。</td></tr>
<tr><td>2026-09-23</td><td>DAVIO: Dense Monocular-Inertial SLAM with Feed-Forward Initialization and Pose-Conditioned Mapping<br><a href='http://arxiv.org/pdf/2609.27702'>论文</a></td><td>本文提出DAVIO，一种仅用相机和IMU即可实时运行的稠密米制SLAM系统，解决传统VIO依赖视差且只能稀疏建图、前馈深度模型又缺乏米制尺度和重力的问题。
◆ 采用单一多视图深度模型Depth Anything 3同时完成启动初始化与姿态条件化建图。
◆ 启动时用五图像窗口与预积分IMU构成无特征线性系统，经鲁棒条件检查求解后，通过缓冲回放引导VIO滤波器，实现无需等待视差的快速米制启动。
◆ 跟踪时以滤波器米制位姿条件化深度模型，残差尺度仅沿视线校正，保留米制相机基线。
◆ 构建保重力子图图与漂移门控重访，持续精炼稠密地图。
在EuRoC上，DAVIO启动更早、定位误差更低，且在相同位姿下建图优于SOTA前馈建图器；在ORI上达到或优于SOTA，GT位姿换成真实里程计时退化更小，并开源了实时稠密米制SLAM代码。</td></tr>
<tr><td>2026-09-23</td><td>Know-Your-Scene (KYS)-SLAM: Hierarchical Semantic-Motion Priors for Feature Matching in Stereo Visual SLAM<br><a href='http://arxiv.org/pdf/2609.27509'>论文</a></td><td>本文提出KYS-SLAM，作为ORB-SLAM3的模块化扩展，把语义、全景与运动上下文从二元特征剔除重构为连续对应代价，在特征匹配阶段调制而非丢弃特征。
◆ 将上下文可信度表达为分级匹配代价，替代传统语义/动态SLAM的特征拒绝，保留BA依赖的几何支撑。
◆ 融合语义类别、实例身份与零样本运动分数的分层兼容性先验，约束结构合理性并降低独立运动物体特征权重。
◆ 设计训练无关运动评分模块，用深度感知自运动模型拟合背景光流，并以自校准、覆盖感知阈值分类全景段，仅惩罚有充分运动证据者。
◆ 在固定配置、无需逐序列调参下，21个双目序列上KITTI户外ATE RMSE降17.4%，EuRoC室内降27.7%，动态KITTI Tracking降6.6%，Virtual KITTI 2降17.8%至31.2%，无回归。</td></tr>
</tbody>
</table>
</div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-28</td><td>Remote Sensing Sparse-View 3D Gaussian Splatting via Depth Image-Based Rendering<br><a href='http://arxiv.org/pdf/2609.35612'>论文</a> | <a href='https://github.com/kanehub/DIBR-GS'>代码</a></td><td>本文针对遥感稀疏视角新视角合成中几何约束不足、跨视角监督有限及深度模糊导致的过拟合问题，提出DIBR-GS框架。核心思想是利用深度图像渲染生成伪视角，为神经高斯泼溅提供跨视角一致性监督。
◆ 通过对齐单目深度先验与稀疏SfM重建，构建可靠几何初始化，并将跨视角外观先验融入神经高斯表示以增强稀疏观测下的外观建模。
◆ 设计渐进式DIBR伪视角监督策略，为弱观测区域补充几何与外观约束，促进更完整重建。
◆ 提出高度约束锚点生长策略，抑制不合理的高斯扩展。
在仅3个输入视角下，该方法优于现有方法，PSNR提升6.83 dB，SSIM相对提升14%，LPIPS相对提升60%，并保持有竞争力的计算效率。</td></tr>
<tr><td>2026-09-26</td><td>QuacamFM: Quaternion-Constrained Flow Matching for Camera Pose Estimation<br><a href='http://arxiv.org/pdf/2609.32455'>论文</a></td><td>论文针对稀疏多视角相机位姿估计中几何约束不足、旋转不确定性难以建模的问题，提出QuacamFM。其核心思想是在生成式相机位姿估计中显式保持单位四元数约束，而不是把旋转当作无约束4D向量处理。
◆ 提出四元数约束流匹配框架，使整个生成轨迹始终位于单位四元数流形上。
◆ 设计基于球面线性插值的四元数流最优传输，获得更平滑、更优的生成轨迹。
在CO3Dv2上，QuacamFM的相机位姿精度超过扩散模型和经典SfM方法。消融实验表明，它优于把标准流匹配直接用于4D四元数向量的做法。该方法还展现出跨数据集和野外样本的良好泛化能力。</td></tr>
<tr><td>2026-09-25</td><td>Reliability-Regulated Trajectory Optimization for Progressive COLMAP-Free 3D Gaussian Splatting<br><a href='http://arxiv.org/pdf/2609.30865'>论文</a> | <a href='https://github.com/Zijian1026/RRTO-CF3DGS'>代码</a></td><td>本文针对无COLMAP渐进式3DGS中相机位姿跟踪易误差累积、早期偏差会污染后续初始化并永久固化的问题，提出可靠性调节的轨迹优化框架。
◆ 构建自监督双向循环一致性机制，统一调节渐进相机轨迹估计，无需外部神经先验或离线预处理。
◆ 在前向运动传播中，利用在线可靠性信号自适应门控刚性运动一阶运动学热启动，为后续成对配准提供方向先验并拦截不可信转换。
◆ 在回溯轨迹校正中，用同一可靠性信号动态加权滑动窗口内相邻位姿的相对一致性约束，回溯整合并抑制渐进漂移。
该框架通过统一可靠性调节器同时管理前瞻初始化和回溯校正，实现自包含的鲁棒轨迹优化。
在Tanks and Temples和CO3D-V2上，方法显著提升相机轨迹精度与新视图渲染质量，优于现有无位姿基线。</td></tr>
<tr><td>2026-09-23</td><td>AstraLOD3: Zero-shot multimodal agentic reconstruction of LOD3 building models<br><a href='http://arxiv.org/pdf/2609.28061'>论文</a></td><td>本文提出AstraLOD3，探索通用多模态基础模型Astra在有限自主智能体框架下零样本重建LOD3建筑模型。
◆ 将LOD3重建从固定专用流程重构为受约束的智能体过程，由Astra动态选择并执行Python与Blender程序。
◆ 融合多视图图像、标定相机、过滤稀疏SfM点云和自然语言重建规范，实现多模态证据驱动的零样本重建。
◆ 在35次运行含24栋基准建筑中取得平均FRDS 0.9647，几何一致性可与以往专用方法相媲美。
◆ 通过受控消融揭示重建引导、证据模态、模型配置及运行随机性对结果的影响。
未来将研究自适应细化、用户引导修正、任务特化及损伤感知重建。</td></tr>
<tr><td>2026-09-21</td><td>SPARSER: Sparse Variable Projection by Exploiting Separable Structure in Robotic Perception<br><a href='http://arxiv.org/pdf/2609.24708'>论文</a></td><td>论文提出SPARSER，一个面向机器人感知中规范对称非线性最小二乘问题的变量投影框架，联合利用可分离性与稀疏性，突破标准VarPro在全局平移旋转不变性下的限制。
它通过解析消去线性变量（如视觉路标）实现降维，同时保留位姿等非线性变量，并可接入迭代NLS求解器。
◆ 构造无矩阵Schur补算子，高效评估降维后的代价、梯度和Hessian向量乘积，避免显式构造大规模矩阵。
◆ 刻画适用问题类别，识别可进一步解析简化的常见情形，并证明IRLS鲁棒代价仍能保留大部分可利用结构。
◆ 在SLAM、SNL、SfM合成与真实基准上，CPU和GPU平均提速5至7倍，个别数据集超过40倍；在多机器人SLAM抗离群值场景中，鲁棒变体比先进GNC求解器快2至16倍。
◆ 开源C++代码与全部数据集，推动变量投影在机器人感知中的实用化。</td></tr>
<tr><td>2026-09-17</td><td>RawSLAM: Online HDR Gaussian SLAM from Linear Radiance<br><a href='http://arxiv.org/pdf/2609.20589'>论文</a></td><td>本文提出RawSLAM，首个直接在单曝光16位线性HDR图像上在线跟踪与建图的高斯SLAM框架，无需离线SfM且可应对大帧间运动和极端光照。
◆ 设计架构无关的HDR高斯泼溅模块，采用无MLP的对数高斯颜色参数化，并原生输出线性场景辐射。
◆ 提出Reinhard范围压缩光度目标与结构引导空间梯度加权，增强极端光照下的跟踪与建图鲁棒性。
◆ 该HDR高斯模块可无缝迁移至SplaTAM、Gaussian SLAM和DROID-W，消除它们在挑战光照序列中的跟踪失败。
方法在轨迹与重建精度上优于直接HDR改装的MonoGS，且同一公式在标准8位输入下将MonoGS基线误差约减半。
为支撑研究，发布RawSLAM数据集，包含10个真实室内序列的16位RAW图像、对齐深度、IMU测量和OptiTrack外部位姿。</td></tr>
<tr><td>2026-09-16</td><td>Cross-Lingual Parkinson&#x27;s Disease Severity Assessment Using Pre-trained Speech Embeddings: A Multi-Class Evaluation<br><a href='http://arxiv.org/pdf/2609.20875'>论文</a></td><td>本文针对语音基础模型在帕金森病严重程度跨语言多类评估中泛化性不足、标注数据有限且缺乏可解释性的问题，选取四个开源语音基础模型，在三个数据集上开展零样本与k-shot跨语言多类严重程度评估，并分析数据属性、预处理和适应策略的影响。
◆ 系统评估四类开源预训练语音嵌入在跨语言帕金森病严重程度多类分类中的迁移能力，填补该场景下多类跨语言评估的空白。
◆ 构建覆盖三个数据集、零样本与k-shot设置的跨语言多类评估框架，并揭示性能对数据集属性、预处理和适应策略高度敏感。
◆ 发现预训练语音嵌入可实现有意义的跨语言迁移，同时将误分类归因于说话人差异和非典型语音模式，强调更鲁棒的特征建模与可解释性对临床可靠洞见的重要性。
总体而言，该研究证明跨语言PD严重程度评估具有可行性，但稳健临床应用仍需进一步改进特征提取、模型适应与可解释方法。</td></tr>
<tr><td>2026-09-16</td><td>RAUL: Reference-Assisted Ureteroscopy Localization for Skill Assessment<br><a href='http://arxiv.org/pdf/2609.19236'>论文</a></td><td>本文提出RAUL参考辅助输尿管镜定位框架，仅用内窥镜视频在体模中重建输尿管镜轨迹，并据此评估导航技能。  
◆ 利用慢速高质量参考探索视频生成参考重建，再将后续探索视频定位到参考，实现无需外部跟踪的轨迹恢复。  
◆ 在9个体模上取得平均平移RMSE 0.5±0.1 mm，帧级定位覆盖率从标准SfM的50.5±14.9%提升至86.1±7.2%。  
◆ 从重建轨迹计算导航指标，可显著区分高经验与低经验住院医师的输尿管镜导航表现。  
◆ 首次实现仅用视频、无需外部跟踪传感器的输尿管镜轨迹恢复与技能评估，支持可扩展的自动化评估。</td></tr>
<tr><td>2026-09-14</td><td>CAL-MOS: Bridging Layers with Adapters for Robust MOS Prediction Across Speech Foundation Models<br><a href='http://arxiv.org/pdf/2609.14956'>论文</a></td><td>本文系统评测十种语音基础模型在四个MOS数据集上的层深选择与多层融合问题，覆盖全量微调、冻结编码器最后一层探测和朴素跨层加权聚合三种策略。实验发现最佳层强依赖骨干与数据集，朴素加权融合跨设置不稳定。为此作者提出CAL-MOS，在池化前用逐层适配器校准各层表征，以增强多层融合鲁棒性。
◆ 首次跨十种SFM与四个MOS数据集系统揭示MOS预测最佳层的不确定性及朴素融合的不稳定性。
◆ 提出逐层适配器校准聚合，将层间信息先校准再池化，提升跨骨干和跨数据集的融合可靠性。
◆ 在保持骨干冻结的同时缩小与全量微调的差距，为高效鲁棒MOS预测提供新方案。</td></tr>
<tr><td>2026-09-14</td><td>HiSfM: Disambiguating Structure-from-Motion via Scaffold-Anchored Hierarchical Reconstruction<br><a href='http://arxiv.org/pdf/2609.04718'>论文</a> | <a href='https://github.com/3dv-casia/HiSfM'>代码</a></td><td>HiSfM提出了一种面向视觉模糊场景的分层粗到细SfM框架，通过构建稳定的脚手架锚点，在显著提升鲁棒性的同时大幅降低计算开销。  
◆ 利用几何启发式规则生成强局部社区，有效聚合冗余图像并减少无效约束。  
◆ 使用边不相交生成树（EDST）连接社区，形成紧凑且强壮的骨架，并通过双视图消歧器验证骨架边，以排除歧义匹配。  
◆ 在验证后的骨架上重建稳定脚手架作为场景锚点，再高效注册剩余图像并完成三角化，兼顾全局一致性与细粒度补全。  
实验表明，该方法在歧义聚焦基准和通用数据集上能避免歧义引发的重建失败，相比已有方法显著缩短运行时间，同时比激进稀疏化方法获得更高的重建完整性。</td></tr>
<tr><td>2026-09-12</td><td>SkyAnchor: Updating Metric-scale Aerial 3D Gaussian Scenes from Unposed Ground-View Sequences<br><a href='http://arxiv.org/pdf/2609.13903'>论文</a></td><td>本文研究如何用新采集、无位姿且未知全局尺度的地面序列更新已有航空3D高斯场景，核心思路是把已有航空SfM与3DGS当作固定支架，而非从头联合重建航空和地面影像。
◆提出基于几何验证航空支撑的短帧组定位，生成稀疏锚点位姿，缓解单图跨视角定位脆弱问题。
◆通过锚点约束子图并固定前后锚点进行增量配准与光束法平差，恢复完整地面轨迹，抑制长轨迹漂移。
◆在保持航空视角的前提下插入过滤后的地面高斯，并进行轻量联合优化，实现街景外观更新且不破坏原航空渲染。
在七个真实航空—地面场景上，方法获得准确的米制地面轨迹，并在航空与地面视角均取得强渲染质量。</td></tr>
<tr><td>2026-09-11</td><td>NOVA-GS: Noise-Aware View-Consistent Gaussian Splatting for Low-Light Novel View Synthesis<br><a href='http://arxiv.org/pdf/2609.12682'>论文</a> | <a href='https://shaurya2524.github.io/nova-gs/'>代码</a></td><td>本文提出NOVA-GS，一种面向低光新视角合成的噪声感知统一3D高斯泼溅框架，将增强、去噪与几何优化整合于单流程，并利用VGGT前馈估计直接从退化输入获得稳健相机位姿与几何，无需SfM。
◆ 结构感知增强模块进行曝光校正，提升低光图像可见性并保持结构信息。
◆ 自监督盲点掩码去噪模块提供伪监督，在无干净标签下抑制传感器噪声。
◆ 一致性驱动高斯泼溅优化强制跨视角几何相干，稳定重建与新视角合成。
◆ 噪声引导球谐正则抑制噪声区域中视角相关伪影，改善光照与颜色一致性。
实验表明该方法在多种真实低光数据集上提升几何保真度、颜色一致性和鲁棒性，且无需配对监督或良好光照参考。</td></tr>
<tr><td>2026-09-11</td><td>Visual-SLAM for the detection of hidden tomatoes in greenhouses by Hierarchical Localization and GLOMAP for robotized harvesting<br><a href='http://arxiv.org/pdf/2609.11766'>论文</a></td><td>本文提出一种用于温室番茄机器人采摘的低成本单目Visual-SLAM系统，并在Agroconnect实验温室真实番茄串上验证。  
◆ 用单目相机替代LiDAR和立体相机，显著降低温室作物监测与建图成本。  
◆ 将Hierarchical Localization与基于Structure-From-Motion的GLOMAP结合，实现从图像采集到三维作物地图的完整流程。  
◆ 采用粗到精的层次定位策略，先全局检索生成位置假设，再在候选区域融合局部特征。  
◆ 能正确识别被遮挡、经典视觉难以触及的番茄簇，并重建其三维模型。  
重建结果通过人工真值测量果实尺寸、质心位置和朝向，确认了几何精度，为后续生长分析与农业管理优化奠定基础。</td></tr>
<tr><td>2026-09-08</td><td>Learning Global Camera Poses from Noisy View-Graphs for Structure from Motion<br><a href='http://arxiv.org/pdf/2609.09491'>论文</a></td><td>本文提出一种基于可学习视图图聚合的深度全局SfM框架，用于从含噪视图图中估计全局一致相机位姿。
◆ 采用置换等变、边条件图神经网络，以噪声相对位姿为输入直接输出全局相机外参。
◆ 训练无需真值监督，仅依赖相对位姿一致性目标，降低对标注数据的依赖。
◆ 网络输出后接三维点三角化和鲁棒光束法平差，形成完整全局SfM流程。
◆ 方法高效、可扩展至千张以上图像，并对视图图密度具有鲁棒性。
在MegaDepth、1DSfM、Strecha和BlendedMVS上，其旋转和平移精度优于以轨迹为中心的深度方法，能配准更多图像，并与先进经典流程竞争且速度更快。</td></tr>
<tr><td>2026-09-07</td><td>Multi-View Structure-from-Motion Enables Oriented Projective Shape Analysis in Three Dimensions<br><a href='http://arxiv.org/pdf/2609.13263'>论文</a></td><td>本文针对经典投影形状分析仅能由单立体像对重建、方向信息可能翻转的问题，利用多视图SfM捆绑调整仅确定到保向投影变换的性质，实现三维有向投影形状分析。
◆ 首次在三维中开展有向投影形状（OPS）分析，并计算外蕴总方差指数与进行统计推断。
◆ 使用Agisoft Metashape Professional 2.3.0对三立方体对象构建8个SfM重建，并通过复现原立体构造验证实现。
◆ 发现SfM数据高集中时OPS指数渐近为PS指数的一半，这是集中度导致的结构性结果而非对象属性。
◆ 对q=14个非框架地标的蓝图假设均未被拒绝，且SfM重建比立体重建约集中26倍，显著提升重建精度。
◆ 通过样本量、照片数量和框架排序分析，支持上述结论的稳健性。</td></tr>
</tbody>
</table>
</div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-25</td><td>Facial classification Using Hybrid Quantum Machine Learning<br><a href='http://arxiv.org/pdf/2609.31915'>论文</a></td><td>本文提出一种可在标准计算硬件上运行的混合量子-经典人脸识别流水线，以解决资源受限场景下混合量子方法研究不足的问题。
◆ 设计gamma校正、对比度增强与PCA预处理，并将特征编码进8量子比特变分量子分类器，再结合经典图像匹配完成识别。
◆ 在含5万张图像（CelebA人脸与CIFAR-10非人脸）的实验中，准确率和训练效率超过已报道的CPU训练FaceNet基线。
◆ 在GPU和量子硬件上评估，并在Mahindra大学与Lloyds Technology Centre合作部署出勤监控，CPU推理每人0.2至0.5秒且对戴眼镜鲁棒。
◆ 证明混合量子方法可在现有CPU硬件上用于人脸识别，具备实际部署可行性。</td></tr>
<tr><td>2026-09-15</td><td>Co-occurrence-Aware Quadratic Assignment for Local Feature Matching in Simultaneous Localization and Mapping<br><a href='http://arxiv.org/pdf/2609.17905'>论文</a></td><td>论文针对Visual SLAM中最近邻匹配在多个相似代价候选下难以选出正确关键点对的问题，提出一种考虑两个关键点对之间成对共现关系的局部特征匹配方法。  
◆ 创新点一：将关键点匹配建模为二次分配问题，利用关键点对之间的共现约束提升匹配判别能力。  
◆ 创新点二：针对该NP-hard组合优化问题，采用基于模拟分岔的Ising机进行求解，实现快速近似优化。  
◆ 创新点三：在HPatches数据集上将匹配精度较传统方法提升约8个百分点，并成功集成到ORB-SLAM3中。  
在KITTI中多个同形状物体重复排列的困难场景下，该方法使绝对位姿误差改善3.78倍、相对位姿误差改善2.85倍。</td></tr>
<tr><td>2026-09-08</td><td>RoMa-$Ω$: What Feed-Forward 3D Models Know About Image Matching<br><a href='http://arxiv.org/pdf/2609.09507'>论文</a></td><td>本文探究前馈3D重建模型对图像匹配的知识，并分析零样本patch特征匹配、3D点预测直接匹配和基于学习表示训练完整匹配器三种场景。
◆系统评估VGGT等前馈3D模型在图像匹配中的零样本、线性探测和端到端训练表现。
◆发现其零样本匹配较弱且深层更差，但学习表示对线性探测和完整匹配流程具有强迁移价值。
◆证明无需训练，其原始3D点预测在中等视角变化和模态差异下也能取得有竞争力的匹配结果。
◆提出RoMa-Ω，用VGGT-Ω替换RoMa v2的DINO骨干，在多个基准上超越现有匹配器，WxBS较RoMa v2提升8.1 mAA。</td></tr>
<tr><td>2026-09-06</td><td>Back to the Feature: Zero-Shot 6DoF Pose Estimation via Dense Local Features<br><a href='http://arxiv.org/pdf/2609.06726'>论文</a></td><td>B2TFPose是一种无需训练的零样本6DoF位姿估计方法，仅利用单个冻结的DINOv3视觉Transformer提取密集局部特征，即可跨越合成到真实的领域差异，无需任何任务微调。该方法重新审视经典局部特征匹配范式，并借助大规模自监督基础模型实现对新物体的位姿估计。在BOP基准的七个核心数据集上，B2TFPose无需精修即达到40.7平均AR，加入精修后达到56.4，超越现有无训练方法，并优于部分有监督方法，且推理速度具有竞争力。其核心贡献包含以下三点：
◆ 提出测地线非极大值抑制策略，用于选取视角多样化的模板集，支撑由粗到精的对应匹配。
◆ 提出渲染引导的重新对应机制，在估计位姿处合成物体特定视图并重建密集2D-3D对应，无需额外参数即可锐化初始位姿。
◆ 设计多掩膜假设选择策略，联合评分多个分割候选，有效解决分割模糊问题。</td></tr>
<tr><td>2026-09-06</td><td>Radiation, Rotation and Scale Invariant Feature Descriptor for Multimodal Image Matching<br><a href='http://arxiv.org/pdf/2609.06343'>论文</a> | <a href='https://github.com/yeyuanxin110/RRSI'>代码</a></td><td>本文提出一种面向多模态图像匹配的辐射、旋转与尺度不变特征描述子RRSI，有效应对几何形变和非线性辐射差异的挑战。其核心贡献在于设计了一个端到端的深度学习框架，能够联合编码模态间的几何与辐射关系。◆ 提出双头区域采样模块，同时进行笛卡尔和对数极坐标采样，兼顾空间结构并增强对旋转和尺度的鲁棒性。◆ 在统一深度特征空间中实现模态内、双头采样和模态间区域的联合特征编码、交互与融合，提升匹配精度。◆ 引入双向跨模态生成式重建约束，通过解码隐特征生成对应模态的结构块，锚定模态不变的几何拓扑，且推理时无额外开销。实验表明该方法在光学红外与光学SAR数据集上性能优越，支持0到360度全旋转及最高四倍尺度变化，并在计算机视觉、遥感和医学图像上展现良好泛化性。</td></tr>
<tr><td>2026-09-04</td><td>ARC-Loc: Leveraging Azimuthal Ray Convergence as a Geometric Cue for Direct Cross-View Localization<br><a href='http://arxiv.org/pdf/2609.04965'>论文</a></td><td>ARC-Loc提出一种全新的跨视角定位范式，无需BEV变换或外部深度模型，即可直接匹配地面图像与卫星图像。其核心思想借鉴人类“后方交会”定位技巧，将地面关键点转为卫星地图上的方位射线，并通过射线汇聚于用户位置这一几何约束完成定位。该方法设计了最小方位射线汇聚求解器确定交点，同时引入ARC损失来优化匹配网络，实现了显式的线到点对应。◆ 创新性地将地面到卫星匹配简化为二维方位射线求交，绕开病态的2D到3D提升过程，避免几何畸变与计算开销。◆ 提出轻量级ARC求解器和配套ARC损失，使网络训练可直接优化定位目标，且无需外部深度先验。◆ 在保持竞争精度的前提下，推理更快、内存更省，并能轻松嵌入现有跨视角定位框架，工程实用性突出。</td></tr>
<tr><td>2026-09-04</td><td>XDG: Accelerated Visual Disambiguation<br><a href='http://arxiv.org/pdf/2608.29733'>论文</a> | <a href='https://github.com/xtcpete/xdg'>代码</a></td><td>该论文针对三维重建中视觉混淆（doppelganger问题）导致错误匹配的难题，提出了一种高效的可扩展视觉消歧模型XDG。其核心洞察是3D基础模型已具备跨视角几何推理能力，因此消歧任务应直接适配骨干网络的表征，而非额外训练庞大的解码器重新学习配对关系。

◆ 创新点一：XDG采用轻量化的LoRA适配器对Depth Anything 3进行微调，避免了传统方法在骨干网络之上叠加重型Transformer分类器带来的巨大计算开销。

◆ 创新点二：创造性地将Depth Anything 3中的相机令牌重新用作紧凑的配对级分类令牌，再通过小型MLP头预测候选图像对是否观测到同一三维表面。

实验结果表明，XDG在保持与当前最优消歧方法相当精度的同时，实现了超过3倍的推理加速，在包含数千张图像的LaMAR场景中可节省十余小时处理时间，展现了出色的精度-效率权衡。</td></tr>
<tr><td>2026-09-02</td><td>Scalable Bayesian Optimization of Composite Functions for Image-Based Inverse Problems in Materials Characterization<br><a href='http://arxiv.org/pdf/2609.02126'>论文</a></td><td>本文针对材料表征中从科学图像反演物理参数的难题,提出了一种可扩展的复合函数贝叶斯优化方法SBOCF,用于电子显微学中样品厚度和晶体倾转角等关键参数的估计。该方法通过利用图像匹配目标的已知复合结构以及模拟图像中的中间信息,将原本需要建模的输出维度从24,649个像素大幅压缩至11个,显著提升了计算效率。

◆ 提出SBOCF方法,利用块级图像摘要加两项修正项,在保持原始像素级目标的同时将建模输出从24,649降至11,大幅降低计算开销。

◆ 在仅50次模拟器评估的预算下,SBOCF在SrTiO3基准测试中将最终SSE中位数降低最高达290倍,显著优于标准期望改进贝叶斯优化。

◆ 无需针对特定任务的预训练即可在实验数据上获得与文献一致的参数估计,并能直接用于下游叠层成像重建,恢复原本模糊的原子结构。</td></tr>
<tr><td>2026-09-02</td><td>GeoStore: Finding Small Storefronts in Large Scenes -- A Fine-Grained POI Localization Benchmark with Global-to-Local Asymmetric Matching<br><a href='http://arxiv.org/pdf/2609.02012'>论文</a></td><td>该论文针对POI本地化任务,指出其与视觉位置识别(VPR)的本质差异:查询图像是目标占据画面主体的近景特写,而参考图像是目标仅占小区域且周围有大量视觉相似店铺的远景街景,呈现显著的非对称细粒度匹配特性。现有面向VPR的全局描述子方法因单一向量难以突出小目标而表现受限。

◆ 提出了首个面向该非对称细粒度开放集设定的基准GeoStore,填补了POI本地化系统化评测的空白。

◆ 提出了GLAM全局到局部非对称匹配框架,结合检索锚定的全局描述子与局部非对称通路,将参考图像编码为压缩的区域token集合,通过可学习的软晚期交互与单查询探针进行匹配。

◆ 推理阶段复用同一组token实现轻量的互最近邻重排序,在Recall@1/5/10和mAP上超越强基线,同时重排序特征量减少约5倍、每对匹配成本降低约两个数量级。</td></tr>
<tr><td>2026-08-30</td><td>SGFormer: Structure-Guided Transformer for Robust Local Feature Matching<br><a href='http://arxiv.org/pdf/2608.03423'>论文</a></td><td>该论文针对局部特征匹配中现有无检测器方法(如LoFTR)在大幅视角变化场景下出现的注意力发散问题,提出了一种新颖的结构引导Transformer网络SGFormer。研究发现,标准Transformer的无约束全局注意力机制会使部分高置信度匹配落在重叠区域之外,降低匹配可靠性。

◆提出Triple-Structure-Attention(TSA)模块,利用网络浅层局部特征强化显著结构区域的特征表达,引导后续Transformer阶段将注意力聚焦于具有显著结构的重叠区域。

◆采用半稠密的由粗到精匹配流水线,自适应地更新显著结构附近的注意力,在提升全局建模能力的同时抑制非重叠区域的干扰。

◆在多个具有挑战性的摄影测量基准数据集上的实验表明,SGFormer有效缓解了注意力发散现象,显著提升了匹配精度与鲁棒性。</td></tr>
<tr><td>2026-08-27</td><td>SSMB: Self-Supervised Local Feature Detection under Motion Blur<br><a href='http://arxiv.org/pdf/2608.27181'>论文</a></td><td>本文针对运动模糊下关键点检测难题,提出去模糊化、自监督的检测器SSMB,无需手工检测器或外部伪标签,直接对模糊图像进行检测。现有方法多依赖耗时的去模糊后处理或回归手工关键点位置,前者易引入伪影,后者继承了手工检测器的假设偏差。

◆ 提出完全自监督的模糊鲁棒关键点检测框架,无需去模糊步骤或外部伪标签
◆ 设计局部判别性增强(LDE)模块,在全局特征混合后有效恢复细粒度局部判别能力
◆ 采用两阶段训练机制:合成几何形状预训练引导空间判别性,真实锐-糊图像对实现模糊不变检测
◆ 设计多组件自监督损失函数,联合约束跨域一致性、几何对齐与空间覆盖

在关键点检测、图像匹配、相对位姿估计和视觉定位等任务上,SSMB均刷新了稀疏关键点检测器的最优性能,一致超越现有监督与自监督基线方法。</td></tr>
<tr><td>2026-08-24</td><td>Misanthrope: A Privacy-Preserving Keypoint Detector<br><a href='http://arxiv.org/pdf/2608.23012'>论文</a> | <a href='https://github.com/fratopa/misanthrope'>代码</a></td><td>本文提出Misanthrope，一种面向图像匹配任务的隐私保护关键点检测器。针对分布式计算场景下本地图像特征易遭受反演攻击、泄露人像隐私的问题，Misanthrope通过自蒸馏训练策略，从源头避免在人体上检测关键点，而非依赖事后模糊处理。

◆ 创新点一：提出从源头规避隐私风险的检测思路，使反演攻击无法重建人物内容
◆ 创新点二：采用自蒸馏训练框架实现&quot;避人&quot;关键点检测，无需人工标注隐私敏感区域
◆ 创新点三：证明传统特征管道的反演图像可用于检测和重识别场景中的人物
◆ 创新点四：在人物作为干扰物的困难场景下，匹配性能超越现有最优方法

在Image Matching Challenge 2021 Phototourism测试集9个场景中，Misanthrope在7个场景上取得稀疏特征提取器最优表现，同时有效缓解了隐私反演攻击风险。</td></tr>
<tr><td>2026-08-23</td><td>CausalCache: Conditional High-Fidelity Restoration for Long-Horizon GUI Agents<br><a href='http://arxiv.org/pdf/2608.22577'>论文</a></td><td>CausalCache 针对长程 GUI 智能体在视觉上下文预算受限时难以兼顾历史保真度的问题，提出了条件保真度恢复框架：每个事件以摘要形式存储并链接归档截图，预算 B 决定哪些事件被提升为&quot;摘要+图像&quot;形式。与 Recent-B 将所有槽位分配给最近事件不同，CausalCache 跨完整轨迹重新分配预算，仅当远距事件的条件边际效用更高时才替换近期图像。方法在 OSWorld-Verified 上比纯摘要记忆提升约 13 个成功率点；在跨应用移动基准上整体提升 3.7 分，记忆关键子集提升 8.6 分，匹配对照组无显著差异。

核心创新点：

◆ 提出条件保真度恢复机制，根据条件边际效用跨完整轨迹动态分配视觉预算，使高保真图像资源从机械偏向近期事件转向任务相关的关键事件。

◆ 设计历史门控键值适配器（HGKV），仅修改被恢复的历史图像令牌，无历史图像时完全旁路，对冻结策略影响最小。

◆ 引入匹配预算对照组与按臂锚定的双重差分监督，确保预算开销相同情况下，仅真正的选择性恢复才获得增益。

◆ 构建预算感知选择器，在摘要事件中自动挑选最值得恢复为高保真的目标，提升决策可解释性与效率。</td></tr>
<tr><td>2026-08-19</td><td>Evaluation of Image Matching Methods for Visual Odometry on UAVs<br><a href='http://arxiv.org/pdf/2608.18624'>论文</a></td><td>本文针对无人机在GNSS信号失效场景下的导航难题，研究了视觉里程计作为关键替代方案。论文系统评估了多种当前最先进的图像匹配方法在无人机下视相机位置追踪任务中的表现，并构建了专用合成数据集进行测试验证。

◆构建了用于无人机视觉里程计评估的合成数据集，解决了真实飞行数据采集成本高、场景受限的问题
◆对深度学习与传统图像匹配方法在VO任务中进行了系统全面的对比评估
◆研究发现虽然最新RoMa匹配器效果最佳，但传统SIFT特征在特定场景下仍能超越部分最新的深度学习方法

该工作为深度学习方法与传统特征方法在无人机视觉导航系统中的实际应用选择提供了重要参考依据。</td></tr>
<tr><td>2026-08-12</td><td>NPLSD: Accelerating Line-Segment Detection on NPU Microcontrollers<br><a href='http://arxiv.org/pdf/2609.25022'>论文</a></td><td>论文指出Transformer线段检测器在STM32N6的Neural-ART NPU上，因attention、grid-sampling和normalization缺少加速原语而难以实用，并逐算子刻画该架构失配。作者据此提出NPLSD，用统一方法构建一对NPU兼容线段检测器。
◆ 提出NPLSD-H，保留LINEA的HGNetv2卷积骨干，用全卷积特征金字塔和F-Clip密集头替换Transformer头。
◆ 提出NPLSD-M，将M-LSD-tiny主干适配到NPU支持的算子集合，实现轻量化。
◆ 通过ImageNet热启动和ShanghaiTech Wireframe训练，2.63M参数的NPLSD-H达sAP10=37.9，int8为35.9；0.62M参数的NPLSD-M达41.9，int8为41.1。
◆ 控制消融将主干设为唯一变量，并发现仅初始化就贡献4.6个点，验证训练策略重要性。</td></tr>
</tbody>
</table>
</div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-28</td><td>CAT-Free: Multi-View Pedestrian Localization without Calibration, Annotations, or Target-Scene Training via Adaptive Geometric Filtering<br><a href='http://arxiv.org/pdf/2609.34302'>论文</a></td><td>CAT-Free提出仅用同步RGB视频即可完成多视角行人定位，无需相机标定、位置标注或目标场景训练。
◆ 它从视频自动估计相机配置，并融合多相机观测估计行人位置。
◆ 针对自动估计误差，引入两个自适应几何滤波器，阈值由输入序列自动确定，剔除不可靠定位。
◆ 在WildTrack、MultiviewX和GMVD上分别取得82.5、84.5、65.7 MODA，且能跨场景无重调迁移。
◆ 定位不确定性可有效预测MODA，相关系数r=-0.98，提供无需标签的可靠性估计。</td></tr>
<tr><td>2026-09-24</td><td>From WPT to Encrypted Telemetry: A Battery-Free Backscattering-based Polarimetric Wireless Sensor<br><a href='http://arxiv.org/pdf/2609.29214'>论文</a></td><td>本文提出一种由辐射式无线携能供电的室内无电池无线传感节点，面向安全、节能的主动感知。该节点集成温湿度、气压和VOC测量，并由低功耗MCU完成校准、VOC指数计算、载荷格式化和AES-128加密。实验表明，多传感器读出与加密传输可靠，且完整感知-计算-加密-传输周期能耗极低。
◆将无电池传感从简单采集回传推进到具备节点计算与AES-128加密保护的安全遥测。
◆在同一低功耗平台上融合多参数环境感知、VOC指数推导、数据格式化与加密传输。
◆提出1-bit控制的反向散射整流天线，同时完成辐射WPT能量收集并产生正交极化反向散射信号，实现稳健极化通信。</td></tr>
<tr><td>2026-09-23</td><td>Calibration-Free Surface Normals Estimation in Vision-Based Tactile Sensing using Universal Photometric Stereo<br><a href='http://arxiv.org/pdf/2609.31754'>论文</a></td><td>本文提出一种免标定的视触觉接触表面法向估计方法，利用通用光度立体神经网络直接从触觉图像推断法向。作者在三种不同光学系统传感器上验证了跨传感器适用性，并在金属球、自然纹理物体及Dome形Digit 360实验中取得平均角误差6.56°、10.66°和10.18°的结果。这表明在充分照明下，仅用合成数据训练的模型也能稳健估计真实接触面法向。
◆ 提出免标定的通用光度立体框架，直接估计接触面法向，免除物理探针标定。
◆ 证明通用方法可跨不同光学系统传感器迁移，并匹配标定基线的精度。
◆ 为不同视触觉传感器建立统一接触面表示，推动可迁移触觉感知。</td></tr>
<tr><td>2026-09-22</td><td>Laser-Tracker-Assisted Camera-to-Robot Calibration for Mobile Robots<br><a href='http://arxiv.org/pdf/2609.27006'>论文</a></td><td>本文提出一种激光跟踪仪辅助的移动机器人相机手眼标定方法，将激光跟踪仪的三维计量与相机的二维观测相结合。该方法在作者此前面向地面观测移动机器人的标定工作基础上，给出了在跟踪仪定位的移动机器人坐标系中估计相机位姿的广义公式。  
◆ 将激光跟踪仪三维计量与相机二维观测融合，用于移动机器人上的相机外参标定。  
◆ 通过串联多个标定目标，放松了先前方法对机器人和相机配置的假设与限制。  
◆ 提出更通用的相机到机器人标定框架，可支持多种配备相机的移动机器人系统。</td></tr>
<tr><td>2026-09-22</td><td>From Instrument-Mounted Demonstrations to In-Vivo Execution: Learning Bimanual Laparoscopic Appendectomy Without Robot-Collected Demonstrations<br><a href='http://arxiv.org/pdf/2609.25625'>论文</a></td><td>本文提出从手持腹腔镜器械演示到活体执行的端到端流程，将术中器械运动捕获并用于训练手术机器人策略，在活兔上验证。
◆ 设计仅装在标准腹腔镜器械杆上的状态记录器，融合惯性、飞行时间与霍尔传感器，无外部相机或追踪器即可恢复器械位姿和钳口状态。
◆ 构建传感器延迟测量与对齐数据管道，以机器人真值校准各通道并生成观察-动作对。
◆ 使用微调DINOv3骨干的扩散策略，并通过由离体兔阑尾深度图重建的物理模拟器闭环选择设计。
◆ 在849条四只活兔演示上重训练，部署于另四只活兔并带电外科，医生选择手术阶段，四只中三只完成阑尾切除。
◆ 证明机器人无需采集演示，仅作校准时序参考和执行器，医生自身器械演示足以训练、选择并部署双臂活体手术策略，且公开两个演示数据集。</td></tr>
<tr><td>2026-09-20</td><td>HEARTH: An Object-Centric RGB-Thermal-3D Dataset for Temperature-Aware Robot Manipulation<br><a href='http://arxiv.org/pdf/2609.23418'>论文</a></td><td>HEARTH 是一个以物体为中心、同时包含 RGB、热成像与 3D 几何并带真实温度测量的机器人操作数据集，覆盖 18 类日常物品的 90 个物体和 145 个状态。
◆ 构建了将表观表面温度经相机标定和位姿迁移映射到重建网格的采集流程，并提供原始温度、相机参数、RGB 纹理网格与热纹理。
◆ 基于这些资产构建三个 LIBERO 衍生任务并采集 1,200 条演示，用于微调预训练 VLA 模型 π0.5。
◆ 通过消融证明热观测对温度相关物体选择任务有效，成功率从仅 RGB 基线的 35.0% 提升到 75.0%。
这些贡献表明 HEARTH 能支持温度感知的机器人操作学习，并可用于训练策略遵循温度相关指令。</td></tr>
<tr><td>2026-09-20</td><td>P$^2$Calib: Utilizing Pattern Priors for LiDAR-Camera Extrinsic Calibration<br><a href='http://arxiv.org/pdf/2609.07516'>论文</a></td><td>本文提出P2Calib，一种利用标定板CAD模型提供的模式先验来提升激光雷达与相机外参标定精度的方法。针对传统四孔标定流程中激光雷达侧孔中心提取受稀疏角覆盖与混合像素影响的问题，该方法将已知孔半径作为拟合约束，有效防止中心估计在数据稀疏时发生退化。进一步地，P2Calib将四个孔的刚性矩形布局作为全局一致性约束，用于修正各孔之间的残余误差。上述两种先验被集成到一个包含完整标定流程的交互式工具中。在模拟与真实数据集上的实验表明，相比基线，联合配准残差分别降低90%和82%，留出重投影误差分别降低96%和77%。代码与数据已公开。
◆创新点一：将已知孔半径作为拟合约束，缓解稀疏角覆盖导致的孔中心估计退化。
◆创新点二：利用四孔刚性矩形布局作为全局一致约束，消除跨孔残余误差，提升整体标定精度。</td></tr>
<tr><td>2026-09-18</td><td>GaitVista: Reliability-Aware AI Measurement toward Accessible Longitudinal Gait Assessment<br><a href='http://arxiv.org/pdf/2609.22619'>论文</a></td><td>GaitVista提出一种面向可及纵向步态评估的可靠性感知测量层，核心是避免传感失效被误判为患者变化。
◆ 它用轻量门控按关节和帧分配视觉贡献，综合相机覆盖、局部视觉质量、跨模态不一致和根运动连续性来估计可靠性。
◆ 它将关节-帧可靠性显式暴露供检查，使多模态融合不再条件盲，并提升可解释性。
◆ 在七种干净与退化传感条件下，它降低全身和下半身平均误差27.7%和27.8%，取得融合方法中最差条件最低误差，并将与关节-帧oracle差距从2.76至5.33厘米降至1.11厘米。
在MoVi上，它是唯一可部署且同时优于两个单模态流的融合方法，标记支持误差较最强学习融合基线降低6.4%，并在TotalCapture上使双膝屈曲波形精度提升18.9%。
惯性数据中位置和时间变化的磁干扰支持其可靠性前提，但研究仅限健康受控参与者且保留个体IMU校准，因此是迈向可及步态评估的进展，而非已验证临床应用。</td></tr>
<tr><td>2026-09-15</td><td>GeomVLA: Unifying Scene, Motion, and Action in 3D<br><a href='http://arxiv.org/pdf/2609.13812'>论文</a></td><td>GeomVLA提出统一场景、运动与动作的VLA模型，在机器人中心3D坐标系中融合感知、潜在场景运动预测与动作生成。
◆ 将预训练VLM特征借助深度和相机标定提升为空间接地的3D场景token，同时保留VLM语义表征。
◆ 提出3D Scene Trajectory Denoiser，以任务为条件学习场景点未来3D运动的潜在表示。
◆ 不直接开环执行预测轨迹，而是提取中间运动token，通过几何感知注意力条件化3D flow-based动作去噪器。
实验上在CALVIN达SOTA，LIBERO和RoboTwin2.0有竞争力，真实操作无机器人动作预训练也超越强基线。
消融表明仅未来运动推理不够，主要增益来自场景表示、运动预测与动作在感知到动作全流程中保持几何一致。</td></tr>
<tr><td>2026-09-14</td><td>Closed-form Bayesian homography estimation from noisy point correspondences<br><a href='http://arxiv.org/pdf/2609.15227'>论文</a></td><td>本文针对传统单应估计多只给点估计、不直接量化噪声不确定性的问题，提出一种快速的贝叶斯单应估计方法。该方法在点对应中显式融合测量不确定性与先验知识，并输出单应参数的后验分布，从而将不确定性传播到后续任务。
◆ 提出面向噪声点对应的贝叶斯单应估计框架，可同时给出参数后验分布与不确定性量化。
◆ 在齐次坐标下推导出单应后验均值的闭式解，显著提高计算效率。
◆ 结合迭代贝叶斯策略处理模型非线性，扩展闭式结果的适用性。
◆ 合成实验表明其在不同噪声条件下精度优于DLT，图像拼接实验验证了真实图像适用性并能额外提供不确定性信息。</td></tr>
<tr><td>2026-09-14</td><td>Comparing Trajectories from Positions Alone: Curvature-Based Time Alignment and Drift Error Metric<br><a href='http://arxiv.org/pdf/2609.14936'>论文</a></td><td>本文针对机器人领域参考轨迹难以获取、ATE/RPE依赖未明假设与参数而可能导致误导比较的问题，提出一套标准化、可靠的轨迹评估协议。  
◆ 提出基于曲率信号的新型时间对齐方法，仅凭位置信息即可比较轨迹。  
◆ 提出按行驶距离归一化的漂移误差度量，提升不同长度轨迹间的可比性。  
◆ 显式处理时间同步、采样对齐与外参标定，并通过敏感性分析量化其影响。  
该协议提升了状态估计、定位与SLAM中轨迹评估的严谨性、可复现性和标准化程度。</td></tr>
<tr><td>2026-09-14</td><td>Semantic Fibers and Cross-Gram Interference: A Calculus of Safety Drift in Overcomplete Representations<br><a href='http://arxiv.org/pdf/2609.14861'>论文</a></td><td>论文针对模型英文拒绝但忠实翻译下遵从的跨语言安全失败，提出用审计等价关系而非仅输出行为来刻画安全漂移。
◆ 在给定商、表示、度量、特征字典、评分头、阈值和对比模型下，将安全漂移精确刻画为纤维内对比的交叉Gram泛函，其最坏值为支撑函数，间隔不变性由零化子条件给出。
◆ 引入受杠杆对偶χ²=1/ℓ-1支配的内在校准暴露度量，把观察漂移分成可重校准的读取器故障、病态不可靠的精确校正和读取器无法消除的表示层碰撞三类。
◆ 该分类表明相同观察暴露可能对应根本不同的修复判决，从而改变安全干预选择。
◆ 框架可扩展到锥值安全头，并用非绑定换序恒等式诊断线性控制接口，其校准残差可预测未见状态与目标上的三控制组合误差。
◆ 实验上该残差的中位Spearman相关达0.964，显著优于静态交叉Gram基线的0.269，验证其诊断与预测价值。</td></tr>
<tr><td>2026-09-12</td><td>Measurement-Error-Aware Causal Distributed-Lag Quantile Modeling of Indoor Air Pollution and Short-Term Lung-Function Deterioration<br><a href='http://arxiv.org/pdf/2609.31646'>论文</a></td><td>本文提出 CAUSALQUANT-ASTHMA，面向室内空气污染与短期肺功能下降，构建测量误差感知的因果分位数分布滞后分析框架。
◆ 利用稀疏参考测量训练非线性校准模型，以校正低成本传感器的非线性测量误差。
◆ 采用稳定序列广义倾向权重处理时变混杂，并用易感性调节、平滑且非交叉的分位数模型估计滞后与持续暴露对比。
因缺乏同时具备密集室内传感、参考共置和结局纵向数据的授权队列，研究用五个半合成面板、每实现150名患者和12600患者日，并以已知反事实真值评估。
结果显示剂量反应IAE为0.304±0.094，较最强测量误差与倾向加权基线改善24.2%，pinball损失最低1.065，零分位交叉，80%区间覆盖78.1%，传感器校准使暴露RMSE降低33.7%。
这些发现证明方法可行与可复现，而非临床有效性，部署前仍需经治理批准的前瞻性外部验证。</td></tr>
<tr><td>2026-09-11</td><td>DRS-VPT: Directly Relocalizing in a Scan with Vision Point Transformers<br><a href='http://arxiv.org/pdf/2609.12557'>论文</a></td><td>DRS-VPT是一种面向基础图像到扫描配准的前馈Transformer架构。
◆ 它统一预测扫描位姿、扫描点图及每台相机位姿和点图，并将它们统一表示在第一相机坐标系中。
◆ 它引入粗到细的逐点与逐像素特征金字塔，实现扫描到首张图像的直接重投影对齐。
◆ 该统一公式连接自动驾驶相机-LiDAR标定与室内相机到地图重定位等下游任务。
实验表明，单一DRS-VPT在自动驾驶图像-LiDAR配准上达到最优，在室内重定位中无需训练地图特定权重也具竞争力，并具有强零样本迁移能力。
定性结果还显示模型学到背面点遮挡等复杂扫描到图像投影特性。</td></tr>
<tr><td>2026-09-09</td><td>Automatic Reproducible Camera Intrinsic Calibration<br><a href='http://arxiv.org/pdf/2609.10082'>论文</a></td><td>本文提出全自动相机内参标定流程，可从采集数据中自动决定高质量图像与径向畸变阶数。核心贡献是无需人工筛选图像或指定畸变阶数，并通过迭代剔除与留出验证提升标定可靠性。
◆ 采用迭代剔除机制，在当前候选图像集估计参数，并移除平均残差超过中位数若干倍的视图，且在每个候选畸变阶数下独立运行，使保留图像集与该阶数残差尺度一致。
◆ 通过留出图像选择畸变阶数，固定内参与畸变、仅重估标定板位姿，确保新增畸变系数得到独立观测支持。
◆ 集成上述步骤为交互式标定工具，支持全流程数据检查和参数估计。
实验在自有相机数据与五个公开真实数据集上表明，图像筛选使留出重投影误差降低25%，阶数选择再降低5%，在四种配置中取得最低留出均值，且无需人工选图，并计划公开代码和数据。</td></tr>
</tbody>
</table>
</div>

<h2 id='robot-vlm'>Robot VLM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-28</td><td>MM-ABC: Towards Generalist Mobile Manipulation via Seeing, Coordinating and Imagining<br><a href='http://arxiv.org/pdf/2609.35652'>论文</a></td><td>MM-ABC是面向通用移动操作的基础模型，围绕“看见、协调、想象”臂基协作，应对连续自运动空间感知与异构臂基动作协调两大挑战。
◆ 采用稀疏多层级VLM特征进行空间感知，为移动操作提供更强的空间落地表示。
◆ 引入仅训练时使用的未来分支，以世界想象和几何意图作为额外监督，提升感知、操作意图预测与整体学习信号。
◆ 提出MM-APT，通过掩码联合注意力和干净动作x预测，协调分离的操作与移动动作流，增强跨流协作。
◆ 在5000+小时、40万+回合、12个数据集、17种本体上预训练，并在多基准及真实移动操作任务中系统验证。
实验显示其EBench成功率44.71%、RoboCasa365为61.2%、LIBERO为99.1%、LIBERO-Plus为82.8%、真实五任务平均83%，消融也证明关键设计有效。</td></tr>
<tr><td>2026-09-28</td><td>JRDB-AVR: An Active Visual Reasoning Benchmark for Embodied Agents in Real-World Environments<br><a href='http://arxiv.org/pdf/2609.35032'>论文</a> | <a href='https://github.com/ControlNet/JRDB-AVR'>代码</a></td><td>现有视觉推理基准多评估被动观察与最终答案，忽视主动推理和证据获取，模型可能未观察相关对象、时间或视角却给出看似合理的答案。
◆ 提出JRDB-AVR，基于真实JRDB机器人数据，用结构化问题生成引擎构建主动视觉推理基准。
◆ 让具身智能体按时间戳和视角请求有限观测，并同时评估最终答案与支撑它的视觉证据。
◆ 覆盖多真实环境，包含时间搜索、视角选择和面向人的组合推理等多样问题。
◆ 提出JRDB-AVR-Agent，维护显式观察锚定的图式世界模型并通过求解作答。
实验显示当前基线答案准确率与证据准确率存在显著差距，证明主动证据感知评估对具身视觉推理必要。</td></tr>
<tr><td>2026-09-28</td><td>D$^2$-VLA: Dual-Memory Dual-Frequency Vision-Language-Action Model For Long Dynamic Manipulation<br><a href='http://arxiv.org/pdf/2609.34792'>论文</a></td><td>本文提出D²-VLA，一种在预训练VLA的KV-cache接口融合双记忆与双频控制的视觉-语言-动作模型，用于长时动态操作。
◆ 它用块级因果KV缓存增量编码观察，并依据不同时间注意力模式，为VLM与动作专家构建分离的历史KV读取视图。
◆ 在周期性VLM更新之间，门控适配器将新视觉特征注入最新历史条件KV块，短快记忆队列支持动作重规划，从而避免频繁调用昂贵VLM。
◆ 论文提出DOMINO-Long十任务基准，要求机器人在操作移动物体时利用已离开视野的早期视觉线索。
实验显示其DOMINO完整任务成功率达29.3%，优于π0.5的9.6%和PUMA的17.2%，DOMINO-Long达60.0%，优于35.4%和20.6%。
它还提升八项真机任务成功率，并在LIBERO-Long达97.5%、RoboTwin 2.0达74.3%。</td></tr>
<tr><td>2026-09-28</td><td>PanoVLN: Towards Effective Panoramic Vision-and-Language Navigation<br><a href='http://arxiv.org/pdf/2609.34759'>论文</a></td><td>PanoVLN探索全景视觉语言导航，认为更完整的视觉上下文应带来更好决策，但简单将透视图像替换为全景增益有限。论文诊断出充分利用更广视野需同时改进动作预测、训练监督和视觉表示。
◆ 提出置信度引导执行策略，动态决定单张全景预测的动作序列中执行多少步后再重规划，以支持更长时程规划和大转向。
◆ 构建含频繁分支点和清晰指令的训练路线，为复杂路口选择提供针对性监督。
◆ 融合RGB全景的语义与几何特征，在不增加视觉token的情况下建模跨视角空间关系。
基于4B骨干和仅RGB输入，PanoVLN在R2R-CE和RxR-CE Val-Unseen成功率上分别超越此前SOTA 11.9%和8.7%，四足真实实验也显示导航更快且停顿更少。</td></tr>
<tr><td>2026-09-28</td><td>Long Time No See: Benchmarking VLMs for Out-of-Sight Spatiotemporal Reasoning in Egocentric Videos<br><a href='http://arxiv.org/pdf/2609.34630'>论文</a></td><td>本文提出Beyond3D，首个用于隔离动态自我中心视频中“视野外时空推理”能力的VQA基准，要求模型回答已移动且离开视野的物体问题。
◆ 构建首个专门评测视野外时空推理的基准，每个查询都针对已移动并离开视野的目标物体。
◆ 利用HD-EPIC标注、3D位置、相机位姿和场景几何生成物体可见性轨迹，区分可见、遮挡与离开视野。
◆ 设计9000道八类问题，覆盖135个视频和9名参与者，并组织为视觉定位、时间定位、场景定位和3D空间感知的推理链。
◆ 对9个通用及空间专用VLM进行系统评测，最佳仅42.2%，纯文本基线31.9%，机会基线29.7%。
实验表明当前模型在追踪物体离开视野后的状态更新和“最后可见时间”恢复上仍远未解决。</td></tr>
<tr><td>2026-09-28</td><td>Where Memory Belongs: Ledger, an Object Ledger for Memory-Augmented VLAs<br><a href='http://arxiv.org/pdf/2609.34554'>论文</a></td><td>本文提出 Ledger，主张记忆类型决定其存放位置：短期感知记忆应留在策略内，长期对象记忆应外置为显式可读记录。
◆ 将记忆拆分为策略内帧采样记忆与外部时空对象账本，分别覆盖重复、计时、回溯与持久空间状态、包含关系、事件历史。
◆ 用 SAM3 跟踪器和 VLM 描述器从演示中构建 ledger，并由 LLM 规划器在步骤边界读取，决定下一步使用哪类记忆。
◆ 在单个微调 π0.5 策略上实现该框架，无需任务级路由器，仅凭指令和记录在运行时选择记忆来源。
◆ 在 RoboMME 上，Ledger 以单套权重取得四套平均 64.3%，超过最强先前方法 45.9%；对象引用 60.7% 对 40.3%，对象永久性 86.7% 对 56.2%。</td></tr>
<tr><td>2026-09-28</td><td>ARS: Agentic Reward System for Robot Learning<br><a href='http://arxiv.org/pdf/2609.34484'>论文</a> | <a href='https://github.com/midea-ai/ars'>代码</a></td><td>论文提出ARS，一种无需额外训练奖励模型、利用通用视觉语言模型进行机器人进度奖励建模的推理框架，可从离线轨迹和任务指令估计逐帧任务进度。  
◆ 提出基于通用VLM的进度奖励建模新范式，无需额外训练奖励模型即可完成推理。  
◆ 设计自适应视觉检查机制，由子代理提议任务相关事件时间线，再由主代理验证和修订。  
◆ 支持可选终端结果标签与视觉参考，并能审计外部奖励模型的进度估计。  
◆ 在语义错配基准中有效抑制错物操作等虚假进度，并在仿真策略学习中优于多个奖励基线。  
◆ 在真实工业装配线多螺丝紧固任务中，支持混合质量离线经验下的长时程策略学习。</td></tr>
<tr><td>2026-09-28</td><td>RoboIRGBench: Benchmarking Implicit Referential Grounding in Vision-Language-Action Models<br><a href='http://arxiv.org/pdf/2609.34384'>论文</a></td><td>◆ 本文将机器人操作中的隐式指代落地（IRG）定义为从语言和感知上下文中恢复未显式说明的目标、数量和关系的能力，并系统研究这一未被充分探索的问题。  
◆ 提出RoboIRG-Bench，基于RoboMME构建11类任务、40个变体，覆盖直接、推理中介、空间和上下文四类指代挑战。  
◆ 评测多种代表性VLA模型及不同记忆机制，揭示显式指令下表现良好的模型在IRG下显著退化，形成明显的指代鲁棒性差距。  
◆ 发现推理中介与空间指代尤其困难，外部VLM可提高鲁棒性但仍大量失败，且换成更强VLM也不能消除差距。  
◆ 在Franka Research 3真实机械臂上验证该差距持续存在，并表现为错误指代和下游执行失败，说明可靠指令跟随需深度融合语言、感知、推理与行动。</td></tr>
<tr><td>2026-09-28</td><td>Predictive Semantic Safety: From Visual Physical Reasoning to Safety-Critical Control<br><a href='http://arxiv.org/pdf/2609.34356'>论文</a></td><td>本文提出预测语义安全PSS，将视觉物理推理与基于备用策略的安全过滤相连接，以应对当前几何环境未显现的未来物理危险。
◆ 利用视觉语言模型预测物理事件及其时序，或直接预测物体位移。
◆ 通过显式运动模型把事件假设转换为物体轨迹。
◆ 采用分裂共形预测联合校准指定物体、观测时间和未来时间上的位置误差，并将位置区域转为预测占用。
◆ 针对该占用评估预设备用机动，推导输入仿射约束，以最小修改名义输入并保持动力学和输入限制下的备用可行性。
MuJoCo中Unitree Go1的坠落物、冲击支撑丧失和接触传播实验表明，PSS安全回合率达99.3%，远高于仅用当前障碍几何的BCBF基线43.3%。</td></tr>
<tr><td>2026-09-28</td><td>RoboICL: Embodied In-Context Learning with GPT-6 Astra<br><a href='http://arxiv.org/pdf/2609.34261'>论文</a> | <a href='https://github.com/Mosi-AI/RoboICL}{https://github.com/Mosi-AI/RoboICL}'>代码</a></td><td>RoboICL是一种无需机器人参数更新或学习专用VLA的具身上下文学习框架，旨在用GPT-6 Astra缩小通用视觉语言模型在高精度和长时程任务上的差距。
◆ 分离演示上下文与交互记忆：前者提供录制的示例，后者累积模型自身动作和观察结果，并共享观察—动作—回执—观察语法。
◆ 结合采样演示块与有界锚定记忆：固定锚点保留早期交互用于上下文学习，最新交互支持即时纠错，从而跨任务阶段保留经验。
◆ 采用可选Jev门控动作复用，在不牺牲性能的情况下减少GPT-6 Astra调用33%—48%，且无需针对机器人微调或训练VLA。
在30个RoboDojo任务上总体得分50.64，远超最强基线33.68；真实机器人平均进度由零样本14.45升至一演示63.33和三演示78.89，十任务子集60.60，接近π0.5+GPT-6 Astra混合方案。</td></tr>
<tr><td>2026-09-28</td><td>RAVEL: Asynchronous Rolling Inference for Flow-Based Vision-Language-Action Models<br><a href='http://arxiv.org/pdf/2609.34170'>论文</a></td><td>本文提出 RAVEL，一个面向基于流的视觉-语言-动作模型的异步滚动推理框架，旨在同时缓解 VLM 编码与多步动作去噪造成的延迟瓶颈。
◆ 通过滚动缓冲区让近期动作在单步去噪后即可执行，并把部分去噪的未来动作继续向前传递，从而减少多步去噪等待。
◆ 将 VLM 编码与滚动动作生成解耦，使动作专家能基于最新可用 VLM 上下文持续运行，避免被慢速编码阻塞。
◆ 引入轻量快速观测通路，将当前观测直接条件化到动作专家，提升闭环响应的实时性。
在仿真与真实机器人操作任务中，RAVEL 显著降低响应延迟，同时保持底层 VLA 的任务能力，实现高频、响应式的闭环控制。</td></tr>
<tr><td>2026-09-28</td><td>Beyond Retrieval Relevance: Scene-Grounded Risk Entailment for Vision-Language Driving<br><a href='http://arxiv.org/pdf/2609.34145'>论文</a></td><td>本文针对RAG中“检索相关但场景不适用”的风险知识鸿沟，提出在VLM决策前引入场景落地的风险蕴含推理。
◆ 构建驾驶风险知识图谱DRKG，以结构化感知实例化当前场景事实，为风险判断提供显式场景基础。
◆ 设计SWRL推理阶段，在规则前件联合满足时推导事件与有向风险关系，将隐式风险结论转为可验证证据。
◆ 将识别事件、绑定风险关系和激活规则语义描述组成紧凑证据，用于条件化VLM与扩散规划器。
在nuReasoning匹配对比中，该方法较相关性检索基线将NPS提升1.30、NC提升2.76。
结果表明，场景适用的风险证据比单纯语义检索更能改善安全加权规划。</td></tr>
<tr><td>2026-09-28</td><td>Quantile Head for Vision-Language-Action Models<br><a href='http://arxiv.org/pdf/2609.34061'>论文</a> | <a href='https://github.com/xwangrs/Quantile-Head-for-VLA'>代码</a></td><td>本文面向VLA动作头中“点回归只给点估计、标准流匹配需昂贵迭代采样”的问题，提出统一回归与流匹配的共享目标，并扩展得到分位数目标。
◆ 统一回归与流匹配目标，推导出分位数目标，连接确定性回归与生成式采样。
◆ 设计Quantile Head，一次前向预测中位数和正间隙，形成有序的边际动作分位数。
◆ 同一组分位数支持多种采样策略且无需重训，并通过联合监督训练默认中位数策略。
◆ 局部分析表明，在校准邻近分位数、固定间隙和匹配修正速度下，直接中位数更新比仅中位数监督方差更低。
实验表明该联合监督中位数策略在LIBERO、LIBERO-Plus、LIBERO-Pro和两个真机任务上平均成功率最高，并在匹配LIBERO基线中平均回合时间最短。</td></tr>
<tr><td>2026-09-27</td><td>Test-Time Spatial Reasoning for Robot Manipulation Using Generative Real-to-Sim<br><a href='http://arxiv.org/pdf/2609.33982'>论文</a></td><td>Simify是一个无需训练、在测试时通过大规模并行物理仿真进行显式空间推理的机器人操作框架。  
◆ 从单张RGB-D图像出发，利用3D生成模型和视觉语言模型重建可直接仿真的物体资产，实现生成式real-to-sim。  
◆ 任务由奖励函数指定，例如搭建最高塔，无需针对具体任务重新训练模型。  
◆ 在测试时启动数千个并行仿真rollout，并用进化搜索优化物体排列，通常数秒内收敛。  
◆ 在真实机器人硬件上端到端完成未见物体的复杂重排，性能优于现有空间推理基础模型。  
◆ 证明完整且准确的几何对成功sim-to-real迁移至关重要，并凸显推理时大规模并行仿真的价值。</td></tr>
<tr><td>2026-09-27</td><td>Robot-GST: geometry-aware spatial-temporal robot policy representation and evaluation<br><a href='http://arxiv.org/pdf/2609.33872'>论文</a></td><td>Robot-GST 提出几何感知的时空机器人策略表示与评估框架，旨在解决长时操作中缺乏结果预测与动作可行性评估导致误差累积的问题。
◆ 从 RGB-D 观测出发，结合 3D Gaussian Splatting 与 SAM3D 构建高保真 Gaussian-SAM 真实到仿真环境，支持“先模拟评估再行动”。
◆ 将视觉观测和语言指令与时空推理结合，利用大型视觉语言模型进行长时任务规划。
◆ 引入高斯感知最终状态估计，通过几何采样与基于状态的轨迹规划衔接高层规划与真实执行。
◆ 在执行前于 Gaussian-SAM 中模拟并评估候选动作序列，过滤不可行动作，提升真实部署可靠性。
在刚体、软体和可变形物体的 cube placing、toy packing、duck rearrangement 任务上验证，表明几何感知时空推理与状态感知执行能跨物体类别提升操作可靠性。</td></tr>
</tbody>
</table>
</div>

<h2 id='robot-visual-semantic-recognition'>Robot Visual Semantic Recognition</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-28</td><td>ExcavaTwin: Training-Free Geometry-Guided Semantic Elevation Mapping for Autonomous Excavation<br><a href='http://arxiv.org/pdf/2609.34719'>论文</a></td><td>ExcavaTwin提出一种纯视觉、无需挖掘专用训练、几何引导的语义高程建图框架。给定多视角RGB图像，它用冻结视觉模型重建几何与语义观测，并推导地形和非地形几何支撑。
◆ 无需挖掘任务专属训练，直接复用冻结视觉模型完成几何与语义感知。
◆ 利用地形与非地形几何支撑约束多视角语义融合，抑制不合理预测并补全缺失观测。
◆ 将融合状态投影为面向任务的语义高程图，联合表达地形几何与任务相关语义。
在公开数据集和真实挖掘场景中验证了可靠性，真实系统平均更新间隔约1.4秒，动态修改区域平均高程误差12.74厘米，较大误差主要来自地形快速变化和机器运动造成的瞬态视觉干扰。</td></tr>
<tr><td>2026-09-27</td><td>TC-ADA: One-Shot Active Domain Adaptation for Semantic Segmentation<br><a href='http://arxiv.org/pdf/2609.33432'>论文</a> | <a href='https://github.com/ywher/TC-ADA'>代码</a></td><td>本文研究语义分割中标签高效的主动域适应，提出实用的单轮图像级设定：一次性选取并密集标注固定目标子集，随后连续适配。为此提出TC-ADA，将整图主动采集与目标校准适配进行联合设计。
◆ 采用单轮图像级主动选择，避免传统多轮采集、标注和重训练流程。
◆ 第一阶段融合视觉基础模型的视觉表示与固定无监督域适应模型的语义预测，在无目标标注下选择兼具代表性和信息量的目标图像。
◆ 第二阶段联合利用有标注源数据、有标注目标数据和剩余无标注目标数据，并在目标标签有限时校准源域与目标域监督。
在五个合成到真实及真实到真实驾驶迁移中，TC-ADA持续优于代表性主动域适应基线。
仅用23至46张标注目标图像（Mapillary为140张），其mIoU与目标域全监督仅差1.9个百分点。</td></tr>
<tr><td>2026-09-27</td><td>AevaScenes: An FMCW LiDAR Dataset and Benchmark for Long-Range Perception<br><a href='http://arxiv.org/pdf/2609.33230'>论文</a></td><td>◆ 本文提出AevaScenes，一个面向长距离感知的FMCW LiDAR数据集与基准。
◆ 数据集包含575个序列、5.75万帧、超800万个3D框，覆盖16类检测目标和24类逐点语义，由六台商用FMCW LiDAR和六台4K相机在八个湾区城市采集，含237个夜间序列，标注延伸至400米。
◆ 基准定义3D目标检测、场景流估计和语义分割三项任务，其中检测与场景流按三个距离区间评估至400米，并提供公开评测服务器。
◆ 研究发现逐点径向Doppler速度为长距离感知提供关键运动线索，使远距离车辆和行人检测AP最高提升2倍，低延迟单帧设置下尤为显著。
◆ 研究还表明Doppler测量在所有距离区间显著提升场景流精度，并已公开数据集与基准以推动后续研究。</td></tr>
<tr><td>2026-09-26</td><td>Toward On-Chip Training of Spiking Neural Networks for Dense Event-Based Vision<br><a href='http://arxiv.org/pdf/2609.32405'>论文</a></td><td>论文提出DELL，一种面向密集事件视觉的逐块局部学习方案，用局部稠密监督替代BPTT的全局梯度传播，以降低脉冲神经网络训练内存并适配片上训练。
◆ 用可学习、空间结构化的局部头对每个块在其合适分辨率进行监督，同时保留块内时序动态。
◆ 将局部学习从分类扩展到光流回归和语义分割，并采用全脉冲U形架构验证。
◆ 在DSEC光流上，DELL比端到端BPTT降低39.6%峰值训练内存，并把EPE从1.941 px改善到1.670 px。
◆ 相比DECOLLE固定随机局部读出，可学习局部头使光流EPE约为其1/3.9，并全面超越端到端训练；分割上恢复大部分差距但仍略低。
◆ 以2.3M参数、较最强SNN基线少24倍，仍保持竞争性，表明块分离更像正则化而非限制。</td></tr>
<tr><td>2026-09-23</td><td>Privacy-Preserving Semantic Segmentation from High-Resolution Depth and Ultra-Low-Resolution RGB<br><a href='http://arxiv.org/pdf/2609.28360'>论文</a></td><td>本文针对移动机器人摄像头隐私风险，提出高分辨率深度与超低分辨率RGB相结合的非对称隐私保护感知设定，在保留密集几何的同时限制细粒度外观，从源头降低视觉隐私暴露。
◆ 提出HR深度与ULR RGB的非对称传感范式，在几何可用性与隐私保护之间取得平衡。
◆ 设计HR几何引导的联合2D框架，同时进行语义导向RGB重建和RGB-D分割，缓解模态信息失衡。
◆ 构建端到端2D到3D分割流程，整合2D语义特征以提升场景级3D理解一致性。
◆ 通过隐私可恢复性分析、跨数据集零样本迁移和真机object-goal navigation验证隐私、泛化与实用性。
在ScanNet上，该方法取得隐私保护方法中最佳2D和3D分割性能，并最强零样本迁移至SUN RGB-D与SceneNN。</td></tr>
<tr><td>2026-09-23</td><td>NaviScale: Generating Large-Scale Semantic Map Datasets for Object Navigation<br><a href='http://arxiv.org/pdf/2609.27218'>论文</a></td><td>NaviScale提出面向语义地图ObjectNav的大规模数据生成框架，预测器仅需部分与完整语义地图配对训练，无需为每个样本重建完整3D环境。
◆ 组合真实住宅平面图与MP3D、HM3DSem的房间级语义和障碍地图，低成本生成大规模多样化语义地图数据。
◆ 房间间缩放改变平面图结构，提升平面图级布局多样性。
◆ 房间内缩放按房间类别匹配不同房间地图，填充同一固定平面图以增加房间组合多样性。
◆ VisRC通过射线投射将组合地图转为部分观测，并显式考虑视场、感知范围和遮挡。
生成192,000张语义地图、24,000个平面图和12,794处房产；在HM3D达64.3% SR/34.8% SPL，MP3D达43.1% SR/16.8% SPL，且不改变预测架构，并验证地图质量、语义分割误差和实机部署。</td></tr>
<tr><td>2026-09-22</td><td>SparseNav: Instruction-conditioned Sparse Semantic Perception for Training-Free Vision-Language Navigation<br><a href='http://arxiv.org/pdf/2609.26408'>论文</a></td><td>SparseNav提出一种免训练、指令条件下的稀疏语义感知框架，用于视觉语言导航，遵循“少即是多”原则。它仅持续维护轻量级几何BEV地图和稀疏地标记忆，并按需获取语义，避免无关对象累积带来的计算浪费和表示干扰。
◆ 通过指令管理器跟踪导航进度并识别当前活跃的地标查询，实现以子指令决定什么值得定位。
◆ 采用指令条件感知机制，仅在查询地标可见且其度量位置能影响下一步决策时，才调用开放词汇分割。
◆ 地标记忆支持VLM在混合前沿与局部方向路点候选中进行选择，无需额外训练。
在R2R-CE和RxR-CE Val-Unseen上分别达到42.8%和40.7%成功率，并成功部署于Unitree Go2四足机器人，在无预建地图的多种室内环境中验证有效。</td></tr>
<tr><td>2026-09-21</td><td>Impact of Data Compression on Downstream AI Tasks: A Study using Teleoperated Driving over 5G<br><a href='http://arxiv.org/pdf/2609.25290'>论文</a></td><td>本文研究5G远程驾驶中传感器数据压缩对边缘或云端下游AI任务性能的影响。作者以目标识别和语义分割为例，覆盖视频、LiDAR单模态及视频加LiDAR多模态，分析压缩对AI性能的作用。结果显示，有损压缩通常降低AI任务性能，且敏感度因数据源类型和压缩程度而异，并可为多模态视觉任务找到经验最优权衡点。
◆ 系统量化传感器压缩对远程驾驶下游AI任务的影响，连接通信约束与安全告警。
◆ 联合比较视频、LiDAR及多模态数据，揭示不同数据源对压缩的差异化敏感度。
◆ 为多模态视觉任务识别出压缩率与AI性能的经验最优权衡点，支撑远程驾驶压缩策略。</td></tr>
<tr><td>2026-09-20</td><td>Which Terrain Is Better? Preference Learning with VLM Prototypes for Off-Road Traversability Ranking<br><a href='http://arxiv.org/pdf/2609.23673'>论文</a></td><td>论文将越野可通行性从语义类别或freespace置信度转为视觉可通行性排序，用区域比较监督偏好方向。
◆ 提出TravPro，把标准标注转化为有序区域对，并在冻结视觉语言模型的patch token上训练小型读出器。
◆ 将VLM token一次性聚类为固定原型库，让读出器为每个原型学习偏好分数。
◆ 以读出器为教师，把稀疏比较生成密集偏好伪标签，并蒸馏到RGB学生，同时学习非地面掩码排除障碍和背景。
在五个未见域上，TravPro平均成对准确率达0.915，最强基线为0.783，能产生对表面条件敏感而按类赋值无法表达的排序。
同一VLM和同一监督若仅用提示或当作密集目标并不能得到该排序，关键在如何使用。</td></tr>
<tr><td>2026-09-18</td><td>AgenticSwarm: Semantic Perception and Adaptive Task Allocation for Heterogeneous Multi-UAV Missions<br><a href='http://arxiv.org/pdf/2609.21716'>论文</a></td><td>AgenticSwarm提出面向异构多无人机任务的智能体框架，将语义感知、约束任务分配与自适应执行统一起来。
◆它用智能体解析航拍图像和自然语言指令，构建连接感知对象、区域、任务需求、能力约束与任务依赖的落地任务表示。
◆它在分配前纳入障碍感知路径可行性、能耗和保护返航要求，实现受约束的可行任务分配。
◆它在无人机故障、电池退化或任务变更时，从当前系统状态重建剩余任务，同时保留已完成工作和侦察进度。
◆它采用SAM3感知管线，相比Grounding DINO+SAM2.1，类感知召回提高25.2个百分点，语义标签准确率提高29.5个百分点，并在五个Gazebo环境和室内真实环境验证。
消融显示，残差任务重规划使平均重复工作从0%升至61.7%，事件后恢复时间增加58.6%。</td></tr>
<tr><td>2026-09-18</td><td>PerSeM: Persistent Semantic Memory for Long-Horizon Open-Vocabulary UAV Mapping<br><a href='http://arxiv.org/pdf/2609.19542'>论文</a></td><td>PerSeM是一种免训练的持久语义记忆框架，面向长时程开放词汇无人机建图，旨在解决逐帧语义预测在重复观测和视角变化下的时序不一致问题。
◆将逐帧开放词汇语义观测关联到持久世界空间体素，并通过多数投票构建世界一致的语义记忆。
◆提出历史保留空间细化、信任感知回放与上下文引导验证，对不确定记忆进行保守精炼，避免错误固化。
◆在Forest和UAVScenes上，持久3D记忆相较逐帧预测显著提升语义正确性与时序稳定性。
◆作为强持久记忆基线，PerSeM在全部五个UAVScenes序列上仍取得一致额外提升，且无需重训练或额外神经网络推理。
◆独立区域分析显示，增益集中于语义困难且时序不稳定区域，说明保守精炼对不确定记忆尤其有效。</td></tr>
<tr><td>2026-09-17</td><td>PAANI : On Device Visual Evidence Fusion and Explainable Guidance for River Robot Simulation<br><a href='http://arxiv.org/pdf/2609.22353'>论文</a></td><td>PAANI提出一种在资源受限Arduino UNO Q上运行的端侧感知到制导架构，用于河流机器人模拟中融合视觉证据并生成可解释引导。
◆将项目训练的YOLO11n检测器与定制MobileNetV3 Small语义分割器按时间戳对齐融合，并用有界跟踪维持目标连续性。
◆设计显式走廊策略，综合水面标签、接受检测、紧迫度与掩码不确定性，且每条最终建议都公开其证据和政策理由。
◆通过ROS 2把本地AI管线接入独立Gazebo船体、定位与控制测试台，形成可复用边缘机器人基础。
训练与评估使用WaterScenes 10000张四类检测和MaSTr1325 1127张分割图像，ONNX模型共14.817 MB，检测mAP@0.5为0.7388/0.7367，分割mIoU为0.9750。
五分钟UNO Q录制在0.5 Hz下中位和95分位延迟为467.8 ms与580.3 ms，同时发现黑输入误分类和采样率不匹配问题；结果区分了模型精度、板载执行与已验证的水上避碰。</td></tr>
<tr><td>2026-09-16</td><td>4D Radar Perception Algorithms for Autonomous Driving: A Review<br><a href='http://arxiv.org/pdf/2609.19216'>论文</a></td><td>本文系统综述面向自动驾驶的4D毫米波雷达感知算法，按感知任务与算法演进梳理领域发展。
◆ 提出以任务演进为主线，从信号处理、目标检测延伸到语义分割、运动估计、占据预测和动态场景重建。
◆ 系统比较仅雷达学习、多模态融合、跨模态监督与知识蒸馏三类范式。
◆ 重点分析高度、多普勒测量和雷达物理先验在不同感知任务中的利用方式。
◆ 汇总现有数据集的任务覆盖、输入数据、标注与评估协议，明确各方向的经验支撑。
◆ 给出从稀疏目标感知走向动态空间理解的任务导向视角，并总结挑战与未来方向。</td></tr>
<tr><td>2026-09-11</td><td>CoralscapesV2: Panoptic and Fine-Grained Visual Scene Understanding in Coral Reefs<br><a href='http://arxiv.org/pdf/2609.12826'>论文</a></td><td>CoralscapesV2是面向珊瑚礁通用视觉场景理解的数据集扩展，旨在支持大规模生态监测与保护。该数据集扩大了规模、范围和标签完整性与质量，并将语义分割类别从39类扩展到95个细粒度类别。
◆ 将珊瑚礁语义分割类别从39类扩展到95个细粒度视觉类别。
◆ 提供约6.5万条鱼类实例掩码标注，并借助视频确保标注完整性，揭示仅用静态图像标注鱼类不足。
◆ 构建首个珊瑚礁全景分割数据集，覆盖多种野外场景，形成具挑战性的语义与实例分割基准。
它推动珊瑚礁通用全景分割，可用于底栖覆盖制图、鱼类行为与鱼礁互动自动量化理解，助力珊瑚礁监测规模化。</td></tr>
<tr><td>2026-09-09</td><td>CLFTv2: Efficient Camera-LiDAR Fusion for Semantic Segmentation via Hierarchical Feature Pyramids<br><a href='http://arxiv.org/pdf/2609.09881'>论文</a></td><td>CLFTv2提出一种面向自动驾驶语义分割的高效相机-LiDAR分层融合框架，旨在提升弱势道路使用者召回并缓解类别不平衡。
◆ 以Swin多尺度编码器替代全局ViT注意力，利用移位窗口注意力在多尺度上提取几何线索。
◆ 采用轻量FPN式残差解码器，在2D透视域进行逐尺度残差融合，避免查询匹配解码器的高计算开销。
◆ 通过模态隔离研究指出，ViT全局感受野仅在LiDAR返回密集时带来更强融合增益。
在ZOD、Waymo等三个驾驶数据集上，CLFTv2-Large于ZOD达53.5% mIoU，行人IoU由35.5%升至44.9%，Waymo达61.7% mIoU；相比基于Swin的Mask2Former适配，所需GFLOPs约少29%，吞吐量高2.2倍且总体精度相当。
这些结果表明，分层局部注意力融合是实时车载感知中替代全局注意力和查询式解码器的可扩展高效方案，代码已公开。</td></tr>
</tbody>
</table>
</div>

<h2 id='robot-vpr'>Robot VPR</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-28</td><td>MarsLab: A Martian Rover Simulator for Planetary Rover Autonomous Navigation<br><a href='http://arxiv.org/pdf/2609.34702'>论文</a> | <a href='https://kimhoyun-robotair.github.io/MarsLab/'>代码</a></td><td>MarsLab是面向火星车自主导航的开源ROS2原生模拟器，用于在部署前研究非结构化地形、光照变化、大气尘埃和通信受限等条件。  
◆ 它将HiRISE衍生地形与程序化地形结合，并支持岩石、陨石坑、太阳光照和大气尘埃等参数化定制。  
◆ 它在NVIDIA Isaac Sim中运行毅力号级火星车，并通过标准ROS2话题发布RGB、深度、RGB-D点云、LiDAR、IMU、轮式里程计和GT位姿。  
◆ 它提供统一SLAM基准，覆盖不同传感模态、尘埃水平、场景几何和路线长度。  
◆ 它提供VPR基准，在重复火星基地遍历中考察光照与尘埃变化下的地点识别。  
最后，它用共享GT轨迹在同一模拟器中比较轨迹级估计与图像级地点识别，并开源项目页面。</td></tr>
<tr><td>2026-09-23</td><td>Geometry-Conditioned Visual Place Recognition in Natural Environments<br><a href='http://arxiv.org/pdf/2609.27370'>论文</a></td><td>本文提出面向自然环境的视觉地点识别方法，利用几何结构比视觉外观更持久的特性，应对重复植被、稀疏地标和显著视角变化。
◆ 提出Depth-Aware Distillation，用几何基础模型推断几何并条件化视觉基础模型的token表示，且无需深度传感器。
◆ 不把几何作为额外输入模态，而是将图像对齐深度投影到VFM token空间，通过通道式几何条件调制视觉表示。
◆ 设计两阶段教师引导学习，先将几何条件表示锚定到预训练外观空间，再精炼以增强地点判别能力。
在WildCross基准上，DAD将平均跨序列Recall@1从61.41%提升至66.37%，Recall@5从65.86%提升至72.49%，逆序和长期外观变化下增益最大。
结果表明，GFM派生几何能在外观不可靠时为VPR提供持久的结构先验。</td></tr>
<tr><td>2026-09-22</td><td>TM-APR: Thermal Temporal-Memory Localization via Analytic Online Adaptation<br><a href='http://arxiv.org/pdf/2609.26766'>论文</a></td><td>本文提出TM-APR，面向热视觉位置识别实现鲁棒域不变地点识别与在线自适应定位。
◆ 首次将解析类增量学习ACIL与域不变VPR结合，发现无梯度矩阵更新可构成优于传统微调的强基线。
◆ 建立ACIL与现代控制理论的代数等价关系，突破其线性假设对极端非线性热波动的脆弱性。
◆ 将无迹传播U-ACIL、高斯混合划分GMM-ACIL与极小极大H∞优化H∞-ACIL直接嵌入ACIL更新循环。
◆ 保证O(1)闭式矩阵更新并绕过反向传播，使在线学习延迟严格低于传感器采集间隔。
该框架消除实时SLAM轨迹跳变，为热VPR在线部署提供高效、鲁棒的新范式。</td></tr>
<tr><td>2026-09-22</td><td>Route-MHT: Multimodal Transformer Guardrails for Thermal Visual Place Recognition<br><a href='http://arxiv.org/pdf/2607.04745'>论文</a></td><td>本文针对热红外视觉位置识别（TIR-VPR）在分布外条件下产生的过度自信强制匹配失败问题，提出了一种名为轨迹锚定优化（TAO）的新型后端处理方法。TAO将传统多假设跟踪（MHT）中指数级复杂度的并行轨迹评估问题，转化为批量化SE(2) Procrustes对齐问题，通过张量级向量化与单次调用的批量SVD计算，绕开动态树扩展过程，实现了严格的每帧O(KN)实时性能。在零泄漏评估协议下，论文揭示了一个关键发现：在5米以下的微观尺度，由于局部视觉歧义性，被动几何后端无法数学分离度量定位误差与连贯性幻觉；而在宏观尺度上，K=100条分散假设会打破滑动窗口内的刚性时序共视约束，使联合优化残差急剧上升。TAO由此构建了一个10米的宏观收敛盆地，能够可靠地隔离灾难性拓扑断裂并抑制关键误接受。

◆ 提出TAO框架，将多假设跟踪的组合爆炸问题转化为批量化SE(2) Procrustes对齐，实现O(KN)严格实时的每帧执行复杂度。
◆ 揭示了5米微观尺度下几何一致性的固有盲区，明确界定10米宏观收敛盆地为幻觉检测的有效工作区间。
◆ 在零泄漏评估协议下，证明了多视图几何一致性可作为高效的失效安全滤波器，有效抑制过自信的误匹配。</td></tr>
<tr><td>2026-09-18</td><td>Multi-viewpoint Geo-localization with Event Cameras<br><a href='http://arxiv.org/pdf/2609.21219'>论文</a> | <a href='https://github.com/AdamDHines/megaevent'>代码</a></td><td>本文提出MegaEvent，一个面向多视角变化的事件相机视觉位置识别系统，旨在解决事件定位器视角鲁棒性不足与相关数据集稀缺问题。
◆ 将五个大规模带地理标签的帧式定位数据集通过Image-to-Event转换为合成事件流，用于预训练事件ViT骨干的微调。
◆ 采用多损失函数训练，使MegaEvent学习对视角变化鲁棒的场所识别特征。
◆ 提出Springfield-Event-VPR数据集，包含3.7km步行路线、三种相机朝向，总计11.1km，用于挑战多视角定位。
◆ 在三个事件定位数据集上取得平均82% Recall@1，领先次优事件方法20个召回点，并优于帧式VPR直接用于事件帧8至26个召回点；在新数据集上领先最强基线9个召回点。
代码已开源。</td></tr>
<tr><td>2026-09-15</td><td>HuMemSLAM: Efficient Human-Inspired Semantic Place Recognition for Robust Visual SLAM<br><a href='http://arxiv.org/pdf/2609.17168'>论文</a></td><td>本文提出 HuMemSLAM，将受人类记忆与感知启发的语义地点识别方法 HuMem-VPR 集成到 ORB-SLAM3，以增强视觉 SLAM 在感知歧义和感知变化下的鲁棒性。
◆ 提出 HuMem-VPR，利用自下而上感知证据与自上而下上下文推理的双向关系，实现高层地点理解。
◆ 将 HuMem-VPR 与 ORB-SLAM3 结合为 HuMemSLAM，面向实时部署同时追求高检索精度和低延迟。
◆ 在真实图像基准上取得最高聚合检索精度，在 CARLA 基准上保持竞争力，延迟约为所评估 SOTA VPR 方法的二到三分之一。
◆ 在多个数据集族和在线实验中，HuMemSLAM 较 ORB-SLAM3 原生检索显著提升 integrated Recall@1，并减少提交给几何后端的候选提议。
总体而言，该方法在鲁棒性、精度与效率之间取得了良好平衡。</td></tr>
<tr><td>2026-09-05</td><td>From Multi-Fisheye Sensing to Panoramic Perception: A Parallax-Aware Onboard Platform for Ultra-Low-Altitude UAVs<br><a href='http://arxiv.org/pdf/2609.02319'>论文</a> | <a href='https://github.com/DUNDAI1998/parallax-aware-uav-panorama.git'>代码</a></td><td>该论文针对超低空无人机在复杂近场环境下的全景感知需求,提出了一套从多鱼眼采集到视差感知全景重建的端到端机载平台,集成定制碳纤维机身、四个同步鱼眼相机、NVIDIA Jetson Orin NX 计算单元以及 GNSS 接收器,可在板上将四路鱼眼流融合为统一的 1280×640 等距柱状全景(ERP)接口。其核心方法是一种视差感知的全景生成流水线,为每个重叠区按内容自适应地选择投影深度,并结合受控拼接缝与光度融合,在精度与部署两个层面提供差异化配置。在基于 18 组野外序列、超过五万组四视图样本的评测中,精度配置相较固定深度将远场 P90 特征错位降低 41.6%,部署配置在 20 Hz 节奏下以 13.29 W 平均功耗稳定运行于 19.99 fps,八扇区 ERP 采样下白天视觉位置识别 Recall@5 达 90.8%。

主要创新点如下:

◆ 视差感知全景生成流水线,按重叠区域逐块选择投影深度并联合优化拼接缝与光度融合,以缓解近距离视差造成的伪影与错位。

◆ 双配置架构:精度配置引入内容自适应拼接缝搜索与验证门控残差网格;部署配置采用裕度门控的逐缝更新以满足传感器级实时运行。

◆ 一体化机载硬件平台,碳纤维机身同步集成多鱼眼感知、嵌入式计算与飞控/GNSS,实现板上面向超低空场景的全景输出。

◆ 开放的标准化 ERP 视觉接口,便于下游任务(如视觉位置识别)直接复用,无需针对鱼眼布局做定制开发。</td></tr>
<tr><td>2026-08-24</td><td>FlatVPR: Plug-and-play Geo-linear Residual Adapter for Geometric Rectification of Foundation Model Feature Manifolds<br><a href='http://arxiv.org/pdf/2606.01734'>论文</a></td><td>本文提出FlatVPR，一种即插即用的几何线性残差适配器，用于解决视觉位置识别中地图轻量化与定位精度的矛盾。研究发现DINOv2等基础模型的特征流形存在显著曲率，物理空间的均匀线性运动在特征空间映射为非线性轨迹，限制了稀疏锚点条件下的可靠重建。

◆ 设计基于残差变换的轻量化适配器Res(·)，对基础特征进行几何校正，无需重新训练整个基础模型即可即插即用。

◆ 提出Pullback Flatness Loss（拉回平坦损失），通过最小化中间特征与相邻锚点连线之间的偏差，显式抑制流形的内蕴曲率。

◆ 利用相邻锚点间的线性插值重建伪描述符，使任意中间位置特征可被几何一致地近似表示。

◆ 构建EM框架，将建图过程解耦为连续的M步（流形自适应）与概念性的E步（最优锚点选择准则）。

◆ 在NCLT数据集的100米超稀疏锚点间隔及极端季节变化场景下均实现显著的定位性能提升。</td></tr>
<tr><td>2026-08-07</td><td>Are Visual Place Recognition Models Recognizing Places or Conditions? Distractor-Augmented Evaluation and Condition Suppression<br><a href='http://arxiv.org/pdf/2608.06847'>论文</a></td><td>这篇论文针对长期视觉位置识别（VPR）中的关键问题展开研究，指出当前VPR方法在匹配过程中容易受光照、天气、季节等条件信息干扰，可能依据条件相似性而非地点身份进行检索。

◆ 提出Distractor-Augmented Recall（DAR）评估指标，通过向数据库注入干扰图像来分离和量化干扰物的影响，揭示现有方法在标准Recall@1下的排名与DAR@1排名存在显著差异。

◆ 提出对VPR描述子进行条件抑制，采用INLP和LEACE方法去除描述子中编码的照明、天气、季节等条件信息。

◆ 在11种VPR方法和6个数据集上的实验表明，条件抑制普遍提升DAR@1性能而不降低标准R@1，证实抗干扰鲁棒性与标准检索性能是相互独立的维度。

该研究的核心贡献在于揭示了VPR模型&quot;识别地点还是识别条件&quot;这一被忽视的问题，为构建更鲁棒的VPR系统提供了新的评估框架和解决方案。</td></tr>
<tr><td>2026-08-06</td><td>Topometric Autonomous Vehicle Localization by Combining Visual Embeddings and Feed-Forward 3D Models<br><a href='http://arxiv.org/pdf/2608.06021'>论文</a></td><td>本文针对自动驾驶视觉定位中地图紧凑性与度量精度的矛盾，提出了一种结合视觉地点识别（VPR）与前馈神经3D几何（FF3D）模型的拓扑度量定位框架。该方法通过粒子滤波器将概率性VPR的全局识别能力与FF3D的局部度量位姿估计相融合，在受控图像集上迭代更新位姿估计，显著提升了外观变化下的定位鲁棒性。

主要创新点如下：

◆ 提出一种将低维图像嵌入的视觉地点识别与前馈神经3D几何度量位姿估计相结合的拓扑度量定位框架，有效兼顾地图紧凑性与度量精度。

◆ 设计了自动离线建图工具，建模场景不同区域中的拓扑-度量位姿与外观交互关系，为在线定位提供先验支撑。

◆ 采用在线粒子滤波器融合里程计与位置置信度，将神经度量估计自然嵌入概率外观定位流程。

◆ 框架具有模块化特性，描述子提取器与FF3D模型可灵活替换，适配不同场景需求。

◆ 通过连续序列置信传播缓解了感知混淆导致的严重定位失败问题。

在三个公开基准上的大量实验表明，该方法相比现有外观定位方法取得了显著性能提升。</td></tr>
<tr><td>2026-07-27</td><td>SLAM: Structured and Localized Analytic Manifold Adaptation for Forgetting-Immune and Domain-Robust Lifelong VPR<br><a href='http://arxiv.org/pdf/2607.04764'>论文</a></td><td>这篇论文针对终身视觉位置识别中ACIL方法对非线性域偏移脆弱的问题，提出名为SLAM的控制论框架。其关键洞见在于揭示了递归ACIL更新与扩展卡尔曼滤波协方差传播之间的代数同构，从而将控制论工具引入增量学习领域。

◆ 提出ACIL-D域概念，构建自相关状态锁定的不变特征流形，作为域适应的规范化空间。

◆ 设计解耦域对齐D-DA，将潜在特征分离为ACIL-D内不变语义与变体风格向量。

◆ 集成动态温度缩放GMM定位拓扑非线性，并采用Unscented扰动传播抑制特征波动。

◆ 引入minimax H∞鲁棒准则约束最坏情况噪声累积。

在NCLT非平稳数据集上以完全无遗忘为前提达到27.7%全类准确率，显著超越现有基线。</td></tr>
<tr><td>2026-07-15</td><td>Visual Place Recognition Using Rate-Encoded Spiking Neural Networks with Discrete STDP Learning<br><a href='http://arxiv.org/pdf/2607.13584'>论文</a></td><td>该论文针对基于STDP的无监督脉冲神经网络在视觉位置识别中召回率不足的难题，提出了一套基于PyTorch与snnTorch的离散化张量化实现方案，并在100地点的Nordland数据集上以15个独立训练网络进行系统评估。

其核心创新点如下：
◆ 采用闭式确定性张量管道替代传统argmax进行神经元分配，显著提升了R@100P指标
◆ 揭示了查询后状态重置机制可独立改善召回精度，且与神经元分配方式解耦
◆ 提出速度补偿的滑动窗口聚合策略，在k=5时即达到R@100P=100.00%，仅引入0.20毫秒额外延迟

不过作者也坦承，各机制的独立贡献以及与先前连续时间模型之间的实现差异尚未完全厘清，仍需后续深入探究。</td></tr>
<tr><td>2026-07-15</td><td>Breaking Déjà Vu: Independent Auditing of Visual Place Recognition through Vision-Language Reasoning<br><a href='http://arxiv.org/pdf/2607.12818'>论文</a></td><td>本文针对视觉位置识别(VPR)在实际部署中依赖固定图像匹配阈值、难以应对环境变化的问题，提出了视觉位置识别审计(Visual Place Recognition Auditing)框架。该方法利用视觉语言模型(VLM)在检索后对查询图像和候选图像进行联合推理，实现独立于特定架构的实例级验证。核心创新包括：◆ 提出了一种独立于VPR架构的事后审计验证框架，无需数据集相关的阈值或部署环境的先验知识。◆ 利用视觉语言模型对查询与候选图像进行联合推理，实现跨环境的鲁棒验证。◆ 在六个基准数据集和五种先进VPR方法上验证，平均将recall@1提升13.6%，同时将误接受率降至12%，保持精度高于95%、覆盖率高于75%。该工作为安全关键机器人系统中环路闭合检测的可靠性提供了新的解决方案。</td></tr>
<tr><td>2026-07-07</td><td>From Open Waters to Enclosed Cabins: ProteusVPR for Cross-Scene Visual Place Recognition in Maritime Perception and Cabin Inspection<br><a href='http://arxiv.org/pdf/2606.24234'>论文</a></td><td>本文针对海上机器人巡检中开放甲板与封闭舱室之间跨场景视觉位置识别的难题，提出ProteusVPR两阶段检索-精修框架。该方法通过几何-视觉估计网络融合时序多帧信息，引入局部仿射坐标系和相机方位角编码实现精确定位。

◆ 提出ProteusVPR两阶段框架，第一阶段使用标准VPR模型完成初步检索，第二阶段利用融合检索图像与两帧时序前帧的几何-视觉估计网络进行精修。
◆ 设计局部仿射坐标系与相机方位角编码机制，增强跨场景几何一致性表达与定位鲁棒性。
◆ 构建XHZ船舶全景数据集（8K图像），涵盖多层舱室结构与甲板过渡区域，并采用严格查询-数据库分离的评估协议。
◆ 实验证明该方法在多种VPR骨干网络上将平均定位误差降低超过60%，在跨场景海事环境中表现出有效性与鲁棒性。</td></tr>
<tr><td>2026-06-14</td><td>VL2Spike: Spike-driven Distillation from VLMs for Low-Power Visual Perception in Embodied AI<br><a href='http://arxiv.org/pdf/2606.15898'>论文</a></td><td>本文提出VL2Spike，一种新颖的脉冲驱动知识蒸馏框架，旨在将视觉语言模型（VLM）的多模态知识迁移到紧凑的Spikformer模型中，在保留脉冲神经网络能效优势的同时显著提升其视觉感知能力，为低功耗机器人感知提供了实用路径。

◆空间-时间视觉脉冲（SVS）蒸馏：实现VLM图像特征与脉冲token的共享流形对齐，并在膜电位和脉冲率上构建热启动的时间一致性机制。

◆脉冲原型引导的语言（SPL）蒸馏：将Spikformer的类别原型与logits与VLM的可提示文本嵌入对齐，实现跨模态语义知识的有效迁移。

实验结果表明，VL2Spike在三个静态数据集上取得6.81%的性能提升，能耗仅为原来的15.7%，并在机器人视觉位置识别任务中实现6.63%的增益，展现出优异的泛化能力与应用潜力。</td></tr>
</tbody>
</table>
</div>

<h2 id='archive'>归档</h2>

> [点击查看所有历史论文归档](./docs/archive.md)


<h2>GitHub 实验室仓库监控</h2>

<h3>HKU-MARS (港大火星实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5228</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4693</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2460</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1645</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1621</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1518</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1342</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1302</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1088</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>1049</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>943</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>810</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>784</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>747</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>743</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>727</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>687</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>667</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>632</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>621</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>611</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>583</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>571</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>534</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>510</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>463</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>457</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>365</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>349</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>278</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>272</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>258</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>242</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>229</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>223</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>212</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>207</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>149</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>146</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>121</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2876</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1673</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1368</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1096</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1059</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>882</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>711</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>668</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>666</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>625</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>604</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>578</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>572</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>571</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>555</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>519</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>510</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>465</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>456</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>452</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>335</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>313</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>312</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>301</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>287</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>279</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>258</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>224</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>208</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>202</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>186</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>177</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>170</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>169</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>160</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>156</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>142</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>139</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/data-driven-dynamics'>data-driven-dynamics</a></td><td>134</td><td>Data Driven Dynamics Modeling for Aerial Vehicles</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>132</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
<tr><td><a href='https://github.com/ethz-asl/phaser'>phaser</a></td><td>132</td><td>A robust pointcloud registration pipeline based on</td></tr>
<tr><td><a href='https://github.com/ethz-asl/ssc_exploration'>ssc_exploration</a></td><td>112</td><td>Incremental 3D Scene Completion for Safe and Effic</td></tr>
<tr><td><a href='https://github.com/ethz-asl/active_grasp'>active_grasp</a></td><td>109</td><td>Closed-loop next-best view planning for grasp dete</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waypoint_navigator'>waypoint_navigator</a></td><td>108</td><td>Stand-alone waypoint navigator</td></tr>
<tr><td><a href='https://github.com/ethz-asl/reinmav-gym'>reinmav-gym</a></td><td>107</td><td>Reinforcement Learning framework for MAVs using th</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waverider'>waverider</a></td><td>106</td><td>RMPs on multi-resolution occupancy maps for effici</td></tr>
<tr><td><a href='https://github.com/ethz-asl/navrep'>navrep</a></td><td>106</td><td>navrep</td></tr>
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>104</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/eth_supermegabot'>eth_supermegabot</a></td><td>102</td><td>Instructions for ETH center for robotics summer sc</td></tr>
<tr><td><a href='https://github.com/ethz-asl/3d_vsg'>3d_vsg</a></td><td>102</td><td>3D可变场景图，用于长期语义场景变化预测。</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.09.29
