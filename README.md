# 计算机视觉领域最新论文 (2026.11.03)

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
<tr><td>2026-11-02</td><td>A Tightly Coupled Magnetic-Inertial SLAM System for Field Robots<br><a href='http://arxiv.org/pdf/2611.03106'>论文</a></td><td>本文提出紧耦合磁惯性SLAM系统MISLAM，仅使用IMU与九磁强计阵列，不依赖外部里程计或平台特定运动假设。  
◆ 创新性地将惯性导航模型与局部多项式磁场模型结合用于短期运动估计，并利用全局高斯过程磁场模型和误差状态卡尔曼滤波进行漂移校正。  
◆ 实现无需视觉、激光、轮式里程计或预装基础设施的紧耦合磁惯性融合，适用于GNSS拒止及粉尘、烟雾、弱光等退化环境。  
◆ 面向地面与空中机器人等现场机器人场景，提供不依赖可见性和轮地接触的补充定位模态。  
在三个室内手持数据集上，总端点闭合误差相对磁惯性里程计降低45.7%至78.0%；弱光下视觉惯性里程计失效后仍保持跟踪，水平闭合误差0.332米，但垂直漂移仍是限制。  
结果表明磁惯性SLAM可作为视觉退化条件下机器人传感器套件的有力补充定位方案。</td></tr>
<tr><td>2026-11-01</td><td>UniGS-SLAM: Monocular Gaussian SLAM with Enhanced Geometry and Open-Vocabulary Semantics<br><a href='http://arxiv.org/pdf/2611.02051'>论文</a> | <a href='https://3dagentworld.github.io/UniGS-SLAM/'>代码</a></td><td>UniGS-SLAM是一种仅依赖RGB的单目语义SLAM框架，核心在于将开放词汇语义与高斯重建解耦，同时保留二者的双向交互。
◆ 利用基础模型先验增强单目深度估计与位姿估计，提升无RGB-D输入下的跟踪和重建稳定性。
◆ 将语义观测融合到带观测来源的独立稀疏体素地图中，使几何更新后可回溯并修订历史语义证据。
◆ 以融合语义指导高斯过滤和局部表面细化，实现语义与几何重建的相互促进。
在Replica、ScanNet和KITTI-360上，该方法在RGB-only方法中取得领先的跟踪、渲染和几何重建性能，并具备较强的开放集语义建图能力，同时相比最快对比语义SLAM基线实现2.37倍重建加速。</td></tr>
<tr><td>2026-11-01</td><td>Spade-SLAM: Sparse Correspondence Anchors for Dense Self-Supervised Visual SLAM<br><a href='http://arxiv.org/pdf/2611.01937'>论文</a> | <a href='https://github.com/JulianPSchmitt/Spade-SLAM'>代码</a></td><td>Spade-SLAM是一种自监督稠密视觉SLAM框架，能在零样本设置下显著缩小与监督方法的性能差距，并提供无需真值位姿和深度标签的标签高效替代方案。其核心是提出稀疏到稠密互补训练机制，用稠密光度信号与稀疏特征匹配信号共同优化。
◆ 无需显式真值位姿和深度标签即可实现高保真跟踪，降低对全监督预训练的依赖。
◆ 以基于图像变换的光度损失提供稠密训练信号，保持稠密自监督学习能力。
◆ 从图像特征匹配中构造稀疏对应损失，稳定优化并抑制模糊区域的漂移。
实验表明该方法相较现有自监督基线显著提升鲁棒性与精度，已接近使用显式位姿和深度监督的SLAM系统，代码将公开。</td></tr>
<tr><td>2026-11-01</td><td>GSExplorer: Interactive World Generation with a Persistent 3D Gaussian World State<br><a href='http://arxiv.org/pdf/2611.01543'>论文</a></td><td>GSExplorer提出以持久3D高斯世界状态为核心的生成—重建框架，用于长时程交互式世界生成，并兼顾局部控制与场景一致性。
◆ 每一步由当前3DGS场景向条件驱动视频生成器提供多模态渲染条件，并通过独立的Relative Ray Encoding分支注入相机几何，从而增强视角控制。
◆ 将生成视频反馈至基于SLAM的重建后端，引入不一致性过滤防止冲突内容污染场景，并用跨块光束法平差提升多次生成间的空间对齐。
◆ 设计复现3DGS外推退化过程的数据构建管线，产出29.3万对退化多模态渲染与真实目标视频训练对。
◆ 在WorldScore单步与三步评估中取得最佳综合性能，单步外推相机控制得分达99.07，并在481帧离开—返回滚动中展现强回访一致性，验证持久3D世界状态对持续探索的价值。</td></tr>
<tr><td>2026-11-01</td><td>Spectral-Convolutional Factorized Transformer for Joint Multipath Parameter Estimation: Applications to mmWave Positioning and Radio SLAM<br><a href='http://arxiv.org/pdf/2611.01491'>论文</a></td><td>本文针对现有学习式信道估计偏重通信目标、较少显式估计多径几何参数的问题，提出谱卷积因子化Transformer（SCFT），从含噪复信道估计和物理波束对描述符中联合检测与分类LoS/NLoS多径，并估计时延、AoA和AoD。
◆ 将局部谱卷积引入多径特征提取，增强含噪复信道中的局部谱结构建模能力。
◆ 设计置换等变波束集注意力，适应波束对描述符的集合特性并保持排列等变性。
◆ 采用查询式Transformer解码器统一完成多径检测、LoS/NLoS分类及多参数回归。
在真实射线追踪数据上，SCFT较最强基线ResNet将GOSPA误差降低13.4%，并在独立快照定位和无线电SLAM中分别将位置RMSE降低18.5%和65.0%。
结果表明，显式恢复多径几何可显著提升下游定位与建图性能。</td></tr>
<tr><td>2026-10-31</td><td>A Straight Line Is Not a Camera Pose: Auditing Short-Clip Pose Benchmarks<br><a href='http://arxiv.org/pdf/2611.00482'>论文</a></td><td>论文系统审计短片段相机位姿基准，发现按Sintel协议，不使用图像的匀速直线预测平均ATE竟优于11个近期模型中的10个，揭示ATE对齐会掩盖几何错误。作者进一步证明ATE将匀速预测映射到真路径最佳拟合线，使直线仅得分回归残差，并提出残差信噪比准则预测直线化何时降低ATE，在多数模型-片段对上成立且能区分Sintel与其他数据集；同时指出仅位置对齐忽略相机朝向，旋转30度可保持ATE不变却恶化重投影，低ATE不等于好几何。
◆ 揭示无图像匀速直线可击败多数近期模型的ATE异常，并给出基于残差信噪比的解释与预测准则。
◆ 证明位置仅对齐忽略朝向，低ATE可能对应更差重投影几何。
◆ 提出pose-anchored ATE，用预测朝向拟合对齐旋转，更好反映几何误差且仅增加约0.06毫秒开销。
◆ 在新指标上正确排序图像无关参考与模型、跟踪旋转和直线化下的重投影误差，并基本保留模型顺序。</td></tr>
<tr><td>2026-10-30</td><td>Visual-Inertial RGB-D SLAM with Encoders for a Differential Wheeled Robot<br><a href='http://arxiv.org/pdf/2610.41768'>论文</a></td><td>本文针对现有VIO方法开源少且在实际中易因特征点临时缺失和快速运动失败的问题，提出利用轮式编码器增强视觉惯性RGB-D SLAM的鲁棒性。
◆提出编码器的生成式测量模型，用于克服纯视觉SLAM的临时失效。
◆推导基于编码器测量的最大后验估计表达式及优化所需的雅可比矩阵。
◆构建紧耦合的视觉-惯性-编码器RGB-D SLAM系统，实现多传感器融合状态估计。
在自建数据集上的实验表明，该系统可在实时运行下获得约2-7厘米RMSE的准确且鲁棒的状态估计。
作者还公开了源代码和包含编码器信息的数据集，便于复现与验证。</td></tr>
<tr><td>2026-10-30</td><td>DrawSplat: Atlanta World-Guided Implicit Gaussian SLAM for Indoor Reconstruction<br><a href='http://arxiv.org/pdf/2610.41602'>论文</a></td><td>本文提出DrawSplat，一种面向室内重建的Atlanta World引导隐式高斯SLAM框架，以“先勾结构、再填细节”的绘画式流程联合显式点线几何与隐式神经高斯。
◆ 采用点线联合跟踪统一估计相机位姿、稀疏几何与重力方向，增强弱纹理和大平面场景下的跟踪鲁棒性。
◆ 利用Atlanta World先验中的共享重力分量从跟踪线推断结构平面，并将其转化为对高斯中心与法向的可微正则项，抑制漂移、厚度伪影和法向噪声。
◆ 设计锚点式隐式神经高斯表示与自适应结构采样，把高斯容量分配给结构信息丰富区域，提高紧凑性与效率。
◆ 通过显式点线“草图”与隐式高斯“上色”的协同，兼顾高保真渲染和连续几何细节。
多数据集实验表明，DrawSplat在Gaussian SLAM中实现鲁棒跟踪、高保真渲染和强几何重建，并在质量、效率与模型大小间取得实用平衡。</td></tr>
<tr><td>2026-10-29</td><td>Stochastic Linesearch Methods for Stochastic Variational Inequality Problems: Parameter-Free Schemes and Non-Monotone Variants<br><a href='http://arxiv.org/pdf/2610.41065'>论文</a></td><td>论文针对现有随机变分不等式方法依赖Lipschitz常数、步长受限且性能可能较差的问题，提出无需参数知识的随机线搜索框架。  
◆ 提出周期重启线搜索的随机外梯度法SEG-LS，可求解伪单调和单调随机变分不等式。  
◆ 新方法产生的步长既不单调，也无需预先知道Lipschitz常数L，实现参数自由。  
◆ 理论上，SEG-LS在期望残差范数不超过ε时达到迭代复杂度O(ε^-2)、样本复杂度O(ε^-4)，单调情形分别改进为O(ε^-1)和O(ε^-2)。  
◆ 进一步提出周期重启的有偏随机线搜索法B-SLAM，用于严格余正条件下的非单调随机变分不等式，复杂度为O(ε^-2)和O(ε^-4)。  
◆ 初步数值实验验证了所提方法的有效性并展示出良好应用潜力。</td></tr>
<tr><td>2026-10-29</td><td>Smartphone Indoor Localization Enhanced by Hierarchical Multi-Sensor Context Recognition<br><a href='http://arxiv.org/pdf/2610.39691'>论文</a></td><td>本文提出一种由分层多传感器上下文识别增强的智能手机室内定位框架，针对PDR在航向漂移、结构转换和携带模式变化下的误差累积问题，将多传感器信息识别为环境、场景和活动概率，并转换为场景事件段与动作上下文段。其核心贡献在于用分层语义为不同类型定位误差提供定位专用校正线索，而非将所有上下文视为单一事件流或局部修正信号。实验在跨楼层与多动作轨迹上以LiDAR-SLAM为参考，验证该方法优于PDR和代表性学习惯性里程计基线。
◆ 构建数据与模型联合驱动的分层上下文识别模型，输出环境、场景和活动概率并形成两类语义段。
◆ 提出场景事件段约束的PDR校正机制，融合走廊航向约束、地标吸引、固定滞后回溯和垂直过渡处理。
◆ 提出动作上下文段驱动的RoNIN位置补偿，针对携带模式相关漂移实现动作感知修正。</td></tr>
<tr><td>2026-10-29</td><td>UMI-Live for In-The-Wild Bimanual Robotics Data Collection<br><a href='http://arxiv.org/pdf/2610.39385'>论文</a> | <a href='https://umi-live.github.io/}{\text{project'>代码</a></td><td>论文提出UMI-Live，一个面向野外双臂机器人数据采集的全栈开源UMI系统，覆盖硬件、采集界面、数据处理、遥操作与策略训练推理。
◆ 定制UMI-Live硬件集成相机、LiDAR-惯性传感、板载计算与供电，无需外部追踪设备或采集环境内标定。
◆ 设计简洁录制界面，并以异步流水线并行执行SLAM重建，发布可直接用于训练的数据集。
◆ 开源软件支持双YAM遥操作及VLA策略训练和推理，形成从采集到部署的闭环工具链。
◆ 通过微调π0.5和MolmoAct2，在双臂抓取放置任务上分别达到10/10和8/10成功率，验证数据质量。
◆ 公开40小时三任务数据、完整硬件设计、软件与复现指南，降低野外双臂数据采集门槛。</td></tr>
<tr><td>2026-10-28</td><td>SKiD-SLAM: Resource-Aware Distributed Multi-Robot LiDAR SLAM for Planetary Missions with Field Deployments at Analog Sites<br><a href='http://arxiv.org/pdf/2610.38141'>论文</a> | <a href='https://sparolab.github.io/research/skid_slam/'>代码</a></td><td>本文提出SKiD-SLAM，一种面向行星探索的分布式多机器人LiDAR SLAM系统，目标是在严重通信受限、机载计算受限且无中心基础设施的环境中协同建图。
◆ 系统调研实际行星任务的通信与计算预算，并据此选择适配模块完成机器人间地点识别、相对位姿估计和分布式轨迹融合。
◆ 在部署前结合类行星环境公开数据集和基于NASA JPL开源漫游车的模拟器完成系统验证。
◆ 在韩国济州岛熔岩管洞穴和延川KICT行星模拟地形分别用轮式漫游车与四足机器人开展实地任务验证。
结果表明，SKiD-SLAM能在250 kbps机器人间通信预算内可靠执行分布式多机器人LiDAR SLAM，验证了其在挑战性野外条件下的可行性，并公开了代码与现场数据。</td></tr>
<tr><td>2026-10-27</td><td>A Stochastic LineseArch Method (SLAM) for Minimizing Expectation Residuals: Weakening Boundedness of Gradient<br><a href='http://arxiv.org/pdf/2610.37947'>论文</a></td><td>本文为随机线搜索方法SLAM建立非凸复合随机优化的收敛保证，并在更弱假设下保持原分析的迭代与样本复杂度阶数。该分析不要求真实梯度有界，也不要求凸非光滑项r满足Lipschitz连续性。在采样梯度一致Lipschitz连续、无偏且方差一致有界，且小批量与迭代预算成比例时，SLAM达到期望近端梯度残差范数不超过ε的迭代复杂度O(ε^-2)与样本复杂度O(ε^-4)。
◆ 弱化真实梯度有界性假设，在无梯度有界条件下仍证明收敛。
◆ 去除凸非光滑项r的Lipschitz连续性要求，扩大方法适用性。
◆ 在更弱假设下保持原复杂度阶，并以期望近端梯度残差给出明确收敛保证。</td></tr>
<tr><td>2026-10-27</td><td>RAVEN: A Unified Active SLAM System for Rapid Autonomous Visual Exploration with Aerial Robots under Localization Uncertainty<br><a href='http://arxiv.org/pdf/2610.37111'>论文</a></td><td>本文提出RAVEN，一个面向四旋翼机器人在定位不确定性下快速自主视觉探索的统一主动SLAM框架，系统性地将定位不确定性纳入探索规划。
◆ 统一识别前沿与主动回环候选并生成全局巡回候选，在同一框架中权衡探索未知区域与利用已访问区域进行主动回环。
◆ 设计分别量化探索效率与定位精度的效用向量，并引入0到1的优先级参数选择最终巡回，使系统可按任务偏好自适应调整性能。
◆ 提出基于在线Fisher信息场的感知感知导航规划器，实时生成平滑执行轨迹以最小化视觉状态估计误差。
◆ 基准测试表明其优于现有主动SLAM方法，并通过定制双目惯性四旋翼的全机载实地实验验证了挑战环境下的实用性。</td></tr>
<tr><td>2026-10-27</td><td>HoloRecon: Incremental Reconstruction of Long-Range Panoramas with Global Consistency<br><a href='http://arxiv.org/pdf/2610.36876'>论文</a> | <a href='https://zhuoxiaoli.github.io/HoloRecon_page/'>代码</a></td><td>HoloRecon提出一种面向长序列全景的增量重建框架，将ORB稀疏全景建图前端与微调前馈模型耦合，实现长距离重访下的全局一致位姿估计与稠密建图。
◆利用前馈模型预测的局部几何对远距离重访特征匹配进行3D验证，从而在重复结构和部分重叠困难时建立长程相机约束。
◆使用稀疏地标校准预测深度，并将验证后的连接加入全局位姿图优化，再用校正位姿更新稠密几何。
◆构建PanoRecon七场景基准，包含重复建筑、大小回环及参考相机位姿和LiDAR几何，用于评估全局一致性。
实验表明，该方法在评估方法中取得最低平均绝对轨迹误差和较高F-1 Score。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-10-29</td><td>NGDEEP: Anchoring the $0.5 &lt; z &lt; 3.5$ Star-Forming Main Sequence at Low Stellar Masses with Ultradeep JWST/NIRISS WFSS<br><a href='http://arxiv.org/pdf/2610.40796'>论文</a></td><td>本文利用JWST/NIRISS WFSS在NGDEEP场对0.5&lt;z&lt;3.5星系开展超深Hα/Hβ光谱观测，探测到HUDF中暗至m_F150W约28等的星系，使低质量星系（z=0.5时logM*/M⊙≳7，z=3.5时≳8）的恒星形成研究成为可能。

