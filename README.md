# 计算机视觉领域最新论文 (2026.08.11)

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
<tr><td>2026-08-06</td><td>A Low-Latency ASIC Architecture for Real-Time Line Segment Detection<br><a href='http://arxiv.org/pdf/2608.06439'>论文</a></td><td>本文针对嵌入式视觉中的实时线段检测任务，提出了一种基于步长算法的低延迟ASIC架构。传统深度学习精度高但资源消耗大，经典算法延迟不固定且与内容相关，难以满足资源受限平台的需求。该架构完全流水线化，每个时钟周期处理一个像素，延迟完全确定，在45nm CMOS工艺下综合实现面积为0.412 mm²、VGA分辨率下可达325帧/秒、Full HD下48帧/秒的吞吐量，功耗仅25.54 mW，125 MHz时性能进一步提升至406 FPS。相比基于线段霍夫变换的90nm ASIC实现，功耗降低49%，帧率提升超过1.6倍。

◆ 基于寄存器的行缓冲与数据复用机制，减少片外存储访问
◆ 采用无乘法器的MCM（多常量乘法）实现滤波，降低硬件复杂度与功耗
◆ 8类角度量化策略，简化角度分类与匹配逻辑
◆ 类CAM的关联存储结构实现单周期匹配，提升关键路径效率
◆ 优化的重复线段去除机制，避免冗余输出带来的额外开销...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-06</td><td>KILVO: Kinematic-Inertial-LiDAR-Visual Odometry with Robust Multimodal Adaptation for Humanoid Robots<br><a href='http://arxiv.org/pdf/2608.05647'>论文</a></td><td>本文提出KILVO，一种面向人形机器人的运动学-惯性-激光-视觉里程计系统。该方法将关节编码器、IMU、LiDAR和相机在异步-顺序混合误差状态迭代卡尔曼滤波(ESIKF)框架下进行紧耦合融合，其中惯性数据用于预测，腿部运动学信息以高频率异步处理以提供本体感受约束，而LiDAR和视觉则按顺序进行外感受更新。

◆提出首个面向人形机器人的四模态紧耦合里程计算法，统一融合关节编码器、IMU、LiDAR与相机，适配平台特性。
◆设计异步-顺序混合ESIKF架构，惯性高频预测、腿部运动学异步处理、LiDAR与视觉顺序外感受更新，兼顾效率与精度。
◆具备多模态自适应能力，可针对单一或多传感器退化与失效进行鲁棒切换，无需额外硬件。
◆开发紧凑的接触估计模块，与状态估计共享信息，无需额外传感器即可辅助里程计精度提升。
在公开数据集与多平台、多步态的真实场景实验中，KILVO在精度、效率和输出频率方面均优于现有融合方法。</td></tr>
<tr><td>2026-08-04</td><td>SLAMFormer-$\infty$: Infinite SLAM Transformer for Unbounded Frontend and Backend Processing<br><a href='http://arxiv.org/pdf/2608.03429'>论文</a></td><td>SLAMFormer-∞是首个支持无显式距离限制的前端与后端统一处理的几何Transformer，它突破了传统SLAM系统对范围扩展性的瓶颈。论文提出用记忆条件来定义输入帧的灵活坐标系和尺度，取代了以第一帧为锚点的传统建模范式，使结构条件表达更加丰富灵活。

◆ 创新点一：提出基于记忆条件的灵活坐标系与尺度定义，摆脱对首帧锚点的依赖，实现无界长程处理能力。

◆ 创新点二：前端在保持局部高效计算的同时，后端能够联合优化长程轨迹与场景几何，实现全局一致性。

◆ 创新点三：在超过17公里的超长轨迹上成功运行，并在大规模数据集的轨迹估计与场景重建任务中取得领先或极具竞争力的性能，展现了出色的泛化能力。</td></tr>
<tr><td>2026-08-03</td><td>CHOW-SLAM: Compact Hybrid Representation with Complementary Overlap Window Optimization for RGB-D SLAM<br><a href='http://arxiv.org/pdf/2608.01914'>论文</a> | <a href='https://github.com/jinjidexiaohuoban/CHOW-SLAM'>代码</a></td><td>CHOW-SLAM提出了一种面向RGB-D SLAM的紧凑混合表示与互补重叠窗口优化框架,旨在解决现有NeRF-based SLAM系统在有限在线资源下难以同时构建空间与时间两类约束的问题。空间层面,该方法将参数化分支与哈希分支按平面与网格进行多尺度组织,并通过统一多输出解码器对齐TSDF与密度诱导的光线终止分布,从而在紧凑参数预算下保持几何与外观的判别性。时间层面,设计互补重叠窗口策略,在固定预算内保留近期帧、选取高重叠局部帧并引入时序分散的历史关键帧,结合损失感知的关键帧插入与BA调度,使优化免受短时重叠或弱关联历史观测的支配。整体流程采用ORB前端进行位姿初始化与跟踪,再以神经渲染优化提升跟踪稳定性。

◆ 提出参数化-哈希(P-H)混合紧凑表示,按平面与网格跨尺度组织,并通过统一多输出解码器对齐TSDF与密度的光线终止分布,在紧凑参数预算下保持几何与外观判别性。
◆ 设计互补重叠窗口优化策略,结合近期帧、高重叠局部帧与时序分散的历史关键帧,并以损失感知的关键帧插入与BA调度自适应调整优化强度。
◆ 集成ORB前端跟踪与神经渲染优化,先进行几何位姿初始化,再通过渲染损失细化位姿,从而提升跟踪稳定性与精度。</td></tr>
<tr><td>2026-08-03</td><td>UniSim-SLAM: Feed-Forward SLAM with Unified Sim(3) Optimization<br><a href='http://arxiv.org/pdf/2608.01706'>论文</a> | <a href='https://vision3d-lab.github.io/unisim-slam/'>代码</a></td><td>UniSim-SLAM 是一套面向几何基础模型的前馈式 SLAM 系统，旨在解决现有方法在长序列下因输入视图差异导致的轨迹漂移和几何不一致问题。系统采用前后端协同架构，前端运行轻量级的两视图关键帧跟踪以保证低延迟，后端则周期性触发多视图子图细化以提供更强的几何约束。

◆ 提出统一多层级 Sim(3) 因子图，联合优化全局关键帧位姿与子图位姿，融合时序两视图里程计边、视图到子图的桥接边以及子图间的连接与尺度约束，使异构局部坐标和尺度下产生的预测能在统一的相似变换空间内保持一致。

◆ 引入基于深度统计量的尺度锚定机制，将多视图子图预测中的尺度信息可靠地传递到全局因子图中，从而在无需标定的情况下获得尺度一致的轨迹。

◆ 在 TUM RGB-D 和 7-Scenes 无标定场景下达到当时最优精度，轨迹误差分别降低 38.5% 和 45.9%，验证了方法的有效性。</td></tr>
<tr><td>2026-08-02</td><td>Stipple: Real-Time Incremental Gaussian Splatting with Visual-Inertial Tracking<br><a href='http://arxiv.org/pdf/2608.00931'>论文</a></td><td>本文提出Stipple方法,将视觉惯性跟踪系统与3D高斯泼溅技术结合,实现了实时增量式的三维场景重建。针对3DGS预处理和训练步骤繁重、难以满足机器人和XR应用实时性需求的问题,作者通过利用Basalt视觉惯性里程计提供的高质量位姿和深度信息,设计了一种新的增量训练策略,避免了大量离线预处理。系统在跟踪线程并行运行重建流程,GPU渲染与跟踪解耦,显著提升了效率。该方法展示了SLAM与3DGS的互补价值,为实时三维重建提供了一条有前景的技术路线。

核心创新点:

◆ 基于Basalt视觉惯性跟踪系统与Brush(GPU无关的Rust实现)构建紧耦合的实时框架,直接复用跟踪线程生成的位姿与深度信息,大幅减少3DGS传统预处理开销。

◆ 提出增量式训练策略,替代3DGS中耗时的全局优化步骤,使得高斯参数可随新数据持续更新,适合在线重建场景。

◆ 将跟踪与重建并行化,设计高效的流水线使训练在跟踪线程运行的同时同步进行,实现真正的实时三维重建。

◆ 引入多种实际工程优化,包括跨平台GPU抽象和内存管理改进,使整个管道能够在资源受限的机器人或XR设备上实时运行。</td></tr>
<tr><td>2026-08-02</td><td>Look Up and Look Back: Hidden Attention and Latent Orientation in a Frozen Foundation Model for Panoramic SLAM<br><a href='http://arxiv.org/pdf/2608.00925'>论文</a></td><td>本文针对单目全景SLAM中相机倾斜、尺度漂移和错误回环等问题，提出HALO-SLAM方法，核心贡献在于挖掘冻结全景几何基础模型的内部隐式线索。◆发现中间token隐式编码相机帧下的重力方向，无需IMU即可实现球面正立规范化。◆发现跨视图注意力可作为潜在回访地点的兼容性线索，并据此设计代价感知的三阶段级联回环检测（DBoW2事件检索+注意力兼容性过滤+稠密几何验证）。◆利用对称子图增强生成像素对齐的3D-3D对应，估计稳健的Sim(3)约束并与顺序约束联合优化。在5个真实全景基准的125条序列上达到100%成功率，ATE较最佳ERP原生基线降低30-88%。</td></tr>
<tr><td>2026-07-29</td><td>VidMap: Exploiting Temporal Structure for Video-Based Structure-from-Motion<br><a href='http://arxiv.org/pdf/2607.27194'>论文</a> | <a href='https://github.com/cvg/vidmap'>代码</a></td><td>本文针对无约束视频的相机标定与度量位姿恢复问题，提出VidMap系统，旨在弥合SLAM与SfM两大主流方法之间的鸿沟。现有SLAM方法对初始化敏感、依赖已知标定，而传统SfM忽略图像时序且难以应对视觉对称与极端运动。VidMap融合了SLAM的强时序约束与离线SfM的全局优化灵活性，实现了对任意长且未标定视频的度量重建。系统利用宽基线稠密图像匹配技术，并以时序信息作为可靠的闭环检测核心线索，同时在全局优化中引入单目深度先验以恢复真实尺度。实验表明，该方法在极端运动和视觉对称等挑战性场景下，显著优于当前最先进的SLAM与SfM方法。

◆ 提出混合框架，将SLAM的时序约束与SfM的全局优化相结合，实现未标定长视频的鲁棒度量重建。
◆ 将时序顺序作为闭环检测的一等公民，提升对称场景与极端运动下的关联可靠性。
◆ 引入宽基线稠密图像匹配，增强跨帧对应关系的精度与覆盖范围。
◆ 在全局优化中融入单目度量深度先验，无需已知标定即可恢复真实尺度。</td></tr>
<tr><td>2026-07-28</td><td>HiFi-UMI: Learning Deployable Manipulation Policies from High-Fidelity UMI Data Alone<br><a href='http://arxiv.org/pdf/2607.25895'>论文</a></td><td>HiFi-UMI提出了一种便携式机器人操作数据采集系统，旨在解决高质量与可扩展性难以兼得的瓶颈问题。系统通过协同设计轨迹精度、夹爪间相对位姿、时钟同步与视场，实现了无需外部追踪设施下3毫米的工作空间末端执行器精度。

◆采用头戴式离线立体惯性SLAM，并直接利用原生（而非重建）的夹爪间相对位姿，保证运动学一致性。
◆通过共享的微秒级GPIO触发器实现多相机硬件级时间同步，显著优于传统软件同步。
◆每只手配置两枚广角相机，覆盖约200度视场，最大限度减少遮挡并提升感知鲁棒性。
◆首次实现&quot;零真机后训练&quot;，仅凭HiFi-UMI数据微调即可在真实机器人上部署，并在多种VLA与世界-动作模型上达到与同域遥操作相当的性能。
◆开源HiFi-UMI-2K数据集，包含2000小时微秒同步、超广角演示数据，每条轨迹经仿真回放自动重建与验证，为机器人学习社区提供大规模高保真资源。</td></tr>
<tr><td>2026-07-28</td><td>HOME: Robust Hough-space Matching Method for Structured and Textureless Videos<br><a href='http://arxiv.org/pdf/2607.25389'>论文</a></td><td>HOME论文针对机器人在结构化或弱纹理环境中传统点特征（如ORB）易失效的问题，提出了一种超轻量、免训练的特征匹配框架。其核心思想是将图像变换到霍夫空间，将全局线性结构映射为稳定的局部极值点作为关键点，从而将复杂的线匹配问题转化为高效的一维点匹配问题。

◆ 提出HOME框架，利用霍夫空间将线匹配降维为一维点匹配，免训练且计算开销极低，适合实时边缘端机器人应用。

◆ 设计了一种一维径向描述子，数学上保证旋转与平移不变性，无需显式方向估计，显著提升了效率。

◆ 将该匹配引擎应用于单应性估计，在点特征失效的结构化、弱纹理场景中实现鲁棒配准，匹配速度大幅优于现有基于线段的方法。

◆ 当前聚焦于单应性估计作为概念验证，未来可拓展至完整的三维位姿估计，具有较大应用潜力。</td></tr>
<tr><td>2026-07-27</td><td>NSL-SLAM: High-Fidelity Neural Structured-Light Depth for Practical SLAM and Reconstruction<br><a href='http://arxiv.org/pdf/2607.24495'>论文</a></td><td>NSL-SLAM是一种面向高保真结构光深度传感的实用SLAM系统。
◆ 将单目深度先验融入结构光立体解码，相对NSL基线将深度RMSE降低35%。
◆ 提出以深度为核心的SLAM流程，以稠密结构光为主跟踪信号，仅补充稀疏视觉对应与轻量级BA以处理退化场景和长距离漂移。
◆ 深度估计与系统设计相互增强：更强深度使简洁流程有效，深度中心化设计则保障重建质量。
实验在Replica-SL上取得最佳跟踪精度并提升重建F-score 1.6分，在8个真实场景中是唯一避免灾难性失败的方法，轨迹偏差较基线降低43.3%，系统以20.9 FPS实时运行。</td></tr>
<tr><td>2026-07-27</td><td>SHARE: Towards Head-Mounted AR with User-Centric SLAM in Shared Human-Robot Workspaces<br><a href='http://arxiv.org/pdf/2607.23901'>论文</a></td><td>针对共享人机协作空间中AR用户延迟较高、边缘资源统一分配不合理的问题，本文设计并实现了以用户为中心的SLAM系统SHARE，优先保障头戴AR用户的交互体验。
◆ 创新点一：首次构建面向HRC智能体的体验模型，能够根据机器人与AR用户的异构延迟需求，自适应调整传输优先级。
◆ 创新点二：利用共享工作空间中多智能体视觉特征的冗余性削减边缘计算开销，从而显著降低端到端延迟。
系统在商用AR头显和地面机器人上进行了真实部署，结果显示AR用户平均延迟降至13.22毫秒，较基线降低43.3%。
同时机器人跟踪精度保持在2厘米以内，用户研究进一步验证了主观体验的统计学显著提升。</td></tr>
<tr><td>2026-07-25</td><td>Semantic Semi-Incremental Data-Association-Free Object SLAM<br><a href='http://arxiv.org/pdf/2607.23384'>论文</a></td><td>本文提出了一种语义半增量无数据关联的物体SLAM框架,旨在解决传统SLAM中数据关联难题。该框架能够联合估计数据关联、机器人位姿、路标位置和路标语义,充分利用神经网络物体检测器提供的类别标签和视觉基础模型提取的实值特征向量等多模态语义信息。在合成数据和真实数据集上的实验表明,该方法在两种语义信息下均显著优于强基线方法。

核心创新点如下:

◆ 提出了通用的无数据关联SLAM框架,将数据关联、位姿估计、路标位置与语义联合建模,利用语义信息辅助数据关联,形成二者的协同优化机制。

◆ 采用半增量估计策略,在保证精度的同时提升计算效率,平衡了批量优化与增量方法的优劣。

◆ 针对路标数量估计这一关键问题,给出了原则性的理论依据、实用准则和启发式方法,增强了框架的可解释性和工程可用性。</td></tr>
<tr><td>2026-07-24</td><td>Mag4D-SLAM Dataset: A Repeated-Traversal Multi-Modal 4D Geomagnetic Dataset for Localization and Mapping<br><a href='http://arxiv.org/pdf/2607.21986'>论文</a></td><td>Mag4D-SLAM是首个面向户外场景的大规模地磁SLAM数据集,填补了现有地磁数据集局限于小规模室内环境、缺乏多模态同步与高精度位姿真值的空白。该数据集包含14条序列、总里程超过18公里,同步采集了LiDAR、相机、IMU、三轴磁力计和GNSS数据,并提供SE(3)精度的6自由度真值位姿。论文通过在校园结构化路径上开展昼夜配对、正反向重复采集的实验设计,系统分析了地磁场的可重复性、无漂移全局航向估计能力以及位置区分性的磁特征三个核心性质。数据集旨在支持偏航漂移抑制、磁回环检测以及长期定位等研究方向,并探索地磁感知如何作为视觉与LiDAR的互补或退化环境下的替代线索。

◆ 提出首个大规模户外地磁SLAM数据集Mag4D-SLAM,同步集成LiDAR、相机、IMU、磁力计和GNSS五种传感器并提供SE(3)真值。
◆ 引入昼夜配对、正反向重复采集的实验协议,使地磁信号的时间稳定性与方向不变性可被定量评估。
◆ 通过重复遍历实验验证地磁场的跨会话可重复性、无漂移全局航向估计及位置判别性磁签名三大特性。
◆ 公开数据集以推动偏航漂移抑制、磁回环检测及GN拒止下长期定位等开放问题研究。</td></tr>
<tr><td>2026-07-23</td><td>GLAM-SLAM: Real-time Gaussian Large-scale Mapping via Flow Densification and Spatial Decomposition<br><a href='http://arxiv.org/pdf/2607.21416'>论文</a></td><td>GLAM-SLAM是一个面向大尺度室外场景的实时单目SLAM系统，针对现有基于3D高斯泼溅的SLAM方法在长序列下内存爆炸、无法实时或重建质量差的问题，提出了一套完整的解耦式解决方案。系统前端采用基于特征的传统SLAM实现轻量跟踪，后端则引入结构化稀疏锚点网格来管理高斯表示，从而保证长程场景的连贯性与可扩展性。

◆针对3DGS需要稠密初始化的难题，提出基于极线约束的流式稠密锚定策略，通过几何约束为跟踪到的稀疏特征生成可靠的初始点云，无需依赖深度传感器即可满足高斯泼溅的初始化需求。

◆将建图问题建模为多场景问题，提出场景分区策略，在每个子场景内利用MLP初始化生成局部化高斯表示，引入强空间归纳偏置，显著提升重建的几何一致性与细节质量。

在KITTI Odometry、Oxford RobotCar和M&#x27;alaga等多个长序列室外数据集上的实验表明，该方法在保持实时性能的前提下，重建质量较次优方法提升约15%，并能有效扩展到更长序列。代码已开源，具有重要的社区价值。</td></tr>
<tr><td>2026-07-22</td><td>DINS-IO: Learned Inertial Odometry via Differentiable INS Consistency<br><a href='http://arxiv.org/pdf/2607.20232'>论文</a></td><td>本文提出DINS-IO，一种无需位置真值、直接从原始IMU数据学习惯性里程计的自监督框架。
◆核心洞察：捷联惯导速度递推构成强可微一致性先验，预测的体坐标系速度旋转至导航系后应与积分比力一致，仅差未知初速度与常值加速度计偏差。
◆将上述约束建模为滑动窗口最小二乘问题，引入全局共享偏差并给出闭式解，使求解残差作为自监督损失，梯度可经解析解回传至网络。
◆设计高频网络按IMU采样率输出稠密体坐标系速度，从而为每个样本提供约束。
◆针对自监督网络缺乏度量标定的问题，仅用少量标注轨迹直接监督体坐标系速度，并只微调低秩LoRA模块完成度量校准。
实验表明，以极少量标签自监督预训练加微调即可匹配或超越全监督基线方法。</td></tr>
<tr><td>2026-07-21</td><td>Identifying and Determining Atmospheric Parameters of BHB Stars Based on LAMOST DR11<br><a href='http://arxiv.org/pdf/2607.19175'>论文</a></td><td>本文基于LAMOST DR11数据,系统搜索并证认了13988条BHB(蓝水平支)恒星光谱,对应10236颗独立的BHB星,识别率约80%–90%,污染率低于10%,为银河系晕族子结构与运动学研究提供了大样本基础。研究者采用数据驱动的SLAM方法估算大气参数,并首次明确证实了加入色指数信息能有效打破有效温度与表面重力之间的简并,显著提升参数估计精度。样本在[Fe/H]分布上呈现明显鼓包,且多数金属富集的BHB星属于银盘族,这一发现为BHB星与薄盘/厚盘星族的关联提供了重要线索。论文还额外提供了4282颗蓝离散星的大气参数,扩展了双星演化研究的样本规模。

◆ 基于LAMOST DR11构建了目前最大的BHB星均匀样本(10236颗),识别率与纯度均处于领先水平。
◆ 创新性地在光谱标注中引入色指数,有效解决了Teff–log g简并难题,提升了大气参数测定精度。
◆ 揭示了金属富集BHB星与银盘族的关联,为银河系化学-动力学演化提供了新观测约束。</td></tr>
<tr><td>2026-07-20</td><td>Lifelong Localization in Dynamic Indoor Environments Combining Odometry with Sparse Distance Sampling<br><a href='http://arxiv.org/pdf/2607.17852'>论文</a></td><td>本文提出了一种面向动态室内环境的终身定位框架，通过融合机器人里程计与稀疏距离采样实现鲁棒定位。该方法利用少量距离样本构建位置先验，能实时解决机器人绑架问题（kidnap problem），并能在时间维度上将该先验与里程计持续融合，逐步收敛至机器人真实位姿。

