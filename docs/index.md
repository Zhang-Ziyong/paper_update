# 计算机视觉领域最新论文 (2026.10.21)

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
<tr><td>2026-10-20</td><td>MAPLE: Mondrian-Anchored Prior for Learning-free Indoor Exploration<br><a href='http://arxiv.org/pdf/2610.28566'>论文</a></td><td>本文提出MAPLE，一种面向未知室内环境的无训练预测探索方法，利用在线生成先验改进移动决策。
◆将Mondrian过程改造为以当前部分地图观测几何为条件的在线生成先验，无需离线训练或反复模型推理。
◆生成多个合理地图假设，并在每个假设内单独评估可见性以估计前沿增益，从而保留不同假设间的预测可见性差异。
◆采用轻量程序化构建，使预测探索可在有限计算资源下运行，并在KTH平面图和真实SLAM环境中跨多个传感器范围验证有效性。
实验表明MAPLE稳定优于非预测探索，并与学习型预测方法保持竞争力；结果还揭示更准确的地图预测不一定带来更好探索，关键在于预测的表示与使用方式。</td></tr>
<tr><td>2026-10-20</td><td>A Head Camera Is (Almost) All You Need: An Electronics-Free UMI Glove Labelled and Observed by One Moving Camera<br><a href='http://arxiv.org/pdf/2610.27622'>论文</a></td><td>本文提出一种几乎仅需头戴相机的无电子UMI手套数据采集与策略学习方案，用单一眼动相机同时完成手套标记、夹爪位姿与夹爪开度观测，替代传统腕相机、位姿跟踪器及多数据流同步校准。
◆ 以印刷fiducial的无电子手套和纸面标定块，让同一头戴相机帧直接给出6-DoF夹爪位姿与夹爪宽度，并作为策略输入。
◆ 部署时用低成本机械臂携带同一相机，依据机器人关节状态模仿采集者头部视角，避免额外传感器与标定链路。
◆ 标签相对机器人编码器的中位误差仅6.5 mm和1.6度，帧覆盖93-100%，用其训练策略仅增加约3%验证损失。
◆ 仅加入194条手套演示即可将48条遥操作的成功率从10/25提升到17/25，接近172条遥操作单独训练的18/25。
◆ 联合训练的头相机策略达到20/25，优于腕相机15/25和固定相机12/25，并缓解目标离开视野时掉物问题。</td></tr>
<tr><td>2026-10-19</td><td>V-JEPA Hand: Simple, Accurate and Fast 3D Hand and Camera Trajectory Recovery from Egocentric Videos<br><a href='http://arxiv.org/pdf/2610.26780'>论文</a> | <a href='https://qft-333.github.io/V-JEPA-Hand-Page/'>代码</a></td><td>论文提出V-JEPA Hand，一个简单的前馈视频模型，可从第一视角视频中联合恢复双手运动与相机自运动。◆采用自监督V-JEPA 2.1编码器提取全帧时空特征，并用查询式预测器一次性解码每帧手部姿态、手部存在性和相机运动。◆将预测的相机运动用于把双手轨迹统一表达在世界坐标系中，并支持已知焦距或自动预测焦距。◆整个片段仅需单次前向传播即可完成重建，避免传统多阶段流水线。◆模型以单阶段端到端方式，在混合伪标签视频和高精度3D标注上联合训练两个组件。实验表明其在ARCTIC、HOT3D和EgoStandard上取得最低覆盖感知MPJPE，世界坐标轨迹误差低于对比的SLAM流程，并在单张RTX A6000上达到93.4 FPS。</td></tr>
<tr><td>2026-10-19</td><td>CAOS-SLAM: Class-Agnostic Object-Aware Real-Time vSLAM for Dynamic Environments<br><a href='http://arxiv.org/pdf/2610.26633'>论文</a></td><td>本文提出CAOS-SLAM，一个面向动态环境的类无关对象感知实时vSLAM框架，在ORB-SLAM3基础上扩展混合感知管线，可同时检测、跟踪并过滤语义已知和此前未见的运动物体。
◆ 采用按需全景分割进行对象发现，并通过未分类区域的深度聚类实例化未知候选对象，降低对预定义语义类别的依赖。
◆ 在全景更新之间，利用轻量检测或基于世界坐标系Kalman预测、深度一致性和外观相似性的时序掩码传播维持持久对象轨迹。
◆ 将估计的对象运动用于剔除SLAM管线中的动态特征，从而减少错误观测对定位与建图的影响。
实验在多个动态RGB-D数据集和真实场景中验证，未知动态物体场景定位误差最高降低59%，重遮挡场景最高降低88%，并在笔记本上达到中位30 FPS。
此外，跟踪模块可输出对象轨迹和速度，为动态环境中的感知、导航与运动规划提供支持。</td></tr>
<tr><td>2026-10-19</td><td>EgoXperience: Learning World-Grounded Egocentric Representations from Human Experience<br><a href='http://arxiv.org/pdf/2610.26625'>论文</a></td><td>论文提出EgoXperience全栈范式，通过数据采集、自动标注、统一建模和基准测试，解决第一视角视频中相机运动、场景几何与手物交互难以保持一致世界的问题。
◆ 设计EgoX-Engine自动标注引擎，将几何验证的对象跟踪与基于SLAM的世界对齐结合，为相机、场景、手和物体提供一致监督。
◆ 构建EgoX-Data-6M数据集，包含50小时室内外任务驱动操作与移动视频及秒级任务描述，并精选1小时形成EgoX-Bench联合重建基准。
◆ 提出EgoX模型，输入单目第一视角视频和首帧物体掩码，单次前向即可在共享世界坐标系中联合度量重建相机、场景、手和物体。
◆ 实验表明其在场景估计和世界空间手物姿态恢复上达到最优，相比最强基线将相机、手和深度误差分别降低68.9%、65.6%、42.9%，物体姿态分数提升28.0%。</td></tr>
<tr><td>2026-10-18</td><td>GOFusion: Real-Time Gaussian-Occupancy Submap Fusion for Fisher-Informed Autonomous Robot Navigation<br><a href='http://arxiv.org/pdf/2610.25261'>论文</a> | <a href='https://github.com/Bennnoo/GOFusion'>代码</a></td><td>GOFusion提出一种面向自主机器人导航的实时视觉建图系统，将高斯原语锚定到局部占据地图，同时提供路径规划所需的空间感知和高保真外观信息。  
◆ 将3D高斯地图与视觉惯性SLAM得到的位姿和局部占据地图结合，并支持位姿校正以保持几何与视觉一致性。  
◆ 将3D高斯泼溅优化限制在活动子地图内，从而约束GPU显存占用并支持大规模实时建图。  
◆ 提出光栅化集成的Fisher近似，在线量化每个高斯原语的敏感度，作为信息驱动启发式用于高斯剪枝和下一最佳视角规划。  
◆ 在公开数据集和真实无人机飞行中验证，建图质量优于多个基线，并实现实时、高保真、不确定性感知的大规模建图。  
◆ 进一步利用Fisher信息启发式实现全自主无人机探索与高斯地图精化。</td></tr>
<tr><td>2026-10-16</td><td>The Rise of Personal Trackers as the Next Infrastructure for Ubiquitous Positioning<br><a href='http://arxiv.org/pdf/2610.24249'>论文</a></td><td>论文指出室内定位长期依赖厂商部署和校准的固定基础设施，难以规模化，而个人追踪器等移动设备正密集嵌入室内空间。为此，作者提出TrackerNet愿景，将私人找物设备转化为去中心化、用户拥有且语义可解释的泛在定位基础设施。
◆ 核心转变是不再把锚点移动视为噪声，而将其建模为概率参考，随时间推断稳定性、信任与语义角色，把室内定位重构为非平稳空间图推断。
◆ 提出面向移动且间歇可见锚点的非平稳SLAM研究前沿。
◆ 提出连接测距信号与锚点行为解释的语义推理研究前沿。
◆ 提出基于同意、隐私保护的跨厂商协作治理研究前沿。
论文还给出厂商、场馆运营者与学术界合作的分阶段实现路径，并明确自身不是已完成系统，而是定义研究议程。</td></tr>
<tr><td>2026-10-16</td><td>F-LIVO: A Feature-Level Geometric Measurement Framework for LiDAR-Inertial-Visual Odometry<br><a href='http://arxiv.org/pdf/2610.23595'>论文</a></td><td>本文提出F-LIVO，一种基于滤波的LiDAR-惯性-视觉里程计框架，通过视觉点与LiDAR平面间的特征级点到面约束耦合视觉惯性子系统和激光惯性子系统。
◆ 采用特征级点到面约束实现跨模态耦合，避免持续附着稠密光度块或外观属性所带来的存储、关联与更新开销。
◆ 在视觉三角化较弱时，利用局部平面拟合和射线-平面相交从LiDAR地图恢复视觉特征深度，以保持跨模态耦合。
◆ 在LiDAR更新中依据局部平面可靠性自适应缩放点到面残差协方差，减少病态表面上的过自信更新。
该方法依赖稀疏几何特征而非持续维护的稠密光度地图属性，从而保持紧凑的地图表示。
实验表明其在多个公开数据集上具有有竞争力且随序列变化的精度，在退化场景中保持连续估计和较低累计端到端漂移，并在评估资源配置下取得最低平均与峰值CPU占用、最低峰值RSS和最低RSS增长率。</td></tr>
<tr><td>2026-10-16</td><td>FLoTS-SLAM: Optical Flow-Derived Uncertainty for Monocular Dynamic SLAM with Two-Stage Optimization<br><a href='http://arxiv.org/pdf/2610.23496'>论文</a></td><td>本文提出面向动态场景的单目RGB SLAM系统FLoTS-SLAM，旨在利用光流导出的运动不确定性提升动态环境下的定位与建图鲁棒性。
◆ 提出由光流与相机运动诱导光流之间的残差估计像素级运动不确定性，直接反映物体运动，并随帧对齐精度变化，从而减少误检并获得更准确的动态区域掩码。
◆ 设计两阶段优化：先用高置信像素估计相机位姿，再在位姿与深度联合细化中对动态像素重投影，降低动态物体运动对位姿和深度更新的干扰。
◆ 对动态掩码进行定量评估，并分析掩码对下游动态对象跟踪与重建的影响。
实验表明该方法在DAVIS上将动态掩码平均IoU相比先进基线提升35%，在Bonn和TUM上分别将平均ATE相对所用SLAM主干降低59%和19%。</td></tr>
<tr><td>2026-10-15</td><td>RTISSLAM-3D: Full 6-DoF SLAM With an In-Air 3D Imaging Sonar<br><a href='http://arxiv.org/pdf/2610.22552'>论文</a></td><td>RTISSLAM-3D提出了一种面向轮式机器人的全6自由度声纳SLAM系统，突破了现有声纳SLAM仅估计2D轨迹、丢弃仰角信息的平面假设，可在森林地面等崎岖倾斜地形中工作。
◆ 利用空中3D成像声纳获取整个前半球信息，并结合IMU与轮式编码器实现6自由度定位与建图。
◆ 在球面上采用CFAR检测将声纳图像稀疏化为3D检测点，为后续声学里程计、地点识别和回环验证提供统一数据基础。
◆ 提出建模声纳波束形状的3D声学里程计，提升声纳观测下的三维运动估计能力。
◆ 采用极坐标子图描述子进行地点识别，并通过3D配准验证回环，将声学里程计、回环与姿态因子融合进6自由度位姿图。
在545米森林行驶实验中，以3D激光雷达SLAM为参考，回环将水平误差从1.74米降至0.28米，高度误差为0.12米，且94.6%的3D声纳地图位于激光雷达地图0.3米范围内。</td></tr>
<tr><td>2026-10-15</td><td>KFS$^4$LAM: Adaptive KeyFrame Selection with Structure-Aware Mapping for Endoscopic Gaussian Splatting SLAM<br><a href='http://arxiv.org/pdf/2610.22505'>论文</a> | <a href='https://xinweiju.github.io/KFSLAM/'>代码</a></td><td>论文提出KFS⁴LAM，一种面向内窥镜高斯泼溅SLAM的自适应关键帧选择与结构感知建图框架，旨在解决结肠镜中非均匀运动、重复解剖、镜面反射和视觉伪影导致的关键帧选择不可靠问题。
◆ 提出运动引导的自适应关键帧选择机制，利用累积运动并结合互补线索抑制冗余或不可靠候选视角。
◆ 设计密度感知建图与解剖轮廓监督，利用结肠褶皱等结构信息强化结构信息丰富区域的建模。
◆ 引入受限时序变形，在适应局部组织动态的同时避免无约束几何漂移。
在C3VD和C3VD-v2上，该方法在轨迹、渲染和深度指标上整体优于Gaussian-SLAM基线，且在更困难的C3VD-v2上增益明显。
与SplaTAM匹配比较时，旋转相对位姿误差降低20.3%，深度RMSE降低38.4%，PSNR提升0.78 dB。
跨骨干实验表明该框架不依赖单一底层SLAM架构，具有良好的通用性。</td></tr>
<tr><td>2026-10-15</td><td>AVALON: Zero-Shot Indoor Navigation with Human-Seeded Topological Memory<br><a href='http://arxiv.org/pdf/2610.21586'>论文</a></td><td>AVALON面向“人类熟悉、机器人未见”的室内服务场景，提出无需现场遍历或站点训练、仅靠楼层平面图、地点线索和初始拓扑-里程计对齐的零样本拓扑导航框架。
◆ 提出人类种子分层空间记忆，用人类先验组织环境，并让视觉深度点目标导航通过已验证节点到达进行平移重锚定，无需机器人构建全局SLAM地图。
◆ 提出节点验证的拓扑执行机制，确保机器人在拓扑路线上的到达与执行可信。
◆ 提出任务触发、证据门控的人机记忆协同更新，融合人类任务约束与离线环境修改，以及机器人主动实地验证的物理状态证据，并分离人类许可与机器人观测可通行性。
在Unitree Go2实验中，AVALON配合X-NavDP完成12.81米Intersection-to-Dining任务仅46.4秒（5/5），比DimOS-Go2少40.9%机器人时间，而仅策略的X-NavDP五次均超时。</td></tr>
<tr><td>2026-10-15</td><td>CLAD: Keypoint Matching Using Global Line Correspondences<br><a href='http://arxiv.org/pdf/2610.21409'>论文</a></td><td>论文提出CLAD，一种利用全局线对应几何上下文的关键点匹配方法，旨在解决重复纹理或弱纹理场景中局部描述子不可靠的问题。
◆ 提出用关键点到匹配直线的邻近关系构成描述子，将全局空间结构引入关键点表示。
◆ 采用HOME检测清晰与弱线性结构并建立线-关键点关联，为描述子提供充分全局线上下文。
◆ 在重复场景中利用全局结构区分相似局部块，提升匹配可靠性并产生几何一致匹配。
◆ 在TUM RGB-D SLAM和户外视频上验证其与传统局部描述子互补，且计算轻量、易于实现。</td></tr>
<tr><td>2026-10-15</td><td>LIN-SLAM: Lightweight LiDAR--Inertial Neural SLAM for Real-Time Onboard Navigation<br><a href='http://arxiv.org/pdf/2610.21199'>论文</a></td><td>本文提出LIN-SLAM，一种将高频几何LiDAR-惯性估计与神经隐式跟踪、持续建图和全局优化耦合的轻量混合SLAM方法。
◆ 提出几何LiDAR-惯性前端与神经隐式后端紧耦合的混合架构，在保持高效状态估计的同时获得连续地图表示和全局精化能力。
◆ 实现轻量化神经隐式跟踪与持续建图后端，显著降低现有神经隐式SLAM的计算开销，支持实时在线运行。
◆ 在三个数据集、十二个序列、32/64/128线LiDAR配置上取得最低整体ATE，定位精度优于现有几何和神经隐式SOTA方法。
◆ 在Unitree Go2、Jetson Orin NX和16线LiDAR平台上完成1.47公里室内重复走廊实时定位与神经建图，端点闭合误差仅0.141米。
◆ 据所知，这是首个在移动机器人平台上实时在线运行并保持SOTA定位精度的神经隐式后端LiDAR-惯性SLAM系统。</td></tr>
<tr><td>2026-10-14</td><td>Line-Augmented cuVSLAM: Robust Visual Odometry in Low-Texture Environments<br><a href='http://arxiv.org/pdf/2610.20958'>论文</a></td><td>本文面向仓库等低纹理环境中点特征视觉里程计易失效的问题，在CUDA加速的cuVSLAM中引入线特征，利用货架立柱、门框、墙角等高对比直线边缘提升鲁棒性。
◆ 采用Plücker坐标进行线特征的几何传递，并使用Bartoli-Sturm最小4自由度正交表示进行优化。
◆ 将Cauchy鲁棒点线残差及解析雅可比直接嵌入cuVSLAM的逐帧高斯牛顿位姿求解，并在Schur补滑动窗口光束法平差中联合优化线状态。
◆ 引入自适应信息权重，使线特征在点特征稀缺时承担更多估计任务；扩展只增加残差块，禁用时可完全退化为原始点管线。
在TUM RGB-D Freiburg3的22个序列和Replica的8个序列上，RGB-D模式、SE(3) Umeyama对齐且无尺度校正下，平均ATE分别降低38.5%和30.1%，中位平移误差降低38.9%、中位旋转误差降低66.4%，且零跟踪失败。</td></tr>
</tbody>
</table>
</div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-20</td><td>CrossFit-GS: Out-of-Fold Pose Estimation for COLMAP-Free 3D Gaussian Splatting<br><a href='http://arxiv.org/pdf/2610.28190'>论文</a></td><td>CrossFit-GS提出一种延迟提交的渐进式无位姿3DGS框架，可在无COLMAP/SfM条件下从无位姿图像序列直接重建场景。
◆将输入序列划分为交错子集并维护两个互补子图，使候选位姿在从未用目标帧优化过的冻结对侧子图上交叉细化，从而获得独立几何参考。
◆引入棋盘验证和空间覆盖保障机制，拒绝不可靠位姿更新，仅将验证通过的位姿提交到所属子图，以打断畸变地图误差自增强循环。
◆在轨迹精炼后丢弃中间子图，并利用固定的精炼位姿从头训练最终全局表示，避免中间误差残留。
实验表明该方法在多个基准上显著降低累计轨迹漂移，并稳定提升相机位姿估计与新视角合成性能。</td></tr>
<tr><td>2026-10-19</td><td>RoboCloth: A Large-Scale Real Cloth Material Dataset for Neural Reflectance Reconstruction<br><a href='http://arxiv.org/pdf/2610.21090'>论文</a></td><td>RoboCloth提出了一个大规模真实布料材质数据集，包含500种布料在机器人控制相机与光照下采集的约580张HDR帧，覆盖广视角-光照半球。数据经SfM细化相机位姿并对齐机器人坐标系，提供每材质稀疏几何和结构化逐点反射观测，可直接用于神经材质训练。论文设计两阶段神经重建流程，先训练共享MLP解码器学习布料材质先验，再冻结解码器并为目标材质拟合2048x2048密集潜纹理。在自留出材料和UBO2014基准上，该方法优于现有测量反射数据集训练的解码器及解析PBR拟合，并能迁移到未见采集系统。数据集、标定文件、观测张量和训练测试划分以CC BY 4.0在Hugging Face Hub发布。
◆构建了机器人控制采集的大规模真实布料反射数据集，覆盖丰富视角-光照条件并提供标定与结构化观测。
◆提出两阶段神经材质重建方法，利用数据先验实现密集潜纹理拟合和跨采集系统迁移。</td></tr>
<tr><td>2026-10-18</td><td>Localization and Neural Splatting on the Edge: An FPGA Scene Memory for Robots<br><a href='http://arxiv.org/pdf/2610.25068'>论文</a></td><td>LENS是部署在AMD KR260上的低功耗FPGA/ARM边缘场景记忆加速系统，将ACEsplat风格相机定位与近邻视图渲染带到无桌面GPU的机器人平台，核心不是提出新场景模型，而是让两个主导内核与板级数据路径协同设计。
◆ 设计INT16 SCR加速器，在25.42 ms内保持DSAC*定位精度，解决SCR姿态敏感带来的边缘部署难题。
◆ 设计位精确定点有序3DGS渲染器，将alpha透射率改写为log-sum-exp递推，并剔除可证明无用的流式高斯。
◆ 全部延迟、功耗和质量结果均板级实测，实现相对Jetson Orin NX每瓦性能1.9至5.7倍提升，功耗约四分之一。
渲染质量上，Cambridge达34.11 dB高于ACEsplat的33.20 dB，RealEstate10K达27.84 dB高于26.11 dB，十个Wayspots场景均达目标。
其端上训练可达ACEsplat级质量，但时间和能耗仍不及GPU，指明未来训练加速器的边界。</td></tr>
<tr><td>2026-10-16</td><td>Ionic switching between supermagnetic states<br><a href='http://arxiv.org/pdf/2610.23829'>论文</a></td><td>论文首次展示利用室温锂离子传输，在不重新合成、不持续外部刺激下实现超铁磁态与超自旋玻璃态的可逆磁离子切换并可保持。  
◆ 提出通过NiO不完全锂化生成纳米Ni和Li2O，实现两种超磁态相互转化的新机制。  
◆ 揭示锂化形成碎片化纳米Ni网络增强偶极相互作用，稳定超铁磁态并提升室温磁矩与记忆。  
◆ 发现脱锂部分再生NiO驱动超自旋玻璃态，获得更高低温矫顽力和更尖锐温度选择性记忆，且多轮循环可逆。  
该工作建立了超磁态可逆切换的通用框架，为磁离子器件设计提供新思路。</td></tr>
<tr><td>2026-10-14</td><td>Why 3D Reconstruction Breaks Down on Under-Ice AUV Video, and How to Predict It<br><a href='http://arxiv.org/pdf/2610.19993'>论文</a></td><td>本文系统检验冰下AUV视频三维重建不准是方法缺陷还是采集系统固有限制，并在同一段南极Icefin/Kamb冰流视频上测试经典特征匹配SfM、可微分光度splatting、体深度融合和无位姿前馈基础模型四类方法。四类方法均失败，分别呈现近乎无配准、光度指标健康但几何破碎、持续覆盖伪影和跨块尺度不稳定，且都可归因于相机基线相对场景深度过小的同一采集机制。作者据此提出快速检测系统，能在几分钟内标记此类失败，避免数小时无效计算。
◆ 首次统一评测四类代表性重建范式，揭示冰下AUV视频的共性失败与不同失效模式。
◆ 将失败根源归因于小相机基线-场景深度比这一采集条件，而非单一算法缺陷。
◆ 提出分钟级失败预警检测系统，显著减少无效算力消耗。</td></tr>
<tr><td>2026-10-13</td><td>Benchmarking 3D Reconstruction for Under-Ice Robotic Perception in Arctic Environments<br><a href='http://arxiv.org/pdf/2610.19097'>论文</a></td><td>本文针对北极冰下机器人感知，提出一个基于视觉的冰下三维重建基准，以弥补多波束声纳缺乏光谱和高分辨率纹理信息、难以刻画冰底精细形态的不足。它利用MOSAiC航次的真实数据和Unreal Engine水下机器人模拟器的合成数据，连接声纳大尺度几何与视觉纹理及光学信息。  
◆ 构建真实与合成结合的冰下视觉三维重建数据与评测基准，覆盖北极冰下复杂环境。  
◆ 在稀疏视觉特征和退化传感条件下，系统评估Structure-from-Motion与单目深度估计两类方法。  
◆ 提出通过跨模态配准到向上多波束声纳的定量评价框架，实现视觉重建与声学几何参考的客观比较。</td></tr>
<tr><td>2026-10-10</td><td>RootSLAM: Square Root Bundle Adjustment for Visual-Inertial SLAM<br><a href='http://arxiv.org/pdf/2610.15157'>论文</a></td><td>RootSLAM是一个基于Basalt构建的多相机视觉惯性SLAM系统，在保持与当前最优方法相当精度的同时，最高可实现20倍加速。它面向资源受限环境，解决了高精度SLAM计算需求大的部署瓶颈。
◆ 将Structure from Motion中的平方根光束法平差引入多相机视觉惯性SLAM，拓展了其适用场景。
◆ 借助系统位姿图对平方根BA进行新重构，使全局优化器能以单精度浮点运行，性能提升一倍。
◆ 提供详尽基准与消融实验，并开源地图管理、回环检测、位姿图优化和全局建图等完整实现。</td></tr>
<tr><td>2026-10-08</td><td>When pose graphs are not enough: a failure analysis of pose-graph-based camera estimation for Gaussian splatting<br><a href='http://arxiv.org/pdf/2610.14090'>论文</a></td><td>本文面向房产高斯泼溅孪生中无人机固定航拍采集，构建专用PGO相机估计系统，检验仅优化位姿能否达到BA精度。  
◆ 首次系统性地开展基于位姿图的相机估计用于Gaussian splatting的失败分析，而非提出通用SfM工具。  
◆ 构建面向密集重叠、GPS与时间标签的专用PGO系统，并在速度上超越COLMAP。  
◆ 发现仅位姿优化虽快，却始终无法在估计质量上超过BA或COLMAP。  
◆ 揭示失败源于手工权重、贪婪合并、噪声GPS，以及SE(3)无尺度自由度和两视图边缺少多视图点耦合两个固有缺陷。  
◆ 指出可行设计必须引入Sim(3)约束、绝对GPS先验、保留结构和不确定性感知加权。</td></tr>
<tr><td>2026-10-08</td><td>Inflow-driven galaxy evolution - II: A hierarchy in the scaling relations of star-forming galaxies<br><a href='http://arxiv.org/pdf/2610.12394'>论文</a></td><td>本文用理想与宇宙学气体流模型统一建模重子循环，解释恒星形成星系三个核心标度关系及其高维关联如何从同一框架涌现。
◆ 提出三个标度关系的层级结构：SFMS、气体与恒星质量比、质量金属度关系依次叠加，每一步引入新的散射来源。
◆ 发现SFMS及其散射主要由宿主晕形成时间决定，仅弱依赖恒星形成效率和质量加载因子。
◆ 证明气体与恒星质量比源于sSFR与恒星形成效率之比并继承其散射，MZR进一步由该比值与质量加载因子决定，相对贡献随星系处于入流驱动或平衡态而变。
◆ 该层级自然导出恒星形成基本面、基本金属度关系及其气体对应，以及各关系与星系尺度的相关性，尺度通过恒星形成定律追踪恒星形成效率。
◆ 提供单一框架将恒星形成星系的观测量与底层重子循环联系起来。</td></tr>
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
</tbody>
</table>
</div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-18</td><td>LateMatch: Breaking the Interaction Bottleneck via Cacheable Matching for Efficient Visual Localization<br><a href='http://arxiv.org/pdf/2610.25358'>论文</a></td><td>论文针对现有深度特征匹配器在每层紧耦合图像内上下文与跨图匹配、对K张库图需重复执行完整网络且无法缓存的问题，指出严重交互瓶颈。  
◆提出可缓存图像匹配新范式，将跨图交互推迟到网络末层，使图像内处理可离线缓存、在线仅执行少量交互计算。  
◆提出LateMatch，通过Context Blocks与Interaction Blocks解耦重构现有匹配器，实现通用且高效的视觉定位部署。  
◆提出E-SToRE，利用晚期交互块香农熵下降，在跨图交互前动态进行空间token缩减与扩展。  
在HPatches、ScanNet、MegaDepth、ETH-3D和Aachen上验证，LateMatch相较标准深度匹配器降低有效计算成本2倍以上。  
E-SToRE进一步带来10%至14%额外节省且精度几乎不退化。</td></tr>
<tr><td>2026-10-16</td><td>DinoMUSE: A DINOv2-guided Framework for Unsupervised Lateral Motion Estimation in Ultrasound Elastography<br><a href='http://arxiv.org/pdf/2610.24020'>论文</a></td><td>论文提出DinoMUSE，一种DINOv2引导的混合专家无监督框架，用于超声弹性成像中的横向运动估计。针对横向分辨率低、采样频率低且缺乏相位信息，现有局部匹配与物理约束方法上下文不足的问题，该方法引入DINOv2高层视觉表征为运动估计提供全局上下文引导。
◆ 将DINOv2学习到的可迁移高层视觉表示融入运动估计网络，以全局上下文弥补局部匹配信息不足。
◆ 设计基于混合专家的特征融合模块，自适应变换并整合DINOv2特征与局部匹配特征，促进两类表示有效交互。
◆ 构建无监督横向位移与应变估计框架，在仿真和活体乳腺数据上验证其横向精度显著优于NCC、GLUE、RAFT和sPICTURE等方法。
实验表明，DinoMUSE在仿真数据上将横向位移和应变估计的MSE分别降低60%和65%，并在活体乳腺数据中提升应变SNR、CNR及病灶可视化效果，同时保持有竞争力的轴向性能。</td></tr>
<tr><td>2026-10-15</td><td>CLAD: Keypoint Matching Using Global Line Correspondences<br><a href='http://arxiv.org/pdf/2610.21409'>论文</a></td><td>论文提出CLAD，用全局线对应为关键点匹配提供几何上下文，以克服SIFT、ORB等局部描述子在重复纹理或弱纹理下不稳定的问题。
◆ 将关键点表示成到匹配线邻近度的向量，编码其与场景线性结构的空间关系。
◆ 使用HOME检测清晰和弱线性结构，建立足够线-关键点关联以形成全局上下文。
◆ 把全局几何一致性引入匹配，补充传统局部描述子，提高重复场景的匹配可靠性。
◆ 方法计算轻量、易于实现，并在TUM RGB-D SLAM和户外视频上验证有效性。</td></tr>
<tr><td>2026-10-12</td><td>The Value of Being Wrong: Self-Mined Visual In-Context Learning from Errors<br><a href='http://arxiv.org/pdf/2610.16977'>论文</a> | <a href='https://tree-shu-zhao.github.io/SMILE/'>代码</a></td><td>本文提出 SMILE，一种利用模型自身错误进行自挖掘视觉上下文学习的方法，以更简单方式提升视觉语言模型的 ICL 效果。  
◆利用目标 VLM 自身预测错误作为天然反事实示例，直接编码其失败模式，避免属性提取、描述工程和组合图像匹配等多阶段管线。  
◆离线构建模型特定的困难负例池，记录该模型过去的错误，使示例选择与具体模型能力绑定。  
◆测试时将当前预测作为方向信号，在语义嵌入空间中检索最可能复发的历史错误，形成预测条件化的示例识别机制。  
◆该机制统一支持闭集分类和开放式视觉问答，无需任务特定设计。  
在四个基准和四个 VLM 上，SMILE 相比 SOTA 基线平均任务得分提升 3.09 分，同时延迟降低 5 倍。</td></tr>
<tr><td>2026-10-09</td><td>Efficient Confidence-Aware Densification for 3DGS<br><a href='http://arxiv.org/pdf/2610.13541'>论文</a></td><td>本文针对3DGS-MCMC按透明度采样致新图元偏向前景、背景欠重建的问题，提出面向固定预算MCMC的置信度感知误差驱动致密化。它在保持固定预算与渐进增长的前提下，用图像误差而非透明度决定图元放置。
◆ 以屏幕空间梯度大且学习置信度低的区域作为新图元采样位置，优先重建当前解释较差的区域。
◆ 将对渲染贡献最小的图元重定位到高误差区域，实现误差驱动而非透明度驱动的密度控制。
◆ 无需先验或单独初始化，在100k至2M各预算下平均PSNR、SSIM、LPIPS均超3DGS-MCMC；100k恢复ConeGS领先PSNR的0.84dB，500k起PSNR/SSIM在固定预算方法中领先。
◆ 可兼容先验：从ConeGS或EDGS初始化后，100k匹配ConeGS，500k三项指标最佳。</td></tr>
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
</tbody>
</table>
</div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-20</td><td>Can a Display Be Used for Rapid LiDAR-Camera Extrinsic Calibration?<br><a href='http://arxiv.org/pdf/2610.28571'>论文</a> | <a href='https://github.com/ZuhaoZou2026/ScreenCalib'>代码</a></td><td>ScreenCalib提出用普通可编程显示屏完成LiDAR-相机外参标定，相机观测屏幕显示的AprilTag，LiDAR测量屏幕物理表面与边界，从而减少专用标定板准备并实现间接跨模态关联。针对显示几何关联歧义和室内杂乱干扰，方法采用标签引导的显示屏提取、几何假设生成与优化，并利用周围场景边缘消歧。实验覆盖仿真及三种传感器平台、机械与非重复LiDAR、干净与杂乱环境，平移精度优于竞争标定板方法，联合多姿态优化进一步降低旋转和平移误差并改善渲染地图对齐。创新点：
◆以普通显示屏作为可编程标定物，兼顾已知视觉标记与可控几何，减少专用靶标准备。
◆通过标签引导提取、几何假设生成优化及场景边缘消歧，稳健解决LiDAR与相机间的间接跨模态关联歧义。
◆提出单姿态静态标定与多姿态共识联合优化，后者无需连续运动或轨迹估计，并降低标签尺寸测量误差敏感性。</td></tr>
<tr><td>2026-10-20</td><td>SynCalib: Breaking Dataset Shortcuts in LiDAR-Camera Calibration via Extrinsic-Controllable Synthesis<br><a href='http://arxiv.org/pdf/2610.27547'>论文</a></td><td>论文针对现有学习式LiDAR-Camera标定方法因训练数据外参多样性不足而过度拟合固定标称外参、产生数据集捷径并导致泛化差的问题，提出SynCalib数据生成框架。该框架利用带深度真值的全向图像数据集，在严格外参约束下合成多模态标定数据，以增强训练数据的外参多样性。
◆提出外参可控的多模态标定数据合成框架，从数据源头打破固定标称外参导致的数据集捷径。
◆在严格外参约束下生成LiDAR-Camera标定样本，提升外参多样性，使网络不再依赖单一标定配置。
◆验证仅用合成数据训练的模型可在多种真实相机-LiDAR配置上零样本迁移，显著提升泛化性与鲁棒性。
实验表明该数据能增强典型学习式标定网络的泛化与鲁棒性，作者还将公开数据生成代码、预训练模型和在线基准数据集。</td></tr>
<tr><td>2026-10-20</td><td>SpatialScout: Can VLM Agents Actively Explore and Map 3D Scenes?<br><a href='http://arxiv.org/pdf/2610.26659'>论文</a> | <a href='https://github.com/JesseZZZZZ/SpatialScout'>代码</a></td><td>本文提出SpatialScout，一个评估VLM智能体主动进行物体级3D建图的基准。该基准包含80个室内场景和3140个目标物体，要求智能体在有限交互预算下控制相机探索并估计共享坐标系中的物体中心。评估采用惩罚漏检的物体尺度重叠分数，同时衡量定位精度与目标覆盖率；实验显示最强模型Claude Opus 5.5平均重叠分数仅41.71%，IoU超0.5和0.9的目标分别占47.23%和3.25%。
◆ 构建覆盖多场景多目标、带交互预算约束的主动物体级3D建图量化测试平台。
◆ 设计联合定位精度与目标覆盖率的物体尺度重叠评估，惩罚漏检并区分粗布局与精确度量地图。
◆ 揭示前沿VLM在视角选择、跨视图关联、几何估计和地图修正上的显著能力缺口。</td></tr>
<tr><td>2026-10-20</td><td>Visual-Inertial Odometry for Ground Robots with Dynamic Camera-IMU Extrinsic Calibration<br><a href='http://arxiv.org/pdf/2610.25397'>论文</a></td><td>本文针对视觉惯性里程计中传感器刚性安装假设限制适应性、难以应对结构运动的问题，研究时变相机-IMU外参标定，以提升地面机器人在动态结构运动场景下的定位适应性。
◆ 提出基于Denavit-Hartenberg约定并融合机器人运动模型的动态相机-IMU外参标定方法，将外参随关节运动变化纳入建模。
◆ 设计两步初始化策略高效估计初始关节角，为后续外参优化提供可靠起点，并支持时变相机-IMU外参的在线估计。
仿真实验表明，该框架能有效适应相机-IMU外参变化，同时保持具有竞争力的定位精度。
该工作的核心创新在于将机器人运动学引入动态外参标定，并通过初始化与在线优化结合实现时变外参的实用估计。</td></tr>
<tr><td>2026-10-20</td><td>HexaShell: A Thin Harness for Exploring the Limits of VLM Agents as Robot Coding Agents<br><a href='http://arxiv.org/pdf/2610.23479'>论文</a> | <a href='https://github.com/HexaFuture/HexaShell'>代码</a></td><td>HexaShell提出一种面向机器人操作的“薄封装”编码智能体框架，让VLM智能体通过单一命令行把代码命令转为机器人动作，框架自身不做决策。
◆ 它采用行动智能体与优化智能体协作：行动智能体执行每个回合，失败后优化智能体读取含命令、图像和消息的完整记录，定位原因并编写或修复带测试的小工具。
◆ 学到的经验以代码形式沉淀，无需演示或训练，运行工具只依赖真实机器人也可获得的RGB图像、相机标定和机械臂状态。
◆ 工具通过多视角三角定位找物体，仿真与硬件的输入一致，因此迁移到不同机械臂只需少量适配。
◆ 在RoboDojo官方隐藏种子评测的42个任务各50回合中，HexaShell取得46.9%成功率和53.2进度分，达到官方榜单SOTA。
实验表明其上限受接触操作限制而非推理：记忆任务达81.0%，精度任务仅32.0%，并开源已演化工具。</td></tr>
<tr><td>2026-10-14</td><td>FOMI: A Force-Feedback Manipulation Interface for Teaching Contact-Rich Manipulation<br><a href='http://arxiv.org/pdf/2610.19839'>论文</a></td><td>本文提出FOMI，一种面向接触丰富操作教学的力反馈操作接口，旨在解决现有手持界面力反馈不足、演示采集困难的问题。其核心贡献是设计剪刀形机构，通过执行连杆将物体交互力直接传递到操作者双手，无需力传感器即可实现直觉力反馈，支持采集中的实时动作调整。
◆ 采用无传感器力反馈机械结构，将交互力直接传给人手，增强接触丰富演示采集的直觉性与可调性。
◆ 构建集成传感器标定、数据采集与同步的无机器人采集系统，并支持位姿与夹爪映射下的遥操作。
在四个接触丰富任务上，FOMI在无机器人采集和遥操作中分别比最佳基线提升约29%和18%的采集效率。基于FOMI采集的演示可训练策略，在挑战性接触丰富操作任务中取得高成功率。</td></tr>
<tr><td>2026-10-10</td><td>HumanPhys: A Human-Centric Physical-World Perception Benchmark for Real-World Visual Reasoning<br><a href='http://arxiv.org/pdf/2610.14679'>论文</a></td><td>本文提出HumanPhys，一个以人为中心的真实世界物理感知基准及同管线生成的训练语料。它系统探测空间状态、运动学、眨眼事件、形变、光照和相机姿态六个维度，问题涵盖深度、人际距离、注视角、位移、速度、朝向步态轨迹、眨眼次数、接触形变强度及光照与相机自运动。所有标签均由传感器标定、源元数据或渲染器状态程序化生成，而非人工标注或基于基准帧的估计器。
◆ 首次构建联合监督上述六类人类中心物理量的MLLM基准与训练语料，填补现有基准仅部分覆盖的空白。
◆ 通过直接元数据或渲染器状态获得物理接地标签，避免标注偏差并支持可扩展生成。
◆ 全面评测开源与闭源MLLM，发现六个能力维度仍具挑战且仅部分可分离，为多模态物理感知研究提供新基准。</td></tr>
<tr><td>2026-10-08</td><td>RAGNAROK: Radar-Aided Gravity-Normalized Alignment for Robust Open Keyframe-based Radar-Visual-Kinematic-Inertial SLAM<br><a href='http://arxiv.org/pdf/2610.11531'>论文</a> | <a href='https://github.com/hanjun815/RAGNAROK'>代码</a></td><td>本文提出RAGNAROK，这是首个面向腿式机器人、可在开放关键帧下运行的雷达-视觉-运动学-惯性SLAM系统，旨在提升非结构化环境中的鲁棒状态估计。
◆ 提出滑动与滚动接触感知的腿部速度估计，使腿式运动学在打滑和接触变化时仍能提供可靠速度约束。
◆ 设计运动学感知雷达因子与雷达辅助重力归一化对齐，增强偏航可观性并抑制长期漂移。
◆ 引入退化感知图像增强、B样条雷达辅助本体感知骨干、自适应权重和在线外参标定，实现故障与退化感知融合。
在公开和自采数据集上，RAGNAROK在恶劣条件下表现鲁棒并优于现有最优基线。</td></tr>
<tr><td>2026-10-08</td><td>Low-Cost Sensor Calibration for Indoor Air Quality Monitoring: A Dataset, Evaluation Scenarios, and a Lightweight Model<br><a href='http://arxiv.org/pdf/2610.11236'>论文</a></td><td>本文聚焦低成本室内空气质量监测中因非线性失真、噪声和时间漂移而必需的校准问题。传统严格成对校准要求每个部署位置共置参考传感器，且未考虑时空异质性。为此，作者发布了一个为期六个月、覆盖五个地点的多变量室内空气质量数据集，同时包含低成本与参考传感器测量及上下文元数据。
◆ 基于该数据集定义了参考高效、位置迁移、长期漂移和事件条件四种评估场景，系统考察空间泛化以及对渐变和突变分布偏移的鲁棒性。
◆ 由此推导设计需求，并提出一种结合输入窗口压缩、残差时序融合与特征融合的轻量时序模型。
实验显示该模型在四类场景中均实现强校准性能，并保持较低的边缘推理成本。</td></tr>
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
</tbody>
</table>
</div>

