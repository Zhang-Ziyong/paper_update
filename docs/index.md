# 计算机视觉领域最新论文 (2026.11.10)

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
<tr><td>2026-11-09</td><td>V3DSAM: Semantic-Geometric Loop Verification and Geometry-Anchored Persistent Instance Mapping for Feed-Forward Dense SLAM<br><a href='http://arxiv.org/pdf/2611.12452'>论文</a></td><td>本文提出V3DSAM，一个面向长序列前馈稠密SLAM的开放词表语义稠密SLAM系统，用于解决跨视角关联不可靠问题。系统将VGGT-SLAM 2.0的前馈几何估计与SAM3的开放词表语义观测相结合，在场景和物体两级建立物理对应。
◆提出语义—几何双尺度回环验证，利用像素级双向重投影和物体级三维空间对应识别假回环，且无需访问骨干网络内部特征。
◆提出几何锚定的持久实例建图，在优化后的全局坐标系中以类别约束的三维连通性定义物理实例，并在不进行帧间身份传播的情况下分配全局ID。
在TUM RGB-D上该验证器拒绝了全部四个假回环候选，在长序列ScanNet上提升了实例身份一致性。因此，V3DSAM降低了对骨干内部特征和时序ID传播的依赖，增强了长期跨视角关联的鲁棒性。</td></tr>
<tr><td>2026-11-09</td><td>DPGS-SLAM: Diffusion-Prior and Provenance-Aware Monocular Gaussian Splatting SLAM for Dynamic Visual Sensing<br><a href='http://arxiv.org/pdf/2611.12038'>论文</a></td><td>DPGS-SLAM提出一种面向动态场景的单目RGB高斯泼溅SLAM框架，在动态观测污染跟踪与建图、且剔除动态会导致遮挡静态背景缺失的情况下实现稠密建图。
◆ 采用光流运动发现与SAM2时序一致掩码传播识别动态区域，降低动态物体对SLAM稳定性的影响。
◆ 设计异步扩散背景补全机制，对关键帧遮挡区域用微调扩散修复模型生成合理背景，并由Metric3D v2预测度量深度初始化临时高斯图元。
◆ 引入provenance-aware高斯建图，用来源标签区分生成图元与观测支持图元，生成内容不参与相机位姿估计和观测地图优化。
◆ 当原遮挡背景可见时移除合格生成图元，并由真实RGB观测和预测深度独立初始化观测支持图元，实现临时补全到真实观测的替换。
实验表明其在TUM和BONN上取得有竞争力的跟踪精度，ATE RMSE分别为1.2 cm和2.7 cm，并在StaDy4D上仅用单目RGB较WildGS-SLAM平均PSNR提升4.60 dB。</td></tr>
<tr><td>2026-11-09</td><td>Scale-Consistent Monocular Fisheye Visual Odometry via Spherical Bundle Adjustment-Guided Unsupervised Depth Learning<br><a href='http://arxiv.org/pdf/2611.11934'>论文</a></td><td>本文提出S²D-FVO单目鱼眼视觉里程计框架，将球面光束法平差SBA与无监督深度学习结合，以提升长轨迹尺度一致性和深度估计精度。
◆ 采用基于球面对数映射的切线空间角度重投影残差，使残差在两个切向均保持敏感且范数等于标量角度残差，克服像素残差非均匀及一阶线性化方向不敏感问题。
◆ 在SBA中引入基于中值深度的尺度正则项，约束重建尺度。
◆ 用SBA在无监督深度学习中替代位姿估计网络以提供更可靠相对位姿，并用训练后的深度网络为SBA提供尺度参考，迭代提升尺度一致性并细化三维路标。
在多个公开数据集和两个新采集大规模数据集上的实验表明，该框架在深度与轨迹估计精度上优于代表性现有方法，且适用于不同相机模型。</td></tr>
<tr><td>2026-11-09</td><td>Prop-WRF: Proposal-Guided Wireless Radiance Field for Scalable Multi-Frequency Outdoor Channel Frequency Response Prediction<br><a href='http://arxiv.org/pdf/2611.11845'>论文</a></td><td>本文提出Prop-WRF，一种面向大规模多频户外场景、由提案网络引导的WRF，用于从接收机位置与多径方向先验预测多子载波CFR，并在仿真中提升预测精度与训练稳定性。
◆ 设计轻量提案网络，通过主网络在线蒸馏学习虚拟锚点占用密度，并迭代引导重采样集中在潜在VA区域。
◆ 主网络在细化区间上预测复数辐射，并借助解析传播模型合成多子载波CFR。
◆ 仅在辐射分支引入频率编码，使单一模型联合学习跨子载波共享的VA几何与频率相关复数辐射。
◆ 提出阶段式混合归一化损失和区间权重正则，增强弱信道监督并抑制虚假VA峰。
◆ 构建多径SLAM前端，细化接收机状态与路径关联，为训练提供几何一致先验。</td></tr>
<tr><td>2026-11-09</td><td>ACROSSVAM3.0: Resource-Bounded 4D Scene Construction and Adaptive Surface Association<br><a href='http://arxiv.org/pdf/2611.11825'>论文</a></td><td>AcrossVAM3.0提出一种资源受限的离线4D场景构建系统，可将文本、图像或单目RGB视频转换为带版本的点表示，并在单GPU上顺序运行冻结组件。
◆该系统用无神经参数的协调层统一更新相机、点和轨迹，实现地图修正与多模块坐标一致。
◆它引入多假设自适应表面链（MHAC），保留多个候选匹配及显式缺失状态，以兼顾局部表面精度与长程跟踪覆盖。
◆在冻结协议下，系统最高采样GPU占用17.14 GB，16场景均获4D重建、15个获非空SLAM地图。
MHAC在十视频留出集将Average Jaccard较仅位置基线提升0.1394，并在265个RoboTAP视频上取得平均配对增益0.0610。
结果支持资源受限场景构建和外部跟踪增益，但不确立度量尺度、语义身份或高保真新视角渲染。</td></tr>
<tr><td>2026-11-08</td><td>Map2SLAM: From Streaming Map Prediction to Real-Time SLAM<br><a href='http://arxiv.org/pdf/2611.11169'>论文</a> | <a href='https://robbyant-research.github.io/Map2SLAM/'>代码</a></td><td>Map2SLAM 将冻结的流式3D基础模型作为几何观测源，把其在线预测转化为外部持久SLAM状态的可修正观测，从而解决流式预测发出后无法通过回环纠正漂移的问题。
◆ 仅训练轻量检索头并保持LingBot-Map冻结，在模型推理接口上构建SLAM，降低适配成本。
◆ 前端用因果流式推理跟踪每帧并筛选关键帧写入持久状态，后端异步选择历史帧重观测并在线校正轨迹。
◆ 通过带新上下文的联合重推理生成回环与分段观测，回环在线纠偏、分段观测在序列后细化稠密几何。
◆ 所有调用共享每图一次帧编码，缓存特征同时用于回环检索，频繁重调用不增加额外编码开销。
在KITTI、VBR和Oxford Spires上达到SOTA，平均ATE较最佳未标定基线降低40%以上，并在RTX 5090D上以518×154分辨率保持超过28 FPS实时跟踪。</td></tr>
<tr><td>2026-11-06</td><td>DASH-SLAM: Calibration-Free Metric Monocular SLAM via Depth Scale Propagation<br><a href='http://arxiv.org/pdf/2611.10239'>论文</a></td><td>本文提出DASH-SLAM，一种无需任务特定微调、无需标定的单目度量SLAM系统，将预训练Depth Anything 3的度量深度预测集成到共享关键帧位姿图中。
◆ 利用共享锚点图像处的深度比值推导尺度校正，并在连续重建间累积，同时用阻尼因子控制其影响。
◆ 尺度校正统一重缩放里程计平移、回环约束和地图几何，从而保持跨重建一致的度量尺度。
◆ 在无需额外标定或微调的情况下实现度量单目SLAM，兼顾数据关联与尺度传播。
在TUM、Replica和7-Scenes上，DASH-SLAM优于现有方法，并通过刚性与相似对齐区分度量尺度保真度和至尺度精度。
在Unified Autonomy Stack野外数据集的隧道、雾和冰湖等四个感知退化序列上，DASH-SLAM优于基础模型SLAM最先进方法，并在经典SLAM失效时保持跟踪。</td></tr>
<tr><td>2026-11-06</td><td>A Straight Line Is Not a Camera Pose: Auditing Short-Clip Pose Benchmarks<br><a href='http://arxiv.org/pdf/2611.00482'>论文</a></td><td>论文系统审计短片段相机位姿基准，发现按Sintel协议，不使用图像的匀速直线预测平均ATE竟优于11个近期模型中的10个，揭示ATE对齐会掩盖几何错误。作者进一步证明ATE将匀速预测映射到真路径最佳拟合线，使直线仅得分回归残差，并提出残差信噪比准则预测直线化何时降低ATE，在多数模型-片段对上成立且能区分Sintel与其他数据集；同时指出仅位置对齐忽略相机朝向，旋转30度可保持ATE不变却恶化重投影，低ATE不等于好几何。
◆ 揭示无图像匀速直线可击败多数近期模型的ATE异常，并给出基于残差信噪比的解释与预测准则。
◆ 证明位置仅对齐忽略朝向，低ATE可能对应更差重投影几何。
◆ 提出pose-anchored ATE，用预测朝向拟合对齐旋转，更好反映几何误差且仅增加约0.06毫秒开销。
◆ 在新指标上正确排序图像无关参考与模型、跟踪旋转和直线化下的重投影误差，并基本保留模型顺序。</td></tr>
<tr><td>2026-11-05</td><td>An Integrated Open-Source Stack for Vision-Based Autonomous Navigation of Wheeled Rovers<br><a href='http://arxiv.org/pdf/2611.08100'>论文</a></td><td>本文提出一个面向轮式巡视器视觉自主导航的开源ROS 2集成栈，实现箭头跟随、到达终端锥并自主返回的完整任务。该系统贯通YOLOv8n检测与几何方向/距离/方位估计、RGB-D SLAM、轮式惯性状态估计、运动学感知规划、行为树任务管理和STM32执行，并公开软件、配置、标注数据集、训练权重与评估日志。
◆以标准接口分离可复用自主性与硬件层，并提供支持低速巡视器的比例路径跟随插件。
◆在478张留出图像上实现mAP@0.5为0.720，优于共享协议下的OpenCV基线，Jetson Orin NX感知延迟25 ms。
◆通过三次室内外任务验证标记引导导航与无操作员运动指令的自主返回，且未报告碰撞。
◆记录现场集成失败与修正选择，同时指出物理导航误差和可靠性仍需重复仪器化试验量化。</td></tr>
<tr><td>2026-11-05</td><td>FREE-LIVO: Physically Decoupled Yet Tightly Coupled LiDAR-Inertial-Visual Odometry<br><a href='http://arxiv.org/pdf/2611.07463'>论文</a></td><td>FREE-LIVO提出一种面向模块化异构机器人系统的紧耦合LiDAR-惯性-视觉里程计，核心贡献是在不依赖刚性LiDAR-相机外参和LiDAR-相机时间同步的条件下实现鲁棒状态估计。
◆无需固定LiDAR-相机相对位姿和精确时间同步，即可联合优化多传感器状态。
◆利用生成模型由单次LiDAR扫描生成密集强度图，并用预训练图像特征匹配器建立相机图像与LiDAR强度图的3D点到像素对应。
◆由该对应构造跨采集时刻的重投影因子，并与点云配准、视觉特征跟踪及各传感器IMU约束放入同一因子图联合优化。
在M3DGR六个序列上，无外参时平均ATE RMSE为0.45米，且在最高0.5秒时间同步误差下精度退化很小。
将LiDAR和相机分别安装在不同机器人上的实验表明，该方法还能联合估计独立运动传感器的轨迹。</td></tr>
<tr><td>2026-11-04</td><td>Scale Anchoring via Implicit Semantics and Sequence-Consistent Loop Closure for VGGT-Based SLAM<br><a href='http://arxiv.org/pdf/2611.06308'>论文</a></td><td>本文针对VGGT类前馈几何基础模型在单目稠密重建中独立子图尺度漂移、跨子图回环测量不一致的问题，扩展VGGT-SLAM 2.0提出固定根尺度锚定与短序列辅助的直接回环连接。
◆提出基于SALAD选帧和联合VGGT推理的尺度锚定，利用隐式语义几何线索在新子图与初始子图间提供仅尺度约束，同时保留原重叠链。
◆设计短序列辅助回环：用相邻图像对做一致性检查和平移尺度对齐，使接受候选直接在已有中心帧节点间生成鲁棒Sim(3)因子，无需辅助回环子图。
◆通过候选审计区分长程尺度锚定、回环连接选择与候选验证的贡献，并揭示短序列检查会额外拒绝视觉重叠对。
17序列实验将9个TUM序列平均Sim(3) ATE由0.1018降至0.0451米，锚定改善全部7个无回环消融，3个Clio场景固定回环比较中直接连接管线优于辅助子图管线。</td></tr>
<tr><td>2026-11-03</td><td>Auditing Targetless Camera-LiDAR Extrinsic Correction before Recursive Use<br><a href='http://arxiv.org/pdf/2611.04397'>论文</a></td><td>本文研究无目标相机-LiDAR外参校正能否在递归使用前，分别审计校正质量、置信度排序和递归风险后再被下游接纳。作者提出log-disjoint协议，在Argoverse 2合成外参漂移上评估各阶段，并将跨数据集与里程计实验限定为有界诊断。
◆ 核心创新是把校正质量、置信度排序和递归污染风险拆成可独立审计的环节，而非直接放行校正结果。
◆ 通过零注入检查、求解器分歧AUROC及最终系统角色实验，给出校正收益与风险不匹配的反例和边界证据。
实验显示单帧Canny在温和档有害，多帧虽改善严重档旋转2.52度却使平移变差0.177米且联合误差改善为负，风险覆盖操作点未获验证；15日志中保守策略不接纳候选而等同Raw，Always-correct反而增大轨迹误差。因此论文贡献是建立可审计分离的思路并揭示不可直接部署，尚未证明校准门、正里程计或SLAM收益、地图一致性和闭环安全。</td></tr>
<tr><td>2026-11-03</td><td>EndoS3:Endoscopic Semantic Splatting SLAM<br><a href='http://arxiv.org/pdf/2611.04358'>论文</a></td><td>针对内窥镜语义SLAM需并行完成位姿跟踪、可变形重建和语义建图且评测数据稀缺的问题，论文提出基于高斯泼溅的EndoS3框架，用实例掩码统一指导三项任务。
◆提出实例级运动分解模块，通过补偿相机运动后的残差流区分静态与动态实例，并考虑流噪声和相邻实例运动比较。
◆设计实例感知变形建模，相机对静态高斯跟踪，每个动态实例拥有独立控制节点和变形网络。
◆提出语义节点分配模块，按实例大小和非刚性在实例间重新分配固定节点预算。
◆构建CRCD++离体胆囊切除数据集，提供RGB-D帧、相机位姿和实例标注，支持完整语义SLAM评测。
在CRCD++和SemSup上，EndoS3在跟踪、重建和语义建图上均优于现有通用及手术语义SLAM方法，表明语义感知的运动与变形建模对手术语义SLAM至关重要。</td></tr>
<tr><td>2026-11-02</td><td>CoReMatch: Recurrent Continuous Coordinate Refinement for Real-Time Robotic Feature Matching<br><a href='http://arxiv.org/pdf/2611.03932'>论文</a></td><td>论文针对现有半稠密匹配器在固定网格上预测置信度、对应点受限于预定义位置且高分辨率网格成本高的问题，提出CoReMatch实时机器人特征匹配框架。其核心贡献是直接在连续坐标空间中迭代细化对应关系，而非预测离散置信图，从而逐步提升匹配定位精度。
◆ 创新性地采用循环连续坐标细化范式，使对应点能够摆脱固定网格限制并在连续空间中优化。
◆ 在粗阶段使用深度聚合Transformer捕获全局上下文并迭代更新对应坐标，增强全局匹配能力。
◆ 设计轻量级回归头进一步锐化定位，在保持高效的同时提升连续坐标估计精度。
实验表明CoReMatch在室内外基准上实现精度与效率的良好平衡，精度超过Efficient LoFTR，且在嵌入式边缘硬件上运行速度超过其10倍。这些结果说明循环坐标细化是一种高效、可扩展的实时机器人特征匹配方案。</td></tr>
<tr><td>2026-11-02</td><td>A Tightly Coupled Magnetic-Inertial SLAM System for Field Robots<br><a href='http://arxiv.org/pdf/2611.03106'>论文</a></td><td>本文提出紧耦合磁惯性SLAM系统MISLAM，仅使用IMU与九磁强计阵列，不依赖外部里程计或平台特定运动假设。  
◆ 创新性地将惯性导航模型与局部多项式磁场模型结合用于短期运动估计，并利用全局高斯过程磁场模型和误差状态卡尔曼滤波进行漂移校正。  
◆ 实现无需视觉、激光、轮式里程计或预装基础设施的紧耦合磁惯性融合，适用于GNSS拒止及粉尘、烟雾、弱光等退化环境。  
◆ 面向地面与空中机器人等现场机器人场景，提供不依赖可见性和轮地接触的补充定位模态。  
在三个室内手持数据集上，总端点闭合误差相对磁惯性里程计降低45.7%至78.0%；弱光下视觉惯性里程计失效后仍保持跟踪，水平闭合误差0.332米，但垂直漂移仍是限制。  
结果表明磁惯性SLAM可作为视觉退化条件下机器人传感器套件的有力补充定位方案。</td></tr>
</tbody>
</table>
</div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-11-02</td><td>Solv3R: 3D Looped Transformer as a Multi-view Solver<br><a href='http://arxiv.org/pdf/2611.02857'>论文</a> | <a href='https://ubc-vision.github.io/solv3r/'>代码</a></td><td>论文提出Solv3R，一种循环Transformer，可学习从当前估计状态继续求解多视图几何，从而支持重建的扩展与细化。
◆ 其更新算子与迭代次数无关，能联合更新已精炼视图和新引入视图，而不必区分各视图的“已求解”程度。
◆ 通过训练该算子在持续迭代中保持准确重建并纠正不准确状态，模型可细化固定图像集合并融合新观测。
◆ 已求解视图的表示可缓存并跨迭代复用为几何上下文，实现紧凑高效的键值缓存。
◆ 单一学习求解器无需任务特定训练或模块，即可统一支持离线重建、增量重建、重定位和流式重建。
作者还分析了求解器动态并与最先进方法比较，验证了上述多任务统一能力与效率优势。</td></tr>
<tr><td>2026-11-01</td><td>Depth Anyviewpoint? Evaluating Monocular Depth Over Viewpoint Sequences<br><a href='http://arxiv.org/pdf/2611.02203'>论文</a></td><td>本文针对单目深度模型仅预测仿射不变深度、在视角变化下空间一致性与度量可解释性不足的问题，提出面向移动相机视频序列的系统评估方法。
◆构建基于移动相机视频序列的单目深度评估协议，用于检验模型在视角变化下的预测一致性。
◆利用structure from motion将模型输出锚定到场景度量深度，从而在真实视频上评估其度量对齐能力。
◆在多样真实世界视频上开展实验，揭示现有单目深度基础模型在长时间跨度上保持时间与三维一致性的开放挑战。
◆进一步指出将SfM直接作为单目深度度量接地工具所面临的困难。
总体而言，论文建立了可操作的视角序列评测流程，并暴露了可广泛应用的单目深度基础模型在一致性与度量接地方面的关键缺口。</td></tr>
<tr><td>2026-10-30</td><td>MFlowAudio: Efficient Text-to-Audio Synthesis via Mamba-based Stateful Flow Matching<br><a href='http://arxiv.org/pdf/2610.41852'>论文</a></td><td>MFlowAudio提出一种基于Mamba的潜在音频生成框架，将Flow Matching的连续时间建模与定制TCMamba主干结合，以解决Transformer扩散模型自注意力二次复杂度对长音频合成的瓶颈。
◆设计TCMamba双扫描机制：TimeMamba以线性复杂度捕捉长程因果依赖，ChannelMamba建模谐波结构等跨通道相关性。
◆提出Stateful Flow Matching范式，天然支持分块训练与流式生成，并保持O(1)缓存复杂度且不引入额外计算开销。
◆设计新的引导机制，缓解提示词语义在线切换引发的向量场碰撞，实现细粒度可控合成。
实验表明MFlowAudio生成保真度与先进基线相当，同时生成加速超过14.5%，并支持恒定1.8秒延迟的感知无缝流式合成。</td></tr>
<tr><td>2026-10-30</td><td>OASIS II: The Ionized Gas Traces Feedback-Driven Declines into the Quiet Side of Bursty Star Formation at z &gt; 4<br><a href='http://arxiv.org/pdf/2610.41490'>论文</a></td><td>本文用54个z&gt;4低质量星系的NIRSpec/PRISM光谱，比较Balmer线SFR与100 Myr恒星连续谱平均SFR，测量静息相进入时标及电离气体响应，发现静息期约100 Myr、恢复更快，且下降快于被动气体耗尽，支持反馈驱动。
◆联合近期与100 Myr平均SFR识别mini-quenched和lulling星系，测得静息相约100 Myr且恢复快于下降。
◆发现[OIII]/[OII]随SFMS位置下降，但更紧密追踪SFR10/SFR100，表明电离气体记录近期SFR变化。
◆发现SFMS下方仍在上升的星系高电离，支持较少且较软电离光子照亮被早期恒星形成耗尽的气体。
◆证明lulling星系ISM条件独特，并将静息相归因于驱逐或抑制气体的反馈，确立电离气体可示踪爆发周期位置。</td></tr>
<tr><td>2026-10-30</td><td>OASIS I: Spectroscopy of Mini-Quenched and Lulling Galaxies Constrains the Quiet Side of Bursty Star Formation at z &gt; 4<br><a href='http://arxiv.org/pdf/2610.41489'>论文</a></td><td>论文利用JWST Cycle 3 OASIS项目对z&gt;4星系开展28小时深曝光NIRSpec/PRISM光谱，系统搜寻爆发式恒星形成周期中被抑制的“安静”阶段，而非依赖偶然发现。
◆系统识别3个mini-quenched星系（低于SFMS 1.2-1.7 dex且无Balmer发射）、5个lulling星系和17个近主序星系，覆盖完整爆发周期。
◆证明光谱不可替代：10个测光候选中有7个并非抑制星系，测光会高估当前SFR且无法区分lulling与mini-quenched。
◆发现抑制星系并不罕见，在非按恒星形成状态选择的样本中占z=4-5.5、logM*=8-9.5星系的29%，数密度约1.6×10^-3 Mpc^-3 dex^-1，远高于模拟预期且质量更高。
◆揭示抑制阶段较持久：越低于SFMS的星系Balmer断裂和恒星年龄越老，lulling约30 Myr、mini-quenched超过100 Myr，且E(B-V)&lt;0.2符合气体库耗竭。
结论是z&gt;4的抑制阶段既不罕见也不短暂，而是早期星系成长中常见且持续的一部分。</td></tr>
</tbody>
</table>
</div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-10-22</td><td>HimmBO: High-Dimensional Interactive Model-Merging Bayesian Optimization for Image Generation<br><a href='http://arxiv.org/pdf/2610.30875'>论文</a></td><td>HimmBO提出一种面向图像生成的两阶段高维交互式适配器合并贝叶斯优化方法，将偏好驱动的模型合并扩展到更大适配器集合并显著降低图像生成开销。
◆筛选阶段利用预生成图像上的水平集估计恢复活跃适配器集合，整个阶段无需生成新图像。
◆精炼阶段在恢复的低维子空间中优化合并系数，避免直接在高维全集合上搜索。
◆两阶段均采用风格感知核，使偏好信息能在视觉相似的适配器之间迁移复用。
实验表明，HimmBO在模拟用户图像匹配中最终相似度优于所有对比方法，达到给定相似度所需图像生成次数不足先前方法的十分之一。
其性能在适配器集合扩展到1080个时仍保持稳定，而竞争方法明显退化。</td></tr>
<tr><td>2026-10-18</td><td>LateMatch: Breaking the Interaction Bottleneck via Cacheable Matching for Efficient Visual Localization<br><a href='http://arxiv.org/pdf/2610.25358'>论文</a></td><td>论文针对现有深度特征匹配器在每层紧耦合图像内上下文与跨图匹配、对K张库图需重复执行完整网络且无法缓存的问题，指出严重交互瓶颈。  
◆提出可缓存图像匹配新范式，将跨图交互推迟到网络末层，使图像内处理可离线缓存、在线仅执行少量交互计算。  
◆提出LateMatch，通过Context Blocks与Interaction Blocks解耦重构现有匹配器，实现通用且高效的视觉定位部署。  
◆提出E-SToRE，利用晚期交互块香农熵下降，在跨图交互前动态进行空间token缩减与扩展。  
在HPatches、ScanNet、MegaDepth、ETH-3D和Aachen上验证，LateMatch相较标准深度匹配器降低有效计算成本2倍以上。  
E-SToRE进一步带来10%至14%额外节省且精度几乎不退化。</td></tr>
</tbody>
</table>
</div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-11-02</td><td>MuCHMDPoser: Multiview RGB-Camera Full-Body Pose Tracking for Virtual Reality<br><a href='http://arxiv.org/pdf/2611.03062'>论文</a> | <a href='https://github.com/antmaio/MuCHMDPoser'>代码</a></td><td>本文针对仅依赖VR头显和手柄等稀疏传感器时全身姿态推断严重欠约束、尤其下肢误差大的问题，提出融合外部多视角RGB相机的全身姿态跟踪框架。论文验证了将RGB姿态估计集成到该框架可显著降低下肢跟踪误差，即使RGB估计存在常见伪影仍有效。
◆ 将多视角RGB姿态估计引入VR稀疏追踪框架，以外部相机信息补偿头显与手柄仅提供3个上半身关节的不足。
◆ 提出无需物理标记的一次性HMD与相机标定流程，简化多相机VR追踪系统的部署。
◆ 实现完整端到端动画系统，在NVIDIA RTX3080上达到60 FPS，并开源代码以支持复现和后续研究。</td></tr>
<tr><td>2026-11-02</td><td>SyncHeC: Markerless Spatio-Temporal Hand-Eye Calibration via Differentiable Rendering and Continuous-Time Joint Optimization<br><a href='http://arxiv.org/pdf/2611.02999'>论文</a></td><td>SyncHeC提出一种面向连续运动的无标记时空手眼标定框架，可在单条机器人轨迹中联合估计相机几何与图像—关节状态时间偏移。其核心是用密集可微渲染构建连续时间联合优化，并通过交替更新统一支持Eye-to-Hand、Eye-in-Hand和多相机标定。
◆ 采用连续时间正运动学，使传感器延迟成为可微变量，从而端到端优化时间偏移。
◆ 引入度量深度补充掩膜轮廓，增强无标记标定的几何约束与稳定性。
◆ 设计结合空间敏感性与时间激励的离线规划，提升短轨迹标定的可观测性和精度。
实验在7自由度机械臂上以6.5秒运动取得0.21厘米平移误差、0.34厘米触测误差和2.7毫秒延迟误差，较CM-Calib分别提升3.7倍和2.3倍，并在七种机械臂、四种深度传感器及策略部署中验证有效性，补偿延迟后成功率提升8.1个百分点。</td></tr>
<tr><td>2026-11-02</td><td>AnchorHEC: Targetless Hand-Eye Calibration of Wrist and Fixed Cameras<br><a href='http://arxiv.org/pdf/2611.02884'>论文</a> | <a href='https://hwanggb.github.io/AnchorHEC/'>代码</a></td><td>论文提出AnchorHEC，一个无需标定物的手眼标定框架，可在单一流程中同时标定腕部相机和固定相机，仅依赖RGB图像、正运动学FK和已知相机内参。该方法用FK与共享3D基础模型重建初始化两类相机，并通过FK约束的腕部图像BA抑制重建位姿和尺度误差；失败或内点不足时自适应放松FK与镜头参数约束，再以精化腕部变换和FK三角化度量点估计固定相机位姿。
◆统一单流程无目标同时标定腕部与固定相机，弥补现有场景法仅支持腕部相机的不足。
◆利用FK与共享3D基础模型重建联合初始化两类相机，无需标定靶标或机器人本体观测。
◆提出FK约束的腕部图像BA及失败或少内点时的自适应松弛策略，降低重建位姿、尺度和镜头参数误差影响。
◆通过精化腕部变换与FK三角化度量点估计固定相机位姿，并在仿真和物理机器人上验证显著降低误差（平移86.4%、旋转71.6%）。</td></tr>
<tr><td>2026-10-27</td><td>Generalizable Target-Less Joint Intrinsic-Extrinsic Camera-LiDAR Calibration using Deep Pixel-Point Correspondences<br><a href='http://arxiv.org/pdf/2610.37350'>论文</a></td><td>本文提出一种全自动、无目标的相机-LiDAR联合标定框架，可直接从原始图像和LiDAR扫描中联合估计相机内参、径向切向畸变及相机-LiDAR外参。
◆ 将基于深度像素点对应的无目标标定从校正图像扩展到原始相机，通过合成增强实现内参与畸变感知的对应学习。
◆ 在标定过程中迭代耦合对应预测与非线性优化，联合精化相机参数和相对传感器变换。
◆ 在未见KITTI配置和三个真实机器人平台上零样本验证，联合标定在恢复准确内参的同时提升了外参精度。
实验表明该方法优于依赖预标定相机的对应标定方法，并具备跨配置与跨平台的泛化能力。</td></tr>
<tr><td>2026-10-27</td><td>ActiveAlign: Aligning Egocentric Manipulation via Active Perception<br><a href='http://arxiv.org/pdf/2610.36859'>论文</a></td><td>本文针对Real2Sim2Real中被动感知导致real2sim差距的问题，提出基于主动感知的对齐框架ActiveAlign，通过机器人交互主动缩小仿真与现实差异。
◆ 提出ActiveAlign-Waving，利用主动手部运动与可微渲染完成手眼标定，减少未标定观测带来的对齐误差。
◆ 提出ActiveAlign-Touching，借助触觉反馈精化物体对齐，实现毫米级精度。
两个模块互补，共同提升real2sim对齐质量，使仿真表示更利于规划、可解释与安全执行。
作者还利用ActiveAlign-Waving为开源未标定机器人操作数据集整理仿真环境，并在真实Unitree G1上验证按按钮、移动滑块等毫米级细操作。
整体上，该工作将主动感知引入Real2Sim2Real对齐，为精细机器人操作提供可落地的校准与对齐方案。</td></tr>
<tr><td>2026-10-27</td><td>OmniGlimpse: Asymmetric Identity Memory for Online Multi-View Tracking<br><a href='http://arxiv.org/pdf/2610.36785'>论文</a></td><td>论文研究在线多视角身份维护OMIM：目标在每个视角仅初始化一次，之后不再提供身份标签，且不依赖离线场景训练或相机标定，需在遮挡和出视野情况下维持跨视角身份一致。为此提出OmniGlimpse非对称提议-验证框架，将自适应关联与稳定身份整合解耦。
◆表示层：用短期局部与跨视角证据在目标自适应空间生成关联提议，同时用冻结编码器定义的标准空间维护长期身份分布用于验证。
◆更新层：短期证据仅指导当前关联，自举后只有经过验证的观测才能更新持久记忆或驱动自适应。
◆在线机制：无需离线场景特定训练和标定，兼顾外观变化适应与可靠证据向稳定身份锚点的巩固。
实验在统一目标指定协议下，M3Track较最佳在线基线提升9.1 IDF1和22.1 CVIDF1，MvMHAT提升20.3和26.2，且IDF1超过离线训练参考并保持跨视角关联竞争力。</td></tr>
<tr><td>2026-10-26</td><td>Spectral fingerprint recognition of mobile signals via Rydberg atomic sensors<br><a href='http://arxiv.org/pdf/2610.35301'>论文</a></td><td>本文提出一种基于里德堡电磁诱导透明光谱与深度学习的量子移动信号分类框架，实现对真实无线信号的智能识别与频谱监测。
◆构建了涵盖蜂窝语音通话、Wi-Fi及三个商用手机品牌5G信号的频谱指纹数据集，并验证里德堡原子传感器用于移动信号分类的可行性。
◆采用卷积神经网络在该数据集上取得93.44%的初始基线分类准确率。
◆提出渐进微调策略持续适应由时间和环境变化引起的光谱漂移，使预训练模型在多样部署场景下保持稳健分类。
◆在蜂窝语音、Wi-Fi及其共存等动态无线条件下实现连续实时监测，60秒测量中获得87.67%的整体帧级识别准确率。
◆打通了里德堡原子射频传感与智能无线信号感知的路径，为实时频谱监测和量子射频感知应用提供新方案。</td></tr>
</tbody>
</table>
</div>