◆ 仅需16个稀疏距离样本即可达到接近完整LiDAR SLAM的定位精度，显著降低传感器成本、存储空间和传输带宽需求。
◆ 基于真实环境数据洞察，对动态障碍进行显式建模与学习，使框架在静态环境以及动态变化已被正确学习的场景中均具备可证明的收敛性保证。
◆ 借助稀疏距离采样替代高密度扫描，兼顾隐私保护与计算效率，适用于资源受限或对隐私敏感的实际部署场景。</td></tr>
<tr><td>2026-07-20</td><td>SLAM in Low-Light Environments: Project Report<br><a href='http://arxiv.org/pdf/2607.17699'>论文</a></td><td>本文系统评估了RGB相机在低光照环境下进行SLAM的极限性能。研究团队选取了六种代表性SLAM系统,涵盖特征点法、直接法、滤波法与学习方法,在LaMARia五个不同难度与光照条件序列上进行基准测试,并结合绝对位姿误差、相对位姿误差和控制点召回率进行多维评估。

◆首次对跨范式的六种主流SLAM系统在统一低光照基准下进行系统性对比,填补了现有研究在低光RGB-SLAM性能边界上的认知空白。

◆揭示了惯性融合与全局优化是低光环境下稳定跟踪的两个必要条件,只有同时具备二者的Kimera-VIO才能完整跟踪所有序列。

◆明确指出现有方法的不足之处:经典单目流程(ORB-SLAM3、DSO)与滤波法(OpenVINS)在低光下普遍失败或发散,即便能跟踪的DPVO和DPV-SLAM也产生约100米的绝对误差。

◆为未来低光SLAM研究指明方向,即发展低光专用的学习前端或重新引入多模态互补传感,具有重要的实践指导意义。</td></tr>
<tr><td>2026-07-20</td><td>AnythingReality: Robust Online Gaussian Splatting SLAM for Open-Vocabulary VR Scene Exploration<br><a href='http://arxiv.org/pdf/2607.09260'>论文</a></td><td>本文提出AnythingReality系统，首次将在线3D高斯泼溅、实时VR探索与语音驱动的视觉语言模型交互三者进行端到端集成，面向开放词汇VR场景探索任务。
◆ 采用ORB-SLAM3位姿估计与在线高斯重建相结合的鲁棒架构，专门针对含噪声的真实数据进行设计，打破了以往方法依赖干净深度或外部位姿的假设
◆ 构建支持增量重建的VR沉浸式探索管线，实现对动态生成场景的实时交互式浏览
◆ 设计语音驱动的语义模块，可转录语音指令、生成场景描述并自动记录兴趣点
实验结果表明，该方法在自建数据集与TUM-RGBD上的图像质量均显著优于当前最优的在线高斯泼溅方法（PSNR最高提升14.5%，LPIPS最多降低21.6%），并通过质量-速度可调配置保持可比或更优的帧率，最终实现了88%的VLM目标识别率，验证了开放词汇交互的有效性。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-06</td><td>Confidence matters: Leveraging Multi-view Geometric Priors for GS-based Reconstruction<br><a href='http://arxiv.org/pdf/2608.06117'>论文</a></td><td>本文针对3D高斯溅射(3DGS)在几何重建尤其是高镜面物体上表现欠佳的问题，系统研究将预测的法线和深度图等几何先验融入3DGS框架的方案。

◆研究发现多视图几何预测器（如视觉几何接地Transformer VGGT）显著优于单视图方案，关键在于多视图模型天然附带置信度图，可对每像素预测进行自适应加权。

◆提出基于置信度的先验融合策略，将VGGT输出的法线、深度及其置信度作为软约束嵌入3DGS优化过程，使模型在高不确定性区域保持鲁棒。

◆在标准基准上的大量实验表明，该方法在重建质量上获得一致提升，并对含镜面物体的复杂场景带来尤为显著的增益。

该工作揭示了多视图几何先验及置信度机制是突破3DGS几何重建瓶颈的关键路径。</td></tr>
<tr><td>2026-08-05</td><td>VLAff: Vision-Language-Affordance Model for Unified Actionable Affordances<br><a href='http://arxiv.org/pdf/2608.05215'>论文</a></td><td>本文针对从人类视频学习机器人操作技能中存在的身体差异问题，提出了一套基于自我中心视频的可操作可供性学习框架。研究者利用三维结构恢复和手部网格重建技术，从人类视频中提取出视觉可供性、抓取可供性和轨迹可供性三种与身体无关的交互表征。

◆提出统一的可供性提取框架，将人类视频转化为包含交互位置、抓取方式和运动路径的完整可供性表示。

◆构建大规模数据集EgoAffordance，包含20.4万条片段、560万视觉可供性以及1160万抓取与轨迹可供性标注。

◆设计基于视觉-语言大模型的基础模型VLAff，通过跨模态关联学习统一预测三类可供性，并结合三维场景信息直接生成可执行动作。

◆在视觉可供性预测任务上达到最优性能，并成功应用于零样本机器人操作和可供性引导的机器人学习等实际场景。</td></tr>
<tr><td>2026-08-03</td><td>Loggia dei Lanzi: AI Thermography Enhancement Comparisons through 3D Photogrammetry<br><a href='http://arxiv.org/pdf/2608.02404'>论文</a></td><td>本文以佛罗伦萨领主广场的佣兵凉廊为研究对象,于2025年12月使用FLIR T1020高清热像仪开展热成像调查,成功揭示了隐藏在灰泥层下的被封堵开口和材料过渡区域等建筑特征。在光束法平差(SfM)摄影测量流程中,系统比较了三种分辨率层级的图像——原生分辨率、FLIR硬件像素移位超分辨率(UltraMax)以及AI超分辨率模型,定量评估了不同增强方式对特征点检测和连接点生成的影响。

◆首次在文化遗产热成像摄影测量工作流中,直接对比硬件微扫描(FLIR UltraMax)与AI超分辨率的实际效果差异。

◆提出基于三档分辨率层级的定量评估方法,验证超分辨率细节能否转化为更密集、更精确的三维热模型。

◆将研究数据整合进交互式三维档案框架及城市级扩展现实叠加应用,实现研究成果的开放共享与沉浸式展示。

◆公开发布完整数据集,为人工智能与遗产热成像这一新兴交叉领域提供可复用的基准资源。</td></tr>
<tr><td>2026-08-02</td><td>Swimm3R: Splatting with Medium-aware SfM for Underwater 3D Reconstruction<br><a href='http://arxiv.org/pdf/2608.00950'>论文</a></td><td>本文提出Swimm3R，一个融合介质感知SfM与水下Beta泼溅的统一框架，旨在解决水下三维重建中因散射和衰减导致的失效问题。该方法将空中几何先验蒸馏到前馈骨干网络，并利用物理回归头同时预测水下图像形成参数、相机位姿以及恢复后的点云。针对水下场景的特殊性，进一步提出Underwater Beta Splatting，用Beta基元扩展高斯泼溅并引入散射感知几何梯度，从而实现稳定的水下几何表征。此外，作者构建了Barbados水下视频数据集用于评估。

◆ 提出统一框架Swimm3R，首次将介质感知SfM与水下Beta泼溅相结合用于水下3D重建
◆ 设计物理回归头，可联合预测水下成像参数、相机位姿及校正后的稠密点云
◆ 提出Underwater Beta Splatting，用Beta基元替代高斯基元并加入散射感知几何梯度
◆ 发布Barbados水下视频数据集，为复杂水下环境评估提供新基准

实验结果表明，Swimm3R在强散射条件下能鲁棒恢复海底几何结构，重建质量较WaterSplatting平均PSNR提升1.47 dB，下游定位任务中RRA@15和RTA@15分别提升2.0和2.4个百分点。</td></tr>
<tr><td>2026-07-29</td><td>VidMap: Exploiting Temporal Structure for Video-Based Structure-from-Motion<br><a href='http://arxiv.org/pdf/2607.27194'>论文</a> | <a href='https://github.com/cvg/vidmap'>代码</a></td><td>本文针对无约束视频的相机标定与度量位姿恢复问题,提出VidMap系统,旨在弥合现有SLAM与SfM方法之间的鸿沟。现有SLAM对初始化敏感、容易瞬态失败且通常依赖已知相机标定,而传统SfM虽支持全局优化但对视觉对称性和极端运动鲁棒性不足。本文方法将SLAM的强序列约束与离线SfM的灵活性及全局优化能力相结合,实现对任意长视频的度量重建。

◆利用宽基线稠密图像匹配建立可靠的图像间关联
◆将时间顺序作为一等公民用于可靠的回环检测
◆在全局优化中引入单目度量深度先验以恢复尺度一致性

在多个具有极端运动和视觉对称性的挑战性数据集上的实验表明,无论是否已知相机标定,该方法均显著优于当前最先进的SLAM和SfM方法。</td></tr>
<tr><td>2026-07-29</td><td>3DGBGS: 3D Granular Ball Gaussian Splatting for Compact Novel View Synthesis<br><a href='http://arxiv.org/pdf/2607.26578'>论文</a></td><td>本文针对基于锚点的三维高斯溅射方法中固定体素化难以适应非均匀点云分布的问题,提出3DGBGS框架,将粒度球计算思想引入三维高斯溅射中,实现了对SfM点云的自适应组织表示。方法使用较大的粒度球紧凑表示平滑冗余区域,使用较小的粒度球保留复杂几何和局部细节,从而缓解锚点数量、模型紧凑度与渲染质量之间的权衡矛盾。

◆ 提出Granular Ball Anchor Initialization (GBAI),利用粒度球中心初始化锚点位置,实现紧凑的锚点布局。

◆ 提出Granular Ball Scale Prior (GBSP),利用粒度球半径为高斯生成提供局部尺度先验,提升几何适应性。

◆ 构建3DGBGS端到端框架,在四个基准数据集上将初始和最终锚点数量分别减少37.1%和10.0%,平均模型存储减少9.8%,同时保持相当的渲染质量。</td></tr>
<tr><td>2026-07-28</td><td>Macroscopic wall pressure and microscopic contact load in crowds without egress: social-group cohesion and boundary buffering<br><a href='http://arxiv.org/pdf/2607.25780'>论文</a></td><td>本文针对无疏散密集人群的机械安全风险，构建了耦合弹性重定向模型（ERM）与社会力模型（SFM）的分析框架，填补了传统疏散与避碰评估之外的力学风险研究空白。◆通过引入社会群体内聚力γ_g与墙体缓冲γ_w作为后碰撞参数，分别从宏观壁面线压力P_wall和微观最大碰撞冲量δp_max量化双重风险尺度。◆研究发现P_wall与δp_max之间存在权衡：群体内聚与壁面缓冲虽能降低壁压，但可能在中等等级引发高冲量危险窗口，γ_g→1时局部配对通过动能重分配降低冲量。◆通过有限尺度分析识别出两类相变边界——独立个体在γ_w=0.5处的磁化率跃迁相变，以及分组个体沿(1-γ_w)(1-γ_g)=0.5的磁化率发散相变并终止于临界点。◆这些相变行为仅在ERM与SFM耦合动力学中涌现，为高密度无疏散场所的人群风险缓解提供了机理性指导。</td></tr>
<tr><td>2026-07-27</td><td>Accuracy potential of visual localization exploiting high-end street-level imagery<br><a href='http://arxiv.org/pdf/2607.24409'>论文</a> | <a href='https://fhnw-muttenz-vl-dataset.github.io/'>代码</a></td><td>本文针对视觉定位精度尚未系统评估的空白,提出了一套可扩展的视觉定位流程,并构建了公开的大规模基准数据集以验证其在测量级应用中的精度潜力。

◆ 提出基于高分辨率街景影像的视觉定位流程,直接将精确地理参考影像作为场景表示,结合先验引导的参考候选筛选与在线局部SfM重建加PnP位姿估计,实现了可扩展的高精度定位。

◆ 发布FHNW Muttenz数据集,覆盖10公里连续道路网,包含两次相隔约1.5年采集的高分辨率参考影像与查询序列,使用四种相机在五个场景获取数据,提供亚厘米级真值位姿。

◆ 在该数据集上的实验表明,视觉定位中位精度可达平移1至5厘米、旋转0.05至0.1度,最优条件下分别低至1厘米和0.03度。

研究表明视觉定位能够补充测量级GNSS定位,为消费级设备实现三维地理空间数据采集和全自动地理参考提供了可行路径。</td></tr>
<tr><td>2026-07-20</td><td>Ergodicity of FIRE: star formation variations within and between simulated galaxies<br><a href='http://arxiv.org/pdf/2607.18005'>论文</a></td><td>本文研究了FIRE-2项目高分辨率模拟星系中恒星形成的遍历性,聚焦于星系偏离恒星形成主序(SFMS)的程度,以及集合平均与时间平均的恒星形成历史是否一致。

◆研究发现无论采用何种SFMS定义和恒星形成示踪量,单个星系的SFMS偏差都随时间趋向遍历性行为。

◆该趋势在不同形态星系中均成立,但核球主导的星系比盘主导星系表现出更小的SFMS偏差范围。

◆基于短时标(10^7年)的恒星形成示踪量比长时标(10^9年)能更快地收敛到遍历性。

◆研究还指出当前结论受限于样本规模,高红移演化以及活动星系核的影响有待进一步研究。</td></tr>
<tr><td>2026-07-20</td><td>Stability and Comfort in Mobile Robot-Pedestrian Interactions<br><a href='http://arxiv.org/pdf/2607.17604'>论文</a></td><td>本文针对公共空间移动机器人需保障行人舒适度的问题,为非完整约束移动机器人(NMR)提出了社会感知导航算法,通过理论分析、仿真标定与真实行人交互实验系统验证了其有效性。

◆创新点一:将社会力模型(SFM)与投影碰撞时间社会力模型(TSFM)相结合,显式建模行人的主观安全感受,克服了传统导航算法将行人简单视为动态障碍的局限。

◆创新点二:首次形式化NMR与行人及障碍物的交互过程,并在有界非被动行人假设下严格证明了系统的稳定性,填补了非完整约束机器人社会导航的理论空白。

◆创新点三:构建兼顾舒适度与速度的混合代价函数进行模型标定,并通过问卷统计分析与遥控基线对比,验证了所提算法在改善行人舒适度方面相对于已有方法的显著优势。</td></tr>
<tr><td>2026-07-17</td><td>HETA++: Global Structure-from-Motion with Hybrid Explicit Translation Averaging<br><a href='http://arxiv.org/pdf/2607.15912'>论文</a></td><td>本文提出了一种新的混合显式平移平均框架HETA++,用于全局式SfM,旨在同时利用相对平移和特征轨迹,克服现有方法在共线相机运动下的退化问题以及对异常值的敏感性。

◆首先利用全局相机旋转精化相对平移并剔除全局不一致的相对平移,提升输入数据的可靠性。

◆接着采用基于凸距离的目标函数估计初始相机位置和三维点,再以非双线性角度目标函数进行精化,兼顾了收敛稳定性和几何一致性。

◆针对平移平均阶段相机旋转固定导致精度受限的问题,提出通过有界角度精化和基于重投影的束调整,联合稳健地优化相机旋转与位置。

◆在优化过程中筛选空间分布均衡的特征轨迹,既提升了效率也增强了鲁棒性,最终通过完整束调整获得高精度结果。

大量实验表明,该方法在顺序和无序真实数据集上均优于当前最先进方法,在精度和计算效率方面均表现突出。</td></tr>
<tr><td>2026-07-16</td><td>Immediate 3D Gaussian Splat Reconstruction of Unordered Input with Global Consistency<br><a href='http://arxiv.org/pdf/2607.14481'>论文</a></td><td>本文针对3D高斯溅射(3DGS)重建中乱序输入与即时反馈难以兼顾的问题，提出首个支持乱序图像输入并保持全局一致性的即时重建框架。该方法通过复用视觉位置识别模型与构建共视性图，实现乱序序列的快速匹配与高连通关键帧筛选，并结合GPU优化和精心设计的高斯基元放置策略，保证局部重建的效率与质量。

◆ 提出基于视觉位置识别与共视性图的乱序图像快速匹配方法，并发现高连通关键帧的选择还能进一步提升有序序列的重建质量。

◆ 提出基于共视性图的聚类式回环闭合策略，无需依赖顺序输入即可实现高效的全局一致性优化。

◆ 引入渐进式层次结构，使方法能够扩展到包含数千张图像的大规模场景，同时兼顾效率与视觉质量。</td></tr>
<tr><td>2026-07-15</td><td>SalientGS: Unified SfM-to-3DGS with Importance-Guided MCMC Gaussian Allocation<br><a href='http://arxiv.org/pdf/2607.11285'>论文</a> | <a href='https://github.com/Six-Bit-TX/SalientGS'>代码</a></td><td>SalientGS提出了一种统一的SfM到3D高斯溅射（3DGS）的端到端重建流水线，旨在消除传统3D场景重建中昂贵的SfM预处理和冻结位姿接口的瓶颈。其核心创新在于引入了重要性引导的MCMC高斯分配策略，通过聚合多视图残差来计算每个高斯点的欠拟合度和冗余度信号。系统利用这些信号构建平滑的重要性加权采样分布，使得高斯点的生成和重定位偏向欠拟合区域，从而在不改基础随机梯度朗之万动力学的前提下，将渲染能力从已拟合良好的区域重新分配到欠拟合区域。SalientGS能够在15分钟内完成端到端重建，并在感知质量上达到最先进水平。◆统一了SfM与3DGS流水线，实现了无需外部预处理的高效端到端三维重建。◆通过多视图残差聚合定义高斯点的重要性信号（欠拟合度与冗余度），实现细粒度的容量分配。◆在保留SGLD框架的基础上，以重要性加权采样分布引导MCMC的生灭与重定位过程，避免了底层动力学修改。</td></tr>
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
<tr><td>2026-07-17</td><td>NoDrift3R: Raymap-Guided Coupling for Drift-Robust Unposed Feed-Forward 3D Reconstruction<br><a href='http://arxiv.org/pdf/2607.07168'>论文</a> | <a href='https://xiangyu1sun.github.io/NoDrift3R-project-page/'>代码</a></td><td>该论文针对无位姿前馈三维高斯溅射在长序列中因位姿漂移导致重建质量退化的问题，提出了一种几何与外观显式协同的新框架。作者识别出位姿累积漂移是制约性能的主要瓶颈，并指出SfM伪真值引入传感器噪声、纯渲染监督易陷入局部最优等矛盾。

◆ 提出Raymap-Guided Coupling Module（RGC）模块，将高斯中心锚定到光线图诱导的几何上，在统一目标下联合优化RGB重建、光线图一致性与相机正则化，形成几何与外观之间的双向反馈循环。

◆ 设计Dual-Frequency Viewpoint Scheduling策略，结合由易到难的间隔扩展与短间隔对回放，稳定长时序学习过程。

在域内和跨域数据集上的大量实验表明，该方法在渲染质量与位姿估计上均取得一致提升，长序列鲁棒性显著增强，验证了几何-外观显式协同是实现可扩展、无漂移无位姿前馈三维重建的关键。</td></tr>
<tr><td>2026-07-12</td><td>Deep far-UV observations of the ELAIS N1 field using AstroSat: Source catalogue, spectral energy distribution modelling and star formation<br><a href='http://arxiv.org/pdf/2607.06143'>论文</a></td><td>本文利用AstroSat卫星上的紫外成像望远镜(UVIT)对ELAIS N1深场进行了F154W波段(far-UV)的深度观测,总曝光时间达30千秒,通过CCDLAB v3.0进行数据处理,获得了1637个3σ和458个5σ的FUV源目录,极限星等分别为25.69和25.13 mag(AB),为该天区提供了目前最深的FUV测光数据。

◆ 基于多波段交叉匹配,结合光学和红外数据以及光谱/测光红移,采用多波段判据剔除活动星系核(AGN),构建了清洁的恒星形成星系样本。

◆ 使用CIGALE进行SED建模,采用延迟型恒星形成历史(可叠加晚期暴发)、Bruzual &amp; Charlot恒星 population合成、Calzetti消光和SKIRTOR AGN模块,系统地推导了样本的恒星形成率(SFR)、总恒星质量和年轻恒星质量随红移的演化。

研究发现SFR随红移单调上升,符合恒星形成主序(SFMS)的演化趋势,同时年轻质量与总质量比值在0&lt;z≲0.76范围内近似为常数,表明样本中的星系主要以自调节的稳态恒星形成为主,而非星暴主导的演化模式。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-06</td><td>A Low-Latency ASIC Architecture for Real-Time Line Segment Detection<br><a href='http://arxiv.org/pdf/2608.06439'>论文</a></td><td>该论文针对嵌入式视觉应用中的线段检测任务，提出了一种低延迟ASIC架构，旨在解决深度学习方法资源消耗大、经典算法延迟不确定的问题。设计基于步长算法并采用全流水线结构，实现每时钟周期处理一个像素，具有确定性延迟特性。在45nm CMOS工艺下，VGA分辨率可达325 FPS，全高清可达48 FPS，功耗仅25.54 mW，面积0.412 mm²；125 MHz下VGA吞吐提升至406 FPS，相比90nm Hough变换ASIC功耗降低49%、帧率提升1.6倍以上。

◆ 基于步长算法设计全流水线ASIC架构,每周期处理一像素,实现确定性低延迟
◆ 寄存器化行缓冲与数据复用机制,减少片外存储访问
◆ 乘法器无关的MCM(多常数乘法)滤波单元,降低硬件复杂度与功耗
◆ 8类角度量化策略,大幅简化梯度方向分类
◆ 类CAM的关联存储结构,支持单周期线段匹配
◆ 优化的重复线段去除机制,提升输出质量与处理效率...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-04</td><td>LoRetta: A Foundation Model and Extensive Dataset for Global-Scale Remote Sensing Dense Image Matching<br><a href='http://arxiv.org/pdf/2608.04106'>论文</a></td><td>该论文针对全球尺度遥感影像密集匹配中存在的几何偏移大、重叠区域不完整等难题,将密集匹配重新建模为&quot;定位-配准&quot;两阶段任务,先定位可匹配区域与仿射几何,再在对齐框架内精化密集残差。

◆ 提出任务范式创新:将密集匹配重构为&quot;定位-配准&quot;流程,通过可匹配性感知仿射定位与引导式密集配准的耦合,有效解决大几何偏移与不可匹配区域导致的预测不可靠问题。

