# 计算机视觉领域最新论文 (2026.11.18)

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
<tr><td>2026-11-17</td><td>Pressure Drop: Gravity Vector Estimation from a Distributed Barometric Pressure Sensor Array<br><a href='http://arxiv.org/pdf/2611.23120'>论文</a></td><td>本文提出利用分布式气压高度计阵列直接观测重力向量方向，为移动机器人SLAM中的重力约束提供新思路。  
◆ 将高度计测量引入重力向量估计，实现对重力方向的直接观测，而非依赖IMU等间接观测。  
◆ 给出估计噪声的理论分析，并通过大量实验验证，同时评估传感器间距对估计精度的影响。  
◆ 在准静态场景下实现0.87度中位倾角估计误差，并与基于IMU的先进方法对比，在高动态场景性能相近，在加速度计饱和的特定情况下更优。  
◆ 将方法集成到ICP算法中，展示其在机器人系统中的潜在应用。  
实验结果表明该方法可行且具应用潜力。</td></tr>
<tr><td>2026-11-17</td><td>Technical Report of Mobile Manipulator Robot for Industrial Environments<br><a href='http://arxiv.org/pdf/2611.22852'>论文</a></td><td>本文提出并实现了面向工业环境的@Work移动操作机器人，用于提升重复性或危险作业的效率。
◆ 采用4轮Mecanum驱动、5自由度机械臂和3D打印夹爪，实现全向移动与物体抓取操作的一体化硬件集成。
◆ 以ESP32自定义PCB和NVIDIA Jetson Orin NX构建分层电子系统，兼顾实时控制与高层计算处理。
◆ 融合Hector SLAM、A*路径规划和YOLO实时目标检测，并利用多传感器数据实现鲁棒导航与可靠避障。
系统在类工业场景中验证了自主导航、物体处理和任务执行能力，体现了有效的软硬件协同集成。</td></tr>
<tr><td>2026-11-17</td><td>DGV-DLIVO: Degeneracy-Guided Visual Fusion for Direct LiDAR-Inertial-Visual Odometry in Degenerate Tunnel Environments<br><a href='http://arxiv.org/pdf/2611.22385'>论文</a> | <a href='https://github.com/0RayZhang0/DGV-DLIVO'>代码</a></td><td>本文提出DGV-DLIVO，一种面向极端隧道环境的退化引导视觉融合直接LiDAR-惯性-视觉里程计，核心是将LiDAR退化方向作为主动引导信号，而非仅把视觉当作通用互补传感器。
◆利用LiDAR退化方向主动确定信息量更高的视觉区域，并建立LiDAR锚定的视觉关联。
◆仅将视觉约束引入缺失的运动子空间，同时自适应抑制同方向不可靠LiDAR信息并保留可靠几何约束。
◆设计子空间选择性融合机制，实现退化方向引导下的LiDAR、惯性与视觉自适应融合。
真实水电隧道实验表明，DGV-DLIVO在车载和手持采集下均保持连续、方向一致的隧道轴向运动估计，40m序列进度比达91.4%，显著优于代表性LIO、LIVO和VIO方法并改善纵向恢复与轨迹稳定性。</td></tr>
<tr><td>2026-11-17</td><td>CoSphere-SLAM: Multi-Agent Panoramic Gaussian Splatting SLAM with Spherical Loop Closure<br><a href='http://arxiv.org/pdf/2611.22235'>论文</a></td><td>CoSphere-SLAM是首个面向全景相机的多智能体高斯泼溅SLAM框架，面向搜索救援、建筑巡检和仓储自动化中的密集协同建图。它针对全景智能体任意3D朝向下的重叠观测、对称房间中相互一致的假闭环、连续单目尺度漂移及短基线深度噪声等难题。
◆ 提出球面闭环：在SO(3)上通过快速傅里叶相关对齐球面特征，并以全局Sim(3)一致性拒绝对称假闭环。
◆ 提出方向性全局优化：求解逐关键帧Sim(3)位姿图并用对数尺度正则，分离光流平移方向与深度幅值以校正尺度漂移。
◆ 提出全向高斯融合：按关键帧相似度变换高斯，并在最大射线响应处渲染高斯，联合优化位姿与地图。
室内和跨会话多智能体全景基准实验表明，该方法在单智能体和多智能体方法中取得领先的轨迹精度与渲染质量。</td></tr>
<tr><td>2026-11-17</td><td>SE(3)-LIVOM: Adaptive Multi-LiDAR-Inertial-Visual Odometry and Mapping<br><a href='http://arxiv.org/pdf/2611.22047'>论文</a> | <a href='https://github.com/url-kaist/se3-livom-comfort'>代码</a></td><td>SE(3)-LIVOM是IROS 2026 COMFORT挑战赛总冠军方案，面向GrandTour数据集中坍塌建筑、工地和雪地等复杂场景，实现双LiDAR、单相机和IMU的实时里程计与建图。
◆ 将SE(3)-LIO前端扩展到多LiDAR与相机融合，并引入自适应下采样，使每帧扫描处理时间在场景内外均保持约35 ms。
◆ 提出在线后端，通过子图上的平面BA和增量位姿图优化来纠正漂移。
◆ 采用单一配置覆盖全部测试场景，在六个场景上取得平均ATE 1.40 cm，并开源代码。
整体上，该系统在复杂腿式机器人场景中兼顾了实时性、多传感器鲁棒性和高精度建图。</td></tr>
<tr><td>2026-11-16</td><td>WinDEX: Metric 3D Hand Motion Reconstruction in the Wild for Dexterous Teleoperation and Policy Learning<br><a href='http://arxiv.org/pdf/2611.21143'>论文</a> | <a href='https://fruitrabbit.github.io/WinDEX/'>代码</a></td><td>WinDEX面向野外低成本、大规模人手操作数据采集与度量三维重建，提出覆盖采集、标注、网络和部署的完整系统。  
◆提出几何-时间优化，从野外第一视角双目视频生成度量三维手标注，并结合视觉惯性SLAM实现世界坐标系重建。  
◆构建WinDEX-Net端到端鱼眼原生网络，融合标定双目、局部细节和时间上下文，并通过模型辅助标注与重训练形成数据-模型飞轮。  
◆利用蒸馏模型同时支持离线重建和因果流式推理，服务强化学习与实时遥操作。  
◆设计低成本CyberCap双目惯性采集设备，构建WinDEX-Hand数据集，含1000小时训练标注，以及留出的野外人工标注2D评测集和独立光学动捕评测集。  
实验显示离线重建达43.61 FPS、因果流式达171 FPS，野外重投影误差14.5像素、世界关节误差37.29毫米，强化学习成功率分别为WiLoR和HaWoR参考的7.6倍和3.6倍，并实现实时臂手遥操作。</td></tr>
<tr><td>2026-11-16</td><td>Improving Radio SLAM via Information Sharing: Collaborative Performance Bounds<br><a href='http://arxiv.org/pdf/2611.20925'>论文</a></td><td>本文面向6G ISAC时代的密集车辆环境，研究多用户设备与环境路标/目标联合估计的协作无线电SLAM性能极限。  
◆推导了集中式多UE蜂窝无线电协作SLAM的后验克拉美-罗界，能够刻画UE数量、几何构型及不同观测能力对定位与建图的影响。  
◆揭示了信息共享性能随UE密度变化的缩放规律和收益递减区间，给出与估计器无关的协作建图与定位性能极限。  
◆通过车辆场景数值结果验证了所提框架，并证明其相对单UE无线电SLAM具有显著性能增益。  
◆该框架可为协作无线电SLAM的UE部署、信息共享策略和系统设计提供理论支撑。  
总体而言，论文将信息共享引入无线SLAM性能界限分析，突出了多UE协作在6G感知通信融合中的潜力。</td></tr>
<tr><td>2026-11-16</td><td>OrthoMark: Place Recognition with Point-Anchored Orthographic Height Mark<br><a href='http://arxiv.org/pdf/2611.20570'>论文</a></td><td>本文提出免训练的OrthoMark激光雷达地点识别方法，其核心原则是仅通过两帧扫描中来自同一几何表面的特征进行比较。  
◆创新点一是采用BEV极坐标傅里叶谱进行平移旋转不变的候选检索，每关键帧描述子仅1.9KB。  
◆创新点二是通过相位相关估计平面位姿，并用点锚定高度柱逐单元验证，每个BEV单元以16位掩码记录自身返回高度。  
◆创新点三是同会话内按两扫描距离计算的传感范围预期重叠，对高度柱评分加权。  
论文揭示高度信息在验证中有效，但在检索中会因距离依赖的垂直视场裁剪而误导全局键。  
在KITTI单机器人免训练且无3D配准方法中AP最高，多机器人序列匹配或超过RING++且描述子仅其1/350，并在所有测试中比BEVPlace++闭合更多机器人间回环。</td></tr>
<tr><td>2026-11-16</td><td>sqrtVINS-Based 360 Visual-Inertial SLAM Systems: Hilti-Trimble SLAM Challenge 2026 Entry<br><a href='http://arxiv.org/pdf/2611.20568'>论文</a></td><td>本文提出一套仅依赖双鱼眼图像与IMU的360视觉惯性SLAM系统，面向Hilti-Trimble 2026挑战赛的长室内复杂场景。
◆ 采用低光增强与静态/动态掩码预处理，提升暗区和动态环境下输入质量。
◆ 前端基于sqrtVINS，融合SuperPoint特征、ELSED线特征与LightGlue匹配实现局部里程计。
◆ 后端基于GTSAM构建紧耦合因子图，结合SALAD全局描述子与视觉BA进行轨迹优化。
◆ 提出局部到全局无结构BA、紧正则内外参精化，并利用相机基线与跨视图约束进行全局尺度调整。
实验表明该方法在多个室内序列中与楼层平面图对齐良好，且流程可在给定ROS2工作空间中复现。</td></tr>
<tr><td>2026-11-15</td><td>M-CROSS: A Multisensor Simulation Dataset for SLAM across Water--Land Transitions<br><a href='http://arxiv.org/pdf/2611.19765'>论文</a></td><td>本文提出M-CROSS，据称是首个面向连续水陆过渡场景SLAM的多传感器仿真数据集与评测基准。
◆ 构建跨陆地、过渡和水下阶段的多传感器同步仿真数据，包含LiDAR、声呐、双目相机、IMU、DVL、深度测量及6DoF位姿真值。
◆ 提供逐传感器介质状态标注和介质相关传感器退化模型，用于刻画水陆过渡引起的传感器特性突变与失效。
◆ 设计过渡感知评测协议，包括轨迹完成率TCR、分段绝对位姿误差PW-APE、过渡终点误差TEE和过渡生存期TSP。
◆ 基于6种代表性SLAM系统的实验揭示现有方法在全水陆过渡中易出现过渡性漂移、轨迹不连续和跟踪失败。
该数据集已公开，可作为跨水陆SLAM定位鲁棒性与连续性的基准。</td></tr>
<tr><td>2026-11-14</td><td>DEFDVO: Deformable Deep Visual Odometry for Equirectangular Images<br><a href='http://arxiv.org/pdf/2611.19095'>论文</a> | <a href='https://github.com/BurakSevsay/DEFDVO'>代码</a></td><td>DEFDVO提出一种直接面向等距柱状投影（ERP）全景图像的基于图像块的深度视觉里程计方法，系统缓解纬度相关畸变、边界接缝和极区采样偏差。◆采用球面几何先验初始化的可变形特征提取，将球面先验与学习到的采样偏移结合，以更好适应全景畸变。◆实现端到端接缝感知估计，保持ERP图像左右边界连续性，减少人工接缝影响。◆设计球面梯度图像块选择策略，降低极区过采样偏差并改善特征分布均衡性。该方法仅用合成TartanAirV2 ERP数据训练，却在TartanAirV2评测上将最佳先前方法的平均绝对轨迹误差从0.201米降至0.042米，提升4.8倍，并在真实360DVO基准两个划分上取得最低平均ATE。</td></tr>
<tr><td>2026-11-12</td><td>RGB-D SLAM on the Edge: Benchmarking and Profiling RTAB-Map and ORB-SLAM3 on the Raspberry Pi 5<br><a href='http://arxiv.org/pdf/2611.16472'>论文</a></td><td>本文在 Raspberry Pi 5 上系统评测并剖析 RTAB-Map 与 ORB-SLAM3 的 RGB-D SLAM 性能，弥补 ARM 边缘板上标准 RGB-D SLAM 运行数据不足的问题。
◆ 构建了覆盖 6 个 TUM RGB-D 序列、3 种分辨率的基准，逐次记录跟踪覆盖率、轨迹误差、每帧耗时、内存、CPU 负载和温度，并开展阶段级与函数级剖析。
◆ 通过每帧处理配置揭示 RTAB-Map 前端耗时 38–74 ms、全流程 150–462 ms，而 ORB-SLAM3 为 13–45 ms 和 26–62 ms，并定位 RTAB-Map 主要开销来自默认无界增长的位姿图优化。
◆ 发现 ORB-SLAM3 的局部 BA 开销与跟踪相当但并行执行，且四分之一分辨率下两者多在多数序列丢失跟踪；丢失跟踪的运行更早结束且保留位姿误差更低，因此时间与精度必须结合覆盖率解读。
实验表明计时重复性为 1–5%，但相同运行轨迹误差可差 27%，两系统精度差异尚不 conclusive，且全程未发生热降频。</td></tr>
<tr><td>2026-11-12</td><td>DPGS-SLAM: Diffusion-Prior and Provenance-Aware Monocular Gaussian Splatting SLAM for Dynamic Visual Sensing<br><a href='http://arxiv.org/pdf/2611.12038'>论文</a></td><td>DPGS-SLAM提出一种面向动态场景的单目RGB高斯泼溅SLAM框架，在动态观测污染跟踪与建图、且剔除动态会导致遮挡静态背景缺失的情况下实现稠密建图。
◆ 采用光流运动发现与SAM2时序一致掩码传播识别动态区域，降低动态物体对SLAM稳定性的影响。
◆ 设计异步扩散背景补全机制，对关键帧遮挡区域用微调扩散修复模型生成合理背景，并由Metric3D v2预测度量深度初始化临时高斯图元。
◆ 引入provenance-aware高斯建图，用来源标签区分生成图元与观测支持图元，生成内容不参与相机位姿估计和观测地图优化。
◆ 当原遮挡背景可见时移除合格生成图元，并由真实RGB观测和预测深度独立初始化观测支持图元，实现临时补全到真实观测的替换。
实验表明其在TUM和BONN上取得有竞争力的跟踪精度，ATE RMSE分别为1.2 cm和2.7 cm，并在StaDy4D上仅用单目RGB较WildGS-SLAM平均PSNR提升4.60 dB。</td></tr>
<tr><td>2026-11-11</td><td>IncR-3DSGG: Incremental Posed RGB Image Based 3D Scene Graph Generation via Privileged Depth Supervision<br><a href='http://arxiv.org/pdf/2611.15429'>论文</a></td><td>IncR-3DSGG提出一种仅依赖带位姿RGB图像的增量式3D场景图生成框架，推理阶段无需深度传感器或重建几何。
◆将深度/3D几何仅作为训练期特权监督，使模型在推理时摆脱深度传感限制。
◆设计参数化关系预测器PRP，从2D视觉特征与2D几何线索估计物体间距离和相对角度。
◆利用位姿图优化PGO跨视图融合学习到的成对测量，恢复度量落地的3D物体位置并增量构建全局一致场景图。
在真实3RScan数据集上，该方法取得52.2平均物体召回和30.8平均谓词召回，显著优于MonoSSG的27.0和17.6，且推理不使用深度或重建几何。
结果表明，仅凭带位姿RGB图像即可预测物体关系并获得度量一致的3D场景图表示。</td></tr>
<tr><td>2026-11-10</td><td>CFAR Detection on Non-Coherently Integrated Angular Maps for mmWave Radio SLAM<br><a href='http://arxiv.org/pdf/2611.14250'>论文</a></td><td>本文针对毫米波波束扫描双基地ISAC的SLAM多径检测，指出现有CFAR基于I/Q数据立方体，不适用于非相干积分后的角度功率图。
◆推导了面向非相干积分角度功率图的改进CFAR检测器，修正后积分噪声统计与标准CA-CFAR假设的差异。
◆提出多单元CUT表述，以更好适配实际检测需求并提升CFAR实用性。
◆设计十字形训练窗，在考虑旁瓣结构的同时显著降低计算开销。
基于60 GHz室内实测和snapshot-SLAM评估，所提CFAR较SVD检测器将整体定位RMSE从0.30 m降至0.24-0.26 m，NLOS场景提升最大。
多单元非相干检测器进一步降低复杂度且不损失定位精度，表明其适合实际多径无线电SLAM。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-17</td><td>Refin3R: Geometry-Guided Refinement for Feed-Forward 3D Reconstruction<br><a href='http://arxiv.org/pdf/2611.23051'>论文</a></td><td>Refin3R针对前馈三维重建点图跨视角不一致且精度不足的问题，提出用SfM点精化点图并将SfM几何传播到图像网格。其双分支架构让2D分支借助几何感知骨干特征扩展SfM覆盖，3D分支对所有视图SfM点推理以捕获多视图结构，两分支双向交换信息并联合精化每个视图，输出密集准确点图。
◆ 以SfM点引导前馈点图精化，并将SfM几何传播到图像网格，而非仅作辅助输入。
◆ 设计2D-3D双分支架构，分别扩展SfM覆盖范围并推理多视图SfM结构。
◆ 通过两分支双向信息交换实现逐视图联合精化，生成密集且准确的点图。
实验表明，Refin3R在ScanNet++、ETH3D、Tanks&amp;Temples及域外人体和手术场景中精度持续领先，且快于最强几何引导基线。</td></tr>
<tr><td>2026-11-16</td><td>Pointillist Maize: 3D Reconstruction of Field-Grown Maize Using RGB UAV Imagery<br><a href='http://arxiv.org/pdf/2611.20502'>论文</a></td><td>本文评估消费级无人机RGB视频结合SfM与MVS能否重建田间玉米并恢复可识别器官，系统考察飞行轨迹与帧采样对重建质量的影响。
◆验证了该流程可恢复叶片、茎、雄穗分枝、果穗、花丝和气生根等田间玉米器官级结构。
◆通过等帧对比量化了单轨道与ribbon skirt轨迹在点云集中度、可见空洞和孤立散点之间的取舍。
◆揭示增加蛇形航线和提高帧采样率能降低密植苗行渲染空洞，但也会因植株运动增加点云弥散。
◆展示curlicue轨迹可在另一田块区分单株且无明显重复结构，同时指出土壤表面仍存在较大空洞。
◆明确当前重建在定量表型前仍需独立几何验证，并给出采集策略、重建完整性与点弥散之间的权衡。</td></tr>
<tr><td>2026-11-15</td><td>Remember, Replay, Adapt: Learning from Past Experience in Online Vision-and-Language Navigation<br><a href='http://arxiv.org/pdf/2611.19901'>论文</a></td><td>论文针对在线VLN中已有反馈未被充分利用的问题，受人类情景记忆启发提出R2A在线适应框架，持续复用成功与失败导航经验进行策略学习。
◆ 提出成功-失败记忆SFM，保留带反馈的成功和失败导航片段，并依据新指令检索任务相关经验，使历史反馈指导后续导航。
◆ 提出先验锚定适应PAA，以冻结预训练策略为锚，相对其强化成功轨迹、抑制失败轨迹，并正则化行为漂移。
二者结合实现了无需源域数据和专家监督的持续反馈复用与稳定策略适应。
在REVERIE、R2R、R2R-CE及五个导航骨干上实验验证一致提升，REVERIE验证未见集上DUET的SR从46.98%升至69.84%，SPL从33.73%升至50.98%。</td></tr>
<tr><td>2026-11-13</td><td>Interpreting JWST UV luminosity functions and angular correlation functions via a &quot;universal language&quot; for high-redshift galaxies<br><a href='http://arxiv.org/pdf/2611.18850'>论文</a></td><td>论文提出连接暗晕质量、恒星质量、恒星形成率和UV星等的“通用语言”，以跨模型与数据一致定义的条件分布链，并用五个流体模拟构建宽先验，联合z&gt;6 JWST的UV光度函数与角相关函数推断星系种群参数。
◆ 建立可跨模型与观测同口径比较的柔性星系种群框架，缓解不同物理过程却给出相似压缩统计量而难以判别的问题。
◆ 联合UV LF与质量完备的ACF进行贝叶斯推断，发现大SHMR弥散被ACF显著压低。
◆ 在模拟先验下得到SFMS恒星形成时标约一个暗晕动力学时标，且SFMS弥散随恒星质量降低而增大，并量化其为固定暗晕质量下UV星等随机性的主源（MUV=-20处约61%，SHMR约36%）。
◆ 贝叶斯模型选择未发现SHMR随红移演化或SFMS斜率偏离1的证据，且z~20预测UV LF比候选体估计低数个量级，指出z≥14 UV LF估计需达成共识。
整体上，该工作提供了统一、可检验的高红移星系统计建模与解释框架。</td></tr>
<tr><td>2026-11-13</td><td>Deep Bundle Adjustment<br><a href='http://arxiv.org/pdf/2611.18256'>论文</a> | <a href='https://cphjsn.github.io/deep-ba/'>代码</a></td><td>DeepBA提出一种图神经网络，将捆绑调整摊销为可学习的图网络，从任意数量视图的2D匹配中恢复相机位姿、内参和场景结构。它不逐场景求解非线性最小二乘，而是基于几何残差迭代精化估计，并能从冷启动收敛。模型采用尺度不变监督（真值旋转、平移方向、内参及重投影自洽），可混合任意度量单位数据集，且与匹配器解耦。
◆ 将BA摊销为学习式GNN，用几何残差迭代精化位姿、内参和结构，无需逐场景非线性优化与细致初始化。
◆ 采用尺度不变监督和重投影自洽，支持任意度量单位数据集混合训练，并实现与匹配器解耦。
◆ 仅2.04M参数即优于已有学习式SfM，在多数位姿指标和重建上领先，中等精度下与经典SfM相当、随视图数增加耗时反超，并接近VGGT等大模型但模块化更强。</td></tr>
<tr><td>2026-11-09</td><td>Budget-aware Correspondence-driven View Selection for Real-time 3D Perception of Mobile Robots<br><a href='http://arxiv.org/pdf/2611.11809'>论文</a></td><td>本文提出预算感知、对应关系驱动的视图采样算法BCVS，用于移动机器人实时3D感知中的在线图像序列过滤。  
◆ 不依赖完整SfM流程或相机位姿估计，仅用纯对应关系评分选择视图，在保持几何稳定性所需重叠的同时优先选择新颖视图。  
◆ 根据用户给定预算迭代选取最独特帧并抑制近重复帧，生成紧凑子集以保持连通性并最小化重建损失。  
◆ 算法CPU上可达22+ FPS，支持在线过滤，并在紧预算下优于CPU友好基线，预算增大时仍具竞争力。  
基准实验验证了BCVS在紧预算下的性能优势与可扩展性。  
大型航空和海洋机器人实地试验表明，其可减少最高16%冗余，同时保持稳健SfM配准和高质量3D重建。</td></tr>
<tr><td>2026-11-09</td><td>Towards Rotation-Only Imaging Geometry: Multi-View Pose Estimation<br><a href='http://arxiv.org/pdf/2611.11770'>论文</a></td><td>本文提出以旋转为核心的多视图位姿估计框架，将全局旋转估计与全局平移恢复统一到仅旋转成像几何中。  
◆提出GRAM，直接利用初始相对旋转和内点匹配，通过最小化边级旋转仅代数残差估计全局旋转。  
◆用单阶段替代传统两视图相对位姿优化加旋转平均流程，减少分步误差累积。  
◆将仅旋转成像几何扩展至多视图，提出MORE，以多视图旋转仅重投影误差非线性精化全局旋转。  
◆提出ART，从LiGT约束推导局部尺度三视图平移，并用加权最小二乘恢复全局平移。  
合成与真实实验验证了方法在精度、鲁棒性和效率上的优势。</td></tr>
<tr><td>2026-11-07</td><td>VAComp: View-Aware Full Projector Compensation<br><a href='http://arxiv.org/pdf/2611.10637'>论文</a> | <a href='https://realkaizhou.github.io/VAComp/'>代码</a></td><td>VAComp是首个面向移动观看者、裸眼场景的视角感知全投影仪补偿框架，可在观看者移动时实现虚拟物体替代真实物体或视角一致的外观与材质修改。
◆ 针对SfM全局尺度未知问题，引入度量标定作为参考恢复全局尺度。
◆ 针对与投影仪反向相机的标定难题，设计分别面向RGB相机和深度相机的双棋盘标定方案。
◆ 提出两种非迭代混合方法VAComp-SD和VAComp-SI，将基于2D高斯、视角条件化的几何校正与学习式光度补偿结合。
◆ 两种方法均通过单次前向推理预测补偿图像，无需逐帧迭代优化，其中VAComp-SD支持实时更新，VAComp-SI达到交互级速率。
真实实验验证两种方法具有有竞争力的补偿质量与运行效率。</td></tr>
<tr><td>2026-11-06</td><td>OfficeTwin: Realizing 3D Reconstruction of Redundant Scenes through Partial Viewpoint Perception<br><a href='http://arxiv.org/pdf/2611.10241'>论文</a></td><td>OfficeTwin面向机器人原生采集的冗余办公场景，解决部分视角、弱纹理和重复结构下难以获得仿真可用3D模型的问题。它提出将不完整单目观测转化为仿真就绪数字孪生的机器人原生重建框架，并强调对象身份、物理属性与水密体积等下游需求。
◆ 先施加度量与结构约束，使重建结果具备真实尺度和结构一致性。
◆ 利用办公室重复隔间的结构冗余，将多次部分观测配准到共享规范帧，以互补信息恢复单视角遮挡几何，避免生成式幻觉。
◆ 在真实办公室扫描中把每个隔间重建为独立、水密、度量的实体，性能优于前馈重建和生成式基线。</td></tr>
<tr><td>2026-11-05</td><td>Degree-Equalized View-Graph Selection under Tight Pair Budgets<br><a href='http://arxiv.org/pdf/2611.07498'>论文</a></td><td>本文针对SfM中全量图像对匹配呈二次增长、需在紧预算下筛选视图图的问题，指出一次性选择器常忽略各图像已获配度数，导致边集中在少数图像并影响重建。作者提出无需训练的贪心规则Degree-Equalized Allocation（DEAL），在选择过程中对端点已被充分覆盖的图像对进行指数式降权，以实现度数均衡的视图图选择。
◆ 将“已分配度数”纳入预算化视图图选择，缓解覆盖选择器的度数集中问题。
◆ 设计无训练的指数降权贪心分配规则，可直接增强同一先验下的一次性选择器。
◆ 在九个1DSfM数据集B=2N上将同先验选择器从0.776提升到0.929，并在标准基准取得无训练选择器最高均值0.875。
实验表明DEAL在共享后端下接近SfM监督边先验的平均注册图像比例（0.929对0.930），且无需训练。</td></tr>
<tr><td>2026-11-04</td><td>METRIC-GS: Selective Metric-Scale Estimation for 3D Gaussian Splatting<br><a href='http://arxiv.org/pdf/2611.06020'>论文</a></td><td>论文提出METRIC-GS，一种面向真实室内照片的3DGS选择性度量尺度估计器，从重建自身语义内容读取尺度，并在证据不足时显式拒绝。现有分位数启发式与度量深度对齐在真实采集上分别误差约27%和35-71%，难以可靠部署。
◆ 选择性尺度估计与弃权机制：用inlier-mass检验将薄证据转为弃权，并作为路由到重型度量模型的条件。
◆ 可见性感知投票与实例尺寸先验：冻结2D教师为高斯标注，融合门、桌、地板到天花板等类别尺寸先验。
◆ 鲁棒最大似然融合：在实例级先验上稳健估计尺度，提升可作用场景数且不降部署精度。
在ScanNet++ 47场景上，单估计器把平均误差从21.1%降至16.6%（实际作用28场景为9.3%，约11秒/场景），仅将弃权样本路由到MASt3R即可匹配全量运行且调用少60%；在自有手机和无人机采集上作用场景均提升、无退化，并指出前馈度量模型的公开分数并非部署估计。</td></tr>
<tr><td>2026-11-03</td><td>Visibility-Aware Reference Generation for Benchmarking Visual 3D Reconstruction in Vegetation-Rich Environments<br><a href='http://arxiv.org/pdf/2611.05361'>论文</a></td><td>本文面向植被丰富户外环境中视觉三维重建与深度估计缺乏几何真值、完整扫描成本高的问题，提出一套可复用的LiDAR参考生成流程，用于评估前馈视觉几何模型的零样本性能并与传统SfM方法对比。该流程复用现有多传感器定位数据集的相机图像、LiDAR扫描和参考位姿，生成逐视图深度图与可见参考点云。
◆提出LargeDepth-Gap Visibility Score（LDGVS），用于累积LiDAR点云的逐点可见性过滤及Hidden Point Removal的自动尺度选择。
◆构建结合HPR与LDGVS的可见参考点云生成方法，在TartanAirV2和TartanGround上相较Poisson表面重建，在相近绝对相对误差下保留约三倍点密度。
◆将流程应用于BotanicGarden并系统比较深度估计与三维重建方法，揭示前馈方法稠密高效但重建可能出现重复结构，SfM几何更一致但稀疏且在植被场景更易失败。
作者将发布基准工具包与数据集，为植被场景三维重建评测提供可复现参考。</td></tr>
<tr><td>2026-11-03</td><td>Sparse Anchors for Visual Multi-Session Registration in Changing Environments<br><a href='http://arxiv.org/pdf/2611.05084'>论文</a></td><td>本文面向环境显著变化下的视觉多会话配准，解决仅部分轨迹可获得可靠跨会话对应时，查询会话难以完整配准到参考地图的问题。方法以稀疏可靠绝对位姿约束为核心，并结合会话内相对位姿信息实现完整轨迹配准。
◆提出稀疏绝对锚点与会话内相对位姿约束融合的配准框架，在跨会话可匹配内容有限时仍能恢复完整轨迹。
◆利用序列一致性筛选视觉位置识别、局部特征匹配和几何验证产生的绝对对齐假设，剔除与共同查询—参考对齐不一致的假设并保留可靠锚点。
◆将绝对锚点通过高斯特征场进行featuremetric细化，并与会话内相对位姿约束共同纳入鲁棒位姿图优化。
在HILTI26建筑工地15组跨会话实验中，该方法取得1米内94.4%、5米内100.0%的召回率，显著优于独立图像定位和独立重建SfM几何直接配准，证明稀疏可靠锚点可实现准确且完整的轨迹配准。</td></tr>
<tr><td>2026-11-02</td><td>Ray-SCR: Generalizing Scene Coordinate Regression Across Camera Models<br><a href='http://arxiv.org/pdf/2611.03098'>论文</a> | <a href='https://jaeminch0.github.io/ray-scr-generalizing-scene-coordinate-regression-across-camera-models/'>代码</a></td><td>针对现有场景坐标回归（SCR）模型在全景、鱼眼或强矫正等不同相机模型间泛化差的问题，论文提出轻量扩展Ray-SCR。该方法将局部视觉特征条件化到标定视线，并用浅层局部Transformer精炼邻域视线条件特征。
◆ 在视线空间中直接构建监督，并以稀疏SfM点作为度量锚点，跨视角和跨相机模型连接观测。
◆ 用全景建图序列构建单一场景表示，使模型能定位针孔、鱼眼和全景等差异显著相机拍摄的查询图像。
◆ 在多种SCR架构及多相机数据集上显著提升跨相机泛化能力，取得 challenging 跨相机设置下的 state-of-the-art 定位性能。
实验表明，Ray-SCR的核心贡献在于以视线条件化和射线空间监督统一跨相机表示，从而有效缓解视场、畸变和重采样导致的像素位置差异问题。</td></tr>
<tr><td>2026-11-02</td><td>RESONATE: a Real Social Navigation Testbed for Autonomous Service Robots<br><a href='http://arxiv.org/pdf/2611.02937'>论文</a></td><td>RESONATE提出了一个面向自主服务机器人真实社交导航的可复现测试床与基准。  
◆基于统一机器人平台、共享ROS 2软件栈、精确轨迹真值和结构化社交交互场景，构建了真实世界可复现基准。  
◆设计8类场景、每类5次重复和8种控制器配置，完成320次物理实验，并提供可复用基线与数据。  
◆融合定量导航与社交指标及参与者主观评估，联合衡量效率、安全、舒适和感知社交行为。  
◆实验揭示不同方法的场景依赖权衡，并识别DWA加高斯社会代价图较可靠、SFM-MPPI在鲁棒性、导航效率和社交接受度间平衡最佳。  
◆提供一致的评估协议、基线、数据和测试床，推动社交感知导航研究发展。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-17</td><td>Automated open-set multi-view seahorse re-identification from underwater photograph sequences<br><a href='http://arxiv.org/pdf/2610.39857'>论文</a></td><td>论文提出面向水下照片序列的自动化开放集多视角海马重识别方法，并在35914张照片、474只野生海马的数据集上训练与评估。
◆ 构建大规模野生海马照片序列数据集，并统一处理物种分类、性别判定和开放集重识别任务。
◆ 将一次观察中的多张照片聚合起来，显著提升物种、性别和重识别性能。
◆ 物种与性别分类采用DINOv3嵌入的线性探针逐图分类，再对观察内照片的logits取平均。
◆ 重识别先用微调MiewID描述子检索候选，并用学习到的相关性分数对照片加权，再以ALIKED与LightGlue局部匹配和RANSAC几何校验重排候选。
◆ 用逻辑模型估计个体是否已在图库，并通过最大后验规则在最佳匹配身份与新个体之间决策。
观察级物种和性别平衡准确率分别达0.97和0.90；开放集重识别归一化准确率在图库含全部历史观察时为0.90，仅含一次观察时为0.83。</td></tr>
<tr><td>2026-11-15</td><td>Mock Observations: Morphological Analysis of Galactic Bars in IllustrisTNG Simulations<br><a href='http://arxiv.org/pdf/2611.19884'>论文</a></td><td>论文利用IllustrisTNG的TNG100/TNG50生成匹配SDSS观测条件的合成r波段图像，并以统一的源分割、形态分类和等相椭圆拟合流程比较z~0.1星系棒的统计与性质。结果显示SDSS、TNG100、TNG50全局棒分数约为26.68%、24.96%、13.42%，TNG100在约10^10至10^11.2太阳质量与SDSS较一致但更高质量偏高，TNG50多数质量段偏低。
◆构建了从模拟图像、观测条件匹配到统一形态测量的可比框架，系统比较模拟与SDSS的星系棒。
◆揭示棒分数差异与核球集中度和盘尺度相关：TNG100高n核球偏少且大质量盘更延展，TNG50高n核球偏多。
◆量化了棒长定义的系统偏差，发现外椭圆率下降估计R0.85max系统大于椭圆率峰值估计。
◆强调观测条件、样本选择和棒识别方法对棒分数与棒长推断的影响，并指出SDSS分辨率可能低估棒分数。</td></tr>
<tr><td>2026-11-06</td><td>OfficeTwin: Realizing 3D Reconstruction of Redundant Scenes through Partial Viewpoint Perception<br><a href='http://arxiv.org/pdf/2611.10241'>论文</a></td><td>OfficeTwin提出一种面向机器人原生采集的部分视角感知框架，可将不完整单目观测转化为可用于仿真的数字孪生。
◆它先施加度量与结构约束，为重建提供稳定的物理尺度与场景结构先验。
◆它利用办公室重复隔间的结构冗余，将重复实例配准到共享规范帧，并通过互补观测恢复单视角中被遮挡的几何，避免生成式幻觉。
◆它面向仿真就绪资产，输出每个隔间独立、水密且具有度量尺度的实体模型。
在真实办公室扫描中，该方法成功恢复每个隔间，优于前馈重建和生成式基线。</td></tr>
<tr><td>2026-11-05</td><td>Federated training performs as well as centralized for 3D Latent Diffusion for Diagnosis-Conditioned Brain MRI Synthesis<br><a href='http://arxiv.org/pdf/2611.08771'>论文</a></td><td>本文提出并验证了一种面向诊断条件脑MRI合成的3D条件潜在扩散模型联邦训练方案。
◆ 首次系统比较联邦训练与集中式训练在该3D条件生成任务上的效果，证明无需共享数据也能获得相近性能。
◆ 采用条件保真度、多尺度SSIM多样性和FID真实性三类指标，从分类有效性、分布匹配和图像真实感多角度评估生成质量。
◆ 结果表明联邦训练可有效利用多站点数据，同时保持数据本地隐私。
因此，联邦学习是构建多站点脑MRI生成模型的可行路径，为稀缺和不均衡神经影像数据增强提供了新思路。</td></tr>
<tr><td>2026-11-05</td><td>USB Gym: A Gymnasium Testbed for Closed-Loop Ultrasound View Matching<br><a href='http://arxiv.org/pdf/2611.08352'>论文</a></td><td>论文提出USB Gym，用于闭环超声视图匹配的标准化测试平台，旨在检验将已发表方法组合成完整引导流程后是否足够有效。  
◆ 构建基于公开患者CT及标签驱动纹理网络的超声仿真引擎，统一模拟并评估探头移动到目标视图的闭环引导。  
◆ 将引导流程拆分为器官分割器、控制器和奖励三个可替换槽位，在同一60个episode、6名留出患者上公平接入20种已发表方法，仅在可检测更优时替换原方法。  
◆ 以20个新CT上“组合方法对比原始引导”的较优者作为基准，并用仅仿真可得的位姿oracle设定参考上限。  
实验显示探头初始平均距目标16.0 mm，oracle可达1.5 mm；仅SSIM奖励略有可检测优势，最终基准停在13.7 mm，仅为oracle进展的16%。  
结论是未调优的已发表方法组合仍无法将探头引导至目标附近，该任务仍待探索，平台可接纳新方法但尚未进行硬件验证。</td></tr>
<tr><td>2026-11-03</td><td>Sparse Anchors for Visual Multi-Session Registration in Changing Environments<br><a href='http://arxiv.org/pdf/2611.05084'>论文</a></td><td>论文面向环境变化下的视觉多会话配准，提出用稀疏可靠绝对锚点结合会话内相对位姿约束，将新查询会话的完整轨迹配准到已有参考地图。
◆ 构建了“稀疏绝对锚点+会话内相对位姿”的鲁棒轨迹配准框架，可在跨会话可靠对应仅覆盖部分轨迹时仍恢复完整轨迹。
◆ 通过视觉位置识别、局部特征匹配和几何验证生成绝对对齐假设，并用序列一致性剔除不一致假设，保留可靠绝对锚点。
◆ 对锚点采用高斯特征场上的特征度量对齐进行精化，再与相对位姿约束联合进行鲁棒位姿图优化。
在HILTI26建筑工地数据集的15组跨会话实验中，该方法1米内召回94.4%、5米内100.0%，显著优于独立图像定位和直接配准独立SfM几何。
结果表明，稀疏而可靠的绝对锚点能够在剧烈场景变化和部分可匹配条件下实现准确且完整的轨迹配准。</td></tr>
<tr><td>2026-11-03</td><td>Manifold Embedding of Deep Image Features for Image Matching via Neural Adjoint Maps<br><a href='http://arxiv.org/pdf/2611.05083'>论文</a> | <a href='https://github.com/NafieAmrani/NAMI'>代码</a></td><td>本文针对真实图像中同类不同实例间的语义对应问题，指出现有基础模型特征常因正则不足导致最近邻匹配噪声大，尤其密集对应更明显。作者将3D形状匹配中的功能映射引入图像匹配，但需为规则图像网格构造有信息量的非平凡几何。
◆提出基于深度图像特征流形嵌入，并用Galerkin有限元方法推导离散Laplace-Beltrami算子，从而赋予图像网格有意义的流形结构。
◆引入神经伴随映射以表示功能映射中的非线性映射，突破传统线性表示限制。
◆在多个真实图像密集对应基准上实现零样本图像对应新SOTA，并公开代码。
该方法核心贡献是构建了面向图像匹配的流形功能映射框架，将特征流形几何与神经非线性映射结合，提升了对应正则化和密集匹配质量。</td></tr>
<tr><td>2026-11-01</td><td>Accurate automated photo-identification of Near Eastern and European fire salamanders<br><a href='http://arxiv.org/pdf/2611.01601'>论文</a></td><td>论文提出一套面向近东火蝾螈、可跨物种迁移的自动照片识别与数据库审计流程，以零样本局部特征匹配解决人工识别慢且易错的问题。
◆ 创新点：采用SuperPoint与LightGlue进行零样本局部特征匹配，无需物种特异性训练即可完成个体重识别。
◆ 创新点：先分离黄色斑点图案，再以高置信关键点匹配数评分，降低多斑点个体累积虚假匹配的混杂，并用两级聚类分配身份。
◆ 创新点：将流程与专家复核结合，可纠正误识别并审计既有数据库，使身份数减少近四分之一。
在留出个体上正确个体排名第一达95.2%、ARI为0.958，未修改迁移至欧洲火蝾螈时两个数据集top-1为95.1%和91.7%，一个数据集重捕识别93.7%（优于五种现有程序的38%–77%，接近人工目检的93.9%）。
这表明该方法无需训练数据、能跨相关物种迁移、可扩展至千个体级数据库，并可在捕获-重捕分析前用于数据库审计。</td></tr>
<tr><td>2026-10-30</td><td>A Generalized Sparse Fuzzy Clustering Framework with Automated Cluster Cardinality Estimation Ability<br><a href='http://arxiv.org/pdf/2611.00159'>论文</a></td><td>本文提出广义稀疏模糊聚类GSFC框架，通过在模糊目标函数中引入连续稀疏惩罚，克服传统模糊聚类隶属度全稠密、抗噪性弱且难以估计真实簇数的问题。
◆ 构建统一的连续稀疏惩罚模糊聚类目标，并针对模糊指数与稀疏指数并存导致无闭式解的问题，设计原始-对偶二分搜索与专用解析路径，严格满足划分约束并将迹隶属度精确驱动为零。
◆ 利用数学强制稀疏性，在初始簇数大于真实簇数时动态剪枝冗余簇，从而自动估计真实簇数。
◆ 引入虚拟噪声汇，将离群点与正常数据隔离，提高高噪声场景下的鲁棒性。
◆ 将框架扩展至线段检测任务，并通过合成数据、高噪声几何压力测试、UCI wine和高光谱图像等实验验证其优于传统模糊基准及现有稀疏可能性与概率软聚类方法。</td></tr>
<tr><td>2026-10-29</td><td>Luggage re-identification: A study of strategies towards a real-world application<br><a href='http://arxiv.org/pdf/2610.40643'>论文</a></td><td>本文面向真实视频监控场景，研究从多路视频流到行李检测与重识别的端到端行李ReID流程，弥补现有方法多依赖干净裁剪图像外观匹配、忽视多镜头多视角互补的不足。作者在真实环境基准数据集上系统评估不同流程变体，分析同一行李多视角与多镜头观测的选择和融合方式，并考察跨环境数据集训练对整体ReID性能的影响。核心贡献在于将多视频流互补信息纳入实际行李ReID应用，并给出可操作的策略评估。
◆ 提出面向真实应用的端到端多视频流行李检测与重识别流程。
◆ 系统研究并利用同一行李的多镜头、多视角和多观测互补信息进行选择与融合。
◆ 在真实环境基准上评估跨环境数据集训练等策略，为提升实际场景行李ReID性能提供依据。</td></tr>
<tr><td>2026-10-29</td><td>Comprehensive empirical evaluation of feature extractors in computer vision<br><a href='http://arxiv.org/pdf/2610.39551'>论文</a></td><td>本文对传统特征检测与描述子进行系统实证评估，覆盖SIFT、SURF、BRIEF、ORB、BRISK、KAZE、AKAZE、FREAK、DAISY、FAST和STAR，并从架构设计与复杂度分析其计算效率和鲁棒性。研究基于Image Matching Challenge Photo Tourism 2020中超过150万张图像，完成超过200万次比较，系统考察旋转、缩放、模糊、亮度变化、仿射、透视、鱼眼和椒盐噪声等条件。结果表明FAST检测器配合ORB描述子和BF匹配器速度最快，ORB在仿射变换和亮度增强图像上表现突出，AKAZE在模糊、鱼眼畸变、旋转和透视畸变下更优。
◆ 构建了覆盖多类传统特征提取器与多种图像变换的大规模统一实证基准。
◆ 揭示了检测器、描述子与匹配器组合对效率和鲁棒性的综合影响。
◆ 给出了面向不同退化与几何变换场景的特征提取方案选型依据。</td></tr>
<tr><td>2026-10-28</td><td>Aligning Misaligned Benchmarks for Single-View Novel View Synthesis<br><a href='http://arxiv.org/pdf/2610.38349'>论文</a></td><td>论文针对单视图新视角合成评测中参考系与真值位姿对齐这一关键但未标准化的问题，系统分析了现有测试时位姿优化和依赖全场景重建对齐策略的缺陷。
◆提出用传统2D-to-2D与2D-to-3D图像匹配技术对齐三维重建，避免病态的测试时位姿优化和不可行的全场景重建。
◆提出仅在视图间共视区域进行评估，因为只有该区域能够定义正确的真值。
◆发现正确坐标对齐后，显式3D高斯方法达到当前最优，纠正了其此前被纯图像2D方法超越的结论。
◆给出直接利用现成视频生成器和前馈几何估计器的简单基线，无需任务特定训练即可与专门方法相当。</td></tr>
<tr><td>2026-10-28</td><td>WovenAnchor Matcher: Specialized Intra- and Inter-Image Context Modeling for Feature Matching<br><a href='http://arxiv.org/pdf/2610.30799'>论文</a> | <a href='https://github.com/mmaiLab/WovenAnchorMatcher'>代码</a></td><td>本文提出WovenAnchor Matcher（WAM）半稠密匹配框架，核心是按图像内与图像间上下文的不同角色进行专门化聚合。
◆ 设计角色分工的WAM框架，将图像内空间证据传播与图像间对应区域信息检索解耦。
◆ 提出WovenMamba，以先水平后垂直的状态空间传播实现图像内聚合，形成结构化二维感受野偏置。
◆ 提出AnchorCrossAttention，在局部代表锚点上进行跨注意力，从可能对应区域聚集信息并抑制无关噪声。
在MegaDepth上，WAM取得66.1 pose AUC@5°，较JamMa基线提升2.0个AUC点。
消融实验表明移除或替换任一专用组件都会降低精度，验证了角色专门化聚合设计的有效性。</td></tr>
<tr><td>2026-10-23</td><td>ACVA-Bench: Beyond Prompt Following in Abstract Concept Visualization Ability for Text-to-Image Models<br><a href='http://arxiv.org/pdf/2610.32058'>论文</a></td><td>本文定义抽象概念可视化能力（ACVA），即T2I模型在无固定视觉参照下将“忠诚”等抽象概念转化为准确、多样且可区分视觉表征的能力，并构建类别平衡的ACVA-Bench进行系统评测。
◆ 提出基于心理语言学规范的ACVA-Bench，在低干预设置下不提供具体物体、场景或视觉隐喻，从语义充分性、表征多样性、概念区分性三个维度评估ACVA。
◆ 针对抽象概念缺乏唯一参考图，提出受概念语义约束的细粒度视觉语义评估方法，将概念语义分解为可独立验证的视觉语义问题，并经人工评估验证有效性。
◆ 系统基准主流T2I模型，揭示其依赖少量原型视觉模式，在表征多样性和概念区分性上仍有明显提升空间。
◆ 提供可解释、可复现的抽象概念可视化评测基础，推动T2I从提示跟随走向更深层的概念理解。</td></tr>
<tr><td>2026-10-22</td><td>MVLoMa: Multi-View Local Feature Matching with Any Geometry Foundation Model<br><a href='http://arxiv.org/pdf/2610.31321'>论文</a></td><td>本文提出MVLoMa，一种稀疏星图局部特征匹配器，将LoMa从图像对扩展到一中心多邻居的多视图匹配，避免逐边独立匹配的参考侧重复计算并利用多视图几何证据。
◆ 使用冻结的多视图几何基础模型联合描述星图中的所有图像，并将跨视图几何上下文注入局部描述子。
◆ 通过每视图自注意力和双向中心—邻居交叉注意力，在单次前向中完成中心图像与全部邻居的匹配。
◆ 仅从深度有效且相互可见的稠密warp生成正对应，并显式惩罚违反极几何的高置信匹配。
◆ 同一设计兼容DA3、π^3、VGGT和VGGT-Ω等冻结几何编码器，且DA3-Giant表现最佳。
在HyperSim、ScanNet++、Mip-NeRF 360和Tanks and Temples的25视图星图上，MVLoMa在三个阈值取得最佳相对位姿AUC（58.65/85.41/90.99），匹配器比顺序评估24条中心—邻居边快2.20倍，消融验证了几何感知描述子、可见性过滤、几何负监督和联合多视图推理的有效性。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-17</td><td>UnrealEvent: Synthetic Dataset Generation and Annotation for Event-Based Vision<br><a href='http://arxiv.org/pdf/2611.23078'>论文</a></td><td>本文提出UnrealEvent，一个基于Unreal Engine 5.5的合成数据集生成与自动标注流水线，用于缓解事件相机目标检测标注数据稀缺问题。
◆ 将受V2E启发的事件帧生成器与EasySynth语义渲染通道结合，可直接把渲染关卡序列转换为成对事件表示和YOLO格式边界框标注，无需人工标注。
◆ 基于相邻帧逐像素对数亮度差生成事件，并从正态分布独立采样对比度阈值，以模拟真实传感器制造导致的阈值失配。
◆ 提供合成数据集，并在eTraM上系统评估YOLOv8在合成训练、零样本真实和真实微调三种设置下的表现。
实验显示合成域内性能较强，但合成到真实存在明显差距，行人尤为突出。
小规模真实子集微调可提升真实域性能，剩余差距说明资产多样性和传感器校准的重要性。</td></tr>
<tr><td>2026-11-16</td><td>SiGMA: Site-Grounded Multi-Modal ISAC Data Generation for Environment-Aware Communications<br><a href='http://arxiv.org/pdf/2611.20665'>论文</a> | <a href='https://github.com/Trans-cending/SiGMA-main'>代码</a></td><td>SiGMA提出面向环境感知通信的站点锚定多模态ISAC数据生成框架，解决新站点数据获取中传感器校准、协同测量和跨模态关联难题。
◆融合OpenStreetMap、Overture Maps与程序化3D重建生成地理参考城市场景，并以共享场景几何和时间索引的动作者状态统一多模态数据。
◆同步生成RGB图像、LiDAR点云、定位记录、FMCW雷达IQ样本和射线追踪无线信道，实现同一站点与动态场景状态下的跨模态关联。
◆支持在直连链路阻塞下按配置生成RIS分量信道，用于共享场景状态下的相位配置评估与相机辅助的传感关联监督。
实验表明该框架在真实DeepSense 6G测量上的零样本波束预测性能优于基于OSM的合成数据基线。
数据集生成流程已开源，便于复现、评估和扩展。</td></tr>
<tr><td>2026-11-12</td><td>NonSense: On the (In)security of FPGA Anti-tamper Sensors<br><a href='http://arxiv.org/pdf/2611.17065'>论文</a></td><td>本文系统性地挑战了FPGA防篡改传感器天然可信的假设，将其视为一个脆弱且未被充分探索的独立攻击面，并呼吁把传感器自身安全纳入威胁模型与防护设计。
◆揭示最先进的硬IP与软IP传感器，其检测和响应机制均可在非侵入式条件下被绕过。
◆指出供电网络的空间与频率相关特性可将故障导向目标而避开邻近传感器，从而降低检测可靠性。
◆揭示温度变化会偏移检测阈值，长期老化会导致校准漂移并可能形成静默检测缺口。
◆提出针对检测与响应机制的加固对策，以提升传感器在物理攻击和环境漂移下的可信性。</td></tr>
<tr><td>2026-11-12</td><td>VBot Exo2Ego Policy: Lightweight Data Collection and Exocentric-to-Egocentric Video Generation<br><a href='http://arxiv.org/pdf/2611.16417'>论文</a></td><td>本文提出VBot Exo2Ego Policy，将第三人称视频生成选定演员的第一人称观测，以低成本扩展第一人称操作数据。
◆ 设计轻量数据采集管线与移动应用，支持第一人称、第三人称及双视角同步采集，并结合配对RGB与相机几何学习跨视图对应。
◆ 基于预训练视频扩散Transformer引入几何引导，以及语义掩码和手部关键点辅助监督，提升手物交互生成保真度。
◆ 训练时随机注入相机几何并逐步移除，使推理阶段无需目标相机标定。
◆ 面向互联网视频多样性，融合源视频感知推理、可选演员参考和多镜头适应，识别目标演员并跨镜头跟踪操作过程。
该系统与模型为跨任务、场景和参与者扩展第一人称操作数据提供了实用基础。</td></tr>
<tr><td>2026-11-11</td><td>Target-Free Autocalibration of Stereo PIV Camera Systems via Persistent-State Motion Representations<br><a href='http://arxiv.org/pdf/2611.18741'>论文</a></td><td>本文提出一种无需标定靶标的立体PIV相机系统自标定方法，可直接从粒子图像序列恢复相机相对位姿，免除物理靶标插入流场及设备移动后的重复标定。方法针对示踪粒子外观不可区分的特点，改为匹配运动而非外观：基于CUT3R用循环Transformer的持久状态累积时序运动信息，解码各相机光流，并由跨视角解码器回归双向点对应，最终用五点RANSAC求解相对位姿。
◆提出持久状态运动表征，将粒子时序运动累积用于无靶标立体PIV外参自标定。
◆用运动匹配替代外观匹配，解决示踪粒子不可区分条件下的跨视角对应难题。
◆联合每相机光流解码与跨视角双向点对应回归，并通过五点RANSAC稳健恢复相对位姿。
◆构建带真值位姿的合成立体PIV数据集，并在标准光流基准和200组真实相机布局上验证，光流、对应和位姿精度优于现有方法。</td></tr>
<tr><td>2026-11-11</td><td>Embedded Sim-to-Real Visual Servoing: Learned Reaching and Force-Guided Placement<br><a href='http://arxiv.org/pdf/2611.15658'>论文</a></td><td>本文提出面向嵌入式平台的仿真到现实视觉伺服架构，在NVIDIA Jetson AGX Orin上以笛卡尔阻抗控制Franka Research 3，并通过RealSense D435i、YOLO11-seg分割、深度反投影和手眼标定获得机器人坐标系下的度量目标。
论文比较两类策略：从仿真迁移的紧凑PPO策略用于物体与孔区域到达，以及采用约2 N法向接触和螺旋搜索的力引导笛卡尔放置。
仿真中两类PPO在1000回合成功率分别为87.2%和83.1%，真实机器人每策略50次试验完成率为70.0%和74.0%，TensorRT感知平均延迟34.55 ms，表明学习自由空间到达结合显式接触校正可行。
◆将学习型自由空间到达与显式力引导接触校正统一到同一嵌入式视觉伺服架构。
◆在紧算力平台上实现仿真迁移的紧凑PPO视觉到达策略并完成真机验证。
◆提出约2 N法向接触加螺旋搜索的力引导放置流程，并给出真机成功率与感知延迟量化结果。</td></tr>
<tr><td>2026-11-10</td><td>GEMOR-GS: Global Extrinsic-calibration-refined Mapping and Online Relocalization for 3D Gaussian-Splatting SLAM<br><a href='http://arxiv.org/pdf/2611.13528'>论文</a></td><td>GEMOR-GS面向LiDAR-惯性-视觉SLAM，构建几何精确、全局精化且可重入的3D高斯泼溅地图，以提升机器人世界模型的外观与度量一致性。
◆提出离线直接法LiDAR-相机外参标定，并在后续在线与离线流程中复用，以高质量外参支撑地图精化。
◆在标定几何下，以门控可微渲染和LiDAR投影联合目标交替优化关键帧位姿与高斯参数。
◆在解除在线约束后，从精化关键帧模式重建最终全局3DGS地图，提升全局几何与外观保真。
◆设计基于XFeat旁路地图、RANSAC-PnP粗定位和高斯RGB-D warp精化的跟踪丢失后在线重定位。
实验在自采集和五个公开序列上验证：离线重建较在线地图在配对关键帧上提升14.3–19.9 dB，PSNR较Gaussian-LIC2约高9 dB，留出重定位成功率达86–100%且与外参质量相关。</td></tr>
<tr><td>2026-11-09</td><td>Galilean Robots, Aristotelian Sensors: Joint Spatiotemporal Trajectory Estimation and Extrinsic Calibration<br><a href='http://arxiv.org/pdf/2611.12526'>论文</a></td><td>本文针对多传感器时空标定中空间外参与时间偏移分离建模、时间偏移依赖插值或连续时间轨迹的问题，提出联合轨迹估计与时空标定框架。  
◆ 采用特殊伽利略群表示机器人轨迹、亚里士多德子群表示传感器外参，通过群结构直接耦合运动与时间偏移，避免单独参数化连续时间轨迹。  
◆ 构建twist驱动和IMU驱动的运动先验，使框架适用于不同运动观测条件。  
◆ 同时支持理想时钟与非理想时钟，并基于相机、位置和测距测量进行验证。  
仿真与真实实验表明，该方法在多种异构传感器配置下取得与现有方法相当的标定和轨迹估计性能，同时以更简化的框架提升了使用便利性且不牺牲性能。</td></tr>
<tr><td>2026-11-09</td><td>RAPA: Ray-Aware Physics Augmentation for Robust Camera-LiDAR Calibration<br><a href='http://arxiv.org/pdf/2611.12129'>论文</a></td><td>本文针对LiDAR点云稀疏导致棋盘格特征提取不可靠的问题，提出将棋盘格定位转化为基于圆柱形LiDAR反射率图像的2D检测任务。
◆将棋盘格定位建模为圆柱形LiDAR反射率图像上的2D目标检测，避免依赖人工3D角点标注或脆弱的几何特征提取。
◆提出射线感知物理增强RAPA，可从单次棋盘格观测生成多样合成训练样本。
◆利用RAPA生成数据提升检测器在不同传感条件下的鲁棒性和泛化能力，仅需一个标注目标观测即可自动完成LiDAR侧目标定位。
在四个独立室内外场景中，RAPA比最强图像空间增强基线在mAP@0.5上高16.1至43.1个百分点；在242次观测上有效定位数量最多，96.4%的返回检测获得有效目标位姿。
这些可靠定位支持全部四个地点的下游相机-LiDAR标定，缓解了基于目标标定的关键瓶颈。</td></tr>
<tr><td>2026-11-08</td><td>Martine: Benchmarking Multi-View 3D Surface Reconstruction Across Viewpoint Coverage, Resolution, and Lighting<br><a href='http://arxiv.org/pdf/2611.11602'>论文</a></td><td>Martine提出了一个面向受控多视角3D物体表面重建的系统性基准，旨在解决现有基准在视角覆盖、分辨率、光照及真值精度方面的偏差与不足。  
◆ 构建包含28个物体（含透明材质与精细结构）的高分辨率多视角数据集，在球冠范围84个视角、9568×6376像素下覆盖单光源与多光源采集条件。  
◆ 提供物体无关的相机标定、精确3D真值扫描，并在测试图像上量化标定与图像到几何对齐精度，使参考数据误差可控。  
◆ 提供材质属性、可见性、曲率和精细结构等3D属性掩码，支持按属性分析重建误差。  
◆ 在摄影测量、经典多视图立体、神经隐式表面、高斯泼溅重建和多视图光度立体等多类方法上开展实验，实现面向采集条件的评估。  
实验表明Martine可分辨亚毫米级重建差异，评估可见表面上最佳Chamfer距离达0.058毫米。</td></tr>
<tr><td>2026-11-05</td><td>eSharp: Diffusion-based Sharp Monocular Metric Event-to-Depth Estimation<br><a href='http://arxiv.org/pdf/2611.08731'>论文</a></td><td>eSharp提出一种面向事件相机的单目度量深度估计框架，旨在克服传统帧式MDE在快速运动和高动态范围场景中的局限。
◆它将预训练扩散模型先验迁移到纯事件输入的度量深度估计中，在真实数据上获得高精度且边界锐利的深度图。
◆它采用跨模态蒸馏，利用与事件相机空间配准的帧相机生成经LiDAR校准的稠密伪标签，缓解真实事件数据集仅含稀疏LiDAR真值导致的稠密监督难题。
◆实验表明其在度量深度精度和空间保真度上优于现有事件到深度基线，并证明扩散模型可作为事件驱动三维感知的有力基础。
该工作将扩散先验、跨模态蒸馏与事件感知相结合，为资源受限条件下的鲁棒深度感知提供了新路线。</td></tr>
<tr><td>2026-11-05</td><td>SLA: Scaling Spatial-Language-Action Model via Continual Pre-training<br><a href='http://arxiv.org/pdf/2611.08373'>论文</a></td><td>SLA的核心贡献是将空间理解作为可迁移的基础模型能力，通过持续预训练规模化隐式空间对齐，并在下游后训练中保持该能力。
◆ 以预训练pi05策略为初始化，联合优化动作预测与中间视觉嵌入对冻结3D感知模型空间表示的对齐。
◆ 构建并统一异构机器人数据集，支持跨多种本体、任务和场景的空间学习。
◆ 引入特征依赖门，自适应聚合多个VLA层的视觉嵌入以进行空间监督。
◆ 教师模型利用部分可用深度、相机标定和RGB观测，有效利用异构几何标注。
◆ 采用概率状态丢弃鼓励依赖视觉线索并缓解轨迹过拟合，且所有辅助组件仅训练使用，保留原推理架构并复用预训练权重。</td></tr>
<tr><td>2026-11-05</td><td>Kinematic Hypothesis Context: Embodiment-Conditioned Learned Video Coding for Bandwidth-Limited Robot Policy Uplinks<br><a href='http://arxiv.org/pdf/2611.07411'>论文</a></td><td>本文提出运动学假设上下文，一种由关节状态、机器人模型和相机标定在两端零速率构建的条件信号，用于带宽受限的机器人策略上行视频编码。  
◆ 利用自运动单应、各链路机器人重投影、末端执行器平面和背景记忆将上一帧重建变换为假设，条件化学习视频编解码器。  
◆ 理论证明仅历史与全局姿态条件在有限感受野和大运动下无法获取该信息，并揭示编码增益在策略成功悬崖处转化为任务增益。  
◆ 在LIBERO上较容量匹配历史条件编解码器节省23.9%码率，较x264、x265、SVT-AV1节省40-56%，等动作偏差下较DCVC-RT少23.2%比特。  
闭环等码率下OpenVLA-OFT成功率从22.8%近倍增至43.1%，pi_0.5从55.5%升至77.4%，且丢包下增益更大并跨编解码器与真实机器人数据迁移。</td></tr>
<tr><td>2026-11-04</td><td>Scale Anchoring via Implicit Semantics and Sequence-Consistent Loop Closure for VGGT-Based SLAM<br><a href='http://arxiv.org/pdf/2611.06308'>论文</a></td><td>本文扩展VGGT-SLAM 2.0，提出固定根尺度锚定与短序列辅助直接回环连接，以缓解子图尺度漂移和跨子图测量不一致。
◆利用SALAD选择初始子图与合格新子图间的图像对，并通过联合VGGT推理的隐式语义几何线索提供仅尺度锚定，同时保留原重叠链。
◆采用邻接图像对进行一致性检查与平移尺度对齐，使每个接受候选在已有中心帧节点间贡献一个鲁棒Sim(3)因子，且无需辅助回环子图。
◆引入短序列检查审计回环候选，可额外拒绝视觉重叠但不一致的图像对，并揭示候选验证的局限。
◆在17个序列上验证，9个TUM序列平均Sim(3) ATE由0.1018降至0.0451米，且锚定提升全部7个无回环模块消融。
◆在3个Clio场景的固定回环比较中，直接连接流程优于所测试的辅助子图流程，并区分了长程尺度锚定与回环连接选择的独立收益。</td></tr>
<tr><td>2026-11-03</td><td>MiCaDe: Online LiDAR-Camera Miscalibration Change Detection for Autonomous Driving<br><a href='http://arxiv.org/pdf/2611.04912'>论文</a> | <a href='https://github.com/CarloSgaravatti/MiCaDe'>代码</a></td><td>本文提出面向自动驾驶的在线LiDAR-相机外参标定漂移检测方法MiCaDe，将标定失效检测建模为序贯变化检测问题，无需标定靶标或修改感知栈。
◆ 核心洞察是标定正确时标准目标检测器输出的3D与2D边界框应保持跨模态几何一致性，据此构造对易外参漂移敏感的一致性指标。
◆ 通过跨模态检测匹配生成几何一致性度量，并按固定大小批次聚合，与参考分布比较得到似然流，再交由变化点模型CPM在线监控。
◆ CPM随时间累积统计证据，可检测原本难以发现的细微漂移，同时保持低误报率和可忽略的计算开销。
在多个长序列数据集及物理诱导失准的真实数据上验证了多场景可靠检测，并开源代码。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vlm'>Robot VLM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-17</td><td>Spool: Low-Latency Streaming Inference for Hybrid Vision-Language Models<br><a href='http://arxiv.org/pdf/2611.23228'>论文</a></td><td>论文针对混合视觉语言模型在滑动窗口视频推理中，循环层将历史帧压缩为共享状态、过期旧帧通常需重放整个窗口的问题，提出无需训练的Spool框架。其核心是利用循环状态更新对状态仿射且系数依赖输入的性质，把每帧影响表示为可结合组合的状态变换。
◆缓存逐帧状态变换，并随窗口推进高效组合，从而无需重放骨干网络即可从各循环层状态中移除过期帧。
◆实现层内精确移除，同时指出类似注意力KV驱逐，过期帧仍可能通过前层缓存输入保留残余影响。
◆设计专用数据结构和GPU内核，降低变换缓存与组合开销。
实验在5个开源混合VLM和4个视频推理基准的20项测试中均取得最低p95首token时延，较两个vLLM基线中较快者几何平均降低6.6倍，并平均提升2.3个百分点准确率。</td></tr>
<tr><td>2026-11-17</td><td>VLM-guided Grounding Expert for Generalised Referring Expression Comprehension<br><a href='http://arxiv.org/pdf/2611.22625'>论文</a></td><td>现有grounding专家对指令变化敏感，生成式VLM难以完整恢复和拒绝缺失目标，两者能力互补。为此提出VGE，将冻结VLM与可训练grounding专家通过层间联合注意力和文本条件实例评分相结合。在三个数据集五个测试划分上平均F1最高，各指令条件差异不超过1.2个百分点；机器人场景下跨变体及无/单/多目标F1最优，且比同VLM基线加速5.3–13.0倍。
◆通过层间联合注意力和文本条件实例评分，实现冻结VLM与可训练grounding专家的深度耦合。
◆利用VLM多模态理解指导对象查询细化和候选选择，同时保留grounding专家的直接边界框预测能力。
◆在机器人场景中显著提升对指令改写、额外上下文及无目标/单目标/多目标的泛化鲁棒性。</td></tr>
<tr><td>2026-11-17</td><td>CueClash: Frontier Vision-Language Models Judge 3-D Relations Close to the Picture Plane<br><a href='http://arxiv.org/pdf/2611.22180'>论文</a></td><td>论文提出CueClash，用渲染场景将五类3-D关系的图像2-D线索与地面布局分离，并让线索正确与错误各占一半，以检验视觉语言模型是否依赖捷径。
◆构建可量化“捷径差距”的诊断基准，揭示Claude Opus 5.5、GPT-5.5、Gemini 3.6 Flash在低推理努力下存在+18至+37个百分点的2-D线索偏差。
◆证明给定地面坐标和关系定义后模型准确率达99%至100%，而像素与相机深度可缩小部分物体差距，定位失败关键在“从图片到布局”的转换。
◆分析模型俯视地图，发现其多保留深度顺序却压缩深度，且不同模型纠正方式不同，Opus 5.5接近人类观察者的深度校正。
◆在CV-Bench误导性2-D线索照片上复现准确率下降，并发现开源模型虽将布局信息传入语言模型，但其地图丢失大量信息。</td></tr>
<tr><td>2026-11-17</td><td>ReLAP: Latent Action Pretraining through Recurrent Video Prediction in JEPA Space<br><a href='http://arxiv.org/pdf/2611.22077'>论文</a></td><td>ReLAP提出一种无动作标注的潜在动作预训练框架，在冻结JEPA表征空间中耦合局部转移学习与循环多步视频预测，以学习紧凑、时间连贯且可迁移的机器人控制表征。
◆ 用共享逆动力学模型从相邻观测推断连续潜在动作，并让潜世界模型循环预测未来JEPA特征，使后续预测成为下一步上下文，误差经rollout反传以约束早期潜在动作。
◆ 将所学表征通过冻结逆教师潜在蒸馏和冻结世界模型循环未来特征预测两项互补目标迁移到视觉语言模型，再用动作流匹配适配机器人演示。
◆ 部署时移除显式潜在动作和世界模型分支，由微调VLM直接预测物理动作，从而降低推理复杂度。
在仅11M预训练样本和1.06B可训练参数下，ReLAP在LIBERO达97.9%、零样本LIBERO-Plus达70.0%，并在LARY基准的平均回归误差和平均分类准确率上均列第二，验证了循环无动作潜在动作预训练的有效性。</td></tr>
<tr><td>2026-11-16</td><td>ScaleVLA: Scaling Vision-Language-Action Models to 552 Billion Parameters<br><a href='http://arxiv.org/pdf/2611.21607'>论文</a></td><td>ScaleVLA将552B参数的DeepSeek-V4.1-Flash前沿VLM与可训练动作DiT连接，并在统一训练设置下系统比较2B至552B的VLM骨干对机器人策略的影响。
◆ 构建了前沿规模VLM作为机器人策略表征基础的系统性验证框架，覆盖样本效率、泛化和精细操作三类核心能力。
◆ 样本效率上，仅用10条演示达到87.8%成功率，超过2B骨干用50条演示的85.6%。
◆ 泛化与精细操作上，LIBERO-PRO成功率达45.1%（小骨干最高31.3%），真实充电器插入从4/10提升到9/10，增益集中在接触敏感对齐。
尽管规模达552B，ScaleVLA每个动作块的中位延迟仅为216 ms。
结果表明前沿VLM不仅可作为推理代理，也能成为高效、可泛化的机器人策略表示基础。</td></tr>
<tr><td>2026-11-16</td><td>Seeing Isn&#x27;t Resolving: Visual and Linguistic Disambiguation with Conversational Grounding<br><a href='http://arxiv.org/pdf/2611.21183'>论文</a></td><td>本文针对真实场景中视觉指代常伴随上下文不确定性的问题，构建了日文模糊视觉grounding对话基准JAG-D。该基准包含覆盖视觉与语言歧义类型的人机多模态对话交互，并用于评估先进视觉语言模型的歧义识别与消解能力。
◆ 提出JAG-D基准，将视觉歧义和语言歧义纳入统一的人机多模态对话评估。
◆ 系统比较视觉歧义与语言歧义在对话上下文grounding中的解决表现，揭示二者差异。
◆ 发现对话上下文能显著提升语言歧义消解，尤其对日语零代词指代效果突出。
◆ 进一步区分并分析grounding提升来自对话语义内容还是会话结构。</td></tr>
<tr><td>2026-11-16</td><td>STA: A Split Temporal Adversary Method for Evaluating Robustness of Multimodal RL-based Driving Policies<br><a href='http://arxiv.org/pdf/2611.20765'>论文</a></td><td>论文针对多模态强化学习驾驶策略的跨模态时序一致性漏洞，提出分裂时序对抗方法STA。该方法将多模态时序攻击建模为统一决策过程，在策略感知和预算约束下联合优化攻击时机与模态选择。  
◆提出统一多模态时序扰动机制，通过历史状态延迟观测实现攻击，无需模态特定噪声，提升通用性与真实性。  
◆提出分裂多模态对抗决策机制，联合优化攻击时机和模态选择，并利用受害者策略的干净动作识别敏感决策模式。  
论文还给出诱导分布偏移的理论分析和模态选择原则。  
CARLA实验表明，STA对PPO的碰撞率超过最强基线两倍且攻击尝试少17.8%，并可泛化到VLM驾驶策略，揭示时序鲁棒性对安全自动驾驶至关重要。</td></tr>
<tr><td>2026-11-16</td><td>A Generalizable Approach to Safety-Aware Robotic Behavior Planning with an Explicit Constraint Space<br><a href='http://arxiv.org/pdf/2611.18026'>论文</a></td><td>本文提出一种面向桌面机器人操作的安全感知行为规划框架，核心是以显式约束空间存储可复用的文本安全规则，使安全知识可表示、可选择、可更新。
◆构建显式约束空间，将任务相关安全规则外化为可复用文本知识，而非仅依赖模型隐式安全能力。
◆将约束选择从语义相似度检索转化为任务与环境条件化的适用性学习，用轻量查询条件双塔模型为当前场景选取适用约束。
◆引入多模态安全检查器评估生成的原语计划，重建完整适用约束集并提供纠正性反馈，以处理错误约束选择和未见危险。
◆利用经校验的检查反馈进行测试时约束适用性适应，并通过LoRA参数高效适应安全检查器，同时将新约束纳入约束空间。
该框架整合显式安全知识表示、上下文感知约束选择、纠正性安全检查和测试时知识适应，提升了安全行为规划的可泛化性。</td></tr>
<tr><td>2026-11-15</td><td>The Flip Test: Video World Models Fail to Learn the World State<br><a href='http://arxiv.org/pdf/2611.19822'>论文</a></td><td>本文提出FlipTest，用反事实扰动检验视频世界模型是否真正跟踪决定未来的世界状态，而非仅生成看似合理的视频。
◆构建视觉最小对、匹配控制和密集扫描三级递进测试，覆盖10个模拟与15个真实任务的1680个初始帧。
◆设计匹配控制与密集扫描，要求预测只在真实未来改变处翻转，并能精确定位状态边界。
◆系统评测11个视频世界模型，发现全部失败，最佳配对准确率仅18.3%，低于随机猜测的25%，且在无变化步上同样翻转、扫描响应平坦。
◆对比显示视觉语言模型具有选择性并呈近S形曲线，编码智能体可逼近真实边界，说明判别信息就在帧内而视频模型未利用。
论文据此呼吁超越纯视频预测，下一帧预测还应识别控制未来动力学的因果状态。</td></tr>
<tr><td>2026-11-14</td><td>SuperGlance: Driving at a Glance with a Vision-Language Model<br><a href='http://arxiv.org/pdf/2611.19138'>论文</a></td><td>SuperGlance的核心贡献是证明VLM在输出首个token前的隐藏状态已足以驾驶并回答视觉问题，从而把decoder-only VLM转为encoder式驾驶策略，实现一次前向的System 1规划。
◆利用VLM隐藏状态加线性头对固定5,273条候选轨迹打分，避免逐步解码式规划。
◆固定候选集使奖励可离线计算，监督目标按奖励加权，强化学习直接最大化精确期望奖励。
◆训练前后用多选问答保持VLM视觉能力，并用双选项顺序约束防捷径、KL项防阶段漂移。
其视觉问答与基座VLM解码相当，规划仅需84 ms GPU时间，比Qwen-Drive-1.0快6倍，并在NAVSIM、PAI-AV和WOD-E2E上至少不差。
在AlpaSim闭环中，每造成一次责任事故的公里数在300 ms延迟内保持，计入GPU时间延迟后相对Qwen-Drive-1.0的领先从2.8倍增至3.9倍。</td></tr>
<tr><td>2026-11-13</td><td>Bring Back Language to Actions: Restoring VLM capabilities in VLA Models via Parameter Merging<br><a href='http://arxiv.org/pdf/2611.18891'>论文</a></td><td>本文针对VLA模型在机器人示教数据上微调VLM后引发灾难性遗忘、损害原VLM语义与视觉 grounding 能力的问题，提出一种无需重新训练任何模型的参数合并方案。
◆ 从VLM与其VLA衍生模型间提取任务向量，并通过奇异值分解将其拆分为多个分量。
◆ 为每个分量学习标量混合系数，以控制保留多少VLA适配信息，并联合优化动作预测与视觉语言能力。
◆ 在无需额外训练的前提下合并VLM与VLA参数，使模型同时保持动作预测和视觉语言理解性能。
实验表明，合并模型在动作预测与视觉语言能力两方面同时表现良好，并持续优于已有参数合并基线。</td></tr>
<tr><td>2026-11-13</td><td>RescueVLM: Model-Agnostic Vision-Language Framework for Rescue Drone Imagery<br><a href='http://arxiv.org/pdf/2611.18813'>论文</a></td><td>RescueVLM针对救援无人机单次任务影像过多、人工筛查心理成本高，以及云端VLM受GDPR/BOS限制、专用检测器易老化且重训认证资源不足的问题，提出开源、免训练、模型无关的影像分诊框架。
◆ 基于SketchVLM与开放权重通用VLM实现全本地部署，并可通过下拉选择切换新模型，使分诊质量随底层模型升级而提升。
◆ 将任务知识置于提示词和输出契约而非训练权重中，实现免训练、模型无关和快速适配。
◆ 单条自然语言查询即可返回排序短名单、逐图理由、可编辑SVG覆盖标注及命中GPS地图。
◆ 在德国消防队三次真实部署和一次实火演习数据上定性验证，可将整次调查任务压缩为少量标注帧供指挥员快速审阅。
总体而言，该工作为受限网络和资源条件下的救援影像智能分诊提供了可落地、可持续升级的开源方案。</td></tr>
<tr><td>2026-11-13</td><td>Vision-Language-Action Models: A Life-Cycle Survey of Design, Training and Deployment<br><a href='http://arxiv.org/pdf/2611.18372'>论文</a></td><td>本文系统综述2022年12月至2026年10月的88项VLA研究，覆盖操作、导航、人形控制、世界动作模型与评测。作者提出贯穿设计、训练、部署的生命周期七轴框架，包括输入与记忆、架构、动作输出、中间预测、预训练数据、后训练和实时执行。基于22个模型的训练数据、参数量、推理速度与硬件分析，文章归纳出数据来源多元化、模型规模两极分化、通用VLA兴起三大趋势。  
◆提出设计—训练—部署全生命周期七轴统一分析框架，并系统比较22个模型的关键训练与部署指标。  
◆比较VLA与世界动作模型，揭示部分基准高分模型在物体或相机轻微移动时失效，指出真实鲁棒性缺口。</td></tr>
<tr><td>2026-11-13</td><td>VLAN: Vision-Language Accessible Navigation<br><a href='http://arxiv.org/pdf/2611.18346'>论文</a> | <a href='https://github.com/InSAI-Lab/VLAN'>代码</a></td><td>VLAN针对现有导航基准以固定有限本体评估可通行性、忽视不同用户与机器人可达性差异的问题，提出面向视觉语言可达性导航的新基准。该基准包含1000个场景、2万条轨迹和16万关键帧，覆盖多样光照、环境、语义与路径几何，并为腿式与轮式智能体（含人形、四足机器人及视障/行动障碍人群）提供本体特定动作与可达性特征。
◆构建大规模、多场景、多具身用户的可达性导航基准与开放数据。
◆提供本体特定动作和细粒度可达性特征，并将障碍与可达标签划分为Passable、Bypass、HighRisk和Blocked。
◆设计目标达成、碰撞感知与可达性对齐指标，同时评估物理安全和用户约束匹配。
◆基准测试揭示现代视觉语言模型难以跨用户画像一致调整障碍相关性、路径选择和安全标准。</td></tr>
<tr><td>2026-11-13</td><td>Objectives as Policies: Vision-Language Model Cost Programs for Contact-Rich Manipulation<br><a href='http://arxiv.org/pdf/2611.18298'>论文</a> | <a href='https://zihaolu001.github.io/oap-project/'>代码</a></td><td>本文提出Objectives as Policies（OaP）框架，将预训练视觉语言模型与共享采样型模型预测控制器连接起来。其核心是用可编辑目标程序作为任务表示，把任务分解为多个阶段，并组合成本库中的运行成本、终端成本与阶段完成条件。VLM根据自然语言指令和场景观测，通过real-to-sim数字孪生生成程序，并依据MPC rollout迭代更新后在真实世界部署。
◆提出可编辑目标程序作为VLM与MPC之间的桥梁，使语义推理能够转化为可执行的物理规划目标。
◆构建基于real-to-sim数字孪生的VLM-MPC闭环，实现仿真中生成、评估和迭代优化后再迁移真机。
◆在仿真和真实世界的四个接触丰富桌面操作任务上验证，性能优于强基线。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-visual-semantic-recognition'>Robot Visual Semantic Recognition</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-10</td><td>HiPFuse: Real-Time LiDAR Semantic Segmentation for Robotic Perception on Edge Devices<br><a href='http://arxiv.org/pdf/2611.14025'>论文</a> | <a href='https://github.com/haiyang2022/HiPFuse'>代码</a></td><td>本文提出HiPFuse，一种面向边缘设备机器人实时感知的点-BEV融合LiDAR语义分割框架，在单帧扫描中兼顾点级细节与二维空间上下文。
◆ 设计跨水平尺度的点与高度划分BEV特征交换机制，减少BEV列内不同标签表面混合。
◆ 采用固定高度分配保留独立垂直聚合组，并用同一3D单元目标对初始BEV特征进行辅助监督。
◆ 引入双尺度BEV上下文模块，从更粗网格获取更广空间上下文。
在SemanticKITTI和MCD上分别达到63.7%和62.5% mIoU，Jetson AGX Orin上达14.2和22.4 FPS，超过10 Hz扫描率，并验证室内适用性。
仅替换固定机器人系统中的基线语义前端，即可使两个室外序列ATE RMSE平均降低10.6%，SemanticKITTI闭环召回提升8.7个百分点，语义地图道路标注更连续。</td></tr>
<tr><td>2026-11-06</td><td>ATLAS: A Multi-Procedure Benchmark and Context-Aware Model for Surgical Anatomy Segmentation<br><a href='http://arxiv.org/pdf/2611.10182'>论文</a> | <a href='https://github.com/TimJaspers0801/ATLAS'>代码</a></td><td>本文针对微创手术解剖识别受限于小型单术式数据集和自然场景分割方法的问题，提出跨术式数据集与上下文感知视频分割模型。
◆ 构建ATLAS-120k数据集：含100段手术视频、121,018帧、14种腹腔镜与机器人辅助术式及41类，标注流程融合人工标注、跟踪传播和外科医生审核。
◆ 提出ATLAS模型：基于域内基础模型嵌入，加入术式与手术阶段上下文查询，并用帧间查询传播形成短期记忆。
实验表明ATLAS在分割精度和时序一致性上优于自然图像及域内基础模型，ViT-L达Dice 0.70且76.2 FPS实时；消融验证上下文查询提升精度、查询传播提升时序一致性。
它还能零样本在CholecSeg8k上匹配专用模型，并在AutoLaparo阶段识别上优于SurgeNet初始化，相关权重、标注和工具已开源。</td></tr>
<tr><td>2026-11-03</td><td>Role-based Effectiveness of an Epistemic Uncertainty Estimate in Training Models for Semantic Segmentation of 3D LiDAR Point Clouds<br><a href='http://arxiv.org/pdf/2611.05569'>论文</a></td><td>本文系统研究认知不确定性估计在3D LiDAR点云语义分割训练中的多重作用，而不仅将其用于提升精度。
◆首次将显式建模的认知不确定性同时作为额外输入特征和逐样本置信权重引入分割训练，比较其不同角色效果。
◆在四个跨机载与移动采集的大规模LiDAR基准上，采用空间不相交训练测试划分，并对比PointNet++、RandLA-Net及其不确定性增强版本进行统一评估。
◆实验表明不确定性感知建模可提升平均IoU，并恢复基线完全漏判的少数类。
◆在一半配置中，该方法还改善了预测误差与估计不确定性之间的对齐，以Patch Accuracy versus Patch Uncertainty衡量。
总体贡献是揭示不确定性可作为分割流程中的多角色信息，而不仅是精度提升装置。</td></tr>
<tr><td>2026-10-29</td><td>LiDAR-SHIELD: A Fully Dockerized Adversarial Robustness Assessment Framework for LiDAR-Based 3D Perception Models<br><a href='http://arxiv.org/pdf/2610.39848'>论文</a> | <a href='https://github.com/alexandrosgk/LiDAR-shield'>代码</a></td><td>LiDAR-SHIELD是面向LiDAR 3D感知模型的全Docker化统一对抗鲁棒性评估框架，用于部署前系统压力测试。
◆ 它逆转传统流程，不把目标模型装入工具包，而通过/info、/forward、/gradient三个轻量HTTP端点暴露任意模型。
◆ 新模型或数据集接入仅需一个加载函数或适配器，显著降低模型特定集成与环境重建成本。
◆ 同一引擎-服务协议同时支持3D语义分割和3D目标检测，并可覆盖异构LiDAR骨干。
◆ 集成任务感知的先进攻击：分割用PGD和Square Attack，检测用点扰动、点移除、点注入和LiDAttack。
◆ 全Docker化统一碎片化攻击实现，提升可复现性与部署便利性，并系统暴露角落案例和漏洞，代码已开源。</td></tr>
<tr><td>2026-10-28</td><td>Safe and Fuel-Efficient Motion Planning for Lunar Propulsive Drones<br><a href='http://arxiv.org/pdf/2610.22225'>论文</a></td><td>本文提出面向月球推进无人机的自主运动规划框架，通过视觉引导最优控制在指定航点间完成安全且省燃料的跳跃。  
◆ 统一融合全局航点规划、抛物线跳跃最优控制与自主改向着陆，兼顾任务连续性与安全性。  
◆ 构建面向月面航拍图像的定制语义分割模型，用于识别障碍并评估候选着陆点安全性。  
◆ 提出快速计算可达地形的方法，以判断航点或着陆点是否安全可达。  
◆ 采用模型预测控制鲁棒跟踪跳跃轨迹，引导无人机飞向安全着陆点并降低跟踪误差。  
在高保真月球仿真中，该框架生成了安全、省燃料且可快速低误差跟踪的跳跃轨迹。</td></tr>
<tr><td>2026-10-22</td><td>RaSFNet: Ray-aligned and Scan-aware Fusion Network for LiDAR Semantic Segmentation<br><a href='http://arxiv.org/pdf/2610.31186'>论文</a></td><td>针对投影式LiDAR语义分割中多点聚合遮蔽几何差异、跨扫描区域空间关系建模不足及点-投影特征交互易混淆不同距离信息的问题，论文提出融合点云几何与LiDAR扫描特性的RaSFNet。
◆ 提出射线对齐几何分布编码RAGDE，在射线对齐坐标系中刻画每个视锥内的点分布，增强几何差异表达。
◆ 设计扫描拓扑感知Mamba模块STAM，按LiDAR方位角采样模式组织视锥特征并捕获跨扫描区域的长程依赖。
◆ 提出距离约束的点-视锥融合机制RCPFF，利用共享距离信息引导点特征与视锥特征交换并保持空间对应。
RaSFNet在SemanticKITTI和nuScenes验证集上分别取得70.2%和77.7%的mIoU，表现出有竞争力的分割性能。</td></tr>
<tr><td>2026-10-22</td><td>RangeNav: Task-Aligned LiDAR Range-Image Pretraining for Robot Navigation<br><a href='http://arxiv.org/pdf/2610.29845'>论文</a> | <a href='https://rangenav.github.io/'>代码</a></td><td>本文提出RangeNav，一个仅183k参数、完全基于合成数据预训练的紧凑型LiDAR距离图像编码器，用于提升机器人在密集人群和杂乱场景中的360度导航感知与策略学习效率。
◆ 采用各向异性卷积和循环填充，专门处理距离图像的极端长宽比与方位接缝问题。
◆ 设计导航对齐的预训练目标，联合距离重建、语义分割和鸟瞰图预测，再将编码器冻结用于强化学习策略。
◆ 以轻量化架构支持大规模并行仿真训练，并具备从仿真到真实机器人部署的零样本迁移能力。
仿真实验表明，加入语义和BEV监督较仅重建基线在程序生成训练环境和分布外真实测试环境中分别平均提升32.03和23.73个百分点。
在Unitree B2-W四足机器人上的零样本真实部署显示，其能在密集人群、低光和施工区中稳健导航，优于有限视场深度策略。</td></tr>
<tr><td>2026-10-21</td><td>AOV-GS: Active Open-Vocabulary Semantic Mapping with 3D Gaussian Splatting<br><a href='http://arxiv.org/pdf/2610.29374'>论文</a> | <a href='https://github.com/OptimusFaber/AOV-GS'>代码</a></td><td>AOV-GS面向人本环境机器人建图，提出无需人工掩码和闭集类别的主动开放词汇语义建图系统，兼顾几何导航与开放词汇查询。
◆ 利用冻结SAM实例分割与CLIP掩码嵌入计算语义新颖度，对几何候选视角重排序，使探索偏向语义信息丰富区域。
◆ 在粗探索和建图全程复用冻结SAM/CLIP提供实例掩码与语言对齐嵌入，避免监督语义分割和手工标注。
◆ 离线将轻量场景特定语言场直接拟合到采集的CLIP嵌入而非人工掩码，从而支持新视角开放词汇文本查询分割。
实验在Replica和Matterport3D上以相同SAM-CLIP感知栈比较，语言场mIoU分别提升1.3和1.8个百分点，CorrCLIP下Replica达35.6%，同时新视角PSNR相当且Replica深度L1改善。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vpr'>Robot VPR</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-16</td><td>Beyond Appearance: Where Forest Visual Place Recognition Actually Fails<br><a href='http://arxiv.org/pdf/2611.21996'>论文</a></td><td>本文在WildCross基准上以MegaLoc为外观基线，系统评估时序、语言、结构与几何上下文能否超越纯外观森林视觉位置识别，并分析各表示的失效边界。
◆ 构建统一评估框架，联合考察score/descriptor序列匹配、视觉语言描述与重排、场景图及LiDAR深度茎干图等多类上下文表示。
◆ 发现同向重访中score-space序列匹配在高精度区显著优于单帧基线，100%精度下召回率由50.9%升至71.6%，而descriptor-space反而降至36.5%。
◆ 揭示其余上下文缺乏稳定增益：描述地点判别力有限、重排受初始候选表约束、茎干图即使有LiDAR深度仍较弱。
结论表明森林VPR的瓶颈不仅在外观相似，更在于上下文表示的判别力与候选覆盖不足。</td></tr>
<tr><td>2026-11-14</td><td>Breaking Déjà Vu: Independent Auditing of Visual Place Recognition through Vision-Language Reasoning<br><a href='http://arxiv.org/pdf/2607.12818'>论文</a></td><td>本文针对真实部署中VPR匹配阈值依赖标注验证数据、环境变化下不可靠的问题，提出独立的后检索验证框架Visual Place Recognition Auditing。
◆ 将视觉语言模型引入VPR验证，通过联合推理查询图像与候选图像实现实例级匹配审核，而非依赖传统置信度或固定阈值。
◆ 该方法无需架构特定置信度、数据集相关阈值或部署环境先验知识，可作为独立模块对现有VPR方法进行事后验证。
◆ 在六个基准数据集上结合五种先进VPR方法和四种视觉语言模型进行系统评估。
结果显示，该方法相较先进方法平均提升recall@1 13.6%，将误接受率降至12%，同时保持精度高于95%、覆盖率高于75%。
这提升了环境变化和安全关键场景下VPR部署的可靠性。</td></tr>
<tr><td>2026-11-03</td><td>Sparse Anchors for Visual Multi-Session Registration in Changing Environments<br><a href='http://arxiv.org/pdf/2611.05084'>论文</a></td><td>论文面向变化环境下的视觉多会话注册，将新查询会话轨迹对齐到已有参考地图，解决显著视觉与结构变化导致跨会话对应仅部分可用的问题。  
◆提出以稀疏但可靠的绝对位姿锚点结合会话内相对位姿约束，通过鲁棒位姿图优化完成整条查询轨迹的注册。  
◆利用视觉地点识别、局部特征匹配和几何验证生成绝对对齐假设，并用序列一致性剔除不一致假设以保留锚点。  
◆采用高斯特征场上的特征度量对齐对锚点进行细化，提高绝对约束精度。  
◆在HILTI26的15个跨会话实验上验证，1米召回率达94.4%、5米召回率达100.0%，优于独立图像定位和直接SfM几何注册。  
总体贡献是证明即使仅部分查询会话存在可靠跨会话对应，稀疏可靠锚点也能实现准确且完整的轨迹注册。</td></tr>
<tr><td>2026-10-26</td><td>VPR-Space: A Benchmark for Visual Place Recognition in Space Analog Domains<br><a href='http://arxiv.org/pdf/2610.35642'>论文</a> | <a href='https://github.com/rfechner/VPR-Space}$'>代码</a></td><td>论文提出VPR-Space，一个面向地外表面及太空模拟域的视觉地点识别新基准，用于评估VPR在特征贫乏环境中的能力。
◆收集了16个基于太空模拟域现有数据的VPR数据库-查询数据集，覆盖环境、视角变化和光照条件等多类挑战。
◆提出一种面向下游SLAM价值的VPR真值生成方法，利用先进相对位姿估计器集成性能构建GT矩阵，替代固定位姿阈值判定。
◆系统评估了9种先进VPR方法，结果显示现有方法仍有较大提升空间，并为未来研究指明方向。
该工作还公开了数据集预发布版本，为月球或火星等极端环境下的VPR与SLAM研究提供评测基础。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5387</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4884</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2493</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1667</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1632</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1544</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1388</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1322</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1141</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>1117</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>955</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>820</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>786</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>754</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>748</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>736</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>704</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>681</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>639</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>633</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>626</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>597</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>573</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>550</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>516</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>482</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>470</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>376</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>350</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>282</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>275</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>260</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>245</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>234</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>231</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>223</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>222</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>216</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>155</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>147</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>124</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2891</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1686</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1371</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1099</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1065</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>889</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>715</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>674</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>671</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>624</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>618</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>579</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>579</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>572</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>555</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>525</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>522</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>466</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>458</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>455</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>352</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>334</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>310</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>305</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>291</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>278</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>259</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>246</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>224</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>208</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>203</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>188</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>177</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>171</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>169</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>160</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>157</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>105</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/eth_supermegabot'>eth_supermegabot</a></td><td>102</td><td>Instructions for ETH center for robotics summer sc</td></tr>
<tr><td><a href='https://github.com/ethz-asl/3d_vsg'>3d_vsg</a></td><td>102</td><td>3D可变场景图，用于长期语义场景变化预测。</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.11.18