<h2 id='robot-vlm'>Robot VLM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-09</td><td>DeltaForge: A Post-hoc Mixture-of-Experts VLA for Multi-Domain Autonomous Driving<br><a href='http://arxiv.org/pdf/2611.11856'>论文</a></td><td>DeltaForge提出首个面向自动驾驶的事后混合专家VLA框架，仅用各域模型权重和小型代理集即可将N个独立微调的分域模型整合为单一多域模型。
◆利用同源基础模型微调更新间的共享结构，联合SVD将各权重更新分解为共享部分与微小域特定部分，使路由器只需处理域特定小分量，从而显著降低路由成本。
◆设计分别面向VLM推理专家和流匹配动力学专家的两个协作式clip级盲路由器，并基于代理数据集的软标签进行训练。
◆支持增量域扩展：新增域只需将其权重更新投影到共享基，无需端到端重训，并能泛化到未显式训练过的域组合。
在覆盖城市、越野、高速及汽车、卡车、ATV的六个域上，其精度接近各域专家，超过合并、路由、集中式和联邦式基线，且参数与计算成本接近单模型。</td></tr>
<tr><td>2026-11-09</td><td>Decoupled Asynchronous System for Humanoids (DASH): Latency-Agnostic Scaling of Vision-Language-Action Models for Humanoid Manipulation<br><a href='http://arxiv.org/pdf/2611.11854'>论文</a></td><td>论文提出DASH，将人形机器人VLA策略解耦为慢速视觉语言模型与快速动作头，使控制频率不再受骨干模型规模限制。
◆将策略拆分为System 2视觉语言模型和System 1流匹配动作头，并通过LCM协议并发运行，使控制率仅由动作头决定。
◆动作头融合冻结骨干提供的陈旧语义与自身ResNet编码器的新鲜视觉，缓解闭环控制中的观测滞后。
◆采用失同步训练，让动作头在训练阶段暴露于部署时遇到的语义陈旧性。
◆引入自适应时间聚合器，在可变推理延迟下对齐重叠动作块。
实验表明，DASH在异步RoboTwin基准中从0.8B到8B骨干均保持20Hz控制率，且成功率更高；真实人形灵巧手抓放任务也明显优于同步流水线。</td></tr>
<tr><td>2026-11-08</td><td>HINT-VLM: Humanoid Interactive Navigation over Rough Terrain with Embodiment-Grounded Vision-Language Model<br><a href='http://arxiv.org/pdf/2611.11665'>论文</a></td><td>论文面向人形机器人在户外崎岖杂乱地形中的可移动障碍物导航问题，提出HINT-VLM混合规划框架，将视觉语言模型的语义先验与机器人本体交互数据相结合。  
◆ 首次将NAMO问题拓展到崎岖地形，要求机器人联合推理地形可通行性与物体可移动性。  
◆ 利用高斯过程残差模型校正VLM给出的可移动性先验，形成基于本体的概率化可移动性估计。  
◆ 将上述概率估计嵌入层次化不确定性感知规划，使机器人能够预测性规划并安全高效地联合利用移动与操作能力。  
该方法代表了通过预测性可移动性推理和概率化VLM集成解决崎岖地形NAMO的首次尝试。</td></tr>
<tr><td>2026-11-08</td><td>MOSU2: Long-range Navigation System with Multi-modal Scene Understanding<br><a href='http://arxiv.org/pdf/2611.11148'>论文</a> | <a href='https://jinggm.github.io/mosu2/'>代码</a></td><td>MOSU2提出一种面向公共户外长距离导航的多模态场景理解系统，核心是将上下文推理与按需证据检索结合到两阶段轨迹选择中。  
◆ 设计两阶段轨迹选择机制，第一阶段判断交互是否未解决以及需要检索何种额外证据。  
◆ 仅当场景交互仍不确定时触发第二阶段，检索几何与动态信息并与场景上下文对齐以辅助导航决策。  
◆ 基于GPS路线规划跟随路线，并利用多模态可通行性分析过滤候选轨迹后再选择运动轨迹。  
◆ 将视觉语言模型的开放场景理解能力与实时导航所需的几何、运动证据按需结合，避免每步调用带来的高延迟。  
真实实验覆盖停止手势、施工区、人行横道及人车混行道路，导航成功率由61.8%提升至94.2%，条件检测准确率由72.2%提升至91.4%，决策延迟约为前代的2.2倍。</td></tr>
<tr><td>2026-11-08</td><td>SoftPAT3D: Physics-Augmented Text-to-3D Scene Generation with Deformables<br><a href='http://arxiv.org/pdf/2611.11087'>论文</a></td><td>SoftPAT3D提出了一个面向文本到3D场景生成的物理增强框架，首次将布料、毛绒玩具和绳索等可变形物体生成为物理有效、可直接仿真的场景实体，并保证其与家具、其他物体及自身无穿插接触。◆针对现有流程仅支持刚体且生成网格几何无效、自交、无静息形状和材料模型的问题，SoftPAT3D从物体制造逻辑构建静息形状，并通过材料库赋予可优化弹性参数。◆它将遮挡支撑区域重建为水密碰撞网格，把物体从支撑部位上方的可优化位置释放，在统一接触模型下驱动整个场景达到静态平衡，并用几何检查和视觉语言模型验证完成度。◆当场景不符合提示时，方法用放置网格搜索纠错，并利用同一接触能量可微仿真的伴随方法实现多物体联合放置及材料参数恢复与优化。◆该框架支持多体场景单次仿真平衡，也可仅由文本提示运行，在全部65个提示上均未产生不良穿插，并直接支持场景编辑和机器人操作。</td></tr>
<tr><td>2026-11-07</td><td>Selective Cooperative Perception via Blind Spot Reasoning and Agentic Dialogue with Vision-Language Models<br><a href='http://arxiv.org/pdf/2611.10819'>论文</a></td><td>论文针对多智能体交通环境中协同感知资源消耗大、难以规模化的问题，提出一种由视觉语言模型驱动的智能体框架，仅在安全关键场景和关键遮挡对象上选择性执行盲区推理与对话式协同感知。  
◆ 设计混合模型架构，融合传统目标检测、视觉语言推理和物理几何模块，以稳定感知、识别关键遮挡并对齐真实可见性约束。  
◆ 引入思维链提示机制，提升盲区推理与感知共享决策的可解释性和意图感知能力。  
◆ 基于城市交通中联网车辆的真实数据，系统比较四种先进视觉语言模型在驾驶关键盲区识别和对话共享上的表现。  
实验表明该方法在驾驶关键盲区检测上达到80%以上准确率、对话驱动感知共享成功率超过90%，为传统协同感知提供了可扩展、可解释且带宽高效的替代方案，并为未来车联网智能体通信设计提供新见解。</td></tr>
<tr><td>2026-11-07</td><td>Locating and Repairing Domain Shift in VLM Trajectory Planning<br><a href='http://arxiv.org/pdf/2611.10720'>论文</a></td><td>论文挑战将VLM轨迹规划的跨城域偏移视为单一量并用统一对齐或单点编辑处理的既有观点。  
◆提出域偏移在模态与层两个维度上具有结构化规律，应定位后只修复发生偏移处。  
◆通过激活修补发现图像与文本token的偏移模式不同，且逐层偏移划分随架构而异但对数据集稳定。  
◆提出MoLaRx框架，用因果重要性分数将偏移估计为模态-层张量并划分功能层区，再用CISR为各区匹配MMD、LoRA或冻结等算子。  
◆在三类VLM和两个跨城基准的六种主表设置中取得最低跨城轨迹误差差距，同时可训练参数减少50-60%、推理延迟降低8.4-10.9 ms。  
这表明显式定位并结构化修复优于统一MMD适配。</td></tr>
<tr><td>2026-11-07</td><td>CPNav: Calibrated Vision-Language Navigation for Object-Goal Search in Unseen Environments<br><a href='http://arxiv.org/pdf/2611.10366'>论文</a> | <a href='https://github.com/practice-lab-ucla/CPnav'>代码</a></td><td>论文提出CPNav，一种面向未见环境中物体目标搜索的无地图视觉语言导航框架，核心是将碰撞感知规划与统计校准的VLM动作评分相结合。方法从RGB-D输入构建可导航地图、生成无碰撞运动基元，并查询两个VLM分别进行目标检测和动作评分。◆提出碰撞感知规划与校准VLM评分融合的无地图物体目标导航框架。◆利用共形预测对VLM动作分数进行离线校准，且模型无关，可包装任意VLM策略并提供用户指定风险下的有限样本保证。◆设计带回溯的树状探索过程获取oracle动作，并在在线阶段记录备选动作以支持回溯。实验表明，CPNav在Habitat仿真和真实机器人部署中均优于未校准基线，显著提升成功率和SPL。</td></tr>
<tr><td>2026-11-06</td><td>Seeing What Matters: Benchmarking Task-Conditioned Actionable Spatial Belief for Manipulation<br><a href='http://arxiv.org/pdf/2611.09794'>论文</a></td><td>本文提出Seeing What Matters基准，将操作中的空间推理重新定义为任务条件下的可操作空间信念，即模型能否获取使当前指令可执行的特定证据。
◆构建覆盖咖啡台、抽屉柜和微波炉三域的860个冻结案例，扩展为逾11.5万评估回合，并设置闭环可操作性与同物体功能OOD泛化两种协议。
◆每个案例配对候选RGB视图、操作指令、共享脚本技能和隐藏后置条件，直接评估视图选择策略是否取得指令真正需要的观察。
◆提供诊断参考管线，维护空间功能信念状态并按缺失证据排序视图；消融功能或指令绑定组件后性能近零。
实验显示参考管线在主要预算下达98.8%闭环和98.9%功能OOD成功，而七个视觉语言模型仅26-43%，且打乱视觉分数使性能骤降至15%/11%。
这些结果说明操作中的空间信念应按是否获取当前指令所需证据来评估，而非按场景级完整性评估。</td></tr>
<tr><td>2026-11-06</td><td>PRISM: Primitive Routing via In-context Skill Mixing for Retentive VLA Adaptation<br><a href='http://arxiv.org/pdf/2611.08917'>论文</a></td><td>◆论文发现不同技能的低秩更新占据可区分低维子空间，复合任务LoRA约一半Frobenius能量集中其中，为参数级技能原语提供几何依据。
◆提出PRISM将可复用技能存为原语库中的专用低秩动作专家适配器，并加入技能特定低秩残差，推理时由逐chunk的VLM条件路由器混合调用。
◆设计路由器读取前缀表示以跟踪任务阶段，并由确定性的任务条件、动作导出oracle生成逐chunk标签监督。
◆复合训练中冻结所有原语，仅更新视觉编码器、语言LoRA、技能残差、路由器及共享动作投影和时间MLP，从构造上保留基础技能适配器。
◆在RoboCasa365上取得56.43%原子技能成功率和20.00%长程复合成功率，优于π0.5-LoRA两阶段微调的17.86%和17.50%，并在AgileX PIPER真机上验证。</td></tr>
<tr><td>2026-11-06</td><td>HomeLoop: A Simulation Framework and Benchmark for Robot-IoT Coordination in Everyday Domestic Assistance and Safety<br><a href='http://arxiv.org/pdf/2611.08914'>论文</a></td><td>本文提出基于Isaac Sim的HomeLoop仿真框架与基准，面向家庭日常辅助与安全中的机器人-IoT协同，统一建模机器人、联网设备与可穿戴设备、模拟居民与访客、故障传感器及动态危险。
◆ 构建机器人-IoT-居民-危险耦合且含故障传感与演化风险的日常家庭仿真环境。
◆ 设计五类20个任务，使同一警报可对应不同成因，覆盖真实家庭危险与需求。
◆ 引入时序逻辑运行时监控，联合最终结果与过程动作评分，并为每个动作设定成本。
◆ 评估六个VLM，最佳家族均衡分为61.9%，揭示过度反应模式：禁止干预失败超过漏干预两倍，常未查因先关炉。
◆ 发布2100种可自动布置布局、5种机器人本体和20类联网设备，支撑协同、长期记忆、主动协助与隐私安全研究。</td></tr>
<tr><td>2026-11-05</td><td>VFlash: Fast, Accurate Visual Planning via Flash Primitive Decoding<br><a href='http://arxiv.org/pdf/2611.08449'>论文</a></td><td>VFlash提出一种基于Flash Primitive Decoding的快速、准确视觉规划方法，用点、框和轨迹等视觉基元表示空间目标与运动。
◆ 利用视觉基元的已知结构，以轻量级drafter单次前向联合预测整个基元的坐标，而非逐坐标自回归生成。
◆ 解码布局可自适应基元类型、维度和长度，兼顾紧凑边界框与长且变长的轨迹。
◆ 训练基于标注基元并直接接受结构有效的预测，不要求复现自回归模型的精确token序列。
在2D和3D机器人轨迹任务中，VFlash相对自回归解码持续降低预测误差，3D点运动预测初步单次rollout约快25倍。
以VFlash规划为条件的world action model在四个MolmoSpaces任务套件上平均成功率达70.2%，高于基线的62.6%。</td></tr>
<tr><td>2026-11-05</td><td>RM-VLM: From Natural-Language Task Descriptions to Vision-Grounded Reward Machines<br><a href='http://arxiv.org/pdf/2611.08308'>论文</a></td><td>RM-VLM针对奖励机依赖人工设计标注函数、难以扩展到新环境的问题，提出从自然语言任务描述直接构建视觉落地奖励机的方法。它先由大语言模型根据自然语言生成奖励机，再由视觉语言模型作为标注函数，在图像观测上把奖励机命题落地。
◆ 用LLM自动生成奖励机，替代手工设计任务时序结构。
◆ 用VLM充当标注函数，实现奖励机命题在图像观测上的视觉落地，消除逐环境手工命题grounding。
◆ 设计基于VLM的价值函数估计器，评估智能体在各奖励机转移上的进展并生成稠密奖励。
作者在非马尔可夫格子世界导航、机器人操作和3D物体收集中验证，RM-VLM任务成功率均高于现有基于VLM的奖励方法。</td></tr>
<tr><td>2026-11-05</td><td>HITCH: Teaching a Vision-Language Model to Operate a Humanoid through a Whole-Body Harness<br><a href='http://arxiv.org/pdf/2611.08039'>论文</a></td><td>本文提出HITCH，为人形机器人构建让视觉语言模型可靠感知与全身控制的接口，并用教师轨迹微调VLM使其学会操作身体。
◆ 感知接口将VLM在图像中选定的任意点返回为三维位置，使模型能直接测量场景。
◆ 执行接口把骨盆、躯干、手、行走和注视命令经学习跟踪器转化为全身运动，提升命令执行准确性。
◆ 通过五个基础任务的教师策略轨迹微调VLM，无需任务特定轨迹也能迁移全身操作知识。
实验表明，微调模型在SIMPLE和HumanoidArena分别完成51%和42.5%，每任务加五条轨迹后SIMPLE达95%。
在真实G1上，无真实训练数据即可搬箱并走到目标。</td></tr>
<tr><td>2026-11-05</td><td>PhySA: Decoupling Aesthetic and Physical Rewards for Humanoid Locomotion<br><a href='http://arxiv.org/pdf/2611.07679'>论文</a></td><td>论文揭示视觉语言模型的美学偏好与物理平滑性相悖：在四个生产VLM中，关节加速度越高的片段美学评分越高，平均Pearson相关系数为+0.66。为此提出PhySA，将美学奖励与物理平滑奖励解耦为两个可独立移除的奖励通道。
◆ 将稀疏、异步的VLM美学评分作为独立奖励通道，无需任务专用特征工程。
◆ 引入由模拟器状态触发的相位校正通道，动态调整物理惩罚权重。
消融表明平滑性增益主要来自校正通道；在MuJoCo Humanoid-v5上，PhySA相较PPO、Text2Reward和Eureka将关节加速度降低26%至32%，但回合长度缩短，单次扩展运行相对Prompt2Policy降低59.5%，三随机种子复现仅降低7.2%且不显著。其增益未能迁移至IsaacLab或Unitree G1，即使重新缩放平滑项。</td></tr>
</tbody>
</table>
</div>

