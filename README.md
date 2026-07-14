# 计算机视觉领域最新论文 (2026.07.14)

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
<tr><td>2026-07-13</td><td>Self-Healing Visual Recovery for Autonomous Ground Vehicles Using Camera-Only Visual Odometry<br><a href='http://arxiv.org/pdf/2607.11686'>论文</a></td><td>本文针对低成本单目无人车在引导线丢失后的恢复难题,提出了一种无需LiDAR、GPS或GPU的轻量级两阶段自愈式视觉恢复方法,可在仅依赖CPU的硬件上以20Hz实时运行。该方法第一阶段通过原地旋转配合渐进式颜色阈值放宽与多帧确认机制重新捕获引导线,第二阶段在搜索失败后利用单目视觉里程计将机器人回退至先前保存的关键路径点,再重新尝试恢复,系统在119次故障注入实验中取得了86.6%的恢复成功率与3.26秒的中位恢复时间。

◆提出两阶段递进式恢复策略,先放宽视觉检测约束进行原地搜索,失败后回退至历史breadcrumb位置重试,在有限感知条件下有效兼顾恢复效率与成功率
◆将完整MAPE-K自适应控制循环压缩嵌入单个50ms控制周期内,无需外部适配管理器,显著简化了系统架构并降低响应延迟
◆集成深度门控HSV线条跟踪器、YOLOv8n障碍物检测器与单目视觉里程breadcrumb映射器,在纯视觉条件下实现感知、决策与恢复的闭环协同
◆在严格成本与算力限制下,通过大规模故障注入仿真验证了纯视觉自愈恢复方案的工程可行性与实用价值...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-13</td><td>GeoGS-SLAM: Online Monocular Reconstruction Using Gaussian Splatting with Geometric Priors<br><a href='http://arxiv.org/pdf/2607.11184'>论文</a> | <a href='https://rlgao.github.io/geogs_slam'>代码</a></td><td>GeoGS-SLAM提出了一种基于3D高斯泼溅（3DGS）的在线单目稠密重建系统，旨在解决现有方法依赖外部深度传感器或丢弃RGB信息导致重建质量下降的问题。该系统利用预训练的前馈视觉几何模型从无标定RGB输入中预测相机位姿和场景几何先验，并将这些几何先验与RGB信息结合用于高斯场景图的构建与优化。

◆ 结合3DGS表示与学习型几何先验，无需外部深度传感器即可实现高质量单目稠密重建

◆ 直接从RGB输入和几何先验中采样高斯基元进行场景扩展，充分利用两种信息源

◆ 采用由粗到精的联合优化策略，同时最小化光度损失和几何损失，提升位姿估计与建图精度

◆ 引入在线回环检测和位姿图优化，确保全局一致性

◆ 保持在线实时性能，在室内外基准测试中渲染质量与跟踪精度均优于现有方法...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-13</td><td>Desc++: Efficient Descriptor Enhancement for Data Association in Existing Visual SLAM Systems<br><a href='http://arxiv.org/pdf/2607.11099'>论文</a></td><td>视觉SLAM依赖可靠的数据关联，而传统手工描述符在光照和视角变化下鲁棒性下降，学习型前端又需替换整个提取匹配流程且计算开销大。为此论文提出Desc++轻量级描述符增强模块，通过混合架构联合编码描述符表征与关键点几何信息，结合顺序无关的全局注意力与几何感知的序列建模，在线性时间内实现空间上下文聚合。该模块保持原始描述符维度与匹配接口不变，可直接嵌入现有V-SLAM系统而无需修改流程。在描述符匹配、对应关系分析及四个V-SLAM系统级基准测试中的实验表明，Desc++在匹配精度和轨迹估计稳定性上均优于现有增强方法，并实现了精度与效率的良好平衡。

核心创新点：
◆ 联合编码描述符表征与关键点几何信息，弥补传统描述符上下文建模不足
◆ 混合架构融合顺序无关的全局注意力与几何感知序列建模
◆ 线性时间复杂度，兼顾上下文表达力与计算效率
◆ 即插即用设计，保留原始描述符维度和匹配接口，兼容已部署V-SLAM系统...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-12</td><td>Mapping Pamir: Multi-Session Visual-Inertial SLAM and 3D Reconstruction of an Underwater Shipwreck<br><a href='http://arxiv.org/pdf/2607.10925'>论文</a></td><td>本文提出了一种面向水下环境的多会话三维重建框架，使用低成本运动相机采集视觉惯性数据，并融合潜水电脑的水深信息以提升尺度估计。系统首先利用开源的SVIn2视觉惯性SLAM框架生成各会话的相机轨迹与稀疏重建，再通过COLMAP结构光束法进行全局优化与稠密重建。针对多会话数据融合难题，论文利用固定位置的标定靶估计不同会话间的坐标变换矩阵，从而将各次采集统一到同一参考系中。该方法被实际应用于巴巴多斯海岸的&quot;帕米尔号&quot;沉船，首次实现了沉船外部结构与可进入内部区域在两次会话中的完整三维映射，并在第三次会话中同时使用两台不同视场的相机进行联合采集。

◆提出结合消费级运动相机、视觉惯性SLAM（SVIn2）与COLMAP的级联式水下多会话重建管线，实现从稀疏定位到稠密建图的全流程处理。

◆将潜水电脑测得的水深信息融入视觉惯性数据，有效解决了水下单目尺度漂移问题。

◆利用固定标定靶估计会话间坐标变换，无需依赖外部定位设备即可实现多时段数据在统一坐标系下的融合。

◆首次对沉船内外整体结构进行多会话联合建模，并验证了异构视场多相机配置下的协同建图可行性。</td></tr>
<tr><td>2026-07-11</td><td>CSI-Assisted Edge SLAM Testbed Platform for 5G Connected Unmanned Autonomous Vehicles<br><a href='http://arxiv.org/pdf/2607.10394'>论文</a></td><td>本文设计并实现了一个面向5G连接无人车的CSI辅助边缘SLAM测试床平台,系统性地整合了定制无人地面车、基于ROS2的SLAM框架以及5G O-RAN系统,提供从机器人传感器数据经5G网络传输到边缘服务器进行SLAM处理的端到端跨层视角。论文深入分析了ROS2 DDS通信、RTPS报文封装以及5G用户面传输机制,并探讨了如何通过O-RAN组件提取和传递信道状态信息(CSI)以融入SLAM流水线。核心创新点如下:

◆ 构建了首个集成CSI感知能力的端到端边缘SLAM测试床,将无线电感知与机器人定位建图在5G O-RAN架构下深度融合。

◆ 实现了ROS2传感器数据流经5G O-RAN用户面传输的完整链路,打通了机器人中间件与移动通信系统的跨层接口。

◆ 提出了基于O-RAN组件的CSI提取与交付机制,使信道信息可作为新型感知模态被SLAM流水线直接调用。

◆ 通过真实实验揭示了通信感知一体化场景下延迟、数据流、同步及跨系统集成等关键挑战,为6G机器人平台设计提供了工程参考。</td></tr>
<tr><td>2026-07-10</td><td>What VGGT Knows About Overlap: Probing Geometric Foundation Models for Co-Visibility<br><a href='http://arxiv.org/pdf/2607.09503'>论文</a></td><td>本文揭示了VGGT几何基础模型在无监督情况下隐式编码共可见性的涌现行为，其内部表征呈现类似大语言模型的层次化结构。◆研究发现早期层负责构建三维场景感知表示，后期层则专门进行共可见性推理，其中第L17层被识别为稳定路由非共可见图像对的负锚点，体现了层间任务专精化。◆提出Co-VGGT方法，冻结VGGT主干，仅训练不到7.5M参数的层级混合专家头，将每层视为根据输入对自适应加权的几何抽象专家。◆在Co-VisiON基准上超越人类标注基线，成对和多视图性能分别提升超过25%和10%。◆预测结果校准良好（ECE=0.030），可直接作为边权重用于下游SfM和SLAM流程，无需后处理校正。</td></tr>
<tr><td>2026-07-10</td><td>AnythingReality: Robust Online Gaussian Splatting SLAM for Open-Vocabulary VR Scene Exploration<br><a href='http://arxiv.org/pdf/2607.09260'>论文</a></td><td>本文提出AnythingReality系统，首次将在线3D高斯泼溅、实时VR探索与语音驱动的视觉语言模型交互三者进行端到端集成，面向开放词汇VR场景探索任务。
◆ 采用ORB-SLAM3位姿估计与在线高斯重建相结合的鲁棒架构，专门针对含噪声的真实数据进行设计，打破了以往方法依赖干净深度或外部位姿的假设
◆ 构建支持增量重建的VR沉浸式探索管线，实现对动态生成场景的实时交互式浏览
◆ 设计语音驱动的语义模块，可转录语音指令、生成场景描述并自动记录兴趣点
实验结果表明，该方法在自建数据集与TUM-RGBD上的图像质量均显著优于当前最优的在线高斯泼溅方法（PSNR最高提升14.5%，LPIPS最多降低21.6%），并通过质量-速度可调配置保持可比或更优的帧率，最终实现了88%的VLM目标识别率，验证了开放词汇交互的有效性。</td></tr>
<tr><td>2026-07-09</td><td>Track2Map: Online Deformable SLAM with Motion-Aware Pose Optimization in Robotic Surgery<br><a href='http://arxiv.org/pdf/2607.08408'>论文</a> | <a href='https://track2map.github.io/'>代码</a></td><td>Track2Map是一种面向机器人辅助微创手术的在线可变形SLAM系统,基于3D高斯泼溅技术,直接从手术视频中联合优化相机轨迹与三维可变形场景重建,无需依赖精确的先验位姿信息。该方法突破了现有离线管道的限制,在相机轨迹先验缺失或存在噪声的情况下仍能稳定工作,实现了真正的同步定位与地图构建。为应对组织运动和视觉歧义带来的优化困难,作者提出了一系列基于稠密2D点轨迹的创新机制,显著提升了重建质量与位姿精度。

◆ 提出在线3D高斯泼渍SLAM框架Track2Map,联合优化相机轨迹与可变形场景表示,摆脱对先验轨迹的依赖。

◆ 引入轨迹锚定的形变初始化策略,利用稠密2D点轨迹稳定组织运动下的优化过程。

◆ 利用轨迹统计信息区分相机运动与场景形变,自动检测静止相机时段以减少增量建图中的漂移。

◆ 在StereoMIS数据集上验证,重建质量与相机轨迹精度均优于现有SLAM及依赖先验的非SLAM方法。</td></tr>
<tr><td>2026-07-09</td><td>RadLoc: Radar-based 3-DoF Global Localization via Fast, Robust, and Lightweight Spatial Descriptor Across Diverse Environmental Scenarios<br><a href='http://arxiv.org/pdf/2607.08115'>论文</a> | <a href='https://sparolab.github.io/research/radloc/'>代码</a></td><td>针对旋转雷达的全局定位问题，本文提出了端到端轻量化流水线RadLoc，将位置识别与3自由度位姿估计整合为一体，并在5个数据集的15个序列上验证了其跨场景的鲁棒性。

◆ 采用1D CA-CFAR滤波加速雷达数据预处理流程，显著提升计算效率。
◆ 利用旋转雷达图像中近距信号占优的特性，设计了紧凑型空间描述符。
◆ 提出由粗到精的分层检索策略，在保证精度的同时实现最快检索速度。
◆ 结合相位相关方法实现3自由度位姿估计，可直接集成于SLAM及多会话SLAM系统。