<h2 id='robot-vlm'>Robot VLM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-20</td><td>UniWALM: Unified World Action Language Model for Embodied Robot Control<br><a href='http://arxiv.org/pdf/2610.28626'>论文</a></td><td>UniWALM提出统一的世界-动作-语言模型，在单一共享表示中联合学习视频、动作和语言，且每个模态既是条件信号也是监督目标。与将推理或视觉语言模型外挂到视频-动作骨干并分阶段运行不同，它用单一Mixture-of-Transformers骨干让各模态扩散头同步协同去噪，在一次生成中解码动作、子任务和文本记忆，无需独立规划阶段。
◆ 统一三模态于单一共享表示和单骨干，消除分阶段规划，并让生成语言在下一步回灌，形成语言即记忆闭环。
◆ 各模态扩散头同步协同去噪，一次生成动作、子任务和文本记忆，支持记忆依赖行为且无需外部规划器或记忆库。
◆ 提出Flow Matching with Correction训练目标，使模型从扰动动作轨迹中学习恢复，且不增加推理成本。
实验显示，UniWALM在MolmoSpaces组合抓放和RMBench记忆子集上稳定优于同骨干基线，记忆子集达34.5%且无需预训练语言或推理模型，单锚帧超过Mem-0的28.5%；真实Find-the-Item任务中文本记忆将成功率从11.1%提升至61.1%，而SOTA VLA不超过33.3%。</td></tr>
<tr><td>2026-10-20</td><td>VLM-Guided Contact Retargeting and Generative Partner Modeling for Humanoid-Human Interaction<br><a href='http://arxiv.org/pdf/2610.28523'>论文</a></td><td>REACT提出从人人示范学习可部署人形-人交互策略的框架，核心是以语义接触结构贯通示范处理、交互学习与机载控制。  
◆提出VLM引导的接触建模与重定向流程，识别语义有意义的接触并迁移到人形-人几何上，同时保持交互结构。  
◆利用接触标注和交互感知接触奖励学习特权交互策略，并蒸馏为仅依赖机载传感、基于逼真人深度渲染训练的自视角深度策略。  
◆引入生成式伙伴状态建模目标，从遮挡的自视角预测伙伴运动，以缓解严重部分可观测性。  
仿真与Unitree G1真机在五类富接触交互上验证，语义接触建模显著提升示范交互保持，生成式建模在四类交互中提升接触召回。  
真机上REACT仅用机载传感完成全部五类交互。</td></tr>
<tr><td>2026-10-20</td><td>CLOSER: Evidence-Aware Active Visual Verification for Embodied Object-Goal Navigation<br><a href='http://arxiv.org/pdf/2610.28476'>论文</a></td><td>CLOSER针对ObjectNav中检测器易将相似物体误判为目标、贪心接近导致候选被遮挡或仅部分观测的问题，提出证据感知的主动视觉验证框架，将停止决策建模为闭环证据获取。  
◆ 微调开源VLM，对跨帧跟踪候选的每个视角判定为目标、非目标或不确定。  
◆ 用基于嵌入的多样性门选择互补视角，并以轻量网络融合各视角概率。  
◆ 当融合判断仍不确定时，用扩散策略仅依据跟踪掩码和深度主动接近候选，直至决策明确。  
该框架可本地运行，并能即插即用于现有ObjectNav系统而无需重新训练。  
在Gibson和Habitat-Matterport 3D上，平均成功率提升3.6点、SPL提升2.0点，表明先验证证据再提交决策可改善具身导航。</td></tr>
<tr><td>2026-10-20</td><td>EventSync: Event-Driven Memory Updates for History-Dependent Manipulation<br><a href='http://arxiv.org/pdf/2610.27917'>论文</a></td><td>本文提出EventSync，一种面向历史依赖操作的分层框架，通过事件驱动记忆更新协调高层任务推理与低层动作执行。
◆ 使用视觉语言模型基于任务计划和交互历史生成子目标，并由视觉语言动作模型执行，形成任务推理与动作执行的闭环。
◆ 设计轻量Event Monitor，融合视觉观察与末端执行器轨迹判断当前子目标是否完成，仅在获得完成证据后写入已完成子目标历史并触发后续推理，避免过早记录完成而误导推理。
◆ 在执行器中引入视觉历史，使子目标执行能够利用交互过程信息，提升历史依赖任务中的执行可靠性。
在RoboMME上取得64.5%总体成功率，较基准最佳基线高20.0个百分点，并在四个具有不同记忆需求的真实机器人任务上验证有效性。</td></tr>
<tr><td>2026-10-20</td><td>Multi-View Latent Action Pretraining for Cross-Embodiment Robot Learning from Videos<br><a href='http://arxiv.org/pdf/2610.27794'>论文</a> | <a href='https://learnsyslab.github.io/multiview_latent_action_pretraining/'>代码</a></td><td>本文提出面向跨具身机器人学习的多视角潜在动作预训练框架，用无动作视频替代昂贵遥操作数据。
◆ 设计同步多摄像头输入的潜动作模型，通过交叉注意力解析深度与遮挡，再压缩为潜在动作，缓解单视角对6D动作的歧义。
◆ 构建冻结VLM骨干上由潜在专家与动作专家经序列流匹配耦合的策略，将多视角潜动作用于下游控制。
◆ 在严格跨具身设置中验证：双视角预训练使真实6D动作可解码性较单视角提升17%，下游成功率提升13.5%（单视角为6.2%），且单一跨具身即可迁移技能，第二视角优于最多四个额外具身。
◆ 硬件实验表明人类手部演示可迁移，成功率较仅动作策略提升20%（850次 rollout），并揭示视频与机器人数据互补、视频收益依赖任务。</td></tr>
<tr><td>2026-10-20</td><td>Give the Model a Finger: Developmentally Aligned Evaluation of Counting in Vision-Language Models<br><a href='http://arxiv.org/pdf/2610.27756'>论文</a></td><td>本文的核心贡献是把VLM计数评估从“干预提升准确率”转向“测量串行视觉推理”：在不训练的情况下，给模型配上无视觉智能的指认与标记工具，使其计数过程在图像上留下可审计痕迹。
◆提出发展对齐的可解释审计框架：按点级真值将每个标记判为命中、重复、幻影或遗漏，并用标记数核对答案、用相反遍历顺序检验顺序无关性。
◆设计无训练agent循环与标签扰动探针，把“指哪数哪”的串行程序外显化，从而判断模型是否真的从标记读取答案，而非仅依赖语言routine。
◆发现精确计数范围是模型特异的连续谱，跨越近两个数量级（R80从3到150个点），且指认精度能预测哪些模型从标记中受益。
◆证明标记作为干预大多不提升准确率，真正价值是可审计轨迹；密集场景主要因遗漏失败，模型看到自身标记后很少修正。
◆揭示能力解离：模型能遵循指定遍历顺序却常因反转而改答案，儿童计数中规则优于分散的优势仅在routine下出现并能经受格阵检验。</td></tr>
<tr><td>2026-10-20</td><td>Evaluating Social Reasoning in Embodied Vision-Language Models<br><a href='http://arxiv.org/pdf/2610.27496'>论文</a></td><td>本文评估具身专用视觉语言模型Gemini Robotics-ER在真实人机社交交互基准SHREC上的社会推理能力，并与通用VLM基线进行比较。
◆ 将社会判断区分为可直接从可观察交互线索读取的任务与需要推断人物内部状态的任务，揭示具身专用模型可能在这两类任务上表现分化。
◆ 发现Robotics-ER在错误/胜任力检测上优于GPT-4o-mini，但在细粒度社会属性判断上更差，且加入视觉帧对两项任务一利一害。
◆ 指出跨模型家族比较的限制，不能把差异单独归因于具身专门化，并强调共享基础模型在多机器人系统中可能放大系统性社会感知错误。
该工作提供初步评估证据，为后续跨情境和基于视频的社会推理分析奠定基础。</td></tr>
<tr><td>2026-10-20</td><td>CondenseVLA: Learnable History Condensation for Efficient Multi-Frame VLA<br><a href='http://arxiv.org/pdf/2610.25927'>论文</a> | <a href='https://github.com/FeiyangHong/CondenseVLA'>代码</a></td><td>论文提出CondenseVLA，一种面向多帧视觉语言动作策略的可学习历史压缩框架，旨在以较低成本利用短期视觉线索提升动作解码。  
◆设计解码器侧历史压缩模块，将VLM主干缓存的逐帧特征通过可学习查询和多头交叉注意力蒸馏为固定数量slot token。  
◆引入简单辅助正则化，惩罚slot注意力图重叠并去相关slot嵌入，促使各slot互补关注、减少历史冗余。  
◆采用任务自适应的选择性压缩而非单纯扩大历史窗口，在保持效率的同时保留对短暂接触、遮挡和中间状态有用的近期证据。  
实验显示，Simpler-WidowX成功率从58.7%升至69.8%，LIBERO达97.2%，真实任务达52.8%，RMBench记忆任务达21.6%。  
结果支持有界近期视觉证据的选择性压缩用于动作解码，同时困难多观测任务也暴露了有限历史窗口的局限。</td></tr>
<tr><td>2026-10-19</td><td>What Would Removing This Corruption Change? Failure Attribution for Vision-Language-Action Models<br><a href='http://arxiv.org/pdf/2610.27277'>论文</a></td><td>论文将VLA模型中的失败归因定义为failure attribution：不仅判断视觉损坏是否存在，而是估计移除当前episode中某项损坏对失败风险的实际收益。针对直接测量移除收益需要昂贵配对rollout的问题，作者提出因子化风险模型，分离学习场景与损坏表示，并通过潜在干预从当前图像和任务指令估计移除收益，无需配对干净图像或额外反事实rollout。
◆ 提出failure attribution问题，强调损坏存在不等于有害，需判断其对当前失败风险的贡献及移除收益。
◆ 设计因子化风险模型与潜在干预机制，在无需配对干净图像和额外rollout条件下估计反事实移除收益。
◆ 在OpenVLA、π0.5仿真及π0.5-DROID真实Franka上验证，归因误差约为前沿VLM的三分之一，并能适应执行上下文、损坏强度和在线失败监控。</td></tr>
<tr><td>2026-10-19</td><td>LVMem: Image-Augmented Memory for Long-Horizon Question Answering<br><a href='http://arxiv.org/pdf/2610.27104'>论文</a></td><td>本文提出LVMem，一个面向长时程时空问答的高效视图记忆框架，在ReMEmbR式记忆基础上增强语言引导感知与持久场景记忆。
◆ 为每条存储描述附加原始图像路径，将文本注释与视觉内容显式关联，支持按需回看原图。
◆ 用基于光流的帧选择策略PSFR替代记忆构建中的均匀采样，保留更具信息量的关键帧。
◆ 以对象中心的描述性场景表示替代普通字幕，使存储注释更丰富、更利于后续推理。
◆ 为VLM智能体配备自适应检索工具，返回与最相关字幕对应的图像，由其自主决定何时进行视觉检查。
在OC-NaVQA上，LVMem在两种骨干下均优于ReMEmbR的二值和位置指标，二值准确率匹配或超过4D场景图DAAAM基线，且仅依赖轻量视图记忆、无需显式图构建。</td></tr>
<tr><td>2026-10-19</td><td>Replan for Error Recovery: Training Embodied VLMs through Verifiable Interaction with Action-Grouped Turn-GSPO<br><a href='http://arxiv.org/pdf/2610.27003'>论文</a></td><td>论文针对具身VLM执行出错后需重规划恢复的问题，提出通过可验证交互学习恢复能力的研究框架。  
◆构建ERR-Env，为任务进展和执行错误提供可验证反馈，支撑恢复学习。  
◆构建ERR-Bench，覆盖正常、中间和错误状态，用于评估恢复能力与执行可靠性。  
◆提出AGT-GSPO在线强化学习方法，结合轮级任务进展与错误状态奖励及动作分组优势估计，并训练2B的ERR-VLM。  
实验发现多种VLM存在任务进展与执行可靠性不匹配，AGT-GSPO使ERR-VLM严格成功率提升10.25个百分点、恢复率提升22.95个百分点。  
消融和零样本迁移进一步验证了方法的有效性。</td></tr>
<tr><td>2026-10-19</td><td>Where is Physical RSI capability from? An Observational Scaling Law of LLM-as-policy<br><a href='http://arxiv.org/pdf/2610.26848'>论文</a></td><td>本文系统研究LLM作为策略的物理递归自我改进机制、缩放行为与泛化性，并提出PhysRSI-eval以五轴指标量化物理RSI。
◆构建PhysRSI-eval，从首次尝试表现、效率、成功率、预算和失败改进五轴，评估不同VLM在18个操作任务固定交互预算下的表现。
◆提出Physical Barrel Hypothesis，指出不同能力可能约束改进的不同环节，且五轴指标能区分公开基准均值接近的系统，并揭示高分未必伴随早期或高效增益。
◆从公开能力预测智能体相对表现、从早期物理反馈预测后续进展两个视角研究观察性缩放，回答智能体能多快、多远地改进。
◆通过工作区干预分析改进遗留效应，发现移除历史降低后期成功、冻结工作区在新布局仍有用、三个跨任务案例更早成功。
结果表明场景特定适应与可复用经验可以共存，为理解和评估物理RSI提供新框架与实证依据。</td></tr>
<tr><td>2026-10-19</td><td>HandsOn: A Large-Scale Simulation Benchmark for Generalizable Dexterous Manipulation<br><a href='http://arxiv.org/pdf/2610.26765'>论文</a></td><td>HandsOn是面向跨具身灵巧操作的大规模可组合仿真平台与基准，旨在研究操作泛化与可靠物理交互的边界。
◆构建支持五种机械臂、六种灵巧手和约200种刚体、铰接及可变形资产随机场景的统一仿真平台。
◆提供18000条精选人类演示与66个经人工验证任务，其中Core-50用于演示学习与执行测试，Transfer-16评估资产与关系迁移、技能组合和无可训练演示的可变形操作。
◆设计覆盖扩散、视觉语言动作、世界动作及提示式VLM等方法的系统评测协议，并用真实机器人定性验证仿真到现实迁移。
◆通过训练策略阶段诊断揭示接触建立、动作协调、目标维持及组合任务排序等失败模式。
实验显示最佳多任务策略Core-50成功率29.1%，未基准微调的GPT-6仅获5.2%和1.9%，为操纵泛化研究提供共享基准。</td></tr>
<tr><td>2026-10-19</td><td>Cartender: Verifiable Language-Conditioned Driving by Learning the Drives Not Taken<br><a href='http://arxiv.org/pdf/2610.26390'>论文</a></td><td>论文提出Cartender，把驾驶建模为“场景决定可行行为、指令从中选择”的一对多问题，并利用未采取的驾驶行为学习可验证的语言条件策略。  
◆Counterfactual Branching无需模拟器，从真实记录构造匹配与不匹配的指令-动作对，用视觉语言模型提出替代未来及对应指令，并以不支持指令作为负标签。  
◆学习场景-语言兼容性分数，在轨迹生成中调节语言条件的作用。  
◆引入奖励训练的语言残差，在场景分数上对生成候选进行重排序。  
◆采用同场景交换指令、测行为而非比对生成目标的评估方式，直接检验指令遵循与场景约束。  
在WOD-E2E上，四候选最佳RFS达8.642，8974个候选平均RFS为8.203且67%优于记录轨迹；相比仅匹配模仿，同场景配对指令成功率从23.67%升至57.00%，RFS从6.32升至7.10，门控将不可行指令执行率从53.36%降至14.18%。</td></tr>
<tr><td>2026-10-19</td><td>Think Densely, Act Sparsely: Latent Expert Cognitive Chains for Vision-Language-Action Autonomous Driving<br><a href='http://arxiv.org/pdf/2610.25734'>论文</a></td><td>本文提出“密思而疏行”的VLA自动驾驶新范式，并构建LECDrive框架，旨在解决稀疏监督导致密集视觉信息被压缩丢弃的问题。
◆ 以紧凑的任务特定潜在令牌为认知载体，在VLA模型内嵌入渐进式潜在专家认知链，显式形成密集世界表示而非仅依赖模型容量。
◆ 将DINOv3视觉表示、SAM3语义结构和DepthAnything3空间几何知识内化到潜在认知链中，实现密集感知与高效推理的统一。
◆ 采用课程学习组织从表示到语义再到几何的渐进监督，使认知链各环节相互依赖并结构化为可解释的专家认知过程。
实验表明LECDrive在多个自动驾驶基准上稳定提升基础VLM，覆盖物体感知、状态预测和轨迹规划等关键任务。
这些结果说明通过结构化潜在专家链构建密集世界模型，是提升VLA自动驾驶安全性与可解释性的有前景方向。</td></tr>
</tbody>
</table>
</div>

