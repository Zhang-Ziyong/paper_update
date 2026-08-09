# 计算机视觉领域最新论文 (2026.08.09)

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
<tr><td>2026-08-06</td><td>KILVO: Kinematic-Inertial-LiDAR-Visual Odometry with Robust Multimodal Adaptation for Humanoid Robots<br><a href='http://arxiv.org/pdf/2608.05647'>论文</a></td><td>本文针对人形机器人提出了一种名为KILVO的运动学-惯性-激光-视觉里程计系统，核心是将关节编码器、IMU、激光雷达和相机四类传感器在异步-顺序混合误差状态迭代卡尔曼滤波框架下进行紧耦合融合。该方法在预测阶段使用惯性数据，异步处理腿部运动学信息以提供本体感觉约束，并依次利用激光点云几何配准和视觉光度误差进行外感知更新，从而实现高精度状态估计。

◆提出异步-顺序混合ESIKF框架，将关节编码器、IMU、LiDAR和相机四源信息高效融合
◆设计多模态自适应机制，使系统在传感器退化或失效时仍具备强鲁棒性
◆集成紧凑的接触估计模块，无需额外传感器即可与状态估计共享信息
◆在多种人形机器人、步态及真实场景下验证，在精度、效率和输出频率上均优于现有融合方法...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-07-20</td><td>Toward Site-Aware MR Art Exhibitions: A SLAM-Based Deployment Pipeline for Spatial Coherence and Exhibition Experience<br><a href='http://arxiv.org/pdf/2607.17665'>论文</a></td><td>本文针对大规模混合现实（MR）艺术展览部署缺乏系统性指导的问题，提出了一套基于SLAM技术的实用部署流程。研究者首先通过试点研究对比了基于标记（marker-based）和基于SLAM的空间对齐方法在MR展览中的表现差异，验证了SLAM在复杂展览环境中的优势。在此基础上，他们将空间对齐不仅视为技术手段，更视为影响展览体验的设计决策，构建了一个融合技术部署与策展理念的完整流程。该流程通过系统开销测量和用户主观体验反馈进行了双重评估，结果表明空间对齐质量直接影响展览的整体连贯性、访客的沉浸感与连续性以及对艺术作品的解读。最后，研究为未来大规模MR艺术展览的部署提供了具有实证依据的设计参考。

◆ 创新点一：将空间对齐从纯技术问题提升为影响展览体验的设计决策，强调技术与策展的融合。

◆ 创新点二：实证对比了基于标记与基于SLAM的对齐方法，为MR展览空间对齐方案的选择提供数据支撑。

◆ 创新点三：提出面向大规模MR艺术展览的系统化部署流程，弥补现有研究多停留在原型或个案层面的不足。

◆ 创新点四：从技术稳定性与用户体验双重维度评估流程效果，揭示空间对齐对展览连贯性、沉浸感及作品解读的多维影响。</td></tr>
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
<tr><td>2026-08-06</td><td>Confidence matters: Leveraging Multi-view Geometric Priors for GS-based Reconstruction<br><a href='http://arxiv.org/pdf/2608.06117'>论文</a></td><td>本文针对3D高斯溅射(3DGS)在高光等复杂场景下几何重建质量不佳的问题,提出将法线和深度等几何先验融入3DGS框架。研究发现,使用VGGT等多视图模型预测的几何先验显著优于单视图替代方案,核心原因在于多视图模型附带输出的置信度图能够对每个预测进行自适应加权,从而大幅提升先验的有效性。实验在标准基准上验证了该方法在重建质量上的一致性提升,尤其在高光物体和复杂场景中增益显著。

◆ 将法线和深度几何先验集成到3DGS框架,改善高光等困难场景下的几何重建质量
◆ 揭示多视图预测(VGGT)优于单视图预测,关键在于多视图模型自带置信度图
◆ 提出利用置信度图对几何先验进行自适应加权,提升先验在不确定区域的鲁棒性
◆ 在标准基准上取得一致性能提升,在含高光物体的复杂场景中表现尤为突出...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-06-10</td><td>SalArt-VQA: Diagnosing Whether VLMs Understand Salient Artifacts in Generated Images<br><a href='http://arxiv.org/pdf/2606.12671'>论文</a></td><td>这篇论文针对视觉语言模型(VLMs)在AI生成图像伪影检测中的细粒度理解能力进行了诊断性研究。作者指出,尽管VLMs在图像级伪影检测上表现良好,但其判断可能依赖错误的视觉线索或区域,导致正确结论背后隐藏着推理失败。为此,论文构建了SalArt-VQA基准,包含950张图像和3681道人工标注的多项选择题,覆盖伪影图像、真实参考图像和配对生成参考图像,从存在性检测、语义定位、空间定位和证据支撑的缺陷识别四个维度系统评估模型。对20个VLMs的测试揭示,最强模型虽达到99.37%的检测召回率,但仅在53.26%的图像上同时答对四类问题,且模型存在敏感性与校准之间的权衡。

◆ 提出首个面向AI生成图像显著伪影细粒度理解的诊断性基准SalArt-VQA,填补了仅依赖图像级检测准确率所掩盖的评估盲区。
◆ 设计四类对齐问题(存在性检测、语义定位、空间定位、证据支撑的缺陷识别),系统检验VLMs的伪影判断是否建立在局部视觉证据之上。
◆ 引入伪影图像、真实参考图像和配对生成参考图像三类对照划分,可定量评估模型在无伪影场景下的校准能力与拒答行为。
◆ 揭示了VLMs普遍存在的敏感性-校准权衡现象:敏感模型易做出无依据的伪影声明,保守模型则通过漏检来规避误报。
◆ 实验证明高检测准确率并不等同于具备扎实的伪影理解能力,为后续模型改进指明方向。</td></tr>
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
<tr><td>2026-08-06</td><td>Design and Evaluation of a Touchscreen-Based Teleoperation Interface for Robotic Manipulators<br><a href='http://arxiv.org/pdf/2608.06219'>论文</a></td><td>本文针对核工业表面接触任务（如拭子采样）对高精度遥操作的需求，设计了将连续手指运动直接映射为机械臂运动、并集成控制与可视化功能的新型触摸屏遥操作界面。基于Franka Emika Panda机械臂的跨国远程控制，20名参与者的对比实验结果显示，触摸屏组任务完成时间较手柄组缩短53.5%（中位数2.50分钟对比5.38分钟），正弦路径覆盖率从84.1%提升至90.7%，且超调量显著降低。NASA-TLX认知负荷评分从手柄组的52分降至触摸屏组的43分（-17.3%），一键自主模式进一步降至31分。研究还通过运动学、生理与行为多维数据，系统评估了任务表现、认知负荷与操作员信任度，验证了触摸屏界面在效率、精度和可用性方面的综合优势。

