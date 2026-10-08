# 计算机视觉领域最新论文 (2026.10.08)

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
<tr><td>2026-10-07</td><td>Argos: Adapt Rich Geometric Priors for Generalizable Online Scene-Change-Detection<br><a href='http://arxiv.org/pdf/2610.10181'>论文</a></td><td>Argos针对动态环境中的在线场景变化检测，指出2D成对图像特征在视角变化、遮挡、噪声和跨域泛化上受限，而显式3D方法常需昂贵离线优化。该工作利用几何基础模型的隐式3D知识，将GFM特征适配到变化检测与3D重建联合任务中。
◆ 提出Argos框架，借助丰富几何先验实现可泛化的联合场景变化检测与3D重建。
◆ 构建大规模基准，包含两个合成数据集和一个真实数据集，并通过跨数据集联合训练提升跨域泛化。
◆ 提出Argos-SLAM，面向机器人实时应用，支持在线变化检测和变化感知4D建图。
在多个基准上，Argos显著优于现有基线，变化IoU最高提升42.01%，F1最高提升27.91%，并支持真实变化环境中的可扩展部署。</td></tr>
<tr><td>2026-10-07</td><td>Towards Accurate End-Effector Localization for UMI-Style Robotic Manipulation Teaching<br><a href='http://arxiv.org/pdf/2610.09857'>论文</a></td><td>本文针对UMI风格机器人示教中近距操作与遮挡下末端定位精度和时序完整性问题，提出MILD数据集与AprilVINS定位框架。
◆ 构建MILD真实与仿真数据集，含86条Insta360 X5/Insight9序列、15类重复桌面任务、标定资产及逐次执行TCP参考轨迹。
◆ 发布MILD-Sim，在Isaac Sim中扩展任务覆盖，支持可控操纵回放研究，并为解释误差量级提供任务相关容差参考。
◆ 提出AprilVINS，将鱼眼视觉惯性估计与序列局部AprilTag几何结合，无需预勘测标定图，并分离先验准入与联合优化状态的受保护导出。
◆ 在统一协议下实现毫米级SE(3)对齐TCP相对APE RMSE和高时间完成率，消融区分定位精度与可导出性。
◆ 建立面向UMI示教采集的诊断性基准框架，揭示现有视觉惯性与标定辅助系统在轨迹误差和时间覆盖上的显著差异。</td></tr>
<tr><td>2026-10-06</td><td>InterCorrect: Intersection-Aware Correction of Demographic Model Merging for Fair ASR<br><a href='http://arxiv.org/pdf/2610.08604'>论文</a></td><td>本文研究面向公平 Speech-LLM ASR 的人口属性感知模型合并，从 SLAM-ASR 出发仅微调 connector，并将人口子集适配的连接器合并为全局模型。
◆ 提出仅微调并合并连接器的人口属性感知模型合并框架，以较低代价提升公平 ASR 的整体与子群表现。
◆ 引入交叉人口属性视角，利用子群 WER 与任务向量冲突识别关键交叉人口对。
◆ 设计交叉特定校正向量，对全局合并模型进行交叉群体校正，缓解多属性交叉下的性能不均。
◆ 在 Fair-Speech 上验证，基于 WER 校正的 TIES 将总体 WER 从 7.38% 降至 5.13%，并在多种合并策略上带来额外增益。
实验还表明，更低平均 WER 并不总意味着更小子群差异，为公平 ASR 评估提供警示。</td></tr>
<tr><td>2026-10-06</td><td>VOMMI: Collecting and Leveraging Portable Demonstrations for Mobile Manipulation<br><a href='http://arxiv.org/pdf/2610.08220'>论文</a></td><td>VOMMI提出一种仅依赖便携RGB演示的移动操作数据收集与学习框架，通过离线轨迹重建和在线视觉-运动条件连接便携演示与VLA后训练。
◆同步身体与手部视角，无需人机运动学校准即可同时捕捉导航上下文和局部物体交互。
◆R2-VO利用稀疏几何锚点精化离线演示轨迹，并生成多预测视野下的因果局部运动token用于在线策略条件。
◆动作组残差适配器仅将这些token注入基础分支，在保持原有能力的同时引入便携运动监督。
实验使用每任务500条便携轨迹、75条用于RGB-VO评估及200条机器人演示参考，仅用便携演示后训练的策略比机器人演示策略底盘速度误差低18.2%，末端平移精度相当。
离线重建使身体和手部流绝对轨迹误差平均降低24.6%，并在三个真实机器人任务上比OpenPI 0.5平均成功率提高8.3个百分点。</td></tr>
<tr><td>2026-10-06</td><td>Image-Space Refraction Correction for Underwater 3D Reconstruction: Warping Flat-Port Views into Pinhole Perspective<br><a href='http://arxiv.org/pdf/2610.07788'>论文</a></td><td>针对平口防水壳消费级相机水下重建中折射引起的碗状变形和度量精度下降问题，本文提出一种图像空间物理折射校正方法。该方法把平口折射视图经光线追踪模型映射为等效针孔透视图像，并与下游算法解耦。  
◆ 在图像空间直接校正主折射畸变，校正结果可直接输入现有SfM、重建与VSLAM流程。  
◆ 基于光线追踪仿真刻画折射畸变，并在两种不同结构真实水下数据集上验证有效性。  
◆ 与常规及折射SfM相比，能消除重建变形、注册更多帧、保持低重投影误差，并泛化到多种重建和VSLAM后端。  
整体上，该工作以即插即用方式提升水下三维重建与导航的度量精度和适用性。</td></tr>
<tr><td>2026-10-05</td><td>RoboCap: A New Platform for Egocentric Robot Learning<br><a href='http://arxiv.org/pdf/2610.07217'>论文</a></td><td>RoboCap面向第一人称操作数据稀缺问题，提出软硬件与3D算法垂直整合的采集平台。硬件为250克六摄像头双IMU帽子，可在野外采集第一人称数据；算法为Grounded API，是设备无关且为RoboCap调优的3D算法套件。
◆ 轻量可穿戴六摄像头双IMU设计，支持自然场景第一人称操作数据采集。
◆ Grounded API实现设备无关的3D算法套件，便于跨设备迁移。
◆ 硬件、标定与3D算法协同优化，在多样场景与设备的SLAM基准上达领先。
◆ 在第一人称深度估计及适配第三方设备的手部跟踪上取得先进表现，并验证厘米级精度与SOTA性能。</td></tr>
<tr><td>2026-10-05</td><td>Stellarators Linking Axisymmetric Mirrors Part 1: Coil Design, MHD Equilibrium, and Physics Metrics<br><a href='http://arxiv.org/pdf/2610.06085'>论文</a></td><td>本文提出SLAM星器-磁镜混合概念，用优化的准等距（QI/OP）星器作为旋转变换源，连接长轴对称圆截面磁镜。
◆ 从DESC omnigenity数据库的OP前体出发，将OP模块线圈沿中平面分开并插入轴对称平面镜线圈，构建nFP=2混合线圈组。
◆ 场线追踪表明，真空嵌套磁面在镜段挤出后仍能存活，且插入处截面形状定性保持。
◆ 利用场线数据映射磁面形状，并用GVEC固定边界求解器计算理想MHD平衡。
◆ 评估新经典输运代理ε_eff、真空磁井W与回旋动理学热流Q，为这类混合构型提供第一性原理分析。</td></tr>
<tr><td>2026-10-05</td><td>Human-in-the-Loop Neuro-Symbolic Drift Anticipation for Reliable Visual SLAM<br><a href='http://arxiv.org/pdf/2610.05757'>论文</a></td><td>本文提出Hybrid DeepSEE（HDS），一种用于视觉SLAM主动漂移预测的人在环神经符号框架，旨在解决数据驱动模型黑箱性强且在分布外环境中易产生物理不一致输出的问题。
◆ 提出人在环神经符号漂移预测范式，将人类上下文融入V-SLAM漂移风险管理。
◆ 融合神经漂移风险估计与符号约束推理，兼顾预测能力与物理一致性。
◆ 以大型语言模型作为推理桥梁，将定性人类知识转化为可解释符号约束。
◆ 构建主动式漂移预测框架，提升视觉SLAM在OOD环境中的可靠性与一致性。
该框架由此实现更可解释、更一致且更可靠的视觉SLAM漂移预测。</td></tr>
<tr><td>2026-10-04</td><td>F$^2$ SLAM: Turning Feed-Forward Geometry into Persistent Factors for SLAM<br><a href='http://arxiv.org/pdf/2610.05207'>论文</a></td><td>针对现有SLAM依赖局部测量易漂移、而前馈3D模型多作为外部几何事后对齐融合的问题，本文提出F2SLAM，将前馈几何直接转化为优化原生的目标权重测量并挂载到持久稠密因子图。
◆ 将前馈几何从外部状态转为持久因子图中的优化原生测量，使多视角证据进入SLAM优化器。
◆ 高频流维持局部跟踪约束与图连通性。
◆ 低频流利用更广多视角上下文，并在状态一致性检查后选择性刷新已有测量。
◆ 两条流通过单一稠密BA共同约束同一组位姿、逆深度和可选相机内参。
多个基准实验表明其轨迹估计与稠密重建稳定提升，未标定配置在Replica上把平均ATE RMSE从最强前馈基线的0.030米降到0.002米。</td></tr>
<tr><td>2026-10-03</td><td>SCCM: Spherically Consistent Coarse Matching for ERP Dense Feature Correspondence<br><a href='http://arxiv.org/pdf/2609.36545'>论文</a></td><td>论文提出SCCM，一种面向ERP全景图像的球面一致粗匹配方法，旨在解决等距柱状投影带来的拓扑、度量和面积三类耦合畸变。
◆ 在粗匹配注意力接口引入球面位置注意力SPA，用偏航周期RoPE建模拓扑，并用切平面偏置校正度量畸变。
◆ 在共可见性门控中引入面积感知共可见性AAC，通过sigmoid前对数面积校正处理面积畸变。
◆ 采用未显式建模球面畸变的朴素粗匹配骨架作为受控参照，将骨架替换效应与球面先验效应分离。
在Matterport3D上，固定粗匹配骨架且精炼器不变时，PCK@1°从0.229提升至0.275。
同一框架还优于ERP原生EDM的0.163和ERP重训RoMa V1的0.198，并可零样本迁移至Stanford2D3D，在Holo360D户外训练后也取得领先。</td></tr>
<tr><td>2026-10-01</td><td>Real-time Event-camera Stereo Visual Odometry via Keytime Gaussian Process Regression<br><a href='http://arxiv.org/pdf/2610.02601'>论文</a></td><td>本文提出一种面向事件相机的实时连续时间双目视觉里程计管线，能在保留异步事件原始时间戳的同时实现实时运行。
◆ 采用关键时间高斯过程回归，将估计状态约简到关键时间，而非随密集测量增长。
◆ 利用物理基础的白噪声-on-加速度先验，将测量插值到其精确时间戳，从而在降低状态规模时保持全时间分辨率。
◆ 该设计将状态规模与密集异步测量数量解耦，又不丢弃事件的异步特性。
在MVSEC和DSEC数据集上，该管线实时运行，MVSEC达22 Hz、DSEC达6 Hz，并在几乎所有测试序列中精度超过ES-PTAM。
其全体有效序列RMS相对误差为0.46 cm和0.038度，分别比ES-PTAM提升11倍和15倍。</td></tr>
<tr><td>2026-10-01</td><td>GlassGuard: Verified Glass Plane Mapping for Robot Navigation<br><a href='http://arxiv.org/pdf/2610.02110'>论文</a> | <a href='https://glassguardproject.github.io/'>代码</a></td><td>GlassGuard针对LiDAR导航中透明镜面表面导致碰撞边界缺失，以及玻璃重建可能污染自由空间的双重问题，提出面向导航的玻璃平面重建框架。
◆ 将玻璃覆盖率与自由空间污染并重作为成功准则，并贯穿候选平面验证和全局地图构建。
◆ 利用基础视觉模型生成玻璃实例掩码，结合结构3D线索生成度量平面假设，再用无深度2D投影几何校验方向后融合为全局地图。
◆ 在9个建筑尺度场景、超1小时和2.1公里真实机器人运行中验证，全景版达85%总覆盖，相同针孔输入下达82%，优于基线最高61%，每帧假体素减少5至17倍。
定性结果显示，重建平面可让导航规划器阻断穿玻璃路径，同时保留可通行路线。
项目页已公开并可访问。</td></tr>
<tr><td>2026-09-30</td><td>BatSLAM 2.0: Sequence-Verified Sonar Place Recognition in a Robust Pose Graph<br><a href='http://arxiv.org/pdf/2609.40085'>论文</a></td><td>本文提出BatSLAM 2.0，一种仅依靠仿生双耳声纳的SLAM系统，可在黑暗杂乱环境中构建拓扑地图。其核心贡献是缓解声纳位置识别的固有歧义，避免错误回环导致拓扑地图崩溃。
◆ 更新声学前端，为声纳位置识别提供更可靠的信号基础。
◆ 引入序列验证器，持续跟踪并验证回环候选，降低误闭环风险。
◆ 在高性能因子图框架上实现位姿图，提升全局优化与建图鲁棒性。
系统在仿真和真实录音中均得到验证，结果表明它能稳健创建拓扑地图、抵抗地图崩溃，并在地图规模扩大时保持鲁棒。</td></tr>
<tr><td>2026-09-30</td><td>MVP-SLAM: Multi-Camera Visual-Inertial Floorplan-Prior SLAM<br><a href='http://arxiv.org/pdf/2609.39596'>论文</a></td><td>论文提出MVP-SLAM，一种面向室内建筑工地的在线视觉惯性SLAM系统，利用设计阶段平面图作为度量先验来抑制长轨迹漂移。
◆ 仅用两个相对朝向的鱼眼相机，不依赖深度传感器，通过检测地图中的墙体并与平面图匹配来在线校正漂移。
◆ 引入漂移感知策略，根据系统漂移状态选择墙体与平面图的匹配，提高校正的可靠性。
◆ 设计多阶段集成机制，将每次匹配增量转化为持久校正，使轨迹在建图过程中持续保持校正并定位在平面图内。
在Hilti-Trimble SLAM Challenge 2026多层工地验证，定位任务22队第2（0.29米均值RMSE），SLAM任务62队第5（0.24米）。
它是在线、集成平面图并定位类方法中两项任务排名第一，证明平面图先验可在无深度传感器条件下提升建筑工地SLAM鲁棒性。</td></tr>
<tr><td>2026-09-29</td><td>Pruning for Efficiency, Paying in Fairness: Demographic Disparities in Pruned Speech-LLMs<br><a href='http://arxiv.org/pdf/2609.38106'>论文</a></td><td>本文系统研究音频编码器剪枝对SLAM-ASR不同人口群体的公平性影响，指出现有仅用总体WER选择压缩模型会掩盖群体差异。
◆ 首次揭示剪枝并非平等影响所有人口群体，表现最好与最差群体间的WER差距会成倍扩大。
◆ 发现这种不公平在三种编码器规模中都存在，但最大模型最初可被总体WER掩盖。
◆ 评估LoRA适配后发现，它虽改善所有群体WER，却更利好原本表现好的群体，并可能拉大某些群体差距。
◆ 在Common Voice英语、丹麦语和荷兰语上，口音差距持续存在但未明显扩大，说明剪枝的公平效应随数据集变化，必须直接测量。
◆ 提出剪枝模型部署应纳入分群体WER，并把最差表现群体的错误率作为明确选择标准。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-06</td><td>Image-Space Refraction Correction for Underwater 3D Reconstruction: Warping Flat-Port Views into Pinhole Perspective<br><a href='http://arxiv.org/pdf/2610.07788'>论文</a></td><td>本文面向平口防水壳消费级相机在水下三维重建中因界面折射产生碗状变形、破坏度量精度的问题，提出图像空间物理折射校正。该方法在重建前将平口视角图像校正为针孔透视，属于下游无关的预处理，可直接接入现有重建与SLAM算法。

