# 计算机视觉领域最新论文 (2026.07.09)

> 每日自动更新计算机视觉领域的最新arXiv论文

> 使用说明: [点击查看](./docs/README.md#usage)

<details>
<summary>分类目录</summary>
<ol>
<li><a href='#slam'>SLAM</a></li>
<li><a href='#sfm'>SFM</a></li>
<li><a href='#image-matching'>Image Matching</a></li>
<li><a href='#obstacle-avoidance'>Obstacle Avoidance</a></li>
<li><a href='#navigation'>Navigation</a></li>
<li><a href='#motion-planning'>Motion Planning</a></li>
<li><a href='#sensor-calibration'>Sensor Calibration</a></li>
<li><a href='#sensor-undistortion'>Sensor Undistortion</a></li>
<li><a href='#archive'>归档</a></li>
</ol>
</details>

<h2 id='slam'>SLAM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-08</td><td>GeoGS-SLAM: Geometry-Only Gaussian Splatting for Dense Monocular SLAM<br><a href='http://arxiv.org/pdf/2607.07452'>论文</a></td><td>本文提出GeoGS-SLAM,一种基于纯几何高斯泼溅的稠密单目视觉SLAM系统。针对现有3DGS方法同时建模外观和几何的问题,作者提出SLAM任务中场景几何比新视角合成更关键的核心洞察,由此设计只保留空间参数的高斯表示。

创新点如下:
◆ 提出Geometry-only Gaussian Splatting(GeoGS)表示,仅保留空间参数,使每个基元的参数量减少超过80%,显著降低高斯数量,加快几何收敛并提升对光照变化的鲁棒性。
◆ 设计单视图与多视图几何及光度联合监督的训练框架,并提出局部平面驱动的初始化策略,使高斯基元更好地对齐局部结构,加速几何收敛。
◆ 针对回环闭合,提出地图全局更新策略,通过整体变换高斯地图与校正后的位姿对齐,避免现有方法中逐视角位姿校正不一致导致的地图撕裂问题。
◆ 在合成和真实数据集上的实验表明,该方法在在线建图效率和几何重建质量上均优于当前最先进方法。</td></tr>
<tr><td>2026-07-08</td><td>PLED-VINS: A Point-Line Event-Based Visual Inertial SLAM for Dynamic Environments<br><a href='http://arxiv.org/pdf/2607.07374'>论文</a></td><td>PLED-VINS是一种面向动态环境的单目事件相机视觉惯性SLAM框架，旨在解决传统事件SLAM假设静态场景以及缺乏特征可靠性估计的问题。

◆ 提出基于事件时间统计的熵-近因性分数图，用以刻画点和线特征的时序可靠性。

◆ 设计统一的点-线鲁棒BA几何可靠性估计模块，同时评估两类特征的观测质量。

◆ 提出自适应权重策略，将时序与几何可靠性融合，并针对线特征引入运动条件可靠性建模，有效抑制运动物体和快速运动产生的不稳定观测。

◆ 在多个动态数据集上的实验表明，PLED-VINS在含运动物体的场景中显著提升了状态估计精度与鲁棒性。</td></tr>
<tr><td>2026-07-08</td><td>Dynamic Object Detection and Tracking in Construction: A Fisheye Camera and LiDAR Sensor Fusion Model<br><a href='http://arxiv.org/pdf/2607.06896'>论文</a></td><td>本文针对建筑工地复杂环境下机器人动态目标检测与跟踪问题，提出了一种基于鱼眼相机与激光雷达融合的新型框架。该方法搭载于四足机器人平台，利用向上安装的鱼眼相机结合LiDAR传感器实现实时感知，通过在已配准的点云中识别运动物体，并将三维坐标投影到二维柱面全景图上完成语义标签分配。系统将图像实时检测结果与点云投影对齐，作为卡尔曼滤波的观测更新，从而无需依赖大量预训练神经网络和复杂后处理即可实现高精度的动态目标跟踪。该方法特别擅长处理目标在动态与静态状态之间切换的过渡场景，具有简洁、鲁棒的特点，适合在真实建筑环境中部署应用。

◆ 提出向上安装的鱼眼相机与LiDAR融合方案，部署于四足机器人实现全方位实时感知
◆ 采用三维点云投影到二维柱面全景图的方法实现语义标签自动分配，避免复杂后处理
◆ 融合图像检测与点云投影作为卡尔曼滤波观测更新，无需依赖大规模预训练网络
◆ 专门针对动态与静态状态切换场景优化，提升建筑工地等复杂环境的跟踪稳定性...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-07</td><td>CILC: Cryptographically-secure Inter-agent Loop Closure Candidate Detection for Multi-Agent Collaborative SLAM<br><a href='http://arxiv.org/pdf/2607.06700'>论文</a></td><td>该论文针对多智能体协作SLAM中全局描述符交换的隐私泄露问题,提出了一种基于安全多方计算(SMPC)的加密回环候选检测系统CILC。研究首先揭示了加密无线电无法防御被攻陷的群体成员,恶意代理可从公开的全局描述符中重建诚实代理的图像与轨迹信息。

◆ 提出首个利用安全多方计算(SMPC)实现跨代理回环检测隐私保护的系统CILC,无需以明文形式交换全局描述符即可识别回环候选。

◆ 采用&quot;局部加密&quot;的隐私-开销权衡策略,仅对计算量小但隐私敏感的全局描述符相似度比较步骤应用SMPC,而非保护整个CSLAM流水线,从而在保证安全性的同时维持实时性能。

◆ 验证了CILC在多模态全局描述符(视觉与LiDAR)下的通用性,并通过仿真与硬件实验证明其在信息泄露防御、实时性及通信可行性方面均表现优异。</td></tr>
<tr><td>2026-07-07</td><td>MiLSD: A Micro Line-Segment Detector for Resource-Constrained Devices<br><a href='http://arxiv.org/pdf/2607.06600'>论文</a></td><td>该论文针对资源受限设备提出亚兆字节级线段检测器MiLSD，系统研究了紧凑模型下精度与内存的权衡关系。

◆ 提出MiLSD检测器，采用轻量全卷积骨干网络，整体参数量控制在1MB以内，可在MCU上部署。

◆ 提出F-Clip中心-长度-角度输出表示形式，在小模型规模下学习效果显著优于其他表示。

◆ 系统分析不同比特宽度量化的影响，发现8-bit量化可保持全精度性能，而4-bit量化在角度回归上退化严重，量化感知训练仅能部分恢复。

◆ 设计多种推理增强策略，包括亚像素解码、测试时增强和轻量级验证器。

◆ 在ShanghaiTech Wireframe上将sAP10从10.6提升至24.1，显著优于同参数量基线，绘制了跨表示、位宽、容量和后处理策略的精度-内存权衡图谱。</td></tr>
<tr><td>2026-07-07</td><td>Hilti-Trimble-Oxford Dataset: 360 Visual-Inertial Benchmark with Floor Plan Priors for SLAM and Localization<br><a href='http://arxiv.org/pdf/2607.06464'>论文</a></td><td>本文针对建筑工地自动进度监测的需求，发布了一个高质量的360度视觉惯性数据集，涵盖某建筑项目八个月间七个楼层的三十条视觉惯性序列，真实反映了光照变化、工人移动、快速运动和重复结构等实际挑战。

◆ 数据集采用高精度的LiDAR-惯性SLAM系统作为地面真值，与360相机刚性连接，在施工环境中同时提供视觉惯性数据和激光真值轨迹，结合楼层平面先验信息，支持SLAM和楼层平面参考定位两类任务。

◆ 论文还组织了公开研究挑战赛，吸引了62支队伍参与SLAM评估、22支队伍参与定位评估，并报告了全球顶尖系统的基准结果。

◆ 挑战赛结果揭示了楼层平面参考定位在建筑环境中仍具较高难度，定位误差明显高于SLAM，凸显了该领域研究的必要性。

该数据集和基准已公开，将为视觉SLAM、定位及建筑进度监测的持续研究提供重要支撑。</td></tr>
<tr><td>2026-07-07</td><td>APVI-SLAM: Real-Time Acoustic-Pressure-Visual-Inertial Localization and Photorealistic Mapping System in Complex Underwater Environment<br><a href='http://arxiv.org/pdf/2607.06222'>论文</a></td><td>APVI-SLAM是一个面向复杂水下环境的实时多传感器融合SLAM系统，旨在解决传统视觉惯性SLAM在极端水下场景中因特征退化导致的定位发散问题。系统融合了声学、压力、视觉与惯性四类传感器数据，实现了高精度水下定位与逼真建图。

◆ 提出可靠性感知定位框架，动态重加权各传感器估计器，并采用滑动窗口冻结策略从跟踪失败中恢复，显著提升了系统在视觉间歇性失效下的鲁棒性。

◆ 设计了基于四叉树引导的高效建图模块，支持增量式水介质建模与三维高斯优化，可实时生成高保真水下场景重建。

◆ 构建了首个珊瑚礁测绘基准数据集，提供同步的多模态数据，弥补了水下建图评估基准的空白。

◆ 在公开与自建数据集上的大量实验表明，APVI-SLAM在定位精度与重建质量上均达到当前最优水平，同时保持实时运行速度。</td></tr>
<tr><td>2026-07-07</td><td>Why does Deep Learning Improve Visual SLAM?<br><a href='http://arxiv.org/pdf/2607.06023'>论文</a></td><td>本文针对深度学习在视觉SLAM中表现优异这一现象,系统性地探究了其性能提升的根本原因。通过控制变量实验,作者对比分析了学习式二维数据关联、不确定性建模以及循环神经网络架构三者各自对系统性能的影响。研究发现,深度学习视觉SLAM系统的成功主要依赖于学习式二维数据关联及其不确定性建模,而非循环架构本身。这一结论强调了数据关联和不确定性学习在SLAM系统设计中的关键作用,为未来基于学习的SLAM研究指明了方向。

◆ 提出了针对深度学习视觉SLAM的受控实验分析方法,系统拆解了数据关联、不确定性建模与循环架构三个组件的独立贡献。

◆ 通过消融实验揭示了学习式二维数据关联与不确定性建模是性能提升的核心因素,而循环架构并非关键。

◆ 论证了基于学习的范式在SLAM关键组件设计中的必要性,为后续研究提供了明确的设计指导。

◆ 承诺开源代码,促进该领域研究方法的可复现性与进一步探索。</td></tr>
<tr><td>2026-07-06</td><td>Geometry-Aware Visual Odometry for Bronchoscopic Navigation via High-Gain Observer Fusion<br><a href='http://arxiv.org/pdf/2607.05162'>论文</a></td><td>本文针对导航支气管镜中视觉里程计在纹理缺乏、镜面反射和管腔消失点等场景下易跟踪失败的问题，提出了一种几何感知的视觉里程计框架。

◆ 创新点一：利用气道管腔的消失点线索，将检测到的管腔反投影为三维射线并通过加权融合获得稳定的前进方向估计，弥补了纯视差线索不足时的航向漂移。

◆ 创新点二：结合基于looming效应的速度估计，使用定制的高增益观测器将航向与速度信息与噪声较大的视觉里程计输出进行融合，引入气道跟随先验并主动抑制漂移。

◆ 创新点三：在体外机械通气人肺上以电磁跟踪为真值进行验证，相比ORB-SLAM2、LoFTR-VO和DPVO等主流方法，绝对轨迹误差降低超过50%，相对位姿误差在所有测试序列中均最低。

该工作摆脱了对术前CT和外部传感器的依赖，为重症监护和资源受限环境下的纯视觉支气管镜导航提供了可扩展的解决方案。</td></tr>
<tr><td>2026-07-07</td><td>Amplitude-Independent Robust Snapshot 6-D Radio SLAM via a Uniffed Angle-Delay Formulation<br><a href='http://arxiv.org/pdf/2607.04847'>论文</a></td><td>本文针对双基地快照无线电SLAM问题，提出了一种幅值无关的鲁棒方法，可在单次多径信道快照中联合估计用户设备6维位姿与时钟偏差并重构环境散射点。

◆创新点一：构建了LoS与单次反射NLoS路径的统一角度-时延公式，粗估计阶段无需依赖路径幅值或路径损耗进行LoS预分类，直接基于几何一致性筛选内点，对标定误差和传播模型失配具有更强鲁棒性。

◆创新点二：通过twist-swing两阶段遍历初始化与SO(3)上局部精炼，将方法推广到一般3维/6维位姿估计。

◆创新点三：精炼阶段采用Jacobian行均衡的迭代重加权最小二乘结合QAIC模型比较，自动检测LoS路径并联合优化UE状态与散射点。

◆创新点四：理论分析了公式特有的局部秩性质及其在路径身份未知条件下的最小集配置。</td></tr>
<tr><td>2026-07-06</td><td>SLAM: Structured and Localized Analytic Manifold Adaptation for Lifelong VPR<br><a href='http://arxiv.org/pdf/2607.04764'>论文</a></td><td>本文针对终身视觉位置识别（VPR）任务中持续适应新环境且避免灾难性遗忘的难题，提出了SLAM框架，即结构化局部化解析流形自适应方法。该框架将不确定性感知平滑（无迹变换）、拓扑空间划分（高斯混合模型）以及H∞鲁棒边界优化优雅地统一为单一的闭式解析递推形式。大量消融实验表明，不确定性平滑与局部映射的协同组合（U+G配置）达到了27.5%的最优标称精度。

◆ 提出统一的解析递推框架，将无迹变换、GMM拓扑划分与H∞鲁棒优化融合为单一闭式解，避免了架构分裂。
◆ 引入GMM进行拓扑空间分区，实现局部化映射，显著提升标称定位精度至27.5%。
◆ 推导H∞数学保证的极小极大鲁棒边界，无需改变网络架构即可通过单一正则化参数灵活调节精度与抗扰动之间的内在权衡。</td></tr>
<tr><td>2026-07-06</td><td>DIVO: Continuous-time DVL-Inertial-Visual Odometry for Unmanned Underwater Vehicles<br><a href='http://arxiv.org/pdf/2607.04615'>论文</a></td><td>本文提出了一种面向无人水下航行器(UUV)的声学-视觉-惯性融合定位系统DIVO,基于连续时间轨迹估计框架,旨在应对水下复杂环境下的定位难题。

◆ 首次将基于高斯过程的连续时间轨迹估计框架应用于DVL、立体相机和IMU的异步多传感器融合,实现无需时间同步的灵活集成。

◆ 提出了一种新颖的视觉前端,采用基于学习的特征提取与匹配方法,能够有效应对水下光照衰减、照明变化和颗粒物干扰等特殊挑战。

◆ 框架设计具备良好的模块化和可扩展性,可无缝集成其他传感器模态,且无需针对不同环境重新配置。

◆ 在真实水下巡检数据集上进行了广泛测试,系统在精度、鲁棒性和轨迹覆盖范围方面均优于当前最先进的视觉-惯性和声学-视觉-惯性SLAM算法。

值得注意的是,即便仅构建短期的视觉数据关联,DIVO仍能取得优于现有方法的性能,凸显了连续时间融合框架的优势。</td></tr>
<tr><td>2026-07-05</td><td>Real-Time LiDAR Gaussian Splatting SLAM<br><a href='http://arxiv.org/pdf/2607.04127'>论文</a></td><td>本文提出了一种基于激光雷达的实时高斯泼溅SLAM框架，通过紧耦合快速G-ICP配准与球面光栅化稠密建图，实现大规模场景下的实时三维重建。该方法利用激光雷达的几何特性而非外观信息，复用跟踪阶段估计的局部协方差来初始化具有距离感知尺度的高斯，并推导表面法向量以支持几何感知的地图优化。

◆ 提出跟踪-建图紧耦合的LiDAR高斯泼溅SLAM框架，结合G-ICP配准与球面光栅化建图，纯在线运行且速度超过20 FPS。

◆ 复用跟踪估计的局部协方差初始化高斯，采用距离感知尺度并推导法向量，实现几何感知的地图优化。

◆ 引入协方差衍生的几何分数度量局部复杂度，在平面区域进行剪枝、在结构丰富区域选择性加密。

◆ 构建高斯与LiDAR置信度反馈机制，将优化后的地图信息回传以增强跟踪的鲁棒性。

该方法在Newer College数据集上取得86.78%的F-score，验证了其在精度、稳定性与可扩展性方面的优势。</td></tr>
<tr><td>2026-07-03</td><td>E-TraMamba: A New Paradigm for Efficient Long-Term 3D Feature Tracking with Event Cameras<br><a href='http://arxiv.org/pdf/2607.02866'>论文</a></td><td>本文针对事件相机3D特征跟踪中现有CNN和Transformer方法难以高效建模稀疏噪声事件流长程时空依赖的问题，提出了E-TraMamba框架。其核心贡献与创新点如下：

◆ 首次将Mamba状态空间模型引入事件相机3D特征跟踪任务，实现线性复杂度的长程时空建模，显著提升效率。

◆ 设计轻量化的仿射变换预测器，有效应对运动模糊和遮挡场景下的稳定跟踪。

◆ 提出多尺度线索融合方案，将局部时空块、相关性图和位置嵌入统一表征，增强跟踪的稳定性与平滑性。

◆ 构建大规模合成数据集EvD-PointOdyssey，通过单目渲染提供同步的事件流、深度图和精确3D轨迹。

◆ 在多个事件基准上取得最优性能，在严格精度阈值下特征寿命提升超过2倍，跟踪比例更高且RMSE更低，适用于低延迟视觉里程计、实时SLAM及交互式机器人。</td></tr>
<tr><td>2026-07-02</td><td>LuxSQA: Ask Me in Luxembourgish with TTS-Augmented Spoken Question Answering<br><a href='http://arxiv.org/pdf/2607.02763'>论文</a></td><td>该论文针对低资源语言卢森堡语,研究了如何利用文本转语音(TTS)技术为语音问答(SQA)任务生成训练数据,避免依赖大规模人工录音语料。研究团队从现有文本QA资源出发,将问题翻译为卢森堡语后通过多种TTS系统合成语音,并与文本答案配对,采用参数高效的SLAM架构连接冻结的Whisper编码器与多语言大语言模型,显著降低了对人工标注数据的依赖。

◆首次将TTS合成数据应用于卢森堡语低资源SQA任务,系统比较了MMS-TTS、Qwen3-TTS和OmniVoice等多种TTS系统以及单源与多源(4TTS)训练配置,发现多源和基于声音设计的合成训练数据效果最佳。

◆构建了约48k单源和约230k多源合成问答语料,采用冻结Whisper编码器加可学习投影器结合LoRA适配器的参数高效微调策略,在仅有两个真实卢森堡语说话人的LLAMA-LB-Test上验证了方法有效性。

◆揭示了无参考TTS质量评分与下游QA性能不呈单调关系的重要发现,强调合成语音需作为任务特定训练数据而非仅追求自然听感来评估,为低资源语音理解研究提供了新视角。</td></tr>
<tr><td>2026-07-02</td><td>A Stereo Visual SLAM System Using Object-Level Motion Estimation and Geometric Filtering Based on Cross Disparity<br><a href='http://arxiv.org/pdf/2607.02005'>论文</a></td><td>本文提出了一种名为OCD SLAM的动态双目视觉SLAM系统，基于ORB-SLAM2进行扩展，旨在解决动态环境下静态世界假设失效的问题。该系统通过特征级和对象级两个层面联合检测动态元素，实现对静态与动态场景元素的鲁棒分离，从而提升位姿估计精度。

创新点如下：

◆ 提出&quot;交叉视差&quot;（cross disparity）新概念，结合视差信息与时间一致性、立体不一致性，有效识别动态特征点。

◆ 将3D目标检测模块（SMOKE）与基于卡尔曼滤波的目标跟踪相结合，实现对象级运动分类，弥补单一特征级检测的不足。

◆ 在KITTI Odometry和KITTI Raw数据集上的实验表明，该方法在轨迹精度上显著优于ORB-SLAM2及多种当前先进的动态SLAM方法。

◆ 消融实验验证了交叉视差模块的有效性，能够检测出仅依靠3D目标检测方案所遗漏的动态特征。</td></tr>
<tr><td>2026-07-03</td><td>DL-SLAM: Enabling High-Fidelity Gaussian Splatting SLAM in Dynamic Environments based on Dual-Level Probability<br><a href='http://arxiv.org/pdf/2607.01860'>论文</a></td><td>本文针对3D高斯泼溅动态SLAM中存在的瞬态静态物体处理不当问题,提出了基于双层概率框架的DL-SLAM系统。现有方法要么直接丢弃预定义的动态物体,要么将瞬态静态物体错误地整合到静态地图中,造成持续性伪影;此外仅依赖几何信息导致不确定性图中物体边界模糊。

核心创新点如下:

◆ 提出双层概率框架,通过融合语义与几何信息计算像素级动态概率,并将其提升到三维空间聚合成实例级的物体级动态概率。

◆ 基于物体级动态概率对动态高斯进行分类剪枝,生成无伪影的高保真静态语义地图。

◆ 静态地图反向提供几何一致性约束,用于迭代精化像素级动态概率的可靠性,形成闭环优化机制。

◆ 在跟踪精度上较现有方法提升最高达13%,同时保持高保真语义建图质量,验证了双层概率机制在动态环境中的有效性。</td></tr>
<tr><td>2026-07-02</td><td>DL-VINS-Factory: A Modular Framework for Learned Visual Front-Ends in Visual-Inertial SLAM<br><a href='http://arxiv.org/pdf/2607.01757'>论文</a> | <a href='https://github.com/limshoonkit/DL-VINS-Factory-ROS2/'>代码</a></td><td>DL-VINS-Factory是一个模块化视觉惯性SLAM框架,系统整合了多种学习型特征提取器(ALIKED、RaCo、SuperPoint、XFeat)与LK光流跟踪或LightGlue描述子匹配,统一接入基于滑动窗口Ceres的紧耦合后端,并支持AnyLoc DINOv2-VLAD回环检测与4自由度位姿图优化。该工作通过EuRoC、NTU-VIRAL、Botanic Garden和SubT-MRS四个涵盖室内、室外、激进运动和视觉退化场景的数据集进行系统基准测试,实证评估了学习型前端在实时嵌入式VI-SLAM中的实际价值。

◆ 首个统一的模块化框架,系统对比多种学习型特征(ALIKED、RaCo、SuperPoint、XFeat)与LK光流或LightGlue匹配的组合,接入紧耦合Ceres后端
◆ 在EuRoC上,ALIKED+LG相比GFTT+LK基线单目ATE降低5%、带回环双目降低7%
◆ 在NTU-VIRAL激进运动场景下,ALIKED+LG双目带回环ATE降低12%
◆ 集成AnyLoc DINOv2-VLAD回环检测,有效回环数比传统BRIEF+DBoW2提升约2到7倍
◆ 全部配置在Jetson AGX Orin上经TensorRT加速后,单目29至47 FPS、双目18至33 FPS,满足实时性要求

研究发现学习型前端在大多数场景下可行但并非全面优于经典方法,需根据具体环境选择性使用。</td></tr>
<tr><td>2026-06-30</td><td>ForgeDrive: Bidirectional Cross-Conditioning for Unified Visual-Action Generation in Autonomous Driving<br><a href='http://arxiv.org/pdf/2606.31226'>论文</a></td><td>◆提出ForgeDrive，一个统一的自回归扩散框架，将未来建模为逐时刻的“图像帧-动作”对，实现视觉生成与动作规划的紧密耦合。
◆它用act-then-imagine范式替代传统imagine-then-act，避免视觉生成误差先行累积并传递到规划阶段。
◆训练中解耦视觉与动作的扩散时间步，并引入类似UniDiffuser的噪声调度，使模型能在两种模态间双向推断与交叉条件生成。
◆推理时先生成动作，再用动作提升未来帧生成质量，进而反哺下一步动作，形成视觉与行动的闭环增强。
◆模型还加入未来自车状态预测，进一步提升规划能力；在NAVSIM实验中同时统一驾驶仿真、规划和视觉里程计，并优于强基线规划器。</td></tr>
<tr><td>2026-06-30</td><td>TACO: A Test and Check Framework for Robust Pose Graph Optimization<br><a href='http://arxiv.org/pdf/2606.29851'>论文</a></td><td>◆提出TACO（Test And Check Optimization），一个面向鲁棒位姿图优化的在线框架，用于在SLAM中抑制错误回环导致的外点影响。
◆其核心思想不是显式建模内点/外点，而是增量近似寻找最大一致测量集合。
◆“Test”部分设计了增量概率一致性算法IPC，可在线评估每个新回环约束的一致性。
◆“Check”部分提出Switchable Outlier Sanitization，周期性利用Switchable Constraints清理IPC误接纳的不一致约束。
◆实验表明，TACO在2D和3D数据集上兼具接近离线鲁棒方法的精度与在线部署所需的效率，并开源了实现。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-08</td><td>NoDrift3R: Raymap-Guided Coupling for Drift-Robust Unposed Feed-Forward 3D Reconstruction<br><a href='http://arxiv.org/pdf/2607.07168'>论文</a></td><td>该论文针对无位姿前馈三维高斯溅射在长序列中因位姿漂移导致重建质量退化的问题，提出了一种几何与外观显式协同的新框架。作者识别出位姿累积漂移是制约性能的主要瓶颈，并指出SfM伪真值引入传感器噪声、纯渲染监督易陷入局部最优等矛盾。

◆ 提出Raymap-Guided Coupling Module（RGC）模块，将高斯中心锚定到光线图诱导的几何上，在统一目标下联合优化RGB重建、光线图一致性与相机正则化，形成几何与外观之间的双向反馈循环。

◆ 设计Dual-Frequency Viewpoint Scheduling策略，结合由易到难的间隔扩展与短间隔对回放，稳定长时序学习过程。

在域内和跨域数据集上的大量实验表明，该方法在渲染质量与位姿估计上均取得一致提升，长序列鲁棒性显著增强，验证了几何-外观显式协同是实现可扩展、无漂移无位姿前馈三维重建的关键。</td></tr>
<tr><td>2026-07-08</td><td>The MAGPI Survey: Evidence for Non-Universal Resolved Dust Attenuation Relations Beyond the Local Universe<br><a href='http://arxiv.org/pdf/2607.07122'>论文</a></td><td>本文基于MAGPI巡天（0.25&lt;z&lt;0.42）的178个星系，研究了中等红移下尘埃消光（A_V）与恒星形成率面密度（Σ_SFR）的空间分辨关系，并与本地MaNGA样本进行了系统比较。主要发现包括：MAGPI星系同样存在A_V与Σ_SFR的正相关，但在固定Σ_SFR下其消光显著高于本地星系；在匹配恒星质量（M*）和偏离主序程度（ΔSFMS）后，该消光过剩仍然存在；过剩幅度强烈依赖于ΔSFMS——低于主序星系约0.40 mag、位于主序约0.28 mag、高于主序仅约0.07 mag，表明kpc尺度的消光不仅受局部恒星形成活动调控，还受宿主星系整体演化状态的影响。

◆首次将空间分辨的A_V–Σ_SFR定标关系外推至中等红移（z~0.3），揭示该关系并非普适
◆通过ΔSFMS分层分析，阐明星系整体演化状态对局部消光规律的调制作用
◆明确指出本地定标的消光关系需引入红移与星系种群依赖性修正，为后续高红移星系性质解读提供关键校准依据...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-07</td><td>Deep far-UV observations of the ELAIS N1 field using AstroSat: Source catalogue, spectral energy distribution modelling and star formation<br><a href='http://arxiv.org/pdf/2607.06143'>论文</a></td><td>本文利用AstroSat卫星上的紫外成像望远镜(UVIT)对ELAIS N1深场进行了F154W波段(far-UV)的深度观测,总曝光时间达30千秒,通过CCDLAB v3.0进行数据处理,获得了1637个3σ和458个5σ的FUV源目录,极限星等分别为25.69和25.13 mag(AB),为该天区提供了目前最深的FUV测光数据。

◆ 基于多波段交叉匹配,结合光学和红外数据以及光谱/测光红移,采用多波段判据剔除活动星系核(AGN),构建了清洁的恒星形成星系样本。

◆ 使用CIGALE进行SED建模,采用延迟型恒星形成历史(可叠加晚期暴发)、Bruzual &amp; Charlot恒星 population合成、Calzetti消光和SKIRTOR AGN模块,系统地推导了样本的恒星形成率(SFR)、总恒星质量和年轻恒星质量随红移的演化。

研究发现SFR随红移单调上升,符合恒星形成主序(SFMS)的演化趋势,同时年轻质量与总质量比值在0&lt;z≲0.76范围内近似为常数,表明样本中的星系主要以自调节的稳态恒星形成为主,而非星暴主导的演化模式。</td></tr>
<tr><td>2026-07-06</td><td>Reference-Induced Consensus for Selective Posed-Reference Visual Localization<br><a href='http://arxiv.org/pdf/2607.04722'>论文</a> | <a href='https://github.com/SNU-DLLAB/ric_loc'>代码</a></td><td>本文提出RIC-Loc（参考诱导共识定位），一种无需场景训练和SfM预建图的位姿参考定位方法。其核心思想是利用冻结的VGGT模型同时预测查询图像的局部位姿、深度以及查询与参考之间的对应轨迹，每个参考图像诱导生成一个SE(3)假设，通过鲁棒共识机制估计最终位姿，并基于保留的假设结构计算两种可靠性分数。

◆ 摆脱对预计算SfM三维点图、2D-3D匹配和PnP求解的依赖，仅利用已知参考位姿即可实现SfM-free的轻量级定位流程。

◆ 提出假设驱动的双可靠性分数互补机制（空间散布与轨迹条件协方差），在无需真值的条件下实现跨室内、室外及低纹理大场景的失败检测。

◆ 共识估计器无需逐场景训练，在室内与基于结构的定位方法具有竞争力，并优于同类前馈基线，为位姿参考定位提供了有效的选择性操作模式。</td></tr>
<tr><td>2026-07-04</td><td>PRISM3D: Probabilistic Refinement and Robust Initialization for Physically Consistent Scene Modeling under Extreme Motion Blur<br><a href='http://arxiv.org/pdf/2607.03855'>论文</a></td><td>本文针对极端运动模糊图像下的盲三维场景重建难题,提出统一框架PRISM3D,突破了传统SfM在严重退化输入下失效的瓶颈。其核心创新与贡献如下:

◆ 提出基于VGGSfM密集跟踪的鲁棒初始化策略,在特征匹配失败的极端模糊条件下恢复全局拓扑,是首个有效利用该范式从极端运动模糊引导3D高斯泼溅自举的工作。

◆ 提出概率-物理耦合优化方案,采用MCMC进行几何概率致密化以稳健填充稀疏先验,同时通过连续贝塞尔轨迹建模物理图像形成过程,有效避免确定性优化发散。

◆ 进一步提出多模态扩展PRISM3D-E,融合高时间分辨率事件流作为结构先验,显著提升重建保真度。

◆ 同步贡献了PRISM3D-E基准数据集,填补了严重退化条件下配对事件流数据缺失的空白。

大量实验表明,所提RGB单模态框架与多模态扩展均建立了新的最先进性能。</td></tr>
<tr><td>2026-07-03</td><td>Fast 3D Foundation Model Initialized Gaussian Splatting<br><a href='http://arxiv.org/pdf/2607.03209'>论文</a></td><td>本文提出了一种无需传统SfM的快速3D高斯泼溅重建方法,利用3D基础模型进行相机位姿和点云的初始化,并通过深度引导损失函数联合优化位姿与高斯基元,显著提升了收敛速度。实验表明,该方法在Mip-NeRF 360、Tanks and Temples和RobustNeRF数据集上取得了23.61 dB PSNR和0.19 LPIPS的竞争性重建质量,同时将训练时间压缩至每个场景约三分钟,适用于机器人、VR和自动驾驶等近实时应用场景。

◆ 采用3D基础模型替代传统SfM进行相机位姿和点云初始化,摆脱了对COLMAP等耗时预处理流程的依赖。

◆ 提出深度引导损失函数,实现相机位姿与高斯基元的联合优化,即使在50-60张稀疏视角的粗略初始化下也能快速收敛。

◆ 引入基于MLP的位姿精修模块,结合基础模型的深度监督,在稀疏视角场景下进一步提升重建质量。</td></tr>
<tr><td>2026-07-01</td><td>EPO: Boosting 3D Foundation Models with Edge-based Pose Optimization<br><a href='http://arxiv.org/pdf/2607.00579'>论文</a></td><td>EPO是一种针对三维基础模型SfM重建结果的无轨迹几何优化框架，旨在解决这类模型虽然推理速度快但几何精度不足的问题。该方法通过边缘图对齐作为几何优化的代理，完全避免了传统Bundle Adjustment类方法所需的特征提取和轨迹构建过程，是一个完全可微的优化框架。实验证明，EPO在多个数据集和任务上能够匹配甚至超越Bundle Adjustment类方法的精度，同时显著降低了运行时间和内存占用。值得注意的是，EPO的内存需求大幅减少，使其能够在消费级硬件上运行，而竞品的精修方法则无法实现。

◆ 创新点一：提出无轨迹优化思路，使用边缘图对齐替代传统特征轨迹，避免了耗时的特征提取与匹配步骤。
◆ 创新点二：设计完全可微的优化框架，将边缘对齐作为几何优化的代理信号，实现端到端优化。
◆ 创新点三：在精度匹配或超越Bundle Adjustment的同时，大幅降低运行时与内存开销，支持消费级硬件部署。</td></tr>
<tr><td>2026-07-01</td><td>Planar-SfM: Camera Pose Estimation via Homography Graph Embeddings<br><a href='http://arxiv.org/pdf/2606.31979'>论文</a></td><td>◆论文提出Planar-SfM，将传统SfM中被视为退化问题的平面场景转化为可利用的几何约束来源。

◆其核心思想是利用多视图中每个可见平面，通过单应性分解独立估计相对相机位姿。

◆方法构建基于单应性估计的位姿图，并引入谱嵌入来识别和剔除不可靠边。

◆该框架可将几何与视觉一致性映射到实线上，从而高效提取最大一致生成树用于位姿恢复。

◆实验表明，该方法在篮球场等高度平面场景中显著优于传统方法，同时在IMC Phototourism等通用三维场景中达到或超过现有最优水平。</td></tr>
<tr><td>2026-07-01</td><td>AnyMatch: Supercharging Universal Multi-Modal Image Matching with Large-Scale Single-View Images<br><a href='http://arxiv.org/pdf/2606.31077'>论文</a></td><td>◆ AnyMatch提出一种利用海量单视图图像生成多模态匹配训练数据的新框架，显著降低对昂贵真实几何标注数据的依赖。
◆ 它结合单目深度估计、3D重投影、扩散式修复和跨模态图像翻译，合成具有多视角、多模态特征的图像对。
◆ 其关键创新在于通过显式3D重投影生成严格满足几何一致性的标注，避免SfM-MVS流程中的误差累积。
◆ 该框架具备强可扩展性，可通过输入图像和相机参数控制场景多样性与匹配难度。
◆ 作者构建了大规模合成数据集Any-syn，并验证其能显著提升LoFTR、EDM、RoMa等模型在多模态匹配任务中的泛化性和鲁棒性。</td></tr>
<tr><td>2026-06-29</td><td>Emergence of a Shared Canonical Object Frame from In-the-Wild Videos<br><a href='http://arxiv.org/pdf/2606.30058'>论文</a> | <a href='https://github.com/Fischer-Tom/Emergent-Canonical-Frame/'>代码</a></td><td>◆ 论文提出一种从野外物体视频中自监督学习共享规范物体坐标系的方法，避免了传统方法对人工规范姿态标注的依赖。
◆ 核心创新是将所有训练序列通过共享几何瓶颈，即一个不含类别细节的粗略规范网格，从而促使不同实例对齐到共同框架。
◆ 方法学习图像像素到规范网格的稠密对应关系，并利用SfM得到的噪声相机几何估计每个视频序列的对齐变换。
◆ 共享规范框架并非显式监督得到，而是从多视角一致性和预训练特征提取器的语义先验中自然涌现。
◆ 在16万个野外物体视频上训练后，该方法在类别级姿态估计基准上达到与依赖规范姿态监督的方法相竞争的性能，显著提升了可扩展性。</td></tr>
<tr><td>2026-06-26</td><td>RayPE: Ray-Space Positional Encoding for 3D-Aware Video Generation<br><a href='http://arxiv.org/pdf/2606.27345'>论文</a></td><td>◆论文指出现有视频DiT的RoPE仅编码(u,v,t)采样网格，缺乏场景3D几何信息，并将相机射线的Plücker互易积与注意力点积建立联系。
◆提出RayPE，将每个token的6D Plücker射线坐标加性注入自注意力的Query和Key，实现射线空间位置编码。
◆设计Query/Key翻转结构，使对称恒等配置下的几何注意力精确对应Plücker互易积。
◆证明注意力分数可分解为内容项、几何项及两类交叉项，实验表明这些组成均不可或缺。
◆为适配不同尺度的相机平移数据，解耦方向与矩量幅值，并引入log幅值门控和RMSNorm稳定训练。
◆该模块参数增量低于0.1%、可零初始化接入预训练视频DiT，并提升相机可控性、跨帧3D一致性和视频质量。</td></tr>
<tr><td>2026-06-25</td><td>PanoImager: Geometry-Guided Novel View Synthesis and Reconstruction from Sparse Panoramic Views<br><a href='http://arxiv.org/pdf/2606.27071'>论文</a></td><td>◆ PanoImager针对稀疏全景图在旋转主导、弱视差场景下SfM/SLAM初始化不稳定的问题，提出了一个无需SfM的三维重建框架。
◆ 方法将全景图分解为局部透视视图，并利用前馈式位姿与深度先验提供初始几何约束。
◆ 通过几何条件扩散模型合成辅助新视角，补充稀疏输入中缺失的观测信息。
◆ 结合深度引导的3D Gaussian Splatting优化，提升跨视角一致性并稳定重建过程。
◆ 实验表明，该方法在极端稀疏全景输入下具有更好的鲁棒性，可作为SfM/SLAM失败时的离线地图细化组件。</td></tr>
<tr><td>2026-06-22</td><td>The EDGE-CALIFA Survey: Star Formation Efficiency and Galaxy Quenching across 62 Main Sequence, Green Valley, and Red Galaxies<br><a href='http://arxiv.org/pdf/2606.23649'>论文</a></td><td>◆ 本文发布GBT-EDGE CO(1-0)巡天，首次用绿岸望远镜系统绘制62个近邻CALIFA星系的分子气体分布，覆盖主序、绿谷和红序星系。

◆ 研究创新性地结合CO观测与CALIFA积分场光谱，统一估计分子气体质量、恒星形成率、金属丰度和恒星质量面密度。

◆ 论文量化发现主序、绿谷和红色星系的分子气体耗尽时间依次显著增加，表明星系越偏离主序，恒星形成效率越低。

◆ 通过测试多种CO-H2转换因子，作者证明SFE下降趋势具有稳健性，不依赖特定转换因子假设。

◆ 核心结论是，部分淬火星系并非缺乏分子气体，而是保留可观气体储备但形成恒星效率低，可能源于低气体密度和形态淬火共同作用。</td></tr>
<tr><td>2026-06-22</td><td>G-MASt3R-SfM: Graph-based View Pruning and Multi-stage Optimization for Robust SfM<br><a href='http://arxiv.org/pdf/2606.22856'>论文</a></td><td>◆ 提出G-MASt3R-SfM，一种面向鲁棒Structure from Motion的新流程，针对MASt3R在非重叠图像对上产生错误匹配的问题进行改进。
◆ 设计Graph-based View Pruning模块，利用匹配置信度构建场景图，并通过几何一致性剪除异常视图和不可靠连接。
◆ 提出Multi-Stage Optimization模块，从局部一致性逐步扩展到全局一致性，分阶段优化相机参数，降低外点对整体估计的影响。
◆ 相比直接使用MASt3R匹配结果的MASt3R-SfM，该方法能更有效抑制错误对应关系带来的噪声和位姿退化。
◆ 在ETH3D数据集上取得相机位姿估计和三维重建的先进精度，验证了其在复杂匹配条件下的鲁棒性和实用价值。</td></tr>
<tr><td>2026-06-20</td><td>ACEsplat: Accelerated 3D Gaussian Scene Regression via RGB and Poses Only<br><a href='http://arxiv.org/pdf/2606.22091'>论文</a></td><td>◆ACEsplat提出了一种仅依赖RGB图像和相机位姿的逐场景3D Gaussian Splatting重建框架，避免了SfM点云、深度图等外部几何先验。
◆其核心创新是用自监督场景坐标回归模块在4–5分钟内构建内部几何先验，提升现场部署的鲁棒性。
◆论文进一步设计轻量级高斯初始化头，将SCR特征与坐标先验融合，为后续3DGS优化提供更好的初始表示。
◆在Wayspots、Cambridge Landmarks和RealEstate10K等数据集上，方法在静态视角渲染和稀疏视角新视角合成中取得有竞争力的画质。
◆整个场景映射与3DGS重建可在单GPU上15–25分钟完成，适合机器人和混合现实中的快速场景搭建。</td></tr>
<tr><td>2026-06-15</td><td>MotionPyramid: Hierarchical Motion Representation and Residual Interfaces<br><a href='http://arxiv.org/pdf/2606.20705'>论文</a></td><td>◆提出MotionPyramid，将类感知层级的表示思想引入运动控制，从数据中学习从即时电机命令到长时程行为片段的多层动作表征。
◆方法以运动跟踪教师为起点，训练递归潜变量解码器，使高层潜变量可经低层展开为 temporally extended 的全身运动程序。
◆预训练后的层级被冻结，并作为下游强化学习策略的多种动作接口，支持不同控制分辨率的复用。
◆实验表明，粗粒度接口能加速早期学习并提升运动规律性，细粒度接口则保留反馈控制能力和最终任务精度。
◆论文还提出Residual Interfaces，使策略可同时使用粗层运动程序与细层残差修正，在结构化抽象和可控性之间取得平衡。</td></tr>
<tr><td>2026-06-16</td><td>Neural Tree Reconstruction for the Open Forest Observatory<br><a href='http://arxiv.org/pdf/2606.18153'>论文</a></td><td>◆本文面向开放森林观测站（OFO）的低成本无人机森林制图需求，指出现有基于传统运动恢复结构（SfM）的3D树木重建存在伪影多、细节不足和林下区域重建困难等问题。
◆论文的核心贡献是探索将神经辐射场（NeRF）等神经3D重建方法引入OFO数据流程，以提升森林三维地图质量。
◆其创新点在于利用NeRF对稀疏视角更鲁棒、可融入数据驱动先验的特点，改善传统航拍影像在复杂森林场景中的重建局限。
◆论文强调高质量3D树木重建对下游生态与气候应用的重要性，如野火模拟、碳汇监测和再造林规划。
◆此外，作者还提出未来将OFO平台扩展到支持更多先进3D视觉模型，为开放、可复用的森林制图工具链奠定基础。</td></tr>
<tr><td>2026-06-15</td><td>MVM-IOD: An Industrial Object-Centric Benchmark Dataset for the Evaluation of 3D Reconstruction Methods<br><a href='http://arxiv.org/pdf/2606.16638'>论文</a></td><td>本文针对工业3D重建缺乏真实场景数据集的问题，提出了机器视觉测量工业物体数据集MVM-IOD，核心创新点如下：
◆构建了首个面向典型工业物体的多视角基准数据集，包含9种物体与2种背景组合的18个场景，并提供高精度参考3D点云与相机位姿。
◆设计了系统化的数据采集方案，利用工业机械臂末端搭载相机沿半球轨迹精准拍摄，真实还原工业视觉检测设定。
◆全面评估了SfM、MVS、前馈模型及2D高斯溅射等现有先进方法，为工业场景的3D重建与位姿估计建立了基准。
◆揭示了此类工业图像会导致前馈方法出现分布外问题，验证了简单预处理可缓解该问题，为工业应用前馈方法提供了重要警示。</td></tr>
<tr><td>2026-06-13</td><td>PEARLS: NuSTAR and XMM-Newton Extragalactic Survey of the JWST North Ecliptic Pole Time Domain Field VI: Multiwavelength SED Analysis<br><a href='http://arxiv.org/pdf/2606.15365'>论文</a></td><td>本文对北黄极时间域场261个X射线源进行多波段SED分析，结合恒星形成主序与黑洞吸积率框架，揭示了星系与超大质量黑洞的演化联系。
◆发现相对于主序的恒星形成率与比AGN光度存在强相关性，具有最高比AGN光度的星系位于或高于主序。
◆揭示X射线光度与恒星形成率强相关，证认出符合短时标剧烈吸积事件的冷类星体群。
◆提出低质量星系呈现高于种群均值的快速生长期吸积，而高质量星系表现为维持模式吸积。
◆证明传统活动星系核分类无法揭示这些区别，凸显了X射线视角识别罕见且关键的AGN瞬时阶段的独特能力。</td></tr>
<tr><td>2026-06-16</td><td>Fast Speech Foundation Model Distillation Using Interleaved Stacking<br><a href='http://arxiv.org/pdf/2606.11766'>论文</a></td><td>本文探索了语音基础模型蒸馏的训练加速问题，旨在加快模型部署速度。
现有的堆叠方法虽然能通过逐渐增加模型深度来加速训练，但会导致模型性能下降。
◆提出了一种名为交错堆叠的新型方法，在堆叠过程中始终保持层位置不变。
◆该方法有效保留了语音基础模型每层编码的独特层特有知识，解决了传统堆叠导致的性能退化问题。
在SUPERB基准上的实验验证了该方法能在加速蒸馏训练的同时有效保持模型性能。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-07</td><td>MiLSD: A Micro Line-Segment Detector for Resource-Constrained Devices<br><a href='http://arxiv.org/pdf/2607.06600'>论文</a></td><td>这篇论文针对资源受限设备（尤其是MCU级微控制器）提出了MiLSD微型线段检测器，核心目标是在亚兆字节内存预算下最大化线段检测精度。作者系统比较了三种输出表征方式，发现所提出的F-Clip中心点-长度-角度公式在小型模型上学习效果最佳。实验表明8位量化可保持全精度性能，而4位量化会造成显著退化，尤其体现在角度回归任务上，量化感知训练仅能部分弥补精度损失。MiLSD在1MB激活预算下，配合亚像素解码、测试时增强和轻量验证器等推理增强策略，将ShanghaiTech Wireframe数据集上的sAP10从10.6提升至24.1。

创新点：
◆ 提出F-Clip中心点-长度-角度输出表征，在小模型规模下学习效率最优
◆ 首次系统性地在亚兆字节预算下探究线段检测的精度与内存权衡关系
◆ 设计面向MCU的推理增强策略（亚像素解码、TTA、轻量验证器）显著提升小模型性能
◆ 全面分析不同比特宽度、模型容量和后处理策略对嵌入式视觉系统的影响...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-06</td><td>Hybrid Deep Learning for Traceability and Classification of Industrial Slate Tiles<br><a href='http://arxiv.org/pdf/2607.04811'>论文</a></td><td>这篇论文针对板岩瓦片工业生产中的实例重识别与产地分类问题,提出了一种轻量级混合深度学习框架,将图像匹配与分类任务统一在单一架构中。研究者构建了一个包含2610张图像、涵盖6个开采场地的板岩瓦片工业数据集,填补了该领域公开数据的空白。在实例匹配分支中,采用XFeat特征提取与LightGlue匹配头相结合,使匹配性能AUC提升15.4%。在分类分支中,通过共享并融合两个骨干网络的特征,相较标准MobileNetV3准确率提升10.9%。实验结果验证了所提方法在工业场景下对自然材料视觉变异的鲁棒性和实用性。

◆ 提出统一的混合深度学习框架,将特征匹配与分类任务融合于单一架构
◆ 利用XFeat与LightGlue组合实现工业级实例重识别
◆ 设计双骨干特征共享与融合机制以提升分类精度
◆ 构建首个板岩瓦片工业数据集(2610张图像,6个产地)</td></tr>
<tr><td>2026-07-03</td><td>A Vision Based System for Guided and Collaborative Reconstruction of Fragmented Documents<br><a href='http://arxiv.org/pdf/2607.03621'>论文</a></td><td>本论文提出了一种基于视觉的协作式碎片文档实时重建系统,用于文化遗产保护中的破损纸质文档复原。系统采用协作机器人配合专门设计的真空吸附装置,能够轻柔精准地定位纸片,对8平方厘米的碎片实现0.57毫米的定位重复精度,有效避免对脆弱文物的损伤。该系统支持两种工作模式:人工操作结合视觉引导,以及机器人全自动定位,为使用者提供灵活的交互选择。研究者系统评估了多种局部特征匹配方法在不同文档类型、旋转缩放及破损程度下的表现,发现无检测器的SE2-LoFTR方法在受损及光学变异的档案材料上表现出最强的鲁棒性。论文的主要创新点可概括如下:

◆ 设计了专用真空吸附末端执行器,使协作机器人能够安全处理易碎的纸质文物碎片,实现毫米级精确定位。

◆ 构建了人机协作的双模式重建框架,支持视觉辅助手动操作与全自动重建灵活切换。

◆ 系统比较了多种特征匹配算法在碎片拼接任务中的性能,验证了SE2-LoFTR对受损和光学退化文档的优越鲁棒性,为实际应用提供了方法选择依据。</td></tr>
<tr><td>2026-07-01</td><td>AnyMatch: Supercharging Universal Multi-Modal Image Matching with Large-Scale Single-View Images<br><a href='http://arxiv.org/pdf/2606.31077'>论文</a></td><td>◆论文提出AnyMatch框架，用低成本、易获取的单视图图像生成多视角、多模态图像匹配训练数据，缓解真实大规模标注数据稀缺问题。
◆方法结合单目深度估计、显式3D重投影、扩散式修复和跨模态图像翻译，同时保证外观多样性与几何一致性。
◆其标注由3D重投影直接产生，避免了传统SfM-MVS流程中的误差累积，更适合训练精确匹配模型。
◆AnyMatch具备强可扩展性，可通过输入图像、相机参数和视角设置控制场景多样性与匹配难度。
◆基于该框架构建的Any-syn数据集显著提升LoFTR、EDM、RoMa等模型在多模态匹配基准上的泛化性和鲁棒性。</td></tr>
<tr><td>2026-06-29</td><td>MF-UAVPose6D: A Model-Free Monocular 6-DoF Pose Estimation Framework for Fixed-Wing UAVs<br><a href='http://arxiv.org/pdf/2606.29697'>论文</a></td><td>◆ 提出MF-UAVPose6D，一个面向固定翼无人机的无模型单目6-DoF位姿估计框架，推理时仅需RGB图像和相机内参，无需CAD模型或关键点先验。
◆ 通过热图引导的中心定位获得稳定目标锚点，提升非合作目标在复杂视角和远距离条件下的检测与定位可靠性。
◆ 设计Perspective-Aware Module建模观测射线先验，使网络更好理解单目成像中的透视几何关系。
◆ 引入Dynamic Topological Sampling，补充机翼、机身、尾翼等弱结构线索，增强对固定翼外形拓扑的利用。
◆ 采用平移与旋转解耦的位姿解码机制，并构建FW-UAV6DPose合成数据集；实验表明该方法在旋转估计、深度恢复和整体位姿评估上兼具精度、效率与鲁棒性。</td></tr>
<tr><td>2026-06-26</td><td>KM-Speaker: Keypoint-Based Style Control for High-Quality Speech-Driven 3D Facial Animation and Dialogue Localization<br><a href='http://arxiv.org/pdf/2606.28568'>论文</a></td><td>◆ KM-Speaker提出一种基于关键点条件的流式生成框架，用参考表演同时实现全局风格引导和逐帧级表情控制。
◆ 该方法面向高质量语音驱动3D面部动画，解决现有可控模型依赖低质量野外数据而损害真实感的问题。
◆ 论文设计了解耦策略，将音频驱动的唇部运动与关键点驱动的上半脸动态分离，提升唇同步与表情控制精度。
◆ 通过全局风格上下文保持机制，模型能在细粒度控制下维持完整面部表现的一致性和连贯性。
◆ 实验表明，KM-Speaker在数据受限场景下仍优于现有方法，尤其在唇同步、风格遵循和对话本地化的时序表情匹配方面表现突出。</td></tr>
<tr><td>2026-06-22</td><td>G-MASt3R-SfM: Graph-based View Pruning and Multi-stage Optimization for Robust SfM<br><a href='http://arxiv.org/pdf/2606.22856'>论文</a></td><td>◆论文提出G-MASt3R-SfM，针对MASt3R在非重叠图像对上产生错误匹配、进而影响SfM位姿估计的问题，构建了更鲁棒的SfM流程。
◆其核心创新之一是Graph-based View Pruning模块，利用匹配置信度构建场景图，并结合几何一致性剔除离群视图和不可靠连接。
◆第二个创新是Multi-Stage Optimization模块，通过从局部一致性到全局一致性的逐阶段优化，逐步细化相机参数。
◆该方法避免将错误匹配直接纳入全局优化，从源头上抑制噪声传播，提高了复杂场景下的位姿估计稳定性。
◆在ETH3D数据集上的实验表明，G-MASt3R-SfM在相机位姿估计和三维重建精度上达到当前最优水平。</td></tr>
<tr><td>2026-06-18</td><td>Evaluation of Image Matching for Art Skills Assessment<br><a href='http://arxiv.org/pdf/2606.20199'>论文</a></td><td>◆本文提出一种基于图像匹配的绘画技能评估方法，通过比较手绘作品与原始模板的相似度来量化绘画水平。

◆研究将计算机视觉用于替代传统人工评估，降低了评估过程的复杂性和主观性。

◆论文实现并对比了SIFT特征匹配与孪生网络两类图像相似度方法。

◆实验结果表明，利用图像相似度评估艺术技能是可行的，能够反映绘画与模板之间的差异。

◆关键发现是SIFT关键点匹配在该任务中表现更有效，更适合用于检测和衡量绘画技能。</td></tr>
<tr><td>2026-06-10</td><td>SalArt-VQA: Diagnosing Whether VLMs Understand Salient Artifacts in Generated Images<br><a href='http://arxiv.org/pdf/2606.12671'>论文</a></td><td>这篇论文针对视觉语言模型(VLMs)在AI生成图像伪影检测中的细粒度理解能力进行了诊断性研究。作者指出,尽管VLMs在图像级伪影检测上表现良好,但其判断可能依赖错误的视觉线索或区域,导致正确结论背后隐藏着推理失败。为此,论文构建了SalArt-VQA基准,包含950张图像和3681道人工标注的多项选择题,覆盖伪影图像、真实参考图像和配对生成参考图像,从存在性检测、语义定位、空间定位和证据支撑的缺陷识别四个维度系统评估模型。对20个VLMs的测试揭示,最强模型虽达到99.37%的检测召回率,但仅在53.26%的图像上同时答对四类问题,且模型存在敏感性与校准之间的权衡。

◆ 提出首个面向AI生成图像显著伪影细粒度理解的诊断性基准SalArt-VQA,填补了仅依赖图像级检测准确率所掩盖的评估盲区。
◆ 设计四类对齐问题(存在性检测、语义定位、空间定位、证据支撑的缺陷识别),系统检验VLMs的伪影判断是否建立在局部视觉证据之上。
◆ 引入伪影图像、真实参考图像和配对生成参考图像三类对照划分,可定量评估模型在无伪影场景下的校准能力与拒答行为。
◆ 揭示了VLMs普遍存在的敏感性-校准权衡现象:敏感模型易做出无依据的伪影声明,保守模型则通过漏检来规避误报。
◆ 实验证明高检测准确率并不等同于具备扎实的伪影理解能力,为后续模型改进指明方向。</td></tr>
<tr><td>2026-06-02</td><td>SAMatcher: Co-Visibility Modeling with Segment Anything for Robust Feature Matching<br><a href='http://arxiv.org/pdf/2606.03406'>论文</a></td><td>该论文提出SAMatcher框架，将图像匹配问题转化为共视性建模问题，通过预测跨视图共视区域作为结构化先验来指导匹配。
◆突破传统像素级匹配局限，首次利用共视区域掩码和边界框作为结构化先验进行对应点估计。
◆提出基于SAM的对称跨视图交互机制，实现双向特征交换与跨视图语义对齐。
◆设计统一监督方案，通过掩码学习、框回归及掩码-框一致性约束联合优化掩码预测与框定位。
实验表明该方法在大视角和尺度变化下优势显著，证明了单目分割基础模型可有效扩展至多视图推理，为图像匹配提供了新视角。</td></tr>
<tr><td>2026-05-30</td><td>BEVIO: Efficient Bird&#x27;s-Eye-View based Sparse-Update Visual-Inertial Odometry for Lunar Day-Night Navigation<br><a href='http://arxiv.org/pdf/2606.00709'>论文</a></td><td>本文针对月球漫游车计算资源受限及昼夜自带光源下特征关联困难的挑战，提出了基于鸟瞰图的稀疏更新视觉惯性里程计BEVIO。
◆提出基于鸟瞰图的图像匹配方案，有效增强了对更大帧间运动的鲁棒性。
◆在显著视觉外观变化下实现了更可靠的特征匹配，克服了夜间自带光源照明的干扰。
◆支持在极稀疏视觉更新率下进行可靠的里程计估计，大幅降低了对计算资源和功耗的依赖。
通过高保真月球仿真和半比例漫游车在真实环境中的长期昼夜部署实验，验证了该方法在低至0.25赫兹更新频率下仍能实现可靠的昼夜导航。</td></tr>
<tr><td>2026-07-01</td><td>SOCO: Benchmarking Semantic Object Correspondence in Vision Foundation Models<br><a href='http://arxiv.org/pdf/2605.31597'>论文</a></td><td>本文提出SOCO基准，旨在解决视觉基础模型中结构化对象理解评估协议不一致和部件级监督有限的问题。
◆构建了包含对应类型分类法的语义对象对应基准，在100个类别和超百万对应对上提供一致且具功能意义的关键点标注。
◆引入关键点语言描述，支持对大型视觉语言模型细粒度部件级理解能力的系统评估。
◆揭示视觉骨干网络虽编码强语义结构，但跨类别迁移对应能力差且仅部分捕获部件位置。
◆发现大视觉语言模型擅长文本提示定位但视觉参考跨图匹配较弱，暴露语言接地与视觉对应间的鸿沟。
◆证明对应性能比ImageNet分类性能更能强有力地预测分割、跟踪及3D检测等密集下游任务的表现。</td></tr>
<tr><td>2026-05-22</td><td>MASt3R-Nav: WayPixel Navigation in Relative 3D Maps<br><a href='http://arxiv.org/pdf/2605.24111'>论文</a></td><td>本文提出了一种基于像素相对连通性的新型地图表示方法MASt3R-Nav，实现了无需全局几何一致性的高精度几何导航。
◆提出像素相对连通性地图表示，既保留了局部几何准确性，又避免了传统3D地图对全局几何一致性的依赖。
◆通过图像对相对3D坐标系中的像素对应关系构建图像间连通性，从而从图像序列生成地图。
◆通过对图像内像素连通性进行近似和稀疏化，实现了基于像素级图的全局路径规划。
◆推导出路点像素代价图表示，并训练以此为条件的控制器来预测轨迹。
实验证明，基于相对几何的密集像素级代价图比图像或对象级条件变量更准确，在多种任务中显著提升了导航能力。</td></tr>
<tr><td>2026-05-11</td><td>3DReflecNet: A Large-Scale Dataset for 3D Reconstruction of Reflective, Transparent, and Low-Texture Objects<br><a href='http://arxiv.org/pdf/2605.10204'>论文</a></td><td>◆ Accurate 3D reconstruction of objects with reflective, transparent, or low-texture surfaces still remains notoriously challenging.
◆ Such materials often violate key assumptions in multi-view reconstruction pipelines, such as photometric consistency and the availability on distinct geometric texture cues.
◆ Existing datasets primarily focus on diffuse, textured objects, and therefore provide limited insight into performance under real-world material complexities.</td></tr>
<tr><td>2026-05-06</td><td>Creative Robot Tool Use by Counterfactual Reasoning<br><a href='http://arxiv.org/pdf/2605.05411'>论文</a></td><td>◆ We propose a causal reasoning framework for creative robot tool use where a suitable tool for a task is correctly identified for use beyond its primary objectives.
◆ The proposed framework first discovers the causal relationships between the tool and the task by conducting simulated experiments in a dynamics model.
◆ We decouple the causal discovery problem into two complementary components: VLM-based feature suggestion and counterfactual tool generation via targeted geometric and physical feature perturbations.</td></tr>
<tr><td>2026-05-02</td><td>SIFT-VTON: Geometric Correspondence Supervision on Cross-Attention for Virtual Try-On<br><a href='http://arxiv.org/pdf/2605.01296'>论文</a> | <a href='https://github.com/takesukeDS/SIFT-VTON'>代码</a></td><td>◆ Diffusion-based virtual try-on methods achieve photorealistic synthesis through cross-attention mechanisms that transfer garment features to target body regions.
◆ However, these approaches rely on implicit learning of spatial correspondences, struggling to preserve fine details such as text and illustrations.
◆ We propose a novel approach, which we call SIFT-VTON, that utilizes SIFT keypoint matching to provide explicit geometric guidance for diffusion-based virtual try-on.</td></tr>
<tr><td>2026-05-01</td><td>TrueEBSD in MTEX: automatic image matching for correlative microscopy applications<br><a href='http://arxiv.org/pdf/2605.00703'>论文</a></td><td>◆ TrueEBSD is an open-source MATLAB program for image alignment and spatial distortion correction of images and electron backscatter diffraction (EBSD) maps.
◆ We have re-implemented TrueEBSD as an add-on to MTEX, an established toolbox for EBSD data analysis.
◆ Spatial alignment enables correlative analysis methods, such as augmenting EBSD orientation maps with data from other imaging modes.</td></tr>
<tr><td>2026-05-29</td><td>MAPRPose: Mask-Aware Proposal and Amodal Refinement for Multi-Object 6D Pose Estimation<br><a href='http://arxiv.org/pdf/2604.20650'>论文</a></td><td>本文针对杂乱场景中严重遮挡和噪声导致的6D姿态估计难题，提出了MAPRPose两阶段框架。
◆在姿态提案阶段，将2D对应关系提升至3D空间建立可靠关键点匹配，基于对应级评分生成几何一致的姿态假设选出Top-K候选。
◆在细化阶段引入AMPR模块，通过重建完整物体几何与动态调整ROI，有效缓解重度遮挡下的定位误差和空间错位。
◆设计GPU加速的RGB-XYZ重投影机制，在张量化渲染比较管线中实现单次前向传播同步细化所有姿态假设。
该方法在BOP基准上取得76.5%的最优平均召回率，精度超越FoundationPose 3.1%，且多目标推理速度提升43倍。</td></tr>
<tr><td>2026-05-01</td><td>Are Pretrained Image Matchers Good Enough for SAR-Optical Satellite Registration?<br><a href='http://arxiv.org/pdf/2604.10217'>论文</a></td><td>◆ Cross-modal optical-SAR (Synthetic Aperture Radar) registration is a bottleneck for disaster-response via remote sensing, yet modern image matchers are developed and benchmarked almost exclusively on natural-image domains.
◆ We evaluate twenty-four pretrained matcher families--in a zero-shot setting with no fine-tuning or domain adaptation on satellite or SAR data--on SpaceNet9 and two additional cross-modal benchmarks under a deterministic protocol with tiled large-image inference, robust geometric filtering, and tie-point-grounded metrics.
◆ Our results reveal asymmetric transfer--matchers with explicit cross-modal training do not uniformly outperform those without it.</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='obstacle-avoidance'>Obstacle Avoidance</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-08</td><td>Social-spatial dependencies for learning visual navigation<br><a href='http://arxiv.org/pdf/2607.07460'>论文</a></td><td>本论文研究了社会性生物视觉导航中的社会-空间依赖关系,通过训练基于神经网络的智能体在不同社会情境下进行导航来探索这一机制。智能体根据相对任务表现和空间效应学习社会依赖性,高质量社会信息的增加会驱动导航策略从独立型向跟随型再到避碰型发生相变。面对可预测且非平稳的环境动态,智能体在远端和近端表现出独立与社会导航之间的行为混合。该研究挑战了仅观察社会性生物个体行为的传统方法,强调应采取自下而上的视角理解生物行为。

创新点:
◆ 提出社会-空间依赖驱动的视觉导航学习框架
◆ 发现社会信息质量触发的导航策略相变机制
◆ 揭示非平稳环境下独立与社会导航的行为混合现象
◆ 强调自下而上研究社会性...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-08</td><td>GeoGS-SLAM: Geometry-Only Gaussian Splatting for Dense Monocular SLAM<br><a href='http://arxiv.org/pdf/2607.07452'>论文</a></td><td>论文针对密集视觉SLAM问题,观察到机器人下游任务(如导航、避障)更依赖准确的几何信息而非逼真渲染,据此提出仅依赖几何的3D高斯泼溅方法GeoGS及对应的SLAM系统GeoGS-SLAM。
◆ 提出GeoGS表示,仅保留空间参数,使每个基元参数量减少超80%,显著降低高斯基元数量、加速几何收敛并增强对光照变化的鲁棒性。
◆ 设计单视图与多视图几何及光度监督的训练框架,结合局部平面驱动的初始化策略,使高斯基元更好地对齐局部结构,加快几何收敛。
◆ 针对回环闭合提出地图全局更新策略,通过整体变换高斯地图对齐校正后的位姿,避免现有方法中因逐视点位姿校正不一致造成的地图撕裂。
实验表明该方法在合成和真实数据集上的在线建图效率和几何重建质量均优于现有最优方法。</td></tr>
<tr><td>2026-07-06</td><td>Dynamic Airspace Management for UAVs in Evolving Urban Environments: Collaborative Coordination and Human Safety<br><a href='http://arxiv.org/pdf/2607.04825'>论文</a> | <a href='https://github.com/pharos-anonymized/source-code.git'>代码</a></td><td>本文针对城市低空经济中无人机安全飞行的关键挑战,提出了名为Pharos的协同多无人机空域管理系统,旨在解决复杂城市地形和人口密集环境下的避碰与人员安全问题。Pharos采用介于分布式局部感知与集中式精细化控制之间的混合范式,协调共享空域中多架无人机的安全并行飞行,并创新性地将人类恐惧心理纳入决策考量。该系统基于MAPPO多智能体强化学习算法实现,相较于HAPPO和HATRPO等同类算法具有更快的收敛速度和更高的奖励回报。作者基于真实城市数据构建了三维仿真平台进行评估,可视化结果验证了其有效的空域协调能力,人类恐惧程度较基准方法Ipopt降低52.72%。

◆ 提出了Pharos协同空域管理系统,首次将人类恐惧心理作为决策因素纳入多无人机空域管理,平衡了分布式与集中式控制范式的优劣。
◆ 创新性地引入空间熵作为系统评估指标,量化空域利用效率,较Ipopt和A-star分别提升70.82%和2.03%。
◆ 基于MAPPO算法实现快速收敛与高效协同,并搭建了基于真实城市数据的三维仿真验证平台。</td></tr>
<tr><td>2026-07-05</td><td>GPU-Accelerated Polygonal Signed Distance Functions for Real-Time Collision Avoidance<br><a href='http://arxiv.org/pdf/2607.04310'>论文</a></td><td>该论文针对基于优化的局部规划与控制中碰撞约束计算瓶颈问题，提出了一种多边形符号距离函数（PSDF）及其在模型预测控制中的集成方法。

◆ 提出了PSDF，用于计算凸多边形机器人轮廓与边界边障碍物之间的几何精确符号距离，避免了传统方法的近似误差
◆ 设计了无权重、无分支的张量化几何流水线，支持批处理GPU执行和自动微分，便于高效并行计算
◆ 提出了PSDF-MPC控制器，将PSDF嵌入基于序列二次规划的实时迭代方案，通过局部线性化阶段安全约束实现实时避障
◆ 采用CPU/GPU分离架构，GPU负责批量PSDF值与梯度计算，CPU求解维度仅由系统状态和预测时域决定的稀疏二次规划

实验结果表明，PSDF在查询效率上优于传统基线方法，并在密集多边形环境中保持了实时可行性和鲁棒的避障性能。</td></tr>
<tr><td>2026-07-05</td><td>Integrated Graph Search and Model Predictive Control for Smooth and Efficient Path Planning in Autonomous Vehicles<br><a href='http://arxiv.org/pdf/2607.04259'>论文</a></td><td>本文针对自动驾驶车辆路径规划中安全性、舒适性、动力学可行性与计算效率难以兼顾的问题，提出一种将图搜索与模型预测控制（MPC）相结合的序列式路径规划框架。该方法首先通过Dijkstra算法在离散栅格上获得粗略路径，并以此构建一个空间变化的凸型横向安全走廊，将离散的避障决策转化为连续的可行性约束。在该走廊内构建MPC优化问题，通过惩罚横向偏移的三阶空间导数来保证路径平滑性，并在预测时域内实现高效求解。该方法在高保真仿真环境CarMaker中的多车超车场景下进行验证，覆盖直道与弯道及单车、多车情形。

创新点如下：

◆提出图搜索与MPC深度融合的序列规划框架，显式利用图搜索的拓扑结构引导后续优化过程。

◆将Dijkstra粗路径转化为空间变化的凸型横向安全走廊，实现避障约束从离散到连续的转换。

◆在MPC代价函数中引入三阶空间导数惩罚项，在保证可行性的同时提升路径平滑性与乘坐舒适性。

◆在多种超车场景下，相较基于多项式拟合与二次规划的方法，同时降低横向加速度、曲率与冲击度，并减少约28%–30%的计算耗时。</td></tr>
<tr><td>2026-07-05</td><td>Anytime Plug-and-Play Control with Contract-Based Distributed MPC<br><a href='http://arxiv.org/pdf/2607.04215'>论文</a></td><td>本文针对多机器人系统中通信拓扑时变这一核心挑战，提出了一种基于局部通信的分布式多智能体控制算法。该方法支持智能体随时加入或离开通信网络，无需中心协调，具备&quot;即插即用&quot;特性。算法通过基于距离的邻居定义和基于预测轨迹的契约约束实现高效扩展，并保证碰撞避免与约束满足。创新点包括：◆ 基于距离的邻居定义机制，使算法能够随智能体数量高效扩展；◆ 引入由预测轨迹生成的契约约束，确保安全性和可行性；◆ 支持任意时刻智能体自由加入或离开网络，无需集中协调；◆ 完全分布式的模型预测控制框架，突破传统集中式方法的局限。该方法在高速对向行驶的多车驾驶场景中得到了仿真和真实实验的双重验证。</td></tr>
<tr><td>2026-07-03</td><td>GDPR-Aware Trajectory Sharing for ISAC-Assisted Robot Navigation: A Case Study on FID-Constrained Collision Prediction<br><a href='http://arxiv.org/pdf/2607.03254'>论文</a></td><td>本文针对集成感知与通信(ISAC)系统中行人轨迹共享引发的隐私合规问题，提出了一种基于费雪信息密度(FID)约束的轨迹共享机制，用于辅助机器人导航中的碰撞预测。研究将GDPR第5(1)(c)条数据最小化原则和第5(1)(f)条完整性保护要求形式化为可量化的技术措施，在轨迹数据共享前根据局部信息含量进行差异化扰动，而非采用固定误差扰动。在真实行人轨迹数据集上的实验表明，FID控制的共享策略在相同的漏检冲突率下，能够持续降低攻击者的重构信息泄露并缩短持续暴露长度，从而实现更优的隐私-效用权衡。该工作将信息论指标作为隐私度量与法规要求的桥梁，验证了信息感知扰动可作为符合GDPR原则的工程化隐私保护手段。

◆ 将费雪信息密度引入轨迹共享机制，实现基于局部信息含量的自适应扰动，替代传统固定误差扰动。

◆ 将GDPR数据最小化与完整性条款形式化为可量化的技术指标，使法规要求与信息论隐私度量相衔接。

◆ 在真实行人轨迹上验证了FID约束方案在隐私-效用权衡上严格优于固定误差扰动策略。</td></tr>
<tr><td>2026-07-03</td><td>Hope for the Best, Prepare for the Worst: Occlusion-Aware Contingency Planning for Autonomous Vehicles<br><a href='http://arxiv.org/pdf/2607.03155'>论文</a></td><td>本文针对自动驾驶车辆在城市遮挡场景下面临的安全挑战，提出了一种形式化的遮挡感知轨迹规划框架。核心思想是&quot;抱最好的希望，做最坏的准备&quot;，即在假设可能存在隐藏交通参与者的前提下规划轨迹。该方法基于作者前期工作，利用可达性分析顺序推断被遮挡交通参与者的可能状态，并集成基于树的运动规划器，对未来观测存在与缺失两种情况同时进行推理。在保持碰撞避免安全保证的前提下，该框架有效降低了规划的保守性，使车辆能够主动且高效地应对遮挡场景。

◆ 提出形式化的遮挡感知轨迹规划框架，将可达性分析与树形运动规划相结合，保证在存在隐藏交通参与者时仍能避免碰撞。
◆ 引入基于树的规划方法，能够对未来的观测及观测缺失进行显式推理，从而区分&quot;乐观&quot;与&quot;悲观&quot;分支。
◆ 在保持安全性的同时显著降低传统遮挡处理方法的保守性，使自动驾驶行为更加主动高效。
◆ 通过具有挑战性的仿真遮挡场景验证了框架的有效性，为城市自动驾驶的安全部署提供了新的解决方案。</td></tr>
<tr><td>2026-07-02</td><td>RCOA Extension and Applications<br><a href='http://arxiv.org/pdf/2607.02797'>论文</a></td><td>本文针对避障最优控制问题中的凸优化难题,对RCOA(松弛凸避障)方法进行了重要扩展与应用。RCOA是首个实现完全凸形式避障最优控制的方法,其收敛分析表明该方法在障碍物超出预测视界时仍能保持避障有效性,这是区别于其他方法的关键特性。

本文的主要创新点如下:

◆ 将RCOA从二维环境扩展到三维空间,并成功应用于无人机(UAV)导航任务,拓宽了方法的适用范围。

◆ 改进RCOA公式以融入车辆几何形状,突破传统质点模型的限制,实现了三维实体之间的碰撞避免,显著提升了实际应用的真实性。

◆ 数值仿真证明RCOA在计算性能上达到或超越现有最优方法,并能使非线性模型预测控制器(NMPC)在缩短预测视界的条件下完成狭窄通道中的激进机动,实时控制频率超过30赫兹,验证了其工程实用价值。</td></tr>
<tr><td>2026-07-01</td><td>Neuro-Symbolic Safety Guidance for Vision-Language-Action Models via Constrained Flow Matching<br><a href='http://arxiv.org/pdf/2607.01378'>论文</a></td><td>本文针对视觉-语言-动作(VLA)模型在机器人操控中缺乏有效安全机制的问题,提出了一种基于神经-符号融合的安全引导方法。现有安全方法仅能防止机器人下一步动作的碰撞,属于被动反应式防护,而该工作通过在流匹配去噪过程中引入约束优化,实现了对整条预测轨迹的前瞻式安全分析。

◆ 核心创新在于将安全约束建模为最小范数约束优化问题,在流匹配去噪的每一步迭代中对中间轨迹进行符号化修正,从而在碰撞不可避免之前提前进行干预。

◆ 方法通过神经轨迹生成与符号约束满足的交替执行,使系统具备预测性碰撞规避能力,显著区别于传统的反应式安全策略。

◆ 在SafeLIBERO基准上,该方法达到82.8%的碰撞避免率和81.6%的任务成功率,较单步方法分别提升6.3%和19.8%,且在长时序任务中因复合分布偏移而获益最为显著。</td></tr>
<tr><td>2026-07-01</td><td>Distributed Containment of a Compromised Agent through Repulsive Cages<br><a href='http://arxiv.org/pdf/2607.01230'>论文</a></td><td>本文针对多智能体系统中合法智能体被劫持后的安全控制问题，提出了一种基于&quot;排斥笼&quot;的分布式围控框架。其核心思路是绕过传统检测与隔离策略，转而利用被入侵智能体底层仍正常工作的避障模块作为间接驱动通道。

◆ 提出将防御者对受损智能体的围控问题建模为在线Stackelberg博弈，防御者作为领导者，攻击者作为跟随者通过高层指令做出反应。

◆ 利用支撑函数和法锥工具，给出鲁棒单步围控的精确几何刻画，并提出&quot;排斥笼&quot;概念，以此构建集中式Stackelberg预言机。

◆ 设计了一种仅依赖局部通信和动态场估计的完全分布式在线近似算法，并证明其相对于集中式基准具有次线性动态遗憾界，量化了网络估计误差与时变最优解的影响。

◆ 通过仿真验证了所提框架在将受损智能体限制在允许区域内并引导至期望目标方面的有效性，理论与实验结果一致。</td></tr>
<tr><td>2026-07-01</td><td>FastBridge: Closing the Model-Based Realization Gap in Safety Filters on 3D Gaussian Splatting for Fast Quadrotor Flight<br><a href='http://arxiv.org/pdf/2607.01200'>论文</a></td><td>针对四旋翼快速飞行中的安全避障问题，本文提出FastBridge方法，弥补了现有3D高斯泼溅（3DGS）安全滤波器在模型层面的实现差距。核心贡献与创新如下：
◆ 基于完整四旋翼非线性动力学设计执行器感知的安全滤波器，突破以往单/双积分器简化模型忽略执行器限制与瞬时响应的假设。
◆ 推导高相对阶的碰撞锥指数控制屏障函数（CBF），为3DGS场景提供连续且几何感知的避障保障。
◆ 提出基于前向仿真备份策略的备份CBF，在输入约束下保持二次规划（QP）的可行性，确保安全可达性。
◆ 相比现有最优3DGS安全滤波器，轨迹抖动降低47%，运行速度提升2.25倍，并在仿真与真实硬件上验证了杂乱环境中的实时导航能力。</td></tr>
<tr><td>2026-07-01</td><td>Robots Ask the Way: Communication-Enabled Social Navigation<br><a href='http://arxiv.org/pdf/2607.01044'>论文</a></td><td>本文提出了一种新的社交导航任务CommNav,使机器人能够在多智能体环境中主动向人类求助以定位目标个体,突破了传统方法仅关注反应式避障的局限。

◆ 首次提出通信使能的社交导航任务CommNav,机器人可主动向居民询问目标人物最近出现的位置、动向等信息。

◆ 构建了Habitat 3.0c仿真环境,在Habitat 3.0基础上扩展了多人类交互与信息交换协议。

◆ 在现有最优社交导航模型中引入通信模块COMM,使Episode Success提升10个百分点,并提出通信预训练代理任务,有效应对交互信号稀疏的挑战。

◆ 通过LLM生成指令与人本研究收集的口语化指令进行训练,验证了策略对自然人类语言具有高度鲁棒性,效果与使用完美结构化数据时统计上无显著差异。</td></tr>
<tr><td>2026-06-29</td><td>Multi-UAV Formation Cooperative Obstacle Avoidance and Adaptive Shape Deformation Control in Complex Environments Based on BI-APF-RRT and Affine Transformation<br><a href='http://arxiv.org/pdf/2606.29755'>论文</a></td><td>◆论文提出一种融合BI-APF-RRT与仿射变换的多无人机编队协同避障方法，兼顾复杂环境中的避障灵活性与编队完整性。
◆采用目标偏置的双向APF-RRT替代传统APF质心规划，提升全局路径搜索效率并降低陷入局部最优的风险。
◆通过改进人工势场与三次B样条插值，增强质心路径的平滑性、收敛速度和可飞行性。
◆引入包含非均匀缩放与旋转的仿射变换矩阵，使编队能根据障碍物距离自适应变形。
◆设计分布式跟踪控制律，使跟随者协同跟踪领航者，实现编队在不解散的情况下安全穿越复杂障碍区域。</td></tr>
<tr><td>2026-07-08</td><td>LAMP: Long-Horizon Adaptive Manipulation Planning for Multi-Robot Collaboration in Cluttered Space<br><a href='http://arxiv.org/pdf/2606.29358'>论文</a></td><td>◆论文提出LAMP框架，面向密集杂乱空间中的长时域多机器人协同操作，联合考虑接触构型、机器人运动、耦合动力学与避碰。

◆核心创新是将学习到的生成式操作模型嵌入规划过程，从而在完整的物体—机器人耦合空间中进行更可 tractable 的搜索。

◆提出LAMPA*规划器，系统化搜索长时域任务中的接触与运动决策，避免仅规划简化物体轨迹带来的局限。

◆提出LAMP-Lazy惰性规划器，通过延迟评估降低计算开销，支持实时重规划。

◆实验表明，该方法能解决以往强化学习或短视接触原语方法难以处理的高密度、长时域多机器人操作任务。</td></tr>
<tr><td>2026-06-27</td><td>When Stopping Fails: Rethinking Minimal Risk Conditions through Human-Interactive Autonomous Driving for Safe Transportation Systems<br><a href='http://arxiv.org/pdf/2606.29115'>论文</a></td><td>◆论文指出，自动驾驶现有“最小风险状态”过度依赖减速或停车，虽能降低碰撞风险，却可能引发交通阻塞、影响应急通行和造成无障碍问题。
◆作者基于公开案例分析AV停车行为失效与人车交互失败，并从感知、规划、控制三个层面建立事件分类框架。
◆论文创新性地将“理解人类权威与社会交通规则”纳入AV安全框架，强调不能只关注物理避障。
◆研究总结了人机交互感知、语言指令理解、无障碍规划、远程协助与遥操作等新方向。
◆核心贡献在于提出从被动停车式安全转向人类交互式自治，以支持AV在复杂城市道路中的可靠部署。</td></tr>
<tr><td>2026-06-27</td><td>LNN-Fly: Continuous-Time UAV Navigation for Robust Obstacle Avoidance under Timing Mismatch<br><a href='http://arxiv.org/pdf/2606.28827'>论文</a></td><td>◆本文提出LNN-Fly，一种面向真实部署的连续时间LiDAR无人机避障导航策略，重点解决仿真到现实中的时间不匹配、传感不规则和控制频率变化问题。
◆其核心创新是将动态规划启发的结构化循环更新、显式控制间隔Δt条件化，以及输入驱动的自适应遗忘门结合起来。
◆该遗忘门能在接近障碍时快速刷新陈旧隐状态，同时在持续机动中保持时序一致性。
◆训练阶段引入可微分 rollout，并模拟真实部署中的感知扰动和时序扰动，从而提升鲁棒性。
◆实验表明，LNN-Fly在低控制频率、稀疏观测和控制周期抖动下表现更稳，并能从简化仿真零样本迁移到真实四旋翼，室内跨频率测试20次飞行成功率达100%。</td></tr>
<tr><td>2026-06-27</td><td>Hierarchical Decision Making with Structured Policies: A Principled Design via Inverse Optimization<br><a href='http://arxiv.org/pdf/2606.28764'>论文</a></td><td>◆提出一种原则化的分层决策框架，将高层目标抽象与低层结构化优化策略系统结合，用于复杂控制任务分解。

◆针对现有RL难以严格满足约束、OC方法短视且计算昂贵的问题，构建了兼顾安全约束与决策效率的分层RL-OC架构。

◆核心创新是引入逆优化方法，从专家示范中学习低层优化问题的目标结构，使低层策略与长期任务目标保持一致，而非依赖启发式设计。

◆该方法提升了低层决策的可解释性和任务相关性，同时保留优化控制在约束处理方面的优势。

◆在网络资源分配和连续碰撞规避任务中，实验表明该框架在效率和决策质量上均优于端到端RL、学习增强OC和现有分层RL基线。</td></tr>
<tr><td>2026-06-27</td><td>Vision-Language Models for Deployable Social Robot Navigation: Bridging Semantic Reasoning and Low-Level Control<br><a href='http://arxiv.org/pdf/2606.28760'>论文</a></td><td>◆本文系统梳理了视觉语言模型在可部署社会机器人导航中的作用，强调其可弥补传统导航缺乏语义理解与社会常识推理的不足。
◆论文提出统一视角，将相关方法划分为高层VLM语义推理、低层规划控制，以及连接二者的中间机制。
◆核心创新在于构建了一条VLM与导航系统耦合的结构化路线图，涵盖语义评估、空间落地、中间表示和控制模块。
◆论文强调实际部署需要混合架构，把VLM的推理能力与实时、安全、可验证的控制系统结合。
◆此外，论文综述了SRN相关数据集与评测平台，并总结了可靠性、实时性、安全性和社会合规性等开放挑战。</td></tr>
<tr><td>2026-06-26</td><td>Bearing-based Circumnavigation with Collision Avoidance in Time-varying Graphs under Limited Target Information<br><a href='http://arxiv.org/pdf/2606.27719'>论文</a></td><td>◆论文研究了异构多智能体对静止目标的分布式环绕问题，并将智能体建模为具有半径的圆盘，更贴近真实物理约束。
◆在目标信息受限条件下，仅少数领导者可直接获取目标位置，跟随者只依赖交互图中指定出邻居的局部信息实现协同。
◆提出了一种仅控制角速度的基于方位的分布式制导律，适用于静态和时变最近邻交互拓扑。
◆通过引入对数型障碍李雅普诺夫函数，显式保证智能体间避碰，并证明无碰撞集合的前向不变性。
◆理论上证明在可行初始条件下，每个跟随者最终会围绕其有向路径末端领导者所对应的同一目标实现环绕运动，仿真验证了方法在不同拓扑下的有效性。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-08</td><td>Social-spatial dependencies for learning visual navigation<br><a href='http://arxiv.org/pdf/2607.07460'>论文</a></td><td>本文研究了社会性生物在视觉导航任务中的社会-空间依赖关系。研究团队训练了由独立神经网络控制的智能体，在不同社会情境中进行导航，社会依赖程度和策略选择由相对任务表现和空间效应决定。

研究发现，当高质量社会信息增加时，智能体的导航策略会发生相变，从独立导航转向跟随行为，并在拥挤觅食区域演化出避碰策略。此外，在可预测的非平稳环境中，智能体会在远端和近端分别发展出独立与社会导航的行为混合模式。

本研究的核心贡献与创新点如下：

◆ 提出自下而上的研究框架，通过独立训练的神经网络智能体研究社会导航行为，避免了仅从群体行为出发的局限性。

◆ 揭示了社会信息质量驱动的导航策略相变现象，从个体导航→跟随→避碰的阶段性转变。

◆ 发现可预测环境动态会引发个体与社会导航的行为混合模式。

◆ 强调社会-空间依赖关系对理解社会性生物行为的关键作用，挑战了仅分析个体行为的传统研究方法。</td></tr>
<tr><td>2026-07-08</td><td>Behavior Foundations for Quadruped Robots: ABot-C0 Technical Report<br><a href='http://arxiv.org/pdf/2607.07370'>论文</a></td><td>ABot-C0是面向四足机器人的通用运动控制系统，通过数据、策略、部署三层互补的行为基础，解决动物运动数据稀缺和跨本体迁移脆弱两大核心难题。

◆ 构建多源运动数据金字塔，综合条件视频生成合成、标注动作捕捉、遥操作与人工设计，产出16,074个物理可行的运动片段
◆ 首次在四足机器人上验证运动跟踪的扩展定律，Flow-Matching通用策略性能随训练规模单调提升，并具备零样本跟踪未见动作的能力
◆ 提出三阶段特权到感知策略框架，融合时序LiDAR记忆与地形预测监督，实现全地形鲁棒遍历运动
◆ 统一部署栈协调多策略执行、行为平滑过渡、能耗优化与安全机制，在城市场景自主导航与陪伴式多模态交互中验证产品级行为智能...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-08</td><td>HumAIN: Human-Aware Implicit Social Robot Navigation<br><a href='http://arxiv.org/pdf/2607.07357'>论文</a></td><td>这篇论文提出HumAIN框架,将隐式社交线索融入机器人导航规划,使机器人能感知人类步态与朝向等细微行为。研究首先训练基于Transformer的教师模型,融合历史图像、骨骼关键点、机器人状态和目标位置等多模态输入,学习面向未来轨迹规划的人类感知表征。为支持实时部署,采用知识蒸馏将知识迁移到轻量级学生模型,通过轨迹重建与潜在特征对齐双重优化,使其仅凭最简输入即可推断复杂社交动态。该方法有效弥合了预测与规划之间的鸿沟,可在资源受限平台上实现自适应且社交合规的导航。实验显示HumAIN在所有轨迹预测指标上较现有最优方法平均提升29.8%,充分验证了利用全身隐式线索实现类人导航的有效性。

创新点:
◆ 将骨骼关键点等隐式社交线索引入导航规划,增强人类行为感知能力
◆ 采用知识蒸馏的师生架构,实现重型模型向轻量级模型的高效迁移
◆ 设计多模态Transformer教师模型,融合图像、姿态、状态与目标信息
◆ 提出轨迹重建与潜在特征对齐的双重优化策略
◆ 在资源受限平台上实现实时推理,性能较现有方法提升29.8%...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-08</td><td>GemNav: Discrete-Token Visual Robot Navigation using a Multimodal Large Language Model<br><a href='http://arxiv.org/pdf/2607.06882'>论文</a></td><td>GemNav提出了一种基于冻结多模态大语言模型（MLLM）的视觉机器人导航策略，挑战了传统依赖专用视觉编码器、定制动作头和大规模跨形态数据集的范式。核心创新包括：◆仅在语言塔上使用低秩适配（LoRA）微调，无需辅助视觉编码器与连续回归头；◆将路径点和分类导航信号统一映射到语言模型头生成的离散token词表，并引入软解码辅助损失以恢复纯交叉熵训练丢失的度量结构。该方法仅在8.7小时的开源数据上训练，规模比现有方案小约三个数量级。策略在四个物理差异显著的未知环境中实现零样本部署，20次真实试验中均能在距目标0.25至0.42米内停止。此外，实验发现引入短时图像历史可提升离线指标，但对真实机器人表现无明显收益，表明在预训练视觉特征充分时，时序上下文存在收益上限。</td></tr>
<tr><td>2026-07-06</td><td>Green for Go, Red for No: Visual Grounding via Semantic Segmentation for VLA Navigation Policies<br><a href='http://arxiv.org/pdf/2607.05122'>论文</a></td><td>本文首次对VLA导航策略中的视觉接地方法进行了系统性实证评估，提出了一种基于SegFormer的实时语义分割接地方法，用绿色高亮可通行区域、红色标记不可通行区域，从而过滤感知干扰和模糊场景理解。

◆ 基于SegFormer的实时分割接地方法，能够在像素级别直接标注可通行与不可通行区域，无需对VLA模型重新训练，计算开销低。

◆ 探索了两种接地变体：仅观测分割以及观测与目标联合增强策略，并系统比较其效果差异。

◆ 在Grand Tour数据集和OmniVLA模型上的实验表明，该方法在最远航点处将平均航点误差降低27%至44%，且对长指令的提升效果显著优于短指令。

◆ 通过归一化误差分析揭示，接地的核心作用是作为轨迹长度正则化器，将预测路径长度缩短30%，但并未改善单位距离内的推理精度，说明该方法无法弥补分布外指令中缺失的训练信号。</td></tr>
<tr><td>2026-07-04</td><td>LH-AVLN: A Benchmark for Long-Horizon Audio-Visual-Language Navigation<br><a href='http://arxiv.org/pdf/2607.03920'>论文</a></td><td>该论文针对长时域具身导航任务中音频线索缺失的问题，提出了LH-AVLN基准，将多目标任务执行、异构目标描述与持续空间化声学提示相结合。智能体接收由2至4个子目标组成的全局任务，每个子目标可通过类别、自然语言描述或参考图像指定，并基于RGB-D、位姿和双耳音频在室内3D环境中导航，同时支持有序和无序两种任务模式。

◆ 首次构建长时域音视觉语言导航基准，填补了现有长时域任务缺乏声学维度、音频导航任务仅限单一目标的空白。

◆ 引入异构目标描述机制（类别、语言、参考图像）与空间化音频提示，使声音既可辅助非视距搜索，又可能随任务进展成为干扰。

◆ 提出无训练的PAG-Nav基线方法，通过时序一致语义地图与渐进式目标状态规划，利用声音进行搜索并保留视觉语义验证完成判定。

◆ 实证表明现有视觉语言、记忆型及音视觉智能体均难以完成完整任务，揭示了该方向存在巨大研究空间。</td></tr>
<tr><td>2026-07-03</td><td>High-Precision Formation Control for Heterogeneous Multi-Robot Systems via Hierarchical Hybrid Physics-Informed Deep Reinforcement Learning<br><a href='http://arxiv.org/pdf/2607.03512'>论文</a></td><td>本文针对异构多机器人系统高精度编队控制难题，提出了一种分层混合物理信息深度强化学习框架HHy-PIDRL，旨在同时解决传统控制方法依赖精确模型和端到端强化学习样本效率低、收敛性差的问题。该框架采用双层结构：上层基于Soft Actor-Critic算法为阿克曼转向领航机器人设计自主导航策略网络，下层为全向跟随机器人融合物理前馈控制器、经典PD控制器与自适应DRL残差控制器，形成混合模型与强化学习协同的编队控制策略网络，并设计了分层奖励函数引导智能体学习精细稳定的控制策略。实验结果表明，所提方法在自主导航和编队控制任务中均达到100%的成功率，并通过消融实验验证了各模块的有效性。

◆ 双层分层架构设计：将领航者自主导航与跟随者编队控制解耦为上下两层，分别采用SAC算法和混合HM-DRL策略，提高了系统响应速度与控制精度。

◆ 混合模型与强化学习融合的编队控制器：将物理前馈控制、经典PD控制与DRL残差控制器相结合，兼顾模型可解释性与学习适应性。

◆ 分层奖励函数设计：为全向跟随机器人定制独特的层次化奖励机制，有效引导智能体收敛至稳定精细的控制策略。</td></tr>
<tr><td>2026-07-03</td><td>GDPR-Aware Trajectory Sharing for ISAC-Assisted Robot Navigation: A Case Study on FID-Constrained Collision Prediction<br><a href='http://arxiv.org/pdf/2607.03254'>论文</a></td><td>本文针对集成感知与通信（ISAC）辅助机器人导航中轨迹共享引发的隐私合规问题，提出了一种基于费雪信息密度（FID）约束的GDPR感知轨迹共享方案。核心思想是在共享感知估计前，根据局部信息内容量对其进行自适应扰动，从而同时满足GDPR第5(1)(c)条数据最小化与第5(1)(f)条完整性保护的要求。在真实行人轨迹数据上的实验表明，FID控制的共享机制相比固定误差扰动实现了严格更优的隐私-效用权衡，在相同漏检冲突率下，重建泄漏率和持续暴露长度均显著降低。研究将信息论度量（FID）作为隐私保护与合规设计之间的桥梁，为ISAC场景下隐私感知的数据处理提供了可量化的技术措施。

◆ 提出FID约束的自适应轨迹扰动共享机制，根据局部信息密度动态调整扰动强度。

◆ 将GDPR数据最小化与完整性原则形式化为信息论约束，实现合规性可量化验证。

◆ 证明信息感知扰动在隐私-效用权衡上严格优于固定误差扰动方法。

◆ 在真实行人轨迹实验中同时降低重建泄漏与持续暴露长度，验证实际有效性。</td></tr>
<tr><td>2026-07-03</td><td>Fast 3D Foundation Model Initialized Gaussian Splatting<br><a href='http://arxiv.org/pdf/2607.03209'>论文</a></td><td>本文提出了一种无需传统SfM的快速3D高斯泼溅重建方法，利用3D基础模型进行相机位姿和点云初始化，并通过深度引导损失联合优化位姿与高斯基元，实现了从粗糙初始化的快速收敛。其核心创新点如下。

◆ 首次将3D基础模型引入3DGS流程，摆脱对COLMAP等传统SfM方法的依赖，仅需50-60张输入视图即可获得可用重建结果。
◆ 设计了深度引导损失函数，在联合优化相机位姿与高斯泼溅参数的过程中，利用基础模型提供的深度先验进行监督。
◆ 提出了基于MLP的位姿精修模块，专门针对稀疏视图场景进一步提升相机位姿估计与重建质量。
◆ 在Mip-NeRF 360、Tanks and Temples和RobustNeRF数据集上取得23.61 dB PSNR和0.19 LPIPS的竞争性表现，同时将训练时间压缩至每场景约3分钟，适合机器人、VR和自动驾驶等近实时应用。</td></tr>
<tr><td>2026-07-02</td><td>ACID: Action Consistency via Inverse Dynamics for Planning with World Models<br><a href='http://arxiv.org/pdf/2607.02403'>论文</a></td><td>本文针对动作条件世界模型在决策时规划中只评判终端状态、忽略中间过渡可行性的问题，提出了一种新的规划框架ACID。该框架通过逆动力学模型从预测的状态转移中反向推断动作，检验其能否恢复原始条件动作，从而约束预测轨迹与真实环境展开之间的一致性。

◆ 提出循环动作一致性机制：利用逆动力学模型从预测转移反向推断动作，检测预测轨迹与真实环境展开的潜在偏差。
◆ 设计尺度不变的自适应权重，将每步逆动力学残差融入规划代价，无需人工调参即可平衡一致性约束与目标达成。

在四个动作条件世界模型、六个涵盖刚体与可形变物体操作、铰链控制和视觉导航任务上的实验表明，ACID能持续提升规划质量，并在显著减少规划计算量的同时达到与基线相当的准确率。</td></tr>
<tr><td>2026-07-02</td><td>SPLC: Social Preference Learning for Crowd Robot Navigation<br><a href='http://arxiv.org/pdf/2607.01925'>论文</a> | <a href='https://github.com/sklus949/SPLC'>代码</a></td><td>本文针对人群环境中机器人离线强化学习的奖励设计难题，提出了SPLC社会偏好学习算法。该方法通过引入社会偏好反馈机制，利用原则化的偏好评价标准自动生成偏好数据，从而消除对人工设计奖励函数的依赖。

◆引入社会偏好反馈机制，基于原则化评价标准自动生成偏好数据，摆脱对人工设计奖励函数的依赖。

◆显式建模行人运动动态的内在复杂性，有效缓解奖励偏差问题，实现对广泛社会规范的系统化量化。

◆与现有离线强化学习方法无缝集成后，在多项标准性能指标上持续超越当前最优基线方法。

◆在TurtleBot4移动机器人平台上完成真实人机共存场景的实物实验验证，充分证明方法的实际部署有效性。

该工作为人群机器人导航中社会合规行为的学习提供了一种数据驱动且具有强泛化能力的新范式。</td></tr>
<tr><td>2026-07-02</td><td>Lightweight Safe Reinforcement Learning for End-to-End UAV Navigation<br><a href='http://arxiv.org/pdf/2607.01794'>论文</a></td><td>本文针对密集环境中无人机自主导航面临的稀疏感知、安全探索不稳定以及计算负担大等挑战，提出了一种端到端的轻量化安全强化学习框架。该框架将感知与控制集成，通过非对称卷积和深度可分离卷积构建轻量网络，将稀疏观测编码为具有碰撞风险感知的特征，适用于机载部署。

◆ 将任务建模为约束马尔可夫决策过程，并采用基于拉格朗日方法的安全PPO算法进行求解，通过分层控制架构实现安全约束下的策略学习，避免了传统安全RL中动作投影带来的不稳定性。

◆ 设计了轻量化的感知网络，利用非对称卷积和深度可分离卷积高效编码稀疏观测，显著降低计算开销，适合嵌入式平台部署。

◆ 引入课程学习策略，由易到难逐步提升训练难度，有效改善了训练稳定性。

◆ 在不同障碍物密度和飞行速度下进行实验，结果表明该方法在成功率、安全性和效率上均优于现有强化学习基线。</td></tr>
<tr><td>2026-07-02</td><td>SpaceEra++: A Unified Framework Towards 3D Spatial Reasoning in Video<br><a href='http://arxiv.org/pdf/2607.01784'>论文</a></td><td>本文提出SpaceEra++框架，针对预训练视觉语言模型在3D空间推理中存在的空间不确定性和数据稀缺问题，在其前身SpaceEra基础上构建了一套涵盖数据构建、模型设计、训练优化和提示推理的完整系统。论文观察到原有框架面临扫描视频输入不足和推理约束薄弱两大新挑战，因此从输入和推理两个维度进行了关键改进。

◆ 提出ScenePick帧采样策略，通过平衡空间覆盖范围与目标语义信息，生成既紧凑又全面的场景表征，有效缓解了视频输入信息不充分的问题。

◆ 设计SpaceAlign方法，通过联合利用绝对坐标与相对空间关系施加成对目标约束，使优化目标与空间准确性保持一致，显著增强了模型的空间推理能力。

在多个基准上的大量实验表明该方法相较强基线取得稳定提升，消融研究验证了各组件的独立贡献与协同效果。</td></tr>
<tr><td>2026-07-01</td><td>Context-Triggered Robust MPC for Temporal Logic Specifications<br><a href='http://arxiv.org/pdf/2607.01515'>论文</a></td><td>本文研究离散时间线性系统在加性有界扰动下满足上下文相关线性时序逻辑(LTL)规约的鲁棒反馈控制综合问题。首先利用基于证书的条件保证可达-规避-停留(RAS)规约的几乎必然满足性,然后提出一种将鲁棒模型预测控制(MPC)与局部不变控制器相结合的切换控制架构,其中MPC值函数充当可达性证书,规避通过鲁棒约束实现,停留由局部控制器保证。为获得可计算的优化问题,采用凸对偶性将鲁棒约束转化为等价的确定性凸优化(凸二次规划或二阶锥规划)。在静态与动态环境下的机器人导航仿真验证了方法的有效性。

◆ 基于证书的RAS规约几乎必然满足性条件,为上下文触发的时序逻辑综合提供了低层控制理论基础。

◆ 切换控制架构融合鲁棒MPC与局部不变控制器,MPC值函数兼具可达性证书功能,鲁棒约束与局部控制分别保证规避与停留。

◆ 利用凸对偶理论将鲁棒约束重构为确定性凸优化问题,显著提升了计算可处理性。

◆ 相比Lyapunov方法具有更大的可行域,并天然支持动态环境与在线任务重配置。</td></tr>
<tr><td>2026-07-01</td><td>BIFROST: Bridging Invariant Feature Representation for Observation-space Sim2Real Transfer<br><a href='http://arxiv.org/pdf/2607.01410'>论文</a></td><td>针对机器人策略学习中sim2real迁移因仿真与现实间视觉和动力学差异而失败的问题，本文提出BIFROST方法。◆该方法通过跨域双模拟目标学习共享历史编码器，将仿真与现实中产生等效长期行为的观测-动作序列映射到邻近的潜在状态，从而域不变地捕获任务共享结构。◆不同于现有方法针对单一差距使用独立适配模块再堆叠组合的策略，BIFROST直接在原始观测空间统一处理视觉与动力学双重差距。基于该编码器，仿真中训练的策略可零样本迁移到现实，无需额外微调或适配模块。实验在sim2sim视觉导航、sim2real接触丰富操作和视觉伺服任务中均验证了BIFROST的有效性，而域适应与协同训练基线在这些任务中均告失败。</td></tr>
<tr><td>2026-07-01</td><td>Path Planning in Physically Viable World Models<br><a href='http://arxiv.org/pdf/2607.00673'>论文</a></td><td>本文针对机器人在非结构化户外环境中使用过时地图进行长时规划的问题，提出了一种物理可行的世界模型。该系统将重建的三维高斯泼溅场景与基于物理的仿真相结合，无需重新采集传感器数据或重建地图，即可生成同一环境的物理修改版本。论文实现了一个地形感知的规划器，能够在部署前评估规划路线在物理事件、障碍物和地形变形等未来条件变化下是否仍然可行。研究人员在德州中部的真实户外场地中，通过多级严重程度的模拟洪水对该系统进行了评估，测量了地形条件恶化时路线与任务可行性。结果表明，物理可行的世界模型能够暴露原始重建环境中无法显现的长时路线失败与重规划行为，使机器人在部署前即可评估未来地形变化对路线可行性的影响。

◆ 将三维高斯泼溅场景与基于物理的仿真相融合，实现无需重采样的环境物理修改生成
◆ 构建物理可行的世界模型以支持机器人导航的what-if查询
◆ 设计地形感知规划器，在复杂环境中可提前评估路线可行性与回退能力
◆ 在真实户外场地验证系统能揭示长时规划中的路线失效与重规划行为...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-30</td><td>LeCropFollow: Latent Space Planning for Navigation in Unstructured Crop Fields<br><a href='http://arxiv.org/pdf/2606.31941'>论文</a> | <a href='https://felipe-tommaselli.github.io/lecropfollow'>代码</a></td><td>◆提出LeCropFollow框架，用学习到的潜在表示替代显式几何建模，面向不规则种植、断行等非结构化田间导航难题。
◆将自监督语义热图提取器与TD-MPC2模型式强化学习规划器结合，使机器人能直接在潜在流形中优化轨迹。
◆保留未压缩的语义热图信号，避免传统几何方法在降维为关键点或路径参考时丢失不确定性与语义上下文。
◆实现从简化仿真到真实玉米田的零样本迁移，无需额外微调。
◆田间实验表明，其在非结构化行间表现接近最优基线，并在种植缺口场景中显著降低语义失败率，相比关键点方法减少2.4倍。</td></tr>
<tr><td>2026-06-30</td><td>Scenario Generation for Testing of Autonomous Driving Systems Using Real-World Failure Records<br><a href='http://arxiv.org/pdf/2606.31131'>论文</a> | <a href='https://github.com/anjaliParashar/crash2scenario'>代码</a></td><td>◆ 论文提出利用真实世界ADS历史故障/事故记录生成仿真测试场景，将自然语言记录转化为可执行测试输入。
◆ 核心创新是构建模块化LLM场景生成流水线，提取类别与上下文信息，并适配具体系统的测试约束。
◆ 方法减少了人工设计场景模板的负担，同时突破传统仿真测试依赖固定场景表示的限制。
◆ 在NHTSA ADS事故记录和Metadrive仿真器上验证，生成了涵盖4类道路、3类非自车运动及施工区异常的多样场景。
◆ 实验表明，生成场景与测试条件一致，并在仅20个场景的有限预算下发现了自动驾驶导航系统的有意义失效。</td></tr>
<tr><td>2026-06-29</td><td>MOAR Planner: Multi-Objective and Adaptive Risk-Aware Path Planning for Infrastructure Inspection with a UAV<br><a href='http://arxiv.org/pdf/2606.30575'>论文</a></td><td>◆提出MOAR路径规划器，面向基础设施巡检中无人机近障飞行需求，同时考虑安全、时间与能耗等多目标优化。
◆引入风险感知代价函数，将预计算代价地图与天气、通信、电池等动态风险因素结合。
◆提出“损伤成本”和“插入成本”概念，用于更细致地刻画路径风险和任务执行代价。
◆设计自适应速度规划框架，使无人机可根据风险变化实时调整轨迹与飞行速度。
◆通过仿真和真实飞行测试验证，结果表明该方法能实时生成覆盖多类指标表现范围约90%的可靠轨迹，提升关键巡检任务的自主性与鲁棒性。</td></tr>
<tr><td>2026-06-29</td><td>Pondering the Way: Spatial-perceiving World Action Model for Embodied Navigation<br><a href='http://arxiv.org/pdf/2606.29908'>论文</a></td><td>◆论文提出SWAM空间感知世界动作模型，将视觉导航从“候选轨迹验证”转为“任务目标驱动”的联合生成范式。

◆SWAM仅需起点和目标RGB图像，即可单次推理同时生成中间RGB-D观测序列与对应动作轨迹，提升目标一致性和规划效率。

◆模型在训练中利用深度伪标签学习空间先验，但推理阶段只依赖单目RGB输入，兼顾空间可行性与实际部署便利性。

◆论文设计视觉引导的动作细化模块，使动作预测与视觉变化更精细对齐，减少轨迹与生成画面不一致的问题。

◆还引入轨迹尺度正则化损失，增强不同导航距离下的预测稳定性，并在成功率、轨迹精度、推理效率和零样本泛化上优于现有两阶段方法。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-08</td><td>HumAIN: Human-Aware Implicit Social Robot Navigation<br><a href='http://arxiv.org/pdf/2607.07357'>论文</a></td><td>论文聚焦于社交机器人导航任务，旨在使机器人能够通过细微的骨骼线索（如步态和朝向）感知人类行为，从而实现符合社会规范的路径规划。研究团队提出了HumAIN框架，其核心思路是借助知识蒸馏技术将隐式社交线索融入规划闭环。首先训练一个基于Transformer的教师模型，融合历史图像、骨骼关键点、机器人状态和目标位置等多种模态输入，学习具有人类感知能力的轨迹表征。随后通过蒸馏将该知识压缩为轻量级学生模型，并以轨迹重建和潜在特征对齐为优化目标，使其从极简输入中推断复杂的社交动态。该方法有效弥合了预测与规划之间的差距，并在实验中较现有最优基线在所有指标上平均提升29.8%，特别适合在资源受限的机器人平台上部署。

◆ 提出基于知识蒸馏的社交机器人导航框架，将隐式社交线索整合至规划闭环
◆ 设计融合多模态输入的Transformer教师模型，充分利用骨骼关键点等全身线索
◆ 通过潜在特征对齐蒸馏得到轻量级学生模型，实现实时部署与社交感知的兼顾
◆ 在轨迹预测任务上较SOTA方法平均提升29.8%，适用于资源受限平台...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-08</td><td>Disturbance-aware Motion Planning for Over-actuated Underwater Vehicles Exploiting Actuation Redundancy for High-fidelity 3D Reconstruction<br><a href='http://arxiv.org/pdf/2607.07139'>论文</a></td><td>本文针对水下机器人在精细目标附近作业时推进器扰动降低成像质量的问题，提出了一种感知感知的运动规划方法，通过利用八推进器ROV的过驱动冗余特性，在满足运动约束的同时搜索推力分配零空间以最小化任务相关区域的预测扰动。

◆ 核心创新在于揭示并利用了作动-感知耦合机制，将传统的以载体为中心的控制目标扩展为兼顾感知质量的联合优化框架。

◆ 基于作动盘理论构建了带方向衰减的推进器尾流代理模型，并经PIV实验高精度验证（R²达0.99）。

◆ 设计了实时冗余求解分配器，以10 Hz（45 ms/求解）的频率在线优化推力配置。

◆ 在440次试验中将目标区域颗粒速度降低67%，3D重建RMSE提升55%，并支持自主扫描与操作员辅助巡检两种模式。</td></tr>
<tr><td>2026-07-08</td><td>Ace! Motion Planning of Professional-Level Table Tennis Serves with a Robot Arm<br><a href='http://arxiv.org/pdf/2607.06989'>论文</a></td><td>本文针对机器人乒乓球领域长期被忽视的发球任务,提出了一种结合运动基元、模型预测控制(MPC)与贝叶斯优化的新型规划框架。该方法能够自动生成符合国际乒联规则的专业级发球动作序列,有效解决了无旋球产生高旋转、精准瞄准以及多目标优化等核心难题。研究者通过分层优化策略对球拍运动轨迹进行精细控制,实现了宽广且可控的发球变化空间。实验结果表明,该系统可生成高达550 rad/s的旋转和6.7 m/s的球速,在关键性能指标上达到并超越精英人类选手水平。这一工作为机器人发球研究建立了新的技术基准,也将高速灵巧操作研究推向了新的高度。

◆ 首次系统性地研究机器人乒乓球的发球任务,填补了长期以来以接球回合为主的研究空白
◆ 提出运动基元与MPC、贝叶斯优化相融合的混合规划框架,兼顾物理建模精度与搜索效率
◆ 突破无旋球到高旋转球的物理极限,通过精细轨迹控制实现高强度旋转的稳定生成
◆ 在球速、旋转等关键性能指标上达到并超越人类精英选手水平...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-07</td><td>Clustering-Embedded Model Predictive Path Integral Control: Avoiding Averaging-Induced Failure and Enabling Efficient Cluster Selection for Dynamic Obstacles<br><a href='http://arxiv.org/pdf/2607.06499'>论文</a></td><td>本文针对采样式运动规划方法MPPI在复杂环境中因加权平均不兼容轨迹而导致的&quot;平均化失效&quot;问题,提出了聚类嵌入式MPPI(CE-MPPI)框架。该方法从架构层面重构了MPPI的控制律,不再仅是抑制干扰,而是通过高保真剪枝与聚类阶段,将可行轨迹模式从不可行的噪声滚动轨迹中分离出来。

◆在采样后引入基于密度的DBSCAN聚类,并结合从碰撞参考点中提取的创新几何方向特征,实现对可行轨迹模式的精准聚类与筛选。

◆设计了智能选择逻辑,在静态场景中以最小代价为优化目标,在动态场景中则主动朝与障碍物运动方向相反的方向进行避让。

◆在JAX加速的2D仿真中有效缓解了障碍物前方的犹豫行为,并避免了在动态环境中与移动障碍物的持续耦合。

◆在基于Isaac Gym和CUDA并行化部署的6自由度UR5e机械臂真实实验中,到达目标时间减少48%,末端执行器路径缩短12%,验证了方法的实用性与高效性。</td></tr>
<tr><td>2026-07-07</td><td>Quality-Aware Personalized AI Service Provisioning in UAV-Assisted 6G Networks<br><a href='http://arxiv.org/pdf/2607.06278'>论文</a></td><td>该论文针对6G网络中AI服务需同时兼顾传统质量（如延迟）与AI服务质量（QoAIS）的双重挑战。现有方法忽视了QoAIS（特别是动态空地场景下的输出保真度、连续性与个性化）保障。论文提出HyPE混合预测-上下文学习框架，融合移动性预测、LLM推理决策与启发式服务放置路由。作者构建了联合UAV轨迹规划、服务放置与路由的优化问题，并给出可扩展的近最优求解方案。仿真验证表明，HyPE在端到端延迟、覆盖率和QoAIS连续个性化方面均优于现有基线方法。

◆ 创新点：提出融合移动性预测的时空请求分布前瞻机制，为动态环境下的资源调度提供基础。
◆ 创新点：引入LLM学习增强推理，灵活优化UAV轨迹与推理任务分配决策。
◆ 创新点：结合预/后处理启发式策略实现服务放置与路由，保障QoAIS驱动的连续个性化。
◆ 创新点：构建传统质量与QoAIS双维度联合优化模型，平衡多目标服务质量。</td></tr>
<tr><td>2026-07-07</td><td>MP-MPPI: A Motion Primitive Guided Sampling-Based Optimizer for Model Predictive Control<br><a href='http://arxiv.org/pdf/2607.06123'>论文</a></td><td>本文提出了一种名为MP-MPPI的新型采样优化方法，将运动基元(motion primitives)引入到模型预测路径积分(MPPI)框架中，以增强结构化采样能力。该方法在实时采样优化循环中同时评估运动基元和扰动控制序列，从而改善了采样控制器在路径规划方面的局限性。论文将该算法在四旋翼无人机仿真器上实现，并针对障碍物场导航任务进行了验证。实验结果表明，所提方法能够有效增强控制空间的探索能力，同时保持实时控制所需的快速响应特性。

◆ 将运动基元与MPPI相结合，形成结构化采样机制，提升全局最优解的收敛性
◆ 在实时采样优化循环中并行评估运动基元与扰动控制序列，丰富控制空间探索
◆ 弥补传统采样控制器在路径规划能力上的不足，同时不牺牲实时反应速度
◆ 通过四旋翼障碍物导航仿真验证了算法在动态复杂环境中的可行性与有效性...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-07</td><td>GraspIT: A Dataset Bridging the Sim-to-Real gap and back for Validated Grasping SE(3) Pose Generation<br><a href='http://arxiv.org/pdf/2607.05869'>论文</a></td><td>GraspIT针对机器人抓取任务中仿真与真实数据难以联合提供逼真观测与物理验证标注的难题,构建了一个大规模RGB-D抓取数据集。该数据集基于NVIDIA Isaac Sim搭建,采用四阶段物理滑移测试对Franka Panda并行实例进行抓取质量评估,超越了传统力闭合判据,并融入了轨迹可达性检查。在约230万个候选抓取中,83%被判定为优质抓取(s≥0.50),剩余17%通过力闭合但未通过滑移测试的样本被作为分级困难负样本。

◆ 提出四阶段物理滑移测试机制,结合力闭合、连续质量评分与轨迹可达性,提供更可靠的抓取物理验证。

◆ 构建Real↔Sim双向闭环标注流程,将仿真标签反向投影到100个真实场景,实现仿真到真实再到仿真的桥接。

◆ 提供约31.6万组带标注的RGB-D帧,覆盖1035个仿真场景与100个真实场景,包含实例掩码、6自由度位姿、物理属性及打分抓取。

◆ 所有工具开源并提供Docker容器化支持,Isaac Sim中的轨迹规划还可流式输出高分辨率演示数据,服务于桌面操作策略学习与行为克隆。</td></tr>
<tr><td>2026-07-06</td><td>Dynamic Evaluation of Classical and Control-Aware Optimal Trajectory Planning in Robot Manipulators<br><a href='http://arxiv.org/pdf/2607.05544'>论文</a></td><td>本文针对机械臂轨迹规划中经典方法仅考虑运动学而忽略动力学与控制代价的问题,提出了一种控制感知的最优轨迹规划框架。核心思路是在有限时域优化中显式纳入机械臂动力学模型与执行器力矩约束,使生成的轨迹在闭环非线性执行下具有更优的跟踪精度与能效表现。

◆ 创新点一:提出控制感知的最优轨迹规划框架,在有限时域内联合优化轨迹形状与执行器力矩分布,克服经典多项式轨迹仅追求运动学平滑而忽视动力学代价的局限。

◆ 创新点二:引入中点线性化策略以提升大范围点对点运动中动力学近似的精度,缓解传统单点线性化在长距离运动中产生的偏差。

◆ 创新点三:构建统一的公平评估框架,使所有规划器在完全一致的闭环非线性动力学、控制器结构与执行器约束下执行,从而能够隔离并真实反映轨迹生成方法本身对执行性能的影响。

◆ 创新点四:基于非线性简化UR5模型的仿真表明,该方法在跟踪误差、修正力矩与闭环执行代价上均显著优于三次、五次及梯形等经典方法,验证了运动学平滑并不等价于动力学高效的关键结论。</td></tr>
<tr><td>2026-07-06</td><td>GaP: A Graph-as-Policy Multi-Agent Self-Learning Harness For Variational Automation Tasks<br><a href='http://arxiv.org/pdf/2607.05369'>论文</a> | <a href='https://graph-robots.github.io/gap'>代码</a></td><td>本文针对&quot;变分自动化&quot;(VA)任务中物体几何与位姿变化大、模型无关策略难以保证可靠性的问题，提出了Graph-as-Policy (GaP) 框架。GaP是一个多智能体编码系统，从模块化开放机器人技能库(MORSL)中选取感知、规划和控制节点，自动生成有向计算图，并构建内部仿真环境并行演练不同图结构与参数，通过迭代优化提升任务成功率和吞吐量。该方法在4个仿真和4个真实场景的8个新VA基准上验证，显著优于现有基线。

核心创新点：

◆ 提出Graph-as-Policy范式，将机器人策略建模为可解释的有向计算图，融合了TAMP任务规划与ROS控制的可解释性与模型无关策略的开放适应性。

◆ 设计多智能体编码协同框架，由多个智能体共同生成、组合并优化计算图节点结构，替代传统端到端黑盒策略。

◆ 构建模块化开放机器人技能库MORSL，提供可复用的感知、规划与控制原语，支持图结构的灵活组装与扩展。

◆ 引入内部仿真环境并行排练机制，在多样化任务实例上迭代精化图结构与参数，实现自我学习与可靠性持续提升。</td></tr>
<tr><td>2026-07-06</td><td>RL-Ballast: Ship Ballast Water Path Planning and Clog Prediction via Reinforcement Learning<br><a href='http://arxiv.org/pdf/2607.04906'>论文</a></td><td>本文针对智能船舶压载水系统在阀门故障和管道堵塞时自适应能力不足的问题，提出了一种基于图深度强化学习的RL-Ballast框架，用于压载水路径规划与传感器稀疏条件下的堵塞诊断。
◆ 将阀门排列组合转化为基于图论与深度优先搜索的54条可行流体传输路径，作为强化学习的动作空间
◆ 利用帧堆叠的液舱液位与动作结果近似部分可观测环境，避免显式建模高维POMDP
◆ 推理阶段引入失败动作记忆与动态动作掩码，防止重复无效动作并支持即时重路由
◆ 累积失败传输历史对可疑阀门或管段排序，实现无需密集仪器的诊断评分
蒙特卡洛仿真表明该方法可完成全部单点堵塞场景，平均决策步数由61.0降至41.5，故障评分在串行不可区分条件下达到100%的Top-3命中率。</td></tr>
<tr><td>2026-07-06</td><td>A Reliable Context-Aware and Temporal Planning Framework for Autonomous Driving<br><a href='http://arxiv.org/pdf/2607.04689'>论文</a></td><td>针对城市密集交通中传感器退化导致规划不稳定的问题，本文提出了一种可靠的上下文感知与时序规划框架RCT-AD。该框架基于共享的鸟瞰图（BEV）空间，通过显式建模特征质量与时序一致性来提升自动驾驶的安全性和一致性。主要创新点如下：

◆ 提出可靠的上下文感知模块，对每帧观测进行可靠性评分，并通过质量门控的FILO（先进后出）记忆机制选择性保留可信特征，利用可靠的历史上下文重建退化观测，避免损坏输入破坏场景表示。

◆ 设计时序轨迹规划器，捕捉长期依赖与多智能体交互，生成更平滑且安全感知的行驶轨迹。

◆ 引入联合检测与分割头，将语义和运动线索注入共享BEV空间，增强场景理解能力。

在nuScenes基准上的实验表明，RCT-AD在感知精度、运动预测和规划鲁棒性上均优于近期端到端基线，同时保持适合实时部署的计算效率。</td></tr>
<tr><td>2026-07-05</td><td>Integrated Graph Search and Model Predictive Control for Smooth and Efficient Path Planning in Autonomous Vehicles<br><a href='http://arxiv.org/pdf/2607.04259'>论文</a></td><td>本文提出一种融合图搜索与模型预测控制（MPC）的自动驾驶路径规划序列框架。该方法首先通过Dijkstra算法在离散网格上搜索得到粗路径，并以此构建一个随空间变化的凸形横向安全走廊。该走廊将离散的避障决策转化为连续的可行性约束，使MPC优化问题自然包含避障信息。在此基础上，MPC通过惩罚横向偏移的三阶空间导数（即急动度）实现路径的平滑精修。基于CarMaker高保真仿真在多种超车场景（含直道与弯道）下的测试结果表明，该方法相比基于多项式拟合与二次规划的方法，显著降低了横向加速度、曲率和急动度，同时在直道和弯道分别减少约28%和29%的计算耗时，验证了图搜索与MPC结合在结构化道路中可有效平衡路径平滑性与计算实时性。

◆ 构建空间变凸横向安全走廊，将图搜索粗路径显式嵌入MPC约束，实现避障信息连续化表达
◆ 引入横向偏移三阶导数（急动度）作为惩罚项，在走廊内完成路径的平滑精修
◆ 在多场景仿真中兼顾舒适性与实时性，计算成本较前作降低28%–29%...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-04</td><td>Handover-Aware Trajectory Planning for Cellular-Connected UAVs under STL Specifications and URLLC Constraints<br><a href='http://arxiv.org/pdf/2607.03781'>论文</a></td><td>本文针对蜂窝连接无人机在超可靠低时延通信约束下执行任务导向飞行的轨迹规划问题,提出了一种兼顾切换感知的联合优化方法。论文将信号时序逻辑用于形式化表达有时间约束的任务语义,并结合有限块长URLLC可行性条件刻画与基站的可靠指令控制链路质量。

◆ 创新点一:将STL任务规范、有限块长URLLC约束与基站切换行为纳入统一的混合整数二次约束规划框架,联合优化轨迹形状、任务满足度、服务基站关联与切换决策。

◆ 创新点二:采用基于逻辑网络流的STL重写技术,将时序逻辑约束转化为可与运动参数耦合的混合整数结构,提升复杂任务的可求解性。

◆ 创新点三:利用贝塞尔曲线参数化运动和圆盘状URLLC服务区域建模,实现连续轨迹与离散切换决策的紧耦合表达。

◆ 创新点四:借助标准分支定界求解器即可处理所提混合离散连续问题,无需定制复杂算法,兼顾通用性与工程实用性。仿真验证表明,所提规划器能在同一蜂窝地图下执行多样化STL任务,同时保持URLLC可行性,并揭示了任务时序、切换关联与有限块长严格性对轨迹形态、链路裕度和计算复杂度的联合影响规律。</td></tr>
<tr><td>2026-07-04</td><td>Occluding the Solution Space: Planner-Agnostic Adversarial Attacks on Tolerance-Aware Manipulation<br><a href='http://arxiv.org/pdf/2607.03758'>论文</a></td><td>该论文针对机器人运动规划中的对抗攻击问题，提出了一种规划器无关的容错感知攻击框架，解决了传统方法依赖精确位姿目标和规划器在线查询的局限。
◆ 创新点之一：将评估范式从精确位姿转向任务级可达性，基于目标区域内是否仍存在可行解进行攻击评估。
◆ 创新点之二：离线阶段构建运动学占据热力图，刻画机器人工作空间能力并编码可行轨迹密度与鲁棒性先验，全程无需调用具体规划器。
◆ 创新点之三：在线阶段将攻击建模为预算约束下的最大覆盖优化问题，在显式几何约束下部署障碍物以最大化遮挡解空间。
大量仿真和真实场景实验表明，该方法能够可靠诱导规划失败，在计算效率和攻击有效性上均显著优于现有基线方法。</td></tr>
<tr><td>2026-07-03</td><td>Optimal mean-time path planning for unmanned underwater vehicles: a Hamilton-Jacobi approach<br><a href='http://arxiv.org/pdf/2607.03407'>论文</a></td><td>本文针对无人水下航行器(UUV)在海洋预报存在不确定性情况下的路径规划问题展开研究。传统方法通常假设单一确定性海洋预报可用，而实际中不同预报模型可能存在差异，导致基于单一预报的最优路径并非真正最优。为此，论文将确定性最优路径规划问题扩展到预报集合（ensemble）情形，旨在寻找使平均航行时间最优的路径。

核心贡献在于提出了一套时间无关的Hamilton-Jacobi偏微分方程组系统，该系统能够融入预报不确定性，同时求解最优平均可达航行时间及对应的最优控制策略。数值求解方面，作者对快速扫描法（Fast Sweeping Method）进行了扩展，实现了该PDE系统的高效数值解算。通过验证与基准测试证明了方法的正确性，并通过数值算例揭示了预报不确定性对最优路径的显著影响。

◆ 将确定性Hamilton-Jacobi路径规划框架推广至预报集合情形，引入预报不确定性，提出求解最优平均航行时间的PDE方程组。
◆ 扩展快速扫描法以高效求解该PDE系统，保证数值计算的可扩展性。
◆ 通过数值实验证明，考虑集合不确定性得到的最优路径可能显著偏离基于任何单一预报的确定性最优路径，凸显了不确定性建模的必要性。</td></tr>
<tr><td>2026-07-03</td><td>Hope for the Best, Prepare for the Worst: Occlusion-Aware Contingency Planning for Autonomous Vehicles<br><a href='http://arxiv.org/pdf/2607.03155'>论文</a></td><td>该论文针对城市自动驾驶中因遮挡导致交通参与者不可见的安全难题，提出了一种形式化的遮挡感知轨迹规划框架。核心思路是结合最坏情况与最好情况的应急规划策略，假设其他交通参与者可能从遮挡区域出现，同时考虑未来可能获得的观测信息来优化决策。研究者利用可达性分析顺序推算被遮挡交通参与者的可能状态，并将其与基于树的运动规划器集成，使车辆能够推理未来有观测和无观测两种情形下的行为。

◆ 提出了一种形式化的遮挡感知应急规划框架，理论上保证在存在潜在隐藏交通参与者情况下的碰撞避免安全性。

◆ 将可达性分析与基于树的运动规划相结合，能够同时推理&quot;有观测&quot;和&quot;无观测&quot;两种未来场景。

◆ 在保持安全保证的前提下显著降低了规划的保守性，提升了自动驾驶车辆在遮挡场景中的通行效率。</td></tr>
<tr><td>2026-07-03</td><td>Function-Space Diffusion for Motion Planning<br><a href='http://arxiv.org/pdf/2607.02977'>论文</a></td><td>扩散运动规划虽能生成多样化高质量轨迹，但现有方法依赖固定长度路径点序列，导致模型与分辨率耦合，难以跨分辨率泛化。该论文提出函数空间扩散运动规划方法FSD-MP，将轨迹建模为连续函数，在函数空间直接进行扩散，实现与离散化无关的轨迹生成。

◆在频谱域中设计基于Matérn型协方差高斯噪声的模式前向过程，使扩散过程摆脱对固定离散粒度的依赖。

◆采用与起终点边界条件兼容的基于离散正弦变换的傅里叶神经算子DST-FNO参数化反向过程，确保起终点约束在不同分辨率下的一致保持。

◆在2D点机器人和7自由度Franka机械臂规划基准上的实验表明，该方法在训练分辨率下取得竞争性规划性能，并能零样本泛化至高16倍分辨率而无需重新训练，证明函数空间扩散是实现离散无关运动规划的有效框架。</td></tr>
<tr><td>2026-07-03</td><td>Continuous-Time Gaussian Belief Trees for Motion Planning<br><a href='http://arxiv.org/pdf/2607.02884'>论文</a></td><td>本文针对连续时间随机系统（线性SDE建模、测量离散到达）下的采样运动规划问题，提出在过程与测量不确定性下兼顾安全与性能的概率规划方法。作者构建离线混合信念传播模型，测量间隔内信念按常微分方程连续演化，测量时刻发生离散卡尔曼滤波更新跳跃，并基于信念屏障函数设计分段级安全检验器以检测样本间机会约束违例。该方法与RRT和SST规划器集成，在多个基准尤其是窄通道场景中取得高成功率和稳健的机会约束满足效果，显著优于离散时间方法。

◆ 连续-离散混合信念传播机制：测量间隔内以ODE连续传播不确定性，测量时刻以卡尔曼滤波做离散更新。
◆ 基于信念屏障函数的分段级概率安全检验：覆盖整条连续轨迹段，可捕获节点式检查漏掉的样本间机会约束违例。</td></tr>
<tr><td>2026-07-02</td><td>Path planning for unmanned naval surface vehicles<br><a href='http://arxiv.org/pdf/2607.01631'>论文</a></td><td>本文针对无人水面航行器（USV）的路径规划问题，提出了一种结合全局与局部规划器的混合方法，用于同时规避固定障碍物和移动障碍物。全局规划器负责在已知固定障碍物环境中规划从起点到目标点的路径，局部规划器则负责实时绕行移动障碍物及未知障碍物，并通过仿真实验与经典的D*算法进行了对比验证。

◆ 提出了一种新颖的全局规划器，将经典的Grassfire算法、新改进的Grassfire算法以及一种新的概率路图（PRM）改进版本三者有机结合。

◆ 设计了一种新的Grassfire改进算法，提升了固定障碍物环境下的路径规划效果。

◆ 提出了一种更直观的新型概率路图版本，使全局路径规划更加合理高效。

◆ 局部规划器创新性地引入了基于障碍物运动方向的高层决策逻辑，使USV能够选择从障碍物后方绕行的策略，避免与移动障碍物平行航行。</td></tr>
<tr><td>2026-07-03</td><td>From Real-Time Planning to Reliable Execution:Scalable Coordination for Heterogeneous Multi-Robot Fleets in Industrial Environments<br><a href='http://arxiv.org/pdf/2607.00591'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-06</td><td>From Fixed to Free Cameras: Calibration-Free View-Robust Vision-Language-Action Model<br><a href='http://arxiv.org/pdf/2607.05396'>论文</a> | <a href='https://alibaba-damo-academy.github.io/CamVLA/'>代码</a></td><td>CamVLA论文针对真实机器人部署中相机位置频繁变化的问题，提出了一种无需标定的视图鲁棒视觉-语言-动作模型。论文指出传统VLA策略依赖显式相机外参才能适应视角变化，主张策略应自主推断相机位姿而非被动接收。核心方法通过解耦操作控制与相机几何，分别...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-02</td><td>Bridging 3D Gaussians and Semantic Occupancy for Comprehensive Open-Vocabulary Scene Understanding from Unposed Images<br><a href='http://arxiv.org/pdf/2607.01633'>论文</a></td><td>该论文提出COVScene框架，针对稀疏无位姿图像下的综合3D场景理解问题，将可渲染的高斯基元与密集语义占据场通过可微分体素提升紧密耦合。其核心思想是在训练计算图内部将预测的语义高斯提升为体素，使体素级正则化能够反向传播至高斯的不透明度、几何和语义特征，从而解决现有前馈高斯方法在未观测区域约束不足的问题。该框架还结合了几何基础模型蒸馏和占据熵正则化等技术，在单一表示中统一支持多种任务。

◆ 在训练计算图中进行可微分体素提升，使体素级监督信号回传至高斯参数
◆ 语义感知几何Transformer实现多任务高斯解码
◆ 几何基础模型蒸馏增强未观测区域的先验约束
◆ 占据熵正则化提升占据场预测的清晰度
◆ 单一表示统一支持新视角合成、开放词汇语义查询与语义占据预测...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-30</td><td>Ground Plane-Aided Extrinsic Calibration of Inertial and RGB-D Sensors for Uncrewed Aerial Vehicles<br><a href='http://arxiv.org/pdf/2606.31019'>论文</a></td><td>◆本文提出了一种面向无人机IMU与RGB-D相机的无标靶外参标定方法，避免依赖棋盘格、专用设备和初始参数估计。
◆方法利用深度学习进行地面分割，从RGB-D深度图中提取地面点并估计其法向量。
◆核心创新是将地面法向量与加速度计测得的重力方向相结合，在鲁棒估计框架下求解传感器外参。
◆该方法特别适合无人机在自然环境中的快速部署与在线/离线标定需求。
◆实验表明，其性能优于MATLAB工具箱，并在无需棋盘格目标的情况下接近Kalibr的标定效果。</td></tr>
<tr><td>2026-06-28</td><td>HiReFF: High-Resolution Feedforward Human Reconstruction from Uncalibrated Sparse-View Video<br><a href='http://arxiv.org/pdf/2606.29333'>论文</a> | <a href='https://iridescentjiang.github.io/HiReFF'>代码</a></td><td>◆ HiReFF提出面向未标定稀疏视角视频的前馈式人体重建框架，可从四个相隔90°视角实现2K、360°动态人体视频重建。
◆ 它将任务分解为稀疏视频前景3D Gaussian重建和高效高分辨率合成，避免传统逐场景优化或依赖相机标定。
◆ 提出Scale-synchronized Camera Calibration，在多视角监督中同步尺度，缓解未标定输入带来的尺度歧义。
◆ 提出Gaussian-wise Foreground Masking，通过调制每个Gaussian参数获得更干净的前景重建并抑制背景干扰。
◆ 提出High-resolution Side-tuning，在主干保持0.5K计算量的同时实现低开销2K渲染，并显著优于现有方法。</td></tr>
<tr><td>2026-06-26</td><td>Robotic Arm-Based Spectral Sensing for Strawberry Positioning and Non-Destructive Sweetness Measurement<br><a href='http://arxiv.org/pdf/2606.28555'>论文</a></td><td>◆提出了一套基于机械臂的草莓光谱感知系统，实现草莓检测、定位、接近与无损甜度估计的闭环集成。
◆系统结合YOLOv11s实时检测、RGB-ToF标定和掩膜-深度对齐，提升了果实三维定位的几何一致性。
◆设计了定制化eye-in-hand手眼标定流程，将目标从相机坐标可靠转换到机器人基坐标，支撑稳定操作。
◆采用路点搜索与增量式闭环接近策略，使传感器能够自动到达适合甜度测量的工作距离。
◆实验达到88.10%的端到端成功率，检测成功率95.24%，目标被检测后的接近成功率为100%，验证了系统可行性。
◆论文还指出当前主要瓶颈在复杂深度和反射条件下的有效感测区域提取，并为未来引入学习型策略提供了可扩展基线。</td></tr>
<tr><td>2026-06-26</td><td>Co-Optimization of Analog Kolmogorov-Arnold Networks for Low-Power Function Approximation in Flexible Electronics<br><a href='http://arxiv.org/pdf/2606.27892'>论文</a></td><td>◆提出模拟Kolmogorov-Arnold网络（AKANs），面向柔性电子中的低功耗多变量函数近似，适用于可穿戴与IoT传感端计算。

◆通过硬件-软件协同优化，将电路级非理想误差纳入训练过程，使模型在实际模拟硬件偏差下仍保持较高精度。

◆设计了软件与硬件双层剪枝方法，在减少样条参数和电路资源的同时降低面积与功耗。

◆实验表明，剪枝不仅压缩硬件开销，还能通过正则化效应提升函数近似精度。

◆在多个基准任务上实现最高55%面积节省和50%功耗降低，平均节省近30%，证明AKANs具备通用性和实用价值。</td></tr>
<tr><td>2026-06-24</td><td>Calousel: Extrinsic Calibration of Non-overlapping Multi-camera Systems from Pure Rotation<br><a href='http://arxiv.org/pdf/2606.25646'>论文</a></td><td>◆论文提出Calousel，用纯旋转运动实现非重叠视场多相机外参标定，只需一块静态标定板，降低了传统大靶标或多靶标预先测量的部署成本。
◆其核心思想是让各相机在不同时间依次观测同一标定板，并通过共享几何参考把这些非同步观测统一起来。
◆方法引入潜在转台坐标系，并在SE(3)上构建三维误差的全局优化模型，以联合估计多相机外参。
◆相比常见运动标定方法，该方案缓解了漂移误差、尺度不确定性和运动退化等问题。
◆实验在受控相机架和真实车辆异构相机平台上验证，表明其在非理想旋转条件下仍具备较高精度和现场部署实用性。</td></tr>
<tr><td>2026-06-22</td><td>IOI: Decoupling Kinematics and Physics for Interactive World Models<br><a href='http://arxiv.org/pdf/2606.23296'>论文</a></td><td>◆ IOI提出一种混合式交互世界模型，将解析运动学先验与学习到的物理动态解耦结合，提升控制对齐和视觉物理合理性。
◆ 它由动作序列显式计算正向运动学轨迹，避免纯数据驱动方法常见的时空漂移。
◆ 论文将轨迹渲染为前、侧、顶三视角正交投影，无需外参标定，并通过多视角运动学聚合与注入模块引导视频生成。
◆ 这种设计让生成器专注建模随机物理交互，而确定性运动由运动学先验保证，形成解析仿真与世界模型的协同。
◆ 在RoboTwin和真实平台实验中，IOI实现了SOTA仿真效果、OOD零样本泛化，并可作为可靠策略评估器和合成数据来源。</td></tr>
<tr><td>2026-06-19</td><td>Online Learning of Robust Legged Odometry with Minimal Exteroceptive Supervision<br><a href='http://arxiv.org/pdf/2606.21669'>论文</a></td><td>◆提出一种即插即用的腿式里程计框架，无需显式外感-本体传感器标定，也不依赖平台特定运动学模型。

◆利用成熟外感运动估计管线作为连续弱监督信号，在线训练仅基于本体感知数据的速度神经网络。

◆将学习到的本体速度、可用外感速度与IMU通过Invariant EKF融合，提高状态估计稳定性与一致性。

◆当视觉/激光等外感在退化环境中失效时，系统可自动切换到学习的本体模型，实现鲁棒连续里程计。

◆在不同四足机器人上验证了方法的平台无关性和快速部署能力，展示其在复杂场景下的可靠运动估计效果。</td></tr>
<tr><td>2026-06-18</td><td>Geometry-Preserving in 3D Gaussian Splatting for LiDAR-Camera Extrinsic Calibration<br><a href='http://arxiv.org/pdf/2606.20103'>论文</a></td><td>◆ 论文针对无标靶LiDAR-相机外参标定中跨模态特征不足的问题，利用3D Gaussian Splatting构建可微的几何代理以支持外参优化。
◆ 作者指出现有3DGS方法过度追求图像渲染质量，容易使高斯空间结构偏离真实LiDAR几何，从而影响标定精度。
◆ 提出通过聚合多视角LiDAR观测生成稠密深度监督，增强高斯代理对真实度量几何的保持能力。
◆ 设计了阻断光度梯度更新高斯空间参数的机制，避免视觉重建目标破坏LiDAR几何结构。
◆ 在公开自动驾驶数据集上的实验表明，该方法在无标靶标定精度上稳定优于现有方法。</td></tr>
<tr><td>2026-06-12</td><td>LV-Calib: LiDAR-Camera Extrinsic Calibration with Boundary-Response Modeling<br><a href='http://arxiv.org/pdf/2606.15010'>论文</a></td><td>本文提出了LV-Calib标定框架，利用可打印平面标定板实现了激光雷达与相机的外参估计及激光雷达边界响应标定。
◆提出基于强度与几何约束的迭代精化方法，自动裁剪背景并估计目标平面，显式处理反射率不连续处因光束足迹和混合回波导致的过渡带展宽与失真问题，提取精确的雷达3D特征点。
◆设计了加权重投影一致的外参优化策略，将图像观测保留在重投影域，并利用精化置信度对雷达特征残差进行加权，提升外参标定精度。
◆利用估计的外参和提取的过渡带，通过计算边界重叠样本的俯仰-偏航-距离残差统计量，实现了激光雷达边界响应的标定。
实验验证了该方法具备亚像素级重投影精度与毫米级特征一致性，并有效提升了里程计性能。</td></tr>
<tr><td>2026-06-12</td><td>StereoGeo: an end-to-end stereo camera calibration method<br><a href='http://arxiv.org/pdf/2606.14619'>论文</a> | <a href='https://github.com/meddourimane/StereoGeo-dataset'>代码</a></td><td>本文提出了StereoGeo，一种基于端到端网络的立体相机标定方法。该方法能够同时估计左右相机的焦距与重力方向，以及它们之间的相对外参变换。
◆突破了现有方法依赖标定板或结构化环境的限制，无需多视角设置即可完成双目标定。
◆打破了传统方法仅局限于单目内参或外参估计的不足，实现了双目内外参的联合估计。
◆扩展了GeoCalib算法，将深度神经网络特征提取与可微优化器进行有效整合。
实验证明该方法在内参标定上极具竞争力，在外参估计上更超越了现有限于单目的方法。</td></tr>
<tr><td>2026-06-12</td><td>Fully Distributed Multi-View 3D Tracking in Real-Time<br><a href='http://arxiv.org/pdf/2606.13127'>论文</a></td><td>本文提出MV3DT,一个面向重叠视野多摄像头网络的全分布式实时三维多目标跟踪框架。该方法摒弃传统集中式融合架构,通过点对点协同实现身份传播与遮挡恢复,有效解决了集中式方法在大规模部署时的计算瓶颈问题。在WILDTRACK数据集上达到94.3%的IDF1和93.3%的MOTA,性能与最先进的集中式方法相当,同时在100个摄像头规模下仍能保持30 FPS的实时性能,摄像头间延迟低于10毫秒,通信开销仅为2.2%。此外,该方法无需场景特定训练,仅依赖摄像头标定即可零样本部署于新环境。

核心创新点如下:

◆ 首次提出完全分布式的多视角三维跟踪架构,通过点对点协调机制取代中心节点聚合,从根本上消除了集中式方法的计算瓶颈。

◆ 设计了轻量级模块化流水线,在每个摄像头节点本地执行单目三维感知、分布式多视图关联与协同融合,通过轻量消息传递实现跨节点协作。

◆ 实现卓越的可扩展性,在100摄像头规模下维持30 FPS实时性能,通信开销仅2.2%,显著优于集中式方案。

◆ 采用零样本运行模式,仅依赖摄像头标定信息,无需任何场景特定的训练或学习,可直接部署到新环境。

◆ 在WILDTRACK基准上取得与集中式SOTA方法相竞争的精度,验证了分布式架构在保持高精度的同时具备规模化部署的实用价值。</td></tr>
<tr><td>2026-06-11</td><td>RGB-S: Image-Aligned Tactile Saliency for Robust Dexterous Manipulation<br><a href='http://arxiv.org/pdf/2606.08765'>论文</a></td><td>本文提出RGB-S框架，旨在解决机器人灵巧操作中视觉遮挡下稀疏触觉与密集视觉难以对齐的问题。与隐式学习跨模态对应的方法不同，该框架通过将物理接触显式锚定在图像域中来提升空间推理能力。
◆利用机器人正运动学与相机校准，将触觉传感器位置直接投影到RGB图像平面，实现跨模态空间对齐。
◆渲染受力调制的高斯显著图，有效建模由运动学与校准误差带来的空间不确定性。
◆采用零初始化条件架构整合二维空间锚点，将物理接触先验注入视觉主干网络，同时保留预训练视觉表征。
在严重视觉遮挡的仿真与真实灵巧操作任务评估中，该方法展现出更强的抗遮挡鲁棒性，真实世界实验成功率较最强隐式基线提升了26.7个百分点。</td></tr>
<tr><td>2026-06-07</td><td>Language as a Sensor: Calibrated Spatial Belief Estimation in 3D Scenes from Natural Language<br><a href='http://arxiv.org/pdf/2606.08666'>论文</a></td><td>该论文提出将自然语言作为一种新型传感器，以解决机器人视场外3D空间推理与多传感器融合的难题。
◆提出语言传感器模型LSM，将语言描述及场景图上下文映射为多模态空间分布，通过混合权重编码指代歧义，分量协方差编码空间不确定性。
◆提出概率建图框架VL-Map，将语言预测视为随机观测，并与机载感知在统一的置信度地图中进行深度融合。
实验证明，LSM是唯一能够保持协方差估计处于校准状态的语言预测器。
将LSM融合进VL-Map后，系统对目标物体位置的预测更加准确，真值目标上的概率质量比最强基线高出约70%。</td></tr>
<tr><td>2026-06-06</td><td>Empowering Feed-Forward Reconstruction Models with Metric Scale via Satellite Images<br><a href='http://arxiv.org/pdf/2606.08205'>论文</a></td><td>该论文提出一种卫星引导框架，利用易获取的卫星图像作为全局度量参考，解决前馈3D重建模型中存在的尺度模糊问题。
◆创新性地引入卫星图像作为度量参考，无需昂贵的度量标注或高精度相机标定即可消除尺度模糊。
◆设计了双向跨视角交互机制，将局部卫星图像块与前馈重建主干网络深度融合，强制重建场景与卫星参考间的一致性。
◆实现在度量坐标系下同时推断绝对尺度、优化场景几何并估计相机姿态的能力。
实验表明，该方法在多数据集的深度估计、点云重建和定位任务上均取得显著提升，且保持了优异的跨域泛化性。</td></tr>
<tr><td>2026-06-06</td><td>SynthICL: Scalable In-context Imitation Learning with Synthetic Data<br><a href='http://arxiv.org/pdf/2606.08154'>论文</a></td><td>本文提出了SynthICL框架，解决了上下文模仿学习在泛化性和可扩展性上的挑战，实现了仅基于纯RGB合成数据训练策略。
◆构建高质量合成数据生成流水线并训练流匹配Transformer策略，摆脱了对深度传感、精确相机标定和真实训练数据的依赖，提供更简单可扩展的方案。
◆引入子目标预测机制，通过训练模型预测下一子目标图像，实现更精确且具有视觉基础的机器人控制。
◆在测试阶段仅需单次演示即可让机器人适应新任务，无需重新训练模型。
该方法在16项未见真实操作任务中取得79%的平均成功率，显著超越了现有方法。</td></tr>
<tr><td>2026-06-03</td><td>Multi-Camera AR Guidance System for Surgical Instrument Handling and Assembly: Investigating Workload and Efficiency<br><a href='http://arxiv.org/pdf/2606.04992'>论文</a></td><td>本文提出了一种用于手术器械处理与装配的多摄像头增强现实引导系统，旨在降低洗手护士的认知需求并提升操作效率。模拟手术的用户研究表明，该系统显著降低了护士的感知工作负荷，将任务完成时间缩短了21.3%，尤其使不熟悉器械的护士获益。
◆提出了无需额外标记的多摄像头6D位姿估计与头戴式显示器原位可视化相结合的手术引导方案。
◆采用纯合成数据训练6D位姿估计网络，利用已知物体实现连续相机校准，提升了算法的泛化能力与真实世界适用性。
◆设计了原位工具提示定位与逐步装配动画，并创新性结合凝视选择与脚踏板实现步进切换，满足术中无菌交互需求。</td></tr>
<tr><td>2026-06-03</td><td>FUSE-Flow: A Decoupled Framework for Calibration and Stateless Real-Time Multi-View Point Cloud Fusion<br><a href='http://arxiv.org/pdf/2606.04376'>论文</a></td><td>本文提出FUSE-Flow，一个将标定与实时多视角点云融合解耦的框架，解决了传统方法中二者紧密耦合导致的波动重建结果、累积误差和扩展性差的问题。核心贡献在于通过GMAC和FUSE两个协同模块，实现了无需标定板、密集图像或全局光束法平差的稀疏视角精确标定，以及线性时间内存消耗的无状态融合。框架中GMAC利用几何约束与多视图重建Transformer优化外参，FUSE则通过置信度加权和自适应空间哈希完成融合，且二者相互增强——精确位姿提升融合精度，置信感知融合修正标定偏差。在公共数据集和真实相机系统上的实验验证，FUSE-Flow在视觉效果、动态稳定性和可扩展性上均优于主流实时重建方法，为大规模实时三维重建提供了实用方案。
◆ 解耦设计：将标定与点云融合拆分为独立模块，避免冲突的优化目标，实现针对性改进。
◆ 几何对齐多视图标定（GMAC）：基于几何约束和Transformer实现稀疏视角标定，无需标定靶标、密集图像或全局BA。
◆ 置信引导无状态融合（FUSE）：结合置信度权重与自适应空间哈希，确保线性时间与内存开销，且支持实时运行。
◆ 双向增强机制：精确位姿提升融合准确性，同时置信度感知融合反向校正标定偏差，形成自优化闭环。</td></tr>
<tr><td>2026-06-06</td><td>Dexterity-BEV: Aligning 3D World and Actions for Generalizable Robot Policies Learning<br><a href='http://arxiv.org/pdf/2606.02274'>论文</a> | <a href='https://hnuzhy.github.io/projects/Dex-BEV'>代码</a></td><td>本文针对端到端操作策略依赖2D输入且缺乏跨机器人和相机的3D空间对齐的局限性，提出了Dexterity-BEV方法。
◆提出对齐顶点图与顶点频谱，利用相机标定和可选深度将2D视觉提升为像素级3D表示，融合了3D感知与2D大模型的泛化优势。
◆提出将操作策略的输入输出对齐至共享坐标系，并创新性地构建鸟瞰图图像，生成对相机位姿变化鲁棒的视角不变表示。
◆开发了全面的数据处理管线以实现大规模对齐，并引入了针对跨多种机器人、人类操作员和数据集轨迹的全新时间对齐方案。
这些贡献共同缓解了输入输出的时空不对齐问题，显著提升了真实世界机器人操作的连贯性与泛化能力。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-undistortion'>Sensor Undistortion</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-07</td><td>Why does Deep Learning Improve Visual SLAM?<br><a href='http://arxiv.org/pdf/2607.06023'>论文</a></td><td>本文深入探讨深度学习提升视觉SLAM性能的核心机理，旨在明确学习式2D数据关联、不确定性建模与循环架构三者的具体贡献。作者通过精心设计的受控消融实验，对各组件进行系统性剥离分析。研究发现，深度学习视觉SLAM的成功主要归功于学习式2D数据关联与不确定性的有效结合，而非循环架构本身。该研究强调了学习式范式在视觉SLAM关键模块设计中的必要性。

◆ 提出针对深度学习视觉SLAM系统各组件的受控消融研究框架
◆ 揭示学习式2D数据关联与不确定性建模是性能提升的关键驱动力
◆ 实证表明循环架构并非深度学习SLAM成功的核心因素
◆ 强调学习式范式在数据关联和不确定性设计中的不可或缺性
◆ 将开源代码以推动该领域的进一步研究...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-06</td><td>A Reliable Context-Aware and Temporal Planning Framework for Autonomous Driving<br><a href='http://arxiv.org/pdf/2607.04689'>论文</a></td><td>这篇论文提出了RCT-AD框架，旨在解决自动驾驶中因相机观测退化（遮挡、运动模糊、光照变化等）导致规划不稳定、碰撞风险升高的问题。针对现有BEV方法不加区分地融合时序信息的缺陷，该框架显式建模特征质量与时序一致性以提升规划安全性与连贯性。

◆ 提出可靠上下文感知模块，对每帧特征进行可靠性评分，并设计质量门控的FILO记忆机制，选择性保留可信特征。

◆ 利用可靠历史上下文重构退化观测，避免损坏输入干扰共享BEV场景表示的稳定性。

◆ 构建时序轨迹规划器，捕捉长期依赖与多智能体交互，生成更平滑、安全感知的轨迹。

◆ 引入联合检测与分割头，将语义和运动线索注入共享BEV空间，强化场景理解。

在nuScenes基准上的实验表明，RCT-AD在感知精度、运动预测和规划鲁棒性上均优于近期端到端基线，同时保持适合实时部署的计算效率。</td></tr>
<tr><td>2026-07-04</td><td>How (not) to prove (un)distortion for diffeomorphisms of one-manifolds<br><a href='http://arxiv.org/pdf/2607.04001'>论文</a></td><td>本文研究一维流形上微分同胚群中&quot;扭曲&quot;与&quot;非扭曲&quot;性质在不同正则性之间的关系。在已知(1,2)情形存在而(2,∞)情形不存在的基础上，作者对(2,3)情形进行了深入探讨。

◆ 证明了在C^2正则性下，Liouville余循环的漂移对于所有C^2-扭曲微分同胚恒为零，从而排除了用该余循环构造新障碍的可能性，并推广到任意&quot;类似&quot;余循环。

◆ 在实线情形下，将已有结论从C^2至C^∞的扭曲性传递推广到更高正则性：只要微分同胚的正则性超过C^{2r+2}，则其C^2-扭曲性可自动传递到C^r-扭曲性。

◆ 结合两部分结果揭示了一个重要规律：低正则性下的扭曲性可以通过损失足够的正则性来恢复，但需要正则性阶数跨越特定阈值。

这些结果深化了对微分同胚群中扭曲现象与正则性之间关系的理解，表明某些Cocycles无法作为判别不同正则性间扭曲差异的工具。</td></tr>
<tr><td>2026-07-04</td><td>PRISM3D: Probabilistic Refinement and Robust Initialization for Physically Consistent Scene Modeling under Extreme Motion Blur<br><a href='http://arxiv.org/pdf/2607.03855'>论文</a></td><td>本文针对极端运动模糊图像下的盲3D场景重建难题，提出统一框架PRISM3D，避免了传统SfM方法失效及依赖清晰图像监督的局限。其核心创新点包括：

◆ 提出基于VGGSfM深度稠密跟踪的鲁棒初始化策略，首次将该范式有效用于极端模糊下3D高斯溅射的自举启动，可在特征匹配失败时恢复全局拓扑。

◆ 引入基于马尔可夫链蒙特卡洛的概率几何稠密化方法，配合连续贝塞尔轨迹建模物理图像形成过程，实现对稀疏噪声初始化的稳定优化。

◆ 进一步扩展为多模态框架PRISM3D-E，融合高时间分辨率事件流作为结构先验以提升重建精度。

◆ 同时构建了首个配对事件流与极端模糊数据的PRISM3D-E基准数据集。

实验表明该单模态及多模态方法均达到了当前最优性能。</td></tr>
<tr><td>2026-07-03</td><td>Attention-Guided Efficientnet Architecture For Precise Criminal Identification in Surveillance Images<br><a href='http://arxiv.org/pdf/2607.03073'>论文</a></td><td>该论文针对监控场景下人脸识别面临的低分辨率、光照变化、运动模糊、姿态改变等挑战，提出了一种用于精确犯罪身份识别的注意力引导EfficientNet（AG-EfficientNet）框架。论文将EfficientNet-B0与卷积块注意力模块（CBAM）相结合，增强在退化监控条件下的判别性人脸特征学习能力，并设计多尺度监控特征融合策略以兼顾局部纹理与高层语义身份表征。论文还引入混合Softmax-Triplet优化机制，提升类间可分性与类内紧凑性，从而实现更稳健的犯罪身份判别。在LFW和SCFace数据集上的实验表明，该框架取得了98.2%的识别准确率以及97.9%的精确率，性能优于AlexNet、VGG16、ResNet50、MobileNetV2及标准EfficientNet-B0等基线模型，并通过Grad-CAM可视化与消融分析验证了注意力引导特征学习策略的有效性。

核心创新点如下：

◆ 将CBAM注意力机制嵌入EfficientNet-B0，构建注意力引导的轻量级特征提取网络，增强对监控低质量人脸图像的关键特征聚焦能力。

◆ 提出多尺度监控特征融合策略，同时保留局部纹理细节与高层语义身份信息，提升对复杂监控退化条件的适应性。

◆ 设计混合Softmax-Triplet优化机制，协同提升类间分离度与类内紧密度，强化犯罪身份判别的鲁棒性。</td></tr>
<tr><td>2026-07-03</td><td>E-TraMamba: A New Paradigm for Efficient Long-Term 3D Feature Tracking with Event Cameras<br><a href='http://arxiv.org/pdf/2607.02866'>论文</a></td><td>该论文针对事件相机3D特征跟踪中长程时空依赖建模困难、实时性受限的问题,提出了首个基于Mamba的3D特征跟踪框架E-TraMamba。该方法采用线性状态空间模型实现高效长程建模,结合轻量化的仿射变换预测器,在运动模糊与遮挡场景下保持稳定跟踪性能。

◆ 创新点一:首次将Mamba状态空间模型引入事件相机3D特征跟踪任务,实现对稀疏噪声事件流的高效长程时空依赖建模。

◆ 创新点二:设计轻量级仿射变换预测器,在运动模糊和遮挡条件下维持跟踪稳定性。

◆ 创新点三:提出多尺度线索融合方案,将局部时空块、相关图和位置编码统一表征,实现平滑稳定的3D跟踪。

◆ 创新点四:构建大规模合成数据集EvD-PointOdyssey,提供同步的事件流、深度图和精确3D轨迹。

实验表明,E-TraMamba在严格精度阈值(0.1米)下特征寿命超过基线2倍以上,跟踪特征比例更高且RMSE更低,在低延迟视觉里程计、实时SLAM和交互式机器人等场景具有应用潜力。</td></tr>
<tr><td>2026-06-30</td><td>Distortion-Corrected Diffusion MRI Using Rotated-View EPI and Joint Field-Map/Image Estimation with Gaussian Primitives<br><a href='http://arxiv.org/pdf/2606.31521'>论文</a></td><td>本文提出一种面向扩散EPI的畸变校正框架，直接从k空间联合估计B0场和无畸变图像，避免传统“先重建、再校正”对中间图像质量的依赖。  
◆ 将图像与B0场表示为高斯基元叠加，并嵌入MRI物理前向模型，实现连续、显式且能兼顾平滑区域和组织边界的参数化。  
◆ 连续模型天然支持旋转视角EPI，无需插值，利用多相位编码方向分散畸变，使点扩散函数更各向同性。  
◆ 将扩散加权图像建模为实值非负，并把相位吸收到每次激发的相位因子中，增强低SNR和高b值条件下的稳健性。  
◆ 在体脑扩散实验中，该方法相比顺序校正方法更接近无畸变结构参考，尤其在高加速和高b值下提升最大，并表现出更好的细节保真和降噪效果。</td></tr>
<tr><td>2026-07-01</td><td>A First Exploration of Neuromorphic OT-CFM for Multi-Speaker VSR<br><a href='http://arxiv.org/pdf/2606.31225'>论文</a></td><td>◆论文提出LipsFlow，将RGB视频转为高时间分辨率事件流，利用神经形态视觉捕捉微秒级唇部动态，提升多说话人VSR在运动模糊、遮挡和细微发音下的鲁棒性。
◆系统结合ByteTrack与TalkNet，对多说话人场景进行跟踪和主动说话人检测，切分为单说话人片段以实现更聚焦的识别。
◆引入OT-CFM在语义潜空间中建模事件特征，通过确定性直线轨迹生成，将推理压缩到仅两步ODE，显著降低延迟。
◆设计双层语义监督，将token级BERT权重绑定与句子级先验结合，缓解同唇形词歧义问题。
◆实验表明该方法在240 ms延迟下达到22.3% WER，建立了高效且鲁棒的事件驱动多说话人VSR新范式。</td></tr>
<tr><td>2026-06-29</td><td>Your Data Manifold is Secretly a Reward Model: Shell-LCC for Text-to-Video Generation<br><a href='http://arxiv.org/pdf/2606.30248'>论文</a></td><td>◆论文提出“数据流形本身就是奖励模型”的观点，通过显式建模高质量SFT数据的流形结构，为T2V扩散模型提供密集、可微且低成本的奖励信号。
◆方法基于Local Coordinate Coding捕捉数据流形的“骨架”，引导视频潜变量靠近高质量数据分布，从而提升生成真实感。
◆针对传统LCC容易产生均值回归、导致细节丢失的问题，论文提出Shell-LCC，将流形表面建模为各向同性“壳层”，更贴近真实高密度区域。
◆该方法无需额外奖励模型、大规模人工标注或昂贵DPO训练，即可改善视频质量，尤其缓解低层次失真问题。
◆实验表明，Shell-LCC能增强高频细节、减少过平滑伪影，并有效减轻运动模糊，提升文本到视频生成的整体视觉质量。</td></tr>
<tr><td>2026-06-28</td><td>Again-Pose: Anchor-Guided Adaptive Inter-Frame Motion Cues Propagating for High-quality Human Pose Reconstruction<br><a href='http://arxiv.org/pdf/2606.29230'>论文</a></td><td>◆Again-Pose面向严重运动模糊、遮挡等退化视频中的连续3D人体姿态重建，指出现有隐式时序注意力在特征崩塌时难以区分有效信号与噪声。
◆论文将退化帧姿态估计重新定义为“运动引导的恢复”任务，而不是简单进行跨帧特征平滑。
◆方法通过特征显著性显式筛选高质量Anchor Frames，并利用其可靠运动与运动学线索修复中间退化帧姿态。
◆提出Dual-path Motion-aware Module捕获细粒度帧间动态，同时用Difference-weighted Fusion Module自适应传播线索并抑制漂移。
◆在Human3.6M、3DPW、PoseTrack和FineDiving等数据集上，Again-Pose在鲁棒性、稳定性和极端场景下的重建质量上显著优于现有方法。</td></tr>
<tr><td>2026-06-25</td><td>Confidence-Aware Tool Orchestration for Robust Video Understanding<br><a href='http://arxiv.org/pdf/2606.26904'>论文</a></td><td>◆论文指出视频推理模型的“盲目信任问题”：默认所有帧同等可靠，导致模糊、眩光、遮挡等扰动下准确率显著下降且无法自知。

◆提出Robust-TO框架，将逐帧可信度显式融入视频理解的证据选择、工具调用和最终推理全过程。

◆设计统一证据接口，协调检测、OCR、动作识别等异构视觉工具，使其输出预测结果、时间定位和校准可靠性分数。

◆引入可靠性-相关性评分选择可信帧，并用高/中/低三层证据综合机制按置信度加权推理。

◆提出置信度-成本GRPO奖励，同时优化答案正确性、证据可靠性和计算效率，在干净与受扰动视频上均取得领先表现。</td></tr>
<tr><td>2026-06-30</td><td>Event-based Gaze Control System for Accurate Real-time Spin Estimation in Professional Ball Games<br><a href='http://arxiv.org/pdf/2606.26780'>论文</a></td><td>◆提出一套事件相机主动视觉系统，结合高速振镜与可调焦长焦镜头，在高速球类运动中持续放大、对焦并跟踪未改装球体。
◆设计混合跟踪策略，将事件驱动的2D检测用于实时居中，并利用3D定位结果进行重初始化，提高比赛场景鲁棒性。
◆提出球面事件对比度最大化方法s-CMax，实现跨乒乓球、棒球、网球和高尔夫的高精度离线旋转估计。
◆面向实时乒乓球应用，构建由伪真值训练的不确定性感知CNN，并结合GPU批量对比度最大化进行快速精修。
◆系统在职业乒乓球三视角实验中达到3毫秒延迟、750Hz吞吐率，并取得8.8%转速幅值误差和6.4度旋转轴误差。</td></tr>
<tr><td>2026-06-25</td><td>Lattice Reconstruction and Orbital Hybridization Suppress Magnetism in TaCo$_2$Te$_2$<br><a href='http://arxiv.org/pdf/2606.26644'>论文</a></td><td>◆ 本文结合STM/STS、nc-AFM、ARPES和DFT，系统揭示了TaCo2Te2中晶格重构、电子结构与磁不稳定性的耦合关系。
◆ nc-AFM解析出畸变六角Te表面晶格，而STM/STS显示类方形电子对称性，说明电子态并不简单跟随原子结构。
◆ ARPES观测到强各向异性费米面和重构低能态，证明晶格重构显著改造其低能电子结构。
◆ 空间分辨谱学和轨道投影DFT表明，STM偏压衬度来自能量积分局域态密度中不同能量态的相反空间衬度，而非简单占据态/未占据态反转。
◆ DFT进一步发现，重构通过增强轨道杂化抑制未畸变结构中的磁不稳定性，稳定非磁基态，使TaCo2Te2成为结构调控磁性与关联相的模型体系。</td></tr>
<tr><td>2026-06-25</td><td>Temporally Consistent Label Interpolation for Robust Surgical Multi-Task Learning under Challenging Conditions<br><a href='http://arxiv.org/pdf/2606.26634'>论文</a></td><td>◆本文针对手术多任务学习中时间任务密集标注与空间任务稀疏标注不匹配的问题，提出了FAROS标签插值框架。

◆FAROS结合零样本分割掩码传播与光流估计，在遮挡、烟雾、运动模糊等复杂手术条件下生成时间一致的密集伪标签。

◆方法将插值后的器械掩码和动作标签融入统一的Transformer多任务模型，同时学习阶段、步骤、预测、器械分割和动作识别。

◆作者先在DAVIS 2017上验证了稀疏标注条件下的传播质量，证明其具备跨领域鲁棒性。

◆在GraSP、MISAW和AutoLaparo上的实验表明，FAROS显著提升了跨任务表征学习与整体手术场景理解性能。</td></tr>
<tr><td>2026-06-24</td><td>Edges Before Embeddings: A Confidence-Aware Blur Gate for Vision-Language Pipelines<br><a href='http://arxiv.org/pdf/2606.25838'>论文</a></td><td>◆ 提出MagikaDocumentFromPixel，一个轻量级CPU图像质量门控，可在约7ms内将输入判为清晰、模糊或不确定，避免下游OCR、检索和VLM在劣质图像上浪费计算。
◆ 通过46种配置、8轮实验搜索，发现输入分辨率是性能主导因素，模型容量只有在384px及以上时才明显收益。
◆ 引入基于选择性预测的置信度感知路由机制，使系统能对不确定样本进行保守处理。
◆ 设计Edge Prior Module，将拉普拉斯幅值作为辅助通道注入网络，直接利用模糊检测所需的边缘频谱证据，F1提升约1.3点。
◆ 最终方案以MobileNetV3-Large、384×384训练和5尺度测试增强达到F1=0.9803、AUC=0.9989，同时作者也明确指出数据分布、单随机种子和校准评估的局限。</td></tr>
<tr><td>2026-07-02</td><td>Shift Variant Image Degradation and Restoration Using Singular Value Decomposition<br><a href='http://arxiv.org/pdf/2606.25818'>论文</a></td><td>◆论文提出了一种基于奇异值分解的移变运动模糊图像复原框架，针对传统单一卷积核难以描述的空间变化退化问题。

◆其核心创新是用位置相关PSF构建移变成像算子，将退化过程统一建模为线性系统并进行SVD分析。

◆论文引入奇异值能量保留准则，系统选择小奇异值数量，以在抑制噪声放大和保留图像细节之间取得平衡。

◆方法覆盖双向线性运动、高斯运动和简谐运动三类一维移变PSF，验证了模型的适用性。

◆实验表明，该SVD稳定反演策略能够有效恢复图像细节、减轻模糊伪影，并揭示移变复原问题的病态特征。</td></tr>
<tr><td>2026-06-24</td><td>1000 Rallies: An Event-Camera Dataset and Real-Time Learned Ball-State Estimation for Robotic Table Tennis<br><a href='http://arxiv.org/pdf/2606.25620'>论文</a></td><td>◆ 提出首个面向乒乓球真实对打场景的大规模事件相机数据集“1000 Rallies”，涵盖1000多回合、不同水平运动员的击球数据。  
◆ 数据集同步采集事件流与14台200 FPS高速相机，并生成1 kHz的球位置、速度和旋转伪真值标签。  
◆ 基于该数据训练了卷积神经网络，可在复杂球员背景运动下从事件数据中联合估计球的图像平面位置与速度。  
◆ 将网络预测的速度作为卡尔曼滤波额外观测后，相比仅用位置的基线，落点预测误差降低36%。  
◆ 系统最终接入Stäubli机械臂，首次实现了由事件视觉驱动的实时人机乒乓球连续对打。</td></tr>
<tr><td>2026-06-24</td><td>EchoStyle: Unlocking High-Fidelity Video Stylization with Reverse Data Synthesis<br><a href='http://arxiv.org/pdf/2606.25465'>论文</a></td><td>◆ EchoStyle提出一个可扩展的文本驱动视频风格化框架，面向任意长度视频实现高保真、稳定的艺术风格迁移。
◆ 它设计了视频到视频架构，更合理地融合原视频内容与文本风格，缓解参考图方法常见的内容泄漏和运动失真。
◆ 论文首创自动化反向数据合成流程，构建了包含2万对高质量视频的V-Style20k数据集，显著缓解训练数据稀缺问题。
◆ 为处理长视频，提出init-follow-mode机制与滑动窗口推理策略，降低风格漂移并提升时序一致性。
◆ 实验证明EchoStyle可适配多种艺术风格，效果接近领先闭源方案，展示了较强的实用性和扩展性。</td></tr>
<tr><td>2026-06-21</td><td>A Theory-grounded Hybrid Neural Network Integrating Complementary Estimation Mechanisms for Stable Visual Object TrackingA<br><a href='http://arxiv.org/pdf/2606.22604'>论文</a></td><td>◆论文提出一种有理论支撑的ANN-CANN混合框架，将人工神经网络与连续吸引子神经网络在同一连续状态空间中对齐。
◆该框架突破了以往HNN主要停留在脉冲/神经元尺度混合的局限，探索了面向连续状态估计的群体尺度混合路径。
◆作者将该框架实例化为视觉目标跟踪网络HTNN，使ANN响应图与CANN动态通过共享状态表示交互。
◆论文揭示并利用了两类机制的偏差-方差互补性：ANN估计渐近无偏，CANN估计方差低但存在时间滞后。
◆实验显示HTNN在九个跟踪基准上稳定优于单一网络和已有混合模型，并在遮挡、运动模糊、背景干扰等复杂场景下保持鲁棒性能。</td></tr>
<tr><td>2026-06-19</td><td>Unsupervised Susceptibility Distortion Correction of EPI without Calibration Scans via Image Translation-Based Registration<br><a href='http://arxiv.org/pdf/2606.21588'>论文</a></td><td>◆ 提出SACRED，一种无需场图或反向相位编码等校准扫描的EPI磁敏感畸变校正框架，仅依赖常规T1w图像和单向PE BOLD图像。
◆ 通过基于图像翻译的配准，将BOLD与T1w之间的模态差异转化为可配准的单对比度问题。
◆ 采用可逆神经网络作为翻译骨干，并结合模态无关邻域描述子约束结构一致性，避免解剖结构被错误改变。
◆ 设计无监督训练目标，不需要真实无畸变BOLD图像即可学习畸变校正。
◆ 引入测试时自适应提升跨扫描仪、跨人群等分布外数据的鲁棒性，并在多个数据集上显著优于代表性方法。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>4910</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4334</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2426</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1615</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1613</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1444</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1276</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1270</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>978</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>957</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>922</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>798</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>781</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>743</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>725</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>713</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>641</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>639</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>625</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>595</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>572</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>558</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>545</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>508</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>501</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>444</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>423</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>348</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>343</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>265</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>254</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>253</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>238</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>223</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>204</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>203</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>171</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>147</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>142</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>119</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2849</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1650</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1357</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1095</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1038</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>869</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>701</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>658</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>649</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>622</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>589</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>575</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>568</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>563</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>552</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>517</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>490</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>463</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>448</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>444</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>335</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>312</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>299</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>284</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>279</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>257</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>222</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>207</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>202</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>186</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>177</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>169</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>168</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>160</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>154</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>138</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>137</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>132</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
<tr><td><a href='https://github.com/ethz-asl/phaser'>phaser</a></td><td>131</td><td>A robust pointcloud registration pipeline based on</td></tr>
<tr><td><a href='https://github.com/ethz-asl/data-driven-dynamics'>data-driven-dynamics</a></td><td>130</td><td>Data Driven Dynamics Modeling for Aerial Vehicles</td></tr>
<tr><td><a href='https://github.com/ethz-asl/ssc_exploration'>ssc_exploration</a></td><td>111</td><td>Incremental 3D Scene Completion for Safe and Effic</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waypoint_navigator'>waypoint_navigator</a></td><td>108</td><td>Stand-alone waypoint navigator</td></tr>
<tr><td><a href='https://github.com/ethz-asl/active_grasp'>active_grasp</a></td><td>108</td><td>Closed-loop next-best view planning for grasp dete</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waverider'>waverider</a></td><td>107</td><td>RMPs on multi-resolution occupancy maps for effici</td></tr>
<tr><td><a href='https://github.com/ethz-asl/reinmav-gym'>reinmav-gym</a></td><td>106</td><td>Reinforcement Learning framework for MAVs using th</td></tr>
<tr><td><a href='https://github.com/ethz-asl/navrep'>navrep</a></td><td>104</td><td>navrep</td></tr>
<tr><td><a href='https://github.com/ethz-asl/eth_supermegabot'>eth_supermegabot</a></td><td>102</td><td>Instructions for ETH center for robotics summer sc</td></tr>
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>102</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/3d_vsg'>3d_vsg</a></td><td>100</td><td>3D可变场景图，用于长期语义场景变化预测。</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.07.09