创新点：
◆ 提出连续手指运动到机械臂运动的直接映射控制方式，突破传统手柄的离散输入限制
◆ 在单一界面集成控制与实时可视化功能，提升操作的直观性与自然性
◆ 构建融合运动学与生理行为数据的多维度评估方法
◆ 面向核工业高精度面接触任务场景，验证触摸屏遥操作在效率、精度和认知负荷方面的综合优势...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-05</td><td>From Transparent Labware Segmentation to Collision Avoidance: A Real-Time Edge-Aware Perception Pipeline<br><a href='http://arxiv.org/pdf/2608.04769'>论文</a> | <a href='https://github.com/havishamy/TransYOLO_3D'>代码</a></td><td>本文针对透明实验室玻璃器皿因折射、镜面反射和缺乏稳定内部纹理而难以被传统分割方法准确识别的问题，提出了一种面向实时机器人碰撞规避的边缘感知实例分割与三维感知流水线。

◆ 提出了一种将轻量级边缘检测分支与一阶段实时实例分割主干相结合的框架，通过边缘引导注意力融合和无参数SimAM模块增强网络对透明物体边界轮廓的感知能力。

◆ 构建了包含3485张图像、21个类别的真实实验室玻璃器皿实例分割数据集LabGlass-IS，填补了透明器皿专用数据集的空白。

◆ 实现了Boundary F-score达到97.80的领先精度，超越FastSAM框架18.93个BF点，同时保持7.1ms的推理速度，参数量仅为最接近竞品的2.85%。

◆ 通过掩码质心的多视图三角化获取三维位置信息，构建保守的包围体碰撞约束，在真实机器人实验中实现93.3%的碰撞规避成功率。</td></tr>
<tr><td>2026-08-05</td><td>OmniRouting: A Semantic-Coupled Multimodal Benchmark for Constraint-Aware Spatial Reasoning in PCB Routing<br><a href='http://arxiv.org/pdf/2608.04434'>论文</a></td><td>OmniRouting是首个面向PCB布线推理的大规模基准，填补了LLM在电子设计自动化复杂约束布线任务上的评估空白。该基准包含1681个工业级原理图耦合PCB设计，涵盖板几何、组件布局、焊盘位置、网络表与叠层信息等真实工程数据。研究提出四项评估任务：几何布线推理、设计规则感知布线推理、电气功能推理及工具增强智能体布线，全面考察模型在路径规划、规则遵守和电气连接保持方面的能力。实验系统揭示了当前大型多模态模型在PCB布线中的显著缺陷，包括弱路径规划能力、差设计规则遵循和不一致的电气功能保持。作者承诺开源全部基准数据、评估代码和工具接口以促进后续研究。

◆ 首创工业级原理图耦合的PCB布线推理基准，弥补EDA领域LLM评估空白
◆ 构建几何、设计规则、电气功能与工具增强的四维任务评估体系
◆ 实证揭示LMM在路径规划、规则遵守、电气一致性方面的关键能力局限
◆ 承诺完全开源基准数据、评估代码与工具接口推动社区研究...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-07-30</td><td>Arm2Air: Cross-Embodiment Skeleton Transfer for 3D Relay Formation<br><a href='http://arxiv.org/pdf/2607.27627'>论文</a></td><td>本文提出Arm2Air跨形态迁移框架，将机械臂的避障运动骨架先验迁移至无人机三维中继放置任务，通过Neural MP模型将源域动作转化为有序骨架，预训练Transformer迁移平台并以LoRA高效适配目标域。

◆跨形态有序骨架迁移机制：首次将异构机械臂运动的结构化骨架作为先验，迁移到UAV三维中继链构造中，解决目标域数据稀缺问题

◆LoRA参数高效适配：仅更新0.134M参数即获53.6%位置误差降低，远低于全微调1.383M

◆多目标协同中继精化：综合优化连通性、瓶颈容量、时延与移动代价，降低最大跳距13.2%与跳距方差75.2%

在9个高复杂度城市地图上规划时间中位数降低64.9%，密集城区瓶颈容量提升32.6%，验证了异构具身任务间有序结构先验迁移的可行性与数据高效性。</td></tr>
<tr><td>2026-07-29</td><td>CinemaTraj: Composing Atomic Camera Trajectories for 3D Scenes with LLM Agents<br><a href='http://arxiv.org/pdf/2607.26910'>论文</a></td><td>CinemaTraj提出了一种基于大语言模型代理的相机轨迹自动生成框架，能够根据自然语言描述在三维场景中规划出具有电影表现力的相机运动路径。该方法将相机轨迹规划重新定义为一个语言驱动的空间推理问题，通过为LLM代理提供结构化的三维场景图作为空间先验，使其能够将用户提示分解为一系列原子化的电影摄影动作。

◆核心创新在于将复杂轨迹生成问题分解为dolly、orbit、crane、pan、tilt、zoom、arc等原子化电影运动的组合，并提出一种新的参数化轨迹表示方法，既能表达电影语义又可优化避障。

◆利用三维场景图作为结构化空间先验，将LLM的推理锚定在准确的几何与语义知识上，避免了现有方法缺乏三维空间感知或脱离摄影语义的局限。

◆框架还同步生成与相机运动对齐的旁白和字幕，输出完整的带叙事视频。