◆ 创新性地将折射畸变通过光线追踪仿真建模，并在图像空间进行物理校正，而非依赖特定后端。
◆ 把平口防水壳视图映射为理想针孔透视，从而在重建前消除主导折射畸变和碗状变形。
◆ 在两组真实水下数据上验证，相比传统和折射SfM能去除变形、配准更多帧并保持低重投影误差。
◆ 校正可泛化到多种三维重建和VSLAM后端，展示了对下游视觉管线的广泛适用性。</td></tr>
<tr><td>2026-10-05</td><td>Structural Foundations of Nonlinear Systems with Unknown Inputs: The UID-Induced Normal Form and Minimal-Sensing Structure-from-Motion<br><a href='http://arxiv.org/pdf/2610.05939'>论文</a></td><td>本文首次为未知输入驱动的非线性系统状态估计给出了通用结构解，并提出UID诱导规范形。  
◆ 证明任意此类系统都可等价表示为UID诱导规范形，从而统一刻画未知输入对可观测动态的影响。  
◆ 将未知输入信息分解为与可观测动态结构解耦的方向，以及完全表征其可观测影响的分量。  
◆ 无需未知输入的模型或随机假设，即可统一实现未知输入解耦与重构。  
◆ 应用于此前未探索的最小Structure-from-Motion配置，仅用三个点特征和单轴陀螺仪实现递推状态估计。  
◆ 可恢复三维结构与相机运动至未知全局尺度，并通过真实数据验证该最小传感配置的可行性。</td></tr>
<tr><td>2026-10-04</td><td>Transferable Adversarial Robustness for Speech Foundation Models via Hierarchical Stabilization<br><a href='http://arxiv.org/pdf/2610.05310'>论文</a> | <a href='https://github.com/arefmousavi/hierarchical-robust-sfm'>代码</a></td><td>本文提出一种面向冻结语音基础模型的可迁移对抗鲁棒性学习框架，无需在未来下游任务上生成对抗样本或微调骨干。
◆ 将鲁棒性建模为冻结骨干表示稳定性与线性分类器决策边界间隔之间的交互，以此指导鲁棒化设计。
◆ 提出层次稳定化，在多个隐藏层稳定表示而非仅最后一层，同时保持干净任务所需的表示。
◆ 在干净适配选定层融合后固定该融合，仅扩大分类器间隔，实现无需下游对抗样本的轻量鲁棒精炼。
在Wav2Vec2、HuBERT和WavLM Large上四个任务、30 dB自适应攻击下，12个骨干任务组合的鲁棒准确率平均提升46.4个百分点。
间隔精炼再提升4.0个百分点鲁棒准确率，仅损失1.1个百分点干净准确率，表明鲁棒性可在任务未知前学习并迁移。</td></tr>
<tr><td>2026-10-01</td><td>MVDG: Efficient Multi-view 3D Disambiguation on Unconstrained Real-World Images<br><a href='http://arxiv.org/pdf/2610.01098'>论文</a></td><td>MVDG针对真实场景中视觉相似3D表面的“幻影匹配”问题，提出基于3D基础模型VGGT的多视图3D消歧框架，可联合推理任意数量视图并单次编码解码，突破传统成对分类器的多视角上下文限制与O(n^2)推理瓶颈。  
◆ 利用3D感知多视图特征替代成对比较，实现可扩展的多视角上下文推理，显著提升下游SfM效率。  
◆ 发现直接微调VGGT在噪声监督下不稳定，受Doppelgangers标签模糊启发，从AerialMegaDepth构建伪成对训练集，并通过采样子集微调获得稳定优化和跨场景泛化。  
◆ 针对完整SfM评估昂贵的问题，提出用伪成对数据集高效验证，并建立常规SfM指标与伪成对分类准确率之间的预测关系。  
实验表明，MVDG在成对准确率相当的同时，提高了SfM精度和推理速度。</td></tr>
<tr><td>2026-09-30</td><td>Introduction to Computer Vision<br><a href='http://arxiv.org/pdf/2609.39627'>论文</a></td><td>本书以代码优先方式系统介绍计算机视觉，覆盖经典二维图像处理、经典三维视觉与深度学习三大部分，共44个短章。
◆ 采用从第一性原理逐章构建的代码优先教学法，让读者同时理解数学与真实数据上的具体行为。
◆ 将经典二维处理、三维视觉和现代深度学习完整串联，覆盖卷积、特征、光流、立体、相机标定、SfM及CNN、检测与分割等。
◆ 每个技术均用Python和NumPy或PyTorch直接实现，并与OpenCV或PyTorch库函数数值核对，强调可验证与可复现。
◆ 借助AI辅助从开放课程笔记提炼材料，把大量工作代码压缩为简洁数学阐述，同时保留验证结果。
本书可作为学生与从业者理解计算机视觉算法及其Python实现的自包含参考。</td></tr>
<tr><td>2026-09-30</td><td>Geometry beneath the Waves: Dense Priors for Sparse-View Underwater 3D Gaussian Splatting<br><a href='http://arxiv.org/pdf/2609.18737'>论文</a></td><td>本文面向稀疏视角水下3D重建中散射、吸收和悬浮颗粒造成的特征与几何退化问题，提出利用领域自适应前馈几何先验增强3D高斯泼溅的框架。
◆ 采用LoRA与教师—学生蒸馏适配VGGT，在合成退化水下图像上训练并保留干净几何监督，从而在不修改预训练预测头的前提下提升对水下外观畸变的鲁棒性。
◆ 将预测的密集几何初始化中间3DGS表示，生成几何引导伪视角以增加视角重叠并强化特征轨迹，进而服务于后续RUSplatting优化。
在SeaThru-NeRF上，该方法将RUSplatting的PSNR从24.37提升至27.11 dB，SSIM从0.7611提升至0.8634。
在Submerged3D上，该方法取得最佳平均PSNR和LPIPS，验证了领域自适应几何先验对稀疏视角水下重建的有效性。
总体而言，其核心贡献是把前馈几何基础模型的水下适配与密集先验驱动的3DGS流程结合，实现更稳健的稀疏视角水下三维重建与视角合成。</td></tr>
<tr><td>2026-09-29</td><td>Beyond Monoscopic Viewing: A Study on 3D Gaussian Splatting Quality in VR<br><a href='http://arxiv.org/pdf/2609.38525'>论文</a></td><td>本文在头显中立体渲染3DGS并开展用户研究，模拟VR真实观看条件，检验单目与立体观看下的感知质量差异。
◆ 将3DGS评估从单目图像扩展到立体HMD真实观看，系统比较单目与立体条件下的用户偏好差异。
◆ 发现真实捕获视角受限时3DGS易出现局部浮点和深度错置，这类伪影在立体观看中更显著。
◆ 通过固定其余训练组件，仅比较SfM基线与SfM结合密集VGGT网络联合初始化，隔离初始化覆盖对重建质量的影响。
◆ 证明PSNR、SSIM、LPIPS及iSQoe、StereoQA等指标对上述感知伪影不敏感，无法预测用户偏好。
◆ 得出单目评估和标准图像质量指标会显著低估VR中3DGS感知伪影，立体评估对VR中3DGS质量评价必不可少。</td></tr>
<tr><td>2026-09-29</td><td>Prior-Driven Enhancements in 3D Gaussian Splatting: Normals and Depths Regularization<br><a href='http://arxiv.org/pdf/2609.36969'>论文</a></td><td>本文针对3DGS依赖SfM稀疏点云与视角相关属性、在复杂场景中易出现几何不准和视觉伪影的问题，提出引入几何先验的正则化优化方法。
◆ 将表面法线先验融入优化，通过使高斯协方差与局部表面结构对齐，提升几何一致性。
◆ 利用稠密深度先验并结合SfM初始点，增强逐像素深度估计，提高深度精度并减少歧义。
该方法能更稳健地处理多样复杂真实场景，减少视觉扭曲并提升重建质量。
作者在街景和高反射等挑战数据集及多个SfM流程上验证，显示良好环境兼容性与鲁棒性。
实验表明该方法提升几何精度和视觉质量，为复杂环境实时3D场景渲染提供可靠方案。</td></tr>
<tr><td>2026-09-28</td><td>OTT3R: Multi-View 3D Reconstruction and Fast Dataset Generation at 1% Compute<br><a href='http://arxiv.org/pdf/2609.36374'>论文</a> | <a href='https://github.com/TheFourthKaramazov/OTT3R'>代码</a></td><td>OTT3R提出面向多视图3D重建与快速数据集生成的知识蒸馏框架，在仅2块GPU的单工作站上实现低成本训练与部署。
◆ 将959M参数的π³蒸馏为102M学生模型，实现9.4倍压缩、最高7倍推理加速，训练计算仅为VGGT的1.6%。
◆ 集成伪标签管线可替代COLMAP，高通量生成逐像素点图和SE(3)相机位姿，667K图像仅用两块消费级GPU 3.5小时，并在所有测试序列成功，包括COLMAP失败案例。
◆ 通用学生模型在分布内单目深度上与教师持平，零样本在7-Scenes和DTU completion上优于COLMAP，但在分布外多视图几何上仍不能替代教师。
◆ 领域专用学生仅以0.2%计算量进行专业化，即在7-Scenes上比COLMAP准4倍、吞吐高980倍，并接近教师completion。
代码已开源，便于复现与后续研究。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-05</td><td>WildMatch: Weakly Supervised Image Matcher Adaptation for Wildlife Re-Identification<br><a href='http://arxiv.org/pdf/2610.07384'>论文</a></td><td>WildMatch研究仅用身份标签对预训练关键点匹配器进行弱监督适配，以提升野生动物个体重识别。
现有方法要么依赖大量标注学习全局嵌入且忽略局部证据，要么直接使用领域无关的现成匹配器。
该方法利用预训练匹配器挖掘信息图像对，从身份一致性生成弱正负监督，并对比微调匹配网络，强化同身份对应、抑制异身份对应。
◆ 首次提出匹配器层面的身份监督适配框架，用于动物重识别。
◆ 无需关键点级或几何对应标注，仅凭监测数据中已有的身份标签实现数据高效领域特化。
◆ 在多个开源数据集上超越现成匹配器和先进局部-全局融合方法，并在开放世界协议下展现对未见个体的可迁移对应先验。</td></tr>
<tr><td>2026-10-02</td><td>Geometry-Aligned Semantic Matching for Cross-Modal Planar Image Registration<br><a href='http://arxiv.org/pdf/2610.03167'>论文</a> | <a href='https://warren-wzw.github.io/CDPM/'>代码</a></td><td>本文提出CDPM，用于跨模态平面图像配准，解决语义相似未必几何对应、CNN细节缺乏全局跨模态语义引导的问题。该方法先建立几何一致的语义表示，并在细粒度定位中保持其在对应估计中的主导作用。
◆ 采用几何一致的跨模态图像块对渐进适配DINOv3，使语义特征相似度更真实反映跨模态空间对应关系。
◆ 构建DINO为中心的跨模态特征金字塔，用多尺度DINO表示维持稳定跨模态对应，并用轻量CNN分支补充结构细节以精化局部定位。
在三个跨模态数据集上，CDPM均取得更优性能。在VIS-IR上，相比RoMa，其AUC@3/5/10/20分别提升7.36、13.40、13.75和10.42个百分点，mACE从5.83像素降至2.78像素。它还在所有指标上超过RoMa v2，并减少45.6%的FLOPs。</td></tr>
<tr><td>2026-09-30</td><td>EPIC: Epipolar-Consistent 360° Immersive Stereo Video Generation<br><a href='http://arxiv.org/pdf/2609.38689'>论文</a></td><td>论文针对现有视频扩散模型只面向传统显示、无法生成高分辨率立体360°内容，且时间与立体不一致在沉浸式头显中更突兀的问题，提出EPIC零样本生成管线。
其核心贡献是把现有视频扩散模型扩展为4K立体360°视频生成，用于按需沉浸式内容。
◆ 提出受双目视觉与深度感知启发的极线感知360°图像匹配度量，可捕捉跨视图的时序与立体几何不一致。
◆ 将该度量作为偏好信号，在有限训练数据下进行直接偏好优化，提升时空与立体一致性。
◆ 构建零样本管线，无需从头训练即可生成4K立体360°视频，并提供可扩展的沉浸式生成路径。
该工作实现了360°立体视频生成，并为混合现实等沉浸式显示带来多样化按需体验。</td></tr>
<tr><td>2026-09-30</td><td>RBF-GNN: Rational Basis Functions for Pseudo-Coordinate based Graph Convolutions<br><a href='http://arxiv.org/pdf/2609.37015'>论文</a> | <a href='https://github.com/pawelswoboda/RationalBasisCNN'>代码</a></td><td>论文提出RBF-GNN，一种基于伪坐标的图神经网络，可利用欧氏、球面或角度坐标形成更强的空间归纳偏置。它在SplineCNN架构基础上，用有理Padé基函数替代稀疏激活B样条，并设计样条子空间初始化和保持方差的权重重缩放来改善训练。
◆ 用有理Padé基函数替代B样条，避免基函数数量随维度指数增长。
◆ 支持欧氏、球面或角度伪坐标，增强空间归纳偏置。
◆ 提出样条子空间初始化与保持方差权重重缩放，提升训练效果。
◆ 在多种采用SplineCNN的架构上仅替换该模块，即在语义关键点匹配、形状匹配和事件相机视觉任务上取得更优结果。</td></tr>
<tr><td>2026-09-29</td><td>UltraMatch: Transport Path Routing for Ultra-Fast and Memory-Efficient Image Matching<br><a href='http://arxiv.org/pdf/2609.36980'>论文</a> | <a href='https://github.com/JiajunLe/UltraMatch'>代码</a></td><td>UltraMatch是一种超高效、可扩展的半稠密图像匹配框架，旨在解决现有方法中密集token级匹配带来的二次计算与内存开销。
◆提出轻量Transport Path Router，在粗块表示上为每个源块排序并仅保留少量候选目标块，将后续token级匹配限制在选定路径，避免构建完整token-to-token匹配矩阵。
◆设计稀疏全局Dual-Softmax，仅在路由后的块候选上执行匹配，同时保留稀疏匹配空间中的全局竞争。
◆采用面向部署的结构重参数化特征提取与共享参数的微小精匹配头，进一步降低推理成本和内存占用。
◆该路由策略可迁移至EDM和ELoFTR，带来约2倍端到端加速且无精度损失。
实验表明UltraMatch在精度上有竞争力，比SuperPoint+LightGlue快1.67倍且峰值内存仅0.44 GiB，并可在单张RTX 3090上支持最高6K分辨率推理。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-07</td><td>RobotWorld: Benchmarking Multimodal Agents for Robot Use Across Diverse Tasks and Embodiments<br><a href='http://arxiv.org/pdf/2610.10409'>论文</a></td><td>◆ 提出RobotWorld，一个面向“机器人使用”的多模态智能体仿真基准，将指令与观察通过机器人接口转化为物理任务执行。
◆ 覆盖84个任务，横跨操作、移动操作、运动、驾驶与空中控制，并设置显式交互预算和可执行成功检查。
◆ 结合任务结果与执行轨迹分析，系统识别可迁移能力与阻碍可靠完成的缺口。
◆ 发现智能体能构建图像分割、相机标定、空间估计和动力学计算等复杂感知控制流程，但这些能力无法稳定组合为成功行为。
◆ 归纳出丢失任务相关物体状态、未纠正无效动作、恢复过晚、把未完成任务误判为完成等失败模式，并揭示Astra与Opus 5.5在不同任务类型上的优势差异。
该工作既提供严格试验场，也给出实证能力缺口，为训练和设计更可靠的物理世界智能体确立具体目标。</td></tr>
<tr><td>2026-10-07</td><td>Hall Effect-Based Tactile Force Detection Sensor for Robot-Assisted Minimally Invasive Surgery<br><a href='http://arxiv.org/pdf/2610.10346'>论文</a></td><td>论文针对机器人微创手术中医生与器械机械隔离导致触觉反馈缺失的问题，提出一种可贴附于手术工具抓取面的紧凑型触觉力传感器。该传感器采用霍尔效应传感器与磁铁嵌入可变形弹性体接触层的设计，集成三个毫米级传感单元，并通过六自由度并联机器人完成校准。
◆ 创新在于将霍尔效应与嵌入式磁铁、弹性体接触层结合，实现毫米级三传感单元的微型化力触觉检测。
◆ 每个传感单元均能检测法向力和剪切力，平均RMSE为2.133 kPa。
◆ 传感器在体模和离体猪组织上验证，可感知牵拉和滑移等触觉事件。
◆ 该工作为力敏感机器人微创手术提供了小型化、可集成的霍尔触觉传感方案，有助于恢复手术触觉反馈。</td></tr>
<tr><td>2026-10-07</td><td>DeltaSplat: Iterative Gaussian Refinement for Pose-Free Feed-Forward 3D Gaussian Splatting<br><a href='http://arxiv.org/pdf/2610.09853'>论文</a></td><td>DeltaSplat针对无位姿前馈3DGS中相机误差传播导致高斯几何与光度不准的问题，提出轻量迭代细化模块。
◆ 通过在当前高斯于输入视角渲染，并依据渲染残差迭代预测每个高斯的位置、不透明度和颜色更新，纠正单次预测误差。
◆ 将每像素Plücker射线与渲染深度作为软几何先验，缓解仅凭2D残差无法确定3D修正的欠定问题。
◆ 采用双分支卷积混合器融合上述先验与残差，并由按属性分头解码生成高斯更新，仅增加约2.2%参数且推理保持完全前馈。
在DL3DV无位姿设置下达到26.64 dB PSNR，比最先进骨干提升1.75 dB，并超过有真值相机的基线，在6-24视图和所有相机模式下均有一致增益。</td></tr>
<tr><td>2026-10-06</td><td>MIM-VLA: Learning Physical Interaction Representations from Gripper Motor Feedback<br><a href='http://arxiv.org/pdf/2610.08425'>论文</a></td><td>MIM-VLA提出一种基于夹爪电机反馈的VLA架构，将近期电流、位置、速度和信号有效性编码为128维交互token，以显式表征接触后的物理响应。
◆ 仅用电机信号预训练MIM，并借助人工审核的接触与交互阶段标签学习物理交互表示。
◆ 该交互token只条件化SmolVLA的夹爪动作通路，保持机械臂动作和位置控制接口不变。
◆ 同一token驱动MEM选择器VLM，对候选交互进行比较，生成基于证据的选择与解释。
◆ 在真实实验中，它支持阻力比较、主动探测区分视觉相似的真品与复制品，以及轻柔抓取易碎物体并泛化到留出实例。
在13对物体测试中，MIM-VLA以75.0%选择更高阻力物体，优于SmolVLA的48.8%，且无需额外触觉阵列、力扭矩传感器、校准力估计或直接电流控制。</td></tr>
<tr><td>2026-10-05</td><td>Less Context, Better Geometry: Masked Geometric Encoder for Robust 3D Foundation Models<br><a href='http://arxiv.org/pdf/2610.06813'>论文</a></td><td>本文针对3D基础模型中全连接全局注意力的二次复杂度和跨视角噪声传播问题，提出掩码几何编码器MGE。它在训练时策略性丢弃帧token，并从预训练全上下文教师模型蒸馏，使模型在不完整跨视角上下文中学习更丰富、鲁棒的单帧几何表示。
◆ 提出MGE，通过掩码全局注意力与教师蒸馏，增强遮挡和假相似视图下的鲁棒几何表示。
◆ 引入中间监督机制，避免因上下文缺失导致性能下降，同时保持标准基准上的高性能。
◆ 设计Anchor-Guided Adaptive token merging，保留代表性锚帧并合并冗余token，实现高效推理。
◆ 在有限视角设置下实现推理加速，并比现有高效推理方法保持更高重建质量。</td></tr>
<tr><td>2026-10-04</td><td>Building A Multi-Sensor Platform For Autonomous Driving Research: Challenges and Lessons Learned<br><a href='http://arxiv.org/pdf/2610.05604'>论文</a></td><td>本文核心贡献是报告一个面向自动驾驶研究的灵活多传感器平台在开发与部署中的挑战和经验，为后续多传感器系统研发提供参考。它指出无论传感器类型如何，定制数据采集平台都会遇到机械设计、传感器标定、电源管理和时间同步等基础问题。作者总结采用GNSS授时与NTP协议实现系统级时间同步、面向不同配置的自定义标定流程，以及提升现场可靠性和数据完整性的设计实践，以增强可复现性与鲁棒性。
◆ 以经验教训形式系统化呈现多传感器平台建设中的共性挑战，填补平台设计参考空白。
◆ 提出基于GNSS授时和NTP协议的系统级时间同步策略，应对多传感器时间一致性问题。
◆ 设计面向不同传感器配置的自定义标定流程，并融入提升现场部署可靠性与数据完整性的工程实践。</td></tr>
<tr><td>2026-10-03</td><td>Online Target-less Radar-LiDAR-Camera Extrinsic Calibration via Joint Optimization<br><a href='http://arxiv.org/pdf/2610.04552'>论文</a></td><td>本文研究雷达-激光雷达-相机系统的在线无目标外参标定，以提升复杂环境下多传感器融合的可靠性。针对现有无目标方法多面向单一传感器对、组合结果难以保证三传感器一致性，以及雷达稀疏噪声使雷达相关配对不可靠的问题，提出联合标定框架。该框架为每个传感器对构建残差并联合优化所有外参，以最小化整体残差，从而获得全局一致标定。  
◆ 提出三传感器联合优化框架，避免分步成对标定带来的不一致性。  
◆ 设计自适应雷达噪声滤波器，利用距离相关余量剔除虚假雷达回波。  
◆ 提出对应累积策略，跨帧聚合稀疏雷达对应，并在自建城市数据集上验证，较先进相机-激光雷达基线降低所有传感器对外参误差。</td></tr>
<tr><td>2026-10-02</td><td>An Assessment of the Triangulation Capabilities of a Multi-Site All-Sky Infrared Camera Array<br><a href='http://arxiv.org/pdf/2610.06922'>论文</a></td><td>本文报告Galileo Project在拉斯维加斯附近部署三套全天空长波红外相机阵列，并建立多站三角测量管线以刻画天空目标。
◆ 构建三站点、每站八台LWIR相机的IR-Dalek阵列，实现360度方位覆盖和公里级基线联合观测。
◆ 提出逐时刻瞬时三维位置估计，以加权平方距离最小化融合同时视线，权重计入相机指向误差与目标距离。
◆ 在LWIR缺乏恒星和固定地标的条件下，利用ADS-B飞机作为参考源完成内外参标定。
◆ 设计多传感器轨迹关联方案，判定不同相机检测是否属于同一目标。
◆ 用一周1650相机小时、2.1亿检测和530万轨迹验证，与ADS-B对比，三站解99%距离误差在5%内，单站对83%，并给出识别完整度随表观尺寸变化，50%阈值对应1.8像素翼展。</td></tr>
<tr><td>2026-10-01</td><td>Physical AI Smart Spaces: A Large-Scale Benchmark for Multi-Camera 3D Perception in Smart Spaces<br><a href='http://arxiv.org/pdf/2610.02580'>论文</a></td><td>本文提出Physical AI Smart Spaces，一个面向室内智能空间的大规模多类别多摄像头3D感知基准，包含超过280小时同步1080p视频、近1800个摄像头，覆盖仓库、医院、零售等场景。
它提供多摄像头身份、2D/3D边界框、相机标定及可用深度等自动标注，并覆盖Isaac Sim合成、Cosmos Transfer外观增强、真实Sim2Real评估以及两个仓库部署中的时间同步、VGGT自动标定和跨摄像头3D框验证。
◆ 首个同时提供大规模、多类别、多摄像头室内智能空间3D感知数据的基准。
◆ 建立从合成生成、外观增强到真实部署、标准化提交与排行榜的完整评测流程。
◆ 提出HOTA的3D实例化，将2D框跟踪评估扩展到3D位置和3D框。
◆ 通过AI City Challenge基线展示从仅行人3D位置跟踪到多类别3D框跟踪的演进。</td></tr>
<tr><td>2026-10-01</td><td>The Impact of Processing Parameters on High-Accuracy Measurements in UAV Photogrammetry<br><a href='http://arxiv.org/pdf/2610.01438'>论文</a></td><td>本文针对无人机摄影测量中处理流程，尤其是光束法平差参数设置对高精度测量影响研究不足的问题，开展系统性全因子实验。研究基于1.5年、220公顷区域内10个无人机数据集，评估768种处理变体和8个关键参数。结果显示最终三维精度差异巨大，最佳RMSE为16毫米，最差达303毫米，最关键因素为地面控制点数量、额外相机检校校正及PPK GNSS确定相机投影中心坐标。研究还评估工作流优化对位移、倾斜变化和水平应变确定的影响，随机位移误差稳定在约6-7毫米，系统误差在各轴降低超过一半，垂直中位绝对误差由14毫米降至7毫米。
◆ 首次开展大规模、面向实践的处理参数选择评估，揭示其对摄影测量产品和变形指标确定精度的深层影响。
◆ 提出可操作的优化建议，支撑更稳健、可重复的高精度无人机摄影测量监测工作流。</td></tr>
<tr><td>2026-09-30</td><td>Introduction to Computer Vision<br><a href='http://arxiv.org/pdf/2609.39627'>论文</a></td><td>这本书以代码优先方式介绍计算机视觉，覆盖经典二维图像处理、经典三维视觉与深度学习三大部分，组织为44个短章。
◆ 从第一性原理逐步构建主题，涵盖图像算术、形态学、卷积、金字塔、频域滤波、特征检测、光流、立体视觉、投影几何、相机标定和运动恢复结构。
◆ 完整串联现代深度学习脉络，从单个神经元到卷积网络、反向传播、经典架构、迁移学习、目标检测、语义与实例分割，并延伸至混合精度与并行训练等工程实践。
◆ 所有技术均用Python和NumPy或PyTorch直接实现，并与OpenCV或PyTorch库函数数值对照，使数学原理与真实及合成数据上的具体行为可见。
◆ 材料借助AI从免费在线课程笔记提炼，将大量工作代码压缩为简明数学阐述，同时保留可验证、可复现的结果。
它可作为学生和从业者理解计算机视觉算法及其Python实现的自包含参考。</td></tr>
<tr><td>2026-09-30</td><td>CAT-Free: Multi-View Pedestrian Localization without Calibration, Annotations, or Target-Scene Training via Adaptive Geometric Filtering<br><a href='http://arxiv.org/pdf/2609.34302'>论文</a></td><td>CAT-Free提出仅用同步RGB视频即可完成多视角行人定位，无需相机标定、位置标注或目标场景训练。
◆ 它从视频自动估计相机配置，并融合多相机观测估计行人位置。
◆ 针对自动估计误差，引入两个自适应几何滤波器，阈值由输入序列自动确定，剔除不可靠定位。
◆ 在WildTrack、MultiviewX和GMVD上分别取得82.5、84.5、65.7 MODA，且能跨场景无重调迁移。
◆ 定位不确定性可有效预测MODA，相关系数r=-0.98，提供无需标签的可靠性估计。</td></tr>
<tr><td>2026-09-29</td><td>DRHeC: Differentiable Rendering for Hand-Eye Calibration with RGB-Based Gradients<br><a href='http://arxiv.org/pdf/2609.36779'>论文</a></td><td>本文提出DRHeC，一种基于RGB的可微渲染手眼标定框架，用于解决传统标记法依赖标记精度、无标记学习法依赖网络特征，以及现有可微渲染使用二值掩码导致细节丢失、优化不稳定和易陷局部极小的问题。
◆ 提出RGB可微渲染框架，融合颜色与掩码几何特征，提供更丰富的几何和外观线索，提升标定精度与优化稳定性。
◆ 提出掩码引导的图像到图像翻译方法，在翻译过程中显式保持颜色与几何一致性。
通过仿真和真实实验验证，该方法具有较强精度与鲁棒性，并明显优于现有可微渲染方法。
在UR5e真实实验中，抓取成功率达88.9%，插入成功率达57.4%，分别比EasyHeC高46.3和48.1个百分点。</td></tr>
<tr><td>2026-09-24</td><td>From WPT to Encrypted Telemetry: A Battery-Free Backscattering-based Polarimetric Wireless Sensor<br><a href='http://arxiv.org/pdf/2609.29214'>论文</a></td><td>本文提出一种由辐射式无线携能供电的室内无电池无线传感节点，面向安全、节能的主动感知。该节点集成温湿度、气压和VOC测量，并由低功耗MCU完成校准、VOC指数计算、载荷格式化和AES-128加密。实验表明，多传感器读出与加密传输可靠，且完整感知-计算-加密-传输周期能耗极低。
◆将无电池传感从简单采集回传推进到具备节点计算与AES-128加密保护的安全遥测。
◆在同一低功耗平台上融合多参数环境感知、VOC指数推导、数据格式化与加密传输。
◆提出1-bit控制的反向散射整流天线，同时完成辐射WPT能量收集并产生正交极化反向散射信号，实现稳健极化通信。</td></tr>
<tr><td>2026-09-23</td><td>Calibration-Free Surface Normals Estimation in Vision-Based Tactile Sensing using Universal Photometric Stereo<br><a href='http://arxiv.org/pdf/2609.31754'>论文</a></td><td>本文提出一种免标定的视触觉接触表面法向估计方法，利用通用光度立体神经网络直接从触觉图像推断法向。作者在三种不同光学系统传感器上验证了跨传感器适用性，并在金属球、自然纹理物体及Dome形Digit 360实验中取得平均角误差6.56°、10.66°和10.18°的结果。这表明在充分照明下，仅用合成数据训练的模型也能稳健估计真实接触面法向。
◆ 提出免标定的通用光度立体框架，直接估计接触面法向，免除物理探针标定。
◆ 证明通用方法可跨不同光学系统传感器迁移，并匹配标定基线的精度。
◆ 为不同视触觉传感器建立统一接触面表示，推动可迁移触觉感知。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vlm'>Robot VLM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-07</td><td>Rephrase Before You Act: Characterizing and Mitigating Language Sensitivity in Vision-Language-Action Models<br><a href='http://arxiv.org/pdf/2610.10526'>论文</a> | <a href='https://sttawm.github.io/rephrase-before-you-act'>代码</a></td><td>论文揭示视觉语言动作模型对指令措辞高度敏感，且未继承视觉语言模型的语言鲁棒性，一词改动可造成数十点成功率波动。