◆ 构建基础模型 LoRetta,融合可匹配性感知仿射定位与引导式密集配准,在 LEVIR-GM 基准上以 83.3% AUC 超越最强基线 RoMa v2 1.6 个百分点,1 像素与 2 像素 PCK 分别提升 6.5 与 8.2 点,同时推理延迟降低 47.8%。

◆ 发布 LEVIR-GM 全球基准,涵盖六大洲、五年时序、0.5-1024 米分辨率的 103K 对齐与 827K 增强光学影像对,并首次提供数据集原生可匹配性标注。

◆ 建立稀疏、半密集与密集匹配器的统一评估协议,并通过航天员-卫星、无人机-卫星地理定位实验验证 LoRetta 作为可复用几何对齐器的跨域迁移能力。</td></tr>
<tr><td>2026-08-04</td><td>SGFormer: Structure-Guided Transformer for Robust Local Feature Matching<br><a href='http://arxiv.org/pdf/2608.03423'>论文</a></td><td>该论文针对局部特征匹配中现有无检测器方法(如LoFTR)在大幅视角变化场景下出现的注意力发散问题,提出了一种新颖的结构引导Transformer网络SGFormer。研究发现,标准Transformer的无约束全局注意力机制会使部分高置信度匹配落在重叠区域之外,降低匹配可靠性。

◆提出Triple-Structure-Attention(TSA)模块,利用网络浅层局部特征强化显著结构区域的特征表达,引导后续Transformer阶段将注意力聚焦于具有显著结构的重叠区域。

◆采用半稠密的由粗到精匹配流水线,自适应地更新显著结构附近的注意力,在提升全局建模能力的同时抑制非重叠区域的干扰。

◆在多个具有挑战性的摄影测量基准数据集上的实验表明,SGFormer有效缓解了注意力发散现象,显著提升了匹配精度与鲁棒性。</td></tr>
<tr><td>2026-08-04</td><td>Double Down on Defense: Strengthening Deep Perceptual Hashes against Evasion Attacks without Retraining<br><a href='http://arxiv.org/pdf/2608.03101'>论文</a></td><td>本文针对深度感知哈希在对抗扰动下易被规避匹配的问题，提出了DualShield防御框架。核心思路是在不重训练、不修改原有模型的前提下，通过匹配流程和参考图预处理两个环节增强鲁棒性。

◆ 匹配时引入随机平滑机制，对扰动后的参考-查询图像对聚合决策，理论上可获得约0.3的ℓ2认证鲁棒半径，保证该范围内的查询扰动无法规避匹配。

◆ 发布前对参考图像添加优化得到的、肉眼难以察觉的扰动进行&quot;硬化&quot;预处理，使后续匹配对对抗攻击天然更具抵抗力。

◆ 采用即插即用设计，可与八种主流深度感知哈希及多种数据集兼容，无需访问或修改底层模型结构，显著降低各类自适应白盒、黑盒及图像变换攻击的成功率，同时保持低碰撞率。

该工作表明，通过改进匹配策略和发布前图像硬化，可在不付出重训练代价的前提下有效提升深度感知哈希系统的安全性。</td></tr>
<tr><td>2026-07-30</td><td>Can Synthetic Data Overcome the Generalization Limits of AI-Based Flower and Pod Detection Across Cowpea Breeding Genotypes and Environments?<br><a href='http://arxiv.org/pdf/2607.28796'>论文</a></td><td>该研究针对豇豆育种中AI视觉模型在不同基因型与环境（G×E）组合下泛化能力下降的问题，系统量化了跨地点、跨季节的花朵和豆荚检测性能衰减，发现花朵检测mAP@50从76.3%降至最低50.6%，豆荚检测对分布漂移更为敏感。为规避逐一标注真实图像的高昂成本，作者提出利用程序化3D模型渲染合成图像替代人工标注的思路，但发现纯合成监督因相机成像差异存在域鸿沟。

◆ 创新点一：提出域鸿沟感知的相机真实感增强策略，通过Wasserstein距离对齐真实图像统计量来度量并优化合成数据与真实域之间的分布差异。

◆ 创新点二：引入线性HDR表示方法，在相同域鸿沟下比8位表示获得更大的检测性能提升，揭示了位深对域迁移增益的关键影响。

◆ 创新点三：证明优化后的HDR合成数据仅需配合少量真实图像即可匹配或超越全真实数据基线的空间泛化效果，并在极低样本量下对豆荚检测收益最大。</td></tr>
<tr><td>2026-07-30</td><td>CXR-Retrieve: Compositional Text-to-Image Retrieval in Chest Radiography<br><a href='http://arxiv.org/pdf/2607.27779'>论文</a></td><td>胸部X光影像库通常只配对自由文本报告，难以高效检索，而现有生物医学视觉语言模型主要针对报告-图像匹配优化，无法满足包含联合与否定等组合约束的临床查询。论文针对这一目标错位问题提出了两项核心贡献。

◆构建了CXR-Retrieve组合检索基准，包含5159张MIMIC-CXR-JPG测试图像和145条覆盖单一发现、联合发现及否定表达的查询，相关性由是否满足所有病理断言决定，而非是否匹配配对报告。

◆提出了标签感知的对比微调目标，吸引病理约束兼容的图像-文本对（包括共享的确认缺席），同时显式排斥矛盾对。

◆基于领域内CXR-CLIP检查点微调后，在双病理联合查询上Precision@5提升8.5个百分点，在否定查询上提升22.0个百分点，证明可靠的胸部X光检索需要建模病理的临床断言方式，而不仅仅是哪些病理被提及。</td></tr>
<tr><td>2026-07-29</td><td>VidMap: Exploiting Temporal Structure for Video-Based Structure-from-Motion<br><a href='http://arxiv.org/pdf/2607.27194'>论文</a> | <a href='https://github.com/cvg/vidmap'>代码</a></td><td>本文针对无约束视频的相机标定与度量位姿恢复问题，提出VidMap系统，旨在弥合SLAM与SfM之间的差距。传统SLAM受限于因果增量特性，对初始化和瞬态失败敏感，且通常需要已知相机标定；传统SfM虽支持全局优化但缺乏对时间顺序的利用。作者通过结合SLAM的强序列约束与离线SfM的全局优化灵活性，实现了对任意长视频、无标定输入的度量三维重建。

◆结合SLAM的序列约束与离线SfM的全局优化能力，支持无标定长视频的度量重建。
◆引入宽基线稠密图像匹配技术，提升特征关联的鲁棒性。
◆将时间顺序信息作为一等公民用于可靠回环检测。
◆在全局优化中融合单目度量深度先验，提高重建精度。
◆在极端运动与视觉对称等挑战性场景下，显著优于现有SLAM和SfM方法。</td></tr>
<tr><td>2026-07-29</td><td>Robust RPC Bundle Adjustment for Multi-Date Satellite Imagery with Season-Invariant Correspondences<br><a href='http://arxiv.org/pdf/2607.26973'>论文</a></td><td>针对多日期卫星影像中季节、照度等地表变化导致的跨时相匹配难题，传统基于手工特征的RPC光束法平差方法难以获得稳健的同名点。本文提出一种感知外观的RPC精修流水线，将学习驱动的局部特征匹配与全局图像描述子筛选相结合，以提升无GCP条件下多视图相对RPC精修的精度与效率。该流水线在匹配前对图像对进行兼容性筛选，再以学习特征完成对应构建，从而在异时相集合上兼顾了连接的完整性与匹配的可靠性。◆ 采用学习型局部特征匹配获取对季节变化稳健的同名点对应，解决异时相图像间传统手工特征匹配易失效的问题。◆ 引入全局图像描述子选择视觉兼容的图像对，剔除冗余和易错匹配，同时保持匹配图的整体连通性。◆ 在39至42视图的季节多样WorldView-3影像集上验证，方法在几何一致性误差和匹配耗时两方面均优于现有开源基线，使多日期卫星影像的RPC精修更加鲁棒高效。</td></tr>
<tr><td>2026-07-26</td><td>Robust 6-DoF Object Pose Tracking with Built-In Recovery under Occlusions and Rapid Object Motions<br><a href='http://arxiv.org/pdf/2607.23468'>论文</a></td><td>本文针对RGB-D数据下6-DoF物体位姿跟踪中面临的全遮挡和快速运动导致跟踪失败的难题，提出了一种融合学习关键点匹配与优化对齐的鲁棒跟踪方法。该方法在易跟踪场景下达到当前最优精度，同时保持57.6 FPS的实时性能，并在遮挡和快速运动等挑战性条件下表现出最强的鲁棒性。

◆ 提出一种结合学习式关键点匹配与优化式对齐的高效跟踪框架，实现对未见物体的6-DoF位姿估计。

◆ 引入新颖的失败检测与恢复模块，实时监测位姿可靠性，识别跟踪发散或遮挡状态。

◆ 设计全局重检测与位姿估计步骤，对恢复候选进行严格验证后再恢复跟踪，实现自动重初始化。

◆ 发布了一个包含遮挡和快速运动场景的新数据集，用于评估该类挑战性条件下的跟踪性能。</td></tr>
<tr><td>2026-07-21</td><td>NGPS: GPS-Denied Aerial Geo-Localization and 2.5D Reconstruction via Deep Satellite Image Matching and Multi-Rate Sensor Fusion<br><a href='http://arxiv.org/pdf/2607.18936'>论文</a> | <a href='https://github.com/snktshrma/ngps_flight'>代码</a></td><td>本文提出NGPS框架，一种面向高空无人机的视觉地理定位系统，通过深度特征将下视图像与地理参考卫星影像匹配，在GPS拒止环境下实现绝对定位。

◆ 提出自适应置信度加权UKF融合方法，利用RANSAC内点率、重投影误差和匹配置信度动态调制协方差。
◆ 基于VIO速度预测卫星影像搜索区域，实现速度预测式核提取，提升匹配效率与鲁棒性。
◆ 设计异步多速率时间优先级队列，将绝对位姿（1-2Hz）、VIO（10-20Hz）与IMU（100-200Hz）按时间顺序交错融合。
◆ 结合VINS位姿图全局优化与NGPS锚定校正，实时生成2.5D地理参考正射镶嵌图。

在60-150米高度的5组飞行实验中，系统达到2.94米位置RMSE，相较单目VIO提升3.5倍最差情况绝对轨迹误差为6.04米，且可在Jetson Orin NX上实时运行。</td></tr>
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
<tr><td>2026-07-01</td><td>SOCO: Benchmarking Semantic Object Correspondence in Vision Foundation Models<br><a href='http://arxiv.org/pdf/2605.31597'>论文</a></td><td>本文提出SOCO基准，旨在解决视觉基础模型中结构化对象理解评估协议不一致和部件级监督有限的问题。
◆构建了包含对应类型分类法的语义对象对应基准，在100个类别和超百万对应对上提供一致且具功能意义的关键点标注。
◆引入关键点语言描述，支持对大型视觉语言模型细粒度部件级理解能力的系统评估。
◆揭示视觉骨干网络虽编码强语义结构，但跨类别迁移对应能力差且仅部分捕获部件位置。
◆发现大视觉语言模型擅长文本提示定位但视觉参考跨图匹配较弱，暴露语言接地与视觉对应间的鸿沟。
◆证明对应性能比ImageNet分类性能更能强有力地预测分割、跟踪及3D检测等密集下游任务的表现。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='obstacle-avoidance'>Obstacle Avoidance</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-10</td><td>Satellite Trajectory Optimization via Proximal Policy Optimization for Space Debris Avoidance<br><a href='http://arxiv.org/pdf/2608.09628'>论文</a></td><td>本文针对低地球轨道和地球同步轨道日益严峻的卫星碰撞规避问题,提出了一种基于近端策略优化(PPO)强化学习的自主避碰策略,并配套开发了开源高保真度航天动力学仿真器。在1000次确定性GEO场景测试中,该智能体实现了97.5%的避碰成功率,显著优于基于规则的方法(20.7%)和脉冲式delta-v规划器(27.5%)。

◆ 基于PPO的端到端强化学习策略,直接从状态映射到规避动作,无需依赖手工规则或预规划轨迹,具备自主决策能力。

◆ 构建开源高保真度航天动力学仿真平台,融合牛顿二体动力学、太阳与月球第三体摄动、燃料消耗模型以及可配置碎片场,贴近真实在轨环境。

◆ 采用课程学习与多目标塑形奖励函数,从生存时长、投影脱靶距离到delta-v消耗进行综合引导,提升策略收敛质量与燃料经济性。

◆ 建立了完全确定性的评估流水线,包括共享随机种子、逐回合日志记录与遥测数据导出,确保实验可复现并便于分析对比。</td></tr>
<tr><td>2026-08-10</td><td>Model-Based Systems Engineering Framework for SysML-Driven Design of Autonomous UAVs<br><a href='http://arxiv.org/pdf/2608.09547'>论文</a></td><td>该论文针对自主无人机这一复杂信息物理系统,提出了一种基于模型的系统工程(MBSE)设计框架,以SysML作为形式化设计骨干,通过需求层、功能分解层、逻辑架构层和物理/软件分配层四个相互关联的层次,系统化地结构化无人机开发过程。框架综合运用需求图、活动图、块定义图、内部块图、状态机图和参数图等多种SysML图,捕获无人机系统的功能、结构、行为、接口和性能等多维特性,并将逻辑架构系统化映射到ROS 2软件架构。

◆ 创新点一:构建四层关联的SysML驱动MBSE设计框架,贯通从利益相关者需求到物理/软件分配的全链路形式化建模,解决传统文档式开发中需求模糊、接口不一致和追溯性弱的问题。
◆ 创新点二:建立SysML模型元素到ROS 2组件的明确映射规则,即块对应节点、流端口与连接器对应话题、请求-响应交互对应服务、目标导向行为对应动作,实现系统模型与软件实现之间的无缝桥接。
◆ 创新点三:以自主起飞、航点导航、悬停稳定、障碍规避、返航和应急处理等典型任务场景为实例验证框架有效性,支持在仿真或物理部署前完成需求分配、接口定义、子系统职责划分和验证规划。</td></tr>
<tr><td>2026-08-10</td><td>UnsDrive: Towards Robust End-to-End Autonomous Driving in Unstructured Scenes<br><a href='http://arxiv.org/pdf/2608.09098'>论文</a></td><td>该论文针对非结构化矿区场景中端到端自动驾驶面临的弱路网结构、地形遮挡和观测不完整等挑战,提出了UnsDrive规划系统。其核心思想是构建未知感知的占据表征,显式建模占据、空白和未知三类空间,并基于多帧可见性线索增强感知鲁棒性。论文还设计了两个安全机制:占据-轨迹一致性损失和不确定性感知轨迹评分器,以惩罚进入不可通行或未观测区域的轨迹。此外,作者构建了面向矿区的闭环仿真平台MineLoop,用于在非规则道路几何、低能见度和重型车辆交互等场景下评估驾驶策略。实验表明,UnsDrive在轨迹精度、避撞能力和长时域鲁棒性方面均优于现有强基线。

◆ 提出面向非结构化矿区的端到端规划器UnsDrive,通过未知感知占据表征结合流匹配规划器生成多模态未来轨迹
◆ 引入占据-轨迹一致性损失与不确定性感知轨迹评分器,提升部分观测下的规划安全性
◆ 构建矿区专用闭环仿真平台MineLoop,支持非规则路形、低能见度和重车交互等工况评测...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-07</td><td>CoCoNav: Conformal Control for Safe Robot Navigation in Crowds<br><a href='http://arxiv.org/pdf/2608.07751'>论文</a></td><td>CoCoNav是一个面向人群场景下机器人安全导航的框架,旨在解决行人运动预测不确定且易变所带来的规划难题。该方法通过在线保形校准(conformal calibration)动态调整轨迹误差边界,使系统能够自适应预测误差的漂移。核心创新在于提出了一种基于保形控制的比例-积分控制器,按预测时域分别调节误差包络,以维持长期的统计覆盖率,既不过于保守也不冒进。框架采用&quot;先松弛后验证&quot;(relax-then-verify)的规划策略,通过软约束MPC生成名义轨迹并配以应急机动,再由运行时验证环节判断其是否满足校准后的安全边界,从而保证求解可行性。

◆ 提出基于保形控制的比例-积分(PI)校准器,按预测时域在线自适应调整轨迹误差边界,有效跟踪非平稳预测误差的统计覆盖率。
◆ 设计&quot;先松弛后验证&quot;的规划架构,通过软约束MPC分离名义轨迹生成与安全验证,显著提升求解可行性并支持应急机动。
◆ 仿真与四足机器人实验表明,CoCoNav在避碰成功率、任务完成与导航效率之间取得了优于现有基线的综合平衡。</td></tr>
<tr><td>2026-08-04</td><td>Projection-Retraction MPPI: Exact Constraint-Manifold Control for Manipulators<br><a href='http://arxiv.org/pdf/2608.07573'>论文</a> | <a href='https://rcilab.github.io/prmppi'>代码</a></td><td>针对MPPI控制仅能通过软惩罚近似处理约束的局限，本文提出Projection-Retraction MPPI（PR-MPPI），将等式与不等式约束强制纳入采样动力学内部以实现严格满足。方法在每个rollout步对采样速度进行分层投影：等式约束先将其限制到子空间，不等式约束再在该子空间内施加半空间限制，从而保证不等式处理不会破坏等式约束。由于投影仅满足一阶精度，有限步长会引入漂移，因此通过retraction操作将最终返回指令拉回约束流形至数值容差，且该过程独立于任务权重。

◆ 将约束处理从代价层提升到采样动力学内部，实现等式与不等式约束的严格满足
◆ 采用分层投影策略，等式约束确定子空间，不等式约束在子空间内进一步施加半空间限制
◆ 引入retraction操作消除一阶投影产生的约束漂移，使返回指令达到数值容差并与任务权重解耦

在14自由度双臂系统上的实验表明，仿真中返回指令在关节极限压力测试和随机障碍物避障场景下均满足闭合链等式约束的数值容差，并在Unitree H1-2人形机器人硬件上实现了对移动障碍物的反应式避障。</td></tr>
<tr><td>2026-08-03</td><td>The Field Knows: Cross-Dimensional Geometry from Navigation to Black Holes<br><a href='http://arxiv.org/pdf/2608.07566'>论文</a></td><td>本文提出了一种连续度量场框架，仅通过单一的因果对比损失进行训练，即可自动学习跨维度、跨几何类型的度量结构。该框架将场景编码为固定对称矩阵基的系数，组装为李代数元素后指数化，生成黎曼或洛伦兹度量，巧妙地统一了机器人导航与广义相对论几何的建模方法。

◆ 提出了统一的连续度量场框架，通过李代数指数化机制，将对称矩阵基系数转化为可微的黎曼或洛伦兹度量。

◆ 设计了单一的因果对比损失，无需针对不同任务调整，同一损失即可驱动从二维平面避障到高维黑洞时空的多种几何涌现。

◆ 实现了跨维度零样本泛化能力，证明网络捕获的是可迁移的几何本质而非记忆特定配置。

◆ 在黑洞设定中，因果损失自发演化出具有正确洛伦兹号差的类黑洞事件视界结构，揭示几何与物理的内在联系。

◆ 同一架构、损失和训练协议横跨机器人运动学配置空间与弯曲时空，体现了&quot;场知道几何，几何知道物理&quot;的统一性思想。</td></tr>
<tr><td>2026-08-02</td><td>AeroDPO: Unleashing Lightweight UAV Navigation with High-Fidelity Perception and Automated Preference Optimization<br><a href='http://arxiv.org/pdf/2608.07557'>论文</a></td><td>本文针对无人机视觉语言导航(UAV-VLN)任务,挑战了当前对大参数语言模型的依赖。通过跨规模实验发现感知质量比语言推理能力更关键,2B轻量模型配合高保真视觉输入即可匹配7B基线的整体成功率。纯行为克隆策略因缺乏负反馈,在分布外场景碰撞率居高不下。为此提出AeroDPO框架,基于确定性物理仿真状态回滚实现零成本自动偏好优化,通过自动提取碰撞因果错误作为拒绝动作,并结合特权干预合成避撞偏好动作,最后用离线视觉语言检查器过滤视觉歧义。最终2B模型在未映射场景中达到49.16%成功率,显著抑制碰撞率,创下自主空中智能体新SOTA。

核心创新点:
◆ 揭示感知质量优于语言推理的关键洞察,证明轻量2B模型匹配7B基线的可行性
◆ 提出基于仿真状态回滚的零成本自动化DPO数据生成流水线,摆脱对人工标注的依赖
◆ 设计解耦特权干预机制,利用物理仿真合成高质量避撞偏好动作
◆ 引入离线视觉语言检查器自动过滤视觉歧义样本,提升训练数据质量...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-07</td><td>Real-time Whole-Body Motion Planning for Mobile Manipulators Carrying Arbitrarily Shaped Payloads via Kinematically-Coupled SVSDF<br><a href='http://arxiv.org/pdf/2608.07005'>论文</a></td><td>本文针对移动机械臂在狭窄环境中搬运大型非凸负载的实时全身运动规划问题，提出了一套完整的规划框架。框架采用三层结构：前端基于链式分解的核函数碰撞检测方法，能够真实保留机械臂与负载的几何形状，并利用紧凑存储和位级查询实现快速检测。

◆ 提出链式分解的核函数碰撞检测前端方法，在紧凑存储和位级快速查询的支持下，精确保留机器人与任意形状负载的真实几何特征，避免过度简化。

◆ 设计中端预处理阶段，将前端路径转化为平滑可行轨迹，在无碰撞时直接执行以跳过耗时的后端优化，从而提升实时性。

◆ 提出运动学耦合稀疏体素距离场（KC-SVSDF），沿运动学链传播避障梯度，生成一致的全身逃逸方向，实现高效的轨迹优化。