实验结果表明，RadLoc在描述符尺寸和检索时间上均优于现有最先进方法，同时保持稳定可靠的定位性能。</td></tr>
<tr><td>2026-07-08</td><td>STEMbot: A Compliant Robot for Under-Canopy Plant Navigation<br><a href='http://arxiv.org/pdf/2607.07873'>论文</a></td><td>有机农业的可扩展性受限于叶片下部和茎部害虫监测所需的高昂人力成本。为实现早期害虫检测，本文提出STEMbot，一种用于植物冠层下自主导航的微型攀爬机器人系统。
◆针对现有攀爬平台缺乏机载感知或仅限于无分支垂直主干的问题，STEMbot在攀爬过程中将基于几何的PIN-SLAM管线与语义OcTree相集成，实现了鲁棒的定位与建图。
◆提出了流形约束A*规划器结合光线追踪目标指定方法，实现了分支感知的穿越与遮挡目标的检查。
◆硬件实验表明，系统可穿越7-33mm直径的茎部，并在四种植物上完成自主导航，平均Chamfer距离小于1cm，验证了全局一致的里程计精度。</td></tr>
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
<tr><td>2026-07-08</td><td>Dynamic Object Detection and Tracking in Construction: A Fisheye Camera and LiDAR Sensor Fusion Model<br><a href='http://arxiv.org/pdf/2607.06896'>论文</a></td><td>本文针对建筑工地等复杂环境中机器人动态目标检测与跟踪的难题，提出了一种基于LiDAR与鱼眼相机融合的轻量级实时框架。系统部署在四足机器人上，利用LiDAR获取三维点云并通过占据栅格方法识别运动目标，再将三维坐标投影到二维圆柱全景图上完成语义标签分配。语义信息通过基于图像的实时检测结果更新，并输入卡尔曼滤波器以实现对目标运动状态的持续跟踪。该方法在保证高精度的同时，避免了对大规模预训练神经网络的依赖，具有结构简洁、响应快速的特点，特别擅长处理目标在动态与静态之间切换的过渡场景。

◆ 提出基于LiDAR点云与向上鱼眼相机的多传感器融合动态目标检测框架，部署于四足机器人平台，适用于建筑工地等复杂环境。
◆ 创新性地将三维点云投影至二维圆柱全景图，实现点云与图像在统一坐标下的语义对齐，简化了融合流程。
◆ 通过基于图像的实时检测结果更新卡尔曼滤波器观测，实现动态与静态目标状态转换的鲁棒跟踪。
◆ 相比依赖预训练网络的方案，该方法结构更简洁、计算开销更低，更适合实时部署。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-13</td><td>SalientGS: Unified SfM-to-3DGS with Importance-Guided MCMC Gaussian Allocation<br><a href='http://arxiv.org/pdf/2607.11285'>论文</a> | <a href='https://github.com/Six-Bit-TX/SalientGS'>代码</a></td><td>SalientGS提出了一种统一的SfM到3D高斯溅射（3DGS）的端到端重建流水线，旨在消除传统3D场景重建中昂贵的SfM预处理和冻结位姿接口的瓶颈。其核心创新在于引入了重要性引导的MCMC高斯分配策略，通过聚合多视图残差来计算每个高斯点的欠拟合度和冗余度信号。系统利用这些信号构建平滑的重要性加权采样分布，使得高斯点的生成和重定位偏向欠拟合区域，从而在不改基础随机梯度朗之万动力学的前提下，将渲染能力从已拟合良好的区域重新分配到欠拟合区域。SalientGS能够在15分钟内完成端到端重建，并在感知质量上达到最先进水平。◆统一了SfM与3DGS流水线，实现了无需外部预处理的高效端到端三维重建。◆通过多视图残差聚合定义高斯点的重要性信号（欠拟合度与冗余度），实现细粒度的容量分配。◆在保留SGLD框架的基础上，以重要性加权采样分布引导MCMC的生灭与重定位过程，避免了底层动力学修改。</td></tr>
<tr><td>2026-07-12</td><td>Mapping Pamir: Multi-Session Visual-Inertial SLAM and 3D Reconstruction of an Underwater Shipwreck<br><a href='http://arxiv.org/pdf/2607.10925'>论文</a></td><td>本文提出了一种利用低成本运动相机进行水下环境多会话建图的框架，将视觉惯性数据与潜水电脑记录的水深信息相融合。框架使用开源的SVIn2视觉惯性SLAM系统生成各会话的轨迹与稀疏重建，再结合关键帧与相机位姿，通过COLMAP结构光束法进行全局优化并生成稠密三维重建。当场景中存在固定位置的标定靶时，可用于估计不同数据采集会话之间的坐标变换，从而将多会话数据统一到同一坐标系下。该方法被成功应用于巴巴多斯海岸的&quot;帕米尔号&quot;沉船，首次同时完成了沉船外部和可进入内部的完整映射，并通过第三个会话使用两台不同视场的相机进一步增强了重建效果。

核心创新点总结如下：
◆ 提出融合低成本运动相机、视觉惯性里程计与潜水电脑水深数据的水下多会话建图整体框架
◆ 采用标定靶估计多会话间的坐标变换，实现不同数据采集会话的全局对齐
◆ 将SVIn2与COLMAP相结合，充分发挥VI-SLAM的实时轨迹估计与SfM的稠密重建优势
◆ 首次对帕米尔号沉船的外部与可进入内部完成完整的多会话三维重建与映射...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-11</td><td>Navigating the Crowd: Non-linear MPC with Social Forces Dynamics for Human-Aware Robot Navigation<br><a href='http://arxiv.org/pdf/2607.10374'>论文</a></td><td>本文针对人机共融环境中机器人安全且符合社会规范的导航问题，提出了SFM-NMPC框架，将社会力模型(SFM)与非线性模型预测控制(NMPC)深度融合。其核心思想是在优化循环内嵌入对周围行人运动轨迹的预测，使控制器能够联合预测人与机器人在预测时域内的运动，从而实现具有社会意识的规划。

◆将社会力模型集成到NMPC的动态模型中，在优化循环内直接预测行人轨迹，实现人机轨迹的联合优化。

◆设计了针对性的社会成本函数，引导优化过程产生尊重个人空间、符合人类舒适度要求的行为。

◆在增加模型复杂度的同时，通过高效求解实现20Hz的实时控制，满足实际部署需求。

◆在拥挤环境仿真中验证了方法在社会合规性指标上优于现有先进方法，并通过消融实验证明了嵌入式SFM动力学和社会成本项的贡献。</td></tr>
<tr><td>2026-07-10</td><td>DGSfM: Depth-Guided Scale-Aware Global Structure-from-Motion<br><a href='http://arxiv.org/pdf/2607.09507'>论文</a> | <a href='https://github.com/sithu31296/DGSfM'>代码</a></td><td>DGSfM提出了一种深度感知的全局SfM流程，旨在解决传统全局SfM因依赖尺度模糊的本质几何约束而对噪声基线和弱视图图约束敏感、且易受视觉模糊对误匹配边影响的问题。该方法将单目深度图作为可扩展先验融入全局优化，同时保留显式多视图优化框架。其核心策略包括：利用深度感知相对位姿求解器将尺度模糊的对极约束转化为尺度感知的相对位姿约束，并通过视图图过滤和基于深度一致性的匹配剪枝来抑制误边和误匹配，最后通过全局尺度平均和深度引导的位姿-点初始化将单目深度图对齐到统一重建尺度，为全局定位和光束法平差提供稳定初值。实验表明，DGSfM在ETH3D和IMC2021数据集上，无论稀疏还是稠密匹配前端均显著优于强基线方法，在位姿精度上取得实质性提升。

◆ 深度感知相对位姿求解器：将尺度模糊的对极几何约束升级为尺度感知的相对位姿约束，从源头缓解基线估计噪声对全局定位的影响

◆ 视图图过滤与深度一致性匹配剪枝：在多视图一致性层面抑制视觉模糊对产生的误边和误匹配，提升视图图鲁棒性

◆ 全局尺度平均与深度引导初始化：将多张单目深度图统一对齐到公共重建尺度，为全局定位和光束法平差提供稳定、尺度一致的初值

◆ 与前端匹配的解耦设计：方法不依赖特定匹配器，在稀疏和稠密匹配前端上均能获得一致的精度提升，具备良好的通用性...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-10</td><td>What VGGT Knows About Overlap: Probing Geometric Foundation Models for Co-Visibility<br><a href='http://arxiv.org/pdf/2607.09503'>论文</a></td><td>本文揭示了VGGT这一几何基础模型隐式编码图像对共可见性（co-visibility）的涌现能力，无需任何任务监督即可实现。研究发现其内部表征呈现类似大语言模型的层级结构：早期层构建3D场景感知表示，而晚期层则专门用于共可见性推理，其中第17层被识别为稳定的&quot;负锚点&quot;层。

◆ 发现几何基础模型中存在类似LLM的层级功能分化，并定位L17层为非共可见对的负锚点，为层专业化提供了任务驱动的实证。

◆ 提出Co-VGGT方法，冻结VGGT主干网络，仅训练一个轻量化的层级混合专家（MoE）头（参数少于7.5M），将每层视为自适应加权的几何抽象专家，从单目RGB直接分类共可见性。

◆ 在Co-VisiON基准上超越人类标注基线，相较先前工作提升超过25%（成对）和10%（多视角），且预测具有良好校准度（ECE=0.030），可作为可见性图的边权重直接用于下游SfM和SLAM流程。</td></tr>
<tr><td>2026-07-10</td><td>Glob3R: Global Structure-from-Motion with 3D Foundation Models<br><a href='http://arxiv.org/pdf/2607.09225'>论文</a> | <a href='https://junyuandeng.github.io/Glob3r'>代码</a></td><td>Glob3R是一个结合3D基础模型与全局优化的SfM重建框架，旨在解决现有前馈基础模型（如VGGT/Pi3X）在长序列或大规模无序图像上精度不足、分块处理易产生漂移和不一致的问题。其核心思想是显式优化基础模型的前馈几何预测，融合深度学习的强先验与经典几何的全局一致性。

核心创新点：
◆ 在冻结的Pi3X骨干网络上增加轻量级稠密匹配头，预测参考帧与邻近视图间的图像形变，并将其转化为稀疏但可靠的多视图特征轨迹，为全局优化提供对应约束。
◆ 提出基于关键帧的滑动窗口关联策略，通过跨重叠窗口传播轨迹和相对位姿，实现可扩展的大规模场景重建。
◆ 通过全局运动平均和光束法平差精修相机位姿、消除尺度不一致，并恢复稠密场景几何。

在室内、室外、大规模驾驶和无序SfM等多类基准上，Glob3R显著优于前馈基础模型基线和现有可扩展重建方法，且比经典SfM更具鲁棒性；精修后的位姿还显著提升了神经渲染质量，验证了基础模型先验与全局几何优化结合的有效性。</td></tr>
<tr><td>2026-07-10</td><td>Empirical Pedestrian Safety Assessment in a Mobile Robot Using a Predictive Social Force Model<br><a href='http://arxiv.org/pdf/2607.09192'>论文</a></td><td>本文针对移动机器人在人行道上与行人共享空间的安全性问题，提出并实证评估了预测型社会力模型。
◆将预测的社会力向量在有限时间范围内进行积分，构建了预测型SFM（PSFM）和预测型TSFM（PTSFM），拓展了传统社会力模型的预测能力。
◆在非完整约束移动机器人平台上系统对比SFM、TSFM、PSFM和PTSFM四种模型，结合客观安全指标（最小PTTC、平均速度、最小距离、轨迹曲率）与Likert量表主观问卷进行全面的实证评估。
实验发现PTTC的引入能够显著提升客观安全性能指标，但预测机制的额外贡献较为有限。
主观评价方面，部分参与者感受到预测方法带来更平滑的运动和更安全的速度，但Mann-Whitney检验未显示统计显著差异。
研究表明基于PTTC的导航能有效增强安全性，但在单行人场景中预测机制的附加价值尚不明显。</td></tr>
<tr><td>2026-07-09</td><td>Deep Spectroscopic Follow-Up of Maisie&#x27;s Galaxy -- A Typical Galaxy in the Early Universe<br><a href='http://arxiv.org/pdf/2607.08749'>论文</a></td><td>本文对高红移星系Maisie&#x27;s Galaxy进行了深度光谱研究,利用JWST两个Cycle 3 NIRSpec G395M项目共19小时以上的曝光时间结合MIRILRS观测,精确测定了其红移(z=11.408)、恒星形成率、金属丰度与电离参数等关键物理量。