<h2 id='robot-visual-semantic-recognition'>Robot Visual Semantic Recognition</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-15</td><td>Safe and Fuel-Efficient Motion Planning for Lunar Propulsive Drones<br><a href='http://arxiv.org/pdf/2610.22225'>论文</a></td><td>本文提出面向月球推进无人机的自主运动规划框架，通过视觉引导最优控制在指定航点间完成安全且省燃料的跳跃。  
◆ 统一融合全局航点规划、抛物线跳跃最优控制与自主改向着陆，兼顾任务连续性与安全性。  
◆ 构建面向月面航拍图像的定制语义分割模型，用于识别障碍并评估候选着陆点安全性。  
◆ 提出快速计算可达地形的方法，以判断航点或着陆点是否安全可达。  
◆ 采用模型预测控制鲁棒跟踪跳跃轨迹，引导无人机飞向安全着陆点并降低跟踪误差。  
在高保真月球仿真中，该框架生成了安全、省燃料且可快速低误差跟踪的跳跃轨迹。</td></tr>
<tr><td>2026-10-15</td><td>SpaceCache: Intermediate Feature Reuse for Efficient Semantic Segmentation on Point Cloud Streams<br><a href='http://arxiv.org/pdf/2610.21207'>论文</a></td><td>该论文面向点云流语义分割，发现连续帧高度重叠且点云Transformer中间特征对相同空间区域跨帧语义一致，尤其深层阶段。
◆ 提出免训练的SpaceCache，跨帧直接复用中间特征，无需重新训练或微调。
◆ 设计跳过式计算：已观察区域token跳过若干Transformer块并读取缓存特征，仅计算剩余token，再恢复完整token布局用于密集预测。
◆ 引入轻量缓存管理，通过限制条目年龄和淘汰低置信条目，保证复用特征可靠。
◆ 与token merging不同，其token选择代价极低，且缓存操作每个编码器阶段仅执行一次。
在nuScenes、Waymo、ScanNet及Utonia、LitePT-B上，SpaceCache最高达1.65倍加速，mIoU下降不足1点，并持续优于token merging方法。</td></tr>
<tr><td>2026-10-14</td><td>MultiFly: A Real-World Multimodal Aerial Dataset with Annotation-Efficient Label Transfer and Cross-Modal Semantic Consistency<br><a href='http://arxiv.org/pdf/2610.10359'>论文</a> | <a href='https://github.com/markus-42/multifly'>代码</a></td><td>本文提出MultiFly，一个面向低空无人机语义感知的真实世界多模态数据集，覆盖RGB、热红外、LiDAR和雷达。
◆ 数据集包含四个郊区场景的17,272个同步样本，提供15类逐帧语义标注以及标定和GNSS-RTK/IMU测量。
◆ 提出标注高效标签迁移方法，仅用115张人工标注RGB图像，通过共享几何表示将标签传播到全部四种模态。
◆ 该方法额外生成17,157张RGB、17,272张热红外、8.4亿LiDAR点和340万雷达点的语义标签，迁移标注平均一致率达89.93%，六种模态对平均语义一致性达90.94%。
◆ 建立四种模态的语义分割基准，揭示密集LiDAR与稀疏雷达数据需要不同架构行为。
综上，MultiFly是首个公开的真实低空航空多模态基准，为可扩展多模态空中感知提供基础。</td></tr>
<tr><td>2026-10-11</td><td>GNFormer: Gaussian Neural Field Transformer for Efficient Camera-based Occupancy Prediction<br><a href='http://arxiv.org/pdf/2610.15522'>论文</a></td><td>本文提出用于相机占据预测的GNFormer，核心是解决现有高斯方法基元利用率低与表达力不足的问题。
◆ 提出Gaussian Neural Field（GNF）三维表示，由高斯基元与神经网络联合参数化占据场，高斯基元定义空间支撑并提供特征，神经网络负责更表达力强的语义占据解码。
◆ 开发Gaussian Neural Field Transformer（GNFormer），一种简洁灵活的框架，可直接预测GNF并完成相机占据预测。
◆ 在Occ-ScanNet、SSCBench-KITTI-360和nuScenes-SurroundOcc上，GNFormer在对比单帧方法中取得最高IoU、mIoU和最快推理速度。
◆ 实验仅用256个室内和1024个室外高斯基元即可表示场景，显著少于先前高斯方法，并提升基元利用率。
本文主要贡献是提出GNF与GNFormer，实现高效、准确的相机占据预测。</td></tr>
<tr><td>2026-10-09</td><td>ForeAct3D: Policy-Grounded Future World Modeling for VLA Policies<br><a href='http://arxiv.org/pdf/2610.04607'>论文</a> | <a href='https://github.com/anthonytao80-crypto/ForeAct3D'>代码</a></td><td>ForeAct3D提出一种嵌入VLA策略、由策略动作接地的未来世界建模框架，训练时用未来语义3D预测和物理约束塑造动作生成表征，推理时无需未来预测。
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
</tbody>
</table>
</div>