通过消融实验、与现有方法的对比基准以及差速驱动移动机械臂的真实场景验证，表明该框架能够在复杂环境中可靠地搬运大型非凸负载通过狭窄通道。</td></tr>
<tr><td>2026-08-06</td><td>Design and Evaluation of a Touchscreen-Based Teleoperation Interface for Robotic Manipulators<br><a href='http://arxiv.org/pdf/2608.06219'>论文</a></td><td>本文针对核工业等复杂环境下表面接触任务的遥操作需求，设计并评估了一种基于触摸屏的机器人遥操作界面。◆创新点一：将连续手指运动直接映射为机械臂运动，提供比传统摇杆更精细的速度控制能力。◆创新点二：将控制与可视化集成于同一界面，使操作者能够更自然、直观地完成表面交互任务。◆创新点三：开展20人跨国家远程用户研究，综合运用运动学、生理与行为数据，对触摸屏、摇杆及单击自主模式三种控制方式进行多维度评估。实验结果表明，触摸屏界面使任务完成时间中位数从5.38分钟降至2.50分钟（减少53.5%），正弦路径覆盖率达90.7%（优于摇杆的84.1%），且认知负荷NASA-TLX评分由52降至43，显著优于摇杆控制。该研究为遥操作表面任务提供了一种易实现、性能优越且有效降低操作员认知负荷的解决方案。</td></tr>
<tr><td>2026-08-05</td><td>From Transparent Labware Segmentation to Collision Avoidance: A Real-Time Edge-Aware Perception Pipeline<br><a href='http://arxiv.org/pdf/2608.04769'>论文</a> | <a href='https://github.com/havishamy/TransYOLO_3D'>代码</a></td><td>本文针对透明实验室玻璃器皿因折射、镜面反射和缺乏稳定内部纹理而难以被传统分割方法准确识别的问题，提出了一种面向实时机器人碰撞规避的边缘感知实例分割与三维感知流水线。

◆ 提出了一种将轻量级边缘检测分支与一阶段实时实例分割主干相结合的框架，通过边缘引导注意力融合和无参数SimAM模块增强网络对透明物体边界轮廓的感知能力。

◆ 构建了包含3485张图像、21个类别的真实实验室玻璃器皿实例分割数据集LabGlass-IS，填补了透明器皿专用数据集的空白。

◆ 实现了Boundary F-score达到97.80的领先精度，超越FastSAM框架18.93个BF点，同时保持7.1ms的推理速度，参数量仅为最接近竞品的2.85%。

◆ 通过掩码质心的多视图三角化获取三维位置信息，构建保守的包围体碰撞约束，在真实机器人实验中实现93.3%的碰撞规避成功率。</td></tr>
<tr><td>2026-08-05</td><td>OmniRouting: A Semantic-Coupled Multimodal Benchmark for Constraint-Aware Spatial Reasoning in PCB Routing<br><a href='http://arxiv.org/pdf/2608.04434'>论文</a></td><td>OmniRouting是首个针对印刷电路板布线推理的大规模基准测试，旨在评估大语言模型在严格几何、拓扑和电气约束下的复杂布线能力。该基准包含1681个工业级原理图耦合PCB设计，涵盖板几何、人工程师布局、封装、焊盘位置、网络表、叠层信息和布线约束等真实数据。它设计了四项互补任务：几何布线推理、设计规则感知布线推理、电气功能推理以及工具增强智能体布线，全面覆盖PCB布线的关键挑战。实验揭示了当前多模态大模型在路径规划、设计规则遵守和电气功能保持方面存在显著不足。论文将开源全部基准数据、评估代码和工具接口以推动后续研究。

◆ 提出首个面向LLM的工业级PCB布线推理基准，填补EDA领域约束感知空间推理评估空白
◆ 构建1681个真实原理图耦合PCB设计数据集，涵盖几何、电气、可制造性等多维约束
◆ 设计四项递进式任务体系，从纯几何路径规划到工具增强智能体协同，系统评估多层次推理能力
◆ 实证揭示现有LMM在路径规划、设计规则遵循和电气一致性方面的关键缺陷
◆ 承诺完全开源基准、评估代码及工具接口，促进可复现的社区研究...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-04</td><td>Intrinsic Stochastic Successive Convexification on SE(3) for Chance Constrained 6-DOF Rendezvous<br><a href='http://arxiv.org/pdf/2608.04114'>论文</a></td><td>本文针对六自由度航天器交会轨迹优化问题，提出了一种在特殊欧氏群SE(3)上构建的内蕴随机逐次凸化方法。

◆ 将原本定义于欧氏空间的随机逐次凸化框架拓展至SE(3)非线性流形，实现位姿轨迹的协方差操纵与机会约束优化的一致求解。

◆ 通过SE(3)上的内蕴建模，统一描述平动与转动的不确定性传播，揭示并利用了二者的本征耦合关系。

◆ 联合优化标称轨迹、协方差矩阵与反馈控制律，主动塑造闭环散布特性，而非仅在确定参考轨迹基础上进行事后补偿。

◆ 仿真结果表明，该方法在碰撞规避、对接走廊、相机视场及力/力矩概率约束等全位姿相关的安全约束下，相比跟踪确定参考加反馈线性化的方案具有更优的概率可行性。</td></tr>
<tr><td>2026-08-04</td><td>Accelerating Human-Aware Robot Trajectory Generation via Diffusion and Consistency Distillation<br><a href='http://arxiv.org/pdf/2608.03159'>论文</a></td><td>本文针对非冗余机械臂在人类-机器人交互环境中难以同时满足碰撞避免、自碰撞避免及运动学约束的问题，提出了一种基于扩散模型和一致性蒸馏的约束运动规划框架。该方法利用RRT和RRT*算法生成满足约束的轨迹数据集，并以此训练扩散模型，通过引导采样实现约束满足的轨迹生成。为降低迭代扩散采样的推理时间，进一步引入一致性蒸馏技术。此外，损失函数中加入关节加权急动度正则化项，通过惩罚关节加速度的突变来提升轨迹平滑性。仿真结果表明，一致性模型能在100毫秒内生成150条候选轨迹，同时保持较高的任务成功率，并显著降低关节和末端执行器的急动度。

◆ 首次将扩散模型与RRT/RRT*结合用于非冗余机械臂的约束运动规划，通过引导采样直接生成满足碰撞和自碰撞约束的关节空间轨迹，突破了传统零空间次任务方法的局限。
◆ 引入一致性蒸馏技术，将扩散模型的迭代采样过程压缩为单步生成，使150条候选轨迹的生成时间控制在100毫秒以内，满足实时规划需求。
◆ 提出关节加权急动度正则化损失项，有效抑制关节加速度突变，显著提升生成轨迹的平滑性，有利于HRI场景中的安全性和舒适性。</td></tr>
<tr><td>2026-08-04</td><td>CUDA MPC: A GPU-Native Solver for Model Predictive Control<br><a href='http://arxiv.org/pdf/2608.03051'>论文</a></td><td>论文针对模型预测控制(MPC)在快速动态、高维或长视野场景下在线优化开销过大的问题,提出GPU原生求解框架CUDA MPC。

◆ 该框架将优化算法、执行模型与内存架构进行协同设计,采用沿视野并行的ADMM分裂策略,实现整个迭代求解在GPU设备上完成。
◆ 设计融合式CUDA内核,中间优化变量始终驻留在片上低延迟共享内存中,大幅减少全局内存访问与主机干预。
◆ 通过局部原子标志同步协议仅在相邻视野块之间进行通信,显著降低核函数调度开销。

实验结果表明,CUDA MPC能在0.1秒采样周期内完成100秒前瞻的避障停车优化问题,并在10智能体集中式协同任务中成为唯一兼顾实时性与无碰撞约束的求解器;相比基于张量框架的同一ADMM分裂实现,融合内核最高可获得965倍加速。</td></tr>
<tr><td>2026-08-03</td><td>Control Barrier Functions via Minkowski Operations for Safe Navigation among Polytopes<br><a href='http://arxiv.org/pdf/2608.02886'>论文</a></td><td>本文针对多面体环境中安全导航问题，提出了一种基于闵可夫斯基运算的控制屏障函数方法，核心贡献在于避免了对多面体的保守近似。采用保守形状（如球体或椭球体）近似多面体会限制机器人的可行运动空间，本文通过闵可夫斯基运算构建伴随凸优化问题，实现了对多面体机器人与多面体障碍物之间精确符号距离函数（SDF）的求解，并将其与非光滑控制屏障函数相结合，在碰撞和无碰撞两种情形下均能保证安全性。论文的关键创新点包括以下几个方面。

◆ 提出基于闵可夫斯基运算的精确SDF公式化方法，通过两个伴随凸优化问题同时处理碰撞与无碰撞两种情形，避免了传统保守近似带来的可行域损失。

◆ 利用二维闵可夫斯基运算的几何性质和伴随凸规划的KKT条件，通过灵敏度分析推导出精确SDF梯度的统一解析表达式。

◆ 揭示了精确旋转梯度中一类由几何耦合与非完整运动学共同诱导的局部极小值现象，这一现象在以往保守近似方法中被掩盖。

◆ 在纯平移和三类非完整（独轮车）模型仿真中验证了框架的有效性，包括从不安全初始位姿的恢复以及单/多障碍物避障，并表明该方法能实现非保守的机动行为与安全性恢复。</td></tr>
<tr><td>2026-08-03</td><td>Biconvex Optimization for Smooth Minimum-Time Trajectories around Convex Obstacles<br><a href='http://arxiv.org/pdf/2608.02834'>论文</a> | <a href='https://wernerpe.github.io/bmtp-website/'>代码</a></td><td>该论文针对凸障碍物环境下的最小时间运动规划问题,提出了一种双凸优化方法,具备收敛保证、任意时刻可中断以及支持任意阶导数约束的特点。

◆ 通过变量替换同时凸化最小时间目标与所有导数约束,再结合时变分离超平面处理避障,将原问题转化为双凸规划。

◆ 采用交替优化策略:一轮计算最大间隔分离平面,一轮优化轨迹,仅对当前轨迹发生碰撞的障碍添加平面,使轨迹能够跨越障碍跳出局部极小。

◆ 理论保证:从任意简单的无碰折线出发都能保证收敛到可行解,具备全局收敛性与对初始化的高鲁棒性。

◆ 在无人机导航和双臂分拣两类实验上,所提方法的计算时间与当前最优的分解式运动规划器相当,但适用问题范围更广且对坏初始化显著更鲁棒,能可靠地生成高质量轨迹。</td></tr>
<tr><td>2026-08-03</td><td>Safe and robust tube-based path-following for robot navigation<br><a href='http://arxiv.org/pdf/2608.02530'>论文</a></td><td>本文针对未知杂乱环境下的机器人路径跟随任务，提出了一种基于Tube模型预测控制的安全鲁棒导航框架。该框架通过整合人工矢量场制导与反步法控制实现名义制导与控制一体化设计，并利用基于障碍函数的安全性约束保证反应式避障。方法的核心特色在于将光滑距离函数、统一控制目标以及自适应扰动补偿机制有机结合，从而在保证路径收敛性的同时实现对未知有界扰动的鲁棒抑制。

◆ 提出基于Tube的鲁棒导航框架，将人工矢量场制导与反步法控制统一于IGC架构中，实现路径跟随的平稳收敛。

◆ 引入光滑距离函数构建连续避障控制律，避免传统方法中的控制不连续问题，保证反应式避障的平滑性。

◆ 设计统一控制目标函数，融合避障与路径跟随任务，平衡两者的优先级以避免冲突。

◆ 加入自适应控制分量在线估计扰动上界，与Tube控制策略协同实现对未知有界扰动的鲁棒补偿。</td></tr>
<tr><td>2026-08-03</td><td>RADAR Perception for Dynamic Obstacle Avoidance onboard small-scale Quadrotor UAVs<br><a href='http://arxiv.org/pdf/2608.01855'>论文</a></td><td>本文针对小型四旋翼无人机的快速动态避障问题，提出了首个基于毫米波雷达的机载感知与控制系统。论文推导并分析了感知范围、相对速度与控制延迟之间的时延和空间边界条件，为成功避障提供了充分条件。系统采用基于交互多模型(IMM)的轻量级跟踪器与基于控制屏障函数(CBF)的控制器，直接输出规避加速度指令。在300次不同物体尺寸和明暗条件下的实验以及90次烟雾环境实验中，系统在x、y、z方向的位置误差分别小于0.15米、0.93米和0.87米。基于Raspberry Pi 4B的机载实现验证了端到端感知到指令延迟约14毫秒的实时可行性。

◆ 首次将毫米波雷达感知与避障控制集成到小型四旋翼无人机上，实现全流程机载运行。

◆ 建立了感知范围、相对速度与控制延迟之间的时延-空间边界理论，得出避障成功的充分条件。

◆ 设计了轻量级IMM跟踪器与CBF控制器组合，直接输出规避加速度，保证实时性。

◆ 毫米波雷达具备穿透烟雾能力，使系统在烟雾等低能见度环境下仍能可靠工作。

◆ 完整开源了390次投掷实验数据集和代码，为后续研究提供基准。</td></tr>
<tr><td>2026-08-04</td><td>Grasp Execution Without a Planner: Configuration-Space Grasp Distance Fields with Certified Safety &amp; Guaranteed Quality<br><a href='http://arxiv.org/pdf/2608.00600'>论文</a></td><td>本文针对多指抓取执行中规划轨迹易受扰动失效、需频繁重规划的问题，提出无需规划器的抓取距离场（GDF）方法。核心思想是在机械臂-手的构型空间上构建抓取候选构型的平滑softmin距离场，控制器直接沿负梯度方向以静止反馈律驱动抓取执行，从而完全消除了轨迹规划、存储与抓取选择环节。

◆ 提出构型空间抓取距离场（GDF），通过softmin聚合N个抓取候选构型，并证明其与真实集合距离的偏差上界为log N/ρ。

◆ 将控制命令通过CBF-CLF二次规划滤波，约束自碰撞、工作空间、物体与障碍物保持安全距离，并以松弛变量显式报告受阻情况，证明闭环安全集前向不变。

◆ 针对手-物接触切换非光滑问题，在预抓取构型处采用滞回切换抓取闭合与保持模式，并设计力矩质量CBF将实际抓取的力闭合裕度约束在保持起始时刻的规定容差内。

◆ 在固定基座机械臂与Unitree G1人形机器人上完成仿真验证，在50个物体中成功抓取并提起46个，已执行抓取中位保留94%的合成质量裕度，每个20ms控制步仅耗时0.09ms求解QP。</td></tr>
<tr><td>2026-07-31</td><td>MROPE: A Multi-Robot Safe Cooperative Strategy via combined Predictive Safety Filters and Ellipse-based Constraint Compression<br><a href='http://arxiv.org/pdf/2607.29203'>论文</a></td><td>本文针对密集障碍环境中无人机集群追踪动态目标所面临的计算与安全双重挑战，提出了名为MROPE的分层协同安全策略。该方法通过将高层协同监视任务与底层严格局部安全需求解耦，实现了任务执行与安全保障的独立优化。

◆ 提出椭圆约束压缩机制，将每个无人机周围复杂的多障碍几何动态聚合为单一安全包围椭圆，大幅降低计算复杂度。

◆ 采用分布式聚合优化算法实现集群高层协同跟踪，提升系统的可扩展性。

◆ 设计去中心化共识方案用于安全区域计算，增强多机间的信息一致性。

◆ 引入局部预测安全滤波器（PSF）实现实时避碰，确保严格的局部安全约束。

◆ 通过虚拟与真实环境实验验证了框架在实时效率与可扩展性方面优于集中式方法。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-07</td><td>Unordered Landmark Visual Navigation<br><a href='http://arxiv.org/pdf/2608.06833'>论文</a></td><td>本文针对图像目标导航依赖时序视频流或深度传感器等强先验的问题，提出无序地标视觉导航（ULVN）框架，仅依靠RGB图像即可在无时间顺序和里程计信息的条件下完成导航任务。该方法将建图、定位与规划统一整合，系统性地缓解了感知混淆、错误关联和建图失败等问题。

◆ 基于几何校验与最大生成森林精炼的二维拓扑地图构建方法，直接从无序图像集合中生成鲁棒拓扑结构
◆ 图信念传播滤波器结合熵自适应融合的全局定位机制，摆脱对序列启发式的依赖
◆ 动态子目标规划策略，实现闭环导航中的稳定执行

在仿真和真实场景中的大量实验表明，ULVN显著优于当前最优方法。</td></tr>
<tr><td>2026-08-07</td><td>CrossTracer: Cross-Embodiment Navigation via VLA Model Reasoning and Trace Residuals Adapting<br><a href='http://arxiv.org/pdf/2608.06688'>论文</a></td><td>CrossTracer针对跨形态机器人导航中VLA模型忽略机器人本体运动约束的痛点,提出了一种基于自适应轨迹残差的两层框架,实现了语义推理与物理可行性之间的统一。框架将导航计划表示为归一化的图像平面航点,作为跨形态泛化的统一接口。

◆ 提出VL-Tracer模块,基于预训练VLA模型根据自我中心观测和灵活的目标描述预测初始导航轨迹

◆ 提出CE-Adapter细化模块,通过视觉可通行性线索、机器人本体身份和初始轨迹预测本体条件化的残差修正

◆ 提出CE-RRT*算法,将全景分割转换为机器人条件化的可通行性代价图,自动生成成本最小化的像素空间轨迹,避免昂贵的人工标注

◆ 构建NaviTrace基准,全面测试从观测、语言指令和机器人类型生成本体一致导航轨迹的能力,总分45.68超越Gemini-2.5-Pro达10.01分,提升28.1%

◆ 在轮式和腿足机器人上完成真实部署,验证了导航成功率和执行效率的提升,体现了方法的实用价值。</td></tr>
<tr><td>2026-08-06</td><td>A Low-Latency ASIC Architecture for Real-Time Line Segment Detection<br><a href='http://arxiv.org/pdf/2608.06439'>论文</a></td><td>本文提出了一种面向实时线段检测的低延迟ASIC架构，基于步长算法并针对硬件实现进行了深度优化，旨在解决传统深度学习方法资源消耗大、经典算法延迟不稳定的难题。该架构采用全流水线设计，每个时钟周期处理一个像素，具有确定性延迟特性，在45nm CMOS工艺下实现VGA分辨率325 FPS、全高清48 FPS的吞吐量，功耗仅25.54 mW，面积为0.412 mm²。

◆ 基于步长算法的硬件定制化设计，将五种ASIC优化技术融合：寄存器式行缓冲与数据复用、无乘法器MCM滤波、8类角度量化、类CAM的关联存储单周期匹配，以及优化的重复线段去除机制。

◆ 全流水线单像素/周期处理架构，实现确定性低延迟，适合实时嵌入式视觉系统。

◆ 在45nm工艺下相比90nm Line Hough变换ASIC，功耗降低49%，帧率提升超过1.6倍，125 MHz时VGA分辨率可达406 FPS，性能优势显著。

◆ 以极小的芯片面积（0.412 mm²）和低功耗（25.54 mW）满足边缘计算场景对实时性、低功耗与小型化的综合需求。</td></tr>
<tr><td>2026-08-06</td><td>Acoustic-driven millimetric helical robot: ultrasonic synergistic manipulation in confined fluidic environment<br><a href='http://arxiv.org/pdf/2608.05746'>论文</a></td><td>本文针对毫米级机器人在受限生物环境中声学推进效率不足的问题，提出了一种协同多声场操控策略，通过声辐射力与声流效应的协同作用实现可控运动。多物理场仿真揭示了组合声场下螺旋机器人的动力学机制，实验验证了平面导航、倾斜爬行和垂直运动等多种运动能力。半自主导航实验表明超声协同显著提升了机动性能。猪静脉血管离体测试进一步证实了协同声场支持单向与往复运动的可行性。该研究为声学微操控向毫米尺度拓展提供了机理基础，推动了生物医学应用中机器人灵活可控运动的发展。

◆提出声辐射力与声流协同的多声场驱动方法，解决毫米级机器人在受限环境中推进效率低的难题

◆建立多物理场耦合仿真模型，揭示组合声场下毫米级螺旋机器人的动力学机制

◆在猪静脉血管等生物受限环境中验证了多种运动模式的可行性，拓展了声学操控的生物医学应用场景...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-06</td><td>PathCover: A Fast Convex Decomposition along a Path via Randomized Iterative Space Partitioning (RISP) on Point Clouds<br><a href='http://arxiv.org/pdf/2608.05586'>论文</a></td><td>针对自主机器人导航中实时走廊生成的计算瓶颈,本文提出PathCover框架及其核心算法RISP,直接从原始点云数据构建凸多面体走廊。

◆ 提出RISP随机化迭代空间划分算法,在温和概率消除条件下实现期望线性时间复杂度,比现有走廊生成方法快一个数量级,同时保持相当的走廊体积。

◆ 沿任意无障碍参考路径生成重叠的无障碍凸多面体序列,可安全约束下游MPC和轨迹优化问题。

◆ 数学上严格证明算法有限步终止,并保证沿参考路径的连续推进。

◆ 在合成与真实LiDAR数据集上完成基准测试,并通过四旋翼高保真仿真与搭载实时LiDAR的四足机器人实物部署完成端到端验证,证实了算法的实时性与实用性。</td></tr>
<tr><td>2026-08-05</td><td>Toward Integrating Adaptive Experience Replay and Online Uncertainty Estimation in Safe Actor-Critic Optimal Control<br><a href='http://arxiv.org/pdf/2608.04732'>论文</a></td><td>本文针对安全强化学习中障碍物过滤、不确定性估计与经验回放通常被分开处理的问题，提出了一种集成式安全Actor-Critic最优控制架构。在该架构中，不确定性估计在线更新控制屏障函数所用的障碍几何形状，滤波干预与估计残差共同决定回放优先级，并且评论家从实际执行的动作而非标称动作中学习。作者在二维机器人导航任务中，对六种组件匹配的配置在相同训练预算、随机种子和扰动下进行了系统比较，包括中等后训练测试、十一级感知噪声扫描以及乘数为6.0的极端压力测试，在极端测试中集成配置在五个种子中均无接触并到达目标点。

◆ 提出将不确定性估计、安全滤波与自适应经验回放耦合的集成安全Actor-Critic架构。