◆ 首次在如此低质量、宽红移范围内用Hα/Hβ锚定短时标（约10 Myr）的恒星形成主序，并对284个&gt;3σ探测星系测量尘埃校正SFR_Hα。

◆ 发现Hα主序本征弥散约0.35–0.5 dex，在z&lt;2.5时比UV基（约100 Myr）主序高约0.2–0.4 dex，表明短时标星暴是弥散增大的重要来源。

◆ 观测到的Hα主序弥散在1.5&lt;z&lt;2.5、logM*/M⊙&lt;9处比FIRE模拟预测高约0.25 dex，提示低质量星系在≲10 Myr尺度上比理论预期更具爆发性。

这些结果为低质量星系短时标恒星形成历史及主序弥散起源提供了关键观测约束。</td></tr>
<tr><td>2026-10-28</td><td>Environmental Quenching of Satellite Galaxies out to z~0.4 with GAMA and DEVILS<br><a href='http://arxiv.org/pdf/2610.38836'>论文</a></td><td>本文利用GAMA与DEVILS在星系属性和环境度量上的一致处理，将卫星星系环境淬灭研究拓展到z~0.4，并降低跨巡天比较的系统偏差。
◆ 实现GAMA与DEVILS之间采用一致样本选择和环境指标的跨红移卫星星系淬灭比较。
◆ 以投影相空间作为入群时间代理，定量刻画淬灭比例演化及卫星星系相对恒星形成主序的偏离。
◆ 测得卫星星系入群后恒星形成率相对SFMS以约0.14 dex/Gyr的速率持续下降。
◆ 发现早型和晚型卫星星系均呈类似下降趋势，且两巡天间无显著红移演化，表明过去约45亿年群团环境对卫星恒星形成活动影响相当。</td></tr>
<tr><td>2026-10-27</td><td>HoloRecon: Incremental Reconstruction of Long-Range Panoramas with Global Consistency<br><a href='http://arxiv.org/pdf/2610.36876'>论文</a> | <a href='https://zhuoxiaoli.github.io/HoloRecon_page/'>代码</a></td><td>本文提出HoloRecon，一个面向长序列全景场景的增量重建框架，将ORB稀疏全景建图前端与微调前馈重建模型耦合，以兼顾准确定位和全局一致稠密建图。
◆ 利用前馈模型预测的局部几何对远距离回访的ORB特征匹配进行3D验证，从而在重复结构和部分重叠困难下建立长程相机约束。
◆ 用稀疏地标校准预测深度，并将验证后的远距离连接加入全局位姿图优化，再用校正位姿更新稠密几何。
◆ 提出PanoRecon七场景基准，涵盖重复建筑、大/小回环，并提供参考相机位姿与LiDAR几何用于全局一致性评测。
该方法在评测中取得最低平均绝对轨迹误差和较高F-1 Score，验证了其长程全景重建的全局一致性。</td></tr>
<tr><td>2026-10-27</td><td>Metric Scale for Insta360 Structure-from-Motion from the Camera&#x27;s Embedded IMU<br><a href='http://arxiv.org/pdf/2610.35554'>论文</a></td><td>本文评估Insta360 X5/X6内置1 kHz IMU作为自包含度量尺度来源，替代手机ARKit/ARCore位姿，通过线性视觉惯性对齐从SfM位姿恢复尺度。◆提出仅依赖360相机内置IMU的自包含度量尺度恢复方案，摆脱对外部手机位姿的依赖。◆完成IMU噪声、相机-IMU同步、加速度计尺度因子和偏置稳定性表征，并从数据估计相机-IMU旋转与帧时序。◆发现全测量共享重力和加速度计偏置会使尺度平均高估3.4%，提出分段独立估计再平均以消除偏差。◆在LiDAR、基准轨迹和生产测量中系统验证，惯性尺度平均绝对误差0.74%，优于手机尺度的1.94%。◆完成窗口构建消融及与单目度量深度网络比较，并分析生产数据中惯性尺度与手机尺度差异的来源。</td></tr>
<tr><td>2026-10-26</td><td>Synthetic Deformable Tubular Benchmark: A mechanically annotated dataset for evaluating deformable 3D reconstruction<br><a href='http://arxiv.org/pdf/2610.35621'>论文</a></td><td>本文提出合成可变形管状基准，用开源工具LumenMorph生成、标注并评估管状场景，包含5580张RGB图像，为可变形三维重建提供受控合成参考。
◆构建跨三种表面运动条件与移动/静止相机的六类场景基线，并提供四类场景的匹配外观变体，系统覆盖相机与表面运动耦合。
◆公开接口给出相机位姿、几何、深度、变形场、持久材质对应及离散有限元记录，支持跨帧追踪同一表面位置及其三维轨迹。
◆引入持久三角形身份与材质权重，并设置独立几何和机械一致性检查，便于核验标注与生成模型的一致性。
◆通过SfM、光流和给定几何位移插值实验，区分配准覆盖与几何精度，揭示相机与表面运动效应，并检验机械先验的收益与失配。
作者明确数据完整性、固定环境重复性和预测分数回放各有验证范围，且不宣称解剖或临床真实性。</td></tr>
<tr><td>2026-10-26</td><td>Generative Structure from Motion with Native 3D Diffusion<br><a href='http://arxiv.org/pdf/2610.35522'>论文</a> | <a href='https://dotb1ue.github.io/GenSfm/'>代码</a></td><td>GenSfM 将基于图像的3D重建与原生3D扩散模型统一起来，用于从少量未标定视图联合恢复物体3D结构和相机运动，避免重建与生成两阶段拼接导致的误差级联。
◆ 提出多模态扩散Transformer，在共享自注意力下联合去噪形状潜变量与每视图位姿潜变量，使生成几何既受输入视图约束，又能借助物体级先验推断未观察区域。
◆ 设计紧凑的3D原生UV-volume tokenization，使联合序列在增加视图时仍保持较小规模，提升多视图联合建模效率。
◆ 引入位姿感知细化阶段，在恢复的相机位姿下采样逐体素图像特征，进一步优化几何与纹理。
在Toys4k和GSO上使用4个未标定视图时，新视角PSNR提升3.2至4.5 dB，中位Chamfer距离降低2.8至3.8倍，输入视图位姿恢复达到96%以上Acc@5°，且无需外部位姿估计骨干、后处理优化或已知内参。</td></tr>
<tr><td>2026-10-26</td><td>Learning Scene Coordinate Reconstruction from Unposed Images via Pose Graph Optimization<br><a href='http://arxiv.org/pdf/2610.35501'>论文</a></td><td>论文提出一种混合框架，将位姿图优化（PGO）引入ACE-Zero，用于从无位姿图像中学习场景坐标重建并优化相机位姿。该方法针对ACE-Zero缺乏全局和多视图一致性约束、易产生位姿漂移和错位的问题，利用ACE-Zero预测的场景坐标直接构建位姿图并提取相对位姿约束。
◆ 将PGO集成到ACE-Zero中，形成学习推理与全局几何优化互补的混合结构，以抑制错误优化和位姿漂移。
◆ 直接从ACE-Zero输出构建位姿图，从预测场景坐标中提取相对位姿约束，避免依赖额外位姿标注。
◆ 引入不确定性感知优化策略，利用对极几何和光流一致性等几何先验估计置信度，提高优化鲁棒性。
实验表明，该方法提升了无监督结构运动恢复中位姿估计的鲁棒性和准确性，说明全局几何推理能有效补充学习式推理。</td></tr>
<tr><td>2026-10-26</td><td>PosePlaner: Denoising Any Feed-Forward Pose Predictor from Pairwise Planar Geometry<br><a href='http://arxiv.org/pdf/2610.34845'>论文</a></td><td>现有前馈多视图位姿预测器将对应、几何与位姿纠缠在单次前向中，难以在测试时利用几何证据校正，主要依赖监督微调。本文提出PosePlaner，将位姿细化建模为条件生成，用流匹配重新耦合粗几何匹配与初始位姿，并融合多个位姿假设形成连续数据驱动的RANSAC式投票。
◆ 以流匹配重新耦合对应与位姿，把位姿精化转化为条件生成问题。
◆ 以粗几何匹配和初始位姿为条件，融合位姿假设得到单一精化估计，提供RANSAC投票的连续数据驱动类比。
◆ 仅在两视图数据上高效训练，却能作为任意前馈n视图流式位姿估计器的周期精化器且无需重训。
◆ 实验证明其能纠正前馈预测失败、提升基于对应求解器，并减少长流式序列的累积漂移。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-10-22</td><td>GelSlim 5.0: Unifying Vision and Touch with a Single Fingertip Camera<br><a href='http://arxiv.org/pdf/2610.31334'>论文</a></td><td>GelSlim 5.0提出一种仅用单个固定相机的指尖传感器，通过切换照明，在同一视点依次获取透过膜的视觉图像与接触敏感触觉图像，从而避免多相机外参标定。
◆ 用单一相机与连续UV响应接触层统一视觉和触觉观测，实现共享视点下的序列采集。
◆ 提出VisTacFusion多模态Transformer，为平面物体位姿和接触几何设置独立预测路径。
◆ 设计非对称瓶颈融合，在引入视觉上下文的同时保留触觉空间特征，以估计深度和表面法线。
◆ 引入模态丢弃机制，使模型支持成对输入或任一单模态推理。
在12个已知物体的真实验证中，成对输入相对纯触觉将深度MSE、角度误差和平移L1分别降低61.2%、72.3%、61.3%；相对纯视觉分别降低93.7%、6.1%、8.6%。</td></tr>
<tr><td>2026-10-22</td><td>WildDepth-v2: A Synchronized RGB--LiDAR--Radar Dataset and Benchmark for Metric Depth, Motion, and Tracking of Wildlife<br><a href='http://arxiv.org/pdf/2610.31123'>论文</a></td><td>本文提出WildDepth-v2，在同步RGB-LiDAR野生动物数据集基础上扩展成像雷达、标准化基准及度量运动与跟踪能力，为动物距离、运动和生态监测提供带度量真值的数据与评测框架。
◆ 新增37个RGB-LiDAR-4D雷达序列共19716帧，提供逐点多普勒速度和实测误差预算，据称是首个成像雷达野生动物记录。
◆ 构建冻结且校验的隐藏测试集，分别面向纯RGB距离估计与RGB加稀疏LiDAR深度补全，并在动物像素和背景像素上分开评估。
◆ 利用LiDAR、雷达或单目深度将2D跟踪提升为度量3D轨迹，形成跨431条轨迹的运动与跟踪基准。
实验表明，对象级雷达校准可在推理不用LiDAR时优于场景级LiDAR校准（AbsRel 0.120对0.198），动物级LiDAR仍最优（0.052）；每轨雷达缩放将3D位置误差从2.20米降至0.58米，并把检测函数偏差从-13%降至-2%，雷达多普勒迁移到LiDAR还使运动掩码更密、动物累积误差降低37%并估计径向速度（r=0.60，约低估50%）。</td></tr>
<tr><td>2026-10-22</td><td>SpatialScout: Can VLM Agents Actively Explore and Map 3D Scenes?<br><a href='http://arxiv.org/pdf/2610.26659'>论文</a> | <a href='https://github.com/JesseZZZZZ/SpatialScout'>代码</a></td><td>本文提出SpatialScout，一个评估VLM智能体主动进行物体级3D建图的基准。该基准包含80个室内场景和3140个目标物体，要求智能体在有限交互预算下控制相机探索并估计共享坐标系中的物体中心。评估采用惩罚漏检的物体尺度重叠分数，同时衡量定位精度与目标覆盖率；实验显示最强模型Claude Opus 5.5平均重叠分数仅41.71%，IoU超0.5和0.9的目标分别占47.23%和3.25%。
◆ 构建覆盖多场景多目标、带交互预算约束的主动物体级3D建图量化测试平台。
◆ 设计联合定位精度与目标覆盖率的物体尺度重叠评估，惩罚漏检并区分粗布局与精确度量地图。
◆ 揭示前沿VLM在视角选择、跨视图关联、几何估计和地图修正上的显著能力缺口。</td></tr>
<tr><td>2026-10-21</td><td>A2I-Calib++: A Kinematics-Driven Anti-noise Active Calibration Framework for Whole-Body Multi-IMU Systems on Legged Robots<br><a href='http://arxiv.org/pdf/2610.29438'>论文</a></td><td>针对腿足机器人全身多IMU标定中运动激励不足及足滑、冲击和振动噪声问题，论文提出运动学驱动的抗噪主动标定框架A2I-Calib++，可在无人工标靶和目标IMU复杂调参下估计时间偏移、外参旋转平移与惯性偏置。
◆ 设计受噪声各向同性启发的轨迹，并给出有限时域条件性命题，以生成足量激励并降低噪声敏感性。
◆ 提出约束感知对抗运动先验控制器，将抗噪激励与滚动接触奖励结合，实现接触感知执行。
◆ 构建接触约束虚拟IMU，融合预标定小腿IMU与关节运动学并基于滚动接触模型生成标定参考。
仿真与真实四足平台实验表明，该方法显著降低噪声敏感性和标定误差，实现可重复的实机标定并提升腿足机器人本体感知里程计精度。</td></tr>
<tr><td>2026-10-20</td><td>VeriCalib: Verifiable Target-Based LiDAR-Camera Calibration<br><a href='http://arxiv.org/pdf/2610.28791'>论文</a></td><td>本文提出VeriCalib，将基于靶标的外参标定建模为可验证估计问题，并输出可指导接受、重提取、重采集或补采的标定状态，而非仅依赖同一批观测上的残差RMSE。
◆ 揭示两级外参补偿机制：残差级由外参补偿观测误差的刚体部分，参数级旋转与平移相互补偿，说明拟合残差无法反映观测与模型不一致及各方向可靠性。
◆ 构建结构化协方差，联合传播相机与LiDAR靶标特征不确定性及已知几何先验，并从残差估计方差分量尺度。
◆ 基于该协方差解耦旋转与平移，量化各方向精度并引导数据采集至最弱方向。
◆ 提出视内与跨视一致性检查，分别检验内部残差和观测间刚性差异，阈值在未知噪声下保持显著性水平。
◆ 将最小可检测偏差扩展到外参，给出各方向最小可检测故障边界，并据上述准则形成接受或补采的标定状态。</td></tr>
<tr><td>2026-10-20</td><td>Can a Display Be Used for Rapid LiDAR-Camera Extrinsic Calibration?<br><a href='http://arxiv.org/pdf/2610.28571'>论文</a> | <a href='https://github.com/ZuhaoZou2026/ScreenCalib'>代码</a></td><td>ScreenCalib提出用普通可编程显示屏完成LiDAR-相机外参标定，相机观测屏幕显示的AprilTag，LiDAR测量屏幕物理表面与边界，从而减少专用标定板准备并实现间接跨模态关联。针对显示几何关联歧义和室内杂乱干扰，方法采用标签引导的显示屏提取、几何假设生成与优化，并利用周围场景边缘消歧。实验覆盖仿真及三种传感器平台、机械与非重复LiDAR、干净与杂乱环境，平移精度优于竞争标定板方法，联合多姿态优化进一步降低旋转和平移误差并改善渲染地图对齐。创新点：
◆以普通显示屏作为可编程标定物，兼顾已知视觉标记与可控几何，减少专用靶标准备。
◆通过标签引导提取、几何假设生成优化及场景边缘消歧，稳健解决LiDAR与相机间的间接跨模态关联歧义。
◆提出单姿态静态标定与多姿态共识联合优化，后者无需连续运动或轨迹估计，并降低标签尺寸测量误差敏感性。</td></tr>
<tr><td>2026-10-20</td><td>SynCalib: Breaking Dataset Shortcuts in LiDAR-Camera Calibration via Extrinsic-Controllable Synthesis<br><a href='http://arxiv.org/pdf/2610.27547'>论文</a></td><td>论文针对现有学习式LiDAR-Camera标定方法因训练数据外参多样性不足而过度拟合固定标称外参、产生数据集捷径并导致泛化差的问题，提出SynCalib数据生成框架。该框架利用带深度真值的全向图像数据集，在严格外参约束下合成多模态标定数据，以增强训练数据的外参多样性。
◆提出外参可控的多模态标定数据合成框架，从数据源头打破固定标称外参导致的数据集捷径。
◆在严格外参约束下生成LiDAR-Camera标定样本，提升外参多样性，使网络不再依赖单一标定配置。
◆验证仅用合成数据训练的模型可在多种真实相机-LiDAR配置上零样本迁移，显著提升泛化性与鲁棒性。
实验表明该数据能增强典型学习式标定网络的泛化与鲁棒性，作者还将公开数据生成代码、预训练模型和在线基准数据集。</td></tr>
<tr><td>2026-10-20</td><td>Visual-Inertial Odometry for Ground Robots with Dynamic Camera-IMU Extrinsic Calibration<br><a href='http://arxiv.org/pdf/2610.25397'>论文</a></td><td>本文针对视觉惯性里程计中传感器刚性安装假设限制适应性、难以应对结构运动的问题，研究时变相机-IMU外参标定，以提升地面机器人在动态结构运动场景下的定位适应性。
◆ 提出基于Denavit-Hartenberg约定并融合机器人运动模型的动态相机-IMU外参标定方法，将外参随关节运动变化纳入建模。
◆ 设计两步初始化策略高效估计初始关节角，为后续外参优化提供可靠起点，并支持时变相机-IMU外参的在线估计。
仿真实验表明，该框架能有效适应相机-IMU外参变化，同时保持具有竞争力的定位精度。
该工作的核心创新在于将机器人运动学引入动态外参标定，并通过初始化与在线优化结合实现时变外参的实用估计。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vlm'>Robot VLM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-02</td><td>D&amp;A: Decoupling Description and Assessment Enables VLMs as Zero-Shot Robotic Reward Models<br><a href='http://arxiv.org/pdf/2611.03622'>论文</a></td><td>D&amp;A将视觉语言模型的零样本机器人奖励建模解耦为“描述”与“评估”两阶段，以缓解确认偏差和失败执行被误判为有进度的问题。方法先让模型生成客观、任务锚定的场景动态文本描述，再依据显式评分标准评估绝对成功程度，而非依赖视频内部时间排序或隐式成功假设。
◆将任务进度估计解耦为客观场景描述与基于显式规则的评估两阶段。
◆在打分前要求模型显式合成绝对成功定义，以外部全局准则锚定评估并避免相对时间排名。
◆纯提示实现，无需昂贵真实机器人数据和逐基础模型后训练，可跨任务、具身与基准泛化。
◆输出细粒度部分进度指标，能校准零样本估计、惩罚失败执行并正确插值成功过程。
◆奖励估计可匹配或超越后训练奖励模型，并支持高效下游强化学习。</td></tr>
<tr><td>2026-11-02</td><td>TAMPAgent: Agentic Belief-Space Planning for Mobile Manipulation<br><a href='http://arxiv.org/pdf/2611.03584'>论文</a></td><td>TAMPAgent提出一种将大视觉语言模型开放世界推理与任务与运动规划的结构化约束满足统一起来的智能体规划框架，面向部分可观测的开放世界移动操作。
该框架为LVLM智能体配备信念空间规划模型，以及可扩展的感知、规划与控制工具API。
◆ 创新性地让智能体先生成由参数化观察动作和执行动作构成的部分任务计划，再交由经典搜索算法补全。
◆ 从任务计划中提取几何约束，并通过工具API绑定有效参数值，从而满足可行性要求并生成可执行运动计划。
◆ 在执行中持续更新信念历史，交错观察与操作形成闭环规划，适应几何不确定性和部分可观测环境。
在Rainbow Y1和Unitree G1上的复杂家居移动操作实验表明，其显著优于直接工具调用基线，证明将TAMP约束满足融入智能体规划循环对非结构化部分可观测环境至关重要。</td></tr>
<tr><td>2026-11-02</td><td>VerifLM: Physically Verified Image-Edit-Guided Goal Pose Generation for Robotic Manipulation<br><a href='http://arxiv.org/pdf/2611.03268'>论文</a></td><td>VerifLM提出一种将图像编辑得到的目标配置转换为经物理验证的6-DoF物体位姿、并用于机器人规划的框架，核心是弥合“易可视化目标”与“可规划数值位姿”之间的鸿沟。
◆ 创新性地以编辑图像恢复主动物体与被动物体的初始相对位姿，并让视觉语言模型生成轴方向采样约束和任务特定验证程序。
◆ 创新性地将候选位姿放入物理模拟器评估，再由视觉语言模型选出最符合任务语义的保留候选。
◆ 创新性地从RGB-D观测重建度量几何并构建多组不同物理与几何参数的假设仿真，通过“平行世界”验证按满足验证程序的世界数量排序，从而无需预定义物体网格或物理参数。
在九个操作任务中，VerifLM在八个任务上取得最高成功率，尤其在需要精确方向和接触关系的目标上提升最大。</td></tr>
<tr><td>2026-11-02</td><td>SurgPace: Complexity-Aware Progressive Distillation for Surgical Multimodal Large Language Models<br><a href='http://arxiv.org/pdf/2611.03125'>论文</a> | <a href='https://github.com/hezhicheng2002/SurgPace'>代码</a></td><td>论文针对外科多模态大模型计算成本高、直接蒸馏因样本难度与视觉歧义差异大及训练中监督作用变化而不稳定的问题，提出复杂度感知的渐进蒸馏框架SurgPace。
◆ 该框架利用预测置信度与Lorentz几何一致性估计样本复杂度，并用融合分数驱动连续的由易到难课程学习。
◆ 它引入特征、logit和概率三级层次化表征对齐，并随训练逐步从教师模仿转向任务监督。
其关键设计在于将样本级课程调度与目标级监督调度解耦，从而提升蒸馏稳定性与效果。
作者在覆盖四个公开外科数据集和五种对话范式的Surg-396K基准上验证，SurgPace稳定优于强蒸馏基线。
实验表明该方法可构建紧凑、内存高效且解码更快的外科多模态大模型，有利于临床部署。</td></tr>
<tr><td>2026-11-01</td><td>Do Embodied VLMs Actually Use Their Scene-Graph Memory?<br><a href='http://arxiv.org/pdf/2611.02056'>论文</a></td><td>论文对具身VLM是否真正利用场景图记忆进行诊断性研究，而不只考察答案准确率。
◆提出graph-swap测试：用另一回合的场景图替换当前记忆，并通过答案改变数量直接衡量模型对图记忆的依赖。
◆系统比较文本与图编码两种记忆投递方式，发现文本记忆显著有效，路线题提升约30分，而图记忆未被有效利用。
◆定位失效原因：编码器保留了信息，但池化与晚期融合丢弃了它；为每个节点分配独立输入token可恢复部分信息，路线题提升8.3分且经swap测试确认来自图。
◆揭示准确率掩盖的捷径：当相同事实已出现在文本中时，模型会忽略场景图。
该测试为检查VLM是否使用场景图记忆提供低成本工具，并为记忆投递设计提供依据。</td></tr>
<tr><td>2026-11-01</td><td>GatedVLA with Camera-Based Emergency Braking: AlpaSim E2E Closed Loop Challenge Technical Report<br><a href='http://arxiv.org/pdf/2611.01663'>论文</a></td><td>本文提出面向PAI-AV赛道的GatedVLA端到端自动驾驶策略。  
◆将驾驶预训练的Qwen-Drive-1.0-4B视觉语言模型与逐层流匹配动作专家结合，输出2.5秒时域的加速度和曲率控制。  
◆在动作专家交叉注意力上引入软视觉掩码，相比同训练基线保持开环总体误差相当，并降低左转误差。  
在150个场景的局部闭环评估中，软掩码将平均场景分从0.479提升至0.517，但配对差异置信区间跨零、统计显著性有限。  
◆部署时加入规则式自动紧急制动模块，将平均分进一步提升至0.599，并把有责碰撞场景均值从34.0降至11.0。</td></tr>
<tr><td>2026-10-31</td><td>Vision-Language Models Are Joint Denoisers in Robotic Action Generation<br><a href='http://arxiv.org/pdf/2611.01215'>论文</a></td><td>论文提出JADE联合动作去噪器，让预训练VLM与动作专家在扩散式VLA中共同细化动作，而非仅由VLM提供静态条件。
◆通过结构化动作潜变量，VLM可在每个去噪步骤读取噪声动作、视觉观测和语言指令，并经门控交叉注意力动态引导动作专家。
◆对VLM施加从噪声动作潜变量恢复干净动作潜变量的监督，使其获得直接动作学习信号，将感知与控制更紧密耦合。
◆联合去噪支持更少采样步数，配合自适应步长调度平衡任务性能与推理延迟，抵消VLM参与的额外开销。
在RoboDojo上JADE以12.67%平均成功率居评测的π0.5类方法之首，并与大规模预训练VLA/WAM模型具竞争力，同时在RoboTwin 2.0及四个真实双臂任务上提升，真实任务平均成功率较π0.5提高20.8个百分点。</td></tr>
<tr><td>2026-10-31</td><td>Auriga Technical Report: A Task-Agnostic Agent Harness for Zero-Shot Embodied Manipulation<br><a href='http://arxiv.org/pdf/2611.01112'>论文</a> | <a href='https://github.com/lose4578/Auriga'>代码</a></td><td>论文提出任务无关的具身智能体执行框架Auriga，用于零样本操作并弥合视觉语言模型高层规划与机器人物理执行之间的规划-执行鸿沟，无需目标任务试验或重置。在RoboDojo上，Auriga关闭68.3%的执行差距，以57.7%成功率和64.0得分排名第一，超过同模型参考框架两倍，并在场景随机化下保持第一。在RoboCasa365上，同一冻结框架达到73.2%成功率，在复合任务上最高超过VLA辅助智能体23.1%。
◆ 模型基于显式任务信念做全部任务决策，并通过直接工具调用或合成的多步Python程序执行。
◆ 框架提供校准的3D测量、手指参考的双臂控制和单一机器人准入网关，运动前暂停仿真检查视觉轨迹预览，执行中检查阶段容差与抓取边界，偏离时停机并返回测量差异供原地恢复。
◆ 框架经13轮跨任务能力迭代后冻结评估，实现任务无关、零样本且无需目标试验或重置的部署。</td></tr>
<tr><td>2026-10-31</td><td>Ripple: Deadline-Aware CPU-GPU Sharing for Embodied Inference<br><a href='http://arxiv.org/pdf/2611.01067'>论文</a></td><td>论文提出Ripple，一个面向统一内存边缘设备的CPU-GPU协同调度器，用于在LLM/VLM推理与时限敏感的机器人CPU任务共存时调控GPU内存流量干扰。
◆创新点一：不依赖带宽计数器或直接限速，而是结合模型推导的GPU内存访问量与CPU完成反馈来在线感知和调节干扰。
◆创新点二：将推理划分为可暂停的层级单元，并把每个CPU任务的截止期余量转换为GPU字节预算，仅在所有重叠任务预算内准入推理工作。
◆创新点三：通过在线更新跟踪干扰变化，并采用截止期感知节流与适度收窄SM占用，在保障CPU时限的同时维持推理进度。
◆创新点四：基于SGLang引擎钩子和中心调度器实现，在DGX Spark上用四类机器人CPU任务混合及LLM/VLM推理进行验证。
结果表明，Ripple是唯一在测试截止期设置下持续满足2% CPU截止期错过目标与VLM截止期、同时保持尽力而为LLM吞吐的方法。</td></tr>
<tr><td>2026-10-31</td><td>Leap-VLA: High-Rate Robot Control from a Low-Rate VLM Backbone<br><a href='http://arxiv.org/pdf/2611.01011'>论文</a></td><td>论文提出Leap-VLA，将低频VLM语义锚点与高频流匹配动作专家解耦，用缓存语义和低延迟新鲜视觉流实现高率机器人控制。
◆缓存复用使策略显式依赖缓存年龄τ，并通过自适应层归一化用τ条件化动作专家。
◆训练时从真实片段历史采样缓存年龄，并用年龄递增像素损坏模拟部署陈旧内容，显式覆盖年龄函数。
◆异步部署下显著缩小陈旧差距，在LIBERO上1至2秒语义刷新仍接近频率匹配锚点。
◆提出soft-nudge前向chunk边界校正，无需自梯度且零额外延迟地完成每控制步重规划并基本无损。
◆用零成本负片段训练CoT verdict gate，在指令与场景不匹配时冻结执行，且不损害可行任务成功率。</td></tr>
<tr><td>2026-10-31</td><td>WorldSketch: Sketching World Models for Zero-Shot Mobile Manipulation<br><a href='http://arxiv.org/pdf/2611.00513'>论文</a></td><td>WorldSketch提出一种面向零样本移动操作的机器人智能体新范式，让VLM从直接生成动作转为构建可执行的世界模型。
◆以VLM作为主动感知智能体，通过查询感知工具构建并视觉验证最小运动学世界模型，仅保留任务相关物体、交互几何与可能运动。
◆在该模型上由几何规划器联合优化接触与全身运动，避免VLM直接推理精细几何和接触。
◆世界模型具备自改进能力，利用执行反馈验证结果、更新不确定假设，并在预测被推翻时修正模型。
◆该范式在RoboCasa、LIBERO-PRO和R2R-CE导航中分别取得91%、97%和76%的零样本成功率，显著优于零样本基线且大幅减少VLM输入token。</td></tr>
<tr><td>2026-10-31</td><td>Knowing Where to Look: Interactive Object Search via Spatial-Semantic Fusion<br><a href='http://arxiv.org/pdf/2611.00499'>论文</a> | <a href='https://skymanaditya1.github.io/objsearch-website/'>代码</a></td><td>论文核心贡献是主张在显式三维信念中联合语义先验与几何证据，从而实现类人交互式物体搜索，并证明其优于单一模态方法。◆提出统一的3D体素信念场，将每个物体的VLM合理性分数与几何占用证据进行融合。◆采用贝叶斯对数几率滤波，把语义合理性与几何占用证据累积为可解释的空间信念。◆依据融合信念场中的高信念区域驱动动作选择，包括换视角细看、导航至未探索区域和物理操作关闭柜子。◆构建端到端系统并在双臂移动人形机器人上验证，较仅几何搜索和LLM规划方法表现更优。实验表明，显式联合语义与几何证据能有效提升机器人交互式物体搜索性能。</td></tr>
<tr><td>2026-10-30</td><td>SketchMate: Agentic Geometric Reasoning for Zero-Shot Precision Insertion<br><a href='http://arxiv.org/pdf/2610.41844'>论文</a></td><td>论文提出SketchMate，将零样本精密插入转化为可测量的任务草图：由VLM构建少量几何基元和两个配合坐标系，再由VLM智能体在多视角深度中用几何工具测量，最后交给标准规划器和柔顺控制器执行。该方法不要求VLM直接输出亚毫米级位姿，而是把高精度几何推理落到草图与测量上。
◆用几何基元和配合坐标系构成草图模型，替代VLM过粗的空间输出。
◆草图与零件摆放解耦，每任务只需构建一次，并存入草图记忆，通过点云配准迁移到新摆放，仅在陌生零件时调用VLM。
◆抓取后近距离检查两个配合面，并用形状匹配修正草图，以提高装配精度。
在69个仿真插入任务中，该方法以严格运动学测试实现88%的装配位姿插入，而ReKep和MOKA均无法插入；在八个任务的新摆放中，复用一次存储草图可达到逐回合调用智能体的效果，并将草图生成时间从约90秒降至3.4秒。</td></tr>
<tr><td>2026-10-30</td><td>MolmoSpaces-CommonSense: Evaluating Commonsense in Robotic Manipulation Policies<br><a href='http://arxiv.org/pdf/2610.41377'>论文</a> | <a href='https://github.com/allenai/molmospaces'>代码</a></td><td>本文针对现有机器人操作仿真基准场景偏干净、任务结构狭窄、缺乏常识推理评测的问题，提出面向真实杂乱与部分可观测场景的常识推理评测框架。
◆ 基于发展认知科学构建机器人操作推理分类法，将遮挡、容器关系、支撑关系、语义抓取点、空间可供性和隐藏物体等常识推理系统化。
◆ 构建新基准 MolmoSpaces-CommonSense，要求策略既识别场景结构又在其中执行正确操作，而非只测低层执行。
◆ 系统评估多种零样本通才操作策略，揭示随干扰物增加成功率下降超50%、约30%情况下作用于错误物体、可供性抓取仅约50%选中正确部件等一致失败。
◆ 进一步发现基于VLM的成功估计在这些场景中不可靠，说明挑战贯穿感知-推理-动作全栈。
结论是现有基准可能显著高估零样本真实世界准备度。</td></tr>
<tr><td>2026-10-30</td><td>TinyAstral: Transferring Self-Evolving Harnesses to Tiny Generalist Manipulation Agents<br><a href='http://arxiv.org/pdf/2610.41216'>论文</a></td><td>TinyAstral提出两阶段框架，将大型教师代理的harness自进化成果迁移到低推理成本的紧凑通用操作代理。
◆ 第一阶段冻结开放权重教师，由前沿LLM代理读取教师轨迹并提出harness编辑，仅当通过配对统计检验时才接受，实现递归自改进。
◆ 第二阶段冻结最终harness，收集含推理与失败恢复的教师轨迹，蒸馏小型学生并在同一harness中替代教师。
◆ 在RoboTwin上，harness进化使教师成功率从33.4%升至63.6%，最终4B学生达62.8%；四个harness版本上学生均接近对应教师且后版本更强。
◆ harness增益可无需重训迁移到其他冻结规划器；相同episode下4B学生优于开放4B、27B SenseNova-RoboRSI及教师置于三家竞品harness的结果，并在未见基准上接近552B同harness规划器。
◆ 实测部署中该4B学生仅用约教师五分之一加速器时间。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-visual-semantic-recognition'>Robot Visual Semantic Recognition</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vpr'>Robot VPR</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-07-15</td><td>Visual Place Recognition Using Rate-Encoded Spiking Neural Networks with Discrete STDP Learning<br><a href='http://arxiv.org/pdf/2607.13584'>论文</a></td><td>该论文针对基于STDP的无监督脉冲神经网络在视觉位置识别中召回率不足的难题，提出了一套基于PyTorch与snnTorch的离散化张量化实现方案，并在100地点的Nordland数据集上以15个独立训练网络进行系统评估。

