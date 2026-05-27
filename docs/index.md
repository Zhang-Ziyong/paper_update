# 计算机视觉领域最新论文 (2026.05.27)

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
</ol>
</details>

<h2 id='slam'>SLAM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-26</td><td>Gaussian Process-Based Extended Object Estimation for 6G ISAC at Millimeter-Wave Frequencies<br><a href='http://arxiv.org/pdf/2605.26915'>论文</a></td><td>本文提出了一种基于高斯过程的扩展目标估计方法，用于6G毫米波通感一体化场景。
◆突破了传统点散射体假设的限制，利用高斯过程实现了对扩展目标的更优估计。
◆结合符合5G新空口标准的双基地感知实际测量平台，验证了该方法在毫米波频段的实用性。
◆证明了通信网络能力增强与双基地感知及高斯过程估计相结合，可有效提升未来无线系统的环境感知能力。
研究结果表明，高斯过程在毫米波建图和同步定位与建图场景中均能有效完成扩展目标估计。</td></tr>
<tr><td>2026-05-25</td><td>G-DRAGON: Geospatial Reasoning and Dynamic Planning for Retrieval-Augmented Outdoor Navigation<br><a href='http://arxiv.org/pdf/2605.25646'>论文</a></td><td>本文提出G-DRAGON，一个用于户外开放世界导航的检索增强框架，解决了现有视觉语言导航缺乏长距离地理空间基础以及云端大模型易产生幻觉且无法进行“最后一公里”探索的问题。
◆提出基于轻量级大模型的生成式检索方法，将自然语言指令映射到本地OSM实体以生成准确坐标，避免了事实幻觉并实现全局路线规划。
◆设计高级规划模块，将地理空间航点投影到机器人可导航坐标系中，成功桥接全局拓扑路线与SLAM系统。
◆针对“最后一公里”任务，</td></tr>
<tr><td>2026-05-24</td><td>FusionCore: A 23-State Unscented Kalman Filter for IMU, Wheel Encoder, GPS, and Visual SLAM Fusion in ROS 2<br><a href='http://arxiv.org/pdf/2605.25239'>论文</a> | <a href='https://github.com/manankharwar/fusioncore'>代码</a></td><td>本文提出了FusionCore，一个开源的ROS 2传感器融合包，通过23状态无迹卡尔曼滤波器将IMU、轮式编码器、GPS和视觉SLAM位姿融合为100Hz里程计流。在NCLT</td></tr>
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
<tr><td>2026-05-20</td><td>SubTGraph: Large-Scale Subterranean Environment Synthesis with Controllable Topological Variability for Robotic Autonomy Validation<br><a href='http://arxiv.org/pdf/2605.20917'>论文</a> | <a href='https://github.com/LTU-RAI/SubTGraph.git'>代码</a></td><td>本文针对地下环境机器人研究缺乏大规模仿真基准的问题，提出了SubTGraph框架。
◆该框架能够根据用户对拓扑、维度和纹理等参数的设定，快速合成具有高变异性的多层地下环境。
◆该方法创新地从结构约束构建成本矩阵，引导Dijkstra算法结合DARPA拓扑贴片进行程序化生成。
研究通过语义分割、多智能体路径规划和LIO SLAM三个案例，验证了该框架对机器人自主系统各层严格评估的有效性。
最后，作者开源了世界创建代码库及包含150个高变异地下环境的数据库。</td></tr>
<tr><td>2026-05-19</td><td>Enhancing Graph-Based SLAM in GNSS-Denied environments by leveraging leg odometry<br><a href='http://arxiv.org/pdf/2605.20484'>论文</a></td><td>本文针对足式机器人在拒止GNSS环境中LiDAR易产生高程漂移的问题，提出了一种基于因子图架构的SLAM增强方法。
◆在LIO-SAM框架中引入了由本体感受腿部里程计驱动的并行运动学通道。
◆通过带有选择性噪声模型的恒等相对位姿约束，将腿部运动学通道与主LiDAR-惯性通道有效耦合。
◆将步态控制中已计算的本体感受数据作为SLAM的轻量级垂直锚点，无需额外计算负担。
在四足平台超过1公里的户外测试中，该方法将高程漂移从30多米大幅降至30厘米以内。
在基线方法完全失效的几何稀疏场景下，本方法依然能成功收敛并实现鲁棒定位。</td></tr>
<tr><td>2026-05-19</td><td>Depth2Pose: A Pose-Based Benchmark for Monocular Depth Estimation without Ground-Truth Depth<br><a href='http://arxiv.org/pdf/2605.19797'>论文</a> | <a href='https://kocurvik.github.io/depth2pose'>代码</a></td><td>本文针对单目深度估计传统评估指标无法反映下游几何任务实用性的问题，提出了Depth2Pose评估框架。
◆提出以相对相机位姿估计精度作为任务驱动的代理指标，结合深度预测与特征对应关系评估深度质量，取代了传统全局深度误差指标。
◆该框架仅需通过运动恢复结构等方法获取相机位姿，免去了昂贵且难以获取的密集真实深度图，使其适用于大尺度或严重遮挡等复杂场景。
◆构建了包含分布外挑战性场景的D2P数据集，揭示了在现有基准上表现优异的方法难以泛化到该更具挑战性的数据集上。
研究还提供了简单且可扩展的评估框架，并开源了代码与数据集，为深度估计的下游实用性评估建立了新标准。</td></tr>
<tr><td>2026-05-19</td><td>Multi-Session Ground Texture SLAM in Low-Dynamic Environments<br><a href='http://arxiv.org/pdf/2605.19701'>论文</a></td><td>本文针对现有地面纹理SLAM系统尚未应用于多会话低动态变化环境的问题，研究了三种技术对轨迹估计精度的影响。研究发现，使用库尔巴克-莱布勒散度作为相似度评分和影响回环闭合置信度的偏差取得了最大成功。该工作的核心创新点如下：
◆首次将库尔巴克-莱布勒散度引入多会话低动态地面纹理SLAM中，全面分析了多种方法，并深入探索了该散度作为相似度评分与回环置信度偏差以提升轨迹估计精度的机制。
◆发布了一个全新的多会话地面纹理数据集，包含会话间地面发生变化的图像以及用于评估的高精度位姿信息，为机器人社区提供了宝贵的评估基准。</td></tr>
<tr><td>2026-05-19</td><td>EpiDiffVO: Geometry-Aware Epipolar Diffusion for Robust Visual Odometry<br><a href='http://arxiv.org/pdf/2605.19556'>论文</a></td><td>本文提出一种稀疏极线匹配框架，通过预测几何一致的紧凑对应点集，解决了现有学习方法依赖稠密匹配导致的冗余及几何可解释性低的问题。
◆提出极线扩散过程，通过建模对应点不确定性并将关键点精修至极线一致性，解决残余噪声与错位问题。
◆将精修的对应点与深度线索提升为图表示，构建编码点间关系结构的Steiner图。
◆利用图神经网络学习紧凑的含信息对应点子集，</td></tr>
<tr><td>2026-05-23</td><td>PRISM-SLAM: Probabilistic Ray-Grounded Inference for Scale-aware Metric SLAM<br><a href='http://arxiv.org/pdf/2605.19257'>论文</a> | <a href='https://prismslam-cmd.github.io/prismslam_pr/'>代码</a></td><td>针对单目SLAM的尺度模糊与动态环境跟踪失败问题，本文提出PRISM-SLAM框架，通过将视觉基础模型先验严谨集成到贝叶斯因子图中，实现了尺度感知且度量一致的实时定位与建图。
◆引入普吕克光线距离因子，在全局度量坐标系中锚定单目观测，使度量尺度具备Fisher可辨识性，从数学上根本解决了尺度漂移问题。
◆提出动态场景不确定性门控机制，利用时间深度一致性推导认知不确定性代理，通过概率软门控降低动态干扰物权重，避免了传统语义分割的高昂计算开销。
系统采用多进程架构异步处理基础模型推理与几何跟踪，仅依赖RGB输入即可实现30帧每秒的实时度量输出。
实验表明其度量绝对轨迹误差几乎等同于无尺度对齐误差，无需任何事后尺度校正即可生成可直接部署的度量轨迹。</td></tr>
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
<tr><td>2026-05-21</td><td>FUSE: A Framework for Unified State Estimation in Vehicular and Robotic SLAM Systems<br><a href='http://arxiv.org/pdf/2605.18047'>论文</a></td><td>本文提出了一种名为FUSE的统一状态估计框架，旨在解决传统紧耦合SLAM中各模块高度绑定导致难以独立修改设计的问题。
◆提出FUSE框架，通过观测摄取、传播、更新和状态查询接口，将时间处理、局部几何关联、估计器公式与地图更新策略彻底解耦。
◆开发LiDAR-IMU实例，在统一接口边界下实现了高频惯性传播、LiDAR几何更新、残差筛选与退化感知校正的协同运作。
◆在混合频率感知和方向退化场景中，有效正则化弱可观方向的更新，增强了系统的鲁棒性。
实验表明，在418米闭环走廊序列中，该实例相比最优基线Faster-LIO实现了7.9%的相对误差降低。
这证明了FUSE为组织状态估计设计提供了有效框架，并能提升实际SLAM系统的估计精度。</td></tr>
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

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-26</td><td>Joint 2D-3D Segmentation and Association in Street-level Imaging<br><a href='http://arxiv.org/pdf/2605.26725'>论文</a></td><td>本文提出了一种联合2D-3D分割与关联的统一框架，将视觉语义与多视图几何推理相结合以解析街景图像。
◆提出基于零样本检测分割与运动恢复结构重建的跨视图对应方法，摆脱了传统对时序帧跟踪的依赖。
◆设计了3D驱动的关联机制取代传统2D多目标跟踪，利用几何一致性在宽基线视角和多变条件下稳健保持目标身份。
该流水线融合了2D纹理线索与全局3D上下文，具备高度扩展性且适用于多种对象类型。
实验证明，该框架在真实序列覆盖度上大幅提升，在复杂城市场景中较纯2D跟踪方法实现了22%的性能增益。</td></tr>
<tr><td>2026-05-26</td><td>Global Structure-from-Motion Meets Feedforward Reconstruction<br><a href='http://arxiv.org/pdf/2605.26103'>论文</a> | <a href='https://github.com/colmap/gluemap'>代码</a></td><td>该论文深入分析了传统运动恢复结构方法在低纹理和对称等复杂场景易失败，而前馈重建方法虽能应对这些挑战却受限于可扩展性与精度的现状。
为此，论文提出了一种全新的SfM流程，成功将传统方法与前馈方法的优势相结合。
◆系统性分析了两类方法的局限性，并创新性地融合了传统SfM与前馈3D重建技术。
◆设计出优势互补的全新管线，既具备前馈方法在退化场景下的强鲁棒性，又保留了传统方法在标准场景下的高精度与可扩展性。
实验证明该方法在广泛场景中均达到了最先进水平，并且已将系统开源供社区使用。</td></tr>
<tr><td>2026-05-24</td><td>Geometry-Aware Image Flow Matching<br><a href='http://arxiv.org/pdf/2605.25294'>论文</a></td><td>本文针对自然图像生成领域局限于欧几里得假设而忽略数据内在几何结构的问题展开研究。研究发现自然图像的语义信息主要编码在方向分量中，范数分量可由全局平均值近似，这表明自然图像能在超球面上被有效建模。
◆提出球面最优传输流匹配方法，利用角距离实现几何感知的生成建模。
◆提出球面流匹配方法，将动态过程直接约束在流形上进行求解。
实验证明这些几何感知方法的性能显著优于欧几里得基线模型。本工作为弥合黎曼流形建模与自然图像生成之间的鸿沟提供了全新视角。</td></tr>
<tr><td>2026-05-22</td><td>Joint Target-Less Intrinsic and Extrinsic Camera-LiDAR Calibration using Deep Point Correspondences<br><a href='http://arxiv.org/pdf/2605.23397'>论文</a></td><td>本文提出首个完全无需标定板的相机与激光雷达联合标定流程，突破了现有基于深度点对应的标定方法需已知内参的局限。该方法利用深度像素点对应关系，可同时估计包含径向与切向畸变的针孔相机内参以及相机与激光雷达的外参。
◆通过运动恢复结构实现相机内参的自动初始化。
◆将相机与激光雷达特征匹配推广至包含畸变且内参未知的原始图像。
◆将对应点估计与内参及外参的联合非线性优化进行紧密耦合。
在KITTI数据集上的实验表明，该联合标定方法在恢复精确内参的同时有效提升了外参的标定精度。</td></tr>
<tr><td>2026-05-20</td><td>JWST Advanced Deep Extragalactic Survey (JADES) Data Release 5: stellar population catalogue for galaxies in GOODS-N and GOODS-S<br><a href='http://arxiv.org/pdf/2605.21599'>论文</a></td><td>本文发布了JADES第五次数据释放的星系恒星种群星表，利用深空JWST成像和多波段数据对GOODS-N和GOODS-S区域约50万个源进行了均匀的贝叶斯物理性质推断。
星表推导了恒星质量、恒星形成率及尘埃消光等参数的后验分布，推进了对z=1至9约35万个星系低质量极限的测量和近期恒星形成约束。
◆创新性地采用随红移演化的星系主序先验来建模非参数化星系恒星形成历史，在保留非参数灵活性的同时为其提供了物理驱动的长期形状。
◆该先验将恒星质量增长与恒星形成率相联系，允许数据支持下的显著偏离，有效缓解了暗弱源的非物理解并减少了红移、年龄、尘埃与金属丰度间的简并性。
经过验证的公开星表为研究宇宙演化中星系生长、熄灭及恒星质量积累提供了可靠的统计样本。</td></tr>
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
<tr><td>2026-05-12</td><td>3D Gaussian Splatting for Efficient Retrospective Dynamic Scene Novel View Synthesis with a Standardized Benchmark<br><a href='http://arxiv.org/pdf/2605.12437'>论文</a></td><td>本文指出在同步多视角设置下，校准的同步视角已提供充足的空间一致性，动态场景的回溯式新视角合成无需引入显式时间耦合或复杂多体约束。
◆提出一种无需时间变形约束的三维高斯溅射方法，通过在起始时刻初始化运动恢复结构点云并随时间传播优化后的高斯，实现了高效的回溯式动态新视角合成。
◆构建了基于Blender的动态多视角数据集生成框架，能够生成高质量同步相机阵列并导出标准格式数据，消除了坐标系约定和数据管线的不一致性。
利用该框架，本文构建了动态基准测试</td></tr>
<tr><td>2026-05-12</td><td>Compositional Neural Operators for Multi-Dimensional Fluid Dynamics<br><a href='http://arxiv.org/pdf/2605.11691'>论文</a></td><td>本文针对科学基础模型预训练成本高且缺乏可解释性的问题，提出了用于二维流体动力学的组合神经算子框架。该框架的核心思想是将复杂偏微分方程分解并预训练为一系列基础物理算子。
◆构建了包含对流、扩散、非线性对流专用算子及泊松求解器的模块化库，有效解决了不可压缩流体中的压力与速度耦合问题。
◆设计了带有聚合器的适应模块，通过最小化数据损失和源自控制方程的物理残差来学习基础算子间的非线性相互作用。
在对流扩散、伯格斯和纳维-斯托克斯方程上的实验表明，该方法显著提升了模型对新物理系统的适应性与可解释性，并促进了预训练模块的高效复用。</td></tr>
<tr><td>2026-05-11</td><td>3DReflecNet: A Large-Scale Dataset for 3D Reconstruction of Reflective, Transparent, and Low-Texture Objects<br><a href='http://arxiv.org/pdf/2605.10204'>论文</a></td><td>本文针对反射、透明和弱纹理物体3D重建的难题，提出了超大规模混合数据集3DReflecNet。
◆构建了超22TB的大规模混合数据集，包含逾12万个基于物理渲染的合成实例与1千多个真实世界物体，总计超700万帧多视角图像。
◆数据涵盖多种材质、复杂光照及广泛几何形态，并创新性地利用扩散模型管道从真实与LLM合成的2D图像生成3D形状。
◆为图像匹配、运动恢复结构、新视角合成、反射去除和重照明五个核心任务设计了评估基准。
大量实验证明现有先进方法在这些复杂材质下难以保持精度，凸显了该数据集对推动鲁棒3D视觉模型发展的重要价值。</td></tr>
<tr><td>2026-05-06</td><td>egenioussBench: A New Dataset for Geospatial Visual Localisation<br><a href='http://arxiv.org/pdf/2605.05351'>论文</a> | <a href='https://github.com/fratopa/egenioussBench'>代码</a></td><td>◆ We present egenioussBench, a visual localisation benchmark built on geospatial reference data: a city-scale airborne 3D mesh and a CityGML LoD2 model.
◆ This pairing reflects deployable mapping assets and supports true scalability beyond traditional SfM-based approaches.
◆ The query data comprise smartphone images with centimetre-accurate, map-independent ground truth obtained via PPK and GCP/CP-aided adjustment.</td></tr>
<tr><td>2026-05-03</td><td>DP-SfM: Dual-Pixel Structure-from-Motion without Scale Ambiguity<br><a href='http://arxiv.org/pdf/2605.01852'>论文</a> | <a href='https://github.com/lilika-makabe/dp-sfm-tpami.git'>代码</a></td><td>◆ Multi-view 3D reconstruction, namely, structure-from-motion followed by multi-view stereo, is a fundamental component of 3D computer vision.
◆ In general, multi-view 3D reconstruction suffers from an unknown scale ambiguity unless a reference object of known size is present in the scene.
◆ In this article, we show that multi-view images captured using a dual-pixel (DP) sensor can automatically resolve the scale ambiguity, without requiring a reference object or prior calibration.</td></tr>
</tbody>
</table>
</div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-22</td><td>MASt3R-Nav: WayPixel Navigation in Relative 3D Maps<br><a href='http://arxiv.org/pdf/2605.24111'>论文</a></td><td>本文提出MASt3R-Nav导航</td></tr>
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
<tr><td>2026-05-01</td><td>Are Pretrained Image Matchers Good Enough for SAR-Optical Satellite Registration?<br><a href='http://arxiv.org/pdf/2604.10217'>论文</a></td><td>◆ Cross-modal optical-SAR (Synthetic Aperture Radar) registration is a bottleneck for disaster-response via remote sensing, yet modern image matchers are developed and benchmarked almost exclusively on natural-image domains.
◆ We evaluate twenty-four pretrained matcher families--in a zero-shot setting with no fine-tuning or domain adaptation on satellite or SAR data--on SpaceNet9 and two additional cross-modal benchmarks under a deterministic protocol with tiled large-image inference, robust geometric filtering, and tie-point-grounded metrics.
◆ Our results reveal asymmetric transfer--matchers with explicit cross-modal training do not uniformly outperform those without it.</td></tr>
</tbody>
</table>
</div>

