# 计算机视觉领域最新论文 (2026.07.30)

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
<tr><td>2026-07-19</td><td>DROID-ANCHOR: Odometry-Anchored Recurrent Metric Depth Estimation<br><a href='http://arxiv.org/pdf/2607.17058'>论文</a></td><td>针对单目视觉SLAM系统的尺度模糊与尺度漂移问题，本文提出Metric-DROID，一种端到端循环架构，通过融合本体感知里程计将视觉SLAM锚定到物理度量空间，在保持视觉重投影精度的同时实现稳定的绝对尺度输出。
◆ LSTM更新算子将高频里程计序列编码为空间特征图，为迭代优化提供持续性的度量偏置，使网络在循环更新过程中有效保留运动学信息。
◆ 不确定性感知度量后端（BA_odom）将里程计视为带学习异方差协方差Σ_o的几何锚点，通过时变协方差自适应平衡视觉重投影与度量平移残差，显著抑制轮式滑动和传感器噪声的影响。
◆ 选择性残差微调策略在保留预训练几何先验的同时实现零样本度量对齐，避免破坏原有视觉特征表达能力。
大量实验表明，Metric-DROID在多个公开数据集上的度量深度估计精度和鲁棒性均显著优于现有方法。</td></tr>
<tr><td>2026-07-18</td><td>A BIM-enabled, Agent-based Discrete-event Simulation Platform for Robotic Studies: A Method based on Graph Theory<br><a href='http://arxiv.org/pdf/2607.16920'>论文</a></td><td>本文提出了一种基于BIM的智能体离散事件仿真平台，用于室内机器人在设施管理中的知识驱动导航与操作规划。该研究将室内环境离散化为网格单元，并映射为图节点，根据其与建筑元素的空间关系将其分类为目标、障碍或常规节点。

◆提出了BIM与智能体仿真深度融合的框架，充分利用BIM中丰富的几何、语义和运行信息，弥补了传统SLAM和路径规划对建筑信息利用不足的局限。

◆构建了基于图论的环境表征方法，将建筑空间抽象为带节点分类和边权成本的图结构，使图论算法能够计算高效且无碰撞的导航路径。

◆通过网格细化策略解决了粗离散化下目标占据与障碍占据单元重叠的问题，显著提升了空间精度与路径可行性。

该平台支持机器人在实际部署前的虚拟评估，为BIM驱动的机器人在设施管理中的应用奠定了基础。</td></tr>
<tr><td>2026-07-18</td><td>GLidE-SLAM: GL-Accelerated Indirect-Direct Embedded SLAM<br><a href='http://arxiv.org/pdf/2607.16897'>论文</a></td><td>GLidE-SLAM 是一种面向嵌入式设备的单目混合视觉 SLAM 系统,通过将直接跟踪与间接建图在架构上解耦,有效解决了资源受限平台上跟踪与建图的算力竞争问题。系统利用 GPU 加速的图像对齐操作进行仅位姿估计的直接跟踪,避免深度优化和地图点创建,从而将高并行度工作负载卸载到 GPU,释放 CPU 资源用于后端的间接建图和地图维护。

◆ 架构创新:采用间接-直接混合的解耦设计,直接跟踪处理中间帧位姿估计,间接流水线专门负责地图扩展和全局一致性,实现跟踪与建图的并行高效协同。

◆ GPU 卸载策略:利用高度并行的图像对齐操作进行位姿跟踪,降低 CPU 负载,使后端任务能获得更多计算资源。

◆ 跨平台可移植性:使用厂商无关的 OpenGL ES 3.1 计算着色器实现直接跟踪器,无需 CUDA 支持即可部署在更广泛的商用嵌入式平台上。

◆ 首创性工作:据作者所知,这是首个通过计算着色器在嵌入式级设备上实现的完整直接光度位姿估计器。

◆ 性能优势:在目标平台上实现相比纯 CPU 基线最高 9 倍的帧率提升,同时保持轨迹精度,提升了在资源受限硬件上的实际部署可行性。</td></tr>
<tr><td>2026-07-16</td><td>Immediate 3D Gaussian Splat Reconstruction of Unordered Input with Global Consistency<br><a href='http://arxiv.org/pdf/2607.14481'>论文</a></td><td>这篇论文提出了首个针对3D高斯泼溅(3DGS)重建的即时反馈方案,能够在无序图像输入下提供全局一致的重建结果。传统3DGS方法依赖有序序列或离线处理,而该方法突破了输入顺序的限制,实现了捕获过程中的实时可视化反馈。

◆ 利用视觉位置识别模型和共视性图(covisibility graph),提出了一种适用于无序序列的快速匹配方法,并能高效筛选高连接度关键帧,即使在有序序列下也能提升重建质量。

◆ 通过GPU优化和高斯基元(primitive)的精放置策略,实现了快速局部重建,在保持视觉质量的同时满足即时反馈的需求。

◆ 基于共视性图提出新颖的聚类(cluster-based)回环闭合方法,无需依赖顺序输入即可高效处理大范围场景中的回环问题,确保全局一致性。

◆ 引入渐进式层级结构(progressive hierarchy),使方法能够高效扩展到包含数千张图像的大规模环境,同时不牺牲计算效率。该方法在多个数据集上验证了其在无序输入下实现高质量即时3DGS重建的可行性。</td></tr>
<tr><td>2026-07-15</td><td>Improving Map Consistency in Graph-Based LiDAR SLAM Through Information-Aware Odometry and Retroactive Loop Closure<br><a href='http://arxiv.org/pdf/2607.13516'>论文</a></td><td>该论文针对图优化LiDAR SLAM中轨迹精度高但地图几何一致性差的痛点，提出了一套系统性的改进方案。

◆ 提出基于几何依赖的信息矩阵估计框架，为ICP里程计约束提供原理化的权重分配，从而提升位姿图优化的可靠性。

◆ 设计分层回环检测模块，将位置识别与几何配准解耦，增强回环检测的鲁棒性。

◆ 提出回溯式回环闭合模块，利用已优化位姿图恢复先前被遗漏的回环约束，进一步修正局部偏差。

◆ 建立专门评估重访位置地图一致性的评测协议，弥补现有方法在局部几何质量评价方面的不足。

实验在多个公开数据集上的结果表明，该方法在保持全局轨迹精度与现有先进方法相当甚至更优的同时，显著提升了重访区域的局部地图几何一致性，验证了不确定性感知里程计与几何引导回环精化耦合的有效性。</td></tr>
<tr><td>2026-07-15</td><td>Breaking Déjà Vu: Independent Auditing of Visual Place Recognition through Vision-Language Reasoning<br><a href='http://arxiv.org/pdf/2607.12818'>论文</a></td><td>本文针对视觉位置识别（VPR）在实际部署中依赖固定阈值、难以适应环境变化的核心痛点，提出了一种基于视觉语言模型（VLM）的后检索独立审计框架。

传统VPR方法在闭环检测等安全关键场景中容易因固定阈值导致误匹配，进而污染SLAM估计的轨迹与地图，而本文方法在检索阶段后对候选匹配进行独立实例级验证。

该框架利用VLM对查询图像与候选图像进行联合推理判断，无需架构特定的置信度度量、数据集相关阈值或部署环境的先验知识，具备良好的通用性。

在六个基准数据集、五种SOTA VPR方法以及四种VLM上的广泛实验表明，该方法平均将recall@1提升13.6%，同时将误接受率降至12%，并保持精度高于95%、覆盖率高于75%。

核心创新点如下：

◆ 提出视觉位置识别审计（VPR Auditing）概念，将VLM作为独立的后检索验证器，实现查询与候选图像的联合语义推理。

◆ 设计无需架构特定置信度、无需数据集相关阈值、无需环境先验知识的通用验证机制，摆脱对部署调参的依赖。

◆ 在多数据集、多VPR方法、多VLM的组合实验中验证了框架的普适性，显著提升召回率的同时有效控制误匹配风险。</td></tr>
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
<tr><td>2026-07-17</td><td>NoDrift3R: Raymap-Guided Coupling for Drift-Robust Unposed Feed-Forward 3D Reconstruction<br><a href='http://arxiv.org/pdf/2607.07168'>论文</a> | <a href='https://xiangyu1sun.github.io/NoDrift3R-project-page/'>代码</a></td><td>该论文针对无位姿前馈三维高斯溅射在长序列中因位姿漂移导致重建质量退化的问题，提出了一种几何与外观显式协同的新框架。作者识别出位姿累积漂移是制约性能的主要瓶颈，并指出SfM伪真值引入传感器噪声、纯渲染监督易陷入局部最优等矛盾。

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
<tr><td>2026-07-29</td><td>VidMap: Exploiting Temporal Structure for Video-Based Structure-from-Motion<br><a href='http://arxiv.org/pdf/2607.27194'>论文</a> | <a href='https://github.com/cvg/vidmap'>代码</a></td><td>本文针对无约束视频的相机标定与度量位姿恢复问题，提出VidMap系统，旨在弥合SLAM与SfM之间的差距。传统SLAM受限于因果增量特性，对初始化和瞬态失败敏感，且通常需要已知相机标定；传统SfM虽支持全局优化但缺乏对时间顺序的利用。作者通过结合SLAM的强序列约束与离线SfM的全局优化灵活性，实现了对任意长视频、无标定输入的度量三维重建。

◆结合SLAM的序列约束与离线SfM的全局优化能力，支持无标定长视频的度量重建。
◆引入宽基线稠密图像匹配技术，提升特征关联的鲁棒性。
◆将时间顺序信息作为一等公民用于可靠回环检测。
◆在全局优化中融合单目度量深度先验，提高重建精度。
◆在极端运动与视觉对称等挑战性场景下，显著优于现有SLAM和SfM方法。</td></tr>
<tr><td>2026-07-29</td><td>Robust RPC Bundle Adjustment for Multi-Date Satellite Imagery with Season-Invariant Correspondences<br><a href='http://arxiv.org/pdf/2607.26973'>论文</a></td><td>本文针对多时相卫星影像在季节、光照和地表覆盖变化下传统特征匹配不可靠的问题，提出了一种面向外观感知的RPC精化流程。该方法将学习型局部特征匹配与全局图像描述符相结合，前者用于提取跨季节稳定的同名点，后者用于筛选视觉兼容的影像对，从而在减少冗余和易错匹配的同时保持匹配图的连通性。实验基于WorldView-3多季节影像数据，在39至42视图的集合上进行验证。

核心创新点如下：

◆ 提出外观感知的RPC精化流程，将学习型局部特征匹配与全局图像描述符协同用于多时相卫星影像处理