◆ 通过统计检验的单编辑波动和oracle短语搜索，系统表征并量化这种语言敏感性，证明仅靠措辞即可接近弥合分布内与分布外任务的21点差距。
◆ 提出无需修改策略、无需重训练的规则化改写框架：先用少量训练任务的多措辞评分，再由大语言模型蒸馏出十到二十条改写规则。
◆ 部署时仅对每条输入指令按规则改写一次，无需逐步验证，即可提升冻结π0在十二个留出任务上的相对成功率16%到27%，且增益集中于分布外场景。
◆ 该流程可复现于π0.5与LIBERO，将微调内成功率从93.6%提升至97.8%，并零样本适用于未见任务和指令。</td></tr>
<tr><td>2026-10-07</td><td>Do Vision-Language-Action Models Understand Instructions? A Mechanistic Interpretability Study on Language Grounding<br><a href='http://arxiv.org/pdf/2610.10178'>论文</a></td><td>本文对π0.5与GR00T N1.7开展受控机制可解释性研究，检验VLA动作生成是否真正依赖语言指令。作者在LIBERO上用同义替换、语义缩放、方向破坏、随机物体替换和空字符串扰动指令，并对动作生成模块残差流做激活与归因修补，发现模型对抽象改写和虚构物体较不敏感，却对空描述和方向语言高度敏感，且敏感层定位因模型而异。
◆ 首次系统比较两类SOTA VLA的语言接地机制，揭示语言依赖具有扰动类型和模型结构依赖性。
◆ 构建动作生成模块残差流的激活/归因修补框架，用于定位指令对动作生成的因果作用位点。
◆ 发现GR00T N1.7中方向扰动可产生最大因果效应却基本不改变内部表示几何，形成因果与表征解离。
◆ 揭示归因修补可靠性因模型而异，GR00T中贴近激活修补，π0.5中明显偏离，说明解释方法需按模型校准。</td></tr>
<tr><td>2026-10-07</td><td>End-to-End Autonomous Generation of Human Assembly Plans<br><a href='http://arxiv.org/pdf/2610.09781'>论文</a></td><td>本文提出一种仅需网格装配体即可端到端自主生成人类装配计划的自包含方法，无需关节元数据、紧固件标注或额外信息，可输出分步手册或结构化失败报告。
◆ 将面向装配设计原则编码为物理模拟器中的系统拆卸成本函数，自动确定装配序列与子装配。
◆ 自主生成装配工具清单、装配手册和改进可装配性的设计反馈，并主要依靠多模态大语言模型完成手册、工具标注与反馈。
◆ 与总是先移除最外层零件的基线相比，DfA感知序列规划在136个5至30零件装配上降低机器人臂代理模拟装配时间35%。
◆ 工具选择正确率达88.6%，并用视觉语言模型裁判对比消融版本，识别手册中承载关键信息的页面元素。
该方法和开源代码可供工程师或AI代理使用，以加速产品制造计划创建。</td></tr>
<tr><td>2026-10-07</td><td>YUBI-STAG: Contact and Semantic-Rich Alignment for VLAs via Automated Video-Language Grounding<br><a href='http://arxiv.org/pdf/2610.09718'>论文</a></td><td>论文针对VLA模型语言指令与物理交互缺乏细粒度对齐的问题，尤其现有机器人演示缺少夹爪、接触对象和抓取移动等执行语义。
◆ 提出YUBI-STAG自动标注框架，结合接触物体分割与视觉语言模型，为演示生成物体身份属性状态、单双臂动作、协调及空间交互语义。
◆ 提出YUBI-VLM蒸馏模型，直接从原始未分割视频、仅腕部视角和少量推理调用中恢复动作结构与细粒度标注。
◆ 构建YUBI-STAG-Bench，覆盖时序、语义与空间接地任务，验证标注精度与泛化能力。
◆ 证明用这些标注后训练VLA策略，可对齐细粒度语言与接触感知结构，提升双臂操作和指令跟随，包括物体身份、执行夹爪、目标位置与空间关系。
实验显示YUBI-VLM以更少调用和更短运行时间接近YUBI-STAG精度，并能泛化到未见操作。</td></tr>
<tr><td>2026-10-07</td><td>System Switch: When Should a Fast Decision Model Stop and Think?<br><a href='http://arxiv.org/pdf/2610.09683'>论文</a></td><td>◆ 提出“系统切换”框架：快速actor每步决策，仅在门控开启时把控制权交给慢速推理视觉语言模型，游戏继续运行；基于闭环Doom与System One模型经llama.cpp评测。
◆ 在900道留出题发现，0.15B–9B零样本决策模型有收集物品偏差，选项顺序影响准确率，且准确率、校准、置信度敏感性彼此不同，同等准确率模型AUROC差异大。
◆ 最敏感模型的置信度主要追踪失败情境类型而非具体错误，说明延迟触发应依据情境而非单题对错。
◆ 离线延迟最不自信30%决策给推理模型，收益与actor AUROC强相关（0.87）；留出游戏中原顺序增益+0.13、打乱+0.08，推理约贡献一半。
◆ 闭环33局三随机种子无变体到出口；承诺计划能开更多门并让静止actor行动，固定探索规则更易死，门锁知识会使推理器误判普通门，未告知则退回收集；并发布代码、提示、数据与日志。</td></tr>
<tr><td>2026-10-07</td><td>Adaptive Code Generation for Controlling Robots<br><a href='http://arxiv.org/pdf/2610.09588'>论文</a></td><td>本文针对机器人在未知动态环境中作为复杂自适应系统部署的需求，提出从刚性命令库转向基于意图的自主性，并指出自然语言是表达有限指令集之外复杂目标的关键媒介。核心贡献是构建一个利用生成式AI控制机器人的架构框架，通过LLM与VLM协同的双AI设计连接高层意图与可执行动作。
◆ 提出双AI架构，由LLM将高层意图翻译为受形式化机器人库和可验证语法约束的程序代码，由VLM通过蒸馏过程提供语义接地。
◆ 针对形式化鸿沟、分类学鸿沟以及环境不可预测性，以受限生成方式弥合不精确意图与可执行动作之间的差距。
◆ 引入基于几何和语义阈值的环境驱动重规划触发机制，并配合连续运行时监控和自适应规划闭环，以维持时间状态与进度感知。
◆ 在多种前沿模型上进行基准测试，证明将生成式AI嵌入反应式受限循环，可在动态未知环境中鲁棒完成复杂意图。</td></tr>
<tr><td>2026-10-07</td><td>Not All Uncertainty Matters: Simulation-in-the-Loop Fast-Slow Reasoning for Decision-Critical Autonomous Driving System<br><a href='http://arxiv.org/pdf/2610.09520'>论文</a></td><td>论文提出SIGMA，一种面向决策关键自动驾驶的模拟在环快慢协作框架，云端VLM按需提供高层推理，车载模块负责实时感知与控制。核心思想是将规划器纳入不确定性评估，通过语义和几何不确定性下可能场景对可行轨迹与规划成本的影响，判断解决该不确定性是否值得调用云模型。
◆ 提出模拟在环的任务导向不确定性评估，以规划收益而非感知不确定性作为云推理触发依据。
◆ 提出期望规划增益EPG，作为决策级指标统一指导云调用、云引导集成与请求优先级，并兼顾截止期和资源约束。
◆ 在CARLA中验证，在静态和动态障碍场景下减少无效云交互，同时提升规划、效率与导航成功率。
◆ 相比固定周期协作，云交互减少50%，导航成功率提升6%以上，动态场景完成时间最多降低26.2%。</td></tr>
<tr><td>2026-10-07</td><td>Sparse Feature Policy Unlearning Mitigates State Hallucination in Vision-Language-Action Models<br><a href='http://arxiv.org/pdf/2610.09496'>论文</a></td><td>本文研究VLA模型中的状态幻觉：模型在机器人-物体状态尚未实现时仍按已达成状态继续行动，导致反复失败。分析发现幻觉与任务相关视觉区域注意力减弱相关，且稀疏自编码器揭示幻觉相关稀疏特征被激活。
◆ 将状态幻觉机制与可解释稀疏特征关联，为定位不良策略知识提供依据。
◆ 提出SOUL，以幻觉失败特征为遗忘目标、成功行为特征为保留目标，选择性反学习状态幻觉相关策略知识。
◆ 在多种VLA架构、仿真与真实环境中验证，SOUL显著减少幻觉失败并提升任务成功率，同时不显著损害既有操控能力。
这些结果表明，可解释特征分析能实际支持对机器人策略中不良知识进行选择性修改。</td></tr>
<tr><td>2026-10-07</td><td>TempoBridge: Language-Guided Tempo Control for Vision-Language-Action Policies<br><a href='http://arxiv.org/pdf/2610.09451'>论文</a></td><td>TempoBridge针对现有VLA模型擅长理解“做什么”、却难以按语言指令控制“以多快或多慢执行”的问题，提出语言引导的动作节奏控制框架。  
◆ 它无需额外节奏条件机器人演示，也无需对基础策略做节奏专用微调，仅利用冻结VLA表示即可实现轻量节奏调制。  
◆ 它从上下文VLM表示中提取节奏线索，并通过因果阶段路由器将节奏与任务进度对齐，执行时调制标称运动命令。  
◆ 在LIBERO任务中，规范节奏指令下Tempo成功率从52.6%提升到89.7%，同时保持较高的任务成功率。  
◆ 在没有节奏线索时性能接近基线，并能无需额外训练泛化到未见过的节奏表达。  
物理机器人实验进一步验证了真实操作中的语言条件节奏调制能力。</td></tr>
<tr><td>2026-10-06</td><td>Co-Evolving Robot Orchestrators and Policies through Deployment<br><a href='http://arxiv.org/pdf/2610.09228'>论文</a></td><td>论文提出Robo-COP，解决VLA策略在真实部署中泛化不足，以及VLM编排器围绕冻结策略只能规避失败、无法突破瓶颈的问题，并让编排器与策略在部署中共演化。它从自身执行中筛选技能演示，在数据可解决重复失败时微调策略，且仅在新策略提升对应技能后采纳，避免单独微调导致与旧编排器脱节。
◆ 编排器与策略在部署中共同演化，打破冻结策略瓶颈。
◆ 从自身执行筛选演示，按需微调并以技能提升验证后采纳新策略。
◆ 将部署变为执行、数据、学习、再执行的自我改进飞轮。
在十个模拟RoboLab任务中平均留出成功率从64.8%升至73.8%，高于固定计划微调的65.8%；三个真实任务从38.3%升至50.0%。</td></tr>
<tr><td>2026-10-06</td><td>PEARS: Physical-Prior-Guided Efficient Adaptation via Failure Reasoning and Diffusion Steering for Tactile Manipulation<br><a href='http://arxiv.org/pdf/2610.08784'>论文</a> | <a href='https://song-kun.github.io/pears'>代码</a></td><td>本文提出PEARS，一个物理先验引导的混合强化学习框架，用于带触觉反馈的预训练策略样本高效在线适应。
◆ 设计物理引导力推理模块，利用视觉语言模型中的物理先验，从视觉结果与触觉交互历史诊断失败并更新任务合适的接触力边界。
◆ 引入高频混合力位控制器，在接触过程中执行这些力边界，将高层物理推理转化为底层力控约束。
◆ 提出触觉条件扩散引导强化学习，通过调整冻结流匹配策略的潜在噪声来纠正自由空间运动与接触时机，无需更新基础模型。
仿真中PEARS较最强单任务基线提升成功率12.4至37.4个百分点，并最多减少53.2%达到成功率阈值所需交互回合。
真实实验中白板擦除成功率达95%，移液管吸液达90%，表明物理推理与策略引导结合可加速适应并降低昂贵交互。</td></tr>
<tr><td>2026-10-06</td><td>MIM-VLA: Learning Physical Interaction Representations from Gripper Motor Feedback<br><a href='http://arxiv.org/pdf/2610.08425'>论文</a></td><td>MIM-VLA提出基于夹爪电机反馈的VLA架构，将近期电流、位置、速度与信号有效性编码为128维交互token。  
◆用仅电机的MIM模块以人工审核的接触和交互阶段标签预训练，并只调节SmolVLA的夹爪动作通路，保持手臂动作与位置控制接口不变。  
◆同一交互token支持MEM选择器VLM比较候选交互，产生证据条件的选择和解释。  
◆方法无需额外触觉阵列、力扭矩传感器、校准力估计或直接电流控制，直接利用夹爪已有电机反馈。  
◆在真实场景中验证阻力比较、真假相似物体主动探测和脆弱物体轻柔抓取，并覆盖未见过实例。  
在13对物体中，MIM-VLA以75.0%选择更高阻力物体，显著高于SmolVLA的48.8%。</td></tr>
<tr><td>2026-10-06</td><td>Event-Driven Proactive Robot Assistance through Vision-Language Reasoning<br><a href='http://arxiv.org/pdf/2610.08344'>论文</a></td><td>本文提出事件驱动的主动机器人协助框架，由人-物交互结果而非用户指令触发高层推理。  
◆ 将主动协助建模为事件驱动问题，利用交互结果启动协助推理，无需推理时任务说明。  
◆ 设计事件监视器，在事件完成后提取稳定的前后快照，刻画状态转移。  
◆ 使用冻结预训练VLM根据快照语义先验推断任务上下文，并判断是否需要协助。  
◆ 限定动作原语和整数ID对象引用，使VLM生成的动作序列可执行且可验证。  
◆ 在三个真实桌面协作任务上验证，无需任务特定训练或微调，性能可与用户指令变体相当。</td></tr>
<tr><td>2026-10-06</td><td>Compact Robot Policies Need Fine-Grained Visual Representations<br><a href='http://arxiv.org/pdf/2610.08183'>论文</a> | <a href='https://corp-policy.github.io/'>代码</a></td><td>论文核心主张是多任务操作策略的性能差异主要来自视觉表示，而非参数量或生成式先验，并据此提出48.9M参数、无VLM和视频生成先验的CoRP，由表示提取器和流匹配动作生成器组成，在LIBERO达97.0%、RoboTwin 2.0达75.78%/73.36%，匹配大40.9-163.6倍系统。
◆ 构建极紧凑策略，证明无需大模型与生成式先验也能实现强多任务操作。
◆ 固定动作生成器消融视觉提取器，发现预训练初始化决定性，冻结编码器损失19.8分，随机ViT与ImageNet ResNet显著下降。
◆ 表示压缩关键，每视图48 token优于全patch token，硬token预算优于变分信息瓶颈，后者会抑制指令相关token选择。
◆ 语言条件仅在观察无法消除目标歧义时关键，LIBERO-Goal从9.2%升至95.8%，无歧义时移除略好。
结论是紧凑策略需具备预训练、任务适配且压缩的视觉表示。</td></tr>
<tr><td>2026-10-06</td><td>The Failure Is in the Readout: Fine-Grained Emotion Recognition Benchmarks Measure Elicitation, Not Perception<br><a href='http://arxiv.org/pdf/2610.08162'>论文</a></td><td>论文核心结论是细粒度情绪识别基准的失败在读出环节，即它测量的更像情绪诱发/答案生成，而非模型感知。  
◆揭示EmoNet-Face-HQ原协议用生成式答案评估VLM，会低估模型并错误得出必须依赖专用微调模型EIF的结论。  
◆提出保留原图像、分类体系和专家评级，仅把每个情绪类别改为独立二分类查询并直接读取logits概率。  
◆在11个开放权重VLM上，验证式读出全部显著超过专家锚点κw=0.468，达κw=0.507-0.586，其中三个还显著超过EIF。  
◆控制实验证明增益来自分级概率而非yes/no提问，阈值化损失142%平均增益并降至κw=0.254-0.423。  
◆真实照片FACES复现较弱且混合，10个通过有效门控的模型中6个增益、3个中性到正、1个负，说明效应不限于合成数据。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-visual-semantic-recognition'>Robot Visual Semantic Recognition</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-07</td><td>MultiFly: A Real-World Multimodal Aerial Dataset with Annotation-Efficient Label Transfer and Cross-Modal Semantic Consistency<br><a href='http://arxiv.org/pdf/2610.10359'>论文</a> | <a href='https://github.com/markus-42/multifly'>代码</a></td><td>本文提出MultiFly，一个面向低空无人机语义感知的真实世界多模态数据集，覆盖RGB、热红外、LiDAR和雷达。
◆ 数据集包含四个郊区场景的17,272个同步样本，提供15类逐帧语义标注以及标定和GNSS-RTK/IMU测量。
◆ 提出标注高效标签迁移方法，仅用115张人工标注RGB图像，通过共享几何表示将标签传播到全部四种模态。
◆ 该方法额外生成17,157张RGB、17,272张热红外、8.4亿LiDAR点和340万雷达点的语义标签，迁移标注平均一致率达89.93%，六种模态对平均语义一致性达90.94%。
◆ 建立四种模态的语义分割基准，揭示密集LiDAR与稀疏雷达数据需要不同架构行为。
综上，MultiFly是首个公开的真实低空航空多模态基准，为可扩展多模态空中感知提供基础。</td></tr>
<tr><td>2026-10-03</td><td>ForeAct3D: Policy-Grounded Future World Modeling for VLA Policies<br><a href='http://arxiv.org/pdf/2610.04607'>论文</a> | <a href='https://github.com/anthonytao80-crypto/ForeAct3D'>代码</a></td><td>ForeAct3D提出一种嵌入VLA策略、由策略动作接地的未来世界建模框架，训练时用未来语义3D预测和物理约束塑造动作生成表征，推理时无需未来预测。
◆ 用可学习几何查询从策略表征解码当前与未来的深度、语义分割和相机位姿，构建语义3D场景状态。
◆ 将未来查询条件于策略生成的动作块，使未来预测与实际计划执行的交互直接绑定。
◆ 引入背景静态性和实例级刚性的物理一致性约束，并把腕部相机位姿锚定到末端执行器运动学。
训练中这些目标共同塑造动作生成共享表征；无机器人预训练时LIBERO平均成功率98.3%，CALVIN平均任务长度3.73，真实世界成功率从6.7%升至37.8%，消融证明语义3D监督、物理一致性和动作条件均有效。</td></tr>
<tr><td>2026-10-02</td><td>CORNAV: Construction-Aware Reasoning for Robot Navigation on Active Worksites<br><a href='http://arxiv.org/pdf/2610.03622'>论文</a></td><td>施工行业长期面临劳动力短缺、低生产率和事故率高等问题，但现有语言导航只依赖语义场景理解，缺少建筑图纸、进度和安全约束等施工上下文，难以在活跃工地安全导航。为此，论文提出 CORNAV，一种仅用二维 CAD 图纸和项目进度、无需 BIM 的蓝图接地且日程感知导航框架。
◆ 将建筑蓝图与层级开放词汇三维场景图对齐，用对象查询接地提升永久建筑特征的定位与任务成功率。
◆ 把项目进度转化为随时间变化的导航约束，使机器人能响应动态施工状态。
◆ 融合 LLM 安全验证与 A* 规划，规划前拒绝危险请求，并强制排除区、优先避开高风险区。
在室内办公室和真实工地实验中，蓝图接地将任务成功率从 13.0% 提升至 72.2%，日程感知消除所有硬区违规，安全模块能正确拒绝因进度误标产生的危险请求。</td></tr>
<tr><td>2026-10-02</td><td>EmbPASS: Towards Cross-Embodiment Open Panoramic Segmentation<br><a href='http://arxiv.org/pdf/2610.03248'>论文</a> | <a href='https://github.com/guopj1/EmbPASS'>代码</a></td><td>论文针对异质具身平台在观察视点与空间布局上的差异所导致的跨具身观察偏移，提出跨具身开放全景分割这一新任务，以推动一致可靠的全景感知研究。
◆ 提出跨具身开放全景分割任务，系统定义并研究异质具身观测下的全景语义分割问题。
◆ 构建 EmbPASS 多平台全景语义分割基准，覆盖车辆、无人机、可穿戴设备与四足平台，并采用统一语义分类体系。
◆ 提出 EPONet 开放词汇全景语义分割网络，融合关系感知度量适配器 RAMA 与内容自适应语义迁移 CAST，增强异质观测下的空间建模和语义迁移。
实验表明 EPONet 在 EmbPASS 上取得 35.82% mIoU 的最佳平台均衡性能，超过最强基线 1.10%，并在现有全景分割基准上保持竞争力。
源码与 EmbPASS 基准将公开。</td></tr>
<tr><td>2026-10-01</td><td>Lang3DSeg: Annotation-Free Open-Vocabulary 3D Segmentation with Point Transformers<br><a href='http://arxiv.org/pdf/2610.00855'>论文</a></td><td>Lang3DSeg 提出一种无需人工标注的开放词汇室外3D LiDAR语义分割框架，首次以点Transformer为主干并完全从头训练。
◆ 首次把点Transformer用于室外稀疏、无界的LiDAR开放词汇分割，突破体素稀疏卷积和室内点Transformer的局限。
◆ 针对2D到3D标签投影的深度歧义，使用显式类别优先规则合成掩码，避免物体后方点被误赋标签。
◆ 在投影实例深度分布的第一个间隙处截断，直接修正投影误差，而非在配准序列中平均。
该方法在nuScenes验证集达到52.8% mIoU，在SemanticKITTI达到41.4%，为已发表无标注方法最高。
每次分割仅用单帧LiDAR，推理实时且无需运行视觉语言模型。</td></tr>
<tr><td>2026-09-30</td><td>NaviScale: Generating Large-Scale Semantic Map Datasets for Object Navigation<br><a href='http://arxiv.org/pdf/2609.27218'>论文</a></td><td>NaviScale提出面向语义地图ObjectNav的大规模数据生成框架，预测器仅需部分与完整语义地图配对训练，无需为每个样本重建完整3D环境。
◆ 组合真实住宅平面图与MP3D、HM3DSem的房间级语义和障碍地图，低成本生成大规模多样化语义地图数据。
◆ 房间间缩放改变平面图结构，提升平面图级布局多样性。
◆ 房间内缩放按房间类别匹配不同房间地图，填充同一固定平面图以增加房间组合多样性。
◆ VisRC通过射线投射将组合地图转为部分观测，并显式考虑视场、感知范围和遮挡。
生成192,000张语义地图、24,000个平面图和12,794处房产；在HM3D达64.3% SR/34.8% SPL，MP3D达43.1% SR/16.8% SPL，且不改变预测架构，并验证地图质量、语义分割误差和实机部署。</td></tr>
<tr><td>2026-09-29</td><td>HIGS: Hierarchical Implicit Grids for Joint Geometric and Semantic Scene Understanding<br><a href='http://arxiv.org/pdf/2609.38620'>论文</a></td><td>本文提出HIGS，一种面向联合几何与语义场景理解的分层隐式网格表示，核心是用多分辨率子图和统一查询解码机制同时支持几何与语义特征。
◆ 采用多分辨率重叠子图分解与分层局部优化，使大规模场景的隐式表示具备可扩展计算能力。
◆ 设计统一查询与解码流程，将可学习地图特征转换为几何和语义输出，训练与推理机制一致。
◆ 引入特征编码器预测初始分层网格特征，显著减少子图特征从头优化所需时间。
◆ 在隐式特征空间内对齐并融合子图，避免解码最终输出，从而加速估计漂移校正。
◆ 将几何特征与视觉语言潜特征嵌入地图，支持SDF构建和开放词汇物体定位，提升计算内存效率并保持估计精度。</td></tr>
<tr><td>2026-09-29</td><td>When to Adapt: Multi-Signal Domain Shift Detection for Efficient Training-Free Adaptation in Open-Vocabulary Segmentation<br><a href='http://arxiv.org/pdf/2609.37602'>论文</a></td><td>论文针对真实机器人长期部署中开放词汇语义分割的域偏移问题，研究何时触发免训练持续测试时适应。现有方法多逐帧适应，在资源受限硬件上不实用。为此，作者提出多信号域偏移检测方法，通过跨连续帧的时间一致性监控并融合视觉变化、适配器不匹配和语义漂移，仅必要时触发适应。
◆ 提出用于免训练持续测试时适应的多信号域偏移检测框架，将适应触发从逐帧改为按需。
◆ 创新性联合视觉变化、适配器不匹配和语义漂移三类互补信号，提升触发判断可靠性。
◆ 在室内外基准及真实机器人数据上验证，保持分割精度同时大幅减少适应次数，使长期部署更可行。</td></tr>
<tr><td>2026-09-29</td><td>Towards Spatial Perception for Heterogeneous Robot Collaboration in Subterranean Mining Environments<br><a href='http://arxiv.org/pdf/2609.37419'>论文</a></td><td>本文针对废弃地下矿深部矿体自主开采中的异构多机器人协同感知难题，指出单一平台难以同时满足长距离穿行与高载荷传感需求。
论文提出PERSEPHONE任务中的机载感知流水线，用轻量Explorer与高载荷Inspector两类机器人协同完成矿井探索与矿体精查。
◆ 引入零样本视觉-语言语义分割，使Explorer能直接依据自然语言提示检测矿藏并生成含检查目标的3D场景图。
◆ 设计几何抽象流程，将原始检测转化为可操作检查目标，包括逐视角边界框生成、跨视角框合并、平面拟合与多边形提取。
◆ 将地图和场景图传递给Inspector，由其规划近距离检查视点，实现探索与精查的异构协作闭环。
◆ 在地下测试设施和活跃菱镁矿完成现场验证，覆盖铁脉与菱镁矿化，并在真实感知退化条件下检验系统鲁棒性。</td></tr>
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
<tr><td>2026-09-22</td><td>SparseNav: Instruction-conditioned Sparse Semantic Perception for Training-Free Vision-Language Navigation<br><a href='http://arxiv.org/pdf/2609.26408'>论文</a></td><td>SparseNav提出一种免训练、指令条件下的稀疏语义感知框架，用于视觉语言导航，遵循“少即是多”原则。它仅持续维护轻量级几何BEV地图和稀疏地标记忆，并按需获取语义，避免无关对象累积带来的计算浪费和表示干扰。
◆ 通过指令管理器跟踪导航进度并识别当前活跃的地标查询，实现以子指令决定什么值得定位。
◆ 采用指令条件感知机制，仅在查询地标可见且其度量位置能影响下一步决策时，才调用开放词汇分割。
◆ 地标记忆支持VLM在混合前沿与局部方向路点候选中进行选择，无需额外训练。
在R2R-CE和RxR-CE Val-Unseen上分别达到42.8%和40.7%成功率，并成功部署于Unitree Go2四足机器人，在无预建地图的多种室内环境中验证有效。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vpr'>Robot VPR</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-07</td><td>Fast and Robust Teach-and-Repeat Navigation Using MixVPR Visual Place Recognition*<br><a href='http://arxiv.org/pdf/2610.09631'>论文</a></td><td>本文针对现有深度学习 teach-and-repeat 导航计算量大、实际部署受限的问题，提出了基于 MixVPR 视觉地点识别的新型导航系统。该系统面向长期移动机器人导航，可在非结构化和动态环境中完成定位与重复路径跟踪。  
◆ 将现代视觉地点识别方法 MixVPR 引入 teach-and-repeat 框架，实现快速且鲁棒的视觉定位。  
◆ 在保持与先进系统相当的导航精度和鲁棒性同时，显著降低计算与硬件需求。  
◆ 通过真实室内外环境测试验证了系统的通用性，使其适合多种机器人平台和实际应用。  
实验表明，该系统兼具高精度、强鲁棒性和低部署门槛，为实用化 teach-and-repeat 导航提供了高效方案。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='archive'>归档</h2>