<h2 id='obstacle-avoidance'>Obstacle Avoidance</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-26</td><td>Trust, Geometry, and Rules: A Credibility-Aware Reinforcement Learning Framework for Safe USV Navigation under Uncertainty<br><a href='http://arxiv.org/pdf/2605.26974'>论文</a></td><td>本文提出了一种融合可信度感知学习、几何安全屏蔽与连续规则嵌入的强化学习框架，解决了无人艇在感知不确定性下的安全合规导航难题。
◆提出可信度加权价值学习，利用滤波协方差与经验误差的差异推导动态信任因子，调节评论家损失以防止策略对噪声样本过拟合。
◆提出协方差膨胀速度障碍方法，将位置估计不确定性映射为角度边界，构建保守的几何屏蔽以覆盖危险的探索动作。
◆提出风险感知的避碰规则职责嵌入，将二元相遇职责松弛为连续的规则感知信号，提供平滑扇区转换并抑制稀疏奖励引起的振荡。
仿真实验表明该框架提升了对抗感知不一致的训练鲁棒性，在避碰与规则合规性上显著优于基线方法。</td></tr>
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
<tr><td>2026-05-21</td><td>N3P: Accelerated Automated Parking via a Learning-Based Naturalistic Three-Stage Scheme<br><a href='http://arxiv.org/pdf/2605.22722'>论文</a></td><td>针对自动泊车中传统Hybrid A*算法计算昂贵且强化学习可靠性差的问题，本文提出了快速学习的三阶段框架N3P。
◆提出三阶段分解机制，通过引入中间预备姿态将复杂泊车机动分解为更简单的子问题以降低计算复杂度。
◆设计学习模块预测该中间预备姿态，利用数据驱动提供启发式引导，从而大幅加速路径生成。
◆创新性地将学习预测与Hybrid A*算法</td></tr>
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
<tr><td>2026-05-20</td><td>Time-To-Reach Separation and Safety Filtering for Safe, Fair, and Efficient Multi-Agent Coordination<br><a href='http://arxiv.org/pdf/2605.20625'>论文</a></td><td>本文针对城市空中交通拥堵环境，提出了一种用于飞行器走廊合并的多智能体协调框架。
◆提出将最小到达时间TTR作为统一指标，贯穿于优先级分配、时间分离和安全过滤三个核心环节。
◆基于TTR为飞行器分配与到达一致的优先级，并利用目标TTR值强制执行时间间距以诱导空间分离。
◆设计了基于哈密尔顿-雅可比可达性价值函数的优先级一致安全过滤层，在最小化修改参考引导指令的同时确保碰撞避免。
仿真结果表明，相比时间最优引导和优先级无关的安全过滤，该框架在安全性、公平性和效率上均有显著</td></tr>
<tr><td>2026-05-20</td><td>Intent-First Aerial V2V for Tactical Coordination and Separation: Protocol and Performance Under Density and Disturbance<br><a href='http://arxiv.org/pdf/2605.20595'>论文</a></td><td>本文针对密集低空飞行作业，提出了首个与控制器耦合的全空中意图优先车联网战术邻区交换协议栈。
◆不同于仅感知广播，该协议结合了刷新的状态与意图信标，实现本地感知、协同感知及降级模式评估。
◆引入事件触发消息机制，用于避让、排序、释放和应急协调等战术交互。
◆采用具有认证新鲜度检查的直通链路级C-V2X模块实现全空中V2V栈，确保信息的实时与可信。
实验表明该栈能减少过时信息分歧、保持可观测性并抑制虚假推断，在低中密度下提供可行通信层，高复杂度下转为防御性回退，是受干扰城市空域扩展战术协调的有界赋能者。</td></tr>
<tr><td>2026-05-19</td><td>Hamilton--Jacobi Reachability for Spacecraft Collision Avoidance<br><a href='http://arxiv.org/pdf/2605.20138'>论文</a></td><td>本文提出了一个基于哈密顿-雅可比可达性的同圆轨道双星避碰框架。
该框架使用平面HCW动力学建模，并依据FCC标准定义了不安全的相对构型。
◆将航天器交互创新性地建模为控制卫星与有界对抗干扰间的零和微分博弈，以应对未知意图。
◆通过计算后向可达集，精确刻画了最坏干扰下无法避免碰撞的相对状态。
◆证明了后向可达集外的状态容许可证明的无碰撞轨迹，确保了安全性。
◆将可达集与监督混合控制逻辑集成，确定规避机动的触发时机，提供了数学上可靠的安全保证。</td></tr>
<tr><td>2026-05-19</td><td>D-CLING: Prior-Preserving Depth-Conditioned Fine-Tuning for Navigation Foundation Models<br><a href='http://arxiv.org/pdf/2605.19690'>论文</a> | <a href='https://toyotafrc.github.io/DCLING-Proj/'>代码</a></td><td>本文提出了D-CLING微调方法，旨在解决导航基础模型微调时预训练先验被侵蚀及避障失效的问题。该方法让模型在新场景中高效学习的同时，保持预训练的泛化能力以实现鲁棒的长期导航。
◆受ControlNet启发，附加预训练骨干的可训练副本并采用零初始化残差路径连接，使模型高效学习域内几何线索。
◆在获取新环境几何信息的同时，有效保留模型原有的各种预训练行为知识，防止微调破坏先验。
◆实验证明该方法显著减少了真实导航中的碰撞与人工干预，并在微调数据集外维持或提升了动作预测能力，为持续学习提供了重要见解。</td></tr>
<tr><td>2026-05-18</td><td>ManiSoft: Towards Vision-Language Manipulation for Soft Continuum Robotics<br><a href='http://arxiv.org/pdf/2605.18617'>论文</a> | <a href='https://buaa-colalab.github.io/ManiSoft'>代码</a></td><td>本文提出了ManiSoft，一个针对软体连续体机器人的视觉语言操作基准，旨在解决软体臂本体感知不可靠和分布式驱动带来的挑战。
◆提出了一种定制仿真器，通过弹性力约束将逼真的软体动力学与丰富接触交互相结合。
◆定义了四个展示可变形控制不同方面的任务，并构建了自动化流程生成6300个多样化场景及专家轨迹。
◆采用分层方法大规模生成高质量轨迹，即高级规划器分解任务为路径点，低级强化学习策略生成力矩命令进行追踪。
基准测试表明现有模型在随机化下性能显著下降，主要归因于视觉本体感知估计不准及未充分利用软体可变形性避障。
该基准为弥合刚性臂与软体臂在视觉语言操作领域的鸿沟提供了宝贵测试平台。</td></tr>
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

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-26</td><td>Adversarial Dual On-Policy Distillation from Expressive Flow-based Teacher<br><a href='http://arxiv.org/pdf/2605.27095'>论文</a></td><td>针对现有具身控制模仿学习方法仅依赖离线专家数据而缺乏在线纠正信号，且标准在线策略蒸馏无法适用于仅有演示场景的问题，本文提出了FA-OPD方法。该方法从演示中学习流匹配教师并与轻量级MLP学生共同训练，在学生交互过程中提供双通道互补信号。
◆设计奖励通道，通过学习状态-动作对的专家相似性目标来驱动长视野策略优化，促进在线探索。
◆设计动作通道，在学生实际访问的状态上提供密集的局部目标，稳定策略的利用。
◆将双通道巧妙耦合，使奖励蒸馏能够泛化超越逐点演示，同时动作蒸馏将探索锚定在类专家行为附近。
实验表明，在六个机器人导航、操作和运动基准测试中，FA-OPD超越了强基线，并在噪声或有限演示条件下展现出显著增强的鲁棒性。</td></tr>
<tr><td>2026-05-26</td><td>Trust, Geometry, and Rules: A Credibility-Aware Reinforcement Learning Framework for Safe USV Navigation under Uncertainty<br><a href='http://arxiv.org/pdf/2605.26974'>论文</a></td><td>本文针对无人水面艇在感知不确定性下安全且符合COLREGs规则的导航难题，提出了一种融合感知可信学习、几何安全屏蔽与连续规则感知嵌入的强化学习框架。
◆可信度加权价值学习通过滤波协方差与经验误差的差异推导动态信任因子，调节评论家异方差损失，防止策略对噪声过拟合。
◆协方差膨胀速度障碍将位置估计不确定性映射为角度裕度，构建保守的几何屏蔽以覆盖危险探索动作。
◆风险感知的COLREGs责任嵌入将二元相遇责任松弛为连续规则信号，提供平滑扇区转换信息并抑制稀疏奖励引起的振荡。
仿真实验表明，该框架能有效提升应对感知不一致的训练鲁棒性，并在避碰与规则合规性上显著优于基线方法。</td></tr>
<tr><td>2026-05-26</td><td>Orion: Enabling Self-adaptive Memory Management for On-device Online Continual Learning<br><a href='http://arxiv.org/pdf/2605.26473'>论文</a></td><td>本文提出了Orion框架，旨在严格内存约束下协同优化在线持续学习的训练延迟、可塑性与稳定性，实现可行的设备端部署。
◆提出基于木桶效应的统一运行时指标URGE，动态地为在线持续学习各组件重新分配内存。
◆在操作系统和应用层面联合协调批处理、回放缓冲区和优化策略，以自适应应对动态内存压力与工作负载变化。
◆引入系统级数据预取技术，最大化提升执行效率。
实验证明，Orion能显著加速训练并保持性能平衡，同时运行时和能耗开销极低，是设备端持续学习的实用解决方案。</td></tr>
<tr><td>2026-05-25</td><td>RCSP: Risk-Sensitive Conjectural Scenario Planning for Safe Dynamic Robot Navigation<br><a href='http://arxiv.org/pdf/2605.26348'>论文</a></td><td>本文研究了移动机器人在动态障碍物即将关闭通道时提前陷入近险承诺的预测问题，提出了风险敏感推测场景规划（RCSP）层。
◆该规划层通过维护局部运动推测的</td></tr>
<tr><td>2026-05-25</td><td>NightSight: Passive Computation for Navigation in Dark Using Events<br><a href='http://arxiv.org/pdf/2605.26330'>论文</a></td><td>本文针对小型无人机在完全黑暗环境中难以自主导航的挑战，提出了一种结合单目事件相机、编码孔径镜头和红外点投影仪的轻量级感知方案。
◆提出基于结构光与编码光学的隐式几何编码机制，红外图案经编码孔径产生深度依赖的模糊特征以隐式编码场景几何。
◆设计了极简的训练范式，仅用平面墙生成的合成数据训练卷积神经网络解码稠密深度图，即可实现对复杂真实场景的零样本泛化。
◆构建了适用于资源受限平台的高效实时系统，在边缘计算设备上以20赫兹运行，2.5米内深度估计绝对误差仅7.0厘米。
该研究还深入分析了不同编码孔径设计对深度估计性能的影响，展示了结构照明、编码光学与事件感知结合在暗光导航中的巨大潜力。</td></tr>
<tr><td>2026-05-25</td><td>Collaborative Navigation and Exploration with $β$-Sparse Gaussian Processes<br><a href='http://arxiv.org/pdf/2605.26304'>论文</a></td><td>针对未知环境下异构机器人协同导航面临传感、通信和计算限制的问题，本文提出了一种领航机器人与移动传感器机器人的协同导航框架。该框架使传感器能在带宽受限的情况下，在线联合选择传输的地图点与导航动作，并预测未探索区域。
◆提出β-稀疏高斯过程模型，这是一种用于任务感知诱导点选择的新颖且鲁棒的变分稀疏高斯过程模型。
◆开发了一种动作选择策略，有效平衡了任务相关性与环境探索。
仿真实验表明，该框架相比无通信场景可减少18%的路径成本，相比原始数据传输基线可减少76%的信息传输量。</td></tr>
<tr><td>2026-05-25</td><td>G-DRAGON: Geospatial Reasoning and Dynamic Planning for Retrieval-Augmented Outdoor Navigation<br><a href='http://arxiv.org/pdf/2605.25646'>论文</a></td><td>该论文提出了G-DRAGON框架，解决了户外导航中长距离全局规划与最后一步精细探索的挑战。
◆基于轻量级大模型的生成式检索方法，将自然语言指令映射到本地OSM实体以获取准确坐标，有效缓解了云端大模型的幻觉问题。
◆高级规划模块将全局拓扑路线与SLAM系统结合，把地理空间航点投影到机器人可导航坐标系，实现全局到局部的桥接。
◆针对最后一步探索，框架无缝切换至基于边界的探索与开放集语义体素建图，精准定位开放词汇目标。
实验表明该框架性能超越现有基线，并在真实世界无人车上成功完成长达500米的行人搜索任务。</td></tr>
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
<tr><td>2026-05-19</td><td>Enhancing Graph-Based SLAM in GNSS-Denied environments by leveraging leg odometry<br><a href='http://arxiv.org/pdf/2605.20484'>论文</a></td><td>该论文提出了一种基于因子图的SLAM架构，通过融合腿部里程计来解决足式机器人在GNSS拒止环境下的高程漂移问题。
◆在LIO-SAM框架中引入了由本体腿部里程计驱动的并行运动学通道。
◆通过具有选择性噪声模型的恒等相对位姿约束，将运动学通道与主激光雷达惯性通道耦合。
◆</td></tr>
<tr><td>2026-05-19</td><td>KappaPlace: Learning Hyperspherical Uncertainty for Visual Place Recognition via Prototype-Anchored Supervision<br><a href='http://arxiv.org/pdf/2605.19435'>论文</a> | <a href='https://github.com/mayayank95/UncertaintyAwareVPR'>代码</a></td><td>针对现有视觉位置识别方法缺乏校准的不确定性估计这一问题，本文提出了KappaPlace框架以学习不确定性感知的表征。
◆提出原型锚定监督策略，利用潜在类别代表作为概率优化目标的锚点。
◆将图像描述子建模为von Mises-Fisher变量，通过轻量级模块预测浓度参数作为偶然不确定性的直接代理。
◆推导出新颖的匹配级公式，突破了现有方法仅限查询视角的局限，能够量化特定查询与参考图对的匹配可靠性。
该方法提供联合训练与后训练扩展两种模式，在五个基准上将期望校准误差降低高达百分之五十，同时保持或提升检索召回率。
实验证明该框架为位置识别流程提供了鲁棒且校准良好的信号，保障了安全关键应用中的可靠决策。</td></tr>
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

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-26</td><td>TCBiRRT: Rapid Motion Planning for Tightly Coupled Dual-arm Space Manipulator Using Task-space Random Expansion<br><a href='http://arxiv.org/pdf/2605.27167'>论文</a></td><td>本文针对紧密耦合双臂空间机械臂在闭链约束下难以高效规划运动的问题，提出了任务空间约束双向快速扩展随机树算法TCBiRRT。
◆不同于传统高维构型空间方法，该算法直接在由操作物体位姿定义的任务空间内进行随机采样与节点扩展。
◆开发了任务空间节点扩展策略生成候选物体运动，并利用路径逆运动学算法将其映射为连续的关节路径。
◆将上述方法与双向RRT框架及重抓取机制相结合，高效实现了两棵随机树的连接。
实验表明，TCBiRRT在复杂轨道装配场景中不仅成功率显著更高，且规划时间相比现有算法提升了数个数量级。</td></tr>
<tr><td>2026-05-26</td><td>Provably Safe Motion Planning Under Unknown Disturbances<br><a href='http://arxiv.org/pdf/2605.26625'>论文</a></td><td>本文提出了一种针对受未知分布随机扰动影响的机器人系统的可证明安全的运动规划算法，将安全性要求表述为机会约束。该方法利用系统轨迹数据学习Wasserstein模糊管，以高置信度包含状态分布轨迹，并将其应用于生成满足约束的概率完备采样规划树。
◆通过学习多个低维模糊管代替单一高维模糊管，有效降低了规划保守性并提升了算法可扩展性。
◆设计了高效的基于强盗的有效性检查器，在不牺牲概率完备性的前提下显著提升了经验性能。
实验表明该算法能在严格安全阈值与杂乱环境中规划出有效路径，性能优于现有方法。</td></tr>
<tr><td>2026-05-26</td><td>Multi-Robot Box Transport over Different Surfaces with Decentralized Role-based Proportional Control<br><a href='http://arxiv.org/pdf/2605.26430'>论文</a></td><td>该论文提出了一种名为R2P2的异步分散式任务与运动规划方法，解决多机器人在不同倾斜度与摩擦力表面上协同运输箱子的挑战。
◆提出去中心化架构，免除机器人间的通信同步与共识需求，有效规避单点故障。
◆设计基于操作模式动态分配角色的机制，根据旋转或平移需求赋予机器人推、支撑或阻止等角色。
◆融合基于规则的控制与比例速度控制，机器人仅需观测自身与箱子的位置及朝向即可执行动作。
◆方法在多变的地形摩擦、倾斜度及箱子质量场景中展现强泛化能力，成功率优于传统虚拟领导者跟随者方法。
◆通过六台机器人的仿真测试与四台Turtlebot的实物实验，充分验证了该策略的有效性与实用性。</td></tr>
<tr><td>2026-05-25</td><td>Totoro$^+$: An Adaptive and Scalable Edge Federated Learning System<br><a href='http://arxiv.org/pdf/2605.26323'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行</td></tr>
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
<tr><td>2026-05-23</td><td>Sum of Costs Diffusion with Dynamic Guidance for Motion Planning<br><a href='http://arxiv.org/pdf/2605.24690'>论文</a></td><td>针对机器人运动规划中现有方法泛化能力不足的问题，本文提出了一种基于扩散模型的高泛化轨迹生成方法。
◆提出利用总碰撞代价的梯度来引导扩散模型的去噪过程，以生成无碰撞轨迹。
◆提出一种动态选择梯度引导起始步的方法，优化了引导介入的时机。
实验表明，这种基于碰撞代价总和的动态引导克服了现有方法的泛化难题，提升了鲁棒性。
该模型在Mπnets数据集的多样化测试场景中取得了对比方法中的最高性能，验证了其有效性。</td></tr>
<tr><td>2026-05-23</td><td>SparseWorld: Enhancing End-to-End Autonomous Driving via World Models with Sparse Scene Representation<br><a href='http://arxiv.org/pdf/2605.24354'>论文</a> | <a href='https://wryzju.github.io/SparseWorld/'>代码</a></td><td>本文提出了SparseWorld，一个轻量级的自动驾驶世界模型，通过稀疏场景表示仅预测关键场景布局，解决了现有稠密表示计算成本高和信息冗余的问题。
◆提出Sparse Dreamer模块，通过联合时间与空间注意力机制在潜空间中预测未来实例。
◆采用自回归展开方式预测未来地图元素和周围智能体，使模型学习驾驶场景的时间演变规律。
◆使运动规划器与预测的未来实例进行交互，从而捕捉更准确的运动模式并生成更具安全意识的轨迹。
实验表明，该方法大幅降低了碰撞风险，在nuScenes开环规划中达到0.05%碰撞率的领先水平，并在Bench2Drive闭环基准上显著超越基线方法。</td></tr>
<tr><td>2026-05-22</td><td>MASt3R-Nav: WayPixel Navigation in Relative 3D Maps<br><a href='http://arxiv.org/pdf/2605.24111'>论文</a></td><td>本文针对传统三维地图需全局一致性而拓扑图缺乏几何理解限制导航能力的问题，提出了一种新型地图表示与导航系统。
◆提出像素相对连通性地图表示，在保持几何准确性的同时免除了对全局几何一致性的需求。
◆受三维接地图像匹配启发，利用图像对相对三维坐标系中的像素对应关系构建图像间连通性，从而从图像序列构建地图。
◆</td></tr>
<tr><td>2026-05-22</td><td>How Many Training Samples Are Needed for the Inverse Kinematics Solutions by Artificial Neural Networks<br><a href='http://arxiv.org/pdf/2605.23583'>论文</a></td><td>本文研究了人工神经网络求解逆运动学问题时训练样本数量与预测精度之间的关系。研究通过关节型机械臂生成不同数量的关节位置数据对来训练前馈神经网络，并评估了其精度、收敛性与泛化能力。
◆建立了关联训练数据集大小与神经网络逆运动学求解器精度的数学框架。
◆揭示了数据效率的临界点，发现当训练样本超过125个时，继续增加数据量不再提升模型的近似精度与整体效率。
该研究为优化神经网络求解逆运动学的数据规模提供了实用指导，有效平衡了实际机器人应用中的计算成本与模型精度。</td></tr>
<tr><td>2026-05-22</td><td>Signal Temporal Logic Motion Planning via Graphs of Convex Sets<br><a href='http://arxiv.org/pdf/2605.23240'>论文</a></td><td>本文提出了一种结合定时自动机推理与凸集图的高效框架，用于解决信号时序逻辑规范下的连续时间运动规划问题。
◆将STL运动规划问题转化为凸集图上的最短路径问题，通过联合定时自动机与构型空间凸分解构建转移系统，从而生成满足逻辑时序规范、平滑性及速度约束的贝塞尔样条轨迹。
◆证明了该方法的可靠性并分析了计算复杂度，表明在自动机和凸分解固定时，其凸松弛随构型空间维度和贝塞尔度数呈多项式级扩展。
◆针对富有表现力的STL片段，利用专用模板和布尔组合开发了一种紧凑的定时自动机构造方法。
多场景数值实验与硬件测试验证了该方法能高效解决复杂STL运动规划问题并生成平滑可执行轨迹。</td></tr>
<tr><td>2026-05-25</td><td>Fast-dDrive: Efficient Block-Diffusion VLM for Autonomous Driving<br><a href='http://arxiv.org/pdf/2605.23163'>论文</a></td><td>本文提出Fast-dDrive模型，这是一种用于自动驾驶的块扩散视觉语言动作模型，通过在语义单元内</td></tr>
<tr><td>2026-05-20</td><td>Benchmarking Empirical and Learning-Based Approaches for Feedforward Steering Control in Autonomous Racing<br><a href='http://arxiv.org/pdf/2605.21111'>论文</a> | <a href='https://github.com/TUMRT/steering_ff_control'>代码</a></td><td>本文系统性地基准测试了两种基于学习和两种基于经验的前馈转向控制器，以评估其在自动驾驶赛车中减少反馈转向修正的能力。研究在基于真实阿布扎比自动驾驶赛车联赛的高保真双轨车辆动力学模拟器中，对这些控制器进行了开环与闭环测试。
◆提出了一种基于多项式曲面拟合的新型EHD公式，该公式能以最少的参数化捕捉依赖速度的非线性转向行为。
◆揭示了学习型控制器在开环评估中虽预测误差最低，但此优势无法转化为闭环路径跟踪性能或圈速的提升。
◆提出的新型EHD方法取得了最佳的闭环鲁棒性和圈速，突显了必须在完整的轨迹规划与控制软件栈中评估前馈策略的必要性。</td></tr>
<tr><td>2026-05-20</td><td>SubTGraph: Large-Scale Subterranean Environment Synthesis with Controllable Topological Variability for Robotic Autonomy Validation<br><a href='http://arxiv.org/pdf/2605.20917'>论文</a> | <a href='https://github.com/LTU-RAI/SubTGraph.git'>代码</a></td><td>本文提出了SubTGraph框架，填补了地下环境缺乏大规模仿真基准以进行机器人自主性严格统计评估的空白。◆创新性地基于用户结构约束构建代价矩阵，结合Dijkstra算法与拓扑度量瓦片程序化生成多层次地下环境。◆支持高变异性与可控参数合成，用户可根据拓扑、维度和纹理等规范生成矿井、自然洞穴和熔岩管道等不同场景。◆通过语义分割真值验证、多智能体路径规划趋势识别和LIO SLAM极限压力测试三个案例，全面验证了框架对自主栈各层级的评估能力。◆开源了环境生成代码库并发布了包含150个高变异性地下世界的数据库，为该领域提供了关键的基准测试资源。</td></tr>
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

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-05-12</td><td>Mobile Traffic Camera Calibration from Road Geometry for UAV-Based Traffic Surveillance<br><a href='http://arxiv.org/pdf/2605.11900'>论文</a></td><td>本文提出了一种轻量级流程，将单目倾斜无人机交通视频转换为局部度量鸟瞰图表示，解决了原始视频难以直接用于交通分析的问题。
◆创新性地利用可见道路几何特征（车道标线、道路边界和斑马线）估计道路平面单应性矩阵，实现从图像坐标到度量地面坐标的稳定转换。
◆通过估计车辆接地点将观测车辆投影至鸟瞰图，从而在道路平面上实现车辆方向、</td></tr>
<tr><td>2026-05-11</td><td>StereoPolicy: Improving Robotic Manipulation Policies via Stereo Perception<br><a href='http://arxiv.org/pdf/2605.09989'>论文</a></td><td>该论文针对单目视觉在机器人操作中缺乏可靠深度线索和空间感知的问题，提出了StereoPolicy框架以增强几何推理能力。
◆提出直接利用同步双目图像对增强几何推理的框架，无需显式3D重建或相机标定。
◆采用预训练2D视觉编码器独立处理图像，并通过立体视觉Transformer融合表征，隐式捕捉空间对应和视差线索。
◆该框架可无缝集成基于扩散的策略和视觉-语言-动作策略，具有极强的兼容性。
实验表明，该方法在多个仿真基准及真实机器人桌面与双手操作任务中，均一致优于RGB、RGB-D和点云等基线方法。
该研究证实了双目视觉是连接2D预训练表征与3D几何理解的可扩展且鲁棒的模态。</td></tr>
<tr><td>2026-05-10</td><td>VFM-SDM: A vision foundation model-based framework for training-free, marker-free, and calibration-free structural displacement measurement<br><a href='http://arxiv.org/pdf/2605.09677'>论文</a></td><td>该研究提出了基于视觉基础模型的结构位移测量框架VFM-SDM，解决了传统视觉测量依赖特定训练、标记安装或手动标定导致难以实际部署的问题。
◆创新性地结合VFM推断的相机参数估计与点追踪技术，通过三角测量重建多向位移，实现了无需任务特定训练、无标记且免标定的非接触式监测。
◆引入结构几何约束以抑制物理上不合理的偏差，从而提升了估计的一致性与准确性。
◆构建了来自在役人行桥的多模态现场数据集及统一基准测试协议，支持可重复的评估验证。
实验表明该框架在真实条件下具有低幅度误差和高时间一致性，推动了自动化可扩展的位移监测发展，为数字孪生工作流奠定了基础。</td></tr>
<tr><td>2026-05-06</td><td>Optimal Uncertainty-Aware Calibration for the AX=YB Problem<br><a href='http://arxiv.org/pdf/2605.04809'>论文</a></td><td>本文提出了一种求解手眼标定问题的通用优化框架。
◆基于李代数开发了一种迭代算法，在严格保持标定参数结构约束的同时实现参数同步更新，从而获得近似全局最优解。
◆针对现实数据不确定性建模困难的问题，摒弃显式建模，引入不确定性度量评估数据源间的相对不确定性，并据此动态优化迭代过程。
◆设计了一种有效的初始解生成方法，显著提升了算法的收敛效率、整体稳定性和准确性。
数值仿真与真实实验验证了该方法的有效性，其在高不确定性条件下的估计精度相比现有方法至少提升了67%。</td></tr>
<tr><td>2026-05-02</td><td>TT4D: A Pipeline and Dataset for Table Tennis 4D Reconstruction From Monocular Videos<br><a href='http://arxiv.org/pdf/2605.01234'>论文</a></td><td>本文提出了TT4D，这是一个大规模高保真的乒乓球4D重建数据集，包含逾140小时的单双打比赛视频及多模态标注。
◆提出先提升后分割的全新重建流水线，通过学习型网络先将未分割的2D轨迹提升至3D再进行时间分割，解决了传统2D分割在遮挡和多视角下易失效的问题。
◆设计的学习型提升网络具备推断球体旋转、处理不可靠检测以及在高遮挡下成功重建轨迹的能力。
这种核心设计使该流水线成为目前唯一能从通用视角单目广播视频中重建乒乓球比赛的方法。
通过球拍撞击时的姿态与速度估计及训练对抗回合生成模型两项下游任务，验证了该数据集的高保真度。</td></tr>
</tbody>
</table>
</div>