其核心创新点如下：
◆ 采用闭式确定性张量管道替代传统argmax进行神经元分配，显著提升了R@100P指标
◆ 揭示了查询后状态重置机制可独立改善召回精度，且与神经元分配方式解耦
◆ 提出速度补偿的滑动窗口聚合策略，在k=5时即达到R@100P=100.00%，仅引入0.20毫秒额外延迟

不过作者也坦承，各机制的独立贡献以及与先前连续时间模型之间的实现差异尚未完全厘清，仍需后续深入探究。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5337</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4839</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2486</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1665</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1630</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1538</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1372</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1319</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1123</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>1099</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>953</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>817</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>785</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>748</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>748</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>735</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>699</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>674</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>637</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>629</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>625</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>593</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>572</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>545</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>515</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>480</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>467</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>375</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>350</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>281</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>275</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>260</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>243</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>234</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>229</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>223</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>223</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>214</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>151</td><td>iBTC</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2888</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1681</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1369</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1098</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1062</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>886</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>714</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>673</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>670</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>623</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>612</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>579</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>576</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>571</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>554</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>521</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>521</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>465</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>457</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>456</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>343</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>334</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>310</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>305</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>290</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>278</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>258</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>105</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/eth_supermegabot'>eth_supermegabot</a></td><td>102</td><td>Instructions for ETH center for robotics summer sc</td></tr>
<tr><td><a href='https://github.com/ethz-asl/3d_vsg'>3d_vsg</a></td><td>102</td><td>3D可变场景图，用于长期语义场景变化预测。</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.11.03