> [点击查看所有历史论文归档](./docs/archive.md)


<h2>GitHub 实验室仓库监控</h2>

<h3>HKU-MARS (港大火星实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5245</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4715</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2465</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1652</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1624</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1522</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1351</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1306</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1092</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>1057</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>949</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>813</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>784</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>747</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>744</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>729</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>689</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>670</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>634</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>622</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>613</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>584</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>570</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>536</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>509</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>466</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>462</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>366</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>350</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>279</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>273</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>258</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>243</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>229</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>223</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>212</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>209</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>150</td><td>iBTC</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2879</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1673</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1368</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1096</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1060</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>882</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>712</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>669</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>666</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>625</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>605</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>578</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>573</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>572</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>555</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>519</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>512</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>465</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>456</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>453</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>335</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>317</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>312</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>302</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>288</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>279</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>258</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>224</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>208</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>202</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>187</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>177</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>170</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>169</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>160</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>156</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>143</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>139</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/data-driven-dynamics'>data-driven-dynamics</a></td><td>134</td><td>Data Driven Dynamics Modeling for Aerial Vehicles</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>132</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
<tr><td><a href='https://github.com/ethz-asl/phaser'>phaser</a></td><td>132</td><td>A robust pointcloud registration pipeline based on</td></tr>
<tr><td><a href='https://github.com/ethz-asl/ssc_exploration'>ssc_exploration</a></td><td>112</td><td>Incremental 3D Scene Completion for Safe and Effic</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waypoint_navigator'>waypoint_navigator</a></td><td>108</td><td>Stand-alone waypoint navigator</td></tr>
<tr><td><a href='https://github.com/ethz-asl/active_grasp'>active_grasp</a></td><td>108</td><td>Closed-loop next-best view planning for grasp dete</td></tr>
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
> 更新于: 2026.10.08