◆在ScanNet++真实场景上的实验表明，该方法在提示对齐度、轨迹质量和安全性指标上均优于现有方法，能生成忠于描述、无碰撞且具有高电影质量的轨迹。</td></tr>
<tr><td>2026-07-29</td><td>Semi-Decentralized Multi-Spacecraft Collision Avoidance under Communication Constraints<br><a href='http://arxiv.org/pdf/2607.26570'>论文</a></td><td>本文针对航天器碰撞规避中地面站间歇通信导致信息延迟和异步更新的问题，研究了通信受限下的协同规划方法。作者将多航天器碰撞规避问题建模为半去中心化POMDP（SDec-POMDP），使信息传播直接受地面站可见性窗口约束，更贴合真实运行场景。论文采用近似递归小步长半去中心化A*算法（RS-SDA*）求解联合机动策略，延续了去中心化多智能体规划的A*算法脉络。实验结果表明，该半去中心化规划在协同质量上接近完全集中式规划，同时比持续协同减少28.5%的同步事件。与传统基于规则的操作员启发式方法相比，通信感知规划能更稳定地满足期望的脱靶距离要求并减少不必要的轨迹偏差。

◆ 创新点一：提出半去中心化POMDP（SDec-POMDP）框架，将信息传播直接建模为地面站可见性窗口，突破传统方法对持续信息共享或不切实际通信模型的假设。

◆ 创新点二：采用近似递归小步长半去中心化A*（RS-SDA*）算法求解联合机动策略，融合了去中心化多智能体规划的前沿方法与航天任务约束。

◆ 创新点三：在显著减少同步通信事件的同时，达成接近集中式规划的碰撞规避性能，并通过对比基于规则的方法验证了通信感知规划在脱靶距离控制和轨迹偏离方面的优势。</td></tr>
<tr><td>2026-07-29</td><td>RLMM-Flow: A Flow-based Mobile Manipulation Framework with Latent-Space Reinforcement Learning<br><a href='http://arxiv.org/pdf/2607.26460'>论文</a></td><td>该论文针对移动操控任务中需要同时满足到达目标、避碰、底盘运动学约束、机械臂关节限制及轨迹平滑性的问题，提出了一种基于流的移动操控框架RLMM-Flow。该框架采用两阶段策略：首先通过专家示教学习一个能够捕捉多模态全身运动先验的流策略，随后冻结该流策略，在隐空间中进行强化学习后训练。

◆ 提出流策略预训练与隐空间强化学习后训练相结合的两阶段框架，在保留快速流推理能力的同时突破示教分布限制。

◆ 设计潜变量引导网络，将初始噪声引导至高价值动作片段，并采用动作空间评论家预热策略来稳定高维隐空间优化。

◆ 引入由粗到细的隐空间引导机制，控制范围从时间共享的隐表示逐步扩展到全维残差表示。</td></tr>
<tr><td>2026-07-28</td><td>Macroscopic wall pressure and microscopic contact load in crowds without egress: social-group cohesion and boundary buffering<br><a href='http://arxiv.org/pdf/2607.25780'>论文</a></td><td>本文针对无疏散通道的密集人群场景,耦合弹性重定向模型(ERM)与社会力模型(SFM),系统研究了宏观壁面压力与微观接触载荷的力学风险机制。研究将群组凝聚力γ_g与墙体缓冲γ_w作为后碰撞行为的两个关键参数,并以壁面线压力P_wall和单体最大碰撞冲量δp_max分别量化宏观与微观风险。

研究发现凝聚力与墙体缓冲总体上通过将个体保留在群体内部来降低P_wall,但在中等凝聚力区间会出现高δp_max的危险窗口,揭示了P-p权衡关系。

◆揭示了ERMS与SFM耦合动力学中由独立个体诱导的γ_w=0.5处的不连续相变边界,以及由群组个体诱导的沿(1-γ_w)(1-γ_g)=0.5有限线段的连续相变边界,该边界伴随磁化率发散并终止于临界点。

◆阐明SFM的推挤与滑动机制显著放大δp_max,而主动驱动行为通过近壁累积抬高P_wall,二者不可同时最优。

◆发现γ_g→1时局部配对抑制簇生长,将动能从相对运动转移到质心运动,从而降低δp_max。

这些相变与权衡关系仅在ERM+SFM耦合系统中出现,为无疏散高密度场所的人群风险评估与安全规划提供了机理指导。</td></tr>
<tr><td>2026-07-28</td><td>SGTP: Sampling-based Game-Theoretic Planning for Real-Time Multi-Vehicle Autonomous Racing<br><a href='http://arxiv.org/pdf/2607.25388'>论文</a> | <a href='https://sgtp-racing.github.io/'>代码</a></td><td>本文针对多车自主竞速中实时规划多样化竞争行为的难题,提出了基于采样的博弈论规划框架SGTP,核心创新如下:

◆ 将博弈论推理与GPU加速的控制序列采样及动力学推演相结合,实现了高效的多车交互决策,在多次迭代求解中平均计算时间仅0.095秒。

◆ 设计了博弈感知成本函数对采样轨迹进行排序,能够捕捉车辆间的竞争交互,生成多样化的竞速策略,解决了战略多样性与计算效率之间的平衡难题。

◆ 通过显式执行赛道边界和动态避碰约束进行可行性筛选,确保不同竞速策略之间过渡的安全性与可靠性。

◆ 在高交互竞速场景中实现95.24%的胜率和99.35%的任务完成率,并成功扩展至最多10辆车的规模化场景,展现出良好的实时性与可扩展性。

◆ 开放了代码与多智能体自主竞速算法基准测试平台,为该领域未来研究提供了重要基础设施。</td></tr>
<tr><td>2026-07-27</td><td>Learning Adaptive Multi-Task Guidance, Navigation, and Control via Hypernetworks<br><a href='http://arxiv.org/pdf/2607.24292'>论文</a></td><td>本文针对轨道自由飞行机器人提出HYPER-GNC多任务强化学习框架,旨在解决传统为每个任务单独训练策略导致的架构脆弱性和灵活性不足问题。核心思路是利用超网络将物理信息驱动的任务嵌入映射到共享actor-critic策略的权重,从而用一个紧凑控制器同时掌握速度跟踪、对接、巡检和带避障的导航四类GNC任务。该连续嵌入空间使控制器在部署时无需重训练即可泛化到新型任务配置,并在大惯性扰动与外部外力下保持稳定。实验表明其样本效率与单任务专家策略相当,且成功在物理卫星仿真器上完成全部任务的仿真到实物迁移。