◆ 利用全局描述符预先筛选视觉兼容的影像对，显著降低冗余匹配和错误匹配风险

◆ 在GCP-free相对RPC精化中取得更优的几何一致性误差，同时大幅缩短匹配时间

◆ 提升了对跨季节外观变化的鲁棒性，使多日期卫星影像能够得到更有效的利用...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-05-29</td><td>MAPRPose: Mask-Aware Proposal and Amodal Refinement for Multi-Object 6D Pose Estimation<br><a href='http://arxiv.org/pdf/2604.20650'>论文</a></td><td>本文针对杂乱场景中严重遮挡和噪声导致的6D姿态估计难题，提出了MAPRPose两阶段框架。
◆在姿态提案阶段，将2D对应关系提升至3D空间建立可靠关键点匹配，基于对应级评分生成几何一致的姿态假设选出Top-K候选。
◆在细化阶段引入AMPR模块，通过重建完整物体几何与动态调整ROI，有效缓解重度遮挡下的定位误差和空间错位。
◆设计GPU加速的RGB-XYZ重投影机制，在张量化渲染比较管线中实现单次前向传播同步细化所有姿态假设。
该方法在BOP基准上取得76.5%的最优平均召回率，精度超越FoundationPose 3.1%，且多目标推理速度提升43倍。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='obstacle-avoidance'>Obstacle Avoidance</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-07-28</td><td>Macroscopic wall pressure and microscopic contact load in crowds without egress: social-group cohesion and boundary buffering<br><a href='http://arxiv.org/pdf/2607.25780'>论文</a></td><td>本论文针对无疏散密集场景下人群机械安全风险评估的难题，耦合弹性转向模型（ERM）与社会力模型（SFM），提出以宏观墙线压力P_wall与微观单代理最大碰撞冲量δp_max作为双重风险量化指标。

◆ 揭示了群体凝聚力γg与墙体缓冲γw对风险的复杂调控规律：两者通常通过保留主体内部群体降低P_wall，但在中等凝聚力下大群体存在高δp_max的危险窗口，而γg趋近1时局部配对抑制簇生长并将动能从相对运动转为质心运动。

◆ 发现了耦合动力学中的P-p权衡关系：SFM推挤与滑移显著放大微观冲击，主动驱动则通过近壁聚集提升宏观墙压，二者无法同时降低。

◆ 通过有限尺度分析识别出两个相变边界：独立代理诱导的γw=0.5处不连续相变（磁化率跳跃），...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-28</td><td>SGTP: Sampling-based Game-Theoretic Planning for Real-Time Multi-Vehicle Autonomous Racing<br><a href='http://arxiv.org/pdf/2607.25388'>论文</a> | <a href='https://sgtp-racing.github.io/'>代码</a></td><td>本文针对多车自主竞速中实时规划多样化竞争行为的难题,提出了基于采样的博弈论规划框架SGTP,核心创新如下:

◆ 将博弈论推理与GPU加速的控制序列采样及动力学推演相结合,实现了高效的多车交互决策,在多次迭代求解中平均计算时间仅0.095秒。

◆ 设计了博弈感知成本函数对采样轨迹进行排序,能够捕捉车辆间的竞争交互,生成多样化的竞速策略,解决了战略多样性与计算效率之间的平衡难题。

◆ 通过显式执行赛道边界和动态避碰约束进行可行性筛选,确保不同竞速策略之间过渡的安全性与可靠性。

◆ 在高交互竞速场景中实现95.24%的胜率和99.35%的任务完成率,并成功扩展至最多10辆车的规模化场景,展现出良好的实时性与可扩展性。

◆ 开放了代码与多智能体自主竞速算法基准测试平台,为该领域未来研究提供了重要基础设施。</td></tr>
<tr><td>2026-07-27</td><td>Hybrid Artificial Potential Fields and Spatio-Temporal Transformers for Real-Time AUV Path Planning<br><a href='http://arxiv.org/pdf/2607.25056'>论文</a></td><td>本文针对自主水下航行器(AUV)在复杂非结构化环境中的实时路径规划问题，对十三种算法进行了系统性比较评估。研究覆盖了从经典图搜索方法(A*、Dijkstra)、基于采样的方法(RRT*)、元启发式算法(PSO、GA、ACO、BCO)到学习架构的完整算法谱系，并在高分辨率水下地形图上通过五种导航场景进行了验证。

◆提出了APF与时空Transformer相融合的混合路径规划框架，将势场法的反应式避障能力与Transformer的全局时空建模优势有机结合。

◆建立了涵盖四类范式共十三种算法的统一对比基准，从路径最优性、避障性能与计算开销三个维度揭示了各类方法的权衡关系。

◆在五种水下场景中实现100%任务完成率，同时取得最短平均路径长度(943.15单位)、低碰撞率(0.031)与高效计算时间(0.96秒)的综合最优平衡。

实验表明，经典方法虽保证无碰撞但路径冗长且延迟高，单纯学习模型需依赖回退机制，元启发式方法则产生不适用的复杂轨迹。Hybrid APF + ST-Transformer框架被推荐为资源受限水下系统中实时AUV导航的优选方案。</td></tr>
<tr><td>2026-07-27</td><td>Learning Adaptive Multi-Task Guidance, Navigation, and Control via Hypernetworks<br><a href='http://arxiv.org/pdf/2607.24292'>论文</a></td><td>本文针对轨道自由飞行机器人提出HYPER-GNC多任务强化学习框架,旨在解决传统为每个任务单独训练策略导致的架构脆弱性和灵活性不足问题。核心思路是利用超网络将物理信息驱动的任务嵌入映射到共享actor-critic策略的权重,从而用一个紧凑控制器同时掌握速度跟踪、对接、巡检和带避障的导航四类GNC任务。该连续嵌入空间使控制器在部署时无需重训练即可泛化到新型任务配置,并在大惯性扰动与外部外力下保持稳定。实验表明其样本效率与单任务专家策略相当,且成功在物理卫星仿真器上完成全部任务的仿真到实物迁移。

◆ 提出基于超网络的多任务GNC统一框架,用一个紧凑控制器替代多个任务专属策略,显著降低架构复杂度和资源开销。
◆ 设计物理信息驱动的连续任务嵌入空间,支持零样本泛化至新任务配置,无需重训练即可适应任务演变。
◆ 兼顾样本效率与鲁棒性,在显著惯性扰动和外部外力下保持稳定控制性能。
◆ 完成从仿真到物理卫星仿真器的全任务迁移验证,有效弥合sim-to-real差距。</td></tr>
<tr><td>2026-07-27</td><td>SILICA: Repurposing Diffusion Priors for Joint Glass Segmentation and Depth Estimation<br><a href='http://arxiv.org/pdf/2607.24249'>论文</a></td><td>本文提出SILICA框架，针对标准深度传感器在透明表面失效这一难题，创新性地复用文本到图像扩散模型的丰富先验，实现玻璃分割与玻璃感知深度的联合预测。该方法通过两个任务间的互信息交换建立稳健的空间层次结构，完全摆脱对真实玻璃深度标注的依赖，并利用预测的分割掩码过滤标准传感器中的错误深度点，从而恢复精确的度量级玻璃深度信息，支撑下游三维建图与自主避障应用。

◆首次将扩散模型先验知识迁移至透明表面感知任务，赋予模型出色的零样本跨环境泛化能力。
◆设计分割与深度联合预测的互信息交换机制，无需配对的真实玻璃深度标注即可完成训练。
◆构建Mirage 18k新数据集，在多个未见环境中较现有最优方法性能提升近20%，树立透明表面感知新基准。</td></tr>
<tr><td>2026-07-27</td><td>A Nonlinear CTH-Based Adaptive Cruise Controller With Safety and String Stability Guarantees<br><a href='http://arxiv.org/pdf/2607.24228'>论文</a></td><td>本文针对异构车辆队列的纵向控制问题，提出了一种基于恒定时距（CTH）策略的非线性自适应巡航控制器。该控制器通过引入速度相关的非线性增益和饱和型非线性环节，在保证时距策略防碰撞特性的同时，限制了车辆速度和加速度的边界。

◆ 设计了适用于异构车队、保证安全与队列稳定性的非线性自适应巡航控制器，结合速度依赖增益与饱和函数实现速度与加速度的有界性。

◆ 通过构造合适的间距误差变量，获得显式的非线性误差动力学方程，从而可直接分析闭环系统，并证明无碰撞区域为正不变集。

◆ 完全基于非线性闭环动力学分析队列稳定性，避免了线性化或频域方法的局限性。

◆ 推导出针对领航车外部输入、扰动及初始条件偏差的 Lp 串稳定性（1≤p≤∞）充分条件，扩展了非线性串稳定性分析框架。</td></tr>
<tr><td>2026-07-23</td><td>Grasp, Handover, Rotate: Bimanual Object Reorientation via Compositional Diffusion and Energy-Based Optimization<br><a href='http://arxiv.org/pdf/2607.21341'>论文</a></td><td>本文针对双臂物体重定向任务（抓取、交接、重抓取与放置）中多目标优化困难的问题，提出了BiCompoDiff框架，核心思想是将预训练的抓取扩散模型与双臂规划能量模型（EBM）进行组合式联合优化。方法在反向扩散过程中注入梯度引导，同时满足避碰、轨迹平滑、可交接性、重抓取安全等多重约束，并结合退火MCMC采样在复合能量景观上精细化抓取姿态。实验表明该方法在多种仿真家庭场景中比强基线提升超过20%的成功率，轨迹平滑度提升达37%，并通过真实机器人验证了有效的仿真到真机迁移能力。

◆ 提出扩散模型与能量模型组合优化的统一框架，将抓取选择、交接、重抓取与运动规划联合求解，避免了分阶段方法的次优问题。
◆ 在反向扩散采样过程中引入基于EBM的梯度引导，将碰撞避免、可微逆运动学驱动的轨迹平滑性、交接可行性与重抓取安全等约束融入生成过程。
◆ 采用退火MCMC采样在复合能量景观上对抓取姿态进行后优化，进一步提升解的质量与任务成功率。
◆ 在仿真与真实场景中均验证了方法在多约束双臂操作任务中的优越性和鲁棒性，显著优于传统采样基线方法。</td></tr>
<tr><td>2026-07-22</td><td>Self-Supervised Bio-Inspired Robotic Trajectory Planning with Obstacle Avoidance<br><a href='http://arxiv.org/pdf/2607.20743'>论文</a></td><td>本论文针对机器人轨迹规划中传统采样方法计算成本高、现有学习方法样本效率低或泛化能力差的问题，提出了一种基于神经启发的自监督学习框架。该框架利用前向模型和逆模型作为内部监督信号，无需专家演示即可在含障碍物的环境中学习生成无碰撞高效轨迹。实验验证了该方法的可行性，但同时发现规划器存在过度利用前向-逆模型学习信号的倾向。针对这一问题，作者进一步提出了多种改进的训练策略和缓解方案，并进行了系统评估。