◆创新点:首次将双Cycle 3 NIRSpec深度光谱与MIRILRS中红外观测相结合,实现对z&gt;10亮源的多波段全面光谱表征
◆创新点:通过[OII]双线精确测定电子密度与恒星形成率,发现该星系位于恒星形成主序上,表明早期宇宙亮源并非都是极端天体
◆创新点:利用Ne3O2比值首次精确测定了该红移处的金属丰度(Z/Z☉=0.17±0.05)与电离参数,并与SED拟合结果交叉对比验证

研究表明,先前被标记为&quot;极端&quot;的早期宇宙亮源实为典型星系,未来需要更深度观测以理解早期星系的平均性质。</td></tr>
<tr><td>2026-07-08</td><td>NoDrift3R: Raymap-Guided Coupling for Drift-Robust Unposed Feed-Forward 3D Reconstruction<br><a href='http://arxiv.org/pdf/2607.07168'>论文</a></td><td>该论文针对无位姿前馈三维高斯溅射在长序列中因位姿漂移导致重建质量退化的问题，提出了一种几何与外观显式协同的新框架。作者识别出位姿累积漂移是制约性能的主要瓶颈，并指出SfM伪真值引入传感器噪声、纯渲染监督易陷入局部最优等矛盾。

◆ 提出Raymap-Guided Coupling Module（RGC）模块，将高斯中心锚定到光线图诱导的几何上，在统一目标下联合优化RGB重建、光线图一致性与相机正则化，形成几何与外观之间的双向反馈循环。

◆ 设计Dual-Frequency Viewpoint Scheduling策略，结合由易到难的间隔扩展与短间隔对回放，稳定长时序学习过程。

在域内和跨域数据集上的大量实验表明，该方法在渲染质量与位姿估计上均取得一致提升，长序列鲁棒性显著增强，验证了几何-外观显式协同是实现可扩展、无漂移无位姿前馈三维重建的关键。</td></tr>
<tr><td>2026-07-08</td><td>The MAGPI Survey: Evidence for Non-Universal Resolved Dust Attenuation Relations Beyond the Local Universe<br><a href='http://arxiv.org/pdf/2607.07122'>论文</a></td><td>本文利用MAGPI巡天（0.25&lt;z&lt;0.42）中178个星系的巴耳末减幅图，系统研究了中等红移下尘埃消光（A_V）与恒星形成率面密度（Σ_SFR）的空间分辨关系，并与本地MaNGA样本进行对比分析。

研究发现MAGPI星系中A_V与Σ_SFR存在显著正相关，但在固定Σ_SFR下其消光系统性高于本地MaNGA样本，表明两者之间存在整体性偏离。

◆即使在匹配恒星质量（M*）和偏离主序程度（ΔSFMS）后，MAGPI星系仍表现出更高的消光，说明空间分辨的A_V-Σ_SFR关系并非普适。

◆消光偏差的大小强烈依赖于星系在主序上的位置：低于主序的星系偏差最大（ΔA_V约0.40 mag），主序上星系约0.28 mag，高于主序的星系仅约0.07 mag，呈现明显的渐进趋势。

◆该结果揭示了kpc尺度上的消光不仅受局部恒星形成活动调控，还受宿主星系整体演化状态的影响，提示本地校准的消光关系不能简单外推至更高红移的星系研究。</td></tr>
<tr><td>2026-07-12</td><td>Deep far-UV observations of the ELAIS N1 field using AstroSat: Source catalogue, spectral energy distribution modelling and star formation<br><a href='http://arxiv.org/pdf/2607.06143'>论文</a></td><td>本文利用AstroSat卫星上的紫外成像望远镜(UVIT)对ELAIS N1深场进行了F154W波段(far-UV)的深度观测,总曝光时间达30千秒,通过CCDLAB v3.0进行数据处理,获得了1637个3σ和458个5σ的FUV源目录,极限星等分别为25.69和25.13 mag(AB),为该天区提供了目前最深的FUV测光数据。

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
<tr><td>2026-07-09</td><td>PanoImager: Geometry-Guided Novel View Synthesis and Reconstruction from Sparse Panoramic Views<br><a href='http://arxiv.org/pdf/2606.27071'>论文</a></td><td>◆ PanoImager针对稀疏全景图在旋转主导、弱视差场景下SfM/SLAM初始化不稳定的问题，提出了一个无需SfM的三维重建框架。
◆ 方法将全景图分解为局部透视视图，并利用前馈式位姿与深度先验提供初始几何约束。
◆ 通过几何条件扩散模型合成辅助新视角，补充稀疏输入中缺失的观测信息。
◆ 结合深度引导的3D Gaussian Splatting优化，提升跨视角一致性并稳定重建过程。
◆ 实验表明，该方法在极端稀疏全景输入下具有更好的鲁棒性，可作为SfM/SLAM失败时的离线地图细化组件。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-07</td><td>MiLSD: A Micro Line-Segment Detector for Resource-Constrained Devices<br><a href='http://arxiv.org/pdf/2607.06600'>论文</a></td><td>针对MCU级资源受限设备上线段检测的挑战，本文提出MiLSD系统，在亚兆字节内存预算内最大化检测精度，并系统研究表征方式、量化位宽与后处理策略之间的权衡关系。

◆提出F-Clip线段表示方法，将线段建模为中心点结合长度与角度参数，在紧凑全卷积骨干下学习效率优于其他表示形式。

◆系统对比三种输出表示与不同位宽量化方案，发现8位量化基本保持全精度性能，4位量化在角度回归上退化严重，量化感知训练仅能部分恢复。

◆融合子像素解码、测试时增强与轻量级验证器等推理增强技术，将ShanghaiTech Wireframe数据集sAP10从0.25MB模型下的10.6提升至1MB预算下的24.1。

◆首次绘制了嵌入式视觉系统中表征方式、量化位宽、模型容量与后处理策略多维度的精度-内存权衡全景图，为后续微小型线段检测器设计提供参考。</td></tr>
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
<tr><td>2026-07-11</td><td>Navigating the Crowd: Non-linear MPC with Social Forces Dynamics for Human-Aware Robot Navigation<br><a href='http://arxiv.org/pdf/2607.10374'>论文</a></td><td>该论文针对机器人在人群环境中的安全与社交合规导航问题，提出了SFM-NMPC框架，将社会力模型（Social Force Model）嵌入非线性模型预测控制（NMPC）的优化过程中。该方法将社会力模型整合到周围行人的动态模型中，使控制器能够在预测时域内联合预测人类和机器人的轨迹，实现社交感知的运动规划。

◆创新点一：将社会力模型直接嵌入NMPC的动力学模型中，把人类运动预测融入优化闭环，突破了传统方法将预测与控制分离的局限。
◆创新点二：设计了针对社交合规性的代价函数集合，引导优化过程产生尊重个人空间、符合人类舒适度的行为。
◆创新点三：尽管模型复杂度增加，算法仍以20 Hz的频率实时运行，兼顾了计算效率与社会合规性。
◆创新点四：在拥挤仿真环境中的大量测试表明，该方法在社交合规指标上优于现有先进基线，并通过消融实验验证了社会力动力学和社交代价项各自的有效性。</td></tr>
<tr><td>2026-07-11</td><td>Robotic Contextual Awareness for Human-Robot Collaboration and Environmental Understanding<br><a href='http://arxiv.org/pdf/2607.10372'>论文</a></td><td>这篇论文针对自主移动机器人在动态人本环境中的情境感知挑战，提出两个互补的创新研究方向。第一个方向聚焦人员再识别与跟踪，使机器人能够识别特定目标人员以实现精准协作；第二个方向从几何与语义两个维度增强机器人的环境感知能力，几何信息支撑运动规划与避障，语义理解则为人机交互提供更丰富的认知。两个方向共同强化了机器人对其所处环境的语义理解，从而实现更自然流畅的人-机-环境交互，为机器人安全共存与高效协作奠定基础。

创新点：
◆ 提出面向人机协作的人员再识别与跟踪方法，使移动机器人能够在多人场景中精准锁定目标个体，忽略无关人员
◆ 构建融合几何结构与语义信息的环境理解框架，兼顾运动规划避障需求与高层语义认知
◆ 通过强化机器人的情境语义理解，推动人-机-环境之间更自然、自适应的协作与共存...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-10</td><td>SEAMLiS: Visibility-Aware Safety for Perception-Limited Multi-Robot Exploration<br><a href='http://arxiv.org/pdf/2607.09959'>论文</a></td><td>本文针对有限感知范围和视场下多机器人自主探索中，探索规划与局部安全控制解耦所引发的安全隐患，提出SEAMLiS模块化执行层安全框架。该框架独立于上游探索栈，通过感知感知的姿态和位置滤波器在执行层强制保障安全，不改变原有规划逻辑。其中，基于门控器的姿态滤波器在促进可见性的偏航策略与跟踪速度的备份策略间自适应切换，以保证对已知自由/未知边界的持续可视性及充足制动余量；基于控制屏障函数（CBF）的位置滤波器则统一实现对已知障碍、新检测障碍及其他机器人的避碰。论文给出了充分的避碰理论条件。最终在随机仿真、Isaac Sim及Crazyflie硬件实验中的多场景验证表明，该方法在保持可见性偏航控制效率的同时实现了无碰探索。

◆ 将安全约束与上游探索规划解耦，以模块化执行层框架保护现有探索栈不变
◆ 设计双模态门控偏航策略，在信息获取与制动安全之间进行自适应切换
◆ 基于CBF的位置滤波器统一处理已知障碍、新检测障碍及多机器人避碰
◆ 给出避碰的充分理论条件，并通过仿真与实物多场景实验进行系统验证...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-08</td><td>Time-to-Collision Based Dynamic Obstacle Avoidance Using Pretrained Vision Models for Robots in Unstructured Environments<br><a href='http://arxiv.org/pdf/2607.07885'>论文</a></td><td>这篇论文提出了一种基于视觉的动态障碍物避障方法,完全基于真实世界数据运行,有效避免了仿真训练策略中的sim-to-real迁移难题。该方法利用预训练的单目深度估计模型UniDepth从RGB视频生成稠密深度图,无需依赖立体相机或激光雷达;同时扩展了SuperPoint和SuperGlue特征匹配流程以实现长序列关键点跟踪,结合相机内参与预测深度将2D像素位置投影到3D空间,并通过光束法平差优化后计算每个关键点的碰撞时间(TTC),据此选取规避运动方向。

◆ 利用预训练UniDepth从单目RGB获取稠密深度,推理阶段无需立体相机或激光雷达
◆ 扩展SuperPoint/SuperGlue实现长序列关键点跟踪并投影到3D空间构建运动轨迹
◆ 基于光束法平差后的3D关键点计算每点TTC,以最小TTC点驱动2D运动基元选择
◆ 纯几何可解释的模块化流水线,完全无需模型训练,仅用74秒数据即可完成超参调优

