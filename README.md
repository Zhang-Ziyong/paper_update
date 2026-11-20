# 计算机视觉领域最新论文 (2026.11.20)

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
<tr><td>2026-11-19</td><td>Stereo Visual Odometry with In-the-Loop Geometric Feed-Forward Models Towards Dense Metric Mapping<br><a href='http://arxiv.org/pdf/2611.25445'>论文</a></td><td>本文提出一种立体视觉里程计框架，将几何前馈模型的稠密深度预测与基于因子图的视觉里程计紧耦合，实现准确定位和稠密度量建图。
◆利用立体与时序多视图观测得到的稀疏但可靠度量几何来标定稠密深度预测，而非直接将预测条件于可能含噪的立体深度，并在每个局部子图内对所有关键帧联合估计尺度-平移变换，获得度量一致的稠密深度。
◆设计分层因子图架构：局部层通过滑动窗口优化估计高频相机位姿和多视图精化三维路标，仅对选定关键帧生成稠密预测，并用SE(3)广义ICP在子图内配准。
◆在连续子图间利用共享几何进行Sim(3)对齐，校正残余尺度不一致，并将子图内与子图间约束统一纳入全局因子图，得到一致轨迹和稠密度量重建。
◆在公开和自采数据集上，该方法定位精度与几何及学习型基线具有竞争力，同时提供准确稠密度量重建，并提升了对学习深度预测失败的鲁棒性。</td></tr>
<tr><td>2026-11-18</td><td>Accord: Universal Online Metric Localization and Dense Mapping from one Camera and an IMU<br><a href='http://arxiv.org/pdf/2611.25279'>论文</a></td><td>Accord提出一种仅依赖任意单相机与IMU的在线稠密度量建图系统，解决VIO度量位姿但几何稀疏、前馈深度稠密却缺乏度量尺度的问题。
◆ 以VIO滤波器输出的度量位姿为条件，用深度基础模型对短关键帧窗口预测深度，并通过因子图融合子图。
◆ 提出多视图一致性机制：将每个关键帧窗口锚定到由滤波器位姿三角化的度量3D点，并利用共视图像间双向稠密深度一致性估计与校正逐图像尺度误差，同时保持锚点建立的度量尺度。
◆ 引入上下文关键帧改善深度预测，并将所得子图在因子图中融合以构建在线稠密度量地图。
在五个公开相机-IMU设置及新Phone-rig/GoPro数据集上，单一映射配置无需逐数据集调参、仅用自身轨迹对齐，即在5cm平均F-score上稳定取得最佳或次佳。
系统与手机架数据集开源，便于社区研究。</td></tr>
<tr><td>2026-11-18</td><td>Induction Head Origins of SLAM-ASR Speech Recognition Models<br><a href='http://arxiv.org/pdf/2611.24721'>论文</a></td><td>论文探究SLAM-ASR为何仅靠小型映射与冻结语言模型即可实现有竞争力的语音识别，并揭示其依赖的具体内部结构。  
◆ 首次表明SLAM-ASR依赖冻结语言模型中的归纳头，即文本中复制重复词序列的注意力头，也负责将语音嵌入映射为转录词元。  
◆ 发现成对注意力头形成受约束的差分注意力，可抵消注意力噪声并锐化对前一生成词的关注。  
◆ 展示归纳头可用于改善噪声音频条件下的转录质量。  
这些发现为SLAM-ASR的工作机制提供了可解释证据，并为噪声鲁棒语音识别提供了利用归纳头的改进思路。</td></tr>
<tr><td>2026-11-18</td><td>Proprioceptive Simultaneous Base and Terrain Elevation Estimation for Legged Robot Locomotion<br><a href='http://arxiv.org/pdf/2611.24310'>论文</a></td><td>论文针对视觉退化环境下腿部机器人仅靠本体感知时全球位置与偏航不可观、垂直漂移危害大的问题，提出将地形本身视为持续的本体感知地标，用每次足步高度测量锚定垂直轴。作者提出实时开源框架SBEE，将用于浮动基估计的左不变扩展卡尔曼滤波与栅格高程图双向耦合，形成以地形高程替代地标的类SLAM闭环。  
◆ 把稳定足接触生成的不确定性感知高度样本插入高程图，并将已映射单元反馈为不确定性加权垂直伪测量，类似回环约束。  
◆ 采用运动学速度测量而非逐腿接触模型增广状态，使LI-EKF状态维数不随腿数增加。  
◆ 实现浮动基估计与高程图的双向耦合，同时估计基座状态和地形高程。  
在MuJoCo四足与双足平台及ANYmal-D GrandTour数据集296米行走中验证，绝对轨迹误差较三种先进本体感知估计器中的最优者降低22.1%。</td></tr>
<tr><td>2026-11-18</td><td>Facet-SLAM: Real-Time Triangle Splatting SLAM<br><a href='http://arxiv.org/pdf/2611.23935'>论文</a> | <a href='https://github.com/edward62740/Facet-SLAM'>代码</a></td><td>Facet-SLAM是首个面向RGB-D相机的实时三角面片splatting SLAM系统，直接构建可三角化为连通网格的表面表示。  
◆将跟踪与建图角色解耦：跟踪器用融合深度设定三角面片质心，并通过GICP将当前帧配准到这些质心，避免依赖过慢的光度跟踪。  
◆在建图端通过变量替换限制优化为非平移更新，防止三角面片被优化推离观测表面而成为不可靠的配准目标。  
◆利用三角面片顶点直接三角化为连通网格，无需额外网格提取或融合阶段，在保持渲染质量的同时提升表面几何精度。  
系统在桌面GPU上约100 FPS、在Jetson AGX Orin上达到传感器帧率，较光度方法快20倍以上，并将Replica上Delaunay网格倒角距离从1.55降至0.86 cm。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-19</td><td>SGAR: Feed-Forward 3D Reconstruction via Sparse Geometry-Guided Attention<br><a href='http://arxiv.org/pdf/2611.26493'>论文</a></td><td>论文针对前馈三维重建中密集全局注意力随视图数平方增长的问题，提出从运动恢复结构视角看多数密集计算并不必要，因为三维结构源于二维几何匹配区域。
◆提出SGAR，用几何相似性引导的稀疏注意力替代密集全局注意力，使每个patch token仅关注其他视图中少量相关token。
◆设计轻量级可学习key选择模块，预测跨视图token的三维邻近关系，从而为稀疏注意力选取几何相关token。
◆该方法具有通用性，可通过微调应用于不同前馈重建模型。
实验表明SGAR在稠密和稀疏方法中速度最快、稀疏方法中最准确，在1000视图下比密集注意力快至多12倍并保持稳定位姿精度，同等时间预算下重建更完整几何。</td></tr>
<tr><td>2026-11-19</td><td>Reference-Twist-Based Velocity-Domain Spatiotemporal Calibration for mmWave Radar, Event Camera, and IMU<br><a href='http://arxiv.org/pdf/2611.26083'>论文</a></td><td>论文针对毫米波雷达、事件相机与IMU跨模态标定中目标、特征、点云或位姿关联难以建立的问题，提出参考twist条件下的速度域时空标定框架。该方法利用刚性套件共享运动，将雷达多普勒、事件法向流和惯性测量回归到同一可信参考体twist，联合估计相对旋转、杆臂、时间偏移及传感器偏置与尺度，无需人工靶标、运动恢复结构或跨模态点云配准。
◆ 将参考体twist作为条件输入而非待标定传感器，建立参考条件化的速度域跨模态标定模型。
◆ 对比联合估计与参考条件估计，推导条件可辨识性、CRLB级协方差和偏差界，并明确条件信息有效的工况。
◆ 利用室内和森林轴分离运动数据系统评估初始化、时间对齐、运动退化、参考输入敏感性和残差一致性。
由于参考不增加物理可观性，估计仍受参考精度、同步、运动激励和投影多样性约束。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-19</td><td>LBW-NPS: A Local Band-Weighted Noise Power Spectrum Loss for Texture-Preserving Low-Dose CT Denoising<br><a href='http://arxiv.org/pdf/2611.25548'>论文</a></td><td>本文提出一种面向低剂量CT去噪的局部频带加权噪声功率谱损失LBW-NPS，在抑制噪声的同时更好地保留参考图像局部纹理。  
◆ 以重叠Hann窗局部patch内谱能量比较替代全局池化谱匹配，缓解区域纹理差异被平均忽略的问题。  
◆ 每个有效patch对三个频带的加权平方对数能量差进行约束，并与L1重建项联合训练。  
◆ 该方法无需组织特异性损失条件，且不改变原有U-Net去噪架构。  
◆ 通过patch尺度消融及肺、软组织、骨区域评估，验证局部频带功率匹配的有效性。  
实验表明，在220张测试切片上，LBW-NPS使64×64评估窗内相关局部谱差距较池化频带加权NPS降低31.9%，PSNR无统计显著变化，并在未参与损失的平均NPS频率和GLCM指标上降低均匀软组织误差。  
因此，其核心贡献是提升区域纹理一致性而不牺牲去噪架构与整体保真度。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-19</td><td>Multiple-Camera Tracking of Rigid Objects<br><a href='http://arxiv.org/pdf/2611.25904'>论文</a></td><td>本文提出一种基于三维模型与图像轮廓对齐的单/多相机刚性物体跟踪方法，通过最小化预测模型点与图像轮廓间的误差，并以视觉伺服闭环方式逐帧更新相机内外参数。
◆系统分析点到点与点到轮廓匹配下的Jacobian矩阵，确定所需最小匹配数及导致秩亏的奇异配置。
◆建立点到点与点到轮廓两类匹配之间的数学联系，并证明后者具有与前者同类的奇异性。
◆研究多相机配置以优化方法鲁棒性，有效应对单相机奇异、坏数据、噪声及缺失数据。
◆用复杂船件和最多三台相机开展大量实验验证方法，并表明该跟踪器可用作相机标定程序。</td></tr>
<tr><td>2026-11-19</td><td>Homeward: No Place Like the Training View<br><a href='http://arxiv.org/pdf/2611.24455'>论文</a></td><td>Homeward提出一种无需训练、即插即用的观测适配器，可将未标定部署相机画面规范化回训练视角，使冻结VLA策略在相机被碰撞、重装或更换后仍能工作。
◆ 通过闭环诊断揭示“理想几何重渲染有效、现成前馈3D模型反而有害”的矛盾，并定位退化主要集中于细长机械臂。
◆ 利用“未知的相机参数与静态场景深度需估计、已知的机器人连杆3D状态可由运动学直接渲染”的非对称性，融合RGB帧与单张训练视角参考完成校正。
◆ 无需场景微调或部署相机标定，即可扩展到6自由度随机位姿、焦距变化及连续相机漂移。
在约30万闭环episode、四种冻结VLA和LIBERO-Plus全部1599种相机变体上，成功率由62.5%、76.5%、68.0%、3.6%提升至77.6%、95.1%、91.2%、26.4%。
在三/四个策略上匹配或超过已标定、场景训练的视角合成基线。</td></tr>
<tr><td>2026-11-18</td><td>Meta-LSQ: A Closed-Form Sobolev Inner Solver for Few-Shot Meta-Learning<br><a href='http://arxiv.org/pdf/2611.24718'>论文</a></td><td>Meta-LSQ提出一种用于少样本元学习的闭式Sobolev内层求解器，用固定随机Fourier基上的正则最小二乘替代需反向传播的梯度内循环，并仅元学习带宽、岭系数和导数权重三个标量。
◆以单次闭式最小二乘拟合每个任务，避免MAML式内环梯度微分和全网元学习。
◆利用正弦函数导数仍为正弦的性质，使同一求解器可吸收导数观测并给出任意阶精确闭式导数。
◆在任务间共享同一核，少量标量即可实现快速元学习，在正弦回归和ARES波束调优中优于一阶MAML或ALPaCA类基线。
◆真实传感器校准中学习先验均值可改善部分目标，但整体仍逊于精确GP/ALPaCA，且非光滑目标和基外无噪目标会暴露岭选择失效。
总体而言，其核心是以极低参数量的闭式谱基求解换取高效、可导且可融合导数的少样本适应。</td></tr>
<tr><td>2026-11-18</td><td>Object Pose: The Link between Weak Perspective, Paraperspective, and Full Perspective<br><a href='http://arxiv.org/pdf/2611.24095'>论文</a></td><td>本文对DeMenthon和Davis的位姿估计方法给出代数推导，说明其通过迭代改进弱透视位姿并逼近透视相机位姿。论文证明该方法属于更一般框架：透视相机模型可零阶近似为弱透视，或一阶近似为平行透视。
◆ 提出并详细描述面向非共面与共面物体点的迭代平行透视位姿计算方法。
◆ 分析并比较收敛性，证明迭代平行透视法比迭代弱透视法具有更好的收敛性质。
◆ 给出简单引入旋转矩阵正交约束的方式，并分析标定误差敏感性、定义最优实验设置。
最后与非线性优化方法比较实验结果，验证所提方法的性能与适用性。</td></tr>
<tr><td>2026-11-18</td><td>Agreement Is Not Accuracy: LiDAR Elevation Errors Hidden in LiDAR-Camera Extrinsics<br><a href='http://arxiv.org/pdf/2611.23972'>论文</a></td><td>论文指出LiDAR与相机观测一致并不代表内部几何准确，系统性LiDAR高程偏差会被外参吸收。
◆ 提出利用同步LiDAR强度与相机估计棋盘位姿，联合估计跨记录的传感器高程修正和逐记录外参。
◆ 用射线-平面交会定位棋盘格且不依赖报告距离，避免距离误差直接移动查表，并获得更小相机一致性残差。
◆ 在六个同构平台中将平均平移参考距离由7.57mm降至3.04mm。
◆ 在独立结构上降低平面间夹角误差并改善图像边缘对齐，旋转平台时最大角改善平面对按高程修正预测移动。
◆ 揭示外参标定后目标投影与回环一致性变化很小，说明标定一致不等于LiDAR内部几何正确，并提供无需大型标定场的实用估计与检验途径。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vlm'>Robot VLM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-19</td><td>ACE-Brain-0.7: Learning Execution-Grounded Reasoning for Embodied Agents<br><a href='http://arxiv.org/pdf/2611.26519'>论文</a></td><td>ACE-Brain-0.7是一个9B视觉语言模型，面向长时程具身任务，融合空间定位、任务理解与执行进度估计。作者构建370万问答对，从第一视角人类视频、机器人片段和仿真中提取执行监督，覆盖执行不同阶段并连接任务判断与观测进度、结果。基于Qwen3.5-9B联合任务、空间定位和进度估计数据微调后，其在六个任务推理基准平均76.5，超过GPT-6 Astra的72.7和Claude Opus 5.5的73.5，并在七个空间定位基准平均75.90、RefCOCOg Acc@0.5达91.25。
◆以观测到的执行状态为锚组织推理监督，使任务判断与执行进度、结果直接关联。
◆构建跨第一视角视频、机器人数据和仿真的大规模执行问答数据，覆盖执行不同阶段。
◆统一空间感知与时间理解，控制实验表明任务模型能更有效利用视觉历史并更准确区分执行状态。</td></tr>
<tr><td>2026-11-19</td><td>Alignment Drives Reuse: Learning Generalizable Robot-Use Agents from Heterogeneous Experience<br><a href='http://arxiv.org/pdf/2611.26376'>论文</a></td><td>论文提出UniCraft框架，核心贡献是证明通过对齐异构机器人经验，可以联合学习一个可泛化的共享操作技能集。该方法在3个基准、6种机器人本体上交错训练，每个智能体模型收集2700次学习rollout，显著提升未见场景和任务的成功率。
◆ 以“对齐”为核心整合跨基准、跨本体的异构交互经验，避免经验碎片化并形成共享技能集。
◆ 统一场景几何的坐标约定，并对齐不同机器人的传感与控制接口，同时将不同基准任务组织为规范格式。
◆ 无需演示数据或模型权重更新，利用交互反馈联合优化共享技能及负责技能选择与组合的编排策略。
◆ 训练中在LIBERO-PRO、RoboTwin 2.0和RoboCasa365上带来显著成功率提升，冻结技能后还能零样本迁移到4种新本体和5个额外智能体模型。</td></tr>
<tr><td>2026-11-19</td><td>EmbodyAgent: Post-Training Embodied VLM Agents via Distillation, SFT, and RL<br><a href='http://arxiv.org/pdf/2611.26196'>论文</a></td><td>EmbodyAgent提出一套端到端后训练框架，将黑盒数据合成、监督微调和在线强化学习三条管线紧耦合，用于把开源VLM训练成闭环机器人使用智能体。  
◆ 设计黑盒教师数据合成管线，在强制“先思考再写代码”契约下查询教师，并按任务成功过滤轨迹。  
◆ 构建SFT蒸馏管线，将解释与程序目标蒸馏进开源9B VLM，并同时训练视觉和语言编码器。  
◆ 提出在线RL管线，用组相对优势和带运行时错误惩罚的结果奖励优化学生生成轨迹。  
三条管线共享无原语Python执行工具，仅暴露原始视觉观测和七维末端控制，且无动作解码器、无阶段间接口切换。  
在LIBERO Spatial严格评估中，100个测试状态成功率从基础0/100升至SFT后14/100、RL后84/100，训练rollout成功率从8.4%升至87.7%，每回合中位模型调用从36降至11。  
论文还识别出可执行代码结果奖励RL诱发的自强化运行时错误模式，并提出失败类别监控与采样侧筛选协议以稳定训练。</td></tr>
<tr><td>2026-11-19</td><td>From Sequence to Space: Explicit Spatial Belief with Vision-Language Distillation for Active Geo-Localization<br><a href='http://arxiv.org/pdf/2611.25866'>论文</a></td><td>本文提出EAGLE，一种面向主动地理定位的显式空间信念智能体，使智能体在小型航拍搜索网格中到达由航拍图、地面照片或文本指定的目标。
◆ 将导航状态从大型序列Transformer的隐式表示改为由单元级航拍特征预测、目标嵌入和轨迹访问掩码显式构建的空间信念张量。
◆ 设计视觉语言蒸馏：离线联合训练教师条件Swin分支与无上下文Swin学生，教师借助Qwen2.5-VL-7B冻结全场景上下文，学生蒸馏教师特征并接受掩码重建与不确定性监督。
◆ 蒸馏后丢弃Qwen、缓存上下文和教师注意力分支，仅保留学生从部分观察预测航拍特征与不确定性，实现推理阶段不使用VLM或缓存视觉token。
◆ 冻结学生后仅用紧凑CNN actor-critic和PPO优化导航策略，并在MASA、xBD零样本迁移和MM-GAG零样本航拍目标子集上取得78.1%、76.4%、76.8%的最优平均成功率。</td></tr>
<tr><td>2026-11-19</td><td>Cognitive-Horizon Action Chunking: Memory-Guided Adaptive Reasoning for Embodied Navigation<br><a href='http://arxiv.org/pdf/2611.25587'>论文</a></td><td>本文提出Cognitive-Horizon Action Chunking（CHAC），一种无需训练、面向冻结导航策略的记忆引导自适应推理框架，旨在降低多模态基础模型在具身导航中的频繁推理开销。核心机制是利用保留的视觉上下文、完成线索和控制器反馈动态确定“认知视野”，即机器人在刷新预测前可执行多少缓存路点。
◆提出训练无关的认知视野动作分块机制，在冻结策略下自适应复用缓存路点以减少模型调用。
◆在策略请求停止时利用局部访问历史进行有界修正，最多增加一次移动且不增加额外模型调用。
实验表明CHAC在HM3D-OVON和R2R-CE上分别减少33.4%和64.7%的VLM调用，成功率仅下降0.63和10.82个百分点，且每次模型调用的成功率和SPL均提升。在四个物理导航任务中，CHAC以每方法40次运行取得18次成功（原生14次），并减少54.9%模型调用和49.7% GPU推理时间。</td></tr>
<tr><td>2026-11-19</td><td>CoachSI: Self-Improvement of Robot Policies with a Language Coach<br><a href='http://arxiv.org/pdf/2611.25529'>论文</a></td><td>CoachSI针对通用机器人策略能可靠执行原子技能却难以组合成长时任务、且仅靠自身经验自我改进会受限于自身分布的问题，提出用冻结现成VLM作为语言教练来补足“下一步”。
◆以语言教练观看机器人并仅输出符合策略原子指令格式的下一步子目标，不输出动作，从同一相机图像提供可执行引导。
◆将教练成功完成的rollout用原始任务指令进行事后重标注并微调策略，使教练仅用于训练、部署时策略可独立运行。
◆在动作骨干冻结下让语言教练教“下一步应该发生什么”，由策略已有技能完成执行，从而提升长时任务组合与未见场景泛化。
◆在WAM和VLA停滞状态下命名下一步使子目标完成率提升4.6倍，且教练仅依赖策略同一相机图像。
微调后未见场景长时任务无辅助成功率从47.4%升至59.3%，分别高于人类演示微调9.8点和等预算自采集成功微调7.3点，仅相机图像教练也达56.8%。</td></tr>
<tr><td>2026-11-19</td><td>ActMem: From Latent Memory Reasoning to Grounded Robotic Action<br><a href='http://arxiv.org/pdf/2611.25461'>论文</a> | <a href='https://github.com/LigphiDonk/ActMem'>代码</a></td><td>ActMem提出一种在单一视觉语言骨干内解耦记忆推理与感知落地的上下文记忆框架，先从带时间戳交互历史推断当前子任务，再以推理隐状态条件化动作专家，并让专家直接关注当前视图。它在RoboMemArena取得71.1%任务成功和80.8%完成成功，超最强基线7.5和8.7个百分点；MIKASA-Robo平均73.8%；真实世界三类记忆任务平均68.8%，超最强记忆增强VLA 10.0个百分点。
◆将记忆推理与感知落地解耦，避免历史上下文挤占当前感知。
◆把子任务推断形成的隐藏状态作为Latent Memory Chain-of-Thought，条件化flow-matching动作专家。
◆设计Perception Attention，使动作专家可直接关注当前视图。
◆提出Efficient Memory CoT Inference，在连续决策间复用计算且不改变输出，加速长历史推理。</td></tr>
<tr><td>2026-11-18</td><td>Verify2Act: Critic-Guided Latent World Models for Verifying Language-Conditioned Manipulation Plans<br><a href='http://arxiv.org/pdf/2611.25243'>论文</a></td><td>Verify2Act提出模块化验证框架，将语言条件下的多步操作计划生成与潜空间物理验证解耦，并在执行前筛选候选计划。
◆用VLM提议候选计划，由潜世界模型V2A-WM在DINOv2特征空间推演，再由双头critic检查时序一致性与目标满足。
◆V2A-WM在流匹配世界模型上引入交叉注意力动作接地和因果时序历史窗口，提升长时程想象稳定性。
◆系统仅用数字孪生生成的数据训练世界模型与critic，并部署到低成本机械臂，实现执行前验证。
在六个语言条件任务上达到83.3%成功率，高于无架构改动的潜世界模型61.7%、单独VLM 53.3%和像素扩散世界模型46.7%。
它验证了所有执行计划且无规划诱发失败，失败均来自低级抓取或放置滑落；在CALVIN取得最高五任务链成功率，并以比像素扩散验证少30倍的反思VLM调用在杂乱螺母装配中取得最高成功率。</td></tr>
<tr><td>2026-11-18</td><td>Bridging vision-language reasoning and learned control for legged navigation in the wild<br><a href='http://arxiv.org/pdf/2611.25215'>论文</a></td><td>ROAM系统将视觉语言模型的世界知识与仿真强化学习得到的运动控制和局部规划策略结合，实现腿足机器人在高山与城市等复杂环境中的公里级自主导航。  
◆创新性地融合互联网规模预训练的VLM常识推理与仿真学习的高鲁棒低层控制，形成高层语义理解到低层物理执行的耦合架构。  
◆让VLM对场景进行语义解释、风险评估、标志识读，并生成带导航代价的语义标签，为导航提供常识与语义先验。  
◆利用开放词汇分割模块将VLM标签转化为稠密实时风险图，进而条件化两个预训练RL策略，分别负责敏捷运动与局部导航。  
◆在真实环境中完成公里级徒步、低干预导航、按标志避险和安全落脚区域评估，验证了系统在非结构化环境中的实用性。  
该工作迈向复杂野外可靠部署，但也表明VLM可靠性与空间推理仍是瓶颈，基础模型是关键组件但尚非完整导航方案。</td></tr>
<tr><td>2026-11-18</td><td>VG-Steer: Visual-Geometric Policy Steering from In-Context Aligned Abstractions<br><a href='http://arxiv.org/pdf/2611.25199'>论文</a> | <a href='https://arthurfenderbucker.github.io/VG-Steer/'>代码</a></td><td>VG-Steer面向有限真实数据下机器人策略的OOD适应，提出一种测试时校正框架，将成功分布内rollout中的细微运动沿有意义的几何轴迁移到冻结策略。
◆ 利用LVM与VLM的语义推理自动识别任务相关实体对，并将其物体关系距离投影组合成统一的视觉几何引导信号。
◆ 以物体关系距离对作为可解释几何轴，迁移分布内成功轨迹的细粒度任务相关运动，弥补现有显式空间校正过于粗糙的问题。
◆ 校正信号不依赖从机器人数据隐式学习的误差模型，避免与被校正策略共同受分布偏移影响，且无需微调原策略。
仿真中该方法在位姿与任务目标偏移下高效校正flow-matching策略；真实实验中扩大冻结策略工作空间覆盖，使训练位置外一格电缆放置成功率翻倍以上，并能将单任务策略引导至未训练物体且近乎消除物体混淆。
这些结果表明VG-Steer为有限数据下的通用机器人策略提供了可解释、细粒度且可测试时部署的OOD适应路径。</td></tr>
<tr><td>2026-11-18</td><td>$Z$-sight: Unifying Vision-Language-Action and Latent World Modeling<br><a href='http://arxiv.org/pdf/2611.24940'>论文</a></td><td>论文提出Z-sight，一个统一视觉-语言-动作与生成式潜在世界建模的机器人基础模型。
◆ 直接在VLM感知当前帧的视觉token空间中预测未来，避免像素重建和外部目标编码器。
◆ 采用混合Transformer耦合预见专家、连续动作专家与VLM，在推理时联合去噪未来空间token和动作。
◆ 联合利用人类视频与机器人轨迹训练，实现未来预测与动作生成的紧耦合。
◆ 无需像素生成即可高效推理，每动作块仅需110毫秒。
◆ 在SIMPLE达81.9%成功率，较最强基线提升9.6点；六个Unitree G1任务平均73.3%，提升20.0点，并在桌面基准保持竞争力。</td></tr>
<tr><td>2026-11-18</td><td>DRIFT: Detachable Reasoning for Runtime-Flexible and Efficient End-to-End Driving<br><a href='http://arxiv.org/pdf/2611.24719'>论文</a> | <a href='https://drift-e2e.github.io/'>代码</a></td><td>本文提出DRIFT，一种集成轻量语言模型用于视觉问答与动作评论的端到端自动驾驶框架，旨在解决VLM计算昂贵且难以在运行时灵活开关语言推理的问题。
◆ 通过将中间驾驶表示高效投影到语言嵌入空间，使参数量小于150M的紧凑语言模型即可完成较强的场景描述与动作评论。
◆ 设计运行时灵活规划模块，利用从语言模型蒸馏的代理推理特征训练，推理时可按部署约束选择语言模型或代理特征，从而完全绕过语言模型而不牺牲驾驶性能。
◆ 以仅255M参数在Bench2Drive上取得最高97.03驾驶得分和89.39%成功率（三次运行均值），通过按选定推理率交错语言模型与代理推理，达到与最强非语言模型相当且远紧凑于现有VLM模型的效果。
◆ 在真实NAVSIM和AlpaSim基准上取得有竞争力结果，且计算成本显著低于现有VLM方法。</td></tr>
<tr><td>2026-11-18</td><td>Teaching VLMs What to Say, Not How to Reason: Rethinking Counterfactual Reasoning in Autonomous Driving<br><a href='http://arxiv.org/pdf/2611.24376'>论文</a></td><td>本文重新审视VLM端到端自动驾驶中反事实推理的实际作用，指出既有方法可能把捷径学习从视觉表征转移到语言模式，并混淆干预式推理与反事实推理。
◆ 首次系统检验真正反事实推理在VLM驾驶决策中诱导的效应，而非仅判断是否加入语言推理。
◆ 发现反事实推理使动作分布更保守并提高推理与决策不确定性，且该效应在强化微调后仍持续。
◆ 视觉注意力分析表明反事实推理未改变视觉 grounding，因果干预实验显示屏蔽因果相关与非因果因素引发相近的决策变化率。
◆ 由此论证反事实推理未形成基于视觉证据的真正因果理解，而是一种重塑动作分布的语言捷径。
◆ 提出“教模型说什么而非如何推理”的核心判断，揭示语言推理与自动驾驶因果理解之间的关键差距。</td></tr>
<tr><td>2026-11-18</td><td>Hardware Acceleration of Vision-Language-Action Models with Weight Precision Rising over the Flow Steps<br><a href='http://arxiv.org/pdf/2611.24234'>论文</a></td><td>论文指出VLA动作头在少步flow matching中每步都从DRAM重读全部权重而仅作用于约50个token，因而推理受内存带宽限制，且后期步骤会衰减前期量化误差，故权重精度应随步骤升高。
◆ 提出无需校准或训练的逐通道舍入精度爬升方案，使权重从2位逐步升至4位即可保持机器人闭环成功率，并比每步4位少传25%权重位。
◆ 设计可编程加速器，使延迟和能耗随传输权重位缩放，并以DRAM速率解码熵编码权重供位串行子阵列使用。
◆ 引入运行时分配器，按每步精度在注意力和线性层间动态划分位串行子阵列，以平衡负载并兼容不同规模动作头及视觉语言模型。
◆ 在DRAM侧每bank集成重量化器和熵编码器，用单份8位存储替代各精度副本；基于LPDDR5X的RTL仿真在GR00T N1.6四步2/3/3/4位下达8.02ms/次，相比Thor NVFP4快1.7倍、能耗低9.1倍且闭环成功率相当。</td></tr>
<tr><td>2026-11-18</td><td>Assessing Vision-Language Models for Early Prediction of Unsafe Situations in Robotics<br><a href='http://arxiv.org/pdf/2611.24146'>论文</a></td><td>论文对视觉语言模型能否在机器人不安全事件发生前进行早期预测开展了系统的实证评估，弥补了相关证据不足。  
◆ 在HuRoN、Pal Robotics和CrowdBot三个机器人案例中，同时分析视频与里程计数据，比较Qwen、InternVL和LLaVA-OneVision的早期故障预警能力。  
◆ 将安全状态细分为安全、潜在不安全和不安全三类，并结合多种不确定性度量分析模型性能与不确定性之间的关系。  
◆ 揭示不同模型在分类准确性、预测可靠性和早期预警及时性上的差异化优势，如Qwen总体分类与可靠性较强、InternVL在部分配置下预警更早。  
◆ 系统考察机器人状态信息与时序历史对不同模型和评估目标的影响，表明最佳配置取决于优先目标是准确评估安全状态、可靠置信度还是及时预警。  
总体而言，通用视觉语言模型可支持机器人早期安全监控，但需根据具体安全目标选择模型与配置。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-visual-semantic-recognition'>Robot Visual Semantic Recognition</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-18</td><td>Does the Action Matter? Probing Action-Conditioned Semantic Forecasting as a World Model for Autonomous Driving<br><a href='http://arxiv.org/pdf/2611.24840'>论文</a> | <a href='https://github.com/binayksingh/does-action-matter'>代码</a></td><td>论文核心贡献是提出并检验动作条件语义预测是否真正依赖动作，而非仅评估预测精度与规划性能。作者比较特征级与输入级动作条件模型和无动作输入的相同模型，用测试时动作干预和分割指标量化动作依赖性，并在合成环境、Cityscapes、BDD100K及跨车辆平台上验证。实验表明执行动作带来的mIoU提升有限，而错误动作会显著降低性能甚至低于无动作模型；真实数据上特征级条件比输入级条件更依赖动作约1.6倍，说明精度增益不能代表动作依赖强度。
◆提出以测试时动作干预衡量动作条件世界模型依赖性的评估框架。
◆系统比较特征级与输入级动作条件方式，并揭示真实数据与合成环境中的依赖差异。
◆发现预测精度与动作依赖强度解耦，为自动驾驶世界模型评估提供新准则。</td></tr>
<tr><td>2026-11-18</td><td>ALIVE: Bring Foundation Features to Life with Events<br><a href='http://arxiv.org/pdf/2611.24579'>论文</a></td><td>论文提出ALIVE，一种基于事件的方法，在两次图像观测之间增量更新视觉基础模型特征，避免反复运行昂贵的图像编码器。
◆ 利用后续事件对冻结DINOv3编码器提取的多层锚点图像特征进行传输与校正，实现基础模型特征的持续刷新。
◆ 设计轻量级特征更新器，仅用合成数据端到端训练，无需下游任务监督，并可零适配直接迁移到真实事件流。
◆ 在检测、语义分割和深度估计等五个任务-数据集设置中，ALIVE在所有指标上均优于所有评估的基于事件方法。
在DSEC上，当锚点帧已过时200ms，ALIVE使检测提升30.9 mAP、分割提升11.6 mIoU、深度AbsRel改善15.9%。
相比图像重编码，ALIVE减少82.4% FLOPs并将延迟降低2.5倍。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vpr'>Robot VPR</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-18</td><td>What Should Visual Place Recognition Be Invariant To? Rethinking Condition Invariance in Visual Place Recognition<br><a href='http://arxiv.org/pdf/2608.06847'>论文</a></td><td>这篇论文针对长期视觉位置识别（VPR）中的关键问题展开研究，指出当前VPR方法在匹配过程中容易受光照、天气、季节等条件信息干扰，可能依据条件相似性而非地点身份进行检索。