◆ 创新点一：提出生物启发的自监督轨迹规划框架，以前向模型与逆模型作为内部监督机制，无需专家演示或人工奖励函数。

◆ 创新点二：将该框架扩展至含障碍物的复杂环境，实现无碰撞轨迹的端到端学习。

◆ 创新点三：首次揭示了规划器对前向-逆模型学习信号的&quot;利用&quot;偏差问题，并系统分析其成因。

◆ 创新点四：提出多种补充训练机制和缓解策略，有效抑制学习信号被过度利用的倾向，提升规划质量与泛化能力。</td></tr>
<tr><td>2026-07-24</td><td>Towards Capability-Aware Traversability Navigation for Unstructured Environments<br><a href='http://arxiv.org/pdf/2607.20679'>论文</a></td><td>这篇论文针对非结构化环境中可通行性评估高度依赖机器人本体的问题，提出了能力感知可通行性（CAT）框架，将物理能力约束直接编码进空间特征表示，而非仅依赖后置轨迹过滤实现跨形态迁移。

◆ 设计了基于真实物理轨迹的交互式标注流程，生成密集监督掩码，使训练数据本身具备本体感知特性。

◆ 引入空间自适应归一化（SPADE）模块，将机器人特定的通行性向量调制到语义地形图中，实现形态条件下的特征融合。

◆ 提出了按机器人分组的原型（per-robot prototypes）机制，使模型能够清晰区分不同平台的能力边界。

实验结果表明，CAT在物理执行轨迹上AUROC提升11.0%，在人工标注数据上AUPRC提升15.8%，消融实验验证了空间条件与本体原型的关键作用。该方法已成功部署于四足机器人和轮式滑移转向平台，在嵌入式硬件上以4.8Hz实时运行，展现出本体感知的避障能力。</td></tr>
<tr><td>2026-07-22</td><td>Distributed Motion Planning with Safety Guarantees for Self-Reconfiguring Robotic Boats<br><a href='http://arxiv.org/pdf/2607.20352'>论文</a></td><td>本文针对水面自重构机器人多智能体形状组装任务中的安全运动规划问题，提出了一种融合分布式模型预测控制（MPC）与控制屏障函数（CBF）的混合框架。该方法将MPC的预测优化能力与CBF的形式化安全保障相结合，通过仿真与实验验证了框架的有效性。

◆提出结合分布式MPC与CBF的混合框架，兼顾多智能体的全局协调规划与实时安全约束修正。

◆采用基于ADMM的分布式MPC方案，通过局部优化与邻居信息交换实现协调轨迹生成，能有效缓解局部极小值问题。

◆在MPC解上叠加分布式CBF滤波器，对智能体间碰撞约束进行实时修正，即使底层优化问题非凸也能提供严格安全保证。

◆通过最多25个智能体的仿真与4台实物机器人实验，验证了方法在形状组装与重构中的有效性与可扩展性。</td></tr>
<tr><td>2026-07-22</td><td>Remote ID Spoofing-Aware Trajectory Planning for Small Unmanned Aerial Systems<br><a href='http://arxiv.org/pdf/2607.19650'>论文</a></td><td>该论文针对小型无人机系统在远程识别(RID)位置欺骗攻击下的安全问题，提出了一种去中心化的欺骗感知轨迹规划框架。传统规划器通常默认RID广播信息可信，在欺骗发生时易引发间隔丧失和空中相撞风险，而本文方法将RID信息视为不可验证数据，利用邻居飞行器的接收信号强度(RSS)进行欺骗检测和欺骗源概率定位。

◆ 基于物理层RSS测量的RID欺骗检测与欺骗源概率定位方法，将广播可信度评估嵌入规划前端。

◆ 采用机会约束(chance-constrained)公式将定位不确定性转化为风险有界的不安全区域，实现鲁棒碰撞规避。

◆ 将上述风险模型集成到基于马尔可夫决策过程(MDP)的单智能体去中心化规划器中，兼顾实时性、任务目标和可扩展性。

◆ 在多机包裹配送仿真场景中验证，相较于假设RID数据可信的规划器，近空中相撞事件显著降低，同时保持适合实时执行的计算效率。</td></tr>
<tr><td>2026-07-21</td><td>Milo, a Fully Autonomous Indoor/Outdoor Robotic Guide Dog<br><a href='http://arxiv.org/pdf/2607.19530'>论文</a></td><td>本文提出Milo,一种面向盲人及低视力人群的自主室内外导盲机器人平台,旨在以低成本替代昂贵的传统导盲犬。针对现有机器人导盲方案依赖先验三维地图、外部计算或对使用者感知不足的问题,该系统基于改装Unitree Go2四足机器人,集成感知与导航全栈技术,在完全未知环境中实现自主避障与行人规避,并大幅降低使用门槛。

◆ 首次提出完全开源、低成本(约2000美元)的室内外通用导盲机器人平台,无需任何环境先验信息,所有计算均在机载完成,具备真正可部署的自主性。

◆ 感知层融合体素建图与地面、障碍物、行人检测,能够在复杂动态环境中鲁棒识别可通行区域与潜在危险。

◆ 导航层采用基于自建鸟瞰图仿真器训练的避障策略,实现了比传统代价地图方法更平滑、碰撞更少的路径规划表现。

◆ 通过真实室内外障碍场景对比实验,验证了系统在减少使用者碰撞次数方面的显著优势。

◆ 公开全部硬件改装方案与软件栈,极大降低盲人社区获取导盲助力的门槛,推动该领域普惠发展。</td></tr>
<tr><td>2026-07-21</td><td>Emergent Autonomous Drifting for Collision Avoidance in Real-World Winter Driving Scenarios<br><a href='http://arxiv.org/pdf/2607.19484'>论文</a></td><td>本文针对真实冬季驾驶场景,研究高侧滑漂移作为主动避撞策略的可行性与最优性。研究者设计了一种具备漂移能力的非线性模型预测控制(MPC)系统,其控制目标基于真实交通事故伤亡数据构建,涵盖车辆偏离车道和迎面来车两种典型危险场景,并在高精度仿真器中完成了部署验证。

◆ 提出基于真实碰撞伤亡数据驱动的漂移能力非线性MPC控制框架,首次将漂移控制从人造测试场景拓展到真实冬季驾驶安全应用场景。

◆ 控制器具备自主激发与维持漂移的能力,能够根据实时状态在冰面打滑和迎面会车等突发事件下自然进入漂移模式,无需预先规划。

◆ 通过与电子稳定控制系统(ESC)对比,揭示了漂移控制以可控性换取稳定性的权衡机制,证明在特定危险工况下漂移能够实现更精确的避撞机动。

◆ 基于蒙特卡洛随机冰面仿真实验,定量验证了所提控制器在多个速度区间具有更低的横向车道偏差,漂移行为主要在高车速下涌现。</td></tr>
<tr><td>2026-07-21</td><td>STL-GCS: A Planner-Controller Framework for Signal Temporal Logic via Graphs of Time-varying Convex Sets<br><a href='http://arxiv.org/pdf/2607.19196'>论文</a></td><td>本文提出STL-GCS，一种针对信号时序逻辑（STL）规范定义在凸谓词上的统一轨迹规划与控制框架。该方法将STL任务编码为配置空间中的时变凸集，并提升到时间-配置联合空间，与图凸集（GCS）框架相结合，形成基于凸时空集合的最短路径规划问题。轨迹采用B样条参数化，从而能够在连续时间上强制执行STL满足、避障以及平滑性约束。在控制层，复用规划阶段的时变集合设计反馈控制器，使系统在存在跟踪误差和模型失配时仍能优先保证STL规范的满足。该方法在仿真以及空间机器人真实平台上均得到了实验验证。

◆创新点：将STL规范编码为时变凸集，通过前向不变性保证规范满足并具备规定的鲁棒裕度。
◆创新点：在时间-配置联合空间中利用GCS框架构建凸集图上的最短路径规划问题。
◆创新点：采用B样条参数化轨迹，实现STL约束、避障与平滑性的连续时间统一处理。
◆创新点：控制层与规划层共享时变集合结构，使反馈跟踪在扰动下优先保障STL满足。</td></tr>
<tr><td>2026-07-21</td><td>End-to-end Conditional Diffusion for Realistic and Controllable Visual Traffic Scenario Generation<br><a href='http://arxiv.org/pdf/2607.18637'>论文</a></td><td>本文针对自动驾驶闭环测试中交通场景生成面临的真实性与可控性难以兼顾的问题,提出了端到端条件扩散框架E2E-CDiff。该方法以前视视觉观测为条件,联合去噪未来运动状态与可执行的低层控制信号,实现统一的状态-动作生成,有效缓解了传统&quot;轨迹预测+控制器&quot;两阶段流水线中存在的规划-控制不匹配问题。通过引入可微分引导机制,模型能够灵活调节车速、约束可行驶区域,并支持避撞或主动碰撞等多种行为模式,从而同时支持自然驾驶与安全关键场景的生成。

◆ 首次提出端到端条件扩散框架,以前视图像为条件联合去噪车辆未来运动状态与可执行低层控制,实现统一的状态-动作生成,消除两阶段方法中的规划-控制不匹配。

◆ 设计可微分引导机制,支持速度调节、可行驶区域约束以及避撞/碰撞趋向等多模式行为控制,实现自然场景与安全关键场景的统一生成。

◆ 在Bench2Drive基准上实现可控性与真实性的良好平衡,其碰撞引导变体可有效生成对多种自动驾驶系统具有挑战性的交互场景。

◆ 框架同时具备作为学习型自车规划器的竞争力,验证了端到端状态-动作扩散范式在不同任务中的通用性。</td></tr>
<tr><td>2026-07-23</td><td>GeoWorldAD: Geometry World Action Model for Autonomous Driving<br><a href='http://arxiv.org/pdf/2607.17521'>论文</a></td><td>本文提出GeoWorldAD，一种基于几何世界模型的自动驾驶动作决策方法，旨在解决现有视觉/视频-动作模型缺乏显式3D几何约束和未来感知空间引导的问题。

◆核心创新在于将轨迹规划锚定于以自车坐标系对齐的3D空间，利用显式几何信息提供安全规划所需的空间约束。