在M3ED真实数据集上的评估表明,该方法在识别TTC小于1秒的帧时达到0.49的精度和0.38的召回率,并在84%的真阳性中正确生成规避方向,对22个独特物理障碍物中的20个能成功检测出至少一帧TTC低于1秒的情况,展现了出色的数据效率与泛化能力。</td></tr>
<tr><td>2026-07-08</td><td>Social-spatial dependencies for learning visual navigation<br><a href='http://arxiv.org/pdf/2607.07460'>论文</a></td><td>本文研究社会环境中神经网络智能体的视觉导航问题，揭示社会依赖性由任务表现与空间效应共同塑造。
◆ 提出融合社会信息质量与空间位置效应的视觉导航学习框架，量化群体结构对个体策略的影响。
◆ 发现高质量社会信息可驱动智能体经历从独立导航到跟随策略再到避碰行为的相变。
◆ 揭示可预测非平稳环境下出现行为杂交现象，智能体在远端采用个体导航、近端采用社会导航。
◆ 挑战仅检查个体行为的传统范式，倡导通过群体交互自下而上地理解社会性生物行为机制。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-13</td><td>Learning to Navigate Efficiently with Only 0.58M Trainable Parameters<br><a href='http://arxiv.org/pdf/2607.11029'>论文</a></td><td>该论文挑战了视觉导航领域&quot;以规模换性能&quot;的范式，提出一种将解析计算与小型学习模块解耦的导航框架，仅用0.58M可训练参数便逼近当前最先进方法的性能。

◆核心创新在于结构化分解：投影几何、占据和坐标变换等具有闭式解的操作以解析方式计算，作为三个小型学习模块之间的接口，分别完成目标定位、出行分布估计和轨迹残差生成。

◆极致参数效率：在22.7M总参数中仅训练0.58M，训练数据仅需44k帧、单卡不到1小时，可训练参数比基线少233倍，且碰撞率最低、推理速度达50Hz。

◆良好的可迁移性与可解释性：通过仅重训123k参数的出目标头即可迁移至无目标探索任务，且在传感器损坏时的失效模式透明、可通过解析方法修正。</td></tr>
<tr><td>2026-07-13</td><td>Think When It Matters: Conditional VLM Reasoning for Social Navigation with RL Policies<br><a href='http://arxiv.org/pdf/2607.10991'>论文</a></td><td>这篇论文针对社交机器人导航中强化学习策略缺乏灵活语义推理能力、而视觉语言模型推理速度慢难以实时部署的矛盾，提出了HUMA混合架构。该架构让响应式RL策略负责常规低密度导航任务，仅在人类进入机器人邻近区域等敏感情境时触发VLM进行高级语义推理。通过这种条件化设计，系统在保持实时性的同时获得了VLM的深度社会推理能力。在Social-MP3D和Social-HM3D基准上的实验表明，该方法分别取得了20%和3%的任务成功率提升，同时显著降低了个人空间侵犯和碰撞次数。此外，方法在Mirokaï移动机器人上的真实部署进一步验证了其实际可行性。

创新点：
◆ 提出HUMA混合架构，将RL的实时响应性与VLM的语义推理能力动态融合
◆ 设计条件触发机制，仅在必要时调用VLM，兼顾推理速度与社会理解深度
◆ 通过系统消融实验和真实机器人部署验证了各模块的有效性与实用性...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-11</td><td>Navigating the Crowd: Non-linear MPC with Social Forces Dynamics for Human-Aware Robot Navigation<br><a href='http://arxiv.org/pdf/2607.10374'>论文</a></td><td>本文提出SFM-NMPC框架，将社会力模型嵌入到非线性模型预测控制中，解决拥挤环境中机器人的安全和社会合规导航问题。核心思想是把人类运动预测融入优化循环，通过将社会力模型作为周围代理的动力学模型，控制器在预测时域内联合预测人类和机器人轨迹，实现社会感知规划。

主要创新点如下：

◆ 将社会力模型直接嵌入NMPC的动态模型中，使人类运动预测成为优化的一部分，实现轨迹的联合预测。
◆ 设计了一套针对性的社会成本函数，引导优化过程产生尊重个人空间、符合人类舒适度的行为。
◆ 在提升模型复杂度的同时，实现了20Hz的实时运行，兼顾计算效率与社会合规性。
◆ 在拥挤仿真场景中，在社会合规指标上超越现有先进方法，并通过消融实验验证了嵌入SFM动力学和社会成本项的关键作用。</td></tr>
<tr><td>2026-07-11</td><td>PIER-Flow: Physics-Informed Efficient Rectified Flow for Real-Time Mobile Robot Navigation<br><a href='http://arxiv.org/pdf/2607.10288'>论文</a></td><td>针对密集动态环境中自主导航对物理可行性与低延迟规划的矛盾，本文提出PIER-Flow框架，将MPC专家策略蒸馏为连续时间常微分方程，实现单步动作生成。

◆ 将基于优化的MPC专家蒸馏为ODE形式的Rectified Flow策略，通过并行潜空间采样与轻量可行性选择实现单步动作生成，兼具多模态表达与毫秒级推理。

◆ 引入物理信息训练目标，将运动学一致性作为约束嵌入学习过程，确保生成动作满足机器人可行性。

◆ 设计异步动作分块架构以增强仿真到真实的迁移鲁棒性，缓解边缘设备推理延迟波动问题。

实验显示PIER-Flow在仿真中达到98.85%成功率与零碰撞，推理仅约1.29毫秒，比MPC快37.2倍，比标准扩散模型快超800倍。

在资源受限的边缘计算平台上实测稳定推理延迟约5.3毫秒，避免了基线方法的延迟尖峰与卡顿，具备实际部署价值。</td></tr>
<tr><td>2026-07-10</td><td>Differential Analysis of Multispectral Images for Terrain Identification<br><a href='http://arxiv.org/pdf/2607.09319'>论文</a></td><td>这篇论文针对自主机器人导航中地形理解的难题，提出了DRIFT，一个轻量级多光谱地形识别框架，旨在解决传统RGB感知在低光照、阴影和材料歧义下鲁棒性差的问题。核心思路是联合利用原始光谱波段与对光照不敏感的比值特征，并通过差分融合增强对噪声的鲁棒性。

◆提出双流残差架构，将原始光谱波段与波段比值表示相结合，后者可有效衰减光照和传感器增益等乘性采集效应。

◆设计差分融合分支，显式建模绝对波段线索与比值线索之间的差异，提升对噪声和不可靠光谱测量的鲁棒性。

◆构建了新的油-土多光谱数据集，使用搭载MicaSense RedEdge-P相机的无人机采集。

◆开展了草地上水-草受控实验，在变化光照及冷热水热扰动下系统分析NIR敏感效应。

实验结果表明DRIFT在多个任务上稳定优于强基线方法，同时具备边缘部署的兼容性。</td></tr>
<tr><td>2026-07-10</td><td>Validating Virtual Reality for Studying Multimodal Human-Robot Interaction in Socially Aware Robot Navigation<br><a href='http://arxiv.org/pdf/2607.09261'>论文</a></td><td>本论文的核心贡献是验证了虚拟现实（VR）作为研究多模态人机交互平台的有效性，特别是在社交感知机器人导航场景中的应用。

研究人员开发了一个VR原型系统，并在配备动作捕捉系统的真实场地与其虚拟副本中进行了被试内实验（N=21），让参与者与PR2移动操作机器人在正交交叉和擦肩而过两种典型共导航场景中交互。

研究发现参与者在VR和真实环境中对机器人社交感知导航的评估相似，且VR能够捕捉到与真实世界一致的人类交互行为，包括轨迹和头部朝向数据。

◆ 提出了一个用于研究社交感知机器人导航的VR原型系统，实现了与真实场景的1:1复刻

◆ 设计了被试内实验设计，同一批参与者在真实环境与VR中分别完成相同任务，直接对比交互行为

◆ 通过主观评价与客观行为数据（轨迹、头部朝向）的多维度分析，系统验证了VR在多模态人机交互研究中的可靠性

◆ 证实VR可以替代真实环境成为研究更丰富多模态社交行为的灵活可靠平台，为未来HRI研究提供了方法论支撑...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-10</td><td>Empirical Pedestrian Safety Assessment in a Mobile Robot Using a Predictive Social Force Model<br><a href='http://arxiv.org/pdf/2607.09192'>论文</a></td><td>本文针对移动机器人在人行道与行人共存的场景，研究如何同时保障客观安全性与行人主观舒适感。作者在传统社会力模型(SFM)的基础上，引入了投影碰撞时间(PTTC)并结合有限时域内的预测社会力向量，提出了预测型SFM(PSFM)与预测型TSFM(PTSFM)两种改进模型，并在非完整约束移动机器人上完成了实机部署与志愿者面对场景实验。

◆ 提出预测型社会力模型PSFM和PTSFM，在有限时域内对未来社会力向量进行积分以增强前瞻性

◆ 首次将SFM、TSFM、PSFM、PTSFM四种变体在真实非完整约束移动机器人上进行系统性对比实验

◆ 构建融合客观指标(最小PTTC、平均速度、最小距离、横向距离、最大轨迹曲率)与Likert量表主观评估的综合性安全评价体系

实验结果表明，集成PTTC的导航方法能够显著提升安全指标；然而在单行人场景中，预测机制的额外收益有限，主观评分经Mann-Whitney检验无显著差异，说明PTTC是改善行人安全的关键因素，而预测项的贡献相对有限。</td></tr>
<tr><td>2026-07-10</td><td>Vascular Geometry Characterization for AI-Based Endovascular Navigation<br><a href='http://arxiv.org/pdf/2607.09130'>论文</a></td><td>本论文针对急性缺血性卒中机械取栓术中强化学习自主导航缺乏标准化难度评估框架的问题，基于61例患者CT血管造影数据，系统研究了血管几何特征对导航性能的影响。研究构建了自动化血管特征提取流程，定量测量了主动脉弓类型、牛角弓、迂曲度、发出角、反向曲率等关键指标，并采用Soft Actor-Critic算法进行120秒自主导航实验。结果表明血管几何形态显著影响导航难度：左侧牛角弓和II/III型主动脉弓分别使导航时间延长30.19秒和37.92秒，迂曲度大幅增加导航耗时并降低成功率；右侧II/III型弓增加45.94秒，每个反向曲率使导航时间延长3.96秒。研究首次证实血管几何特征是MT智能体导航难度的关键决定因素。

◆创新点一：首次系统建立血管几何形态与强化学习导航难度之间的量化关联，揭示左右侧血管的关键影响因素差异。
◆创新点二：提出自动化、可重复的血管特征定量分析管线，为未来标准化复杂度分级与RL模型评估奠定基础。</td></tr>
<tr><td>2026-07-09</td><td>FSD-VLN: Fast-Slow Dual-System Modeling for Aerial Long-Horizon Vision-Language Navigation<br><a href='http://arxiv.org/pdf/2607.08359'>论文</a></td><td>本文针对无人机长航时视觉语言导航（VLN）中全局多模态理解与序列动作生成之间的结构性错位问题，提出了FSD-VLN框架。该框架采用快慢双系统异步架构，将高层语义推理与低延迟飞行控制解耦，缓解了现有方法在长航时场景下轨迹抖动和决策延迟严重的问题。

◆ 慢速流：基于预训练视觉语言模型提取稳定的语义先验信息，为导航决策提供可靠的全局语义支撑。

◆ 快速流：采用扩散变换器（DiT）建模跨时间动作分布，生成时序一致的飞行控制指令，实现低延迟、高稳定性的动作输出。

◆ 引入时间感知自适应优化器，稳定长序列训练过程并有效抑制梯度振荡。