◆ 利用在线不确定性估计动态更新控制屏障函数所用的障碍几何形状。

◆ 基于滤波干预和估计残差自适应调整经验回放优先级。

◆ 批评家从实际执行动作（而非标称动作）进行学习，更贴合真实控制行为。

◆ 给出有限训练下的回放曝光界和考虑估计误差与可行性的鲁棒屏障条件。</td></tr>
<tr><td>2026-08-05</td><td>A Vision-based Control Framework for Real-time Autonomous UUV Operations<br><a href='http://arxiv.org/pdf/2608.04723'>论文</a></td><td>本文针对无人水下航行器(UUV)在动态、视觉挑战性水下环境中的自主作业需求,提出了一种全集成视觉驱动的实时定位、导航与建图一体化框架。该框架能够在真实运行中同时实现网相对定位和全局定位,并实时生成连续的三维环境地图,显著提升了系统的鲁棒性和适应性。研究团队通过合成数据集(含真值)以及UUV实船自主导航实验对所提方法进行了全面验证,实验结果证明了其实时性能与稳健性。

本文的核心创新点可概括如下:

◆ 构建了面向UUV的全集成视觉定位-导航-建图一体化流水线,实现了多任务协同运行的端到端框架。

◆ 同步支持网相对定位与全局定位双模式,赋予UUV在网箱等受限场景与开阔水域的灵活作业能力。

◆ 在动态、视觉退化等复杂水下条件下实现了连续三维地图的实时构建,提升了环境感知的时间连续性。

◆ 通过合成数据与实船在线实验双重验证,兼顾了算法精度评估与工程落地可靠性,为海洋机器人现场部署提供了技术基础。</td></tr>
<tr><td>2026-08-04</td><td>Lightweight 3D Object Detection via Mamba-Based Knowledge Distillation<br><a href='http://arxiv.org/pdf/2608.03490'>论文</a></td><td>本文针对激光雷达三维目标检测中精度与计算效率难以平衡的问题，提出了一种基于Mamba的轻量化知识蒸馏框架。该方法通过选择性体素空间特征对齐，将强教师模型在目标级别的体素表征迁移到轻量级学生网络中，显著降低了计算开销。实验在公开数据集和真实场景数据上均验证了该方法在保持竞争精度的同时大幅减少计算量。

◆ 提出基于Mamba的轻量化三维目标检测知识蒸馏框架，通过选择性体素空间特征对齐实现教师到学生的知识迁移。

◆ 设计了多分支Mamba教师骨干网络，利用选择性状态空间的线性时间序列建模优势提取高效特征。

◆ 提出了框感知的特征传递机制，通过空间对应的体素特征对齐实现精确的知识传递。

◆ 构建了基于Mamba的投影模块，在教师与学生网络之间实现体素特征的高效对齐与融合。

◆ 在公开数据集和真实数据上的实验表明，该方法在显著降低计算负载的同时保持了与先进方法相当的检测精度。</td></tr>
<tr><td>2026-08-04</td><td>UniNav: A Unified World-Action Diffusion Model for Visual Navigation<br><a href='http://arxiv.org/pdf/2608.03244'>论文</a></td><td>UniNav提出了一种统一的视觉导航框架，将未来视觉观测预测与路径点轨迹生成整合到单一扩散过程中，通过联合去噪视觉与动作token实现预测与决策的统一。

◆核心创新是将世界模型与动作策略融合为单一Transformer扩散过程，同时生成未来图像观测和连续路径点轨迹，避免了传统世界模型所需的昂贵规划rollout。

◆引入几何感知的相机token增强空间定位能力，使模型在复杂环境中具备更准确的空间理解。

◆采用混合训练策略，同时利用带轨迹标注的导航数据和纯视频数据，使模型能够从多样化视频中学习而无需昂贵的动作标注。

◆提出两种推理变体：UniNav-Full联合预测可解释的未来观测及对应轨迹，UniNav-Fast在推理时去除未来图像token以实现0.1秒低延迟的轨迹预测。

在多个导航基准测试中，UniNav在ATE指标上均优于最强基线，实现了精度与效率的平衡。</td></tr>
<tr><td>2026-08-03</td><td>Safe and robust tube-based path-following for robot navigation<br><a href='http://arxiv.org/pdf/2608.02530'>论文</a></td><td>该论文提出了一种基于Tube控制的安全鲁棒路径跟随导航框架，使机器人在未知且杂乱环境中能够同时实现避障反应式安全性和对目标路径的收敛保证。方法集成了人工矢量场引导与反步控制，构建了标称综合制导与控制方案，并利用障碍函数和李雅普诺夫理论给出了安全与稳定性的形式化证明，通过大量数值仿真验证了框架的有效性。

◆ 提出基于Tube的控制策略，有效抑制未知但有界外部扰动对系统的影响，保证跟踪误差始终处于安全管内。
◆ 设计平滑距离函数，实现连续控制律下的无缝避障，避免传统方法中控制不连续的问题。
◆ 构建统一控制目标，在碰撞规避与路径跟随之间实现动态平衡。
◆ 引入自适应控制分量，进一步增强对外部扰动的鲁棒性。</td></tr>
<tr><td>2026-08-03</td><td>DF$^3$: World Modeling via Decoder-Free Feature Forecasting in Autonomous Navigation<br><a href='http://arxiv.org/pdf/2608.02428'>论文</a></td><td>该论文针对自动驾驶场景中的世界建模与未来状态预测任务,指出传统像素级生成方法计算开销大,基于特征的方法仍依赖重型解码器,存在效率瓶颈。为此,作者提出Decoder-Free Feature Forecasting(DF³)框架,完全在潜在空间中建模世界演化并直接推导任务输出,无需任何解码器,实现了高效的感知与控制一体化。

◆核心创新一是&quot;解码器自由&quot;设计:将可学习的空间查询注入冻结视觉基础模型的末端块,直接提取未来状态表征,从根本上消除了传统解码器带来的计算负担。

◆核心创新二是运动感知的上下文融合机制(MACF):通过粗光流warp与细粒度潜在交叉相关性的统一结合,使查询与历史token表征显式对齐,从而精确预测下一帧特征。

◆核心创新三是任务查询解耦策略:训练一组专用任务查询对预测特征进行探测,使感知预测与下游决策输出在统一框架内高效衔接,具备良好的灵活性。

在公开基准和机器人仿真器的零样本部署实验中,DF³在性能与SOTA方法相当的同时,显著提升了推理效率,展现出在端到端自主导航中的实用价值。</td></tr>
<tr><td>2026-08-02</td><td>Resilient Consensus-Based Target Tracking under False Data Injection Attacks in Multi-Agent Networks<br><a href='http://arxiv.org/pdf/2608.01222'>论文</a></td><td>本文针对多智能体网络中分布式目标跟踪在虚假数据注入攻击下面临的脆弱性问题，提出了一种基于共识的弹性目标跟踪算法。该算法将近乎匀速运动模型与基于饱和度的滤波机制相结合，有效抑制测量中的脉冲式异常扰动，实现鲁棒的分布式状态估计。为应对对抗性攻击，研究引入了基于创新阈值动态检测与隔离机制，可在异常数据污染全局估计前识别并剔除可疑测量。仿真结果表明，增加网络连通性和共识迭代速率可提升估计精度与收敛速度，而合理调节的饱和滤波能在故障抑制与精确估计间取得良好平衡。在局部、协调式及瞬态虚假数据注入攻击下，所提机制能够成功识别被攻陷的智能体并阻止其数据破坏全局估计。整体而言，该研究提供了一种轻量化的容错方案，显著增强了分布式目标跟踪的准确性与抗攻击能力，且不带来过高的通信与计算开销。

◆ 提出融合近匀速运动模型与饱和滤波的共识估计算法，提升对脉冲式测量扰动的鲁棒性。
◆ 设计基于创新阈值的动态虚假数据注入检测与隔离机制，在数据融合前主动排除可疑测量。
◆ 通过仿真验证算法在局部、协调及瞬态等多种攻击场景下的弹性与实用性。</td></tr>
<tr><td>2026-08-01</td><td>LOCUS-DT: Localization via Observation-Conditioned Uncertainty Scoring with Digital Twins<br><a href='http://arxiv.org/pdf/2608.00406'>论文</a></td><td>LOCUS-DT提出了一种基于数字孪生的室内定位框架，将快照定位问题建模为对发射机位置的后验推断，避免了传统单点估计在多模态似然分布下的局限性。系统利用已知环境的射线追踪数字孪�生成候选位置的合成多径剖面，并与实测信道剖面进行比对。

◆ 核心创新在于设计了一种新颖的学习评分函数，仅比较固定数量的主导镜面路径，使其对数字孪生环境建模误差和物理信道估计误差均具有鲁棒性。

◆ 框架在多种环境的集合上进行训练，确保了对未见布局的泛化能力。

◆ 实验基于Sionna射线追踪后端验证，结果表明LOCUS-DT能够比高斯及高斯混合基准方法更准确地捕捉室内定位中固有的尖锐多模态后验结构，从而提升复杂遮挡与多径环境下的定位精度。</td></tr>
<tr><td>2026-07-30</td><td>X-NavDP: Generalizing Navigation Diffusion Policy to Novel Behavior and Embodiments with Group Q-score Reweighted Matching<br><a href='http://arxiv.org/pdf/2607.28560'>论文</a> | <a href='https://yty-sky.github.io/x-navdp-project-page'>代码</a></td><td>本文针对预训练导航扩散策略在新形态和复杂场景中泛化能力不足的问题，提出了一种数据高效的扩散强化学习后训练框架GQRM。由于扩散策略的似然难以计算，传统策略梯度方法在此场景下不稳定且探索效率低，研究者通过引入自举式探索策略和分组Q值归一化机制来稳定扩散策略的强化学习训练，并保留了预训练策略的先验知识。最终得到微调策略X-NavDP，在异构机器人形态的分布式在线RL训练后，仿真和真实场景中的跨形态视觉导航性能均达到最优水平，整体成功率从61.20%提升至84.28%，真实困难场景从10%提升至65%。

◆自举式探索与行为扰动机制：在保留预训练策略先验的同时实现高效探索，避免破坏已有导航能力。
◆分组Q值归一化与重加权得分匹配：通过计算每条轨迹在每个状态上的价值，实现稳定且高效的扩散策略强化学习更新。
◆跨形态异构机器人协同训练框架：支持多种机器人形态同时进行分布式在线RL训练，显著提升策略对不同本体的泛化能力。</td></tr>
<tr><td>2026-07-30</td><td>Learning Social Robot Navigation By Sensing Human Legs<br><a href='http://arxiv.org/pdf/2607.27922'>论文</a></td><td>本文针对移动机器人在行人环境中导航的问题，指出传统方法将行人简化为圆形等几何形状，忽略了2D LiDAR近地面扫描时主要观测到的是腿部运动而非完整人体的关键事实。为此，作者提出了CALF（Convolutional Attention for Leg Features）端到端神经网络架构，结合卷积层、注意力机制和MLP直接从LiDAR扫描中解析腿部运动特征并生成安全导航指令。

◆ 提出CALF网络架构，首次将卷积、注意力机制与MLP结合，直接从LiDAR扫描数据中学习腿部运动特征并输出导航策略，突破了将行人简化为几何形状的传统范式。

◆ 构建LegNav轻量级2D仿真器，集成了2D LiDAR光线追踪与新颖的行人步态模型，为基于深度强化学习的端到端训练提供了高效平台。

◆ 基于JAX实现LegNav，单消费级GPU一小时即可完成训练，并通过TurtleBot 4实现零样本真实场景部署，验证了方法的实用性和社交合规性。</td></tr>
<tr><td>2026-07-29</td><td>Context-Informed Ship Trajectory Prediction via Conditional Attention<br><a href='http://arxiv.org/pdf/2607.27418'>论文</a></td><td>本文针对船舶长期轨迹预测这一海事安全关键问题，指出现有Transformer方法仅依赖历史运动学状态、将环境变量作为对等特征处理，忽略了天气对船舶动态的单向调制作用。提出Conditional Informer编码器-解码器架构，将轨迹预测重新建模为条件生成任务，核心包含两项创新。◆Conditional Attention机制：通过交叉注意力使船舶状态显式查询环境上下文，编码了环境调制船舶动态但不反之的物理先验，区别于传统的联合分布建模方式。◆Modality Masking训练策略：针对传感器间歇性失效场景，通过随机掩码环境模态防止模型走捷径学习，保障传感器回退时的预测鲁棒性。在AIS和ERA5数据上的大量实验表明，该方法在上下文可用时预测精度较基线提升15.4%，且在传感器回退时将误差降低近一个数量级。</td></tr>
<tr><td>2026-07-28</td><td>DVPSFormer: Efficient Online Depth-aware Video Panoptic Segmentation for Autonomous Driving<br><a href='http://arxiv.org/pdf/2607.26165'>论文</a> | <a href='https://royyang0714.github.io/DVPSFormer'>代码</a></td><td>这篇论文提出了DVPSFormer，一种面向自动驾驶的统一在线4D场景理解架构，旨在同时完成度量深度估计、语义分割和实例跟踪，解决现有深度感知视频全景分割方法计算开销大、依赖多阶段管线或离线跟踪的问题。

◆ 显式场景离散化（ESD）机制：利用分割查询分别表征前景与背景区域，为深度解码提供结构化场景表示。
◆ 离散到连续（D2C）深度头：基于ESD输出以单次前向解码度量深度，将语义学习与几何学习紧耦合并显著降低推理延迟。
◆ 在线多数投票（OMV）机制：在实例跟踪阶段利用时序一致性精化分类结果，提升跟踪的稳定性与准确性。

该方法在Cityscapes-DVPS和SemKITTI-DVPS基准上均刷新了最优性能，为在线机器人感知提供了一套高效且简洁的解决方案。</td></tr>
<tr><td>2026-07-27</td><td>Accuracy potential of visual localization exploiting high-end street-level imagery<br><a href='http://arxiv.org/pdf/2607.24409'>论文</a> | <a href='https://fhnw-muttenz-vl-dataset.github.io/'>代码</a></td><td>本文针对视觉定位在测量级精度需求下的潜力尚未被系统研究这一空白,提出了一套完整的解决方案。研究的核心动机是现有公开户外数据集缺乏亚厘米级真值位姿,无法满足测绘级评估要求。

主要创新点如下:

◆ 提出了一种可扩展的视觉定位流水线,直接以高精度地理参考的街景图像作为场景表示,并融合先验引导的参考候选选取、即时局部SfM重建与PnP位姿估计,实现了高精度定位。

◆ 发布并开源了FHNW Muttenz真实数据集,覆盖连续10公里街道网络,包含两次相隔约1.5年的移动测量采集数据、四种相机与五个典型场景,所有图像经过精确配准,可提供亚厘米级6自由度真值位姿。

◆ 基于该数据集,首次系统评估了视觉定位达到1至5厘米平移精度和0.05至0.1度旋转精度的潜力,最佳条件下可达1厘米和0.03度,证明视觉定位可与测量级GNSS互补,为消费级设备实现全自动三维地理空间数据采集铺平道路。</td></tr>
<tr><td>2026-07-27</td><td>GaussianSeed: Hierarchical Gaussian Seeding for High-Resolution 3D Occupancy Prediction<br><a href='http://arxiv.org/pdf/2607.20071'>论文</a> | <a href='https://github.com/Athameral/GUSD'>代码</a></td><td>该论文针对以视觉为中心的3D占据预测在高分辨率下计算成本过高的问题，提出了GaussianSeed框架。◆提出渐进式多尺度高斯占据预测框架，将高斯基元组织成由粗到细的层次结构，有效绕开了密集表征的内存瓶颈，实现了0.1米空间分辨率下的实时推理能力。◆构建了TJScenes全景六相机占据数据集，提供0.1米精细标注，可用于高分辨率几何感知的全面评估。在Occ3D-nuScenes和TJScenes上的大量实验表明，GaussianSeed在所有评估方法中延迟最低，同时保持极具竞争力的精度，推进了高分辨率3D占据预测的效率与质量前沿。该工作的核心价值在于为自动驾驶和机器人导航提供了一种高效且高质量的密集场景表征新范式。</td></tr>
<tr><td>2026-07-29</td><td>EA-Nav: Learning Safe Visual Navigation Policies with Embodiment Awareness<br><a href='http://arxiv.org/pdf/2607.19880'>论文</a></td><td>EA-Nav提出了一种基于模仿学习的跨具身视觉导航框架，旨在解决不同形态智能体因相同视觉观测对应不同动作而导致的动作歧义问题。该方法采用模块化的多阶段设计，在预训练阶段从互联网视频中构建跨具身导航数据集，并将具身几何信息作为条件令牌注入模型，从而有效降低动作预测的歧义性。在微调阶段，作者设计了基于解耦架构的多模态信息注入机制，通过轨迹增广策略生成高风险样本，分别训练空间感知与风险感知修正模块，使模型能够显式地融合具身几何信息以实现安全导航。

◆ 从互联网视频中构建跨具身导航数据集，并引入具身几何作为条件令牌，缓解了相同观测下动作歧义的问题。

◆ 提出基于解耦架构的多模态信息注入机制，将视觉、几何等异构信息分别处理后再融合，增强策略对不同具身的适应性。

◆ 设计轨迹增广策略生成高风险样本，分别训练空间感知与风险感知修正子模块，将具身几何显式融入到安全导航决策中。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-10</td><td>Energy-Structured Latent World Models with Neural Time Fields for Physically Constistent Open-World Motion Planning<br><a href='http://arxiv.org/pdf/2608.09876'>论文</a></td><td>本文针对具身AI中物理一致的运动规划难题，提出能量结构化潜在世界模型（ELWM），通过将能量与动量显式嵌入潜在状态，结合耗散与控制端口保证严格因果转换，使模型能够从多模态RGB-D与惯性交互数据中学习可复用的物理知识，从而实现物理一致的未来预测。

◆ 提出Energy-Structured Latent World Model (ELWM)，将能量与动量显式编码进潜在状态，通过耗散与控制端口约束状态转移，从根本上解决现有潜在模型物理隐式吸收、无法形成可复用知识的问题。

◆ 构建Physics-Conditioned Neural Time Fields (PC-NTF)，将ELWM通过Eikonal方程融入到达时间场，生成物理信息驱动的导航策略，桥接预测式世界模型与安全可行的运动规划。

◆ 在保留场景的实验中全面优于基线方法：0.8秒运动预测NRMSE由0.36降至0.29，导航成功率从81.3%提升至89.7%，SPL从0.64提升至0.73，物理碰撞率从12.1%降至5.8%，Eikonal残差从0.083降至0.031。</td></tr>
<tr><td>2026-08-10</td><td>Entanglement-Free Trajectory Planning for Tethered Mobile Robots with a Slack Tether<br><a href='http://arxiv.org/pdf/2608.09860'>论文</a></td><td>本文针对带有松弛缆绳的系缆移动机器人，提出了一种能够在运动规划全过程中考虑缆绳缠绕状态的规划算法，能够在含静态障碍物的环境中计算出动态可行且避免缠绕的轨迹。该方法的核心思路是将缠绕避免约束整合到规划管线的每一个阶段，而非仅在轨迹优化阶段进行处理。算法采用三步式管线：首先构建系缆机器人无缠绕构型空间的拓扑模型，然后基于该模型生成满足无缠绕约束的候选路径，最后通过求解同伦约束的轨迹生成问题得到动态可行的最终轨迹。

◆ 构建了系缆机器人无缠绕构型空间的拓扑模型，为路径搜索提供几何基础。

◆ 基于拓扑模型生成满足无缠绕约束的候选路径集合，确保路径层面的安全性。

◆ 通过同伦约束的轨迹生成，将拓扑层面的缠绕避免与动态可行性相结合。

仿真结果表明，该方法能够有效避免缠绕约束的违反，生成更安全可靠的运动轨迹。</td></tr>
<tr><td>2026-08-10</td><td>FactorDrive: Adaptive Multi-Step Reasoning Driven by Planning-Critical Factors for End-to-End Autonomous Driving<br><a href='http://arxiv.org/pdf/2608.09591'>论文</a></td><td>该论文针对端到端自动驾驶中视觉语言模型空间物理证据融合不足、推理适应性粗糙以及推理路径优化未充分探索等问题，提出FactorDrive框架，以规划关键因子(PCFs)驱动自适应多步推理。◆构建PCF-CoT思维链数据集，将规划推理锚定于轨迹相关的空间物理证据，并围绕场景特定PCFs组织推理过程，使推理路径的组成与深度能够适配不同规划需求。◆设计质量搜索引导的分组相对策略优化方法(QS-GRPO)，将蒙特卡洛树搜索与轨迹级规划奖励结合，自动发现并优化具有更高规划质量的推理路径。◆在nuScenes开放环和NAVSIM闭环导向基准上均取得最先进的规划性能。</td></tr>
<tr><td>2026-08-09</td><td>360CityArena: A Realistic Virtual Urban Navigation Benchmark for Embodied Agents<br><a href='http://arxiv.org/pdf/2608.08814'>论文</a></td><td>360CityArena是一个面向具身智能体的城市导航基准测试平台，旨在解决现有户外基准在真实感和复杂度上与现实城市环境差距过大的问题。该平台基于日本东京秋叶原街区的真实360度视频重建而成，涵盖602段视频和85条街道，提供了175个由人工精心设计的任务，任务分为环境理解、路径推理和空间推理三大类，全面考察定位、地标搜索、路径规划与关系空间推理等城市探索所需的核心能力。实验结果表明，即便是当前最先进的Gemini 2.5 Flash模型，其表现也仅为17.1%，远低于人类77.3%的水平，揭示了城市级具身导航与推理任务仍面临巨大挑战。该工作为未来研究提供了一个必要且具有挑战性的真实感城市导航测试平台。