◆ 提出Distractor-Augmented Recall（DAR）评估指标，通过向数据库注入干扰图像来分离和量化干扰物的影响，揭示现有方法在标准Recall@1下的排名与DAR@1排名存在显著差异。

◆ 提出对VPR描述子进行条件抑制，采用INLP和LEACE方法去除描述子中编码的照明、天气、季节等条件信息。

◆ 在11种VPR方法和6个数据集上的实验表明，条件抑制普遍提升DAR@1性能而不降低标准R@1，证实抗干扰鲁棒性与标准检索性能是相互独立的维度。

该研究的核心贡献在于揭示了VPR模型&quot;识别地点还是识别条件&quot;这一被忽视的问题，为构建更鲁棒的VPR系统提供了新的评估框架和解决方案。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5393</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4887</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2493</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1667</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1632</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1544</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1390</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1323</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1142</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>1117</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>956</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>820</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>786</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>754</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>748</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>736</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>705</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>681</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>639</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>633</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>626</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>597</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>573</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>550</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>516</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>483</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>471</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>376</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>351</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>148</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>124</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2892</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1686</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1371</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1099</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1065</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>889</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>715</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>674</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>671</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>624</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>619</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>580</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>579</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>572</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>555</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>525</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>522</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>466</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>458</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>455</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>353</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>334</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>310</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>305</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>292</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
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
> 更新于: 2026.11.20
