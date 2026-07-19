# 历史论文归档 (2026.07.19)

> 所有历史论文完整归档，按分类展示

<details>
<summary>分类目录</summary>
<ol>
<li><a href='#slam'>SLAM (130篇)</a></li>
<li><a href='#sfm'>SFM (65篇)</a></li>
<li><a href='#image-matching'>Image Matching (20篇)</a></li>
<li><a href='#obstacle-avoidance'>Obstacle Avoidance (137篇)</a></li>
<li><a href='#navigation'>Navigation (145篇)</a></li>
<li><a href='#motion-planning'>Motion Planning (212篇)</a></li>
<li><a href='#sensor-calibration'>Sensor Calibration (36篇)</a></li>
<li><a href='#sensor-undistortion'>Sensor Undistortion (79篇)</a></li>
</ol>
</details>

<h2 id='slam'>SLAM (130篇)</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-16</td><td>Immediate 3D Gaussian Splat Reconstruction of Unordered Input with Global Consistency<br><a href='http://arxiv.org/pdf/2607.14481'>论文</a></td><td>这篇论文提出了首个针对3D高斯泼溅(3DGS)重建的即时反馈方案,能够在无序图像输入下提供全局一致的重建结果。传统3DGS方法依赖有序序列或离线处理,而该方法突破了输入顺序的限制,实现了捕获过程中的实时可视化反馈。

◆ 利用视觉位置识别模型和共视性图(covisibility graph),提出了一种适用于无序序列的快速匹配方法,并能高效筛选高连接度关键帧,即使在有序序列下也能提升重建质量。

◆ 通过GPU优化和高斯基元(primitive)的精放置策略,实现了快速局部重建,在保持视觉质量的同时满足即时反馈的需求。

◆ 基于共视性图提出新颖的聚类(cluster-based)回环闭合方法,无需依赖顺序输入即可高效处理大范围场景中的回环问题,确保全局一致性。

◆ 引入渐进式层级结构(progressive hierarchy),使方法能够高效扩展到包含数千张图像的大规模环境,同时不牺牲计算效率。该方法在多个数据集上验证了其在无序输入下实现高质量即时3DGS重建的可行性。</td></tr>
<tr><td>2026-07-15</td><td>Breaking Déjà Vu: Independent Auditing of Visual Place Recognition through Vision-Language Reasoning<br><a href='http://arxiv.org/pdf/2607.12818'>论文</a></td><td>本文针对视觉位置识别（VPR）在实际部署中依赖固定阈值、难以适应环境变化的核心痛点，提出了一种基于视觉语言模型（VLM）的后检索独立审计框架。

传统VPR方法在闭环检测等安全关键场景中容易因固定阈值导致误匹配，进而污染SLAM估计的轨迹与地图，而本文方法在检索阶段后对候选匹配进行独立实例级验证。

该框架利用VLM对查询图像与候选图像进行联合推理判断，无需架构特定的置信度度量、数据集相关阈值或部署环境的先验知识，具备良好的通用性。

在六个基准数据集、五种SOTA VPR方法以及四种VLM上的广泛实验表明，该方法平均将recall@1提升13.6%，同时将误接受率降至12%，并保持精度高于95%、覆盖率高于75%。

核心创新点如下：

◆ 提出视觉位置识别审计（VPR Auditing）概念，将VLM作为独立的后检索验证器，实现查询与候选图像的联合语义推理。

◆ 设计无需架构特定置信度、无需数据集相关阈值、无需环境先验知识的通用验证机制，摆脱对部署调参的依赖。

◆ 在多数据集、多VPR方法、多VLM的组合实验中验证了框架的普适性，显著提升召回率的同时有效控制误匹配风险。</td></tr>
<tr><td>2026-07-15</td><td>Improving Map Consistency in Graph-Based LiDAR SLAM Through Information-Aware Odometry and Retroactive Loop Closure<br><a href='http://arxiv.org/pdf/2607.13516'>论文</a></td><td>该论文针对图优化LiDAR SLAM中轨迹精度高但地图几何一致性差的痛点，提出了一套系统性的改进方案。

◆ 提出基于几何依赖的信息矩阵估计框架，为ICP里程计约束提供原理化的权重分配，从而提升位姿图优化的可靠性。

◆ 设计分层回环检测模块，将位置识别与几何配准解耦，增强回环检测的鲁棒性。

◆ 提出回溯式回环闭合模块，利用已优化位姿图恢复先前被遗漏的回环约束，进一步修正局部偏差。

◆ 建立专门评估重访位置地图一致性的评测协议，弥补现有方法在局部几何质量评价方面的不足。

实验在多个公开数据集上的结果表明，该方法在保持全局轨迹精度与现有先进方法相当甚至更优的同时，显著提升了重访区域的局部地图几何一致性，验证了不确定性感知里程计与几何引导回环精化耦合的有效性。</td></tr>
<tr><td>2026-07-15</td><td>SeeSE3: Emergence of 3D Space in Vision Features<br><a href='http://arxiv.org/pdf/2607.14228'>论文</a></td><td>本文研究视觉基础模型的特征空间是否内在反映三维欧几里得空间的性质。作者以SE(3)变换群为分析框架，从拓扑与几何双重视角探测特征空间结构，区别于以往回归深度或法向量等图像级量的传统方式。

◆ 提出互近邻度量，从拓扑角度衡量特征邻域与空间结构的对齐程度。

◆ 设计Poincaré Adapter，测试相机运动几何在潜位移中的线性可及性。

◆ 发现自监督视觉模型的潜空间子结构与三维空间存在高度相关性，即使训练中未使用显式3D监督。

◆ 基于此提出&quot;潜空间导航&quot;方法，无需显式三维重建即可在潜空间中完成视觉里程计与定位。</td></tr>
<tr><td>2026-07-14</td><td>PixelLoop: Shortcut Topological Navigation with Pixel-Level Loops<br><a href='http://arxiv.org/pdf/2607.12811'>论文</a> | <a href='https://pixelloop-nav.github.io/'>代码</a></td><td>本文研究拓扑地图中的回环检测问题,聚焦于在纯拓扑表示中回环对导航的具体作用与下游影响。区别于传统基于全局位姿的SLAM回环,作者认为拓扑地图中的回环是连接不同路径的捷径,而非仅用于坐标对齐。

◆ 在像素空间直接引入回环闭合,提出PixelLoop方法,利用基于像素级相对3D几何的稠密拓扑表示,使回环作为稠密的拓扑捷径改变规划连通性和代价传播。

◆ 相比稀疏的图像级边或位姿图校正,像素级回环能够实现稳定的任意点到任意点导航,并生成与几何最短路径精确对齐的代价地图。

◆ 验证了将回环应用于细粒度像素拓扑相对于图像级拓扑的独特优势,在需要利用捷径的场景中提升最为显著。

在大量仿真实验中,PixelLoop相比图像级相对基线在成功率和SPL上均取得超过35%的绝对提升,并通过真实移动机器人部署进一步验证了稠密像素级回环作为拓扑视觉导航基础的实用性与鲁棒性。</td></tr>
<tr><td>2026-07-14</td><td>DiffRadar: Differentiable Physics-Aware Radar SLAM with Gaussian Fields<br><a href='http://arxiv.org/pdf/2607.12265'>论文</a></td><td>DiffRadar提出了一种基于可微物理感知高斯场的实时雷达SLAM系统，旨在解决传统雷达扫描匹配中离散化破坏几何连续性、导致位姿估计不稳定的问题。该方法将场景表示为各向异性高斯基元，通过可微雷达前向模型在距离-方位和多普勒-方位空间渲染观测，从而可直接从雷达信号联合优化机器人位姿与场景结构。

◆ 将雷达观测建模为可微物理感知高斯场，替代传统离散扫描匹配，保持几何连续性
◆ 采用各向异性高斯基元，通过可微前向模型在距离-方位和多普勒-方位空间渲染雷达信号
◆ 实现从雷达信号直接联合优化机器人位姿与场景结构，突破传统几何配准的局限
◆ 在商用FMCW雷达硬件上实现70 FPS实时运行

实验在Radarize基准及针对走廊退化、运动模式切换、动态杂波、长时回环等失效模式的压力测试套件上进行，结果显示轨迹误差显著降低，地图一致性提升超过一倍，尤其在特征稀疏的走廊场景下优势明显。</td></tr>
<tr><td>2026-07-13</td><td>Self-Healing Visual Recovery for Autonomous Ground Vehicles Using Camera-Only Visual Odometry<br><a href='http://arxiv.org/pdf/2607.11686'>论文</a></td><td>针对低成本仅用摄像头的地面机器人在循线行驶时易因遮挡或急转丢失引导线的问题，本文提出了一种轻量级的两阶段自愈恢复方法，无需激光雷达、GPS或GPU支持。
◆第一阶段通过原地旋转、逐步放宽颜色检测阈值并结合多帧确认来重新捕获引导线。
◆第二阶段利用单目视觉里程计回溯到预先保存的&quot;面包屑&quot;位置，为重新搜索争取空间。
◆整套系统在50毫秒控制周期内嵌入了完整的MAPE-K自适应循环，无需外部适配管理器。
◆系统融合深度门控HSV循线器、YOLOv8n障碍检测器与视觉里程计地图，在纯CPU硬件上达到20赫兹运行频率。
在Webots三个仿真场景共119次故障注入测试中，该方法成功率达86.6%，中位恢复时间为3.26秒，验证了仅依靠摄像头在成本与算力受限条件下实现可靠视觉恢复的可行性。</td></tr>
<tr><td>2026-07-13</td><td>GeoGS-SLAM: Online Monocular Reconstruction Using Gaussian Splatting with Geometric Priors<br><a href='http://arxiv.org/pdf/2607.11184'>论文</a> | <a href='https://rlgao.github.io/geogs_slam'>代码</a></td><td>GeoGS-SLAM提出了一种基于3D高斯泼溅的单目在线稠密重建系统，核心目标是解决现有方法依赖外部深度传感器或丢弃RGB信息导致重建质量下降的问题。系统首先利用预训练的前馈视觉几何模型从无标定RGB输入中预测相机位姿与场景几何先验，随后通过直接从RGB和几何先验中采样高斯基元来扩展场景地图。

◆提出融合3DGS表征与学习几何先验的单目稠密SLAM框架，无需外部深度传感器即可实现高质量重建。

◆设计从RGB和几何先验联合采样高斯基元的策略，并采用由粗到精的优化方式协同最小化光度与几何损失。

◆引入在线回环检测与位姿图优化以保证全局一致性，同时维持在线实时性能。

◆在室内外基准测试中取得了优于现有方法的渲染质量与跟踪精度。</td></tr>
<tr><td>2026-07-13</td><td>Desc++: Efficient Descriptor Enhancement for Data Association in Existing Visual SLAM Systems<br><a href='http://arxiv.org/pdf/2607.11099'>论文</a></td><td>本文针对视觉SLAM中传统手工描述符在光照和视角变化下鲁棒性不足、而学习型前端又需替换整个流水线的问题，提出了一种轻量级描述符增强模块Desc++。

◆创新点一：提出联合编码描述符表征与关键点几何信息的混合架构，将顺序无关的全局注意力与几何感知的序列建模相结合，在保持线性时间复杂度的同时增强上下文表达能力。

◆创新点二：增强后的描述符保持原始维度和匹配接口，无需修改现有流水线即可直接集成到已部署的V-SLAM系统中。

◆创新点三：在描述符匹配、对应点分析以及四个不同V-SLAM系统的系统级基准测试中，匹配精度超越现有最优增强方法，并将提升转化为更准确稳定的轨迹估计。

◆创新点四：在精度与效率之间取得良好平衡，适合实际集成到实时V-SLAM流水线中。</td></tr>
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
<tr><td>2026-07-08</td><td>STEMbot: A Compliant Robot for Under-Canopy Plant Navigation<br><a href='http://arxiv.org/pdf/2607.07873'>论文</a></td><td>有机农业的可扩展性受限于叶片下部和茎部害虫监测所需的高昂人力成本。为实现早期害虫检测，本文提出STEMbot，一种用于植物冠层下自主导航的微型攀爬机器人系统。
◆针对现有攀爬平台缺乏机载感知或仅限于无分支垂直主干的问题，STEMbot在攀爬过程中将基于几何的PIN-SLAM管线与语义OcTree相集成，实现了鲁棒的定位与建图。
◆提出了流形约束A*规划器结合光线追踪目标指定方法，实现了分支感知的穿越与遮挡目标的检查。
◆硬件实验表明，系统可穿越7-33mm直径的茎部，并在四种植物上完成自主导航，平均Chamfer距离小于1cm，验证了全局一致的里程计精度。</td></tr>
<tr><td>2026-07-07</td><td>Amplitude-Independent Robust Snapshot 6-D Radio SLAM via a Uniffed Angle-Delay Formulation<br><a href='http://arxiv.org/pdf/2607.04847'>论文</a></td><td>本文针对双基地快照无线电SLAM问题，提出了一种幅值无关的鲁棒方法，可在单次多径信道快照中联合估计用户设备6维位姿与时钟偏差并重构环境散射点。

◆创新点一：构建了LoS与单次反射NLoS路径的统一角度-时延公式，粗估计阶段无需依赖路径幅值或路径损耗进行LoS预分类，直接基于几何一致性筛选内点，对标定误差和传播模型失配具有更强鲁棒性。

◆创新点二：通过twist-swing两阶段遍历初始化与SO(3)上局部精炼，将方法推广到一般3维/6维位姿估计。

◆创新点三：精炼阶段采用Jacobian行均衡的迭代重加权最小二乘结合QAIC模型比较，自动检测LoS路径并联合优化UE状态与散射点。

◆创新点四：理论分析了公式特有的局部秩性质及其在路径身份未知条件下的最小集配置。</td></tr>
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
<tr><td>2026-07-07</td><td>CILC: Cryptographically-secure Inter-agent Loop Closure Candidate Detection for Multi-Agent Collaborative SLAM<br><a href='http://arxiv.org/pdf/2607.06700'>论文</a></td><td>这篇论文针对多智能体协作SLAM中全局描述符交换所引发的隐私泄露隐患，提出了名为CILC的密码学安全回环候选检测系统。作者首先揭示了一个具体且可实施的攻击：被攻陷的智能体能够从他方智能体广播的明文全局描述符中重建出其近似图像与运动轨迹。系统的核心创新在于引入安全多方计算（SMPC），使各智能体在不暴露明文描述符的前提下完成相似度比较。区别于对整个CSLAM流水线加密的方案，CILC仅对计算量轻量的回环检测环节施加密码学保护，从而获得更优的隐私与开销权衡。仿真与硬件实验均验证了系统在视觉和LiDAR多模态描述符下均具备实时性与通信可行性。

◆ 首次揭示被攻陷智能体可从公开广播的全局描述符反推出他方图像与轨迹的具体隐私威胁
◆ 提出首个基于安全多方计算的智能体间回环候选检测系统CILC，无需明文交换描述符
◆ 采用选择性保护策略，仅对轻量级描述符相似度比较施加SMPC加密，实现隐私与效率的平衡
◆ 支持视觉与LiDAR跨模态全局描述符，并在仿真与硬件平台上验证了实时可行性...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-07</td><td>MiLSD: A Micro Line-Segment Detector for Resource-Constrained Devices<br><a href='http://arxiv.org/pdf/2607.06600'>论文</a></td><td>该论文针对资源受限设备提出亚兆字节级线段检测器MiLSD，系统研究了紧凑模型下精度与内存的权衡关系。

◆ 提出MiLSD检测器，采用轻量全卷积骨干网络，整体参数量控制在1MB以内，可在MCU上部署。

◆ 提出F-Clip中心-长度-角度输出表示形式，在小模型规模下学习效果显著优于其他表示。

◆ 系统分析不同比特宽度量化的影响，发现8-bit量化可保持全精度性能，而4-bit量化在角度回归上退化严重，量化感知训练仅能部分恢复。

◆ 设计多种推理增强策略，包括亚像素解码、测试时增强和轻量级验证器。

◆ 在ShanghaiTech Wireframe上将sAP10从10.6提升至24.1，显著优于同参数量基线，绘制了跨表示、位宽、容量和后处理策略的精度-内存权衡图谱。</td></tr>
<tr><td>2026-07-06</td><td>Geometry-Aware Visual Odometry for Bronchoscopic Navigation via High-Gain Observer Fusion<br><a href='http://arxiv.org/pdf/2607.05162'>论文</a></td><td>本文针对导航支气管镜中视觉里程计在纹理缺乏、镜面反射和管腔消失点等场景下易跟踪失败的问题，提出了一种几何感知的视觉里程计框架。

◆ 创新点一：利用气道管腔的消失点线索，将检测到的管腔反投影为三维射线并通过加权融合获得稳定的前进方向估计，弥补了纯视差线索不足时的航向漂移。

◆ 创新点二：结合基于looming效应的速度估计，使用定制的高增益观测器将航向与速度信息与噪声较大的视觉里程计输出进行融合，引入气道跟随先验并主动抑制漂移。

◆ 创新点三：在体外机械通气人肺上以电磁跟踪为真值进行验证，相比ORB-SLAM2、LoFTR-VO和DPVO等主流方法，绝对轨迹误差降低超过50%，相对位姿误差在所有测试序列中均最低。

该工作摆脱了对术前CT和外部传感器的依赖，为重症监护和资源受限环境下的纯视觉支气管镜导航提供了可扩展的解决方案。</td></tr>
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
<tr><td>2026-07-03</td><td>DL-SLAM: Enabling High-Fidelity Gaussian Splatting SLAM in Dynamic Environments based on Dual-Level Probability<br><a href='http://arxiv.org/pdf/2607.01860'>论文</a></td><td>本文针对3D高斯泼溅动态SLAM中存在的瞬态静态物体处理不当问题,提出了基于双层概率框架的DL-SLAM系统。现有方法要么直接丢弃预定义的动态物体,要么将瞬态静态物体错误地整合到静态地图中,造成持续性伪影;此外仅依赖几何信息导致不确定性图中物体边界模糊。

核心创新点如下:

◆ 提出双层概率框架,通过融合语义与几何信息计算像素级动态概率,并将其提升到三维空间聚合成实例级的物体级动态概率。

◆ 基于物体级动态概率对动态高斯进行分类剪枝,生成无伪影的高保真静态语义地图。

◆ 静态地图反向提供几何一致性约束,用于迭代精化像素级动态概率的可靠性,形成闭环优化机制。

◆ 在跟踪精度上较现有方法提升最高达13%,同时保持高保真语义建图质量,验证了双层概率机制在动态环境中的有效性。</td></tr>
<tr><td>2026-07-03</td><td>E-TraMamba: A New Paradigm for Efficient Long-Term 3D Feature Tracking with Event Cameras<br><a href='http://arxiv.org/pdf/2607.02866'>论文</a></td><td>本文针对事件相机3D特征跟踪中现有CNN和Transformer方法难以高效建模稀疏噪声事件流长程时空依赖的问题，提出了E-TraMamba框架。其核心贡献与创新点如下：

◆ 首次将Mamba状态空间模型引入事件相机3D特征跟踪任务，实现线性复杂度的长程时空建模，显著提升效率。

◆ 设计轻量化的仿射变换预测器，有效应对运动模糊和遮挡场景下的稳定跟踪。

◆ 提出多尺度线索融合方案，将局部时空块、相关性图和位置嵌入统一表征，增强跟踪的稳定性与平滑性。

◆ 构建大规模合成数据集EvD-PointOdyssey，通过单目渲染提供同步的事件流、深度图和精确3D轨迹。

◆ 在多个事件基准上取得最优性能，在严格精度阈值下特征寿命提升超过2倍，跟踪比例更高且RMSE更低，适用于低延迟视觉里程计、实时SLAM及交互式机器人。</td></tr>
<tr><td>2026-07-02</td><td>A Stereo Visual SLAM System Using Object-Level Motion Estimation and Geometric Filtering Based on Cross Disparity<br><a href='http://arxiv.org/pdf/2607.02005'>论文</a></td><td>本文提出了一种名为OCD SLAM的动态双目视觉SLAM系统，基于ORB-SLAM2进行扩展，旨在解决动态环境下静态世界假设失效的问题。该系统通过特征级和对象级两个层面联合检测动态元素，实现对静态与动态场景元素的鲁棒分离，从而提升位姿估计精度。

创新点如下：

◆ 提出&quot;交叉视差&quot;（cross disparity）新概念，结合视差信息与时间一致性、立体不一致性，有效识别动态特征点。

◆ 将3D目标检测模块（SMOKE）与基于卡尔曼滤波的目标跟踪相结合，实现对象级运动分类，弥补单一特征级检测的不足。

◆ 在KITTI Odometry和KITTI Raw数据集上的实验表明，该方法在轨迹精度上显著优于ORB-SLAM2及多种当前先进的动态SLAM方法。

◆ 消融实验验证了交叉视差模块的有效性，能够检测出仅依靠3D目标检测方案所遗漏的动态特征。</td></tr>
<tr><td>2026-07-02</td><td>DL-VINS-Factory: A Modular Framework for Learned Visual Front-Ends in Visual-Inertial SLAM<br><a href='http://arxiv.org/pdf/2607.01757'>论文</a> | <a href='https://github.com/limshoonkit/DL-VINS-Factory-ROS2/'>代码</a></td><td>DL-VINS-Factory是一个模块化视觉惯性SLAM框架,系统整合了多种学习型特征提取器(ALIKED、RaCo、SuperPoint、XFeat)与LK光流跟踪或LightGlue描述子匹配,统一接入基于滑动窗口Ceres的紧耦合后端,并支持AnyLoc DINOv2-VLAD回环检测与4自由度位姿图优化。该工作通过EuRoC、NTU-VIRAL、Botanic Garden和SubT-MRS四个涵盖室内、室外、激进运动和视觉退化场景的数据集进行系统基准测试,实证评估了学习型前端在实时嵌入式VI-SLAM中的实际价值。

◆ 首个统一的模块化框架,系统对比多种学习型特征(ALIKED、RaCo、SuperPoint、XFeat)与LK光流或LightGlue匹配的组合,接入紧耦合Ceres后端
◆ 在EuRoC上,ALIKED+LG相比GFTT+LK基线单目ATE降低5%、带回环双目降低7%
◆ 在NTU-VIRAL激进运动场景下,ALIKED+LG双目带回环ATE降低12%
◆ 集成AnyLoc DINOv2-VLAD回环检测,有效回环数比传统BRIEF+DBoW2提升约2到7倍
◆ 全部配置在Jetson AGX Orin上经TensorRT加速后,单目29至47 FPS、双目18至33 FPS,满足实时性要求

研究发现学习型前端在大多数场景下可行但并非全面优于经典方法,需根据具体环境选择性使用。</td></tr>
<tr><td>2026-07-02</td><td>LuxSQA: Ask Me in Luxembourgish with TTS-Augmented Spoken Question Answering<br><a href='http://arxiv.org/pdf/2607.02763'>论文</a></td><td>本文针对低资源语言卢森堡语的语音问答任务，探索了利用文本转语音合成训练数据的可行性。研究从现有文本QA资源出发，将问题翻译为卢森堡语，并通过多种TTS系统合成语音问题，与文本答案配对，构建了约4.8万条单源和约23万条四TTS多源语料。模型采用SLAM风格架构，通过可学习的投影器与LoRA适配器连接冻结的Whisper编码器与冻结的多语言大语言骨干，实现参数高效训练。实验在包含真实卢森堡语说话人的LLAMA-LB-Test上表明，多源合成与基于声音设计的训练配置能取得最佳效果。同时发现无参考TTS质量评分与下游QA性能并非单调相关，说明合成语音应作为任务特定训练数据而非仅追求自然度来评估。

◆首次系统验证TTS合成可作为低资源SQA任务专用训练数据，无需大规模人工录音语料
◆提出多TTS系统混合的数据增强策略，显著提升模型对真实说话人的泛化能力
◆采用冻结Whisper编码器加投影器加LoRA的轻量化架构，有效适配多语言LLM
◆揭示了TTS自然度与下游任务性能脱钩的现象，倡导以任务为导向评估合成语音...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-30</td><td>TACO: A Test and Check Framework for Robust Pose Graph Optimization<br><a href='http://arxiv.org/pdf/2606.29851'>论文</a></td><td>◆提出TACO（Test And Check Optimization），一个面向鲁棒位姿图优化的在线框架，用于在SLAM中抑制错误回环导致的外点影响。
◆其核心思想不是显式建模内点/外点，而是增量近似寻找最大一致测量集合。
◆“Test”部分设计了增量概率一致性算法IPC，可在线评估每个新回环约束的一致性。
◆“Check”部分提出Switchable Outlier Sanitization，周期性利用Switchable Constraints清理IPC误接纳的不一致约束。
◆实验表明，TACO在2D和3D数据集上兼具接近离线鲁棒方法的精度与在线部署所需的效率，并开源了实现。</td></tr>
<tr><td>2026-06-30</td><td>ForgeDrive: Bidirectional Cross-Conditioning for Unified Visual-Action Generation in Autonomous Driving<br><a href='http://arxiv.org/pdf/2606.31226'>论文</a></td><td>◆提出ForgeDrive，一个统一的自回归扩散框架，将未来建模为逐时刻的“图像帧-动作”对，实现视觉生成与动作规划的紧密耦合。
◆它用act-then-imagine范式替代传统imagine-then-act，避免视觉生成误差先行累积并传递到规划阶段。
◆训练中解耦视觉与动作的扩散时间步，并引入类似UniDiffuser的噪声调度，使模型能在两种模态间双向推断与交叉条件生成。
◆推理时先生成动作，再用动作提升未来帧生成质量，进而反哺下一步动作，形成视觉与行动的闭环增强。
◆模型还加入未来自车状态预测，进一步提升规划能力；在NAVSIM实验中同时统一驾驶仿真、规划和视觉里程计，并优于强基线规划器。</td></tr>
<tr><td>2026-06-30</td><td>VOCA: Visual Odometry with Codec Awareness<br><a href='http://arxiv.org/pdf/2607.00189'>论文</a></td><td>VOCA是一种面向压缩视频流的因果式立体视觉里程计方法，旨在解决传统视觉里程计系统在硬件压缩视频上因压缩伪影而性能退化的问题。

◆ 创新性地将视频编解码器信息（如运动矢量、量化参数等元数据）融入视觉里程计跟踪流程，利用编解码器先验提升位姿估计的鲁棒性。
◆ 提出了因果式立体视觉里程计框架，在严格因果性约束下融合编解码器信息，兼容实际流式处理场景。
◆ 在压缩视频流上同时取得相对轨迹误差、绝对轨迹误差和运行效率三个维度的领先性能。
◆ 揭示了广泛可用的编解码器元数据对下游视觉任务的潜在增益，为压缩域视觉感知研究提供了新思路。</td></tr>
<tr><td>2026-06-30</td><td>PRISM-VO: Scale-Aware Visual Odometry Using Photometric Plenoptic Bundle Adjustment<br><a href='http://arxiv.org/pdf/2607.00176'>论文</a> | <a href='https://prism-vo.github.io/'>代码</a></td><td>PRISM-VO是一种面向聚焦型光场相机的纯优化稀疏光度视觉里程计框架,核心是基于滑动窗口的光度光场束束调整方法,联合优化相机位姿与特征点逆深度。

◆ 提出光度光场束束调整,将光度误差与光场投影模型相结合,在滑动窗口内同时优化相机位姿和逆深度,提升运动估计的精度与抗漂移能力。

◆ 利用单张光场图像的几何深度先验与时序多视图约束相融合,无需复杂初始化即可获得可靠的深度估计。

◆ 通过显式建模光场投影过程,有效解决了单目SLAM中普遍存在的尺度模糊问题,实现了场景的公制尺度重建。

◆ 仅依赖单一光场传感器,方法简洁高效,在室内外场景实验中超越现有光场视觉里程计方法,并与基于优化和学习的方法相媲美,同时能够准确恢复场景的公制尺度。</td></tr>
<tr><td>2026-06-29</td><td>Robust and Efficient Monocular 3D Gaussian SLAM for Kilometer-Scale Outdoor Scenes<br><a href='http://arxiv.org/pdf/2606.30436'>论文</a></td><td>◆提出KiloGS-SLAM，面向公里级室外场景解决单目3DGS-SLAM中长期位姿易漂移与大规模建图显存开销高的耦合难题。
◆设计运动自适应混合跟踪模块，通过条件触发的三层求解流程提升长序列位姿鲁棒性。
◆该跟踪模块可在Essential矩阵与PnP模型间动态切换，以应对不同运动模式和几何退化情况。
◆引入按需启动的基础模型，在轨迹发生灾难性漂移时进行恢复，增强系统长期运行稳定性。
◆提出生命周期管理的高斯建图策略，结合概率初始化、分块多视图增密与剪枝，在保留细节的同时显著减少冗余，实验表明其在单GPU上可处理超过1万帧并达到先进的跟踪和渲染效果。</td></tr>
<tr><td>2026-06-29</td><td>CSAR: Containerized System Architecture for Robotics<br><a href='http://arxiv.org/pdf/2606.30293'>论文</a> | <a href='https://github.com/goyoambrosio/CSAR'>代码</a></td><td>◆提出CSAR这一面向机器人团队与边缘-云连续体的容器化系统架构，解决依赖隔离、兼容性、复现性和异构部署难题。
◆将LXC/LXD系统容器、ROS 2/DDS通信和三层边缘基础设施结合，形成持久、硬件亲和且与实验负载解耦的运行环境。
◆通过基础设施核心、平台与多用户编排、计算与加速三层设计，实现强隔离、受控资源共享和拓扑感知网络。
◆在真实学术机器人实验室中部署验证，展示其对多用户协作开发、共享专用硬件和安全原型实验的支持。
◆通过边缘卸载3D SLAM和GPU加速语义建图案例评估，证明CSAR能提升资源利用率、简化集成并增强实验可复现性。</td></tr>
<tr><td>2026-06-29</td><td>Self-supervised Geometry Reasoning for LiDAR Simultaneous Localization and Mapping<br><a href='http://arxiv.org/pdf/2606.30166'>论文</a></td><td>◆提出一种用于LiDAR SLAM的自监督几何推理框架，解决传统手工局部几何估计在稀疏点云和低分辨率LiDAR下噪声大、不稳定的问题。
◆将每个点显式建模为高斯分布，用协方差表示局部几何，从而获得可解释的符号化几何表示。
◆无需密集几何标签或真实位姿，通过预测协方差、点对应关系和SLAM轨迹之间的一致性关系构造自监督信号。
◆设计几何学习与SLAM相互促进的递归闭环：更好的几何提升定位建图，更准确的轨迹又提供更干净的监督。
◆方法与后端无关，可直接插入现有LiDAR SLAM系统而无需改动架构。
◆在KITTI及不同LiDAR分辨率实验中，该方法同时提升了里程计精度和全局配准效果。</td></tr>
<tr><td>2026-06-29</td><td>MSFA-Net: An Advanced Deep Learning Model for Identifying Blue Horizontal-Branch Stars from LAMOST DR12<br><a href='http://arxiv.org/pdf/2606.29918'>论文</a></td><td>该论文针对蓝水平支(BHB)恒星在低分辨率光谱中识别困难的问题,提出了名为MSFA-Net的两阶段深度学习框架,显著提升了BHB恒星的分类精度。MSFA-Net通过多尺度卷积与软频率注意力机制,实现波长域与傅里叶频域的联合特征学习,从而更充分地捕捉光谱的判别性信息。在测试集上,该框架的初步多分类筛选精度达到94.67%,二分类精修精度高达98.07%。

◆ 提出两阶段级联识别框架,先进行多分类粗筛再进行二分类精修,有效降低类间混淆

◆ 将多尺度卷积与软频率注意力机制相结合,在波长域和傅里叶频域双域联合学习光谱特征

◆ 基于LAMOST DR12数据新增3583颗经巴尔末线轮廓拟合确认的BHB恒星,大幅扩充了BHB样本目录,并通过Gaia DR3测光交叉验证和SLAM大气参数估计提供了完备的恒星物理参数分析。</td></tr>
<tr><td>2026-06-29</td><td>MyGO-Splat: Multi-Objective Closed-Loop Geometric Feedback for RGB-Only Gaussian SLAM<br><a href='http://arxiv.org/pdf/2606.29738'>论文</a></td><td>◆ MyGO-Splat提出一种面向RGB-only单目SLAM的闭环Gaussian SLAM框架，解决传统单目系统尺度不确定和几何漂移难以自校正的问题。
◆ 该方法将3D Gaussian原语解析光栅化为逐像素深度和表面法线，使已优化地图能够反向监督相机位姿跟踪。
◆ 论文引入尺度感知的自适应对齐机制，将基础模型预测的单目深度投影到全局一致的Gaussian空间中。
◆ 通过“深度先验—Gaussian优化—位姿反馈”的闭环设计，系统实现了尺度反馈和几何自校正，提升了尺度稳定性。
◆ 实验表明，MyGO-Splat在仅使用RGB输入的情况下，获得了接近RGB-D方法的表现，并改善了外观与几何的一致性。</td></tr>
<tr><td>2026-06-28</td><td>VCS-SLAM: Geometry-Validated Semantic Evidence Fusion for 3D Gaussian SLAM<br><a href='http://arxiv.org/pdf/2606.29494'>论文</a></td><td>◆提出VCS-SLAM，一个面向RGB-D 3D Gaussian SLAM的几何验证语义证据融合框架。
◆不同于统一加权融合2D语义先验，它显式评估在线语义观测的几何可靠性。
◆通过可见性一致性抑制遮挡区域的错误语义更新，减少全局地图中的持久伪影。
◆利用表面支撑的边界证据缓解语义边界外溢，并用射线级冲突不确定性延迟模糊区域的过早标注。
◆实验表明，该方法在Replica上提升语义一致性、边界保持和重建质量，在ScanNet真实RGB-D输入下仍保持有竞争力的跟踪性能。</td></tr>
<tr><td>2026-06-28</td><td>PL-LIT: A LiDAR-Inertial-Thermal SLAM Using Point-Line Features and Thermographic Mapping<br><a href='http://arxiv.org/pdf/2606.29259'>论文</a></td><td>◆ 提出PL-LIT通用LiDAR-惯性-热成像SLAM框架，可同时适配可见光与热红外相机，提升恶劣光照、雾等条件下的定位鲁棒性。
◆ 通过在线光度标定缓解热相机AGC和低对比度带来的亮度不一致问题。
◆ 引入深度网络提取点线特征，使热图像跟踪更稳定、可重复。
◆ 在ESIKF中构建紧耦合LiDAR-惯性-热成像状态估计，并设计可靠的线特征几何约束。
◆ 构建概率热强度体素地图，支持实时热异常检测与安全巡检。
◆ 实验证明其在可见光环境具备通用性，在长距离热红外数据集上达到先进性能。</td></tr>
<tr><td>2026-06-28</td><td>MoPe: Motion Permanence for Robust Monocular Gaussian Mapping in Dynamic Environments<br><a href='http://arxiv.org/pdf/2606.29237'>论文</a></td><td>该论文针对动态环境中单目Gaussian Splatting SLAM易把短暂停止或遮挡后重现的动态物体误融入地图、产生鬼影的问题，提出MoPe以提升建图稳定性与定位鲁棒性。
◆提出“运动永久性”原则，强调动态性应由历史运动状态决定，而非逐帧重新判断。
◆设计记忆感知不确定性滤波器，通过几何一致的SE(3)扭曲传播历史动态后验。
◆采用有界贝叶斯log-odds更新融合历史与当前观测，避免动态状态被短时静止外观覆盖。
◆将持久动态后验用于跟踪、建图、动态感知高斯插入和高斯级后处理清理。
实验在Wild-SLAM、Bonn和TUM上验证了MoPe能减少残留鬼影并提升跟踪鲁棒性，尤其适用于动态行人场景。</td></tr>
<tr><td>2026-06-27</td><td>How to Leverage Synthetic Speech for LLM-Based ASR Systems?<br><a href='http://arxiv.org/pdf/2606.29031'>论文</a></td><td>◆本文面向隐私受限的银行、医疗等场景，系统研究如何用合成语音训练基于LLM的ASR，并直面合成与真实语音的分布差距来源。

◆作者通过探测SLAM-ASR架构，定位出LLM骨干主要在早期到中层区分真实与合成语音。

◆研究发现，时间结构和韵律扰动最容易破坏这种判别信号，说明差距不仅来自音质自然度。

◆论文指出，表示层面的真实/合成可分性虽有参考价值，但不能直接预测最终ASR性能提升。

◆作者发现RIR卷积能通过模拟真实录音的声学不规则性缩小差距，并结合层选择模块，使系统仅用25%真实语音即可匹配全真实数据基线。</td></tr>
<tr><td>2026-06-27</td><td>J-LAW: Joint Localization and Actionable World Modeling via Coupled Latent Factor Graphs<br><a href='http://arxiv.org/pdf/2606.28712'>论文</a></td><td>◆ J-LAW将传统SLAM的度量定位建图与可用于规划的动作条件世界模型统一为同一个联合估计问题。
◆ 它提出耦合潜因子图，同时优化物体位姿、潜在世界状态和潜在地标嵌入。
◆ 关键创新是引入位姿条件潜编码器和位姿—潜变量耦合因子，使定位与世界模型相互校正、共同提升。
◆ 方法把观测、动作预测、里程计、潜在闭环和潜在地标观测等统一进单一MAP目标。
◆ 实验表明，J-LAW相比开环 rollout 显著降低潜预测误差和终点漂移，并提升全局轨迹一致性，生成兼具度量性和可行动性的地图。</td></tr>
<tr><td>2026-06-26</td><td>RayPE: Ray-Space Positional Encoding for 3D-Aware Video Generation<br><a href='http://arxiv.org/pdf/2606.27345'>论文</a></td><td>◆ RayPE指出传统视频DiT仅在(u,v,t)网格上做RoPE，缺乏对场景三维几何关系的显式建模。
◆ 它将每个token对应的相机射线表示为6D Plücker坐标，并利用Plücker互易积与Transformer注意力点积同为双线性形式的联系。
◆ 方法把射线位置编码以加法方式注入Q/K，并设计query/key翻转结构，使对称恒等配置可精确对应互易积。
◆ 注入后注意力分解为内容项、几何项及两类内容-几何交叉项，实验表明这些部分都不可或缺。
◆ 为适配不同相机平移尺度，RayPE解耦射线方向与矩幅值，引入基于对数幅值的门控，并用RMSNorm稳定对齐内容分支。
◆ 该模块参数增加不到0.1%、可零初始化接入预训练视频DiT，并提升相机可控性、跨帧3D一致性和整体视频质量。</td></tr>
<tr><td>2026-06-26</td><td>LXD-SLAM: LiDAR+X Dense SLAM with $\sum_{i=0}^{5}C_5^i$ Configurable Sensor Combinations<br><a href='http://arxiv.org/pdf/2606.27811'>论文</a> | <a href='https://github.com/peterWon/LXD-SLAM'>代码</a></td><td>◆ LXD-SLAM提出以3D LiDAR为核心的高度模块化密集SLAM框架，可即插即用融合相机、IMU、轮速计和GNSS，支持最多32种传感器组合。
◆ 方法采用统一的迭代误差状态卡尔曼滤波，并通过自适应分层预测融合不同传感器观测，提升数学一致性与鲁棒性。
◆ 在更新阶段同时最小化点到网格距离和视觉重投影误差，实现几何与视觉信息的紧耦合优化。
◆ 论文用连续多层高斯过程子网格建模环境，支持高效射线到网格深度恢复，并生成高质量实时密集网格。
◆ 为保证全局一致性，提出基于GP子网格的ESC描述子和双向PnP优化，在混合位姿图中实现稳健多模态回环检测。
◆ 实验表明，LXD-SLAM在多种配置下达到或超过专用里程计方法，并能在真实场景中输出全局一致的高保真地图。</td></tr>
<tr><td>2026-06-26</td><td>PinNet: Keypoint-Aware Learned Local Descriptors with Geometric Embedding for Loop Closure in LiDAR SLAM<br><a href='http://arxiv.org/pdf/2606.28637'>论文</a></td><td>◆PinNet面向仅依赖LiDAR几何信息的回环检测难题，学习生成适用于地点识别和scan-to-scan配准的局部几何描述子。
◆它将关键点检测与描述子提取整合在同一神经网络中，使特征更贴合点云中的稳定几何结构。
◆论文提出基于平面的几何自注意力模块，显式建模关键点之间的空间关系，从而增强描述子的判别性。
◆该方法不仅用于回环候选识别，还能支持精确相对位姿估计和单次定位，提升LiDAR SLAM的全局一致性。
◆在不同LiDAR传感器和多种环境数据集上的实验表明，PinNet具备较强的泛化性、地点识别能力和配准精度。</td></tr>
<tr><td>2026-06-26</td><td>Fast and Accurate Outlier-Aware LiDAR Super-Resolution for SLAM Applications<br><a href='http://arxiv.org/pdf/2606.28607'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-26</td><td>Improvement of Robot&#x27;s Simultaneous Localization and Mapping Using an Effective Transformation to Achieve Linear Model<br><a href='http://arxiv.org/pdf/2606.28475'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-25</td><td>PanoImager: Geometry-Guided Novel View Synthesis and Reconstruction from Sparse Panoramic Views<br><a href='http://arxiv.org/pdf/2606.27071'>论文</a></td><td>◆PanoImager面向稀疏全景图在旋转主导、弱视差条件下难以进行SfM/SLAM初始化的问题，提出了一个无需SfM的三维重建框架。
◆它结合前馈式位姿/深度先验，为极少量全景输入提供可靠的几何约束。
◆方法将全景图分解为局部透视视图，并通过几何条件扩散模型合成辅助新视角，增强稀疏观测信息。
◆在重建阶段，PanoImager利用深度引导的3D Gaussian Splatting优化，提高跨视角一致性与优化稳定性。
◆多数据集实验表明，该方法在极端稀疏输入下更稳定，可作为SfM/SLAM失败时的离线地图细化组件。</td></tr>
<tr><td>2026-06-25</td><td>Structured-Li-GS: Structured 3D Gaussians Splatting with LiDAR Incorporation and Spatial Constraints<br><a href='http://arxiv.org/pdf/2606.27509'>论文</a></td><td>◆提出Structured-Li-GS，一个融合LiDAR-惯性-视觉SLAM的轻量级3D Gaussian Splatting框架，实现尺度准确的高质量三维重建。
◆利用精确、稠密、带颜色的点云进行训练，并用子采样点云锚定Gaussian primitives，从源头减少所需高斯数量。
◆根据局部表面几何初始化高斯椭球参数，使模型更符合真实结构并提升重建效率。
◆设计包含光度、平坦化、偏移、深度和法线约束的综合损失，在无需Gaussian densification的情况下保持高保真重建。
◆构建硬件同步的LiDAR-相机手持扫描设备，并在公开与自建真实数据集上验证其优于现有方法且模型规模更小。</td></tr>
<tr><td>2026-06-24</td><td>FAST-LIVGO: A Degeneracy-Robust LiDAR-Inertial-Visual-GNSS Fusion Odometry<br><a href='http://arxiv.org/pdf/2606.19190'>论文</a></td><td>◆ FAST-LIVGO提出一种基于误差状态迭代卡尔曼滤波的紧耦合LiDAR-惯性-视觉-GNSS融合里程计，面向长距离、大尺度和动态环境中的稳健定位建图。
◆ 其在线时空对齐模块引入动态时间规整，提升多传感器在高速和强动态条件下的同步与融合可靠性。
◆ 方法设计了基于多普勒频移和固定锚点时间差分载波相位的GNSS观测模型，在不增广历史状态的情况下提供毫米级相对约束。
◆ 针对几何退化或纹理缺失场景，提出退化感知的双模式外点剔除策略，可在LIVO先验引导和GNSS辅助恢复之间自适应切换。
◆ 在M3DGR和20 m/s固定翼无人机数据集上的实验表明，该系统显著降低累计漂移和地图重影，精度与鲁棒性优于现有方法。</td></tr>
<tr><td>2026-06-24</td><td>GeoFlow-SLAM++: A Robust Multi-Camera Visual-Inertial SLAM System with Relocalization<br><a href='http://arxiv.org/pdf/2606.22051'>论文</a></td><td>◆提出GeoFlow-SLAM++，将原GeoFlow-SLAM从单RGB-D扩展为标定多相机视觉惯性SLAM，并采用统一的以机体为中心的紧耦合状态表示。
◆系统在同一多相机框架下支持可互换的ORB前端与基于SuperPoint/LightGlue的神经网络特征前端，增强了外观变化场景下的鲁棒性。
◆统一整合跟踪、建图与重定位，结合多相机重投影约束、IMU预积分、跨视角地点识别和光流/NN特征双流跟踪。
◆引入可选的跨视角一致伪深度约束，使仅RGB输入也能获得额外几何信息辅助定位。
◆在EuRoC、OpenLORIS、TUM、Hilti及自采多相机数据集上的实验表明，该方法在鲁棒性、定位精度和跨会话重定位方面均具有竞争力，手持数据上达到接近LiDAR的表现。</td></tr>
<tr><td>2026-06-24</td><td>RoboAtlas: Contextual Active SLAM<br><a href='http://arxiv.org/pdf/2606.26046'>论文</a></td><td>◆ 提出RoboAtlas，一个上下文主动SLAM框架，可在几何探索与语义推理之间自适应权衡。

◆ 构建OpenRoboVox可扩展3D语义地图系统，将大规模语义实例与空间结构结合，为导航决策提供全局上下文。

◆ 通过上下文多臂老虎机机制融合前沿探索、全局语义地图推理和第一视角VLM推理，使机器人随场景理解提升逐步转向语义引导导航。

◆ 在超过1800平方米真实环境和约3万语义实例映射中实现100%任务成功率，验证了系统的大规模实用性。

◆ 在GOAT-Bench Val Unseen上以GPT-4o达到90.6%成功率，并用更小的Qwen2.5-VL-7B仍达88.8%，表明高质量3D语义地图比单纯更换更强基础模型更关键。</td></tr>
<tr><td>2026-06-24</td><td>DSP-SLAM++: A Unified Framework for Multi-Class, High-Fidelity Object SLAM in the Wild<br><a href='http://arxiv.org/pdf/2606.25953'>论文</a></td><td>◆ DSP-SLAM++针对现有目标级SLAM在实时性、多类别支持和高保真建模之间的矛盾，提出了统一的多类别高精度目标SLAM框架。

◆ 该方法在DSP-SLAM基础上引入异步建图流水线，显著缓解建图线程瓶颈，使系统更适合实时运行。

◆ 论文针对单目鱼眼相机与LiDAR组合设计了专门的传感器融合适配，增强了在真实复杂场景中的鲁棒性。

◆ 实验表明，系统可为多类物体生成细粒度、几何完整且语义一致的三维形状。

◆ 相比先进基线，DSP-SLAM++最高可降低70%的目标处理延迟，并在25 Hz多类别数据集上实现稳定实时表现。</td></tr>
<tr><td>2026-06-24</td><td>SA-LIVO: Efficient LiDAR-Inertial-Visual Odometry with Subspace-Aware Degeneracy Handling<br><a href='http://arxiv.org/pdf/2606.25699'>论文</a></td><td>◆提出SA-LIVO，面向LiDAR退化与视觉失效并存的LIVO场景，将方向选择性融合引入紧耦合LiDAR-惯性-视觉里程计。
◆核心创新SAIF对联合LiDAR-视觉信息矩阵做特征分解，并在每个特征方向上用线性钳位软门控，削弱退化方向、完整保留可观方向。
◆系统让视觉信息主要补偿LiDAR欠约束子空间，避免在LiDAR已充分约束方向重复注入信息或在退化时全状态分散补偿。
◆LiDAR与视觉残差在共享线性化点的InEKF中联合优化，且视觉光度雅可比可预组装并跨迭代复用，显著降低计算开销。
◆在29个序列和并发退化场景中，SA-LIVO达到强基线级精度并在对手发散时保持有界漂移，同时CPU实时运行且峰值内存降低3.6–6.3倍。</td></tr>
<tr><td>2026-06-24</td><td>OrthoTrack: Continuous 6-DoF UAV Trajectory Estimation Anchored in Public Orthophotos<br><a href='http://arxiv.org/pdf/2606.25245'>论文</a></td><td>◆提出OrthoTrack，一个无需训练的连续6-DoF无人机轨迹估计系统，仅依赖公开正射影像和地表模型作为地图先验。
◆通过将关键帧与正射影像匹配，并利用地表模型把2D对应提升到公制3D，实现绝对尺度定位。
◆利用光流将地图锚定的对应关系传播到中间帧，从而在无GPS和无后处理对齐的情况下逐帧输出位姿。
◆构建MovingDrone数据集，提供逼真无人机序列、密集6-DoF真值及多时相多模态地理数据。
◆实验表明该方法可在单GPU实时运行，并显著优于包括使用真值尺度和对齐信息的基线，具备跨区域部署能力。</td></tr>
<tr><td>2026-06-23</td><td>Vision-Language Model Reasoning for Contextual Semantic Mapping in Intralogistics<br><a href='http://arxiv.org/pdf/2606.24814'>论文</a></td><td>◆论文提出一种面向仓内物流的上下文语义建图流程，将SLAM几何建图、SAM实例分割、实例聚类与VLM多视角推理结合起来。

◆该方法不仅建模环境几何结构和物体类别，还进一步推断物体的上下文属性，如是否可移动。

◆其创新在于利用零样本、开放词汇的VLM推理，无需任务专门训练或预定义类别即可理解物体属性。

◆通过聚合多视角观测，系统提升了语义分类与可移动性判断的可靠性，分别达到98.93% mIoU和89.17% mAcc。

◆论文还通过组件分析指出，VLM推理是上下文理解瓶颈，实例聚类是全景性能主要限制，为后续改进提供依据。</td></tr>
<tr><td>2026-06-23</td><td>Pocket-SLAM: Rendering-Area-Aware Pruning for Memory-Efficient 3DGS-SLAM<br><a href='http://arxiv.org/pdf/2606.24796'>论文</a> | <a href='https://github.com/UMN-ZhaoLab/Pocket-SLAM.git'>代码</a></td><td>◆提出Pocket-SLAM，面向大规模3DGS-SLAM中高斯点持续累积导致的内存膨胀问题，提升系统可扩展性。
◆核心创新是“渲染区域感知剪枝”，不再仅依赖透明度、梯度等高斯级启发式指标。
◆该方法根据高斯点对有效渲染区域的实际贡献进行选择性删除，更直接地定位并消除内存冗余。
◆在运行时显著降低峰值显存/内存占用，同时保持定位与建图精度基本不受影响。
◆在EuRoC和KITTI数据集上验证，尤其在大规模户外场景中优于现有剪枝方法，实现超过60%内存减少和2倍以上FPS提升。</td></tr>
<tr><td>2026-06-23</td><td>Decentralized Pose Graph Riemannian Optimization for Object-based Multi-Robot SLAM<br><a href='http://arxiv.org/pdf/2606.24489'>论文</a></td><td>◆本文提出面向对象级多机器人SLAM的完全去中心化位姿图黎曼优化框架，可同时估计机器人轨迹与共享持久物体位姿。
◆方法通过一致性机制解耦强耦合的多机器人-物体估计问题，使通信拓扑不必与物理观测关系一致，适应稀疏、间歇和变化网络。
◆论文设计了分布式近似牛顿算法，利用局部二阶信息并直接在SE(d)流形上优化，以保持几何一致性。
◆理论上证明算法收敛到黎曼一阶驻点，并通过局部条件数分析解释二阶近似相较一阶下降的收敛优势。
◆实验表明该方法在公共数据集、大规模仿真和真实多机器人场景中减少迭代与通信开销，同时提升精度、效率、可扩展性和抗通信故障能力。</td></tr>
<tr><td>2026-06-22</td><td>HERCULES: An Open-Source Simulation Framework for Heterogeneous Multi-Robot SLAM, Collaborative Perception, and Exploration<br><a href='http://arxiv.org/pdf/2606.22756'>论文</a> | <a href='https://lunarlab-gatech.github.io/HERCULES-website'>代码</a></td><td>◆ HERCULES提出了一个开源的异构多机器人仿真与数据采集框架，支持UAV与UGV在大规模、照片级真实、动态环境中并发运行。

◆ 它突破了AirSim/Cosys-AirSim的架构限制，引入与UAV接口一致的UGV航点跟踪控制器，并提供跨平台共享的导航、建图、可通行性分析、规划与控制栈。

◆ 框架扩展了传感器能力，加入物理建模的长波红外相机和可配置夜视模式，增强了退化视觉环境下的感知研究能力。

◆ HERCULES提供轻量API、ROS 2封装和严格的多传感器多平台时间同步，并集成行人、交通、野生动物、火灾、洪水等高保真动态要素。

◆ 它支持离线轨迹回放的数据生成模式和在线闭环规划模式，并通过SLAM、协同感知和探索实验验证了其在异构多机器人自主研究中的实用价值。</td></tr>
<tr><td>2026-06-22</td><td>Offline Reinforcement Learning for Warehouse SLAM Throughput Control<br><a href='http://arxiv.org/pdf/2606.23978'>论文</a></td><td>◆提出面向仓库SLAM（扫描/贴标/应用/清单）吞吐控制的离线强化学习框架，用历史日志学习策略，避免在线试错风险。
◆方法可动态推荐吞吐设定，在提升处理能力与维持下游稳定、降低拥堵之间取得平衡。
◆设计了包含历史信息的状态表示、面向延迟影响的动作抽象，以及同时刻画上下游运营指标的奖励函数。
◆框架具有算法无关性，并集成三种先进离线RL算法在大规模仓库脱敏日志上训练。
◆采用回归即时奖励估计、FQE长程评估和Deep Koopman动力学评估等多方法验证，结果显示CQL策略最佳，使系统健康度提升22.97%，平均限流时长降低3.18%。</td></tr>
<tr><td>2026-06-21</td><td>Reference-Free Assessment of Physical Consistency in World Model-based Video Generation<br><a href='http://arxiv.org/pdf/2606.22363'>论文</a></td><td>◆本文提出一种无需参考视频的生成视频物理一致性评估框架，用于衡量世界模型视频生成中的物理保真度。
◆方法结合相对评估与绝对评估，避免依赖昂贵的人类投票或难以获得的真实参考视频。
◆其核心技术利用DROID-SLAM和SEA-RAFT量化几何、运动等物理不一致性，受WorldScore思想启发。
◆实验表明，经相对一致性筛选的视频可使任务成功率提升超过8%，有效缩小仿真到现实的差距。
◆绝对评估还能进行时空定位，直观显示物理伪影出现的时间和位置，增强评估的可解释性。</td></tr>
<tr><td>2026-06-20</td><td>ACEsplat: Accelerated 3D Gaussian Scene Regression via RGB and Poses Only<br><a href='http://arxiv.org/pdf/2606.22091'>论文</a></td><td>◆ ACEsplat提出了一种仅依赖RGB图像和相机位姿的快速逐场景3D Gaussian重建框架，避免了SfM点云、深度图等外部几何先验。

◆ 其核心创新是两阶段流程：先用自监督场景坐标回归模块在数分钟内构建内部几何先验，再用于后续高斯初始化与优化。

◆ 论文设计了轻量级Gaussian初始化头，将SCR特征与坐标先验融合，提升无外部3D信息条件下的3DGS初始化质量。

◆ 实验表明，该方法在Wayspots、Cambridge Landmarks和RealEstate10K等数据集上取得有竞争力的渲染质量，适用于静态视角和稀疏视角新视角合成。

◆ ACEsplat可在单GPU上15到25分钟内完成场景映射与3DGS重建，为机器人和混合现实中的快速现场建图提供了实用方案。</td></tr>
<tr><td>2026-06-19</td><td>Spectral GS-SLAM: Observability-Aware, Degeneracy-Robust Tracking for Real-Time 3D Gaussian Splatting SLAM<br><a href='http://arxiv.org/pdf/2606.21258'>论文</a></td><td>◆提出Spectral GS-SLAM，将ICP跟踪与互补的特征约束结合，面向实时3D Gaussian Splatting SLAM中的退化与弱纹理场景。
◆通过可观测性/谱分析识别ICP优化中的欠约束方向，并自适应补偿信息，缓解几何退化导致的病态和数值不稳定。
◆补偿机制不干扰用于建图的共享高斯表示，在增强跟踪鲁棒性的同时保持3DGS实时建图框架的简洁性。
◆引入高斯感知的平面性加权，利用3D高斯协方差刻画局部几何结构，指导几何与特征信息融合。
◆在TUM RGB-D挑战序列上实现40.14 FPS，并在结构缺失和特征缺失环境中保持稳定跟踪。
◆总体上，该方法在退化场景中保持轨迹完整性，同时在常规场景下维持有竞争力的精度与实时性。</td></tr>
<tr><td>2026-06-19</td><td>Ultra-Fusion: A Resilient Tightly-Coupled Multi-Sensor Fusion SLAM Framework under Sensor Degradation and Spatiotemporal Perturbation for Intelligent Transportation Systems<br><a href='http://arxiv.org/pdf/2606.21223'>论文</a></td><td>◆提出Ultra-Fusion，一个面向智能交通场景的紧耦合多传感器SLAM框架，旨在应对光照差、LiDAR退化、轮滑、GNSS中断等传感器失效问题。
◆设计统一滑动窗口估计器，将异步传感器数据按时间戳排序并转化为可选因子，统一支持WIO、VIO、LIO、LVIO及轮速/GNSS增强。
◆引入可观测性感知初始化机制，可根据场景条件自适应选择更可靠的启动模式，提升系统冷启动鲁棒性。
◆提出因子级可靠性调度，对退化测量进行门控或降权，减少异常传感器对定位结果的破坏。
◆实现在线LiDAR-IMU时空标定，可在运行中修正时间偏移和旋转外参，并通过多数据集与60余种开源SLAM对比验证了跨平台、长时高速和退化场景下的竞争性精度与可用性。</td></tr>
<tr><td>2026-06-18</td><td>A Smart-Scheduled Hybrid (SSH) EKF-FGO State Estimation<br><a href='http://arxiv.org/pdf/2606.16057'>论文</a></td><td>该论文针对状态估计中精度与计算成本的平衡问题，提出一种智能调度混合SSH EKF-FGO框架，作为显式研究优化调度作用的受控测试平台。
◆将优化调度作为独立设计变量进行实验性表征，明确其如何控制中间估计精度与计算成本的权衡。
◆通过固定求解器结构与计算量，结合EKF状态传播与周期性批处理优化，成功剥离并孤立出优化调度变量。
◆基于平面SLAM仿真，揭示了优化调度对优化前漂移、瞬态误差及运行时的强烈影响。
研究发现了能以极小计算成本保留大部分全局优化收益的运行机制，凸显了优化调度在混合状态估计中是未被充分探索却至关重要的因素。</td></tr>
<tr><td>2026-06-18</td><td>A High-accuracy Event-based Underwater SLAM System<br><a href='http://arxiv.org/pdf/2606.18951'>论文</a></td><td>◆提出首个高精度事件相机水下双目SLAM系统，针对水下速度波动、宽基线和重复纹理导致的TS质量下降与匹配失败问题进行系统性解决。
◆设计基于结构张量相干性与梯度的TS结构感知度量，用于量化时间表面中的结构信息密度。
◆将最优TS生成按初始化前后解耦：初始化前用贝叶斯优化预测先验TS，跟踪阶段用异步在线局部搜索实时更新合适TS。
◆引入先验视差保障精确数据关联，并采用“最新观测优先”的三角化机制提升三维点构建稳定性。
◆构建并开源首个高质量真实水下事件数据集UWE，覆盖可变运动、复杂纹理和多类轨迹，实验表明系统精度达到或优于现有事件SLAM方法。</td></tr>
<tr><td>2026-06-18</td><td>Towards 3D karst underwater scene reconstruction from rotating sonar data<br><a href='http://arxiv.org/pdf/2606.20322'>论文</a></td><td>本文面向喀斯特含水层水下探测中声呐稀疏、噪声强且导航漂移严重的问题，提出了一套从旋转声呐数据重建三维水下通道场景的完整流程。
◆ 将连续时间SLAM用于校正水下航迹漂移，提高了声呐剖面在三维空间中的配准精度。
◆ 提出两阶段深度学习表面重建方法，从稀疏噪声声呐观测中恢复更连续的洞穴/管道表面。
◆ 将运动估计校正与学习式几何重建结合，突破传统三维重建方法对精确导航和密集观测的依赖。
◆ 最终生成可沉浸式浏览和导航的三维网格，为水文地质分析和喀斯特管道结构理解提供支持。</td></tr>
<tr><td>2026-06-18</td><td>Gaussian Process Prior Variational Autoencoder for Endoscopic Videos<br><a href='http://arxiv.org/pdf/2606.19908'>论文</a></td><td>◆论文提出GPVAE用于内窥镜视频修复，以时间高斯过程先验替代传统VAE的独立潜变量先验，从而更好利用帧间连续性并支持缺失帧插值。
◆模型结合EndoVAE卷积骨干和GastroNet-5M预训练ViT编码器，增强对内窥镜图像特征的表达能力。
◆为提升可扩展性，论文引入HPA和SPA两种高斯过程近似方法，并用DUCKNet掩膜排除镜面反射污染像素对训练目标的干扰。
◆在C3VDv2数据集上，最佳GPVAE相较匹配VAE平均降低重建RMSE 21.9%，最高降低26.1%。
◆修复结果还提升了视觉里程计和PoseNet轨迹估计表现，平均降低轨迹RMSE 12.7%，同时GP后验提供逐帧不确定性作为恢复置信度信号。</td></tr>
<tr><td>2026-06-18</td><td>MMD-SLAM: Structure-Enhanced Multi-Meta Gaussian Distribution-Guided Visual SLAM<br><a href='http://arxiv.org/pdf/2606.19874'>论文</a></td><td>◆ MMD-SLAM提出一种结构增强的3DGS视觉SLAM框架，利用Atlanta World假设显式引入场景主方向先验，提升地图一致性与渲染质量。
◆ 其点线融合位姿优化策略将3D线段纳入跟踪过程，为相机位姿估计提供更强几何约束，增强复杂场景下的鲁棒性。
◆ 论文设计了Multi-Meta Gaussian表示，用多个带主方向的元高斯编码结构信息，使高斯建图更贴合真实建筑几何。
◆ 提出的高斯演化策略可根据场景几何自适应调整，并在全局优化中融入结构线索，减少地图漂移和不一致。
◆ 实验表明，MMD-SLAM在跟踪精度和建图质量上达到领先水平，相比MonoGS在ScanNet上ATE RMSE降低48.56%，在Replica上PSNR提升5.71%。</td></tr>
<tr><td>2026-06-18</td><td>UNSEEN: Uncertainty-aware Navigation via Sparse Estimation in Unknown Environments<br><a href='http://arxiv.org/pdf/2606.20755'>论文</a></td><td>◆提出UNSEEN，一个仅依赖前视相机的统一不确定性感知与感知感知导航框架，面向未知环境中的轻量级机器人导航。
◆核心创新是显式耦合定位、建图与规划，而非采用松散模块化流水线，从而让运动决策直接考虑感知质量。
◆系统以6Hz估计稀疏地图、机器人位姿及其不确定性，并将这些不确定性在导航栈中一致传播。
◆规划器采用滚动时域方式，同时优化任务推进和状态估计精度，使机器人主动选择更有利于定位与建图的轨迹。
◆实验表明，UNSEEN-SLAM将绝对平移误差降低9.8%，UNSEEN-Plan最高提升45%估计精度，并在真实未知环境中实现100%任务成功率。</td></tr>
<tr><td>2026-06-17</td><td>Sensor Configuration Matters: A Systematic Evaluation of Multimodal SLAM on Quadruped Robots<br><a href='http://arxiv.org/pdf/2606.19067'>论文</a></td><td>◆论文针对四足机器人腿式运动带来的冲击、振动和快速旋转问题，系统研究了不同传感器硬件配置对多模态SLAM性能的影响。

◆作者基于ANYmal D四足机器人采集的GrandTour数据集，对视觉、视觉惯性和LiDAR-视觉-惯性SLAM方法进行了统一评测。

◆研究定量比较了相机模态、快门类型和不同等级IMU在定位精度、鲁棒性和计算资源消耗上的权衡。

◆实验发现，双目配置整体优于单目和RGB-D，全局快门相比卷帘快门能显著减少运动导致的跟踪失败。

◆一个重要结论是，在剧烈腿式运动下，常规惯性融合反而可能削弱以视觉为主的SLAM系统性能，为四足机器人传感器载荷设计提供了实用指南。</td></tr>
<tr><td>2026-06-17</td><td>C-ARC: Continuous-Adaptive Range Clustering for Non-Repetitive LiDAR Sensors<br><a href='http://arxiv.org/pdf/2606.18948'>论文</a></td><td>◆ C-ARC面向非重复式Risley棱镜LiDAR，解决其无规则扫描线、无明确帧边界和点云分布不均导致传统聚类方法失效的问题。  
◆ 提出连续自适应距离聚类框架，在滑动窗口中维护持久化双图结构，将高频点插入与按需簇提取解耦，适配SLAM和目标跟踪等实时任务。  
◆ 设计自适应距离网格分辨率机制，通过初始化阶段的指数控制循环自动校准网格尺寸，无需预知扫描模式。  
◆ 该机制在稀疏性与网格碰撞之间取得平衡，并可提升现有网格聚类方法在非重复LiDAR数据上的聚类质量。  
◆ 系统以开源单线程C++17库实现，可在普通硬件上对Livox Mid-360实现20 Hz实时聚类，同时评估指出强集中扫描传感器中无界单元占用是主要限制。</td></tr>
<tr><td>2026-06-16</td><td>RICH-SLAM: Radar SLAM with Incremental and Continuous Hilbert Mapping<br><a href='http://arxiv.org/pdf/2606.17534'>论文</a></td><td>◆ RICH-SLAM提出了一种面向雷达传感器的SLAM框架，旨在解决雷达数据稀疏、噪声大而难以构建稠密一致地图的问题。
◆ 其后端采用Rao-Blackwellized粒子滤波结构，用粒子滤波估计机器人位姿，并用卡尔曼滤波增量更新地图参数。
◆ 论文引入基于Hilbert空间低秩高斯过程的增量映射方法，可从稀疏雷达观测中生成连续、稠密且带不确定性的占据地图。
◆ 作者设计了后验感知的粒子权重计算机制，利用地图参数的完整后验分布进行似然评估，从而提升定位与建图的鲁棒性。
◆ 在自采数据和公开ColoRadar数据集上的实验表明，RICH-SLAM能有效构建连续雷达占据地图，并支持移动机器人的不确定性感知规划。</td></tr>
<tr><td>2026-06-15</td><td>CrossMaps: Confidence-Aware Open-Vocabulary Semantic Mapping for Rover Navigation<br><a href='http://arxiv.org/pdf/2606.16935'>论文</a></td><td>本文提出了CrossMaps，一个用于探测车导航的实时置信度感知开放词汇语义建图管线，能够基于RGB-D数据构建支持自然语言查询的地图。
◆创新性地将多尺度CLIP嵌入与置信度感知融合相结合，利用几何、语义和时间置信度线索来有效聚合噪声视觉观测。
◆提出了双记忆架构，短期记忆处理动态噪声观测，长期记忆则将高置信度且连贯的单元提升为持久语义地标。
◆实现了在Jetson Orin边缘平台与SLAM协同的实时部署方案，生成可查询语义热图引导导航。
该系统有效解决了部分可观测环境下感知与导航的耦合问题，提升了探测车导航的可靠性。</td></tr>
<tr><td>2026-06-15</td><td>SGM-SLAM: Scene Graph Matching for Data-Efficient Distributed SLAM<br><a href='http://arxiv.org/pdf/2606.16881'>论文</a></td><td>本文提出了一种面向多机器人团队的数据高效分布式SLAM框架，利用场景图匹配来识别机器人间的测量约束。
◆首次仅利用对象标签和质心进行场景图匹配以识别机器人间约束，区别于以往依赖特征级匹配的方法。
◆创新性地通过融合RGB-LiDAR点云构建场景图，生成语义分割点云层与离散有界对象层伴随机器人轨迹。
◆通过协作交换与匹配邻居机器人的对象数据完成场景图匹配，并采用多步数据交换与优化过程最大化通信效率。
该框架在室内外真实腿式机器人及仿真数据集上均验证了其有效性与高效性。</td></tr>
<tr><td>2026-06-15</td><td>MVOFormer: Flow-Semantic Transformer for Robust Monocular Visual Odometry<br><a href='http://arxiv.org/pdf/2606.16474'>论文</a></td><td>本文提出了一种用于鲁棒单目视觉里程计的新型Transformer框架MVOFormer，解决了现有学习方法缺乏可解释互补特征和架构复杂的问题。
◆提出流语义双分支编码器，协同融合密集几何运动线索与以物体为中心的语义先验，显式区分静态结构与动态干扰物。
◆设计迭代多模态解码器，融合上述表征实现由粗到细的位姿细化，并动态抑制对不可靠区域的注意力。
该框架无需任何目标域微调，即可在多种基准测试中实现卓越的零样本泛化能力与鲁棒性。
在TartanAir等四个多样化数据集上的广泛评估表明，MVOFormer显著优于以往基于学习的帧到帧方法。</td></tr>
<tr><td>2026-06-13</td><td>FD-SLAM: Fast Dense Radar-Inertial SLAM with Frequency-Domain Loop Closure and Pose Graph Optimization<br><a href='http://arxiv.org/pdf/2606.15491'>论文</a></td><td>◆ 提出FD-SLAM，一种快速稠密雷达-惯性SLAM系统，在稠密雷达-惯性里程计基础上加入频域回环检测与位姿图优化，面向视觉退化环境下的地面车辆定位建图。

◆ 设计了紧凑的频域极坐标描述子，保留扫描雷达数据的类图像结构，用于高效检索长轨迹中的回环候选，提升雷达测量匹配的可靠性。

◆ 构建多阶段回环验证流程，包括时间滤波、相位相关筛选、扫描对齐相似度评估和几何一致性检查，从而降低雷达噪声和误匹配带来的影响。

◆ 将验证后的回环作为非连续约束加入SE(2)位姿图，并与雷达-惯性里程计因子联合优化，有效减小累计漂移。

◆ 在公开数据集上使用KITTI指标评估，结果表明FD-SLAM相比FD-RIO基线有明显提升，并在多条驾驶轨迹上展现出具有竞争力的精度，尤其是旋转精度表现较好。

◆ 运行时间分析显示，其雷达-惯性前端可在纯CPU环境下超过雷达采样率运行，回环检测和图优化也适合并行后台执行，具备较好的实时应用潜力。</td></tr>
<tr><td>2026-06-10</td><td>Triangle Splatting SLAM<br><a href='http://arxiv.org/pdf/2605.31419'>论文</a></td><td>本文提出了一种使用可微三角形作为三维地图表示的稠密RGB-D SLAM系统。与3D高斯溅射不同，三角形天然兼容传统渲染硬件及需要显式几何的下游任务。
◆首次提出基于三角形溅射的稠密SLAM系统，通过对无结构三角形汤进行在线可微渲染来联合执行追踪与建图。
◆利用受限德劳内三角剖分将地图在线转换为连通网格，赋予了系统在线网格变形和碰撞检查的新能力。
在Replica和TUM-RGBD数据集上，该系统在三维几何重建上优于基线，追踪精度与之持平，并实现了在线场景编辑。</td></tr>
<tr><td>2026-06-09</td><td>Information-Preserving Continuous Occupancy Mapping with Variance-Weighted Submap Joining<br><a href='http://arxiv.org/pdf/2606.10442'>论文</a></td><td>本文提出了首个连续概率子图拼接框架，在隐对数几率空间联合优化子图位姿和全局占据率场，解决了离散网格方法梯度不平滑及忽略估计不确定性的问题。
◆提出信息保留的稀疏贝叶斯公式，将原始观测压缩为充分统计量对数几率元组，有效保留了原始观测的后验信息。
◆推导出占据率映射的闭式预测均值和方差估计，直接实现了具有解析雅可比矩阵的子图拼接公式。
◆在位姿收敛时可直接获得闭式最优全局地图，提高了地图优化的准确性与效率。
实验表明，该方法比网格方法具有更高的位姿精度和全局一致性，同时比现有连续方法生成的地图更紧凑且不确定性校准更好。</td></tr>
<tr><td>2026-06-08</td><td>Efficient Minimal Solvers for Visual-Inertial Relative Pose Estimation in Multi-Camera Systems<br><a href='http://arxiv.org/pdf/2606.09477'>论文</a></td><td>本文针对多相机系统相对位姿估计计算复杂度高和依赖过多点对应的问题，提出了两种基于新型参数化的高效最小求解器。
◆利用惯性测量单元提供的垂直方向先验设计第一种求解器。
◆利用惯性测量单元提供的旋转轴方向先验设计第二种求解器。
◆仅需四个点对应即可完成估计，并将问题降阶为求解单变量六次多项式，显著优于现有方法的八次多项式。
上述创新大幅降低了计算复杂度与数据需求，使其在RANSAC框架中表现优异，非常适合视觉里程计应用。
在合成数据和KITTI数据集上的实验验证了该方法具备卓越的计算效率与极具竞争力的精度。</td></tr>
<tr><td>2026-06-06</td><td>G2G: Exploiting Intra-Group Geometry for Inter-Group Pose Estimation<br><a href='http://arxiv.org/pdf/2606.08284'>论文</a> | <a href='https://github.com/WeiYuFei0217/G2G'>代码</a></td><td>本文提出G2G方法解决跨图像组的6自由度相对位姿估计问题，弥补了现有模型将视图视为无结构集合而忽略跨组推理的不足。该方法在冻结视觉基础模型的同时，以极低的参数量和纯位姿监督实现了跨越多个数据集的最先进精度。
◆设计三个轻量级模块，包括感知重采样器、含合并自注意力的跨组桥接和多帧位姿头，有效建立了组间联系。
◆保持预训练基础模型完全冻结，仅新增约3200万可训练参数，占比不足6%，极大降低了计算与存储开销。
◆仅需相对位姿进行监督，无需额外复杂监督，并在室内外仿真、跨季节实景及零样本迁移等四项测试中超越了全量监督重训的基线模型。</td></tr>
<tr><td>2026-06-06</td><td>X-OP: Cross-Morphology Whole-Body Teleoperation via MPC Retargeting<br><a href='http://arxiv.org/pdf/2606.07934'>论文</a></td><td>本文提出了一种由单个XR设备驱动的分层全身遥操作框架，解决了现有方法成本高、需重训策略及忽略动态可行性等问题，实现了跨机器人形态的泛化。
◆提出基于模型预测控制的运动重定向器，联合优化操作意图对齐与机器人动态可行性，为底层控制器生成最优指令。
◆引入状态同步机制与基于SLAM的全局位姿反馈，前者在每个MPC步长重置仿真器状态以应对噪声与接触敏感性，后者缓解长期漂移，确保鲁棒的在线执行。
仿真实验表明该方法表现优异，使人形机器人完成时间降超30%、功耗降20%，移动机械臂实现零碰撞。
真实世界实验进一步验证了其有效性与灵活性，该即插即用框架支持跨平台部署及用户偏好定制，提供了可扩展的通用解决方案。</td></tr>
<tr><td>2026-06-04</td><td>RadiusFPS: Efficient Farthest Point Sampling on CPUs and GPUs via Spherical Voxel Pruning<br><a href='http://arxiv.org/pdf/2606.06255'>论文</a></td><td>针对最远点采样在处理大规模点云时时间复杂度高导致实时机器人感知受限的问题，本文提出了基于球面体素剪枝的FPS加速框架RadiusFPS。
◆通过球面体素索引推导保守的几何边界，在每次迭代中剪枝冗余的距离计算。
◆引入坐标级点跳过测试，进一步消除残差更新。
◆提出RadiusFPS-G，一种warp级GPU实现，将体素选择、剪枝和距离更新融合到内存合并的内核中，避免高开销的全局内存往返。
实验表明，RadiusFPS-G相比GPU版FPS实现高达2.5倍加速，在保持精度的同时比QuickFPS节省近一半显存且速度更优。
结合FastPoint采样器后，该流水线实现了最快的端到端推理，使高质量FPS在资源受限的机器人视觉中变得实用。</td></tr>
<tr><td>2026-06-04</td><td>Breaking Time: A Fully Gaussian Framework for Distributed and Continuous-Time SLAM<br><a href='http://arxiv.org/pdf/2606.06250'>论文</a></td><td>本文提出了G-solver，一个全高斯且分布式的连续时间SLAM框架，旨在解决异构异步传感器的轨迹估计问题。
◆结合高斯置信传播与高斯过程运动先验，实现了连续时间轨迹的分布式估计。
◆利用高斯过程模型提供轨迹的概率表示，支持一致性插值及数据驱动超参数的使用。
◆采用高斯置信传播的消息传递机制，提升了求解器的可扩展性并适用于去中心化场景。
◆该框架能自然扩展至多相机场景，免去了繁琐的专门同步与工程处理。
实验表明该方法在卷帘快门和分布式多相机优化中估计准确稳定，运行效率与现有方法相当并已开源。</td></tr>
<tr><td>2026-06-04</td><td>Towards Realistic 3D Sonar Simulation<br><a href='http://arxiv.org/pdf/2606.06130'>论文</a></td><td>◆论文指出现有3D声呐仿真过度依赖几何渲染，类似“水下LiDAR”，难以刻画折射、多路径干涉和相位相关成像等关键声学现象。

◆作者提出一种模块化真实感3D声呐仿真架构，将GPU加速图形引擎与物理声学传播模型结合。

◆论文在NVIDIA Isaac Sim中实现了参考Water Linked 3D-15传感器的体积式3D声呐模型，并接入完整水下仿真框架。

◆系统通过硬件在环实验验证，使用Jetson Orin Nano运行改造后的FastLIO2 SLAM，并融合合成声呐、DVL、IMU和压力数据。

◆论文还将仿真结果与港口钢板桩检测的真实数据进行定性对比，分析当前sim-to-real差距，并为面向真实声学机制的体积感知仿真提出发展路线。</td></tr>
<tr><td>2026-06-03</td><td>Teaching Robots to Say &#x27;I Don&#x27;t Know&#x27; : SENTINEL for Uncertainty-Aware SLAM<br><a href='http://arxiv.org/pdf/2606.04853'>论文</a></td><td>本文提出SENTINEL框架，解决了低成本2D激光雷达缺乏强度通道而无法诊断测量失效的问题。
◆该框架免训练且免标签，创新性地结合基于几何的扫描统计量与激光雷达和RGB-D相机的跨模态深度一致性，计算零到一的逐扫描可靠性评分。
◆当评分低于阈值时，系统主动拒绝损坏的扫描数据并退回校准的轮式里程计，有效防止无声的SLAM损坏。
◆针对仿真中缺失的透明和反光等失效模式，该研究完全在真实硬件上验证，生成的空间可靠性图谱能清晰分离正常与失效情况。
这使得机器人具备不确定性感知能力，能够识别并拒绝噪声区域，显著提升了低端平台SLAM的鲁棒性。</td></tr>
<tr><td>2026-06-03</td><td>BPDA-GMM: Bayesian Probabilistic Data Association via Gaussian Mixture Models for Semantic SLAM<br><a href='http://arxiv.org/pdf/2606.04618'>论文</a> | <a href='https://github.com/thanhnguyencanh/BPDA-SLAM'>代码</a></td><td>本文提出了一种用于语义SLAM的在线贝叶斯概率数据关联框架BPDA-GMM，解决了现有方法假设固定路标、重复计算权重或依赖人工调参的局限。
◆引入基于狄利克雷过程先验的中国餐馆过程关联模型，自动分配新旧路标概率，无需人工调整零假设权重。
◆结合语义几何门控与CRP权重计算关联概率，以闭式更新语义高斯路标，构建高斯混合模型并提取主成分作为最大混合因子传给后端。
◆当关联权重模糊时，引入由模糊性触发的alpha散度回火步骤以增强路标区分能力。
◆设计解耦后端，将语义因子的位姿雅可比矩阵置零，使噪声检测能优化路标而不直接扰动轨迹。
实验证明该方法在轨迹精度、语义建图质量及鲁棒性上均优于现有基线。</td></tr>
<tr><td>2026-06-02</td><td>PixVOD: Pixel-Distributed Direct Visual Odometry and Depth Estimation<br><a href='http://arxiv.org/pdf/2606.03989'>论文</a></td><td>PixVOD 提出了一种面向焦平面传感器-处理器(focal-plane sensor-processors)的全并行视觉里程计与深度估计方法,将传统集中式的视觉计算下沉到每个像素内部完成,从而减少传感器原始数据的冗余传输,并为上层视觉任务提供更高层次的语义信号。该方法基于高斯置信传播(GBP)使各像素处理单元通过局部消息交换达成对相机运动的共识,并结合逐像素光度观测与表面法向先验推断深度。为保证优化过程中的几何稳定性,作者引入了一种类关键帧的锚定机制以调节有效基线长度,使运动与深度更新保持一致性。在真实数据集上的实验验证了该像素级分布式里程计与深度估计方案在传感器端的可行性。

◆ 首次提出在焦平面传感器-处理器上完全像素级并行执行直接视觉里程计与深度估计的框架。
◆ 利用高斯置信传播(GBP)实现像素间的局部消息传递,从分布式光度观测中协同求解相机运动并达成共识。
◆ 将每像素光度观测与表面法向先验结合,实现稠密的逐像素深度推断。
◆ 设计了类关键帧的锚定机制,有效调节帧间基线,提升分布式优化中的几何稳定性与收敛一致性。
◆ 在真实数据集上验证了片上像素分布式里程计与深度估计的可行性,为新型智能视觉传感器提供了算法范式。</td></tr>
<tr><td>2026-06-02</td><td>Autonomous Navigation System for Library Service Robot Based on Unitree Go2 Edu<br><a href='http://arxiv.org/pdf/2606.03340'>论文</a></td><td>本文基于Unitree Go2 Edu四足机器人，提出了一套适用于图书馆场景的ROS 2自主导航系统。系统集成了4D激光雷达、深度相机和IMU，利用RTAB-Map实现视觉与激光融合SLAM，结合AMCL和EKF定位，并通过Nav2栈实现路径规划与局部避障。
◆针对图书馆真实部署中的地面过渡、临时杂物和部分受阻通道等移动不连续性问题进行优化，克服了低底盘轮式平台的局限。
◆将四足机器人引入图书馆狭窄通道与动态人群环境，并通过多传感器融合方案提升了复杂场景下的导航鲁棒性。
◆在真实图书馆中验证了系统的卓越性能，静态、低动态和高动态场景下导航成功率分别达100%、96%和88%，建图平均度量误差仅3.7厘米。</td></tr>
<tr><td>2026-06-01</td><td>Embedding Semantic Risk into Distance Fields and CBFs for Online Monocular Safe Control<br><a href='http://arxiv.org/pdf/2606.01605'>论文</a></td><td>本文提出一种在线单目感知至控制框架，将语义风险嵌入基于控制障碍函数的安全导航距离场中，克服了现有方法未在空间表征中编码风险的局限。
◆提出将语义信息直接嵌入欧几里得符号距离场，在控制优化前编码风险，使高风险物体在安全场中扩展更大的空间影响，且不损失运行时查询效率。
◆结合基础模型SLAM前端与逐帧语义分割，从单目RGB视频在线重建并融合密集的三维几何语义表征。
◆在距离场计算前对安全相关区域施加类别相关的膨胀，并通过类别相关增益进一步调节CBF控制器的响应。
仿真与硬件实验验证了该框架能在10至20赫兹下在线运行，并在遥操作与自主导航中实现语义感知的安全行为。</td></tr>
<tr><td>2026-05-31</td><td>One Channel to Rule Them All: Rethinking Input Representation for Visual Place Recognition<br><a href='http://arxiv.org/pdf/2606.00936'>论文</a></td><td>本文挑战了视觉地点识别中必须依赖RGB输入的固有假设，系统性地探究了色彩信息在真实世界外观变化下的实际作用。
◆发现灰度图像在一般条件下性能与RGB持平，在严重外观变化下因避免了色彩干扰而优于RGB，颜色仅在具备持久区分度线索时才有增益。
◆验证了全灰度训练的模型能取得更高的Recall@1，且参数量减少60%的轻量级灰度变体即可超越较重的RGB模型。
◆证明了灰度输入在节省存储空间、降低带宽消耗以及适配资源受限系统方面具有显著的实际优势。
研究最终得出结论，对于面临光照和季节等剧烈变化的VPR任务，色彩贡献极小，单通道灰度足以实现可靠的地点识别。</td></tr>
<tr><td>2026-05-30</td><td>SuperMemory-VQA: An Egocentric Visual Question-Answering Benchmark for Long-Horizon Memory<br><a href='http://arxiv.org/pdf/2606.00825'>论文</a></td><td>本文提出了SuperMemory-VQA，一个针对长期自我中心记忆任务的视觉问答数据集，旨在弥补现有数据集仅关注短视频理解而忽视真实人类记忆需求的不足。
◆构建了包含52.9小时多模态数据及4853对人工验证问答的大规模基准，全面涵盖物体位置、意图回忆及时间线重建等六类真实记忆需求。
◆创新性地引入带有明确无法回答选项的多项选择题格式，以严格测试模型在证据不足时的抗幻觉鲁棒性。
◆通过对前沿大模型和智能体框架的基准测试，揭示了现有系统在真实记忆任务上的不可靠性，指明需开发仅在证据充分时才作答的接地架构。
参与者调查进一步验证了该基准问题设计的现实性与实用性。</td></tr>
<tr><td>2026-05-30</td><td>Dynamic Resilient Spatio-Semantic Memory with Hybrid Localization for Mobile Manipulation<br><a href='http://arxiv.org/pdf/2606.00576'>论文</a></td><td>本文提出了DREAM框架，一种无需预建图的在线移动操作框架，解决了动态室内环境中场景信息易过期或不对齐的问题。
◆构建基于多传感器融合SLAM的在线时空语义体素记忆，实现几何一致与语义可查的场景表征。
◆提出位姿图感知的冗余感知记忆修剪方法，在位姿修正后动态更新历史观测，并保持长时序记忆的计算有界。
◆设计结合语言条件3D检索、开放词汇检测及多模态大模型语义验证的混合目标定位与重获机制。
实验表明，该框架将长时序任务成功率提升至55%-70%，并维持了极低的内存占用与更新延迟。</td></tr>
<tr><td>2026-05-29</td><td>ScaRF-SLAM: Scale-Consistent Reconstruction with Feed-Forward Models and Classical Visual SLAM<br><a href='http://arxiv.org/pdf/2606.00307'>论文</a></td><td>本文提出ScaRF-SLAM,一种将经典基于特征的视觉SLAM与几何基础模型(GFM)解耦融合的框架,旨在解决直接使用GFM预测进行位姿跟踪时因模型不确定性导致的精度问题。该方法利用经典SLAM实现鲁棒低延迟的位姿跟踪,而将GFM专门用于稠密建图,从而避免GFM预测误差传播到位姿估计中,同时对重建施加几何约束。系统通过多关键帧构建子图,采用轻量级的帧与子图尺度优化保证尺度一致性,并支持在线更新以反映SLAM轨迹的修正。实验表明,该方法在建筑尺度数据集上每10米误差约2厘米,在大规模户外场景中每30米误差约10厘米,重建精度较现有方法提升10%-20%。

核心创新点如下:

◆ 提出跟踪与建图解耦的架构,经典特征SLAM负责位姿估计,GFM专注稠密重建,避免GFM预测误差对位姿的负面影响。

◆ 设计基于帧和子图的轻量级尺度优化机制,解决GFM预测中跨帧深度尺度不一致的问题,保证全局几何一致性。

◆ 采用基于投影的子图内点云融合,并支持在线更新子图以同步SLAM轨迹的回环修正,实现可扩展的稠密重建。

◆ 构建了一个富含回环、建筑级室内数据集,提供精确传感器轨迹与LiDAR真值,为稠密SLAM评测提供新基准。

◆ 在建筑级与大规模室外场景中均验证了优越的轨迹精度和重建精度,展现出良好的可扩展性与实用性。</td></tr>
<tr><td>2026-05-29</td><td>Geodesic Flow Matching for Denoising High-Dimensional Structured Representations<br><a href='http://arxiv.org/pdf/2606.00248'>论文</a> | <a href='https://github.com/kremHabashy/CleanupSSP'>代码</a></td><td>本文针对空间语义指针在连续环面流形上的去噪问题，指出标准流匹配方法基于欧几里得几何假设会导致线性插值破坏流形结构，进而损害解码所需的相位和幅度信息。
◆提出测地线流匹配方法，将黎曼传输动力学引入去噪过程，严格将去噪流约束在SSP环面流形上。
◆设计了流形感知的信号清理机制，有效避免了传统欧式插值对高维分布式表征内部结构的破坏。
该方法在脉冲神经SLAM系统中得到验证，证明其能够通过流形清理稳定路径积分以抵抗漂移。
实验表明，与竞争基线相比，该方法使跟踪误差降低了百分之七十二，同时神经效率提升了百分之四十。</td></tr>
<tr><td>2026-05-28</td><td>Exploiting Chordal Sparsity for Globally Optimal Estimation with Factor Graphs<br><a href='http://arxiv.org/pdf/2605.30617'>论文</a> | <a href='https://github.com/borglab/gtsam'>代码</a></td><td>该论文针对机器人状态估计中因子图局部求解器易陷入局部最优，而现有凸松弛技术构建复杂且计算成本高的问题提出了新方法。
◆在GTSAM框架内创建了一种新流程，能够针对包含常见因子和变量类型的任意因子图，自动构建凸半定规划松弛问题。
◆利用GTSAM原生的贝叶斯树构造来分解半定规划问题，通过挖掘弦稀疏性显著提升了求解器的计算速度。
论文通过三维位姿图SLAM和二维定位两个案例研究，验证了该全局估计器相较于标准局部求解器在扩展性上的优势。
相关软件框架已在GitHub开源。</td></tr>
<tr><td>2026-05-28</td><td>CoMo3R-SLAM: Collaborative Monocular Dense SLAM with Learned 3D Reconstruction Priors for Outdoor Multi-Agent Systems<br><a href='http://arxiv.org/pdf/2605.30488'>论文</a></td><td>论文提出CoMo3R-SLAM，这是首个针对室外多智能体系统的协作单目密集RGB SLAM系统，解决了传统方法依赖深度传感器以及室外单目SLAM面临尺度歧义与数据关联不可靠的难题。
◆引入学习到的前馈三维重建先验，设计了先验引导的前端，实现单目相机的实时跟踪与局部密集融合。
◆提出基于协调器的密集点图匹配机制，实现了跨智能体的鲁棒验证与闭式Sim(3)规范同步。
◆采用GPU加速的全局光束法平差并结合段级深度优化，从而生成全局一致的度量地图。
该系统无需深度传感器与参数化内参，仅依赖单目RGB即可输出鲁棒约束，在多数据集上精度超越或媲美最先进的RGB-D方法，且能以8FPS实现在线运行。</td></tr>
<tr><td>2026-05-27</td><td>PRISM-SLAM: Probabilistic Ray-Grounded Inference for Scale-aware Metric SLAM<br><a href='http://arxiv.org/pdf/2605.19257'>论文</a> | <a href='https://prismslam-cmd.github.io/prismslam_pr/'>代码</a></td><td>针对单目SLAM的尺度模糊与动态环境跟踪失败问题，本文提出PRISM-SLAM框架，通过将视觉基础模型先验严谨集成到贝叶斯因子图中，实现了尺度感知且度量一致的实时定位与建图。
◆引入普吕克光线距离因子，在全局度量坐标系中锚定单目观测，使度量尺度具备Fisher可辨识性，从数学上根本解决了尺度漂移问题。
◆提出动态场景不确定性门控机制，利用时间深度一致性推导认知不确定性代理，通过概率软门控降低动态干扰物权重，避免了传统语义分割的高昂计算开销。
系统采用多进程架构异步处理基础模型推理与几何跟踪，仅依赖RGB输入即可实现30帧每秒的实时度量输出。
实验表明其度量绝对轨迹误差几乎等同于无尺度对齐误差，无需任何事后尺度校正即可生成可直接部署的度量轨迹。</td></tr>
<tr><td>2026-05-27</td><td>Provably Guaranteed Polytopic Uncertainty Quantification for SLAM<br><a href='http://arxiv.org/pdf/2605.28172'>论文</a> | <a href='https://github.com/LIAS-CUHKSZ/Polytopic-SLAM-Uncertainty-Quantification'>代码</a></td><td>本文提出了针对3D-3D基于地标的SLAM的可证明保证的不确定性量化算法，解决了现有方法缺乏形式化保证或仅关注位姿估计的局限。该算法包含前向UQ、后向UQ和位姿复合三个模块，能生成经过认证的不确定性集合。
◆提供确定性保证机制，当输入边界确定时，输出集合可证明包含真实的位姿和地标。
◆采用多面体表示不确定性集合，实现了计算可处理性以及对位姿不确定性的统一处理。
◆结合保形预测技术从数据中校准测量不确定性，在保持规定概率的同时显著提升了算法的实用性。</td></tr>
<tr><td>2026-05-27</td><td>SAFEVPR: Patch-Based Conformal Verification for Safe Cross-Condition Sequence Visual Place Recognition<br><a href='http://arxiv.org/pdf/2605.28048'>论文</a> | <a href='https://github.com/Hasar12139/SafeVPR'>代码</a></td><td>本文提出了SAFEVPR，一种用于跨条件序列视觉位置识别的非训练式验证与校准流水线，解决了传统保形预测在跨条件部署下因可交换性被破坏而失效的问题。
◆采用基于冻结DINOv2 ViT特征的互近邻图像块匹配分数，替代标准骨干网络的余弦相似度。
◆采用Mondrian保形Learn-Then-Test校准替代平坦校准，在不同分数区间拟合独立的Bonferroni校正阈值。
该方法在23个跨条件实验设置中均实现经验有效，目标错误发现率为0.10时平均FDR仅0.014且真阳性率达0.75。
研究表明仅靠高区分度不足以保证保形有效性，且本方法能在无纹理重复场景中安全放弃不可靠匹配。</td></tr>
<tr><td>2026-05-27</td><td>Con-DSO: Learning Short-Horizon Consistency Priors for RGB-D Direct Sparse Odometry<br><a href='http://arxiv.org/pdf/2605.27952'>论文</a></td><td>针对RGB-D直接法视觉里程计在动态物体、遮挡和光照变化等复杂环境下因一致性假设失效导致性能下降的问题，本文提出了Con-DSO框架。
◆提出一致性感知的里程计框架，通过时间相邻的RGB-D帧对预测稠密的光度与深度几何一致性不确定性，将一致性破坏表征为像素级不确定性。
◆利用光流引导的光度误差和投影深度一致性误差训练网络，并将成对不确定性预测转换为基于关键帧追踪的宿主端质量先验。
◆在位姿估计阶段通过质量感知的支撑像素选择和解耦的光度几何加权来应用该先验，实现对不可靠观测的连续衰减而非硬性拒绝或阈值门控。
实验表明该方法在五个公开基准上显著超越基线，在多个数据集上绝对轨迹误差降低了20%至80%。</td></tr>
<tr><td>2026-05-26</td><td>Gaussian Process-Based Extended Object Estimation for 6G ISAC at Millimeter-Wave Frequencies<br><a href='http://arxiv.org/pdf/2605.26915'>论文</a></td><td>本文提出了一种基于高斯过程的扩展目标估计方法，用于6G毫米波通感一体化场景。
◆突破了传统点散射体假设的限制，利用高斯过程实现了对扩展目标的更优估计。
◆结合符合5G新空口标准的双基地感知实际测量平台，验证了该方法在毫米波频段的实用性。
◆证明了通信网络能力增强与双基地感知及高斯过程估计相结合，可有效提升未来无线系统的环境感知能力。
研究结果表明，高斯过程在毫米波建图和同步定位与建图场景中均能有效完成扩展目标估计。</td></tr>
<tr><td>2026-05-26</td><td>Trinity: Unifying Class-Agnostic Terrain and Semantic Segmentation for Unstructured Outdoor Environments by Leveraging Synthetic Data<br><a href='http://arxiv.org/pdf/2605.27644'>论文</a></td><td>该论文的核心贡献在于提出了Trinity，一种基于Transformer架构的统一网络，能够同时进行类别特定的语义分割和类无关的地形分割。地形分割仅依赖视觉外观，无需预定义语义标签或机器人特定的可通过性分数，从而学习到机器人无关的视觉地形先验，便于迁移至不同的下游任务。为支撑大规模训练，论文扩展了OAISYS模拟器并引入合成数据集RUGDSynth，同时构建了真实场景数据集EXTerra，包含类特定和类无关两种标注。实验验证了联合分割方法在复杂户外环境中的可行性。

◆ 首次提出在单一网络内联合执行类特定语义分割与类无关地形分割，打破传统方法对机器人依赖或预定义类别的限制。  
◆ 学习机器人无关的视觉地形先验，可灵活结合机器人自身经验用于可通过性估计、视觉里程计等任务，提升跨平台迁移能力。  
◆ 构建了大规模合成数据集RUGDSynth和真实数据集EXTerra，填补了类无关地形标注数据的空白，并开源代码与数据集以促进研究。</td></tr>
<tr><td>2026-05-25</td><td>G-DRAGON: Geospatial Reasoning and Dynamic Planning for Retrieval-Augmented Outdoor Navigation<br><a href='http://arxiv.org/pdf/2605.25646'>论文</a></td><td>本文提出了G-DRAGON框架，这是一种用于户外开放世界导航的检索增强系统，有效解决了长距离全局规划与精细最后一公里探索的双重挑战。
◆提出了基于轻量级大语言模型的生成式检索方法，将自然语言指令映射到本地OSM实体，避免了云端大模型的事实幻觉并生成准确的全局坐标。
◆设计了高级规划模块，成功将全局拓扑路线与SLAM系统桥接，把地理空间路径点投影到机器人的可导航坐标系中。
◆针对最后一公里探索，结合前沿探索与开放集语义体素建图技术，实现了对开放词汇目标的精准定位。
实验证明该框架在仿真中超越了现有基线，并在真实世界无人地面车辆上成功完成了长达500米的行人搜索任务。</td></tr>
<tr><td>2026-05-24</td><td>FusionCore: A 23-State Unscented Kalman Filter for IMU, Wheel Encoder, GPS, and Visual SLAM Fusion in ROS 2<br><a href='http://arxiv.org/pdf/2605.25239'>论文</a> | <a href='https://github.com/manankharwar/fusioncore'>代码</a></td><td>本文提出了FusionCore，这是一个开源的ROS 2传感器融合包，利用23状态无迹卡尔曼滤波器将IMU、轮式编码器、GPS和视觉SLAM位姿融合为100Hz的单一里程计流。</td></tr>
<tr><td>2026-05-24</td><td>A Decentralized LiDAR-SLAM System with Certifiably Optimal Pose Graph Optimization<br><a href='http://arxiv.org/pdf/2605.25051'>论文</a></td><td>本文提出首个集成可证明最优位姿图优化后端的去中心化多机器人LiDAR-SLAM系统，旨在解决现有方法在大规模或退化环境中全局一致性差的难题。
◆首次将可证明最优的PGO后端集成于去中心化LiDAR-SLAM中，克服了传统局部搜索易陷入次优解和长期不一致的缺陷。
◆创新性地采用黎曼块坐标下降算法，确保了全局一致的轨迹估计。
◆系统无需依赖精确的初始猜测即可实现优化，显著增强了在复杂场景下的鲁棒性。
实验表明，该系统轨迹均方根误差相比现有最先进的DiSCo-SLAM大幅降低了48.9%。</td></tr>
<tr><td>2026-05-23</td><td>LC-Flow: Learning Local Continuous Optical Flow and Confidence from events<br><a href='http://arxiv.org/pdf/2605.24604'>论文</a></td><td>LC-Flow是首个纯粹基于局部事件的时间连续学习型光流估计器，解决了现有方法无法充分利用事件时间连续性的问题。它在局部方法中表现最优，其聚合方法更在MVSEC数据集上超越了繁重的帧法网络，确立了新的整体最优性能。
◆提出连续局部循环网络，维持空间网格的持久隐藏状态以逐步积累时间上下文，可在任意时间戳输出稀疏局部光流，克服了固定累积窗口与无状态从头计算的缺陷。
◆联合学习置信度分数，量化局部预测的可靠性，显式处理了事件稀疏性与孔径问题带来的内在模糊性。
◆赋予置信度双重作用，既过滤不可靠估计以服务下游视觉里程计等任务，又为多尺度聚合提供权重，将稀疏局部光流重建为全局一致光流。</td></tr>
<tr><td>2026-05-21</td><td>Extending Deep Event Visual Odometry with Sparse Point-Cloud Export<br><a href='http://arxiv.org/pdf/2605.22890'>论文</a></td><td>本文在深度事件视觉里程计DEVO的基础上，提出了一种稀疏点云导出管线。该系统在不改变原有视觉里程计性能的前提下，成功实现了稀疏几何场景的输出。
◆提出一种无侵入式的稀疏点云导出管线，通过提取DEVO内部已估算的3D结构并将其转换为显式点云，实现了点云的可视化与后续处理，且无需修改核心里程计公式。
◆构建了一套完整的数据导出实用工作流，涵盖数据导出、格式转换及点云清理功能，增强了系统的工程可用性。
实验表明，导出的稀疏点云与EMVS重建结果局部一致且在5厘米阈值下具有高精度，但也揭示了其在点云密度、完整性及抗累积噪声方面的局限。</td></tr>
<tr><td>2026-05-21</td><td>FRED: A Multi-Modal Autonomous Driving Dataset for Flooded Road Environments<br><a href='http://arxiv.org/pdf/2605.22018'>论文</a></td><td>本文提出了FRED数据集，据我们所知，这是首个专门针对道路积水灾害场景收集数据的多模态自动驾驶数据集。
◆首次提供涵盖洪涝期间及事后五个地点的多模态数据，包含高分辨率相机图像、64线激光雷达点云及RTK GNSS校正的IMU数据。
◆数据集同时采用KITTI风格与RTMaps两种格式发布，兼顾了现有工具的易集成性与车辆数据的直接回放需求。
◆提供语义标注以支持水害检测的训练与评估，兼容单传感器及传感器融合方法。
◆额外提供位置、速度及干燥条件数据，不仅助力结合地图的基于位置检测方法开发，还能评估定位与SLAM等任务。</td></tr>
<tr><td>2026-05-21</td><td>FUSE: A Framework for Unified State Estimation in Vehicular and Robotic SLAM Systems<br><a href='http://arxiv.org/pdf/2605.18047'>论文</a></td><td>本文提出了一种名为FUSE的统一状态估计框架，旨在解决传统紧耦合SLAM中各模块高度绑定导致难以独立修改设计的问题。
◆提出FUSE框架，通过观测摄取、传播、更新和状态查询接口，将时间处理、局部几何关联、估计器公式与地图更新策略彻底解耦。
◆开发LiDAR-IMU实例，在统一接口边界下实现了高频惯性传播、LiDAR几何更新、残差筛选与退化感知校正的协同运作。
◆在混合频率感知和方向退化场景中，有效正则化弱可观方向的更新，增强了系统的鲁棒性。
实验表明，在418米闭环走廊序列中，该实例相比最优基线Faster-LIO实现了7.9%的相对误差降低。
这证明了FUSE为组织状态估计设计提供了有效框架，并能提升实际SLAM系统的估计精度。</td></tr>
<tr><td>2026-05-20</td><td>SubTGraph: Large-Scale Subterranean Environment Synthesis with Controllable Topological Variability for Robotic Autonomy Validation<br><a href='http://arxiv.org/pdf/2605.20917'>论文</a> | <a href='https://github.com/LTU-RAI/SubTGraph.git'>代码</a></td><td>本文针对地下环境机器人研究缺乏大规模仿真基准的问题，提出了SubTGraph框架。
◆该框架能够根据用户对拓扑、维度和纹理等参数的设定，快速合成具有高变异性的多层地下环境。
◆该方法创新地从结构约束构建成本矩阵，引导Dijkstra算法结合DARPA拓扑贴片进行程序化生成。
研究通过语义分割、多智能体路径规划和LIO SLAM三个案例，验证了该框架对机器人自主系统各层严格评估的有效性。
最后，作者开源了世界创建代码库及包含150个高变异地下环境的数据库。</td></tr>
<tr><td>2026-05-19</td><td>Depth2Pose: A Pose-Based Benchmark for Monocular Depth Estimation without Ground-Truth Depth<br><a href='http://arxiv.org/pdf/2605.19797'>论文</a> | <a href='https://kocurvik.github.io/depth2pose'>代码</a></td><td>本文针对单目深度估计传统评估指标无法反映下游几何任务实用性的问题，提出了Depth2Pose评估框架。
◆提出以相对相机位姿估计精度作为任务驱动的代理指标，结合深度预测与特征对应关系评估深度质量，取代了传统全局深度误差指标。
◆该框架仅需通过运动恢复结构等方法获取相机位姿，免去了昂贵且难以获取的密集真实深度图，使其适用于大尺度或严重遮挡等复杂场景。
◆构建了包含分布外挑战性场景的D2P数据集，揭示了在现有基准上表现优异的方法难以泛化到该更具挑战性的数据集上。
研究还提供了简单且可扩展的评估框架，并开源了代码与数据集，为深度估计的下游实用性评估建立了新标准。</td></tr>
<tr><td>2026-05-19</td><td>Enhancing Graph-Based SLAM in GNSS-Denied environments by leveraging leg odometry<br><a href='http://arxiv.org/pdf/2605.20484'>论文</a></td><td>本文针对足式机器人在拒止GNSS环境中LiDAR易产生高程漂移的问题，提出了一种基于因子图架构的SLAM增强方法。
◆在LIO-SAM框架中引入了由本体感受腿部里程计驱动的并行运动学通道。
◆通过带有选择性噪声模型的恒等相对位姿约束，将腿部运动学通道与主LiDAR-惯性通道有效耦合。
◆将步态控制中已计算的本体感受数据作为SLAM的轻量级垂直锚点，无需额外计算负担。
在四足平台超过1公里的户外测试中，该方法将高程漂移从30多米大幅降至30厘米以内。
在基线方法完全失效的几何稀疏场景下，本方法依然能成功收敛并实现鲁棒定位。</td></tr>
<tr><td>2026-05-19</td><td>Multi-Session Ground Texture SLAM in Low-Dynamic Environments<br><a href='http://arxiv.org/pdf/2605.19701'>论文</a></td><td>本文针对现有地面纹理SLAM系统尚未应用于多会话低动态变化环境的问题，研究了三种技术对轨迹估计精度的影响。研究发现，使用库尔巴克-莱布勒散度作为相似度评分和影响回环闭合置信度的偏差取得了最大成功。该工作的核心创新点如下：
◆首次将库尔巴克-莱布勒散度引入多会话低动态地面纹理SLAM中，全面分析了多种方法，并深入探索了该散度作为相似度评分与回环置信度偏差以提升轨迹估计精度的机制。
◆发布了一个全新的多会话地面纹理数据集，包含会话间地面发生变化的图像以及用于评估的高精度位姿信息，为机器人社区提供了宝贵的评估基准。</td></tr>
<tr><td>2026-05-19</td><td>EpiDiffVO: Geometry-Aware Epipolar Diffusion for Robust Visual Odometry<br><a href='http://arxiv.org/pdf/2605.19556'>论文</a></td><td>针对现有学习型视觉里程计依赖稠密匹配导致冗余且几何可解释性差的问题，本文提出了一种基于几何感知对极扩散的稀疏匹配框架。
◆引入对极扩散过程，通过建模对应点不确定性将关键点细化至对极一致性，以解决残差噪声与未对齐问题。
◆提出Steiner图表示法，将细化后的对应点与深度线索结合，利用图神经网络学习并筛选出信息量大的紧凑对应点子集。
筛选出的子集被输入可微奇异值分解求解器，实现端到端的相对位姿估计。
实验表明，该方法在减少匹配冗余的同时，能在具有挑战性的基线下保持鲁棒的位姿估计。</td></tr>
<tr><td>2026-05-19</td><td>Smartphone-based Circular Plot Sampling for Forest Inventory<br><a href='http://arxiv.org/pdf/2605.19213'>论文</a></td><td>本文提出了一种基于智能手机的轻量级圆形样地森林清查方法，解决了传统方法成本高或劳动强度大的问题。
◆提出仅需消费级手机与便携支架，通过单次穿行视频即可完成样地树木测量的轻量级流程。
◆创新性地将单目深度估计和树木实例分割与SLAM框架结合，联合优化相机轨迹与深度。
◆通过融合SLAM位姿和分割深度图恢复树木位置及胸径，并利用校准参考长度锚定绝对真实尺度。
实验表明，该方法在人工林和天然林的胸径测量平均绝对误差分别为1.51厘米和2.30厘米，且跨视频测量一致性强。
该系统实现了与传统方法相当的精度，但大幅降低了设备成本与操作复杂性，使专业和非专业用户均能广泛使用。</td></tr>
<tr><td>2026-05-18</td><td>Towards Ubiquitous Mapping and Localization for Dynamic Indoor Environments<br><a href='http://arxiv.org/pdf/2605.18385'>论文</a></td><td>该论文提出了UbiSLAM系统，旨在解决动态室内环境下的实时建图与定位问题。
◆采用部署固定RGB-D摄像机网络的方法，摆脱了对移动单元传感器的依赖，克服了传统SLAM对环境变化敏感的局限。
◆构建并持续更新集中式全局地图，为机器人提供准确的实时全局视图，从而提升导航精度、减少碰撞并优化人机交互。
◆将计算负载从机器人转移至固定网络，使低复杂度机器人平台也能高效运行，显著增强了系统的整体鲁棒性。
针对空间覆盖盲区挑战，论文探讨了整合机器人数据、自动校验相机布局及增强通信协议等潜在解决方案。
这些工作为实现泛在化的室内建图与定位提供了全新范式。</td></tr>
<tr><td>2026-05-17</td><td>Mono-Hydra++: Real-Time Monocular Scene Graph Construction with Multi-Task Learning for 3D Indoor Mapping<br><a href='http://arxiv.org/pdf/2605.17661'>论文</a></td><td>Mono-Hydra++提出了一种仅依赖单目RGB与IMU输入的...[摘要不完整，待更新]</td></tr>
<tr><td>2026-05-17</td><td>Stretch-ICP: A Continuous-Trajectory Registration and Deskewing Algorithm in Scenarios of Aggressive Motions<br><a href='http://arxiv.org/pdf/2605.17264'>论文</a></td><td>针对复杂环境中机器人剧烈运动导致传感器测量受损和状态估计退化的问题，本文提出了提升SLAM算法鲁棒性的方法。
◆提出TIGS数据集，包含激光雷达与IMU滚落山坡的记录，其最高角速度达同类数据集四倍且已公开。
◆提出饱和感知角速度估计算法SAAVE，在陀螺仪测量饱和时仍能准确估计角速度，将估计误差降低83.4%。
◆提出新型配准与去畸变算法Stretch-ICP，能在剧烈运动下重建更平滑的六自由度连续轨迹。
该算法将扫描边界处的线速度和角速度误差分别大幅降低了95.2%和94.8%。
综合来看，本文显著提升了剧烈运动场景下激光雷达惯性状态估计的鲁棒性与一致性。</td></tr>
<tr><td>2026-05-16</td><td>Rethinking the State Update Gate for Long-Sequence Recurrent 3D Reconstruction<br><a href='http://arxiv.org/pdf/2605.16981'>论文</a></td><td>本文揭示了长序列循环三维重建中现有逐令牌状态更新门存在幅值受限且随帧不变的结构瓶颈，导致有效记忆范围极短并引发长序列漂移。其根源在于现有方法仅在帧内逐令牌级别调节更新，忽略了每帧对状态贡献强度的帧级问题。
◆提出一种标量帧级门控机制，通过内部特征的帧间变化推导出闭式解，相当于经典SLAM关键帧选择的连续松弛。
◆该门控机制无需额外参数、训练或额外前向传播，在零训练成本下维持了严格的恒定内存预算。
在长达4541帧的六项基准测试中，该方法将长序列位姿误差降低51%，视频深度误差降低12.8%，性能全面超越现有基线。</td></tr>
<tr><td>2026-05-15</td><td>LAPS: Improving Incremental LiDAR Mapping using Active Pooling and Sampling for Neural Distance Fields<br><a href='http://arxiv.org/pdf/2605.15496'>论文</a> | <a href='https://github.com/dongjae0107/LAPS'>代码</a></td><td>本文提出LAPS框架，解决增量激光雷达建图中神经距离场在线优化易受灾难性遗忘影响的问题。现有方法采用被动缓冲区和均匀采样，导致内存浪费在冗余观测且对欠约束区域训练不足。
◆基于可靠性的主动池化机制，在有限内存下优先保留可靠的历史样本以改进回放保留。
◆基于不确定性的主动采样机制，引导优化过程聚焦于约束不足的区域以改进回放分配。
实验表明，LAPS在保持几何精度的同时显著提升了重建完整性，在Oxford Spires数据集上其召回率和F1分数均大幅超越PIN-SLAM。</td></tr>
<tr><td>2026-05-13</td><td>LEXI-SG: Monocular 3D Scene Graph Mapping with Room-Guided Feed-Forward Reconstruction<br><a href='http://arxiv.org/pdf/2605.13741'>论文</a> | <a href='https://ori-drs.github.io/lexisg-web/'>代码</a></td><td>LEXI‑SG 首次实现仅使用单目RGB相机的开放式词汇三维场景图稠密映射。  
◆ 通过开放式词汇基础模型将场景先划分为房间，在完整观测到房间后才进行前馈重建，避免了滑动窗口导致的比例不一致。  
◆ 提出基于房间的因子图框架，在全局对齐房间重建的同时保持局部地图一致并自然约束语义层次结构。  
◆ 在每个房间内部支持开放式词汇的物体分割与跟踪，实现细粒度目标层级的场景图。  
◆ 在 Habitat‑Matterport 3D 数据集和自采集的办公室序列上验证，显著提升轨迹估计和稠密重建质量，且在开放式词汇分割任务上表现具有竞争力。</td></tr>
<tr><td>2026-05-08</td><td>AERO-VIS: Asynchronous Event-based Real-time Onboard Visual-Inertial SLAM<br><a href='http://arxiv.org/pdf/2605.07885'>论文</a> | <a href='https://ethz-mrl.github.io/AERO-VIS'>代码</a></td><td>◆ The robustness of event cameras to high dynamic range and motion blur holds the potential to improve visual odometry systems in challenging environments.
◆ Although their high temporal resolution does not require synchronous processing, most event-based odometry methods still run at fixed rates, which simplifies system design but restricts latency and throughput.
◆ In this work, we present AERO-VIS, a stereo event-inertial SLAM system with an integrated, data-driven, robust, and performance-optimized keypoint detector.</td></tr>
<tr><td>2026-05-06</td><td>Dr-PoGO: Direct Radar Pose-Graph Optimization<br><a href='http://arxiv.org/pdf/2605.04806'>论文</a> | <a href='https://github.com/utiasASRL/dr_pogo'>代码</a></td><td>◆ This paper introduces Dr-PoGO, a method for Simultaneous Localization And Mapping (SLAM) using a 2D spinning radar.
◆ Unlike cameras or lidars that require line-of-sight, millimetre-wave radars can `see&#x27; through dust, falling snow, rain, etc.
◆ Accordingly, it is a great modality for robust perception regardless of the weather conditions.</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sfm'>SFM (65篇)</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-16</td><td>Immediate 3D Gaussian Splat Reconstruction of Unordered Input with Global Consistency<br><a href='http://arxiv.org/pdf/2607.14481'>论文</a></td><td>本文针对3D高斯溅射(3DGS)重建中乱序输入与即时反馈难以兼顾的问题，提出首个支持乱序图像输入并保持全局一致性的即时重建框架。该方法通过复用视觉位置识别模型与构建共视性图，实现乱序序列的快速匹配与高连通关键帧筛选，并结合GPU优化和精心设计的高斯基元放置策略，保证局部重建的效率与质量。

◆ 提出基于视觉位置识别与共视性图的乱序图像快速匹配方法，并发现高连通关键帧的选择还能进一步提升有序序列的重建质量。

◆ 提出基于共视性图的聚类式回环闭合策略，无需依赖顺序输入即可实现高效的全局一致性优化。

◆ 引入渐进式层次结构，使方法能够扩展到包含数千张图像的大规模场景，同时兼顾效率与视觉质量。</td></tr>
<tr><td>2026-07-15</td><td>SalientGS: Unified SfM-to-3DGS with Importance-Guided MCMC Gaussian Allocation<br><a href='http://arxiv.org/pdf/2607.11285'>论文</a> | <a href='https://github.com/Six-Bit-TX/SalientGS'>代码</a></td><td>SalientGS提出了一种统一的SfM到3D高斯溅射（3DGS）的端到端重建流水线，旨在消除传统3D场景重建中昂贵的SfM预处理和冻结位姿接口的瓶颈。其核心创新在于引入了重要性引导的MCMC高斯分配策略，通过聚合多视图残差来计算每个高斯点的欠拟合度和冗余度信号。系统利用这些信号构建平滑的重要性加权采样分布，使得高斯点的生成和重定位偏向欠拟合区域，从而在不改基础随机梯度朗之万动力学的前提下，将渲染能力从已拟合良好的区域重新分配到欠拟合区域。SalientGS能够在15分钟内完成端到端重建，并在感知质量上达到最先进水平。◆统一了SfM与3DGS流水线，实现了无需外部预处理的高效端到端三维重建。◆通过多视图残差聚合定义高斯点的重要性信号（欠拟合度与冗余度），实现细粒度的容量分配。◆在保留SGLD框架的基础上，以重要性加权采样分布引导MCMC的生灭与重定位过程，避免了底层动力学修改。</td></tr>
<tr><td>2026-07-12</td><td>Deep far-UV observations of the ELAIS N1 field using AstroSat: Source catalogue, spectral energy distribution modelling and star formation<br><a href='http://arxiv.org/pdf/2607.06143'>论文</a></td><td>本文利用AstroSat卫星上的紫外成像望远镜(UVIT)对ELAIS N1深场进行了F154W波段(far-UV)的深度观测,总曝光时间达30千秒,通过CCDLAB v3.0进行数据处理,获得了1637个3σ和458个5σ的FUV源目录,极限星等分别为25.69和25.13 mag(AB),为该天区提供了目前最深的FUV测光数据。

◆ 基于多波段交叉匹配,结合光学和红外数据以及光谱/测光红移,采用多波段判据剔除活动星系核(AGN),构建了清洁的恒星形成星系样本。

◆ 使用CIGALE进行SED建模,采用延迟型恒星形成历史(可叠加晚期暴发)、Bruzual &amp; Charlot恒星 population合成、Calzetti消光和SKIRTOR AGN模块,系统地推导了样本的恒星形成率(SFR)、总恒星质量和年轻恒星质量随红移的演化。

研究发现SFR随红移单调上升,符合恒星形成主序(SFMS)的演化趋势,同时年轻质量与总质量比值在0&lt;z≲0.76范围内近似为常数,表明样本中的星系主要以自调节的稳态恒星形成为主,而非星暴主导的演化模式。</td></tr>
<tr><td>2026-07-12</td><td>Mapping Pamir: Multi-Session Visual-Inertial SLAM and 3D Reconstruction of an Underwater Shipwreck<br><a href='http://arxiv.org/pdf/2607.10925'>论文</a></td><td>本文针对水下船骸等复杂环境的多会话三维重建难题，提出了一套基于低成本运动相机的多会话水下建图框架。该框架将SVIn2视觉惯性SLAM与COLMAP SfM相结合，利用SVIn2生成每段会话的相机轨迹与稀疏重建，再通过COLMAP进行全局优化并生成稠密三维模型。

◆ 创新性地融合了潜水电脑的水深数据与视觉惯性信息，增强了水下场景的尺度估计与几何约束。

◆ 提出利用固定位置的标定靶估计不同会话间的坐标变换矩阵，实现了多会话数据的统一配准。

◆ 首次对巴巴多斯近海Pamir沉船的外部与可进入内部进行完整多会话建图，其中第三会话采用双相机不同视场配置以兼顾全局覆盖与细节捕获。</td></tr>
<tr><td>2026-07-11</td><td>Navigating the Crowd: Non-linear MPC with Social Forces Dynamics for Human-Aware Robot Navigation<br><a href='http://arxiv.org/pdf/2607.10374'>论文</a></td><td>本文针对人机共融环境中机器人安全且符合社会规范的导航问题，提出了SFM-NMPC框架，将社会力模型(SFM)与非线性模型预测控制(NMPC)深度融合。其核心思想是在优化循环内嵌入对周围行人运动轨迹的预测，使控制器能够联合预测人与机器人在预测时域内的运动，从而实现具有社会意识的规划。

◆将社会力模型集成到NMPC的动态模型中，在优化循环内直接预测行人轨迹，实现人机轨迹的联合优化。

◆设计了针对性的社会成本函数，引导优化过程产生尊重个人空间、符合人类舒适度要求的行为。

◆在增加模型复杂度的同时，通过高效求解实现20Hz的实时控制，满足实际部署需求。

◆在拥挤环境仿真中验证了方法在社会合规性指标上优于现有先进方法，并通过消融实验证明了嵌入式SFM动力学和社会成本项的贡献。</td></tr>
<tr><td>2026-07-10</td><td>DGSfM: Depth-Guided Scale-Aware Global Structure-from-Motion<br><a href='http://arxiv.org/pdf/2607.09507'>论文</a> | <a href='https://github.com/sithu31296/DGSfM'>代码</a></td><td>本文提出DGSfM,一种深度感知的全局SfM流水线,旨在解决传统全局SfM在基线估计噪声和视图图约束弱时定位不稳定、以及视觉模糊对产生虚假边导致重建退化的问题。论文的核心思路是引入单目深度图作为可扩展先验,同时保留显式多视图优化。

◆ 提出深度感知的相对位姿求解器,将原本尺度模糊的极线约束转化为尺度感知的相对位姿约束,使全局定位摆脱对噪声基线估计的依赖。

◆ 通过视图图过滤和基于深度一致性的匹配剪枝,抑制在极线几何下看似合理但实际错误的边和匹配,提升鲁棒性。

◆ 设计全局尺度平均和深度引导的位姿-点初始化策略,将各图像的单目深度图对齐到统一重建尺度,并为全局定位与光束法平差提供稳定初值。

在ETH3D和IMC2021上的实验表明,DGSfM在稀疏和稠密匹配前端下均持续优于强基线全局SfM方法,在位姿精度上取得显著提升。代码已开源,具有较好的实用价值。</td></tr>
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
<tr><td>2026-07-09</td><td>PanoImager: Geometry-Guided Novel View Synthesis and Reconstruction from Sparse Panoramic Views<br><a href='http://arxiv.org/pdf/2606.27071'>论文</a></td><td>◆ PanoImager针对稀疏全景图在旋转主导、弱视差场景下SfM/SLAM初始化不稳定的问题，提出了一个无需SfM的三维重建框架。
◆ 方法将全景图分解为局部透视视图，并利用前馈式位姿与深度先验提供初始几何约束。
◆ 通过几何条件扩散模型合成辅助新视角，补充稀疏输入中缺失的观测信息。
◆ 结合深度引导的3D Gaussian Splatting优化，提升跨视角一致性并稳定重建过程。
◆ 实验表明，该方法在极端稀疏全景输入下具有更好的鲁棒性，可作为SfM/SLAM失败时的离线地图细化组件。</td></tr>
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
<tr><td>2026-07-01</td><td>EPO: Boosting 3D Foundation Models with Edge-based Pose Optimization<br><a href='http://arxiv.org/pdf/2607.00579'>论文</a></td><td>EPO是一种针对三维基础模型SfM重建结果的无轨迹几何优化框架，旨在解决这类模型虽然推理速度快但几何精度不足的问题。该方法通过边缘图对齐作为几何优化的代理，完全避免了传统Bundle Adjustment类方法所需的特征提取和轨迹构建过程，是一个完全可微的优化框架。实验证明，EPO在多个数据集和任务上能够匹配甚至超越Bundle Adjustment类方法的精度，同时显著降低了运行时间和内存占用。值得注意的是，EPO的内存需求大幅减少，使其能够在消费级硬件上运行，而竞品的精修方法则无法实现。

◆ 创新点一：提出无轨迹优化思路，使用边缘图对齐替代传统特征轨迹，避免了耗时的特征提取与匹配步骤。
◆ 创新点二：设计完全可微的优化框架，将边缘对齐作为几何优化的代理信号，实现端到端优化。
◆ 创新点三：在精度匹配或超越Bundle Adjustment的同时，大幅降低运行时与内存开销，支持消费级硬件部署。</td></tr>
<tr><td>2026-06-29</td><td>Emergence of a Shared Canonical Object Frame from In-the-Wild Videos<br><a href='http://arxiv.org/pdf/2606.30058'>论文</a> | <a href='https://github.com/Fischer-Tom/Emergent-Canonical-Frame/'>代码</a></td><td>◆ 论文提出一种从野外物体视频中自监督学习共享规范物体坐标系的方法，避免了传统方法对人工规范姿态标注的依赖。
◆ 核心创新是将所有训练序列通过共享几何瓶颈，即一个不含类别细节的粗略规范网格，从而促使不同实例对齐到共同框架。
◆ 方法学习图像像素到规范网格的稠密对应关系，并利用SfM得到的噪声相机几何估计每个视频序列的对齐变换。
◆ 共享规范框架并非显式监督得到，而是从多视角一致性和预训练特征提取器的语义先验中自然涌现。
◆ 在16万个野外物体视频上训练后，该方法在类别级姿态估计基准上达到与依赖规范姿态监督的方法相竞争的性能，显著提升了可扩展性。</td></tr>
<tr><td>2026-06-26</td><td>RayPE: Ray-Space Positional Encoding for 3D-Aware Video Generation<br><a href='http://arxiv.org/pdf/2606.27345'>论文</a></td><td>论文核心贡献是提出RayPE，一种面向三维感知视频生成的射线空间位置编码模块。现有视频DiT仅在(u,v,t)采样网格上使用RoPE，缺乏对场景三维结构的显式建模，作者由此指出Plücker互反积在代数形式上与注意力点积同为双线性结构，进而将每条相机射线的6D Plücker坐标以加性方式注入自注意力的Query与Key。

◆ 基于Plücker互反积与注意力点积的双线性类比，将6D射线坐标加性注入Q/K，使注意力分数自然分解为内容项、几何项与两组交叉项，实验验证各项均不可或缺。

◆ 采用Query/Key翻转设计，使对称恒等配置与互反积严格对齐，保证编码的物理一致性。

◆ 针对异构相机平移尺度（SfM、深度SLAM、度量尺度）问题，将射线方向与矩幅解耦，并以log幅值的可学习函数门控编码，结合RMSNorm与QKNorm对齐。

◆ 模块新增参数小于0.1%，零初始化以保留预训练权重，可即插即用至预训练视频DiT，显著提升相机可控性、跨帧三维一致性与整体视频质量。</td></tr>
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
<tr><td>2026-06-16</td><td>Fast Speech Foundation Model Distillation Using Interleaved Stacking<br><a href='http://arxiv.org/pdf/2606.11766'>论文</a></td><td>本文探索了语音基础模型蒸馏的训练加速问题，旨在加快模型部署速度。
现有的堆叠方法虽然能通过逐渐增加模型深度来加速训练，但会导致模型性能下降。
◆提出了一种名为交错堆叠的新型方法，在堆叠过程中始终保持层位置不变。
◆该方法有效保留了语音基础模型每层编码的独特层特有知识，解决了传统堆叠导致的性能退化问题。
在SUPERB基准上的实验验证了该方法能在加速蒸馏训练的同时有效保持模型性能。</td></tr>
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
<tr><td>2026-06-15</td><td>MotionPyramid: Hierarchical Motion Representation and Residual Interfaces<br><a href='http://arxiv.org/pdf/2606.20705'>论文</a></td><td>◆提出MotionPyramid，将类感知层级的表示思想引入运动控制，从数据中学习从即时电机命令到长时程行为片段的多层动作表征。
◆方法以运动跟踪教师为起点，训练递归潜变量解码器，使高层潜变量可经低层展开为 temporally extended 的全身运动程序。
◆预训练后的层级被冻结，并作为下游强化学习策略的多种动作接口，支持不同控制分辨率的复用。
◆实验表明，粗粒度接口能加速早期学习并提升运动规律性，细粒度接口则保留反馈控制能力和最终任务精度。
◆论文还提出Residual Interfaces，使策略可同时使用粗层运动程序与细层残差修正，在结构化抽象和可控性之间取得平衡。</td></tr>
<tr><td>2026-06-13</td><td>PEARLS: NuSTAR and XMM-Newton Extragalactic Survey of the JWST North Ecliptic Pole Time Domain Field VI: Multiwavelength SED Analysis<br><a href='http://arxiv.org/pdf/2606.15365'>论文</a></td><td>本文对北黄极时域场中261个X射线源（最高红移z~5）进行多波段SED建模分析，结合恒星形成主序（SFMS）和黑洞吸积率（BHAR）框架，揭示AGN活动与宿主星系恒星形成的瞬时关联，样本X射线源的SFR普遍低于SFMS而BHAR高于群体平均值，符合X射线选样本的预期特征。

◆ 首次在X射线选大样本中发现SFR相对SFMS的偏离与比AGN光度（L_AGN/M_*）呈强正相关（ρ=+0.73），最高L_AGN/M_*的星系位于或高于SFMS。

◆ 发现X射线光度与SFR的强相关性（ρ=+0.80），识别出恒星形成活跃且X射线明亮的&quot;冷类星体&quot;种群，对应剧烈短时标的吸积爆发。

◆ 揭示低质量星系BHAR远高于其质量对应的群体平均值，呈&quot;生长爆发&quot;模式；高质量星系则处于&quot;维持模式&quot;吸积。

◆ 证明传统AGN分类（遮蔽/无遮蔽/射电噪）无法区分这些演化相，凸显X射线视角在揭示SMBH与星系瞬时耦合方面的独特价值。</td></tr>
<tr><td>2026-06-12</td><td>A Lightweight Fiducial-Based Pipeline for 3D Hyperspectral Mapping of ex-vivo Lumpectomy Specimens<br><a href='http://arxiv.org/pdf/2606.14534'>论文</a></td><td>本文提出了一种全自动且无需标定的轻量级流程，通过消费级RGB图像和单次高光谱采集，生成离体乳房切除术标本的3D高光谱点云。
◆采用深度学习运动恢复结构骨干网络进行3D几何重建，并通过四个ArUco标记角点一致性的自定义光束法平差，在度量参考系中实现稳定。
◆提出无需恢复高光谱相机位姿的配准新方法，利用双模态可见的16个标记角点驱动平面单应性，并通过正交深度图查找恢复3D坐标。
在离体标本评估中，该流程的中位3D配准误差低于1毫米，2D重投影误差低于0.02毫米。
加速硬件下单标本处理时间不到4分钟，证明了将其应用于保乳手术术中切缘评估的可行性。</td></tr>
<tr><td>2026-06-12</td><td>MooMIns -- Monocular 3D Reconstruction and Object Pose Estimation from Multiple Instances<br><a href='http://arxiv.org/pdf/2606.14389'>论文</a></td><td>该论文针对单目图像同时进行3D重建与6D位姿估计的病态问题，提出MooMIns方法，利用工业料箱场景中单图隐含的同物体多视角信息实现联合重建与估计。
◆反转高斯溅射公式，将传统的多相机渲染单一场景转变为单相机渲染多个物体实例。
◆结合SAM3实例分割掩码与改进的运动恢复结构流程进行方法初始化。
◆采用基于图像证据的纯几何重建，有效避免了深度学习单目深度估计因训练数据先验产生的幻觉问题。
实验表明，该方法在合成与真实场景中均能准确重建未见物体并可靠估计各实例的6D位姿。</td></tr>
<tr><td>2026-06-09</td><td>Multi-Angular Reflectance Anisotropy Observed from UAV Multispectral Imagery<br><a href='http://arxiv.org/pdf/2606.10350'>论文</a></td><td>本文针对无人机多光谱影像因低空大视场产生的几何驱动辐射变异问题，提出了一种几何感知的多角度观测提取工作流程，从二向性反射分布函数视角量化观测几何效应。
◆提出基于运动恢复结构优化相机参数，并将正射影像均一区域重投影到多视点原始子图像的方法，实现同目标多视角下多波段反射率与几何参数的联合提取。
◆引入在观测天顶角与相对方位角域进行逐波段极坐标可视化的分析方法，直观揭示了几何效应对多角度反射率的影响规律。
◆通过草地目标实验发现十个波段均存在显著反射率各向异性，红边与近红外波段的反射率变异性高达119%至137%。
该研究证明了观测几何效应对辐射一致性具有不可忽视的影响，为无人机影像精准辐射校正提供了新依据。</td></tr>
<tr><td>2026-06-08</td><td>Minimal Solvers for Full-DoF Motion Estimation from Asynchronous Differential SfM<br><a href='http://arxiv.org/pdf/2606.09218'>论文</a></td><td>本文提出了一种基于异步光流直接进行全自由度自运动估计的新框架，旨在联合恢复角速度和线速度，以解决事件相机异步数据流对传统同步算法的挑战。
◆将微分对极约束解耦为独立的角速度和线速度分量，并推导了其面向异步数据的公式。
◆通过引入旋转动力学的一阶近似将约束方程转化为多项式形式，推导出首个代数最小五点求解器。
◆通过截断高阶角速度项，提出了一种加速求解器以满足高速场景的实时性需求。
实验表明该异步方法在精度和对时空噪声的鲁棒性上优于传统同步方法，为高速机器人的连续时间运动估计奠定了基础。</td></tr>
<tr><td>2026-06-04</td><td>S23DR 2026 Winning Solution<br><a href='http://arxiv.org/pdf/2606.06695'>论文</a></td><td>本文提出了S23DR 2026挑战赛的首胜方案，解决了从稀疏SfM、拟合深度和语义分割中进行结构化3D线框重建的问题。
◆将顶点视为条件集，利用基于Perceiver风格场景标记的条件流匹配DiT，对64个顶点标记进行去噪。
◆采用两阶段重建策略，首先通过全局通道预测粗略结构，接着利用裁剪外壳的第二通道进行细化。
◆引入小型多样本一致性步骤，有效保持了随机采样器的稳定行为。
该系统最终在私有排行榜上排名第一，取得了0.654的HSS成绩。</td></tr>
<tr><td>2026-06-02</td><td>Eliciting Complex Spatial Reasoning in MLLMs through Wide-Baseline Matching<br><a href='http://arxiv.org/pdf/2606.03577'>论文</a></td><td>本文针对多模态大语言模型在宽基线匹配中缺乏系统评估与训练框架的问题，深入探索并提升了其复杂空间推理能力。
◆构建了ReasonMatch-Bench基准，按视点位移和匹配粒度分层，揭示了当前模型在细粒度宽基线对应任务上远逊于人类的显著缺陷。
◆建立了可扩展的数据生成流水线，从大规模RGB-D视频和SfM重建等3D语料库中自动提取宽基线视图对，提供多样且可验证的监督信号。
◆提出了动态对应强化学习算法DCRL，结合图像级视点递进与点级对应课程，通过可验证奖励优化模型而无需显式思维链监督。
实验表明，DCRL显著提升了宽基线匹配及跨基准的空间推理性能，同时维持了良好的通用视觉理解能力。</td></tr>
<tr><td>2026-06-02</td><td>SAMatcher: Co-Visibility Modeling with Segment Anything for Robust Feature Matching<br><a href='http://arxiv.org/pdf/2606.03406'>论文</a></td><td>本文提出SAMatcher框架，将特征匹配转化为共可见性建模问题，突破了现有方法仅停留在像素级而缺乏跨视图共可见区域显式建模的局限。
◆不同于直接匹配局部特征，该方法首创预测共可见区域掩码和边界框作为对应估计的结构化先验。
◆基于SAM模型引入对称跨视图交互机制，实现了视图间的双向特征交换与跨视图语义对齐。
◆提出统一监督方案，通过掩码学习、框回归及掩码框一致性约束联合优化掩码预测与框定位。
实验表明该方法在大视角和尺度变化下显著优于现有方法，并证实单目分割模型可扩展至多视图推理，为图像匹配提供新视角。</td></tr>
<tr><td>2026-06-01</td><td>Edge Prediction for Roof Wireframe Reconstruction with Transformers<br><a href='http://arxiv.org/pdf/2606.02406'>论文</a></td><td>本文提出了一种受DETR启发的端到端Transformer编解码器架构，用于从稀疏SfM点云和地面语义数据中重建3D房屋屋顶线框模型。
◆提出基于语义优先级对稀疏SfM点云进行动态下采样，并融合格式塔与ADE20k类别特征进行增强。
◆将点云投影至冻结自编码器生成的潜特征图中提取额外格式塔特征编码，与点特征融合以丰富分割上下文。
◆利用交叉注意力机制，将学习到的查询嵌入直接解码为3D线框边缘。
该方法在HoHo 22k数据集上显著超越手工与学习基线，以0.6476的混合结构得分在S23DR挑战赛中夺得亚军。</td></tr>
<tr><td>2026-06-01</td><td>SAVMap: Structure-Aided Visual Mapping of Large-Scale 2.5D Manhattan Wireframes from Panoramic Video<br><a href='http://arxiv.org/pdf/2606.01939'>论文</a></td><td>本文提出了SAVMap方法，仅利用全景视频相机作为传感器输入，即可生成工业仓库货架和照明设施的语义线框地图。
◆结合语义分割网络前端，从全景视频校正图像中提取稀疏的语义结构特征点如货架角点和灯具中心，并在图像序列中对其进行跟踪。
◆提出一种结合曼哈顿网格等现实世界几何关系的约束运动恢复结构算法，从而计算构成线框地图的精确三维点。
该方法在拥有46排大型货架的仓库中得到了验证，仅用一小时全景视频便成功构建了超五千个货架元素的线框地图。
实验结果表明，该地图相对于真实值的总体平均绝对误差仅为4.8厘米，展现了出色的可扩展性与高精度。</td></tr>
<tr><td>2026-05-30</td><td>Optimizing 3D Gaussian Splatting via Point Cloud Upsampling<br><a href='http://arxiv.org/pdf/2606.00450'>论文</a></td><td>本文旨在解决3D高斯溅射性能严重依赖初始种子点质量的问题，通过点云上采样优化其初始化过程。研究评估了线性插值、三角插值、样条表面重建、移动最小二乘和Voronoi生成等多种点云上采样方法。
◆提出了一种深度引导的点提升方法，利用深度图保持与运动恢复结构重建的几何一致性。
◆揭示了不同上采样策略的适用场景，如表面重建方法适用于有机细节场景，简单插值适用于分段平滑几何。
◆证实深度引导方法在整个场景特别是无纹理区域能有效添加几何感知点。
研究最终基于场景特征和计算约束，为选择合适的上采样方法提供了实用指南，推进了对点云初始化影响3DGS质量的理解。</td></tr>
<tr><td>2026-05-29</td><td>Beyond Instance-Level Alignment and Uniformity: Semantic Factor Learning for Collaborative Filtering<br><a href='http://arxiv.org/pdf/2605.31414'>论文</a></td><td>本文提出SaFeAU框架，通过语义因子增强对齐与均匀性，解决传统协同过滤实例级学习导致的假阴性标签问题，使矩阵分解无需图邻域聚合即可捕获高阶协同过滤信号。
◆提出语义因子路由，将物品表示解耦为独立的全局语义因子。
◆设计语义因子匹配，识别与已交互物品共享语义因子的未交互物品作为潜在正样本，丰富稀疏监督信号。
◆构建语义对齐，同时对观测和潜在正样本对进行对齐，并促进用户与物品表示的均匀性。
实验表明，该框架在稀疏数据集上的推荐准确度和计算效率均优于现有的图卷积与矩阵分解方法。</td></tr>
<tr><td>2026-05-28</td><td>City-Mesh3R: Simulation-Ready City-Scale 3D Mesh Reconstruction from Multi-View Images<br><a href='http://arxiv.org/pdf/2605.30310'>论文</a></td><td>本文提出City-Mesh3R框架，实现从大规模无序图像直接重建适用于仿真的城市级高保真水密三维网格，克服了现有方法几何缺失和表面噪声的问题。
◆采用基于分治策略的端到端图像到网格重建流程，取代传统的全局稀疏SfM初始化与分布式稠密重建，使模型可扩展至任意大规模场景。
◆利用拓扑图像聚类进行聚类独立稀疏SfM与地图合并，无需穷举图像特征匹配即可构建稀疏城市地图。
◆结合几何感知相机选择与曲率感知自适应顶点密度重网格化技术进行表面细化，有效保障网格几何规则且细节精细。
◆通过空间分区与网格缝合技术无缝拼接局部网格，生成全局水密城市网格，验证了分布式端到端处理的卓越扩展性与重建保真度。</td></tr>
<tr><td>2026-05-28</td><td>The JADES Mass-Metallicity and Fundamental Metallicity Relations at $z\gtrsim2$ Using New High-Redshift Metallicity Calibrations<br><a href='http://arxiv.org/pdf/2605.30513'>论文</a></td><td>◆本文利用JADES中601个恒星形成星系的JWST/NIRSpec叠加光谱，系统测量了1.4&lt;z&lt;7.0的质量-金属丰度关系和基本金属丰度关系。

◆创新点在于采用基于高红移星系的最新强发射线金属丰度标定，降低了传统本地标定用于早期宇宙时的系统偏差。

◆研究发现MZR斜率从本地到z≈5演化较弱，但归一化随红移平滑下降，表明星系气体金属富集随宇宙时间逐步增强。

◆在z≳5，低质量星系金属丰度继续下降而高质量端相对稳定，导致MZR整体变陡，揭示早期低质量星系更受反馈和气体流动影响。

◆论文还发现固定质量下金属丰度与SFMS偏移存在较弱反相关，说明FMR可能在z≈5已开始形成，并指出现有模拟尚难同时再现各红移的斜率和归一化。</td></tr>
<tr><td>2026-05-27</td><td>CLEAR-NeRF: Collinearity and Local-region Enhanced Accurate 3D Reconstruction in Unbounded Scenes<br><a href='http://arxiv.org/pdf/2605.28125'>论文</a></td><td>本研究提出CLEAR-NeRF方法，将基于NeRF的三维重建应用于多关注区域的无界场景，提升了应对光照和位姿变化的鲁棒性，并确保了适用于数字孪生的度量精度。
◆自动局部区域定位检测与重建，无需增加子模块即可无缝优先处理关注区域。
◆共线性强制的射线采样，以学习平滑的平面和曲面。
◆深度定位邻域点提取，有效抑制表面伪影。
◆几何相关颜色聚合，缓解由光照和位姿引起的颜色变化。
实验表明该方法的性能显著优于基线NeRF模型和传统SfM-MVS解决方案。</td></tr>
<tr><td>2026-05-26</td><td>Global Structure-from-Motion Meets Feedforward Reconstruction<br><a href='http://arxiv.org/pdf/2605.26103'>论文</a> | <a href='https://github.com/colmap/gluemap'>代码</a></td><td>该论文深入分析了传统运动恢复结构方法在低纹理和对称等复杂场景易失败，而前馈重建方法虽能应对这些挑战却受限于可扩展性与精度的现状。
为此，论文提出了一种全新的SfM流程，成功将传统方法与前馈方法的优势相结合。
◆系统性分析了两类方法的局限性，并创新性地融合了传统SfM与前馈3D重建技术。
◆设计出优势互补的全新管线，既具备前馈方法在退化场景下的强鲁棒性，又保留了传统方法在标准场景下的高精度与可扩展性。
实验证明该方法在广泛场景中均达到了最先进水平，并且已将系统开源供社区使用。</td></tr>
<tr><td>2026-05-26</td><td>Joint 2D-3D Segmentation and Association in Street-level Imaging<br><a href='http://arxiv.org/pdf/2605.26725'>论文</a></td><td>本文提出了一种联合2D-3D分割与关联的统一框架，将视觉语义与多视图几何推理相结合以解析街景图像。
◆提出基于零样本检测分割与运动恢复结构重建的跨视图对应方法，摆脱了传统对时序帧跟踪的依赖。
◆设计了3D驱动的关联机制取代传统2D多目标跟踪，利用几何一致性在宽基线视角和多变条件下稳健保持目标身份。
该流水线融合了2D纹理线索与全局3D上下文，具备高度扩展性且适用于多种对象类型。
实验证明，该框架在真实序列覆盖度上大幅提升，在复杂城市场景中较纯2D跟踪方法实现了22%的性能增益。</td></tr>
<tr><td>2026-05-24</td><td>Geometry-Aware Image Flow Matching<br><a href='http://arxiv.org/pdf/2605.25294'>论文</a></td><td>本文针对自然图像生成领域局限于欧几里得假设而忽略数据内在几何结构的问题展开研究。研究发现自然图像的语义信息主要编码在方向分量中，范数分量可由全局平均值近似，这表明自然图像能在超球面上被有效建模。
◆提出球面最优传输流匹配方法，利用角距离实现几何感知的生成建模。
◆提出球面流匹配方法，将动态过程直接约束在流形上进行求解。
实验证明这些几何感知方法的性能显著优于欧几里得基线模型。本工作为弥合黎曼流形建模与自然图像生成之间的鸿沟提供了全新视角。</td></tr>
<tr><td>2026-05-22</td><td>Joint Target-Less Intrinsic and Extrinsic Camera-LiDAR Calibration using Deep Point Correspondences<br><a href='http://arxiv.org/pdf/2605.23397'>论文</a></td><td>本文提出首个完全无需标定板的相机与激光雷达联合标定流程，突破了现有基于深度点对应的标定方法需已知内参的局限。该方法利用深度像素点对应关系，可同时估计包含径向与切向畸变的针孔相机内参以及相机与激光雷达的外参。
◆通过运动恢复结构实现相机内参的自动初始化。
◆将相机与激光雷达特征匹配推广至包含畸变且内参未知的原始图像。
◆将对应点估计与内参及外参的联合非线性优化进行紧密耦合。
在KITTI数据集上的实验表明，该联合标定方法在恢复精确内参的同时有效提升了外参的标定精度。</td></tr>
<tr><td>2026-05-20</td><td>Sensitivity analysis of Stochastic Fluid Models: Stationary and transient quantities with applications<br><a href='http://arxiv.org/pdf/2605.21209'>论文</a></td><td>本文首次针对随机流体模型建立了敏感性分析的理论与结果。
◆推导了该类模型中关键稳态量和瞬态量的敏感性分析表达式。
◆构建数值算例验证了该方法在劣化系统与保险风险过程等排队系统中的应用潜力。
◆为更广泛的马尔可夫调制模型的敏感性分析研究奠定了理论基础。
这些成果不仅填补了随机流体模型敏感性分析的空白，也拓宽了相关理论在复杂系统中的应用边界。</td></tr>
<tr><td>2026-05-20</td><td>Transcoding a 3D Gaussian Splatting Model from a Plenoptic Point Cloud or Mesh without the Original Multi-view Images<br><a href='http://arxiv.org/pdf/2605.21051'>论文</a></td><td>本文提出了一种端到端的转码管线，在无法获取原始多视图图像的情况下，可直接从现有的全光点云或网格模型生成3D高斯溅射模型。
◆提出一种自定义初始化策略，有效引导3DGS模型的学习过程。
◆引入几何约束机制，确保最终生成的3DGS模型与输入的点云或网格表面紧密对齐。
实验表明，该管线生成的3DGS模型不仅视觉质量高，其使用的高斯点数量也远少于原始密集点云。
与传统SfM初始化方法相比，该自定义初始化显著加快了模型的收敛速度，并实现了更清晰的表面表示。</td></tr>
<tr><td>2026-05-20</td><td>JWST Advanced Deep Extragalactic Survey (JADES) Data Release 5: stellar population catalogue for galaxies in GOODS-N and GOODS-S<br><a href='http://arxiv.org/pdf/2605.21599'>论文</a></td><td>本文发布了JADES第五次数据释放的星系恒星种群星表，利用深空JWST成像和多波段数据对GOODS-N和GOODS-S区域约50万个源进行了均匀的贝叶斯物理性质推断。
星表推导了恒星质量、恒星形成率及尘埃消光等参数的后验分布，推进了对z=1至9约35万个星系低质量极限的测量和近期恒星形成约束。
◆创新性地采用随红移演化的星系主序先验来建模非参数化星系恒星形成历史，在保留非参数灵活性的同时为其提供了物理驱动的长期形状。
◆该先验将恒星质量增长与恒星形成率相联系，允许数据支持下的显著偏离，有效缓解了暗弱源的非物理解并减少了红移、年龄、尘埃与金属丰度间的简并性。
经过验证的公开星表为研究宇宙演化中星系生长、熄灭及恒星质量积累提供了可靠的统计样本。</td></tr>
<tr><td>2026-05-19</td><td>Depth2Pose: A Pose-Based Benchmark for Monocular Depth Estimation without Ground-Truth Depth<br><a href='http://arxiv.org/pdf/2605.19797'>论文</a> | <a href='https://kocurvik.github.io/depth2pose'>代码</a></td><td>该论文提出Depth2Pose框架，将单目深度估计的评估与下游几何任务结合，解决了传统深度误差指标无法反映深度对下游任务有用性的问题。
◆提出以相对相机位姿估计精度作为任务驱动的深度质量代理指标，通过结合深度预测与特征对应关系来评估单目深度估计器。
◆打破对昂贵逐像素真实深度标注的依赖，仅需通过运动恢复结构获取相机位姿即可评估，使框架适用于大尺度或严重遮挡等困难场景。
◆构建了D2P数据集，包含常见训练数据分布之外的极具挑战性的场景。
实验表明，在传统基准上表现优异的方法在相同数据集上位姿指标良好，却难以泛化到D2P数据集，该评估框架及代码已开源。</td></tr>
<tr><td>2026-05-18</td><td>Efficient 3D Content Reconstruction and Generation<br><a href='http://arxiv.org/pdf/2605.18052'>论文</a></td><td>该论文致力于推动自动3D内容创建技术的发展，以替代耗时的人工建模和扫描流程。论文的核心贡献涵盖了3D生成与3D重建这两个互补的研究范式。
◆在3D生成方面，提出了Instant3D方法，创新性地将多视角扩散与前馈稀疏视角3D重建相结合，在5至20秒内即可生成高质量的3D资产。
◆在3D重建方面，开发了FastMap运动恢复结构流程，通过广泛结合一阶优化与融合GPU内核，相比现有最优方法实现了高达10倍的加速。
◆FastMap在实现极致加速的同时，依然保持了与之前方法相当的相机位姿估计精度和下游新视角合成质量。</td></tr>
<tr><td>2026-05-16</td><td>RHINO: Reconstructing Human Interactions with Novel Objects from Monocular Videos<br><a href='http://arxiv.org/pdf/2605.17014'>论文</a> | <a href='https://lxxue.github.io/RHINO'>代码</a></td><td>本文提出了RHINO三步框架，从单目RGB视频中共同恢复人、未知物体和静态场景的3D重建，解决了深度模糊、遮挡和运动纠缠的难题。同时，该研究构建了包含手持单目视频与4D捕捉真值的新数据集，并在新视角合成与4D重建任务上超越了现有基线。
◆利用3D感知基础模型稳定结构恢复，分别从前景和背景像素提取粗糙物体形状与表观运动以及场景形状与相机运动。
◆通过估计人体并从表观运动中减去相机运动来提取物体真实运动，成功将人、物体和场景对齐到统一的世界坐标系中。
◆采用具有逐组件符号距离场的组合式神经场细化形状，并引入可微接触先验吸引表面同时惩罚穿透，提升重建的物理合理性。</td></tr>
<tr><td>2026-05-16</td><td>SemaVoice: Semantic-Aware Continuous Autoregressive Speech Synthesis<br><a href='http://arxiv.org/pdf/2605.16964'>论文</a></td><td>现有连续自回归语音合成存在语义建模与连续语音表示不匹配的问题，导致模型过度关注低级声学纹理而牺牲高级语义连贯性，加剧了生成误差累积。为解决此问题，本文提出SemaVoice，一种面向高保真零样本文本转语音的语义感知连续自回归框架。
◆引入语音基础模型引导的对齐机制，精炼连续语音表示以更好捕获局部语义一致性与全局结构关系。
◆在自回归框架内采用块级扩散头，基于精炼后的表示条件进行高质量语音合成。
实验表明，SemaVoice在Seed-TTS基准上取得1.71%的英文词错率，主客观评估均媲美前沿开源系统，且验证了该对齐机制在不同表示粒度下的显著提升效果。</td></tr>
<tr><td>2026-05-15</td><td>SCARED-C: Corrected Camera Poses for Endoscopic Depth Estimation<br><a href='http://arxiv.org/pdf/2605.16628'>论文</a></td><td>本论文指出了广泛使用的内窥镜深度估计基准SCARED数据集存在非关键帧位姿误差严重的问题，导致其可靠标注仅限35个关键帧。
◆提出SCARED-C修正数据集，利用运动恢复结构系统COLMAP重新估计所有帧的相机位姿，有效消除了原数据集由机器人运动学引入的误差。
◆设计了尺度恢复步骤，通过关键帧的真实深度图将重建结果对齐到度量空间，确保了深度数据的物理尺度准确性。
◆大幅扩充了高质量的可用数据，将可靠的RGB-D图像对数量从原本的35个增加至17135个。
该研究还通过立体视差评估和单目深度估计实验验证了修正位姿的有效性，并公开了数据集与代码。</td></tr>
<tr><td>2026-05-14</td><td>Denoising-GS: Gaussian Splatting with Spatial-aware Denoising<br><a href='http://arxiv.org/pdf/2605.14880'>论文</a></td><td>本文提出Denoising-GS框架，将3D高斯溅射的优化过程重新定义为基元去噪过程，解决了现有方法仅调整位置而忽略空间结构从而引入噪声的问题。
◆设计了保留空间优化流的优化器，实现连贯且有方向性的去噪而非随机扰动。
◆提出空间梯度去噪策略，结合基元的空间支撑确保梯度一致性更新。
◆引入基于不确定性的去噪模块，通过估计基元的不确定性来修剪冗余和噪声基元。
◆采用空间连贯性细化策略，在稀疏区域选择性地分裂基元以维持结构完整性。
实验表明该方法在提升新视角合成保真度的同时保持了表示紧凑性，在多个基准上达到最佳性能。</td></tr>
<tr><td>2026-05-14</td><td>Efficient Dense Matching for Enhanced Gaussian Splatting Using AV1 Motion Vectors<br><a href='http://arxiv.org/pdf/2605.14629'>论文</a></td><td>本文针对3D高斯泼溅依赖初始点云质量且传统SfM管道计算成本高、无纹理区域点云稀疏的问题，提出了一种基于AV1的特征检测与匹配管道。
◆利用AV1视频编解码器固有的运动向量进行特征匹配，绕过了计算昂贵的穷举匹配，同时保持了几何鲁棒性。
◆该管道能生成比传统SfM密集最多八倍的点云，有效解决了无纹理区域的稀疏性问题。
这种增强的密集初始化直接提升了3DGS的整体性能表现。
实验表明，该方法使VMAF指标提升了9分，且达到基准质量所需的平均训练时间减少了63%，显著提高了重建效率和视觉保真度。</td></tr>
<tr><td>2026-05-12</td><td>WildPose: A Unified Framework for Robust Pose Estimation in the Wild<br><a href='http://arxiv.org/pdf/2605.12774'>论文</a></td><td>本文提出了WildPose，一个统一的单目位姿估计框架，有效解决了动态环境下的位姿估计难题，同时在纯静态和低自运动场景中保持SOTA性能。
◆创新性地将前馈模型的丰富感知前端与可微束调整的端到端优化两种强大范式相连接。
◆基于冻结的预训练MASt3R特征骨干构建了3D感知更新算子，强化了模型的3D空间理解与特征关联能力。
◆设计了高容量运动掩码检测器，利用同一骨干网络提取的多级3D感知特征精准识别并屏蔽动态物体干扰。
广泛的实验证明，该框架在动态、静态及低自运动等多种基准测试上均持续超越现有方法。</td></tr>
<tr><td>2026-05-12</td><td>3D Gaussian Splatting for Efficient Retrospective Dynamic Scene Novel View Synthesis with a Standardized Benchmark<br><a href='http://arxiv.org/pdf/2605.12437'>论文</a></td><td>本文针对同步多视角动态场景的回顾式新视角合成问题，提出在具备强几何约束的同步多视角设置下，无需使用显式时间耦合或复杂多体约束。
◆提出一种无时间变形约束的3D高斯溅射方法，通过初始化起始时刻的SfM点云并随时间传播优化高斯，实现高效的动态场景新视角合成。
◆构建基于Blender的动态多视角数据集生成框架，能生成高质量同步摄像机阵列并以标准格式导出，消除坐标系与数据流水线的不一致性。
◆利用该框架创建动态基准测试套件，在受控条件下对代表性NeRF和3DGS方法进行标准化评估，推动动态新视角合成方法可复现性研究。
研究表明，在同步多视角配置下仅用3D高斯溅射即可高效实现动态场景合成，同时提供的数据框架填补了该领域标准化基准的空白。</td></tr>
<tr><td>2026-05-12</td><td>Compositional Neural Operators for Multi-Dimensional Fluid Dynamics<br><a href='http://arxiv.org/pdf/2605.11691'>论文</a></td><td>本文针对科学基础模型预训练成本高且缺乏可解释性的问题，提出了用于二维流体动力学的组合神经算子框架。该框架的核心思想是将复杂偏微分方程分解并预训练为一系列基础物理算子。
◆构建了包含对流、扩散、非线性对流专用算子及泊松求解器的模块化库，有效解决了不可压缩流体中的压力与速度耦合问题。
◆设计了带有聚合器的适应模块，通过最小化数据损失和源自控制方程的物理残差来学习基础算子间的非线性相互作用。
在对流扩散、伯格斯和纳维-斯托克斯方程上的实验表明，该方法显著提升了模型对新物理系统的适应性与可解释性，并促进了预训练模块的高效复用。</td></tr>
<tr><td>2026-05-11</td><td>3DReflecNet: A Large-Scale Dataset for 3D Reconstruction of Reflective, Transparent, and Low-Texture Objects<br><a href='http://arxiv.org/pdf/2605.10204'>论文</a></td><td>本文针对反射、透明和弱纹理物体3D重建的难题，提出了超大规模混合数据集3DReflecNet。
◆构建了超22TB的大规模混合数据集，包含逾12万个基于物理渲染的合成实例与1千多个真实世界物体，总计超700万帧多视角图像。
◆数据涵盖多种材质、复杂光照及广泛几何形态，并创新性地利用扩散模型管道从真实与LLM合成的2D图像生成3D形状。
◆为图像匹配、运动恢复结构、新视角合成、反射去除和重照明五个核心任务设计了评估基准。
大量实验证明现有先进方法在这些复杂材质下难以保持精度，凸显了该数据集对推动鲁棒3D视觉模型发展的重要价值。</td></tr>
<tr><td>2026-05-11</td><td>BathyFacto: Refraction-Aware Two-Media Neural Radiance Fields for Bathymetry<br><a href='http://arxiv.org/pdf/2605.10174'>论文</a></td><td>BathyFacto是一种集成于Nerfstudio的折射感知双介质神经辐射场方法，旨在解决浅水测深中水面折射导致的深度偏差，生成高精度水下点云。
◆提出基于共享哈希网格密度场与介质条件颜色头的双段光线追踪机制，依斯涅尔定律将光线分为空气直线段与水中折射段渲染。
◆设计折线密度包装...[摘要不完整，待更新]</td></tr>
<tr><td>2026-05-08</td><td>TriP: A Triangle Puzzle Approach to Robust Translation Averaging<br><a href='http://arxiv.org/pdf/2605.07143'>论文</a></td><td>本文提出了TriP，一种基于三角形的鲁棒平移平均框架，旨在从成对相对平移方向中恢复相机位置。
◆利用三角形几何推断局部边尺度，并在对数域同步重叠三角形的尺度以恢复全局边长，通过高阶一致性有效对抗恶意与结构化腐蚀。
◆无需额外反塌缩约束即可避免塌缩问题，因为对数尺度同步在构造上直接排除了退化的零尺度解。
◆为精确的相机位置恢复提供了极强的理论保证。
该方法完全可并行化且计算高效，能自然扩展至数百万相机的图。
在合成和真实数据集上的实验表明，TriP大幅超越了所有现有的平移平均方法。</td></tr>
<tr><td>2026-05-06</td><td>egenioussBench: A New Dataset for Geospatial Visual Localisation<br><a href='http://arxiv.org/pdf/2605.05351'>论文</a> | <a href='https://github.com/fratopa/egenioussBench'>代码</a></td><td>◆ We present egenioussBench, a visual localisation benchmark built on geospatial reference data: a city-scale airborne 3D mesh and a CityGML LoD2 model.
◆ This pairing reflects deployable mapping assets and supports true scalability beyond traditional SfM-based approaches.
◆ The query data comprise smartphone images with centimetre-accurate, map-independent ground truth obtained via PPK and GCP/CP-aided adjustment.</td></tr>
<tr><td>2026-05-03</td><td>DP-SfM: Dual-Pixel Structure-from-Motion without Scale Ambiguity<br><a href='http://arxiv.org/pdf/2605.01852'>论文</a> | <a href='https://github.com/lilika-makabe/dp-sfm-tpami.git'>代码</a></td><td>◆ Multi-view 3D reconstruction, namely, structure-from-motion followed by multi-view stereo, is a fundamental component of 3D computer vision.
◆ In general, multi-view 3D reconstruction suffers from an unknown scale ambiguity unless a reference object of known size is present in the scene.
◆ In this article, we show that multi-view images captured using a dual-pixel (DP) sensor can automatically resolve the scale ambiguity, without requiring a reference object or prior calibration.</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='image-matching'>Image Matching (20篇)</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-15</td><td>Breaking Déjà Vu: Independent Auditing of Visual Place Recognition through Vision-Language Reasoning<br><a href='http://arxiv.org/pdf/2607.12818'>论文</a></td><td>本文针对视觉位置识别（VPR）在机器人SLAM应用中因依赖固定阈值而难以应对环境变化、易接受错误闭环的问题，提出了视觉位置识别审计（VPR Auditing）这一独立的后检索验证框架。该方法利用视觉语言模型（VLM）对查询图像和候选图像进行联合推理，实现实例级匹配验证，摆脱了对特定架构置信度、数据集阈值和部署环境先验知识的依赖。

◆ 提出独立审计框架：将验证环节与原始VPR检索解耦，作为后处理模块独立审计检索结果，无需修改现有VPR系统。
◆ 基于VLM的联合推理机制：通过对查询-候选图像对的语义级推理进行匹配评估，具备跨场景泛化能力。
◆ 全面性能提升：在六个基准数据集、五种VPR方法和四种VLM上的实验表明，平均recall@1提升13.6%，误接受率降至12%，精度保持在95%以上，覆盖率超过75%，显著优于现有验证方法。</td></tr>
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
<tr><td>2026-07-01</td><td>SOCO: Benchmarking Semantic Object Correspondence in Vision Foundation Models<br><a href='http://arxiv.org/pdf/2605.31597'>论文</a></td><td>本文提出SOCO基准，旨在解决视觉基础模型中结构化对象理解评估协议不一致和部件级监督有限的问题。
◆构建了包含对应类型分类法的语义对象对应基准，在100个类别和超百万对应对上提供一致且具功能意义的关键点标注。
◆引入关键点语言描述，支持对大型视觉语言模型细粒度部件级理解能力的系统评估。
◆揭示视觉骨干网络虽编码强语义结构，但跨类别迁移对应能力差且仅部分捕获部件位置。
◆发现大视觉语言模型擅长文本提示定位但视觉参考跨图匹配较弱，暴露语言接地与视觉对应间的鸿沟。
◆证明对应性能比ImageNet分类性能更能强有力地预测分割、跟踪及3D检测等密集下游任务的表现。</td></tr>
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
<tr><td>2026-05-29</td><td>MAPRPose: Mask-Aware Proposal and Amodal Refinement for Multi-Object 6D Pose Estimation<br><a href='http://arxiv.org/pdf/2604.20650'>论文</a></td><td>本文针对杂乱场景中严重遮挡和噪声导致的6D姿态估计难题，提出了MAPRPose两阶段框架。
◆在姿态提案阶段，将2D对应关系提升至3D空间建立可靠关键点匹配，基于对应级评分生成几何一致的姿态假设选出Top-K候选。
◆在细化阶段引入AMPR模块，通过重建完整物体几何与动态调整ROI，有效缓解重度遮挡下的定位误差和空间错位。
◆设计GPU加速的RGB-XYZ重投影机制，在张量化渲染比较管线中实现单次前向传播同步细化所有姿态假设。
该方法在BOP基准上取得76.5%的最优平均召回率，精度超越FoundationPose 3.1%，且多目标推理速度提升43倍。</td></tr>
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
<tr><td>2026-05-01</td><td>Are Pretrained Image Matchers Good Enough for SAR-Optical Satellite Registration?<br><a href='http://arxiv.org/pdf/2604.10217'>论文</a></td><td>◆ Cross-modal optical-SAR (Synthetic Aperture Radar) registration is a bottleneck for disaster-response via remote sensing, yet modern image matchers are developed and benchmarked almost exclusively on natural-image domains.
◆ We evaluate twenty-four pretrained matcher families--in a zero-shot setting with no fine-tuning or domain adaptation on satellite or SAR data--on SpaceNet9 and two additional cross-modal benchmarks under a deterministic protocol with tiled large-image inference, robust geometric filtering, and tie-point-grounded metrics.
◆ Our results reveal asymmetric transfer--matchers with explicit cross-modal training do not uniformly outperform those without it.</td></tr>
<tr><td>2026-05-01</td><td>TrueEBSD in MTEX: automatic image matching for correlative microscopy applications<br><a href='http://arxiv.org/pdf/2605.00703'>论文</a></td><td>◆ TrueEBSD is an open-source MATLAB program for image alignment and spatial distortion correction of images and electron backscatter diffraction (EBSD) maps.
◆ We have re-implemented TrueEBSD as an add-on to MTEX, an established toolbox for EBSD data analysis.
◆ Spatial alignment enables correlative analysis methods, such as augmenting EBSD orientation maps with data from other imaging modes.</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='obstacle-avoidance'>Obstacle Avoidance (137篇)</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-16</td><td>Learning Agile Navigation in Crowded Environments for Quadruped Robots<br><a href='http://arxiv.org/pdf/2607.15036'>论文</a></td><td>针对四足机器人在动态拥挤环境中导航的难题,本文提出VOP-Nav系统,融合速度障碍法的几何安全性与端到端学习的敏捷适应性。该系统仅依赖局部激光雷达观测,避免显式障碍物检测与跟踪流程,有效应对传感器遮挡问题。

◆创新点一:设计VOP-Net网络处理多帧LiDAR数据,隐式编码动态约束并预测基于速度障碍理论的安全速度区域,无需显式运动估计。

◆创新点二:将VO预测结果同时作为推理时的导航策略输入和训练时的奖励信号,实现双重作用,引导策略学习安全运动。

◆创新点三:在Isaac Gym仿真中取得高于所有基线方法的成功率,同时兼顾运动速度与避障能力。

◆创新点四:在Unitree Go2四足机器人上的真实部署验证了系统在复杂室内外动态环境中的鲁棒性与高效性。</td></tr>
<tr><td>2026-07-16</td><td>CosFly-VLA: A Spatially Aware Vision-Language-Action Model for UAV Tracking<br><a href='http://arxiv.org/pdf/2607.15004'>论文</a></td><td>该论文针对无人机在复杂城市环境中跟踪动态目标时面临的遮挡问题，提出了一种空间感知的视觉-语言-动作模型CosFly-VLA。该模型通过结构化预测接口联合实现目标定位、可见性估计和连续飞行动作生成，在目标被遮挡时仍能保持鲁棒的跟踪能力。

论文设计了一套大规模训练流程，包括在50万混合数据上进行空间基础继续预训练以注入深度、距离和三维空间推理能力，随后通过三阶段课程监督微调和思维链训练强化遮挡恢复推理能力，最后采用多组件奖励的强化学习阶段优化闭环跟踪行为。

◆在架构层面，提出统一的结构化预测接口，将目标定位、可见性估计和连续动作生成融合在单一VLA框架中，使模型能够在遮挡场景下做出空间感知的恢复性决策。

◆在训练策略层面，结合继续预训练、课程学习、思维链推理和强化学习的多阶段训练方法，显著提升模型对长时遮挡的鲁棒性和空间推理能力。

◆在实验效果层面，相比OpenVLA基线，CosFly-VLA-0.8B在开环和闭环评估中均取得显著提升，验证了从可见帧模仿到空间基础动作闭环控制的进展。</td></tr>
<tr><td>2026-07-16</td><td>Modeling and Validation of Quality of Control for Edge-Offloaded Collaborative Navigation<br><a href='http://arxiv.org/pdf/2607.14853'>论文</a></td><td>本文针对复杂环境下协作控制面临的无线时延随机性和可靠性变化问题，将原有的控制质量（QoC）框架扩展到实际机器人模型中，研究边缘卸载协作导航场景下的端到端网络效应对闭环性能的影响。论文系统性地探索了机器人运动控制参数对网络时延-可靠性的作用机制，并基于私有5G测试平台，在不同时延、可靠性和控制配置下进行了实验验证。研究给出了实际机器人系统的最优控制-通信协同设计工作区间，并对比了ROS 2标准QoS策略在真实条件下的QoC表现，发现RELIABLE策略在特定实验设置下比BEST-EFFORT策略的QoC提升51.5%。

◆ 创新点一：将QoC框架从抽象模型扩展到包含动态避障的实际机器人导航系统，实现了端到端网络效应对闭环控制性能的建模。

◆ 创新点二：系统性地分析了机器人运动控制参数与网络时延-可靠性之间的耦合关系，揭示了控制-通信协同设计的最优工作区域。

◆ 创新点三：在私有5G测试平台上进行了多维度实验验证，并定量比较了ROS 2不同QoS策略的实际QoC性能差异。</td></tr>
<tr><td>2026-07-16</td><td>NavCMPO: Critic-Guided MeanFlow Policy Optimization for Adaptive Navigation<br><a href='http://arxiv.org/pdf/2607.14643'>论文</a></td><td>NavCMPO提出了一种两阶段自适应导航框架,旨在解决端到端扩散策略在无地图视觉导航中推理延迟高以及行为克隆性能受限的问题。该方法通过少量步数的MeanFlow轨迹生成显著降低推理时延,并结合基于障碍物点云监督训练的评论家网络进行轨迹细化,在预训练阶段引入障碍物邻近度预测任务以增强视觉表征的避障能力。论文在InternVLA-N1基准上以匹配的训练预算取得了74.7%的平均成功率,较基线提升6.4个百分点,同时将推理延迟从85毫秒降至60毫秒,并在Unitree Go2上验证了良好的仿真到真实迁移效果。

主要创新点如下:

◆ 采用少量步数MeanFlow替代传统多步扩散,大幅降低轨迹生成的推理延迟,实现高效实时导航。

◆ 提出基于评论家梯度的轨迹细化方法CGTR,利用障碍物点云监督训练的评论家网络补偿少步生成带来的避障性能退化。

◆ 设计障碍物邻近度预测预训练任务,引导视觉编码器学习障碍感知的空间表征,提升对环境结构的理解。

◆ 在自适应阶段结合PPO强化学习微调与行为克隆正则化,并同步更新评论家以适应不同机器人本体观测变化,实现跨平台迁移。</td></tr>
<tr><td>2026-07-16</td><td>3D Geometric Tooth Alignment Planning via Deep Reinforcement Learning<br><a href='http://arxiv.org/pdf/2607.14544'>论文</a></td><td>该论文提出了一种基于深度强化学习的3D牙齿正畸对齐规划框架，将牙齿移动序列的规划问题建模为马尔可夫决策过程，以捕捉其顺序决策特性，并融合牙齿间碰撞避免与路径效率等空间约束。方法采用深度确定性策略梯度算法作为基础，并在10K例专家设计的临床正畸方案数据集上进行了验证，实验表明在路径安全性和几何效率方面均优于现有基线方法。

◆ 基于Transformer的智能体：有效建模牙齿之间复杂的空间交互关系，并应对高维状态-动作空间带来的挑战。

◆ 动态掩码机制：每步仅允许稀疏子集的牙齿进行移动，更贴合临床中分阶段、顺序调整的逻辑。

◆ 两阶段课程学习策略：逐步增加任务难度，提升训练稳定性并加速有效路径的发现。</td></tr>
<tr><td>2026-07-15</td><td>Discriminative Barrier Functions for Safe Adversarial Imitation Learning from Observation<br><a href='http://arxiv.org/pdf/2607.13938'>论文</a></td><td>这篇论文针对逆强化学习(IRL)依赖无约束探索导致实际部署不安全的问题,以及控制屏障函数(CBF)需要人工解析设计耗时困难的问题,提出了一种将两者优势结合的安全对抗式模仿学习框架。该方法通过将IRL中的奖励函数候选空间约束为CBFs空间,实现了从无标签专家观测中数据驱动地恢复屏障函数,并在保证安全的前提下支持在线控制与持续经验改进。

◆ 提出将IRL奖励函数候选空间限制为CBFs空间的新框架,首次实现了从无标签专家观测中自动恢复屏障函数
◆ 证明了恢复的屏障函数对专家数据中完全缺失的不安全状态具有鲁棒性
◆ 在仿真导航环境中系统对比了所提方法与标准IRL基线的安全性能,验证了显著改进
◆ 在仿真和真实世界避障任务中,深入分析了基于规划与基于策略的IRL方法之间的权衡

该工作为安全模仿学习从观察提供了一种理论严谨且可数据驱动的新方案,具有实际部署价值。</td></tr>
<tr><td>2026-07-14</td><td>MAMMOTH: A Multi-Modal End-to-End Policy for Off-Road Mobility Robust to Missing Modality<br><a href='http://arxiv.org/pdf/2607.12965'>论文</a></td><td>MAMMOTH是一种面向越野自主导航的端到端统一策略，旨在解决复杂非结构化环境中因光照剧烈变化和传感器退化导致的可靠性问题。该方法通过高效融合RGB、热成像、3D点云和自车速度等多模态观测，显著提升了对极端光照和恶劣地形的适应性。为克服现有方法对完整传感器输入的刚性依赖，模型在训练阶段引入模态随机丢弃机制，使其在推理时能够稳健应对任一模态缺失甚至完全失效的情况。此外，MAMMOTH采用扩散策略联合建模物理可行轨迹与内在可通行性启发式，使规划结果倾向于更安全、平滑的路径。该工作通过包含夜间场景在内的真实机器人实验进行了充分验证，在避障、地形感知规划及模态缺失泛化能力上均表现优异。代码与数据集将公开以促进后续研究。

◆ 提出融合RGB、热成像、3D点云与自车速度的统一端到端越野导航策略，提升对光照剧变和传感器退化的鲁棒性。
◆ 引入模态随机丢弃训练机制，使模型在推理时能稳健应对任意模态缺失或完全失效。
◆ 采用扩散策略联合建模物理可行轨迹与可通行性启发式，倾向于规划更安全平滑的路径。
◆ 支持视觉目标条件导航与无方向探索两种任务模式，并在真实夜间越野环境中完成验证。</td></tr>
<tr><td>2026-07-14</td><td>Globalized Constrained Stein Variational Inference for Diverse Feasible Robot Motion Planning<br><a href='http://arxiv.org/pdf/2607.12732'>论文</a></td><td>该论文针对机器人运动规划中多模态解与严格约束并存的核心难题,提出了一种名为SteinSQP(Stein变分序列二次规划)的新方法,在保证所有粒子满足碰撞避免、关节限制、接触条件及动力学一致性等硬约束的同时,维持解集的多样性,以覆盖多条低代价运动路径。

◆ 提出SteinSQP方法,将约束直接嵌入核空间下的SQP子问题,实现了变分推断与约束优化的统一框架,使粒子群在迭代过程中始终朝向可行且多样的低代价区域演化。

◆ 设计了GPU友好的无矩阵原始-对偶算法求解约束Stein-Newton子问题,支持批量粒子同步更新,显著提升计算效率。

◆ 引入粒子集合层面的全局价值函数,联合权衡目标函数值、约束违背程度与粒子多样性,实现了方法的全局收敛性。

◆ 在五类约束运动规划任务上的实验表明,SteinSQP在迭代次数、粒子可行性及批处理求解时间上均优于一阶约束Stein基线与串行多起点非线性规划方法,验证了其在机器人尺度复杂任务中的有效性与鲁棒性。</td></tr>
<tr><td>2026-07-14</td><td>Improving Autonomous Nano-drones Performance via Automated End-to-End Optimization and Deployment of DNNs<br><a href='http://arxiv.org/pdf/2607.12593'>论文</a></td><td>该论文针对亚10厘米纳米无人机的视觉自主导航任务，提出了一套端到端自动化的CNN部署流程，将PULP-Dronet神经网络从训练、优化到最终在Crazyflie 2.1超低功耗多核SoC上的闭环部署进行了全流程整合。相较于原始手工设计的网络，自动化流程在保持预测精度的同时，将内存占用缩减了2倍，推理速度提升了1.6倍，计算功耗仅占无人机总预算的1.6%以下。论文核心贡献与创新点如下：

◆ 构建了首个覆盖训练、优化到部署的端到端自动化工具链，取代了传统易错且劳动密集型的迭代开发流程。

◆ 提出了针对ULP多核SoC的CNN自动压缩与优化方法，在内存和推理速度上实现双重显著提升。

◆ 实现了卓越的实地飞行性能：障碍物躲避峰值制动速度达1.65 m/s，陌生环境自由飞行速度达1.96 m/s，并能完成90度弯道路径跟踪。

◆ 开源了与Crazyflie 2.1即用兼容的完整软件项目，促进该领域后续研究与新应用的开发。</td></tr>
<tr><td>2026-07-14</td><td>StratMamba: Strategic and Reactive Stream Partitioning for Path-Efficient LiDAR-Based Obstacle Avoidance<br><a href='http://arxiv.org/pdf/2607.12370'>论文</a></td><td>本文提出StratMamba，一种基于双流Mamba的时序建模架构，用于解决机器人在复杂障碍物环境中导航时对长时程依赖的建模问题。其核心思想是借鉴人类认知中的战略与反应分离机制，将记忆系统划分为快速衰减与慢速衰减两条并行流，分别承担不同时间尺度的任务。

◆ 创新点1：提出双流Mamba架构，结合快衰减与慢衰减记忆机制，分别处理高频LiDAR数据用于反应式避障，以及长时程目标信息用于战略性规划。

◆ 创新点2：在IsaacLab、Gazebo仿真及Unitree GO1四足机器人真机部署中验证了方法的有效性，展示了良好的sim-to-real迁移能力。

◆ 创新点3：相比LSTM、Transformer和Vanilla-Mamba等基线，在超时率、导航速度（576中位步数，比Vanilla-Mamba提升5.0%）和路径最优性（0.915）上均达到最优。

◆ 创新点4：双流划分设计使模型在扩展LiDAR感知范围下保持更鲁棒的性能，有效平衡了反应式安全与战略性导航之间的矛盾。</td></tr>
<tr><td>2026-07-13</td><td>More than a Manipulator: Planning Propellant-Free Attitude Maneuvers for Free-Floating Spacecraft<br><a href='http://arxiv.org/pdf/2607.12130'>论文</a></td><td>本论文针对自由漂浮航天器,提出了利用机械臂运动实现无推进剂姿态控制的新方法,突破了传统上将机械臂视为干扰源而非控制执行器的设计范式。研究者将该问题建模为一个带有关节限位和碰撞规避约束的轨迹优化非线性规划问题,并采用内点法求解器进行了高效求解。通过对不同运动学复杂度和质量参数航天器-机械臂系统的仿真,论文展示了复杂的回转(Slew)与消旋(Detumble)机动轨迹,并通过动量与力矩包络与反作用轮阵列的控制能力进行了直接对比,验证了机械臂作为冗余乃至主用姿态控制执行机构的可行性。

本文的核心创新点可总结如下:

◆ 提出将机械臂运动作为无推进剂姿态控制执行机构的全新设计理念,改变其传统&quot;干扰源&quot;角色定位。

◆ 构建了考虑关节限位、碰撞规避等关键约束的轨迹优化框架,实现复杂机动任务的安全规划。

◆ 通过动量与力矩包络对比方法,量化评估了机械臂相对反作用轮阵列的控制权限能力。

◆ 拓展了机械臂在太空组装与制造等任务中的多用途功能,尤其适用于抓取大质量比载荷的场景。</td></tr>
<tr><td>2026-07-12</td><td>Self-Healing Coordination in Cognitive Swarm Agents with Bloch-Type Perceptual Memory<br><a href='http://arxiv.org/pdf/2607.11960'>论文</a></td><td>本文针对反应式群集模型缺乏内部感知状态调节恢复过程的局限，提出了一种基于Bloch型慢-快架构的认知群智能体自愈协调机制。每个智能体携带一个有界的Bloch型感知寄存器，并与慢速调节状态耦合，形成闭合的慢-快回路，其中感知记忆被操作性地定义为回路内历史依赖的线索解析过程。该架构在非周期、障碍密集的无人机迁徙任务中进行了多种子消融实验，评估恢复时间、最大集群重建、极性序、局部一致性、碰撞风险和路径效率等指标。实验结果表明，闭合慢-快回路主要功能影响体现在自愈能力上：障碍引发群体破碎后，该机制能显著加速空间连通性的恢复，而解耦的慢速迹线则退化为无记忆控制器。

◆ 将Bloch型动力学作为保正性有效机制引入群智能体的感知记忆建模，明确其非量子微观描述的工程定位。

◆ 提出慢-快耦合的闭合回路架构，将感知寄存器与调节状态整合，实现历史依赖的线索解析。

◆ 首次系统验证Bloch型感知记忆在障碍诱导破碎后对空间连通性恢复的加速作用，揭示自愈协调的内部机制。

◆ 通过与无记忆基线和部分反馈基线的多种子对比，澄清了耦合结构而非单纯慢速记忆是自愈能力的关键。</td></tr>
<tr><td>2026-07-11</td><td>Navigating the Crowd: Non-linear MPC with Social Forces Dynamics for Human-Aware Robot Navigation<br><a href='http://arxiv.org/pdf/2607.10374'>论文</a></td><td>该论文针对机器人在人群环境中的安全与社交合规导航问题，提出了SFM-NMPC框架，将社会力模型（Social Force Model）嵌入非线性模型预测控制（NMPC）的优化过程中。该方法将社会力模型整合到周围行人的动态模型中，使控制器能够在预测时域内联合预测人类和机器人的轨迹，实现社交感知的运动规划。

◆创新点一：将社会力模型直接嵌入NMPC的动力学模型中，把人类运动预测融入优化闭环，突破了传统方法将预测与控制分离的局限。
◆创新点二：设计了针对社交合规性的代价函数集合，引导优化过程产生尊重个人空间、符合人类舒适度的行为。
◆创新点三：尽管模型复杂度增加，算法仍以20 Hz的频率实时运行，兼顾了计算效率与社会合规性。
◆创新点四：在拥挤仿真环境中的大量测试表明，该方法在社交合规指标上优于现有先进基线，并通过消融实验验证了社会力动力学和社交代价项各自的有效性。</td></tr>
<tr><td>2026-07-11</td><td>Robotic Contextual Awareness for Human-Robot Collaboration and Environmental Understanding<br><a href='http://arxiv.org/pdf/2607.10372'>论文</a></td><td>该论文针对自主移动机器人在动态人机共存环境中缺乏上下文感知能力这一核心挑战，从人机协作和环境理解两个互补方向展开研究，旨在提升机器人对周围空间、物体及人员的综合感知与理解能力，使其能够进行自适应行为规划并与人类进行自然交互。

◆ 提出基于人重识别与跟踪的移动机器人定向协作方法，使机器人能够识别特定目标人物并选择性地与该人员协作，同时忽略环境中的其他个体，从而提升人机协作的针对性与安全性。

◆ 构建几何与语义相结合的环境感知框架，其中几何信息支撑运动规划与避障，语义信息赋予机器人对场景的高层次理解，为复杂交互任务提供丰富的环境知识。

◆ 将人重识别与场景理解技术深度融合，统一于机器人上下文感知的整体架构中，增强了机器人对&quot;人-物-环境&quot;三者关系的语义理解能力。

◆ 通过上述两大方向的协同推进，论文为人机共存场景下机器人的安全自主运行和有效协作提供了系统性的解决方案，向更具情境感知能力的下一代机器人迈出了重要一步。</td></tr>
<tr><td>2026-07-10</td><td>SEAMLiS: Visibility-Aware Safety for Perception-Limited Multi-Robot Exploration<br><a href='http://arxiv.org/pdf/2607.09959'>论文</a></td><td>本文针对有限感知范围下多机器人自主探索中上层规划过于乐观、障碍物发现过晚导致无法及时避碰的问题，提出SEAMLiS模块化执行层安全框架。该框架与上游目标分配器和局部规划器完全解耦，通过感知感知的态度和位置滤波器在执行层强制施加安全约束。

◆ 模块化执行层安全架构：将安全保证从探索规划中分离，作为独立中间层接入分布式探索系统，无需修改原有规划算法即可提升安全性。
◆ 门控式态度滤波器：在促进可见性的偏航策略与速度跟踪备份策略之间智能切换，确保对已知自由区域与未知区域的边界始终保持具有足够制动余量的观测。
◆ 基于控制障碍函数的位置滤波器：统一处理已知障碍、新检测障碍及其他机器人的避碰问题，并给出充分的避碰条件理论保证。
◆ 多平台验证：在随机仿真、Isaac Sim及Crazyflie四旋翼硬件实验中均实现零碰撞探索，同时保留了可见性偏航控制带来的效率优势。</td></tr>
<tr><td>2026-07-08</td><td>LAMP: Long-Horizon Adaptive Manipulation Planning for Multi-Robot Collaboration in Cluttered Space<br><a href='http://arxiv.org/pdf/2606.29358'>论文</a></td><td>◆论文提出LAMP框架，面向密集杂乱空间中的长时域多机器人协同操作，联合考虑接触构型、机器人运动、耦合动力学与避碰。

◆核心创新是将学习到的生成式操作模型嵌入规划过程，从而在完整的物体—机器人耦合空间中进行更可 tractable 的搜索。

◆提出LAMPA*规划器，系统化搜索长时域任务中的接触与运动决策，避免仅规划简化物体轨迹带来的局限。

◆提出LAMP-Lazy惰性规划器，通过延迟评估降低计算开销，支持实时重规划。

◆实验表明，该方法能解决以往强化学习或短视接触原语方法难以处理的高密度、长时域多机器人操作任务。</td></tr>
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
<tr><td>2026-07-08</td><td>Time-to-Collision Based Dynamic Obstacle Avoidance Using Pretrained Vision Models for Robots in Unstructured Environments<br><a href='http://arxiv.org/pdf/2607.07885'>论文</a></td><td>这篇论文提出了一种基于视觉的动态障碍物避障方法,完全基于真实世界数据运行,有效避免了仿真训练策略中的sim-to-real迁移难题。该方法利用预训练的单目深度估计模型UniDepth从RGB视频生成稠密深度图,无需依赖立体相机或激光雷达;同时扩展了SuperPoint和SuperGlue特征匹配流程以实现长序列关键点跟踪,结合相机内参与预测深度将2D像素位置投影到3D空间,并通过光束法平差优化后计算每个关键点的碰撞时间(TTC),据此选取规避运动方向。

◆ 利用预训练UniDepth从单目RGB获取稠密深度,推理阶段无需立体相机或激光雷达
◆ 扩展SuperPoint/SuperGlue实现长序列关键点跟踪并投影到3D空间构建运动轨迹
◆ 基于光束法平差后的3D关键点计算每点TTC,以最小TTC点驱动2D运动基元选择
◆ 纯几何可解释的模块化流水线,完全无需模型训练,仅用74秒数据即可完成超参调优

在M3ED真实数据集上的评估表明,该方法在识别TTC小于1秒的帧时达到0.49的精度和0.38的召回率,并在84%的真阳性中正确生成规避方向,对22个独特物理障碍物中的20个能成功检测出至少一帧TTC低于1秒的情况,展现了出色的数据效率与泛化能力。</td></tr>
<tr><td>2026-07-06</td><td>Dynamic Airspace Management for UAVs in Evolving Urban Environments: Collaborative Coordination and Human Safety<br><a href='http://arxiv.org/pdf/2607.04825'>论文</a> | <a href='https://github.com/pharos-anonymized/source-code.git'>代码</a></td><td>本文针对城市低空经济中无人机安全飞行的关键挑战,提出了名为Pharos的协同多无人机空域管理系统,旨在解决复杂城市地形和人口密集环境下的避碰与人员安全问题。Pharos采用介于分布式局部感知与集中式精细化控制之间的混合范式,协调共享空域中多架无人机的安全并行飞行,并创新性地将人类恐惧心理纳入决策考量。该系统基于MAPPO多智能体强化学习算法实现,相较于HAPPO和HATRPO等同类算法具有更快的收敛速度和更高的奖励回报。作者基于真实城市数据构建了三维仿真平台进行评估,可视化结果验证了其有效的空域协调能力,人类恐惧程度较基准方法Ipopt降低52.72%。

◆ 提出了Pharos协同空域管理系统,首次将人类恐惧心理作为决策因素纳入多无人机空域管理,平衡了分布式与集中式控制范式的优劣。
◆ 创新性地引入空间熵作为系统评估指标,量化空域利用效率,较Ipopt和A-star分别提升70.82%和2.03%。
◆ 基于MAPPO算法实现快速收敛与高效协同,并搭建了基于真实城市数据的三维仿真验证平台。</td></tr>
<tr><td>2026-07-05</td><td>GPU-Accelerated Polygonal Signed Distance Functions for Real-Time Collision Avoidance<br><a href='http://arxiv.org/pdf/2607.04310'>论文</a></td><td>该论文针对密集障碍物场景下基于优化的局部规划与控制中碰撞约束计算耗时的问题，提出了一种几何精确的多边形符号距离函数（PSDF）及其在模型预测控制中的高效应用方案。

◆ 提出PSDF：基于凸多边形机器人轮廓与障碍物边界边的几何精确符号距离函数，采用无权重无分支的张量化几何流水线，支持批量GPU执行与自动微分。

◆ 设计PSDF-MPC控制器：在基于SQP的实时迭代方案中通过局部线性化嵌入分阶段安全约束，将计算任务分配至CPU与GPU，CPU负责求解低维稀疏二次规划，GPU批量评估PSDF值与梯度，QP维度仅取决于系统维度与预测时域，与障碍物特征无关。

◆ 微基准测试显示PSDF相对现有符号距离查询基线具有更优的可扩展性。

◆ 闭环仿真与真实世界导航实验证明了PSDF-MPC在密集多边形环境中能够保持实时可行性和鲁棒避障能力。</td></tr>
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
<tr><td>2026-07-01</td><td>Neuro-Symbolic Safety Guidance for Vision-Language-Action Models via Constrained Flow Matching<br><a href='http://arxiv.org/pdf/2607.01378'>论文</a></td><td>本文针对视觉-语言-动作(VLA)模型在机器人操控中缺乏有效安全机制的问题,提出了一种基于神经-符号融合的安全引导方法。现有安全方法仅能防止机器人下一步动作的碰撞,属于被动反应式防护,而该工作通过在流匹配去噪过程中引入约束优化,实现了对整条预测轨迹的前瞻式安全分析。

◆ 核心创新在于将安全约束建模为最小范数约束优化问题,在流匹配去噪的每一步迭代中对中间轨迹进行符号化修正,从而在碰撞不可避免之前提前进行干预。

◆ 方法通过神经轨迹生成与符号约束满足的交替执行,使系统具备预测性碰撞规避能力,显著区别于传统的反应式安全策略。

◆ 在SafeLIBERO基准上,该方法达到82.8%的碰撞避免率和81.6%的任务成功率,较单步方法分别提升6.3%和19.8%,且在长时序任务中因复合分布偏移而获益最为显著。</td></tr>
<tr><td>2026-06-29</td><td>Multi-UAV Formation Cooperative Obstacle Avoidance and Adaptive Shape Deformation Control in Complex Environments Based on BI-APF-RRT and Affine Transformation<br><a href='http://arxiv.org/pdf/2606.29755'>论文</a></td><td>◆论文提出一种融合BI-APF-RRT与仿射变换的多无人机编队协同避障方法，兼顾复杂环境中的避障灵活性与编队完整性。
◆采用目标偏置的双向APF-RRT替代传统APF质心规划，提升全局路径搜索效率并降低陷入局部最优的风险。
◆通过改进人工势场与三次B样条插值，增强质心路径的平滑性、收敛速度和可飞行性。
◆引入包含非均匀缩放与旋转的仿射变换矩阵，使编队能根据障碍物距离自适应变形。
◆设计分布式跟踪控制律，使跟随者协同跟踪领航者，实现编队在不解散的情况下安全穿越复杂障碍区域。</td></tr>
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
<tr><td>2026-06-25</td><td>G2DP: Diffusion Planning with Spatio-Temporal Grid Guidance<br><a href='http://arxiv.org/pdf/2606.26017'>论文</a></td><td>◆提出G2DP，一种网格引导的扩散式自动驾驶规划器，解决传统扩散规划随机性强、闭环执行中安全与路线约束不足的问题。
◆其核心创新是构建可微的时空代价体，将未来占用概率分布与路线进度图融合，形成密集环境约束。
◆方法把该代价体建模为连续安全能量函数，并在推理去噪过程中直接注入梯度，引导轨迹远离碰撞区域并保持路线进展。
◆相比依赖稀疏几何查询或后处理优化的方法，G2DP具备更强的场景感知能力，尤其适合复杂交互交通。
◆实验表明，G2DP在nuPlan闭环评测达到SOTA，并在interPlan和DeepScenario零样本迁移中保持优异鲁棒性。</td></tr>
<tr><td>2026-06-25</td><td>Large-Scale Tunnel Air-Ground Collaboration With FLISP: Fast LiDAR-IMU Synchronized Path Planner<br><a href='http://arxiv.org/pdf/2606.25393'>论文</a> | <a href='https://github.com/ArchibaldGuo/FLISP.git'>代码</a></td><td>◆ FLISP提出一种面向水电隧道巡检的无地图UGV-UAV协同路径规划框架，避免了传统建图、栅格化和采样规划带来的计算开销与不稳定性。
◆ 其核心创新是用车载单套LiDAR-IMU同时驱动地面车和无人机的同步路径生成，降低系统复杂度并减少状态估计漂移影响。
◆ 针对不同平台，FLISP为UGV设计增强萤火虫算法实现避障，为UAV设计动态迭代优化器生成可飞行轨迹。
◆ 论文还提出分层轨迹细化策略，在不依赖全局地图的情况下保证运动学可行性与协同一致性。
◆ 在1.2 km真实运行隧道中，FLISP实现100%成功率和约7 ms延迟，相比栅格法快7倍、相比采样法快约三个数量级，展示了在退化线性基础设施巡检中的可扩展性。</td></tr>
<tr><td>2026-06-25</td><td>Design and Performance Evaluation of Secure RF and WiFi-Based Communication in Drone Swarms via Testbed Implementation<br><a href='http://arxiv.org/pdf/2606.27028'>论文</a></td><td>该论文针对无人机蜂群中MAVLink协议缺乏内置加密、遥测数据易被窃听的安全问题,在前期工作MAVShield轻量级加密框架基础上,将MAVShield与AES-CTR、Speck-CTR、ChaCha20、Rabbit五种加密方案集成到四架自建无人机中,经由RF和WiFi信道构建安全通信链路,并通过真实飞行试验对其性能进行系统评估。

◆ 提出MAVShield轻量级加密框架,在保持与未加密通信相当性能的同时,综合效率优于AES-CTR、Speck-CTR、ChaCha20和Rabbit,并经代数密码分析与Wireshark流量分析验证其抗密钥恢复与遥测保密能力。

◆ 构建四机无人机蜂群硬件测试平台,实现加密遥测下的自主编队控制与避障飞行,将安全通信与协同任务在真实物理层中联合验证。

◆ 设计基于大地坐标的改进人工势场(APF)避障算法,直接在大地坐标系计算吸引与排斥力,无需笛卡尔变换,有效减小轨迹振荡并规避局部极小值陷阱。

◆ 在CPU占用、内存消耗与分组投递率等多维度指标下,对多种加密方案在RF与WiFi链路上的性能进行横向对比,为无人机蜂群加密方案选型提供实测依据。</td></tr>
<tr><td>2026-06-24</td><td>Explainable Control Framework (XCF) based on Fuzzy Model-Agnostic Explanation and LLM Agent-Supported Interface<br><a href='http://arxiv.org/pdf/2606.25941'>论文</a></td><td>论文提出面向复杂闭环控制器的可解释控制框架XCF，旨在让人类理解控制动作的产生原因和控制器工作机制。
◆XCF具有模型无关性，可解释黑箱或复杂控制器，并能结合系统响应动态进一步细化局部解释。
◆提出HFMAE-C方法，用模糊逻辑系统近似控制器行为与系统动力学，以IF-THEN规则揭示决策逻辑。
◆该方法提供样本、局部、域和全局多层级解释，并用显著性值量化各系统状态对控制动作的贡献。
◆构建LLM Agent支持的交互界面，可自动分析用户需求、选择算法、生成自然语言解释报告并支持咨询。
倒立摆和Turtlebot避障实验表明，该框架相比主流可解释控制方法具有更好的有效性与实用性。</td></tr>
<tr><td>2026-06-23</td><td>Grounding Generative Policies in Physics: Optimization-Guided Diffusion for Robot Control<br><a href='http://arxiv.org/pdf/2606.24208'>论文</a></td><td>◆论文提出一种推理时优化引导的扩散框架，用于弥合生成式机器人策略与真实物理可执行性之间的“具身差距”。
◆其核心创新是将扩散反向采样中的随机扰动替换为优化得到的修正量，使生成结果在贴近学习先验的同时满足约束。
◆该方法无需重新训练扩散模型，即可在采样过程中加入可达性、避障、闭环可跟踪性等硬约束或软惩罚。
◆实验覆盖灵巧抓取和动态操作，并验证了方法在不同机器人具身形态上的迁移能力。
◆相比投影和梯度引导基线，该方法更好保持抓取质量，并显著提升控制器可执行性与任务成功率，最高提升20和23个百分点。</td></tr>
<tr><td>2026-06-22</td><td>Stable Transformer-Actor-Critic Model Predictive Control: A Contraction Analysis Approach<br><a href='http://arxiv.org/pdf/2606.20197'>论文</a></td><td>◆提出了一种Transformer-Actor-Critic MPC架构，用于处理复杂非凸控制任务，并同时关注闭环稳定性与鲁棒性保证。
◆首次证明Transformer网络可满足全局增量输入到状态稳定性δISS，为序列模型用于控制提供理论基础。
◆利用黎曼收缩理论分析物理系统与预测神经网络之间的互联系统动态，建立稳定性判据。
◆将理论推导得到的稳定性与鲁棒性界作为训练正则项，使学习策略具备可认证的鲁棒性。
◆在非线性3D无人机目标到达与避障任务中验证了方法的有效性，展示其在复杂动态场景中的应用潜力。</td></tr>
<tr><td>2026-06-22</td><td>LP-NavOA: Integrated Local Navigation and Obstacle Avoidance for Humanoid Robots under Limited Perception<br><a href='http://arxiv.org/pdf/2606.23249'>论文</a></td><td>◆ LP-NavOA面向短程、部分可观测感知下的人形机器人，实现了局部导航、避障与稳定全身运动的一体化框架。
◆ 其先训练射线感知条件下的PPO运动骨干，采用机器人中心的圆形航向-速度指令和共享安全过滤器，提升高速指令跟踪能力。
◆ 在冻结运动骨干后，利用A-star和航点教师数据蒸馏循环局部规划器，部署时仅改写航向指令，避免破坏全身控制策略。
◆ 系统运行只需本体感知、短程距离感知和机体坐标系目标方向，不依赖全局地图、连续航点流或外部规划器。
◆ 实验显示其能完成绕障和遮挡后目标恢复，将准时到达率从38–40%提升到85–97%，并减少擦碰式前进。
◆ 消融验证了动态路线塑形、教师主动数据采集和圆形指令接口的重要性，Unitree G1分析也表明其具备硬件可执行性。</td></tr>
<tr><td>2026-06-22</td><td>Scalable Online Flight Trajectory Optimization via Sequential Quadratic Programming for Urban Air Mobility in Ultra Low-Altitude Airspace<br><a href='http://arxiv.org/pdf/2606.23008'>论文</a></td><td>◆提出面向超低空城市空域UAM的在线轨迹优化框架，将城市几何约束、运行限制与飞行器全自由度动力学统一纳入SQP求解。

◆创新地不依赖预先生成的无障碍走廊，而是在每次迭代中实时重建分离超平面约束，实现障碍规避与动力学优化的联合在线求解。

◆引入可变尺度四叉树分解，在复杂城市级三维环境中控制计算规模，提升高密度、高速飞行场景下的实时性与可扩展性。

◆该方法能够随参考轨迹和环境变化动态更新约束，更适合真实UAM运行中的在线重规划需求。

◆在五个真实城市环境中与传统SQP、iLQR和DDP对比，CPU平台上实现100%成功率和安全净空率，验证了其鲁棒性与实用价值。</td></tr>
<tr><td>2026-06-22</td><td>Verifiable Foundation Models for Robot Safety<br><a href='http://arxiv.org/pdf/2606.23754'>论文</a></td><td>◆提出FEARL框架，将机器人策略拆分为大型Controller和小型Safety模块，兼顾基础模型的感知推理能力与安全可验证性。
◆Controller负责高维多模态感知和任务理解，Safety模块仅基于低维安全传感器信息及有界上下文嵌入输出最终动作。
◆该设计把碰撞避免、工作空间边界等安全约束的形式化验证范围缩小到Safety模块，使现有验证工具可实际应用。
◆论文证明这种模块化分解不会显著牺牲任务能力，并在三个仿真机器人任务中测试了多种控制器骨干和训练方式。
◆实验还包括现成视觉-语言-动作模型，并展示了从仿真到真实机器人的迁移，说明低维安全接口具有实践价值。</td></tr>
<tr><td>2026-06-21</td><td>Any-Body Guard: Universal Safeguarding for Manipulation Policies via Action Masking<br><a href='http://arxiv.org/pdf/2606.22278'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-20</td><td>Decentralized Geometric Control for Cable-Suspended Payload Transport with Adaptive Mass Estimation<br><a href='http://arxiv.org/pdf/2607.00024'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-19</td><td>Backpropagating Through Simulation: Analytic Policy Gradients for Sample and Learning Efficient Differentiable Continuous Control<br><a href='http://arxiv.org/pdf/2606.21525'>论文</a></td><td>◆本文提出Analytic Policy Gradients（APG），利用可微环境将回报视为策略参数的可微函数，直接通过仿真反向传播计算精确梯度，替代高方差采样估计。

◆APG显著提升连续控制中的样本效率，针对PPO需要大量交互的问题，在多种任务上进行系统对比验证。

◆论文设计了包含环境步数与梯度步数的多轴评估协议，从而区分样本效率和计算效率。

◆为解决长时域任务中的梯度衰减问题，提出分段反向传播，并结合蒙特卡洛或critic引导的bootstrap机制。

◆实验覆盖从点质量导航到刚体推动和7自由度机械臂 reaching 的不同复杂度任务，并通过消融分析研究分段长度与bootstrap策略的影响。</td></tr>
<tr><td>2026-06-19</td><td>Reference-Free, Long-Horizon Trajectory Optimization for Aggressive Autonomous Driving in Milliseconds<br><a href='http://arxiv.org/pdf/2606.21486'>论文</a></td><td>◆论文面向激进自动驾驶，研究如何在无参考轨迹、无热启动条件下，毫秒级求解长视距、全车辆动力学的最优控制问题。
◆作者通过分析车辆动力学刚性特征，证明低阶A稳定积分方法更适合该类OCP，求解速度相比其他方法可提升最高两个数量级。
◆论文系统揭示了内点法中障碍参数更新策略和Hessian不定性保护机制对非线性求解鲁棒性的关键影响。
◆提出基于动态平衡的高效初值生成方法，将初始不可行性最多降低四个数量级，从而显著提升实时求解能力。
◆实验在高保真BeamNG仿真中实现260米视距仅55毫秒的计算时间，并展示高速避障中漂移可成为生成可行轨迹的必要行为。</td></tr>
<tr><td>2026-06-18</td><td>Agentic AutoResearch forSpace Autonomy: An Auditable, LLM-Driven Research Agent for Aerospace Control Problems<br><a href='http://arxiv.org/pdf/2606.20394'>论文</a></td><td>◆ 提出AutoResearch框架，用大语言模型作为离线研究代理，自动阅读问题描述、修改训练脚本、运行实验并记录结果，用于航天控制策略开发。

◆ 明确区分“研究代理”和“ onboard 控制器”：LLM只负责离线发现策略，最终部署的是训练好的控制策略，避免LLM直接操控航天器。

◆ 引入内嵌可信度审计层，要求结果通过种子噪声测量、最佳配置重采样验证和留一编辑剪枝三重检验后才被认可。

◆ 在相对交会和带安全约束的避障对接两个任务上，框架无需改动即可应用，并以最优控制基准校准性能。

◆ 实验显示，经审计的策略显著超过种子噪声，而无定向搜索无法达到同等效果；在对接任务中，随机搜索甚至找不到可行策略。</td></tr>
<tr><td>2026-06-18</td><td>Lagrange: An Open-Vocabulary, Energy-Based Sparse Framework for Generalized End-to-End Driving<br><a href='http://arxiv.org/pdf/2606.20274'>论文</a></td><td>◆ Lagrange提出一种面向开放世界端到端驾驶的稀疏能量框架，兼顾效率、泛化能力与轨迹可执行性。
◆ 它利用VLM将类别无关的目标提案编码为连续语义视觉 token，突破传统闭集感知对OOD场景的依赖。
◆ 论文设计了意图驱动的掩码交叉注意力模块，可在时间维度过滤无关实体，聚焦与驾驶决策相关的信息。
◆ 模型将注意后的语义表示解码为空间坐标上的隐式连续能量场，用于表达风险、语义和环境约束。
◆ 通过把规划建模为拉格朗日作用量最小化问题，Lagrange在避障同时严格满足车辆运动学约束。
◆ 在nuScenes和CODA上的离线实验表明，该方法在标准与长尾场景中具备更强的鲁棒性、可解释性和开放词汇泛化潜力。</td></tr>
<tr><td>2026-06-18</td><td>Frequency-Aware Flow Matching for Continuous and Consistent Robotic Action Generation<br><a href='http://arxiv.org/pdf/2606.20135'>论文</a></td><td>◆论文提出Frequency-Aware Flow Matching（FAFM），解决现有机器人流匹配/扩散策略依赖离散动作块、难以适配不同控制频率且动作不连续的问题。
◆方法将离散动作序列通过DCT变换到频域，在频域系数上进行流匹配，再用余弦基展开重建连续动作。
◆为提升时间一致性，FAFM加入一阶时间导数正则，相当于Sobolev约束，可抑制高频误差和突变动作。
◆该方法不增加额外网络参数，能无缝用于独立流匹配策略和视觉-语言-动作模型。
◆在仿真、LapGym、LIBERO及真实Franka机器人实验中，FAFM提升成功率、平滑性、收敛速度、多模态表达能力，并增强对机械偏差和混合频率数据的鲁棒性。</td></tr>
<tr><td>2026-06-18</td><td>Contraction-based Neural Control for Cooperative Aerial Payload Transportation with Variable-length Cables<br><a href='http://arxiv.org/pdf/2606.20127'>论文</a></td><td>◆ 提出一种面向多无人机变长度缆绳吊运刚体载荷的神经非线性控制框架，解决协同空运中的轨迹跟踪与避障问题。
◆ 将系统动力学重构为载荷运动与缆绳长度动力学解耦的形式，使不同控制通道可模块化设计。
◆ 针对载荷子系统，联合训练神经控制收缩度量控制器与神经反馈控制器，以满足收缩条件并提升非线性跟踪稳定性。
◆ 针对缆绳长度子系统，设计利用可变长度自由度的控制律，实现通过障碍或门洞时的空间调整。
◆ 仿真验证了该框架可实现刚体载荷轨迹跟踪和门洞穿越，展示了其在复杂环境协同运输中的潜力。</td></tr>
<tr><td>2026-06-17</td><td>Congestion-Aware Robot Tour Planning in Crowded Environments<br><a href='http://arxiv.org/pdf/2606.19031'>论文</a></td><td>◆本文提出了一种面向拥挤环境的概率式机器人巡游规划方法，专门解决人群对机器人导航效率和路径选择的影响。

◆其核心创新在于显式建模“人群拥堵”因素，而不是仅将行人视为局部避障中的动态障碍物。

◆论文利用CLiFF地图学习人流运动模式，可根据初始观测预测行人轨迹和未来拥堵分布。

◆基于这些预测，系统在线构建并求解马尔可夫决策过程，从而为机器人选择更高效、更少受人群干扰的巡游路线。

◆该方法具备可扩展性，能够随着新行人观测不断重新规划，并在真实购物中心人群数据集上验证了有效性。</td></tr>
<tr><td>2026-06-17</td><td>WST Multi-Object Spectrograph Fiber Positioners:Development of a 32,000-Unit Precision Robotic System<br><a href='http://arxiv.org/pdf/2606.18957'>论文</a></td><td>◆ 论文提出了面向WST多目标光谱仪的超大规模光纤定位系统方案，覆盖3.1平方度视场，包含3万台低分辨率和2000台高分辨率定位器。

◆ 其核心挑战是让每个密集排布的机器人定位器达到5微米RMS精度，规模较DESI、4MOST等现有装置提升六倍以上。

◆ 为降低32,000个精密机构量产风险，项目采用多概念并行开发策略，由EPFL、AIP、UKATC和AAO合作推进。

◆ 论文创新性比较了四种定位器架构，包括6.2毫米间距、63单元三角模块以及新的内联模块化概念。

◆ 研究建立了系统化测试指标，涵盖定位精度、重复性、重配置速度、避碰能力和可制造性，为2026–2027年概念筛选提供依据。

◆ 当前原型测试表明关键性能指标具备可行性，为WST在2040年代初实现首光奠定了技术基础。</td></tr>
<tr><td>2026-06-17</td><td>One Demo is Worth a Thousand Trajectories: Action-View Augmentation for Visuomotor Policies<br><a href='http://arxiv.org/pdf/2606.19586'>论文</a></td><td>◆提出一种从单条真实眼在手示教中生成大量训练数据的动作-视角增强框架，缓解机器人初始位姿变化和未知障碍导致的分布外问题。
◆设计适用于大视场鱼眼相机的Gaussian Splatting重建方法，可生成逼真的鱼眼图像序列，并支持在三维场景中编辑加入未见物体。
◆结合轨迹优化生成平滑、无碰撞且适合视角渲染的动作轨迹，保证增强数据在视觉和物理执行上都更可信。
◆该方法仅需便携式夹爪和单个鱼眼相机采集演示，显著降低了大规模机器人示教数据收集成本。
◆仿真和真实实验表明，该增强框架能提升多种操作任务的成功率，尤其在含障碍物、需要避障的增强场景中效果明显。</td></tr>
<tr><td>2026-06-17</td><td>pdSTL: Probabilistic Differentiable Signal Temporal Logic for Stochastic Systems<br><a href='http://arxiv.org/pdf/2606.19561'>论文</a></td><td>◆ 提出pdSTL框架，将概率语义与可微鲁棒性统一起来，使随机动力学和感知噪声下的机器人能够在信念轨迹上进行时序逻辑约束优化。  
◆ 采用区间值概率语义，组合式地沿STL语法树传播保守满足概率边界，从而提供形式化的概率安全保证。  
◆ 将时序鲁棒性评估重构为类似LSTM的递归展开，实现线性时间、端到端可微的STL监测与轨迹优化。  
◆ 相比传统确定性可微STL，pdSTL显式考虑信念空间不确定性，因此在真实扰动环境中能更稳定地保持安全裕度。  
◆ 通过仿真避障、换道和Crazyflie四旋翼真实飞行实验验证了方法的效率、可优化性和在随机系统中的实际安全优势。</td></tr>
<tr><td>2026-06-16</td><td>VEGA: Learning Navigation VLAs from In-the-Wild Egocentric Video with Geometric Trajectory Supervision<br><a href='http://arxiv.org/pdf/2606.18426'>论文</a></td><td>◆ VEGA提出了一种从未标注的第一人称野外导航视频中训练导航Vision-Language-Action模型的方法，利用互联网规模视频作为可扩展数据源。

◆ 它通过单目视频重建局部场景几何，并基于文本、图像或空间路标采样导航目标，生成机器人坐标系下的避障轨迹监督。

◆ VEGA仅在训练阶段使用几何信息，将避障规划能力蒸馏到纯视觉策略中，并采用flow-matching训练VLA导航策略。

◆ 论文还构建了VEGA-Bench，包含25万场景和约500万导航目标，用于系统评估目标推进、碰撞避免和障碍间距。

◆ 实验表明，VEGA在基准测试中显著减少碰撞并提升避障间距，在真实世界试验中也大幅提高成功率，证明视频派生几何监督是训练避障导航VLA的有效可扩展信号。</td></tr>
<tr><td>2026-06-15</td><td>Optimal Bounded Thrust Powered Descent with Analytical Ground-Collision Avoidance<br><a href='http://arxiv.org/pdf/2606.17050'>论文</a></td><td>本文提出了一种解决有界推力动力下降并确保避撞的新方法，通过质量多项式近似构建了有界线性二次最优控制问题。该方法的核心是推力分配的分层分离，对水平推力施加硬约束而保持垂直推力无约束。
◆与基于数值优化和轨迹成型的现有方法不同，该方法提供了显式的解析避撞条件。
◆制导律能预测饱和与未饱和弧段的切换时间并塑造推力曲线，在控制器长时间饱和时仍可实现软着陆。
由于具有解析特性，该制导律计算高效且推力曲线连续，便于实时应用，仿真验证了其在扰动下精确的无碰撞软着陆性能。</td></tr>
<tr><td>2026-06-15</td><td>Instance-Aware Knowledge Distillation for Semi-Supervised Learning of an On-Board Multi-Task Dense Prediction Model for Collision Avoidance System<br><a href='http://arxiv.org/pdf/2606.16414'>论文</a></td><td>◆提出面向碰撞避免系统的实例感知知识蒸馏半监督框架，降低目标场景大规模标注需求。
◆伪标签生成同时利用教师模型的领域先验与基础模型的实例级知识，从而缓解教师偏差并提升实例分割质量。
◆训练得到轻量级车载多任务密集预测学生模型，可同时执行前方障碍物检测/实例分割与单目深度估计。
◆构建大规模乡村俱乐部场景数据集，并将模型集成到实际系统中，通过CAN消息编码障碍物空间信息以支持AGV运行。
◆实验表明学生模型在实例分割上超过大教师模型，同时显著降低深度估计性能退化，并以22.68倍FLOPs和14.33倍参数压缩实现低成本边缘设备实时运行。</td></tr>
<tr><td>2026-06-15</td><td>SemGeoNav:A Safety-Guided Visual Navigation Approach with Semantic Reasoning and Geometric Planning<br><a href='http://arxiv.org/pdf/2606.16400'>论文</a></td><td>针对端到端模型缺乏几何约束导致避障不可靠，以及传统几何规划难以处理高维视觉目标的问题，本文提出了SemGeoNav分层视觉导航框架。该框架将端到端模型的高级语义推理与基于几何的可靠局部规划紧密结合，实现了鲁棒的图像导航并显著提升了避障能力。
◆提出语义推理与几何规划紧耦合的分层架构，兼顾高维语义目标处理与物理避障安全。
◆引入时序轨迹平滑机制，确保机器人运动的连续性与稳定性。
在真实环境四足机器人上的实验表明，该方法在成功率和导航时间上均优于ViNT和NoMaD等现有方法。</td></tr>
<tr><td>2026-06-15</td><td>PolyMerge: Compressing 3D Gaussian Splats with Polytope Coverings for Provably Safe Resource-Constrained Navigation<br><a href='http://arxiv.org/pdf/2606.16232'>论文</a> | <a href='https://athlon76.github.io/PolyMerge-website/'>代码</a></td><td>本文提出PolyMerge方法，将大规模的3D高斯溅射模型转换为轻量级的凸多面体表示，以解决3DGS模型在机载感知路径规划中计算和内存开销过大的问题。
◆提出基于凸多面体覆盖的3DGS压缩方法，其多面体合集可证明对原3DGS模型中的所有障碍物进行保守包络。
◆支持调节多面体数量，灵活权衡避障的保守性与计算成本。
◆将多面体表示与控制障碍函数深度融合，实现可证明安全的无碰撞路径规划。
无人机硬件与仿真实验表明，该方法在极严苛的机载算力下实现了实时安全轨迹规划，在保证安全的同时运行速度超越基线方法。</td></tr>
<tr><td>2026-06-14</td><td>Act on What You See: Unlocking Safe Social Navigation in Vision-Language-Action Models<br><a href='http://arxiv.org/pdf/2606.10495'>论文</a></td><td>本文提出SALSA框架，解决了预训练视觉-语言-动作模型虽已编码行人区分与碰撞信号，但行为克隆无法将其转化为安全社交动作的问题。
◆社交行为对齐，将中间层社交特征桥接至动作头，并利用反事实人-物场景对进行训练以打破视觉显著性捷径。
◆时序安全对齐，通过自动生成的未来风险监督信号，使模型能够实现前瞻性的碰撞规避。
实验表明，SALSA在无需额外标注的情况下将近距离碰撞减少了86.4%，并将社交反事实准确率从53%提升至93%。
该研究证明，通过更好地对齐潜层表征与动作生成，即可让模型依据已有表征行动，成功解锁预训练VLA策略的安全社交导航潜能。</td></tr>
<tr><td>2026-06-14</td><td>$λ$-Reachability: Geometric-Horizon Safety Bellman Equations for Humanoid Safety<br><a href='http://arxiv.org/pdf/2606.16022'>论文</a></td><td>本文提出了λ-Reachability方法，为高维机器人系统提供了一种可扩展的哈密顿-雅可比安全分析方案。
◆不同于先前依赖固定单步贝尔曼更新的折扣公式，该方法采用具有几何分布推演视界和随机吸收终端的随机多步安全值估计器。
◆通过可解释的视界控制参数，该方法在局部自洽更新与长视界最大化轨迹安全目标之间进行插值。
◆不同于TD(λ)总包含终端值，其终端安全值仅在参数δ控制的概率下使用，在δ小于1时产生支持时序差分学习的收缩映射，且当λ趋于1时能恢复无折扣可达性目标。
实验表明，该方法在仿真与真实人形机器人的平衡和避障任务中，显著提升了安全集边界分类与安全裕度估计的准确性。</td></tr>
<tr><td>2026-06-14</td><td>FlashNav: Ultra-Fast Policy Training for Robot Navigation within 20 Seconds<br><a href='http://arxiv.org/pdf/2606.15846'>论文</a></td><td>本文提出了FlashNav，这是首个实现秒级策略训练的基于深度强化学习的机器人导航框架，最快可在20秒内完成部署级策略的训练。
◆提出与导航马尔可夫决策过程对齐的轻量化仿真思想，保留占据几何和运动动力学等核心组件，剔除了冗余渲染和高保真物理细节。
◆构建基于批量位图仿真器和全GPU驻留训练管线的架构，结合FastDSAC学习器，实现导航经验在GPU上的大规模并行生成。
◆首次在桌面级显卡上将深度强化学习导航训练时间缩短至20秒内，且策略在标准测试中达到百分之百成功率。
实验表明，该框架训练出的策略可直接迁移至真实的轮式和足式机器人，在静态和动态室内场景中均展现出鲁棒的避障导航能力。</td></tr>
<tr><td>2026-06-14</td><td>Can Causal Models Enhance Robot Navigation? Online Causal Adaptation for Real-Robot Navigation<br><a href='http://arxiv.org/pdf/2606.15691'>论文</a></td><td>本文探索了将因果模型迁移至真实机器人导航场景的挑战，证明了用于行为解释的因果模型能成功整合到实际导航系统中。核心贡献在于通过离线与在线两种方式验证了因果模型对导航性能的提升作用。具体创新点如下：
◆将因果模型作为离线评估模块，预测真实导航轨迹的胜任度并关联其定量表现，发现该预测与路径效率正相关、与不规则性负相关，且与人类标注高度一致。
◆将因果模型作为在线自适应模块，在默认导航预测胜任度低时实施干预，在转弯和避障等复杂场景中有效提升了导航指标，而在简单场景提升有限。
结果表明因果模型在任务复杂性增加时对增强导航尤为有效。</td></tr>
<tr><td>2026-06-13</td><td>GuideWalk: Learning Unified Autonomous Navigation and Locomotion for Humanoid Robots across Versatile Terrains<br><a href='http://arxiv.org/pdf/2606.10449'>论文</a></td><td>本文提出了GuideWalk框架，这是一个将可穿越性感知导航引导与地形自适应运动教师相结合的统一端到端人形机器人导航框架。
◆引入提供显式速度引导的导航模块，将避障与地形条件解耦，从而在多样环境中实现鲁棒规划。
◆提出复合教师蒸馏方案，将目标导向指令与动态一致动作聚合并蒸馏至单一策略中。
◆采用强化学习和辅助行为克隆目标精炼蒸馏策略，在促进探索的同时保留教师的优良行为。
实验表明，该框架能够在各种复杂地形上实现稳定且有效的人形机器人导航与运动控制。</td></tr>
<tr><td>2026-06-13</td><td>Hamilton-Jacobi Reachability-Based Safe Reinforcement Learning for Emergency Collision Avoidance<br><a href='http://arxiv.org/pdf/2606.15311'>论文</a></td><td>本文提出了一种基于哈密顿-雅可比可达性运动安全集引导的安全强化学习框架，用于解决极端驾驶条件下紧急避障的前瞻性安全控制问题。
◆构建了结合几何碰撞边界与底盘稳定性极限的统一符号安全函数，并通过可达性分析将其扩展为有限时域运动安全集，以表征未来车辆状态演化下的安全性。
◆利用离线极端驾驶数据近似运动安全集，有效减轻了传统基于网格的HJ求解器带来的巨大计算负担。
◆将学习到的安全集作为连续安全代价嵌入约束马尔可夫决策过程，并采用PID-拉格朗日策略优化方案自适应调节拉格朗日乘子以严格执行安全约束。
仿真与实车实验表明，该方法在低附着避障场景下实现了更高的目标到达率、更平滑的避障动作以及更大的统一安全裕度。</td></tr>
<tr><td>2026-06-12</td><td>Sensitivity Shaping for Latent Modeling<br><a href='http://arxiv.org/pdf/2606.14585'>论文</a></td><td>该论文关注机器人规划中学习式生成动力学模型的安全部署问题，指出现有事后OOD支持度估计方法在动力学对关键动作不敏感时会失效。
◆ 论文揭示了一种新的失败机制：不受支持的控制动作可能产生看似正常的潜在预测，从而掩盖真实预测误差和OOD风险。
◆ 提出“支持条件化控制敏感性正则化”，在高支持训练区域增强模型对控制输入变化的局部响应。
◆ 该方法既保留了由控制引起的有效动态差异，又避免在低支持区域产生不稳定外推。
◆ 在视觉避障、操作任务和真实机器人导航实验中，该方法提升了OOD检测能力，并带来更安全的闭环规划表现。</td></tr>
<tr><td>2026-06-12</td><td>ForestBack: Breadcrumb-Based Pedestrian Dead Reckoning for Infrastructure-Free Return Navigation<br><a href='http://arxiv.org/pdf/2606.14421'>论文</a></td><td>◆提出ForestBack，一种无需GPS、Wi-Fi、蓝牙信标或预部署设施的行人返航导航框架，面向无基础设施和GPS受限环境。
◆其核心创新是将行走轨迹记录为可逆“面包屑”节点序列，并基于双向路径重建生成原路返回指导。
◆系统融合加速度步态检测、自适应步长估计、磁力计航向估计和气压高度校正，以提升PDR轨迹稳定性。
◆在含障碍物和五个检查点的室内路线中，ForestBack相较传统PDR将平均RMSE从1.129米降至0.965米，提升15.76%。
◆其最终位置误差也从1.781米降至1.388米，转弯事件检测一致性约达99.90%，验证了路径保持返航能力。
◆论文还发布包含36次行走试验和42,474个时序样本的数据集及分析笔记本，支持复现和后续基准测试。</td></tr>
<tr><td>2026-06-12</td><td>Robustness without Wrinkles: Parallel Simulation and Robust MPC for Certified Deformable Manipulation<br><a href='http://arxiv.org/pdf/2606.14188'>论文</a></td><td>本文提出了CORD-SLS方法，实现了对绳索和布料等可变形物体的安全实时控制。
◆开发了带有接触平滑技术的GPU并行可微模拟器，实现了间歇接触下的高效梯度规划。
◆提出了一种实时GPU并行输出反馈鲁棒模型预测控制算法，以应对模型与感知不确定性并满足约束。
◆利用保角预测校准视觉反馈与感知误差界限，构建可达管道以实现高概率的认证安全控制。
◆证明该模拟器可加速基于模型的强化学习，从而高效训练神经操纵策略。
实验表明该方法在高维接触丰富的任务中实现了毫秒级规划，在安全性速度和成功率上均超越基线。</td></tr>
<tr><td>2026-06-11</td><td>EmbodiSteer: Steering Embodiment-Agnostic Visuomotor Policies with Joint-Space Guidance for Zero-Shot Cross-Embodiment Deployment<br><a href='http://arxiv.org/pdf/2606.12965'>论文</a> | <a href='https://frankwang67.github.io/EmbodiSteer-Page'>代码</a></td><td>论文核心贡献总结:

该论文提出了EmbodiSteer,一个无需训练的框架,用于将与机器人本体无关的视觉运动策略零样本部署到不同机器人上,同时实现本体感知的安全执行。该方法在笛卡尔空间中保持策略学习的可扩展性,并在推理阶段通过正向运动学和雅可比矩阵将扩散采样过程提升到目标机器人的关节空间,从而在保留末端执行器行为的同时避免全身碰撞。实验表明,相比仅笛卡尔执行,该方法在9个仿真机器人上降低碰撞率46.1%、提升任务成功率28.5%,在两个真实机器人的高约束场景下分别达到90.0%碰撞率降低和36.7%成功率提升。

创新点:

◆ 提出训练免费的引导框架,在保持笛卡尔空间策略学习优势的同时,实现推理阶段对目标机器人本体的感知与适配,解决了末端执行器抽象忽略机器人本体约束的核心难题。

◆ 通过正向运动学和基于雅可比矩阵的更新,高效地将扩散采样过程从笛卡尔空间提升至目标机器人的关节空间,实现跨本体推理时的空间转换。

◆ 在每个去噪步骤后引入全身碰撞感知的关节轨迹引导机制,使机械臂在保留已学习末端行为的前提下主动避开碰撞。

◆ 实现真正的零样本跨本体部署,在9个仿真机器人和2个真实机器人上验证了显著的碰撞率降低和成功率提升,展示了方法的通用性与实用性。</td></tr>
<tr><td>2026-06-10</td><td>Koopman-based NMPC for Virtually Coupled Train Control System<br><a href='http://arxiv.org/pdf/2606.11858'>论文</a></td><td>该论文针对虚拟编组列车控制系统的跟踪控制问题,提出了一种基于Koopman算子的解析型非线性模型预测控制(K-NMPC)方法。作者将包含列车动力学、速度与控制输入约束、乘客舒适度约束以及避碰约束的非线性列车运动模型,通过闭式可观测函数系统性地提升到有限维Koopman空间中,从而将原非线性控制问题转化为可高效求解的二次规划问题。仿真结果表明,所提方法在控制性能上与传统时间离散NMPC方案相当,但在线计算时间显著减少,展现出良好的实时应用潜力。

核心贡献和创新点如下:

◆ 首次将解析型Koopman算子方法应用于虚拟编组列车控制系统,为列控领域提供了新的建模与控制思路。

◆ 通过闭式可观测函数将含多类约束的非线性列车运动模型系统性地提升到有限维Koopman空间,避免了传统数据驱动Koopman方法对大量训练数据的依赖。

◆ 提出沿移位预测轨迹冻结仿射参数变化提升预测器的策略,将在线优化问题转化为可高效求解的二次规划问题。

◆ 在保证与传统NMPC相当控制性能的前提下,显著降低了在线计算时间,为虚拟编组列控系统的实时实现提供了可行方案。</td></tr>
<tr><td>2026-06-09</td><td>Free Parametrization of L_2-Bounded Structured State-Space Controllers for Nonlinear Control with Stability Guarantees<br><a href='http://arxiv.org/pdf/2606.11049'>论文</a></td><td>本文针对非线性系统控制中神经网络易失稳和现有约束方法计算开销大的问题，提出了基于结构化状态空间模型的自由参数化方法。
◆提出具有预定L2增益的线性时不变系统的新型自由参数化方法。
◆构建L2循环单元，该状态空间模型层在设计上天然强制执行L2界限。
◆结合小增益定理或性能提升框架，在无需约束优化参数的情况下保证闭环稳定性，实现完全无约束优化。
◆所提参数化结构支持并行扫描算法，能够高效处理长输入序列。
移动机器人编队控制实验验证了该方法在保证稳定性和性能的同时能有效避障。</td></tr>
<tr><td>2026-06-09</td><td>Language-Driven Cost Optimization for Autonomous Driving<br><a href='http://arxiv.org/pdf/2606.10974'>论文</a></td><td>本文提出了一种用于自动驾驶自适应代价设计的语言驱动框架，解决了传统代价参数调整依赖专业知识且难以适应动态场景与用户偏好的问题。
◆利用大语言模型解释结构化场景描述和自然语言查询，为风险感知MPPI控制器自动生成代价参数。
◆引入人机回环验证机制，在部署前用非技术语言向用户描述行为变更并获取确认。
◆支持用户在部署前后提供反馈，实现了车辆运动行为的持续迭代优化。
仿真结果表明该系统能直观地实现符合意图的行为改变，有效弥合了智能车辆控制系统与终端用户之间的鸿沟。</td></tr>
<tr><td>2026-06-09</td><td>NOVA: Symbolic Regression Discovery of Interpretable Car-Following and Lane-Change Models with Driver Heterogeneity<br><a href='http://arxiv.org/pdf/2606.10583'>论文</a></td><td>本文提出了NOVA自主符号回归框架，能在极少先验下从原始轨迹数据中发掘可解释的跟车与换道模型。
◆开发了基于Rust的确定性搜索引擎，在海量数据中评估万级代数结构，提取出紧凑的双项加速度模型。
◆在跟车预测任务上超越现有最优基线，并发现一个鲁棒的主导非线性项作为跟车骨架，残差分析揭示了其与碰撞避让心理物理学理论的联系。
◆发现的特征算子在不同高速公路场景间具备零样本迁移能力，泛化性能损失极小。
◆将模型扩展至换道建模，结合多项逻辑斯蒂框架在未知驾驶员测试上取得67.4%的平衡准确率，大幅超越现有基线近三十个百分点。</td></tr>
<tr><td>2026-06-08</td><td>Your Model Already Knows: Attention-Guided Safety Filter for Vision-Language-Action Models<br><a href='http://arxiv.org/pdf/2606.09749'>论文</a></td><td>该论文提出了一种免训练的注意力引导安全过滤框架，解决了视觉语言动作模型无法实时避开任务无关物体的问题。作者发现VLA模型内部的少数注意力头能够可靠地定位策略意图接近的目标物体。
◆提出利用VLA模型内部注意力头实时提取活跃目标，无需额外训练或调用缓慢的视觉语言模型。
◆将提取的目标与轻量级实时跟踪器及控制障碍函数过滤器结合，实现了对非静态障碍物的实时避碰。
◆扩展了包含移动障碍物的动态评估基准，在动态场景中比依赖初始化识别的预言机方法平均性能提升43%。</td></tr>
<tr><td>2026-06-08</td><td>Safe Polytope-in-Polytope Motion Planning and Control with Control Barrier Functions<br><a href='http://arxiv.org/pdf/2606.09719'>论文</a></td><td>本文提出了一种基于控制屏障函数的安全多面体内多面体局部运动规划与控制方法，确保多面体形状的机器人足迹始终保持在持续更新的凸自由空间区域内。该方法将包容条件转化为模型预测控制器中的离散时间控制屏障函数约束，克服了传统简化几何模型在狭窄环境中过于保守的问题。
◆安全约束数量仅取决于局部自由空间几何复杂度和机器人形状，而非障碍物数量，有效降低了计算维度。
◆所提出的自由空间公式化无需进行任何障碍物检测或分割，简化了系统的处理流程。
◆与传统的多面体避障公式相比，该方法计算时间最高可缩减91倍，显著提升了规划效率。
该方法在仿真和硬件平台上均得到验证，成功在嵌入式计算机上实现了10Hz的实时安全规划及动态障碍物反应式避障。</td></tr>
<tr><td>2026-06-08</td><td>Motion planning for hundreds of floating robots<br><a href='http://arxiv.org/pdf/2606.09620'>论文</a></td><td>本文解决了大规模水面浮动机器人集群因避障产生强耦合而导致的运动规划难题，实现秒级生成跨越数千时间步的无碰撞轨迹。
◆提出了一种可扩展的运动规划流水线，能够根据稀疏关键帧快速为数百个机器人生成编舞轨迹。
◆通过构建碰撞图将强耦合问题分解为多个交互簇，使得各簇能够独立且并行地求解，大幅提升了计算效率。
◆设计了针对常见分解病理的鲁棒性机制，确保了并行求解过程和最终轨迹的可靠性。
该方法在多达500个机器人的仿真中得到验证，并成功部署于苏黎世湖24艘船只及2025年威尼斯双年展的真实场景中。</td></tr>
<tr><td>2026-06-08</td><td>Shape Formation for the Cooperative Transportation of Arbitrary Objects Using Multi-Agent Reinforcement Learning<br><a href='http://arxiv.org/pdf/2606.09610'>论文</a></td><td>本文针对具有任意形状和非均匀质量分布的现实物体协作运输挑战，提出了一种新颖的多智能体强化学习方法来解决模式编队控制问题。该方法使多机器人系统能够自主移动到物体下方以安全支撑其重量。
◆创新性地解决了现实物体任意形状与非均匀质量分布带来的支撑难题，使机器人能够自主定位以平衡支撑物体重量。
◆将编队控制与避障相结合，使机器人在形成支撑编队的过程中能够有效避开环境障碍物。
◆提出的策略展现出强大的泛化能力，在多样环境与不同数量机器人下，能够可靠生成平衡编队，并成功适用于杂乱场景及复杂物体。</td></tr>
<tr><td>2026-06-08</td><td>LAEI: Layered Autonomous Edge Intelligence Framework for Robust UAV Swarm Operations<br><a href='http://arxiv.org/pdf/2606.09099'>论文</a></td><td>本文提出了分层自主边缘智能LAEI框架，旨在解决无人机集群在通信受限与故障场景下的协调难题，克服了集中式易受单点影响与完全去中心化缺乏全局一致性的缺陷。该框架的核心创新如下。
◆提出机载学习与轻量级监督相结合的分层架构，无人机本地执行感知避障与动作选择，监督层提供自适应目标重分配和策略指导但不干预底层动作。
◆设计故障感知恢复机制，集成动态重关联、备份监督支持与局部自主降级策略，有效保障故障场景下的任务连续性。
◆在保障分布式防碰撞决策的前提下，显著缩短任务完成时间并提升整体运行效率。</td></tr>
<tr><td>2026-06-08</td><td>Autonomous FPV Flight with Translational Optical Flow and Uncertainty Mask<br><a href='http://arxiv.org/pdf/2606.09088'>论文</a></td><td>本文提出一种基于平移光流和不确定性掩膜的单目RGB四旋翼自主避障与高速飞行系统。
◆提出将光流分解为平移和旋转分量，仅使用捕捉场景几何与深度线索的平移光流作为输入，解决了障碍物光流与自运动背景光流难以分离的问题。
◆引入由前向和后向光流估计不一致性导出的不确定性掩膜，有效凸显了包括扩展焦点区域在内的障碍物结构，克服了该区域信噪比低的瓶颈。
◆将上述线索输入基于可微分仿真框架训练的控制策略，实现了感知与控制模块之间的高效一阶优化。
实验表明，该系统在真实森林环境中实现了11.79米/秒的高速飞行，成功率达93.3%，将单目光流无人机的真实世界飞行速度记录几乎提升了一倍。</td></tr>
<tr><td>2026-06-08</td><td>FlexPath: Learned Semantic Path Priors for Image-Based Planning<br><a href='http://arxiv.org/pdf/2606.10167'>论文</a> | <a href='https://github.com/FraunhoferIVI/FlexPath'>代码</a></td><td>◆ FlexPath提出两阶段图像规划框架，将“路径可行性”与“任务偏好”解耦，突破了以往学习式规划器受最短路径监督目标限制的问题。
◆ 第一阶段通过模仿学习从视觉地图中学习任务无关的可行路径空间先验，获得可复用的路径结构知识。
◆ 第二阶段引入可微的路径形状目标（PSOs），无需重新学习模型即可将同一先验适配到最短路、避障间隙、语义避让和航点引导等不同目标。
◆ 在最短路径任务中，FlexPath相比TransPath在TMP上减少14.3%的搜索开销，同时平均路径成本更低，并在三个未见域中表现出强零样本泛化能力。
◆ 该方法还能与经典规划器在推理阶段兼容，兼具学习方法的灵活性和传统搜索的可靠性。</td></tr>
<tr><td>2026-06-07</td><td>IR-SIM: A Lightweight Skill-Native Simulator for Navigation, Learning, and Benchmarking<br><a href='http://arxiv.org/pdf/2606.08729'>论文</a> | <a href='https://github.com/hanruihua/ir-sim'>代码</a></td><td>本文提出了一个轻量级技能原生导航仿真器IR-SIM，旨在解决现有仿真器接口复杂阻碍快速原型开发的问题。
◆场景完全由YAML文件定义，使仿真完全可描述和可复现，并通过智能体技能支持直接从文本提示生成和修改场景。
◆支持导航算法的自动化基准测试以及机器人学习训练数据的自动生成，极大提升了算法评估与模型训练效率。
◆提供通向高保真仿真器和真实世界部署的桥梁，用户无需额外编码即可在更真实的环境中验证原型算法。
多项实验充分验证了IR-SIM在自然语言构建场景、避碰策略训练及虚实迁移等任务上的便捷性与多功能性。</td></tr>
<tr><td>2026-06-07</td><td>Real-Time and Accurate Collision-Free Teleoperation via Differentiable Constraint-Based Trajectory Planning<br><a href='http://arxiv.org/pdf/2606.08725'>论文</a></td><td>本文针对遥操作中仅控制末端执行器易导致机械臂碰撞的问题，提出了一种基于可微约束的实时无碰撞轨迹规划方法。
◆将基于凸优化对偶性的可微避碰约束公式引入遥操作场景，避免了传统方法因近似导数导致的收敛差与计算耗时问题。
◆采用胶囊体近似机械臂和多面体表示环境障碍物，克服了传统球体近似几何精度低的缺陷，实现了更准确的障碍物建模。
仿真与真实UR5e机械臂的实验结果表明，该方法在多变障碍物环境中具有更低的计算延迟。
最终实现了更平滑且完全无碰撞的末端执行器遥操作，有效提升了系统的安全性与实时性。</td></tr>
<tr><td>2026-06-07</td><td>Towards End to End Motion Planning and Execution for Autonomous Underwater Vehicles Using Reinforcement Learning<br><a href='http://arxiv.org/pdf/2606.08513'>论文</a></td><td>该论文提出了一种面向自主水下航行器(AUV)的端到端深度强化学习运动规划与执行框架,旨在减少传统流水线中繁重的人工工程设计,直接将原始传感器数据映射为推进器指令。作者设计了分层强化学习架构,将问题拆分为两个马尔可夫决策过程,并在高保真HoloOcean仿真器中验证。实验结果显示,该方法在轨迹长度上接近RRT*基线(差距仅4%-6%),并对传感器噪声和能见度下降表现出较强鲁棒性,但在新颖障碍物形状的未知场景中泛化能力有限。整体上,该工作展示了样本高效的端到端DRL在水下导航中的可行性,且仅需极少计算硬件。

◆ 提出双层级HRL架构:高层策略以2Hz处理原始单目相机图像、前视声呐和本体感知数据生成空间子目标,低层策略以10Hz将子目标转换为推进器指令,实现感知到控制的端到端闭环。

◆ 高层策略采用基于先验示范的强化学习(RLPD),并在改进的SERL框架内训练,显著提升了样本效率。

◆ 低层策略结合Soft Actor-Critic与Hindsight Experience Replay,有效处理稀疏奖励下的子目标到达问题。

◆ 首次在高保真HoloOcean仿真器中实现融合视觉与声呐多模态原始输入的端到端AUV避障导航,且性能可媲美经典RRT*规划。

◆ 系统验证了该方法对传感器噪声及低能见度等水下典型扰动的鲁棒性,并明确指出当前方法在未知几何环境中的泛化局限。</td></tr>
<tr><td>2026-06-06</td><td>A Barrier-Modulated Architecture for Safe Affine Formation Control in Second-Order Multi-Agent Systems<br><a href='http://arxiv.org/pdf/2606.08137'>论文</a></td><td>本文针对二阶多智能体系统，提出了一种结合高阶控制障碍函数与自适应动态规划的安全仿射编队控制框架，解决了参数不确定性下的避碰挑战。
◆引入障碍调制控制架构，在智能体接近安全边界时平滑衰减名义编队跟踪目标，有效防止控制输入冲突。
◆开发了解析型障碍梯度排斥控制器，具有计算高效的特点，为安全控制提供了严格的数学基准。
◆设计了基于执行器-评论家神经网络的数据驱动最优安全控制器，通过在线求解HJB方程实现未知参数下的最优避碰。
理论证明上述控制器均能保证安全集前向不变性以实现绝对避碰，并维持编队跟踪误差一致最终有界，仿真验证了其鲁棒性。</td></tr>
<tr><td>2026-06-06</td><td>Learning Predictive Control with Deep Koopman Operators for Autonomous Vehicle Motion Planning<br><a href='http://arxiv.org/pdf/2606.08136'>论文</a></td><td>本文提出了基于深度Koopman算子的学习预测控制框架，以解决传统模型预测控制实时性差和强化学习缺乏控制理论结构的问题。
◆提出基于深度Koopman的预测器，以数据驱动方式将非线性不确定车辆动力学提升至可解释的线性可观空间。
◆通过滚动时域Actor-Critic学习，在每个预测区间内生成闭环状态反馈策略，克服了传统MPC仅计算开环控制序列的局限。
◆针对非凸环境约束构建障碍物的凸局部替代表示并定义势场函数，将其与梯度直接嵌入Actor-Critic结构以实现安全感知的策略学习。
仿真与红旗实车实验表明，该框架在复杂避障场景下的安全性计算效率和舒适性均优于现有基准方法。</td></tr>
<tr><td>2026-06-05</td><td>Spline Policy: A Structured Representation for Robot Policies<br><a href='http://arxiv.org/pdf/2606.07386'>论文</a></td><td>本论文提出 Spline Policy (SP),一种用于机器人操控的结构化策略表示方法。该方法以样条参数取代传统模仿学习中固定分辨率的动作块 (action chunks),在保持策略主干网络不变的前提下,显式暴露出机器人动作的几何与时间结构,从而支持紧凑解码、时间重采样、参数空间编辑、不确定性传播以及与经典控制器的兼容融合。作者将 SP 应用于扩散模型、流匹配、Transformer 及视觉-语言-动作等多种主流策略框架,并在低维运动学习、仿真操控、灵巧操控和真实机器人任务中验证了其有效性。

◆ 提出样条参数化策略表示 SP,替代固定分辨率动作块,可在执行前显式呈现动作的几何与时间结构,并能以任意时间分辨率查询和编辑。
◆ 针对二次样条输出,设计了基于解析距离场的构造方法,将样条转化为状态相关的向量场,在正则性与投影假设下保证诱导动力学不会增加到预测轨迹的距离,从而提供有原则的局部纠偏机制。
◆ 支持从观测到样条参数、轨迹及流场的不确定性传播,为策略输出提供可量化的可信度评估。
◆ 可与零空间避障等经典控制机制无缝结合,无需重新训练策略主干即可实现安全约束。
◆ 该表示具有良好通用性,可即插即用地嵌入扩散、流匹配、Transformer 及 VLA 等多种现代策略学习框架。</td></tr>
<tr><td>2026-06-05</td><td>Task Editing for Generalizable 3D Visuomotor Policy Learning<br><a href='http://arxiv.org/pdf/2606.07012'>论文</a></td><td>这篇论文针对3D视觉运动策略学习中真实世界示范数据收集成本高、现有数据增强方法仅做局部物体变换而难以合成多样化场景-技能-物体组合的问题,提出了一种名为Task-Edit的新型示范生成框架。该框架从任务中心的编辑视角出发,将任务分解为场景、技能和物体三个组件,并通过灵活重组这些组件来生成多样化的轨迹数据,从而实现可扩展的示范生成,显著提升了长时序操作任务的泛化能力。作者通过大量真实世界实验验证了方法在多种任务和机器人本体上的有效性、跨场景的泛化性,以及在抗干扰、避障和未见杂乱场景等难以采集真实数据的场景下的适用性。

核心创新点如下:

◆ 提出任务中心的示范编辑视角,突破了以往仅做物体姿态或尺度等局部变换的局限,能够合成更丰富的场景-技能-物体组合。

◆ 将任务解耦为场景、技能、物体三个独立组件并支持灵活重组,这种结构化分解为可扩展的示范生成提供了新思路。

◆ 构建了Task-Edit示范生成框架,显著提升3D视觉运动策略在长时序复杂操作任务中的数据效率与泛化性能。

◆ 使模型能够处理真实世界中难以采集数据的复杂场景,包括抗干扰、动态避障以及未见过的杂乱环境。

◆ 在多种真实世界任务和不同机器人本体上验证了方法的通用性,展现出良好的跨平台适配能力。</td></tr>
<tr><td>2026-06-04</td><td>AIS-Based Vessel Trajectory Prediction Using Memory-Augmented Neural Networks<br><a href='http://arxiv.org/pdf/2606.06311'>论文</a></td><td>船舶轨迹预测对海事安全和效率至关重要。本文的核心贡献是首次实证验证了记忆增强神经网络在基于AIS数据的船舶轨迹预测中的显著优势。
◆将原本应用于行人和车辆轨迹预测的记忆增强神经网络创新性地引入船舶轨迹预测，填补了该技术在海事领域的应用空白。
◆利用外部记忆模块选择性检索相关信息，有效增强了模型对复杂船舶运动模式的捕捉与预测能力。
◆在墨西哥湾和纽约湾的真实AIS数据集上进行广泛实验，证明了该方法相比未使用外部记忆的深度学习基线模型具有一致且显著的性能提升。</td></tr>
<tr><td>2026-06-04</td><td>Preparing for the Next Carrington: Spatiotemporal Agent-Based Modeling for Safeguarding Satellite Infrastructure Under Extreme Space Weather Disturbances<br><a href='http://arxiv.org/pdf/2606.05732'>论文</a></td><td>本论文针对极端空间天气(如卡灵顿级太阳风暴)对卫星基础设施的潜在威胁,构建了一种新颖的时空智能体建模框架,用于预测灾害影响并为卫星提供实时机动指导。研究基于41,644条卫星记录、5次近期空间天气事件的历史数据及大气密度模型,模拟了具有物理驱动行为的独立卫星智能体决策过程。情景分析显示,低地球轨道95%的卫星将面临8倍基线水平的大气阻力增强,碰撞风险提升2-3倍,单颗受影响卫星的直接经济损失约为4000万美元,而模型机动建议准确率达92%。该研究首次为抵御下一次卡灵顿级灾难提供了实时自适应决策系统的原型框架。

核心贡献和创新点如下:

◆ 首次将时空智能体建模(ABM)方法应用于极端空间天气下的卫星基础设施安全研究,突破了以往仅依赖统计群体模型的局限,实现对单颗卫星个体行为的精细化模拟。

◆ 构建了具有物理驱动行为的卫星智能体,能够根据推进剂约束和碰撞规避阈值动态做出独立决策,真实反映卫星在灾害情境下的自适应响应。

◆ 整合了41,644条真实卫星数据、5次历史空间天气事件记录和大气密度模型,通过蒙特卡洛模拟量化了灾害的物理影响与经济损失,为风险评估提供了定量依据。

◆ 提出了具备92%准确率的实时机动推荐机制,首创性地为卫星运营商提供应对卡灵顿级事件的实时自适应决策原型系统,具有重要的工程与战略价值。</td></tr>
<tr><td>2026-06-03</td><td>DiffSlack: Learning under Nonlinear Inequality Constraints via Learnable Slack Variables<br><a href='http://arxiv.org/pdf/2606.05247'>论文</a></td><td>本文提出了一种名为DiffSlack的可微投影层，旨在解决神经网络中非线性不等式约束执行困难的问题。
◆通过引入可学习的松弛变量将不等式转化为等式，将其作为增强网络输出进行预测，为阻尼高斯-牛顿投影提供数据驱动的热启动。
◆设计投影层将原始预测映射到增强可行流形上，同时保持端到端的可微性。
◆提出两阶段课程学习策略，进一步稳定训练过程并提升约束满足能力。
在包含两百个非线性约束的车辆路径规划实验中，DiffSlack在同等推理预算下实现了更高的规划成功率和约束满足度。
消融实验表明硬投影层降低了对监督质量的敏感性，且闭环与实车实验证实了该方法的可执行性与实用价值。</td></tr>
<tr><td>2026-06-03</td><td>MAD: Mapping-Aware World Models for Agile Quadrotor Flight<br><a href='http://arxiv.org/pdf/2606.04534'>论文</a></td><td>论文核心贡献总结:

本文提出了Mapping-Aware Dreamer(MAD),一种面向视觉四旋翼飞行的几何感知世界模型。该方法摒弃了传统世界模型以原始图像重建作为自监督目标的做法,转而利用循环潜在动力学重建机器人中心的占用栅格图、可见性栅格图以及本体感知状态,从而使潜在表征直接编码局部几何、可见性历史和自运动信息。MAD在DiffAero仿真平台中训练,并支持三种策略学习模式(MAD-Dreamer想象式训练以及基于PPO和SHAC的特征提取器变体),最终在仿真中达到9.66 m/s、真实森林环境中达到5.05 m/s的飞行速度。

◆ 提出以占用栅格与可见性栅格重建替代原始图像重建作为世界模型的自监督目标,使潜在状态显式编码避障所需的几何与可见性信息。
◆ 设计了GPU并行的地图构建模块,在DiffAero中提供高吞吐的占用与可见性监督信号,解决了大规模训练的数据效率问题。
◆ 将学习到的几何感知表征灵活应用于想象式策略学习(MAD-Dreamer)和作为PPO、SHAC的特征提取器三种模式,展示了表征的通用性。
◆ 在视觉导航与竞速任务中相较纯视觉基线实现了更高成功率、更快速度以及更好的跨任务迁移能力,并产出可解释的地图预测与精准的自运动估计。
◆ 在配备Intel RealSense D435i的真实四旋翼上完成室内外部署,验证了该方法作为模块化导航与端到端学习之间实用折中方案的可行性。</td></tr>
<tr><td>2026-06-03</td><td>AgenticRL: Self-Refining Agentic Reinforcement Learning for Vision-Conditioned UAV Navigation<br><a href='http://arxiv.org/pdf/2606.03963'>论文</a></td><td>本文提出AgenticRL框架，解决了无人机导航中强化学习严重依赖人工奖励设计与微调的痛点，实现了奖励生成、策略优化和真实部署的自主化。
◆提出基于多模态GPT智能体的闭环自优化奖励设计机制，由智能体自动生成奖励、评估训练策略并诊断失败模式，从而自我完善奖励函数。
◆引入推理阶段的智能策略调度机制，利用多模态智能体融合真实图像与自然语言自动识别当前场景，动态选择最匹配的策略执行。
实验表明该闭环优化过程使策略表现较初始奖励提升了71%。
框架还成功实现了仿真到现实的迁移，真实世界成功率达91%，虚实迁移准确率达94%。</td></tr>
<tr><td>2026-06-02</td><td>RSC: Decentralized Rigid Formation Flocking for Large-Scale Swarms via Hybrid Predictive Control and Online Reconfiguration<br><a href='http://arxiv.org/pdf/2606.04248'>论文</a></td><td>本文针对分散式刚性编队集群在杂乱环境中易陷入局部最小值死锁、控制振荡及避障灵活性差等问题，提出了大规模群体分散式控制框架RSC。
◆提出混合控制架构，将有限时域轨迹预测与响应式人工势场安全控制器相结合，通过长期规划逃离局部最小值并确保短期安全。
◆引入基于稳定角色交换的在线领航-跟随重构机制，在穿越障碍后加速编队重聚且不中断任务执行。
在25架无人机的挑战性环境测试中，该框架可靠地统一了刚性编队保持、避障与目标追踪。
在无碰撞且最大相对边长误差低于10%的严格标准下，RSC成功率达83%，显著优于成功率不足5%的现有基线方法。</td></tr>
<tr><td>2026-06-02</td><td>Distribution-Free Risk-Aware Planning and Control Under Uncertainty Using Conformal Spectral Risk Control<br><a href='http://arxiv.org/pdf/2606.04185'>论文</a></td><td>动态不确定环境下的安全导航常依赖对真实不确定性分布的准确估计，但有限数据往往导致分布假设错误从而引发危险决策。本文提出了一种结合预测集的风险感知模型预测控制框架，无需假设底层不确定性分布即可保证风险低于用户设定阈值。
◆将共形风险控制扩展至一般谱风险度量，开发了无分布的风险量化框架来生成预测集。
◆证明将预测集引入控制框架，即使不确定性设定错误也能在谱风险约束满足方面提供统计安全性保证。
仿真实验验证了该框架在车辆避障场景中的有效性，相比基线方法显著提升了安全性并缩短了求解时间。</td></tr>
<tr><td>2026-06-02</td><td>Throughput Optimization for Multi-AP IEEE P802.11bq Networks Based on Combinatorial Multi-Armed Bandits<br><a href='http://arxiv.org/pdf/2606.03528'>论文</a></td><td>本文致力于解决密集多AP IEEE P802.11bq网络的分布式吞吐量优化问题。
◆构建了全新的包级模型，联合刻画了跨链路CSMA/CA、RTS/CTS交换、波束训练开销、定向毫米波干扰、基于SINR的MCS选择及重传机制。
◆将网络配置问题创新性地建模为多组组合多臂老虎机，使每个AP能从有限候选集中选择竞争窗口、CCA阈值、波束宽度和MCS预留裕量。
◆提出基于Hadamard引导可行探索的分组可行CSAR变体算法，通过估计经验排名分数高效淘汰各组内低效候选参数。
仿真表明，该方法较Thompson采样基线提升了吞吐量，且稳定时间缩短约49%。
研究还揭示了高吞吐量需平衡控制信道激进性、空间复用、波束成本与鲁棒性，而非单纯减少碰撞或最大化物理速率。</td></tr>
<tr><td>2026-05-31</td><td>Crazyflow: An Accurate, GPU-Accelerated, Differentiable Drone Simulator in JAX<br><a href='http://arxiv.org/pdf/2606.01478'>论文</a></td><td>本文提出了Crazyflow，一个基于JAX构建的GPU加速、高精度且可微的无人机仿真器，填补了现有仿真器无法统一支持保真度、可微性和集群模拟的空白。
◆实现了前所未有的仿真速度与并行规模，单机仿真比现有SOTA快超一个数量级，可同时模拟数千个含4000架无人机的集群。
◆同时兼顾了高精度与可微性，支持基于解析梯度的策略学习，在无需域随机化的情况下实现了亚厘米级的轨迹跟踪精度。
◆打破了传统先训练后部署的范式，凭借极高的仿真速度实现了飞行中在线强化学习，仅用0.38秒即可从零训练出无人机空中恢复策略并成功稳定。
◆具备出色的兼容性与易用性，直接兼容开源Crazyflie模型，并提供轻量级系统辨识流程，支持多级仿真抽象及跨平台快速重构。</td></tr>
<tr><td>2026-05-31</td><td>Time-Optimal Collision Avoidance Via a Greedy Polynomial Backward Sweep<br><a href='http://arxiv.org/pdf/2606.01169'>论文</a></td><td>本文针对低推力卫星碰撞规避问题，提出了一种贪婪时间最优反向扫描方法，用于求解确保安全的最晚机动启动时间。
◆该方法采用反向迭代传播策略，从名义最近接近时间起向后传播，每步贪婪选择局部最小化危险度量的推力方向。
◆引入微分代数技术高效传播状态敏感度，实现了最近接近时间的在线动态更新。
研究采用错过距离和碰撞概率作为安全度量，在大量交会数据集上对方法进行了验证。
实验表明该方法准确度高，与最优控制基准相比仅有极小的最优性损失。
其运算时间短，非常适合航天器星载环境的实时计算与实现。</td></tr>
<tr><td>2026-05-31</td><td>Tether-Aware Dynamic Collision Avoidance for USV-HROV Systems<br><a href='http://arxiv.org/pdf/2606.01112'>论文</a></td><td>本文针对无人水面艇跟踪混合遥控潜水器时面临的水下系绳易剐蹭且避障易致系绳绷紧的挑战，提出了一种系绳感知的动态避障方法。
◆引入了系绳安全感知平面域，在无需显式系绳形状模型的情况下，表征系绳与障碍船只之间的三维碰撞风险。
◆开发了系绳绷紧感知速度障碍方法，在实现安全避障的同时降低系绳绷紧的可能性。
◆将该方法与视线导引法相整合，有效协调了HROV跟踪与动态避障任务。
仿真结果表明，该方法在无人艇执行规避机动时，能成功避让动态障碍船只并保障系绳安全。</td></tr>
<tr><td>2026-05-31</td><td>Robust Integrated Planning and Control for Quadrotors in Dynamic Environments via NMPC with CBF Penalties<br><a href='http://arxiv.org/pdf/2606.01038'>论文</a></td><td>本文提出了一种针对四旋翼无人机在动态环境下的鲁棒集成规划与控制新策略。
◆将控制障碍函数作为指数惩罚项嵌入非线性模型预测控制中，在严格输入约束下改善了可行性并确保平滑避障，同时提供权衡跟踪精度与避障激进度的调节参数。
◆引入高增益扰动观测器估计并补偿外部扰动，显著提升了系统的鲁棒性。
◆结合卡尔曼滤波实现计算高效的障碍物运动实时预测，使无人机能够规避动态障碍物。
◆这是首个经过硬件实验验证的NMPC与CBF结合的集成规划控制框架，对比实验证明了其在可行性安全性和鲁棒性上的显著优势。</td></tr>
<tr><td>2026-05-31</td><td>OSCAR: Obstacle Survival Curves for Adaptive Robot Navigation<br><a href='http://arxiv.org/pdf/2606.00990'>论文</a></td><td>本文提出OSCAR框架，解决移动机器人在已知路线图上遇到临时障碍物时等待与重规划之间的低效决策问题。
◆提出基于障碍物类别的生存建模方法，从在线经验中学习残余清障时间分布，并引入右删失观测处理未观察到清障就重规划的情况。
◆将生存模型集成到时变图规划器中，动态计算被阻塞边的耐心阈值，从而自适应地决定等待时间或选择替代路线。
◆框架支持在多个导航回合中持续更新清障时间估计，实现导航策略的在线进化与优化。
仿真与真实机器人实验表明，该方法在每类障碍物不到20次观测后即可收敛至接近真实分布的最优水平，显著优于启发式基线。</td></tr>
<tr><td>2026-05-30</td><td>DriveAnchor: Progressive Anchor-based Flow Learning for Autonomous Driving Planning<br><a href='http://arxiv.org/pdf/2606.00519'>论文</a></td><td>DriveAnchor提出了一个三阶段的自动驾驶规划框架，在可组合流水线中实现了行为多样性、可控性与安全性。
◆提出示范流预训练，用最远点采样构建的2398个轨迹形状词汇表替代非结构化高斯先验，从结构上保证行为多样性。
◆提出引导流后训练，联合训练能量场与流匹配，仅依据静态道路几何将锚点重定位至用户指定走廊，无需可微引导即可实现可控性且新预设无需重训练流匹配。
◆提出奖励精炼流微调，利用零阶强化学习对齐避撞目标，将单步流匹配的奖励优化简化为锚点空间的方向搜索，无需计算对数似然或ODE转SDE。
该方法在约两百万测试场景中将近距碰撞率降低89%，平均奖励提升32%且不损失模仿精度。
其推理速度达2.06毫秒，并通过实车测试证实了量产部署的实用性。</td></tr>
<tr><td>2026-05-29</td><td>BERS: Locally Optimal Continuous Algorithm for Maritime Weather Routing with Just-in-Time Arrival<br><a href='http://arxiv.org/pdf/2605.31533'>论文</a></td><td>该论文提出了一种名为BERS的气象航线优化框架，旨在解决动态风浪和障碍物约束下的准时到达航线规划问题。
◆提出了结合CMA-ES全局进化搜索与FMS局部变分细化的两阶段优化框架。
◆采用贝塞尔曲线参数化航线并进行密集路径采样，确保轨迹平滑且兼顾中段效应与可行性约束。
该方法在七项操作标准的基准测试中均匹配或超越已有基线，在复杂流场下保持鲁棒收敛。
真实海洋数据验证表明，仅航线优化即可降低23%至59%的推进能耗。
结合风辅助推进后总节能高达75%，证明了该框架在海事脱碳节能规划中的实用性与可扩展性。</td></tr>
<tr><td>2026-05-29</td><td>LiftNav: Path Planning via Semantic Lifting in TSDF-Guided Gaussian Splatting<br><a href='http://arxiv.org/pdf/2605.31376'>论文</a></td><td>本文提出了LiftNav框架，解决了传统TSDF缺乏语义与三维高斯泼溅几何偏软导致难以精确避障的矛盾。
◆构建基于TSDF+GS双地图的混合导航框架，兼顾了可靠的碰撞避障与物体级语义理解。
◆设计了结合YOLO检测与TSDF三维提升的实时流水线，无需密集三维嵌入即可实现灵活的语义导航。
◆引入了基于铰链损失的碰撞惩罚项，有效提升了B样条轨迹优化的平滑度与安全性。
实验表明，相较于最先进的辐射场基线，该方法实现了百分之百的轨迹可行率且路径更短。</td></tr>
<tr><td>2026-05-29</td><td>Simulation of collision avoidance behavior in crowd movement by data-driven approach<br><a href='http://arxiv.org/pdf/2605.31210'>论文</a></td><td>针对现有数据驱动人群模拟模型在双向和多向流中碰撞率过高的问题，本文提出了一种融合行人碰撞机制的新型数据驱动人群模拟模型CPGAN。
◆提出基于横向加速度的碰撞损失函数，将其融入生成对抗网络架构，显著降低了逆向行人碰撞率至与对照实验相当的水平。
◆提出基于Voronoi的运动特征提取方法，提升了模型对行人运动特征的捕捉能力。
实验表明，CPGAN在双向流场景中有效模拟了人群运动，成功重现了车道形成现象和N-t曲线。
本研究为将行人动力学机制整合到数据驱动人群模拟的损失函数中提供了重要启示。</td></tr>
<tr><td>2026-05-29</td><td>Trajectory Planning for Non-Communicating Mobile Robots using Inverse Optimal Control<br><a href='http://arxiv.org/pdf/2605.30906'>论文</a></td><td>本文核心贡献是提出了一种针对无通信移动机器人避碰场景的轨迹规划与预测结合算法。
◆基于逆最优控制，通过观察历史轨迹来估计所有机器人的未知目标状态。
◆每个机器人从他人视角出发，结合自我预测与估计的目标状态来求解联合预测问题。
◆将联合预测结果纳入自身的轨迹规划中进行考量，实现高效交互。
◆相比传统恒加速度估计方法，该方法使到达目标的时间中位数缩短9.8%，且求解器从未出现无法求解的情况，鲁棒性极高。</td></tr>
<tr><td>2026-05-29</td><td>GSAM: A Generalizable and Safe Robotic Framework for Articulated Object Manipulation<br><a href='http://arxiv.org/pdf/2605.30740'>论文</a></td><td>本文提出GSAM框架，旨在解决关节类物体操作中泛化能力有限和易发生破坏性碰撞的问题。
◆提出基于微调视觉语言模型的优化器，利用思维链常识推理修正视觉感知器的原始运动学参数估计。
◆设计交互约束函数生成器，结合物体与避障知识生成提示，由大语言模型将其函数化并应用于轨迹与姿态规划以防碰撞。
◆开发运动学感知操作规划器，以验证规划轨迹和姿态的可达性。
实验表明该框架将标准差降低了3.1%，操作成功率提升了36.0%，显著增强了实际场景中的物体泛化性与交互安全性。</td></tr>
<tr><td>2026-05-29</td><td>Geometry-Aware Control Barrier Functions for Collision Avoidance via Bernstein Polynomial Approximations<br><a href='http://arxiv.org/pdf/2605.30696'>论文</a></td><td>针对不规则几何形状机器人和障碍物的安全导航问题，传统控制障碍函数的形状代理往往过于保守或约束数量过多，影响实时性能。本文提出了一种基于伯恩斯坦多项式符号距离场的新型几何感知控制障碍函数。该研究的核心创新点如下：
◆提出统一表示方法，利用BP-SDFs统一表示障碍物和机器人，从而以统一的最小距离构建障碍函数，避免了多局部基元导致的约束膨胀。
◆实现闭环控制约束，利用伯恩斯坦多项式的可微特性，能够轻松地在闭环系统中强制执行控制约束，提升了算法实用性。
仿真实验在单机器人导航和异构多机器人避碰场景中验证了该方法的高效性与安全保障能力。</td></tr>
<tr><td>2026-05-29</td><td>Constrained Whole-Body Tracking for Humanoid Robots<br><a href='http://arxiv.org/pdf/2606.00374'>论文</a></td><td>这篇论文提出了ConstrainedMimic,一个面向人形机器人全身运动跟踪的实时约束执行控制框架,旨在解决强化学习策略在训练后难以满足新增安全约束的问题。该方法结合操作空间控制(OSC)与控制屏障函数(CBF)的思想,在RL跟踪策略之上施加运行时约束,既约束运动学参考也约束底层动力学,从而在保证安全的同时最小化对策略原有能力的限制。作者在仿真Unitree G1上完成了全身运动跟踪与遥操作实验,验证了自碰撞与外部障碍物避让、关节限位以及质心稳定性等多种约束的有效性。

◆ 提出ConstrainedMimic框架,首次将OSC与CBF原理统一融入RL全身跟踪策略,实现训练后可任意指定的运行时约束执行。
◆ 同时在运动学参考层和动力学执行层施加约束,使安全保障贯穿整个控制流程,而非仅修正最终动作。
◆ 通过保持与当前接触模式及跟踪目标的一致性,实现约束激活时对策略能力的最小侵入式干预。
◆ 方法完全可微,支持CPU、GPU和TPU多平台部署,运行频率可达300-500Hz,具备良好的实时性与可扩展性。
◆ 在统一框架下验证了自碰撞避让、外部障碍避让、关节限位与质心稳定等多类异构约束,展示了方法的通用性。</td></tr>
<tr><td>2026-05-29</td><td>GLENS: Global Search via Learning from Solver Iterates with Diffusion Models<br><a href='http://arxiv.org/pdf/2606.00366'>论文</a></td><td>本文针对多峰非凸连续优化问题,提出了一种名为GLENS(基于求解器迭代学习的全局搜索)的数据高效全局搜索方法,旨在生成大量高质量(求解器快速收敛)且多样化(覆盖多个局部最优)的初始猜测,以支持灵活的下游决策。该方法的核心思想是利用求解器在离线运行过程中产生的中间迭代点作为&quot;免费&quot;的数据增强,从而克服了现有方法仅使用最终收敛解、丢失局部邻域信息且训练数据有限的不足。实验在改进的非凸基准问题和双机器人避障导航问题上验证了方法的有效性,表明GLENS能在保持多峰分布多样性的同时显著加快求解器收敛速度,并在不同问题设置和求解器下均具有良好表现。

◆ 首次提出将求解器的中间迭代点而非仅最终收敛解作为训练数据,实现了&quot;免费&quot;的数据增强,显著提升了数据利用效率。

◆ 设计了邻域结构模型,利用扩散模型在问题参数条件下学习局部最优解周围的几何结构,从而保留了解的邻域分布信息。

◆ 提出了求解器行为模型,在扩散采样过程中学习并引入精化方向,引导样本进一步逼近附近的局部最优解。

◆ 将神经网络生成模型与传统数值求解器的迭代行为深度耦合,实现了高质量与多样性兼顾的全局初始猜测生成。

◆ 在非凸基准问题和实际双机器人避障导航场景中均验证了方法的通用性,并系统分析了关键超参数对性能的影响。</td></tr>
<tr><td>2026-05-28</td><td>Trust, Geometry, and Rules: A Credibility-Aware Reinforcement Learning Framework for Safe USV Navigation under Uncertainty<br><a href='http://arxiv.org/pdf/2605.26974'>论文</a></td><td>本文提出了一种融合可信度感知学习、几何安全屏蔽与连续规则嵌入的强化学习框架，解决了无人艇在感知不确定性下的安全合规导航难题。
◆提出可信度加权价值学习，利用滤波协方差与经验误差的差异推导动态信任因子，调节评论家损失以防止策略对噪声样本过拟合。
◆提出协方差膨胀速度障碍方法，将位置估计不确定性映射为角度边界，构建保守的几何屏蔽以覆盖危险的探索动作。
◆提出风险感知的避碰规则职责嵌入，将二元相遇职责松弛为连续的规则感知信号，提供平滑扇区转换并抑制稀疏奖励引起的振荡。
仿真实验表明该框架提升了对抗感知不一致的训练鲁棒性，在避碰与规则合规性上显著优于基线方法。</td></tr>
<tr><td>2026-05-28</td><td>Hybrid Digital and Analog Airy Beamforming for Near-Field Multi-User Communications<br><a href='http://arxiv.org/pdf/2605.29481'>论文</a></td><td>本文针对6G近场多用户通信中,高频聚焦波束因直线传播易受障碍物遮挡、导致频谱效率下降的问题,提出了一种基于Airy波束的混合数模波束赋形方案。该方案利用Airy波前的弯曲传播特性,使波束能够绕过障碍物并在用户处实现能量聚焦,同时通过分层波束训练和数模混合架构实现低复杂度的多用户接入与干扰抑制。仿真表明,在毫米波至太赫兹频段下,所提方案在波束方向图和频谱效率方面均优于传统聚焦波束赋形。

◆ 首次将Airy波束引入近场多用户通信,构建了兼具绕障传播与能量聚焦双重能力的近场Airy波前模型。
◆ 设计了分层Airy波束训练方法,可快速搜索能够绕过障碍物并与用户对齐的最优波束,无需获取完整信道状态信息。
◆ 提出了基于选定Airy波束配置模拟波束赋形器、再利用数字波束赋形器抑制用户间干扰的低复杂度混合架构。
◆ 解决了传统聚焦波束在多用户链路存在遮挡时频谱效率严重退化的瓶颈问题。
◆ 验证了该方案在毫米波至太赫兹宽频段下相较传统聚焦波束赋形的性能优势,拓展了近场通信的应用场景。</td></tr>
<tr><td>2026-05-27</td><td>EventShiftFlow: Towards Hardware-efficient FPGA-based Flow Estimation<br><a href='http://arxiv.org/pdf/2605.28312'>论文</a></td><td>本文提出了一种面向FPGA的流式速度估计器EventShiftFlow，旨在解决现有事件相机运动估计算法计算量大且难以硬件映射的问题。该方法将异步事件离散化为固定时长的时间窗并构建1位空间占用网格，通过并行评估多个速度假设来输出稀疏量化的速度估计。
◆提出纯整数逻辑的数据通路设计，仅使用移位寄存器、计数器、比较器和LUT映射的小型乘法器，无需浮点运算、除法器、DSP模块、帧重建和迭代优化。
◆在算法与硬件间进行针对性权衡，放弃稠密亚像素光流，换取每个活跃像素的稀疏量化速度估计，满足低延迟和资源受限平台的实时避障需求。
◆实现极低硬件开销的FPGA部署，数据通路存储需求小于2kB，并在低成本FPGA上完成原型验证，同时在真实数据集中达到了99.5%的方向准确率。</td></tr>
<tr><td>2026-05-26</td><td>Look Further: Socially-Compliant Navigation System in Residential Buildings<br><a href='http://arxiv.org/pdf/2605.26710'>论文</a></td><td>本文核心贡献在于证明了在住宅楼走廊环境中，将移动机器人对人的反应距离延长至八米以上能显著改善人类对机器人运动的感知。与关注短距离避让的传统社交导航方法不同，该研究通过远距离提前反应优化了人机交互体验。
◆提出主动换道运动模式，机器人在八米外识别到迎面而来的人时，便从走廊中心横向移动至侧边。
◆构建了利用该模式的导航系统，突破了典型交互距离限制，实现远距离的社会合规导航。
通过四十二名参与者的用户研究评估了安全、平滑和礼貌三个服务目标，结果表明在直走廊迎面场景下该系统显著优于传统模式，但在盲区转角场景中各方法无显著差异。</td></tr>
<tr><td>2026-05-25</td><td>Safety-Critical Whole-Body Control for Humanoid Robots via Input-to-State Safe Control Barrier Functions<br><a href='http://arxiv.org/pdf/2605.25546'>论文</a> | <a href='https://kwlee365.github.io/SafeWBC-Website/'>代码</a></td><td>本文针对人形机器人在未知干扰下运动学安全保证易降级的问题，提出了一种基于输入状态安全控制障碍函数的分层安全关键全身控制框架。
◆提出了结合运动学级全身控制器、ISSf-CBF安全滤波器和动力学级全身控制器的分层架构，实现从任务生成到动态执行的闭环安全控制。
◆引入输入状态安全控制障碍函数（ISSf-CBF），在有限未知干扰下对参考轨迹进行最小修改，确保运动学安全约束不被破坏。
◆通过保守调节ISSf-CBF参数，将基于全身运动学模型的安全保证成功转移到全阶动力学模型中，保障了动态可行性与接触稳定性。
仿真与真实机器人实验表明，该框架在模型失配下能提升安全裕度，并在运动、遥操作等任务中实时可靠地满足多重安全约束。</td></tr>
<tr><td>2026-05-24</td><td>Communication-Constrained Energy-Optimal Trajectory Generation for Quadrotor UAVs in Urban Environments<br><a href='http://arxiv.org/pdf/2605.24865'>论文</a></td><td>本文针对城市环境中的四旋翼无人机，提出了一个通信受限的能量最优轨迹生成框架。
◆将全刚体飞行动力学、城市无线通信模型、累积数据吞吐量约束与避障要求统一纳入自由终点时间的最优控制框架。
◆突破了基于简化运动学或质点模型的传统方法局限，生成了适用于实际无人机平台的动力学可行轨迹。
◆采用序列凸规划迭代求解通信与飞行动力学高度耦合的非凸最优控制问题，使系统能根据数据中继需求自适应调整任务时长。
该研究有效平衡了能量消耗与通信质量，为密集城市中需要可靠通信的自主无人机作业提供了实用的解决方案。</td></tr>
<tr><td>2026-05-23</td><td>A Reinforcement Learning Inspired Latent Yield Based Adaptive Algorithm Switching Mechanism<br><a href='http://arxiv.org/pdf/2605.24436'>论文</a></td><td>针对动态环境中仅依赖瞬时性能指标导致算法切换过于反应性且不稳定的问题，本文提出了一种基于潜在收益的自适应算法切换机制。该方法通过计算高效的方式跨多个问题实例聚合算法性能，对实例特征的剧烈变动具有极强的免疫力。
◆受强化学习启发，将奖惩信息封装为潜在收益，通过该收益触发探索与利用机制，从而实现自适应的算法切换。
◆受遗传算法启发，引入岛屿模型，以促进局部算法种群间的并行探索与性能交换。
在排序算法和机器人避障任务上的实验充分验证了该方法的可行性与有效性，展现了其在需要自适应算法选择领域的重要应用潜力。</td></tr>
<tr><td>2026-05-22</td><td>On the Performance of DCF in Full Duplex WLANs with Hidden Terminals<br><a href='http://arxiv.org/pdf/2605.23276'>论文</a></td><td>本文研究了在存在隐藏终端的全双工无线局域网中分布式协调功能机制的吞吐量性能。虽然全双工技术理论上能提升系统吞吐量，但其实际运行需要MAC层允许两个节点同时接入共享介质，而标准DCF机制恰恰是为避免这种并发而设计的。作者基于性能建模，深入对比分析了CSMA/CA协议在隐藏终端场景下全双工与半双工的表现差异。
◆构建了结合隐藏终端与全双工通信特征的CSMA/CA协议性能分析模型。
◆揭示了在现有DCF机制约束下，全双工技术的饱和吞吐量相比半双工仅有极微小提升，指出了传统MAC避免并发的逻辑与全双工需求存在的冲突。</td></tr>
<tr><td>2026-05-21</td><td>Superhuman Safe and Agile Racing through Multi-Agent Reinforcement Learning<br><a href='http://arxiv.org/pdf/2605.22748'>论文</a></td><td>本文证明了多智能体强化学习能为真实世界交互提供关键的安全支撑，打破了传统单智能体范式将其他主体视作环境噪声的局限。
◆提出基于联赛自博弈的多智能体强化学习框架，训练智能体在高速无人机竞速中应对复杂的空气动力学交互与战略机动。
◆智能体涌现出主动避撞、超车及处理气动下洗等高级预期行为，在超22米每秒的竞速中击败人类冠军，且碰撞率较单智能体基线降低50%。
◆通过与多样化的人工智能体共同训练，实现了向更安全的人机交互场景的零样本泛化。
这些成果表明，实现机器人在现实中的稳健共存不应依赖孤立的安全约束，而是源于多智能体交互的严格考验。</td></tr>
<tr><td>2026-05-21</td><td>N3P: Accelerated Automated Parking via a Learning-Based Naturalistic Three-Stage Scheme<br><a href='http://arxiv.org/pdf/2605.22722'>论文</a></td><td>本文提出了N3P，一个基于学习的快速三阶段自动泊车框架，旨在解决传统Hybrid A*计算昂贵以及强化学习方法缺乏可靠性和轨迹次优的问题。
◆提出三阶段分解机制，通过引入中间准备姿态将复杂的泊车操作简化为更易求解的子问题。
◆引入学习模块来预测该中间准备姿态，有效降低了计算复杂度并加速了路径生成。
◆显著提升规划效率，结合Hybrid A*算法后使泊车规划速度提升超过80%。
◆相比强化学习基线，在成功率、轨迹长度和换挡次数等指标上均表现更优，且规划时间相当或更短。</td></tr>
<tr><td>2026-05-21</td><td>Perceived Safety of Workers in Encounters with Large Industrial AGVs<br><a href='http://arxiv.org/pdf/2605.22461'>论文</a></td><td>本文研究了工人在共享空间中与大型工业自动导引车相遇时的感知安全问题，填补了现有研究空白。
◆聚焦大型载荷AGV，并以真实产业工人而非学生作为实验参与者，克服了既往研究的对象局限。
◆对比了真实场景与虚拟现实环境，发现VR中感知威胁略高但偏好一致，验证了VR实验结果的可转移性。
◆创新性地结合手持压敏触发器与问卷进行评估，并让工人自主设定避撞参数以反映真实偏好。
研究最终得出1.5至2米是工人在预设和自定义轨迹下均最偏好的安全通过距离。</td></tr>
<tr><td>2026-05-20</td><td>Safe and Steerable Geometric Motion Policies for Robotic Dexterous Manipulation<br><a href='http://arxiv.org/pdf/2605.21811'>论文</a></td><td>本文提出了安全拉回丛动力系统框架，用于解决机器人灵巧操作中异构几何空间目标与约束的协调问题，能够从任意任务流形上的目标与安全需求计算出最优且安全可证的构型流形加速度。
◆提出拉回控制障碍函数构造方法，将任务流形的安全条件转化为构型流形加速度上的线性约束。
◆设计了任务流形动作接口，允许高级策略注入低维残差运动以引导探索，且在任意输入下均能保证安全性，零输入则恢复自主行为。
实验在23自由度灵巧手平台上验证了该框架，在20种物体的灵巧抓取任务中取得了92.5%的成功率。
该方法还通过一维动作接口实现94.4%的三指抓取成功率，并首次实现了基于模型的全驱动掌下物体重定向，支持双向超过360度的偏航旋转。</td></tr>
<tr><td>2026-05-20</td><td>Flying Together: Human-Guided Immersive Shared Control for Aerial Robot Teams in Unknown Environments<br><a href='http://arxiv.org/pdf/2605.21680'>论文</a></td><td>本文提出了一种基于虚拟现实的无人机集群共享控制框架，旨在解决多机器人在非结构化环境中难以适应突发状况和捕捉操作员目标的问题。
◆提出了一种基于运动原语的用户引导规划器，可在持续融合操作员输入的同时计算连续且无碰撞的轨迹。
◆将上述规划器与导纳控制器相结合，使操作员能灵活影响集群行为并引导无人机前往自主规划易忽略的兴趣区域。
◆开发了双通道VR交互界面，支持物理与模拟无人机混合编队，允许操作员通过迁移点引导集群并获取即时视觉反馈。
实验表明，该沉浸式人机协同导航方法不仅提升了避障能力和机间间距保持效果，还显著降低了操作员的工作负荷。</td></tr>
<tr><td>2026-05-20</td><td>Design for Manufacturing: A Manufacturability Knowledge-Integrated Reinforcement Learning Framework for Free-Form Pipe Routing in Aeroengines<br><a href='http://arxiv.org/pdf/2605.20644'>论文</a></td><td>本文提出FPRO框架，将制造知识融入强化学习，解决航空发动机管路设计与制造脱节导致反复试错的问题。
◆将布线问题转化为Frenet坐标系下的边值问题，用曲率和挠率轮廓表示管路路径。
◆将领域制造知识作为曲率和挠率的约束条件嵌入设计中，实现设计与制造的有效集成。
◆采用含阶段引导奖励机制的近端策略优化算法进行路径寻优，并将路径直接映射为六轴自由弯曲机的运动轨迹。
实验表明该方法能生成更平滑且可制造的管路，收敛更快，并在真实制造中验证了其实用性。</td></tr>
<tr><td>2026-05-20</td><td>Time-To-Reach Separation and Safety Filtering for Safe, Fair, and Efficient Multi-Agent Coordination<br><a href='http://arxiv.org/pdf/2605.20625'>论文</a></td><td>本文针对高密度城市空域的多飞行器协调问题，提出了一种基于最小到达时间的多智能体协调框架。
◆创新点在于将最小到达时间作为统一度量，用于优先级分配、时间分离和安全过滤，并基于此分配到达一致的优先级。
◆创新点在于通过目标到达时间值强制执行时间间隔，从而转化为飞行器间的安全空间分离。
◆创新点在于构建了基于汉密尔顿-雅可比可达性值函数的优先级一致安全过滤层，在保证避碰的同时最小化修改参考引导指令。
仿真结果表明，该方法在拥堵走廊汇入场景下，相比传统时间最优引导和优先级无关安全过滤方法，有效提升了系统的安全性、公平性与效率。</td></tr>
<tr><td>2026-05-20</td><td>Intent-First Aerial V2V for Tactical Coordination and Separation: Protocol and Performance Under Density and Disturbance<br><a href='http://arxiv.org/pdf/2605.20595'>论文</a></td><td>本文针对密集低空飞行作业，提出了首个与控制器耦合的全空中意图优先车联网战术邻区交换协议栈。
◆不同于仅感知广播，该协议结合了刷新的状态与意图信标，实现本地感知、协同感知及降级模式评估。
◆引入事件触发消息机制，用于避让、排序、释放和应急协调等战术交互。
◆采用具有认证新鲜度检查的直通链路级C-V2X模块实现全空中V2V栈，确保信息的实时与可信。
实验表明该栈能减少过时信息分歧、保持可观测性并抑制虚假推断，在低中密度下提供可行通信层，高复杂度下转为防御性回退，是受干扰城市空域扩展战术协调的有界赋能者。</td></tr>
<tr><td>2026-05-19</td><td>D-CLING: Prior-Preserving Depth-Conditioned Fine-Tuning for Navigation Foundation Models<br><a href='http://arxiv.org/pdf/2605.19690'>论文</a> | <a href='https://toyotafrc.github.io/DCLING-Proj/'>代码</a></td><td>本文提出了D-CLING微调方法，旨在解决导航基础模型微调时预训练先验被侵蚀及避障失效的问题。该方法让模型在新场景中高效学习的同时，保持预训练的泛化能力以实现鲁棒的长期导航。
◆受ControlNet启发，附加预训练骨干的可训练副本并采用零初始化残差路径连接，使模型高效学习域内几何线索。
◆在获取新环境几何信息的同时，有效保留模型原有的各种预训练行为知识，防止微调破坏先验。
◆实验证明该方法显著减少了真实导航中的碰撞与人工干预，并在微调数据集外维持或提升了动作预测能力，为持续学习提供了重要见解。</td></tr>
<tr><td>2026-05-19</td><td>Hamilton--Jacobi Reachability for Spacecraft Collision Avoidance<br><a href='http://arxiv.org/pdf/2605.20138'>论文</a></td><td>本文提出了一个基于哈密顿-雅可比可达性的同圆轨道双星避碰框架。
该框架使用平面HCW动力学建模，并依据FCC标准定义了不安全的相对构型。
◆将航天器交互创新性地建模为控制卫星与有界对抗干扰间的零和微分博弈，以应对未知意图。
◆通过计算后向可达集，精确刻画了最坏干扰下无法避免碰撞的相对状态。
◆证明了后向可达集外的状态容许可证明的无碰撞轨迹，确保了安全性。
◆将可达集与监督混合控制逻辑集成，确定规避机动的触发时机，提供了数学上可靠的安全保证。</td></tr>
<tr><td>2026-05-18</td><td>ManiSoft: Towards Vision-Language Manipulation for Soft Continuum Robotics<br><a href='http://arxiv.org/pdf/2605.18617'>论文</a> | <a href='https://buaa-colalab.github.io/ManiSoft'>代码</a></td><td>本文提出了ManiSoft，一个针对软体连续体机器人的视觉语言操作基准，旨在解决软体臂本体感知不可靠和分布式驱动带来的挑战。
◆提出了一种定制仿真器，通过弹性力约束将逼真的软体动力学与丰富接触交互相结合。
◆定义了四个展示可变形控制不同方面的任务，并构建了自动化流程生成6300个多样化场景及专家轨迹。
◆采用分层方法大规模生成高质量轨迹，即高级规划器分解任务为路径点，低级强化学习策略生成力矩命令进行追踪。
基准测试表明现有模型在随机化下性能显著下降，主要归因于视觉本体感知估计不准及未充分利用软体可变形性避障。
该基准为弥合刚性臂与软体臂在视觉语言操作领域的鸿沟提供了宝贵测试平台。</td></tr>
<tr><td>2026-05-18</td><td>Adversarial Stress Testing of SPARK Humanoid Safety Filters<br><a href='http://arxiv.org/pdf/2605.19009'>论文</a></td><td>本文研究了SPARK人形机器人安全滤波器的鲁棒性，指出现有基准评分无法全面揭示其在严苛环境下的真实安全行为。
◆在MuJoCo中复现了SPARK基准用例，并在受控随机种子下系统评估了六种主流安全滤波方法。
◆构建了专用的后处理流程，将原始运行日志转化为目标跟踪、最小距离和碰撞步数等可量化的核心指标。
◆引入对抗性压力测试，揭示了障碍物拥挤、距离估计噪声及信息延迟等极端条件对安全行为的显著影响。
实验表明不同方法在目标跟踪与碰撞规避上存在权衡，强调人形机器人部署前必须超越标称性能，采用能暴露故障模式的指标进行严格评估。</td></tr>
<tr><td>2026-05-18</td><td>The distance-based formation controller design for multi-agent systems in port-Hamiltonian form<br><a href='http://arxiv.org/pdf/2605.18502'>论文</a></td><td>本文针对端口哈密顿多智能体系统，研究了基于距离的编队控制与防碰撞集成问题，提出了一种统一控制器同时实现速度跟踪、目标编队获取及智能体间安全。
◆构造了具有满列秩性质的符号关联矩阵，其对应有向无环图，为控制器设计奠定基础。
◆引入仅吸引势场设计，有效克服了传统人工势场中普遍存在的局部极小值问题。
◆结合安全屏障机制，在无排斥势场的情况下严格保障了防碰撞约束。
闭环系统稳定性由LaSalle不变集原理保证，数值仿真验证了该策略的有效性。</td></tr>
<tr><td>2026-05-18</td><td>Assessing Localization Technologies for Pedestrian Collision Avoidance<br><a href='http://arxiv.org/pdf/2605.18295'>论文</a></td><td>本文核心贡献是评估了超宽带和蓝牙6.0技术在行人防碰撞预警系统中的定位精度，并将其与全球导航卫星系统进行了性能基准测试。实验重点考察了这两种技术在关键指标上的表现，包括定位精度和对环境条件的鲁棒性。
◆创新性地将超宽带和蓝牙6.0应用于车辆行人碰撞预警系统，发挥其高精度测距与低延迟通信优势。
◆在多种环境条件下，对上述技术与传统全球导航卫星系统开展了定位性能的基准对比评估。
◆证实上述技术可作为传统系统的可行替代或补充方案，有效提升态势感知能力并实现及时的行人预警。</td></tr>
<tr><td>2026-05-15</td><td>Constrained MPC-Based Motion Planning for Morphing Quadrotors in Ultra-Narrow Passages under Limited Perception<br><a href='http://arxiv.org/pdf/2605.15999'>论文</a> | <a href='https://github.com/harshjmodi1996/morphocopter_mpc}{Github'>代码</a></td><td>本文提出了一个针对变形四旋翼在极受限环境和有限感知条件下的形态与轨迹运动规划框架。
◆提出了一种用于非线性模型预测控制的平滑指数障碍物代价函数，克服了传统人工势场在狭窄通道中代价过高而阻断路径的问题，在保持强避碰能力的同时维持低遍历代价。
◆该公式避免了硬激活阈值，并引入了代价降低因子，有效降低了狭窄通道内部的通行代价。
◆将二维激光雷达测量数据直接应用于模型预测控制中，实现了对任意形状障碍物的导航规避。
该方法嵌入基于acados的非线性模型预测控制框架，不仅适用于变形四旋翼，也广泛适用于其他移动机器人。
仿真与实验结果验证了该计算高效且实用的方案能成功穿越典型排斥代价函数失效的狭窄走廊。</td></tr>
<tr><td>2026-05-15</td><td>PCASim: Promptable Closed-loop Adversarial Simulation for Urban Traffic Environment<br><a href='http://arxiv.org/pdf/2605.15654'>论文</a> | <a href='https://zhenhaooo.github.io/PCASim.github.io/'>代码</a></td><td>本文提出了PCASim框架，旨在解决城市自动驾驶闭环测试中对抗场景生成与安全智能体训练难以协同进化的挑战。
◆构建了基于规则过滤开源数据集的对抗行为知识库，并结合了适配仿真环境的知识检索模块。
◆利用大语言模型融合知识驱动、数据驱动和对抗驱动方法，生成符合用户定制需求的安全关键交通场景。
◆采用强化学习模型训练各类车辆行为，在保持真实性的同时显著提升了仿真场景的多样性。
实验表明，该框架将领域语言生成准确率提升了12%，新场景转换成功率提高了8%，且避障能力增强了30%。</td></tr>
<tr><td>2026-05-13</td><td>HCSG: Human-Centric Semantic-Geometric Reasoning for Vision-Language Navigation<br><a href='http://arxiv.org/pdf/2605.13321'>论文</a> | <a href='https://haoxuanxu1024.github.io/HCSG/'>代码</a></td><td>本文提出 HCSG，首个面向视觉‑语言导航的人类中心框架，旨在动态室内环境中实现安全、社交智能的导航。  
◆ 统一的人类理解模块融合几何预测与基于视觉‑语言模型的语义解释。  
◆ 将语义‑几何融合表示嵌入拓扑地图，实现指令条件的规划。  
◆ 引入社交距离损失约束，确保交互距离符合社会规范。  
◆ 在 HA‑VLNCE 基准上实现成功率提升 14%、碰撞率降低 34% 的显著改进。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='navigation'>Navigation (145篇)</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-16</td><td>NavCMPO: Critic-Guided MeanFlow Policy Optimization for Adaptive Navigation<br><a href='http://arxiv.org/pdf/2607.14643'>论文</a></td><td>NavCMPO是一个用于自适应导航的两阶段框架，旨在解决端到端扩散策略推理延迟高以及行为克隆受限于专家示范质量的难题。该方法在预训练阶段通过障碍物距离预测任务学习障碍感知的视觉表征，并结合少步MeanFlow轨迹生成将推理延迟从85ms降至60ms；在自适应阶段采用带行为克隆正则化的PPO进行微调，同时更新评论器以适应不同本体形态的观测变化。

◆ 提出少步MeanFlow轨迹生成机制，显著降低扩散策略的推理延迟。
◆ 设计障碍物距离预测预训练任务，使视觉表征显式编码障碍物空间信息。
◆ 提出评论器引导的轨迹精炼方法CGTR，利用障碍点云监督信号修正中间轨迹，缓解少步生成带来的避障性能下降。
◆ 提出融合行为克隆正则化的PPO微调策略，实现对新形态机器人的高效自适应。
◆ 在InternVLA-N1基准上达到74.7%成功率，并在Unitree Go2上验证了有效的仿真到真机迁移能力。</td></tr>
<tr><td>2026-07-15</td><td>Breaking Déjà Vu: Independent Auditing of Visual Place Recognition through Vision-Language Reasoning<br><a href='http://arxiv.org/pdf/2607.12818'>论文</a></td><td>本文提出了一种名为视觉位置识别审计的新框架，用于独立验证视觉位置识别系统的检索结果。该方法利用视觉语言模型对查询图像和候选图像进行联合推理，实现实例级别的真伪判断，无需依赖特定架构的置信度度量、数据集相关的阈值或部署环境的先验知识。实验在六个基准数据集上评估，结合五种先进VPR方法和四种VLM，结果显示该方法在保持高于95%精确率和75%覆盖率的同时，将召回率@1平均提升13.6%，并将错误接受率降至12%。

◆ 提出视觉位置识别审计范式，将VLM作为独立的后检索验证模块，摆脱对架构特定置信度和数据集阈值调优的依赖。

◆ 利用VLM对查询与候选图像进行联合推理，实现无需先验环境知识的实例级真假匹配判断。

◆ 在六数据集、五VPR方法、四VLM上系统验证，证明该方法在精度、召回率和错误接受率之间取得优越平衡。</td></tr>
<tr><td>2026-07-15</td><td>Recursive ArUco Markers: A Scalable Fiducial Marker Design for Unmanned Aerial Vehicle Landing Pads<br><a href='http://arxiv.org/pdf/2607.13830'>论文</a></td><td>本文针对无人机(UAV)自主着陆中传统视觉基准标记在远近距离均难以检测的问题,提出了一种新颖的递归ArUco标记设计。该方法允许将任何标准基准标记转换为具有任意递归深度的递归标记,通过改进检测过程中的位采样策略,在父标记的黑白位中嵌入完整的子标记,从而实现无限递归深度并显著扩展了可操作距离范围。

◆ 创新点一:提出改进的位采样策略,将完整子标记同时嵌入父标记的黑色位和白色位中,实现任意深度的递归嵌套,使标记在不同高度和距离下均可被可靠检测。

◆ 创新点二:不依赖标记中心区域的可见性,即使在发生部分遮挡的情况下仍能保持鲁棒检测,解决了现有递归与分形标记易受遮挡影响的缺陷。

◆ 创新点三:所有递归尺度共享单一唯一标识符,既大幅扩展了可用字典容量,又支持多架无人机同时使用不同着陆点,克服了Fractal和Harco标记在结构与字典规模上的限制,适用于无人机集群协同着陆场景。</td></tr>
<tr><td>2026-07-15</td><td>From Language to Navigation Goals: A Vision-Language Approach for Semantic Navigation of Mobile Robots Using RGB-D Perception<br><a href='http://arxiv.org/pdf/2607.13624'>论文</a></td><td>本论文提出了一种基于自然语言的移动机器人语义导航框架，将用户口语指令转化为可执行的导航目标。系统采用模块化ROS 2架构，将语言理解、RGB-D视觉感知与Nav2导航栈有机结合，实现端到端的语义导航流程。

◆ 提出基于视觉-语言的语义导航框架，将自然语言指令解析与RGB-D目标定位深度融合，仅通过语言即可驱动机器人到达指定目标。

◆ 采用模块化ROS 2组件化设计，只需配置对应话题和服务即可跨平台移植，在TurtleBot3 Waffle和Unitree Go2等多种机器人上均能部署。

◆ 引入上下文理解能力，不仅能处理&quot;去邮箱&quot;等直接命令，还能解析包含场景上下文的间接请求，并生成自然语言反馈。

系统在仿真和真实环境中均验证了可行性和泛化能力，为非专业用户提供了直观的人机交互范式。</td></tr>
<tr><td>2026-07-15</td><td>Visual Place Recognition Using Rate-Encoded Spiking Neural Networks with Discrete STDP Learning<br><a href='http://arxiv.org/pdf/2607.13584'>论文</a></td><td>该论文针对基于STDP的无监督脉冲神经网络在视觉位置识别(VPR)中R@100P不足的问题，提出基于PyTorch和snnTorch的离散、张量化SNN-VPR流水线，并在100场景的Nordland数据集上以15个独立训练网络进行系统评估。

◆ 提出闭式确定性张量化神经元分配方法，显著优于标准argmax的R@100P。

◆ 证明每次查询后状态重置能普遍提升R@100P，与具体分配方式无关。

◆ 速度补偿滑动窗口聚合在k=5时实现R@100P=100.00%，仅多0.20ms延迟。

◆ 三项设计结合后在恒速遍历下达到完全可靠的闭环检测。

然而各机制和实现差异的独立贡献尚未完全解耦，仍需进一步研究。</td></tr>
<tr><td>2026-07-15</td><td>Flow-aware Optimal Navigation in Unsteady Flows through Reinforcement Learning<br><a href='http://arxiv.org/pdf/2607.13553'>论文</a></td><td>本文针对非定常时变流体环境中自主机器人导航的难题，提出基于TD3强化学习的导航方法，在参数化混沌双涡流场中训练智能体到达任意目标位置，摆脱了传统最优控制对全局流动先验知识的依赖。

◆系统比较了五种仿生观测策略（包括相对位置、局部速度、局部涡量及其短期记忆变体），揭示了不同感知模式在导航性能上的权衡规律。

◆发现能够感知并记忆有限数量流速信息的智能体表现最优，而显式提供全局流动参数反而会降低导航性能。

◆研究表明速度感知有利于能量效率优化，涡量感知则在结构映射和目标接近度方面更具优势。

◆进一步指出基于强化学习的自主系统在仅使用隐式流动表征时能学习到更鲁棒和通用的策略，为仿生机器人导航从仿真过渡到真实环境提供了重要参考。</td></tr>
<tr><td>2026-07-15</td><td>WNOJ-LIO: A White-Noise-on-Jerk Motion-Prior EKF for High-Dynamic LiDAR-IMU Fusion<br><a href='http://arxiv.org/pdf/2607.13405'>论文</a> | <a href='https://github.com/LvJohny/wnoj-ekf-lio.git'>代码</a></td><td>WNOJ-LIO提出了一种基于白噪声加加速度(WNOJ)运动先验的扩展卡尔曼滤波框架,专门应对高动态驾驶中LiDAR-IMU融合面临的扫描内运动畸变与振动噪声耦合两大挑战。该方法在R^3×SO(3)上构建解耦的WNOJ先验用于状态预测,并将IMU重新定位为高频测量源而非状态传播驱动,利用后验状态历史完成点云去畸变与点面配准更新。仿真与实车实验表明,该方法在加速度、角速度去噪及定位精度上均优于FAST-LIO基线。

◆ 提出解耦的WNOJ运动先验,实现封闭形式协方差传播,弥合了批处理高斯过程轨迹先验与递归滤波之间的理论差距。
◆ 重新定义IMU为高频测量源而非状态传播驱动,从机制上阻断惯性噪声向去畸变点云和扫描配准结果的传播路径。
◆ 在53至208 km/h的真实赛车数据上系统验证,覆盖宽幅振动场景,综合评估了加速度、角速度、速度、姿态与位置等关键状态量的估计性能。</td></tr>
<tr><td>2026-07-15</td><td>ConFlow: Constraints-Guided Learning with Flow Matching for Motion Generation<br><a href='http://arxiv.org/pdf/2607.14424'>论文</a></td><td>ConFlow针对机器人运动生成中流匹配方法面临的训练-推理不一致问题,提出了一种约束引导的流匹配框架。论文指出传统方法仅在推理时施加约束,与训练阶段的优化目标存在偏差,导致约束满足效果有限。

核心创新点包括:

◆ 将可微分的障碍函数或代价函数直接整合进流匹配的训练目标,实现训练阶段的约束引导,缩小了训练与推理之间的差距。

◆ 用条件高斯过程替代标准的高斯源分布,以更好地建模平滑性和边界条件等设计规范。

◆ 利用不可行演示作为负监督信号,在不增加专家数据的前提下提升约束满足度。

◆ 在双机器人导航任务上的实验表明,无论是否使用推理时引导,ConFlow均显著降低了碰撞率并提升了轨迹质量,验证了训练时约束整合的有效性。</td></tr>
<tr><td>2026-07-14</td><td>MAMMOTH: A Multi-Modal End-to-End Policy for Off-Road Mobility Robust to Missing Modality<br><a href='http://arxiv.org/pdf/2607.12965'>论文</a></td><td>本文针对非结构化越野环境中自主导航的鲁棒性问题,提出MAMMOTH(基于掩码多模态输入的越野可穿越性启发式导航)端到端导航策略。该方法融合RGB、热成像、3D点云和自车速度四种模态观测,并在训练阶段采用模态丢弃策略,使模型在推理时能应对部分模态缺失或传感器退化的情况。方法采用扩散策略学习物理可行驶轨迹与内在可穿越性启发式的联合条件分布,利用启发式引导生成更安全、更平滑的轨迹。

创新点如下:
◆提出多模态融合架构,联合整合RGB、热成像、3D点云和自车速度信息,弥补单一RGB模态在眩光、阴影和低光照条件下性能不足的问题。
◆引入模态丢弃训练策略,使策略在推理阶段能鲁棒应对任意模态缺失或传感器故障,显著提升泛化能力。
◆采用扩散策略联合建模轨迹与可穿越性启发式的条件分布,实现更安全、平滑且地形感知的规划。
◆通过大量真实机器人实验在多种越野环境(含夜间场景)验证,证明在避障、地形规划和模态缺失泛化方面均显著优于现有方法。</td></tr>
<tr><td>2026-07-14</td><td>Unveiling Complex Collective Behaviors from Simple Rewards<br><a href='http://arxiv.org/pdf/2607.12861'>论文</a></td><td>该论文针对多智能体强化学习策略黑箱化、难以解释的问题，提出两阶段EEC可解释框架，旨在揭示简单奖励驱动下复杂群体行为的隐藏机制。

◆ 提出Agent Response Map（ARM）这一新颖分析工具，能够刻画智能体在空间中的决策模式，识别聚集与回避区域。

◆ 利用ARM发现机器人会隐式学习环境的几何场结构，并将其作为协调运动的期望目标，揭示了奖励与行为之间的隐含关联。

◆ 在合作多机器人形状装配任务中，ARM揭示未占用的目标内部区域为导航目的地，中心被占据后目标自动转向边界。

◆ 在竞争性捕食者-猎物追逃任务中，意外发现猎物收敛于捕食者Voronoi图的边界。

◆ 两类任务的实验共同验证了ARM能够挖掘MARL策略背后隐藏的几何结构。</td></tr>
<tr><td>2026-07-14</td><td>PixelLoop: Shortcut Topological Navigation with Pixel-Level Loops<br><a href='http://arxiv.org/pdf/2607.12811'>论文</a> | <a href='https://pixelloop-nav.github.io/'>代码</a></td><td>这篇论文提出了PixelLoop方法,聚焦于纯拓扑表示中闭环检测的作用,将闭环直接引入像素空间而非传统的图像级或位姿图层面,从而作为密集的拓扑捷径改变规划连通性和代价传播。

◆核心创新是在像素级拓扑图中构建闭环,区别于稀疏的图像级边,使任意点到任意点的导航更加稳定,代价图与几何最短路径高度对齐。

◆像素级闭环充当密集的拓扑捷径,能够显著提升利用捷径场景下的导航效率,这是图像级拓扑方法无法实现的独特优势。

◆在仿真实验中,PixelLoop相比图像级相对基线在成功率和SPL指标上均取得了超过35%的绝对提升,优势在需要捷径利用的场景中最为明显。

该方法在仿真和真实移动机器人部署中均得到验证,表明密集像素级闭环为拓扑视觉导航提供了实用且鲁棒的基础。</td></tr>
<tr><td>2026-07-14</td><td>Improving Autonomous Nano-drones Performance via Automated End-to-End Optimization and Deployment of DNNs<br><a href='http://arxiv.org/pdf/2607.12593'>论文</a></td><td>本文针对亚10厘米级自主纳米无人机的视觉导航任务，提出了一套端到端自动化的CNN部署优化流程，将PULP-Dronet网络部署于Crazyflie 2.1纳米无人机上的超低功耗多核SoC任务计算机上。相比原始手工设计的CNN，该方法在保持预测精度的同时，实现了内存占用减半、推理速度提升1.6倍的显著效果，并大幅改善了实际飞行表现。

◆ 构建了从训练到闭环评估的全流程自动化工具链，替代了传统易错且耗时的人工迭代开发流程。

◆ 提出了针对ULP多核SoC的CNN自动压缩与部署优化方法，使计算功耗仅占无人机总功耗预算的1.6%以下。

◆ 实现了多个关键飞行能力的突破：障碍物避障峰值制动速度达1.65 m/s、熟悉环境自由飞行速度提升至1.96 m/s（基线仅0.5 m/s）、以及包含90度转弯的路径跟踪。

◆ 开源了整套兼容Crazyflie 2.1的即用型软件设计，为该领域后续研究与应用提供了可复现的基础平台。</td></tr>
<tr><td>2026-07-14</td><td>StratMamba: Strategic and Reactive Stream Partitioning for Path-Efficient LiDAR-Based Obstacle Avoidance<br><a href='http://arxiv.org/pdf/2607.12370'>论文</a></td><td>StratMamba提出了一种基于双流Mamba的时序建模架构,旨在提升机器人在复杂障碍物环境中捕获长时程依赖关系的效率。该方法融合快衰减与慢衰减两种记忆机制,其中快衰减流处理高频LiDAR数据以实现反应式避障,慢衰减流则维护长时程目标信息以支持战略性规划。

◆ 提出双流Mamba架构,融合快慢衰减记忆机制,分别处理反应式避障与战略性规划任务
◆ 在IsaacLab、Gazebo仿真及Unitree GO1四足机器人上完成多场景验证,实现成功仿真到现实迁移
◆ 性能全面超越LSTM、Transformer和Vanilla-Mamba基线,路径效率达0.915,导航速度提升5.0%

实验结果表明,StratMamba具有最低的超时率与最高的路径最优性。在扩展LiDAR范围的真实测试中,该方法相比Vanilla-Mamba和Transformer表现出更强的鲁棒性,验证了双流分区策略能够有效平衡反应式安全与战略性导航。</td></tr>
<tr><td>2026-07-14</td><td>A Hybrid Mamba for Audio-Visual Navigation<br><a href='http://arxiv.org/pdf/2607.13110'>论文</a></td><td>本文提出Samba，一种用于音视频导航的混合Mamba架构，旨在突破自2020年以来以CNN和RNN为核心的骨干网络五年未变的局限。

◆ 设计自适应选择机制的Mamba状态编码器(M-SE)，替代传统GRU进行时序聚合，更高效地建模动态多模态序列

◆ 构建音频Mamba编码器(AME)，突破卷积算子难以捕获频谱图全局时频依赖的瓶颈

实验表明，Samba在未听过的声源和未见过的场景中均展现出优异的泛化能力，在Matterport3D数据集上将导航成功率提升11.3%，在场景结构更精细的Replica数据集上提升更为显著，并以更低的计算成本实现了更强的具身表征能力，为音视频导航领域的范式演进提供了高鲁棒性的技术路径。</td></tr>
<tr><td>2026-07-13</td><td>Learning to Navigate Efficiently with Only 0.58M Trainable Parameters<br><a href='http://arxiv.org/pdf/2607.11029'>论文</a></td><td>该论文挑战了视觉导航领域&quot;以规模换性能&quot;的范式，提出一种将解析计算与小型学习模块解耦的导航框架，仅用0.58M可训练参数便逼近当前最先进方法的性能。

◆核心创新在于结构化分解：投影几何、占据和坐标变换等具有闭式解的操作以解析方式计算，作为三个小型学习模块之间的接口，分别完成目标定位、出行分布估计和轨迹残差生成。

◆极致参数效率：在22.7M总参数中仅训练0.58M，训练数据仅需44k帧、单卡不到1小时，可训练参数比基线少233倍，且碰撞率最低、推理速度达50Hz。

◆良好的可迁移性与可解释性：通过仅重训123k参数的出目标头即可迁移至无目标探索任务，且在传感器损坏时的失效模式透明、可通过解析方法修正。</td></tr>
<tr><td>2026-07-13</td><td>Think When It Matters: Conditional VLM Reasoning for Social Navigation with RL Policies<br><a href='http://arxiv.org/pdf/2607.10991'>论文</a></td><td>本文针对社交机器人导航中强化学习策略缺乏语义推理能力、而视觉语言模型推理速度慢难以实时部署的矛盾，提出了HUMA混合架构。核心思路是让反应式RL策略处理常规低密度导航任务，仅当人类进入机器人的近距敏感区域时，才激活经过后训练的高层VLM进行深度语义推理与条件干预。这种&quot;按需思考&quot;的设计既保留了RL的实时反应性，又获得了VLM的语义理解能力，显著降低了计算开销。

◆ 提出了HUMA混合架构，动态融合RL策略的计算效率与VLM的深度语义理解能力。
◆ 设计了基于人类接近区域的条件触发机制，仅在敏感场景下激活VLM推理，实现&quot;按需思考&quot;。
◆ 采用后训练的高层VLM对RL策略进行条件化干预，兼顾推理速度与语义决策质量。
◆ 在Social-MP3D和Social-HM3D基准上分别实现20%和3%的任务成功率提升，同时显著减少个人空间侵犯和碰撞，并在Mirokaï机器人上完成了真实环境部署验证。</td></tr>
<tr><td>2026-07-13</td><td>ACZ-GSeg: Adaptive Concentric Zone-based Two-stage Ground Segmentation for LiDAR Point Clouds<br><a href='http://arxiv.org/pdf/2607.12110'>论文</a></td><td>该论文针对复杂道路场景下LiDAR点云地面分割中因远距离点云稀疏、地面起伏及非地面结构干扰导致的欠分割问题，提出了一种基于自适应同心区域模型的两阶段地面分割方法ACZ-GSeg。其核心思路是首先构建自适应同心区域模型，根据距离动态调整每环扇区数量，使远近区域形成点云分布更均衡的局部区块。在此基础上设计两阶段分割流程：粗分割阶段引入最低高度种子约束与高度衰减加权，建立加权主成分分析平面拟合模型以提取地面候选点；细分割阶段利用反射强度一致性约束区分高置信地面点与不确定点，再结合邻域高度稳定性对不确定点进行精修。

◆ 自适应同心区域模型，根据LiDAR距离远近动态分配扇区数量，缓解远端点云稀疏问题

◆ 粗分割阶段提出最低高度种子约束结合高度衰减加权的加权PCA平面拟合方法

◆ 细分割阶段融合反射强度一致性约束与局部高度稳定性约束的两级精修策略

实验在SemanticKITTI和自采RUBY-PLUS数据集上分别取得97.66%和99.36%的F1分数，验证了该方法在保持地面召回率的同时有效降低了非地面点误分率，对稀疏长距离点云和复杂场景具有较强适应性。</td></tr>
<tr><td>2026-07-13</td><td>Enabling 24-hour Agricultural Robotics: Unsupervised Day-to-Night Cross-Modal Image Translation for Nighttime Visual Navigation<br><a href='http://arxiv.org/pdf/2607.12065'>论文</a> | <a href='https://github.com/mamorobel/AgriNight'>代码</a></td><td>本文针对农业机器人夜间视觉导航难题,提出了一种无监督的日间到夜间跨模态图像翻译框架,将白天植物行的RGB图像转换为近红外夜间图像,从而可直接复用日间语义标签训练夜间感知模型,避免了昂贵的人工夜间标注。核心创新包括:◆ 利用预训练CLIP模型在翻译过程中保持语义一致性,使生成的夜间图像保留与日间图像一致的语义结构,显著提升下游分割任务的精度。◆ 引入可见性掩码以建模夜间NIR光照有限的有效范围,更真实地反映实际夜间成像条件。◆ 提出首个面向夜间农业视觉导航的基准数据集AgriNight,包含428张白天和549张夜间农田图像及像素级语义标注。◆ 通过大量对比实验和真实机器人夜间自主导航验证了方法的有效性,生成的夜间图像在质量和下游分割性能上均优于现有图像翻译方法,为农业机器人实现全天候作业提供了可行方案。</td></tr>
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
<tr><td>2026-07-10</td><td>Validating Virtual Reality for Studying Multimodal Human-Robot Interaction in Socially Aware Robot Navigation<br><a href='http://arxiv.org/pdf/2607.09261'>论文</a></td><td>该论文聚焦于验证虚拟现实(VR)能否真实再现真实环境中人机共导航时的多模态交互行为。研究团队开发了一个沉浸式VR原型系统,并通过21名被试的组内实验,对比了同一PR2移动机器人在动作捕捉真实场地与其VR复刻环境中的交互表现。

◆ 首次系统性地验证了VR在社会感知机器人导航研究中保留多模态交互动态的可行性,填补了该领域实证依据的空白。

◆ 采用组内实验设计,直接对比同一被试在真实场地与VR环境中的行为和主观感受,提高了实验内部效度。

◆ 同时采集轨迹与头部朝向数据,从行为层面多维度验证VR与真实世界交互的一致性。

◆ 选取正交交叉和擦肩而过两种典型共导航场景,涵盖面较广,具有一定代表性。

实验结果表明,被试在VR和真实环境中对机器人社会感知能力的评价相似,且行为反应模式也保持一致,从而证明VR可以作为研究社会导航和HRI中多模态行为的可靠且灵活的平台。</td></tr>
<tr><td>2026-07-10</td><td>Empirical Pedestrian Safety Assessment in a Mobile Robot Using a Predictive Social Force Model<br><a href='http://arxiv.org/pdf/2607.09192'>论文</a></td><td>本文针对移动机器人在人行道与行人共存的场景，研究如何同时保障客观安全性与行人主观舒适感。作者在传统社会力模型(SFM)的基础上，引入了投影碰撞时间(PTTC)并结合有限时域内的预测社会力向量，提出了预测型SFM(PSFM)与预测型TSFM(PTSFM)两种改进模型，并在非完整约束移动机器人上完成了实机部署与志愿者面对场景实验。

◆ 提出预测型社会力模型PSFM和PTSFM，在有限时域内对未来社会力向量进行积分以增强前瞻性

◆ 首次将SFM、TSFM、PSFM、PTSFM四种变体在真实非完整约束移动机器人上进行系统性对比实验

◆ 构建融合客观指标(最小PTTC、平均速度、最小距离、横向距离、最大轨迹曲率)与Likert量表主观评估的综合性安全评价体系

实验结果表明，集成PTTC的导航方法能够显著提升安全指标；然而在单行人场景中，预测机制的额外收益有限，主观评分经Mann-Whitney检验无显著差异，说明PTTC是改善行人安全的关键因素，而预测项的贡献相对有限。</td></tr>
<tr><td>2026-07-10</td><td>Vascular Geometry Characterization for AI-Based Endovascular Navigation<br><a href='http://arxiv.org/pdf/2607.09130'>论文</a></td><td>本论文针对急性缺血性卒中机械取栓术中强化学习自主导航缺乏标准化难度评估框架的问题，基于61例患者CT血管造影数据，系统研究了血管几何特征对导航性能的影响。研究构建了自动化血管特征提取流程，定量测量了主动脉弓类型、牛角弓、迂曲度、发出角、反向曲率等关键指标，并采用Soft Actor-Critic算法进行120秒自主导航实验。结果表明血管几何形态显著影响导航难度：左侧牛角弓和II/III型主动脉弓分别使导航时间延长30.19秒和37.92秒，迂曲度大幅增加导航耗时并降低成功率；右侧II/III型弓增加45.94秒，每个反向曲率使导航时间延长3.96秒。研究首次证实血管几何特征是MT智能体导航难度的关键决定因素。

◆创新点一：首次系统建立血管几何形态与强化学习导航难度之间的量化关联，揭示左右侧血管的关键影响因素差异。
◆创新点二：提出自动化、可重复的血管特征定量分析管线，为未来标准化复杂度分级与RL模型评估奠定基础。</td></tr>
<tr><td>2026-07-09</td><td>Behavior Foundations for Quadruped Robots: ABot-C0 Technical Report<br><a href='http://arxiv.org/pdf/2607.07370'>论文</a></td><td>该论文提出ABot-C0四足机器人通用运动控制系统，构建了三大互补的行为基础：多源运动数据管线、跨任务的鲁棒策略学习以及统一部署栈。研究团队通过条件视频生成合成、动捕标注、遥操作和人工设计搭建数据金字塔，产出了16,074条物理可行的运动片段，为多样化运动学习提供了数据基础。基于大规模数据训练的Flow-Matching通用策略首次在四足机器人上验证了运动跟踪的缩放规律，表现出对未见动作的零样本泛化能力。

◆ 通过条件视频生成合成、动捕、遥操作与人工设计四源融合，构建16,074条运动片段的数据金字塔，突破动物数据稀缺瓶颈。
◆ 首次在四足平台上验证运动跟踪的缩放定律，Flow-Matching通用策略随训练规模提升而性能单调增长，并具备零样本跟踪未见动作的能力。
◆ 采用三阶段特权到感知框架，结合时序LiDAR记忆与地形预测监督，实现复杂全地形鲁棒运动。
◆ 提出多策略协同的部署栈，支持平滑行为切换、能量高效控制与安全机制，支撑城市自主导航与陪伴式多模态交互的实际应用。</td></tr>
<tr><td>2026-07-09</td><td>FSD-VLN: Fast-Slow Dual-System Modeling for Aerial Long-Horizon Vision-Language Navigation<br><a href='http://arxiv.org/pdf/2607.08359'>论文</a></td><td>本文针对无人机长航时视觉语言导航（VLN）中全局多模态理解与序列动作生成之间的结构性错位问题，提出了FSD-VLN框架。该框架采用快慢双系统异步架构，将高层语义推理与低延迟飞行控制解耦，缓解了现有方法在长航时场景下轨迹抖动和决策延迟严重的问题。

◆ 慢速流：基于预训练视觉语言模型提取稳定的语义先验信息，为导航决策提供可靠的全局语义支撑。

◆ 快速流：采用扩散变换器（DiT）建模跨时间动作分布，生成时序一致的飞行控制指令，实现低延迟、高稳定性的动作输出。

◆ 引入时间感知自适应优化器，稳定长序列训练过程并有效抑制梯度振荡。

大规模低空仿真实验表明，该方法在未见场景上的导航成功率较现有最优方法提升最高达2倍，同时单步推理延迟和总任务运行时间均减少超过50%，验证了解耦式语义-控制建模的有效性，为长航时空中VLN提供了实用范式。</td></tr>
<tr><td>2026-07-08</td><td>Social-spatial dependencies for learning visual navigation<br><a href='http://arxiv.org/pdf/2607.07460'>论文</a></td><td>本文研究了社会性生物在视觉导航任务中的社会-空间依赖关系。研究团队训练了由独立神经网络控制的智能体，在不同社会情境中进行导航，社会依赖程度和策略选择由相对任务表现和空间效应决定。

研究发现，当高质量社会信息增加时，智能体的导航策略会发生相变，从独立导航转向跟随行为，并在拥挤觅食区域演化出避碰策略。此外，在可预测的非平稳环境中，智能体会在远端和近端分别发展出独立与社会导航的行为混合模式。

本研究的核心贡献与创新点如下：

◆ 提出自下而上的研究框架，通过独立训练的神经网络智能体研究社会导航行为，避免了仅从群体行为出发的局限性。

◆ 揭示了社会信息质量驱动的导航策略相变现象，从个体导航→跟随→避碰的阶段性转变。

◆ 发现可预测环境动态会引发个体与社会导航的行为混合模式。

◆ 强调社会-空间依赖关系对理解社会性生物行为的关键作用，挑战了仅分析个体行为的传统研究方法。</td></tr>
<tr><td>2026-07-08</td><td>HumAIN: Human-Aware Implicit Social Robot Navigation<br><a href='http://arxiv.org/pdf/2607.07357'>论文</a></td><td>该论文提出HumAIN框架，旨在通过知识蒸馏将隐式社交线索融入机器人规划循环，实现对人类行为的敏感感知。系统首先训练一个基于Transformer的教师模型，融合历史图像、骨骼关键点、机器人状态和目标位置等多模态输入学习人类感知轨迹表示，再通过轨迹重建与潜在特征对齐的双目标优化，将知识蒸馏至轻量级学生模型以支持实时部署。

◆ 创新点一：首次将步态、姿态等全身隐式社交线索整合至规划环节，有效桥接预测与规划模块之间的鸿沟。

◆ 创新点二：采用师生蒸馏架构兼顾表征能力与推理效率，适合在资源受限的嵌入式平台上实时运行。

◆ 创新点三：通过多模态融合策略使机器人具备自适应、鲁棒且社交合规的类人导航能力。

实验结果表明，HumAIN在所有轨迹预测指标上平均较现有最优基线提升29.8%，验证了利用隐式全身线索提升导航感知能力的有效性与实用性。</td></tr>
<tr><td>2026-07-08</td><td>GemNav: Discrete-Token Visual Robot Navigation using a Multimodal Large Language Model<br><a href='http://arxiv.org/pdf/2607.06882'>论文</a></td><td>GemNav提出了一种基于冻结多模态大语言模型（MLLM）的视觉机器人导航策略，挑战了传统依赖专用视觉编码器、定制动作头和大规模跨形态数据集的范式。核心创新包括：◆仅在语言塔上使用低秩适配（LoRA）微调，无需辅助视觉编码器与连续回归头；◆将路径点和分类导航信号统一映射到语言模型头生成的离散token词表，并引入软解码辅助损失以恢复纯交叉熵训练丢失的度量结构。该方法仅在8.7小时的开源数据上训练，规模比现有方案小约三个数量级。策略在四个物理差异显著的未知环境中实现零样本部署，20次真实试验中均能在距目标0.25至0.42米内停止。此外，实验发现引入短时图像历史可提升离线指标，但对真实机器人表现无明显收益，表明在预训练视觉特征充分时，时序上下文存在收益上限。</td></tr>
<tr><td>2026-07-08</td><td>STEMbot: A Compliant Robot for Under-Canopy Plant Navigation<br><a href='http://arxiv.org/pdf/2607.07873'>论文</a></td><td>针对有机农业中冠层下方害虫难以早期检测的问题，本文提出STEMbot微型攀爬机器人系统，通过自主攀爬植物枝干实现近距离害虫监测。

◆ 提出融合PIN-SLAM几何流水线与语义OcTree的感知框架，在机器人攀爬过程中实现鲁棒定位与全局一致的稠密建图。

◆ 提出流形约束A*规划器结合光线追踪目标指定方法，支持分支感知遍历及对叶背等遮挡目标区域的自主检查。

系统采用柔顺机构可稳定攀附7-33毫米直径的枝干，并在四种不同植物上完成了自主导航硬件实验验证。

几何重建结果与离线摄影测量基准对比的平均Chamfer距离小于1厘米，证明了系统的高保真建图能力与全局一致性。</td></tr>
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
<tr><td>2026-07-01</td><td>Path Planning in Physically Viable World Models<br><a href='http://arxiv.org/pdf/2607.00673'>论文</a></td><td>本文针对机器人在非结构化户外环境中使用过时地图进行长时规划的问题，提出了一种物理可行的世界模型用于路径规划评估。该系统通过将重建的3D高斯泼溅场景与基于物理的仿真相结合，能够在不重新采集传感器数据或重建地图的情况下，生成同一环境的物理修改版本，从而支持&quot;假设&quot;查询。

◆ 提出了物理可行的世界模型，将3D高斯泼溅场景重建与物理仿真深度融合，可针对未来地形变化生成物理修改后的环境副本

◆ 设计了地形感知的规划器，能够综合考虑世界模型模拟的物理事件、障碍物和地形形变，在路径提交前评估其可行性

◆ 在德州中部真实户外场地上，以多级严重程度的模拟洪水为干预条件进行系统验证

实验结果表明，该方法能够暴露仅基于原始重建环境规划时无法发现的长期路径失效和重规划行为，使机器人和操作员在部署前即可评估未来地形变化对路径可行性的影响，从而在撤退与恢复受限的约束环境中显著提升任务决策的安全性。</td></tr>
<tr><td>2026-07-01</td><td>Context-Triggered Robust MPC for Temporal Logic Specifications<br><a href='http://arxiv.org/pdf/2607.01515'>论文</a></td><td>本文研究离散时间线性系统在加性有界扰动下满足上下文相关线性时序逻辑(LTL)规约的鲁棒反馈控制综合问题。首先利用基于证书的条件保证可达-规避-停留(RAS)规约的几乎必然满足性,然后提出一种将鲁棒模型预测控制(MPC)与局部不变控制器相结合的切换控制架构,其中MPC值函数充当可达性证书,规避通过鲁棒约束实现,停留由局部控制器保证。为获得可计算的优化问题,采用凸对偶性将鲁棒约束转化为等价的确定性凸优化(凸二次规划或二阶锥规划)。在静态与动态环境下的机器人导航仿真验证了方法的有效性。

◆ 基于证书的RAS规约几乎必然满足性条件,为上下文触发的时序逻辑综合提供了低层控制理论基础。

◆ 切换控制架构融合鲁棒MPC与局部不变控制器,MPC值函数兼具可达性证书功能,鲁棒约束与局部控制分别保证规避与停留。

◆ 利用凸对偶理论将鲁棒约束重构为确定性凸优化问题,显著提升了计算可处理性。

◆ 相比Lyapunov方法具有更大的可行域,并天然支持动态环境与在线任务重配置。</td></tr>
<tr><td>2026-07-01</td><td>BIFROST: Bridging Invariant Feature Representation for Observation-space Sim2Real Transfer<br><a href='http://arxiv.org/pdf/2607.01410'>论文</a></td><td>针对机器人策略学习中sim2real迁移因仿真与现实间视觉和动力学差异而失败的问题，本文提出BIFROST方法。◆该方法通过跨域双模拟目标学习共享历史编码器，将仿真与现实中产生等效长期行为的观测-动作序列映射到邻近的潜在状态，从而域不变地捕获任务共享结构。◆不同于现有方法针对单一差距使用独立适配模块再堆叠组合的策略，BIFROST直接在原始观测空间统一处理视觉与动力学双重差距。基于该编码器，仿真中训练的策略可零样本迁移到现实，无需额外微调或适配模块。实验在sim2sim视觉导航、sim2real接触丰富操作和视觉伺服任务中均验证了BIFROST的有效性，而域适应与协同训练基线在这些任务中均告失败。</td></tr>
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
<tr><td>2026-06-29</td><td>Vision-Language Procedural Reasoning for Context-Aware Reward Modeling of Robotic Endovascular Guidewire Navigation<br><a href='http://arxiv.org/pdf/2606.30698'>论文</a></td><td>◆ 论文提出VL-PR框架，将视觉-语言程序推理引入机器人血管内导丝自主导航，以提升复杂血管环境中的上下文感知能力。
◆ 其核心创新是不让多模态大模型直接输出底层控制，而是根据实时视觉观察推断导航阶段、解剖语境和任务进展。
◆ 基于这些高层程序理解，系统动态调整不同奖励项的权重，实现上下文自适应奖励建模。
◆ 该方法使单一策略能够在推进效率、安全性、稳定性等竞争目标之间灵活权衡，并处理复杂阶段切换。
◆ 物理机器人平台实验表明，相比静态奖励方法，该框架提高了任务可靠性和导航效率，具备扩展到多任务血管介入流程的潜力。</td></tr>
<tr><td>2026-06-28</td><td>CORE Planner: Contextual-memory Oriented Reinforcement-learning in Unknown Environments for Robot Navigation<br><a href='http://arxiv.org/pdf/2606.29222'>论文</a> | <a href='https://github.com/BBD00/core_planner'>代码</a></td><td>◆ CORE Planner将传统规划的结构化表示与强化学习决策相结合，使机器人能在无先验地图的未知环境中高效导航到目标。

◆ 方法采用稀疏可见性图表示环境，相比稠密栅格地图降低计算开销，同时保留关键拓扑信息。

◆ 论文引入Transformer进行全局环境理解，并结合上下文记忆机制，缓解环境记忆不足和局部最优问题。

◆ 提出的可见性图稀疏化方法提升了大规模复杂场景中的计算效率和可扩展性。

◆ 该方法仅在图像仿真环境中训练即可实现零样本sim-to-real迁移，实验中路径长度较FAR Planner减少13%，较学习基线最高减少48%。</td></tr>
<tr><td>2026-06-28</td><td>Empowering a Single-Frequency GNSS Receiver to Achieve High-Precision Positioning with Relative Observations<br><a href='http://arxiv.org/pdf/2606.29192'>论文</a></td><td>◆提出一种紧耦合状态估计框架，使低成本单频GNSS接收机可结合轮速计、相机、LiDAR等相对运动传感器实现高精度定位。
◆设计滑动窗口因子图，将通用相对运动约束与由连续载波相位跟踪生成的全局“历元到锚点”约束统一融合。
◆引入虚拟锚点机制，在首次观测卫星时锁定其状态作为参考，从而摆脱物理基站依赖。
◆用单频多模态运动先验和鲁棒周跳恢复技术替代多频硬件冗余，保障廉价接收机的载波相位完整性。
◆大量真实实验表明，该方法可将单频GNSS定位精度从数米提升到分米级，为自主导航提供低成本可靠替代方案。</td></tr>
<tr><td>2026-06-27</td><td>Vision-Language Models for Deployable Social Robot Navigation: Bridging Semantic Reasoning and Low-Level Control<br><a href='http://arxiv.org/pdf/2606.28760'>论文</a></td><td>◆本文系统梳理了视觉语言模型在社会机器人导航中的作用，强调其可补足传统导航在语义理解、常识推理和自然语言交互方面的不足。
◆论文提出统一视角，将相关方法划分为高层VLM推理、低层规划控制，以及连接两者的中间机制三部分。
◆其核心创新在于给出一条面向部署的结构化路线图，涵盖语义推理、评估器、空间 grounding、中间表示和控制模块。
◆论文突出混合架构的重要性，指出VLM不能直接替代安全关键控制，而应与经典规划、避障和实时控制协同。
◆此外，文章综述了SRN相关数据集与评测平台，并总结了可靠性、实时性、安全性和社会规范适配等开放挑战。</td></tr>
<tr><td>2026-06-27</td><td>He3-Seeker: Robotic Information Planning for Lunar Helium-3 Distribution Mapping<br><a href='http://arxiv.org/pdf/2606.28746'>论文</a> | <a href='https://github.com/OpenSpace-Lab/He3-Seeker'>代码</a></td><td>◆论文首次形式化定义了月球氦-3主动探测与分布制图问题，针对传统遥感方法精度低、可靠性不足的缺陷提出新思路。
◆提出He3-Seeker框架，通过多点钻探、采样与原位分析实现更直接的氦-3分布获取。
◆引入机器人信息规划方法，指导机器人自主导航和主动感知，使采样路径更具信息增益。
◆设计了基于低分辨率轨道遥感数据生成高可信参考氦-3分布的方法，用于算法评估。
◆仿真实验证明He3-Seeker可快速、高保真地完成氦-3分布制图，并公开代码与仿真环境以促进复现。</td></tr>
<tr><td>2026-06-26</td><td>Regularized Reward-Punishment Reinforcement Learning<br><a href='http://arxiv.org/pdf/2606.28152'>论文</a></td><td>◆ 论文提出KL-Coupled Policy Regularization（KCPR），让奖励策略与惩罚策略互为动态学习的先验，实现策略层面的直接协同。
◆ 基于KCPR推导KL-Coupled Soft Optimality（KCSO），形成耦合软最优策略和KL正则化Bellman算子，使奖励与惩罚信息共同影响价值传播。
◆ 作者进一步实现深度算法klDMP，用于在复杂环境中训练兼顾任务收益与安全约束的智能体。
◆ 为提升稳定性，论文引入伴随先验软化机制，并研究分离回放缓冲区以平衡奖励和惩罚经验。
◆ 在网格世界和Gazebo机器人导航实验中，klDMP相比DQN、SQL和softDMP表现出更好的安全性与学习稳定性，同时保持有竞争力的任务性能。</td></tr>
<tr><td>2026-06-26</td><td>RS-Diffuser: Risk-Sensitive Diffusion Planning with Distributional Value Guidance<br><a href='http://arxiv.org/pdf/2606.27766'>论文</a></td><td>◆ 提出RS-Diffuser，将扩散式轨迹生成与风险敏感离线强化学习结合，面向安全关键场景处理罕见但灾难性的风险。

◆ 方法学习未来状态轨迹扩散模型，并通过独立逆动力学模型将规划轨迹解码为动作，提高规划与控制的模块化能力。

◆ 引入基于分位数回归的蒙特卡洛分布式价值评论器，用于估计候选轨迹的完整回报分布，而非仅关注期望回报。

◆ 在采样去噪过程中加入CVaR等尾部风险目标的梯度引导，使生成轨迹可按风险偏好进行调整。

◆ 单个训练好的模型仅需改变推理时风险参数，即可产生风险规避、风险中性或风险偏好行为。

◆ 在风险敏感D4RL和机器人导航任务中取得领先表现，同时提升平均回报、最坏情况鲁棒性并减少安全违规。</td></tr>
<tr><td>2026-06-25</td><td>Ordinal Neural Collapse as a Representation Prior for Visual Navigation<br><a href='http://arxiv.org/pdf/2606.26839'>论文</a></td><td>论文提出ORION，针对端到端视觉导航中编码器仅受动作损失间接监督、易学到动作无关表征的问题，引入更具结构性的表征先验。
◆ 将导航动作从Far Left到Far Right视为天然有序类别，显式利用动作间的序关系来组织视觉表征空间。
◆ 鼓励各类别表征沿单一判别轴顺序排列，同时压制类内离轴方差，减少模糊场景下的动作不一致。
◆ 将预训练编码器接入扩散式导航框架，并进行端到端微调，实现表征学习与策略生成的统一优化。
◆ 在仿真和真实环境中均取得更高成功率和目标推进效果，尤其在复杂多岔路口等视觉干扰强场景中优势明显。</td></tr>
<tr><td>2026-06-24</td><td>Learning Robot Visual Navigation in Crowds via Intention-Aware Scene Representations<br><a href='http://arxiv.org/pdf/2606.26047'>论文</a></td><td>◆论文提出iCrowdNav，一种面向拥挤人群的视觉导航方法，使机器人能从第一视角视觉观测中同时理解行人意图与环境结构约束。
◆不同于将行人简化为2D点的传统方法，该方法利用更丰富的人体姿态、运动和场景视觉线索构建意图感知场景表征。
◆其时空编码器用于提取场景占据信息，帮助机器人理解可通行空间和动态障碍分布。
◆提出Intent-Interact Former，通过注意力机制建模人体姿态与人际交互，从而推断行人的运动意图。
◆这些特征被融合为紧凑状态嵌入，用于深度强化学习策略训练，并在仿真和真实部署中均优于基线方法。</td></tr>
<tr><td>2026-06-24</td><td>Event-Adaptive Motion Planning with Distilled Vision-Language Model in Safety-Critical Situations<br><a href='http://arxiv.org/pdf/2606.25629'>论文</a></td><td>本文提出EAMP框架，面向安全关键导航中由动态智能体异常行为引发的语义事件，实现高层语义推理与低层运动控制的实时协同。
◆设计提示可配置语义事件触发器PC-SET，仅在检测到短时行为异常时激活语义干预，避免频繁调用大VLM带来的控制延迟。
◆提出事件触发的蒸馏SemNav-VLM，通过物理验证的语义蒸馏，将异常事件映射为离散策略级决策。
◆构建语义模型预测控制SMPC，把策略决策转化为优化目标和几何参考的动态重配置。
◆实验表明，EAMP在安全关键物流场景中提升动态安全裕度，同时保持实时效率，优于现有基线方法。</td></tr>
<tr><td>2026-06-24</td><td>GROVE: Grounded Pedestrian Simulation via Natural Language for Interactive Social Robot Navigation<br><a href='http://arxiv.org/pdf/2606.25504'>论文</a></td><td>◆提出GROVE，一个基于自然语言的行人仿真框架，可将文本提示直接转化为面向社交机器人导航的复杂场景。
◆支持紧急、排队、常规等预设，也允许自由输入提示，从而降低手工构建行人场景的成本。
◆通过长程人类行为、中程行人导航和短程人机社交交互等模块，分别保证仿真的真实性与合理性。
◆各模块会根据文本意图进行调节，并动态选择合适的SotA方法，以刻画不同情境下的行人行为细节。
◆系统已集成到Isaac Sim、Gazebo和RViz，并在住宅、医院、办公室等环境中验证，生成更真实、多样且具挑战性的社交导航测试场景。</td></tr>
<tr><td>2026-06-24</td><td>NavIsaacLab: Generating Realistic Crowd via Parallel Robot Learning for Benchmarking Human-aware Navigation<br><a href='http://arxiv.org/pdf/2606.26265'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-23</td><td>SkyJEPA: Learning Long-Horizon World Models for Zero-Shot Sim-to-Real Control of Quadrotors<br><a href='http://arxiv.org/pdf/2606.23444'>论文</a></td><td>◆提出SkyJEPA，将联合嵌入预测架构引入四旋翼高频实时控制，避免自回归预测误差随时间累积的问题。
◆构建潜在空间动力学模型，实现面向长时域的稳定预测，提升无人机在不确定环境中的决策能力。
◆设计物理启发式prober，将冻结的潜在表示映射为可解释状态，使长时域预测更具物理一致性。
◆将学习到的世界模型与采样式最优控制结合，并部署在嵌入式硬件上实现实时控制。
◆提出自动化、结构化数据生成流程，减少对昂贵且有风险的真实飞行数据采集依赖。
◆通过开环预测和户外闭环实验验证其零样本仿真到现实迁移能力及跨工况泛化性能。</td></tr>
<tr><td>2026-06-23</td><td>From Open Waters to Enclosed Cabins: ProteusVPR for Cross-Scene Visual Place Recognition in Maritime Perception and Cabin Inspection<br><a href='http://arxiv.org/pdf/2606.24234'>论文</a></td><td>◆论文聚焦船舶开放甲板与封闭舱室之间的跨场景视觉地点识别难题，指出现有VPR方法在海事机器人巡检中泛化不足。
◆提出ProteusVPR两阶段框架，先用任意标准VPR模型进行候选检索，再通过精细化模块提升定位精度。
◆创新设计几何-视觉估计网络，融合检索图像与前两帧时序信息，并引入几何描述子、局部仿射坐标系和相机方位角编码。
◆构建XHZ数据集，包含8K全景船载图像、多层舱室、甲板过渡区域及严格查询/数据库划分，支持更真实评测。
◆实验表明ProteusVPR可稳定增强多种VPR骨干网络，平均定位误差降低超过60%，展现出强鲁棒性和实用价值。</td></tr>
<tr><td>2026-06-23</td><td>Deep Learning Approaches for 3D Medical Scene Completion: From Geometric Modeling to Generative Paradigms<br><a href='http://arxiv.org/pdf/2606.24180'>论文</a></td><td>◆本文系统梳理了2016—2026年3D医学场景补全的发展脉络，覆盖从SSCNet体素语义补全到生成式扩散先验与高斯泼溅渲染结合的新范式。

◆论文总结了体素网格、点云学习、隐式神经场、Transformer、扩散模型和3D高斯基元等表示范式的演进。

◆其核心贡献是构建了较完整的分类体系，帮助理解不同方法在几何建模、语义补全和生成能力上的差异。

◆论文强调了生成式模型与实时渲染技术融合对高质量、可交互3D场景补全的推动作用。

◆最后，论文归纳了当前挑战，并提出下一代3D医学场景补全系统的研究方向。</td></tr>
<tr><td>2026-06-23</td><td>NavWM: A Unified Navigation World Model for Foresight-Driven Planning<br><a href='http://arxiv.org/pdf/2606.24101'>论文</a></td><td>◆NavWM提出统一的导航世界模型，将感知、潜在世界推理、动作预测与可控视觉生成整合到同一框架中，缓解传统导航策略的短视决策问题。

◆其核心创新是引入潜在世界token，用于提炼环境中的几何与语义先验，增强智能体对空间结构和时序动态的理解。

◆论文设计了基于anchor的多模态轨迹预测机制，生成多样化候选动作，避免确定性策略导致的模式坍塌。

◆NavWM将生成式世界模型用于闭环规划，通过“视觉预见”模拟未来状态并评估不同路径，从而选择更优导航决策。

◆在多种机器人数据集上的实验表明，NavWM在高保真未来状态生成和零样本导航成功率上均显著优于现有方法。</td></tr>
<tr><td>2026-06-22</td><td>DVL-DeepONet: A Physics-Guided Operator Learning for Resilient Underwater Navigation<br><a href='http://arxiv.org/pdf/2606.23502'>论文</a></td><td>◆提出DVL-DeepONet，一种物理引导的深度神经算子框架，用于在DVL波束缺失、噪声干扰或传感器配置受限时实现鲁棒水下速度估计。

◆该方法学习从时序惯性/DVL观测到AUV速度向量的非线性算子，突破传统模型在复杂海洋环境中对完整波束和精确传感器的依赖。

◆引入DVL测量物理一致性约束，使网络预测不仅依赖数据驱动学习，还符合DVL几何与测量机理。

◆设计了三类应用变体，分别支持惯性/DVL融合下的抗噪估计、仅DVL条件下的速度学习，以及缺失波束测量恢复。

◆基于约10,000米真实AUV航行实验验证，结果显示其相较模型方法和学习基线整体性能提升约40%，增强了低成本和受损感知场景下的导航韧性。</td></tr>
<tr><td>2026-06-22</td><td>Humanoid-OmniOcc: Stereo-Based Full-View Occupancy Dataset for Embodied AI<br><a href='http://arxiv.org/pdf/2606.22971'>论文</a> | <a href='https://d-robotics-ai-lab.github.io/humanoid-omniocc'>代码</a></td><td>◆提出Humanoid-OmniOcc，一个面向类人机器人具身智能的全景双目体素占据数据集，弥补现有自动驾驶数据集在视角、场景和几何先验上的局限。

◆数据集覆盖15个多样化仿真室内场景和5个真实环境，包含超过15.5万样本，具备较强的场景与风格多样性。

◆引入Real2Sim2Real闭环范式，用真实传感器规格构建物理准确仿真，再生成大规模标注数据并在真实采集上验证。

◆提出Humanoid Surround Stereo-guided Occupancy模型，利用双目深度先验提升2D到3D占据预测的准确性。

◆实验表明该方法优于单目基线，并能泛化到未见仿真场景和真实环境，验证了数据集与闭环设计的有效性。</td></tr>
<tr><td>2026-06-19</td><td>Long-Distance Real-World Navigation of the Legged-Wheeled Robot Go2-W Using Deep Reinforcement Learning<br><a href='http://arxiv.org/pdf/2606.21387'>论文</a></td><td>◆本文面向商用腿轮机器人Go2-W，构建了基于深度强化学习的运动控制器与自主导航系统，验证其在真实长距离场景中的可用性。
◆作者将此前用于四足机器人的仅依赖本体感知的策略扩展到16自由度腿轮机器人，实现了无需外部地形感知的稳健运动控制。
◆论文发现轮式运动会使负载集中于髋关节并导致过热，提出通过负载分配来抑制热集中、提升持续行驶能力的策略。
◆系统在筑波挑战2025中完成约2.8公里自主导航，覆盖人行道、公园和楼梯等复杂环境。
◆实验表明，该方法能在不因过热停机的情况下完成长距离真实世界导航，推进了腿轮机器人从实验室控制到实际应用的落地。</td></tr>
<tr><td>2026-06-18</td><td>Fast Human Attention Prediction for Fixation-guided Active Perception in Autonomous Navigation<br><a href='http://arxiv.org/pdf/2606.20491'>论文</a></td><td>◆提出GazeLNN，一种面向机器人主动感知的轻量级人类扫描路径预测模型，用Liquid Neural Networks作为循环核心，并结合MobileNetV3提取视觉特征。

◆模型以自回归方式根据当前图像和历史注视信息连续预测 fixation heatmap，从而模拟人类结构化视觉注意过程。

◆在仅需0.61 GFLOPs的计算量下，GazeLNN在MIT Low Resolution数据集上达到0.47 ScanMatch，取得领先性能。

◆相比现有循环式基线方法，该模型在多项指标上表现更优，同时将计算成本降低99.40%，推理速度最高提升6倍。

◆论文进一步将GazeLNN嵌入强化学习训练的主动相机-机器人控制策略，实现由人类注视引导的自主导航感知，并在真实空中机器人上完成验证。</td></tr>
<tr><td>2026-06-18</td><td>Slow Brain, Fast Planner: Latency-Resilient VLM-Augmented Urban Navigation<br><a href='http://arxiv.org/pdf/2606.20458'>论文</a></td><td>◆论文指出城市人行道导航中存在“轨迹评分鸿沟”：学习式规划器能生成好候选轨迹，但常因缺乏高层场景理解而选错。

◆提出VLM-Planner接口，让视觉语言模型从规划器候选轨迹中选择更合理的索引，而非用端到端VLA模型替代原规划器。

◆针对VLM 1–3秒推理延迟，设计无需训练的延迟鲁棒轨迹级融合层，将过期VLM选择通过几何相似度和指数衰减转化为实时评分。

◆实验显示，在约2000个真实复杂场景中，VLM选择相比规划器原最优输出将ADE降低30%，尤其改善路口和行人交互等难例。

◆仿真和实机验证表明，该方法在最高5秒延迟下仍保持80%以上成功率，并能在校园人行道上稳定运行。</td></tr>
<tr><td>2026-06-18</td><td>Vision-Reasoning-Guided Occlusion Removal from Light Fields<br><a href='http://arxiv.org/pdf/2606.19985'>论文</a></td><td>◆ 提出一种视觉推理引导的光场遮挡去除框架，将光场积分的物理可见性恢复能力与视觉语言模型的语义推理能力结合起来。

◆ 方法先利用多视角光场积分抑制前景植被等密集遮挡，生成可见性增强的初始场景表示。

◆ 引入视觉语言模型作为条件语义先验，在观测约束下修复退化结构并恢复细节，提升复杂自然场景中的重建质量。

◆ 设计多样本融合策略，将多个生成假设聚合为一致结果，从而减少幻觉伪影并增强恢复稳定性。

◆ 在合成和真实数据集上取得先进性能，在4个合成光场基准场景中获得最高平均SSIM，并展现出对结构化和非结构化采集条件的良好泛化能力。</td></tr>
<tr><td>2026-06-18</td><td>UNSEEN: Uncertainty-aware Navigation via Sparse Estimation in Unknown Environments<br><a href='http://arxiv.org/pdf/2606.20755'>论文</a></td><td>◆ UNSEEN提出一种仅依赖前置相机的统一导航框架，在未知环境中紧耦合定位、稀疏建图与规划，降低对多传感器和环境先验的依赖。
◆ 其核心创新是显式建模并传播位姿、地图和感知质量的不确定性，使规划不只追求到达目标，也主动选择有利于估计的运动。
◆ 系统以6Hz在线估计带不确定性的稀疏地图和机器人位姿，并在滚动时域内联合优化任务进展与定位精度。
◆ 相比传统松耦合管线和只优化单模块的感知感知方法，UNSEEN将运动指令与视觉感知的相互影响纳入同一决策闭环。
◆ 仿真和真实实验表明，UNSEEN-SLAM将绝对平移误差降低9.8%，UNSEEN-Plan最高提升45%估计精度，并实现100%任务成功率。</td></tr>
<tr><td>2026-06-17</td><td>Sensor Configuration Matters: A Systematic Evaluation of Multimodal SLAM on Quadruped Robots<br><a href='http://arxiv.org/pdf/2606.19067'>论文</a></td><td>◆本文针对四足机器人在足端冲击、机械振动和快速旋转下SLAM性能不稳定的问题，系统评估了传感器硬件配置对多模态SLAM的影响。
◆作者基于ANYmal D的GrandTour数据集，对视觉、视觉惯性、激光-视觉-惯性SLAM方法进行了统一比较。
◆论文量化分析了相机模态、快门类型和IMU等级在定位精度、鲁棒性与计算资源消耗之间的权衡。
◆实验发现，双目配置整体优于单目和RGB-D，全局快门相比卷帘快门更能减少运动导致的跟踪失败。
◆一个关键发现是，在剧烈腿式运动中，标准惯性融合反而可能削弱以视觉为主的SLAM性能。
◆论文最终给出了面向敏捷四足机器人的传感器载荷设计建议，为可靠自主导航提供了实践依据。</td></tr>
<tr><td>2026-06-15</td><td>SidewalkBench: Benchmarking Visual Navigation on Urban Sidewalks<br><a href='http://arxiv.org/pdf/2606.16953'>论文</a></td><td>本文提出了SidewalkBench，一个专为城市人行道视觉导航设计的综合基准，填补了该领域缺乏统一评估标准的空白。
◆基于NVIDIA Isaac Sim构建，实现了对多样化高保真人行道环境（含程序生成和真实扫描场景）的GPU加速仿真。
◆引入了丰富的基于事件的反应式行人行为及灵活高效的动画，支持在逼真的真实设定下进行模型标准化评估。
研究在330个单元测试、800个行人反应场景和105个长视距场景上对9种模型进行了全面评估。
结果揭示行人交互与长视距鲁棒性是现有模型的关键瓶颈，而利用合成数据扩大训练规模是极具前景的解决方案。</td></tr>
<tr><td>2026-06-15</td><td>MVOFormer: Flow-Semantic Transformer for Robust Monocular Visual Odometry<br><a href='http://arxiv.org/pdf/2606.16474'>论文</a></td><td>本文提出MVOFormer框架，旨在解决现有单目视觉里程计方法缺乏可解释互补特征或架构过于复杂的问题，从而显著提升鲁棒性与跨域泛化能力。
◆提出流-语义双分支编码器，协同融合密集几何运动线索与面向对象的语义先验，显式区分静态结构与动态干扰物。
◆设计迭代多模态解码器，实现由粗到细的位姿细化，并在融合多模态表征时动态抑制对不可靠区域的注意力。
实验表明，在无需任何目标域微调的情况下，该方法展现出卓越的零样本泛化能力。
在TartanAir和KITTI等多个基准测试中，MVOFormer显著超越了以往基于学习的帧间方法。</td></tr>
<tr><td>2026-06-15</td><td>SemGeoNav:A Safety-Guided Visual Navigation Approach with Semantic Reasoning and Geometric Planning<br><a href='http://arxiv.org/pdf/2606.16400'>论文</a></td><td>现有端到端视觉导航模型缺乏显式几何约束导致避障不可靠，而传统几何规划器难以处理高维视觉目标。为此，本文提出了一种新型分层视觉导航框架SemGeoNav，实现了基于图像的鲁棒导航并显著提升了避障能力。
◆将端到端模型的高级语义推理与基于几何方法的可靠局部规划能力进行紧密集成。
◆引入时间轨迹平滑机制以确保机器人连续且稳定的运动。
真实环境中四足机器人的实验表明，SemGeoNav在成功率和导航时间上均优于ViNT和NoMaD等代表性方法。</td></tr>
<tr><td>2026-06-15</td><td>Embedded Arena: Iterative Optimization via Hardware Feedback<br><a href='http://arxiv.org/pdf/2606.16190'>论文</a></td><td>本文核心贡献是提出一种基于硬件在环的智能体框架，以替代人类专家自主完成边缘微控制器上的AI模型与固件协同优化。
◆提出硬件在环的智能体竞技场机制，利用真实硬件的编译烧录与测量反馈，指导大语言模型进行模型与固件的闭环迭代协同优化。
◆验证了纯大语言模型完全无法完成部署，而引入硬件反馈后仅需3次迭代即可成功部署，7次迭代即可超越人类专家水平。
◆实现了极高的模型压缩比且精度损失极小，视觉模型压缩250倍而精度损失不足3.3%，音频模型压缩400倍，使商用微控制器能依靠太阳能实现无电池运行。
该方法在麋鹿检测相机和语音转录可穿戴设备等真实系统中的成功应用，充分证明了其实用价值与工程意义。</td></tr>
<tr><td>2026-06-15</td><td>VISTA: Scale-Aware Visual Navigation via Action History Conditioning<br><a href='http://arxiv.org/pdf/2606.17294'>论文</a></td><td>◆VISTA针对视觉导航基础模型中“归一化动作”带来的尺度敏感问题，指出不同缩放因子会改变同一轨迹的真实几何形状，从而影响部署安全性与性能。

◆论文提出将归一化动作历史与图像观测共同作为条件输入，使模型显式理解预测动作与机器人实际物理位移之间的关系。

◆该方法提升了模型对不同机器人尺度、动作执行尺度和环境变化的适应能力，增强零样本部署鲁棒性。

◆为应对视觉重复、特征不明显场景中的导航困难，VISTA引入DINOv3编码器，以获得更丰富的空间与几何表征。

◆实验表明，VISTA在室外、森林和办公室等真实未见环境中实现100%目标预测准确率，并平均通过95%的检查点，体现出稳定路径跟随能力。</td></tr>
<tr><td>2026-06-14</td><td>FlashNav: Ultra-Fast Policy Training for Robot Navigation within 20 Seconds<br><a href='http://arxiv.org/pdf/2606.15846'>论文</a></td><td>本文提出了FlashNav框架，首次将基于深度强化学习的机器人导航策略训练时间缩短至20秒以内。
该框架训练出的策略能够成功迁移至真实的轮式和足式机器人，在静态与动态室内场景中均展现出可靠的避障能力。
◆提出与导航MDP对齐的仿真理念，保留占据几何与测距感知等核心组件，移除冗余的渲染与高保真物理细节。
◆设计基于批量位图仿真器的全GPU常驻训练流水线，结合FastDSAC学习器在GPU上生成海量并行导航交互数据。
实验表明该框架在多种桌面GPU上均能实现数十秒内的极速训练，并在高端显卡上达到百分之百的成功率。</td></tr>
<tr><td>2026-06-14</td><td>Can Causal Models Enhance Robot Navigation? Online Causal Adaptation for Real-Robot Navigation<br><a href='http://arxiv.org/pdf/2606.15691'>论文</a></td><td>本文核心贡献在于成功将因果模型集成到真实机器人导航系统中，解决了因果模型在真实环境中部署研究不足的问题。
◆提出将因果模型作为离线评估模块，能准确预测导航轨迹的能力，其预测结果与路径效率正相关且与人类标注高度一致。
◆提出将因果模型作为在线自适应模块，在默认导航能力预测较低时进行干预，显著提升了转弯和避障等复杂场景的导航性能。
实验表明因果模型在任务复杂性增加时对导航的增强尤为有效，而在基线已近最优的简单场景中提升有限。
综上，本研究证明了用于行为解释的因果模型能够成功融入并增强真实机器人的导航系统。</td></tr>
<tr><td>2026-06-13</td><td>GuideWalk: Learning Unified Autonomous Navigation and Locomotion for Humanoid Robots across Versatile Terrains<br><a href='http://arxiv.org/pdf/2606.10449'>论文</a></td><td>本文提出了GuideWalk，一个统一的端到端框架，将可穿越性感知的导航引导与地形自适应运动教师相结合，以解决人形机器人在复杂地形上难以协调避障与动态可行运动的导航挑战。
◆提出一种提供显式速度引导的导航模块，将避障与地形条件解耦，从而实现跨多样环境的鲁棒规划。
◆设计了复合教师蒸馏方案，将目标导向指令和动态一致动作聚合并蒸馏至单一策略中。
◆结合强化学习和辅助行为克隆目标对蒸馏策略进行优化，在促进探索的同时保留了教师的优秀行为，进一步提升了鲁棒性。
实验证明，GuideWalk能够在保持人形机器人稳定运动的同时，实现有效且稳健的导航。</td></tr>
<tr><td>2026-06-13</td><td>G2IA: Geometry-Guided Instance-Aware Retrieval and Refinement for Cross-Modal Place Recognition<br><a href='http://arxiv.org/pdf/2606.15287'>论文</a></td><td>本文提出了一种用于跨模态地点识别的几何引导实例感知框架G2IA，突破了传统单一全局描述符匹配的局限，有效应对图像与点云间的模态差异和感知歧义问题。
◆在检索阶段，该框架创新性地将VGGT的视觉几何先验与实例特征相融合，构建出与激光雷达地图表征高度兼容的地点描述符。
◆在精炼阶段，提出通过显式验证局部实例形状及其相对空间布局在跨模态间的一致性，对检索候选进行细粒度重排。
实验证明，G2IA在不同定位阈值下均持续提升了图像到点云的地点识别性能。
同时，该框架还展现出了优异的跨数据集泛化能力。</td></tr>
<tr><td>2026-06-13</td><td>Driving, Fast or Slow? Neuro-Symbolic Guidance for Motion Prediction in Multi-Modal Ground Mobility<br><a href='http://arxiv.org/pdf/2606.15251'>论文</a></td><td>本文提出轨迹合规塑造神经符号框架，通过可解释的概率一阶逻辑增强黑盒运动预测主干网络，解决了现有方法缺乏现实交通规则与行为约束显式编码的问题。
◆提出智能体代码生成流水线，成功将交通规则的自然语言描述转化为概率运动预测的约束。
◆引入反应式数据流推理引擎，能够在场景演进时高效维护并更新合规态势。
◆设计神经置信度评分机制，通过上下文感知衰减合规信号，防止过度自信地误导主干网络的预测方向。
在Argoverse 2基准上的实验表明，该框架能持续提升最先进预测主干的性能，是纯神经预测器的有效且高效的补充。</td></tr>
<tr><td>2026-06-12</td><td>Sensitivity Shaping for Latent Modeling<br><a href='http://arxiv.org/pdf/2606.14585'>论文</a></td><td>本文针对生成式动力学模型中安全检测策略引发的分布外转换问题进行了研究。
现有方法在动力学对关键动作局部不敏感时会失效，导致未支持的动作产生类似演示的预测，从而掩盖了真实的预测误差。
◆揭示了现有固定动力学模型附加事后支持代理时，因局部控制不敏感导致分布外检测信号被抑制的失效机理。
◆提出了支持条件控制灵敏度正则化方法，在高等支持训练区域促进动力学对控制输入变化的敏感局部响应。
◆通过该正则化机制，有效保留了控制引起的变异，同时限制了因经验支持不足导致的不稳定外推。
实验表明该方法显著提升了分布外检测的准确性和闭环规划的安全性。</td></tr>
<tr><td>2026-06-12</td><td>SplatlessDF: Continuous Distance Field Mapping with Non-Splatting Gaussians<br><a href='http://arxiv.org/pdf/2606.13990'>论文</a></td><td>本文提出了SplatlessDF，一个从空间视角利用各向异性高斯元素的连续距离场建图框架。
◆直接参数化高斯并优化恢复可微分距离场，支持在空间域查询距离和梯度，满足机器人导航等下游任务需求。
◆将该方法与二维高斯泼溅耦合，构建仅基于高斯基元的统一框架，同时实现连续距离场学习、表面建模和光度渲染。
◆提出独立距离场与联合渲染两种设置，独立模式提供高效准确的查询，联合模式在改善渲染几何的同时建模距离场。
该研究证明了高斯表示不仅限于表面建模与渲染，在机器人导航建图中同样极具潜力。</td></tr>
<tr><td>2026-06-11</td><td>NavWAM: A Navigation World Action Model for Goal-Conditioned Visual Navigation<br><a href='http://arxiv.org/pdf/2606.13494'>论文</a> | <a href='https://dachii-azm.github.io/navwam/'>代码</a></td><td>这篇论文针对目标条件视觉导航任务,提出了导航世界动作模型(NavWAM),将原本仅用于预测的导航世界模型升级为可直接驱动闭环控制的策略模型,解决了传统世界模型必须依赖外部规划器(如CEM采样搜索)才能转化为可执行动作的问题。作者通过仿真预训练与真实机器人适配相结合的方式构建该模型,并在离线基准测试和真实机器人闭环部署中验证其在图像目标导航任务上优于基于规划的世界模型基线及代表性直接导航策略。

◆ 提出基于扩散Transformer的导航世界动作模型NavWAM,首次将未来观测预测、目标进度价值估计与动作序列统一编码到共享的潜在序列中进行联合学习。
◆ 通过将未来预测与决定闭环行为的动作目标、价值目标联合训练,使视觉前瞻能力可直接用于机器人控制,无需额外规划模块。
◆ 摆脱了对CEM式动作搜索的依赖,采用默认策略模式即可实现高效推理,在性能上反超基于规划的世界模型方法。
◆ 设计了仿真预训练加真实机器人适配的两阶段训练流程,有效弥合了仿真到现实的差距,实现了真实场景下的闭环部署验证。</td></tr>
<tr><td>2026-06-11</td><td>Traceable Virtual Sea Trials in the Marine Robotics Unity Simulator for Manoeuvring Assessment of Unmanned Surface Vehicles<br><a href='http://arxiv.org/pdf/2606.12349'>论文</a></td><td>本文扩展了开源MARUS模拟器，提出一种标准化的虚拟海试框架，用于无人水面艇回转和Z形试验的自动执行与数据生成。
◆开发了专门的TC与ZZ数据采集及后处理管道，生成面向系统辨识的即用型数据集，提升了模拟器操纵的重复性与可审计性。
◆实现了可追溯的指令与执行日志记录，并自动提取符合IMO和ITTC标准的操纵性指标。
◆针对差动推力转向提出了指令与执行的分离机制，将操纵输入记录为等效舵指令，实际执行记录为推力衍生的执行层代理。
案例研究验证了该框架可生成符合IMO标准的可重复操纵行为，有效支持水动力导数辨识与数字孪生工作流。</td></tr>
<tr><td>2026-06-10</td><td>MB-Loc: Multi-planar Bird&#x27;s-eye-view Localization in outdoor LiDAR scenes<br><a href='http://arxiv.org/pdf/2606.08744'>论文</a></td><td>本文提出了MB-Loc框架，解决了现有场景坐标回归方法计算效率低且对视角变化敏感的问题。
◆提出2.5D多平面鸟瞰图表示法，将点云沿Z轴切片并映射带符号深度至2D平面，在保留3D几何的同时利用2D卷积提升计算效率。
◆引入KL正则化潜在瓶颈模块，显式建模空间不确定性且不引入随机噪声，有效应对室外LiDAR的稀疏性。
◆在平面投影前应用3D空间增强策略，迫使网络隐式学习视角不变特征，显著提升旋转鲁棒性。
实验表明该方法在NCLT数据集上达到最优，且以实时推理速度实现了比传统3D架构更高的计算效率。</td></tr>
<tr><td>2026-06-10</td><td>Embodied-BenchClaw: An Autonomous Multi-Agent System for Embodied Spatial Intelligence Benchmark Construction<br><a href='http://arxiv.org/pdf/2606.11909'>论文</a></td><td>本文针对现有具身空间智能基准构建费时费力且易饱和的问题，提出了Embodied-BenchClaw这一自主多智能体基准构建系统。
◆提出了由规划、构建和评估三个智能体协调的五阶段自动化流水线，可根据用户评估意图端到端生成可更新的完整基准包。
◆引入了可扩展的技能库，提升了基准构建的可复用性和组合性。
◆设计了过程质量控制机制，确保基准构建过程可验证且可修复。
通过实例化多种跨载体和空间能力的基准并结合全面实验验证，表明该系统能显著减少人工成本，构建出可靠、可维护且具诊断价值的具身空间基准。</td></tr>
<tr><td>2026-06-10</td><td>SAFER-Nav: Enhancing Safety for Visual Robot Navigation via Segmentation-Aware Fine-Tuning<br><a href='http://arxiv.org/pdf/2606.11636'>论文</a></td><td>◆论文提出SAFER-Nav，通过分割感知微调将障碍物边界和可通行自由空间显式融入视觉导航策略中。
◆该方法针对仅依赖RGB输入的导航基础模型在陌生环境、未见障碍和分布偏移下容易产生不安全轨迹的问题。
◆与外部轨迹修正或手工几何先验不同，SAFER-Nav让策略在训练阶段直接学习安全相关的空间结构表示。
◆方法具有较强兼容性，可适配ViNT、NoMaD等不同RGB导航骨干模型。
◆实验覆盖多种机器人平台、室内环境以及静态和动态障碍场景，结果显示其显著降低碰撞率。
◆同时，SAFER-Nav在提升安全性的同时基本保持了原有的目标到达能力。</td></tr>
<tr><td>2026-06-09</td><td>AgniNav: Configuration-Driven Cross-Embodiment Local Planning for Robot Navigation<br><a href='http://arxiv.org/pdf/2606.10903'>论文</a></td><td>◆ AgniNav提出一种配置驱动的单目局部导航框架，使不同机器人形态间的迁移以“碰撞安全包络”为统一接口，而非依赖特定机体或相机安装。  
◆ 论文用高度、前长、后长、半宽四个可测参数描述机器人安全包络，其中高度用于条件化图像到伪激光扫描的感知网络。  
◆ 其余足迹参数被用于尺寸感知局部规划器，实现按机器人外形进行碰撞检测和轨迹选择。  
◆ 训练阶段利用彩色-深度配对数据生成高度条件化的列最小扫描标签，使同一图像可监督不同安全包络，无需为每种机器人重新采集数据。  
◆ 实验表明该方法可在Turtlebot2、Unitree Go2和K1人形机器人上零重训练部署，并在Jetson Orin上以30Hz运行，取得较高成功率和较低碰撞率。</td></tr>
<tr><td>2026-06-09</td><td>GUIDE: Goal-Initialized Directional Understanding for End-to-End Visual Navigation<br><a href='http://arxiv.org/pdf/2606.10832'>论文</a></td><td>传统基于学习的视觉导航依赖连续目标更新，不仅增加计算开销，且易在部分可观察下陷入局部短视与死胡同。为此，本文提出GUIDE框架，采用仅开局输入一次目标的目标初始化设定，培育机器人的内在方向感知以实现完全端到端的导航。
◆提出空间锚点预测器，利用多频率本体感受历史提取自运动表征，从而维持长视野的空间上下文与持久方向感。
◆结合原始深度流感知局部几何结构，使策略能够在无后续目标更新与先验地图的情况下克服短视行为。
实验证明，GUIDE使四足机器人能在密集障碍与结构化迷宫中安全导航，验证了其可靠的自运动与方向感知能力。</td></tr>
<tr><td>2026-06-09</td><td>MARCH: Model-Assisted Reinforcement Learning for the Perceptive Control of Humanoids over Sparse Footholds<br><a href='http://arxiv.org/pdf/2606.10288'>论文</a></td><td>本文提出了一种模型辅助的强化学习框架MARCH，旨在解决人形机器人在稀疏落脚点上感知行走的难题，有效结合了基于模型方法的精确性与无模型方法的鲁棒性。
◆利用简化模型生成安全参考轨迹，为安全关键的约束运动提供基础引导。
◆构建基于控制李雅普诺夫函数的奖励机制，以此引导特权教师策略的训练，确保运动的安全与精确。
◆将特权教师策略蒸馏为基于视觉的学生策略，实现从感知输入到动作控制的端到端部署。
该框架不仅提高了样本效率并减少了对复杂学习课程的依赖，还能生成更平滑的步态并在踏脚石任务上达到与无模型基线相当的精度。
该方法在仿真和实物中均得到验证，成功实现了Unitree G1人形机器人在带横向约束的稀疏落脚点上的安全导航。</td></tr>
<tr><td>2026-06-08</td><td>QuadVerse: An Integrated Framework Aligning Visual-Physical Reality for Quadruped Simulation<br><a href='http://arxiv.org/pdf/2606.07118'>论文</a></td><td>QuadVerse 是一个面向四足机器人仿真的集成框架,旨在解决仿真到现实(sim-to-real)迁移中视觉与动力学差距相互耦合、累积传播的问题。该框架以重建场景作为统一的校准基底,将视觉感知、物理交互与执行器动力学三方面对齐,从而显著缩小仿真与真实环境的差距。实验证明,QuadVerse 在重建质量与运动跟踪精度上均优于相关基线方法,并可在无需任务级真实环境采样的情况下,实现零样本视觉导航策略的稳健部署。

核心贡献与创新点如下:

◆ 提出 QuadVerse 集成框架,首次将视觉、接触物理与执行器动力学三类 sim-to-real 差距统一在同一校准基底上对齐,避免了传统方法分别处理所导致的误差累积与耦合问题。

◆ 基于 RGB 视频构建几何约束的 3D 高斯泼溅(3DGS)场景,既支持批量化的高真实感第一视角渲染,又可提取带语义的可碰撞网格,实现&quot;视觉渲染&quot;与&quot;物理仿真&quot;的双重可用性。

◆ 提出基于语义网格的接触校准方法:利用空间可变摩擦先验进行初始化,再通过轨迹后验搜索进行精细化优化,实现地形接触参数的精准建模。

◆ 设计残差动力学补偿器,在已完成接触校准的地形上回放真实轨迹进行训练,有效解耦地形接触误差与执行器非理想特性,使补偿更具针对性。

◆ 在上述基础上实现了无需任务级真实采样的零样本视觉导航策略部署,验证了该框架在真实机器人任务中的实用性与泛化能力。</td></tr>
<tr><td>2026-06-08</td><td>Efficient Minimal Solvers for Relative Pose Estimation in Autonomous Driving Applications<br><a href='http://arxiv.org/pdf/2606.09569'>论文</a></td><td>本文针对自动驾驶中相对位姿估计计算成本高且依赖大量特征匹配的局限，提出了一种基于新型平移参数化和一阶旋转近似的高效统一框架。
◆提出结合惯性测量单元垂直方向先验的高效最小求解器。
◆提出利用转向时旋转轴方向先验的高效最小求解器。
◆提出针对地面车辆平面运动假设的高效最小求解器。
这些方法通过减少所需的最小点对应数量并降低代数复杂度，显著加速了RANSAC流程中的假设生成。
实验证明，与现有算法相比，所提求解器在速度和精度间取得了更优的平衡，高度适用于实时自动驾驶系统。</td></tr>
<tr><td>2026-06-08</td><td>Virtual-point-based Solutions to Handle Generalized Absolute Pose Problem<br><a href='http://arxiv.org/pdf/2606.09294'>论文</a></td><td>针对现有PnP求解器无法处理多相机系统多投影中心的问题，本文提出了一种基于虚拟点的公式化方法。
◆创新地构建虚拟点公式，搭建了标准PnP与广义位姿问题之间的桥梁，提出可将现有PnP求解器转化为广义位姿求解器的统一流程。
◆基于该框架推导出三种虚拟点广义位姿求解器，即基于Cayley参数化的VGPc、四元数参数化的VGPq和旋转矩阵参数化的VGPr。
◆提出的求解器继承了原PnP算法的精度与效率并显著优于现有广义求解器，其中VGPc在异方差噪声下精度更高，VGPq保持全局最优，VGPr具备卓越计算效率且精度无损。
这项工作为多相机广义绝对位姿估计提供了统一且高性能的解决方案。</td></tr>
<tr><td>2026-06-08</td><td>VGP-Nav: Metric-Aware Visual Geometric Perception for Robot Navigation<br><a href='http://arxiv.org/pdf/2606.09268'>论文</a></td><td>本文提出了VGP-Nav框架，仅依赖单目RGB输入即可同时实现机器人的全局定位与度量一致的障碍物感知。
◆将基于定位的视觉几何锚定到由地平面几何推导出的物理尺度约束上，为单目感知提供了可靠的度量参考。
◆在线解决单目尺度歧义问题，生成可直接用于下游规划的基于定位的度量障碍物表示。
该方法避免了多传感器融合带来的复杂标定与高部署成本，克服了传统单目视觉系统无法兼顾全局定位与度量感知的缺陷。
广泛实验证明该框架在多种环境中具有强泛化能力，并在真实移动机器人上成功部署，实现了低成本且安全的自主导航。</td></tr>
<tr><td>2026-06-08</td><td>A Geometric Framework for Absolute Pose and Velocity Estimation with Event Cameras<br><a href='http://arxiv.org/pdf/2606.09139'>论文</a> | <a href='https://github.com/Zibin6/EventPoseVelocity'>代码</a></td><td>针对事件相机绝对位姿与速度同时估计的难题，本文提出了一种基于场景3D直线及其触发事件的几何框架。
◆提出了两个核心几何约束：3D直线与其对应事件平面法向量的正交性，以及事件与其关联直线2D投影的共线性。
◆针对绝对位姿估计，设计了高效的线性求解器和提供旋转全局最优解的多项式求解器。
◆针对速度估计，开发了兼顾效率的线性求解器和提升精度的基于优化的求解器，以恢复角速度和线速度。
该方法仅需最少三个事件与直线的对应关系即可独立确定6自由度绝对位姿或速度。
实验表明该方法实现了目前最优性能，在精度和计算效率上均显著优于现有方法。</td></tr>
<tr><td>2026-06-08</td><td>Bayesian Optimization for Learning Nonlinear MPC in Autonomous Agent Navigation<br><a href='http://arxiv.org/pdf/2606.14763'>论文</a></td><td>◆提出一种无地图自主导航框架，将基于LiDAR的高斯占据表示、滚动时域A*反应式规划与非线性MPC紧密结合，实现动态未知环境中的实时避障与轨迹跟踪。
◆在MPC中引入平滑sigmoid障碍物屏障，并通过CasADi/IPOPT求解，提高了碰撞约束处理的连续性与控制可实现性。
◆采用基于TPE的离线贝叶斯优化，自动寻找对导航综合目标近优的控制器参数，缓解MPC参数敏感问题。
◆利用高斯过程代理模型分析参数敏感性和优化景观，为参数选择提供可解释性。
◆该方法具有机器人无关性，并在Unitree Go2仿真和实机上验证，显示仿真调参可有效迁移到硬件，部署成功率最高达90.0%，仿真指标平均提升38.9%。</td></tr>
<tr><td>2026-06-04</td><td>Towards Realistic 3D Sonar Simulation<br><a href='http://arxiv.org/pdf/2606.06130'>论文</a></td><td>现有三维声纳仿真通常依赖几何驱动渲染，将其视为水下激光雷达，忽略了折射和多径干涉等基本声学现象。
◆提出一种结合GPU加速图形引擎与物理声学传播原理的模块化真实三维声纳仿真架构。
◆在NVIDIA Isaac Sim中实现了基于Water Linked 3D-15的体积三维声纳模型并集成到水下仿真框架中。
◆通过硬件在环配置验证系统，在Jetson Orin Nano上运行改进的FastLIO2融合多源合成数据。
最后通过与真实港口检测数据的对比，刻画了仿真与现实的差距，并为全声学驱动的体积感知指明了路线图。</td></tr>
<tr><td>2026-06-04</td><td>LongSpace: Exploring Long-Horizon Spatial Memory from Perception to Recall in Video<br><a href='http://arxiv.org/pdf/2606.05677'>论文</a></td><td>针对现有多模态大语言模型在长视距任务中缺乏对先前空间布局和视角变化等空间记忆进行检索与回忆的能力，本文进行了深入研究。
◆提出LongSpace-Bench基准，这是一个基于房间漫游视频的长视距空间记忆评测数据集，全面覆盖场景感知、空间关系和空间记忆三大维度。
◆提出LongSpace记忆框架，将长视频建模为序列块进行处理，突破了长视频空间推理的瓶颈。
◆在解码器早期层引入3D结构线索，增强了模型对底层空间结构的感知与建模能力。
◆构建层感知记忆机制，实现了问题引导下的精准空间信息检索与召回。
实验表明该框架显著提升了长视频空间理解能力，证明了显式空间记忆是长视距视频模型的关键能力。</td></tr>
<tr><td>2026-06-03</td><td>WAM-Nav: Asymmetric Latent World-Action Modeling for Unified Visual Navigation<br><a href='http://arxiv.org/pdf/2606.04907'>论文</a></td><td>本文提出WAM-Nav，一种用于具身视觉导航的潜在世界-动作模型，通过联合学习动作生成与潜在视觉预见，解决了现有反应式策略缺乏前瞻性和模块化方法易产生误差累积的问题。
◆采用共享扩散Transformer进行非对称联合扩散，同时生成长视界动作与短视界视觉预见，有效降低了多步自回归带来的推理延迟与视觉误差累积。
◆引入双流上下文条件机制，将片段级自运动历史与序列视觉观察相融合，促使生成更加平滑且一致的导航轨迹。
◆设计统一目标对齐模块，保持不同目标类型的平衡表征，使单一策略即可同时支持图像目标、点目标及无目标探索任务。
实验证实该模型泛化性优异，图像目标与点目标导航成功率分别提升15.7%和3.3%，并在真实场景中实现了85%的零样本迁移成功率。</td></tr>
<tr><td>2026-06-03</td><td>Recent Advances and Trends in Learning-based 3D Representations<br><a href='http://arxiv.org/pdf/2606.04871'>论文</a></td><td>本文系统综述了基于学习的三维表示方法，涵盖从传统离散显式格式到新兴连续隐式场及基元泼溅的演进。论文详细阐述了各类表示的公式变体、优缺点及关键应用，并总结了开放挑战与未来方向。与广泛讨论三维重建的综述不同，本文核心贡献在于聚焦表示本身的演进。
◆聚焦三维表示自身的演进过程，而非宽泛地讨论三维物体与场景重建。
◆着重强调向隐式表示和基于基元的表示的范式转变。
◆提供新兴三维格式如何从根本上改变三维与四维工作流的新颖视角。</td></tr>
<tr><td>2026-06-03</td><td>MineXplore: An Open-Source Reinforcement Learning Exploration Benchmark for GNSS-Denied Underground Environment<br><a href='http://arxiv.org/pdf/2606.04569'>论文</a></td><td>本文提出了MineXplore，首个基于真实生产矿山几何结构且兼容GPU加速的开源强化学习探索基准，解决了地下无GNSS环境下缺乏高保真仿真平台的问题。
◆提出六阶段轮廓到MJCF的转换流程，构建了超十万平方米的隧道网络，并引入八边形截面、激光雷达锯齿墙壁、多摩擦区、全局倾斜和周期性光照等真实矿井特征。
◆通过高达0.9538的交并比和79.4%的六维表面纹理相似度，严格验证了环境重建的高几何与视觉保真度。
◆基于RLlib的单智能体PPO基线实现了88.89%的最佳滚动覆盖率，证实该基准能支持在真实地下感知与拓扑约束下进行稳定且可复现的策略学习。
MineXplore填补了开源生态系统的空白，为极端地下环境下的自主导航研究提供了标准化的测试平台。</td></tr>
<tr><td>2026-06-03</td><td>MAD: Mapping-Aware World Models for Agile Quadrotor Flight<br><a href='http://arxiv.org/pdf/2606.04534'>论文</a></td><td>本文提出了MAD，一种用于敏捷四旋翼飞行的建图感知世界模型，解决了传统纯反应式方法在杂乱场景中面临的部分可视和高延迟问题。
◆摒弃原始图像重建，通过学习循环潜在动力学来重建以机器人为中心的占据栅格图、可视栅格图及本体感受状态，强制潜在状态编码与避障直接相关的局部几何和可视历史。
◆在DiffAero框架中利用GPU并行建图模块进行训练，为占据和可视状态提供高吞吐量的监督信号。
基于该模型的智能体在导航和竞速任务中实现了更高的成功率和更快的飞行速度，展现出优越的跨任务迁移能力，并能生成可解释的地图预测和精准的自运动估计。
策略成功部署于实体四旋翼，在有限感知下实现安全飞行，仿真与真实森林实验最高速度分别达9.66m/s和5.05m/s。
这项工作证明了建图感知世界模型在模块化导航与端到端学习之间提供了实用的折中方案。</td></tr>
<tr><td>2026-06-03</td><td>Uncertainty-Aware Adaptive Sensor Fusion for Autonomous Navigation<br><a href='http://arxiv.org/pdf/2606.05437'>论文</a></td><td>本文提出一种结合混合深度学习与无迹卡尔曼滤波的方法，以提升视觉惯性里程计在自主导航中的姿态估计精度。该模型采用视觉Transformer网络提取IMU数据的时间依赖性，并利用多尺度卷积神经网络学习视觉数据的光流运动线索。
◆提出自适应传感器融合模块，通过利用估计的不确定性对视觉和惯性特征进行动态加权，增强了复杂环境下的鲁棒性。
◆设计新颖的不确定性感知损失函数，将预测不确定性显式融入学习过程，有效应对噪声或不完整的传感器输入。
在KITTI数据集上的评估表明该方法在绝对轨迹与相对位姿误差上显著超越基线，且在A100上达155帧每秒的高效处理速度，极适于资源受限系统。</td></tr>
<tr><td>2026-06-02</td><td>Autonomous Navigation System for Library Service Robot Based on Unitree Go2 Edu<br><a href='http://arxiv.org/pdf/2606.03340'>论文</a></td><td>本文提出了一种基于Unitree Go2 Edu四足机器人的ROS 2自主导航系统，专为图书馆狭窄过道和动态环境设计。该系统集成了4D激光雷达、深度相机和IMU，并融合了RTAB-Map视觉激光SLAM、AMCL与EKF定位以及基于Nav2的A*和DWA规划算法。
◆突破传统将图书馆视为崎岖地形的假设，专注解决实际部署中的移动不连续性问题，如地面过渡、临时杂物和部分受阻通道，克服了低底盘轮式平台的局限。
◆构建了针对四足机器人的多传感器融合与完整导航堆栈，实现了复杂室内场景下的精准建图、定位与动态避障。
◆在真实图书馆中进行了严格验证，系统在静态、低密度动态和高密度动态场景下的导航成功率分别达到100%、96%和88%，且建图平均误差仅为3.7厘米，证明了其高效性与准确性。</td></tr>
<tr><td>2026-06-01</td><td>Adversarial Dual On-Policy Distillation from Expressive Teacher<br><a href='http://arxiv.org/pdf/2605.27095'>论文</a> | <a href='https://github.com/vanzll/FA-OPD'>代码</a></td><td>针对现有具身控制模仿学习方法仅依赖离线专家数据而缺乏在线纠正信号，且标准在线策略蒸馏无法适用于仅有演示场景的问题，本文提出了FA-OPD方法。该方法从演示中学习流匹配教师并与轻量级MLP学生共同训练，在学生交互过程中提供双通道互补信号。
◆设计奖励通道，通过学习状态-动作对的专家相似性目标来驱动长视野策略优化，促进在线探索。
◆设计动作通道，在学生实际访问的状态上提供密集的局部目标，稳定策略的利用。
◆将双通道巧妙耦合，使奖励蒸馏能够泛化超越逐点演示，同时动作蒸馏将探索锚定在类专家行为附近。
实验表明，在六个机器人导航、操作和运动基准测试中，FA-OPD超越了强基线，并在噪声或有限演示条件下展现出显著增强的鲁棒性。</td></tr>
<tr><td>2026-06-01</td><td>Co-training with Ego-centric Video and Demonstration for Robot Navigation Task<br><a href='http://arxiv.org/pdf/2606.01951'>论文</a></td><td>现有的视觉语言动作模型依赖昂贵的真实机器人数据，且将第一人称人类视频应用于移动机器人导航面临视角变化的挑战。本文提出了一种将第一人称行走视频转换为移动机器人模仿学习数据集的框架。
◆该方法通过估计人类视频中的相机运动，将其转换为与地面移动机器人兼容的动作表示。
◆通过联合训练人类衍生数据与机器人收集数据，克服了单一数据源的局限，提升了模型的语言理解与动作生成鲁棒性。
实验验证了第一人称人类视频作为移动机器人学习有效且可扩展数据源的潜力。</td></tr>
<tr><td>2026-06-01</td><td>Adversarial Attacks on Robot Localization Systems via Deep Feature Perturbation<br><a href='http://arxiv.org/pdf/2606.01892'>论文</a></td><td>本文研究了基于深度学习的机器人定位系统面对对抗攻击的脆弱性，提出了一种针对视觉定位中乘积量化的对抗查询生成框架。
◆提出轻量级乘积量化网络（LPQN）来扰动查询特征编码，误导检索过程返回语义无关的数据库条目。
◆设计了前向与反向两阶段生成程序，前向传播扰动特征分布，反向传播通过优化细化扰动。
◆LPQN的轻量化设计能够在极小的计算开销下，生成细微却高效的对抗性扰动。
大量受控与真实机器人环境实验证明，该方法显著降低了定位系统性能，暴露了实际应用中的关键安全漏洞。</td></tr>
<tr><td>2026-06-01</td><td>PlatonicNav: Unveiling Semantic Correspondence in Navigation with Platonic Topological Maps<br><a href='http://arxiv.org/pdf/2606.01788'>论文</a> | <a href='https://github.com/AIGeeksGroup/PlatonicNav'>代码</a></td><td>本文将柏拉图表示假设扩展至具身导航领域，把纯视觉对象导航、跨模态对象导航和视觉语言导航统一为同一对象中心语义流形的三种接口，提出了免训练的PlatonicNav框架。该框架通过构建柏拉图拓扑图并融合几何与语义节点距离，在仿真基准和实体机器人上验证了其无需显式跨模态训练即可跨任务、跨模态与跨实体泛化的能力。
◆提出免训练框架PlatonicNav，构建柏拉图拓扑图，融合自监督视觉编码器中的几何与语义节点距离。
◆利用盲匹配机制实现语言目标对齐，无需任何配对的视觉-语言数据或显式跨模态监督。
◆验证了独立训练的视觉与语言编码器共享通用语义结构，揭示了纯视觉建图即可实现语言对齐的潜力。</td></tr>
<tr><td>2026-06-01</td><td>Embedding Semantic Risk into Distance Fields and CBFs for Online Monocular Safe Control<br><a href='http://arxiv.org/pdf/2606.01605'>论文</a></td><td>本文提出了一个在线单目感知到控制框架，将语义风险直接嵌入到控制障碍函数所使用的欧几里得符号距离场中，实现了语义感知的安全导航与遥操作。
◆提出将语义信息直接编码到ESDF中，在控制优化前融合语义风险，使高风险物体在安全场中产生更大的空间影响。
◆结合基础模型SLAM前端与逐帧语义分割，从单目RGB视频在线重建并融合具有像素级类别标签的密集3D几何结构。
◆在ESDF计算前施加依赖类别的膨胀，并通过依赖类别的增益进一步调节CBF控制器的响应，改变了以往仅在下游调整控制器的方式。
实验表明该框架能以10至20赫兹的频率在线运行，并在遥操作和自主导航中成功展现出语义感知的安全行为。</td></tr>
<tr><td>2026-06-01</td><td>Hierarchical Object Representation for Spatial Robot Perception: Points, Meshes, and Superquadrics<br><a href='http://arxiv.org/pdf/2606.01545'>论文</a> | <a href='https://github.com/perceptica-robotics/Hickory'>代码</a></td><td>本文提出了一种用于空间机器人感知的层次化物体表示方法，解决了现有三维场景图中物体几何表示过于简化的问题。该表示方法能够支持高保真物体重建、鲁棒重定位与安全导航规划。
◆设计了四层渐进式抽象的几何表示结构，从原始传感器数据逐步过渡到密集三维网格，最终提炼为超二次曲面解析基元，实现了稀疏且解析的几何表达。
◆开发了直接从机器人RGB-D图像流构建该层次化表示的完整处理流程，验证了其在室内外开放集物体场景中的有效性。
◆提出基于超二次曲面的地图对齐方法，在多种数据集上的表现超越了当前最先进方法ROMAN，并实现了密集环境下高效且解析的碰撞检查。</td></tr>
<tr><td>2026-05-31</td><td>DeepIPCv3: Event-Aware Multi-Modal Sensor Fusion for Sudden Pedestrian Crossing Avoidance<br><a href='http://arxiv.org/pdf/2606.01277'>论文</a> | <a href='https://github.com/oskarnatan/DeepIPCv3'>代码</a></td><td>本文提出了DeepIPCv3多模态自动驾驶框架，旨在解决传统帧传感器在突发行人穿越场景下存在的感知延迟和运动模糊问题。
◆提出受Transformer启发的跨模态注意力机制，动态关联激光雷达的稠密三维空间几何与动态视觉传感器的微秒级异步事件流，在保留场景结构感知的同时优先处理高速动态更新。
◆设计混合策略网络，将启发式轨迹跟踪与直接神经预测相结合，把融合后的潜表征精准映射为安全局部航点和可执行控制命令。
◆构建涵盖正午和夜间挑战性条件的自定义多模态数据集进行严格离线评估，证明该融合方式能消除曝光失效与运动模糊，取得最低的轨迹和控制命令误差。
该框架不受环境光照影响，能够实现高度敏捷且数学上有界的规避机动，相关代码即将开源。</td></tr>
<tr><td>2026-05-31</td><td>OSCAR: Obstacle Survival Curves for Adaptive Robot Navigation<br><a href='http://arxiv.org/pdf/2606.00990'>论文</a></td><td>该论文提出了OSCAR框架，解决移动机器人在图导航中遇到临时障碍物时等待与绕行决策效率低下的问题。传统方法通常采用固定规则，忽略了不同类型障碍物持续时间的差异。
◆引入生存建模方法，利用在线经验学习基于障碍物类别的剩余清除时间分布，并创新性地处理了机器人提前绕行时产生的右删失观测数据。
◆将生存模型集成到时间相关的图规划器中，为每个被阻塞的边动态计算耐心阈值，智能平衡等待与绕行的时间成本。
◆框架具备持续更新能力，能够跨导航回合不断优化清除时间估计。实验表明，该方法在仿真中不到20次观测即可收敛至接近真实分布的Oracle水平，真实部署也验证了其在线学习与自适应优化的有效性。</td></tr>
<tr><td>2026-05-30</td><td>BEVIO: Efficient Bird&#x27;s-Eye-View based Sparse-Update Visual-Inertial Odometry for Lunar Day-Night Navigation<br><a href='http://arxiv.org/pdf/2606.00709'>论文</a></td><td>针对月球车在极端资源限制下视觉更新稀疏以及昼夜自照明导致特征关联困难的问题，本文提出了BEVIO算法。
◆提出基于鸟瞰图的图像匹配方案，增强了对较大帧间运动的鲁棒性。
◆在视觉外观发生显著变化时，依然能实现可靠的特征匹配，克服了昼夜及自照明环境的挑战。
通过高保真月面仿真和半比例月球车真实长时昼夜部署实验进行了广泛评估。
结果表明，该方法在视觉更新率低至0.25赫兹时仍能实现可靠的昼夜导航，非常适合算力与功耗受限的月球车。</td></tr>
<tr><td>2026-05-29</td><td>Collaborative Navigation and Exploration with $β$-Sparse Gaussian Processes<br><a href='http://arxiv.org/pdf/2605.26304'>论文</a></td><td>针对未知环境下异构机器人协同导航面临传感、通信和计算限制的问题，本文提出了一种领航机器人与移动传感器机器人的协同导航框架。该框架使传感器能在带宽受限的情况下，在线联合选择传输的地图点与导航动作，并预测未探索区域。
◆提出β-稀疏高斯过程模型，这是一种用于任务感知诱导点选择的新颖且鲁棒的变分稀疏高斯过程模型。
◆开发了一种动作选择策略，有效平衡了任务相关性与环境探索。
仿真实验表明，该框架相比无通信场景可减少18%的路径成本，相比原始数据传输基线可减少76%的信息传输量。</td></tr>
<tr><td>2026-05-29</td><td>Replicable Simulation-Based Robot Validation through Provenance<br><a href='http://arxiv.org/pdf/2605.29973'>论文</a></td><td>该论文针对基于仿真的机器人测试可复现性不足的问题，提出将数据溯源与FAIR原则相结合以提升测试文档的透明度。
◆提出将数据溯源与FAIR原则深度融合，通过追踪产物关联和添加关于文件来源与设计决策的机器可读元数据来保障验证的可复现性。
◆强调溯源与元数据不应作为最终数据集的事后补充，而必须内嵌于生成数据集的测试流程中，从而实现测试证据的端到端重建。
论文通过扩展现有仿真测试框架引入溯源跟踪与元数据收集机制，成功对移动机器人导航数据集进行了结构化溯源与FAIR元数据的丰富。
最后，论文总结了集成过程中遇到的词汇对齐、属性选择与领域标准采用等障碍，并为在机器人验证工作流中实施以溯源为中心的FAIR元数据提供了可操作建议。</td></tr>
<tr><td>2026-05-29</td><td>AR Forcing: Towards Long-Horizon Robot Navigation World Model<br><a href='http://arxiv.org/pdf/2605.31314'>论文</a></td><td>本文针对基于扩散的机器人导航世界模型中训练与推理存在的分布偏移导致长程预测不稳定的问题，提出了AR Forcing自回归训练策略。
◆将标准扩散损失整合到自回归训练循环中，消除了并行监督与自回归推理之间的不一致。
◆模型每一步利用自身预测更新上下文并优化单步噪声预测目标，使训练显式暴露于推理状态分布。
◆无需引入额外判别器或分布匹配损失，保留了原始扩散框架与采样器，易于集成。
实验表明，该方法在多域导航数据集上显著提升了长程导航的图像生成一致性与轨迹预测精度，增强了模型在复杂环境下的鲁棒性。</td></tr>
<tr><td>2026-05-29</td><td>Geometry-Aware Control Barrier Functions for Collision Avoidance via Bernstein Polynomial Approximations<br><a href='http://arxiv.org/pdf/2605.30696'>论文</a></td><td>针对具有不规则几何形状机器人和障碍物的安全导航问题，传统控制障碍函数的形状代理往往过于保守或导致约束数激增。本文提出了一种基于伯恩斯坦多项式符号距离场的几何感知控制障碍函数。
◆提出基于BP-SDF的统一表示方法，将障碍物与机器人统一建模，并以统一的最小距离来表示障碍函数。
◆利用伯恩斯坦多项式的可微性，可以轻松地以闭环方式强制执行控制约束。
仿真结果表明，该方法在单机器人导航和异构多机器人避碰场景中均能高效保障安全。</td></tr>
<tr><td>2026-05-29</td><td>Predicted-Flow Control Barrier Functions for Real-Time Safe Optimal Control<br><a href='http://arxiv.org/pdf/2606.00297'>论文</a></td><td>该论文针对传统控制屏障函数(CBF)难以构造且具有短视性的问题,提出了预测流控制屏障函数(P-CBF)框架,将CBF从当前状态的函数推广为有限预测时域内参数化控制规划下预测流的泛函,使安全保证覆盖整个预测时域,并通过单一凸优化(在多面体约束下退化为二次规划)统一了有限时域积分代价优化与安全认证,所提出的FlowBarrier算法在非完整地面机器人密集环境导航实验中相比非线性MPC和两种CBF安全滤波方法实现了最高目标到达率、零安全违例和最低计算耗时。

◆ 提出预测流控制屏障函数(P-CBF)概念,将传统基于当前状态的CBF推广为基于参数化控制规划下预测流的泛函,克服了CBF的短视性缺陷。

◆ 引入终端候选P-CBF机制,要求预测流在终端时刻进入备份安全集,从而解决了控制约束下P-CBF有效性难以保证的问题。

◆ 创新性地提出规划时移(planning-time shift)概念,通过调节预测时域长度提供额外自由度,确保优化问题的可行性。

◆ 实时控制量、控制规划参数与规划时移由单一凸优化联合求解,保证可行性并使关联安全集前向不变,在多面体控制约束下可简化为QP问题。

◆ 实现了有限时域积分代价优化与全时域安全认证的统一框架,并通过FlowBarrier算法在100次实验中验证了其在到达率、安全性和计算效率上的全面优势。</td></tr>
<tr><td>2026-05-28</td><td>Trust, Geometry, and Rules: A Credibility-Aware Reinforcement Learning Framework for Safe USV Navigation under Uncertainty<br><a href='http://arxiv.org/pdf/2605.26974'>论文</a></td><td>本文针对无人水面艇在感知不确定性下安全且符合COLREGs规则的导航难题，提出了一种融合感知可信学习、几何安全屏蔽与连续规则感知嵌入的强化学习框架。
◆可信度加权价值学习通过滤波协方差与经验误差的差异推导动态信任因子，调节评论家异方差损失，防止策略对噪声过拟合。
◆协方差膨胀速度障碍将位置估计不确定性映射为角度裕度，构建保守的几何屏蔽以覆盖危险探索动作。
◆风险感知的COLREGs责任嵌入将二元相遇责任松弛为连续规则信号，提供平滑扇区转换信息并抑制稀疏奖励引起的振荡。
仿真实验表明，该框架能有效提升应对感知不一致的训练鲁棒性，并在避碰与规则合规性上显著优于基线方法。</td></tr>
<tr><td>2026-05-28</td><td>Fisher-Preserving Guidance: Training-Free Manifold Constraints for Safe Diffusion Control<br><a href='http://arxiv.org/pdf/2605.29937'>论文</a></td><td>本文针对扩散模型在视觉导航中因更新偏离训练流形而导致轨迹不可靠的问题，提出了一种无需训练的推理方法。
◆提出基于外积跨度投影的费雪保持引导机制，在优化任务目标的同时避免离分布动作引起的费雪漂移，确保更新不偏离流形。
◆利用低秩雅可比分解计算费雪保持更新，每步仅需单次反向传播，满足实时应用要求。
◆引入截断费雪去噪敏感度作为不确定性信号，以此实现鲁棒的多样本动作混合策略。
实验表明，该方法在多种仿真和真实机器人导航任务中，无需额外训练即可显著优于强扩散策略基线。</td></tr>
<tr><td>2026-05-28</td><td>How to Relieve Distribution Shifts in Semantic Segmentation for Off-Road Environments<br><a href='http://arxiv.org/pdf/2605.29599'>论文</a></td><td>本文针对越野环境语义分割中由域差异和传感器损坏引起的分布偏移问题，提出了ST-Seg框架。该框架通过显式扩展源分布来提升分割的鲁棒性和越野导航的安全性。
◆提出风格扩展方法，通过生成多样化的逼真风格拓宽域覆盖范围，有效增强源域有限的风格信息。
◆引入纹理正则化技术，利用深度纹理流形稳定受风格增强学习影响的局部纹理表示。
◆打破以往在固定源分布内隐式泛化的局限，提供了一种直观且显式扩展源分布以应对分布偏移的新思路。
实验证明该框架在多种分布偏移的目标域上均显著优于现有方法。</td></tr>
<tr><td>2026-05-28</td><td>GUITestScape: Towards Open-set Evaluation on Exploratory GUI Testing<br><a href='http://arxiv.org/pdf/2605.29532'>论文</a></td><td>当前探索性GUI测试评估存在两大不足，即仅关注交互缺陷而忽视显示缺陷，且评估受限于预定义标注而无法区分不同的失效模式。
◆提出交互式基准GUITestScape，涵盖61个真实安卓应用及508个交互与显示类型的预设缺陷，弥补了现有基准的缺陷类型局限。
◆引入开放集评估器GUIJudge，将智能体的测试轨迹分解为独立可诊断的能力，实现了超越预定义标注的过程感知评估。
实验表明，GUIJudge大幅优于所有基线，提供了可靠的评估结果。
此外，基准测试揭示了现有模型在两类缺陷上的检测瓶颈，且将GUIJudge的验证器集成至现有智能体中无需重训即可显著提升其检测性能。</td></tr>
<tr><td>2026-05-28</td><td>Learning-Based Navigation for Indoor Mobile Robots<br><a href='http://arxiv.org/pdf/2605.30468'>论文</a> | <a href='https://ntdathp.github.io/rl_robot_web/'>代码</a></td><td>该论文提出了一种面向室内移动机器人的学习式导航框架,将全局规划与局部控制相结合,通过监督学习训练全局路径规划器,并采用行为克隆与强化学习相结合的方式优化局部规划器。该方法在仿真与真实室内环境中均得到验证,能够生成可行的全局路径并输出安全可靠的运动指令,实现避障与目标导向的自主导航,展示了学习式全局规划与强化学习精调局部控制相结合的有效性。

核心贡献与创新点如下:

◆ 提出了一种端到端的学习式室内导航框架,将神经网络全局规划器与学习式局部规划器有机整合,实现从路径生成到运动控制的统一学习方案。

◆ 设计了基于代价感知A*专家轨迹监督训练的神经全局规划器,使网络在模仿专家的同时学习到代价信息,从而生成更优的全局路径。

◆ 提出了Learning-Based DWA局部规划器,将传统动态窗口法的连续控制问题转化为在DWA动作格上的离散候选选择问题,既保留了DWA的可行性优势又引入了学习能力。

◆ 采用两阶段训练策略,先通过行为克隆获得初始策略,再使用带可行性掩码的PPO进行强化学习精调,提升了训练稳定性与最终性能。

◆ 引入可行性感知掩码机制,在强化学习过程中过滤不安全或不可行动作,保障了学习过程与执行阶段的安全性。

◆ 在仿真与真实室内环境中均完成了系统部署与验证,并开源代码,体现了方法的实用性与可复现性。</td></tr>
<tr><td>2026-05-27</td><td>Chance-Constrained MPPI under State and Dynamic Object Prediction Uncertainty and the Evaluation of Collision Risk Calibration<br><a href='http://arxiv.org/pdf/2605.28330'>论文</a></td><td>现有机会约束MPPI控制隐式假设上游定位与感知不确定性已良好标定，但实际估计器常标定不当，导致过度自信引发安全违规或缺乏自信引发保守冻结。
◆提出一种严谨的评估方法，应用严格评分规则来评估闭环执行期间预测碰撞风险的统计有效性。
◆提出双不确定性机会约束管MPPI实时风险感知规划架构，通过单管无迹变换近似联合整合定位不确定性，并利用蒙特卡洛聚合整合动态障碍物预测不确定性。
在高度杂乱环境中，该框架实现了稳健的失效缓解，能安全过渡至保守机动而不陷入死锁。
其导航成功率较基线提升近28%，且旅行时间最短、社会作用力最小，证明可靠的概率安全性需要整个技术栈具备统计有效的不确定性估计。</td></tr>
<tr><td>2026-05-27</td><td>STR Robot: Design of an Autonomous Mobile Robot from Simulation to Reality<br><a href='http://arxiv.org/pdf/2605.28110'>论文</a> | <a href='https://ntdathp.github.io/outdoor-robot-web'>代码</a></td><td>本文核心贡献是实现了基于现有机械平台的自主移动机器人从仿真到现实的完整部署。研究未聚焦机械设计，而是重点开发了机载控制、自定位与自主导航系统。
◆创新性地将机载感知与计算相结合，实现了无需外部辅助的机器人位姿估计与自主导航。
◆验证了一套仿真优先的开发框架，即先在仿真中构建与测试整体系统，再成功部署至真实机器人，证明了仿真是开发可靠系统的有效基础。
项目代码即将开源，为相关研究提供了可复用的资源。</td></tr>
<tr><td>2026-05-27</td><td>Ontology-Guided Reasoning for Affordance-Based Explanations of Robot Navigation<br><a href='http://arxiv.org/pdf/2606.00117'>论文</a></td><td>本文提出了一种基于本体引导推理的机器人导航可供性解释方法，使机器人在路线受阻时能推理环境物体的可供性与状态变化以寻找安全通过方式。
◆构建局部可供性本体，对附近实体、可供性、可供性状态及定性空间关系进行统一的结构化表示。
◆提出假设评估机制，通过评估假设的对象与可供性状态变化作为候选解释因子，生成语义基础扎实且具有可操作性的解释。
◆突破传统局限，将可供性本体从单纯的环境语义描述提升为支持可解释性与可靠自主性的推理基础。
在图书管理员机器人场景的测试中，该方法比纯语义基线更准确地识别解释因子，并在语义杂乱增加时保持强鲁棒性。</td></tr>
<tr><td>2026-05-26</td><td>Orion: Enabling Self-adaptive Memory Management for On-device Online Continual Learning<br><a href='http://arxiv.org/pdf/2605.26473'>论文</a></td><td>本文提出了Orion框架，旨在严格内存约束下协同优化在线持续学习的训练延迟、可塑性与稳定性，实现可行的设备端部署。
◆提出基于木桶效应的统一运行时指标URGE，动态地为在线持续学习各组件重新分配内存。
◆在操作系统和应用层面联合协调批处理、回放缓冲区和优化策略，以自适应应对动态内存压力与工作负载变化。
◆引入系统级数据预取技术，最大化提升执行效率。
实验证明，Orion能显著加速训练并保持性能平衡，同时运行时和能耗开销极低，是设备端持续学习的实用解决方案。</td></tr>
<tr><td>2026-05-25</td><td>G-DRAGON: Geospatial Reasoning and Dynamic Planning for Retrieval-Augmented Outdoor Navigation<br><a href='http://arxiv.org/pdf/2605.25646'>论文</a></td><td>该论文提出了G-DRAGON框架，解决了户外导航中长距离全局规划与最后一步精细探索的挑战。
◆基于轻量级大模型的生成式检索方法，将自然语言指令映射到本地OSM实体以获取准确坐标，有效缓解了云端大模型的幻觉问题。
◆高级规划模块将全局拓扑路线与SLAM系统结合，把地理空间航点投影到机器人可导航坐标系，实现全局到局部的桥接。
◆针对最后一步探索，框架无缝切换至基于边界的探索与开放集语义体素建图，精准定位开放词汇目标。
实验表明该框架性能超越现有基线，并在真实世界无人车上成功完成长达500米的行人搜索任务。</td></tr>
<tr><td>2026-05-25</td><td>RCSP: Risk-Sensitive Conjectural Scenario Planning for Safe Dynamic Robot Navigation<br><a href='http://arxiv.org/pdf/2605.26348'>论文</a></td><td>本文研究了动态导航中的预测性近距交错承诺问题，即当前安全速度可能使机器人驶入即将被移动障碍物封堵的通道，并提出了风险敏感推测场景规划方法RCSP。
◆提出RCSP规划层，通过评估候选指令与短期障碍物未来轨迹的交互来提前预判风险。
◆维持局部运动推测的轻量级信念，通过采样未来交互并惩罚高风险尾部实现风险敏感决策。
◆结合局部安全检查层执行指令，可作为补充模块集成至现有导航技术栈中提升动态安全性。
在MuJoCo和ROS2实验中RCSP实现了零碰撞并减少近距交错失败，但在严苛基准成功率上略逊于调优算法。
该方法被定位为在动态瓶颈环境下有效补充现有导航系统的预测性风险模块。</td></tr>
<tr><td>2026-05-25</td><td>NightSight: Passive Computation for Navigation in Dark Using Events<br><a href='http://arxiv.org/pdf/2605.26330'>论文</a></td><td>本文针对小型无人机在完全黑暗环境中难以自主导航的挑战，提出了一种结合单目事件相机、编码孔径镜头和红外点投影仪的轻量级感知方案。
◆提出基于结构光与编码光学的隐式几何编码机制，红外图案经编码孔径产生深度依赖的模糊特征以隐式编码场景几何。
◆设计了极简的训练范式，仅用平面墙生成的合成数据训练卷积神经网络解码稠密深度图，即可实现对复杂真实场景的零样本泛化。
◆构建了适用于资源受限平台的高效实时系统，在边缘计算设备上以20赫兹运行，2.5米内深度估计绝对误差仅7.0厘米。
该研究还深入分析了不同编码孔径设计对深度估计性能的影响，展示了结构照明、编码光学与事件感知结合在暗光导航中的巨大潜力。</td></tr>
<tr><td>2026-05-24</td><td>GreenSeg: Ground Segmentation Algorithm for Agricultural Robots in Mediterranean Greenhouses using RGB-D Point Clouds<br><a href='http://arxiv.org/pdf/2605.25279'>论文</a></td><td>本文针对地中海温室环境通道狭窄、地形异构且塑料覆膜导致深度传感器产生严重光学干扰的问题，提出了基于RGB-D点云的GreenSeg地面分割算法，替代了昂贵的3D激光雷达方案。
◆提出结合鲁棒全局平面拟合与表面曲率滤波的双层验证策略，以适应从混凝土到耕地等复杂的异构地形。
◆引入基于种子点的区域生长约束，确保可行驶平面的空间连续性。
在AGRICOBIOT I平台上四种不同太阳高度角的昼夜场景中进行的实验验证了该算法的有效性。
结果表明，GreenSeg在走廊尽头关键旋转操作中表现优异，平均召回率和mIoU分别最高提升11.58%和19.24%，显著超越基准方法。
这证实了该算法能够在预算受限且对光照敏感的非结构化动态农业环境中实现稳定安全的自主导航。</td></tr>
<tr><td>2026-05-24</td><td>Micro-Swarm Locomotion Optimization in Dynamic Flow using Multi-Objective Multi-Agent Reinforcement Learning<br><a href='http://arxiv.org/pdf/2605.25025'>论文</a></td><td>本文提出了一个混合计算流体动力学与多目标多智能体强化学习框架，首次将高保真不可压缩Navier-Stokes求解器与分散式近端策略优化直接耦合，解决了动态生理流体环境下微型集群协调的难题。
◆引入PCGrad梯度冲突解决机制，证明在同时优化上游前进、能量守恒和运动平滑度时，梯度冲突解决是该领域的结构性必要条件，有效避免了效率和平滑度奖励的崩溃。
◆实现了多目标优化的卓越性能，收敛策略在前进奖励、能量效率和运动平滑度上均表现优异，而暴力基线的能量效率始终为负。
◆揭示了三种涌现的物理行为，包括抑制前向流速的集体双层流体动力学节流阵型、利用逆流重定位的周期同步棘轮机制，以及接近目标时的个体化最终趋近策略。
该研究确立了依赖时间的流体与智能体交互可直接纳入多目标强化学习循环，为生物医学导航和微流体控制等领域提供了基于物理的全新范式。</td></tr>
<tr><td>2026-05-24</td><td>Performance Comparison of Classical and Neural Sampling Algorithms for Robotic Navigation<br><a href='http://arxiv.org/pdf/2605.25010'>论文</a></td><td>本文系统比较了经典算法RRT*与神经网络采样算法Neural RRT*及Neural Informed RRT*在机器人导航中的性能表现。实验在包含不同密度凸面和凹面障碍物的环境中进行综合评估。
◆揭示了神经引导采样策略能显著提升路径质量，使路径缩短达14%，轨迹平滑度提高55%至75%。
◆验证了Neural Informed RRT*算法在路径长度与轨迹平滑度上取得了最优综合性能。
◆证明了即便计算时间略增，AI引导策略仍能有效提升机器人和无人机导航的可靠性与轨迹效率。</td></tr>
<tr><td>2026-05-24</td><td>Convex-Neural RRT*: Fast and Reliable Learning-Guided Sampling for High-Quality Robot Path Planning<br><a href='http://arxiv.org/pdf/2605.25006'>论文</a></td><td>针对基于采样的机器人路径规划算法获取高质量解需大量迭代的问题，本文提出了Convex-Neural RRT*算法。
◆引入神经引导机制预测高质量路径附近的信息丰富航点区域。
◆从预测结果中提取凸候选区域，使规划器在聚焦几何相关区域探索的同时保留全局探索能力。
实验表明，该算法相比神经引导变体和LTA*分别减少30%至75%和88%至98%的计算时间。
同时，其路径长度比传统RRT*平均缩短约5%，整体成功率保持在99%以上，有效平衡了计算效率与求解质量。</td></tr>
<tr><td>2026-05-23</td><td>Vision-Guided Outdoor Flight and Obstacle Evasion via Reinforcement Learning<br><a href='http://arxiv.org/pdf/2605.24449'>论文</a></td><td>本文提出了一种基于立体视觉和视觉惯性里程计的感觉运动策略，解决了四旋翼在无GNSS和遥测信号环境下的自主导航与避障问题。
◆设计了一种结合预训练自编码器感知头与LSTM规划控制网络的架构，可直接输出供商用无人机执行的速度指令。
◆提出两阶段强化与特权学习训练范式，先利用全局规划器最优轨迹作为监督主干进行初始训练，再在课程环境中微调。
◆通过引入领域随机化和奖励塑形技术，有效缩小了仿真到现实的差距，增强了策略对噪声和域偏移的鲁棒性。
该方法在室外实验中实现了零样本迁移，成功在训练时未见过的障碍物环境和无人机平台上完成自主飞行任务。</td></tr>
<tr><td>2026-05-22</td><td>MASt3R-Nav: WayPixel Navigation in Relative 3D Maps<br><a href='http://arxiv.org/pdf/2605.24111'>论文</a></td><td>本文提出了一种基于像素相对连接性的新型地图表示，解决了传统3D地图需全局一致性以及拓扑图缺乏几何理解限制导航能力的问题。
◆提出像素相对连接性地图表示，兼具几何准确性且无需全局几何一致性。
◆基于3D图像匹配技术，利用图像对相对3D坐标系中的像素对应关系构建图像间连接性与地图。
◆通过逼近和稀疏化图像内像素连接性进行全局路径规划，推导出WayPixel代价图表示。
◆训练以该稠密像素级代价图为条件的控制器预测轨迹展开，证明相对几何代价图比图像及物体级的条件变量更准确。
该导航系统在模拟器四种任务及真实世界演示中均得到验证，展现出强大的导航能力。</td></tr>
<tr><td>2026-05-20</td><td>Flying Together: Human-Guided Immersive Shared Control for Aerial Robot Teams in Unknown Environments<br><a href='http://arxiv.org/pdf/2605.21680'>论文</a></td><td>本文提出了一种基于虚拟现实的无人机团队共享控制框架，旨在解决自主多机器人在非结构化环境中难以适应未知条件和捕捉操作员意图的问题，实现实时用户引导探索。
◆提出用户引导的基于运动基元的规划器，在持续融合操作员输入的同时计算连续无碰撞轨迹。
◆结合导纳控制器，使操作员能灵活影响团队行为并引导无人机前往自主规划器易忽略的关注区域。
◆构建支持物理与仿真无人机混合现实操作的双边VR界面，操作员可通过迁移点引导团队并获取即时视觉反馈。
实验结果表明，该沉浸式人在回路系统有效改善了避障性能，保持了智能体间距，并显著降低了操作员负担。</td></tr>
<tr><td>2026-05-20</td><td>ArchSIBench: Benchmarking the Architectural Spatial Intelligence of Vision-Language Models<br><a href='http://arxiv.org/pdf/2605.20837'>论文</a></td><td>本文提出了ArchSIBench基准，旨在填补现有视觉语言模型在高级建筑空间认知评估上的空白。
◆创新性地融合建筑学、认知科学与心理学视角，构建了涵盖感知、推理、导航、变换和构型五个核心维度及十七个细粒度子任务的系统评估框架。
◆通过建筑背景专家的精细手工标注，构建了包含三千个问答对的高质量专业数据集，确保了评估的权威性与准确性。
◆基于该基准对多款模型进行全面评测，首次系统揭示了模型与人类在建筑空间智能上的差异，以及模型在不同能力维度上的显著波动。
评测发现，最先进模型虽能接近未受专业训练的人类水平，但在空间变换和构型推理上与受过专业训练的建筑师仍存在明显差距。
该研究为衡量和提升视觉语言模型的建筑空间智能提供了重要的系统资源与方向。</td></tr>
<tr><td>2026-05-20</td><td>Q-SpiRL: Quantum Spiking Reinforcement Learning for Adaptive Robot Navigation<br><a href='http://arxiv.org/pdf/2605.20801'>论文</a></td><td>本文针对动态环境中自适应机器人导航的可靠性与轨迹效率问题，提出了Q-SpiRL量子脉冲强化学习框架。
◆创新性地提出了量子增强脉冲神经网络作为核心架构，将脉冲驱动的时序处理与变分量子特征变换有效结合。
◆构建了包含表格Q学习、经典MLP、经典SNN、量子MLP和QSNN五种智能体的统一训练与评估管线，并在多尺寸及动静障碍物混合的网格世界中进行了系统对比。
◆实验表明QSNN在任务完成率、轨迹效率和运动平滑度间取得了最优的整体权衡，在最具挑战性的环境中成功率达99%且维持了高路径效率。
◆在IBM真实量子硬件上的成功执行，验证了该混合策略在真实量子设备条件下实际部署的可行性。</td></tr>
<tr><td>2026-05-19</td><td>KappaPlace: Learning Hyperspherical Uncertainty for Visual Place Recognition via Prototype-Anchored Supervision<br><a href='http://arxiv.org/pdf/2605.19435'>论文</a> | <a href='https://github.com/mayayank95/UncertaintyAwareVPR'>代码</a></td><td>针对现有视觉位置识别方法缺乏校准的不确定性估计这一问题，本文提出了KappaPlace框架以学习不确定性感知的表征。
◆提出原型锚定监督策略，利用潜在类别代表作为概率优化目标的锚点。
◆将图像描述子建模为von Mises-Fisher变量，通过轻量级模块预测浓度参数作为偶然不确定性的直接代理。
◆推导出新颖的匹配级公式，突破了现有方法仅限查询视角的局限，能够量化特定查询与参考图对的匹配可靠性。
该方法提供联合训练与后训练扩展两种模式，在五个基准上将期望校准误差降低高达百分之五十，同时保持或提升检索召回率。
实验证明该框架为位置识别流程提供了鲁棒且校准良好的信号，保障了安全关键应用中的可靠决策。</td></tr>
<tr><td>2026-05-19</td><td>Enhancing Graph-Based SLAM in GNSS-Denied environments by leveraging leg odometry<br><a href='http://arxiv.org/pdf/2605.20484'>论文</a></td><td>本文针对足式机器人在GNSS拒止环境中因几何稀疏或重复场景导致激光雷达产生高程漂移的问题，提出了一种增强图优化SLAM的新架构。该方法通过融合本体感知的腿部里程计，有效弥补了外部感知传感器的垂直漂移缺陷。实验表明，在超过一公里的户外测试中，该方法将高程漂移从30多米降至30厘米以内，并使基线方法完全失效的场景成功收敛。
◆在LIO-SAM框架中引入由腿部里程计驱动的并行运动学通道。
◆通过带有选择性噪声模型的恒等相对位姿约束，将运动学通道与主激光雷达惯性通道耦合。
◆挖掘用于步态控制的本体感知数据，为SLAM提供轻量且有效的垂直锚点。</td></tr>
<tr><td>2026-05-19</td><td>Minimalist Visual Inertial Odometry<br><a href='http://arxiv.org/pdf/2605.19990'>论文</a></td><td>本文提出一种极简的平面视觉惯性里程计方法，证明仅用四个视觉测量值与IMU即可实现差速机器人的鲁棒运动估计，大幅降低了传统VIO处理高像素图像的资源消耗。
◆创新性地使用四个朝下的光电二极管透过光学盖伯掩膜感知环境，产生直接编码速度的信号以替代传统相机。
◆提出在物理仿真器中联合优化盖伯掩膜参数与时序卷积网络，使模型仅凭四个测量值即可解码出线速度。
通过将解码的线速度与IMU的角速度结合即可生成连续轨迹。经室内外多地形测试，该系统无需真实数据微调即可准确跟踪真值，验证了极简感知实现高效里程计的可行性。</td></tr>
<tr><td>2026-05-18</td><td>Qumus: Realization of An Embodied AI Quantum Material Experimentalist<br><a href='http://arxiv.org/pdf/2605.18407'>论文</a></td><td>本文介绍了首个AI量子材料实验学家Qumus，它是一个物理具身于机器人微型实验室的智能多模态多智能体系统，专用于原子级薄二维材料的创建与纳米加工。
◆实现了从假设生成、方案规划到多步实验执行、结果分析与报告的全科学周期自主导航。
◆首次达成了AI创造石墨烯，以及通过范德华堆叠制造原子层级场效应晶体管等复杂纳米器件的突破。
◆具备自主纠错和闭环实验的卓越能力，有效整合了高层推理、多模态信息处理与实时物理执行。
该成果为直接从量子世界学习的自我改进型具身AI系统建立了通用化框架，为加速量子材料与电子学等领域的发现开辟了新途径。</td></tr>
<tr><td>2026-05-16</td><td>NORM-Nav: Zero-Shot Mobile Robot Navigation with Natural Language Behavioral Constraints<br><a href='http://arxiv.org/pdf/2605.16979'>论文</a> | <a href='https://ei-nav.github.io/NORM-Nav'>代码</a></td><td>本文提出NORM-Nav框架，解决了传统基于代价图的导航仅关注几何可行性而忽视社会行为规范的问题，实现了零样本自然语言行为约束的移动机器人导航。
◆利用大语言模型解析自然语言指令生成结构化约束，并借助实时视觉与激光雷达感知完成约束落地。
◆将行为约束编码为包含几何、语义、方向及速度线索的多层代价图，且与标准网格规划器直接兼容。
仿真与真实世界实验证明，该框架有效提高了任务成功率。
其生成的轨迹也显著比代表性基线方法更接近人类参考行为。</td></tr>
<tr><td>2026-05-13</td><td>LEXI-SG: Monocular 3D Scene Graph Mapping with Room-Guided Feed-Forward Reconstruction<br><a href='http://arxiv.org/pdf/2605.13741'>论文</a> | <a href='https://ori-drs.github.io/lexisg-web/'>代码</a></td><td>近年来，场景图成为机器人导航的标准层次化表示，但多数方法依赖深度传感器。  
◆首次提出仅用单目RGB实现开放词汇密集3D场景图映射的系统LEXI‑SG。  
◆利用基础模型的语义先验将场景划分为房间，并在房间完整观测后进行前馈重建，避免滑动窗口尺度不一致。  
◆构建房间级因子图实现全局对齐，保持局部地图一致性和语义层次结构。  
◆在每个房间内支持开放词汇对象分割与跟踪，实现细粒度物体理解。  
实验在Habitat‑Matterport 3D和自采办公场景上验证，显示轨迹估计和密集重建精度提升，开放词汇分割性能具有竞争力。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='motion-planning'>Motion Planning (212篇)</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-16</td><td>Stigmergic Graph Memory: An Environment-Aware Approach for Many-to-Many Multi-Agent Pickup and Delivery<br><a href='http://arxiv.org/pdf/2607.15182'>论文</a></td><td>本文针对自动化履约仓库中多对多多智能体取送货（MAPD）问题，提出了一种基于环境感知的方法Stigmergic Graph Memory（SGM）。现有图引导方法主要在目标确定后影响路径规划，而请求的端点选择缺乏对近期交通状况的感知。SGM作为一层有界的衰减记忆层，在仓库节点和有向边上记录近期执行信号，用于对可行端点和路径偏好进行排序，同时不改变碰撞约束或规划器的有效性。

◆提出在规划器外部维护一个有界、衰减的记忆层，将环境反馈编码为节点和边上的执行信号，使记忆随时间自然淡化并控制资源占用。
◆将记忆机制与碰撞规划解耦，仅在端点选择和路径偏好排序阶段利用记忆，不破坏原规划器的可行性与完备性。
◆在五种仓库布局、三种负载、每种条件下25个随机种子的全面实验中，在全部15种地图-负载组合上均优于重构的多对多分配基线，配对吞吐量提升达20.5%至36.7%。

该工作表明近期执行记忆可通过塑形哪些可行目标进入规划器来提升吞吐，而不仅限于优化既定目标间的行进方式。</td></tr>
<tr><td>2026-07-16</td><td>Catch, Throw, Repeat: Planning for Human-Robot Partner Juggling<br><a href='http://arxiv.org/pdf/2607.15129'>论文</a></td><td>本文针对人机之间动态物体交换这一挑战性问题，提出了一种面向人机合作抛接球的实时规划与控制架构。该系统集成了预测性球追踪、基于多重打靶法（multiple-shooting）的自适应在线轨迹优化以及状态机协调逻辑，能够在多球模式下与人类伙伴实现同步接抛。论文首次实现了人与机器人共享的三球级联（cascade）模式下的协调抛接，突破了以往仅能完成简单物体交换的限制。在8名不同技能水平用户参与的实验中，所有参与者在10分钟测试内均超过此前人机抛接球的最佳成绩。实验中，一名参与者将人机共享三球级联的连续接球记录从4次提升五倍至连续20次，另一名参与者在单球接抛场景下实现了连续40次100%成功率的优异表现。

◆ 提出了集成预测性球追踪、基于多重打靶法的自适应在线轨迹优化和状态机协调逻辑的实时规划与控制架构
◆ 首次实现人机共享的三球级联（cascade）同步抛接，验证了多球复杂模式下的协调能力
◆ 通过8名不同技能水平用户参与的实验验证系统有效性，所有参与者在10分钟内均超过此前最佳记录
◆ 创下人机共享三球级联连续接球20次的新记录，并将此前最佳成绩提升五倍
◆ 在单球接抛场景下实现连续40次100%成功率的稳定表现...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-16</td><td>BridgeFlow: Fast and Robust SE(2)-Equivariant Motion Planning with Flow Matching<br><a href='http://arxiv.org/pdf/2607.14725'>论文</a></td><td>BridgeFlow提出了一种快速且严格SE(2)等变的生成式运动规划框架,旨在解决现有学习型规划器在等变性与推理速度之间的两难困境。该方法通过轻量级的任务中心化规范化模块实现精确的空间等变性,无需依赖计算昂贵的专用等变网络,即可使用标准架构完成泛化。

◆ 设计了任务中心化规范化模块(task-centric canonicalization),以轻量化方式实现严格SE(2)等变性,使标准网络架构即可获得空间泛化能力。

◆ 采用布朗桥信息先验与上下文感知小批量最优传输相结合,构建拉直化的向量场,最小化传输成本并稳定训练过程。

◆ 引入无分类器引导(Classifier-Free Guidance)显式嵌入环境感知,提升轨迹生成对复杂环境的适应性。

◆ 在密集2D环境与7自由度Franka机械臂上的实验表明,推理速度提升最高达15倍,有效轨迹率比现有最优扩散基线提高2倍,并能稳健泛化到完全未见过的环境与任意空间变换。</td></tr>
<tr><td>2026-07-16</td><td>DRIFT: Drift and Aggregation for Motion Planning<br><a href='http://arxiv.org/pdf/2607.14507'>论文</a></td><td>DRIFT是一种用于端到端轨迹规划的固定深度规划器，针对多假设行为表达与单一可执行轨迹输出的矛盾问题提出解决方案。论文的核心在于将紧凑轨迹潜在空间中的一步漂移生成与场景感知的提议聚合相结合，实现高效的多假设运动规划。

◆ 一步漂移潜在空间生成：DRIFT解码器基于预训练视觉编码器特征，单次批量生成48个提议特征（32个α=0.5、16个α=0.9），无需迭代采样，实现高效并行推理。

◆ 轻量级聚合头设计：聚合头直接融合提议特征与场景、导航及自车状态信息，无需轨迹级质量标签即可预测最终轨迹，简化训练流程。

◆ 地图边界正则化器：利用可行驶区域多边形对路点施加惩罚，鼓励规划轨迹贴合可行驶边界，提升合规性。

◆ 在NAVSIM navtest基准上达到89.6 PDMS与90.4 EPDMS，提议生成与聚合模块在RTX 4090上仅需10.82毫秒，全模型推理66.43毫秒，验证了多假设规划的高效可行性。</td></tr>
<tr><td>2026-07-16</td><td>Motion Planning with Model-Based Diffusion via Constraint Optimization and Adaptive Scheduling<br><a href='http://arxiv.org/pdf/2607.14455'>论文</a></td><td>该论文提出MD-COAS方法,用于解决高度非凸约束环境下的单机器人运动规划问题。该方法基于模型扩散框架,将运动规划重新建模为轨迹优化问题,通过已知动力学模型解析估计得分函数来引导扩散去噪过程,从而无需示教学习即可生成低代价且满足约束的轨迹。针对现有方法在安全约束处理上的不足,论文提出了两项核心创新:◆将非精确增广拉格朗日方法(iALM)的软扩散先验与基于凸可行集(CFS)的硬投影算子统一到同一框架中,实现软硬约束的协同优化;◆提出自适应调度机制,将安全约束执行强度与扩散调度过程联合优化,使约束强度能够随扩散进程动态调整。在随机生成的二维非凸环境基准和七自由度机械臂避障任务上的实验表明,该方法在安全性、成功率、收敛速度和最终代价方面均优于现有基线规划器。</td></tr>
<tr><td>2026-07-15</td><td>S-squared-VLA: Decoupling Semantic and Spatial Streams in Vision-Language-Action Models for Autonomous Driving<br><a href='http://arxiv.org/pdf/2607.13926'>论文</a></td><td>该论文针对自动驾驶VLA模型中语义-物理鸿沟及空间表征塌缩问题，提出S-squared-VLA框架，显式解耦语义与空间两条流，以解决统一策略中细粒度空间几何先验被不可逆破坏的瓶颈。

◆ 语义流采用层次化桥接机制，从VLM中提取多尺度特征用于高层驾驶意图推理，保持了语言模型的语义理解能力
◆ 空间流绕过自回归语言瓶颈，直接保留视觉编码器的未压缩空间特征，并通过辅助感知监督任务显式注入丰富几何先验
◆ 双流规划适配器利用级联注意力机制融合高层语义意图与精确空间约束，实现连续轨迹的精准输出

在NAVSIM闭环基准测试中，该方法在纯监督微调设置下取得87.1的PDMS分数和98.4的最高无碰撞率，刷新了VLA模型在该任务上的SOTA。</td></tr>
<tr><td>2026-07-15</td><td>Merging Reaction to Cognition: A Hybrid Cognitive Strategy for Odour Source Localisation in Natural Environments<br><a href='http://arxiv.org/pdf/2607.13853'>论文</a></td><td>本文针对湍流环境下气味源定位难题，提出了一种融合反应式行为与认知规划的新型混合策略。传统生物启发方法依赖检测触发的瞬时反应，需场景特定调参；而认知方法虽鲁棒但探索过多、依赖信念精度。该工作基于先前马尔可夫链分析发现——气味检测后源定向运动概率约为其他情况的两倍——将反应性显式嵌入信念依赖的运动规划中，并设计了检测触发的切换机制以权衡横向探索与源定向运动，同时使行为参数由信念指标直接推导，实现了无需人工调参的自适应反应性。

◆ 提出混合认知策略，将生物启发的反应性显式整合到基于信念的运动规划框架中
◆ 设计检测触发的切换机制，形式化横风探索与源定向运动之间的过渡，优先考虑源接近而非信息增益
◆ 行为参数直接由信念指标推导，实现无需人工调参的自适应反应性
◆ 在三种湍流条件下仿真验证，并在葡萄牙蒙得戈河自主水面艇现场实验中取得最高50%路径缩短、86%成功率与3.2米平均定位误差的优异性能...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-15</td><td>Dynamical Vehicle Orienteering Problem for Multi-Rotor Unmanned Aerial Vehicles<br><a href='http://arxiv.org/pdf/2607.13789'>论文</a></td><td>本文针对多旋翼无人机的飞行规划问题，提出了动力学车辆定向问题（DVOP），将经典定向问题（OP）推广到同时考虑外部力与车辆主动力的三维点质量模型（PMM）场景，约束包括最大速度、最大加速度及重力加速度，并以最大飞行时间作为旅行预算。核心贡献在于将奖励最大化与时间最优轨迹规划耦合求解，避免了传统图问题简化带来的建模失真。

◆ 提出了一种新的问题建模DVOP，将车辆动力学（速度、加速度、重力约束）显式纳入定向问题。
◆ 设计了基于分支定界（BnB）的精确求解框架，融合非线性规划（NLP）与混合整数线性规划（MILP），其中MILP通过目标三元组的时间最优轨迹基元构建紧致奖励上界。
◆ 提出基于大邻域搜索（LNS）的元启发式方法，利用受限推力分解快速计算高质量PMM轨迹，为BnB提供初始奖励界并扩展问题规模可解性。
◆ 在基准实例上较运动学定向问题最优解最高提升37%，并通过真实多旋翼无人机部署验证了所提轨迹的工程可行性。</td></tr>
<tr><td>2026-07-15</td><td>Unifying Decision-Making and Trajectory-Planning in Unsignalized Intersections Using Time-Varying Potential Fields<br><a href='http://arxiv.org/pdf/2607.13626'>论文</a></td><td>本文针对无信号交叉路口场景，提出了一种将决策与轨迹规划统一处理的自动驾驶框架。该方法将时变人工势场融入有限时域最优控制问题，借助短时域运动预测与专门的冲突区占用系数刻画碰撞风险，从而在统一的优化框架内同步完成通行决策与轨迹生成。仿真结果在多车交通场景中验证了所提方法能够输出可行且安全的参考轨迹。

主要创新点如下：

◆ 提出时变人工势场与有限时域最优控制相结合的方法，将决策与轨迹规划统一在同一优化框架中，消除了传统分层架构中两者衔接的时序与一致性问题。

◆ 引入冲突区占用系数，对车辆在交叉口内部冲突区域的占用状态进行量化，使势场能够显式表征交叉口特有的空间冲突风险。

◆ 将短时域运动预测嵌入最优控制过程，使控制器能够前瞻性地评估他车行为变化，从而提升复杂多车交互场景下的安全性与适应性。</td></tr>
<tr><td>2026-07-15</td><td>Influence of Magnetospheric Plasma Environment on Surface Charging of the Lunar South Pole<br><a href='http://arxiv.org/pdf/2607.13510'>论文</a></td><td>本文针对月球南极表面充电问题，构建了基于LRO/LOLA高程数据的高保真地形模型(86°S–90°S)，并采用有限元–BP神经网络耦合方法，结合月球相位依赖的太阳风与地球磁层等离子体参数，模拟了半个轨道周期内的表面充电演化过程。

◆ 首次将高保真南极地形与动态磁层等离子环境相结合，系统揭示了地形遮蔽效应对表面电势分布的调控规律。

◆ 提出有限元与BP神经网络的耦合计算方案，提升了复杂地形下充电模拟的精度与效率。

◆ 阐明了月球穿越磁层不同区域时表面电势与电场的变化特征，发现从太阳风到等离子体片过程中电势降低、电场增强的总体趋势。

◆ 发现仅在等离子体片相邻的磁尾瓣区出现电势短暂回升和电场减弱现象，等离子体片内电势最低可达约-1000 V，峰值电场约5 V/m。

◆ 识别出风向上游地形带高电势、背风屏蔽区低电势的分布模式，指出环形山背风壁上下游及坑底–坑壁交界处存在显著电场增强。

研究成果可为月面着陆点选择、巡视器路径规划及设备静电防护提供重要参考。</td></tr>
<tr><td>2026-07-15</td><td>VAMP-MR: Vector-Accelerated Motion Planning and Execution for Multi-Robot-Arms<br><a href='http://arxiv.org/pdf/2607.13478'>论文</a> | <a href='https://vamp-mr.github.io/vamp-mr'>代码</a></td><td>这篇论文针对多机械臂运动规划中计算效率低、难以实时部署的关键难题，提出了一套名为VAMP-MR的向量加速运动规划系统。核心思路是将经典规划算法与基于CPU SIMD指令的向量化碰撞检测技术相结合，从根本上加速规划过程中的主要瓶颈环节。

◆ 设计了一套新的多机械臂运动规划器套件，能够实现近实时的无碰撞运动生成，适用于安全执行的多臂制造任务。

◆ 引入基于CPU SIMD指令的向量化碰撞检测技术，显著提升了碰撞检查这一核心瓶颈步骤的执行效率。

◆ 在多臂操作任务的运动规划与执行后处理阶段均实现了最高达两个数量级的加速比，大幅提升了系统整体性能。

◆ 采用经典规划算法与向量化加速相结合的方法，在保证运动质量的同时兼顾了实时性与可部署性。

◆ 开源了完整实现代码，降低了多机械臂规划与操作研究的门槛，促进了相关领域的科研与应用发展。</td></tr>
<tr><td>2026-07-15</td><td>A Hybrid Sampling-Based Trajectory Planner with Game-Theoretic Guidance for Autonomous Racing<br><a href='http://arxiv.org/pdf/2607.13354'>论文</a></td><td>该论文针对自动驾驶赛车场景中车辆极限动力学与多智能体战略决策难以兼顾的问题，提出了一种融合博弈论引导与采样规划器的混合轨迹规划架构。基于α-势能博弈框架，研究者利用离线学习的势能函数建模多智能体交互，并通过在线梯度优化动态调整交互参数，生成&quot;交互参考路径&quot;，再将其作为动态代价偏置注入高频采样规划器中，从而在保持计算效率的同时实现战略性行为。

核心贡献与创新点如下：

◆ 提出了一种博弈论与采样规划器深度融合的混合架构，将战略交互推理与鲁棒轨迹生成相结合，规避了完整动态博弈求解的高计算负担。

◆ 引入基于离线学习的势能函数来刻画多智能体交互，并设计在线梯度优化机制动态精化交互参数，生成&quot;交互参考路径&quot;。

◆ 将交互参考路径作为动态代价偏置嵌入采样规划器，使车辆能够在不求解完整博弈的前提下展现阻挡等防御性策略行为。

◆ 在Yas Marina赛道的高保真仿真中验证了该方法，结果表明其能有效激发博弈驱动的战略性行为，同时满足高频实时规划的计算需求。</td></tr>
<tr><td>2026-07-15</td><td>Information-Theoretic Adaptive Cooling for Deterministic MPPI via Entropy Feedback<br><a href='http://arxiv.org/pdf/2607.14245'>论文</a></td><td>本文研究确定性模型预测路径积分(MPPI)控制中的温度冷却调度问题,传统方法依赖预设的开环冷却方案,效率与鲁棒性受限。为此,本文提出一种基于信息论的自适应冷却框架ITAC,利用重要性权重的香农熵作为在线反馈信号来动态调节温度,实现权重分散时快速推进、权重集中时谨慎冷却。

◆核心创新是提出以重要性权重熵为反馈信号的自适应冷却机制,替代传统的开环冷却方案,使冷却速率能够响应当前采样状态。

◆证明了ITAC方案的渐近收敛性,并推导出关键熵阈值,形成光滑屏障以防止重要性权重过早退化。

◆在非光滑信号时序逻辑运动规划任务上的实验验证表明,该方法在保持MPPI无导数特性的同时,显著提高了采样效率并实现了相比现有基线更快的收敛速度。</td></tr>
<tr><td>2026-07-14</td><td>Globalized Constrained Stein Variational Inference for Diverse Feasible Robot Motion Planning<br><a href='http://arxiv.org/pdf/2607.12732'>论文</a></td><td>本文针对机器人运动规划中多模态采样的难题,提出了一种约束型Stein变分推理方法SteinSQP,能够在严格满足碰撞避免、关节限制、接触条件和动力学一致性等硬约束的同时,生成多样化且低成本的运动轨迹集合。传统的概率规划方法难以同时兼顾多样性和可行性,而SteinSQP通过将约束直接嵌入到核空间中的序列二次规划(SQP)子问题,使粒子群在演化过程中始终保持可行。

◆ 将约束条件嵌入到Stein变分推理的核空间SQP子问题中,提出Stein-Newton子问题的约束变分推断框架,确保采样过程中每个粒子都满足硬约束。

◆ 设计了GPU友好的无矩阵原始-对偶求解算法,通过批量并行更新实现粒子集的高效同步演化,显著提升大规模机器人的计算效率。

◆ 提出基于集合层面的价值函数,联合平衡目标值、约束违反和粒子多样性,实现方法的全局化收敛,避免陷入局部可行解。

◆ 在五个约束运动规划任务上的实验表明,SteinSQP相比一阶约束Stein方法和串行多启动非线性规划,具有更快的迭代收敛速度、更高的粒子可行性,并在机器人级复杂任务上实现更快的批量求解时间。</td></tr>
<tr><td>2026-07-14</td><td>Model-Based Diffusion Optimal Control for Multi-Robot Motion Planning<br><a href='http://arxiv.org/pdf/2607.12423'>论文</a></td><td>本文提出了一种名为MDOC（Model-Based Diffusion Optimal Control）的模型驱动扩散最优控制方法，用于解决连续环境中多机器人运动规划问题。针对现有基于扩散模型的方法依赖大量演示数据、难以严格保证动力学可行性和安全性约束的局限，MDOC通过将已知动力学模型与受控制屏障函数（CBF）约束的投影机制相结合，在无需任何训练数据的前提下高效生成动态可行且安全无碰撞的轨迹。该方法通过冲突基搜索（CBS）自然地扩展到多机器人协同规划场景，显著缓解了联合轨迹空间的组合爆炸问题。实验结果表明，MDOC在采样效率、轨迹几何平滑性、规划成功率以及计算时间方面均优于代表性基线方法。

主要创新点如下：

◆ 提出无需演示数据的模型驱动扩散规划框架，利用已知动力学模型生成动态可行轨迹，克服了数据驱动的扩散方法对大规模数据集的依赖。

◆ 设计了基于控制屏障函数（CBF）约束投影的安全机制，在扩散采样过程中严格保证硬安全约束的满足。

◆ 将安全机制与冲突基搜索（CBS）相结合，使该方法能够自然地扩展到多机器人规划场景。

◆ 在多项仿真实验中综合优于基线方法，体现在采样效率、平滑性、成功率以及计算时间上的全面提升。</td></tr>
<tr><td>2026-07-14</td><td>Worlds in One Demo: A Synthetic Data Engine for Learning Open-World Mobile Manipulation<br><a href='http://arxiv.org/pdf/2607.13154'>论文</a></td><td>本文针对开放世界移动操作任务对大规模数据的需求，提出了WANDA系统，仅需一条人类示教即可通过合成数据引擎生成海量多样化训练数据。系统首先从源RGBD观测中重建背景高斯泼溅和机器人-物体交互轨迹作为世界基底，随后将接触丰富的交互片段重组到广阔的空间构型中，并利用全身运动规划将其串联成新轨迹。为提升长时序鲁棒性，系统应用了校正状态扩展策略以增加不同阶段机器人与物体状态的多样性；为实现跨环境泛化，在由日常照片生成的多种3D世界中进行轨迹合成，并通过将渲染的机器人与物体网格与高斯泼溅背景合成来生成照片级真实观测。

◆提出从单条示教出发，通过高斯泼溅重建与轨迹片段重组生成大规模多样化训练数据的合成数据引擎WANDA
◆引入全身运动规划将接触丰富的交互片段链接为新轨迹，实现空间构型的可扩展生成
◆设计校正状态扩展机制，在移动操作各阶段增加机器人与物体状态多样性以增强长时序鲁棒性
◆利用日常照片生成多样化3D世界，在其中合成轨迹以实现跨环境泛化
◆将渲染网格与高斯泼溅背景合成生成照片级真实观测，并天然支持跨形态机器人的零样本部署...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-07-13</td><td>CR-Solver: GPU-Accelerated Kinematics Solver for Tendon-driven Continuum Robots<br><a href='http://arxiv.org/pdf/2607.11340'>论文</a></td><td>针对现有运动规划库多基于刚体假设、难以适用于连续体机器人的问题，本文提出了CR-Solver，一种基于优化的两阶段运动生成求解器，专门面向腱驱动连续体机器人。该方法将逆运动学、路径跟随和轨迹规划统一在同一约束非线性优化框架内，避免了多模块拼接带来的误差传递和接口不一致问题。

◆ 创新点：在一个统一的约束非线性优化框架中同时完成逆运动学、路径跟随与轨迹规划，替代了传统分散的多模块方法。
◆ 创新点：基于GPU并行加速优化求解过程，相较传统CPU求解器获得显著速度提升。
◆ 创新点：在三项任务上系统验证，成功率持续高于95%，并保持毫米级定位精度。
◆ 创新点：采用纯Python实现并开源，降低了连续体机器人高性能运动规划的使用门槛与扩展成本。</td></tr>
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
<tr><td>2026-07-10</td><td>Shortcut Trajectory Planning for Efficient Offline Reinforcement Learning<br><a href='http://arxiv.org/pdf/2607.09336'>论文</a></td><td>本文针对离线强化学习中基于扩散模型的轨迹规划推理成本高的问题,提出了一种Shortcut Trajectory Planning(STP)框架。该方法将shortcut模型作为高效轨迹生成器,绕过了传统一致性模型所需的两阶段师生蒸馏流程,大幅简化了训练过程。

◆ 采用单阶段训练方式学习条件shortcut轨迹模型,避免了教师-学生蒸馏带来的训练成本和稳定性问题。

◆ 通过步长条件化机制支持可调节的单步和少步推理,显著降低了在线规划时的计算延迟。

◆ 引入可行性感知的Critic修正机制来选择候选规划,提升了生成轨迹在环境约束下的可执行性。

在D4RL涵盖运动、导航、操作和灵巧控制的多个标准基准上,STP在取得强劲性能的同时简化了生成式规划的训练流程。</td></tr>
<tr><td>2026-07-10</td><td>Diffusion for Long-Horizon Multi-Robot Path Planning in Human-Shared Environments<br><a href='http://arxiv.org/pdf/2607.09911'>论文</a></td><td>该论文提出了一种名为Multi-Robot Rolling Diffusion（MRRD）的新型框架，用于在人类共享环境中实现大规模机器人团队的实时长视野路径规划。该方法针对现有生成式规划器路径时长固定、计算延迟高、难以适应不同目标距离和实时部署的问题进行了改进。

核心创新点包括：

◆ 采用滚动视野方案以适应人类运动的有限预测视野，实现长视野导航。

◆ 通过并行化扩散推理实现可扩展的人类风格路径生成，并结合基于冲突搜索的机制解决机器人间碰撞。

◆ 引入基于紧迫度的时序条件生成变速路径，并采用差异化引导项同时最大化对人类的社交感知和机器人间的高效协调。

实验结果表明，MRRD能在密集人群环境中实时扩展至15个机器人，在安全性和任务成功率方面均显著优于现有基线方法。</td></tr>
<tr><td>2026-07-08</td><td>Dynamic Evaluation of Classical and Control-Aware Optimal Trajectory Planning in Robot Manipulators<br><a href='http://arxiv.org/pdf/2607.05544'>论文</a></td><td>本文针对机械臂轨迹规划中经典方法仅考虑运动学而忽略动力学与控制代价的问题,提出了一种控制感知的最优轨迹规划框架。核心思路是在有限时域优化中显式纳入机械臂动力学模型与执行器力矩约束,使生成的轨迹在闭环非线性执行下具有更优的跟踪精度与能效表现。

◆ 创新点一:提出控制感知的最优轨迹规划框架,在有限时域内联合优化轨迹形状与执行器力矩分布,克服经典多项式轨迹仅追求运动学平滑而忽视动力学代价的局限。

◆ 创新点二:引入中点线性化策略以提升大范围点对点运动中动力学近似的精度,缓解传统单点线性化在长距离运动中产生的偏差。

◆ 创新点三:构建统一的公平评估框架,使所有规划器在完全一致的闭环非线性动力学、控制器结构与执行器约束下执行,从而能够隔离并真实反映轨迹生成方法本身对执行性能的影响。

◆ 创新点四:基于非线性简化UR5模型的仿真表明,该方法在跟踪误差、修正力矩与闭环执行代价上均显著优于三次、五次及梯形等经典方法,验证了运动学平滑并不等价于动力学高效的关键结论。</td></tr>
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
<tr><td>2026-07-08</td><td>Shift &amp; Drift: A Zero-Shot Benchmark for Generalizable and Robust Autonomous Driving Motion Planning<br><a href='http://arxiv.org/pdf/2607.07844'>论文</a></td><td>本文提出Shift &amp; Drift双轨基准测试，用于评估自动驾驶运动规划器在分布偏移下的泛化性和鲁棒性。研究发现，尽管基于大规模数据集(如nuPlan)训练的闭环规划器在分布内表现良好，但在面对新城市拓扑和执行扰动时的泛化能力与恢复机制仍缺乏系统研究。

◆ 构建了语义偏移轨道(Semantic Shift Track)，通过新颖的转换流水线将DeepScenario Open 3D航拍数据集集成到nuPlan仿真框架中，提供1182个涵盖德国四城及旧金山的零样本评估场景，重点测试密集行人-骑行者交互场景。

◆ 设计了状态分布漂移轨道(State-Distribution Drift Track)，通过向自车动力学注入随机扰动，量化规划器对累积执行错误的鲁棒性。

◆ 系统评估了模仿学习与强化学习等多种规划范式的失效模式，揭示了模仿学习在语义偏移(尤其在行人密集环境)下表现显著下降，且在时间相关执行噪声下持续漂移。

◆ 发现强化学习规划器在两个轨道上均表现出更优雅的性能退化，验证了模仿保真度与闭环韧性之间存在经验性权衡，为可靠部署提供了严格评测基准。</td></tr>
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
<tr><td>2026-07-07</td><td>MP-MPPI: A Motion Primitive Guided Sampling-Based Optimizer for Model Predictive Control<br><a href='http://arxiv.org/pdf/2607.06123'>论文</a></td><td>本文提出了一种将运动基元与模型预测路径积分（MPPI）相结合的新型采样优化方法MP-MPPI，旨在解决传统MPPI在路径规划能力上的局限性。该方法在实时采样优化循环中同时评估运动基元与扰动控制序列，实现了对控制空间的结构化探索与全局最优解的快速收敛。作者将该算法部署在四旋翼飞行器仿真平台上，并在包含障碍物的导航任务中进行了验证。

◆ 将运动基元引入MPPI框架，形成结构化采样与随机扰动采样相结合的混合采样策略，提升了算法对复杂控制空间的探索能力。

◆ 通过在单次优化循环中并行评估运动基元与扰动控制序列，加快了向全局最优解的收敛速度，同时保持了采样式控制器原有的实时性与反应性。

◆ 在四旋翼仿真平台上验证了算法在障碍物场导航任务中的有效性，证明了该方法在增强探索的同时不牺牲实时控制所需的快速响应特性。</td></tr>
<tr><td>2026-07-07</td><td>GraspIT: A Dataset Bridging the Sim-to-Real gap and back for Validated Grasping SE(3) Pose Generation<br><a href='http://arxiv.org/pdf/2607.05869'>论文</a></td><td>GraspIT针对机器人抓取任务中仿真与真实数据难以联合提供逼真观测与物理验证标注的难题,构建了一个大规模RGB-D抓取数据集。该数据集基于NVIDIA Isaac Sim搭建,采用四阶段物理滑移测试对Franka Panda并行实例进行抓取质量评估,超越了传统力闭合判据,并融入了轨迹可达性检查。在约230万个候选抓取中,83%被判定为优质抓取(s≥0.50),剩余17%通过力闭合但未通过滑移测试的样本被作为分级困难负样本。

◆ 提出四阶段物理滑移测试机制,结合力闭合、连续质量评分与轨迹可达性,提供更可靠的抓取物理验证。

◆ 构建Real↔Sim双向闭环标注流程,将仿真标签反向投影到100个真实场景,实现仿真到真实再到仿真的桥接。

◆ 提供约31.6万组带标注的RGB-D帧,覆盖1035个仿真场景与100个真实场景,包含实例掩码、6自由度位姿、物理属性及打分抓取。

◆ 所有工具开源并提供Docker容器化支持,Isaac Sim中的轨迹规划还可流式输出高分辨率演示数据,服务于桌面操作策略学习与行为克隆。</td></tr>
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
<tr><td>2026-07-05</td><td>Integrated Graph Search and Model Predictive Control for Smooth and Efficient Path Planning in Autonomous Vehicles<br><a href='http://arxiv.org/pdf/2607.04259'>论文</a></td><td>本文提出一种将图搜索与模型预测控制(MPC)相结合的自动驾驶路径规划框架,先利用Dijkstra算法在离散网格上获得粗路径,再据此构建空间变化的凸侧向安全走廊,将离散的避障决策转化为MPC的连续可行性约束。主要创新点包括:

◆ 提出序列式规划框架,显式利用图搜索粗路径引导MPC精细化过程,融合全局规划与局部优化能力。

◆ 构建空间变化的凸侧向安全走廊,把离散避障约束转化为MPC的连续可行性约束,在保证安全的同时提升求解效率。

◆ 在预测时域内通过惩罚侧向偏移的三阶空间导数(加加速度)保证路径平滑性,提升乘坐舒适性。

CarMaker高保真仿真结果表明,在直道与弯道多种超车场景下,相比基于多项式拟合与二次规划的方法,所提方法在侧向加速度、曲率和加加速度方面均更低,且计算成本在直道降低28.08%、弯道降低29.52%,在路径平滑性与计算效率之间取得了有效平衡。</td></tr>
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
<tr><td>2026-07-03</td><td>From Real-Time Planning to Reliable Execution:Scalable Coordination for Heterogeneous Multi-Robot Fleets in Industrial Environments<br><a href='http://arxiv.org/pdf/2607.00591'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-07-02</td><td>Path planning for unmanned naval surface vehicles<br><a href='http://arxiv.org/pdf/2607.01631'>论文</a></td><td>本文针对无人水面艇(USV)的路径规划问题，提出了一种结合全局与局部规划器的混合框架，同时处理固定障碍物和移动障碍物的避障任务。

◆ 全局规划器创新性地融合了三种方法：经典Grassfire算法、其新改进版本，以及一种更直观的新型概率路图法(PRM)。

◆ 局部规划器基于对障碍物运动方向相对于全局路径的观察，采用高层决策逻辑，系统性地引导USV从障碍物后方绕行，而非沿其平行行驶等待通过机会。

◆ 与传统D*算法相比，该方法在动态避障中表现出更优的策略选择能力。

仿真实验验证了所提方法的有效性，并通过与D*算法及其他动态规划系统的对比分析，凸显了其在移动障碍物避障场景中的独特优势。</td></tr>
<tr><td>2026-07-01</td><td>From Prediction Uncertainty to Conformalized Distance Fields for Safe Motion Planning<br><a href='http://arxiv.org/pdf/2607.00776'>论文</a></td><td>该论文针对动态环境中的安全运动规划问题,提出了一种基于函数型共形预测(FCP)的距离场不确定性量化与安全保障框架。核心思路是将整个预测距离场而非标量聚合分数进行共形化,从而获得分布无关、场级别的距离下界,保证任何满足该约束的轨迹都是安全可行的。

主要创新点如下:

◆ 提出函数型共形预测(FCP)框架,对整个预测距离场进行共形化,保留空间相干性,克服了传统标量共形方法在密集场景中过度保守和扩展性差的缺点。

◆ 揭示残差距离场具有经验低秩且近似时间不变的特性,使共形界可在系数空间分解,大幅降低计算复杂度,使每步成本几乎与障碍物数量无关。

◆ 离线通过函数型主成分分析和基于高斯混合模型的归纳共形过程拟合包络,在线通过轻量级自适应函数共形(AFCP)更新在低维向量上完成修正,能够在分布漂移下保持长期场覆盖率。

◆ 将包络作为收紧的安全约束嵌入采样型模型预测控制器FCP-MPC,在ETH-UCY行人基准和包含多达280个动态障碍物的密集3D四旋翼任务中,实现了安全性、可行性与效率的优良平衡,且计算开销远低于在线不确定性推理基线。</td></tr>
<tr><td>2026-07-01</td><td>Path Planning in Physically Viable World Models<br><a href='http://arxiv.org/pdf/2607.00673'>论文</a></td><td>本文提出了一种物理可行的世界模型，用于在非结构化户外环境中对机器人导航进行假设性查询评估。系统通过将三维高斯溅射重建场景与基于物理的仿真相结合，无需重新采集传感器数据即可生成物理修改后的环境版本，从而解决了机器人在使用陈旧地图时因环境物理变化而面临的长时域规划难题。

◆ 提出物理可行的世界模型，将3D高斯溅射场景与物理仿真结合，可生成未来地形变化下的多种环境版本

◆ 设计地形感知规划器，能够考虑模拟的物理事件、障碍物和形变，评估预规划路线在条件恶化后的可行性

◆ 在德州中部真实户外场地进行实验，通过多等级洪水模拟验证系统能暴露原始规划中不可见的长时域路径失败和必要的重路由行为

该方法使机器人和操作员能够在部署前评估未来地形变化对路径可行性的影响，特别适用于撤退或恢复困难等受限环境。</td></tr>
<tr><td>2026-07-01</td><td>Search-Based Spatiotemporal and Multi-Robot Motion Planning on Graphs of Space-Time Convex Sets<br><a href='http://arxiv.org/pdf/2607.00444'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-01</td><td>NeHMO: Neural Hamilton-Jacobi Reachability Learning for Decentralized Safe Multi-Arm Motion Planning<br><a href='http://arxiv.org/pdf/2607.00326'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-01</td><td>SE(2) Navigation Mesh<br><a href='http://arxiv.org/pdf/2607.01454'>论文</a></td><td>针对复杂多层环境中地面机器人的全局导航问题，本文提出SE(2)导航网格（SE(2) NavMesh），一种编码偏航角相关可通行性的多边形表示方法。现有方法存在点云缺乏显式表面结构、稠密三角网格路径规划计算昂贵、传统导航网格假设偏航不变等局限，SE(2) NavMesh有效解决了上述难题。

◆创新点一：基于足迹掩码评估可通行性，突破传统NavMesh偏航不变假设，使非圆形机器人在狭窄空间的导航成为可能。
◆创新点二：构建偏航角特定层级的图结构，显式表示平移与旋转连通性。
◆创新点三：提出A*-路径拉直-A*（ASA）分层路径规划策略，分别优化机器人位置和朝向。
◆创新点四：提出从流式点云在线增量更新SE(2) NavMesh的方法，支持与几何重建并发进行。

仿真显示该方法比传统NavMesh多捕获50%以上可通行区域，并优于基于采样的方法，真实机器人实验验证了其实时性与跨环境导航的有效性。</td></tr>
<tr><td>2026-07-01</td><td>CommonRoad-Game: A Human-in-the-Loop Simulation Framework for Autonomous Driving<br><a href='http://arxiv.org/pdf/2607.01382'>论文</a> | <a href='https://github.com/Yunfei-Bi8/CommonRoad-Game'>代码</a></td><td>CommonRoad-Game是一个轻量级的人在环仿真框架，专注于自动驾驶运动规划算法在交互场景中的系统化测试与人类驾驶行为分析，旨在解决现有平台依赖录制数据集、缺乏实时交互接口、与自动驾驶生态集成度弱及计算开销大等问题。

◆ 提出基于多线程架构的时间同步机制，将仿真时间与墙钟时间对齐，确保人车交互的确定性与时间一致性。
◆ 设计了场景生成模块，可记录人类驾驶日志，进而构建多样化且可复现的测试用例。
◆ 与CommonRoad平台深度集成，支持无缝接入兼容的运动规划器，实现可扩展的多智能体仿真。
◆ 整体架构轻量化，适合早期自动驾驶研究中的快速原型开发与灵活实验。

实验结果表明，该框架在时间同步稳定性、多智能体可扩展性及交互场景生成方面均表现良好。</td></tr>
<tr><td>2026-06-30</td><td>RRT-Rope: A deterministic shortening approach for fast near-optimal path planning in large-scale uncluttered 3D environments<br><a href='http://arxiv.org/pdf/2606.31948'>论文</a></td><td>◆本文提出RRT-Rope，面向大型、较少障碍的三维环境，实现快速近最优路径规划。
◆方法先用改进的RRT-connect快速生成可行路径，再进行高效后处理缩短。
◆其核心创新是确定性shortcutting策略，利用树枝中加入的中间节点更系统地拉直路径。
◆相比依赖随机收敛的Informed RRT*、RRT#等方法，RRT-Rope显著降低计算时间和路径代价。
◆实验显示该方法在多种仿真环境中均优于常见RRT变体和缩短技术，在代表性采场中最快可比次优算法快70%。</td></tr>
<tr><td>2026-06-30</td><td>Energy-Optimal Spatial Iterative Learning within a Virtual Tube<br><a href='http://arxiv.org/pdf/2606.31487'>论文</a></td><td>◆提出一种面向无人机的无模型在线空间迭代学习框架，在虚拟管道约束内逐次优化路径以降低能耗。
◆方法不依赖显式的无人机动力学模型或能耗模型，降低了建模误差和工程部署门槛。
◆相比传统基于模型的轨迹优化，该方法每次迭代计算复杂度仅为O(n)，适合实时或在线应用。
◆在测试案例中，其计算速度比IPOPT基准方法快约50至60倍，显著提升优化效率。
◆仿真和多平台真实飞行实验验证了该方法在节能效果、计算效率和实际适用性方面的有效性。</td></tr>
<tr><td>2026-06-30</td><td>Efficient Sim-to-Real Transfer of World-Action Models from Synthetic Priors<br><a href='http://arxiv.org/pdf/2606.31101'>论文</a></td><td>◆论文首次验证了世界-动作模型可仅依赖合成先验实现真实机器人操作的零样本迁移。

◆方法基于Cosmos Policy，将视频扩散模型适配为视觉-运动控制策略，用于生成和执行动作。

◆作者构建了带大规模域随机化的仿真环境，并利用AnyTask运动规划流水线自动生成示范数据。

◆在物体举升、开抽屉和抓取放置任务中，每个任务仅使用约800条合成示范，完全不依赖真实示范。

◆真实Franka机器人零样本部署平均成功率达到35%，表明该路线可显著降低真实数据采集成本。</td></tr>
<tr><td>2026-06-30</td><td>ELMP: Efficient Learning for Motion Planning via Analytical Policy Gradients<br><a href='http://arxiv.org/pdf/2607.00215'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-30</td><td>Optimal any-angle path planning in static and dynamic environments<br><a href='http://arxiv.org/pdf/2607.00065'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-30</td><td>Solution space path planning for supporting en-route air traffic control<br><a href='http://arxiv.org/pdf/2607.00064'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-29</td><td>MOAR Planner: Multi-Objective and Adaptive Risk-Aware Path Planning for Infrastructure Inspection with a UAV<br><a href='http://arxiv.org/pdf/2606.30575'>论文</a></td><td>◆提出MOAR路径规划器，面向基础设施巡检中无人机近距离避障与动态风险并存的自主导航问题。
◆构建多目标风险感知框架，可在任务过程中实时权衡安全性、飞行时间与能耗。
◆设计融合预计算代价地图、损伤代价和插入代价的风险感知代价函数，以刻画天气、通信、电池等变化风险。
◆引入自适应速度规划机制，使轨迹不仅调整空间路径，也能根据风险和资源状态动态调整飞行速度。
◆通过离散化状态与动作空间进行图搜索，并在仿真和真实飞行测试中验证其可实时生成性能覆盖约90%主流算法指标范围的轨迹。</td></tr>
<tr><td>2026-06-29</td><td>ReactiveBFM: Reactive Closed-Loop Motion Planning Towards Universal Humanoid Whole-Body Control<br><a href='http://arxiv.org/pdf/2606.30362'>论文</a></td><td>◆提出ReactiveBFM，将生成式运动规划与行为基础模型控制先验整合为实时闭环规划-控制框架，使人形机器人不再局限于预定义参考动作。

◆通过“调度式前缀采样”课程训练，让规划器从带误差的物理状态中学习恢复策略，有效缓解级联开环方法的累积暴露偏差。

◆设计异步重规划机制，解决自回归规划低频与全身控制高频之间的严重延迟不匹配问题。

◆结合轨迹分块与时序集成，生成更连续稳定的空间参考，减少执行抖动，实现流畅的全身协调运动。

◆在Unitree G1上实现大规模文本条件闭环动作，并支持零样本移动目标触达；仿真扰动测试中成功率达93.1%，较开环基线提升28.6%。</td></tr>
<tr><td>2026-06-29</td><td>Multi-UAV Formation Cooperative Obstacle Avoidance and Adaptive Shape Deformation Control in Complex Environments Based on BI-APF-RRT and Affine Transformation<br><a href='http://arxiv.org/pdf/2606.29755'>论文</a></td><td>◆论文提出一种融合BI-APF-RRT与仿射变换的多无人机编队协同避障框架，兼顾复杂环境中的避障灵活性与编队完整性。
◆以目标偏置的双向APF-RRT替代传统APF质心规划，提升全局路径搜索能力并缓解局部最优问题。
◆通过改进人工势场和三次B样条插值，提高质心路径的平滑性、收敛速度和可飞行性。
◆利用包含非均匀缩放与旋转的仿射变换矩阵，使编队可根据障碍物距离自适应变形。
◆结合分布式跟踪控制律，使跟随者稳定跟踪领导者，实现编队不解散地安全穿越复杂障碍区域。</td></tr>
<tr><td>2026-06-29</td><td>Motion Planning in Compressed Representation Spaces<br><a href='http://arxiv.org/pdf/2606.30940'>论文</a></td><td>◆论文提出了一种生成式运动规划框架，将深度学习的数据先验与基于搜索/优化的模型规划方法统一起来。

◆其核心是训练高压缩率自编码器，把轨迹表示为具有层级粗到细结构的离散潜空间token。

◆规划阶段不直接在原始轨迹空间搜索，而是在压缩后的token空间中搜索，从而显著降低维度并提升效率。

◆该方法支持在测试时优化任意目标函数，无需针对特定任务重新训练，兼具灵活性和泛化能力。

◆实验在nuPlan和Waymo Open Motion Dataset上验证了其在闭环运动规划与多智能体场景生成中的有效性，能生成真实且高质量的行为。</td></tr>
<tr><td>2026-06-29</td><td>TAPE: Tether-Aware Path Planning for Autonomous Exploration of Unknown 3D Cavities Using a Tangle-Compatible Tethered Aerial Robot<br><a href='http://arxiv.org/pdf/2606.30817'>论文</a></td><td>◆提出TAPE，首个面向未知三维洞穴自主探索的系绳感知路径规划方法，同时优化飞行距离与放绳长度。
◆采用两级层次架构，基于“缠绕主要受局部路径影响”的观察，将全局探索与局部系绳管理解耦。
◆全局层使用前沿点规划并求解TSP，以尽量缩短整体探索路径。
◆局部层通过可调决策函数在路径代价和系绳长度之间权衡，提升对最大系绳长度约束的满足能力。
◆仿真与实地测试表明，该方法仅比纯TSP路径平均多4.1%距离，却将系绳超限问题从47%案例降至0%。</td></tr>
<tr><td>2026-06-29</td><td>DSIP: A Dynamic Coordination Planner for Signal-Free Intersections using Diffusion-Model-Based Multi-Agent Motion Planning<br><a href='http://arxiv.org/pdf/2606.30694'>论文</a></td><td>◆论文提出DSIP，一种基于扩散模型的无信号交叉口多智能体运动规划框架，将路口控制从传统相位切换转向连续车辆轨迹协同优化。
◆DSIP利用生成式扩散过程同时规划多车轨迹，在理想通信与执行条件下评估该策略的理论性能上限。
◆该方法面向联网自动驾驶车辆，通过软件定义的轨迹级协调减少停车等待和启停行为，释放路口潜在通行能力。
◆作者在SUMO中针对多种四岔路口场景进行实验，验证了DSIP在不同交通密度下的适用性。
◆结果表明，DSIP相比固定配时信号和先进强化学习控制器显著降低平均延误、提高平均速度，尤其在中高流量下优势更明显。</td></tr>
<tr><td>2026-06-28</td><td>Analyzing Uncertainty in the Spatial Representation of the Kinematic Bicycle Model<br><a href='http://arxiv.org/pdf/2606.29566'>论文</a></td><td>◆本文聚焦后轮驱动自行车运动学模型在轮位移和转向角不确定性下的协方差演化问题，服务于自动驾驶定位与路径规划。
◆作者利用泰勒展开线性化非线性三角项，并推导了相关随机变量期望的闭式表达。
◆论文给出了离散随机运动学模型协方差矩阵各组成项的较完整解析形式，弥补了以往结果不完整或不准确的问题。
◆解析结果与蒙特卡洛仿真高度一致，验证了方法在实时不确定性传播中的近似精度。
◆该研究有助于评估离散运动学模型的适用边界，并可用于移动机器人和自动驾驶车辆的SLAM与里程计自标定。</td></tr>
<tr><td>2026-06-27</td><td>A Unified Framework for Multi-Contact Path Planning in the Rolling Robot Systems<br><a href='http://arxiv.org/pdf/2606.29065'>论文</a></td><td>◆论文提出了一个面向球形滚动机器人多接触无滑移路径规划的统一框架，针对多物体接触状态耦合与非完整约束难题。

◆基于Montana接触坐标公式，推导了紧凑的多球滚动运动学模型，将每个接触表示为五维堆叠状态。

◆在球面接触流形上直接构建Voronoi路线图，并支持球冠障碍物和互斥区域的流形内碰撞检测。

◆提出符合流形几何的log-exp平滑方法，将离散图路径优化为连续、平滑的表面路径。

◆通过运动学提升与前向仿真验证路径的可行性，并系统评估平滑性、采样密度、计算时间与路径质量的关系。</td></tr>
<tr><td>2026-06-27</td><td>Human2Any: Human-to-Robot Transfer via Constraint-Aware Compositional Planning<br><a href='http://arxiv.org/pdf/2606.28813'>论文</a> | <a href='https://human2any.github.io/'>代码</a></td><td>◆ Human2Any提出一种从人类视频向机器人操作迁移的框架，无需目标任务场景中的真实机器人示教数据。
◆ 其核心表示是“物体-物体交互运动”，聚焦任务相关的场景变化，弱化人手与机器人形态差异带来的影响。
◆ 方法学习可复用的物体中心交互先验，并将其与机器人端的可行性约束、运动规划进行组合。
◆ 该组合式规划使同一人类经验可适配不同机器人本体、场景几何和任务上下文。
◆ 实验在Franka桌面平台和RBY-1人形移动机器人上验证了其鲁棒的交互式操作能力。</td></tr>
<tr><td>2026-06-27</td><td>Vision-Language Models for Deployable Social Robot Navigation: Bridging Semantic Reasoning and Low-Level Control<br><a href='http://arxiv.org/pdf/2606.28760'>论文</a></td><td>◆本文系统梳理了视觉语言模型在社会机器人导航中的作用，强调其可为机器人提供语义理解、常识推理和自然语言交互能力。

◆论文提出一个统一视角，将现有方法划分为高层VLM推理、低层规划控制以及连接两者的中间机制三部分。

◆其核心创新在于提出结构化路线图，说明如何将VLM的高层语义判断可靠转化为空间接地、行为评估和可执行控制指令。

◆论文突出混合架构的重要性，指出可部署系统不能仅依赖VLM，而需结合传统导航的实时性、安全性和稳定性。

◆此外，文章综述了相关数据集与评估平台，并总结开放挑战，为构建可靠、合规、可落地的VLM社会导航系统提供参考框架。</td></tr>
<tr><td>2026-06-27</td><td>A Path-Space Formulation of Prediction in World Models: From a Single Action to Prediction, Planning, and Irreversibility<br><a href='http://arxiv.org/pdf/2606.28751'>论文</a></td><td>◆ 提出世界模型预测的“路径空间”表述，认为模型核心对象不是单步状态转移，而是未来轨迹上的概率测度。
◆ 在潜在动力学近似马尔可夫的局部情形下，将该路径测度写成Onsager-Machlup作用量形式。
◆ 统一解释预测、规划与不确定性：最可能轨迹、约束优化和涨落都可视为同一作用泛函上的操作。
◆ 将潜在动力学分解为可逆与不可逆部分，并基于模型rollout给出熵产生的操作性度量。
◆ 实验证明注意力不对称会随数据不可逆性而学习形成；强制对称化会抑制熵产生并损害不可逆长程预测，说明不可逆性可能是世界模型的计算资源。</td></tr>
<tr><td>2026-06-26</td><td>CascadeOcc: Rethinking 3D Occupancy World Models with Cascaded VQ Representations<br><a href='http://arxiv.org/pdf/2606.27644'>论文</a></td><td>◆提出CascadeOcc，将3D占用世界模型的重点从依赖外部模态或大语言模型，转向挖掘占用表示自身的结构层次潜力。
◆在自回归框架中引入级联VQ表示，以粗到细的方式从全局结构逐步恢复细粒度3D场景细节。
◆设计多尺度空间架构，增强复杂驾驶场景中占用表示的表达能力和生成精度。
◆加入TimeMixer建模多尺度时间依赖，形成空间与时间上的双重层次建模机制。
◆在4D占用预测和运动规划基准上取得视觉中心方法中的领先性能，证明优化内在表示可替代对外部基础模型的依赖。</td></tr>
<tr><td>2026-06-26</td><td>P-ARC: Exploiting Subproblem Independence for Parallel Multi-Robot Motion Planning<br><a href='http://arxiv.org/pdf/2606.27625'>论文</a></td><td>◆论文提出P-ARC，将自适应机器人协调方法ARC扩展为并行多机器人运动规划框架。

◆其核心创新是利用ARC问题分解后形成的子问题独立性，并行化个体初始规划、冲突检测和冲突解决三个阶段。

◆作者进一步引入OR并行多启动策略，结合ARC与P-ARC形成混合并行方法OR-P-ARC，以提升搜索效率和鲁棒性。

◆实验覆盖最多128个机器人的2D移动机器人与平面机械臂场景，系统分析冲突规模和任务分布对并行性能的影响。

◆在真实启发的多Panda机械臂场景中，P-ARC使用16个CPU核心相较顺序ARC获得接近4倍的规划时间加速。</td></tr>
<tr><td>2026-06-26</td><td>Physics-Guided Robotic Radiation Source Localization along Arbitrary Measurement Paths in Unstructured Environments<br><a href='http://arxiv.org/pdf/2606.27624'>论文</a></td><td>◆提出一种面向机器人辐射源定位的自动化框架，可在任意测量路径和未知非结构化环境中估计辐射源位置，无需专门规划接近辐射源的轨迹。

◆核心创新是引入物理信息机器学习模型，将伽马射线传播、衰减等物理规律融入数据驱动定位过程，提升泛化能力与可信度。

◆设计了物理启发的模型张量，用于处理由未知障碍物造成的衰减通量信号，并通过并行多模型计算增强定位精度和鲁棒性。

◆该方法在高保真蒙特卡洛粒子输运仿真中，覆盖不同空间尺度、源类型、障碍材料与几何形状、机器人轨迹，验证了广泛适用性。

◆论文还通过未纳入仿真的真实实验配置进行验证，并在实机部署中引入持续学习，推动机器人辐射感知从点式探测迈向空间智能。</td></tr>
<tr><td>2026-06-25</td><td>G2DP: Diffusion Planning with Spatio-Temporal Grid Guidance<br><a href='http://arxiv.org/pdf/2606.26017'>论文</a></td><td>◆ G2DP提出一种网格引导的扩散式自动驾驶规划器，解决现有扩散规划在去噪过程中缺乏密集环境约束、闭环执行不稳定的问题。
◆ 其核心创新是构建可微的时空代价体，将未来占用概率分布与路线进度图融合，形成统一的安全与导航约束表示。
◆ 该方法把代价体转化为连续安全能量函数，在推理阶段直接向扩散去噪过程注入密集梯度，引导轨迹避碰并沿路线高效前进。
◆ 相比依赖稀疏实体几何查询或事后优化的引导方式，G2DP具备更强的场景感知能力，尤其适合密集交互交通。
◆ 实验表明，G2DP在nuPlan闭环评测达到领先性能，并在interPlan和DeepScenario零样本迁移中保持高分，显著提升碰撞避免能力。</td></tr>
<tr><td>2026-06-25</td><td>BOWConnect: Parallel Bayesian Optimization over Windows with Learned Local Cost Maps for Sample-Efficient Kinodynamic Motion Planning<br><a href='http://arxiv.org/pdf/2606.27292'>论文</a> | <a href='https://bow-connect.github.io/'>代码</a></td><td>◆提出BOWConnect，一种面向动力学约束运动规划的双向并行采样框架，针对高维状态空间样本效率低、启发式代价不可靠和窄通道困难三大问题。
◆将“窗口贝叶斯优化”作为学习型转向函数，使各并行工作线程在线学习局部代价地图与约束，引导采样到可行、无碰撞控制。
◆采用从起点和目标区域同时扩展的双向树结构，显著提升复杂环境中的探索与连接效率。
◆引入空间哈希进行快速连接查询，并结合边值问题求解器生成满足运动学/动力学约束的桥接轨迹。
◆实验显示其在10个基准环境中达到100%成功率，并在窄通道、非凸空间及真实地面车和四旋翼部署中实现快速、无碰撞规划。</td></tr>
<tr><td>2026-06-25</td><td>PlanRL: A Trajectory Planning Architecture for Reinforcement Learning-based Driving Experts<br><a href='http://arxiv.org/pdf/2606.26858'>论文</a></td><td>◆论文提出PlanRL，将强化学习驾驶策略从直接输出油门/转向改为生成可规划的轨迹，提升了可解释性和与端到端规划架构的兼容性。
◆方法将RL策略与基于多项式的轨迹规划器结合，使驾驶专家能够在更高层次的轨迹空间中决策。
◆通过引入Frenet坐标系，复杂道路几何被转化为结构化的曲线坐标表示，降低了策略学习的空间复杂度。
◆规划阶段加入运动学可行性检查，确保轨迹满足车辆物理约束，并缓解规划跟踪中的累积误差。
◆在CARLA Offline Leaderboard v1和NoCrash基准上，PlanRL相比现有控制型RL专家显著提升驾驶分数和成功率，验证了其有效性。</td></tr>
<tr><td>2026-06-25</td><td>Learning Motion Feasibility from Point Clouds in Cluttered Environments<br><a href='http://arxiv.org/pdf/2606.26700'>论文</a></td><td>◆本文研究从原始RGB-D点云直接预测7自由度机械臂在杂乱场景中的抓取运动可行性，减少传统采样式运动规划器在不可行情形下的高计算开销。
◆作者提出首个面向真实杂乱桌面环境的大规模基准，包含88个扫描物体、190个场景和270万条抓取可行性标签。
◆论文系统比较了MLP、体素CNN和点云Transformer三类代表性模型，并在统一训练条件下评估其泛化能力。
◆最佳模型GRASPFC-PTX利用点云Transformer建模复杂几何关系，在新物体测试上达到0.996 AUROC。
◆该方法在保持高精度的同时显著快于SBMP，为任务与运动规划中的快速可行性筛选提供了实用学习方案。</td></tr>
<tr><td>2026-06-25</td><td>AO-ARC: Almost-Surely Asymptotically Optimal Multi-Robot Motion Planning with ARC<br><a href='http://arxiv.org/pdf/2606.27495'>论文</a></td><td>◆提出AO-ARC，一种anytime多机器人运动规划方法，兼具快速获得初始可行解和持续优化解质量的能力。
◆将AO-x元算法适配到ARC，通过反复求解带makespan代价界的MRMP实例，把可行性求解器转化为渐近优化算法。
◆利用ARC的自适应耦合/解耦机制，同时保持不同机器人组合下的一致代价界，从而提升扩展性与稳定性。
◆给出理论证明，表明AO-ARC具备几乎必然的渐近最优性保证。
◆实验覆盖不同协同复杂度的2D场景和真实应用相关的3D机械臂场景，显示其随机器人数量增加时比现有anytime方法收敛更快、更可靠。</td></tr>
<tr><td>2026-06-24</td><td>Event-Adaptive Motion Planning with Distilled Vision-Language Model in Safety-Critical Situations<br><a href='http://arxiv.org/pdf/2606.25629'>论文</a></td><td>◆论文提出EAMP框架，面向安全关键场景中由动态智能体异常行为引发的碰撞风险，实现事件自适应导航。
◆其核心思想是避免在控制闭环中频繁调用大型VLM，从而降低推理延迟并保证实时执行稳定性。
◆设计了提示可配置的语义事件触发器PC-SET，通过短时序视觉片段持续监测行为异常并按需触发语义干预。
◆提出蒸馏版SemNav-VLM，利用物理验证的语义蒸馏将异常事件映射为离散策略级决策。
◆进一步通过SMPC把高层语义策略转化为优化目标和几何参考的动态重配置。
◆实验表明，该方法在物流安全关键场景中显著提升动态安全裕度，同时保持较高实时效率。</td></tr>
<tr><td>2026-06-24</td><td>AISPO: Enhancing Depth Reliability for Robotic Manipulation of Non-Lambertian Objects via Affine-Invariant Shape Prior<br><a href='http://arxiv.org/pdf/2606.25503'>论文</a></td><td>AISPO面向透明、高反光等非朗伯物体的机器人操作，解决原始深度缺失或畸变导致抓取规划失败的问题。
◆提出一种深度补全框架，将多尺度RGB-D特征融合用于在复杂感知条件下恢复更可靠的深度。
◆引入仿射不变形状先验，约束预测深度的几何一致性，减少灾难性深度错误。
◆相比仅追求平均深度精度的方法，AISPO更强调物理可行性和结构完整性，使深度结果更适合抓取与运动规划。
◆通过基准测试和真实抓取实验验证了其对未见物体、新场景的泛化能力，并显著提升透明物体操作成功率。</td></tr>
<tr><td>2026-06-24</td><td>PRISM: Efficient and Locally Optimal Probabilistic Planning with Reachability Guarantees<br><a href='http://arxiv.org/pdf/2606.26413'>论文</a></td><td>◆ PRISM提出了一种面向受运动不确定性、状态与控制约束影响的信念空间多查询规划算法，兼顾高覆盖率与低轨迹成本。

◆ 论文给出了约束条件下状态协方差可控性的新理论结果，使信念空间规划可分解为确定性均值规划与协方差收缩。

◆ PRISM避免依赖低效的采样连通验证或高代价鲁棒控制，从而提升受限信念空间中的可达性覆盖。

◆ 算法引入在线局部优化机制，在保持可行性的同时降低信念空间轨迹的平均成本和成本方差。

◆ 在温和假设下，PRISM证明了即使存在执行器和障碍物约束也能实现完整覆盖，并在仿真实验中显著优于现有方法。</td></tr>
<tr><td>2026-06-24</td><td>Scaling Nonlinear Optimization: Many Problems One GPU<br><a href='http://arxiv.org/pdf/2606.26341'>论文</a> | <a href='https://github.com/johnviljoen/jaxipm'>代码</a></td><td>◆提出jaxipm：首个基于IPOPT思想、用JAX实现的GPU批量非线性规划求解器，可同时求解大量机器人NLP问题。
◆面向GPU并行框架重构传统CPU串行NLP求解流程，使其能融入强化学习、MPC和仿真批处理管线。
◆引入“异构迭代融合”以消除IPOPT中的复杂控制流，提升GPU可编译与并行执行效率。
◆提出“迭代级批处理”以减少GPU空闲时间，提高多问题并发求解吞吐量。
◆在多种四旋翼NMPC任务中验证，包括避障跟踪、多机无碰导航和杂乱环境导航，较IPOPT最高实现32.85倍吞吐提升。</td></tr>
<tr><td>2026-06-23</td><td>Optimization-based Safe Trajectory Planning for Autonomous Ground Vehicle in Multi-Floor Scenarios<br><a href='http://arxiv.org/pdf/2606.24631'>论文</a></td><td>该论文面向多楼层场景下自主地面车辆的安全轨迹规划问题，提出了一个由任务规划和轨迹规划组成的整体框架。

◆提出基于广义Voronoi图和多目标算法的任务规划策略，用于在各楼层中合理选择出口。

◆采用优化方法生成高质量、安全可行的车辆轨迹，适应多楼层环境中的复杂约束。

◆设计了热启动的分层规划框架，以提升优化求解速度并保证快速收敛。

◆提出相关约束计算方法，减少复杂障碍物带来的约束数量，降低轨迹规划计算负担。

◆通过仿真实验验证了该框架在多楼层场景中的可行性、效率和安全性。</td></tr>
<tr><td>2026-06-23</td><td>Adaptive Machine Learning Framework for UAV Trajectory Optimization in O-RAN<br><a href='http://arxiv.org/pdf/2606.24483'>论文</a></td><td>◆论文提出面向O-RAN架构的无人机轨迹优化框架，将UAV作为开放无线单元用于6G动态覆盖增强。
◆核心创新是引入增强型持续迁移学习，避免每个新环境都从零训练，提升跨场景适应效率。
◆框架维护预训练模型库，并通过模型选择机制匹配最相似环境，实现更精准的知识迁移。
◆当缺乏相似模型时，系统使用可持续优化的备用模型，保证新场景下的基本轨迹规划性能。
◆论文结合真实城市地图和射线追踪提升训练可靠性，仿真显示其收敛时间较从零训练降低44%至56%，较传统迁移学习最多降低40%。</td></tr>
<tr><td>2026-06-23</td><td>Varying Bundle Size Reactive Multi-Task Assignment using Selective Cost Estimation for Multi-Agent Systems<br><a href='http://arxiv.org/pdf/2606.24462'>论文</a></td><td>◆提出一种面向多机器人系统的可扩展反应式多任务分配框架，解决高精度任务执行成本估计昂贵导致实时性不足的问题。
◆设计分布式两阶段、多保真度的任务束生成方法，先用低保真启发式快速搜索候选任务束，再对最有前景者进行高保真路径规划验证。
◆支持动态变化的任务束大小，缓解传统组合拍卖中任务束枚举带来的指数复杂度。
◆通过中央协调器求解集合打包问题，在保证全局可行性的同时最大化整体效用。
◆仿真结果表明，该方法在多种环境中提升了反应式拍卖分配性能，并且无需暴露智能体状态和内部成本模型。</td></tr>
<tr><td>2026-06-23</td><td>DriveStack-VLA: Render-Teacher Alignment for BEV-Based DeepStack Vision-Language-Action Model<br><a href='http://arxiv.org/pdf/2606.24051'>论文</a></td><td>◆ DriveStack-VLA面向VLA自动驾驶模型空间智能不足的问题，将BEV表征引入大语言模型解码器，使策略具备更强的度量几何和俯视场景理解能力。
◆ 其DeepStack式连接把顶视结构信息与视觉语言推理深度融合，弥补仅依赖透视图像token和语言先验的缺陷。
◆ 论文提出Render-Teacher Alignment，通过栅格化图像教师对齐真实图像的感知关注，提升对安全关键线索的覆盖与利用。
◆ 为解决多模态轨迹选择难题，作者设计head-based self-critique模块，对采样轨迹排序并按需细化最优轨迹。
◆ 实验显示该方法在NAVSIMv1、NAVSIMv2和闭环Bench2Drive上取得强性能，验证了BEV空间 grounding、感知对齐与自我评估规划的有效性。</td></tr>
<tr><td>2026-06-23</td><td>CKM-Driven Communication-Aware UAV Intelligent Trajectory Optimization for Urban Inspection<br><a href='http://arxiv.org/pdf/2606.24979'>论文</a></td><td>◆提出面向城市巡检多无人机任务的CKM驱动通信感知轨迹规划框架，将信道建模与路径决策统一起来。

◆利用扩散模型构建时间累积信道知识地图，仅依靠稀疏观测即可重建高保真全局信道质量分布，降低飞行探测开销。

◆设计全局到局部的图注意力网络-软演员评论家算法，实现巡检目标排序与连续轨迹控制的协同优化。

◆图注意力网络解决复杂组合节点排序问题，生成兼顾任务效率和通信质量的巡检目标访问序列。

◆软演员评论家算法进一步优化平滑飞行动作，并动态避开通信衰减区域，使无人机无需依赖实时信道反馈也能提升轨迹效率和通信可靠性。</td></tr>
<tr><td>2026-06-22</td><td>Decentralized Autonomous Traffic Management through Corridor Networks<br><a href='http://arxiv.org/pdf/2606.23585'>论文</a></td><td>◆论文提出一种面向高级空中交通走廊网络的去中心化自治交通管理方法，以应对高密度载人/无人航空器协同难题。  
◆其核心创新是将多智能体强化学习从单走廊场景扩展到包含汇入、分流等结构的多走廊网络。  
◆训练策略可在更复杂网络中零样本迁移，无需集中式协调或重新训练。  
◆实验表明，该方法对交通密度变化、网络几何差异和异构飞行器性能具有良好泛化能力。  
◆仅依赖局部的进入、穿越和退出协同行为，系统仍能实现较好的边界遵循、完成率、速度、路径效率和安全间隔保持。</td></tr>
<tr><td>2026-06-22</td><td>Dense Reward for Multi-View 3D Reasoning with Global Maps and Local Views<br><a href='http://arxiv.org/pdf/2606.23557'>论文</a></td><td>◆提出DR-MV3D，一个面向多视角3D视觉问答的地图驱动学习框架，用密集、可验证奖励缓解仅靠答案级监督导致的跨视角推理不一致问题。
◆将任务分解为全局3D地图构建、问题条件下的视角轨迹规划，以及基于局部视图的自我中心 grounding 与答案预测。
◆设计全局一致性奖励，利用冻结的3D视觉基础模型生成几何一致伪标签，监督模型学习可靠的场景地图。
◆设计局部轨迹奖励，直接约束有序视角选择过程，提升多步空间推理中的视角规划能力。
◆通过GRPO进行轨迹级策略优化，并在MindCube、VSI-Bench和BLINK(MV)上优于强多图像基线，证明过程级密集监督对MV3D-VQA有效。</td></tr>
<tr><td>2026-06-22</td><td>FPAS: Frontier-Based Path Planning with Adaptive Sampling for Large-Scale Unknown Environments<br><a href='http://arxiv.org/pdf/2606.22838'>论文</a></td><td>◆ FPAS提出了一种面向大规模未知环境的前沿驱动路径规划框架，专注于提升长距离目标到达任务的效率。
◆ 该方法重新定义并利用frontier概念，不仅用于探索未知区域，还用于引导机器人朝目标方向持续推进。
◆ 在遇到死胡同或低效路径时，FPAS可基于frontier选择更有潜力的子目标，从而实现有效回退与重规划。
◆ 论文引入基于frontier开放度指标的自适应采样机制，在开阔区域稀疏建图以降低计算开销，在狭窄通道保持较高采样密度以保证连通性。
◆ 实验表明，FPAS在保持较强目标到达能力的同时，相比基线方法显著提升了计算效率，适合大规模未知环境导航。</td></tr>
<tr><td>2026-06-21</td><td>Interpolations: a linear algebra approach<br><a href='http://arxiv.org/pdf/2606.22671'>论文</a></td><td>◆本文提出一个统一的线性代数插值框架，将拉格朗日插值、Hermite样条和三角插值等问题表述为有限维函数空间对偶空间中的线性泛函条件。
◆论文建立了通用的存在唯一性定理，使插值问题可通过维数匹配与泛函线性无关性来判定。
◆作者推导了与给定插值条件对偶的基函数显式公式，从而可高效构造插值函数。
◆该框架扩展到三角插值，给出闭式对偶基并分析退化条件。
◆论文还处理异构传感器场景，即不同位置给定函数值与导数，并展示其在轨迹规划和信号处理中的应用潜力。</td></tr>
<tr><td>2026-06-21</td><td>Semantic-Aware Autonomous Exploration for UAVs in Unknown Indoor Environments<br><a href='http://arxiv.org/pdf/2606.22670'>论文</a></td><td>◆提出一种面向未知室内环境的语义感知无人机自主探索框架，将语义信息融入传统基于几何的探索流程。
◆在Dynamic Exploration Planner基础上，增量构建PRM并增加语义层，使路线图同时表达空间连通性与场景语义价值。
◆设计语义奖励函数，优先引导无人机探索包含关键物体或结构的高信息量区域，从而提升探索效率。
◆通过持续更新路线图，实现更高效的前沿选择与路径规划，适应探索过程中不断变化的环境认知。
◆在ROS Noetic与Gazebo中基于RGB-D传感器验证，实验表明该方法达到90%至94%的覆盖率，并相比几何方法减少探索时间和飞行距离。</td></tr>
<tr><td>2026-06-21</td><td>LAWNs Meet SWIPT: Beamforming and Power Splitting Optimization for Predictive Control<br><a href='http://arxiv.org/pdf/2606.22534'>论文</a></td><td>◆论文首次面向SWIPT赋能的低空无线网络，研究多天线基站同时向多架UAS传输控制信息与无线能量的联合设计问题。

◆针对存在多个移动禁飞区的场景，引入流函数理论构造平滑且安全的参考轨迹，实现无碰撞路径规划。

◆建立实时联合优化框架，同时优化控制输入、发射波束成形向量和功率分割比例，以兼顾轨迹跟踪精度与能量可持续性。

◆提出两阶段求解方法：先基于MPC生成预测控制输入，再结合SDR与SCA高效优化通信与能量传输变量。

◆论文证明了所用SDR在该问题中的紧性，并通过仿真表明该方案在跟踪精度和能量收集方面显著优于基准方法。</td></tr>
<tr><td>2026-06-19</td><td>THREAD: Trajectory Planning for Hybrid Rigid-Soft Manipulators with Environment-Aware Diffusion<br><a href='http://arxiv.org/pdf/2606.21792'>论文</a></td><td>◆提出THREAD，首个面向刚柔混合机械臂的扩散式轨迹规划器，专门解决狭窄孔洞穿越等受限环境操作难题。
◆方法学习在局部环境几何条件下物理可实现的骨架轨迹生成先验，而非仅在自由空间规划。
◆将刚性段与软体段联合建模，避免独立规划带来的运动学耦合失配问题。
◆引入受物理启发的损失函数，同时约束曲率、轨迹平滑性和碰撞风险，提升可行性与安全性。
◆仿真结果显示THREAD达到92.4%任务成功率，碰撞次数比最强基线少5倍。
◆系统还能以少量在线更新实现跨本体真实迁移，并成功穿过仅为软体段直径1.3倍的小孔。</td></tr>
<tr><td>2026-06-19</td><td>Temporal logics and formal synthesis for robot planning and control<br><a href='http://arxiv.org/pdf/2606.21438'>论文</a></td><td>◆论文系统阐述了时序逻辑，尤其是线性时序逻辑和信号时序逻辑，如何用于精确描述机器人随时间变化的复杂行为需求。

◆其核心贡献是将机器人规划与控制问题统一到“形式化规约—自动合成—可证明保证”的框架中。

◆论文梳理了多类形式化合成方法，包括离散图搜索、博弈模型、采样式运动规划、轨迹优化和基于控制证书的方法。

◆创新点在于强调从高层逻辑任务到低层连续控制之间的衔接，使机器人行为不仅可执行，而且可验证。

◆论文还指出真实机器人部署中的关键挑战：模型精度、计算复杂度与可获得的严格保证之间需要权衡。</td></tr>
<tr><td>2026-06-18</td><td>DIFF-IPPO: Diffusion-Based Informative Path Planning with Open-Vocabulary Belief Maps<br><a href='http://arxiv.org/pdf/2606.16780'>论文</a></td><td>本文提出了DIFF-IPPO框架，将开放词汇信念图生成器与基于扩散的规划器相结合用于信息性路径规划。
◆提出将基于扩散模型的规划器引入信息性路径规划，突破了现有方法难以直接基于非高斯多模态信念图生成全局轨迹的局限。
◆构建了结合开放词汇感知与扩散规划的流水线，使生成的轨迹能将传感器覆盖集中于高信念区域。
该方法在多场景中取得了81.49%至86.55%的归一化检测得分。
在模拟搜救任务中，五架无人机利用批处理条件轨迹生成，仅3.5分钟即可首次定位目标。</td></tr>
<tr><td>2026-06-18</td><td>Increasing Resilience of Continuum Robots via Motion Planning Algorithms<br><a href='http://arxiv.org/pdf/2606.20495'>论文</a></td><td>◆ 本文面向连续体机器人韧性提升问题，系统研究了运动规划算法在多准则决策下对路径质量与执行时间的影响。

◆ 作者将层次分析法AHP引入遗传算法和A星算法，用距离、电机损伤、机械臂损伤和精度四项指标综合评估路径优劣。

◆ 论文的核心创新在于把“减少维护需求、延长运行时间”的韧性目标转化为可量化的路径规划评价准则。

◆ 实验在两个模拟环境中进行，并结合真实机器人原型特征设计单路径点和多路径点场景，提高了验证的针对性。

◆ 结果表明，遗传算法的运行时间对环境规模不敏感，且能生成更多样化路径，相比A星更有利于提升连续体机器人的韧性。</td></tr>
<tr><td>2026-06-18</td><td>Autonomous Driving with Priority-Ordered STL Specifications Under Multimodal Uncertainty<br><a href='http://arxiv.org/pdf/2606.20336'>论文</a></td><td>◆提出一种面向自动驾驶的轨迹规划框架，将多项Signal Temporal Logic规范按词典序优先级组织，用于处理安全、舒适性和交通规则之间的冲突。

◆该方法在规划中显式考虑周围交通参与者轨迹预测的多模态不确定性，使规范满足性在不确定环境下仍具有意义。

◆框架能够在无法同时满足所有要求时，优先保证更高优先级规范，例如安全约束，再尽量优化低优先级目标。

◆作者将该优先级STL formulation与Model Predictive Path Integral控制结合，实现可用于在线轨迹生成的求解方案。

◆仿真实验表明，该方法能在现实多模态不确定场景中高效处理冲突目标，并生成更符合安全关键需求的驾驶行为。</td></tr>
<tr><td>2026-06-17</td><td>Admittance-Based Surface Alignment for Human-in-the-Loop Robotic Visual Inspection<br><a href='http://arxiv.org/pdf/2606.18601'>论文</a></td><td>◆提出一种面向人机协同机器人视觉检测的实时闭环姿态控制流程，解决感知噪声、表面不规则和人工遥操作共同作用下的表面对齐问题。
◆将操作员输入与视觉感知得到的表面法向对齐目标统一到导纳控制框架中，实现共享自治下的柔顺响应。
◆创新性地把末端执行器建模为在黏性介质中运动的虚拟球体，用可解释的质量-阻尼系统生成同步、平滑的姿态调整。
◆相比纯离线规划，该方法能够根据实时表面几何误差和人工指令动态修正运动，更适合工业在线检测场景。
◆在6自由度机械臂上验证了系统的稳定法向跟踪能力，最终平均姿态误差达到0.4°，体现出较高精度。</td></tr>
<tr><td>2026-06-16</td><td>LAGO Policy: Latency-Aware Asynchronous Diffusion Policies with Goal-Directed Collision-Free Planning for Smooth Manipulation<br><a href='http://arxiv.org/pdf/2606.17982'>论文</a> | <a href='https://lago-policy.github.io/'>代码</a></td><td>LAGO Policy针对异步扩散视觉运动策略在真实机器人中易出现动作块间不连续、运动抖动和碰撞的问题，提出了一个兼顾平滑性、安全性与实时执行的统一框架。
◆ 通过延迟感知的classifier-free guidance，将未来动作作为条件引入扩散策略，显著提升异步推理下的动作块间一致性。
◆ 从示范数据中预测任务相关交互目标，使策略具备面向目标的避障与无碰撞轨迹规划能力。
◆ 引入时空轨迹优化，对即将执行的动作进行低加加速度、可行性和安全性约束下的细化。
◆ 将扩散策略生成、目标推断与轨迹优化整合到同一异步动作生成流程中，提升真实场景部署可靠性。
实验表明，LAGO Policy在多种复杂操作任务中实现了更平滑、更安全的执行，并保持较高任务成功率。</td></tr>
<tr><td>2026-06-16</td><td>FLAP: FOV-Constrained Active Perception Planning for Prior-Map-Free 3D Navigation<br><a href='http://arxiv.org/pdf/2606.17630'>论文</a></td><td>◆本文提出FLAP框架，将主动感知直接融入未知复杂3D环境中的无人机轨迹优化，以兼顾安全性与飞行效率。
◆其感知约束由无人机动力学推导，并在传感器坐标系中建模，从而更精确处理有限视场和探测距离。
◆论文设计了速度触发的感知约束激活机制，使规划器能根据运动状态动态权衡避障感知与轨迹效率。
◆方法引入带参数化起始时间优化的主动感知子轨迹段，降低因障碍物发现过晚导致的碰撞风险。
◆该框架支持任意3D机动中的主动感知，无需依赖昂贵的感知感知前端路径生成器，并在仿真和真实实验中验证了对不同环境与传感器配置的鲁棒性。</td></tr>
<tr><td>2026-06-16</td><td>Task Allocation and Motion Planning in Dynamic, Cluttered Environments via CBBA and Graphs of Convex Sets<br><a href='http://arxiv.org/pdf/2606.18516'>论文</a></td><td>◆论文提出一种面向动态、杂乱环境的多智能体任务分配与运动规划联合框架，将CBBA分布式任务分配与GCS轨迹优化相结合。

◆利用时间扩展的3D+time配置空间，GCS能够在存在静态和动态障碍的场景中生成安全且时间高效的最优轨迹。

◆方法将任务分配与轨迹规划紧密耦合，使CBBA在决策时不仅考虑任务归属，还考虑智能体到达动态任务的时间和位置可行性。

◆该框架支持动态任务如会合目标的分配，能够提供更准确的任务完成时间估计，从而提升分配质量。

◆通过在3D+time空间中协调路径，系统可降低多智能体间碰撞风险，并在仿真杂乱环境中验证了有效性。</td></tr>
<tr><td>2026-06-15</td><td>WaveSync: Constrained Wavefront Optimization for Synchronized Co-Speech Gestures in Humanoid Robots<br><a href='http://arxiv.org/pdf/2606.16600'>论文</a> | <a href='https://github.com/pairs-lab/WaveSync}{WaveSync}'>代码</a></td><td>本文提出了WaveSync混合框架，解决了人形机器人生成共语手势时难以兼顾语音同步与硬件运动约束的耦合难题。
◆利用大语言模型将对话分解为结构化语义模式并分配逐词重要性权重，创新性地构建出连续的语义重要性波形。
◆采用动态运动基元塑造手势轨迹，在增强手势表现力的同时严格保证了运动的运动学可行性。
◆引入波前优化阶段，通过手势时长压缩与前向传播机制，实现手势与语音的峰值对齐并解决残余的运动学违规问题。
实验表明该方法实现了高同步精度，在客观与主观评估中均超越基线，且各组件对生成富有表现力且符合运动学规范的手势均不可或缺。</td></tr>
<tr><td>2026-06-15</td><td>Steering Emotional Dynamics for Art Therapy: Controllable Narrative Script Generation through Hierarchically Guided LLM Agents<br><a href='http://arxiv.org/pdf/2606.16481'>论文</a></td><td>本文提出了EC-Script框架，一种基于大语言模型智能体的分层控制框架，解决了现有文本生成方法无法遵循指定情感轨迹以满足艺术治疗需求的问题。
◆通过情感轨迹规划建立整体叙事方向，确保叙事的宏观情感走向受控。
◆采用角色驱动的场景生成推进场景级情节发展，使情节逻辑与角色状态契合。
◆利用情感控制的剧本编写调节角色局部情感变化，精细管理微观情感波动。
实验表明，该框架生成的逐场景剧本与预设轨迹高度一致，在情感轨迹遵循度上显著优于基线方法。
该研究实现了叙事生成中情感动态的有效导向，为AI辅助情感疗愈提供了可靠技术支持。</td></tr>
<tr><td>2026-06-15</td><td>HOLO-MPPI: Multi-Scenario Motion Planning via Hierarchical Policy Optimization<br><a href='http://arxiv.org/pdf/2606.16480'>论文</a></td><td>◆ 提出HOLO-MPPI框架，将离线高层策略学习与在线低层MPPI随机最优控制结合，用于无需逐场景调参的多场景运动规划。

◆ 离线阶段学习一个在抽象动作空间中生成鲁棒计划的高层策略，并配合学习到的世界模型支持在线预测与评估。

◆ 在线阶段让高层策略作为数据驱动的先验生成器，根据当前观测和目标动态参数化MPPI的采样分布，避免手工设计先验难以扩展的问题。

◆ 通过MPPI在高层先验附近实时优化低层控制序列，使系统既具备跨场景泛化能力，又能适应局部扰动和随机交互。

◆ 在自动驾驶任务中，论文设计了有效的高层动作空间和针对性的模型结构，并在多种驾驶场景中验证其优于传统MPPI和端到端RL基线，同时保持实时控制性能。</td></tr>
<tr><td>2026-06-15</td><td>Game-Theoretic Multi-Agent Reinforcement Learning for Swarm Trajectory Planning in Low-Altitude Wireless Networks<br><a href='http://arxiv.org/pdf/2606.16386'>论文</a></td><td>本文针对低空无线网络中多小区场景下无人机群轨迹规划存在资源块分配引发强战略耦合的问题进行研究。为了在通信吞吐量和任务完成效率之间取得平衡并解决多小区资源拥塞问题，作者提出了一种基于博弈论的多智能体强化学习框架。
◆将多小区拥塞感知的无人机轨迹规划问题构建为具有通信与任务感知效用函数的合作随机拥塞博弈。
◆提出一种集中训练分布式执行的多智能体近端策略优化算法，以在多小区资源拥塞下最大化社会效益。
仿真结果表明，该方法在总体效用和任务成功率上优于多种基线算法，且能在实际训练预算内实现稳定收敛。</td></tr>
<tr><td>2026-06-15</td><td>GraphWorld: Long-Horizon Planning with World Models for End-to-End Autonomous Driving<br><a href='http://arxiv.org/pdf/2606.16274'>论文</a></td><td>针对现有端到端自动驾驶方法局限于短期规划且缺乏长期时序依赖建模的问题，本文提出了GraphWorld框架，通过隐式世界模型显式增强长视距规划能力。
◆提出以自车为中心的交互图，基于空间距离自适应建模关键相邻智能体，并通过跨节点交叉注意力将关系上下文传播至规划查询。
◆提出世界状态条件规划，通过建模自车与周围智能体的交互来学习以自车为中心的隐式世界表征。
该表征捕捉了关键的交互动态与安全语义，并作为条件信号引导具有安全意识的长视距轨迹规划。
实验表明，GraphWorld显著降低了碰撞率并提升了长视距规划性能，验证了其在复杂驾驶环境中的有效性。</td></tr>
<tr><td>2026-06-15</td><td>PolyMerge: Compressing 3D Gaussian Splats with Polytope Coverings for Provably Safe Resource-Constrained Navigation<br><a href='http://arxiv.org/pdf/2606.16232'>论文</a> | <a href='https://athlon76.github.io/PolyMerge-website/'>代码</a></td><td>◆ PolyMerge将高保真的3D Gaussian Splatting场景压缩为轻量级凸多面体集合，显著降低导航所需的存储与计算开销。

◆ 其核心创新是用凸多面体并集对3DGS中的障碍物进行可证明的保守外包络，从而保证不会低估碰撞风险。

◆ 方法允许调节多面体数量，在表示保守性、路径可行性和实时计算成本之间灵活权衡。

◆ PolyMerge进一步与控制屏障函数（CBF）结合，使无人机能够基于压缩场景模型规划可证明安全的无碰撞轨迹。

◆ 论文通过仿真和Crazyflie无人机硬件实验验证了该方法在严苛机载算力限制下仍能实时运行，并在速度上优于基线方法。</td></tr>
<tr><td>2026-06-15</td><td>Intermittent Strategic Cooperation of Two Selfish Agents on Graphs<br><a href='http://arxiv.org/pdf/2606.17216'>论文</a></td><td>◆该论文提出IC2PP问题，刻画两个自利智能体在图上追求各自目标时，如何在特定节点进行间歇性合作以降低自身路径成本。
◆它将该问题建模为双人最短路径博弈，突出合作虽可互利但因任一时刻可偏离而具有战略脆弱性。
◆论文系统刻画了纯纳什均衡联合策略的结构，证明稳定合作必须满足高度受限的形式。
◆作者证明任意IC2PP实例至少存在一个纯纳什均衡，并给出多项式时间算法枚举所有相关均衡。
◆在存在多个均衡时，论文引入基于讨价还价理论的均衡选择机制，并通过实验比较个体旅行时间与社会福利表现。</td></tr>
<tr><td>2026-06-14</td><td>Identification of a Physics-Based Electrical Power Consumption Model for the Unitree G1 Humanoid Arm<br><a href='http://arxiv.org/pdf/2606.15915'>论文</a></td><td>本文针对Unitree G1仿人机器人的七自由度左臂，提出了一种基于物理的参数线性电功耗预测模型。
◆该模型结合了执行器损耗项与基线扭矩校正，有效捕捉了重力补偿负载变化，并能准确预测负净功率轨迹。
◆引入了成对交互项，成功建模了多关节同时运动时的功率耦合效应。
模型参数通过机器人机载功率测量数据进行辨识，在897条多速度轨迹测试中R平方达0.933，且在未见速度轨迹上R平方达0.965，展现了出色的泛化能力。
此外，对辨识参数的分析揭示了手臂各异的功耗特征，即粘性摩擦主导肩俯仰与腕关节，铜损主导肩偏航与肘部，库仑摩擦则主导肩横滚。</td></tr>
<tr><td>2026-06-14</td><td>Pixels to Proofs: Probabilistically-Safe Latent World Model Control via Parallel Conformal Robust MPC<br><a href='http://arxiv.org/pdf/2606.15594'>论文</a></td><td>◆ 提出SLS²框架，实现从像素输入到安全反馈运动规划的端到端控制，将学习型潜在世界模型与鲁棒MPC结合。
◆ 训练动作条件联合嵌入世界模型，获得紧凑且近似马尔可夫的潜在状态，使梯度轨迹优化更高效。
◆ 引入保形预测校准潜在动力学误差，为真实系统的不确定性构造概率有效的鲁棒误差界。
◆ 结合GPU加速的系统级综合鲁棒MPC，在潜在空间中施加鲁棒约束以提升闭环安全性。
◆ 进一步学习并保形化潜在约束检查器，使规划器能处理概率安全约束；实验显示其在视觉控制任务中同时提升到达目标能力和安全性。</td></tr>
<tr><td>2026-06-13</td><td>Task-Aware Environment Augmentation for Reliable Navigation via Shielded Conditional Diffusion<br><a href='http://arxiv.org/pdf/2606.15154'>论文</a> | <a href='https://scoda-diffusion.github.io/}'>代码</a></td><td>本文提出了任务感知环境增强这一全新问题，即在给定地图和规划轨迹下，通过在环境中布置有限数量的视觉标记来保障机器人在不确定性下的可靠执行，并提出了SCoDA方法予以解决。
◆翻转了传统研究视角，不再让机器人去适应缺乏观测的固定环境，而是通过优化标记布局让环境主动支持机器人的任务执行。
◆利用条件扩散模型学习高性能标记布局的条件分布，并以环境、轨迹、扰动上下文和期望执行特征为条件进行生成。
◆提出屏蔽采样器，通过推理执行过程中需要姿态纠正的关键位置，将扩散分布引导至任务相关且符合有限预算的增强方案。
仿真和硬件实验表明，该方法显著提升了轨迹执行的可靠性并缩短了完成时间。</td></tr>
<tr><td>2026-06-12</td><td>Bounding Boxes as Goals: Language-Conditioned Grasping via Neuro-Symbolic Planning<br><a href='http://arxiv.org/pdf/2606.12910'>论文</a></td><td>论文核心贡献总结:

该论文提出了GRASP(Grounded Reasoning and Symbolic Planning)框架,旨在实现开放词汇的桌面机器人操作任务。该方法利用预训练的视觉-语言模型(VLM)将自然语言指令转换为神经符号目标状态,并通过边界框检测管道将其与物理世界相对应,从而使机器人能够实时响应自然语言提示。在90次真实机器人实验中,该框架在三个难度等级上实现了73.3%的总体成功率,且无需任何任务特定的训练或微调。

主要创新点如下:

◆ 提出神经符号规划框架,将VLM的语言理解能力与符号化目标表示相结合,把自然语言查询转化为可执行的符号目标状态。

◆ 采用边界框作为目标表示形式,通过检测管道将抽象语言概念与物理空间精准对接,避免了传统方法对固定颜色列表或硬编码坐标的依赖。

◆ 实现真正的零样本开放词汇操作能力,无需数千次演示数据训练,即可解释&quot;顶层货架&quot;等抽象空间概念。

◆ 相比于当前计算密集型的SOTA方法,该框架更加轻量化,降低了计算开销,更适合实时部署。

◆ 在真实机器人平台上完成了多难度等级的系统性验证,证明了方法在实际场景中的可行性与泛化性。</td></tr>
<tr><td>2026-06-12</td><td>Short-Horizon Position Accuracy of Single-Track Models: Implications for Motion Planning of Autonomous Vehicles<br><a href='http://arxiv.org/pdf/2606.14216'>论文</a></td><td>自动驾驶运动规划依赖计算高效且准确的车辆模型，但目前缺乏针对模型短时域位置精度的系统性实车评估。本文通过实车专用实验识别参数，在多种驾驶工况下将三种单轨模型的短时域位置预测与实车测量数据进行了系统比较。
◆首次系统性地评估了单轨车辆模型在短时域内的位置精度，填补了模型预测与真实测量数据对比的空白。
◆揭示了模型复杂度、参数化质量与位置精度之间的权衡关系，打破了寻找单一最优模型的局限。
◆为模型预测控制等运动规划应用中的车辆模型选择，提供了基于实际精度权衡的指导性见解。</td></tr>
<tr><td>2026-06-12</td><td>Semidefinite Relaxations for Collision-Free Motion Planning<br><a href='http://arxiv.org/pdf/2606.14063'>论文</a></td><td>本文研究了无碰撞运动规划的半定松弛方法，将点机器人穿越球形障碍物的问题精确建模为多项式曲线上的非凸问题，并提出自然半定松弛。
◆首次从理论证明，求解该凸松弛等价于在更高维空间中全局求解相关的运动规划问题，给出了松弛紧致性的充要条件与直观解释。
◆提出对称性约简方法，使半定正定锥的规模仅与多项式阶数线性相关且独立于环境维度，显著缩小了问题规模。
实验表明，该方法比直接使用SNOPT和IPOPT求解非线性规划快十至百倍，方差更低，能可靠找到原问题的局部最优路径。
最后，该方法被成功用作RRT规划器中的凸转向函数，实现了具有C4连续轨迹的四旋翼最小抖动规划。</td></tr>
<tr><td>2026-06-12</td><td>ParkingTransformer: LLM-Enhanced End-to-End Trajectory Planning for Autonomous Parking<br><a href='http://arxiv.org/pdf/2606.17082'>论文</a></td><td>◆ 提出ParkingTransformer，用大语言模型增强端到端自主泊车规划，提升长距离从道路到车位泊车的语义理解与可解释性。

◆ 方法将轨迹查询与LLM隐式状态特征结合，直接利用历史信息和原始多视角传感器数据生成轨迹，避免依赖稠密BEV表示。

◆ 引入3D位置编码，显式注入空间几何信息，弥补LLM在空间推理方面的不足。

◆ 设计固定窗口流式历史处理机制，提高长时序信息建模效率和推理速度。

◆ 采用粗到细解码策略逐步优化轨迹精度，并在CARLA和真实车辆实验中验证了较高的驾驶得分与泊车成功率。</td></tr>
<tr><td>2026-06-11</td><td>Mana: Dexterous Manipulation of Articulated Tools<br><a href='http://arxiv.org/pdf/2606.13677'>论文</a></td><td>论文核心贡献总结:

该论文提出了Mana(Manipulation Animator),一个面向铰接式工具灵巧操作的通用sim-to-real框架,旨在解决灵巧机器人领域中协调内部自由度与接触丰富交互的难题。作者将灵巧操作重新诠释为动画生成问题,借鉴计算机动画的思想,采用由粗到细的流程,将程序化生成的抓取关键帧通过运动规划与强化学习转化为完整的操作轨迹。该方法在四种不同尺度和关节类型的铰接工具上均实现了抓取与手内操作的零样本sim-to-real迁移,为可扩展的铰接工具灵巧操作提供了新思路。

主要创新点:

◆ 首次将铰接式工具的灵巧操作问题重新表述为动画生成问题,借鉴计算机动画中的关键帧思想构建操作轨迹生成范式。

◆ 提出由粗到细的Mana流程,将程序化生成的抓取关键帧通过运动规划和强化学习相结合,转化为高质量的操作轨迹。

◆ 数据生成过程高度自动化,用户仅需几次鼠标点击即可指定功能性可供性,每个工具配置耗时不到一分钟,大幅降低人工成本。

◆ 在四种不同尺度与关节类型的铰接工具上验证了零样本sim-to-real迁移能力,包括抓取与手内操作两类任务。

◆ 填补了以往研究主要聚焦于刚性物体的空白,首次系统地解决铰接式工具功能性抓取与操作策略的学习难题,具有良好的可扩展性。</td></tr>
<tr><td>2026-06-11</td><td>Distribution-Agnostic Robust Trajectory Optimization via Chance-Constrained Reinforcement Learning<br><a href='http://arxiv.org/pdf/2606.13605'>论文</a></td><td>本文提出了一种基于机会约束强化学习的分布无关鲁棒轨迹优化框架,通过对不确定性仅要求可采样的方式,突破了传统方法对高斯分布等特定假设的依赖。该框架先离线计算确定性标称轨迹,再利用强化学习对其进行鲁棒化增强,并通过两个差异显著的航天轨迹问题(三维多脉冲地火转移与大气层精确定点火箭着陆)验证了方法的通用性与有效性,在保持概率可行性的同时,在上尾燃料成本上仍具竞争力。

◆ 提出分布无关的鲁棒轨迹优化框架,初始条件与过程噪声仅需可采样,无需已知概率分布形式。

◆ 采用&quot;标称轨迹+鲁棒化增强&quot;的两阶段设计,强化学习仅用于在确定性基线上施加结构化的仿射闭环修正律,包含前馈控制调整与时变反馈增益。

◆ 通过基于轨迹采样的上尾分位数经验性地强制概率可行性,并利用协方差可行性惩罚约束终端散布。

◆ 同一鲁棒化架构无需重新设计核心随机控制结构,即可跨异构航天轨迹规划问题(脉冲深空转移与连续推力大气着陆)迁移使用。

◆ 在训练中未见的过程扰动以及有界均匀不确定性等非高斯场景下,验证了方法的泛化与鲁棒能力。</td></tr>
<tr><td>2026-06-11</td><td>SPARC: Reliable Spatial Annotations from Robot Demonstrations at Scale<br><a href='http://arxiv.org/pdf/2606.13497'>论文</a> | <a href='https://intuitive-robots.github.io/sparc-labeling'>代码</a></td><td>本文提出了SPARC(带可靠性校准的机器人演示空间标注框架),这是一个风险感知的自动化标注系统,能够为机器人演示数据生成结构化空间标注(如边界框、物体轨迹、操作阶段标签)并为每条标注分配可靠性评分。针对现有自动化标注流程缺乏可靠质量信号、检测器置信度无法准确反映标注正确性的问题,SPARC利用机器人任务固有的时空结构生成可靠性信号,在减少噪声标签的同时保留更多有用样本。在涵盖多种机器人形态和场景的1.7k人工标注演示上,SPARC显著优于仅依赖检测的基线方法,且在高精度工作点下保留了三倍以上的样本。

◆ 提出了首个面向机器人演示的风险感知空间标注框架SPARC,首次将可靠性校准引入自动化标注流程。
◆ 创新性地利用机器人任务的时空结构作为可靠性信号来源,突破了传统检测器置信度校准不准确的瓶颈。
◆ 提出Interaction-Aware Bench(IA-Bench)新基准,专门评估模型对机器人演示中被交互物体位置的定位能力。
◆ 验证了无需人工标注或验证数据,基于SPARC标注微调的模型即可在物体定位和指向基准上达到同规模模型的SOTA水平。
◆ 证明了基于SPARC标注训练的策略在杂乱、视觉模糊的真实场景中显著超越基线方法,具备实际落地价值。</td></tr>
<tr><td>2026-06-11</td><td>Proprioceptive-visual correspondence enables self-other distinction in humanoid robots<br><a href='http://arxiv.org/pdf/2606.13222'>论文</a> | <a href='https://euron-zc.github.io/humanoid-self-model/'>代码</a></td><td>这篇论文研究了人形机器人如何在共享工作空间中实现自我与他者的区分,这是社交智能的基础前提。作者提出通过本体感觉与视觉的对应关系,使机器人无需身份标签或运动学模型即可自主学习自我识别能力。一旦建立自我区分,系统便能引导构建预测性自我模型,将关节配置映射到三维身体占据空间,从而捕捉身体随动作的变化。该方法在涉及人类或形态相同机器人的多智能体场景中均能可靠识别自身,并支持目标到达、避碰运动规划以及人机动作重定向等下游任务,为机器人在共享物理环境中与他者协同行动提供了具身自我表征的可行路径。

核心创新点如下:

◆ 首次提出基于本体感觉与视觉对应关系的自我-他者区分机制,完全摆脱对身份标签和预设运动学模型的依赖,实现真正自监督的自我识别。

◆ 构建了从关节配置到三维身体占据空间的预测性自我模型,使机器人能够动态捕捉身体随动作变化的空间形态。

◆ 验证了该方法在多智能体复杂场景下的鲁棒性,即使面对形态完全相同的同类机器人,系统仍能准确识别自身。

◆ 将自我模型成功应用于目标到达、碰撞感知运动规划和人到机器人动作重定向等多种下游任务,展现了具身自我表征的实用价值与通用性。</td></tr>
<tr><td>2026-06-11</td><td>Computing Smooth Geodesics under Two-Sided Curvature Bounds with Applications to Robotics and Image Analysis<br><a href='http://arxiv.org/pdf/2606.14794'>论文</a></td><td>本文致力于解决计算物理与几何中极具挑战性的问题，即追踪受任意上下界曲率约束的极小路径。
◆提出了一种基于哈密顿-雅可比-贝尔曼偏微分方程框架的新型曲率有界测地线模型，通过强制曲率范围约束对极小路径实现强几何控制，保证路径平滑且曲率受限。
◆设计了针对哈密顿量及结合曲率边界的HJB PDE的离散化方案，为模型数值解的估计提供了高效求解器。
该模型在机器人路径规划和图像曲线结构追踪等应用中展现出强大的能力。
数值实验证明该曲率有界测地线模型是寻找满意路径的强大且鲁棒的工具。</td></tr>
<tr><td>2026-06-10</td><td>Fibration Trees: A Unified Approach to Multi-Robot Motion Planning<br><a href='http://arxiv.org/pdf/2606.12070'>论文</a></td><td>本文针对多机器人运动规划中投影与分解缺乏统一框架的问题，提出了纤维化树这一全新方法。纤维化树由状态空间节点和表示高维到低维投影的纤维化边构成，为高维规划提供了统一的拓扑结构。
◆通过将投影建模为纤维化，首次将顺序优先化、并行分解和任务空间投影统一在一个连贯的形式化框架中。
◆提出基于快速探索随机纤维化树的Fibration-RRT规划器，该算法不仅推广了商空间RRT和离散RRT的策略并支持任务空间投影，还被严格证明具有概率完备性。
在高达96自由度的32个场景中的实验表明，该算法能高效解决高维问题，确立了纤维化树作为多机器人运动规划统一框架的地位。</td></tr>
<tr><td>2026-06-10</td><td>Learning Unions of Convex Sets via Invertible Latent Decomposition for Path Planning<br><a href='http://arxiv.org/pdf/2606.12027'>论文</a></td><td>本文提出ILD框架，弥合了显式表示扩展性差与隐式表示缺乏硬保证之间的鸿沟。
◆联合学习可逆映射与潜空间中显式凸多面体的组合，在潜空间规划后将路径解码回原空间，兼顾了复杂几何的扩展性与显式约束的安全可行性。
◆提出能见度引导采样策略，有效保持凸集间的连通性以满足路径规划需求。
实验表明，该方法在2D至14自由度环境中实现了更广覆盖、更好连通性与更高规划成功率，且测试细化后零假阳性。
在14自由度双臂机械臂上，该方法实现了实时无碰撞规划，并能在真实部署中适应场景几何变化。</td></tr>
<tr><td>2026-06-10</td><td>MPPI-based Informative Trajectory Planning for Search and Capture of Drifting Targets with ASVs<br><a href='http://arxiv.org/pdf/2606.12019'>论文</a></td><td>本文针对自主水面航行器(ASV)在开放水域中搜索与捕获多个漂移目标(如海洋垃圾)的问题,提出了一种混合规划框架,通过结合长时域信息性轨迹规划与纯追踪制导控制,有效平衡了未知区域探索与已知目标跟踪之间的矛盾。该方法在动态环境下兼顾了搜索效率与捕获精度,并通过仿真实验和实船现场试验验证了其相较基线方法的优越性。

核心贡献与创新点如下:

◆ 提出了一种基于模型预测路径积分(MPPI)控制的时空信息性规划方法,利用采样式模型预测控制在长时域内直接优化连续轨迹,生成运动学层级的控制指令,克服了传统方法仅依赖简单制导行为和短期预测的局限。

◆ 设计了一种多目标代价函数,融合搜索、跟踪以及安全可行性约束,使规划器能够在漂移目标动态变化的环境中自适应地权衡探索与跟踪。

◆ 构建了搜索与捕获两阶段的混合规划框架,在拦截阶段切换至纯追踪制导控制器,实现对运动目标的物理捕获,提高了系统在实际任务中的完整性与实用性。

◆ 在仿真和真实ASV的现场试验中均验证了该方法的有效性,证明其性能优于所选基线规划方法,具备工程应用价值。</td></tr>
<tr><td>2026-06-10</td><td>G-MAPP: GPU-accelerated Multi-Agent Planning and Perception for Reactive Motion Generation<br><a href='http://arxiv.org/pdf/2606.12579'>论文</a></td><td>该论文提出了G-MAPP,一个基于GPU加速的多智能体规划与感知框架,旨在解决非结构化动态环境中实时反应式运动生成的挑战。论文指出现有方法的主要瓶颈在于高保真环境下规划模块的运行时性能,以及感知与规划模块之间的时序集成问题。作者通过GPU并行化加速世界建模和基于向量场的规划过程,实现了在保持高质量世界表征的前提下的高效运算。该框架在7自由度Franka Emika机器人上进行了真实世界实验验证,GPU版本相比CPU版本达到最高5倍加速,并能在复杂杂乱场景下成功避障。

核心创新点如下:

◆ 提出了GPU加速的世界建模方法,在不牺牲环境表征精度的情况下显著提升运算效率,解决了高保真感知与实时规划之间的矛盾。

◆ 设计了基于GPU并行化的向量场规划算法,通过并行状态探索实现准全局轨迹规划,相比CPU版本实现最高5倍的加速。

◆ 实现了感知-动作环路的紧耦合时序集成,使用现成的深度传感器即可在动态杂乱环境中完成实时反应式运动生成。

◆ 在真实7自由度Franka Emika机械臂上进行了定量与定性实验验证,证明该框架在简单和复杂物理场景下均能稳定避障。</td></tr>
<tr><td>2026-06-10</td><td>Foresight: Iterative Reasoning About Clues that Matter for Navigation<br><a href='http://arxiv.org/pdf/2606.12550'>论文</a></td><td>论文《Foresight: Iterative Reasoning About Clues that Matter for Navigation》针对开放世界中基于稀疏语言指令的无地图导航问题,提出了一种测试时迭代推理框架。该方法利用预训练视觉语言模型(VLM)发现与指令相关的新型环境线索(如坡道、标识、绕行路径等),并通过&quot;提议-批判&quot;循环不断优化运动规划,在6个真实环境中相较最先进基线平均任务成功率提升37%,每次任务干预次数减少52%,并能在Jetson AGX Orin上实时运行。

◆ 提出Foresight测试时推理框架,让微调后的VLM在图像空间中交替执行运动规划提议与基于语言目标和视觉上下文的批判,实现执行前的迭代式规划精炼。

◆ 突破以往方法依赖已知导航因素和闭集类别的局限,利用VLM发现开放集的、与指令相关的新颖线索。

◆ 将线索识别与运动规划深度耦合,捕获依赖于具体规划的线索,而非传统方法中规划前一次性识别线索。

◆ 通过人类反馈学习奖励模型,并在&quot;规划-批判&quot;循环中使用强化学习对VLM进行后训练,使批判与精炼过程对齐开放集的行为偏好。

◆ 在离线评估与6个真实世界环境中验证了方法的有效性,且具备实时部署能力。</td></tr>
<tr><td>2026-06-09</td><td>Combining Reinforcement Learning with Arc-search Interior-Point Method for Path Planning<br><a href='http://arxiv.org/pdf/2606.07920'>论文</a></td><td>本文针对含障碍物环境下的非线性和非凸路径规划问题，提出了一种结合强化学习与弧搜索内点法的新框架。该框架的核心贡献在于有效克服了单一方法的局限性，实现了两者的优势互补。
◆创新性地将强化学习的实时决策能力与弧搜索内点法的寻优性能相融合，解决了机器学习路径非最优与优化方法实时性差的问题。
◆利用强化学习在无需高保真模型的情况下快速生成可行路径，满足系统的实时性要求。
◆引入弧搜索内点法对生成的路径进行进一步优化，确保路径在长度或时间等性能指标上达到最优或近最优。
仿真结果表明，该方法显著提升了路径规划的综合性能。</td></tr>
<tr><td>2026-06-09</td><td>Diffusion Forcing Planner: History-Annealed Planning with Time-Dependent Guidance for Autonomous Driving<br><a href='http://arxiv.org/pdf/2606.11019'>论文</a></td><td>该论文提出Diffusion Forcing Planner框架，旨在解决基于学习的运动规划器在自动驾驶中因帧间扰动累积导致的时间不一致与轨迹不稳定问题。现有方法将历史作为静态条件易使模型盲目复制历史而无法适应新环境，DFP则通过历史引导控制来解决此局限。
◆提出异构联合扩散过程，将轨迹分解为历史、当前与未来段并赋予独立噪声水平，对历史与未来段进行联合去噪。
◆引入时间依赖的引导机制，在推理时应用无分类器引导，利用退火历史以可控方式引导未来轨迹采样。
在nuPlan数据集上的闭环评估与消融实验表明，DFP在复杂驾驶场景中不仅取得了极具竞争力的性能，还能生成连续、稳定且可控的运动规划。</td></tr>
<tr><td>2026-06-09</td><td>Multi-UAV Active Sensing with Information Gain-based Planning and Belief Fusion<br><a href='http://arxiv.org/pdf/2606.10986'>论文</a></td><td>本文在真实精准农业场景中验证了一个多无人机主动感知框架，用于概率二元地形映射。
◆提出基于因子图构建概率信念地图以有效表征空间依赖关系。
◆引入基于信息增益的启发式路径规划引导无人机决策，其性能优于随机游走和扫描覆盖基线。
◆系统评估了多无人机信息共享的空间权重与融合规则，发现简单权重比自适应权重更鲁棒，且贝叶斯等融合规则性能最优。
实验表明该规划方法能更有效降低地图熵与误差，同时更宽视野提升了真实环境的覆盖与精度。</td></tr>
<tr><td>2026-06-09</td><td>LieIPM: Lie Group Interior Point Method for Direct Trajectory Optimization of Rigid Bodies<br><a href='http://arxiv.org/pdf/2606.10579'>论文</a></td><td>本文提出了一种直接在矩阵李群上进行刚体约束轨迹优化的结构感知框架，解决了传统欧式空间优化器忽略流形结构而导致的奇异性与病态问题。
◆基于李群结构的二阶刚体模型，实现了高效的牛顿型更新并保留了底层几何特性。
◆提出线搜索李群内点法以直接处理流形上的约束问题。
◆利用李群变分积分器实例化该框架，并推导出利用群对称性的闭式内蕴导数。
该方法从根本上保留了旋转运动的拓扑结构并避免了奇异性，数值实验证明其比现有方法具备更强的鲁棒性与更快的收敛速度。</td></tr>
<tr><td>2026-06-09</td><td>A Modular Dual-Camera Pipeline for Micro-Inspection Using Aerial Robots<br><a href='http://arxiv.org/pdf/2606.11419'>论文</a> | <a href='https://github.com/SaxionMechatronics/aerial_micro_inspection'>代码</a></td><td>本文提出了一种名为aerial_micro_inspection的模块化双摄像头无人机微检管道，解决了传统巡检需近距离飞行、依赖先验几何信息及易受干扰丢失目标的问题。
◆提出了双摄像头协同架构，利用广角立体导航相机获取目标表面、估计距离并分区，结合变焦云台检查相机在安全距离外捕捉微小细节。
◆设计了基于视觉的反馈回路，在检查相机对大表面进行分区扫描时，有效补偿无人机运动带来的干扰，提升了窄视角下的覆盖鲁棒性。
◆构建了基于ROS 2的开源模块化系统，无需目标先验信息，只需替换表面分割和微目标检测的模型权重即可快速适配不同应用场景。
仿真与真实实验表明，该管道在干扰下具有鲁棒的覆盖率，并在树木害虫检测和温室昆虫高精度成像中表现出色。</td></tr>
<tr><td>2026-06-08</td><td>Safe Polytope-in-Polytope Motion Planning and Control with Control Barrier Functions<br><a href='http://arxiv.org/pdf/2606.09719'>论文</a></td><td>本文提出了一种针对多面体外形机器人的安全局部运动规划与控制方法，确保机器人始终位于持续更新的凸自由空间区域内，避免了将机器人简化为点或圆的保守性。
◆将包含条件表述为模型预测控制器中的离散时间控制障碍函数约束。
◆安全约束的数量仅取决于局部自由空间几何与机器人形状，而非障碍物数量，且无需进行障碍物检测或分割。
◆与传统基于多面体的避障方法相比，该方法的计算时间大幅缩减，最高可达91倍。
该方法在仿真和硬件实验中均得到验证，在嵌入式计算机上实现了10赫兹的安全实时运动规划与控制，并能有效应对动态障碍物。</td></tr>
<tr><td>2026-06-08</td><td>Motion planning for hundreds of floating robots<br><a href='http://arxiv.org/pdf/2606.09620'>论文</a></td><td>本文针对大规模机器人舰队防碰撞运动规划中因智能体强耦合导致的计算困难，提出了一种面向水面全向漂浮机器人的可扩展规划框架。该框架能够在分钟级过渡和数千时间步下，根据稀疏关键帧在数秒内快速生成轨迹。
◆基于初始化构建碰撞图，将强耦合问题分解为交互簇，并对其进行独立且并行的求解，有效提升了计算扩展性。
◆引入鲁棒性机制处理常见的解耦病理问题，确保了复杂情况下的规划成功率。
该方法在多达500个机器人的仿真中得到了验证，并成功应用于苏黎世湖24艘船只及2025年威尼斯双年展的真实世界演示。</td></tr>
<tr><td>2026-06-08</td><td>MASS: Deep Research for Social Sciences with Memory-Augmented Social Simulation<br><a href='http://arxiv.org/pdf/2606.09198'>论文</a></td><td>本文提出名为MASS的记忆增强型社会模拟新范式，解决了现有大模型深度研究智能体在社会科学领域缺乏洞察力与创造力的问题。该范式通过高真实度且面向研究的社会模拟，增强了智能体生成研究的创造力与实证基础。
◆引入带有多层次社会规范约束的动态目标-路径规划，以有效引导模拟过程。
◆构建多学科行为数据集，用于实现智能体记忆的冷启动。
◆提出受艾宾浩斯曲线启发的结构化遗忘机制，确保模拟真实性。
实验结果证明该方法有效，其整体生成质量较基础大模型提升6.81%，洞察力较强基线提升17.19%。</td></tr>
<tr><td>2026-06-08</td><td>Trajectory Optimization in Single and Dual-UAV Bearing-Only Target Localization<br><a href='http://arxiv.org/pdf/2606.09188'>论文</a></td><td>本文提出一种针对单和双无人机仅测角目标定位的轨迹优化方法，利用费舍尔信息矩阵将几何构型与飞行器机动性动态融合到优化框架中。
◆提出谱加权FIM目标函数，在退化构型附近提供更优的梯度动态，使规划器能迅速脱离不良观测条件。
◆在双无人机场景中引入交角正弦项，通过改善视线交角来优化三角测量几何，从而有效防止轨迹聚合。
◆提出结合运动模型约束与粒子归一化的改进粒子群优化算法，确保轨迹的物理可行性并提升与目标函数的兼容性。
仿真结果表明，该方法在单和双无人机场景下分别将中位定位误差降低了99.21%和69.70%，在远距离机动目标的长时定位中表现卓越。</td></tr>
<tr><td>2026-06-08</td><td>Deterministic versus Stochastic Optimization for Joint Path Planning and Dynamic Time Splitting in Multiple-UAV-Cached IoT Networks<br><a href='http://arxiv.org/pdf/2606.09014'>论文</a></td><td>本文研究了配备反向散射与缓存技术的多无人机无线供电物联网网络，旨在联合优化动态时间分割比、轨迹和发射功率以最大化总吞吐量。针对该非凸优化问题的挑战，论文的核心创新点如下：
◆提出基于块坐标下降法的交替优化算法，并利用KKT条件推导出最优动态时间分割比的闭式表达式，大幅减少了计算时间。
◆引入采用单点交叉、值变异和排序选择的遗传算法，全面评估并提供了该问题的随机优化求解方案。
数值结果表明，这两种算法较基准方法实现了至少31%的吞吐量提升且计算时间更短。这充分验证了所提方案在缓存使能的无人机辅助物联网网络中的性能增益与实际可行性。</td></tr>
<tr><td>2026-06-08</td><td>Submodular Optimization with Applications to Decision and Control<br><a href='http://arxiv.org/pdf/2606.10192'>论文</a></td><td>本文综述了次模优化在决策与控制领域的理论、算法及应用，为子集选择问题提供了统一的组合框架。
◆系统梳理了次模函数的结构特性、实际约束条件及单调与非单调最大化的最新近似算法与理论界限。
◆强调实用且具近似保证的贪心算法，并通过曲率和次模比实现了依赖实例的算法精细化改进。
◆明确了典型控制目标的次模性，指出可控性格拉姆矩阵的对数行列式等具有次模性，而稳态卡尔曼滤波误差等则不具备。
此外，文章还探讨了传感器调度与多智能体协调等应用，并指出了跨领域的未来开放研究方向。</td></tr>
<tr><td>2026-06-08</td><td>FlexPath: Learned Semantic Path Priors for Image-Based Planning<br><a href='http://arxiv.org/pdf/2606.10167'>论文</a> | <a href='https://github.com/FraunhoferIVI/FlexPath'>代码</a></td><td>该论文提出了FlexPath，一个两阶段的路径规划框架，将路径的可行性与偏好解耦，解决了现有学习型规划器局限于最短路径目标的问题。
◆提出两阶段解耦架构，第一阶段利用模仿学习从视觉地图中获取与任务无关的可行路径空间先验。
◆引入可微路径形状目标，在第二阶段仅需在目标层面进行高效适应，无需重新学习路径结构，单一预训练模型即可适配多种规划标准。
实验表明，在最短路径规划上，该方法比现有最优方法减少14.3%的搜索量并找到更低成本路径，同时在三个未见领域展现出强零样本泛化能力。
在障碍物间隙任务中实现96.8%完全避障与低搜索成本，还可扩展至语义避障和航路点引导，且推理时与经典规划器兼容。</td></tr>
<tr><td>2026-06-08</td><td>Uncertainty-Aware Motion Planning for Autonomous Driving in Mixed Traffic Environment<br><a href='http://arxiv.org/pdf/2606.09958'>论文</a></td><td>这篇论文针对混合交通环境下自动驾驶运动规划问题,提出了一种考虑人类意图预测不确定性的强化学习方法UAMP。现有基于强化学习的方法通常将预测的人类意图作为确定性状态直接纳入观测,忽略了由行为多样性、感知噪声和部分可观测性带来的固有不确定性,容易导致不安全的决策。UAMP通过量化交互条件下的意图不确定性,并在价值学习中校正由此引发的偏差,从而在保持交通效率的同时显著提升了行驶安全性和舒适性。

◆ 提出了面向混合交通的不确定性感知运动规划框架UAMP,首次将人类意图预测的不确定性显式建模并融入自动驾驶决策。

◆ 设计了邻近感知的不确定性估计器,量化交互条件下的意图不确定性,并构建周围人驾车辆的联合意图分布。

◆ 提出不确定性校准价值学习方法UCVL,针对将不确定意图直接纳入观测所导致的价值函数学习偏差进行修正。

◆ 在多种混合交通场景下的大量实验表明,该方法相比现有方法在安全性和舒适性上有显著提升,同时保持了通行效率。</td></tr>
<tr><td>2026-06-07</td><td>Video2Sim2Real: Full-Stack Autonomous Dexterous Skill Acquisition from a Single Human Video<br><a href='http://arxiv.org/pdf/2606.08828'>论文</a></td><td>本文提出了Video2Sim2Real全栈框架，实现了从单个人类视频中自主获取机器人灵巧操作技能，克服了感知误差与具身鸿沟的挑战。
◆提出以物体为中心的关键帧优化策略，在模拟器中利用物体信息优化机器人配置作为锚点来细化运动轨迹，确保操作对环境产生预期影响。
◆设计了解耦的虚实迁移策略，通过模仿学习从含噪点云重校准配置以应对感知误差，并结合残差强化学习进行局部手指适应以克服交互动态变化。
◆引入碰撞感知的运动规划模块，使习得的技能能够空间泛化至未见过的物体配置。
实验表明该框架在多项任务中显著提升了模拟与真实环境下的成功率、安全性与轨迹连贯性。</td></tr>
<tr><td>2026-06-07</td><td>Real-Time and Accurate Collision-Free Teleoperation via Differentiable Constraint-Based Trajectory Planning<br><a href='http://arxiv.org/pdf/2606.08725'>论文</a></td><td>遥操作中仅控制末端执行器易导致机械臂自碰撞与环境碰撞，而现有的最优控制轨迹规划方法常采用球体近似降低几何精度，或近似导数导致收敛慢及计算耗时增加。本文提出了一种基于可微约束轨迹规划的实时无碰撞遥操作方法来解决上述问题。
◆将基于凸优化对偶性的可微避碰约束新公式引入遥操作场景。
◆采用胶囊体近似机械臂并用多面体表示环境，在保持可微性的同时显著提升了障碍物建模的几何精度。
仿真和真实UR5e机械臂实验表明，该方法计算时间更短，实现了更平滑准确的无碰撞遥操作。</td></tr>
<tr><td>2026-06-07</td><td>Towards End to End Motion Planning and Execution for Autonomous Underwater Vehicles Using Reinforcement Learning<br><a href='http://arxiv.org/pdf/2606.08513'>论文</a></td><td>该论文提出一种端到端深度强化学习方法，直接将原始传感器数据映射为水下自主航行器的推进器指令，以替代传统复杂的工程流水线。
◆提出分层强化学习架构，将任务分解为两个马尔可夫决策过程，即处理视觉声纳数据生成子目标的高层策略与将子目标转为推进器指令的低层策略。
◆在训练框架上进行针对性设计，高层策略采用基于先验演示的强化学习与改进的SERL框架，低层策略结合软演员评论家算法与事后经验回放。
在高保真模拟器中，该方法实现了成功避障，且轨迹长度与RRT星基线仅相差百分之四至百分之六。
此外，该策略对模拟传感器噪声和低能见度展现出强鲁棒性，尽管在未见过的复杂障碍物形状上存在泛化局限。
该研究最终证明了在极低计算硬件下，样本高效的端到端强化学习在水下导航任务中的巨大潜力。</td></tr>
<tr><td>2026-06-06</td><td>SIMPLE: Simulation-Based Policy Learning and Evaluation for Humanoid Loco-manipulation<br><a href='http://arxiv.org/pdf/2606.08278'>论文</a></td><td>本文提出了SIMPLE，一个用于人形机器人全身移动操作策略学习与评估的统一仿真试验台，解决了该领域缺乏可扩展和可复现基准的问题。
◆该框架将MuJoCo的精确接触动力学与IsaacSim的照片级真实渲染相结合，构建了包含60项任务、50个室内场景和超千种物体的大规模环境。
◆集成了基于运动规划的自动化轨迹生成和低延迟VR遥操作两条数据采集流水线，实现了高效且可扩展的数据收集。
◆大规模集成并基准测试了包括轻量级模仿网络、视觉语言动作模型和世界动作模型在内的主流人形策略。
实验证明仿真与真实世界性能高度相关，且在SIMPLE中训练的策略可零样本迁移至物理人形机器人，为人形机器人研究提供了坚实基础。</td></tr>
<tr><td>2026-06-06</td><td>Learning Predictive Control with Deep Koopman Operators for Autonomous Vehicle Motion Planning<br><a href='http://arxiv.org/pdf/2606.08136'>论文</a></td><td>本文针对自动驾驶运动规划中传统模型预测控制实时性差及强化学习缺乏控制理论结构的问题，提出了基于深度Koopman算子的学习预测控制框架。
◆提出深度Koopman预测器，以数据驱动方式将非线性不确定车辆动力学提升至可解释的线性可观空间。
◆通过滚动时域Actor-Critic学习，在每个预测区间生成闭环状态反馈策略，突破了传统MPC仅计算开环序列的局限。
◆针对非凸环境约束，构建障碍物凸局部代理表示并定义势场函数，将其与梯度直接嵌入Actor-Critic结构实现安全感知策略学习。
仿真与实车实验表明，该框架在多样避障场景中的安全性、计算效率和舒适性均优于基准方法。</td></tr>
<tr><td>2026-06-05</td><td>Lane Change Trajectory Planning for Personalized Driving Comfort and Mobility Efficiency<br><a href='http://arxiv.org/pdf/2606.06805'>论文</a></td><td>该论文针对换道轨迹规划中纵横向运动耦合及驾驶员个性化差异显著的问题,提出了一种神经网络驱动的轨迹规划方法,将三阶多项式轨迹生成器与学习模块相结合,能够在多样化驾驶条件下推断最优轨迹参数,从而同时兼顾驾驶舒适性与通行效率。通过代表性案例和蒙特卡洛仿真验证,该规划器在个性化数据充足时可实现个性化的舒适性与机动效率,在数据不足或不可获取的条件下也能保证轨迹的可行性。

核心贡献与创新点如下:

◆ 提出了融合三阶多项式轨迹生成器与神经网络学习模块的换道轨迹规划框架,实现了纵横向耦合运动的个性化参数推断。

◆ 设计了共享主干加双分支头部的网络结构,一个分支负责保证全工况下的基础可行性,另一个分支负责捕获驾驶员对舒适性或通行效率的个性化偏好。

◆ 引入基于误差胜出逻辑回归的统计门控机制,实现头部之间的自适应切换,使规划器能够根据驾驶情境上下文动态选择合适的输出分支。

◆ 构建了在个性化数据稀缺或不可访问时仍能保证轨迹可行性的兜底机制,提升了方法在真实场景中的鲁棒性与适用性。

◆ 通过代表性案例与蒙特卡洛仿真系统验证了该方法在个性化舒适性、机动效率和工况适应性方面的综合优势。</td></tr>
<tr><td>2026-06-05</td><td>Path Planning Using Deep Deterministic Policy Gradient: A Reinforcement Learning Approach<br><a href='http://arxiv.org/pdf/2606.07855'>论文</a></td><td>本文针对威胁环境下自动驾驶车辆路径规划计算慢的问题，提出了一种基于深度确定性策略梯度的强化学习方法。该方法将威胁建模为圆形禁区，通过试错训练使智能体学习从当前状态到可行动作的直接映射以安全抵达目标。
◆设计了包含终点吸引场、障碍物排斥场和控制能量惩罚的三部分奖励函数，有效引导智能体规划出倾向直线的安全路径。
◆通过训练寻找能保证安全到达目的地的最大起始点集合，从而为任务规划提供关键的事前可行性评估信息。
◆与传统伪谱最优控制方法对比表明，该方法在生成有效路径的同时计算速度显著更快，更适合实时应用场景。</td></tr>
<tr><td>2026-06-04</td><td>Waypoints Matter: A Systematic Study for Sampling-Based Trajectory Planning<br><a href='http://arxiv.org/pdf/2606.06366'>论文</a></td><td>本文首次将采样式轨迹规划中的路标点放置视为一等设计变量，系统研究了其对规划器性能的直接影响。在固定轨迹基元和候选预算的条件下，研究跨越449种配置和五种地图，对比了三种路标点放置策略。
◆揭示了路标点标称间距是驱动规划性能的核心因素，仅放置方式的差异就会导致规划可靠性产生巨大变化。
◆发现调优后的均匀采样性能优于RDP*变体，且本文提出的曲率条件分配策略在复杂道路下具有稳定优势。
研究结论指出间距应作为首要调优参数，几何感知策略仅适用于曲率密集且可行性受限的特殊走廊区域。</td></tr>
<tr><td>2026-06-04</td><td>3D Underwater Path Planning via Generative Flow Field Surrogates<br><a href='http://arxiv.org/pdf/2606.06077'>论文</a></td><td>该论文针对自主水下航行器(AUV)在前进母船尾部进行发射与回收时需穿越复杂三维螺旋桨尾流的路径规划难题,提出用条件生成对抗网络(cGAN)替代高保真RANS CFD仿真,从而在保证流场精度的同时满足机载实时计算需求。作者将生成式流场代理模型嵌入三维能量加权A*路径规划框架,并在四种环境感知层级(均匀流、真实CFD、PatchGAN、2D3DGAN-SA)下对550种流况、共19800条轨迹进行了系统性基准测试,验证了生成模型在能量节省与高速尾流核心规避方面的实用价值。

◆ 首次将两种cGAN架构(正则化PatchGAN和带自注意力的2D3DGAN)作为RANS CFD的即插即用代理,集成进三维水下路径规划框架。
◆ 提出分层生成管线,仅依靠标量工况输入即可合成完整的128³体素三维流场,推理时间仅28-146微秒,相较RANS的数小时计算实现数量级加速。
◆ 设计三维能量加权A*规划器,可直接利用生成的流场体积进行能量最优路径搜索,适配边缘计算设备部署。
◆ 首次系统量化了cGAN预测流场在三维海事机器人路径规划下游任务中的实际价值:完整CFD感知可降低5.7-12.5%能耗、减少最高77.8%的高速尾流核心穿越,而cGAN代理可恢复其中约45-60%的收益。
◆ 建立了覆盖550种流况、19800条独立轨迹的大规模对比评测基准,为生成式流场模型在水下机器人规划中的应用提供了量化证据。</td></tr>
<tr><td>2026-06-04</td><td>Sample-efficient Low-level Motion Planning for Robotic Manipulation Tasks via Zero-shot Transfer Learning<br><a href='http://arxiv.org/pdf/2606.06041'>论文</a></td><td>本文针对复杂机器人操作任务中样本高效的交叉熵方法性能受限的问题，提出了一种结合零样本迁移学习的iCEM+TL框架。
◆提出iCEM+TL框架，通过将简单上游任务的关键iCEM参数迁移至复杂下游任务，实现知识的高效重用与零样本引导规划。
◆引入奖励重设计机制，针对堆叠和货架放置等复杂操作进行任务分解，优化了特定任务的奖励函数以提升规划性能。
仿真实验表明，该框架在复杂场景下的任务成功率最高提升了23%。
在真实Franka Emika机器人堆叠任务上的进一步验证，证明了该方法的实际部署可行性。</td></tr>
<tr><td>2026-06-04</td><td>IDDMBSE: Integrating Data-Driven and Model-Based Systems Engineering for Trusted Autonomous Cyber-Physical Systems<br><a href='http://arxiv.org/pdf/2606.06727'>论文</a></td><td>该论文针对自主信息物理系统(CPS)开发中基于模型的系统工程(MBSE)与数据驱动的机器学习/人工智能方法长期割裂的问题,提出了一种名为IDDMBSE的集成方法论。该方法在传统MBSE的V型流程每一步骤中嵌入数据驱动闭环,以SysML、自主性栈以及混合式架构为支撑,并通过一套开源工具链加以实现,最后在受争议地形的Isaac Sim测试场中以可信自主地面机器人为案例验证了全生命周期的有效性。

核心贡献与创新点如下:

◆ 首次提出IDDMBSE方法论,在严谨的MBSE V型流程的每个环节原生融入数据驱动循环,填补了MBSE与ML/AI在系统工程层面缺乏统一方法的空白。

◆ 开发了PERFECT工具,可将SysML系统架构自动映射为可执行的ROS自主性栈,实现大规模性能评估。

◆ 提出TRADES-X工具,将设计空间探索分解为&quot;基于模型的优化&quot;与&quot;数据驱动评估&quot;两阶段,实现混合式权衡分析。

◆ 构建了VERITAS统一保证工作流,将形式化验证、数据驱动验证与运行时验证整合到单一框架中。

◆ 以可信自主地面机器人为完整案例,涵盖传感器选型、风险敏感路径规划、行为树任务验证、基于共形预测的鲁棒感知及多机器人协同保证等环节,并开源了配套的Isaac Sim测试场。

◆ 展望了基于SysML v2/KerML重构IDDMBSE的路径,以实现语言原生的可组合性与更紧密的ML/AI集成。</td></tr>
<tr><td>2026-06-03</td><td>DiffSlack: Learning under Nonlinear Inequality Constraints via Learnable Slack Variables<br><a href='http://arxiv.org/pdf/2606.05247'>论文</a></td><td>本文提出DiffSlack可微投影层，解决神经网络中非线性不等式约束难以强制执行的问题。
◆将不等式转化为带可学习松弛变量的等式，并作为网络输出预测，为阻尼高斯-牛顿投影提供数据驱动的热启动。
◆设计可微投影层，将原始预测映射至增广可行流形，同时保持端到端可微性。
◆引入两阶段课程学习策略，稳定训练并提升约束满足能力。
在含200个非线性约束的路径规划中，该方法在同等预算下取得更高成功率与约束满足度，并降低对监督质量的敏感性。
实车实验进一步验证了其生成轨迹的可执行性与工程实用价值。</td></tr>
<tr><td>2026-06-03</td><td>Joint 3D Trajectory and Power Allocation for HAPs-UAV Bistatic ISARAC in Low-Altitude Networks<br><a href='http://arxiv.org/pdf/2606.04600'>论文</a></td><td>本论文提出了一种高海拔平台与无人机协同的双基地集成合成孔径雷达与通信系统架构，其中HAPs负责广域通信与波形发射，UAV利用机动性近距离接收回波以实现高分辨率SAR成像。核心贡献在于联合优化了UAV的三维飞行轨迹与系统的功率分配，以最大化地面用户的总通信速率，同时满足SAR成像的信噪比与分辨率约束、总能量预算以及无人机动力学限制。为解决这一非凸问题，作者开发了交替优化框架：功率分配子问题可得到闭式水填充解，而轨迹优化子问题则通过逐次凸近似和凸差规划高效求解。仿真结果证实了该方法在低空网络中同时保障连续通信覆盖与高精度感知的有效性。

◆ 创新性地将HAPs与UAV结合构成双基地ISARAC系统，兼顾广域覆盖与近距离高分辨率感知优势。
◆ 首次联合考虑通信速率最大化与SAR成像质量约束，建立了三维轨迹与功率分配的协同优化模型。
◆ 提出基于交替优化、逐次凸近似和凸差规划的求解算法，功率分配获得闭式解，显著降低了计算复杂度。</td></tr>
<tr><td>2026-06-03</td><td>Discussion on the Physics Problem of a Boat Crossing a River<br><a href='http://arxiv.org/pdf/2606.04515'>论文</a></td><td>该论文研究了非均匀流速下的船只过河问题，构建了恒定水流、线性分布和偶次幂函数分布三种流速模型。
◆构建了包含偶次幂可调参数的多模型分析框架，有效模拟真实河流复杂的流速分布场景。
◆结合矢量叠加与微积分方法，推导出固定航向角下船只空间轨迹的解析表达式。
◆引入拉格朗日乘数法构建约束优化模型，求得了满足到达正对岸边界条件的最短时间最优航向角解析解。
这些研究成果为内河船舶智能导航系统的路径规划提供了重要的理论支持。</td></tr>
<tr><td>2026-06-03</td><td>Think Fast and Far: Long-Horizon Online POMDP Planning via Rapid State Sampling<br><a href='http://arxiv.org/pdf/2606.04355'>论文</a> | <a href='https://github.com/RDLLab/ROPRAS3}'>代码</a></td><td>本文提出了一种名为ROP-RAS3的新型近似在线POMDP求解器，旨在解决长视野部分可观察马尔可夫决策过程难以求解的问题。
◆引入极快的基于采样的运动规划技术来采样状态空间并在线生成多样化的宏动作，利用这些宏动作引导信念空间采样并推断高质量策略，免去了现代求解器必须穷举动作空间的根本限制。
◆在理论收敛性上，该方法收敛到近优参考解的速率取决于采样动作的数量而非动作空间的大小，从而大幅提升了规划效率。
实验表明，在长达3000步前瞻和35维状态空间的复杂混合空间长视野POMDP中，该方法的成功率成倍超越其他最先进方法。
此外，该方法的实用性也在真实物理机器人演示中得到了成功验证。</td></tr>
<tr><td>2026-06-02</td><td>Multi-Agent Next-Best-View Optimization for Risk-Averse Planning<br><a href='http://arxiv.org/pdf/2606.04158'>论文</a></td><td>本文提出了一种分布式风险感知多智能体下一最佳视角框架，用于未知环境下的安全路径规划，克服了集中式方法通信开销大与可扩展性差的缺陷。
◆构建了基于局部三维高斯溅射地图的分布式协作机制，通过共识ADMM求解器联合最大化轨迹遮罩区域的预期信息增益。
◆设计了极低通信开销的交互策略，各机器人仅需交换候选视角、轨迹描述符与标量信息增益值，无需共享原始传感器数据。
◆提出了基于平均风险价值的碰撞风险建模方法，利用局部地图评估风险并动态调整遮罩半径与路径评分，确保轨迹安全性。
◆多规模团队实验表明，该分布式方案在地图质量与安全性能上逼近集中式基线，同时将通信量降低了数个数量级。</td></tr>
<tr><td>2026-06-02</td><td>AgenticDiffusion: Agentic Diffusion-based Path Planning for Vision-Based UAV Navigation<br><a href='http://arxiv.org/pdf/2606.04111'>论文</a></td><td>本文提出AgenticDiffusion框架，解决了室内无人机导航中单视角观察导致的遮挡和全局场景推理受限问题。
◆提出了多视角无人机导航框架，将语言引导推理、开放词汇目标定位、视觉扩散规划与NMPC控制整合于统一管线。
◆设计了基于第一人称视角和俯视图的自适应视角选择机制，在轨迹执行前确定最具信息量的视角并生成任务计划。
◆开发了视角特异性的扩散规划器，利用互补视角生成轨迹，减少了重复目标探索并提升了复杂室内环境下的导航效率。
实验表明，该框架在四类真实场景的四十次试验中，实现了百分之八十的整体任务成功率和百分之百的轨迹生成成功率。</td></tr>
<tr><td>2026-06-02</td><td>Neural Navigation Functions for Zero-Shot Generalizable Motion Planning<br><a href='http://arxiv.org/pdf/2606.03756'>论文</a></td><td>本文提出了神经导航函数，这是一种能够在未知环境几何中实现零样本迁移的学习型反应式导航函数。
◆将数据驱动的适应性与结构化椭圆规划器结合，在学习目标的同时通过构造保留规划器结构。
◆将内在拉普拉斯特征映射为局部偏微分方程系数，通过求解边界值问题生成全局一致的值函数。
◆通过构造保证生成的策略无碰撞、具有单调下降性，且在目标处具有全局最小值。
◆在任何参数设置下，该方法都具有线性可解的最优控制解释。
实验表明，该方法实现了强大的零样本迁移，性能比直接预测值函数的规划器提升了高达五倍。</td></tr>
<tr><td>2026-06-02</td><td>SPADE: Sketch-guided Path Planning Augmented with Diffusion Experts<br><a href='http://arxiv.org/pdf/2606.03512'>论文</a></td><td>针对现有模仿学习路径规划方法在未见环境中泛化能力有限及演示收集鲁棒性低的问题，本文提出了SPADE框架。
◆基于ROS 2构建了一款全面改进的标注工具，提升了专家演示数据收集的鲁棒性。
◆提出了一种新颖的训练策略，将基于扩散模型的增强技术集成到基线行为克隆模型中。
实验表明，该方法的绝对位姿误差和弗雷歇特起始距离分别降低了39.1%和33.5%，且可训练参数减少了93.8%。
此外，该框架在实现扩散级别泛化能力的同时，成功保留了最先进模型的实时边缘计算特性。</td></tr>
<tr><td>2026-06-02</td><td>Grasp-Then-Plan with Failure Attribution: A Closed Two-Stage Framework for Precise and Generalizable Robotic Manipulation<br><a href='http://arxiv.org/pdf/2606.03385'>论文</a></td><td>本文针对机器人操作中抓取与运动规划耦合导致失败源模糊和低效试错的问题，提出了GTP-FA闭环两阶段操作框架。
◆创新点一是学习失败归因模型，能泛化至未见抓取并生成稳定的失败模式分布以指导诊断优化。
◆创新点二是在抓取模块注入任务级先验和风险惩罚，抑制不稳定或任务不兼容的抓取候选。
◆创新点三是在规划模块针对高风险初始状态进行定向数据收集和微调，解决真正的规划瓶颈。
仿真与真实实验表明，该框架在强化学习、模仿学习、扩散策略和VLA等多种基线设置下均显著提升了任务成功率。</td></tr>
<tr><td>2026-06-02</td><td>Bridging Predictive Uncertainty and Safe Action: Sample-Conditioned Differentiable Planning for Autonomous Driving<br><a href='http://arxiv.org/pdf/2606.03296'>论文</a></td><td>本文提出一种新颖的样本条件可微分规划框架，成功弥合了高表达不确定性建模与可解释安全运动规划之间的脱节。
◆提出基于条件扩散模型的样本条件规划机制，将生成的多样化未来轨迹样本直接输入可微分规划器，避免压缩为单一结果或依赖黑盒架构。
◆引入经验条件风险价值尾风险约束显式缓解预测不确定性，使规划器能优化出对罕见且安全关键交互具有鲁棒性的物理可解释轨迹。
◆提出场景上下文的有向图表示方法，显著提升了预测效果与计算效率。
在Waymo和Argoverse 2数据集上的广泛开闭环评估表明，该框架在安全性、效率和舒适度上均显著超越现有基线。</td></tr>
<tr><td>2026-06-01</td><td>Evaluating Real-World Generalizability of Algorithm Selection Models<br><a href='http://arxiv.org/pdf/2606.02016'>论文</a></td><td>本文系统性地研究了算法选择模型在合成与真实世界优化景观之间的泛化能力。研究跨越了学术基准与实际应用场景，揭示了现有模型在跨域迁移时的真实表现。
◆构建了涵盖BBOB和CEC学术基准以及机器人轨迹优化和无人机路径规划等真实问题集的综合评估框架。
◆通过系统的跨基准评估，深入分析了AS模型的跨域迁移表现，明确识别出泛化成功与失效的具体场景。
◆揭示了当前AS方法在现实特定领域应用中面临的挑战，为开发更可靠且广泛适用的真实世界优化AS系统提供了重要指导。</td></tr>
<tr><td>2026-06-01</td><td>Motion Planning in Dynamic Environments: A Survey from Classical to Modern Methods<br><a href='http://arxiv.org/pdf/2606.02677'>论文</a></td><td>本文对2015至2025年间138篇动态环境运动规划文献进行了全面综述，弥补了现有研究多关注静态环境的不足。
◆系统梳理了从经典到学习的各类方法，将其划分为采样、图搜索、模型预测控制、学习及传统局部规划五大类别。
◆深入探讨了动态感知在运动规划中的关键作用，涵盖了利用相机、激光雷达和事件传感器检测与建模移动障碍物的技术。
◆重点剖析了动态环境特有的挑战，如预测不确定性、人机交互和机器人冻结问题，并详细评估了各方法的原理与优劣。
该综述为研究人员构建了理解动态环境下运动规划方法的结构化参考框架。</td></tr>
<tr><td>2026-05-31</td><td>Mean-Field Diffuser: Scaling Offline MARL to Thousands of Agents<br><a href='http://arxiv.org/pdf/2605.30190'>论文</a></td><td>这篇论文针对扩散式规划在多智能体离线强化学习中因联合轨迹空间维度爆炸而难以扩展的问题,提出了MF-Diffuser框架,将轨迹规划提升至轨迹分布的Wasserstein空间,利用混沌传播性质,仅用少量代表性智能体即可刻画整个种群的动态,从而支撑千级以上规模的离线多智能体强化学习。论文同时建立了端到端的次优性理论界,并通过三个均值场基准实验验证了方法在大规模和次优数据场景下的显著优势。

核心贡献和创新点如下:

◆ 首次将扩散规划提升至轨迹分布的Wasserstein空间,借助混沌传播性质用小规模代表性智能体子集刻画全种群动态,突破联合空间维度灾难,使离线MARL可扩展至上千智能体。

◆ 提出价值加权的混沌熵目标函数,在保证生成保真度的同时实现回报最大化,协调了扩散模型的生成质量与策略优化目标。

◆ 设计了分层的由粗到细策略,在去噪过程中渐进式扩展智能体种群规模,提升大规模场景下的生成效率与稳定性。

◆ 给出包含四个可解释项的端到端次优性理论界,证明均值场近似误差以O(H²/√N)规模下降,且离线分布偏移不随种群规模N增长,理论上保证生成策略为近似均值场纳什均衡并给出显式收敛保证。

◆ 在涵盖阶段博弈、序列动态与对抗团队竞争的三类均值场基准上取得多数最优表现,在次优离线数据和N≥10³的极端规模下增益最为显著。</td></tr>
<tr><td>2026-05-31</td><td>Learning-based Directed Graph Abstraction of Combinatorial Spaces for Order-Preserving Search in Mixed-Combinatorial Nonlinear Optimization<br><a href='http://arxiv.org/pdf/2606.01425'>论文</a></td><td>针对混合组合非线性规划问题中传统编码方式引入伪关系、增加维度且需额外约束的缺陷，本文提出了一种基于学习的组合空间抽象方法。
◆首次提出使用边场图网络对组合空间进行结构化抽象，将无向全连接组合图映射为指示改进方向的有向图。
◆将该方向感知的抽象模型作为推荐系统，在仅搜索连续变量的优化框架中检索最适组合，提升了检索的可扩展性与可解释性。
实验将该方法与粒子群和遗传算法求解器结合，在三个基准非线性问题上进行了测试。
结果表明，相比使用索引组合的基线求解器，基于图神经网络的推荐系统在平均最优值和鲁棒性上均取得更优表现。</td></tr>
<tr><td>2026-05-31</td><td>ActMVS: Active Scene Reconstruction with Monocular Multi-View Stereo<br><a href='http://arxiv.org/pdf/2606.01367'>论文</a> | <a href='https://github.com/TrickyGo/ActMVS'>代码</a></td><td>该论文提出了ActMVS，这是首个仅依赖单目视觉的主动场景重建框架，解决了传统方法依赖深度传感器增加成本，以及现有单目方法无法实时提供全局一致稠密深度的问题。
◆提出视图因子图构建方法，用于指导多视图立体的深度预测。
◆引入全局深度优化机制，实现在线生成高质量且全局一致的稠密深度图。
这些创新使单目机器人或无人机能够实时维护高置信度的占据地图，实现安全的无碰撞轨迹规划与自主重建。
实验证明该方法性能可媲美基于RGB-D的方案，极大提升了单目视觉的空间智能与实用性。</td></tr>
<tr><td>2026-05-31</td><td>Make Your VLA More Robust Without More Data By Interleaving Motion Planning<br><a href='http://arxiv.org/pdf/2606.00985'>论文</a></td><td>视觉-语言-动作模型在长视距任务中因目标难以维持和误差累积导致表现不佳，单纯增加微调数据无法解决此问题。为此，本文提出无需额外训练的运动规划与VLA交织框架MPVI。
◆将基于模型的运动规划与VLA结合，利用开放词汇目标检测、前沿探索与运动规划，实现在杂乱场景中对远处或遮挡目标的定位与导航。
◆设计了基于视觉语言模型的完成度检查与本体感受触发机制，有效解决模块间可靠切换的难题。
实验表明，该方法在BEHAVIOR-1K基准上，任务进度相比顶级端到端基线提升了113%。这充分证明了MPVI框架在不增加数据前提下提升VLA鲁棒性的显著效果。</td></tr>
<tr><td>2026-05-30</td><td>Generative Multi-Robot Motion Planning via Diffusion Modeling with Multi-Agent Reinforcement Learning Guidance<br><a href='http://arxiv.org/pdf/2606.00933'>论文</a></td><td>本文提出了一种结合去中心化生成式轨迹规划与多智能体强化学习引导的协调框架，用于解决多机器人运动规划中的交互与可扩展性难题。
◆利用仅在单智能体数据上训练的扩散模型为每个机器人独立生成可行且多样的候选轨迹，保留了去中心化规划的可扩展性。
◆通过多智能体强化学习训练的集中式价值函数引导反向扩散过程，采用基于梯度的策略和指数倾斜公式，将去噪分布偏向具有更高多智能体期望回报的轨迹。
◆无需进行集中式联合规划或重新训练生成模型，即可实现具备交互意识的轨迹生成，有效减少智能体间冲突。
实验表明，该价值引导规划将四机器人环境中的智能体干扰率从55.4%降至41.8%，成功在保持去中心化扩展性的同时实现了有效协调。</td></tr>
<tr><td>2026-05-30</td><td>From Cues to Horizons: Dynamic Risk Horizon Profiling for Trajectory Prediction<br><a href='http://arxiv.org/pdf/2606.00857'>论文</a> | <a href='https://github.com/bilab-nyu/RHP'>代码</a></td><td>本文提出了一种名为风险水平剖面（RHP）的模块，通过连续可学习的势场模型来动态刻画未来时空的风险分布，从而将风险演化与不确定性引入轨迹预测任务，显著提升了预测精度与泛化能力。该方法在highD高速公路和SHRP2城市道路两个不同场景的数据集上进行了评估，相较基线实现了5秒RMSE降低25.0%和5秒minFDE降低29.1%的显著效果，证明了其对短时和长时预测的有效性以及跨场景的鲁棒性。该工作为自动驾驶车辆路径规划和战略选择提供了更贴近人类驾驶认知的风险感知支持。

◆ 首次提出将未来风险水平剖面作为动态可学习的特征，而不仅仅将过去风险作为辅助信号，实现了对风险时空演化的显式建模。
◆ 采用连续可学习的势场模型来量化车辆间时空接近度，避免了传统离散风险度量的局限性，支持自适应识别关键风险时刻。
◆ 在highD和SHRP2两个不同驾驶环境数据集上验证了方法的通用性，并在近碰撞、碰撞等多样化风险场景中均取得显著性能提升。</td></tr>
<tr><td>2026-05-30</td><td>A Framework for Motion Planning with Temporal Logic Precedence Specifications via Augmented Graphs of Convex Sets<br><a href='http://arxiv.org/pdf/2606.00842'>论文</a></td><td>本文提出了一种运动规划框架，能够在避障的同时满足由信号时序逻辑片段表达的逻辑先后约束。该框架对包含障碍物、钥匙和门的环境进行建模，其中获取钥匙可解锁对应门并可能开辟通往目标的更短路径。
◆基于对自由空间的精确凸分割，构建了增广凸集图，其分层结构精确编码了钥匙与门的先后逻辑。
◆通过在增广凸集图中寻找最短路径，实现了同时选择最优钥匙收集序列与计算最优连续轨迹。
该方法在有限的贝塞尔曲线参数化下提供了精确解，有效解决了具有时序先决条件的复杂运动规划问题。</td></tr>
<tr><td>2026-05-30</td><td>ROG-Grasp: Root-Oriented Geometry for Robotic Grasping and Placement<br><a href='http://arxiv.org/pdf/2606.00449'>论文</a></td><td>本文提出了ROG-Grasp框架，这是一种基于几何的机器人抓取与放置方法，通过RGB-D感知从农产品根部表面几何形状估计其朝向，解决了农业加工中的朝向感知操作问题。
◆提出结合YOLO根部检测器与点云平面拟合推断根部法线，从而实现稳定的抓取姿态生成。
◆设计了受朝向约束的笛卡尔运动规划，确保农产品能以一致的构型被放置。
◆与视觉语言动作策略相比，该方法在抓取可靠性和准确性上更优，且执行速度更快。
在番茄和洋葱的实验中，该框架在孤立与杂乱场景下均展现出高成功率和稳定的执行时间。
这些结果证明了几何驱动感知在实际朝向控制操作任务中的有效性和实用性。</td></tr>
<tr><td>2026-05-29</td><td>LiftNav: Path Planning via Semantic Lifting in TSDF-Guided Gaussian Splatting<br><a href='http://arxiv.org/pdf/2605.31376'>论文</a></td><td>本文提出了LiftNav混合导航框架，解决了传统TSDF缺乏语义和高斯溅射几何软导致避障不精确的问题。该框架基于TSDF与高斯溅射双地图构建，实现了可靠的碰撞避障与物体级理解。
◆设计了基于YOLO检测与TSDF三维提升的实时管线，无需密集三维嵌入即可实现灵活的语义导航。
◆引入了基于铰链损失的碰撞惩罚机制，有效提升了轨迹的平滑度与安全性。
◆结合B样条轨迹优化，在仿真实验中相比现有基线实现了百分之百的轨迹可行率和更短的路径。</td></tr>
<tr><td>2026-05-29</td><td>Haptic Sorter: A Unified Planning Framework for Online Shape Estimation and Real-Time Pose Inference<br><a href='http://arxiv.org/pdf/2605.31352'>论文</a></td><td>本文针对机器人操作中物体形状与姿态先验未知及传感器遮挡问题，提出了一个融合触觉感知、建模与操作规划的统一几何框架。
◆引入贝叶斯优化指导触觉探索以推断物体形状，并利用超椭圆近似几何边界。
◆自适应地构建编码物体几何的操作势函数，用于准静态机器人与物体交互。
◆提出基于模型预测和触觉反馈的在线常微分方程，实现物体实时姿态推断。
该框架在二维机器人分拣任务的仿真与真实多臂平台上进行了验证，证明了其在不同几何形状下的鲁棒性与泛化能力。</td></tr>
<tr><td>2026-05-29</td><td>AR Forcing: Towards Long-Horizon Robot Navigation World Model<br><a href='http://arxiv.org/pdf/2605.31314'>论文</a></td><td>该论文指出了基于扩散的机器人导航世界模型中，并行监督训练与自回归推理间的分布偏移导致长程预测不稳定的问题。为此，论文提出了AR Forcing自回归训练策略来消除这一偏差。
◆将标准扩散损失整合进自回归训练循环，模型每步利用自身预测更新上下文并优化单步噪声预测，使其在训练时显式暴露于推理状态分布。
◆无需引入额外判别器或分布匹配损失，完全保留原始扩散框架与采样器，方法简单且极易集成。
◆在多个导航数据集上的实验表明，该方法显著提升了长程导航中图像生成的一致性与轨迹预测精度，增强了模型在复杂及未知环境下的鲁棒性。</td></tr>
<tr><td>2026-05-29</td><td>DriveMA: Driving Vision-Language-Action Models with verifiable Meta-Actions<br><a href='http://arxiv.org/pdf/2605.31271'>论文</a></td><td>本文提出DriveMA框架，旨在解决驾驶视觉语言动作模型中语言与动作间的鸿沟问题，并在Waymo等数据集上取得了最先进的端到端规划性能。
◆提出可验证的元动作，将未来自车运动转化为紧凑的语言域意图，并可通过轨迹标注管线构建以及基于规则的投影进行验证。
◆引入动作中心的监督训练，有效利用元动作的可验证性来指导模型学习。
◆设计数据高效的回合级信用分配强化学习框架，通过密集奖励与精确信用分配，显式对齐高级决策与低级轨迹规划。
实验结果表明，即使是简单的元动作接口，只要具备可验证性并针对语言动作对齐进行优化，即可实现卓越的自动驾驶规划效果。</td></tr>
<tr><td>2026-05-29</td><td>Trajectory Planning for Non-Communicating Mobile Robots using Inverse Optimal Control<br><a href='http://arxiv.org/pdf/2605.30906'>论文</a></td><td>该论文提出了一种新颖的轨迹规划与预测组合算法，以解决非通信移动机器人避障场景下的高效交互问题。
◆利用逆最优控制方法，基于观测到的历史轨迹来估计所有机器人的未知目标状态。
◆引入视角转换机制，每个机器人从其他机器人视角出发进行自我预测，并结合估计目标状态求解联合预测问题。
◆将联合预测结果直接融入自身的轨迹规划中，实现预测与规划的深度耦合。
仿真实验表明，在2至8个机器人的场景下，该方法使所有机器人到达目标的中位耗时缩短了9.8%。
同时，该算法确保求解器始终能成功找到规划或预测问题的解，彻底避免了无解情况的发生。</td></tr>
<tr><td>2026-05-29</td><td>Coupling Language Models with Physics-based Simulation for Synthesis of Inorganic Materials<br><a href='http://arxiv.org/pdf/2606.00315'>论文</a></td><td>机器学习虽能提出新型无机材料，但复杂的物理过程和计算工具的缺乏使得合成规划极具挑战。本文提出了一个新型混合框架，通过结合热力学数据库与简化动力学模型来评估大语言模型在无机合成规划中的表现。
◆将大语言模型与基于物理的模拟相耦合，构建了能够近似真实合成条件的评估框架。
◆通过对比经典路径规划算法，揭示了大语言模型的隐式先验知识能够生成更具可行性的合成策略。
该研究以铌氧系统为案例，突显了在复杂合成问题中大语言模型隐式先验的独特价值，为无机材料合成规划提供了新思路。</td></tr>
<tr><td>2026-05-28</td><td>Multi-Robot Box Transport over Different Surfaces with Decentralized Role-based Proportional Control<br><a href='http://arxiv.org/pdf/2605.26430'>论文</a></td><td>该论文提出了一种名为R2P2的异步分散式任务与运动规划方法，解决多机器人在不同倾斜度与摩擦力表面上协同运输箱子的挑战。
◆提出去中心化架构，免除机器人间的通信同步与共识需求，有效规避单点故障。
◆设计基于操作模式动态分配角色的机制，根据旋转或平移需求赋予机器人推、支撑或阻止等角色。
◆融合基于规则的控制与比例速度控制，机器人仅需观测自身与箱子的位置及朝向即可执行动作。
◆方法在多变的地形摩擦、倾斜度及箱子质量场景中展现强泛化能力，成功率优于传统虚拟领导者跟随者方法。
◆通过六台机器人的仿真测试与四台Turtlebot的实物实验，充分验证了该策略的有效性与实用性。</td></tr>
<tr><td>2026-05-28</td><td>A Radius-Sensitive Approximation Algorithm for Connected Submodular Maximization<br><a href='http://arxiv.org/pdf/2605.30053'>论文</a></td><td>本文研究连通子模最大化问题(CSM)及其有向版本(DCSM)和有向有根版本(DRCSM)。该问题在无线网络部署、路径规划、疫情传播和癌症基因组研究等领域具有重要应用。论文针对以最优解半径r为参数的近似比进行了显著改进,突破了此前最优的Ω(1/r)和Ω(1/√k)近似界。作者提出了一个多项式时间框架,对于(有向)CSM达到Ω(ε³/r^ε)的近似比,对于DRCSM达到Ω(δε³/r^ε)的双准则近似,其中规模约束最多被违反1+δ倍。

◆ 首次将CSM的近似比从Ω(1/r)改进到Ω(ε³/r^ε),由于r≤k,该结果同时优于以k为参数的现有最优界Ω(1/√k)。

◆ 提出核心算法GreedyRadius,可将任意以k为参数的双准则近似算法转化为以r为参数的同等近似比算法(至多相差常数因子),具有良好的通用性和可扩展性。

◆ 为DRCSM设计了灵活的双准则近似框架,允许在近似比与规模约束违反程度之间进行可调节的权衡(δ可在[1/k,1]之间取值)。

◆ 将算法框架统一推广到无向、有向以及有向有根三种CSM变体,扩展了问题的适用范围。

◆ 引入参数ε实现近似比的精细调控,为不同应用场景下的算法性能优化提供了理论基础。</td></tr>
<tr><td>2026-05-28</td><td>FLIP: Real-Time and Resilient Formation Planning for Large-Scale DIstributed Swarms via Point Cloud Registration<br><a href='http://arxiv.org/pdf/2605.29704'>论文</a></td><td>该论文提出了FLIP,一种面向大规模分布式无人机集群的实时、弹性编队规划方法,通过将编队位置分配问题转化为时空点云配准问题,实现了高性能且大规模的协同轨迹规划。核心思路是让每个智能体分布式地计算自身当前位置与所有其他智能体期望编队位置之间的匹配结果,从而获得最优编队位置序列(OFPS),并基于此优化协同编队轨迹。论文采用带有外点剔除机制的点云配准方法,有效阻止次优轨迹和失效智能体在协同网络中的传播扩散。最终通过120架无人机的大规模仿真验证了方法的有效性,并与SOTA方法进行了严格对比基准测试,展示了其优越性。

◆ 首次将最优编队位置序列(OFPS)计算问题创新性地转化为时空点云配准(PCR)问题,为大规模编队分配提供了全新求解范式。

◆ 提出基于带外点剔除的点云配准方法,可快速完成大规模编队位置匹配,显著降低计算复杂度。

◆ 设计了具有弹性的分布式协同机制,通过外点剔除阻断次优轨迹和失败智能体在协作网络中的扩散影响,提升集群鲁棒性。

◆ 实现了弹性、高效与分布式三者统一的轨迹规划框架,突破了传统方法在表示简化与全协作计算负担之间的权衡难题。

◆ 在120架无人机规模的仿真场景中验证了方法的可扩展性,并通过严格基准测试证明其相较于SOTA方法的显著优势。</td></tr>
<tr><td>2026-05-28</td><td>The Open Motion Planning Library 2.0<br><a href='http://arxiv.org/pdf/2605.29301'>论文</a></td><td>本文介绍了开放运动规划库(OMPL)的重大升级版本OMPL 2.0。OMPL自2008年首次发布以来,已成为运动规划领域的基石,提供了广泛的基于采样的最先进算法实现。经过近二十年的持续开发,该库不断扩展新的规划器、状态空间和问题表述,涵盖从渐近最优规划、惰性规划到约束运动规划及时序逻辑目标规划等多种功能。OMPL 2.0在此基础上进行了重大演进,旨在通过硬件加速实现实时运动规划,并与现代AI研究工作流无缝集成。论文同时回顾了OMPL与运动规划领域共同成长的历程,并讨论了该库对研究界的广泛影响。

核心创新点如下:

◆ 推出OMPL 2.0版本,作为运动规划库的重大演进,标志着该领域工具链的全新升级。

◆ 通过硬件加速技术实现实时运动规划能力,显著提升了规划效率与响应速度。

◆ 与现代AI研究工作流无缝集成,促进了传统运动规划方法与人工智能技术的深度融合。

◆ 持续扩展多样化的规划器与状态空间,涵盖渐近最优、惰性规划、约束运动规划以及基于时序逻辑目标的规划等前沿方向。

◆ 系统性回顾了OMPL与运动规划领域协同发展的历程,为后续研究提供了重要的参考与反思视角。</td></tr>
<tr><td>2026-05-27</td><td>Integrated Exploration-Aware UAV Route Optimization and Path Planning<br><a href='http://arxiv.org/pdf/2605.28654'>论文</a></td><td>本文提出了一个集成探索感知的无人机路线优化与路径规划框架，用于解决先验信息不确定且动态变化下的危险环境监测问题。核心贡献在于将有限的飞行续航合理分配于检查已知危险区域和探索未知信息区域之间。
◆将报告的危险源建模为不确定的感兴趣区域而非确认目标，要求无人机在检查报告区域的同时探索信息量大的区域。
◆通过在路线中增加辅助伪节点来提升空间覆盖率，并优化动态可行的B样条轨迹以进行局部探索。
◆引入在线重规划机制，根据无人机实时测量更新网格信念图，并在新信息和剩余预算允许时自适应调整后续轨迹。
实验表明，该方法在四十八种场景配置下表现优异，在线重规划比离线优化和直线遍历的平均KL散度降低效果分别提升了15.9%和48.6%。</td></tr>
<tr><td>2026-05-27</td><td>Accelerating Robot Path Planning via Connectivity-Preserving Region Proposal Network<br><a href='http://arxiv.org/pdf/2605.28362'>论文</a></td><td>本文提出连接性保持区域提议网络CP-RPN，通过预测紧凑且拓扑连通的候选区域，有效解决了传统采样算法延迟高和学习方法区域碎片化的问题，显著压缩了搜索空间。
◆设计了结合可变形注意力Transformer与反卷积解码器的分割模型，前者捕捉长距离依赖以获取全局连通性，后者保留细粒度空间细节。
◆提出融合交叉熵损失、连通性感知损失和基于持久同调的拓扑连续性损失的复合损失函数，从局部到全局严格保证预测掩膜的连通性。
◆构建基于高连通走廊区域的Voronoi图规划与局部A*回退相结合的机制，兼顾了路径规划的高效性与鲁棒性。
实验表明，该方法将候选区域缩减超60.13%，实现平均0.11秒的低延迟规划及99.60%的高成功率，表现优于传统算法。</td></tr>
<tr><td>2026-05-27</td><td>Deconstructing Spatial Complexity: Hierarchical Decomposition for LLM Spatial Reasoning<br><a href='http://arxiv.org/pdf/2605.28144'>论文</a></td><td>本文针对大语言模型空间推理能力不足的问题，提出了一种受分层强化学习启发的分层任务分解方法，引导模型通过识别关键中间状态和生成简化子环境来处理复杂任务。
然而，由于模型缺乏充足的空间先验，往往难以推导出最优中间状态从而导致次优分解。
◆提出MCTS引导的群组相对策略优化算法，通过将模型的先验预测概率与认知不确定性结合来改进UCT公式，从而优化中间状态生成并增强规划能力。
◆设计了更细粒度的优势函数，使模型能够有效学习并生成最优路径规划策略。
实验表明，该方法在导航、规划和策略游戏等空间任务上大幅提升了模型性能并达到业界最优，为具身智能等现实应用铺平了道路。</td></tr>
<tr><td>2026-05-26</td><td>TCBiRRT: Rapid Motion Planning for Tightly Coupled Dual-arm Space Manipulator Using Task-space Random Expansion<br><a href='http://arxiv.org/pdf/2605.27167'>论文</a></td><td>本文针对紧密耦合双臂空间机械臂在闭链约束下难以高效规划运动的问题，提出了任务空间约束双向快速扩展随机树算法TCBiRRT。
◆不同于传统高维构型空间方法，该算法直接在由操作物体位姿定义的任务空间内进行随机采样与节点扩展。
◆开发了任务空间节点扩展策略生成候选物体运动，并利用路径逆运动学算法将其映射为连续的关节路径。
◆将上述方法与双向RRT框架及重抓取机制相结合，高效实现了两棵随机树的连接。
实验表明，TCBiRRT在复杂轨道装配场景中不仅成功率显著更高，且规划时间相比现有算法提升了数个数量级。</td></tr>
<tr><td>2026-05-26</td><td>Provably Safe Motion Planning Under Unknown Disturbances<br><a href='http://arxiv.org/pdf/2605.26625'>论文</a></td><td>本文提出了一种针对受未知分布随机扰动影响的机器人系统的可证明安全的运动规划算法，将安全性要求表述为机会约束。该方法利用系统轨迹数据学习Wasserstein模糊管，以高置信度包含状态分布轨迹，并将其应用于生成满足约束的概率完备采样规划树。
◆通过学习多个低维模糊管代替单一高维模糊管，有效降低了规划保守性并提升了算法可扩展性。
◆设计了高效的基于强盗的有效性检查器，在不牺牲概率完备性的前提下显著提升了经验性能。
实验表明该算法能在严格安全阈值与杂乱环境中规划出有效路径，性能优于现有方法。</td></tr>
<tr><td>2026-05-26</td><td>AURA: Asymptotically Optimal Uncertainty-Robust Replanning Algorithm for Kinodynamic Systems<br><a href='http://arxiv.org/pdf/2605.27699'>论文</a></td><td>本文提出了AURA框架，这是一个针对运动学动态系统的渐近最优元规划器，解决了传统离线规划无法即时执行以及运动不确定性导致跟踪偏差的两大局限。
◆提出一种重规划方法，在执行过程中持续探索状态空间并优化轨迹，实现了渐近最优的在线规划。
◆引入优化过程，通过细化未来控制输入来减少跟踪误差，有效提升了运动不确定性下的执行精度。
该框架将重规划与控制优化相统一，使系统能够在发挥在线渐近最优规划优势的同时提高执行准确性。
仿真和真实世界的多系统实验表明，AURA在轨迹质量、跟踪精度和整体性能上均显著优于基线方法。</td></tr>
<tr><td>2026-05-26</td><td>Simulation-Informed Diffusion for Decentralized Multi-robot Motion Planning<br><a href='http://arxiv.org/pdf/2605.27697'>论文</a></td><td>本文针对去中心化多机器人运动规划中现有方法无法预测邻居未来行为的局限，提出了仿真信息扩散框架。该框架基于约束感知扩散模型，有效提升了对未来动态的预判与安全规划能力。
◆提出仿真与规划双阶段机制，先模拟邻居机器人的未来轨迹，再依据仿真结果与安全约束规划自身轨迹。
◆设计了一种最小通信方案，借助精确的邻居仿真，仅在高度拥挤时才触发必要的通信协调。
◆在扩展性与规划性能上取得突破，在108台机器人和160个障碍物的大规模场景中，其规划有效性与约束满足度显著优于基线方法。</td></tr>
<tr><td>2026-05-25</td><td>Fast-dDrive: Efficient Block-Diffusion VLM for Autonomous Driving<br><a href='http://arxiv.org/pdf/2605.23163'>论文</a></td><td>本文提出Fast-dDrive，一种用于自动驾驶的块扩散视觉语言动作模型，解决了自回归模型内存受限和全序列扩散模型逻辑泄漏的问题，实现了轨迹规划与高效推理的平衡。
◆提出块扩散机制，在语义单元内进行双向细化，同时跨单元保持严格的因果顺序。
◆针对结构化输出冻结结构标记为段落支架，并采用优先安全关键规划的段落感知训练策略。
◆引入支架投机解码，在保证自回归相当质量的同时显著提升推理吞吐量。
◆提出低开销测试时扩展方案，通过共享前缀KV缓存分叉并平均N个随机轨迹来抑制预测方差。
实验表明该模型在WOD-E2E和nuScenes上取得SOTA精度，结合SGLang实现12倍吞吐量提升，满足实时车载部署需求。</td></tr>
<tr><td>2026-05-25</td><td>Totoro$^+$: An Adaptive and Scalable Edge Federated Learning System<br><a href='http://arxiv.org/pdf/2605.26323'>论文</a></td><td>Totoro+ 是一个新型可扩展的边缘联邦学习系统,旨在支持大规模联邦学习应用在边缘网络上同时运行。其核心思路是利用基于分布式哈希表(DHT)的点对点(P2P)模型,将传统集中式联邦学习架构重构为完全去中心化的架构,为每个应用分配专属参数服务器,任何边缘节点都可担任协调者、聚合者、客户端选择器或工作节点等任意角色,从而显著提升系统的可扩展性与适应性。在500台Amazon EC2服务器上的真实实验表明,该系统能够随应用数量优雅扩展,将训练总时间加速1.2至14倍,在百万节点规模下实现O(log N)跳的模型分发与梯度聚合,并能高效适应实际边缘网络与节点动态变化。

核心创新点如下:

◆ 提出基于DHT的P2P去中心化架构,摒弃传统单一集中式参数服务器,为每个联邦学习应用配置独立参数服务器,从根本上突破了可扩展性瓶颈。

◆ 设计了具备位置感知能力的P2P多环结构,使节点组织能够感知网络拓扑,有效降低跨区域通信开销。

◆ 提出基于发布/订阅机制的森林抽象模型,用于高效支持模型分发与梯度聚合,实现对数级通信复杂度。

◆ 引入基于博弈论的路径规划模型,并理论上证明可达到ε近似纳什均衡,实现节点间通信路径的优化决策。

◆ 实现任意边缘节点可灵活承担多种角色的统一调度机制,使系统能够动态适应实际边缘网络环境与节点频繁加入退出的churn现象。</td></tr>
<tr><td>2026-05-25</td><td>Collaborative Threat-Aware Autonomy (CTAA)<br><a href='http://arxiv.org/pdf/2605.25741'>论文</a></td><td>本文提出协作威胁感知自主框架，解决无人机群在动态对抗武器交战区中单机易失效的根本挑战。
◆提出角色分化的多智能体协同轨迹规划框架，为机群分配主拦截、护航和诱饵三种角色，以提高团队任务成功率并管理个体威胁暴露。
◆基于碰撞球边界逃避零集推导出反应式引导律，该引导律考虑了最小转弯半径带来的机动性约束，引导车辆驶向兼顾安全与目标推进的最优航向。
◆通过角色分配与空间路线分离，引入概率冗余效应，即利用多条独立路径提升团队整体成功概率。
◆同时实现威胁饱和效应，即利用低优先级的护航和诱饵吸引敌方注意力，保障主车辆不受阻碍地通行。</td></tr>
<tr><td>2026-05-24</td><td>Performance Comparison of Classical and Neural Sampling Algorithms for Robotic Navigation<br><a href='http://arxiv.org/pdf/2605.25010'>论文</a></td><td>本文的核心贡献是在包含不同密度凸凹障碍物的环境中，系统评估并对比了RRT*、Neural RRT*和Neural Informed RRT*三种经典与神经采样算法的性能。
◆证明了神经引导规划器能显著提升路径质量，使路径缩短达14%，轨迹平滑度提升55%至75%。
◆明确了Neural Informed RRT*算法在路径长度和轨迹平滑度上具备最优的综合表现。
◆验证了AI引导采样策略对提升机器人和无人机导航可靠性与轨迹效率的有效性，即便存在计算时间的轻微增加。
该研究突显了AI在实时机器人路径规划应用中日益重要的作用。</td></tr>
<tr><td>2026-05-24</td><td>Convex-Neural RRT*: Fast and Reliable Learning-Guided Sampling for High-Quality Robot Path Planning<br><a href='http://arxiv.org/pdf/2605.25006'>论文</a></td><td>传统基于采样的机器人路径规划算法往往需要大量迭代才能获得高质量解，计算效率较低。本文提出了Convex-Neural RRT*算法，通过引入神经引导来预测高质量路径附近的有用航点区域。
◆从神经网络的预测结果中提取凸候选区域，使规划器能够集中探索几何相关区域。
◆在聚焦局部高价值区域探索的同时，保留了算法的全局探索能力，确保了寻路成功率。
实验表明，该算法相比神经引导变体和LTA*分别减少30%至75%和88%至98%的计算时间，且路径长度平均缩短约5%，在复杂环境中改善更大。该算法在计算效率和路径质量间取得了有效平衡，整体成功率超99%，非常适合对时间敏感的机器人导航任务。</td></tr>
<tr><td>2026-05-24</td><td>Scaling up Energy-Aware Multi-Agent Reinforcement Learning for Mission-Oriented Drone Networks with Individual Reward<br><a href='http://arxiv.org/pdf/2605.24992'>论文</a></td><td>本文针对无人机网络中动态环境和有限电池容量限制下的协同任务挑战，提出了一种能量感知的多智能体强化学习模型。该模型基于深度Q网络，有效提升了无人机群协作执行任务的效率。
◆设计了由任务执行进度和无人机剩余电量共同驱动的个体奖励函数，解决了传统共享奖励中信用分配不清的问题。
◆在环境规模扩展时表现出显著优势，对环境大小和智能体数量的变化具备更强的鲁棒性。
◆通过明确个体目标减少了任务执行步数，在保持高成功率的同时进一步提升了能量效率。</td></tr>
<tr><td>2026-05-24</td><td>Learning Transferable Motor Skills for Geometry-Aware Robotic Surface Tasks<br><a href='http://arxiv.org/pdf/2605.24881'>论文</a></td><td>本文针对机器人表面交互任务中几何规划与运动执行耦合导致可迁移性差的问题，提出了一种将几何运动规划与执行级专业知识解耦的模块化框架。
◆提出将专家行为表示为可解释的原子运动规则词汇表，如速度缩放和姿态偏移，从而系统性地修改几何规划的参考路径。
◆训练了多模态神经网络，能够从运动轨迹数据和CAD模型几何形状中联合推断出运动规则的参数。
◆通过解耦规划与执行并引入几何感知的规则推断机制，打破了传统模仿学习对特定训练几何形状的依赖。
在L形和窗形物体上的仿真实验表明，该模型能成功跨越不同拓扑结构提取速度和姿态规则，实现了运动技能的有效迁移。</td></tr>
<tr><td>2026-05-23</td><td>SparseWorld: Enhancing End-to-End Autonomous Driving via World Models with Sparse Scene Representation<br><a href='http://arxiv.org/pdf/2605.24354'>论文</a> | <a href='https://wryzju.github.io/SparseWorld/'>代码</a></td><td>本文提出了SparseWorld，一个轻量级的自动驾驶世界模型，通过稀疏场景表示仅预测关键场景布局，解决了现有稠密表示计算成本高和信息冗余的问题。
◆提出Sparse Dreamer模块，通过联合时间与空间注意力机制在潜空间中预测未来实例。
◆采用自回归展开方式预测未来地图元素和周围智能体，使模型学习驾驶场景的时间演变规律。
◆使运动规划器与预测的未来实例进行交互，从而捕捉更准确的运动模式并生成更具安全意识的轨迹。
实验表明，该方法大幅降低了碰撞风险，在nuScenes开环规划中达到0.05%碰撞率的领先水平，并在Bench2Drive闭环基准上显著超越基线方法。</td></tr>
<tr><td>2026-05-23</td><td>Sum of Costs Diffusion with Dynamic Guidance for Motion Planning<br><a href='http://arxiv.org/pdf/2605.24690'>论文</a></td><td>该论文针对机器人操作中的运动规划问题,提出了一种基于扩散模型的高泛化能力轨迹生成方法。该方法通过总碰撞代价的梯度引导去噪过程,从而生成无碰撞轨迹,并设计了动态选择梯度引导起始步骤的策略,以提升模型在多样化场景下的鲁棒性。实验在Mπnets数据集的多种测试设置中验证了方法的有效性,结果表明该方法相比现有竞争方法具有更强的泛化性能,取得了最佳表现,有效克服了传统方法和已有深度学习方法在跨场景适应性方面的不足。

核心创新点如下:

◆ 提出基于扩散模型的运动规划框架,利用总碰撞代价(Sum of Costs)的梯度对去噪过程进行引导,从而生成无碰撞的可行轨迹。

◆ 设计了一种动态确定梯度引导起始步骤的机制,而非采用固定起始点,使引导过程更加灵活并适应不同场景。

◆ 通过将碰撞代价信息融入扩散模型的采样过程,显著提升了模型在多样化环境下的泛化能力,克服了现有方法在跨场景适应性方面的局限。

◆ 在Mπnets数据集的多种测试设置中达到了同类方法中的最优性能,验证了该方法在复杂操作任务中的鲁棒性与有效性。</td></tr>
<tr><td>2026-05-22</td><td>MASt3R-Nav: WayPixel Navigation in Relative 3D Maps<br><a href='http://arxiv.org/pdf/2605.24111'>论文</a></td><td>本文提出了一种新型导航系统MASt3R-Nav，旨在解决传统3D地图依赖全局一致性而拓扑图缺乏几何理解导致导航能力受限的问题。
◆提出像素相对连通性的新型地图表示方法，在保证几何精度的同时免去了对全局几何一致性的需求。
◆通过图像对相对3D坐标系中的像素对应关系构建图像间连通性，并稀疏化图像内连通性进行全局路径规划，推导出WayPixel Costmap。
◆基于该密集像素级代价图训练条件控制器以预测轨迹，证明了相对几何的像素级条件变量比图像或对象级更准确。
该系统在四种仿真导航任务及真实世界演示中得到验证，展现了卓越的导航能力。</td></tr>
<tr><td>2026-05-22</td><td>How Many Training Samples Are Needed for the Inverse Kinematics Solutions by Artificial Neural Networks<br><a href='http://arxiv.org/pdf/2605.23583'>论文</a></td><td>本文研究了人工神经网络求解逆运动学问题时训练样本数量与预测精度之间的关系。研究通过关节型机械臂生成不同数量的关节位置数据对来训练前馈神经网络，并评估了其精度、收敛性与泛化能力。
◆建立了关联训练数据集大小与神经网络逆运动学求解器精度的数学框架。
◆揭示了数据效率的临界点，发现当训练样本超过125个时，继续增加数据量不再提升模型的近似精度与整体效率。
该研究为优化神经网络求解逆运动学的数据规模提供了实用指导，有效平衡了实际机器人应用中的计算成本与模型精度。</td></tr>
<tr><td>2026-05-22</td><td>Signal Temporal Logic Motion Planning via Graphs of Convex Sets<br><a href='http://arxiv.org/pdf/2605.23240'>论文</a></td><td>本文提出了一种结合定时自动机推理与凸集图的高效框架，用于解决信号时序逻辑规范下的连续时间运动规划问题。
◆将STL运动规划问题转化为凸集图上的最短路径问题，通过联合定时自动机与构型空间凸分解构建转移系统，从而生成满足逻辑时序规范、平滑性及速度约束的贝塞尔样条轨迹。
◆证明了该方法的可靠性并分析了计算复杂度，表明在自动机和凸分解固定时，其凸松弛随构型空间维度和贝塞尔度数呈多项式级扩展。
◆针对富有表现力的STL片段，利用专用模板和布尔组合开发了一种紧凑的定时自动机构造方法。
多场景数值实验与硬件测试验证了该方法能高效解决复杂STL运动规划问题并生成平滑可执行轨迹。</td></tr>
<tr><td>2026-05-21</td><td>Scene Reconstruction as Mapping Priors for 3D Detection<br><a href='http://arxiv.org/pdf/2605.22997'>论文</a></td><td>本文提出了一种可扩展的解决方案，通过利用场景重建的地图先验来提升3D目标检测性能，克服了传统高精地图维护成本高的局限。
◆提出一种自动构建密集地图先验的流程，通过聚合传感器数据生成先验，消除了人工标注的需求。
◆设计了新颖的地图先验增强3D检测框架MPA3D，能够有效将地图先验与不同传感器模态进行融合。
在Waymo开放数据集上的广泛实验表明，该方法取得了全新的最优结果。
这证明了可扩展的重建场景先验对于增强3D检测的有效性。</td></tr>
<tr><td>2026-05-21</td><td>Verified Task-Space Motion Planning Under Joint-Space Constraints<br><a href='http://arxiv.org/pdf/2605.22991'>论文</a></td><td>针对反应式任务空间规划器因固定笛卡尔步长和忽略关节极限而导致跟踪漂移及目标不可达的问题，本文提出一种在关节位移边界下计算经认证可达的最大笛卡尔超长方体的方法。
◆利用逆运动学的二阶多项式近似和S-procedure，构建了求解认证步长半宽的小型半定规划问题。
◆提出一种利用二次结构的等效二分法，将认证求解时间缩短至亚毫秒级以适应实时需求。
将此认证机制与Bug2结合，使规划器步长能根据局部运动学条件自适应调整。
在94个对抗场景测试中，该SOS验证规划器实现了零关节极限违反和百分之百的目标到达率，彻底解决了标准Bug2算法的违规与失败问题。</td></tr>
<tr><td>2026-05-21</td><td>N3P: Accelerated Automated Parking via a Learning-Based Naturalistic Three-Stage Scheme<br><a href='http://arxiv.org/pdf/2605.22722'>论文</a></td><td>本文提出了N3P，一种基于学习的自然三阶段自动泊车框架，旨在解决传统Hybrid A*算法计算昂贵以及强化学习方法可靠性差和轨迹次优的问题。
◆引入中间准备姿态并利用学习模块进行预测，将复杂的泊车操作分解为简单的子问题，从而有效降低了计算复杂度。
◆将学习预测模块与Hybrid A*算法深度集成，大幅加速了路径的生成过程。
◆实验验证N3P增强的Hybrid A*规划速度提升超过80%，显著优于传统方法。
◆相比强化学习基线，该方法具有更高的成功率，且生成的轨迹更短、换挡次数更少，同时保持了相近或更低的规划时间。</td></tr>
<tr><td>2026-05-21</td><td>Branch-Stochastic Model Predictive Control for Motion Planning under Multi-Modal Uncertainty with Scenario Clustering<br><a href='http://arxiv.org/pdf/2605.22600'>论文</a></td><td>该论文针对自动驾驶运动规划中多模态不确定性导致传统方法过于保守的问题，提出了一种结合随机模型预测控制与分支结构的新方法。
◆将SMPC与分支结构相结合，为不同意图生成专属轨迹，在保证轨迹安全的同时克服了意图层面的保守性。
◆提出基于高级决策相似度的场景聚类方法，通过合并预测场景确保了算法的实时计算可行性。
◆引入自适应分支时间计算机制，将分离规划的时机推迟到意图不确定性充分降低之后。
仿真结果表明，该方法有效提升了安全性，减少了保守性，并实现了实时计算。</td></tr>
<tr><td>2026-05-20</td><td>Benchmarking Empirical and Learning-Based Approaches for Feedforward Steering Control in Autonomous Racing<br><a href='http://arxiv.org/pdf/2605.21111'>论文</a> | <a href='https://github.com/TUMRT/steering_ff_control'>代码</a></td><td>本文系统性地基准测试了两种基于学习和两种基于经验的前馈转向控制器，以评估其在自动驾驶赛车中减少反馈转向修正的能力。研究在基于真实阿布扎比自动驾驶赛车联赛的高保真双轨车辆动力学模拟器中，对这些控制器进行了开环与闭环测试。
◆提出了一种基于多项式曲面拟合的新型EHD公式，该公式能以最少的参数化捕捉依赖速度的非线性转向行为。
◆揭示了学习型控制器在开环评估中虽预测误差最低，但此优势无法转化为闭环路径跟踪性能或圈速的提升。
◆提出的新型EHD方法取得了最佳的闭环鲁棒性和圈速，突显了必须在完整的轨迹规划与控制软件栈中评估前馈策略的必要性。</td></tr>
<tr><td>2026-05-20</td><td>SubTGraph: Large-Scale Subterranean Environment Synthesis with Controllable Topological Variability for Robotic Autonomy Validation<br><a href='http://arxiv.org/pdf/2605.20917'>论文</a> | <a href='https://github.com/LTU-RAI/SubTGraph.git'>代码</a></td><td>本文提出了SubTGraph框架，填补了地下环境缺乏大规模仿真基准以进行机器人自主性严格统计评估的空白。◆创新性地基于用户结构约束构建代价矩阵，结合Dijkstra算法与拓扑度量瓦片程序化生成多层次地下环境。◆支持高变异性与可控参数合成，用户可根据拓扑、维度和纹理等规范生成矿井、自然洞穴和熔岩管道等不同场景。◆通过语义分割真值验证、多智能体路径规划趋势识别和LIO SLAM极限压力测试三个案例，全面验证了框架对自主栈各层级的评估能力。◆开源了环境生成代码库并发布了包含150个高变异性地下世界的数据库，为该领域提供了关键的基准测试资源。</td></tr>
<tr><td>2026-05-20</td><td>MC-Risk: Multi-Component Risk Fields for Risk Identification and Motion Planning<br><a href='http://arxiv.org/pdf/2605.21406'>论文</a></td><td>本文提出了MC-Risk，一种与规划器对齐的鸟瞰图多组件风险场，能够实现早期校准且类别感知的风险定位。
◆提出机动车辆风险场，融合多模态轨迹预测与高斯环面结构，使横向宽度随速度和曲率增加，高度随前视距离衰减。
◆设计弱势道路使用者风险场，采用与航向和速度对齐的各向异性前偏核，替代了传统的各向同性行人斑块。
◆构建道路惩罚场，利用高精地图拓扑施加偏离道路惩罚及车道感知风险暴露，区分同向与反向车道风险。
本研究首次在RiskBench碰撞子集上进行风险场的标准化定量评估，取得了最佳风险定位与最早危险指示效果。
最后，将该风险场作为模型预测控制的代价密度，无需额外训练即可实现风险感知轨迹生成的插拔式规划接口。</td></tr>
<tr><td>2026-05-19</td><td>Trajectory Planning and Control near the Limits: an Open Experimental Benchmark on the RoboRacer Platform<br><a href='http://arxiv.org/pdf/2605.19881'>论文</a> | <a href='https://roboracer-benchmark.github.io/planning_control_benchmark/'>代码</a></td><td>本文提出了一个模块化框架，用于在极限高加速机动下对自动驾驶轨迹规划和控制方法进行基准测试，并基于1比10比例的RoboRacer平台进行了实验验证。
◆提出一种新型模型结构化神经网络来学习转向控制的逆动力学，显著提高了跟踪精度，减少了转向振荡，且具备物理可解释性。
◆引入在线时间最优速度重规划机制，通过补偿执行误差有效缩短圈速，使车辆能安全达到更高的速度和加速度。
研究通过谨慎与激进赛车线的消融实验，深入分析了各独立模块及其组合的性能表现。
为支持未来研究，作者公开了代码与数据集等资源，为该领域建立了一个开放的实验基准。</td></tr>
<tr><td>2026-05-18</td><td>REACT: Environment-Adaptive Architecture for Continuous Formation Navigation of Wheeled Mobile Robots<br><a href='http://arxiv.org/pdf/2605.18441'>论文</a> | <a href='https://dongjh20.github.io/REACT-website'>代码</a></td><td>针对轮式移动机器人现有编队控制难以适应复杂环境的问题，本文提出了REACT分层架构，集成了集中式编队生成与分布式编队维持。
◆在上层，该架构按需生成环境自适应新编队，并提出TCF-R2T算法在多项式时间内计算无轨迹冲突的机器人目标分配，实现无冲突的及时编队转换。
◆在下层，各机器人执行提出的JSTP方法，通过同时优化空间位置与时间持续时间来维持编队，显著增强了多机器人间的协调性。
这种联合时空轨迹规划使机器人能够在密集静态和动态障碍物场景中实现连续导航。
仿真与真实世界实验充分验证了该架构的有效性与实际应用价值。</td></tr>
<tr><td>2026-05-15</td><td>Constrained MPC-Based Motion Planning for Morphing Quadrotors in Ultra-Narrow Passages under Limited Perception<br><a href='http://arxiv.org/pdf/2605.15999'>论文</a> | <a href='https://github.com/harshjmodi1996/morphocopter_mpc}{Github'>代码</a></td><td>本文提出了一种针对可变形四旋翼在极受限环境和有限感知条件下的形态与轨迹运动规划框架。
◆提出了一种用于非线性模型预测控制的平滑指数障碍物代价函数，通过引入代价降低因子且无硬激活阈值，在保持强避碰能力的同时，解决了传统人工势场在狭窄通道中代价过高阻断路径的问题。
◆将二维激光雷达测量值直接应用于模型预测控制中，使机器人能够有效绕过任意形状的障碍物。
该方法基于acados框架实现，计算高效且实用，实验和仿真结果均验证了其在典型排斥代价函数失效的狭窄走廊中成功穿越的能力。
此外，该代价函数具有通用性，不仅限于可变形四旋翼，还可广泛应用于任何移动机器人。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration (36篇)</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-15</td><td>Unsupervised Detection of Entry and Exit Regions from Vehicle Trajectories for Camera-Agnostic Turning Movement Counts<br><a href='http://arxiv.org/pdf/2607.10949'>论文</a></td><td>本文针对交叉口转向流量计数中人工标注成本高的问题，提出了一种基于车辆轨迹的无监督出入口区域检测流水线。该方法通过聚类轨迹的起点和终点位置，生成持久的空间区域多边形，未来轨迹可通过点-多边形包含关系以线性复杂度进行分类，避免了传统轨迹聚类方法每次重新执行的问题。

◆提出无需人工标注、相机标定或先验几何知识的无监督流水线，仅利用目标检测与多目标跟踪得到的原始轨迹即可识别出入口区域。
◆将区域识别转化为对轨迹起终点的位置聚类，生成持久的区域多边形，显著降低分类计算成本并提升跨视角稳定性。
◆设计包含六个可配置步骤的完整流水线框架，并通过对19152次执行的系统统计分析，识别出三个始终显著的关键参数，给出经验性推荐配置。
◆在印度班加罗尔25个相机（含16个未见过的位置）和UA-DETRAC数据集上实现约3%的中位分类误差，GEH指标符合工程标准。
◆验证了至少60分钟的校准片段结合高峰时段交通选取可进一步提升区域估计质量，证实了方法的实用性。</td></tr>
<tr><td>2026-07-13</td><td>Why Low-Light Cameras Go Color Blind: Removing Color Bias in Raw Denoising<br><a href='http://arxiv.org/pdf/2607.11090'>论文</a></td><td>本文针对低光条件下的原始图像去噪任务,提出了一种无需相机校准的通用去噪框架。研究发现黑电平误差引起的颜色偏差是导致去噪性能下降和严重色偏的主要原因,这一发现为盲去噪问题提供了新的视角。◆ 提出了一个偏置估计网络,将黑电平误差作为全局特征从噪声输入中预测出来,从而实现相机无关、无需校准的低光原始图像去噪。◆ 在ELD、SID和LRID等多个数据集上取得优于现有盲去噪方法的性能,尤其在颜色校正方面表现突出,在某些情况下甚至可与需要更强监督的方法相媲美。◆ 揭示了广泛使用的SIDD数据集的ground-truth存在显著颜色偏差,会导致训练模型产生不真实的颜色还原。◆ 提出了一种新的ground-truth提取框架,以解决SIDD数据集中的颜色偏差问题,并在修正后的数据集上对现有方法提供了新的基准评测。</td></tr>
<tr><td>2026-07-12</td><td>Projection-Domain Sensitivity Analysis of Vertebral DRRs Under Intrinsic Calibration Perturbation<br><a href='http://arxiv.org/pdf/2607.10551'>论文</a></td><td>本文针对椎体透视成像中的几何标定问题,系统评估了内参标定扰动对投影域一致性的影响。研究采用基于CT的椎体模型与受控锥束成像几何,生成真实与扰动标定下的DRR对,通过解剖标志位移、轮廓距离、剪影重叠、图像相似度及2D-3D配准精度等多维指标,定量分析AP与LAT视图下的投影变化。

◆ 提出基于合成框架的投影域标定敏感性分析方法,弥补传统重建域重投影误差指标的不足,为标定鲁棒性评估提供新视角。

◆ 揭示了标定敏感性的强视角依赖性,发现LAT投影在形变与解剖位移上比AP投影更为显著,明确了脊柱成像中多视角标定的差异化要求。

◆ 证实微小内参扰动即可显著降低下游2D-3D配准的旋转对齐精度,建立了标定质量与配准性能之间的直接定量关联,有助于提升图像引导脊柱手术的可靠性。</td></tr>
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
<tr><td>2026-06-26</td><td>Co-Optimization of Analog Kolmogorov-Arnold Networks for Low-Power Function Approximation in Flexible Electronics<br><a href='http://arxiv.org/pdf/2606.27892'>论文</a></td><td>◆提出模拟Kolmogorov-Arnold网络（AKANs），面向柔性电子中的低功耗多变量函数近似，适用于可穿戴与IoT传感端计算。

◆通过硬件-软件协同优化，将电路级非理想误差纳入训练过程，使模型在实际模拟硬件偏差下仍保持较高精度。

◆设计了软件与硬件双层剪枝方法，在减少样条参数和电路资源的同时降低面积与功耗。

◆实验表明，剪枝不仅压缩硬件开销，还能通过正则化效应提升函数近似精度。

◆在多个基准任务上实现最高55%面积节省和50%功耗降低，平均节省近30%，证明AKANs具备通用性和实用价值。</td></tr>
<tr><td>2026-06-26</td><td>Robotic Arm-Based Spectral Sensing for Strawberry Positioning and Non-Destructive Sweetness Measurement<br><a href='http://arxiv.org/pdf/2606.28555'>论文</a></td><td>◆提出了一套基于机械臂的草莓光谱感知系统，实现草莓检测、定位、接近与无损甜度估计的闭环集成。
◆系统结合YOLOv11s实时检测、RGB-ToF标定和掩膜-深度对齐，提升了果实三维定位的几何一致性。
◆设计了定制化eye-in-hand手眼标定流程，将目标从相机坐标可靠转换到机器人基坐标，支撑稳定操作。
◆采用路点搜索与增量式闭环接近策略，使传感器能够自动到达适合甜度测量的工作距离。
◆实验达到88.10%的端到端成功率，检测成功率95.24%，目标被检测后的接近成功率为100%，验证了系统可行性。
◆论文还指出当前主要瓶颈在复杂深度和反射条件下的有效感测区域提取，并为未来引入学习型策略提供了可扩展基线。</td></tr>
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
<tr><td>2026-06-12</td><td>Fully Distributed Multi-View 3D Tracking in Real-Time<br><a href='http://arxiv.org/pdf/2606.13127'>论文</a></td><td>本文提出MV3DT,一个面向重叠视野多摄像头网络的全分布式实时三维多目标跟踪框架。该方法摒弃传统集中式融合架构,通过点对点协同实现身份传播与遮挡恢复,有效解决了集中式方法在大规模部署时的计算瓶颈问题。在WILDTRACK数据集上达到94.3%的IDF1和93.3%的MOTA,性能与最先进的集中式方法相当,同时在100个摄像头规模下仍能保持30 FPS的实时性能,摄像头间延迟低于10毫秒,通信开销仅为2.2%。此外,该方法无需场景特定训练,仅依赖摄像头标定即可零样本部署于新环境。

核心创新点如下:

◆ 首次提出完全分布式的多视角三维跟踪架构,通过点对点协调机制取代中心节点聚合,从根本上消除了集中式方法的计算瓶颈。

◆ 设计了轻量级模块化流水线,在每个摄像头节点本地执行单目三维感知、分布式多视图关联与协同融合,通过轻量消息传递实现跨节点协作。

◆ 实现卓越的可扩展性,在100摄像头规模下维持30 FPS实时性能,通信开销仅2.2%,显著优于集中式方案。

◆ 采用零样本运行模式,仅依赖摄像头标定信息,无需任何场景特定的训练或学习,可直接部署到新环境。

◆ 在WILDTRACK基准上取得与集中式SOTA方法相竞争的精度,验证了分布式架构在保持高精度的同时具备规模化部署的实用价值。</td></tr>
<tr><td>2026-06-12</td><td>StereoGeo: an end-to-end stereo camera calibration method<br><a href='http://arxiv.org/pdf/2606.14619'>论文</a> | <a href='https://github.com/meddourimane/StereoGeo-dataset'>代码</a></td><td>本文提出了StereoGeo，一种基于端到端网络的立体相机标定方法。该方法能够同时估计左右相机的焦距与重力方向，以及它们之间的相对外参变换。
◆突破了现有方法依赖标定板或结构化环境的限制，无需多视角设置即可完成双目标定。
◆打破了传统方法仅局限于单目内参或外参估计的不足，实现了双目内外参的联合估计。
◆扩展了GeoCalib算法，将深度神经网络特征提取与可微优化器进行有效整合。
实验证明该方法在内参标定上极具竞争力，在外参估计上更超越了现有限于单目的方法。</td></tr>
<tr><td>2026-06-12</td><td>LV-Calib: LiDAR-Camera Extrinsic Calibration with Boundary-Response Modeling<br><a href='http://arxiv.org/pdf/2606.15010'>论文</a></td><td>本文提出了LV-Calib标定框架，利用可打印平面标定板实现了激光雷达与相机的外参估计及激光雷达边界响应标定。
◆提出基于强度与几何约束的迭代精化方法，自动裁剪背景并估计目标平面，显式处理反射率不连续处因光束足迹和混合回波导致的过渡带展宽与失真问题，提取精确的雷达3D特征点。
◆设计了加权重投影一致的外参优化策略，将图像观测保留在重投影域，并利用精化置信度对雷达特征残差进行加权，提升外参标定精度。
◆利用估计的外参和提取的过渡带，通过计算边界重叠样本的俯仰-偏航-距离残差统计量，实现了激光雷达边界响应的标定。
实验验证了该方法具备亚像素级重投影精度与毫米级特征一致性，并有效提升了里程计性能。</td></tr>
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
<tr><td>2026-06-06</td><td>Dexterity-BEV: Aligning 3D World and Actions for Generalizable Robot Policies Learning<br><a href='http://arxiv.org/pdf/2606.02274'>论文</a> | <a href='https://hnuzhy.github.io/projects/Dex-BEV'>代码</a></td><td>本文针对端到端操作策略依赖2D输入且缺乏跨机器人和相机的3D空间对齐的局限性，提出了Dexterity-BEV方法。
◆提出对齐顶点图与顶点频谱，利用相机标定和可选深度将2D视觉提升为像素级3D表示，融合了3D感知与2D大模型的泛化优势。
◆提出将操作策略的输入输出对齐至共享坐标系，并创新性地构建鸟瞰图图像，生成对相机位姿变化鲁棒的视角不变表示。
◆开发了全面的数据处理管线以实现大规模对齐，并引入了针对跨多种机器人、人类操作员和数据集轨迹的全新时间对齐方案。
这些贡献共同缓解了输入输出的时空不对齐问题，显著提升了真实世界机器人操作的连贯性与泛化能力。</td></tr>
<tr><td>2026-06-06</td><td>Empowering Feed-Forward Reconstruction Models with Metric Scale via Satellite Images<br><a href='http://arxiv.org/pdf/2606.08205'>论文</a></td><td>该论文提出一种卫星引导框架，利用易获取的卫星图像作为全局度量参考，解决前馈3D重建模型中存在的尺度模糊问题。
◆创新性地引入卫星图像作为度量参考，无需昂贵的度量标注或高精度相机标定即可消除尺度模糊。
◆设计了双向跨视角交互机制，将局部卫星图像块与前馈重建主干网络深度融合，强制重建场景与卫星参考间的一致性。
◆实现在度量坐标系下同时推断绝对尺度、优化场景几何并估计相机姿态的能力。
实验表明，该方法在多数据集的深度估计、点云重建和定位任务上均取得显著提升，且保持了优异的跨域泛化性。</td></tr>
<tr><td>2026-06-06</td><td>SynthICL: Scalable In-context Imitation Learning with Synthetic Data<br><a href='http://arxiv.org/pdf/2606.08154'>论文</a></td><td>SynthICL提出了一种可扩展的上下文模仿学习框架,完全基于RGB-only合成数据训练策略,无需深度传感、精确相机标定和真实世界数据。

◆ 提出了基于合成数据的可扩展数据生成流水线,能够为上下文模仿学习高效产出高保真度训练数据,大幅降低了数据获取成本。

◆ 采用流匹配Transformer作为策略架构,仅依靠单张RGB图像输入即可完成端到端动作预测。

◆ 引入子目标图像预测机制,让模型在生成动作前先预测下一子目标图像,实现了更精准且视觉上更具可解释性的控制。

◆ 在16个未见过的真实世界操作任务上以单条示范实现79%的平均成功率,优于现有方法,验证了纯合成数据训练在真实场景中的迁移能力。</td></tr>
<tr><td>2026-06-03</td><td>Multi-Camera AR Guidance System for Surgical Instrument Handling and Assembly: Investigating Workload and Efficiency<br><a href='http://arxiv.org/pdf/2606.04992'>论文</a></td><td>本文提出了一种用于手术器械处理与装配的多摄像头增强现实引导系统，旨在降低洗手护士的认知需求并提升操作效率。模拟手术的用户研究表明，该系统显著降低了护士的感知工作负荷，将任务完成时间缩短了21.3%，尤其使不熟悉器械的护士获益。
◆提出了无需额外标记的多摄像头6D位姿估计与头戴式显示器原位可视化相结合的手术引导方案。
◆采用纯合成数据训练6D位姿估计网络，利用已知物体实现连续相机校准，提升了算法的泛化能力与真实世界适用性。
◆设计了原位工具提示定位与逐步装配动画，并创新性结合凝视选择与脚踏板实现步进切换，满足术中无菌交互需求。</td></tr>
<tr><td>2026-06-03</td><td>FUSE-Flow: A Decoupled Framework for Calibration and Stateless Real-Time Multi-View Point Cloud Fusion<br><a href='http://arxiv.org/pdf/2606.04376'>论文</a></td><td>本文提出FUSE-Flow，一个将标定与实时多视角点云融合解耦的框架，解决了传统方法中二者紧密耦合导致的波动重建结果、累积误差和扩展性差的问题。核心贡献在于通过GMAC和FUSE两个协同模块，实现了无需标定板、密集图像或全局光束法平差的稀疏视角精确标定，以及线性时间内存消耗的无状态融合。框架中GMAC利用几何约束与多视图重建Transformer优化外参，FUSE则通过置信度加权和自适应空间哈希完成融合，且二者相互增强——精确位姿提升融合精度，置信感知融合修正标定偏差。在公共数据集和真实相机系统上的实验验证，FUSE-Flow在视觉效果、动态稳定性和可扩展性上均优于主流实时重建方法，为大规模实时三维重建提供了实用方案。
◆ 解耦设计：将标定与点云融合拆分为独立模块，避免冲突的优化目标，实现针对性改进。
◆ 几何对齐多视图标定（GMAC）：基于几何约束和Transformer实现稀疏视角标定，无需标定靶标、密集图像或全局BA。
◆ 置信引导无状态融合（FUSE）：结合置信度权重与自适应空间哈希，确保线性时间与内存开销，且支持实时运行。
◆ 双向增强机制：精确位姿提升融合准确性，同时置信度感知融合反向校正标定偏差，形成自优化闭环。</td></tr>
<tr><td>2026-06-03</td><td>A Geometry-Informed Computer Vision Method for Detecting and Examining Overtaking Vehicles From A Bicycle<br><a href='http://arxiv.org/pdf/2606.23699'>论文</a></td><td>该论文针对超车事件人工标注瓶颈，提出基于单目视频与几何约束的自动检测流水线，无需多传感器配置或相机标定。系统融合RT-DETR目标检测与ByteTrack多目标跟踪，通过基于透视投影原理的三阶段几何验证模块（方位角趋势、视尺寸增长、空间确认）滤除误检。在315个真实城市超车事件中取得97.8%召回率且零假阳性，平均提前2.44秒识别超车意图，84.1%超过1.5秒人类反应阈值。免标定横向距离估计方法在96个事件中达到13-14厘米误差，并发现33.3%的车辆横向通过距离低于5英尺法定阈值。

◆ 基于单目视频与几何约束的自动超车事件检测框架，摆脱多传感器与标定依赖
◆ RT-DETR检测与ByteTrack跟踪结合三阶段透视投影几何验证，显著降低误检
◆ 基于边界框几何特征的免标定横向距离估计方法，实现厘米级测量精度...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-01</td><td>Effective Multi-sensor Conditioning for Street-view Novel-view Synthesis<br><a href='http://arxiv.org/pdf/2606.01590'>论文</a></td><td>本文提出StreetNVS视频扩散框架，解决现有街景新视角合成方法未充分利用多传感器信号导致偏离轨迹时画质下降的问题。该方法将稀疏激光雷达的精确度量几何、环视图像的密集外观与相机位姿进行有效融合。
◆基于相对光线级位置编码的参考增强相机注意力模块，实现对上述三种信号的联合条件化处理。
◆两阶段课程训练策略，通过逐步增加激光雷达稀疏度来提升模型鲁棒性。
在Waymo数据集上，该框架在稀疏激光雷达条件下大幅超越现有基线，媲美使用十至百倍密集点云的方法，并能合成升降或旋转等极端偏离轨迹的连贯视频。</td></tr>
<tr><td>2026-05-29</td><td>Joint Multi-Camera LiDAR Extrinsic Calibration via Learned Pairwise Initialization and Geometric Refinement<br><a href='http://arxiv.org/pdf/2605.31576'>论文</a></td><td>现有基于学习的相机与激光雷达标定方法通常独立处理各对数据，忽视了多相机平台的刚体几何耦合，导致系统层面不一致。
◆提出了一种联合多相机激光雷达外参标定的两阶段框架，克服了独立估计导致的系统性不一致问题。
◆结合深度学习匹配与几何优化，先利用CMRNext独立生成各相机的初始外参及密集2D-3D对应关系，再通过多帧光束法平差进行联合优化。
◆在优化阶段引入重投影、单相机先验及相对位姿先验约束，成功将局部成对预测转化为全局一致的标定结果。
实验表明该方法提升了单相机精度和相机间一致性，在KITTI数据集上实现了0.89厘米的平移误差。
在域外Walkley数据集上，该方法将平移误差从108.6厘米大幅降至3.1厘米，验证了显式多相机耦合在单相机预测不可靠时的巨大优势。</td></tr>
<tr><td>2026-05-27</td><td>Beyond Binary: Sim-to-Real Dexterous Manipulation with Physics-Grounded Contact Representation<br><a href='http://arxiv.org/pdf/2605.28812'>论文</a></td><td>该论文针对接触密集型操作中触觉信号因仿真到现实差距难以有效迁移的问题，提出了一种基于物理原理的触觉表示方法。
◆提出基于物理原理的压力中心触觉表示法，既保留了密集的接触信息，又对仿真到现实迁移保持鲁棒性。
◆提出基于可微动力学的传感器校准方案，无需真实力测量即可估计触觉单元朝向以支持该表示。
◆在多指手的插孔和平衡球等盲态任务中实现零样本仿真到现实迁移，性能显著优于二值接触和原始触觉基线。
◆分析表明，基于该表示的策略能将物体质量等任务相关物理属性作为控制的涌现副产品进行编码。</td></tr>
<tr><td>2026-05-22</td><td>Calibration-Informative Region Selection for Online LiDAR--Camera Calibration in Agricultural Environments<br><a href='http://arxiv.org/pdf/2605.23580'>论文</a></td><td>本文提出了一种基于支撑图的在线激光雷达-相机多模态标定方法，旨在识别真正约束外参的观测并剔除噪声。该方法将标定过程解耦为初始标定、跨模态残差提取、支撑图估计和支撑感知优化四个功能模块，并基于无目标方法MDPCalib和CMRNext实现了具体应用。
◆提出密集标定支撑图，通过聚合对齐观测的跨模态一致性，突出标定证据持续可靠的空间区域。
◆揭示标定证据在空间和语义上的非均匀性，证明了特定语义区域能提供比其他区域更强的标定线索。
◆引入支撑感知优化机制，通过筛选标定信息丰富的区域进行精化，在KITTI数据集上有效提升了平移精度。</td></tr>
<tr><td>2026-05-22</td><td>Joint Target-Less Intrinsic and Extrinsic Camera-LiDAR Calibration using Deep Point Correspondences<br><a href='http://arxiv.org/pdf/2605.23397'>论文</a></td><td>本文提出了首个完全无标定靶的联合标定框架，利用深度像素-点对应关系同时估计包含径向切向畸变的相机内参和相机-激光雷达外参。
◆通过运动恢复结构实现相机内参的自动初始化。
◆将相机与激光雷达的匹配推广至包含畸变的未知内参原始图像。
◆将对应关系估计与内参和外参的联合非线性优化进行紧耦合。
在KITTI数据集上的实验表明，该联合标定方法不仅有效恢复了精确的相机内参，还进一步提升了外参的标定精度。</td></tr>
<tr><td>2026-05-14</td><td>CalibAnyView: Beyond Single-View Camera Calibration in the Wild<br><a href='http://arxiv.org/pdf/2605.14615'>论文</a></td><td>CalibAnyView针对传统相机标定受限于受控环境及现有单视图学习法缺乏跨视图几何一致性的问题，提出一种支持任意输入视图数量的统一标定框架。
◆构建了涵盖多相机模型、动态场景、真实运动轨迹与异构畸变的大规模多视图视频数据集。
◆开发多视图Transformer预测密集透视场，并融入几何优化框架以联合估计相机内参和重力方向。
◆通过显式建模跨视图几何一致性，突破了单视图限制，实现了对任意数量输入视图的支持。
实验表明，该方法在单视图下鲁棒性强，多视图下性能更优，全面超越现有技术，为野外3D重建与机器人感知提供了可靠基础。</td></tr>
<tr><td>2026-05-13</td><td>Calibration-Free Gas Source Localization with Mobile Robots: Source Term Estimation Based on Concentration Measurement Ranking<br><a href='http://arxiv.org/pdf/2605.13208'>论文</a></td><td>本文针对移动机器人使用低成本气体传感器时因环境干扰和非线性响应导致需频繁校准的问题，提出了一种免校准的气体源定位方法。
◆提出基于浓度测量相对排名的新型特征提取算法，利用动态积累数据集中测量值的相对排序替代绝对浓度。
◆通过比较收集数据与物理扩散模型之间的排名差异，估算整个环境中气体源位置的概率分布。
◆该方法彻底消除了对气体传感器进行频繁校准的依赖，有效克服了传感器非线性响应和环境因素的干扰。
高保真仿真和物理实验均表明，即使在使用未校准传感器的情况下，该方法也能保持一致的定位精度。
这使得该技术在实际危险环境的应急响应与部署中具有极高的适用性和应用前景。</td></tr>
<tr><td>2026-05-12</td><td>Mobile Traffic Camera Calibration from Road Geometry for UAV-Based Traffic Surveillance<br><a href='http://arxiv.org/pdf/2605.11900'>论文</a></td><td>本文提出了一种轻量级流水线，将单目倾斜无人机交通视频转换为局部度量俯视图表示，从而实现车辆方向、速度、航向和动态3D立方体的估计。
◆利用可见的道路几何特征计算图像坐标到度量地面坐标的单应性矩阵，避免了复杂的传感器标定。
◆通过估计车辆与地面的接触点，将观测结果投影至俯视图，直接从单目视频中提取车辆运动学和三维几何信息。
◆在UAVDT数据集上验证了该方法的有效性，为可部署的无人机交通摄像头及未来实时交通数字孪生系统奠定了实用基础。
实验也指出了远场车辆对单应性误差敏感及单平面假设的局限性，表明目前手动验证仍比全自动标定更可靠。</td></tr>
<tr><td>2026-05-11</td><td>StereoPolicy: Improving Robotic Manipulation Policies via Stereo Perception<br><a href='http://arxiv.org/pdf/2605.09989'>论文</a></td><td>该论文针对单目视觉在机器人操作中缺乏可靠深度线索和空间感知的问题，提出了StereoPolicy框架以增强几何推理能力。
◆提出直接利用同步双目图像对增强几何推理的框架，无需显式3D重建或相机标定。
◆采用预训练2D视觉编码器独立处理图像，并通过立体视觉Transformer融合表征，隐式捕捉空间对应和视差线索。
◆该框架可无缝集成基于扩散的策略和视觉-语言-动作策略，具有极强的兼容性。
实验表明，该方法在多个仿真基准及真实机器人桌面与双手操作任务中，均一致优于RGB、RGB-D和点云等基线方法。
该研究证实了双目视觉是连接2D预训练表征与3D几何理解的可扩展且鲁棒的模态。</td></tr>
<tr><td>2026-05-10</td><td>VFM-SDM: A vision foundation model-based framework for training-free, marker-free, and calibration-free structural displacement measurement<br><a href='http://arxiv.org/pdf/2605.09677'>论文</a></td><td>◆提出VFM-SDM框架，将视觉基础模型用于结构位移测量，实现无需任务特定训练、无需布设标记、无需人工相机标定的非接触式部署。

◆框架结合VFM推断的相机参数估计与点跟踪，并通过三角测量重建结构多方向位移。

◆引入结构几何约束，抑制不符合物理规律的偏差，提升位移估计的一致性与鲁棒性。

◆构建了服役人行桥多模态现场数据集，并提出统一基准测试流程，增强方法评估的可复现性。

◆实验结果显示其在竖向和横向位移上具有较低幅值误差、较高时间相关性和较小峰峰值误差，证明了真实场景下的应用潜力。</td></tr>
<tr><td>2026-05-06</td><td>Optimal Uncertainty-Aware Calibration for the AX=YB Problem<br><a href='http://arxiv.org/pdf/2605.04809'>论文</a></td><td>◆论文提出了一个面向AX=YB手眼标定问题的通用优化框架，能够同时求解并更新相关标定参数。
◆方法基于李代数构建迭代算法，在优化过程中严格保持旋转和平移等结构约束，避免传统方法中约束破坏的问题。
◆相比传统分步求解，该方法支持参数同步更新，并能获得近似全局最优解，提高了标定稳定性。
◆针对真实工业场景中数据不确定性难以精确建模的问题，论文不直接建立噪声模型，而是引入相对不确定性度量来动态调整优化过程。
◆论文还设计了有效的初值生成策略，以提升收敛效率、整体稳定性和估计精度。
◆仿真和真实实验表明，该方法在高不确定性数据下显著优于现有方法，合成数据中精度至少提升67%。</td></tr>
<tr><td>2026-05-02</td><td>TT4D: A Pipeline and Dataset for Table Tennis 4D Reconstruction From Monocular Videos<br><a href='http://arxiv.org/pdf/2605.01234'>论文</a></td><td>本文提出了TT4D，这是一个大规模高保真的乒乓球4D重建数据集，包含逾140小时的单双打比赛视频及多模态标注。
◆提出先提升后分割的全新重建流水线，通过学习型网络先将未分割的2D轨迹提升至3D再进行时间分割，解决了传统2D分割在遮挡和多视角下易失效的问题。
◆设计的学习型提升网络具备推断球体旋转、处理不可靠检测以及在高遮挡下成功重建轨迹的能力。
这种核心设计使该流水线成为目前唯一能从通用视角单目广播视频中重建乒乓球比赛的方法。
通过球拍撞击时的姿态与速度估计及训练对抗回合生成模型两项下游任务，验证了该数据集的高保真度。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-undistortion'>Sensor Undistortion (79篇)</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-15</td><td>Your Data Manifold is Secretly a Reward Model: Shell-LCC for Text-to-Video Generation<br><a href='http://arxiv.org/pdf/2606.30248'>论文</a></td><td>◆论文提出“数据流形本身就是奖励模型”的观点，通过显式建模高质量SFT数据的流形结构，为T2V扩散模型提供密集、可微且低成本的奖励信号。
◆方法基于Local Coordinate Coding捕捉数据流形的“骨架”，引导视频潜变量靠近高质量数据分布，从而提升生成真实感。
◆针对传统LCC容易产生均值回归、导致细节丢失的问题，论文提出Shell-LCC，将流形表面建模为各向同性“壳层”，更贴近真实高密度区域。
◆该方法无需额外奖励模型、大规模人工标注或昂贵DPO训练，即可改善视频质量，尤其缓解低层次失真问题。
◆实验表明，Shell-LCC能增强高频细节、减少过平滑伪影，并有效减轻运动模糊，提升文本到视频生成的整体视觉质量。</td></tr>
<tr><td>2026-07-15</td><td>DriveFace: A Cross-Spectral Through-Glass Face Dataset for On-the-Move Vehicular Border Control<br><a href='http://arxiv.org/pdf/2607.13515'>论文</a></td><td>本文针对跨境边境检查中车载移动场景下人脸识别的数据缺失问题，提出了DriveFace数据集。该数据集采集自车辆通过检查站时的近红外(NIR)视频，并与基于智能手机的预注册人脸数据进行配对，覆盖了运动模糊、光照变化、遮挡及跨光谱注册等真实挑战。基准实验表明，现有最先进模型在该场景下性能明显受限，验证了数据集的必要性。

◆ 构建了首个面向车载移动边境控制的跨玻璃人脸数据集DriveFace，填补了该场景下公开基准的空白。

◆ 数据集融合NIR车辆通行视频与智能手机预注册图像，模拟真实跨光谱注册场景。

◆ 系统性地涵盖了运动模糊、复杂光照、遮挡及跨玻璃成像等实际挑战。

◆ 通过基线评测揭示了现有SOTA模型在真实车载场景下的性能局限，为后续算法研究指明方向。</td></tr>
<tr><td>2026-07-15</td><td>WNOJ-LIO: A White-Noise-on-Jerk Motion-Prior EKF for High-Dynamic LiDAR-IMU Fusion<br><a href='http://arxiv.org/pdf/2607.13405'>论文</a> | <a href='https://github.com/LvJohny/wnoj-ekf-lio.git'>代码</a></td><td>本文针对高动态场景下LiDAR-IMU里程计面临的扫描内运动畸变与IMU振动噪声耦合问题，提出了基于白噪声加速度先验（WNOJ）的扩展卡尔曼滤波融合框架WNOJ-LIO。该方法在R^3×SO(3)上采用解耦的WNOJ过程模型进行状态预测，并将IMU视为高频测量源而非状态传播驱动，从而避免惯性噪声直接污染去畸变结果和点云配准。

◆在平移和旋转空间上分别建立解耦的WNOJ先验过程模型，实现独立的运动学建模与状态传播。
◆将IMU从传统状态传播驱动角色转变为高频测量源，抑制振动噪声向点云配准环节的传递。
◆推导闭式协方差传播公式，弥合批式WNOJ高斯过程轨迹先验与递归滤波之间的理论鸿沟。

仿真与真实赛车实验（最高速度208 km/h）表明，该方法在去畸变、加速度/角速度去噪及定位精度上均优于FAST-LIO基线。</td></tr>
<tr><td>2026-07-13</td><td>Event-RGB Adaptive Tracking for Nighttime Highway Perception<br><a href='http://arxiv.org/pdf/2607.11646'>论文</a> | <a href='https://github.com/haidongwang96/SEHN'>代码</a></td><td>本文针对高速公路夜间场景下传统RGB相机感知性能退化问题，提出了一种新的多模态融合跟踪方案。其核心思想是打破现有方法中僵化的传感器优先级策略，将异步事件流与RGB帧统一到联合数据关联优化框架中。系统利用自适应扩展卡尔曼滤波，通过NIS统计量在线估计测量噪声，动态调节两种模态的融合权重，使事件流在暗光或高速运动下发挥主导作用，而RGB帧在明亮或静态条件下提供互补信息。此外，作者还基于CARLA仿真器构建了大规模合成数据集SEHN，涵盖白天、无路灯夜间、有路灯夜间等多种环境与交通密度，填补了事件相机高速公路感知领域公开数据集的空白。实验表明该方法在低光照、高速等挑战性场景下显著优于单一模态基线。整体工作为夜间智能交通感知提供了从算法到数据的基础支撑。

◆ 提出JEAT联合事件-RGB自适应跟踪框架，统一异步融合与数据关联，避免硬编码优先级。
◆ 设计基于NIS统计的自适应扩展卡尔曼滤波，动态估计噪声并自适应加权多模态测量。
◆ 发布大规模合成数据集SEHN，覆盖多样化光照与交通条件，弥补事件式高速公路数据集的空白。</td></tr>
<tr><td>2026-07-13</td><td>Diffusion MRI preprocessing affects ADC estimation and automatic PI-RADS v2.1 classification in bi-parametric prostate MRI<br><a href='http://arxiv.org/pdf/2607.11385'>论文</a></td><td>本文系统研究了扩散加权成像(DWI)预处理策略对前列腺MRI中表观扩散系数(ADC)估计和自动PI-RADS分类的影响。研究基于fastMRI前列腺队列的268例数据,依次应用去噪、吉布斯环形伪影校正和微分同胚配准进行磁敏感畸变校正,比较了线性最小二乘(LLS)和迭代加权LLS(IWLLS)两种ADC估计方法,并训练3分类DenseNet预测PI-RADS评分。结果显示,不同预处理流程之间ADC值存在统计学显著差异,LLS与IWLLS生成的ADC图数值上等价;多数数据集间ADC值保持高度线性关系(PCC约0.99),而畸变校正因将DWI重新对齐到T2w解剖结构,PCC降至约0.90;完整预处理数据集在高风险PI-RADS类别中取得了最佳的AUROC和灵敏度,且产生最少的高风险类过度自信错误预测,在临床分诊中具有重要价值。

◆ 首次系统比较了去噪、吉布斯校正和畸变校正等DWI预处理步骤对前列腺MRI下游分析的级联影响,揭示畸变校正是改变ADC值和提升分类性能的关键步骤。

◆ 证实LLS与IWLLS在ADC估计上数值等价,为临床和研究中选择计算更简单的LLS方法提供了依据。

◆ 证明完整DWI预处理流程能显著提升DenseNet对高风险PI-RADS类别的自动分类性能,并降低过度自信的假阴性预测,具有临床分诊价值。</td></tr>
<tr><td>2026-07-13</td><td>HandFlow: Fully Generative 4D Hand Recovery with Flow Matching<br><a href='http://arxiv.org/pdf/2607.11221'>论文</a></td><td>该论文提出HandFlow，一个基于流匹配的全生成式框架，用于从单目视频中恢复时序一致的3D手部姿态与形状。现有判别式方法缺乏时序上下文且预测易抖动，时间模型虽能提升一致性但作为确定性回归器在遮挡和运动模糊下表现脆弱，因此作者采用生成式建模范式学习合理手部运动先验。HandFlow通过单次ODE积分对整个时间窗口的MANO参数进行去噪，无需自回归解码，核心采用Flux风格双流Transformer捕获长程依赖，并引入置信度感知的连续掩码机制融合可学习掩码标记以处理噪声或缺失观测。实验表明该方法在DexYCB和HOT3D上达到最先进性能，世界空间姿态误差降低超30%，加速度误差最低，且在单GPU上以47fps重建150帧序列，速度约为此前最快视频方法的12倍。

◆ 提出基于流匹配的全生成式4D手部恢复框架，通过单次ODE积分对整段时序MANO参数去噪。
◆ 设计Flux风格双流Transformer，无需自回归解码即可捕获长程时序依赖。
◆ 提出置信度感知的连续掩码机制，融合可学习掩码标记以鲁棒处理噪声与缺失观测。</td></tr>
<tr><td>2026-07-12</td><td>MRUF: Multi-granularity Routing with Uncertainty-Aware Fusion for Robust Multimodal Sentiment Analysis<br><a href='http://arxiv.org/pdf/2607.10599'>论文</a></td><td>针对多模态情感分析中模态质量差异导致传统融合过度信任不可靠模态的问题，本文提出可靠性感知融合方法MRUF。该方法融合多粒度路由与不确定性校准，对情感相关表征进行子空间级与模态级路由分配。

◆ 利用留一法误差增量作为监督信号，自动估计各话语下模态的相对重要性，实现数据驱动的权重学习。
◆ 预测模态级不确定性并通过逆方差加权精修门控，使高不确定性模态获得更低融合权重，提升融合鲁棒性。
◆ 引入模态不变的对比对齐损失，稳定共享表征空间，增强跨模态语义一致性。

在CMU-MOSI和CMU-MOSEI数据集的对齐与非对齐实验设置中，MRUF均稳定优于强基线模型。机制分析进一步验证了预测不确定性越高的模态在融合时被赋予的权重越低，证实了方法的有效性与可解释性。</td></tr>
<tr><td>2026-07-11</td><td>BOCCHI: A More Realistic and Challenging Benchmark for Local Motion Blur Detection with MSDCT-UNet<br><a href='http://arxiv.org/pdf/2607.10427'>论文</a></td><td>本文针对局部运动模糊检测任务,指出现有基准测试使模型依赖梯度捷径而难以泛化的问题。为此作者提出了两大核心贡献:一方面构建了真实拍摄的BOCCHI基准数据集,其清晰区域与模糊梯度分布存在重叠,有效规避了梯度捷径问题;另一方面设计了MSDCT-UNet网络,采用频域感知的编码-解码结构,通过多尺度离散余弦变换先验提升检测性能。

◆ 构建BOCCHI真实拍摄基准,首次通过清晰区域与模糊梯度分布的重叠设计来消除梯度捷径,使评估更贴近真实应用场景。

◆ 提出MSDCT-UNet,引入多尺度DCT先验与DCT Attention及FiLM模块,在频域层面增强模型对模糊特征的捕获能力。

◆ 验证方法在BOCCHI上取得最优mIoU和边界定位性能,且仅用633张训练图像即在跨数据集迁移中超越其他训练来源,体现了强泛化能力。</td></tr>
<tr><td>2026-07-10</td><td>Event Stream based Multi-Modal Video Anomaly Detection: A Benchmark Dataset and Algorithms<br><a href='http://arxiv.org/pdf/2607.09114'>论文</a></td><td>本文针对传统视频异常检测在光照变化、快速运动和复杂背景下鲁棒性不足的问题，提出了基于事件相机的多模态视频异常检测框架EVAD。该框架联合利用可见光视频和事件流，事件相机以高时间分辨率异步捕捉亮度变化，对运动模糊和极端光照具有天然鲁棒性。论文构建了大规模可见光-事件基准数据集TJUTCM-Pha，包含6.3亿事件和376,368帧视频，涵盖多样化光照、运动模式和背景复杂度，填补了事件异常检测数据集的空白。设计了对比式多模态预训练框架，通过对齐事件流、可见光视频和文本描述的语义嵌入来学习判别性事件表示，并采用自适应融合模块动态整合事件时序线索与视频空间语义。

◆ 构建大规模可见光-事件多模态异常检测基准数据集TJUTCM-Pha，涵盖6.3亿事件与37万余帧视频，填补该领域真实可扩展数据集的空白。
◆ 提出对比式多模态预训练框架，跨模态对齐事件流、视频与文本语义，习得判别性强的事件表示。
◆ 设计自适应融合模块，动态整合事件时序运动线索与视频空间语义特征，显著提升对光照变化等环境干扰的鲁棒性。</td></tr>
<tr><td>2026-07-10</td><td>A Numerically-Robust ROS 2 Port of iG-LIO: Diagnosing and Fixing Toolchain-Induced Failures in Incremental GICP LiDAR-Inertial Odometry<br><a href='http://arxiv.org/pdf/2607.09947'>论文</a> | <a href='https://github.com/Forestry-Robotics-UC/ig_lio/tree/ros2-jazzy'>代码</a></td><td>本文报告了将iG-LIO（一种紧耦合的LiDAR-惯性里程计算法）从ROS 1迁移到ROS 2 Jazzy的开源移植工作，并重点诊断了迁移过程中出现的环境诱导型数值失效问题。研究发现，在保持估计算法完全不变的前提下，编译运行后仍出现NaN发散，其根源在于现代ROS 2工具链的两个问题：一是服务质量(QoS)配置不匹配导致IMU数据被静默丢弃和重排序，二是oneTBB与Eigen组合中并行归约累加器未初始化。

◆QoS不匹配导致IMU静默丢失与乱序的诊断与修复

◆oneTBB与Eigen并行归约累加器未初始化的根源定位与解决

◆修正Ouster点云字段解析以适配新版本硬件，实现正确去畸变

◆新增Velodyne Velarray M1600传感器支持

◆为Livox提供编译时门控CustomMsg路径与无驱动的PointCloud2标准路径（如Mid-360）

◆通过YAML文件暴露运行时参数配置

该移植结果已在Ouster OS0 Rev7、Ouster OS1 Rev7和Livox MID-360三款硬件上完成实测验证。</td></tr>
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
<tr><td>2026-07-02</td><td>Shift Variant Image Degradation and Restoration Using Singular Value Decomposition<br><a href='http://arxiv.org/pdf/2606.25818'>论文</a></td><td>◆论文提出了一种基于奇异值分解的移变运动模糊图像复原框架，针对传统单一卷积核难以描述的空间变化退化问题。

◆其核心创新是用位置相关PSF构建移变成像算子，将退化过程统一建模为线性系统并进行SVD分析。

◆论文引入奇异值能量保留准则，系统选择小奇异值数量，以在抑制噪声放大和保留图像细节之间取得平衡。

◆方法覆盖双向线性运动、高斯运动和简谐运动三类一维移变PSF，验证了模型的适用性。

◆实验表明，该SVD稳定反演策略能够有效恢复图像细节、减轻模糊伪影，并揭示移变复原问题的病态特征。</td></tr>
<tr><td>2026-07-01</td><td>A First Exploration of Neuromorphic OT-CFM for Multi-Speaker VSR<br><a href='http://arxiv.org/pdf/2606.31225'>论文</a></td><td>◆论文提出LipsFlow，将RGB视频转为高时间分辨率事件流，利用神经形态视觉捕捉微秒级唇部动态，提升多说话人VSR在运动模糊、遮挡和细微发音下的鲁棒性。
◆系统结合ByteTrack与TalkNet，对多说话人场景进行跟踪和主动说话人检测，切分为单说话人片段以实现更聚焦的识别。
◆引入OT-CFM在语义潜空间中建模事件特征，通过确定性直线轨迹生成，将推理压缩到仅两步ODE，显著降低延迟。
◆设计双层语义监督，将token级BERT权重绑定与句子级先验结合，缓解同唇形词歧义问题。
◆实验表明该方法在240 ms延迟下达到22.3% WER，建立了高效且鲁棒的事件驱动多说话人VSR新范式。</td></tr>
<tr><td>2026-06-30</td><td>Event-based Gaze Control System for Accurate Real-time Spin Estimation in Professional Ball Games<br><a href='http://arxiv.org/pdf/2606.26780'>论文</a></td><td>◆提出一套事件相机主动视觉系统，结合高速振镜与可调焦长焦镜头，在高速球类运动中持续放大、对焦并跟踪未改装球体。
◆设计混合跟踪策略，将事件驱动的2D检测用于实时居中，并利用3D定位结果进行重初始化，提高比赛场景鲁棒性。
◆提出球面事件对比度最大化方法s-CMax，实现跨乒乓球、棒球、网球和高尔夫的高精度离线旋转估计。
◆面向实时乒乓球应用，构建由伪真值训练的不确定性感知CNN，并结合GPU批量对比度最大化进行快速精修。
◆系统在职业乒乓球三视角实验中达到3毫秒延迟、750Hz吞吐率，并取得8.8%转速幅值误差和6.4度旋转轴误差。</td></tr>
<tr><td>2026-06-30</td><td>Distortion-Corrected Diffusion MRI Using Rotated-View EPI and Joint Field-Map/Image Estimation with Gaussian Primitives<br><a href='http://arxiv.org/pdf/2606.31521'>论文</a></td><td>本文针对扩散MRI中EPI成像因B0场不均匀性导致的几何畸变问题，提出了一种物理驱动的联合校正框架。传统方法采用先并行成像重建、再估计B0场、最后校正畸变的串行流程，在高加速因子和高b值下重建伪影和低信噪比会严重制约校正质量。本文方法直接从k空间数据联合估计B0场和无畸变图像，跳过了中间重建步骤，从而突破了串行流程的性能瓶颈。

核心创新点如下：

◆ 提出基于MRI物理前向模型的联合B0场与无畸变图像估计框架，直接从k空间数据出发，无需依赖并行成像的中间重建结果。

◆ 将图像和B0场均建模为高斯基元（Gaussian primitives）的叠加，参数化连续且显式，能够同时刻画平滑区域和组织边界。

◆ 支持旋转视角（rotated-view）EPI采集无需插值，使畸变分布于多个相位编码方向，提升点扩散函数各向同性并增强B0估计的约束。

◆ 将扩散加权图像建模为实数且非负，图像相位被吸收进每次采集的相位因子，简化了模型同时保持物理一致性。

在体内脑部扩散EPI数据上，该方法与无畸变结构参考的脑边界吻合度最佳，且在高b值和高加速条件下相较串行方法提升最为显著，同时在细节保真和噪声抑制方面也有明显优势。</td></tr>
<tr><td>2026-06-28</td><td>Again-Pose: Anchor-Guided Adaptive Inter-Frame Motion Cues Propagating for High-quality Human Pose Reconstruction<br><a href='http://arxiv.org/pdf/2606.29230'>论文</a></td><td>Again-Pose提出了一种锚点引导的自适应帧间运动线索传播框架，专门用于解决严重运动模糊和遮挡等极端场景下从无约束视频重建3D人体姿态的难题。该方法将退化帧的姿态估计重新定义为运动引导的恢复任务，通过特征显著性显式识别高质量锚点帧，并将其可靠的运动学线索传播以&quot;修复&quot;中间退化帧的姿态，从而克服了现有隐式时序注意力方法在视觉严重退化时因特征坍缩而失效的局限性。

◆ 基于特征显著性的锚点帧选择机制：显式筛选高质量参考帧作为可靠信息来源，避免退化特征的误导。

◆ 双路径运动感知模块：精细建模帧间动态，提取细粒度的运动学线索。

◆ 差异加权融合模块：自适应加权传播运动线索，有效抑制误差漂移。

◆ 在Human3.6M、3DPW、PoseTrack及高难度的FineDiving数据集上均显著优于现有最优方法，在其他方法失败的场景中仍能恢复出合理稳定的姿态。</td></tr>
<tr><td>2026-06-25</td><td>Confidence-Aware Tool Orchestration for Robust Video Understanding<br><a href='http://arxiv.org/pdf/2606.26904'>论文</a></td><td>该论文揭示了视频推理语言模型普遍存在的&quot;盲目信任问题&quot;，即隐式假设所有输入帧同等可靠，导致在运动模糊、眩光、遮挡等真实扰动下准确率下降15-30个百分点而模型毫无察觉。为此提出Robust-TO智能体框架，将逐帧可信度显式融入推理全过程。

◆提出&quot;盲目信任问题&quot;概念，系统揭示现有视频推理模型在帧级证据可靠性评估上的根本缺陷。

◆设计统一证据接口，将异构视觉感知工具（目标检测、运动追踪、OCR、动作识别等）封装为标准化输出格式，包含具体预测、时序定位和校准可信度分数。

◆提出基于可靠性-相关性分数的帧选择机制，结合高/中/低三级证据合成流程，实现推理过程中的动态证据加权。

◆构建融合正确性、证据可靠性与效率的置信度-成本GRPO奖励函数，联合优化推理鲁棒性与计算开销。

实验在两个视频推理基准的八项任务上取得56.4%平均准确率，超越最强开源基线10.6个百分点，并优于Gemini-2.5-Pro；在五种真实扰动下仍保持54.3%准确率，干净到退化场景的精度跌幅为所有方法中最小。</td></tr>
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
<tr><td>2026-06-19</td><td>Context-Aware Autoregressive Diffusion for Gloss-Wise Sign Language Production<br><a href='http://arxiv.org/pdf/2606.21234'>论文</a></td><td>◆ 论文提出GARD，一种面向逐词素生成的上下文感知自回归扩散框架，用于提升句子级手语生成的自然性与可控性。
◆ 不同于一次性生成整段序列的方法，GARD按gloss逐段合成，有效缓解长句中的时间漂移和手部运动模糊问题。
◆ 模型同时利用语义语言上下文与运动学上下文建模词素间协同发音，使单个gloss生成更准确且与上下文一致。
◆ 论文设计Inter-Gloss Transition Guidance，通过梯度引导对齐相邻gloss边界姿态，增强过渡连续性。
◆ 还引入Global Motion Harmonizer，对整体运动序列进行全局细化，在Phoenix-T和CSL-Daily上取得优于现有方法的语言准确性与运动相似度。</td></tr>
<tr><td>2026-06-18</td><td>ARTEMIS: Agent-guided Reliability-aware Temporal Mask Evolution for Imperfectly Supervised Video Polyp Segmentation<br><a href='http://arxiv.org/pdf/2606.20161'>论文</a> | <a href='https://github.com/wangtong627/ARTEMIS'>代码</a></td><td>◆ ARTEMIS面向不完美监督的视频息肉分割，统一处理点、涂鸦和少量密集标注等低成本监督，缓解伪标签边界泄漏、形状退化和时序不一致问题。
◆ 提出“辩论-裁判”式视觉语言智能体，在弱监督下自动筛选可靠的时序锚点，提升伪标签初始化质量。
◆ 利用SAM2进行双向时序传播，从可靠锚点逐步修正不可靠或未标注帧，实现可靠性感知的时序掩码演化。
◆ 设计时序可靠性感知鲁棒学习机制，包括参考选择、参考原型传输模块和鲁棒损失，以传递目标身份并降低噪声监督影响。
◆ 在SUN-SEG和CVC-ClinicDB-612的涂鸦、点标注及少标签设置下取得领先性能，验证了框架的有效性与临床应用潜力。</td></tr>
<tr><td>2026-06-18</td><td>NeoLoc-68: End-to-end 68-point neonatal facial landmark localisation in neonatal clinical environments<br><a href='http://arxiv.org/pdf/2606.20823'>论文</a></td><td>◆提出首个端到端68点新生儿面部关键点定位模型NeoLoc-68，面向真实临床环境中的疼痛评估需求。
◆整合11个公开数据集的37,459张单脸图像，并加入1,123帧临床新生儿手工标注数据，统一为68点标注体系。
◆将YOLO关键点模型适配为新生儿面部关键点回归器，并利用预训练新生儿人脸检测器权重初始化，提升泛化能力。
◆模型在公开数据集上取得当前最优性能，NME、FR和AUC等指标均表现突出。
◆在临床测试集上，模型面对遮挡、姿态变化和运动模糊仍保持较低检测失败率，微调后性能进一步提升，为非接触式新生儿疼痛与健康监测提供基础。</td></tr>
<tr><td>2026-06-18</td><td>UNSEEN: Uncertainty-aware Navigation via Sparse Estimation in Unknown Environments<br><a href='http://arxiv.org/pdf/2606.20755'>论文</a></td><td>◆UNSEEN提出一种仅依赖前视相机的未知环境视觉导航框架，面向资源受限机器人降低传感器复杂度和部署成本。
◆其核心创新是将定位、建图与规划统一到不确定性感知框架中，显式建模运动指令与感知质量之间的耦合关系。
◆系统以6Hz估计稀疏地图、机器人位姿及其不确定性，并将这些信息持续传递到导航决策中。
◆UNSEEN-Plan采用滚动时域规划，同时优化任务推进和状态估计精度，从而主动选择更利于感知的轨迹。
◆实验表明，UNSEEN-SLAM将绝对平移误差降低9.8%，规划模块最高提升45%估计精度，并在真实未知环境中实现100%任务成功率。</td></tr>
<tr><td>2026-06-17</td><td>Pinning Down the Geometry of the Type Ic Broad-Line Supernova 2026gzf<br><a href='http://arxiv.org/pdf/2606.18881'>论文</a></td><td>◆论文首次对Ic-BL型超新星SN 2026gzf在X射线激波 breakout 后4.6天和16.5天开展成像偏振与光谱偏振观测，约束其早期爆炸几何。

◆持续较低的连续谱偏振表明其外层抛射物近似球形，说明爆炸未显著破坏前身星外壳结构。

◆第16.5天Ca II近红外三重线出现超过1.5%的高偏振，揭示氧燃烧产物的激发结构具有明确对称轴。

◆研究发现Ca II线同时包含高速主成分和更外层的次级成分，后者偏振显示外层激发几何非轴对称且更复杂。

◆通过三维蒙特卡洛建模，论文推断观测视角约为相对对称轴40度，可合理再现Ca II线的光谱与偏振特征。</td></tr>
<tr><td>2026-06-17</td><td>Learning to Distort: Weakly-Supervised Image Quality Transfer for Prostate DWI Correction<br><a href='http://arxiv.org/pdf/2606.18869'>论文</a></td><td>◆ 提出一种弱监督图像质量迁移框架，用图像级质量标签（失真/未失真）替代昂贵的体素级配对数据来学习前列腺DWI畸变相关表征。
◆ 在预训练特征空间中构建“质量原型”，利用IQA信号监督从未失真图像到失真图像的质量迁移。
◆ 提出弱监督原型流匹配算法，显式约束生成轨迹逼近失真原型，从而合成更真实的磁敏感伪影。
◆ 通过先“学习生成真实畸变”来构造伪配对数据，再训练正向校正模型，规避了直接无配对校正的不稳定性。
◆ 实验显示该方法生成的伪影能模拟真实临床诊断干扰，并在PI-RADS和Gleason评分等下游任务及外部数据上优于CycleGAN、UNIT-DDPM、OT-FM等方法。</td></tr>
<tr><td>2026-06-17</td><td>Optimal transport of signed fractal measures with dimensional distortion: a variational characterization<br><a href='http://arxiv.org/pdf/2606.19631'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-12</td><td>An ultra-wide-bandgap semiconductor photodetector for linear measurement of bright sub-bandgap light<br><a href='http://arxiv.org/pdf/2606.07807'>论文</a></td><td>本文提出了一种亚带隙氮化铝光电探测器，解决了传统探测器在中低强度光下易饱和的问题。
◆实现了对超过40瓦每平方厘米的超强蓝光的非饱和线性响应。
◆在高达300摄氏度的高温下依然保持无失真的线性响应。
◆揭示了金属-氮化铝肖特基结处深能级点缺陷介导光响应的物理机制。
◆通过掺杂和接触工程证明，窄空间电荷区是实现超强光探测与精确测量的关键。
该研究为超宽禁带半导体器件在航空航天及核电等极端条件下的可靠运行提供了工程策略。</td></tr>
<tr><td>2026-06-12</td><td>HumP-KD: A Hybrid Uncertainty-Aware Multi-Stage Progressive Knowledge Distillation Framework for Efficient Fire Classification<br><a href='http://arxiv.org/pdf/2606.14684'>论文</a></td><td>本文提出了HumP-KD框架，用于在资源受限硬件上实现高效且可部署的实时火灾分类。
◆提出混合异构教师知识蒸馏，将冻结的Swin-Tiny和ViT-Base及其Meta-MLP集成的知识蒸馏到轻量级MobileViT-S中。
◆设计层次渐进式知识蒸馏，通过层次特征构建器生成融合空间注意力掩码，选择性引导蒸馏关注判别性区域。
◆引入多阶段知识蒸馏机制，在训练中逐步激活三个蒸馏阶段。
实验表明该方法F1分数达0.9876，显著优于无蒸馏基线，且具备强鲁棒性与泛化能力。
学生模型仅4.94M参数，参数缩减最高达17.5倍，CPU帧率达37.72FPS，完全满足实时部署需求。</td></tr>
<tr><td>2026-06-12</td><td>FEMOT: Multi-Object Tracking using Frame and Event Cameras<br><a href='http://arxiv.org/pdf/2606.14094'>论文</a> | <a href='https://github.com/Event-AHU/FEMOT'>代码</a></td><td>针对RGB相机在复杂场景下性能受限且RGB-事件多目标跟踪缺乏数据的问题，本文提出了FEMOT数据集及FEMOTR框架。
◆构建了大规模RGB-事件多目标跟踪数据集FEMOT，涵盖多样真实场景与14个挑战属性，填补了该领域缺乏高质量标注数据的空白。
◆基于该数据集评估了十余种先进跟踪器，建立了全面的综合基准，为未来研究提供可靠平台。
◆提出多模态跟踪框架FEMOTR，在频域中对RGB和事件特征进行解耦与融合。
该机制有效利用了两者的互补特性，实现了更鲁棒的目标定位与身份关联。
在FEMOT和DSEC-MOT数据集上的广泛实验充分验证了所提方法的有效性。</td></tr>
<tr><td>2026-06-11</td><td>Revisiting Vehicle Color Recognition in Long-Tailed Surveillance Scenarios<br><a href='http://arxiv.org/pdf/2606.13625'>论文</a> | <a href='https://github.com/viniciusorru/vcr-synthetic'>代码</a></td><td>该论文针对监控场景下车辆颜色识别中存在的严重类别不平衡问题,基于真实世界数据集 UFPR-VeSV 开展了系统性研究。作者结合生成式数据增强、现代视觉表征、损失重加权、学习率调度、颜色安全增强、前景感知预处理与集成融合等多种策略,显著提升了对稀有颜色类别的识别性能。最终方法在微观准确率上达到 94.6%,宏观准确率达 79.7%,相比最新文献宏观准确率提升 8.2 个百分点。此外,作者通过人工错误分析指出,部分剩余错误即使对人类标注者也存在视觉模糊性,从而揭示了基于颜色的车辆识别在非受限监控图像中的实际局限。

核心创新点如下:

◆ 首次系统性地将文本条件生成(RunDiffusion/JuggernautXL)与图像条件颜色编辑(Gemini 2.0 Flash)两种现成生成式策略应用于车辆颜色少数类的合成增强。

◆ 提出综合性训练流程,将合成数据与损失重加权、颜色安全数据增强、前景感知预处理及集成融合相结合,有效缓解长尾分布问题。

◆ 在 UFPR-VeSV 数据集上取得 SOTA 性能,宏观准确率较已有文献提升 8.2 个百分点,显著改善稀有颜色类别的识别效果。

◆ 通过人工错误分析揭示了颜色识别任务的固有视觉模糊性,为该领域的性能上限提供了实证依据。

◆ 开源了所生成的合成图像与完整源码,促进后续在长尾监控场景下的可复现研究。</td></tr>
<tr><td>2026-06-11</td><td>Observation of intertwined charge density wave order and superconductivity in Janus monolayer<br><a href='http://arxiv.org/pdf/2606.13828'>论文</a></td><td>◆首次系统地用第一性原理研究Janus单层1T-ZrSeTe中的2×2×1电荷密度波与超导不稳定性。
◆揭示M点显著声子软化源于增强的电子-声子耦合，以及带间和带内散射共同诱发的电子不稳定性。
◆发现CDW晶格畸变会重构能带并打开小的间接带隙，使体系由半金属转变为半导体。
◆证明用Se替代一层Te会显著降低畸变能量收益，从而削弱相较于ZrTe2单层的CDW不稳定性。
◆指出电子关联和双轴应变可作为调控CDW与超导不稳定性的有效手段。
◆在高温未畸变相中预测声子介导的双能隙超导，并发现SOC会改变电子态且降低超导转变温度。</td></tr>
<tr><td>2026-06-10</td><td>Spatially Coupled Phase-to-Depth Calibration for Fringe Projection Profilometry<br><a href='http://arxiv.org/pdf/2606.11601'>论文</a></td><td>针对条纹投影轮廓术中逐像素独立拟合导致的空间不一致和结构化伪影问题，本文提出了一种空间耦合的相位深度标定方法。
◆提出空间耦合的相位深度变换模型，所有像素共享由全局相位标量与仿射空间项构成的单个低维映射，替代独立的逐像素拟合，并可选附加有界平滑修正场。
◆引入原生网格配对方案，直接在参考相机网格上构建相位深度标定对，将立体三维平面沿原生光线采样回相机网格，从而避免对相位图进行纠正。
在具备高分辨率真值的牙科目标上，该方法取得了与主动立体参考相当的点对面均方根误差（约12微米）。
相比传统逐像素标定法，它不仅大幅提升了空间一致性，还将运行时映射简化为少量的逐像素元素级操作，参数存储几乎可忽略。</td></tr>
<tr><td>2026-06-10</td><td>TESS detection of periodic brightness variations during the rise of classical nova PGIR22akgylf<br><a href='http://arxiv.org/pdf/2606.12532'>论文</a></td><td>这篇论文利用TESS空间望远镜对缓慢上升型经典新星PGIR22akgylf进行了高精度光度监测,覆盖了新星发现后3到16天的关键阶段,并辅以地面观测追踪了其长达约133天的完整上升过程。研究团队探测到周期为0.1802±0.0012天、峰峰振幅约0.02星等的周期性亮度变化,该信号在TESS观测的两周内保持稳定,暗示其源于双星轨道运动。作者据此推断伴星为矮星,并提出周期性信号是由于双星轨道运动使新星包层(此时尺度与双星轨道间距相当)发生形变所致,从而揭示了公共包层相互作用在该新星壳层抛射中的重要作用。

◆ 首次在经典新星上升阶段利用TESS高精度光度数据探测到稳定的周期性亮度调制信号,为研究新星包层结构提供了新观测窗口。

◆ 提出周期性光变源自双星轨道运动对膨胀新星包层的形变作用这一新颖物理解释,将光变特征与包层几何结构直接关联。

◆ 首次为经典新星缓慢上升阶段提供了公共包层相互作用参与壳层抛射的直接观测证据。

◆ 打破了缓慢上升现象仅存在于共生双星热核爆发中的传统认知,证明该现象同样可发生于含矮星伴星的紧致双星系统中。

◆ 通过周期稳定性和轨道动力学分析,首次利用上升阶段光变对新星伴星性质(矮星)做出限定,为新星双星系统参数测定提供了新方法。</td></tr>
<tr><td>2026-06-09</td><td>A Multimodal RGB and Events Dataset for Hand Detection in First-Person View<br><a href='http://arxiv.org/pdf/2606.10790'>论文</a></td><td>该论文针对事件相机在手部检测中训练数据匮乏的瓶颈，提出了一种合成第一人称视角事件数据集的方法。
◆提出利用现有RGB Egohands数据集结合v2e工具箱，合成第一人称视角事件相机手部数据集的方法。
◆通过变化v2e工具箱参数，生成了涵盖不同光照条件和尺度的多版本数据集，增强了数据多样性。
◆设计了结合微调YOLOv8模型与时间插值的标注策略，实现了高时间分辨率事件数据的真值生成。
研究最终构建了多模态RGB与事件数据集，并利用现有多模态算法验证了其有效性，达到了与前沿方法媲美的检测性能。</td></tr>
<tr><td>2026-06-08</td><td>Dense Force Estimation with an Event-based Optical Tactile Sensor<br><a href='http://arxiv.org/pdf/2606.09451'>论文</a></td><td>本文提出了首个基于事件光学触觉传感器的密集三维力场重建框架，解决了现有事件传感器仅能预测整体净力的问题。
◆提出基于事件的标记跟踪算法以恢复触觉表面的剪切位移。
◆利用卷积神经网络预测法向位移，并收集了同步的力-位移-事件数据集用于训练。
◆创新性地通过逆有限元法将三维表面位移映射为物理受力。
实验表明该框架在最高20N受力范围内实现了低误差精准重建，平均运行频率达100Hz。
此工作为机器人抓取与灵巧操作的高频控制迈出了密集力反馈的第一步。</td></tr>
<tr><td>2026-06-08</td><td>Beyond Humans: Multispecies Animal Face Recognition Using Transfer Learning<br><a href='http://arxiv.org/pdf/2606.09353'>论文</a></td><td>该论文针对传统动物识别物理设备不实用且现有动物面部数据集规模小难以训练深度学习模型的问题，提出利用迁移学习实现多物种动物面部识别的方法。
◆创新性地探索了利用在大规模人类面部或通用物体数据集上预训练的模型作为骨干网络，解决动物面部数据不足的迁移学习方案。
◆首次系统比较了专门针对人类面部训练的FaceNet与在通用物体类别上预训练的Vision Transformer在跨物种动物面部识别上的性能差异。
研究在狗、灵长类和牛这三个图像质量与捕获条件差异极大的数据集上进行了验证。
结果表明，Vision Transformer在狗和牛的数据集上表现优异且超越了现有最优方法，而在图像质量较差的灵长类数据集上虽具鼓励性但表现波动。</td></tr>
<tr><td>2026-06-07</td><td>Magnetic Brunn-Minkowski inequalities<br><a href='http://arxiv.org/pdf/2606.08626'>论文</a></td><td>本文研究了黎曼流形上的闵可夫斯基平均，其中插值由给定磁势下作用量最小化的磁测地线实现。
◆建立了该操作的布鲁恩-闵可夫斯基不等式与磁里奇曲率下界之间的等价关系。
◆探讨了Kähler流形和Sasakian流形上的自然磁场等多种实例。
◆为海森堡群上的接触磁测地线证明了一个尖锐且无畸变的布鲁恩-闵可夫斯基不等式。
◆发现来自不同上同调类的闭磁势可能会产生不同的测地线闵可夫斯基平均。</td></tr>
<tr><td>2026-06-05</td><td>TraRA: Trajectory-level Recognition Aggregation for Video Text Spotting in Urban Surveillance<br><a href='http://arxiv.org/pdf/2606.07161'>论文</a> | <a href='https://github.com/trid2912/TraRA'>代码</a></td><td>这篇论文针对城市监控场景中视频文本识别(VTS)面临的运动模糊、遮挡、尺度变化等挑战,提出了TraRA(轨迹级识别聚合)方法。现有VTS方法通常在每一帧上独立进行文本识别,导致序列间结果不一致且不准确。TraRA作为一种即插即用的方法,通过利用时间和多模态一致性,在整个文本轨迹层面进行识别聚合,从而在复杂监控条件下实现鲁棒的文本识别。作者在RoadText、BOVText、ArTVideo和ICDAR15四个公共基准上进行了大量实验,证明TraRA在跟踪和识别性能上均优于现有最先进的VTS方法。

核心贡献与创新点如下:

◆ 提出了TraRA框架,首次将视频文本识别从帧级独立处理提升到轨迹级聚合识别,利用时序和多模态一致性显著提升监控视频中的文本识别鲁棒性。

◆ 设计了时序聚类模块(Temporal Clustering),通过将时间上和视觉上一致的文本实例进行分组,有效净化和细化噪声轨迹,缓解跟踪结果不稳定的问题。

◆ 提出了视觉-语言聚合模块(Vision-Language Aggregation),采用LoRA(低秩适应)增强的视觉-语言模型,跨帧融合视觉线索与语言上下文,实现多模态信息的有效整合。

◆ 该方法具备即插即用的特性,可灵活适配现有VTS方法,在四个公共数据集上的实验均验证了其在跟踪与识别任务上的一致性能提升。</td></tr>
<tr><td>2026-06-03</td><td>IMPose: Interactive Multi-person Pose Estimation with Dynamic Correction Propagation<br><a href='http://arxiv.org/pdf/2606.04480'>论文</a></td><td>IMPose是一款面向多人动态姿态标注的交互式工具,旨在解决现有标注工具在多人场景下缺乏时序传播能力、依赖大量人工干预的问题。该工具通过双层级跟踪机制,将标注员在单帧上的多人姿态修正自动传播至整段视频,显著降低了跨帧重复修正的成本。实验表明,IMPose在3DPW数据集上仅需每1050帧视频27次点击,在PoseTrack21上每条轨迹84帧仅需3次点击即可实现高精度标注。作者还借助该工具,以10名标注员10小时的极低成本将PoseTrack21扩展了18.8万个姿态实例(355万关键点)。

◆ 提出双层级跟踪机制:关键点层级通过序列建模实现修正的时序传播,实例层级利用关键点感知嵌入与相对位置编码保持多人跨帧一致性。

◆ 设计轨迹库(trajectory bank)存储历史姿态与实例线索,增强长程时序关联,在遮挡和运动模糊等困难场景下稳定标注效果。

◆ 将稀疏的人工修正转化为稠密、连贯的姿态轨迹,在不同交互预算下均取得优异的精度-效率权衡,尤其在低点击数场景下优势显著。

◆ 基于该工具发布了大规模扩展版PoseTrack21数据集,并开源标注工具、代码与数据,为社区提供了高效的多人动态姿态标注方案。</td></tr>
<tr><td>2026-05-31</td><td>DeblurNVS: Geometric Latent Diffusion for Novel View Synthesis from Sparse Motion-Blurred Images<br><a href='http://arxiv.org/pdf/2606.01315'>论文</a> | <a href='https://github.com/PKU-YuanGroup/DeblurNVS'>代码</a></td><td>本文提出DeblurNVS框架，实现了直接从稀疏运动模糊图像合成高保真新视图，且无需耗时的逐场景优化。
◆提出恢复中间几何表征的方法，从模糊输入中重建可靠的结构与对应线索，并结合目标相机信息重构清晰的新视图。
◆基于DL3DV-10K构建了运动模糊新视图合成数据集，利用插值有限曝光模糊合成技术实现了大规模训练。
实验证明该方法在合成和真实模糊场景基准上均优于现有基线。
它有效克服了传统方法依赖逐场景优化的局限，生成了感知更清晰且结构更稳定的视图。</td></tr>
<tr><td>2026-05-31</td><td>Event-Based Vision in Space: Applications, Trends, and Future Directions<br><a href='http://arxiv.org/pdf/2606.01280'>论文</a></td><td>传统帧式光学传感器在挑战性的轨道环境中常面临运动模糊、高功耗和极端数据冗余等问题。事件相机作为一种受生物启发的异步传感器，仅捕获局部光照变化，从而提供微秒级时间分辨率、极高动态范围和卓越的能效。针对当前空间应用科学文献零散的现状，本文全面综述了空间领域事件视觉的最新进展。
◆构建了涵盖大气与高速观测、环境监测与变化检测、运行支持与星载处理、地理空间建模与预测分析四个主要领域的分类法。
◆强调神经形态工程不仅是补充性成像技术，更是解决现代遥感和可持续太空探索关键瓶颈的范式转变。</td></tr>
<tr><td>2026-05-31</td><td>DeepIPCv3: Event-Aware Multi-Modal Sensor Fusion for Sudden Pedestrian Crossing Avoidance<br><a href='http://arxiv.org/pdf/2606.01277'>论文</a> | <a href='https://github.com/oskarnatan/DeepIPCv3'>代码</a></td><td>针对传统基于帧传感器在突发行人横穿场景下存在感知延迟和运动模糊的安全隐患，本文提出了DeepIPCv3多模态自动驾驶导航框架。
◆引入了受Transformer启发的跨模态注意力机制，动态融合激光雷达的稠密3D空间几何与动态视觉传感器的微秒级异步事件流，在不损失结构感知的前提下优先处理高速动态更新。
◆设计了混合策略网络，将启发式轨迹跟踪与直接神经预测相结合，把融合特征映射为安全的局部路径点和可执行控制指令。
本文在自建的涵盖白天与夜间条件的多模态数据集上进行了离线严格验证。
实验表明该框架实现了最先进的预测性能，有效消除了曝光失效和运动模糊。
其在轨迹与控制指令误差上达到最低，使车辆能在任意环境光照下完成高响应且数学有界的规避机动，并即将开源代码。</td></tr>
<tr><td>2026-05-31</td><td>Rank-Aware Quantile Activation for Motion-Robust Crop Segmentation in UAV Imagery<br><a href='http://arxiv.org/pdf/2606.01118'>论文</a></td><td>针对高速无人机运动模糊破坏高频幅度特征从而导致稀有农作物信号被抹除的问题，本文提出了双分位数激活机制。
◆提出秩感知模块QAct，利用实例级秩归一化替代传统CNN中易受模糊影响的幅度门控。
◆揭示并验证了秩感知激活与模糊域训练是两种互补的鲁棒性来源，而非相互替代。
实验表明QAct是提升性能的主导架构因素，在中等模糊下零样本QAct甚至超越了经蒸馏训练的ReLU。
结合两者的Distill-QAct在所有模糊严重度下均取得最佳性能，在稀有结构和纹理类别上实现了持续的mIoU提升。</td></tr>
<tr><td>2026-05-29</td><td>Towards Neuromorphic Event-Based Sensing for High-Speed Multi-Spectral Classification and Tracking of Microparticles<br><a href='http://arxiv.org/pdf/2605.31038'>论文</a></td><td>本文针对传统微流控成像系统在速度与带宽间的权衡，以及现有事件相机仅能追踪单一球形粒子的局限，提出了一种新型神经形态微流控传感平台。
◆创新性地集成空间复用RGB滤光片与异步事件传感器，在传感阶段直接编码多分散微粒的光谱特征与运动，免除了图像重建或学习推理的需求。
◆实现了亚毫秒级时间分辨率，在广泛尺寸与流速（含非层流）下保持鲁棒，对0.08至0.18毫米彩色粒子的分类准确率达82%。
◆事件驱动架构将数据带宽降低超240倍，同时维持460平方毫米每秒的面积吞吐量。
该框架为临床诊断与环境监测中的高速无标记异构分析物筛选提供了高效低延迟的可扩展方案。</td></tr>
<tr><td>2026-05-29</td><td>Omni-Supervised Motion Editing: Balancing Change and Invariance through Positive-Negative Learning<br><a href='http://arxiv.org/pdf/2605.30969'>论文</a> | <a href='https://github.com/rocket-ycyer/OmniME.git'>代码</a></td><td>本文针对文本驱动的人体运动编辑中难以平衡改变与不变性的核心挑战，提出了全监督正负学习框架OmniME。
◆提出回溯特征监督，在Transformer层间强制执行从粗到细的特征一致性。
◆设计运动保留机制，根据源与目标的相似度关注细微变化以保留未编辑部分。
◆引入基于三元组的语义对齐，增强文本与运动之间的语义对应关系。
这三个互补组件共同构成了统一监督范式，有效平衡了目标区域的精准编辑与未编辑部分的完整保留。
在多个数据集上的广泛实验证明，OmniME实现了最先进的编辑对齐性能。</td></tr>
<tr><td>2026-05-29</td><td>Magnetic self-frustration from spontaneous structural distortion<br><a href='http://arxiv.org/pdf/2606.00339'>论文</a></td><td>本文提出并证实了一种与常规认知相反的物理现象，即自发结构畸变不仅未消除磁简并，反而诱导了新的阻挫。
◆首次提出“磁性自阻挫”概念，打破了结构畸变通常作为逃逸磁简并度途径的传统观点。
◆发现具有平凡最近邻伊辛铁磁作用的kagome晶格会发生磁结构相变进入呼吸状相，其中一个子晶格自发膨胀为等腰三角形并作为刚性拼图块决定另一收缩子晶格的几何结构。
◆证明该畸变后的磁系统可映射为有效的反铁磁三角晶格，在低温下保持无序并保留三分之一的万尼尔剩余熵。
研究还表明，这种自阻挫相存在于中等磁弹性耦合区间，介于弱耦合的无畸变铁磁相与强耦合的规则二聚化反铁磁有序相之间。</td></tr>
<tr><td>2026-05-28</td><td>Resolution-free neural surrogates for geometric parameterization and mapping with spatially varying fields<br><a href='http://arxiv.org/pdf/2605.28551'>论文</a></td><td>针对空间变化场引起的几何映射问题，传统变分模型在处理高分辨率且参数场变化的实例时计算成本极高。本文提出一种分辨率无关的神经代理模型，可在任意结构化或非结构化点集上直接预测映射位置。
◆采用多分辨率几何编码策略，以坐标增强的参数场样本为网络条件，摆脱了对固定网格的依赖。
◆无需带标签的解数据进行训练，而是通过强制执行源自变分能量、扩散密度均衡和拟共形理论的几何感知约束来优化模型。
实验表明该方法在拟共形映射和密度均衡映射问题上具有显著有效性。</td></tr>
<tr><td>2026-05-28</td><td>Turbulence-Robust Dynamic Object Segmentation with Multi-Signal Priors and SAM2 Refinement<br><a href='http://arxiv.org/pdf/2605.29292'>论文</a></td><td>本文提出了针对湍流环境下动态目标分割的免训练多信号分割流水线。
◆融合多信号先验，结合RAFT的密集运动响应、DINOv2的语义目标先验与ViBe的免训练背景建模，解决了单一运动线索在强湍流下不可靠的问题。
◆采用纯推理模式设计，完全无需端到端网络优化或针对特定任务的模型训练与微调，适应了湍流导致的伪运动、模糊和目标间歇可见等复杂情况。
◆引入人工校准的候选融合策略，并结合预训练的SAM2模型通过框提示进行掩膜精修，有效提升了分割边界的准确性。
该方法在CVPR 2026挑战赛中取得了0.425的mIoU和0.457的mDice。</td></tr>
<tr><td>2026-05-26</td><td>Can We Hear from Events? Generating Speech from Event Camera<br><a href='http://arxiv.org/pdf/2605.26672'>论文</a> | <a href='https://xrfang-0102.github.io/EventSpeechWeb/'>代码</a></td><td>本文提出EventSpeech框架，首次利用微秒精度的神经形态事件相机进行文本条件驱动的情感语音生成，解决传统RGB相机因固定曝光导致的高频发音瞬态模糊问题。
◆提出基于事件相机的语音生成新范式，利用微秒级事件与声学波形动态自然对齐的特性，打破了传统视觉语音生成的时间粒度限制。
◆设计了包含专用事件编码器和多尺度音频编码器的架构，引入分层小波上下文化器与双向对齐机制，实现语言内容、视觉动态与声学特征的精准同步。
◆构建了首个事件相机语音生成基准数据集EVT-SPK，涵盖大规模合成数据与神经形态硬件真实录音。
实验证明，该方法在保留细粒度情感和抗运动模糊方面显著优于现有基线，确立了多模态语音生成的新范式。</td></tr>
<tr><td>2026-05-25</td><td>Event-based Batting Impact Estimation<br><a href='http://arxiv.org/pdf/2605.25656'>论文</a></td><td>本文针对RGB相机和IMU在估计击球冲击时机上的局限性，提出了一种基于事件相机的全新框架。
◆提出利用事件相机微秒级分辨率优势，通过检测球和球棒的加权质心距离来估计击打时机。
◆为克服事件帧与RGB图像间的域鸿沟导致的分割精度下降问题，提出生成高密度事件帧的方法。
◆引入一种掩码细化网络，利用高密度事件帧和双向掩码信息，并配合新型损失函数进行优化。
真实数据集实验表明，该方法在低光和严重遮挡等挑战条件下优势显著，将平均绝对误差降低了约百分之六十三。</td></tr>
<tr><td>2026-05-23</td><td>COD10K-C: Benchmarking Robustness of Camouflaged Object Detection Under Natural Image Corruptions<br><a href='http://arxiv.org/pdf/2606.02603'>论文</a></td><td>该论文针对伪装目标检测(COD)模型在真实场景下鲁棒性评估缺失的问题,构建了首个系统性的腐蚀鲁棒性基准 COD10K-C,并提出了一个轻量级鲁棒模型 RobustCODLite。作者基于 COD10K 数据集引入 8 种腐蚀类型和 5 个严重级别,共生成 40 种测试条件和 81,040 对评估样本,对 SINet-v2、PFNet 和 ZoomNet 三种主流模型进行了系统评测,发现所有模型在腐蚀图像上均出现显著性能下降,其中运动模糊和高斯模糊影响最大(SINet-v2 在运动模糊下 Dice 下降 18.5 分),而亮度变化和雾效影响较小。RobustCODLite 在腐蚀条件下保持了 92.3% 的清洁 Dice 分数,显著优于对比模型,并在最难的腐蚀场景下达到或超越在清洁数据上表现更好的模型。

核心创新点如下:

◆ 首次提出面向伪装目标检测的腐蚀鲁棒性基准 COD10K-C,涵盖 8 种腐蚀类型和 5 个严重级别,共 81,040 对评估样本,填补了 COD 领域在真实成像退化下评估缺失的空白。

◆ 系统量化了三种主流 COD 模型在不同腐蚀类型下的性能衰减规律,揭示了模糊类腐蚀对 COD 任务的破坏性远大于光照与天气类腐蚀。

◆ 提出轻量级鲁棒模型 RobustCODLite,融合腐蚀数据增强、频率先验分支和不确定性一致性损失三种机制,提升模型对退化输入的稳定性。

◆ 实验证明 RobustCODLite 在腐蚀保持率上显著优于更大规模的 SOTA 模型,在最严重腐蚀条件下甚至超越清洁数据上表现更优的模型,验证了鲁棒性导向设计的有效性。

◆ 将公开发布 COD10K-C 代码仓库,为后续鲁棒伪装目标检测研究提供标准化评估工具。</td></tr>
<tr><td>2026-05-21</td><td>SpaceDG: Benchmarking Spatial Intelligence under Visual Degradation<br><a href='http://arxiv.org/pdf/2605.22536'>论文</a></td><td>本文提出了SpaceDG，首个针对视觉退化条件下空间理解的大规模数据集与基准，填补了现有空间推理基准忽视真实世界视觉退化的空白。
◆首创物理驱动的退化合成引擎，将退化形成过程嵌入3D高斯溅射渲染中，真实模拟九种退化类型并生成约百万问答对。
◆构建了经人工验证的SpaceDG-Bench基准，涵盖11个推理类别与9种退化类型，产生逾万条视觉问答实例。
◆对25个多模态大模型的全面评估揭示了视觉退化会显著损害空间推理能力，暴露出模型关键的鲁棒性缺陷。
◆证实了退化感知训练的潜力，在SpaceDG上微调不仅能大幅提升退化条件下的鲁棒性甚至超越人类，且不牺牲清晰图像的性能。</td></tr>
<tr><td>2026-05-20</td><td>DarkShake-DVS: Event-based Human Action Recognition under Low-light andShaking Camera Conditions<br><a href='http://arxiv.org/pdf/2605.20680'>论文</a></td><td>本文针对低光照和相机剧烈抖动下人体动作识别易失效的难题，提出了新的解决方案。
◆提出EIS-HAR方法，其事件惯性稳定模块通过非线性变形函数减少运动模糊以重构运动补偿输入，动作识别模块采用四阶段混合架构高效提取时空特征。
◆构建DarkShake-DVS数据集，这是首个结合低光照、六自由度相机运动及同步IMU数据的大规模事件相机动作识别基准，含超一万八千个真实片段。
该研究有效填补了现有研究缺乏综合基准与运动补偿技术的空白。
三个数据集的大量实验表明，EIS-HAR方法的性能持续优于现有最先进算法。</td></tr>
<tr><td>2026-05-18</td><td>Open-source segmentation and biometry dataset using spectrally-multiplexed whole-eye optical coherence tomography<br><a href='http://arxiv.org/pdf/2605.19191'>论文</a></td><td>本文针对全眼OCT系统在成像性能上的权衡以及前节标注数据匮乏的问题，提出了新型频分复用WEOCT系统并开源了大规模数据集。
◆采用1310nm和1060nm双同步200kHz扫频光源，突破了现有系统在信噪比、速度与运动伪影间的局限。
◆构建了包含深度学习分割、3D畸变校正及光线追踪折射校正的端到端自动化流水线，实现了解剖学精确的眼球分层3D重建。
◆通过超300人的用户及体模研究，验证了系统能够同时精准测量角膜地形图与3D瞳孔中心。
◆发布了目前稀缺的大规模开源综合数据集，包含276名受试者的6621个标注体积及校准的3D前节点云。</td></tr>
<tr><td>2026-05-18</td><td>See Silhouettes in Motion with Neuromorphic Vision<br><a href='http://arxiv.org/pdf/2605.17984'>论文</a></td><td>本文针对移动平台上传统帧成像因运动模糊和恶劣光照导致准双峰物体二值化失效的问题，提出一种基于神经形态视觉的帧与事件双模态二值化方法。该方法能在仅CPU设备上实现实时高帧率二值化，为资源受限边缘平台的轻量级感知与交互铺平了道路。
◆提出帧与事件协同的双模态机制，利用事件相机的高时间分辨率和高动态范围优势，有效减少运动模糊并显著提升恶劣光照下的二值化表现。
◆设计异步工作流，规避了传统时间分箱重建在事件稀缺时易崩溃的缺陷，确保在极端千赫兹帧率下依然维持清晰的目标轮廓。
◆实现轻量化高效计算，在仅CPU设备上达成实时高帧率处理，且输出的二值结果可作为可靠表征直接赋能多种下游任务。</td></tr>
<tr><td>2026-05-17</td><td>Channel Modeling and LED Spot Detection for Dense Image-Sensor Visible Light Communication<br><a href='http://arxiv.org/pdf/2605.17375'>论文</a></td><td>针对高密度LED阵列可见光通信中光斑模糊重叠引发严重符号间干扰，以及径向畸变与暗角效应阻碍信号检测的问题，本文提出一种保持全信令密度的鲁棒解码框架。
◆提出导频辅助的几何识别方法，结合点扩散函数约束的霍夫变换与圆心对齐细化技术。
◆引入径向畸变校正与暗角感知补偿机制，恢复几何一致性并抑制边缘检测误差。
◆利用导频帧的先验结构知识，在严重光学畸变下有效分离重叠的LED信号。
实验表明该方法解码精度和吞吐量显著优于传统基线方法，在干扰环境下具备高效应用潜力。</td></tr>
<tr><td>2026-05-15</td><td>DepthPolyp: Pseudo-Depth Guided Lightweight Segmentation for Real-Time Colonoscopy<br><a href='http://arxiv.org/pdf/2605.16519'>论文</a> | <a href='https://github.com/ReaganWu/DepthPolyp/'>代码</a></td><td>本文提出了DepthPolyp，一个基于伪深度引导多任务学习的轻量级鲁棒息肉分割框架，旨在解决真实临床环境中运动模糊和光照不稳导致的性能下降问题。
◆引入层级Ghost分解，实现了紧凑高效的视觉特征生成。
◆提出交错混洗融合机制，以极低计算成本完成跨尺度特征交互。
◆设计动态分组门控模块，实现了自适应的分组特征权重分配与调制。
实验表明，该方法在跨数据集泛化测试中表现优异，在真实手术视频评估中甚至超越了20倍参数量的模型。
该模型仅需3.57M参数和0.86 GMACs，移动端帧率超180 FPS，极具资源受限临床环境下的实时部署潜力。</td></tr>
<tr><td>2026-05-13</td><td>What Limits Vision-and-Language Navigation ?<br><a href='http://arxiv.org/pdf/2605.13328'>论文</a> | <a href='https://yunheng-wang.github.io/stereonav-public.github.io'>代码</a></td><td>本文提出StereoNav框架，解决了视觉语言导航中从仿真到真实部署时因感知不稳定和指令模糊导致的性能下降问题。
◆引入目标位置先验作为合成训练与物理执行间的持久桥梁，提供跨域不变的稳定视觉引导，在指令模糊时实现可靠的空间定位。
◆利用立体视觉构建语义与几何的统一表示，通过增强深度感知减轻运动模糊和光照变化的干扰，实现精确的动作预测。
该方法在R2R-CE和RxR-CE数据集上以更少的参数和训练数据取得了最先进的性能。
真实机器人部署也证实了其在复杂非结构化环境中显著提升了导航的可靠性。</td></tr>
<tr><td>2026-05-12</td><td>EgoEV-HandPose: Egocentric 3D Hand Pose Estimation and Gesture Recognition with Stereo Event Cameras<br><a href='http://arxiv.org/pdf/2605.12297'>论文</a> | <a href='https://github.com/ZJUWang01/EgoEV-HandPose'>代码</a></td><td>本文提出了EgoEV-HandPose端到端框架，旨在解决传统相机运动模糊及现有事件相机自我运动干扰与深度模糊等限制，实现立体事件流下的3D双手姿态估计与手势识别。
◆提出KeypointBEV立体融合模块，将特征提升至鸟瞰图空间，并利用迭代重投影引导的细化循环逐步解决深度不确定性及强化运动学一致性。
◆构建EgoEVHands数据集，这是首个大规模真实世界自我中心立体事件相机手部感知数据集，包含5419个标注序列及38种手势类别的密集3D与2D关键点。
实验证明，该方法以30.54毫米的MPJPE和86.87%的手势识别准确率取得了最优性能。
特别是在低光照和双手遮挡场景下，该框架显著超越了现有基于RGB和事件相机的方案，为事件相机自我中心感知设立了新基准。</td></tr>
<tr><td>2026-05-12</td><td>BronchoLumen: Analysis of recent YOLO-based architectures for real-time bronchial orifice detection in video bronchoscopy<br><a href='http://arxiv.org/pdf/2605.11748'>论文</a></td><td>本文提出了BronchoLumen，一个基于YOLO的实时支气管镜视频支气管开口检测系统，旨在辅助呼吸道导航和计算机辅助诊断。
◆首次仅利用有限的公开数据集，探索并验证了最先进的目标检测架构在不同图像域中鲁棒检测支气管开口的可行性。
◆深入对比了广泛使用的YOLOv8与集成注意力模块的最新架构YOLOv12，揭示出YOLOv12虽精度略低，但具有更优的目标定位准确性。
◆开发了具有高准确性和效率的跨域开源权重解决方案，且系统在运动模糊和低对比度等挑战下仍展现出整体鲁棒性。
该研究通过公开发布模型，为支气管镜导航领域的进一步研究提供了重要基准和工具。</td></tr>
<tr><td>2026-05-11</td><td>Computational Design of a Low-Visibility UAV Using a Human-Aligned Perceptual Metric<br><a href='http://arxiv.org/pdf/2605.11296'>论文</a></td><td>本文提出了一种名为Phantom Twist的单旋翼无人机，通过高速旋转利用运动模糊效应实现低可见度。
◆首创利用高速旋转与运动模糊来降低无人机视觉可见度的单旋翼设计概念。
◆开发了基于人类对齐感知度量LPIPS的两阶段自动化设计流水线，以优化功能组件的布局。
◆在最小化视觉感知度的同时，严格满足稳定飞行所需的惯性与空气动力学约束。
◆通过制作并飞行测试多个原型机，验证了该流水线生成的无人机具备稳定可控的飞行能力。
实验最终证实，这种优化设计的无人机相比传统四旋翼具有显著更低的视觉可感知性。</td></tr>
<tr><td>2026-05-11</td><td>VVitCutLER: Towards Unsupervised Object Detection and Segmentation in Videos<br><a href='http://arxiv.org/pdf/2605.17584'>论文</a></td><td>本文针对无监督视频理解中因运动模糊和遮挡导致伪标签时序漂移与闪烁的问题，提出了无监督视频目标检测与实例分割框架VVitCutLER。
◆提出时序稳定的伪标签生成器VitCut，通过跨帧区域一致性来减少退化过程中的误差累积。
◆设计了蒸馏解码器，以实现高效准确的实例掩码预测。
◆在VVitCutLER框架中集成了跨帧特征聚合机制，进一步增强了视频级别的鲁棒性。
实验证明该方法显著提升了检测与分割性能并降低了时序不稳定性，凸显了时序一致性监督对于鲁棒视频理解的重要性。</td></tr>
<tr><td>2026-05-09</td><td>Kinematics-Driven Gaussian Shape Deformation for Blurry Monocular Dynamic Scenes<br><a href='http://arxiv.org/pdf/2605.08635'>论文</a></td><td>本文提出了Kinematics-GS框架，解决模糊单目视频重建动态3D场景时运动与几何纠缠阻碍一致性的难题。
◆将模糊建模为运动对齐的变形，并引入运动学先验沿运动轨迹重新参数化高斯形状，无需辅助运动监督即可缓解退化形状坍缩。
◆利用时间变形方差将场景分解为动态与静态成分，并采用由粗到细的变形策略，稳定优化并兼顾全局运动与精细细节。
◆构建了一个极具挑战性的真实世界数据集，包含具有非刚体运动和空间非均匀运动模糊的可变形弹性物体。
实验证明该方法在真实模糊基准上显著超越现有方法，有效处理了复杂非刚体运动场景。</td></tr>
<tr><td>2026-05-09</td><td>Egocentric Whole-Body Human Mesh Recovery with Prior-Guided Learning<br><a href='http://arxiv.org/pdf/2605.08606'>论文</a> | <a href='https://github.com/naso06/EgoSMPLX'>代码</a></td><td>本文致力于解决单目头戴式相机图像中缺乏可靠真实标注且难以恢复手部和面部细节的自我中心全身人体网格恢复问题。为此，作者提出了一种基于先验引导的学习框架，从单张自我中心图像中恢复全身网格。
◆构建了与三维关节监督对齐的基于优化的伪真实标注，比现有基于回归的伪标注大幅提升了准确性。
◆通过适配第三人称人体网格恢复基础模型并结合基于扩散模型的姿态先验，充分利用了多种先验知识。
◆引入了确定性去畸变模块，有效处理了自我中心图像中的鱼眼畸变问题。
实验表明该方法在多个基准上实现了优于现有技术的全身重建效果，并已开源代码与数据。</td></tr>
<tr><td>2026-05-08</td><td>AERO-VIS: Asynchronous Event-based Real-time Onboard Visual-Inertial SLAM<br><a href='http://arxiv.org/pdf/2605.07885'>论文</a> | <a href='https://ethz-mrl.github.io/AERO-VIS'>代码</a></td><td>本文提出了AERO-VIS系统，这是一种异步事件驱动的实时机载视觉-惯性SLAM系统，突破了传统固定频率处理带来的延迟和吞吐量限制。
◆集成了一种数据驱动、鲁棒且性能优化的关键点检测器，提升了特征提取的稳定性与准确性。
◆采用异步方式处理事件流，使系统能够动态适应下游计算需求，确保低延迟和实时性能。
◆在无人机平台上部署时，实现了机载事件SLAM前所未有的高精度。
◆成为首个仅依赖机载计算实现闭环无人机控制和大规模状态估计的纯事件驱动惯性SLAM系统。</td></tr>
<tr><td>2026-05-08</td><td>A Task-Agnostic Algebraic Integrity Metric for Event-Camera Streams Toward SOTIF-Compliant Perception using Pearson Correlation Coefficient<br><a href='http://arxiv.org/pdf/2605.21500'>论文</a></td><td>本文针对事件相机异步流缺乏任务无关的质量评估指标问题，提出统一代数框架以满足自动驾驶SOTIF认证需求。
◆创新性地将皮尔逊相关系数提升至时间面、事件帧和体素网格三种标准事件表示形式。
◆推导出用于流完整性监控的r-TS、仅需整数比较的自适应ROI指标r2-EF，以及时间冗余门控指标r-VG。
◆建立了事件相机对比度阈值机制与基于PCC变化准则的结构同构性，并对流水线延迟与信息损失进行对称分析。
通过直接模拟发射模型生成的合成事件流验证了指标，在隧道异常场景中指标成功从0.93降至负值并触发报警。</td></tr>
<tr><td>2026-05-08</td><td>AsyncEvGS: Asynchronous Event-Assisted Gaussian Splatting for Handheld Motion-Blurred Scenes<br><a href='http://arxiv.org/pdf/2605.07192'>论文</a> | <a href='https://openimaginglab.github.io/AsyncEvGS/'>代码</a></td><td>本文针对严重运动模糊导致3D重建失败的问题，提出了一种灵活的高分辨率异步RGB-Event双摄系统及对应重建框架。
◆提出高分辨率异步RGB-Event双摄系统与重建框架，打破了传统方法对低分辨率传感器和严格硬件同步的依赖，提升了手持拍摄的实用性。
◆设计基于VGGT的跨域位姿估计模块，先利用事件数据重建清晰图像，从而为3DGS提供鲁棒的初始化。
◆引入结构驱动的事件损失和视角特定一致性正则化器，有效缓解传统损失函数的病态行为，确保稳定且高保真的重建。
◆构建了全新的高分辨率异步RGB-Event去模糊数据集AsyncEv-Deblur，实验验证了该方法在严重模糊场景下实现了最先进的重建鲁棒性。</td></tr>
<tr><td>2026-05-07</td><td>Advancing Reliable Synthetic Video Detection: Insights from the SAFE Challenge<br><a href='http://arxiv.org/pdf/2605.06912'>论文</a></td><td>本文核心贡献在于组织并总结了ICCV 2025上的SAFE合成视频检测挑战赛，为评估合成媒体检测算法提供了重要基准。
◆构建了包含13种现代高质量生成模型和21种真实来源的6000个视频数据集，总计20小时，全面覆盖多样化生成源。
◆设计了双任务评估体系，不仅考察跨生成器检测能力，还专门测试对缩放、重压缩和运动模糊等后处理操作的鲁棒性。
◆采用全盲评估条件，依托Hugging Face平台在90天内收集12个团队的600余次提交，确保了评估的客观与广泛性。
◆揭示了当前检测方法的关键特性，即跨生成器泛化能力取得进步，但在面对后处理伪影时仍存在持续脆弱性。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

---
> 更新于: 2026.07.19