◆ 基于602段360度视频构建了秋叶原街区的真实感三维城市环境，显著提升了户外导航基准的视觉保真度
◆ 设计了涵盖环境理解、路径推理与空间推理三大类别的175个细粒度任务，支持多维度的能力评估
◆ 首次系统性地量化了当前LMM智能体与人类在城市级导航任务上的巨大性能差距，明确了未来研究方向...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-09</td><td>PEEL: Parallel Extraction for Long-Horizon Disassembly Planning via Scale-Invariant Sampling<br><a href='http://arxiv.org/pdf/2608.08773'>论文</a></td><td>PEEL提出了一种用于长视野多部件物体拆卸的并行规划算法，旨在解决狭窄通道下无碰撞拆卸序列的计算难题。算法采用尺度不变采样方案，通过burn-in阶段估计物体尺度，并利用方向采样器高效完成单物体运动规划。◆创新点一：尺度不变采样机制，结合burn-in阶段尺度估计与方向采样器，显著提升狭窄通道下的规划效率。◆创新点二：多臂赌博机RRT（MAB-RRT）规划器，根据奖励信号自适应切换不同采样器，增强了算法的鲁棒性。◆创新点三：并行运行批量规划器以构建有序拆卸图，明确部件移除顺序，支持长视野拆卸任务。实验表明，MAB-RRT在76个装配体上实现100%单部件拆卸成功率，并在Fetch机械臂上成功解决4个包含10至17个部件的复杂长视野拆卸问题。</td></tr>
<tr><td>2026-08-08</td><td>AOC-CBS: Anytime-Optimal Continuous-time Conflict-Based Search for Generalised Multi-Agent Path Finding<br><a href='http://arxiv.org/pdf/2608.08175'>论文</a></td><td>本文针对多智能体路径规划（MAPF）传统假设的局限，提出了一种广义MAPF问题表述，取消了离散时间、同质智能体、单一目标以及到达目标后必须停留等限制，能够处理异构车队、非几何冲突、任务序列及完成后继续移动等复杂情形。

◆ 提出AOC-CBS算法，一种针对广义MAPF的精确且完备的求解器，具备任意时刻最优性保证，在运行过程中持续输出已知最优性间隙上界的可行解。

◆ 引入新的修复函数——Tier-Prioritized Safe Interval Path Planning（分层优先安全区间路径规划），可与多种修复函数组合使用。

◆ 支持多核并行计算，扩展了问题求解规模。

实验表明，AOC-CBS在求解最优解时与精确求解器OC-CBS表现相当，而在允许有界最优性间隙时，可将可求解规模从数十个智能体扩展到数百个，并在混合非凸智能体沿光滑动力学可行轨迹运动的场景中得到了验证。</td></tr>
<tr><td>2026-08-08</td><td>SurgWMBench: A Vision-Based Benchmark for World-Modeling Surgical Instrument Motion Planning<br><a href='http://arxiv.org/pdf/2608.08070'>论文</a></td><td>这篇论文指出现有手术视频理解方法侧重于阶段识别，而运动预测方法缺乏对视觉状态演化的联合建模，手术世界模型评估又过度依赖FVD等生成质量指标，与实际运动规划需求严重脱节。为此，作者提出SurgWMBench基准，基于术中图像序列和历史器械轨迹，评估近期器械运动预测的几何准确性、时间连贯性及在连续展开或输入扰动下的稳定性。

◆ 构建了首个面向手术世界模型运动规划能力的视觉基准，填补了该领域缺乏公开数据集和标准化评估协议的结构性空白。

◆ 强调运动几何精度与时间一致性评估，直接衡量预测轨迹是否可执行，而非仅关注视觉生成质量。

◆ 引入稳定性评估维度，测试模型在持续展开和输入扰动下的鲁棒性，提升下游规划任务的实用性。

该工作为手术世界模型从视觉生成向可行动规划的发展提供了关键评测基础设施。</td></tr>
<tr><td>2026-08-07</td><td>Drone-Assisted UAV-UGV Collaboration for Autonomous Navigation in Snow-Covered Terrain<br><a href='http://arxiv.org/pdf/2608.07797'>论文</a></td><td>本文针对高海拔雪地环境能见度低、地面不稳定的问题，提出一种无人机-无人车(UAV-UGV)协同自主导航框架。系统采用高效U-Net网络实现实时道路分割，并结合合成雪景数据增强技术达到96.5%的分割精度。针对无人机定位，设计了融合GPS与IMU数据的扩展卡尔曼滤波器，最大位置误差仅为±0.5米。无人车位置由YOLOv5目标检测与无人机搭载的RGB-D相机深度数据联合估算。基于上述感知与定位结果，动态路径规划算法能够针对雪堆遮挡实时调整行驶路径，实测在视线受阻环境中仍可成功导航。

创新点如下：
◆ 面向计算约束的高效U-Net架构设计，在满足实时性要求的同时保持高精度道路分割
◆ 合成雪景数据增强方法，提升模型在复杂雪地条件下的鲁棒性
◆ 融合GPS与IMU的扩展卡尔曼滤波定位方案，最大误差控制在±0.5米
◆ 基于YOLOv5与RGB-D深度信息的跨平台无人车视觉跟踪管道
◆ 考虑雪堆遮挡的动态路径规划算法，可在视线受阻环境中实现稳定导航...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-07</td><td>Hölder Signed Distance: A Differentiable, Signed, Parallelizable Metric for Robotics<br><a href='http://arxiv.org/pdf/2608.07707'>论文</a></td><td>本文针对机器人运动规划与控制中凸多面体间的距离计算问题，提出了一种新型可微符号距离度量Hölder signed distance。现有欧几里得符号距离函数(SDF)并非处处可微，而其他可微替代方案往往牺牲可微性、符号信息或计算效率。该方法的核心思想是首先提出Hölder意义下的可微最小和最大算子，然后用它们替换经典SDF公式中的min-max运算，从而获得全程可微且保持符号信息的距离函数。

◆ 提出Hölder最小算子和Hölder最大算子，作为传统min-max算子的可微替代，使距离计算在所有点处均可微。

◆ 基于上述算子构造凸多面体间的Hölder符号距离，保持符号信息的同时实现全空间可微。

◆ 采用闭式计算而非迭代算法，避免了收敛性问题，并天然适合GPU并行化，大幅提升计算效率。

◆ 通过运行时对比和机械臂控制实验验证了该方法在实时优化中的实用性和优越性能。</td></tr>
<tr><td>2026-08-07</td><td>Detection and Ranging of Transient Extrinsic Contacts Based on 6D Dynamic Tactile Sensing<br><a href='http://arxiv.org/pdf/2608.07075'>论文</a> | <a href='https://humitlab.github.io/TECDAR/'>代码</a></td><td>本文针对机器人在精细操作中难以感知抓取物体与环境之间瞬时微小碰撞的问题，提出了TECDAR（瞬态外部接触检测与测距）方法。

◆ 创新地采用尺寸仅2.5×3 mm的6D IMU作为动态触觉传感器核心，以7 kHz采样率捕获亚毫秒级指尖形变，数据流仅84 KB/s，兼顾高带宽与紧凑数据量。

◆ 提出了融合触觉数据与机器人位姿的扩展卡尔曼滤波（EKF）算法，可在180 ms内达到毫米级的外部接触定位精度。

◆ 实验结果表明，在线接触和点接触任务中平均定位精度约7 mm，并支持毫秒级轨迹修正以及纯触觉环境探索与建图。

该方法有望在精密装配、手术辅助以及触觉主导的自主探索等场景中发挥重要作用。</td></tr>
<tr><td>2026-08-07</td><td>Real-time Whole-Body Motion Planning for Mobile Manipulators Carrying Arbitrarily Shaped Payloads via Kinematically-Coupled SVSDF<br><a href='http://arxiv.org/pdf/2608.07005'>论文</a></td><td>本文针对移动操作臂在杂乱环境中运输大型非凸负载的全身运动规划问题，提出了一种实时三层规划框架。前端采用链式分解的核函数碰撞检测方法，精确保留机器人和负载的真实几何形状并支持快速位级查询；中端将路径转化为平滑可行的连续轨迹，无碰撞时直接执行以避免冗余优化；后端基于运动学耦合SVSDF (KC-SVSDF) 沿运动链传播避障梯度，生成连贯的全身逃离方向。在差速驱动移动操作臂上的仿真与真实场景实验均验证了该框架的可靠性。

◆ 链式分解的核函数碰撞检测前端，紧凑存储任意形状负载几何并支持快速位级查询，最大限度保留可行空间
◆ 中端预处理阶段实现轨迹平滑化与可行性检查，无碰撞时直接执行以跳过耗时的后端优化
◆ 基于运动学耦合SVSDF (KC-SVSDF) 的后端轨迹优化，沿运动链传播避障梯度生成连贯的全身逃离方向
◆ 首次实现移动操作臂运输任意形状负载的实时全身运动规划，并完成真实场景下的紧致通道与杂乱环境验证...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-07</td><td>Decoupling Intention from Trajectory: A Representational Deduction Framework for World Action Models<br><a href='http://arxiv.org/pdf/2608.06994'>论文</a></td><td>该论文针对世界动作模型（WAMs）中高层物理状态演化与底层动作轨迹生成之间的表征纠缠问题，提出了名为PILOT的Representational Deduction（RD）框架，通过将运动思维链（CoT）作为模型的原生能力来弥合这一鸿沟。RD框架鼓励动作分支显式建模潜在的状态转移token，并将其作为CoT保留在推理空间中，从而引导细粒度的运动轨迹生成。该方法在复杂机器人操作任务中显著提升了WAMs的成功率和泛化能力，同时通过解耦高层运动语义与底层轨迹细节增强了模型的可解释性。此外，RD引入的丰富状态转移监督信号有效缓解了动作生成中的稀疏监督问题，使其成为一种高效的小样本真机微调策略。

◆ 揭示了现有WAMs中高层物理条件演化与底层动作轨迹生成之间的表征纠缠瓶颈
◆ 提出Representational Deduction框架，将状态转移token作为运动CoT原生融入动作模型
◆ 实现了高层运动语义与底层轨迹细节的解耦，提升模型物理可解释性
◆ 利用丰富状态转移监督缓解动作生成的稀疏监督问题
◆ 具备良好的架构兼容性，可作为小样本真机微调的高效策略并迁移至主流WAM架构...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-06</td><td>Plan-and-Avoid: Real-Time Aircraft Trajectory Coordination in a Multi-Agent Environment<br><a href='http://arxiv.org/pdf/2608.06648'>论文</a></td><td>本文提出一种实时&quot;规划与规避&quot;(PAA)框架,用于在多智能体空域环境中围绕已声明的优先航迹进行协同协调。该框架将优先航迹规划与协同避让建议生成统一于同一系统中,当优先航迹无法独立维持安全间隔时,系统会向附近航空器发出考虑其飞行性能约束的调整建议。论文以应急着陆规划器为典型应用,基于华盛顿特区真实ADS-B交通数据,在900余例迫降场景、超过140小时模拟飞行中进行了验证。结果显示,全部575个独立冲突均生成了可行建议,最差端到端响应时间为5.7秒,93.5%的建议满足RTCA DO-365规定的35秒时间阈值,验证了框架的低时延与可靠性。

◆ 首次将优先航迹规划与协同避让建议生成统一在同一实时框架内,实现&quot;边规划边避让&quot;
◆ 引入不确定性感知的安全间隔违犯预测,提升对真实空域不确定性的鲁棒性
◆ 生成符合飞行器性能约束的单向避让建议,且可适用于任何类型的已声明优先航迹
◆ 在个人计算机上实现最差5.7秒端到端响应,满足实时运行需求...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-06</td><td>A Precise Treatment of Soft Quotient Topology and Soft Covering Maps<br><a href='http://arxiv.org/pdf/2608.06525'>论文</a></td><td>本文系统建立了软商拓扑的基础理论框架,给出了软商拓扑的普适性质,并深入探讨了全局软拓扑与其参数切片之间的关系,指出仅依靠切片层次的商性质不足以刻画软商结构。研究还构建了相应的软商空间,并对软群作用及其轨道空间进行了细致分析。

◆ 提出了一套系统化的软商拓扑构造理论,并证明其满足普适性质,填补了该领域基础理论的空白。

◆ 揭示了参数切片商行为与全局软商之间的本质差异,明确指出切片层次的商性质不能充分表征软商结构。

◆ 针对现有文献中软覆盖映射定义不一致的问题,给出了精确且自洽的严格定义。

◆ 将理论框架应用于多智能体运动规划,有效降低了参数不确定性下的组合复杂度,展现了广泛的实际应用价值。</td></tr>
<tr><td>2026-08-06</td><td>Fast and Accurate: An Adaptive VLA Inference Framework through Environment-aware Model Selection<br><a href='http://arxiv.org/pdf/2608.06434'>论文</a></td><td>该论文提出了一种名为EMS（环境感知模型选择）的自适应VLA推理框架，旨在同时满足具身智能对长时域推理与实时闭环响应的需求。与现有紧耦合的双系统VLA架构不同，EMS将大型推理系统与轻量级反应系统完全解耦，并通过基于强化学习的切换策略根据实时反馈动态选择调用哪个系统，从而实现慢系统的稀疏使用，提升运行效率。

◆ 完全解耦且模块化的双系统架构，支持即插即用的模型替换，摆脱了端到端联合训练的束缚
◆ 基于强化学习的环境感知自适应切换策略，动态平衡预训练知识利用与运行时效率
◆ 轻量级反应系统实现高频闭环控制，在保持任务成功率的同时显著提升推理速度

在LIBERO基准测试中，EMS以93.4 Hz的有效动作频率达到了与大型基线相当的成功率，并在真实双臂操控任务中进一步验证了框架良好的可扩展性与泛化能力。</td></tr>
<tr><td>2026-08-06</td><td>Coordinated Multi-Robot Disassembly for Makespan Optimization of Large-Scale Assemblies<br><a href='http://arxiv.org/pdf/2608.05830'>论文</a></td><td>本文提出了一种名为CoMuDi的协调多机器人拆卸规划方法，旨在解决大型装配体拆卸过程中多机器人在受限工作空间内的协调任务与运动规划问题。CoMuDi以机器人团队、装配体及依赖图作为输入，生成包含抓取、放置和退出动作的复合任务，并通过时间约束传播机制使每个机器人尽早开始和结束任务，同时避免与邻近机器人发生碰撞。将时空RRT*（ST-RRT*）规划器集成到CoMuDi中，使个体任务的到达时间最小化，从而降低整体完工时间。实验对比了CoMuDi结合ST-RRT*与普通RRT*在不同时间约束下的表现，证明前者具有更高的成功率和更短的makespan。在多达49个零件和9个机器人的六种装配场景中验证表明，CoMuDi能够可靠地求解大规模拆卸问题，并生成低空闲时间的机器人路径。

◆ 提出CoMuDi框架，通过依赖图驱动的复合任务生成与时间约束传播机制，实现多机器人拆卸任务的高效协调与碰撞避免。
◆ 将ST-RRT*运动规划器与高层任务协调深度集成，在最小化个体任务到达时间的同时优化整体完工时间。
◆ 在包含最多49个零件和9个机器人的大规模装配场景中验证了方法的可扩展性与可靠性，相比传统RRT*显著提升成功率和效率。</td></tr>
<tr><td>2026-08-06</td><td>Iterative Hybrid Discrete-Continuous Viewpoint Planning for UAV Photogrammetry<br><a href='http://arxiv.org/pdf/2608.05718'>论文</a></td><td>无人机摄影测量需要适应复杂场景几何,传统飞行模式易产生局部重建误差。本文提出基于代理重建的迭代混合离散-连续视点规划方法,综合摄影测量启发式评分与聚类CMA-ES优化,自动识别弱观测区域,生成并迭代精炼候选视点,同时移除冗余视点。

◆融合离散采样与连续优化两种范式,使近距离细节视点与广域覆盖视点协同工作,平衡局部重建质量与全局图像网络鲁棒性。
◆构建点级与集合级双层评价体系,前者融合前向性、成像距离、视差与多视角观测数,后者评估可见性、图像对重叠度与图连通性。
◆采用迭代反馈机制,从当前代理重建中持续发现弱观测区域并更新视点集合,形成闭环优化流程。

三组合成场景实验验证了该方法在重建精度和完整性上均优于现有无人机路径规划方法。</td></tr>
<tr><td>2026-08-06</td><td>A Unified Framework for Trajectory Prediction with Explicit Planning and Reaction Decomposition<br><a href='http://arxiv.org/pdf/2608.05673'>论文</a> | <a href='https://github.com/11isnotavailable/INTraJ'>代码</a></td><td>本文针对轨迹预测中社会影响力功能角色区分不足的问题，提出了一个统一框架INTraJ。该方法将社会交互分解为&quot;规划&quot;和&quot;反应&quot;两个阶段：首先利用未来社会信息构建参考轨迹，再通过完整上下文预测与参考轨迹的残差恢复局部调整。

◆ 核心创新在于显式分解社会影响为规划与反应两个阶段，模拟人类先规划后调整的认知过程。

◆ 框架同时支持多目标和单目标两种预测范式，具有良好的通用性。

◆ 引入参考轨迹与残差建模机制，使长时域预测的稳定性和一致性显著提升。

◆ 在Argoverse 2、ETH/UCY、SDD等四个标准基准上取得多个场景下的最优性能，尤其在FDE和长时域指标上表现突出。</td></tr>
<tr><td>2026-08-06</td><td>PathCover: A Fast Convex Decomposition along a Path via Randomized Iterative Space Partitioning (RISP) on Point Clouds<br><a href='http://arxiv.org/pdf/2608.05586'>论文</a></td><td>该论文提出PathCover框架,旨在解决自主机器人导航中实时生成无障碍走廊的效率瓶颈问题。

◆ 提出随机迭代空间分割(RISP)算法,能够在期望线性时间内直接从原始点云数据构建凸多面体,显著降低计算复杂度。

◆ 通过数学证明保证算法在有限步内终止,并沿任意无障碍参考路径持续推进,保证走廊生成的可靠性和连续性。

◆ 生成重叠的无障碍凸多面体序列,可安全约束下游模型预测控制(MPC)和轨迹优化任务。

◆ 在合成和真实LiDAR数据集上的基准测试显示,相比现有最先进方法实现了一个数量级的速度提升,同时保持相当的走廊体积。

◆ 通过高保真四旋翼仿真和在四足机器人上的物理部署验证了完整流水线,使用实时LiDAR感知在受限环境中导航,证明方法的实用性和实时性。</td></tr>
<tr><td>2026-08-06</td><td>TRACE: Ergodic Trajectory Optimization for Active Scene Reconstruction<br><a href='http://arxiv.org/pdf/2608.02304'>论文</a> | <a href='https://github.com/spikelab-jhu/trace-active-reconstruction'>代码</a></td><td>本文针对主动场景重建中贪心下一最佳视角方法因短视规划导致效率低下的问题,提出基于遍历性覆盖的全局轨迹优化框架TRACE。

◆ 将主动重建重新建模为遍历性覆盖问题,使传感器轨迹的时间平均空间统计量匹配由地图导出的目标信息分布,实现全局结构感知的路径规划。

◆ 在线从地图的不确定性与可见性中推导目标信息分布,让规划器动态响应建图状态变化。

◆ 提出核遍历性水平规划器,结合梯度流与足迹消减机制,生成长视域且信息高效的轨迹。

◆ 打通建图与轨迹优化的闭环,避免感知资源在视点间转移过程中的浪费。

在Replica数据集上,TRACE相比NBV基线在PSNR上提升1.5 dB,验证了所提方法的有效性。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-10</td><td>CableDex: Cable Length Estimation on Industrial Reels Using a Handheld Device<br><a href='http://arxiv.org/pdf/2608.09392'>论文</a></td><td>CableDex是一种基于计算机视觉的电缆长度自动测量系统，仅需通过手机拍摄单张照片即可估算工业卷盘上的电缆长度，取代了传统耗时且不准确的手工测量方式。该系统整合了相机标定、实例分割、姿态估计和体积计算四个核心模块，能够适应五种不同卷盘类型和多种电缆规格。团队基于1000张人工标注图像训练了实例分割模型，在测试中达到99.5%的mAP50，且推理时间仅5.66毫秒。在75个卷盘上的工业数据验证后，系统实现了4.90%的平均绝对百分比误差，满足行业通常接受的10%误差容限要求。

◆提出端到端的移动视觉测量流程，将相机标定、实例分割、姿态估计与体积计算无缝集成，实现从图像采集到长度估算的全自动化处理。
◆构建高精度实时实例分割模型，在自建数据集上达到99.5%的mAP50，单图推理仅需5.66毫秒，兼顾精度与运行效率。
◆实现跨卷盘类型和电缆规格的强泛化能力，在五种卷盘类型上测量误差仅4.90%，优于行业10%的容差标准。</td></tr>
<tr><td>2026-08-01</td><td>Self Supervised Learning from Automatically Generated Demonstrations for Visual Robotic Manipulation<br><a href='http://arxiv.org/pdf/2608.07553'>论文</a></td><td>本文提出了一种面向视觉机器人操作的自监督学习方法，核心思想是让机器人围绕目标位姿自动生成演示数据，并直接从腕部RGB图像中学习相对位姿修正，从而摆脱传统方法对人工示教和标定的依赖。

在数据采集层面，系统利用ROS 2与Isaac Sim自动生成带有位姿标签的图像-位姿对，无需显式的相机-机器人外参标定，并分别为平面精修和三维粗接近阶段构建了独立数据集。

控制策略上采用由粗到精的两阶段框架，先利用含高度变化训练的三维模型完成物体接近，再使用平面数据训练的模型进行最终对齐。

在仿真实验中，平面精修阶段将最终位姿分散度从9.69毫米降低至5.38毫米；真实UR5e机器人上对三个物体的端到端抓取实验在两种无旋转工况下分别取得66.6%和63.3%的成功率。

主要创新点包括：

◆ 提出机器人自主生成演示数据的自监督流程，无需人工遥操作或示教即可获得标签化训练样本。

◆ 利用系统级同步机制规避显式手眼外参标定，降低了实际部署的工程门槛。

◆ 设计粗到精双网络架构，分别针对三维接近和平面精修任务训练专用模型。