◆方法通过潜在未来几何token预测短时域场景演化，使模型能够预判周围智能体和自车可用空间的未来变化，从而在避免过度保守决策的同时保障安全性。

◆设计了渐进式多尺度几何聚合与迭代轨迹精修机制，高效融合当前几何与潜在未来几何信息。

◆在NAVSIM v1和v2基准上取得最优性能，验证了显式3D几何建模与未来世界建模对安全高效自动驾驶的有效性。</td></tr>
<tr><td>2026-07-19</td><td>An Update to the Level Set Theorems in Hamilton-Jacobi Reachability Analysis<br><a href='http://arxiv.org/pdf/2607.17435'>论文</a></td><td>本文针对Hamilton-Jacobi可达性分析（HJR）中的水平集定理进行了重要的技术更新。HJR是处理不确定性下安全关键系统控制的重要框架，其理论基础源于Hamilton-Jacobi偏微分方程所求解的值函数。水平集定理能够将值函数与定性目标（如目标到达或避障）的满足性进行关联解释，是控制器综合的关键工具。本文的核心贡献在于揭示并补充了原有水平集定理成立所需的额外条件，完善了相关理论体系。◆明确了原有水平集定理在应用中被忽略或缺失的附加判定准则，使定理的适用条件更加严格完整。◆通过补充这些技术条件，提升了HJR框架在目标到达和避障问题中的理论可靠性，为相关安全控制器的设计提供了更坚实的数学基础。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-07-24</td><td>ACME: A Multi-Cultural, Multi-Embodiment Social-Navigation Dataset<br><a href='http://arxiv.org/pdf/2607.21964'>论文</a></td><td>该论文提出了ACME数据集，旨在解决现有社交导航数据集在文化、地理和人机交互多样性方面的不足。研究团队在5个国家的8个地点使用7种机器人平台开展大规模数据采集，最终获得29.35小时的机载数据和43.5小时的上方行人追踪数据。

◆ 首次构建跨文化、跨地域的社交导航数据集，覆盖5国8地，捕捉不同文化背景下的社会行为差异。

◆ 采用7种不同机器人平台实现多具身数据采集，显著提升数据集在硬件层面的多样性。

◆ 引入基于语音的显式机器人-人群交互机制，聚焦目标驱动的复杂社交场景，填补现有数据空白。

◆ 提供3D/2D场景特征、里程计、交互信息及人工标注的行人轨迹，并同时支持人类可读与原始二进制格式，便于多任务研究。

◆ 实验表明，ACME数据集相比现有数据集涵盖更具挑战性的场景和更广泛的行人行为分布。</td></tr>
<tr><td>2026-07-23</td><td>DAPM: UAV Monocular Depth Estimation from Any Height, Pitch, Roll and FOV<br><a href='http://arxiv.org/pdf/2607.21438'>论文</a> | <a href='https://github.com/ThisIsLT/DAPM'>代码</a></td><td>本文针对无人机(UAV)在动态相机姿态下的单目深度估计难题,提出了DAPM框架,首次实现了在任意高度、俯仰、滚转和视场角条件下同时估计相机姿态与深度。作者通过理论分析建立了无人机视角与视距之间的几何对应关系,为后续模块设计提供了数学基础。

◆构建了基于地面参考的无人机视角定量表征理论,推导出视角与视距的几何对应关系,解决了现有方法在多样化空中视角下泛化能力不足的问题。

◆提出理想地面深度(IGD)模块,利用视角与视距的衍生几何关系实现密集的相机姿态监督,并增强深度特征提取能力。

◆设计渐进式量化分箱(PQB)模块,通过渐进监督和分层量化分箱策略,由粗到细实现复杂空中场景下的鲁棒深度估计。

◆构建了UAPD数据集,涵盖连续分布的姿态参数,弥补了现有数据集在无人机视角多样性方面的不足。

在UAPD数据集上的实验表明,DAPM在深度和相机姿态估计指标上均达到最先进水平,验证了各模块设计的有效性。</td></tr>
<tr><td>2026-07-23</td><td>VoLN: Vision-Only Long-Horizon Navigation---Paradigm, Benchmark, and Method<br><a href='http://arxiv.org/pdf/2607.21400'>论文</a> | <a href='https://admire-ljb.github.io/VoLN-UAV/'>代码</a></td><td>本文提出了一种全新的导航范式Vision-Only Long-Horizon Navigation (VoLN),将传统视觉语言导航(VLN)中由外部指令提供的路线相关信息,转化为由智能体在线检测和解读的场景内局部可观测线索,使其更贴近真实无GPS开放环境下的部署需求。

◆ 提出VoLN新范式:以目标视图指定目的地,路线信息仅通过场景内局部可观测信标获取,智能体需在线检测、解释并选择信标,摆脱对外部指令空间先验的依赖。

◆ 构建VoLN-UAV基准:包含7,210个航拍导航任务,融合长视野目标飞行、连续三维运动、大视角变化及上下文相关信标选择,覆盖五种测试环境。

◆ 设计VoLN-MLLM基线方法:将自监督视觉特征与结构化语义空间对齐,基于观测历史、目标视图、检索的视觉语义token及本体感知预测短视野航点段。

在Test-Unseen分割上,Easy、Normal、Hard难度成功率分别为7.4%、4.5%和1.8%,初步验证了VoLN的可行性,同时揭示了长视野证据整合、跨视角目标匹配及闭环稳定性等核心挑战。</td></tr>
<tr><td>2026-07-22</td><td>Socially Consistent Multi-Robot Navigation Using Decoupled Planning and Trajectory Coordination<br><a href='http://arxiv.org/pdf/2607.20772'>论文</a></td><td>本文针对人机共存环境中的多机器人导航问题，提出了一种部分去中心化框架，将全局路径规划与轨迹协调解耦，以实现可预测且符合社会规范的多机器人运动。

◆ 在全局规划层面，提出了一种改进的A*算法，将宏观社会规范（如靠右行走、保持距离等）嵌入代价函数中，使生成的路径天然具有社会一致性。

◆ 各机器人将规划路径共享，协同构建一个&quot;社会路径图&quot;，强化路径一致性，并显著减少后续规划的计算开销。

◆ 在轨迹协调层面，利用社会约束路径的涌现结构，将多机器人冲突消解问题建模为混合整数凸优化问题（MICP），可高效计算无冲突轨迹。

◆ 该凸规划框架具备良好的可扩展性，能够支持大规模机器人编队以及动态任务分配场景。

实验表明，在路径规划阶段引入社会一致性约束，不仅能产出可预测且合规的机器人路径，还大幅简化了原本复杂的多机协调问题。</td></tr>
<tr><td>2026-07-27</td><td>GaussianSeed: Hierarchical Gaussian Seeding for High-Resolution 3D Occupancy Prediction<br><a href='http://arxiv.org/pdf/2607.20071'>论文</a> | <a href='https://github.com/Athameral/GUSD'>代码</a></td><td>该论文针对以视觉为中心的3D占据预测在高分辨率下计算成本过高的问题，提出了GaussianSeed框架。◆提出渐进式多尺度高斯占据预测框架，将高斯基元组织成由粗到细的层次结构，有效绕开了密集表征的内存瓶颈，实现了0.1米空间分辨率下的实时推理能力。◆构建了TJScenes全景六相机占据数据集，提供0.1米精细标注，可用于高分辨率几何感知的全面评估。在Occ3D-nuScenes和TJScenes上的大量实验表明，GaussianSeed在所有评估方法中延迟最低，同时保持极具竞争力的精度，推进了高分辨率3D占据预测的效率与质量前沿。该工作的核心价值在于为自动驾驶和机器人导航提供了一种高效且高质量的密集场景表征新范式。</td></tr>
<tr><td>2026-07-22</td><td>Unified Prediction and Planning via Conflict-Aware Disjoint Parameter Training<br><a href='http://arxiv.org/pdf/2607.19971'>论文</a></td><td>本文针对拥挤环境中机器人导航的预测与规划耦合问题，提出了一种统一的紧凑模型框架。核心发现是当预测和规划任务共享参数时会出现&quot;技能冲突&quot;现象，即不同任务争夺相同权重导致模型无法充分专精化。

◆ 提出了技能冲突概念，揭示了统一模型中预测与规划任务因参数重叠而产生的表征竞争问题。

◆ 设计了基于模型合并的分离参数训练框架DPT，通过分布式参数学习让各任务在合并前占据不同关键参数区域，从而保留各自核心能力。

◆ 采用稀疏合并策略，仅整合各任务最具影响力的参数而非全部参数，避免相邻特征干扰，提升表征效率。

◆ 验证了DPT可与多种现有合并方法并行兼容，在JRDB和JTA等标准人群导航基准上均取得优越性能，证明了其通用性与有效性。</td></tr>
<tr><td>2026-07-29</td><td>EA-Nav: Learning Safe Visual Navigation Policies with Embodiment Awareness<br><a href='http://arxiv.org/pdf/2607.19880'>论文</a></td><td>EA-Nav提出了一种基于模仿学习的跨具身视觉导航框架，旨在解决不同形态智能体因相同视觉观测对应不同动作而导致的动作歧义问题。该方法采用模块化的多阶段设计，在预训练阶段从互联网视频中构建跨具身导航数据集，并将具身几何信息作为条件令牌注入模型，从而有效降低动作预测的歧义性。在微调阶段，作者设计了基于解耦架构的多模态信息注入机制，通过轨迹增广策略生成高风险样本，分别训练空间感知与风险感知修正模块，使模型能够显式地融合具身几何信息以实现安全导航。

◆ 从互联网视频中构建跨具身导航数据集，并引入具身几何作为条件令牌，缓解了相同观测下动作歧义的问题。

◆ 提出基于解耦架构的多模态信息注入机制，将视觉、几何等异构信息分别处理后再融合，增强策略对不同具身的适应性。

◆ 设计轨迹增广策略生成高风险样本，分别训练空间感知与风险感知修正子模块，将具身几何显式融入到安全导航决策中。</td></tr>
<tr><td>2026-07-22</td><td>SOPD-SocialNav: Selective On-Policy Distillation for Vision-Language Social Navigation<br><a href='http://arxiv.org/pdf/2607.19850'>论文</a></td><td>该论文针对视觉语言模型在社交机器人导航中部署困难的核心矛盾,提出了一种选择性在线策略蒸馏方法SOPD-SocialNav,旨在将大型教师VLM的社交导航知识高效迁移到轻量级学生VLM中,既保证模型可部署性又保留社交推理能力。

◆ 提出基于熵的token选择机制,通过教师模型的不确定性识别具有社交语义价值的决策token,同时抑制来自低熵token(对应平凡导航状态)的梯度传播,从而实现有针对性的知识蒸馏。