大规模低空仿真实验表明，该方法在未见场景上的导航成功率较现有最优方法提升最高达2倍，同时单步推理延迟和总任务运行时间均减少超过50%，验证了解耦式语义-控制建模的有效性，为长航时空中VLN提供了实用范式。</td></tr>
<tr><td>2026-07-08</td><td>STEMbot: A Compliant Robot for Under-Canopy Plant Navigation<br><a href='http://arxiv.org/pdf/2607.07873'>论文</a></td><td>针对有机农业中冠层下方害虫难以早期检测的问题，本文提出STEMbot微型攀爬机器人系统，通过自主攀爬植物枝干实现近距离害虫监测。

◆ 提出融合PIN-SLAM几何流水线与语义OcTree的感知框架，在机器人攀爬过程中实现鲁棒定位与全局一致的稠密建图。

◆ 提出流形约束A*规划器结合光线追踪目标指定方法，支持分支感知遍历及对叶背等遮挡目标区域的自主检查。

系统采用柔顺机构可稳定攀附7-33毫米直径的枝干，并在四种不同植物上完成了自主导航硬件实验验证。

几何重建结果与离线摄影测量基准对比的平均Chamfer距离小于1厘米，证明了系统的高保真建图能力与全局一致性。</td></tr>
<tr><td>2026-07-08</td><td>Social-spatial dependencies for learning visual navigation<br><a href='http://arxiv.org/pdf/2607.07460'>论文</a></td><td>本文研究了社会性生物在视觉导航任务中的社会-空间依赖关系。研究团队训练了由独立神经网络控制的智能体，在不同社会情境中进行导航，社会依赖程度和策略选择由相对任务表现和空间效应决定。

研究发现，当高质量社会信息增加时，智能体的导航策略会发生相变，从独立导航转向跟随行为，并在拥挤觅食区域演化出避碰策略。此外，在可预测的非平稳环境中，智能体会在远端和近端分别发展出独立与社会导航的行为混合模式。

本研究的核心贡献与创新点如下：

◆ 提出自下而上的研究框架，通过独立训练的神经网络智能体研究社会导航行为，避免了仅从群体行为出发的局限性。

◆ 揭示了社会信息质量驱动的导航策略相变现象，从个体导航→跟随→避碰的阶段性转变。

◆ 发现可预测环境动态会引发个体与社会导航的行为混合模式。

◆ 强调社会-空间依赖关系对理解社会性生物行为的关键作用，挑战了仅分析个体行为的传统研究方法。</td></tr>
<tr><td>2026-07-09</td><td>Behavior Foundations for Quadruped Robots: ABot-C0 Technical Report<br><a href='http://arxiv.org/pdf/2607.07370'>论文</a></td><td>该论文提出ABot-C0四足机器人通用运动控制系统，构建了三大互补的行为基础：多源运动数据管线、跨任务的鲁棒策略学习以及统一部署栈。研究团队通过条件视频生成合成、动捕标注、遥操作和人工设计搭建数据金字塔，产出了16,074条物理可行的运动片段，为多样化运动学习提供了数据基础。基于大规模数据训练的Flow-Matching通用策略首次在四足机器人上验证了运动跟踪的缩放规律，表现出对未见动作的零样本泛化能力。

◆ 通过条件视频生成合成、动捕、遥操作与人工设计四源融合，构建16,074条运动片段的数据金字塔，突破动物数据稀缺瓶颈。
◆ 首次在四足平台上验证运动跟踪的缩放定律，Flow-Matching通用策略随训练规模提升而性能单调增长，并具备零样本跟踪未见动作的能力。
◆ 采用三阶段特权到感知框架，结合时序LiDAR记忆与地形预测监督，实现复杂全地形鲁棒运动。
◆ 提出多策略协同的部署栈，支持平滑行为切换、能量高效控制与安全机制，支撑城市自主导航与陪伴式多模态交互的实际应用。</td></tr>
<tr><td>2026-07-08</td><td>HumAIN: Human-Aware Implicit Social Robot Navigation<br><a href='http://arxiv.org/pdf/2607.07357'>论文</a></td><td>该论文提出HumAIN框架，旨在通过知识蒸馏将隐式社交线索融入机器人规划循环，实现对人类行为的敏感感知。系统首先训练一个基于Transformer的教师模型，融合历史图像、骨骼关键点、机器人状态和目标位置等多模态输入学习人类感知轨迹表示，再通过轨迹重建与潜在特征对齐的双目标优化，将知识蒸馏至轻量级学生模型以支持实时部署。

◆ 创新点一：首次将步态、姿态等全身隐式社交线索整合至规划环节，有效桥接预测与规划模块之间的鸿沟。

◆ 创新点二：采用师生蒸馏架构兼顾表征能力与推理效率，适合在资源受限的嵌入式平台上实时运行。

◆ 创新点三：通过多模态融合策略使机器人具备自适应、鲁棒且社交合规的类人导航能力。

实验结果表明，HumAIN在所有轨迹预测指标上平均较现有最优基线提升29.8%，验证了利用隐式全身线索提升导航感知能力的有效性与实用性。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-13</td><td>Trajectory Planning and Certification for 3-DOF Robot Manipulators Using Real Quantifier Elimination Based on Comprehensive Gröbner Systems<br><a href='http://arxiv.org/pdf/2607.11657'>论文</a></td><td>本文针对3自由度机械臂的轨迹规划与解的认证问题，提出了一种基于Comprehensive Gröbner Systems的实量词消去（CGS-QE）算法及其实现。该方法的核心思路是将末端执行器坐标作为参数，计算参数化系统的CGS，从而避免了沿轨迹逐点重复计算Gröbner基的耗时操作。在轨迹规划阶段，通过一次CGS计算即可高效求解逆运动学问题；在解认证阶段，CGS-QE方法能够严格证明沿直线段或三次自然样条轨迹的任意点都存在逆运动学解。该算法在计算机代数系统Risa/Asir中实现，兼具代数严格性与计算效率。

◆将末端执行器坐标作为参数，通过计算一次Comprehensive Gröbner System替代沿轨迹逐点重复计算Gröbner基，显著提升轨迹规划效率。

◆基于CGS-QE方法实现逆运动学解的严格数学认证，确保沿直线段或三次自然样条轨迹的任意点均存在有效解。

◆在Risa/Asir计算机代数系统中完成完整算法实现，为机械臂轨迹规划提供了兼顾代数严谨性与实用性的工具。</td></tr>
<tr><td>2026-07-13</td><td>Velocity Scheduled Flow Matching<br><a href='http://arxiv.org/pdf/2607.11442'>论文</a></td><td>本文提出速度调度流匹配（VSFM），核心思想是将传统流匹配中恒定的条件速度目标 x1-x0 替换为可调的速度剖面 v(t)(x1-x0)，其中 v(t) 为满足归一化条件的非负函数。研究选取了六种来自运动规划的剖面进行分析。

◆ 在推理阶段，预训练的线性流匹配模型无需重新训练，仅通过在非均匀 τ 网格上积分 ODE 即可切换任意剖面，CIFAR-10 上 FID 最多降低 19.8%。

◆ 在训练阶段采用刹车剖面从头训练，在 4 NFE 条件下进一步降低 FID 达 17.4%。

◆ 上述增益均可由欧拉积分器在诱导网格上的局部截断误差理论统一解释。

◆ 该方法将采样精度问题转化为离散化策略选择，兼具灵活性与零额外成本的优势。</td></tr>
<tr><td>2026-07-13</td><td>From Sketch Prior to Trajectories: A Mission-Oriented Coordinated Navigation Framework for Indoor UAV Swarm<br><a href='http://arxiv.org/pdf/2607.11386'>论文</a></td><td>本文针对室内无人机集群任务导向的协同导航问题，提出了一种利用草图先验的协同导航框架。核心思路是观察到室内任务多在固定高度层执行，将任务级区域转移视为平面连接性问题。

◆ 利用草图先验（楼层平面图、CAD布局等）指导多无人机室内任务，提出任务导向的可通行性表征方法，通过在线观测进行拓扑对齐，将先验与实时感知融合。

◆ 提出分层2D-3D协同导航框架：2D引导路径规划生成任务导向的引导路径，3D轨迹优化基于引导路径生成动力学可行且无碰撞的轨迹。

◆ 框架支持通信可用与通信丢失两种条件下的协同导航，增强了系统的鲁棒性。

◆ 通过多楼层仿真验证了系统对分层室内结构的可扩展性，并在实际多房间室内环境中进行了实验验证。

该工作将先验知识、拓扑对齐、分层规划有机结合，为室内无人机集群执行巡检、巡逻、物流等任务提供了完整的解决方案。</td></tr>
<tr><td>2026-07-13</td><td>CR-Solver: GPU-Accelerated Kinematics Solver for Tendon-driven Continuum Robots<br><a href='http://arxiv.org/pdf/2607.11340'>论文</a></td><td>针对连续体机器人运动规划工具的空白，本文提出CR-Solver，一种基于GPU加速的两阶段优化求解器。该方法将逆运动学、路径跟踪和轨迹规划统一在单一约束非线性优化框架中，通过GPU并行优化实现显著速度提升，同时保持毫米级精度和95%以上的成功率。CR-Solver采用纯Python实现，降低了使用门槛并便于扩展。

◆ 将逆运动学、路径跟踪和轨迹规划统一在单一约束非线性优化框架中
◆ 采用两阶段优化策略结合GPU并行加速实现高效求解
◆ 纯Python实现降低采用门槛并提供可扩展的高性能规划基础...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-12</td><td>Coverage Path Planning: Classical Foundations, Recent Advances, and Future Directions<br><a href='http://arxiv.org/pdf/2607.10649'>论文</a></td><td>本文是一篇关于覆盖路径规划（CPP）的综合性综述，回顾了125篇代表性文献，系统梳理了该领域从经典方法到最新研究的演变脉络。作者将CPP方法归纳为六大类别：单机器人CPP、多机器人CPP、三维CPP、约束型CPP、基于学习的CPP以及视觉CPP，并对每类方法的规划公式、代表性算法、优势与局限性进行了深入分析。

◆ 提出了基于环境知识、工作空间几何、机器人约束、感知目标和协调需求的多维度分类分析框架

◆ 系统性地将传统经典方法与2015至2026年间的前沿研究相结合，揭示CPP从二维单机器人到复杂三维、多智能体及学习驱动范式的演进规律

◆ 首次全面涵盖视觉覆盖、平台约束覆盖等新兴方向，填补了现有综述在视觉与约束场景方面的空白

◆ 指出了可扩展在线规划、多机器人协调、3D与视觉覆盖、统一平台约束与资源感知覆盖以及学习增强覆盖等未来开放挑战，为后续研究指明方向。</td></tr>
<tr><td>2026-07-12</td><td>World Models as Adversaries: Multi-Agent Self-Play Fine-Tuning for Robust Motion Planning<br><a href='http://arxiv.org/pdf/2607.10630'>论文</a></td><td>论文针对密集交通中罕见关键场景数据不足的问题，将对抗鲁棒规划建模为约束 min-max 对弈，提出对抗世界建模（AWM）多智能体自博弈微调框架。由于精确求解博弈不可行，方法采用原理化的解耦求解器。

◆ 将规划器自身的预测世界模型转化为角色条件化的对抗体，通过反事实信用分配学习稀疏、场景自适应的攻击联盟。
◆ 外层最大化中，自车规划器求解遗憾感知的鲁棒最优响应，结合尾部风险加权与参考锚定信赖域，提升困难场景恢复能力的同时保持名义驾驶行为。
◆ 框架无需外部场景生成器或启发式扰动，易与现代自回归规划器直接集成。