◆ 仅依靠单帧腕部RGB图像直接回归相对平移与旋转，简化感知链路。</td></tr>
<tr><td>2026-08-06</td><td>Toward surface-based registration of a virtual preoperative cutting guide onto the mandible for reconstruction surgery<br><a href='http://arxiv.org/pdf/2608.06599'>论文</a></td><td>本文针对下颌骨节段性切除重建手术中3D打印切割导板存在的成本高、不可调整、易污染等问题，提出了一种基于表面配准的无标记增强现实替代方案。该方法利用HoloLens 2飞行时间相机采集术中部分点云，以牙齿作为最显著可见表面特征，仅需用户进行粗略头部对齐即可裁剪感兴趣区域。配准流程采用牙齿加权的全局刚性对齐与非对称点到平面ICP精配准两阶段策略，实现虚拟导板到下颌骨的精确位姿映射，并通过实时跟踪与插值跟随目标运动。在幻影实验中，三种暴露条件下中位TRE分别为4.05、6.10和7.10毫米，运动到显示延迟中位数为0.805秒。

◆ 提出面向经口入路下颌重建的表面配准框架，以牙齿为关键区分性特征替代物理打印导板，无需安装基准标记或手工选点
◆ 设计牙齿加权全局配准结合非对称点对平面ICP的两阶段方法，提升在部分深度点云条件下的配准鲁棒性与精度
◆ 建立盲法幻影评估协议，量化多种暴露场景下的目标配准误差与系统延迟，为AR替代打印导板提供可测试路径...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-05</td><td>Beyond Reprojection Error: Camera Calibration with 3D Targets<br><a href='http://arxiv.org/pdf/2608.05066'>论文</a></td><td>本文提出了一种基于场景光线预测的相机标定框架,突破了传统二维平面标定的局限,适用于三维重建任务。作者推导了重建误差和交点误差两种基于光线的新型度量,结合自助法统计评估不同标定对象和标定流程,用于内外参标定。

主要创新点如下:

◆ 提出基于场景光线预测的标定框架,可灵活集成先进相机模型,并采用广义畸变模型更准确地刻画真实相机的物理效应。

◆ 引入重建误差和交点误差作为新的标定评价指标,证明传统重投影误差可能是三维精度的误导性指标,光线度量提供更全面的评估。

◆ 设计了一种正二十面体标定靶配合环形特征检测器,合成数据上平均交点误差降低约40%,且自助法试验中标定结果更稳定。

实验表明广义畸变模型在标定精度上优于传统模型,但实际数据应用需依赖极高的制造精度。</td></tr>
<tr><td>2026-08-05</td><td>Differential 6-DOF Pose Estimation with Provable First-Order Immunity to Camera Calibration Errors<br><a href='http://arxiv.org/pdf/2608.04673'>论文</a> | <a href='https://github.com/zyoungszu/pami2026'>代码</a></td><td>本文提出一种差分6自由度位姿估计方法，直接由帧间图像位移与已知3D控制点恢复平台运动，避免了传统3D-2D方法对外参标定误差的敏感性。主要创新点包括：
◆通过差分透视投影方程与深度不变性近似，在SE(3)流形上建模运动，无需逐帧独立求解绝对位姿，并支持单目与多相机系统；
◆理论上证明平移外参误差可精确抵消，旋转外参误差仅引入受标定误差、运动幅度和观测几何共同约束的有界扰动，实现一阶标定误差免疫；
◆推导通用可观测性条件、Cramér-Rao下界及无偏一致性估计器，并明确近似有效性的适用边界。
大量合成与真实实验表明，该方法在精度、鲁棒性和效率上均显著优于代表性PnP与广义PnP方法，单目求解器仅需5个控制点即可在0.5像素噪声下达到10.09角秒旋转RMSE和3.70毫米平移RMSE，双目求解器运行时间仅0.27毫秒。</td></tr>
<tr><td>2026-07-27</td><td>Lindblad-Inspired Multi-Timescale Reservoir Computing with Separable Rotation and Dissipation<br><a href='http://arxiv.org/pdf/2608.04028'>论文</a></td><td>本文提出了一种受Lindblad方程启发的多时间尺度回声状态网络，通过将开量子系统动力学原理与结构化状态空间建模相结合，解决了传统储层中信号混合、记忆保持与稳定性耦合在单一随机矩阵中的问题。核心思想是将循环算子分解为精确离散化的阻尼旋转模态，使旋转（控制相位混合）与衰减（控制记忆丧失）成为相互独立的设计变量。

◆ 基于精确离散化阻尼旋转模态构建循环算子，将旋转与衰减解耦为两个独立可调的设计变量，分别控制相位混合与记忆丧失。

◆ 通过正交模混合保持矩阵法向性，使衰减谱直接决定回声状态稳定边界，无需后验谱半径缩放即可获得全局稳定性保证。

◆ 引入受Lindblad开放系统动力学启发的结构化储层设计框架，使混合、记忆、稳定性成为显式且可独立调控的物理量。

实验表明，该方法在十组对齐种子下，在有界NARMA-20上取得最佳固定储层性能，在Lorenz-63上获得最低平均误差，并在多种基准上保持竞争力；消融研究证实旋转增强状态多样性，耗散提供受控遗忘并改善预测条件。</td></tr>
<tr><td>2026-08-03</td><td>CalibBEV: LiDAR-Camera Calibration via BEV Alignment<br><a href='http://arxiv.org/pdf/2608.02309'>论文</a></td><td>这篇论文提出CalibBEV，一种基于鸟瞰图(BEV)对齐的激光雷达与相机外参标定新方法，核心思想是将两种异构传感器数据统一到共享的BEV三维空间表示中，从而实现精确且鲁棒的跨模态标定。

◆ 创新点一：构建统一BEV空间表征，利用模态专用网络分别从图像和点云中提取BEV特征，为跨模态几何对齐提供共同表达基础。
◆ 创新点二：提出两阶段对齐策略，先隐式回归粗标定矩阵，再显式将一种模态的BEV特征对齐到另一种，逐步精化标定结果。
◆ 创新点三：借鉴CLIP对比学习思想设计损失函数，约束两模态BEV特征在统一语义空间中对齐，有效缓解跨模态语义鸿沟。

在KITTI和nuScenes基准上的实验表明，该方法将相对旋转误差分别降低51%和68%，相对平移误差降低80%和91%，全面超越现有基于点-像素匹配的方法，达到当前最优标定精度。</td></tr>
<tr><td>2026-08-03</td><td>Multi-View Unified Camera Fields: Geometry-Shaped Action-Facing Representations for RGB-Only Multi-Camera VLA Policies<br><a href='http://arxiv.org/pdf/2608.01826'>论文</a></td><td>本文提出Multi-View Unified Camera Fields (MVUCF)，一种仅在训练阶段生效的多视角视觉-语言-动作模型框架，旨在解决现有方法将多相机token简单拼接导致动作表征缺乏度量深度且跨视角不一致的问题。其核心思想是在不同相机之间构建共享的、面向动作的潜在场，将几何信息直接注入到动作模块所使用的隐藏状态中。

◆构建跨视角共享的动作导向潜在场，形成几何一致的多视角统一表征。
◆设计坐标查询的深度目标，使度量深度可从隐藏状态中恢复。
◆提出预处理感知的对应目标，对齐不同相机下观测同一物理点的token。
◆训练阶段注入几何，部署时移除深度、校准及辅助头，原始RGB图零额外推理开销。

在GR00T-N1.6设置下，MVUCF在LIBERO上达到98.9%，LIBERO-Plus提升22.4分，并在覆盖触碰、移动放置与接触交互三类动作的六个RoboTwin任务上平均提升23.3分，真实人形机器人实验进一步验证了其RGB-only部署的实用价值。</td></tr>
<tr><td>2026-07-29</td><td>VidMap: Exploiting Temporal Structure for Video-Based Structure-from-Motion<br><a href='http://arxiv.org/pdf/2607.27194'>论文</a> | <a href='https://github.com/cvg/vidmap'>代码</a></td><td>本文针对无约束视频的相机标定和度量位姿恢复问题,分析了现有SLAM和SfM方法的局限性:SLAM对初始化敏感且通常需要已知标定,而传统SfM忽略图像时序信息,在视觉对称性和极端运动下鲁棒性差。论文提出VidMap系统,融合SLAM的强时序约束与离线SfM的全局优化灵活性,首次实现对任意长视频进行度量重建而不依赖标定参数。

◆ 将时序顺序作为一等公民用于可靠的回环闭合,克服视觉对称性和极端运动导致的误匹配

◆ 引入宽基线稠密图像匹配技术,提升帧间对应关系估计的精度和鲁棒性

◆ 在全局优化中融合单目深度先验约束,实现无标定视频的度量尺度重建

◆ 综合采用全局捆绑调整策略,兼顾SLAM的因果稳定性和SfM的全局最优性

在多个具有极端运动和视觉对称性的数据集上的实验表明,VidMap在鲁棒性和精度上均显著优于当前最先进的SLAM和SfM方法,无论相机标定是否已知。</td></tr>
<tr><td>2026-07-24</td><td>Metric Surface Reconstruction of Neurosurgical Scenes from Monocular Operating Microscope Images and Microscope Pose<br><a href='http://arxiv.org/pdf/2607.22773'>论文</a></td><td>本文提出了一种基于单目手术显微镜图像与导航系统提供的显微镜位姿数据来恢复神经外科术野度量级三维几何结构的方法。研究团队在体模实验中，利用ZEISS Pentero 800显微镜与Brainlab颅脑导航系统采集同步图像与位姿信息，在内外参标定后采用预训练的Depth Anything 3基础模型进行深度估计，再经点云融合与泊松曲面重建获得三维表面，并与结构光扫描和CT结果进行对比验证。实验结果表明，深度术野体模重建精度在1.95–2.33 mm之间，直接暴露表面体模精度可达1.02–1.52 mm，达到毫米级重建水平。

核心创新点如下：

◆ 提出将常规单目显微镜视频与导航系统位姿数据相结合的无需专用硬件改造的度量级三维重建流程。

◆ 首次将基础深度估计模型（Depth Anything 3）零样本应用于神经外科术野重建，验证了无需任务特定微调的可行性。

◆ 将该方法用于术野暴露的客观量化评估、图像融合及工作空间表征，为未来手术器械设计与术中导航增强提供了技术基础。</td></tr>
<tr><td>2026-07-22</td><td>Calibration-Free 3D Multi-Camera People Tracking for Indoor Environment<br><a href='http://arxiv.org/pdf/2607.22731'>论文</a></td><td>本文针对多相机行人跟踪中传统手动标定效率低下的问题，提出了一种无需标定的统一3D多相机行人跟踪框架。该系统融合了YOLOX无锚框检测、BoT-SORT鲁棒跟踪、OsNet外观特征、HRNet姿态估计以及VGGT视觉几何变换器等多类深度基础模型，实现从原始视频直接推断三维几何结构。

◆ 提出基于VGGT的无标定三维重建方法，直接从视觉数据恢复场景几何，避免对内外参标定矩阵的依赖。

◆ 设计姿态引导的三维提升策略，将头部关键点投影至重建流形上，取代传统地面单应性投影方案。

◆ 引入基于外观-几何联合代价与速度门控的分层聚类算法，实现跨相机的全局身份关联。

◆ 在AI City Challenge 2024数据集上取得53.13%的HOTA分数，为纯视觉三维跟踪建立了强基线。

该工作为大规规模无约束视频档案的自动化三维行人跟踪提供了新的解决思路。</td></tr>
<tr><td>2026-07-23</td><td>TransBiolab: A Real-World Multi-View Dataset of Cluttered Transparent Biomedical Objects<br><a href='http://arxiv.org/pdf/2607.21071'>论文</a> | <a href='https://dualtransparency.github.io/TransBiolab/'>代码</a></td><td>TransBiolab针对自主生物医学实验室中透明塑料器皿的视觉感知需求,发布了一个真实场景的RGB-D数据集,填补了现有透明物体数据集中多目标杂乱堆叠、遮挡与多视角标定联合评估的空白。该数据集包含来自98个场景的161,315帧图像和约103万条实例标注,涵盖15类实验室物品,提供6D位姿、完整与可见掩码、深度图及逐帧相机标定信息。

◆ 首次构建真实世界杂乱堆叠透明生物医学物体的多视角标定数据集,综合了多目标、遮挡与多视角采集的真实实验室操作场景特征。

◆ 沿物体类别、帧内物体数量和相机视角三个难度维度组织数据,便于系统性评估模型在不同操作复杂度下的表现。

◆ 提供大规模细粒度标注(6D位姿、掩码、深度、标定),支撑分割、深度估计与补全、6D位姿估计及多视图推理等多任务基准测试。

◆ 配套发布系统级机器人操作评估流程,使数据集可直接服务于透明器皿抓取与操控等实际应用验证。</td></tr>
<tr><td>2026-07-20</td><td>Two-Stage Extrinsic Calibration of a Static Line-Scanning Lidar with a Rotary Platform<br><a href='http://arxiv.org/pdf/2607.18578'>论文</a></td><td>本论文针对静态线扫描激光雷达与旋转平台组合系统中的外部标定难题展开研究。核心贡献是提出两阶段标定方法，分别在静态和动态条件下自动估计旋转平台轴线相对于激光雷达坐标系的变换关系。该方法解决了工业精密扫描与检测场景中三维点云重建的关键问题，因为任何轴线标定误差都会直接导致物体几何失真。研究通过自制旋转平台与FMCW激光雷达采集的真实数据集进行了系统验证，并深入分析了算法在不同初始条件下的收敛特性。论文特别强调在静态配置下识别旋转轴的精确变换，这是构建高质量三维点云的前提。

◆ 提出两阶段(静态与动态)外部标定框架，自动估计旋转平台轴线在激光雷达坐标系下的变换关系，无需人工精确测量初始位姿。
◆ 在真实FMCW激光雷达与自制旋转平台上进行实验验证，系统评估了算法在不同初始条件下的收敛性与鲁棒性。
◆ 解决了线扫描激光雷达仅能在固定平面内获取距离与方位信息、必须依赖相对运动实现三维感知时的轴线精确标定难题。</td></tr>
<tr><td>2026-07-13</td><td>Why Low-Light Cameras Go Color Blind: Removing Color Bias in Raw Denoising<br><a href='http://arxiv.org/pdf/2607.11090'>论文</a></td><td>本文针对低光条件下的原始图像去噪任务,提出了一种无需相机校准的通用去噪框架。研究发现黑电平误差引起的颜色偏差是导致去噪性能下降和严重色偏的主要原因,这一发现为盲去噪问题提供了新的视角。◆ 提出了一个偏置估计网络,将黑电平误差作为全局特征从噪声输入中预测出来,从而实现相机无关、无需校准的低光原始图像去噪。◆ 在ELD、SID和LRID等多个数据集上取得优于现有盲去噪方法的性能,尤其在颜色校正方面表现突出,在某些情况下甚至可与需要更强监督的方法相媲美。◆ 揭示了广泛使用的SIDD数据集的ground-truth存在显著颜色偏差,会导致训练模型产生不真实的颜色还原。◆ 提出了一种新的ground-truth提取框架,以解决SIDD数据集中的颜色偏差问题,并在修正后的数据集上对现有方法提供了新的基准评测。</td></tr>
<tr><td>2026-07-15</td><td>Unsupervised Detection of Entry and Exit Regions from Vehicle Trajectories for Camera-Agnostic Turning Movement Counts<br><a href='http://arxiv.org/pdf/2607.10949'>论文</a></td><td>本文针对交叉口转向流量计数中人工标注成本高的问题，提出了一种基于车辆轨迹的无监督出入口区域检测流水线。该方法通过聚类轨迹的起点和终点位置，生成持久的空间区域多边形，未来轨迹可通过点-多边形包含关系以线性复杂度进行分类，避免了传统轨迹聚类方法每次重新执行的问题。

◆提出无需人工标注、相机标定或先验几何知识的无监督流水线，仅利用目标检测与多目标跟踪得到的原始轨迹即可识别出入口区域。
◆将区域识别转化为对轨迹起终点的位置聚类，生成持久的区域多边形，显著降低分类计算成本并提升跨视角稳定性。
◆设计包含六个可配置步骤的完整流水线框架，并通过对19152次执行的系统统计分析，识别出三个始终显著的关键参数，给出经验性推荐配置。
◆在印度班加罗尔25个相机（含16个未见过的位置）和UA-DETRAC数据集上实现约3%的中位分类误差，GEH指标符合工程标准。
◆验证了至少60分钟的校准片段结合高峰时段交通选取可进一步提升区域估计质量，证实了方法的实用性。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-undistortion'>Sensor Undistortion</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-10</td><td>Bootstrapping Vision-Language Model for Hysteroscopic Surgical Scene Segmentation<br><a href='http://arxiv.org/pdf/2608.09302'>论文</a> | <a href='https://github.com/viscom-tongji/VLM-hyster'>代码</a></td><td>该论文针对宫腔镜手术场景分割中病灶形态高度相似以及镜面反射、运动模糊、液体遮挡等伪影干扰的难题,提出了首个基于视觉-语言模型(VLM)的宫腔镜手术场景分割方法VLM-hyster,实现了对15类典型结构的像素级定位。

◆ 首次将视觉-语言模型引入宫腔镜手术场景分割任务,利用预训练图像编码器结合Transformer解码器完成密集预测,提升了复杂场景下的视觉特征表征能力。

◆ 设计了类别特定的文本提示,并引入掩码蒸馏分支以过滤与文本相关性低的视觉特征,使模型更聚焦于类别相关区域,有效缓解了病灶间高相似性带来的判别困难。

◆ 构建了一个包含4020张高分辨率图像的多中心宫腔镜手术场景数据集,提供了精细的掩码标注,填补了该领域数据资源的空白。

◆ 大量实验表明VLM-hyster显著优于当前最先进的AI模型,并经妇科医生评估以及多中心、前瞻性验证,证明了其在真实临床应用中的鲁棒性和泛化能力。</td></tr>
<tr><td>2026-08-09</td><td>RMR-Net: Degradation-Evidence-Guided Road-Image Restoration for Defect Detection<br><a href='http://arxiv.org/pdf/2608.08957'>论文</a></td><td>本文提出RMR-Net,一种用于道路缺陷检测的任务感知图像复原前端,旨在解决车载相机因运动模糊、失焦、低光照和噪声导致细小裂缝与坑洞边界丢失的问题。RMR-Net从图像中估计退化证据并可与已知退化参数融合,引导轻量级复原块通过有界残差路径恢复路面高频细节。实验在IVCNZ和PCM数据集上使用合成退化参数(非实测车载遥测),采用冻结的YOLO11s检测器作为统一评估标准。在八种未见退化条件下RMR-Net在其中七种取得最高mAP50,例如IVCNZ运动模糊0.140-0.427,PCM失焦0.060-0.233。消融实验表明有界细节路径贡献最大,退化条件与检测器感知稳定项提供互补引导。

创新点:
◆ 退化证据估计驱动的轻量级任务感知复原前端设计
◆ 有界残差路径专用于恢复路面高频细节
◆ 退化条件与检测器感知稳定项的协同引导机制
◆ 基于冻结检测器一致的统一评估框架...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-09</td><td>ERF-GS: Reconstructing Fast Motion from Disjoint Event-RGB Viewpoints<br><a href='http://arxiv.org/pdf/2608.08531'>论文</a> | <a href='https://github.com/andrewbxy/ERF-GS'>代码</a></td><td>本文提出ERF-GS框架，将事件相机信息与高斯溅射相结合，专门解决从分离的RGB和事件视角重建快速运动三维场景的难题。现有基于帧视频的方法在体育、动物等高速运动场景中容易产生模糊和细节丢失，而事件相机的高时间分辨率提供了新的解决途径。该工作通过将事件信息集成到高斯溅射的优化与致密化阶段，并采用现实仿真设置训练事件学习模块，使其与RGB输入解耦。
◆ 将事件信息同时融入高斯溅射的优化与致密化两个关键阶段，显著提升快速运动重建的精度与完整性
◆ 实现了与RGB输入解耦的事件学习范式，可应用于低帧率、运动模糊的复杂自然视频及非对齐视角
◆ 在Neu3D和Nvidia多个数据集变体上，性能优于4DGS基线及同期方法E-D3DGS...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-06</td><td>ASTRA: Asynchronous Spatio-Temporal Reconstruction via Trajectory Alignment<br><a href='http://arxiv.org/pdf/2608.02006'>论文</a></td><td>该论文针对动态三维场景重建中多相机时间异步问题展开研究,指出传统基于光度监督的同步方法因纹理缺失和形变耦合两大瓶颈而失效。

为此,作者提出ASTRA框架,核心思想是利用二维运动轨迹作为显式、纹理无关的监督信号来估计时间偏移。

◆ 创新点一:首次引入2D运动轨迹作为纹理无关的显式时间监督,从根本上解决低纹理区域对齐信号消失的问题。

◆ 创新点二:通过将重建3D点的投影运动与观测2D轨迹对齐,实现时间偏移与动态3D表示的联合优化,显式解耦时间误差与几何形变。

◆ 创新点三:设计动态掩码与确信度掩码机制,有效抑制运动模糊区域和不可靠轨迹的负面影响。

◆ 创新点四:在多种动态高斯溅射基模型上验证,在最高25帧的严重偏移下仍保持鲁棒,PSNR提升约1.4dB,时间偏移MAE降低54.0%,同步成功率提升近4倍。</td></tr>
<tr><td>2026-08-03</td><td>When Extreme Darkness Meets Motion Blur: MeanFlow for Unified RAW Restoration<br><a href='http://arxiv.org/pdf/2608.01720'>论文</a></td><td>针对极低光照RAW图像增强中运动模糊与噪声耦合退化的难题，本文提出了一个统一的RAW恢复框架。◆ 构建了首个面向极低光照的SIDED数据集，对原始传感器RAW数据施加可控的运动退化，同时保留真实噪声特性。◆ 设计了统一RAW tokenizer，通过显式的域条件表征校准来对齐极低光照与正常曝光RAW域。◆ 首次将MeanFlow引入极低光照RAW增强任务，仅需单次函数评估即可完成图像恢复。◆ 提出物理引导的精细化模型，在不增加推理开销的前提下强化光照-反射一致性、像素保真度与色彩保持。大量实验表明，该方法在极低光照RAW增强上达到最先进水平，并能鲁棒地处理运动与噪声耦合退化。</td></tr>
<tr><td>2026-08-01</td><td>E2Pano: Learning Event-to-Panorama Image Reconstruction<br><a href='http://arxiv.org/pdf/2608.00694'>论文</a></td><td>E2Pano提出了一种基于几何引导的端到端事件相机到全景图像重建框架,旨在解决现有优化方法计算开销大、传统学习方法缺乏全景几何感知的问题。整体而言,论文通过在管线的几何映射环节保留真实球面坐标,并设计轻量级增强模块与球面Transformer来实现从事件流到高质量全景图像的高效重建,训练完全基于合成数据,但在真实采集数据上展现出良好的迁移能力。