◆ 设计温度控制的Jensen-Shannon散度目标函数,在被选中的token上对齐学生与教师的分布,使蒸馏过程更加稳定且符合社交导航任务的实际需求。

◆ 在SNEI和MUSON基准上的实验表明,SOPD在动作预测、感知一致性和推理一致性三个维度上均显著优于监督微调、离线蒸馏及标准在线蒸馏等基线方法。

◆ 通过在Scout Mini机器人上的真实部署验证,在对话和排队等典型社交场景中,蒸馏后的轻量模型能够生成更加符合社会规范的导航行为,证明了方法的实用性和有效性。</td></tr>
<tr><td>2026-07-22</td><td>Koopman Dreamer: Spectrally Constrained Latent Dynamics for Stable World-Model Imagination<br><a href='http://arxiv.org/pdf/2607.19719'>论文</a></td><td>Koopman Dreamer将Koopman算子理论融入Dreamer框架，提出一种谱约束的确定性潜在动力学核心，旨在解决长视野潜在轨迹想象中误差累积与模态持久性难以直接控制的问题。

◆ 采用二维旋转-缩放模块作为动力学骨架，通过有界半径显式约束阻尼、旋转和近周期模态。

◆ 结合线性与低秩双线性动作项建模全局与状态依赖控制效应，并以随机状态调制补充局部修正信息。

◆ 联合后验EMA教师目标、一步一致性、多步展开与开环观测预测进行训练，缓解后验训练与先验想象之间的分布不匹配。

◆ 推导出多步展开误差上界，分离谱放大、双线性交互、随机失配与建模残差各自的贡献，阐明误差衰减与长期信息保留之间的权衡。

◆ 在DeepMind Control Suite与UAV-LiDAR自主导航任务上的实验验证了模型在长视野潜在轨迹稳定性与闭环控制性能方面的优势。</td></tr>
<tr><td>2026-07-21</td><td>Eversion-based robots can enable safe access,steering and endoscopic imaging within the spinal subarachnoid space<br><a href='http://arxiv.org/pdf/2607.19274'>论文</a></td><td>该论文针对脊髓蛛网膜下腔内导航难题，提出一种直径2毫米的柔性外翻生长机器人平台，通过压力驱动的尖端外翻机制实现无摩擦扩展与转向，并集成微型内窥镜进行实时鞘内可视化。

◆采用外翻生长机制，将运动局限于远端尖端，显著减少部署体与组织的相对滑动，从根本上降低界面摩擦和剪切损伤风险。

◆结合计算建模、幻影体实验及完整人体尸体实验进行多层次机械验证，幻影实验中平均交互力较推送式降低65.2%，峰值力降低48%。

◆在人体尸体中实现从标准腰椎入路跨越多个椎体水平150毫米受控延伸，术后解剖未观察到硬脊膜或神经结构宏观损伤。

该研究首次在完整人类脊髓解剖中实现外翻机器人的机械表征与多模态验证，为未来鞘内干预技术奠定了量化和程序基础。</td></tr>
<tr><td>2026-07-21</td><td>NaviAIS: A Scenario-Level Vessel Trajectory Prediction Dataset withVectorized Lane Priors and the NaviLane Forecasting Framework<br><a href='http://arxiv.org/pdf/2607.18887'>论文</a></td><td>针对现有船舶轨迹预测数据集采样不统一、缺乏结构化航道信息的问题，本文提出了NaviAIS标准化场景级数据集与NaviLane预测框架两大贡献。NaviAIS将多船历史与未来轨迹组织在统一时间窗和局部坐标系下，并提供栅格化可航行地图、矢量化航道先验、航道图与结构化地图表示，弥补了公开AIS资源在环境感知与可复现性方面的不足。

◆ 贡献一：NaviAIS数据集，在统一时间窗口与局部坐标系下组织多船轨迹，融合矢量化航道先验与结构化地图，同时支持矢量化航道、多场景覆盖与开放访问。

◆ 贡献二：NaviLane预测框架，采用分层宏动作设计实现由粗到细的多模态轨迹生成。

◆ 提出轨迹-地图联合编码机制，构建统一的场景表征。

◆ 设计离散宏动作码本生成多模态候选轨迹，并结合残差细化模块提升局部几何与动力学一致性。

◆ 引入基于世界模型的后果感知评估器，对候选轨迹按交互风险与环境可行性进行排序。实验证明该框架在单模态与多模态设置下均优于代表性基线，验证了结构化航道先验、分层多模态生成与后果感知评估的有效性。</td></tr>
<tr><td>2026-07-21</td><td>Broken Gates: Re-evaluating Web Bot Defenses in the Age of LLM Agents<br><a href='http://arxiv.org/pdf/2607.18659'>论文</a></td><td>本文针对大语言模型驱动的浏览器智能体对Web安全的威胁，系统评估了现有机器人防御机制的有效性。研究覆盖了7种商业验证码求解服务与6种LLM智能体在hCaptcha、reCaptcha v2/v3及Cloudflare Turnstile上的对抗表现，涉及云端、自托管、AI辅助及浏览器扩展等多种部署形态。

◆ 证明交互式挑战型防御对商业求解服务几乎完全失效，后者以极低成本实现近乎100%的绕过率。

◆ 表明LLM智能体在配备专用求解模块时同样能高效击败各类验证码挑战。

◆ 通过细粒度交互轨迹分析，揭示非交互式防御（如reCaptcha v3）的韧性并不源于行为判别能力。

◆ 发现行为特征几乎相同的两个智能体在非交互式防御下结果截然不同，证实执行环境的真实性才是决定性因素。

◆ 指出当前非交互式防御的安全边界实际位于环境层，对机器人管理系统的设计与评估具有重要启示意义。</td></tr>
<tr><td>2026-07-20</td><td>Learning Adaptive Safety Margins for Visual Navigation<br><a href='http://arxiv.org/pdf/2607.18200'>论文</a></td><td>本文针对室内杂乱环境中固定安全裕度难以兼顾保守与激进这一痛点，提出了一种基于上下文条件的安全评论器，用于对扩散规划器生成的轨迹候选进行自适应排序与可靠筛选。该评论器将安全裕度分解为三个互补目标：包含净空预算惩罚与控制屏障函数残差的安全项、融合平滑度与安全门控绕行比惩罚的效率项，以及将学习预算锚定于实际ESDF净空的距离约束匹配项，从而在抑制绕路的同时避免近边捷径和裕度坍塌。训练阶段先在仿真中利用特权ESDF几何训练评论器，再通过两阶段师生蒸馏迁移为仅依赖RGB-D的感知版选择器。实验在HM3D与MP3D的PointGoal导航及跨数据集场景下取得了最高的成功率和SPL，并零样本部署到Unitree G1人形机器人，无需任务级调参。

◆ 提出上下文条件安全评论器，将自适应净空偏好分解为安全、效率与距离匹配三项耦合目标，缓解固定裕度在保守与激进之间的失衡。
◆ 设计安全门控绕行比惩罚与控制屏障函数残差联动机制，显式抑制近边捷径并防止裕度坍塌。
◆ 采用特权ESDF到纯感知的两阶段师生蒸馏，使评论器在仅输入RGB-D时仍逼近特权几何的评判能力。
◆ 实现从仿真训练到Unitree G1人形机器人真实室内场景的零样本跨平台迁移，无需任务级参数调整。</td></tr>
<tr><td>2026-07-20</td><td>Distilling Global Traversability Priors for Image-based Affordance Prediction in Off-road Environments<br><a href='http://arxiv.org/pdf/2607.17984'>论文</a></td><td>该论文针对非结构化越野环境中自主导航存在的短视问题展开研究。传统基于LiDAR或相机构建的度量地图受限于深度感知范围,导致机器人在长距离任务中只能做出次优的局部决策。为解决这一瓶颈,作者提出直接从第一人称视角图像中提取长距离可通行性前沿,弥补了测距范围之外的信息缺失。

◆ 利用卫星影像为图像/位姿数据集计算全局可行导航路径,以此作为监督信号训练网络,显著减少了对大量人工演示数据的依赖。

◆ 将全局可通行性先验知识蒸馏到基于图像的affordance预测模型中,使机器人能够感知超视距的可通行区域。

◆ 在多个离线基准测试中,所提方法相比现有方法性能提升超过10%,并在真实环境实验中有效减少了人工干预次数。</td></tr>
<tr><td>2026-07-20</td><td>Lifelong Localization in Dynamic Indoor Environments Combining Odometry with Sparse Distance Sampling<br><a href='http://arxiv.org/pdf/2607.17852'>论文</a></td><td>本文针对动态室内环境下的机器人终身定位问题,提出了一种结合里程计与稀疏距离采样的鲁棒定位框架。该方法利用少量距离样本为机器人位置提供鲁棒先验,能够实时解决&quot;机器人绑架&quot;问题,并在长时间运行中与里程计融合以收敛到真实位姿。

◆ 基于真实环境数据建立动态障碍物模型,使定位框架能够适应环境变化,在静态和动态环境下均能保证收敛性。
◆ 通过稀疏距离采样(仅16个样本)实现了与全LiDAR SLAM相当的定位精度,大幅降低传感器成本、存储空间和传输带宽需求,同时保护隐私。
◆ 方法具有理论保证,在环境静态或动态变化已被正确学习时,均可证明收敛到机器人真实位姿。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-29</td><td>CinemaTraj: Composing Atomic Camera Trajectories for 3D Scenes with LLM Agents<br><a href='http://arxiv.org/pdf/2607.26910'>论文</a></td><td>本文针对从自然语言自动生成3D场景电影化相机轨迹的难题,提出了CinemaTraj框架。其核心思想是将相机轨迹规划重新定义为由语言引导的空间推理任务,结合LLM智能体与结构化3D场景图。

◆创新点一:将复杂提示分解为原子化电影运动序列(推拉、环绕、升降、摇移、俯仰、变焦、弧线运动),实现语义化轨迹组合。

◆创新点二:设计新颖的参数化轨迹表示,兼具电影表现力与可优化性,支持碰撞避免约束求解。

◆创新点三:以3D场景图作为结构化空间先验,为LLM智能体提供精确的几何与语义知识,解决现有方法缺乏3D空间感知的问题。

◆创新点四:同步生成与相机运动对齐的语音旁白和字幕,产出带解说的完整电影化视频。