◆ 提出基于超网络的多任务GNC统一框架,用一个紧凑控制器替代多个任务专属策略,显著降低架构复杂度和资源开销。
◆ 设计物理信息驱动的连续任务嵌入空间,支持零样本泛化至新任务配置,无需重训练即可适应任务演变。
◆ 兼顾样本效率与鲁棒性,在显著惯性扰动和外部外力下保持稳定控制性能。
◆ 完成从仿真到物理卫星仿真器的全任务迁移验证,有效弥合sim-to-real差距。</td></tr>
<tr><td>2026-07-27</td><td>SILICA: Repurposing Diffusion Priors for Joint Glass Segmentation and Depth Estimation<br><a href='http://arxiv.org/pdf/2607.24249'>论文</a></td><td>本文提出SILICA框架，针对标准深度传感器在透明表面失效这一难题，创新性地复用文本到图像扩散模型的丰富先验，实现玻璃分割与玻璃感知深度的联合预测。该方法通过两个任务间的互信息交换建立稳健的空间层次结构，完全摆脱对真实玻璃深度标注的依赖，并利用预测的分割掩码过滤标准传感器中的错误深度点，从而恢复精确的度量级玻璃深度信息，支撑下游三维建图与自主避障应用。

◆首次将扩散模型先验知识迁移至透明表面感知任务，赋予模型出色的零样本跨环境泛化能力。
◆设计分割与深度联合预测的互信息交换机制，无需配对的真实玻璃深度标注即可完成训练。
◆构建Mirage 18k新数据集，在多个未见环境中较现有最优方法性能提升近20%，树立透明表面感知新基准。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-06</td><td>Acoustic-driven millimetric helical robot: ultrasonic synergistic manipulation in confined fluidic environment<br><a href='http://arxiv.org/pdf/2608.05746'>论文</a></td><td>本文提出了一种协同多声场驱动策略,通过将声辐射力与声流效应相结合,实现了毫米级螺旋机器人在受限生物流体环境中的可控推进,有效解决了传统声学操控在毫米尺度推进效率不足的问题。研究团队借助多物理场仿真揭示了组合声场下螺旋机器人的动力学机制,并通过实验验证了其平面导航、斜面爬升和垂直运动等多模态运动能力,以及半自主导航下的机动性显著提升。进一步的体外猪静脉血管实验证明,协同声场能够支持单向与往复运动,展现了在生物医学受限环境中的适用性。

◆提出声辐射力与声流协同的多声场驱动新策略,突破毫米级声学推进效率瓶颈
◆建立多物理场仿真模型,系统阐明组合声场下毫米螺旋机器人的运动动力学机制
◆实现平面、斜面与垂直多模态运动及半自主导航,显著提升机动性能
◆在猪静脉血管体外模型中验证受限生物环境下的可控运动,为体内介入应用奠定基础...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-07-26</td><td>Learning Traversability-Aware Global Planners for Long Horizon Off-Road Navigation<br><a href='http://arxiv.org/pdf/2607.23743'>论文</a></td><td>这篇论文针对越野大范围自主导航难题,提出了一种融合航拍数据学习可通行性地图的全局规划方法。其核心思想是利用人类驾驶GPS轨迹作为监督信号,同时结合LiDAR自监督几何先验,从卫星影像、航空LiDAR和矢量地图中直接学习连续的越野可通行性表征。◆提出一种无需密集标注的可通行性学习范式,仅依赖人类轨迹监督与LiDAR几何先验即可训练,克服了航拍数据标注稀缺的瓶颈。◆发布了一个大规模公开数据集,涵盖299个场景约1244平方公里多样地形,并配有1130公里人类驾驶轨迹。◆在Clearpath Warthog实地测试中,七个路线上的规划路径长度仅比人类路径长3.66%,相比仅使用局部规划器减少约85%的人工干预,显著提升了长距离越野自主导航的可靠性。</td></tr>
<tr><td>2026-07-24</td><td>Offline Vision-Language Navigation with Geometric Goal Localization for Outdoor Environments<br><a href='http://arxiv.org/pdf/2607.22226'>论文</a></td><td>本文针对户外视觉语言导航(VLN)系统过度依赖云端基础模型、无法离线运行的问题,提出了面向完全本地化部署的解决方案。

◆ 首次系统性地对17个边缘可部署小型语言模型(SLM)与4个在线API在机器人导航指令分解任务上进行了基准测试,涵盖三种计算平台,准确率和延迟方面均提供了选型指导。

◆ 提出了一种轻量级的语义-几何混合目标定位框架,融合开放词汇目标检测、提示式分割与LiDAR几何信息,可在几何观测不可靠时保持视觉方位引导。

◆ 集成上述技术构建了Edge-BehAV系统,作为BehAV架构的完全本地化扩展,支持云独立的行为引导导航。

实验结果表明,最佳离线SLM在指令分解性能上可与最强云端API媲美,运行速度约快9倍且无需网络;目标定位框架将平均目标距离误差从2.05米降至0.20米;完整系统在32次闭环户外试验中成功31次。</td></tr>
<tr><td>2026-07-24</td><td>Safe Learning Predictive Control for Ego-World Robotic Systems<br><a href='http://arxiv.org/pdf/2607.22225'>论文</a></td><td>本文针对共享环境中自主导航的安全避障问题，提出了SOWL-MPC，一种基于学习的预测控制策略，应用于作者新提出的&quot;自我-世界&quot;机器人框架。系统仅依赖噪声状态测量，通过稀疏变分高斯过程（SVGP）推断世界机器人潜在控制策略的后验分布，并利用在线变分条件（OVC）方法随流式数据持续更新。学习的策略经非线性动力学的近似矩传播后输入到不确定性感知模型预测控制（MPC）中，从而实现自我机器人的安全机动。

◆ 提出了&quot;自我-世界&quot;机器人框架这一新场景，其中世界机器人的控制策略完全未知，自我机器人需通过在线学习推断其行为以实现安全避障。