<h2 id='robot-vpr'>Robot VPR</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-12</td><td>Removing the Compute Bottleneck for Event-based Visual Place Recognition with Spiking Neural Networks<br><a href='http://arxiv.org/pdf/2610.16022'>论文</a></td><td>本文针对事件视觉地点识别下游仍采用稠密类帧计算、丢失低延迟优势的问题，提出在普通CPU上数十微秒内完成查询的稀疏脉冲神经网络方案。
◆ 采用加性STDP训练两层SNN，使权重矩阵形成强双峰分布，便于激进幅度剪枝。
◆ 推理时仅读取查询活跃像素对应的剪枝权重，避免稠密计算和无效访存。
◆ 由于存活权重幅度接近均匀，神经元打分简化为匹配突触的整数计数，而非加权求和，从而降低单查询延迟。
◆ 该稀疏计算规模小到可常驻CPU片上高速缓存，支持低延迟执行。
在三个事件VPR基准上，该方法召回超过LENS，延迟降低5.5至6.2倍至数十微秒，并匹配稠密版本和SAD基线召回，同时读取权重少10倍，表明事件输入与学习权重的稀疏性已可用于传统处理器低延迟推理。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5294</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4785</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2475</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1658</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1624</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1528</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1361</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1313</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1110</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>1076</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>951</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>814</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>783</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>747</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>746</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>733</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>695</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>673</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>634</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>625</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>617</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>589</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>570</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>540</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>513</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>473</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>464</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>373</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>350</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>280</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>274</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>259</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>243</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>229</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>226</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>217</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>213</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>152</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>146</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>123</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2883</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1678</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1368</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1097</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1060</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>884</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>712</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>670</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>668</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>624</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>606</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>578</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>576</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>572</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>554</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>519</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>514</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>464</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>457</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>455</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>334</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>330</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>311</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>305</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>289</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>278</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>258</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>246</td><td>This package provides an end-to-end system to lase</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>142</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>139</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/data-driven-dynamics'>data-driven-dynamics</a></td><td>134</td><td>Data Driven Dynamics Modeling for Aerial Vehicles</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>132</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
<tr><td><a href='https://github.com/ethz-asl/phaser'>phaser</a></td><td>132</td><td>A robust pointcloud registration pipeline based on</td></tr>
<tr><td><a href='https://github.com/ethz-asl/ssc_exploration'>ssc_exploration</a></td><td>112</td><td>Incremental 3D Scene Completion for Safe and Effic</td></tr>
<tr><td><a href='https://github.com/ethz-asl/active_grasp'>active_grasp</a></td><td>111</td><td>Closed-loop next-best view planning for grasp dete</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waypoint_navigator'>waypoint_navigator</a></td><td>108</td><td>Stand-alone waypoint navigator</td></tr>
<tr><td><a href='https://github.com/ethz-asl/reinmav-gym'>reinmav-gym</a></td><td>106</td><td>Reinforcement Learning framework for MAVs using th</td></tr>
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
> 更新于: 2026.10.21