在 nuPlan 和 InterPlan 基准上的实验表明，方法能生成可迁移的对抗交互，并在常规与长尾高交互场景下均取得具竞争力的闭环性能，理论分析也证实了解耦求解器与各优化组件的合理性。</td></tr>
<tr><td>2026-07-12</td><td>BucketKD: A Safety-Aware Bucket-Based Knowledge Distillation Framework for End-to-End Motion Planning<br><a href='http://arxiv.org/pdf/2607.10565'>论文</a></td><td>本文针对端到端运动规划模型难以部署在资源受限平台的问题，提出了BucketKD框架，通过知识蒸馏实现紧凑且安全感知的规划器。传统方法依赖简化的规划状态表征，而该工作将关键环境变量离散化为自适应桶，能够在保持效率的同时捕获更丰富的场景语义。

◆提出基于桶的知识蒸馏框架BucketKD，通过将关键环境变量离散化为自适应桶，保留了比简化状态表征更丰富的场景语义信息，同时兼顾计算效率。

◆设计了安全感知的路径点注意力机制，利用交通领域广泛使用的碰撞时间(TTC)公式，综合考虑障碍物距离和相对运动来评估每个路径点的风险等级。

◆在CARLA仿真器与Bench2Drive数据集上的大量实验表明，BucketKD在规划精度和安全性方面均显著优于当前最优方法，同时保持了较高的模型压缩比。</td></tr>
<tr><td>2026-07-11</td><td>Large Language Model Enhanced Differentiable Trajectory Planning for IoT-Enabled Autonomous Driving<br><a href='http://arxiv.org/pdf/2607.10438'>论文</a></td><td>本文针对IoT自动驾驶规划中模仿学习覆盖复杂交互不足、与下游约束优化一致性弱、实时场景语义利用不充分等问题，提出了一种大语言模型增强的可微轨迹规划框架。该方法以周围智能体轨迹作为额外规划监督来扩充训练分布，并结合复杂度自适应的异步LLM语义增强模块，在可控在线开销下提取高层场景特征，最后通过可微优化模块以显式残差惩罚精修轨迹并回传梯度到上游规划器。在nuPlan闭环非反应式与反应式Hard20基准上分别取得83.63和78.29的最佳综合得分，并在CARLA-ROS实车测试中验证了在线实时闭环部署能力。

◆ 周围智能体中心的数据增强策略：将周围车辆轨迹重组为额外规划监督，在不采集新数据的前提下改善训练分布对长尾交互的覆盖。

◆ 复杂度感知的异步LLM语义增强模块：根据场景复杂度自适应调用LLM提取高层语义特征，兼顾语义理解与实时在线开销控制。

◆ 可微优化精修模块：引入显式残差惩罚对生成轨迹进行约束精修，并将优化梯度反向传播至上游规划器，实现端到端联合训练。</td></tr>
<tr><td>2026-07-11</td><td>Robotic Contextual Awareness for Human-Robot Collaboration and Environmental Understanding<br><a href='http://arxiv.org/pdf/2607.10372'>论文</a></td><td>本文针对自主移动机器人在动态人本环境中的情境感知难题，提出了两条互补的研究路线。第一条路线聚焦于人机协作中的人体重识别与跟踪，使移动机器人能够识别特定目标人物，从而实现有针对性的协作而忽略无关个体。第二条路线致力于提升机器人对环境的整体感知能力，融合几何信息与语义信息以增强理解深度。几何信息支撑运动规划与避障，语义信息则为更高级的人机交互提供丰富语境。

◆提出基于视觉的人体重识别与跟踪方法，使移动机器人能够在多人场景中锁定特定目标人物并维持持续识别，从而支持有针对性的人机协作。

◆构建融合几何与语义的双重环境感知框架，既能精确建模空间结构以保障导航与避障安全，又能赋予环境高层语义以支持复杂交互。

◆将人体级交互理解与环境级场景理解相结合，形成面向人机协作的完整情境感知系统，推动机器人与人类、环境的自然共融。</td></tr>
<tr><td>2026-07-11</td><td>PrismAD: Decoupled Planning via Semantic Mixture-of-Planners for End-to-End Autonomous Driving<br><a href='http://arxiv.org/pdf/2607.10336'>论文</a></td><td>PrismAD是一个基于语义规划器混合(Semantic Mixture-of-Planners)的解耦式端到端自动驾驶框架。其核心思想是解决现有规划器将异构场景令牌聚合到耦合表示空间、导致单一规划分支需同时建模智能体交互、道路几何和驾驶意图的问题。该框架将场景令牌按交互、几何和意图进行语义分组，并分配给具有相同架构但独立参数的规划专家，由语义感知路由器自适应融合专家预测。在nuScenes开环数据集和NeuroNCAP闭环基准上的实验表明该方法具有竞争力。

◆ 提出语义规划器混合架构，将场景令牌按交互、几何、意图三组语义划分，分配给独立参数的规划专家进行专业化建模。

◆ 引入语义感知路由器，为运动预测和自车规划分别生成路由权重，自适应聚合多专家输出。

◆ 采用稀疏Top-K激活结合噪声门控机制，提升路由鲁棒性并减少不必要的专家计算开销。</td></tr>
<tr><td>2026-07-11</td><td>Millimeter Wave Radar: From Synthetic Aperture to Probabilistic Mapping<br><a href='http://arxiv.org/pdf/2607.10161'>论文</a> | <a href='https://github.com/rpl-cmu/rpm'>代码</a></td><td>本文针对自主机器人在烟雾、雾霭等恶劣环境下的鲁棒概率建图难题，提出了一套基于毫米波雷达的完整解决方案。研究的核心贡献在于将合成孔径雷达(SAR)处理与概率建模相结合，建立了从原始雷达信号到概率占据地图的端到端流水线，有效克服了毫米波雷达数据稀疏、噪声大等固有问题。作者在多种室内场景中开展了广泛的实验验证，并通过下游路径规划任务评估建图质量，同时系统分析了关键参数及天线阵列配置对建图性能的影响。此外，该工作揭示了SAR概率建图在实际机器人部署中的有效性与局限性。为推动后续研究，团队还开源了级联毫米波雷达数据集及配套的GPU加速信号处理工具链。

◆ 提出了从原始毫米波雷达信号到概率占据地图的完整处理流水线，融合SAR成像与概率建模两大模块。

◆ 设计了基于路径规划性能的建图质量评估方法，将下游任务表现作为衡量建图优劣的关键指标。

◆ 系统性地研究了天线阵列配置及关键参数对概率建图性能的影响，为实际部署提供了配置依据。

◆ 开源了级联毫米波雷达数据集和GPU加速信号处理流水线，促进了相关研究的可复现性与广泛应用。</td></tr>
<tr><td>2026-07-10</td><td>Diffusion for Long-Horizon Multi-Robot Path Planning in Human-Shared Environments<br><a href='http://arxiv.org/pdf/2607.09911'>论文</a></td><td>本文提出Multi-Robot Rolling Diffusion (MRRD)框架，将扩散模型应用于多机器人在人类共享环境中的长时域路径规划任务。现有生成式规划器受限于固定路径时长和高计算延迟，该方法通过滚动时域方案有效应对人类运动预测的有限视野并实现长时域导航。该框架结合并行扩散推理、冲突搜索机制和紧迫性时序条件生成，能够在密集人群中为大规模机器人团队实时生成安全且类人的运动路径。差异化引导项的设计分别优化了人类周围的社会感知行为与机器人间的高效协调。实验结果表明该方法可支持15个机器人实时运行，在安全性和任务成功率上均显著优于现有基线。

◆ 滚动时域方案适应人类运动预测的有限视野
◆ 并行扩散推理实现大规模类人路径的可扩展生成
◆ 基于冲突搜索的机制解决机器人间相互碰撞
◆ 紧迫性时序条件生成可变速的灵活路径
◆ 差异化引导项兼顾社会感知与多机协调...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-10</td><td>Shortcut Trajectory Planning for Efficient Offline Reinforcement Learning<br><a href='http://arxiv.org/pdf/2607.09336'>论文</a></td><td>本论文针对离线强化学习中扩散轨迹规划器推理成本高的问题，提出了Shortcut Trajectory Planning (STP)框架。与依赖迭代去噪的扩散方法或需要两阶段师生蒸馏的一致性方法不同，STP引入shortcut模型作为高效轨迹生成器，将训练流程简化为单阶段，避免了额外蒸馏带来的成本与不稳定性。模型通过步长条件化机制实现可调节的单步或少步推理，大幅提升采样效率。在候选方案选择方面，STP采用融合可行性感知修正的critic网络对生成规划进行评估筛选。在D4RL标准的运动、导航、操作及灵巧控制等多类基准任务上的广泛实验表明，STP能在显著简化训练流程的同时保持强劲性能。

核心创新点：
◆ 提出单阶段训练的shortcut轨迹模型，通过步长条件化灵活支持单步和少步推理，免去扩散的迭代去噪和一致性模型的两阶段蒸馏过程
◆ 设计融合可行性感知修正的critic用于候选规划评估与筛选，提升离线决策的可靠性与可执行性
◆ 在D4RL多类任务上实现统一高效的生成式规划，在简化训练的同时保持优异表现...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-08</td><td>Shift &amp; Drift: A Zero-Shot Benchmark for Generalizable and Robust Autonomous Driving Motion Planning<br><a href='http://arxiv.org/pdf/2607.07844'>论文</a></td><td>本文提出Shift &amp; Drift双轨基准测试，用于评估自动驾驶运动规划器在分布偏移下的泛化性和鲁棒性。研究发现，尽管基于大规模数据集(如nuPlan)训练的闭环规划器在分布内表现良好，但在面对新城市拓扑和执行扰动时的泛化能力与恢复机制仍缺乏系统研究。

◆ 构建了语义偏移轨道(Semantic Shift Track)，通过新颖的转换流水线将DeepScenario Open 3D航拍数据集集成到nuPlan仿真框架中，提供1182个涵盖德国四城及旧金山的零样本评估场景，重点测试密集行人-骑行者交互场景。

◆ 设计了状态分布漂移轨道(State-Distribution Drift Track)，通过向自车动力学注入随机扰动，量化规划器对累积执行错误的鲁棒性。

◆ 系统评估了模仿学习与强化学习等多种规划范式的失效模式，揭示了模仿学习在语义偏移(尤其在行人密集环境)下表现显著下降，且在时间相关执行噪声下持续漂移。

◆ 发现强化学习规划器在两个轨道上均表现出更优雅的性能退化，验证了模仿保真度与闭环韧性之间存在经验性权衡，为可靠部署提供了严格评测基准。</td></tr>
<tr><td>2026-07-08</td><td>HumAIN: Human-Aware Implicit Social Robot Navigation<br><a href='http://arxiv.org/pdf/2607.07357'>论文</a></td><td>本文提出HumAIN框架，针对社会机器人导航中人类行为感知问题，将人体骨骼等隐式社交线索融入规划过程。核心创新包括：◆提出基于知识蒸馏的师生架构，教师模型采用Transformer融合历史图像、骨骼关键点、机器人状态和目标点等多模态信息，学习人类感知的轨迹规划表征。◆通过轨迹重建与潜在特征对齐双重优化，将知识蒸馏到轻量级学生模型，仅需最少输入即可推理复杂社交动态，实现资源受限平台上的实时部署。◆强调利用步态、姿态等全身隐式线索进行社交合规导航。实验表明，HumAIN在所有轨迹预测指标上平均比现有最优方法提升29.8%，验证了隐式人体线索在实现类人导航感知方面的有效性。</td></tr>
<tr><td>2026-07-08</td><td>Disturbance-aware Motion Planning for Over-actuated Underwater Vehicles Exploiting Actuation Redundancy for High-fidelity 3D Reconstruction<br><a href='http://arxiv.org/pdf/2607.07139'>论文</a></td><td>本文针对水下机器人在精细目标附近作业时推进器扰动降低成像质量的问题，提出了一种感知感知的运动规划方法，通过利用八推进器ROV的过驱动冗余特性，在满足运动约束的同时搜索推力分配零空间以最小化任务相关区域的预测扰动。