◆ 融合稀疏变分高斯过程与在线变分条件机制，实现对潜在策略后验分布的实时流式更新，仅需噪声状态观测。

◆ 通过非线性动力学的近似矩传播将学习到的不确定策略前向预测，并嵌入不确定性感知MPC，兼顾安全性与实时性。

◆ 通过ROS 2大规模蒙特卡洛仿真及真实室内机器人硬件实验，验证了方法的实时可行性与安全保障。</td></tr>
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
<tr><td>2026-08-05</td><td>Failing Gracefully: Mitigating Impact of Inevitable Robot Failures<br><a href='http://arxiv.org/pdf/2608.05313'>论文</a></td><td>本文针对服务机器人在家庭环境中不可避免的故障问题，提出了一种全新的安全规划框架。现有研究多聚焦于故障检测与恢复，而本文创新性地从&quot;故障影响&quot;的角度入手，将故障视为规划阶段必须考虑的约束条件。

◆ 提出了一种新颖的安全评估公式，综合量化故障发生时机器人与周围实体发生影响性交互的概率及其后果严重程度，使机器人能够在任务效率与安全性之间做出更合理的规划决策。

◆ 提出了基于概率与严重性联合度量的影响评估方法，将抽象的&quot;故障后果&quot;转化为可计算的规划目标，从而支持机器人在任务执行前主动规避高风险行为。

◆ 开发了FailBench仿真基准，基于MuJoCo构建，可系统模拟感知异常、执行器故障等多种故障模式下的机器人与环境交互，为安全规划算法与学习策略的评估提供统一平台。

总体而言，本文将故障应对从&quot;事后处理&quot;前移至&quot;事前规划&quot;，为家庭服务机器人在不可避免故障下的安全可靠部署提供了理论基础与实验工具。</td></tr>
<tr><td>2026-08-05</td><td>OmniRouting: A Semantic-Coupled Multimodal Benchmark for Constraint-Aware Spatial Reasoning in PCB Routing<br><a href='http://arxiv.org/pdf/2608.04434'>论文</a></td><td>OmniRouting是首个面向PCB布线推理的大规模基准测试,旨在评估大语言模型在严格几何、拓扑和电气约束下处理复杂布线问题的能力。该基准包含1681个工业级原理图耦合PCB设计,涵盖板几何、组件布局、焊盘位置、网络表、叠层信息及布线约束等真实工业数据。

◆首创了面向EDA领域的语义耦合多模态基准,首次将PCB布线作为约束感知空间推理任务进行系统评估。

◆设计了四个递进式任务层级,涵盖几何布线、设计规则感知、电气功能保持及工具增强代理式布线,全面衡量模型在物理、规则与电气三个维度的推理能力。

◆揭示了当前多模态大模型在路径规划、设计规则遵循和电气功能保持方面的显著不足,为未来研究提供了重要参考。

该工作填补了LLM在工业级EDA布线推理领域的评估空白,并将开源全部数据、代码与工具接口以促进后续研究。</td></tr>
<tr><td>2026-08-05</td><td>SCOPE: Field-of-View-Aware Path Planning in Unknown 3D Environments via Safety-Volume Certification<br><a href='http://arxiv.org/pdf/2608.04420'>论文</a></td><td>SCOPE提出了一种面向有限视场传感器的安全路径规划框架，要求机器人在执行每个运动前必须对其膨胀后的完整体积进行观测并验证为自由空间。该方法在未知体素地图中提出在线安全体积认证机制，构建认证图结构，其顶点恰好对应具有完全已知自由安全体积的位置。

◆核心创新是引入安全体积认证概念，将规划解耦为乐观目标导向引导与认证执行两部分，把乐观路径上的首个未认证点转化为显式观测义务。

◆提出基于目标中心的视点搜索方法，并递归清除中间未认证的视点可达性，形成系统的观测规划递归结构。

◆设计认证预览机制与观测感知的轨迹优化后端，实现平滑执行，并证明在理想条件下具有条件完备性。

实验在三个未知3D环境的60个随机任务中全部到达目标，进入非认证膨胀空间接近零，预览机制使任务时间平均缩短27%，并在真实机器人上得到验证。</td></tr>
<tr><td>2026-08-04</td><td>Flying over The Uncertain Nature (FORTUNE): Intelligent and Humanistic 3D Path Planning for Low-Altitude Collaboration<br><a href='http://arxiv.org/pdf/2608.03408'>论文</a></td><td>FORTUNE提出了一种面向低空协同感知的3D多无人机路径规划与任务分配框架，旨在解决城市动态环境下异构时空需求、环境不确定性和以人为本的操作约束等关键挑战。该工作将地面兴趣点(PoI)需求统一建模为持续型、可预测型和突发型三类，并引入高度相关的社会与环境成本(如噪声暴露和公共安全风险),以平衡感知性能与社会合规性。

◆ 构建统一的时空需求建模框架,首次将持续性、可预测和突发三类PoI需求纳入同一优化问题,并叠加高度相关的社会与环境代价。

◆ 提出Transformer驱动的离线预测机制,精准预估Type-II PoI的激活时间窗,提升规划的前瞻性与协调性。

◆ 设计增强型麻雀搜索算法,通过优先级感知的解码策略和危险感知进化机制,高效求解大规模混合整数非线性问题。

◆ 搭建分层离线-在线架构,在线轻量化模块能够动态响应突发需求,同时保持全局任务的一致性与稳定性。

◆ 在真实交通数据和合成场景上的实验表明,FORTUNE在有效性、可扩展性和实际适用性方面均优于现有先进方法。</td></tr>
<tr><td>2026-08-04</td><td>Accelerating Human-Aware Robot Trajectory Generation via Diffusion and Consistency Distillation<br><a href='http://arxiv.org/pdf/2608.03159'>论文</a></td><td>本文针对人机交互场景中非冗余机械臂的约束运动规划问题，提出了一种结合扩散模型与一致性蒸馏的轨迹生成框架。首先利用RRT和RRT*算法生成满足碰撞避免与自碰撞避免约束的轨迹数据集，据此训练扩散模型以通过引导采样生成符合约束的关节空间轨迹。为克服扩散模型迭代采样推理时间长的瓶颈，进一步引入一致性蒸馏技术将推理过程大幅压缩。该方法在损失函数中加入了关节加权的jerk正则化项，惩罚关节加速度的突变，从而生成更加平滑的轨迹。仿真结果表明，一致性模型能够在100毫秒内生成150条候选轨迹，并保持较高的任务成功率，同时显著降低关节和末端执行器的jerk值。