在ScanNet++真实环境上的实验表明,该方法在提示对齐、轨迹质量与安全性指标上均优于现有方法。</td></tr>
<tr><td>2026-07-29</td><td>Risk-Aware Motion Planning with Learned Trajectory Primitives and Probabilistic Safety Assessment<br><a href='http://arxiv.org/pdf/2607.26802'>论文</a></td><td>本文提出了一种基于径向基函数网络(RBFN)的风险感知运动规划框架,用于城市自动驾驶场景下的安全高效规划。该方法利用RBFN学习最小加加速度的轨迹作为运动基元,有效压缩了模型预测控制(MPC)的搜索空间并保证动态一致性。框架结合...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-29</td><td>RLMM-Flow: A Flow-based Mobile Manipulation Framework with Latent-Space Reinforcement Learning<br><a href='http://arxiv.org/pdf/2607.26460'>论文</a></td><td>该论文提出RLMM-Flow框架，将基于流模型的专家动作先验与潜空间强化学习相结合，用于移动操作任务中全身动作块的生成。核心思路是先通过模仿学习预训练流策略以捕捉多模态运动先验，再冻结该策略，由潜空间引导网络优化初始噪声以产生更高价值的动作序列。实验表明该方法在任务成功率、避障能力和轨迹质量上显著优于纯模仿流策略和现有强化学习后训练基线，同时保留了流策略的快速推理优势。

创新点：
◆ 冻结预训练流策略，通过潜空间引导网络优化初始噪声，避免破坏已学习的多模态运动先验
◆ 动作空间评论家预热后联合训练潜空间评论家与潜空间演员，缓解高维潜空间优化不稳定问题
◆ 由粗到精的潜空间引导策略，从时段共享潜变量渐进扩展到全维度残差表示
◆ 将流模型生成能力与潜空间强化学习相结合，在保持快速推理的同时实现策略质量的超越演示分布提升...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-29</td><td>Fully distributed singularity-free prescribed-time stabilization of the continuous-time generalized adaptive Bellman-Ford algorithm<br><a href='http://arxiv.org/pdf/2607.26424'>论文</a></td><td>该论文针对连续时间广义自适应Bellman-Ford算法(GABF)在分布式最短路径问题中的应用展开研究。现有文献仅关注渐近稳定性,缺乏对收敛速度的分析,限制了其实际应用。为此,论文提出了两种控制策略,实现了GABF的预定时间稳定性,使算法能够在用户预先指定的时间内收敛到稳态值。

论文的核心创新点如下:

◆ 提出了两种新颖的控制策略,首次实现GABF算法的预定时间稳定化,收敛时间可由用户根据需求自由设定。

◆ 所设计的控制律具备完全分布式和避免奇异性的特点,不依赖全局信息,提升了算法的可扩展性和鲁棒性。

◆ 将所提方法应用于时间依赖最短路径问题,并结合真实机器人机械臂数据和基于学习的路径规划场景进行仿真验证,展示了算法的实际有效性和广泛适用性。</td></tr>
<tr><td>2026-07-28</td><td>MetaKoopman: Bayesian Meta-Learning of Koopman Operators for Modeling Structured Dynamics under Distribution Shifts<br><a href='http://arxiv.org/pdf/2607.26345'>论文</a> | <a href='https://mahmoud-selim.github.io/MetaKoopman/'>代码</a></td><td>本文针对分布偏移下的非线性动态建模难题,提出MetaKoopman框架,将贝叶斯元学习与Koopman算子理论相结合,实现通过线性潜表示对复杂非线性系统进行建模与预测。该方法在多个分布偏移场景中(包括冰雪路面等恶劣条件)均优于现有方法,在多步预测精度、不确定性校准和鲁棒性方面表现突出,并通过自动驾驶卡车和挂车系统的现场实验验证了其在极限牵引力场景下运动规划的有效性。

核心创新点如下:

◆ 提出基于Koopman算子的贝叶斯元学习框架MetaKoopman,通过线性潜空间表示实现对复杂非线性动力学的统一建模

◆ 在Koopman算子上学习矩阵正态-逆Wishart(MNIW)先验分布,实现基于近期轨迹片段的闭式贝叶斯更新,无需依赖梯度优化或反向传播

◆ 推导得到闭式后验预测分布,同时捕捉认知不确定性和偶然不确定性,为运动规划等下游任务提供可靠的置信估计

◆ 首次将该类方法在全尺寸自动驾驶卡车和挂车系统上进行了全面评估,涵盖多种冬季恶劣工况及极限操控场景,显著提升了分布偏移下的预测与规划鲁棒性...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-28</td><td>Beyond Zooming: Learning Multi-Tool Visual Reasoning for Ultra-High-Resolution Remote Sensing<br><a href='http://arxiv.org/pdf/2607.25993'>论文</a></td><td>本文针对超高分辨率遥感图像中证据稀疏且空间分散的难题,发现单一zoom-in工具仅能处理简单和中等难度任务,在需要全局搜索、多区域比较、路径规划等复杂任务上表现饱和。为此构建了大规模地理空间多工具视觉推理数据集GeoMTVR,包含13K超高分辨率视觉问答样本,涵盖交错推理轨迹、多样化视觉工具调用及返回的视觉观察。

◆ 构建GeoMTVR数据集,支持问题分解、工具选择、区域检查、目标级定位、辅助视觉推理及跨工具证据整合
◆ 提出工具注意力聚焦的强化学习算法,将优化集中在何时调用工具、选择何种工具、应用位置及如何解读输出等关键决策上
◆ 研发GeoLens多工具视觉推理模型,结合监督微调与强化学习

实验表明GeoLens在精度、证据定位和工具使用轨迹效率上均优于直接推理和单工具zoom-in基线方法。</td></tr>
<tr><td>2026-07-28</td><td>Schrödinger&#x27;s Cat: Probabilistic Representation and Prediction of Potential Scene Kinematics<br><a href='http://arxiv.org/pdf/2607.25984'>论文</a></td><td>本文提出GARFIELD模型（Goal-Aware Representations of Future kInEmatic Latent Distributions），旨在解决从部分观测预测多种可能未来的难题，区别于现有外观主导的视频预测或仅采样少量轨迹的方法。

◆ 核心创新之一：构建结构化时空潜在表示，将未来运动的多模态分布联合编码到潜空间中，并配合确定性密度解码器直接访问运动分布，避免了昂贵的蒙特卡洛采样。

◆ 核心创新之二：支持可选的时空稀疏约束输入，使不确定性能够精准定位到具体场景元素和时间步，并可随约束增加实现渐进式细化。

实验结果表明，该方法在运动规划任务上与大型视频生成模型性能相当，但轨迹采样速度提升97倍，运动密度估计速度提升两个数量级，从而支持交互式探索和不确定性感知规划。</td></tr>
<tr><td>2026-07-28</td><td>Decompose and Reorganize: Planning with Primitives and Visuomotor Policies Learned from Demonstrations<br><a href='http://arxiv.org/pdf/2607.25397'>论文</a> | <a href='https://dr-lfd.github.io/DR-LfD-website'>代码</a></td><td>本文提出DR-LfD框架，将任务与运动规划(TAMP)与模仿学习有机结合，旨在解决长时域灵巧操作任务中高层推理与精细执行的难题。该方法根据接触关系将人类演示分解为原子技能，并以视觉运动策略或物体中心原语的形式进行复现，使技能的启动、终止与约束条件以TAMP兼容方式建模。

◆ 基于接触关系将演示分解为原子技能，显著降低数据需求，使演示负担从技能序列的指数级增长转变为与技能类型数量呈线性关系。

◆ 将视觉运动策略无缝集成到TAMP门控决策系统中，融合了TAMP的符号规划能力与模仿学习的视觉反馈优势。

◆ 技能以TAMP兼容形式表达约束条件，支持跨来源技能的灵活重组，增强了空间泛化能力和多阶段操作的适应性。

◆ 通过大量真实场景与仿真基准测试，验证了框架在多步骤、未见过的设置以及物理约束任务中的优异表现。</td></tr>
<tr><td>2026-07-27</td><td>Reactive 3D Motion Planning for a Franka Arm via Star-World Workspace Reshaping<br><a href='http://arxiv.org/pdf/2607.25138'>论文</a></td><td>本文针对反应式运动规划中安全膨胀导致障碍物重叠、违反模块化方法不相交假设的问题，研究了基于Star-World工作空间重塑的Franka Panda机械臂三维反应式控制方法。系统将相交障碍物聚类并替换为星形代理，再由基于动力学的末端执行器控制器求解，零空间人工势场项辅助机械臂本体避障。作者在六个PyBullet场景中以目标达成率、路径长度比和计算时间为指标，与未重塑基线进行了12次对比评估。

◆初步实验中，重塑方法在5/6场景成功到达目标，优于基线的4/6，并成功解决了经典重叠墙体问题，单次...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-27</td><td>Hybrid Artificial Potential Fields and Spatio-Temporal Transformers for Real-Time AUV Path Planning<br><a href='http://arxiv.org/pdf/2607.25056'>论文</a></td><td>本文针对自主水下航行器在复杂非结构化环境中的实时路径规划问题，系统比较了13种算法（涵盖A*、Dijkstra等图搜索方法，RRT*等采样方法，PSO、GA等元启发式方法以及学习架构）的性能，并在5个高分辨率水下地形场景中进行评估。主要创新点如下：

◆ 提出将人工势场法（APF）与时空Transformer（ST-Transformer）相结合的混合路径规划框架，融合了反应式避障与全局路径优化的双重优势。

◆ 构建了涵盖四类方法的大规模基准对比实验，量化分析了各算法在路径最优性、避碰性能与计算开销之间的权衡关系。

◆ 实验结果表明该混合方法在任务完成率100%的前提下，平均路径长度最短（943.15单位），碰撞率低（0.031），计算时间仅0.96秒，整体性能优于单一学习模型与经典算法。

◆ 揭示了经典算法延迟高、元启发式方法轨迹复杂等局限，为资源受限的水下系统在动态任务中的算法选择提供了实用指导。</td></tr>
<tr><td>2026-07-27</td><td>Motion Generation With Environmental Constraints<br><a href='http://arxiv.org/pdf/2607.25053'>论文</a></td><td>本文针对高维空间下机器人运动规划中碰撞避免带来的计算复杂性问题，提出了一种名为&quot;环境约束利用&quot;（Environmental Constraint Exploitation, ECE）的替代方法。该方法主张主动利用环境接触而非完全规避接触，从而降低规划维度并简化问题。

◆ 提出ECE范式，颠覆传统碰撞避免思路，通过主动利用环境接触来降低运动规划的状态空间维度和计算复杂度

◆ 将ECE集成到RRT采样规划器中，使探索偏向任务相关区域，提高规划效率