<h2 id='robot-visual-semantic-recognition'>Robot Visual Semantic Recognition</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-09-30</td><td>NaviScale: Generating Large-Scale Semantic Map Datasets for Object Navigation<br><a href='http://arxiv.org/pdf/2609.27218'>论文</a></td><td>NaviScale提出面向语义地图ObjectNav的大规模数据生成框架，预测器仅需部分与完整语义地图配对训练，无需为每个样本重建完整3D环境。
◆ 组合真实住宅平面图与MP3D、HM3DSem的房间级语义和障碍地图，低成本生成大规模多样化语义地图数据。
◆ 房间间缩放改变平面图结构，提升平面图级布局多样性。
◆ 房间内缩放按房间类别匹配不同房间地图，填充同一固定平面图以增加房间组合多样性。
◆ VisRC通过射线投射将组合地图转为部分观测，并显式考虑视场、感知范围和遮挡。
生成192,000张语义地图、24,000个平面图和12,794处房产；在HM3D达64.3% SR/34.8% SPL，MP3D达43.1% SR/16.8% SPL，且不改变预测架构，并验证地图质量、语义分割误差和实机部署。</td></tr>
</tbody>
</table>
</div>

<h2 id='robot-vpr'>Robot VPR</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5363</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4864</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2489</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1665</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1630</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1540</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1380</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1321</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1133</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>1109</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>955</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>819</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>785</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>751</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>748</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>735</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>700</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>674</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>638</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>632</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>626</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>594</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>573</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>546</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>515</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>481</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>469</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>376</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>350</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>282</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>275</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>260</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>243</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>234</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>230</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>223</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>222</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>215</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>152</td><td>iBTC</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2886</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1681</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1370</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1099</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1062</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>887</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>714</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>674</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>671</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>623</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>614</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>579</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>579</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>571</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>554</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>523</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>522</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>466</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>458</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>456</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>348</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>187</td><td>Implementation for safe low altitude navigation in</td></tr>
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
> 更新于: 2026.11.10