◆ 将RRT/RRT*生成的约束满足轨迹与扩散模型结合，解决非冗余机械臂在HRI中难以同时处理安全与运动学约束的问题。
◆ 引入一致性蒸馏技术，将迭代扩散采样的推理时间压缩至100毫秒以内，支持实时生成大量候选轨迹。
◆ 在损失函数中加入关节加权jerk正则化项，有效平滑关节加速度变化，提升轨迹的动态品质。</td></tr>
<tr><td>2026-08-04</td><td>SUV: Future Scene Understanding as Video Generation for End-to-End Driving<br><a href='http://arxiv.org/pdf/2608.03084'>论文</a></td><td>本文提出SUV框架，将端到端自动驾驶中的未来场景理解问题重新定义为视频生成任务。◆创新点一：摒弃任务特定的视觉预测头，采用预训练视频基础模型作为共享视频专家，统一预测未来外观、语义、相对深度和实例动态四种信息流。◆创新点二：设计联合视频-动作注意力机制，使动作规划模块能够关注所有未来视频流的隐式表征，并直接生成自车轨迹。◆创新点三：实验表明结构化的未来监督和直接访问未来流能够显著提升轨迹规划质量。总体而言，SUV仅依赖单前视摄像头且无需候选轨迹选择，在NAVSIM-v2的navtest和navhard上分别取得91.0 EPDMS和36.9的当前最优成绩，并在长尾WOD-E2E基准上达到具有竞争力的7.94 RFS。</td></tr>
<tr><td>2026-08-03</td><td>Biconvex Optimization for Smooth Minimum-Time Trajectories around Convex Obstacles<br><a href='http://arxiv.org/pdf/2608.02834'>论文</a> | <a href='https://wernerpe.github.io/bmtp-website/'>代码</a></td><td>本文提出了一种用于凸障碍物环境下最小时间运动规划的双凸优化方法，具备收敛保证、随时性及任意阶导数约束支持能力。作者通过变量替换将最小时间目标与所有导数约束联合凸化，并以时变分离超平面处理避障，将问题转化为双凸程序，通过交替计算最大间隔分离平面与优化轨迹来求解。

◆ 通过变量变换实现最小时间目标与任意阶导数约束的联合凸化，大幅扩展了可处理问题的范围
◆ 引入时变分离超平面与双凸优化交替迭代，仅为当前迭代发生碰撞的障碍物添加平面，使轨迹可跳跃绕障并逃离局部极小值
◆ 从简单无碰撞折线出发即可保证全局收敛，对不良初始化具有显著鲁棒性

在无人机导航与双臂卸料实验中，该方法以接近现有最优分解式规划器的计算时间生成了高质量轨迹，同时能处理更广泛的问题类别。</td></tr>
<tr><td>2026-08-06</td><td>TRACE: Ergodic Trajectory Optimization for Active Scene Reconstruction<br><a href='http://arxiv.org/pdf/2608.02304'>论文</a> | <a href='https://github.com/spikelab-jhu/trace-active-reconstruction'>代码</a></td><td>本文针对主动场景重建中贪心下一最佳视角方法因短视规划导致效率低下的问题,提出基于遍历性覆盖的全局轨迹优化框架TRACE。

◆ 将主动重建重新建模为遍历性覆盖问题,使传感器轨迹的时间平均空间统计量匹配由地图导出的目标信息分布,实现全局结构感知的路径规划。

◆ 在线从地图的不确定性与可见性中推导目标信息分布,让规划器动态响应建图状态变化。

◆ 提出核遍历性水平规划器,结合梯度流与足迹消减机制,生成长视域且信息高效的轨迹。

◆ 打通建图与轨迹优化的闭环,避免感知资源在视点间转移过程中的浪费。

在Replica数据集上,TRACE相比NBV基线在PSNR上提升1.5 dB,验证了所提方法的有效性。</td></tr>
<tr><td>2026-08-03</td><td>A Forward-Inverse Dynamic Game Framework for Enhanced Multi-Agent Trajectory Planning<br><a href='http://arxiv.org/pdf/2608.01636'>论文</a></td><td>本文研究非线性动力学系统中多智能体轨迹规划的反馈纳什均衡求解问题,针对现有方法假设完全理性且依赖固定正则化的不足,提出了一种前向-逆向动态博弈的统一框架。

◆ 提出带状态依赖权重的KL正则化动态博弈方法,自适应平衡最优性与行为先验,有效刻画有限理性与空间变化的交互强度。

◆ 开发基于最大熵逆强化学习与物理信息正则化的上下文感知逆博弈模块,在保持前向博弈结构一致性的同时从演示数据中推断未知代价参数。

◆ 证明正则化局部博弈的逐次迭代良态性,并在有界名义轨迹更新条件下论证自适应权重函数的Lipschitz连续性,提供理论保障。

协同导航与汇车场景下的数值仿真与多机器人实验验证了所提框架在安全关键任务中的有效性与实用性。</td></tr>
<tr><td>2026-08-02</td><td>DreamTrajectory: Trajectory-Guided Action Generation with World Model Alignment for Mobile Manipulation<br><a href='http://arxiv.org/pdf/2608.01381'>论文</a></td><td>DreamTrajectory 是一个面向语言条件移动操作的轨迹引导框架，旨在解决现有视觉-语言-动作策略在协调底盘与机械臂运动时缺乏显式任务空间规划以及开环执行导致规划与实际运动偏差累积两大问题。该方法通过在单一动作专家中联合预测意图级别的末端执行器轨迹和全身动作块，使轨迹显式引导底盘-机械臂动作生成，并利用轻量级轨迹世界模型预测候选动作块将产生的轨迹，进而在测试时通过搜索-预测-评分流程挑选与规划轨迹最一致的候选动作。实验表明该方法在 MS-HAB 基准上将平均成功率从 32.3% 提升至 47.5%，经测试时精炼后进一步达到 54.8%，并在三个真实移动操作任务上分别取得 63.3%、81.7% 和 90.0% 的成功率，在接触丰富的关节物体任务上提升最为显著。

