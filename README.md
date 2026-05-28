# 计算机视觉领域最新论文 (2026.05.28)

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
<tr><td>2026-05-26</td><td>Trinity: Unifying Class-Agnostic Terrain and Semantic Segmentation for Unstructured Outdoor Environments by Leveraging Synthetic Data<br><a href='http://arxiv.org/pdf/2605.27644'>论文</a></td><td>本文提出了一种基于Transformer的Trinity架构，旨在解决现有可穿越性估计方法跨平台迁移性差及标准语义分割无法捕捉地形多样性的问题。
◆提出统一网络联合执行类特定语义分割和类无关地形分割，其中地形分割仅基于视觉外观，无需预定义标签或机器人特定分数，从而学习机器人无关的视觉地形先验，便于结合特定经验用于下游任务。
◆扩展了OAISYS模拟器并引入RUGDSynth合成数据集，提供大规模的类无关地形样本以支持模型训练。
◆发布了EXTerra真实世界数据集，包含类特定与类无关地形双重标注，填补了相关真实数据空白。
实验充分验证了该联合分割方法在复杂户外环境中的可行性与有效性。</td></tr>
<tr><td>2026-05-26</td><td>Gaussian Process-Based Extended Object Estimation for 6G ISAC at Millimeter-Wave Frequencies<br><a href='http://arxiv.org/pdf/2605.26915'>论文</a></td><td>本文提出了一种基于高斯过程的扩展目标估计方法，用于6G毫米波通感一体化场景。
◆突破了传统点散射体假设的限制，利用高斯过程实现了对扩展目标的更优估计。
◆结合符合5G新空口标准的双基地感知实际测量平台，验证了该方法在毫米波频段的实用性。
◆证明了通信网络能力增强与双基地感知及高斯过程估计相结合，可有效提升未来无线系统的环境感知能力。
研究结果表明，高斯过程在毫米波建图和同步定位与建图场景中均能有效完成扩展目标估计。</td></tr>
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
<tr><td>2026-05-19</td><td>EpiDiffVO: Geometry-Aware Epipolar Diffusion for Robust Visual Odometry<br><a href='http://arxiv.org/pdf/2605.19556'>论文</a></td><td>针对现有学习型视觉里程计依赖稠密匹配导致冗余且几何可解释性差的问题，本文提出了一种基于几何感知对极扩散的稀疏匹配框架。
◆引入对极扩散过程，通过建模对应点不确定性将关键点细化至对极一致性，以解决残差噪声与未对齐问题。
◆提出Steiner图表示法，将细化后的对应点与深度线索结合，利用图神经网络学习并筛选出信息量大的紧凑对应点子集。
筛选出的子集被输入可微奇异值分解求解器，实现端到端的相对位姿估计。
实验表明，该方法在减少匹配冗余的同时，能在具有挑战性的基线下保持鲁棒的位姿估计。</td></tr>
<tr><td>2026-05-27</td><td>PRISM-SLAM: Probabilistic Ray-Grounded Inference for Scale-aware Metric SLAM<br><a href='http://arxiv.org/pdf/2605.19257'>论文</a> | <a href='https://prismslam-cmd.github.io/prismslam_pr/'>代码</a></td><td>针对单目SLAM的尺度模糊与动态环境跟踪失败问题，本文提出PRISM-SLAM框架，通过将视觉基础模型先验严谨集成到贝叶斯因子图中，实现了尺度感知且度量一致的实时定位与建图。
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-27</td><td>CLEAR-NeRF: Collinearity and Local-region Enhanced Accurate 3D Reconstruction in Unbounded Scenes<br><a href='http://arxiv.org/pdf/2605.28125'>论文</a></td><td>本研究提出CLEAR-NeRF方法，将基于NeRF的三维重建应用于多关注区域的无界场景，提升了应对光照和位姿变化的鲁棒性，并确保了适用于数字孪生的度量精度。
◆自动局部区域定位检测与重建，无需增加子模块即可无缝优先处理关注区域。
◆共线性强制的射线采样，以学习平滑的平面和曲面。
◆深度定位邻域点提取，有效抑制表面伪影。
◆几何相关颜色聚合，缓解由光照和位姿引起的颜色变化。
实验表明该方法的性能显著优于基线NeRF模型和传统SfM-MVS解决方案。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-05-27</td><td>EventShiftFlow: Towards Hardware-efficient FPGA-based Flow Estimation<br><a href='http://arxiv.org/pdf/2605.28312'>论文</a></td><td>本文提出了一种面向FPGA的流式速度估计器EventShiftFlow，旨在解决现有事件相机运动估计算法计算量大且难以硬件映射的问题。该方法将异步事件离散化为固定时长的时间窗并构建1位空间占用网格，通过并行评估多个速度假设来输出稀疏量化的速度估计。
◆提出纯整数逻辑的数据通路设计，仅使用移位寄存器、计数器、比较器和LUT映射的小型乘法器，无需浮点运算、除法器、DSP模块、帧重建和迭代优化。
◆在算法与硬件间进行针对性权衡，放弃稠密亚像素光流，换取每个活跃像素的稀疏量化速度估计，满足低延迟和资源受限平台的实时避障需求。
◆实现极低硬件开销的FPGA部署，数据通路存储需求小于2kB，并在低成本FPGA上完成原型验证，同时在真实数据集中达到了99.5%的方向准确率。</td></tr>
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
<tr><td>2026-05-18</td><td>Adversarial Stress Testing of SPARK Humanoid Safety Filters<br><a href='http://arxiv.org/pdf/2605.19009'>论文</a></td><td>本文研究了SPARK人形机器人安全滤波器的鲁棒性，指出现有基准评分无法全面揭示其在严苛环境下的真实安全行为。
◆在MuJoCo中复现了SPARK基准用例，并在受控随机种子下系统评估了六种主流安全滤波方法。
◆构建了专用的后处理流程，将原始运行日志转化为目标跟踪、最小距离和碰撞步数等可量化的核心指标。
◆引入对抗性压力测试，揭示了障碍物拥挤、距离估计噪声及信息延迟等极端条件对安全行为的显著影响。
实验表明不同方法在目标跟踪与碰撞规避上存在权衡，强调人形机器人部署前必须超越标称性能，采用能暴露故障模式的指标进行严格评估。</td></tr>
<tr><td>2026-05-18</td><td>ManiSoft: Towards Vision-Language Manipulation for Soft Continuum Robotics<br><a href='http://arxiv.org/pdf/2605.18617'>论文</a> | <a href='https://buaa-colalab.github.io/ManiSoft'>代码</a></td><td>本文提出了ManiSoft，一个针对软体连续体机器人的视觉语言操作基准，旨在解决软体臂本体感知不可靠和分布式驱动带来的挑战。
◆提出了一种定制仿真器，通过弹性力约束将逼真的软体动力学与丰富接触交互相结合。
◆定义了四个展示可变形控制不同方面的任务，并构建了自动化流程生成6300个多样化场景及专家轨迹。
◆采用分层方法大规模生成高质量轨迹，即高级规划器分解任务为路径点，低级强化学习策略生成力矩命令进行追踪。
基准测试表明现有模型在随机化下性能显著下降，主要归因于视觉本体感知估计不准及未充分利用软体可变形性避障。
该基准为弥合刚性臂与软体臂在视觉语言操作领域的鸿沟提供了宝贵测试平台。</td></tr>
<tr><td>2026-05-18</td><td>The distance-based formation controller design for multi-agent systems in port-Hamiltonian form<br><a href='http://arxiv.org/pdf/2605.18502'>论文</a></td><td>本文针对端口哈密顿多智能体系统，研究了基于距离的编队控制与防碰撞集成问题，提出了一种统一控制器同时实现速度跟踪、目标编队获取及智能体间安全。
◆构造了具有满列秩性质的符号关联矩阵，其对应有向无环图，为控制器设计奠定基础。
◆引入仅吸引势场设计，有效克服了传统人工势场中普遍存在的局部极小值问题。
◆结合安全屏障机制，在无排斥势场的情况下严格保障了防碰撞约束。
闭环系统稳定性由LaSalle不变集原理保证，数值仿真验证了该策略的有效性。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-27</td><td>Chance-Constrained MPPI under State and Dynamic Object Prediction Uncertainty and the Evaluation of Collision Risk Calibration<br><a href='http://arxiv.org/pdf/2605.28330'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-05-27</td><td>STR Robot: Design of an Autonomous Mobile Robot from Simulation to Reality<br><a href='http://arxiv.org/pdf/2605.28110'>论文</a> | <a href='https://ntdathp.github.io/outdoor-robot-web'>代码</a></td><td>本文核心贡献是实现了基于现有机械平台的自主移动机器人从仿真到现实的完整部署。研究未聚焦机械设计，而是重点开发了机载控制、自定位与自主导航系统。
◆创新性地将机载感知与计算相结合，实现了无需外部辅助的机器人位姿估计与自主导航。
◆验证了一套仿真优先的开发框架，即先在仿真中构建与测试整体系统，再成功部署至真实机器人，证明了仿真是开发可靠系统的有效基础。
项目代码即将开源，为相关研究提供了可复用的资源。</td></tr>
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
<tr><td>2026-05-19</td><td>Enhancing Graph-Based SLAM in GNSS-Denied environments by leveraging leg odometry<br><a href='http://arxiv.org/pdf/2605.20484'>论文</a></td><td>本文针对足式机器人在GNSS拒止环境中因几何稀疏或重复场景导致激光雷达产生高程漂移的问题，提出了一种增强图优化SLAM的新架构。该方法通过融合本体感知的腿部里程计，有效弥补了外部感知传感器的垂直漂移缺陷。实验表明，在超过一公里的户外测试中，该方法将高程漂移从30多米降至30厘米以内，并使基线方法完全失效的场景成功收敛。
◆在LIO-SAM框架中引入由腿部里程计驱动的并行运动学通道。
◆通过带有选择性噪声模型的恒等相对位姿约束，将运动学通道与主激光雷达惯性通道耦合。
◆挖掘用于步态控制的本体感知数据，为SLAM提供轻量且有效的垂直锚点。</td></tr>
<tr><td>2026-05-19</td><td>KappaPlace: Learning Hyperspherical Uncertainty for Visual Place Recognition via Prototype-Anchored Supervision<br><a href='http://arxiv.org/pdf/2605.19435'>论文</a> | <a href='https://github.com/mayayank95/UncertaintyAwareVPR'>代码</a></td><td>针对现有视觉位置识别方法缺乏校准的不确定性估计这一问题，本文提出了KappaPlace框架以学习不确定性感知的表征。
◆提出原型锚定监督策略，利用潜在类别代表作为概率优化目标的锚点。
◆将图像描述子建模为von Mises-Fisher变量，通过轻量级模块预测浓度参数作为偶然不确定性的直接代理。
◆推导出新颖的匹配级公式，突破了现有方法仅限查询视角的局限，能够量化特定查询与参考图对的匹配可靠性。
该方法提供联合训练与后训练扩展两种模式，在五个基准上将期望校准误差降低高达百分之五十，同时保持或提升检索召回率。
实验证明该框架为位置识别流程提供了鲁棒且校准良好的信号，保障了安全关键应用中的可靠决策。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-05-26</td><td>AURA: Asymptotically Optimal Uncertainty-Robust Replanning Algorithm for Kinodynamic Systems<br><a href='http://arxiv.org/pdf/2605.27699'>论文</a></td><td>本文提出了AURA框架，这是一个针对运动学动态系统的渐近最优元规划器，解决了传统离线规划无法即时执行以及运动不确定性导致跟踪偏差的两大局限。
◆提出一种重规划方法，在执行过程中持续探索状态空间并优化轨迹，实现了渐近最优的在线规划。
◆引入优化过程，通过细化未来控制输入来减少跟踪误差，有效提升了运动不确定性下的执行精度。
该框架将重规划与控制优化相统一，使系统能够在发挥在线渐近最优规划优势的同时提高执行准确性。
仿真和真实世界的多系统实验表明，AURA在轨迹质量、跟踪精度和整体性能上均显著优于基线方法。</td></tr>
<tr><td>2026-05-26</td><td>Simulation-Informed Diffusion for Decentralized Multi-robot Motion Planning<br><a href='http://arxiv.org/pdf/2605.27697'>论文</a></td><td>本文针对去中心化多机器人运动规划中现有方法无法预测邻居未来行为的局限，提出了仿真信息扩散框架。该框架基于约束感知扩散模型，有效提升了对未来动态的预判与安全规划能力。
◆提出仿真与规划双阶段机制，先模拟邻居机器人的未来轨迹，再依据仿真结果与安全约束规划自身轨迹。
◆设计了一种最小通信方案，借助精确的邻居仿真，仅在高度拥挤时才触发必要的通信协调。
◆在扩展性与规划性能上取得突破，在108台机器人和160个障碍物的大规模场景中，其规划有效性与约束满足度显著优于基线方法。</td></tr>
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
<tr><td>2026-05-25</td><td>Totoro$^+$: An Adaptive and Scalable Edge Federated Learning System<br><a href='http://arxiv.org/pdf/2605.26323'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-05-25</td><td>Fast-dDrive: Efficient Block-Diffusion VLM for Autonomous Driving<br><a href='http://arxiv.org/pdf/2605.23163'>论文</a></td><td>本文提出Fast-dDrive，一种用于自动驾驶的块扩散视觉语言动作模型，解决了自回归模型内存受限和全序列扩散模型逻辑泄漏的问题，实现了轨迹规划与高效推理的平衡。
◆提出块扩散机制，在语义单元内进行双向细化，同时跨单元保持严格的因果顺序。
◆针对结构化输出冻结结构标记为段落支架，并采用优先安全关键规划的段落感知训练策略。
◆引入支架投机解码，在保证自回归相当质量的同时显著提升推理吞吐量。
◆提出低开销测试时扩展方案，通过共享前缀KV缓存分叉并平均N个随机轨迹来抑制预测方差。
实验表明该模型在WOD-E2E和nuScenes上取得SOTA精度，结合SGLang实现12倍吞吐量提升，满足实时车载部署需求。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-undistortion'>Sensor Undistortion</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-27</td><td>Resolution-free neural surrogates for geometric parameterization and mapping with spatially varying fields<br><a href='http://arxiv.org/pdf/2605.28551'>论文</a></td><td>针对空间变化场引起的几何映射问题，传统变分模型在处理高分辨率且参数场变化的实例时计算成本极高。本文提出一种分辨率无关的神经代理模型，可在任意结构化或非结构化点集上直接预测映射位置。
◆采用多分辨率几何编码策略，以坐标增强的参数场样本为网络条件，摆脱了对固定网格的依赖。
◆无需带标签的解数据进行训练，而是通过强制执行源自变分能量、扩散密度均衡和拟共形理论的几何感知约束来优化模型。
实验表明该方法在拟共形映射和密度均衡映射问题上具有显著有效性。</td></tr>
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
<tr><td>2026-05-21</td><td>SpaceDG: Benchmarking Spatial Intelligence under Visual Degradation<br><a href='http://arxiv.org/pdf/2605.22536'>论文</a></td><td>本文提出了SpaceDG，首个针对视觉退化条件下空间理解的大规模数据集与基准，填补了现有空间推理基准忽视真实世界视觉退化的空白。
◆首创物理驱动的退化合成引擎，将退化形成过程嵌入3D高斯溅射渲染中，真实模拟九种退化类型并生成约百万问答对。
◆构建了经人工验证的SpaceDG-Bench基准，涵盖11个推理类别与9种退化类型，产生逾万条视觉问答实例。
◆对25个多模态大模型的全面评估揭示了视觉退化会显著损害空间推理能力，暴露出模型关键的鲁棒性缺陷。
◆证实了退化感知训练的潜力，在SpaceDG上微调不仅能大幅提升退化条件下的鲁棒性甚至超越人类，且不牺牲清晰图像的性能。</td></tr>
<tr><td>2026-05-08</td><td>A Task-Agnostic Algebraic Integrity Metric for Event-Camera Streams Toward SOTIF-Compliant Perception using Pearson Correlation Coefficient<br><a href='http://arxiv.org/pdf/2605.21500'>论文</a></td><td>本文针对事件相机异步流缺乏任务无关的质量评估指标问题，提出统一代数框架以满足自动驾驶SOTIF认证需求。
◆创新性地将皮尔逊相关系数提升至时间面、事件帧和体素网格三种标准事件表示形式。
◆推导出用于流完整性监控的r-TS、仅需整数比较的自适应ROI指标r2-EF，以及时间冗余门控指标r-VG。
◆建立了事件相机对比度阈值机制与基于PCC变化准则的结构同构性，并对流水线延迟与信息损失进行对称分析。
通过直接模拟发射模型生成的合成事件流验证了指标，在隧道异常场景中指标成功从0.93降至负值并触发报警。</td></tr>
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
<tr><td>2026-05-11</td><td>VVitCutLER: Towards Unsupervised Object Detection and Segmentation in Videos<br><a href='http://arxiv.org/pdf/2605.17584'>论文</a></td><td>本文针对无监督视频理解中因运动模糊和遮挡导致伪标签时序漂移与闪烁的问题，提出了无监督视频目标检测与实例分割框架VVitCutLER。
◆提出时序稳定的伪标签生成器VitCut，通过跨帧区域一致性来减少退化过程中的误差累积。
◆设计了蒸馏解码器，以实现高效准确的实例掩码预测。
◆在VVitCutLER框架中集成了跨帧特征聚合机制，进一步增强了视频级别的鲁棒性。
实验证明该方法显著提升了检测与分割性能并降低了时序不稳定性，凸显了时序一致性监督对于鲁棒视频理解的重要性。</td></tr>
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

<h2 id='archive'>归档</h2>

> [点击查看所有历史论文归档](./docs/archive.md)


<h2>GitHub 实验室仓库监控</h2>

<h3>HKU-MARS (港大火星实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>4716</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4109</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2406</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1605</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1596</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1405</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1248</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1224</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>916</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>914</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>898</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>791</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>780</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>736</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>721</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>700</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>629</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>621</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>619</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>582</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>560</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>549</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>529</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>498</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>464</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>433</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>391</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>341</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>336</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>261</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>252</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>233</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>221</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>211</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>197</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>195</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>151</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>560</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>549</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>513</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>479</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>462</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>440</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>440</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
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
> 更新于: 2026.05.28