<h2>GitHub 实验室仓库监控</h2>

<h3>HKU-MARS (港大火星实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>4709</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4101</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2405</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1605</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1595</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1404</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1248</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1223</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>915</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>914</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>894</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>791</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>780</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>736</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>721</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>699</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>628</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>622</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>617</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>582</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>560</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>549</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>529</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>498</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>464</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>432</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>389</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>341</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>336</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>261</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>252</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>233</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>221</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>208</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>197</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>194</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>148</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>146</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>142</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>116</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2841</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1629</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1351</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1096</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1035</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>868</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>696</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>654</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>652</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>618</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>582</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>571</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>563</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>559</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>549</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>513</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>479</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>462</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>440</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>439</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>335</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>311</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>298</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>281</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>274</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>258</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>221</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>205</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>201</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>185</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>176</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>168</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>166</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>159</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>150</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>137</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>134</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>131</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
<tr><td><a href='https://github.com/ethz-asl/phaser'>phaser</a></td><td>130</td><td>A robust pointcloud registration pipeline based on</td></tr>
<tr><td><a href='https://github.com/ethz-asl/data-driven-dynamics'>data-driven-dynamics</a></td><td>130</td><td>Data Driven Dynamics Modeling for Aerial Vehicles</td></tr>
<tr><td><a href='https://github.com/ethz-asl/ssc_exploration'>ssc_exploration</a></td><td>111</td><td>Incremental 3D Scene Completion for Safe and Effic</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waypoint_navigator'>waypoint_navigator</a></td><td>107</td><td>Stand-alone waypoint navigator</td></tr>
<tr><td><a href='https://github.com/ethz-asl/active_grasp'>active_grasp</a></td><td>107</td><td>Closed-loop next-best view planning for grasp dete</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waverider'>waverider</a></td><td>107</td><td>RMPs on multi-resolution occupancy maps for effici</td></tr>
<tr><td><a href='https://github.com/ethz-asl/reinmav-gym'>reinmav-gym</a></td><td>106</td><td>Reinforcement Learning framework for MAVs using th</td></tr>
<tr><td><a href='https://github.com/ethz-asl/navrep'>navrep</a></td><td>104</td><td>navrep</td></tr>
<tr><td><a href='https://github.com/ethz-asl/eth_supermegabot'>eth_supermegabot</a></td><td>102</td><td>Instructions for ETH center for robotics summer sc</td></tr>
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>102</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.05.27