◆ 在单个动作专家中联合预测意图级末端轨迹与全身动作块，使轨迹显式引导底盘与机械臂的协调动作生成。
◆ 引入轻量级轨迹世界模型，预测候选动作块将实际产生的轨迹，缩小规划与执行之间的运动偏差。
◆ 设计测试时搜索-预测-评分流程，从多个候选中筛选与规划轨迹最对齐的动作，提升执行可靠性。</td></tr>
<tr><td>2026-08-02</td><td>PRISM: Privileged Probabilistic Latent Supervision for End-to-End Autonomous Driving Motion Planning<br><a href='http://arxiv.org/pdf/2608.01201'>论文</a></td><td>本文针对端到端自动驾驶系统中输出监督难以有效训练深层隐藏层的问题，提出了一种基于特权信息的概率潜在监督方法PRISM。区别于现有依赖视觉语言模型进行潜在特征监督的工作，PRISM从理论层面深入剖析了此类方法性能增益的真实来源，并设计了更简洁有效的替代方案。

◆ 理论发现VLM监督的收益本质源于训练过程中模型与真实标注数据之间形成的潜在连接，而非VLM本身的推理能力。

◆ 提出概率深度监督框架，将模型中间潜在变量视为可重参数化分布，直接利用未来真实轨迹作为特权信息进行正则化。

◆ 通过证据下界（ELBO）对整体架构进行优化，无需引入额外的VLM推理过程。

◆ 在nuScenes数据集的实验中，使用相同训练数据和端到端架构，规划L2误差降低8%，碰撞率减少3%，且仅带来可忽略的计算开销。</td></tr>
<tr><td>2026-08-02</td><td>DynActiveGS: Active Gaussian Splatting for Dynamic Scene Reconstruction<br><a href='http://arxiv.org/pdf/2608.01178'>论文</a></td><td>DynActiveGS提出了一种面向动态环境的主动重建框架，核心目标是在存在运动干扰的条件下实现高质量的三维场景重建。该方法基于3D高斯溅射（3DGS）构建场景表示，并通过在线不确定性预测和不确定性加权优化策略，有效抑制被运动污染的观测数据对重建质量的影响。

创新点方面：

◆ 显式分解不确定性为结构不确定性和运动引起的不确定性，使系统能够区分欠重建的静态区域和因运动导致的不可靠区域。

◆ 基于双重不确定性场进行动态感知的视点选择，优先选择信息丰富且观测稳定的视角，提升探索效率。

◆ 设计动态约束的路径规划机制，在自主探索过程中主动规避运动区域，保证采集数据的可靠性。

◆ 构建统一的闭环流水线，整合重建、不确定性估计、视点选择与路径规划，实现端到端的鲁棒主动重建。

该方法在多个动态基准数据集上的实验表明，在重建精度、完整性、渲染质量和探索效率方面均优于现有主动重建基线方法。</td></tr>
<tr><td>2026-08-02</td><td>Complete Motion Planning using Workspace-Fibered Decomposition for nR-Planar Manipulator<br><a href='http://arxiv.org/pdf/2608.01172'>论文</a></td><td>该论文针对nR平面冗余机械臂在复杂环境中的运动规划问题，提出了一种基于工作空间纤维分解的递归规划框架，避免在高维完整构型空间中直接搜索。
◆提出工作空间纤维分解方法，将n维构型空间规划问题降维为低维非冗余子链可达工作空间的逐步构造，并通过冗余方向纤维递归提升
◆在引入冗余自由度之前利用最小非冗余子链精确刻画可达性，实现对起始构型连通分量的早期不可行性检测
◆设计增量式纤维提升过程，结合雅可比行列式连续性约束保证局部逆运动学分支一致性，从而正确传递无碰撞连通结构
实验结果表明，该方法在保持规划完整性的同时，显著降低了碰撞检测的计算复杂度。</td></tr>
<tr><td>2026-08-02</td><td>Sampling-Based Visibility Task Planning<br><a href='http://arxiv.org/pdf/2608.01027'>论文</a></td><td>本文针对机器人任务与运动规划（TAMP）中可见性类工具（摄像头、闪光灯、定向天线等）的规划难题，指出传统基于距离度量的启发式方法因无法有效处理视场约束而失效。作者提出两种新型采样算法 VisPRM 和 VisRRT，专门解决可见性任务的规划问题。

◆ VisPRM 利用环境层次化分解与&quot;可见性完整性&quot;概念，高效采样具有清晰视线到目标的构型，显著提升采样质量。

◆ VisRRT 引入专门的逆运动学求解器，使机器人在适当时机能够&quot;瞥视&quot;目标方向，从而快速发现关键构型。

◆ 论文系统性地解决了视场约束下传统 PRM、RRT 和 VIR 算法性能退化的问题，拓展了 TAMP 在感知型设备中的适用性。

通过仿真与真实物理实验，验证了所提算法在成功率与运行时间上均优于现有方法的改进版本，证明了方法的有效性与实用性。</td></tr>
<tr><td>2026-08-01</td><td>GeminiPainter&#x27;s sequence-formed pipeline comprised of perception, cognition, planning, and action stages<br><a href='http://arxiv.org/pdf/2608.00829'>论文</a></td><td>这篇论文提出了GeminiPainter系统，一个融合实时人脸检测、AI素描生成与机器人绘制的自主肖像画生成系统，采用了感知-认知-规划-动作的序列化流水线架构。该系统从视频帧中提取人脸区域，通过Gemini Vision API将其转化为极简单线素描，再利用基于图论的路径规划优化笔画顺序，最终在6自由度协作机械臂上完成平滑绘制。