◆ 核心创新在于揭示并利用了作动-感知耦合机制，将传统的以载体为中心的控制目标扩展为兼顾感知质量的联合优化框架。

◆ 基于作动盘理论构建了带方向衰减的推进器尾流代理模型，并经PIV实验高精度验证（R²达0.99）。

◆ 设计了实时冗余求解分配器，以10 Hz（45 ms/求解）的频率在线优化推力配置。

◆ 在440次试验中将目标区域颗粒速度降低67%，3D重建RMSE提升55%，并支持自主扫描与操作员辅助巡检两种模式。</td></tr>
<tr><td>2026-07-08</td><td>Ace! Motion Planning of Professional-Level Table Tennis Serves with a Robot Arm<br><a href='http://arxiv.org/pdf/2607.06989'>论文</a></td><td>该论文针对机器人乒乓球研究中被忽视的发球任务，提出了一种结合运动基元、模型预测控制（MPC）与贝叶斯优化的发球规划方法，填补了相关研究空白。通过该方法，机械臂能够从无旋转的球中产生多样化的旋转，并实现精确瞄准，满足官方比赛规则要求。实验结果表明，该系统可生成高达550 rad/s的旋转和6.7 m/s的球速，旋转与速度的多样性可灵活控制。

◆ 研究视角新颖：聚焦于此前研究较少的发球任务，而非主流的接球回击，揭示了发球在物理建模与控制方面的独特挑战。

◆ 融合多方法：首次将运动基元、模型预测控制与贝叶斯优化相结合，实现发球动作的高效规划与多目标优化。

◆ 解决高难度物理问题：实现从无旋球中产生高旋转（最高550 rad/s），突破了机械臂发球的关键技术瓶颈。

◆ 性能达到专业水平：球速与旋转多样性可媲美甚至超越人类精英选手，验证了方法在真实比赛场景中的实用性。</td></tr>
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
<tr><td>2026-07-08</td><td>Dynamic Evaluation of Classical and Control-Aware Optimal Trajectory Planning in Robot Manipulators<br><a href='http://arxiv.org/pdf/2607.05544'>论文</a></td><td>本文针对机械臂轨迹规划中经典方法仅考虑运动学而忽略动力学与控制代价的问题,提出了一种控制感知的最优轨迹规划框架。核心思路是在有限时域优化中显式纳入机械臂动力学模型与执行器力矩约束,使生成的轨迹在闭环非线性执行下具有更优的跟踪精度与能效表现。

◆ 创新点一:提出控制感知的最优轨迹规划框架,在有限时域内联合优化轨迹形状与执行器力矩分布,克服经典多项式轨迹仅追求运动学平滑而忽视动力学代价的局限。

◆ 创新点二:引入中点线性化策略以提升大范围点对点运动中动力学近似的精度,缓解传统单点线性化在长距离运动中产生的偏差。

◆ 创新点三:构建统一的公平评估框架,使所有规划器在完全一致的闭环非线性动力学、控制器结构与执行器约束下执行,从而能够隔离并真实反映轨迹生成方法本身对执行性能的影响。

◆ 创新点四:基于非线性简化UR5模型的仿真表明,该方法在跟踪误差、修正力矩与闭环执行代价上均显著优于三次、五次及梯形等经典方法,验证了运动学平滑并不等价于动力学高效的关键结论。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-13</td><td>Why Low-Light Cameras Go Color Blind: Removing Color Bias in Raw Denoising<br><a href='http://arxiv.org/pdf/2607.11090'>论文</a></td><td>本文针对低光照Raw图像去噪中颜色偏置问题展开研究，提出了一种相机无关、无需标定的去噪新范式。主要创新点如下：

◆ 发现黑电平误差是导致去噪性能下降和严重色彩偏移的主要根源，揭示了现有方法在该问题上的局限性

◆ 设计偏置估计网络，将黑电平误差作为全局特征从噪声输入中直接预测，从而在去噪过程中实现有效颜色校正

◆ 在ELD、SID、LRID等多个公开数据集上验证，所提方法在盲去噪器中表现最优，尤其在颜色准确性方面具有突出优势，在很多场景下可媲美甚至超越有更强监督的方法

◆ 揭示广泛使用的SIDD数据集真值图像存在显著颜色偏置问题，会导致训练出的模型产生不真实的色彩还原

◆ 提出新的真值提取框架，构建了校正后的基准数据集，为后续低光去噪研究提供更可靠的评估平台...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-12</td><td>Unsupervised Detection of Entry and Exit Regions from Vehicle Trajectories for Camera-Agnostic Turning Movement Counts<br><a href='http://arxiv.org/pdf/2607.10949'>论文</a></td><td>该论文针对交叉口转向流量计数依赖人工标注的问题，提出无监督的车辆入口与出口区域自动识别流程。核心创新是不对完整轨迹聚类，而是聚类轨迹起止点位置生成持久空间多边形，通过点-多边形包含以线性复杂度分类新轨迹。流程含六个可配置步骤，作者基于25个摄像头与10段UA-DETRAC序列共19152次执行进行系统统计检验，识别三个最显著参数并给出经验推荐配置。该方法在25个摄像头（含16个未见过的地点）上达到约3%的中位分类误差，GEH符合工程阈值。相较轨迹聚类基线，跨摄像头稳定性与计算成本均更优，但中位误差略高；60分钟以上校准视频及高峰时段选取能进一步提升区域估计质量。

核心创新点：
◆ 完全无监督，无需人工标注、摄像头标定或交叉口几何先验
◆ 聚类起止点位置生成持久多边形，线性复杂度分类未来轨迹
◆ 25个摄像头19152次执行的大规模参数敏感性分析
◆ 摄像头无关设计，在16个未见地点仍保持约3%分类误差...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-12</td><td>Projection-Domain Sensitivity Analysis of Vertebral DRRs Under Intrinsic Calibration Perturbation<br><a href='http://arxiv.org/pdf/2607.10551'>论文</a></td><td>本文针对透视引导脊柱成像中内在标定扰动对椎体DRR投影的影响,提出了一种基于合成CT模型的系统评估框架。该框架通过控制锥束成像几何,在固定解剖结构与采集姿态的条件下生成真值与扰动DRR对,并从解剖标志位移、轮廓距离、轮廓重叠、图像相似度以及2D-3D配准精度等多个维度量化投影域变化。研究表明,即使微小的内在标定扰动也能引起椎体投影几何、轮廓形态、标志点定位及DRR外观的可测量改变,且侧位投影的敏感性显著高于正位投影,具有明显的视角依赖性。投影域的不一致性进一步降低了下游2D-3D配准性能,尤其影响旋转对齐精度。研究结果证明投影域一致性可有效补充传统基于重建误差的标定评估方法,为DRR生成与透视引导脊柱配准的可靠性提升提供了实用框架。

◆ 提出基于合成CT的投影域标定扰动敏感性分析框架,弥补传统重建误差评估在投影域层面的不足
◆ 构建涵盖解剖标志、轮廓形态、图像相似度与配准精度的多维度量化评估体系
◆ 揭示标定敏感性具有显著的视角依赖性,侧位投影比正位投影更易受扰动影响
◆ 阐明投影域不一致性与下游2D-3D配准性能退化的关联机制,尤其是旋转对齐精度...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-06</td><td>From Fixed to Free Cameras: Calibration-Free View-Robust Vision-Language-Action Model<br><a href='http://arxiv.org/pdf/2607.05396'>论文</a> | <a href='https://alibaba-damo-academy.github.io/CamVLA/'>代码</a></td><td>该论文针对真实机器人部署中相机位置经常变化的问题,指出现有VLA策略依赖显式相机外参,导致在视角变化时脆弱难用,提出策略应自主推断相机位姿而非被告知。针对这一痛点,论文提出CamVLA模型,其核心思想是将操控控制与相机几何解耦。模型同时预测相机坐标系下的末端执行器动作以及6自由度手眼矩阵,通过确定性几何变换将两者合成为机器人基坐标系下的动作。该方法实现了免标定、免深度、单视角,部署时仅需单张单目RGB图像和任务指令。仿真与真实机器人实验均表明,CamVLA在多种未见视角下均能稳定提升任务成功率。

◆ 创新点一:提出相机中心化的动作表征方式,直接在相机局部坐标系下预测末端执行器动作,实现与相机几何的解耦。

◆ 创新点二:联合预测6自由度手眼矩阵,使策略能够自主推断相机相对机器人基座的位姿,无需外部标定。

◆ 创新点三:通过确定性几何变换将姿态无关的动作与相机位姿估计组合,实现真正免标定、免深度、单视角的部署范式。</td></tr>
<tr><td>2026-07-02</td><td>Bridging 3D Gaussians and Semantic Occupancy for Comprehensive Open-Vocabulary Scene Understanding from Unposed Images<br><a href='http://arxiv.org/pdf/2607.01633'>论文</a></td><td>该论文提出COVScene框架，旨在从无位姿的稀疏图像中实现全面的3D场景理解，涵盖可渲染几何、开放词汇语义及自由/占用空间预测。核心思想是将可渲染的高斯原语与密集语义占据场通过可微分体素化在训练计算图中进行耦合，使体素正则化能够反向传播梯度到高斯的不透明度、几何和语义特征。

◆ 提出可微体素化提升机制，将语义高斯在训练图内提升为体素，无需外部相机标定即可实现无位姿重建与体素级正则化协同优化。

◆ 设计语义感知的几何Transformer与多任务高斯解码器，联合预测几何与多任务特征。

◆ 引入几何基础模型蒸馏和占据熵正则化，在没有直接体素监督的情况下提升语义占据预测能力。

◆ 在单一表示中同时支持新视角合成、开放词汇语义查询和语义占据预测三项任务，并在ScanNet和ScanNet++上取得竞争性渲染质量、更好的开放词汇分割与更强的语义占据预测效果。</td></tr>
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
<tr><td>2026-07-13</td><td>Event-RGB Adaptive Tracking for Nighttime Highway Perception<br><a href='http://arxiv.org/pdf/2607.11646'>论文</a> | <a href='https://github.com/haidongwang96/SEHN'>代码</a></td><td>这篇论文针对高速公路夜间场景下RGB相机因运动模糊、曝光不足和信噪比差导致的感知退化问题，提出了一种新的多模态融合跟踪方案。核心思路是打破现有方法的刚性优先级限制，实现事件相机与RGB相机的自适应协同。该工作为夜间高速公路智能交通感知提供了有效的技术路径与数据支撑。

◆ 提出JEAT联合事件-RGB自适应跟踪框架，将异步事件流和RGB帧统一到联合数据关联优化中
◆ 引入基于NIS统计量的自适应扩展卡尔曼滤波器，动态估计测量噪声并自适应加权双模态，黑暗或高速时优先事件流，亮光或静态时优先RGB帧
◆ 发布大规模合成数据集SEHN，基于CARLA仿真器生成，覆盖白天、夜间及无人工照明夜间等多样化环境与交通密度，提供同步的RGB与事件流数据...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-13</td><td>Diffusion MRI preprocessing affects ADC estimation and automatic PI-RADS v2.1 classification in bi-parametric prostate MRI<br><a href='http://arxiv.org/pdf/2607.11385'>论文</a></td><td>本文研究DWI预处理策略对前列腺MRI中ADC估计及自动PI-RADS分级的影响。基于fastMRI数据集268例样本，依次应用去噪、吉布斯振铃校正和失真校正，比较LLS与IWLLS算法计算ADC，并训练3类DenseNet进行PI-RADS分级。结果显示预处理流程显著影响ADC值，LLS与IWLLS数值等效；多数数据集保持线性关系（PCC约0.99），而失真校正后关系降至0.90。完全预处理数据集在高危PI-RADS分级中表现最佳AUROC和敏感性，且过度自信错误预测最少，有利于临床分诊。