◆ 利用环境接触实现不确定性约简，增强运动执行阶段的鲁棒性

◆ 在真实场景中验证了ECE结合RRT规划器的实际有效性，展示了其在复杂环境中的适应性和性能优势

◆ 整合并扩展了相关前期研究，形成了系统的环境约束利用理论体系...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-27</td><td>Model Predictive Planner for UAV Navigation in Non-Convex Air Corridors<br><a href='http://arxiv.org/pdf/2607.24369'>论文</a></td><td>本文针对无人机在非凸城市空中走廊中的运动规划问题，提出了一种基于混合整数跟踪模型预测控制(MPC)的运动规划框架。该方法将走廊可行性与动态一致性约束统一在单一的优化问题中，避免了传统分层规划中多个模块之间的不一致问题。

◆ 采用混合整数MPC框架，在单一优化问题中同时满足走廊约束和动态可行性约束。

◆ 提出基于最短路径思想的偏移代价函数，并结合可行性约束嵌入到规划问题中，确保轨迹收敛至目标点。

◆ 有效缓解了非凸几何结构引发的局部极小值问题，无需依赖外部全局规划阶段。

◆ 数值仿真验证了所提方法能生成动力学有效的轨迹，完整满足走廊约束并可靠收敛到目标。该框架为城市空中交通中的复杂走廊规划问题提供了一种高效且自洽的解决方案。</td></tr>
<tr><td>2026-07-27</td><td>Quality-Adaptive Multi-UAV 3D Reconstruction with Sparse Workload Redistribution<br><a href='http://arxiv.org/pdf/2607.24233'>论文</a></td><td>本文针对多无人机协同三维重建中的在线协调难题,提出了一种质量自适应的去中心化决策策略,能够以用户指定的保真度构建三维地图。该方法通过将基于TSDF置信度的质量准则融入视点生成与信息增益估计,使生成的视点与期望的保真度目标保持一致。

◆ 提出了基于TSDF置信度的质量导向准则,集成到视点生成和信息增益估计中,实现用户自定义保真度的三维重建。

◆ 设计了两级协调机制:在视点评估中加入惩罚因子以鼓励无人机局部分散,避免重复探索。

◆ 提出基于正则化聚类和最优任务分配的全局不平衡修正机制,仅在检测到相对于高信息区域的负载失衡时触发,实现稀疏的工作负载再分配。

仿真结果表明,该方法在路径效率上优于当前最先进的无人机群探索方法,同时在覆盖率和精度方面获得了更高保真度的重建结果,且代码已开源。</td></tr>
<tr><td>2026-07-27</td><td>Bridging Reinforcement Learning and Optimal Control via Feasible Action Mapping<br><a href='http://arxiv.org/pdf/2607.23930'>论文</a></td><td>本文提出可行动作最优控制框架FAOC，将强化学习与最优控制融合以应对受约束动力系统的控制难题。该方法旨在同时满足复杂任务求解与递归可行性及安全约束的竞争性要求。
◆ 设计了基于优化的可行动作映射算法，将RL智能体的抽象动作转换为状态相关的OCP可行参数集，严格保证动力学约束的满足
◆ 抽象动作空间无需依赖专家或启发式设计，且OCP公式不受RL可行性保证能力的限制
在机器人乒乓球实时运动规划任务中验证，FAOC在样本效率和闭环性能上均优于现有基线方法。</td></tr>
<tr><td>2026-07-26</td><td>BC-NMPC: Battery-Constrained NMPC with Propulsion Prediction and Replanning for High-Speed Flight<br><a href='http://arxiv.org/pdf/2607.23867'>论文</a></td><td>该论文针对高速敏捷飞行中无人机因电池放电导致最大可用推力下降、轨迹跟踪性能恶化的问题，提出了一种将电池与推进系统模型集成到非线性模型预测控制（NMPC）框架中的新方法BC-NMPC。该方法能够在控制过程中实时预测电压、消耗电流、功率和最大可用推力，从而主动规划推力衰减带来的影响。论文同时设计了一种基于推力极限演化的飞行中轨迹重规划算法，使无人机能够动态调整飞行路径以适应推力变化。

◆ 在NMPC框架中集成电池与推进系统动力学模型，实现电压、电流、功率及最大推力的在线实时预测。

◆ 显式建模电池放电引起的最大可用推力动态变化，将其纳入预测控制的约束条件中。

◆ 提出基于实时推力极限演化的在线轨迹重规划算法，使控制器在飞行过程中动态调整参考轨迹。

◆ 模型精度通过真实飞行实验验证，重规划算法通过仿真评估，在复杂障碍环境中实现跟踪RMSE降低6倍、飞行距离增加46%、飞行时间增加100%的显著性能提升。</td></tr>
<tr><td>2026-07-26</td><td>TRUAV: Distributed Multi-Agent Reinforcement Learning for Trajectory Planning and Routing Enhancement in UAV-Aided IoT-Enabled VANETs<br><a href='http://arxiv.org/pdf/2607.23734'>论文</a></td><td>本文针对城市环境下UAV辅助IoT车载自组网(VANETs)中的轨迹规划与路由增强问题,提出了基于独立表格Q学习的分布式多智能体强化学习框架TRUAV,旨在解决传统集中式方法因需全局状态聚合而难以适用于带宽和能量受限场景的难题。TRUAV的核心思想是每个UAV仅基于本地可观测信息(包括车辆密度、数据包队列状态及邻居UAV位置)进行自主决策,完全消除了全局状态交换的需求,具备良好的可扩展性和实用性。论文设计了一种受势位博弈启发的奖励机制,在鼓励智能体之间保持空间分布多样性的同时,综合考虑路由质量和能量消耗,实现轨迹规划与路由性能的联合优化。在包含200辆移动车辆的大规模城市仿真中,TRUAV的网络覆盖率和分组投递比与集中式深度强化学习方法相当,但在中继时延和能量效率方面表现更优。

本文主要创新点如下:

◆ 提出基于独立表格Q学习的分布式多智能体强化学习框架,实现UAV轨迹规划与路由增强的完全去中心化协同,无需全局网络状态信息交换,有效降低通信开销。

◆ 设计势位博弈启发的奖励函数,兼顾空间分布多样性、路由感知定位和能量消耗,实现多目标联合优化,确保多智能体策略收敛至均衡。

◆ 通过仅依赖本地观测(车辆密度、队列状态、邻居位置)即可获得与集中式深度强化学习相当的覆盖和投递性能,同时在时延与能耗方面表现更优,验证了轻量级表格方法的实用可行性。</td></tr>
<tr><td>2026-07-24</td><td>Conformal Constraint Tightening for Chance-Constrained Motion Planning with Unknown Dynamics<br><a href='http://arxiv.org/pdf/2607.22409'>论文</a></td><td>本文针对具有未知动力学和近似名义模型的自主机器人运动规划问题，提出了一种基于共形预测的约束收紧方法，以在真实系统上获得概率性任务完成保证。核心思想是利用共形预测对名义模型与真实系统之间的轨迹偏差提供概率性界，并将机会约束问题转化为名义模型下的确定性收紧问题。

◆创新点一：提出了与具体规划器无关的(planner-agnostic)约束收紧框架，能够方便地集成到多种现有运动规划算法中，具有良好的通用性。
◆创新点二：基于共形预测理论给出了在规划问题分布上成立的轨迹偏差概率界，并理论证明了在名义模型下求解收紧问题等价于在真实系统上以规定概率满足原约束的充分条件。
◆创新点三：通过理论分析和仿真实验验证了该方法的有效性，结果表明在保持概率保证的同时显著提升了任务完成率，相较于纯名义模型规划具有明显优势。</td></tr>
<tr><td>2026-07-24</td><td>AgentHOI: Multi-Agent Reasoning for Human-Object-Interaction Video Generation via Implicit Representation Alignment<br><a href='http://arxiv.org/pdf/2607.22241'>论文</a> | <a href='https://github.com/bone-11/agenthoi'>代码</a></td><td>本文针对人-物交互(HOI)视频生成任务展开研究,指出现有方法过度依赖显式运动控制信号,导致难以泛化到多样化的物体和交互场景。AgentHOI提出&quot;先思考后生成&quot;的框架,利用多智能体推理机制分别处理感知、交互和运动规划,将高层文本意图与物理执行有效衔接。

◆ 设计了基于多智能体推理的思考-生成框架,分别从感知、交互、运动规划三个维度协作生成交互计划,显式建模HOI的逻辑结构。

◆ 提出隐式文本-运动对齐策略,将预训练文本到运动模型的先验知识蒸馏到视频扩散模型中,使推理阶段无需显式运动输入即可生成合理的交互动作。

◆ 实现了纯文本驱动的HOI视频生成,显著提升了交互自然度、物体外观保真度以及对复杂指令(如穿戴、骑行等)的遵循能力。</td></tr>
<tr><td>2026-07-24</td><td>Learning Spatiotemporal Decision Priors for Efficient Path Planning under Partial Observability<br><a href='http://arxiv.org/pdf/2607.22166'>论文</a></td><td>本文针对部分可观测性下路径规划效率低下的问题，提出了一种先验引导的学习框架ImiPath。该框架从演示轨迹中提炼可复用的时空决策先验，并将其作为基于经验的方向性启发式嵌入传统规划器，引导搜索朝向可靠且有潜力的区域推进，从而显著减少冗余节点扩展并缓解局部短视搜索问题。

◆ 构建融合环境空间信息与历史轨迹时序信息的局部时空观测表征，统一编码局部感知与历史经验。
◆ 设计时空注意力策略网络STAPNet，将局部观测表征高效转化为可迁移的决策先验。
◆ 将决策先验作为方向性启发式嵌入异构规划器，实现对多种传统搜索算法的即插即用增强。
◆ 在磁控微机器人平台上完成物理实验验证，证明了框架的实际部署能力与跨场景适应性。</td></tr>
<tr><td>2026-07-23</td><td>GeoWorldAD: Geometry World Action Model for Autonomous Driving<br><a href='http://arxiv.org/pdf/2607.17521'>论文</a></td><td>本文提出GeoWorldAD，一种基于几何世界模型的自动驾驶动作决策框架，旨在解决现有视觉/视频动作模型缺乏显式几何约束和未来感知的问题。核心思路是将轨迹规划建立在以自车为中心的3D空间几何基础上，并利用潜在的未来几何令牌预测短时域场景演化，从而在安全避障与驾驶效率之间取得更好平衡。

◆在以自车坐标系对齐的3D空间中进行轨迹规划，引入显式几何约束提升安全性。