◆ 提出感知-认知-规划-动作四阶段流水线框架，将计算机视觉、神经艺术抽象、运动优化与机器人控制进行系统性整合。
◆ 引入Gemini Vision API实现极简单线人脸素描的AI自动生成，简化传统肖像绘制的复杂流程。
◆ 采用基于图论的路径规划方法优化笔画执行顺序，提升机械臂绘制效率与轨迹平滑性。
◆ 在6自由度协作机械臂上实现完整闭环，将抽象AI艺术输出转化为可执行的物理绘制动作。
◆ 通过用户评分验证系统效果，素描质量、执行表现和用户体验均获得4分以上的高评价，证明该方案的可行性与艺术表现力。</td></tr>
<tr><td>2026-08-01</td><td>RIT*: Riemannian Informed Trees for Cost-Adaptive Optimal Motion Planning<br><a href='http://arxiv.org/pdf/2608.00822'>论文</a> | <a href='https://muhayyuddin.github.io/ritstar/'>代码</a></td><td>RIT*是一种基于黎曼几何的批处理知情运动规划框架，将传统欧几里得基元替换为黎曼基元，以适应空间变化的代价度量。

◆提出代价一致的黎曼知情集，比欧几里得知情集更紧致，能更快聚焦低代价区域。

◆在搜索过程中采用各向异性距离度量进行最近邻查找，并通过级联方案高效评估边代价。

◆引入碰撞自适应度量精化CARM方法，从碰撞反馈中在线学习障碍物邻近度代价场，降低对先验度量设计的依赖。

◆在2-D到14-D的多类环境中，RIT*在低维和度量恒定场景下与BIT*持平，但在高维各向异性场景中显著优于欧几里得基线，其中14-DOF双臂规划任务代价改进达24.8%至63.5%。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-undistortion'>Sensor Undistortion</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-07-15</td><td>WNOJ-LIO: A White-Noise-on-Jerk Motion-Prior EKF for High-Dynamic LiDAR-IMU Fusion<br><a href='http://arxiv.org/pdf/2607.13405'>论文</a> | <a href='https://github.com/LvJohny/wnoj-ekf-lio.git'>代码</a></td><td>本文针对高动态场景下LiDAR-IMU里程计面临的扫描内运动畸变与IMU振动噪声耦合问题，提出了基于白噪声加速度先验（WNOJ）的扩展卡尔曼滤波融合框架WNOJ-LIO。该方法在R^3×SO(3)上采用解耦的WNOJ过程模型进行状态预测，并将IMU视为高频测量源而非状态传播驱动，从而避免惯性噪声直接污染去畸变结果和点云配准。

◆在平移和旋转空间上分别建立解耦的WNOJ先验过程模型，实现独立的运动学建模与状态传播。
◆将IMU从传统状态传播驱动角色转变为高频测量源，抑制振动噪声向点云配准环节的传递。
◆推导闭式协方差传播公式，弥合批式WNOJ高斯过程轨迹先验与递归滤波之间的理论鸿沟。

仿真与真实赛车实验（最高速度208 km/h）表明，该方法在去畸变、加速度/角速度去噪及定位精度上均优于FAST-LIO基线。</td></tr>
<tr><td>2026-07-13</td><td>Event-RGB Adaptive Tracking for Nighttime Highway Perception<br><a href='http://arxiv.org/pdf/2607.11646'>论文</a> | <a href='https://github.com/haidongwang96/SEHN'>代码</a></td><td>本文针对高速公路夜间场景下传统RGB相机感知性能退化问题，提出了一种新的多模态融合跟踪方案。其核心思想是打破现有方法中僵化的传感器优先级策略，将异步事件流与RGB帧统一到联合数据关联优化框架中。系统利用自适应扩展卡尔曼滤波，通过NIS统计量在线估计测量噪声，动态调节两种模态的融合权重，使事件流在暗光或高速运动下发挥主导作用，而RGB帧在明亮或静态条件下提供互补信息。此外，作者还基于CARLA仿真器构建了大规模合成数据集SEHN，涵盖白天、无路灯夜间、有路灯夜间等多种环境与交通密度，填补了事件相机高速公路感知领域公开数据集的空白。实验表明该方法在低光照、高速等挑战性场景下显著优于单一模态基线。整体工作为夜间智能交通感知提供了从算法到数据的基础支撑。

◆ 提出JEAT联合事件-RGB自适应跟踪框架，统一异步融合与数据关联，避免硬编码优先级。
◆ 设计基于NIS统计的自适应扩展卡尔曼滤波，动态估计噪声并自适应加权多模态测量。
◆ 发布大规模合成数据集SEHN，覆盖多样化光照与交通条件，弥补事件式高速公路数据集的空白。</td></tr>
<tr><td>2026-07-15</td><td>Your Data Manifold is Secretly a Reward Model: Shell-LCC for Text-to-Video Generation<br><a href='http://arxiv.org/pdf/2606.30248'>论文</a></td><td>◆论文提出“数据流形本身就是奖励模型”的观点，通过显式建模高质量SFT数据的流形结构，为T2V扩散模型提供密集、可微且低成本的奖励信号。
◆方法基于Local Coordinate Coding捕捉数据流形的“骨架”，引导视频潜变量靠近高质量数据分布，从而提升生成真实感。
◆针对传统LCC容易产生均值回归、导致细节丢失的问题，论文提出Shell-LCC，将流形表面建模为各向同性“壳层”，更贴近真实高密度区域。
◆该方法无需额外奖励模型、大规模人工标注或昂贵DPO训练，即可改善视频质量，尤其缓解低层次失真问题。
◆实验表明，Shell-LCC能增强高频细节、减少过平滑伪影，并有效减轻运动模糊，提升文本到视频生成的整体视觉质量。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5039</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4478</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2438</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1622</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1617</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1471</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1297</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1280</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1030</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>996</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>929</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>804</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>782</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>745</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>731</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>718</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>658</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>647</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>626</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>605</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>601</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>565</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>564</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>522</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>502</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>449</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>439</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>355</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>345</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>266</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>263</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>255</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>239</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>226</td><td>dyn_small_obs_avoidance</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1661</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1364</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1096</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1047</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>877</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>701</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>662</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>652</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>623</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>594</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>575</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>573</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>567</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>553</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>518</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>501</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>464</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>452</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>448</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>334</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>313</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>300</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>285</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>279</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>258</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>239</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
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
> 更新于: 2026.08.09