核心创新点如下:

◆ 提出几何引导的事件到全景重建管线,贯穿整个流程保持真实的球面坐标,避免透视投影假设对全景几何的破坏。

◆ 设计轻量级增强模块结合频域监督,有效弥合事件与图像之间的领域差异,提升重建细节质量。

◆ 提出带3D位置嵌入的球面Transformer,实现面向全景结构的光度重建,降低了相对优化方法的计算成本。

◆ 构建PanoScan数据集,包含4370个合成全景场景与30个真实旋转扫描场景,并配套事件流数据,填补了该方向的数据空白。</td></tr>
<tr><td>2026-08-01</td><td>Optical Flow from Photons<br><a href='http://arxiv.org/pdf/2608.00499'>论文</a></td><td>本文针对高速低光场景下传统相机易产生运动模糊和欠曝光的问题，提出首个直接从单光子雪崩二极管(SPAD)光子流估计密集光流的方法QuantaFlow。核心思想是将SPAD表示构建嵌入到迭代光流精化过程中，突破传统固定输入表示的局限，在每次迭代中利用当前光流对源和目标子流内的切片进行粗对齐，再通过光子通量变换构建包含强度与结构线索的多尺度表示，并由自适应多尺度融合在每个像素上平衡光子噪声与残余运动模糊，最终驱动特征扭曲的光流更新。实验表明该方法在合成数据集和真实SPAD数据上均有效且具备良好泛化能力。

创新点如下：

◆ 首个直接从SPAD二值光子流估计密集光流的方法，规避了传统相机在高速低光场景下的运动模糊与欠曝光问题。

◆ 提出将SPAD表示构建嵌入到迭代光流精化框架中，使表示构造与流估计相互引导，缓解了运动感知聚合对预知光流的依赖。

◆ 设计光子通量变换与自适应多尺度融合机制，在像素级平衡光子噪声与残余运动模糊，提升表示质量。

◆ 构建了首个用于SPAD光流训练与评估的合成数据集，填补了该领域数据空白。</td></tr>
<tr><td>2026-07-30</td><td>ENCORE: Event-Assisted Complementary Motion Refinement for Learned Video Compression<br><a href='http://arxiv.org/pdf/2607.28020'>论文</a></td><td>ENCORE提出了一种事件相机辅助的学习视频压缩框架,旨在解决传统学习方法仅依赖RGB帧推断运动时在快速运动、模糊、低光照等场景下鲁棒性不足的问题。

◆ 提出互补运动表示(CMR),将对齐后的RGB-事件特征分解为共享的公共运动表示和模态特定的运动表示,充分利用两种模态的互补信息。

◆ 设计空间能量与冗余感知的校准模块(SERIC),用于识别事件相对于RGB的新颖且活跃的响应,抑制弱证据或冗余信息,并预测候选光流修正量。

◆ 引入能量感知路由机制(EAR),自适应决定光流修正的应用位置和强度,实现精细化的运动细化。

◆ 在多个数据集(BS-ERGB、HQ-EVFI、CED)上均取得一致性能提升,在BS-ERGB上最高实现20.80%的PSNR-RGB和22.14%的MS-SSIM-RGB BD-rate节省。

◆ 事件仅作为运动建模的辅助模态,RGB仍然是唯一的编码与重建目标,保证了框架的实用性和兼容性。</td></tr>
<tr><td>2026-07-29</td><td>Semantic-Aware Temporal Adaptation for UAV Anti-UAV Tracking<br><a href='http://arxiv.org/pdf/2607.26511'>论文</a> | <a href='https://github.com/XiaozhenQiao/SATATrack'>代码</a></td><td>该论文针对UAV反无人机跟踪任务,提出了一种语义感知的时序自适应框架SATATrack。由于观察者无人机和目标无人机同时运动,场景存在快速视角变化、运动模糊和视觉相似干扰物,使固定视觉表征难以可靠匹配目标。

◆ 核心创新一:语义感知上下文传播(SACP),利用稳定的目标语言描述作为语义锚点,在骨干网络各阶段引导跨帧时序上下文传播,有效保持快速外观变化下的目标身份一致性。

◆ 核心创新二:训练阶段引入对比正则化器,抑制模型对语义相似背景区域的响应,提升特征判别性。

◆ 核心创新三:推理阶段提出时序感知分布对齐(TADA),无需更新模型参数,在线融合近期帧特征估计与训练时统计量,缓解视频特定的测试时域偏移。

该方法在UAV-Anti-UAV基准上达到最优性能,同时在反无人机和无人机目标跟踪任务上也具有竞争力,验证了语义与时序自适应协同设计的有效性。</td></tr>
<tr><td>2026-07-28</td><td>Eddeep: a deep-learning framework for fast eddy-current distortion correction in diffusion MRI<br><a href='http://arxiv.org/pdf/2607.26292'>论文</a> | <a href='https://github.com/CIG-UCL/eddeep'>代码</a></td><td>本文提出Eddeep，一种用于扩散磁共振成像(dMRI)中涡流畸变校正的深度学习框架，旨在解决传统迭代方法(如FSL Eddy)计算成本高的问题。Eddeep将校正任务分解为两阶段：首先采用监督式图像翻译网络对扩散加权图像和b=0图像进行外观标准化，消除对比度差异以利于可靠配准；其次采用无监督配准网络在物理约束的二次畸变模型下，同时估计涡流畸变参数和体素间头动参数，实现单次前向传播完成校正。◆两阶段分解策略：先通过监督式图像翻译标准化图像外观，再通过无监督配准联合估计畸变与运动参数，简化了传统迭代校正流程。◆物理约束的二次畸变模型：将涡流畸变与头动参数在统一框架下联合估计，保证校正结果符合物理规律。◆单次前向传播推理：摆脱对迭代优化的依赖，显著降低计算时间，适合大规模研究和临床部署。方法在UK Biobank数据上训练，并在域内和域外数据集(Memodyn)上验证，在体素间抖动、扩散峰度残差、信号不规则性和互信息等多项指标上达到与FSL Eddy相当的校正质量，同时大幅提升推理速度。</td></tr>
<tr><td>2026-07-26</td><td>Neuromorphic Object Detection: An In-Depth Study and Future Directions<br><a href='http://arxiv.org/pdf/2607.23576'>论文</a></td><td>本文针对传统帧相机在高速运动模糊和低光环境下目标检测能力不足的问题,系统综述了基于神经形态相机的事件驱动目标检测方法。文章首先对问题进行形式化描述,梳理了可用数据集和评估指标,然后从事件表示、时间建模、多模态融合、异步处理、低延迟处理和能效计算六个维度深入分析了现有方法,并对代表性模型进行了广泛基准测试和对比分析,最后指出了该领域尚未解决的关键问题与未来研究方向。该工作填补了神经形态目标检测领域缺乏统一基准和深度理解的空白,为后续研究提供了重要参考。

◆ 提出首个针对神经形态目标检测的全面综述与统一基准框架,系统整合了事件表示、时间建模、多模态融合、异步与低延迟处理以及能效计算等多个关键技术维度。

◆ 对大量代表性神经形态目标检测模型进行标准化基准评测,提供详尽的对比分析,弥补了该领域缺乏公平统一评估体系的不足。

◆ 重新审视并梳理了神经形态数据集与评价指标,为后续研究的可比性和可复现性奠定基础。

◆ 明确指出当前神经形态目标检测领域尚未解决的关键问题,并提出具有前瞻性的未来研究方向,为研究者提供清晰的指引。</td></tr>
<tr><td>2026-07-22</td><td>RealVDeblur: One-Step Diffusion for Generalizable Real-World Video Deblurring<br><a href='http://arxiv.org/pdf/2607.20628'>论文</a> | <a href='https://rbjin.github.io/RealVDeblur'>代码</a></td><td>本文针对真实场景视频去模糊中运动模式多样、真实训练数据稀缺等难题，提出了RealVDeblur生成式框架。其核心贡献包括：构建了基于3D高斯泼溅资产和高帧率视频的大规模物理可信模糊合成管线，能够生成覆盖相机抖动与物体运动模糊的真实训练数据；利用视频扩散先验进行复原，并通过禁用VAE时间压缩和逐帧编码策略来适应帧间差异化的模糊分布；进一步将多步扩散采样蒸馏为高效的单步生成器以提升实用性；提出免训练的时间窗口掩码机制，使模型能在恒定显存下稳定处理超出训练时长的长视频。实验表明，该方法在多个真实基准上取得了优异的感知质量、语义保真度与时间一致性，并显著增强了下游3D重建在严重运动模糊下的鲁棒性。</td></tr>
<tr><td>2026-07-20</td><td>Certified Training for Convolutional Perturbations<br><a href='http://arxiv.org/pdf/2607.18195'>论文</a></td><td>本文针对视觉模型在运动模糊等卷积扰动下的脆弱性问题,提出了一种新颖的认证训练方法。该方法通过引入卷积扰动的高效编码机制,使模型在训练阶段即可获得形式化的鲁棒性保证,弥补了数据增强和对抗训练缺乏安全保障的不足。

◆ 提出了一种面向卷积扰动(如运动模糊)的认证训练框架,首次将卷积扰动纳入可证明鲁棒性的训练框架中。

◆ 设计了卷积扰动的高效编码方案,大幅降低了认证训练的计算开销,使训练过程更加实用可行。

◆ 该方法在CIFAR10上针对合理强度的运动模糊实现了超过80%的鲁棒准确率,同时保持了与标准模型相当的常规准确率,显著优于对抗训练方法。

◆ 为关键应用场景中视觉模型的部署提供了可验证的安全保障,有助于识别和缓解潜在的隐藏漏洞。</td></tr>
<tr><td>2026-07-20</td><td>Benchmarking NACTI Species Recognition in Long-Tailed Regimes<br><a href='http://arxiv.org/pdf/2607.18033'>论文</a> | <a href='https://github.com/ZehuaLiuY/Species-Classification'>代码</a></td><td>本文针对北美相机陷阱图像数据集NACTI中存在的严重长尾类别分布不均问题(最大类占据3.7M图像的50%以上),基于PyTorch Wildlife模型系统评估了长尾识别方法在物种识别任务上的表现。

◆ 提出了一套针对NACTI长尾场景的优化配置,通过专用损失函数与长尾敏感正则化策略,在测试集上达到了99.40%的Top-1准确率,刷新了该基准的最优性能。

◆ 首次将长尾物种识别模型在ENA-Detection、Caltech Camera Traps和Missouri Camera Traps三个独立分布外测试集上进行跨域鲁棒性评估,验证了LTR增强模型相比标准交叉熵方法具有显著更强的泛化能力。

◆ 揭示了当前长尾识别方法的局限性,发现其在严重域偏移下对稀有尾部类别仍存在灾难性预测失败,说明表示瓶颈尚未被完全克服。

◆ 公开了所有数据集划分、关键代码及网络权重,为该领域后续研究提供了高可复现性的实验基础。</td></tr>
<tr><td>2026-07-20</td><td>Does Robust VIO Need More Learning? Geometry-Verified Visual Measurements under Distribution Shift<br><a href='http://arxiv.org/pdf/2607.17956'>论文</a></td><td>本文针对分布偏移下视觉惯性里程计(VIO)的鲁棒性问题,提出一种&quot;极简学习&quot;立体VIO框架,主张将学习严格限制在视觉测量生成环节,时序跟踪、几何验证与状态估计仍采用显式建模。

◆ 仅使用SEA-RAFT网络生成稠密立体匹配并预测像素级不确定性,避免对整个管线进行端到端学习,体现&quot;学习越少越鲁棒&quot;的设计哲学。

◆ 在稀疏特征点处采样稠密光流,并通过预测不确定性和对极几何一致性进行双重筛选,过滤不可靠的测量。

◆ 在滑窗立体惯性优化器中加入不确定性加权重投影因子,实现紧耦合的鲁棒状态估计。

◆ 将匹配不确定性通过立体三角化传递至下游,用于各向异性3D高斯建图,提升地图质量。

消融实验表明,单纯依赖学习光流并不充分,真正的性能增益来自学习匹配与几何验证、不确定性加权的协同。该方法在EuRoC、VIODE和4Seasons数据集上,面对运动模糊、动态场景、光照变化及室内到室外的大幅分布偏移,均表现出准确且稳定的估计性能。</td></tr>
<tr><td>2026-07-20</td><td>SLAM in Low-Light Environments: Project Report<br><a href='http://arxiv.org/pdf/2607.17699'>论文</a></td><td>本文是一篇项目报告，系统评估了六种覆盖特征点法、直接法、滤波法和学习法的SLAM系统在低光照环境下的表现。研究基于LaMARia数据集中五个不同难度与光照条件的序列，采用绝对与相对位姿误差以及控制点召回率作为评价指标。实验结果表明，Kimera-VIO是唯一能够完成全部序列跟踪的系统，具有最低的相对位姿误差但因缺少回环闭合导致绝对误差持续累积；DPVO和DPV-SLAM虽不丢失跟踪，但在低光下绝对误差达到约100米；而经典单目系统ORB-SLAM3、DSO以及滤波法OpenVINS在低光照条件下普遍失败或发散。

◆首次在统一基准下系统对比了六种代表性SLAM系统(ORB-SLAM3、DSO、Kimera-VIO、OpenVINS、DPVO、DPV-SLAM)跨越四大范式在低光照场景下的鲁棒性与精度。

◆将低光跟踪性能与系统架构组件显式关联，揭示惯性融合与全局优化是RGB-only SLAM在低光下保持稳定跟踪的两个必要条件。

◆明确指出当前RGB-only方案的局限，并提出未来突破方向：开发针对低光照的学�的前端特征提取模块，或回归多传感器(深度、热成像)融合的解决方案。</td></tr>
<tr><td>2026-07-20</td><td>Luminosity-Adaptive Contrast Enhancement Using CLAHE for Retinal Fundus Images with Quantitative Validation and Comparative Analysis<br><a href='http://arxiv.org/pdf/2607.17691'>论文</a></td><td>该论文针对视网膜眼底图像普遍存在的光照不均、对比度低等问题，提出了一种结合HSV色彩空间亮度校正与CLAHE的两阶段增强流水线，通过仅在V通道上施加对比度受限的自适应直方图均衡来恢复图像结构与细节。实验在公开的DRIVE数据集上以PSNR、SSIM和CNR三项指标进行定量评估，并辅以二值掩膜分割用于高反射血管病变区域的提取与验证。结果显示所提方法在PSNR 29.3 dB、SSIM 0.91和CNR 3.12上均显著优于传统HE和AHE基线方法，且单张图像平均处理时间仅0.14秒，具备临床筛查的实时性潜力。论文还讨论了局限性与未来引入深度学习对比的研究方向。

◆ 创新点一：将HSV色彩空间解耦用于亮度分量校正，再单独对V通道施加CLAHE，避免了RGB直方图操作引起的色偏问题。
◆ 创新点二：在经典CLAHE框架前增加亮度归一化预处理，使对比度增强对非均匀光照具备自适应性。
◆ 创新点三：联合PSNR、SSIM与CNR进行多维度定量验证，并加入二值掩膜对血管高反射区域进行针对性评估，增强结果可解释性。
◆ 创新点四：实验效率达0.14秒/张，兼顾增强质量与临床实时部署需求。</td></tr>
<tr><td>2026-07-18</td><td>Splat-based 3D Scene Reconstruction with Extreme Motion-blur<br><a href='http://arxiv.org/pdf/2607.16926'>论文</a> | <a href='https://github.com/KAIST-VCLAB/gs-extreme-motion-blur'>代码</a></td><td>该论文提出了一种基于高斯溅射的RGB-D三维场景重建方法,专门针对低光环境下因长曝光时间产生的极端运动模糊问题。传统方法如COLMAP因模糊难以准确估计相机位姿,而NeRF和3DGS等方法又依赖精确的轨迹,ICP算法也因深度传感器视野有限和快速运动导致点云重叠不足而失效。论文的核心创新在于将相机位姿估计与图像去模糊统一在高斯溅射框架中,利用3D高斯点和深度信息增强场景表示。

◆ 通过光流和ICP对连续RGB-D帧进行初步对齐,再通过调整高斯点位置优化深度一致性,从而联合精化相机位姿与三维几何。

◆ 在曝光时间内对相机运动进行建模,通过将模糊输入图像与一系列清晰渲染帧进行对比,实现有效的图像去模糊。

◆ 提出了一个包含极端运动模糊的新RGB-D数据集,填补了该领域基准数据的空白。

实验表明该方法在极具挑战性的条件下仍能实现高质量重建,对机器人、自动导航和增强现实等三维建图应用具有重要价值。</td></tr>
<tr><td>2026-07-31</td><td>JADE-GS: Joint Allocation of Deblurring Evidence for Event-Assisted 3D Gaussian Splatting<br><a href='http://arxiv.org/pdf/2607.14990'>论文</a></td><td>JADE-GS针对3D高斯泼溅(3DGS)在运动模糊场景下的重建难题,提出了一种融合事件相机信息的联合去模糊框架。论文观察到事件双积分(EDI)的解析反演与基于学习的帧-事件联合复原这两种先验在不同区域具有互补性,各有所长。本文的核心思想是将二者的结合建模为空间证据分配问题,通过轻量级的空间先验路由器在像素级预测融合权重,生成额外的监督目标。

◆ 提出空间证据分配框架,将EDI解析反演与学习式复原两种互补先验在像素级进行自适应融合
◆ 设计轻量级空间先验路由器,仅利用模糊帧和事件流即可预测逐像素分配权重
◆ 路由器无需清晰参考图像训练,通过场景一致性与曝光测量作为自监督信号
◆ 优化完成后移除路由器,推理阶段保持原生3DGS渲染,无需生成式解码

实验表明,JADE-GS在基准上取得了领先的感知质量,在真实数据集上保真度最优,且训练开销远低于基于扩散的替代方案。</td></tr>
<tr><td>2026-07-23</td><td>DriveFace: A Cross-Spectral Through-Glass Face Dataset for On-the-Move Vehicular Border Control<br><a href='http://arxiv.org/pdf/2607.13515'>论文</a></td><td>本文针对跨境边境检查中车载移动场景下人脸识别的数据缺失问题，提出了DriveFace数据集。该数据集采集自车辆通过检查站时的近红外(NIR)视频，并与基于智能手机的预注册人脸数据进行配对，覆盖了运动模糊、光照变化、遮挡及跨光谱注册等真实挑战。基准实验表明，现有最先进模型在该场景下性能明显受限，验证了数据集的必要性。

◆ 构建了首个面向车载移动边境控制的跨玻璃人脸数据集DriveFace，填补了该场景下公开基准的空白。

◆ 数据集融合NIR车辆通行视频与智能手机预注册图像，模拟真实跨光谱注册场景。

◆ 系统性地涵盖了运动模糊、复杂光照、遮挡及跨玻璃成像等实际挑战。

◆ 通过基线评测揭示了现有SOTA模型在真实车载场景下的性能局限，为后续算法研究指明方向。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5050</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4492</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2439</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1624</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1617</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1472</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1299</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1280</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1032</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>997</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>931</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>804</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>782</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>745</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>731</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>718</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>660</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>647</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>627</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>605</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>601</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>565</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>565</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>523</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>503</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>449</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>440</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>356</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>345</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>267</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>262</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>255</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>239</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>227</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>223</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>212</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>207</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>183</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>147</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>145</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>120</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2863</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1662</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1364</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1096</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1048</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>877</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>701</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>662</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>652</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>623</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>594</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>575</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>574</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>568</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>552</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>518</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>501</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>464</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>453</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>448</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>334</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>313</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>300</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>285</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>279</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>258</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>247</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>223</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>207</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>202</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>184</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>177</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>169</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>168</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>160</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>156</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>138</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>137</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>132</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
<tr><td><a href='https://github.com/ethz-asl/phaser'>phaser</a></td><td>132</td><td>A robust pointcloud registration pipeline based on</td></tr>
<tr><td><a href='https://github.com/ethz-asl/data-driven-dynamics'>data-driven-dynamics</a></td><td>130</td><td>Data Driven Dynamics Modeling for Aerial Vehicles</td></tr>
<tr><td><a href='https://github.com/ethz-asl/ssc_exploration'>ssc_exploration</a></td><td>111</td><td>Incremental 3D Scene Completion for Safe and Effic</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waypoint_navigator'>waypoint_navigator</a></td><td>108</td><td>Stand-alone waypoint navigator</td></tr>
<tr><td><a href='https://github.com/ethz-asl/active_grasp'>active_grasp</a></td><td>108</td><td>Closed-loop next-best view planning for grasp dete</td></tr>
<tr><td><a href='https://github.com/ethz-asl/reinmav-gym'>reinmav-gym</a></td><td>106</td><td>Reinforcement Learning framework for MAVs using th</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waverider'>waverider</a></td><td>106</td><td>RMPs on multi-resolution occupancy maps for effici</td></tr>
<tr><td><a href='https://github.com/ethz-asl/navrep'>navrep</a></td><td>104</td><td>navrep</td></tr>
<tr><td><a href='https://github.com/ethz-asl/eth_supermegabot'>eth_supermegabot</a></td><td>102</td><td>Instructions for ETH center for robotics summer sc</td></tr>
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>102</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/3d_vsg'>3d_vsg</a></td><td>101</td><td>3D可变场景图，用于长期语义场景变化预测。</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.08.11