◆ 系统评估DWI预处理对ADC定量和深度学习PI-RADS分级的综合影响，填补前列腺MRI预处理标准化研究空白
◆ 提出结合去噪、吉布斯振铃校正与失真校正的完整顺序预处理流程
◆ 将预处理效果分析与临床PI-RADS自动分级任务相结合，证明失真校正是提升模型性能的关键环节...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-13</td><td>HandFlow: Fully Generative 4D Hand Recovery with Flow Matching<br><a href='http://arxiv.org/pdf/2607.11221'>论文</a></td><td>该论文提出HandFlow，一个基于流匹配的全生成式框架，用于从单目视频中恢复时序一致的3D手部姿态与形状。现有判别式方法缺乏时序上下文且预测易抖动，时间模型虽能提升一致性但作为确定性回归器在遮挡和运动模糊下表现脆弱，因此作者采用生成式建模范式学习合理手部运动先验。HandFlow通过单次ODE积分对整个时间窗口的MANO参数进行去噪，无需自回归解码，核心采用Flux风格双流Transformer捕获长程依赖，并引入置信度感知的连续掩码机制融合可学习掩码标记以处理噪声或缺失观测。实验表明该方法在DexYCB和HOT3D上达到最先进性能，世界空间姿态误差降低超30%，加速度误差最低，且在单GPU上以47fps重建150帧序列，速度约为此前最快视频方法的12倍。

◆ 提出基于流匹配的全生成式4D手部恢复框架，通过单次ODE积分对整段时序MANO参数去噪。
◆ 设计Flux风格双流Transformer，无需自回归解码即可捕获长程时序依赖。
◆ 提出置信度感知的连续掩码机制，融合可学习掩码标记以鲁棒处理噪声与缺失观测。</td></tr>
<tr><td>2026-07-12</td><td>MRUF: Multi-granularity Routing with Uncertainty-Aware Fusion for Robust Multimodal Sentiment Analysis<br><a href='http://arxiv.org/pdf/2607.10599'>论文</a></td><td>该论文针对多模态情感分析中因遮挡、噪声、模糊或转写错误导致的模态质量不稳定问题,提出了一种可靠性感知融合方法MRUF。MRUF首先对情感相关表示进行多粒度摘要,然后在子空间和模态两个层级进行动态路由,并通过留一法误差增量监督模态路由,自动估计每个话语的模态重要性。模型进一步预测各模态的不确定性,利用逆方差重加权对模态门控进行精炼,同时引入模态不变对比对齐以稳定共享表示空间。在CMU-MOSI和CMU-MOSEI上的对齐与非对齐实验表明,MRUF在多个强基线上取得一致提升,且机制分析验证了预测不确定性更高的模态会获得更低的融合权重,证明其能有效识别并抑制不可靠模态。

◆ 提出多粒度路由机制,结合子空间级与模态级路由,捕获更细粒度的情感判别性信息
◆ 设计留一法误差增量监督的模态重要性估计方法,无需额外标注即可自动学习模态可靠性
◆ 引入基于逆方差重加权的不确定性感知门控精炼,使低质量模态在融合时被自动降权
◆ 利用模态不变对比对齐稳定共享表示空间,提升跨模态表征的一致性与鲁棒性...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-11</td><td>BOCCHI: A More Realistic and Challenging Benchmark for Local Motion Blur Detection with MSDCT-UNet<br><a href='http://arxiv.org/pdf/2607.10427'>论文</a></td><td>局部运动模糊检测要求像素级定位模糊区域，但现有基准存在梯度捷径问题，导致模型难以泛化。本文提出BOCCHI基准，采用真实拍摄数据并使清晰区域与模糊梯度分布重叠，从而有效消除这些捷径。同时提出MSDCT-UNet，一种频率感知编解码器，通过DCT Attention和FiLM模块注入多尺度DCT先验。实验表明，MSDCT-UNet在BOCCHI上的mIoU和边界定位均排名第一。更重要的是，基于BOCCHI训练的模型在跨数据集迁移中超越所有其他训练源，且仅需633张训练图像，验证了基准的真实性和方法的强泛化能力。

◆ 构建BOCCHI真实拍摄基准，通过清晰与模糊梯度分布重叠设计消除梯度捷径
◆ 提出MSDCT-UNet频率感知架构，结合DCT Attention与FiLM模块注入多尺度DCT先验
◆ 实现优异的跨数据集迁移能力，仅用633张训练图像即超越其他训练源所训模型...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-10</td><td>A Numerically-Robust ROS 2 Port of iG-LIO: Diagnosing and Fixing Toolchain-Induced Failures in Incremental GICP LiDAR-Inertial Odometry<br><a href='http://arxiv.org/pdf/2607.09947'>论文</a> | <a href='https://github.com/Forestry-Robotics-UC/ig_lio/tree/ros2-jazzy'>代码</a></td><td>本文报告了iG-LIO（一种紧耦合LiDAR-惯性里程计系统）从ROS 1到ROS 2 Jazzy的开源移植工作。核心贡献在于诊断并修复了移植后出现的内部NaN数值失败问题，其根因不在算法本身而是ROS 2工具链：一是QoS配置不匹配导致IMU采样被静默丢弃和重排序，二是oneTBB与Eigen组合中并行归约累加器未初始化引发数值异常。作者还修正了新版Ouster点云字段解析以确保正确去畸变，新增Velodyne Velarray M1600支持及Livox双路径...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-10</td><td>Event Stream based Multi-Modal Video Anomaly Detection: A Benchmark Dataset and Algorithms<br><a href='http://arxiv.org/pdf/2607.09114'>论文</a></td><td>本文针对传统视频异常检测在光照变化、快速运动和复杂背景下鲁棒性不足的问题，提出了基于事件相机的多模态视频异常检测框架EVAD。该框架联合利用可见光视频和事件流，事件相机以高时间分辨率异步捕捉亮度变化，对运动模糊和极端光照具有天然鲁棒性。论文构建了大规模可见光-事件基准数据集TJUTCM-Pha，包含6.3亿事件和376,368帧视频，涵盖多样化光照、运动模式和背景复杂度，填补了事件异常检测数据集的空白。设计了对比式多模态预训练框架，通过对齐事件流、可见光视频和文本描述的语义嵌入来学习判别性事件表示，并采用自适应融合模块动态整合事件时序线索与视频空间语义。

◆ 构建大规模可见光-事件多模态异常检测基准数据集TJUTCM-Pha，涵盖6.3亿事件与37万余帧视频，填补该领域真实可扩展数据集的空白。
◆ 提出对比式多模态预训练框架，跨模态对齐事件流、视频与文本语义，习得判别性强的事件表示。
◆ 设计自适应融合模块，动态整合事件时序运动线索与视频空间语义特征，显著提升对光照变化等环境干扰的鲁棒性。</td></tr>
<tr><td>2026-07-09</td><td>EVIS: A Physics-Grounded Event Camera Plugin for NVIDIA Isaac Sim<br><a href='http://arxiv.org/pdf/2607.08098'>论文</a> | <a href='https://github.com/spikelab-jhu/isaac-sim-event-camera-plugin'>代码</a></td><td>该论文提出EVIS，一个基于物理的Isaac Sim事件相机插件，可在物理仿真环境中生成高速、完全标注的事件流，以缓解事件相机标注数据稀缺的问题。插件以极小改动从普通RGB相机迁移而来，继承Isaac Sim的物理引擎与帧级真值，输出可直接用于预训练事件网络的下游任务。

◆实现了基于对数强度对比度的事件生成模型，并采用逐像素异步参考更新策略以更贴近真实事件相机行为。

◆提出基于双向运动矢量扭曲的稀疏关键帧插值方法，仅渲染少量关键帧即可合成中间事件帧，实现单GPU实时生成。

◆引入可配置的传感器噪声与运动模糊模型，进一步缩小仿真到真实的差距。</td></tr>
<tr><td>2026-07-07</td><td>Why does Deep Learning Improve Visual SLAM?<br><a href='http://arxiv.org/pdf/2607.06023'>论文</a></td><td>本文针对深度学习视觉SLAM系统性能优越的根本原因进行了系统性探究。研究者通过精心设计的受控实验,分别剥离和组合&quot;学习式二维数据关联&quot;、&quot;不确定性估计&quot;以及&quot;循环神经网络架构&quot;三个关键组件,以揭示各自的贡献。

研究发现,深度学习SLAM系统的成功主要归功于学习式二维数据关联与不确定性建模的协同作用,而非循环架构本身。

◆ 首次以受控消融实验方式,定量分离并评估了学习式数据关联、不确定性估计和循环架构三者对DL-SLAM性能的独立贡献。

◆ 明确指出不确定性建模与数据关联学习是关键驱动因素,挑战了以往将性能提升简单归因于循环结构的普遍认知。

◆ 为未来SLAM系统的设计提供了明确指引,强调应聚焦于发展基于学习的二维数据关联与不确定性估计方法,而非过度依赖循环结构。

◆ 承诺开源代码以促进可复现研究,推动社区对深度学习SLAM内部机理进一步探索。</td></tr>
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
<tr><td>2026-06-30</td><td>Event-based Gaze Control System for Accurate Real-time Spin Estimation in Professional Ball Games<br><a href='http://arxiv.org/pdf/2606.26780'>论文</a></td><td>◆提出一套事件相机主动视觉系统，结合高速振镜与可调焦长焦镜头，在高速球类运动中持续放大、对焦并跟踪未改装球体。
◆设计混合跟踪策略，将事件驱动的2D检测用于实时居中，并利用3D定位结果进行重初始化，提高比赛场景鲁棒性。
◆提出球面事件对比度最大化方法s-CMax，实现跨乒乓球、棒球、网球和高尔夫的高精度离线旋转估计。
◆面向实时乒乓球应用，构建由伪真值训练的不确定性感知CNN，并结合GPU批量对比度最大化进行快速精修。
◆系统在职业乒乓球三视角实验中达到3毫秒延迟、750Hz吞吐率，并取得8.8%转速幅值误差和6.4度旋转轴误差。</td></tr>
<tr><td>2026-07-02</td><td>Shift Variant Image Degradation and Restoration Using Singular Value Decomposition<br><a href='http://arxiv.org/pdf/2606.25818'>论文</a></td><td>◆论文提出了一种基于奇异值分解的移变运动模糊图像复原框架，针对传统单一卷积核难以描述的空间变化退化问题。

◆其核心创新是用位置相关PSF构建移变成像算子，将退化过程统一建模为线性系统并进行SVD分析。

◆论文引入奇异值能量保留准则，系统选择小奇异值数量，以在抑制噪声放大和保留图像细节之间取得平衡。

◆方法覆盖双向线性运动、高斯运动和简谐运动三类一维移变PSF，验证了模型的适用性。

◆实验表明，该SVD稳定反演策略能够有效恢复图像细节、减轻模糊伪影，并揭示移变复原问题的病态特征。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>4935</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4352</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2426</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1616</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1611</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1447</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1281</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1271</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>986</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>961</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>924</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>798</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>781</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>743</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>726</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>713</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>642</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>640</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>625</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>595</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>578</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>558</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>549</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>511</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>502</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>445</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>426</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>173</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1040</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>870</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>701</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>659</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>650</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>623</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>590</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>575</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>569</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>563</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>553</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>517</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>494</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>463</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>449</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>446</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>335</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>314</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>122</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
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
> 更新于: 2026.07.14