◆设计潜在未来几何令牌机制，预测周围交通参与者和自由空间的演化趋势，避免决策过于保守。

◆提出渐进式多尺度几何聚合与迭代轨迹精炼策略，高效融合当前与未来几何信息。

◆在NAVSIM v1和v2基准上取得最优性能，验证了显式3D几何建模和未来世界建模对自动驾驶安全与效率的有效性。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-29</td><td>VidMap: Exploiting Temporal Structure for Video-Based Structure-from-Motion<br><a href='http://arxiv.org/pdf/2607.27194'>论文</a> | <a href='https://github.com/cvg/vidmap'>代码</a></td><td>本文提出VidMap系统,旨在解决从无约束、未标定长视频中进行精确相机标定和度量位姿恢复的难题。该系统融合了SLAM的强序列约束与离线SfM的全局优化灵活性,弥补了两类方法各自的不足。系统利用宽基线稠密图像匹配技术,并将时间顺序作为可靠回环检测的一等公民,同时引入度量单目深度先验增强全局优化。实验证明,该方法在包含极端运动和视觉对称性的数据集上,比现有SLAM和SfM方法(无论经典或学习方法)在鲁棒性和精度上都有显著提升。

◆融合SLAM序列约束与离线SfM全局优化的混合框架,支持任意长度的未标定视频进行度量重建
◆利用宽基线稠密图像匹配技术提升特征关联的鲁棒性
◆将时间顺序信息作为可靠回环检测的关键线索
◆将度量单目深度先验引入全局优化,提升尺度一致性...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-24</td><td>Metric Surface Reconstruction of Neurosurgical Scenes from Monocular Operating Microscope Images and Microscope Pose<br><a href='http://arxiv.org/pdf/2607.22773'>论文</a></td><td>本论文验证了利用单目手术显微镜图像与导航位姿数据重建神经外科术野度量级三维几何的可行性。系统通过内外参标定后，采用预训练的Depth Anything 3基础模型进行深度估计，无需任务特定微调，经点云融合与泊松表面重建生成网格。在动脉瘤训练体模实验中，浅表暴露场景精度达1.02±0.93 mm，深部手术通道场景为1.95±1.70 mm至2.33±2.15 mm。增加图像集主要提升重建完整性而非精度，整体几何保持良好，仅在不完全区域存在局部偏差。该工作为术中暴露量化、图像融合及器械工作空间表征提供了受控环境下的技术可行性依据。

创新点：
◆ 融合单目显微镜图像与导航位姿数据实现神经外科场景的度量级三维重建
◆ 利用预训练基础深度模型完成零样本深度估计，无需任务特定微调训练
◆ 在深部通道与浅表暴露两类典型术野中完成基于结构光扫描与CT基准的定量验证...[摘要不完整，待更新]</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-undistortion'>Sensor Undistortion</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-29</td><td>Semantic-Aware Temporal Adaptation for UAV Anti-UAV Tracking<br><a href='http://arxiv.org/pdf/2607.26511'>论文</a> | <a href='https://github.com/XiaozhenQiao/SATATrack'>代码</a></td><td>该论文针对UAV反无人机跟踪任务,提出了一种语义感知的时序自适应框架SATATrack。由于观察者无人机和目标无人机同时运动,场景存在快速视角变化、运动模糊和视觉相似干扰物,使固定视觉表征难以可靠匹配目标。

◆ 核心创新一:语义感知上下文传播(SACP),利用稳定的目标语言描述作为语义锚点,在骨干网络各阶段引导跨帧时序上下文传播,有效保持快速外观变化下的目标身份一致性。

◆ 核心创新二:训练阶段引入对比正则化器,抑制模型对语义相似背景区域的响应,提升特征判别性。

◆ 核心创新三:推理阶段提出时序感知分布对齐(TADA),无需更新模型参数,在线融合近期帧特征估计与训练时统计量,缓解视频特定的测试时域偏移。

该方法在UAV-Anti-UAV基准上达到最优性能,同时在反无人机和无人机目标跟踪任务上也具有竞争力,验证了语义与时序自适应协同设计的有效性。</td></tr>
<tr><td>2026-07-28</td><td>Eddeep: a deep-learning framework for fast eddy-current distortion correction in diffusion MRI<br><a href='http://arxiv.org/pdf/2607.26292'>论文</a> | <a href='https://github.com/CIG-UCL/eddeep'>代码</a></td><td>Eddeep是一种用于扩散磁共振成像涡流畸变校正的深度学习框架，旨在解决传统方法（如FSL Eddy）计算成本高的问题。该框架将校正任务分解为两个阶段：先通过监督式图像翻译网络统一扩散加权图像与b=0图像的外观，消除对比度差异对配准的干扰；再通过无监督配准网络在物理约束的二次畸变模型下，单次前向推断即可同时估计涡流畸变与头动参数。模型在UK Biobank数据上训练，并在域内和域外（Memodyn）数据集上系统验证。

◆ 提出两阶段解耦式深度学习框架，将图像外观标准化与无监督配准分离处理
◆ 设计监督式图像翻译网络统一扩散加权与b=0图像的对比度，提升配准可靠性
◆ 引入物理约束的二次畸变模型，实现单次前向推断估计畸变与头动参数
◆ 摆脱迭代优化依赖，在保持与FSL Eddy相当的校正精度的同时大幅缩短推理时间，为大规模研究和临床应用提供高效处理方案...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-07-10</td><td>A Numerically-Robust ROS 2 Port of iG-LIO: Diagnosing and Fixing Toolchain-Induced Failures in Incremental GICP LiDAR-Inertial Odometry<br><a href='http://arxiv.org/pdf/2607.09947'>论文</a> | <a href='https://github.com/Forestry-Robotics-UC/ig_lio/tree/ros2-jazzy'>代码</a></td><td>本文报告了将iG-LIO（一种紧耦合的LiDAR-惯性里程计算法）从ROS 1迁移到ROS 2 Jazzy的开源移植工作，并重点诊断了迁移过程中出现的环境诱导型数值失效问题。研究发现，在保持估计算法完全不变的前提下，编译运行后仍出现NaN发散，其根源在于现代ROS 2工具链的两个问题：一是服务质量(QoS)配置不匹配导致IMU数据被静默丢弃和重排序，二是oneTBB与Eigen组合中并行归约累加器未初始化。

◆QoS不匹配导致IMU静默丢失与乱序的诊断与修复

◆oneTBB与Eigen并行归约累加器未初始化的根源定位与解决

◆修正Ouster点云字段解析以适配新版本硬件，实现正确去畸变

◆新增Velodyne Velarray M1600传感器支持

◆为Livox提供编译时门控CustomMsg路径与无驱动的PointCloud2标准路径（如Mid-360）

◆通过YAML文件暴露运行时参数配置

该移植结果已在Ouster OS0 Rev7、Ouster OS1 Rev7和Livox MID-360三款硬件上完成实测验证。</td></tr>
<tr><td>2026-07-10</td><td>Event Stream based Multi-Modal Video Anomaly Detection: A Benchmark Dataset and Algorithms<br><a href='http://arxiv.org/pdf/2607.09114'>论文</a></td><td>本文针对传统视频异常检测在光照变化、快速运动和复杂背景下鲁棒性不足的问题，提出了基于事件相机的多模态视频异常检测框架EVAD。该框架联合利用可见光视频和事件流，事件相机以高时间分辨率异步捕捉亮度变化，对运动模糊和极端光照具有天然鲁棒性。论文构建了大规模可见光-事件基准数据集TJUTCM-Pha，包含6.3亿事件和376,368帧视频，涵盖多样化光照、运动模式和背景复杂度，填补了事件异常检测数据集的空白。设计了对比式多模态预训练框架，通过对齐事件流、可见光视频和文本描述的语义嵌入来学习判别性事件表示，并采用自适应融合模块动态整合事件时序线索与视频空间语义。

◆ 构建大规模可见光-事件多模态异常检测基准数据集TJUTCM-Pha，涵盖6.3亿事件与37万余帧视频，填补该领域真实可扩展数据集的空白。
◆ 提出对比式多模态预训练框架，跨模态对齐事件流、视频与文本语义，习得判别性强的事件表示。
◆ 设计自适应融合模块，动态整合事件时序运动线索与视频空间语义特征，显著提升对光照变化等环境干扰的鲁棒性。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5012</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4436</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2435</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1620</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1617</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1462</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1294</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1277</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1011</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>989</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>927</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>802</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>782</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>744</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>729</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>717</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>654</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>643</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>625</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>597</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>595</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>565</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>556</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>521</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>502</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>447</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>435</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>352</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>344</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>265</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>259</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>254</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>238</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>223</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>208</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>205</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>180</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>147</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>144</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>120</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2859</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1658</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1363</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1096</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1045</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>872</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>701</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>661</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>652</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>623</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>593</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>575</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>571</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>567</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>553</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>519</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>501</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>464</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>451</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>448</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>335</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>313</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>300</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>285</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>279</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>258</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>222</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>213</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>156</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>138</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>137</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>132</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
<tr><td><a href='https://github.com/ethz-asl/phaser'>phaser</a></td><td>132</td><td>A robust pointcloud registration pipeline based on</td></tr>
<tr><td><a href='https://github.com/ethz-asl/data-driven-dynamics'>data-driven-dynamics</a></td><td>130</td><td>Data Driven Dynamics Modeling for Aerial Vehicles</td></tr>
<tr><td><a href='https://github.com/ethz-asl/ssc_exploration'>ssc_exploration</a></td><td>111</td><td>Incremental 3D Scene Completion for Safe and Effic</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waypoint_navigator'>waypoint_navigator</a></td><td>108</td><td>Stand-alone waypoint navigator</td></tr>
<tr><td><a href='https://github.com/ethz-asl/active_grasp'>active_grasp</a></td><td>108</td><td>Closed-loop next-best view planning for grasp dete</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waverider'>waverider</a></td><td>107</td><td>RMPs on multi-resolution occupancy maps for effici</td></tr>
<tr><td><a href='https://github.com/ethz-asl/reinmav-gym'>reinmav-gym</a></td><td>106</td><td>Reinforcement Learning framework for MAVs using th</td></tr>
<tr><td><a href='https://github.com/ethz-asl/navrep'>navrep</a></td><td>104</td><td>navrep</td></tr>
<tr><td><a href='https://github.com/ethz-asl/eth_supermegabot'>eth_supermegabot</a></td><td>102</td><td>Instructions for ETH center for robotics summer sc</td></tr>
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>102</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/3d_vsg'>3d_vsg</a></td><td>101</td><td>3D可变场景图，用于长期语义场景变化预测。</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.07.30
