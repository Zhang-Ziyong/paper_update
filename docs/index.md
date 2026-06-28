# 计算机视觉领域最新论文 (2026.06.28)

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
<tr><td>2026-06-25</td><td>RayPE: Ray-Space Positional Encoding for 3D-Aware Video Generation<br><a href='http://arxiv.org/pdf/2606.27345'>论文</a></td><td>◆ RayPE指出传统视频DiT仅在(u,v,t)网格上做RoPE，缺乏对场景三维几何关系的显式建模。
◆ 它将每个token对应的相机射线表示为6D Plücker坐标，并利用Plücker互易积与Transformer注意力点积同为双线性形式的联系。
◆ 方法把射线位置编码以加法方式注入Q/K，并设计query/key翻转结构，使对称恒等配置可精确对应互易积。
◆ 注入后注意力分解为内容项、几何项及两类内容-几何交叉项，实验表明这些部分都不可或缺。
◆ 为适配不同相机平移尺度，RayPE解耦射线方向与矩幅值，引入基于对数幅值的门控，并用RMSNorm稳定对齐内容分支。
◆ 该模块参数增加不到0.1%、可零初始化接入预训练视频DiT，并提升相机可控性、跨帧3D一致性和整体视频质量。</td></tr>
<tr><td>2026-06-25</td><td>PanoImager: Geometry-Guided Novel View Synthesis and Reconstruction from Sparse Panoramic Views<br><a href='http://arxiv.org/pdf/2606.27071'>论文</a></td><td>◆PanoImager面向稀疏全景图在旋转主导、弱视差条件下难以进行SfM/SLAM初始化的问题，提出了一个无需SfM的三维重建框架。
◆它结合前馈式位姿/深度先验，为极少量全景输入提供可靠的几何约束。
◆方法将全景图分解为局部透视视图，并通过几何条件扩散模型合成辅助新视角，增强稀疏观测信息。
◆在重建阶段，PanoImager利用深度引导的3D Gaussian Splatting优化，提高跨视角一致性与优化稳定性。
◆多数据集实验表明，该方法在极端稀疏输入下更稳定，可作为SfM/SLAM失败时的离线地图细化组件。</td></tr>
<tr><td>2026-06-24</td><td>RoboAtlas: Contextual Active SLAM<br><a href='http://arxiv.org/pdf/2606.26046'>论文</a></td><td>◆提出RoboAtlas，一种上下文主动SLAM框架，可在几何探索与语义推理之间自适应切换，实现更高效的任务导向导航。
◆构建OpenRoboVox大规模3D语义地图系统，支持在真实大场景中累积约3万个语义实例并为基础模型提供空间 grounding。
◆设计上下文多臂老虎机机制，融合前沿探索、全局语义地图推理和第一视角VLM推理，随场景理解提升逐步转向语义导航。
◆在仿真和Unitree Go2真实机器人上验证，覆盖超过1800平方米环境，并实现100%任务成功率。
◆在GOAT-Bench Val Unseen上以GPT-4o达到90.6%成功率，领先最强基线17.8个百分点；使用Qwen2.5-VL-7B仍达88.8%，证明语义地图带来的信息增益比单纯更换更强模型更关键。</td></tr>
<tr><td>2026-06-24</td><td>DSP-SLAM++: A Unified Framework for Multi-Class, High-Fidelity Object SLAM in the Wild<br><a href='http://arxiv.org/pdf/2606.25953'>论文</a></td><td>◆ DSP-SLAM++针对现有目标级SLAM在实时性、多类别支持和高保真建模之间的矛盾，提出了统一的多类别高精度目标SLAM框架。

◆ 该方法在DSP-SLAM基础上引入异步建图流水线，显著缓解建图线程瓶颈，使系统更适合实时运行。

◆ 论文针对单目鱼眼相机与LiDAR组合设计了专门的传感器融合适配，增强了在真实复杂场景中的鲁棒性。

◆ 实验表明，系统可为多类物体生成细粒度、几何完整且语义一致的三维形状。

◆ 相比先进基线，DSP-SLAM++最高可降低70%的目标处理延迟，并在25 Hz多类别数据集上实现稳定实时表现。</td></tr>
<tr><td>2026-06-24</td><td>SA-LIVO: Efficient LiDAR-Inertial-Visual Odometry with Subspace-Aware Degeneracy Handling<br><a href='http://arxiv.org/pdf/2606.25699'>论文</a></td><td>◆提出SA-LIVO，面向LiDAR退化与视觉失效并存的LIVO场景，将方向选择性融合引入紧耦合LiDAR-惯性-视觉里程计。
◆核心创新SAIF对联合LiDAR-视觉信息矩阵做特征分解，并在每个特征方向上用线性钳位软门控，削弱退化方向、完整保留可观方向。
◆系统让视觉信息主要补偿LiDAR欠约束子空间，避免在LiDAR已充分约束方向重复注入信息或在退化时全状态分散补偿。
◆LiDAR与视觉残差在共享线性化点的InEKF中联合优化，且视觉光度雅可比可预组装并跨迭代复用，显著降低计算开销。
◆在29个序列和并发退化场景中，SA-LIVO达到强基线级精度并在对手发散时保持有界漂移，同时CPU实时运行且峰值内存降低3.6–6.3倍。</td></tr>
<tr><td>2026-06-24</td><td>OrthoTrack: Continuous 6-DoF UAV Trajectory Estimation Anchored in Public Orthophotos<br><a href='http://arxiv.org/pdf/2606.25245'>论文</a></td><td>◆提出OrthoTrack，一个无需训练的连续6-DoF无人机轨迹估计系统，仅依赖公开正射影像和地表模型作为地图先验。
◆通过将关键帧与正射影像匹配，并利用地表模型把2D对应提升到公制3D，实现绝对尺度定位。
◆利用光流将地图锚定的对应关系传播到中间帧，从而在无GPS和无后处理对齐的情况下逐帧输出位姿。
◆构建MovingDrone数据集，提供逼真无人机序列、密集6-DoF真值及多时相多模态地理数据。
◆实验表明该方法可在单GPU实时运行，并显著优于包括使用真值尺度和对齐信息的基线，具备跨区域部署能力。</td></tr>
<tr><td>2026-06-23</td><td>Vision-Language Model Reasoning for Contextual Semantic Mapping in Intralogistics<br><a href='http://arxiv.org/pdf/2606.24814'>论文</a></td><td>◆论文提出一种面向仓内物流的上下文语义建图流程，将SLAM几何建图、SAM实例分割、实例聚类与VLM多视角推理结合起来。

◆该方法不仅建模环境几何结构和物体类别，还进一步推断物体的上下文属性，如是否可移动。

◆其创新在于利用零样本、开放词汇的VLM推理，无需任务专门训练或预定义类别即可理解物体属性。

◆通过聚合多视角观测，系统提升了语义分类与可移动性判断的可靠性，分别达到98.93% mIoU和89.17% mAcc。

◆论文还通过组件分析指出，VLM推理是上下文理解瓶颈，实例聚类是全景性能主要限制，为后续改进提供依据。</td></tr>
<tr><td>2026-06-23</td><td>Pocket-SLAM: Rendering-Area-Aware Pruning for Memory-Efficient 3DGS-SLAM<br><a href='http://arxiv.org/pdf/2606.24796'>论文</a> | <a href='https://github.com/UMN-ZhaoLab/Pocket-SLAM.git'>代码</a></td><td>◆提出Pocket-SLAM，面向大规模3DGS-SLAM中高斯点持续累积导致的内存膨胀问题，提升系统可扩展性。
◆核心创新是“渲染区域感知剪枝”，不再仅依赖透明度、梯度等高斯级启发式指标。
◆该方法根据高斯点对有效渲染区域的实际贡献进行选择性删除，更直接地定位并消除内存冗余。
◆在运行时显著降低峰值显存/内存占用，同时保持定位与建图精度基本不受影响。
◆在EuRoC和KITTI数据集上验证，尤其在大规模户外场景中优于现有剪枝方法，实现超过60%内存减少和2倍以上FPS提升。</td></tr>
<tr><td>2026-06-23</td><td>Decentralized Pose Graph Riemannian Optimization for Object-based Multi-Robot SLAM<br><a href='http://arxiv.org/pdf/2606.24489'>论文</a></td><td>◆本文提出面向对象级多机器人SLAM的完全去中心化位姿图黎曼优化框架，可同时估计机器人轨迹与共享持久物体位姿。
◆方法通过一致性机制解耦强耦合的多机器人-物体估计问题，使通信拓扑不必与物理观测关系一致，适应稀疏、间歇和变化网络。
◆论文设计了分布式近似牛顿算法，利用局部二阶信息并直接在SE(d)流形上优化，以保持几何一致性。
◆理论上证明算法收敛到黎曼一阶驻点，并通过局部条件数分析解释二阶近似相较一阶下降的收敛优势。
◆实验表明该方法在公共数据集、大规模仿真和真实多机器人场景中减少迭代与通信开销，同时提升精度、效率、可扩展性和抗通信故障能力。</td></tr>
<tr><td>2026-06-22</td><td>Offline Reinforcement Learning for Warehouse SLAM Throughput Control<br><a href='http://arxiv.org/pdf/2606.23978'>论文</a></td><td>◆提出面向仓库SLAM（扫描/贴标/应用/清单）吞吐控制的离线强化学习框架，用历史日志学习策略，避免在线试错风险。
◆方法可动态推荐吞吐设定，在提升处理能力与维持下游稳定、降低拥堵之间取得平衡。
◆设计了包含历史信息的状态表示、面向延迟影响的动作抽象，以及同时刻画上下游运营指标的奖励函数。
◆框架具有算法无关性，并集成三种先进离线RL算法在大规模仓库脱敏日志上训练。
◆采用回归即时奖励估计、FQE长程评估和Deep Koopman动力学评估等多方法验证，结果显示CQL策略最佳，使系统健康度提升22.97%，平均限流时长降低3.18%。</td></tr>
<tr><td>2026-06-22</td><td>HERCULES: An Open-Source Simulation Framework for Heterogeneous Multi-Robot SLAM, Collaborative Perception, and Exploration<br><a href='http://arxiv.org/pdf/2606.22756'>论文</a> | <a href='https://lunarlab-gatech.github.io/HERCULES-website'>代码</a></td><td>◆ HERCULES提出了一个开源的异构多机器人仿真与数据采集框架，支持UAV与UGV在大规模、照片级真实、动态环境中并发运行。

◆ 它突破了AirSim/Cosys-AirSim的架构限制，引入与UAV接口一致的UGV航点跟踪控制器，并提供跨平台共享的导航、建图、可通行性分析、规划与控制栈。

◆ 框架扩展了传感器能力，加入物理建模的长波红外相机和可配置夜视模式，增强了退化视觉环境下的感知研究能力。

◆ HERCULES提供轻量API、ROS 2封装和严格的多传感器多平台时间同步，并集成行人、交通、野生动物、火灾、洪水等高保真动态要素。

◆ 它支持离线轨迹回放的数据生成模式和在线闭环规划模式，并通过SLAM、协同感知和探索实验验证了其在异构多机器人自主研究中的实用价值。</td></tr>
<tr><td>2026-06-21</td><td>Reference-Free Assessment of Physical Consistency in World Model-based Video Generation<br><a href='http://arxiv.org/pdf/2606.22363'>论文</a></td><td>◆本文提出一种无需参考视频的生成视频物理一致性评估框架，用于衡量世界模型视频生成中的物理保真度。
◆方法结合相对评估与绝对评估，避免依赖昂贵的人类投票或难以获得的真实参考视频。
◆其核心技术利用DROID-SLAM和SEA-RAFT量化几何、运动等物理不一致性，受WorldScore思想启发。
◆实验表明，经相对一致性筛选的视频可使任务成功率提升超过8%，有效缩小仿真到现实的差距。
◆绝对评估还能进行时空定位，直观显示物理伪影出现的时间和位置，增强评估的可解释性。</td></tr>
<tr><td>2026-06-20</td><td>ACEsplat: Accelerated 3D Gaussian Scene Regression via RGB and Poses Only<br><a href='http://arxiv.org/pdf/2606.22091'>论文</a></td><td>◆ ACEsplat提出了一种仅依赖RGB图像和相机位姿的快速逐场景3D Gaussian重建框架，避免了SfM点云、深度图等外部几何先验。

◆ 其核心创新是两阶段流程：先用自监督场景坐标回归模块在数分钟内构建内部几何先验，再用于后续高斯初始化与优化。

◆ 论文设计了轻量级Gaussian初始化头，将SCR特征与坐标先验融合，提升无外部3D信息条件下的3DGS初始化质量。

◆ 实验表明，该方法在Wayspots、Cambridge Landmarks和RealEstate10K等数据集上取得有竞争力的渲染质量，适用于静态视角和稀疏视角新视角合成。

◆ ACEsplat可在单GPU上15到25分钟内完成场景映射与3DGS重建，为机器人和混合现实中的快速现场建图提供了实用方案。</td></tr>
<tr><td>2026-06-24</td><td>GeoFlow-SLAM++: A Robust Multi-Camera Visual-Inertial SLAM System with Relocalization<br><a href='http://arxiv.org/pdf/2606.22051'>论文</a></td><td>◆提出GeoFlow-SLAM++，将原GeoFlow-SLAM从单RGB-D扩展为标定多相机视觉惯性SLAM，并采用统一的以机体为中心的紧耦合状态表示。
◆系统在同一多相机框架下支持可互换的ORB前端与基于SuperPoint/LightGlue的神经网络特征前端，增强了外观变化场景下的鲁棒性。
◆统一整合跟踪、建图与重定位，结合多相机重投影约束、IMU预积分、跨视角地点识别和光流/NN特征双流跟踪。
◆引入可选的跨视角一致伪深度约束，使仅RGB输入也能获得额外几何信息辅助定位。
◆在EuRoC、OpenLORIS、TUM、Hilti及自采多相机数据集上的实验表明，该方法在鲁棒性、定位精度和跨会话重定位方面均具有竞争力，手持数据上达到接近LiDAR的表现。</td></tr>
<tr><td>2026-06-19</td><td>Spectral GS-SLAM: Observability-Aware, Degeneracy-Robust Tracking for Real-Time 3D Gaussian Splatting SLAM<br><a href='http://arxiv.org/pdf/2606.21258'>论文</a></td><td>◆提出Spectral GS-SLAM，将ICP跟踪与互补的特征约束结合，面向实时3D Gaussian Splatting SLAM中的退化与弱纹理场景。
◆通过可观测性/谱分析识别ICP优化中的欠约束方向，并自适应补偿信息，缓解几何退化导致的病态和数值不稳定。
◆补偿机制不干扰用于建图的共享高斯表示，在增强跟踪鲁棒性的同时保持3DGS实时建图框架的简洁性。
◆引入高斯感知的平面性加权，利用3D高斯协方差刻画局部几何结构，指导几何与特征信息融合。
◆在TUM RGB-D挑战序列上实现40.14 FPS，并在结构缺失和特征缺失环境中保持稳定跟踪。
◆总体上，该方法在退化场景中保持轨迹完整性，同时在常规场景下维持有竞争力的精度与实时性。</td></tr>
<tr><td>2026-06-19</td><td>Ultra-Fusion: A Resilient Tightly-Coupled Multi-Sensor Fusion SLAM Framework under Sensor Degradation and Spatiotemporal Perturbation for Intelligent Transportation Systems<br><a href='http://arxiv.org/pdf/2606.21223'>论文</a></td><td>◆提出Ultra-Fusion，一个面向智能交通场景的紧耦合多传感器SLAM框架，旨在应对光照差、LiDAR退化、轮滑、GNSS中断等传感器失效问题。
◆设计统一滑动窗口估计器，将异步传感器数据按时间戳排序并转化为可选因子，统一支持WIO、VIO、LIO、LVIO及轮速/GNSS增强。
◆引入可观测性感知初始化机制，可根据场景条件自适应选择更可靠的启动模式，提升系统冷启动鲁棒性。
◆提出因子级可靠性调度，对退化测量进行门控或降权，减少异常传感器对定位结果的破坏。
◆实现在线LiDAR-IMU时空标定，可在运行中修正时间偏移和旋转外参，并通过多数据集与60余种开源SLAM对比验证了跨平台、长时高速和退化场景下的竞争性精度与可用性。</td></tr>
<tr><td>2026-06-18</td><td>Towards 3D karst underwater scene reconstruction from rotating sonar data<br><a href='http://arxiv.org/pdf/2606.20322'>论文</a></td><td>本文面向喀斯特含水层水下探测中声呐稀疏、噪声强且导航漂移严重的问题，提出了一套从旋转声呐数据重建三维水下通道场景的完整流程。
◆ 将连续时间SLAM用于校正水下航迹漂移，提高了声呐剖面在三维空间中的配准精度。
◆ 提出两阶段深度学习表面重建方法，从稀疏噪声声呐观测中恢复更连续的洞穴/管道表面。
◆ 将运动估计校正与学习式几何重建结合，突破传统三维重建方法对精确导航和密集观测的依赖。
◆ 最终生成可沉浸式浏览和导航的三维网格，为水文地质分析和喀斯特管道结构理解提供支持。</td></tr>
<tr><td>2026-06-24</td><td>FAST-LIVGO: A Degeneracy-Robust LiDAR-Inertial-Visual-GNSS Fusion Odometry<br><a href='http://arxiv.org/pdf/2606.19190'>论文</a></td><td>◆ FAST-LIVGO提出一种基于误差状态迭代卡尔曼滤波的紧耦合LiDAR-惯性-视觉-GNSS融合里程计，面向长距离、大尺度和动态环境中的稳健定位建图。
◆ 其在线时空对齐模块引入动态时间规整，提升多传感器在高速和强动态条件下的同步与融合可靠性。
◆ 方法设计了基于多普勒频移和固定锚点时间差分载波相位的GNSS观测模型，在不增广历史状态的情况下提供毫米级相对约束。
◆ 针对几何退化或纹理缺失场景，提出退化感知的双模式外点剔除策略，可在LIVO先验引导和GNSS辅助恢复之间自适应切换。
◆ 在M3DGR和20 m/s固定翼无人机数据集上的实验表明，该系统显著降低累计漂移和地图重影，精度与鲁棒性优于现有方法。</td></tr>
<tr><td>2026-06-18</td><td>A High-accuracy Event-based Underwater SLAM System<br><a href='http://arxiv.org/pdf/2606.18951'>论文</a></td><td>◆提出首个高精度事件相机水下双目SLAM系统，针对水下速度波动、宽基线和重复纹理导致的TS质量下降与匹配失败问题进行系统性解决。
◆设计基于结构张量相干性与梯度的TS结构感知度量，用于量化时间表面中的结构信息密度。
◆将最优TS生成按初始化前后解耦：初始化前用贝叶斯优化预测先验TS，跟踪阶段用异步在线局部搜索实时更新合适TS。
◆引入先验视差保障精确数据关联，并采用“最新观测优先”的三角化机制提升三维点构建稳定性。
◆构建并开源首个高质量真实水下事件数据集UWE，覆盖可变运动、复杂纹理和多类轨迹，实验表明系统精度达到或优于现有事件SLAM方法。</td></tr>
<tr><td>2026-06-18</td><td>A Smart-Scheduled Hybrid (SSH) EKF-FGO State Estimation<br><a href='http://arxiv.org/pdf/2606.16057'>论文</a></td><td>该论文针对状态估计中精度与计算成本的平衡问题，提出一种智能调度混合SSH EKF-FGO框架，作为显式研究优化调度作用的受控测试平台。
◆将优化调度作为独立设计变量进行实验性表征，明确其如何控制中间估计精度与计算成本的权衡。
◆通过固定求解器结构与计算量，结合EKF状态传播与周期性批处理优化，成功剥离并孤立出优化调度变量。
◆基于平面SLAM仿真，揭示了优化调度对优化前漂移、瞬态误差及运行时的强烈影响。
研究发现了能以极小计算成本保留大部分全局优化收益的运行机制，凸显了优化调度在混合状态估计中是未被充分探索却至关重要的因素。</td></tr>
</tbody>
</table>
</div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-25</td><td>RayPE: Ray-Space Positional Encoding for 3D-Aware Video Generation<br><a href='http://arxiv.org/pdf/2606.27345'>论文</a></td><td>◆论文指出现有视频DiT的RoPE仅编码(u,v,t)采样网格，缺乏场景3D几何信息，并将相机射线的Plücker互易积与注意力点积建立联系。
◆提出RayPE，将每个token的6D Plücker射线坐标加性注入自注意力的Query和Key，实现射线空间位置编码。
◆设计Query/Key翻转结构，使对称恒等配置下的几何注意力精确对应Plücker互易积。
◆证明注意力分数可分解为内容项、几何项及两类交叉项，实验表明这些组成均不可或缺。
◆为适配不同尺度的相机平移数据，解耦方向与矩量幅值，并引入log幅值门控和RMSNorm稳定训练。
◆该模块参数增量低于0.1%、可零初始化接入预训练视频DiT，并提升相机可控性、跨帧3D一致性和视频质量。</td></tr>
<tr><td>2026-06-25</td><td>PanoImager: Geometry-Guided Novel View Synthesis and Reconstruction from Sparse Panoramic Views<br><a href='http://arxiv.org/pdf/2606.27071'>论文</a></td><td>◆ PanoImager针对稀疏全景图在旋转主导、弱视差场景下SfM/SLAM初始化不稳定的问题，提出了一个无需SfM的三维重建框架。
◆ 方法将全景图分解为局部透视视图，并利用前馈式位姿与深度先验提供初始几何约束。
◆ 通过几何条件扩散模型合成辅助新视角，补充稀疏输入中缺失的观测信息。
◆ 结合深度引导的3D Gaussian Splatting优化，提升跨视角一致性并稳定重建过程。
◆ 实验表明，该方法在极端稀疏全景输入下具有更好的鲁棒性，可作为SfM/SLAM失败时的离线地图细化组件。</td></tr>
<tr><td>2026-06-22</td><td>The EDGE-CALIFA Survey: Star Formation Efficiency and Galaxy Quenching across 62 Main Sequence, Green Valley, and Red Galaxies<br><a href='http://arxiv.org/pdf/2606.23649'>论文</a></td><td>◆ 本文发布GBT-EDGE CO(1-0)巡天，首次用绿岸望远镜系统绘制62个近邻CALIFA星系的分子气体分布，覆盖主序、绿谷和红序星系。

◆ 研究创新性地结合CO观测与CALIFA积分场光谱，统一估计分子气体质量、恒星形成率、金属丰度和恒星质量面密度。

◆ 论文量化发现主序、绿谷和红色星系的分子气体耗尽时间依次显著增加，表明星系越偏离主序，恒星形成效率越低。

◆ 通过测试多种CO-H2转换因子，作者证明SFE下降趋势具有稳健性，不依赖特定转换因子假设。

◆ 核心结论是，部分淬火星系并非缺乏分子气体，而是保留可观气体储备但形成恒星效率低，可能源于低气体密度和形态淬火共同作用。</td></tr>
<tr><td>2026-06-22</td><td>G-MASt3R-SfM: Graph-based View Pruning and Multi-stage Optimization for Robust SfM<br><a href='http://arxiv.org/pdf/2606.22856'>论文</a></td><td>◆ 提出G-MASt3R-SfM，一种面向鲁棒Structure from Motion的新流程，针对MASt3R在非重叠图像对上产生错误匹配的问题进行改进。
◆ 设计Graph-based View Pruning模块，利用匹配置信度构建场景图，并通过几何一致性剪除异常视图和不可靠连接。
◆ 提出Multi-Stage Optimization模块，从局部一致性逐步扩展到全局一致性，分阶段优化相机参数，降低外点对整体估计的影响。
◆ 相比直接使用MASt3R匹配结果的MASt3R-SfM，该方法能更有效抑制错误对应关系带来的噪声和位姿退化。
◆ 在ETH3D数据集上取得相机位姿估计和三维重建的先进精度，验证了其在复杂匹配条件下的鲁棒性和实用价值。</td></tr>
<tr><td>2026-06-20</td><td>ACEsplat: Accelerated 3D Gaussian Scene Regression via RGB and Poses Only<br><a href='http://arxiv.org/pdf/2606.22091'>论文</a></td><td>◆ACEsplat提出了一种仅依赖RGB图像和相机位姿的逐场景3D Gaussian Splatting重建框架，避免了SfM点云、深度图等外部几何先验。
◆其核心创新是用自监督场景坐标回归模块在4–5分钟内构建内部几何先验，提升现场部署的鲁棒性。
◆论文进一步设计轻量级高斯初始化头，将SCR特征与坐标先验融合，为后续3DGS优化提供更好的初始表示。
◆在Wayspots、Cambridge Landmarks和RealEstate10K等数据集上，方法在静态视角渲染和稀疏视角新视角合成中取得有竞争力的画质。
◆整个场景映射与3DGS重建可在单GPU上15–25分钟完成，适合机器人和混合现实中的快速场景搭建。</td></tr>
<tr><td>2026-06-15</td><td>MotionPyramid: Hierarchical Motion Representation and Residual Interfaces<br><a href='http://arxiv.org/pdf/2606.20705'>论文</a></td><td>◆提出MotionPyramid，将类感知层级的表示思想引入运动控制，从数据中学习从即时电机命令到长时程行为片段的多层动作表征。
◆方法以运动跟踪教师为起点，训练递归潜变量解码器，使高层潜变量可经低层展开为 temporally extended 的全身运动程序。
◆预训练后的层级被冻结，并作为下游强化学习策略的多种动作接口，支持不同控制分辨率的复用。
◆实验表明，粗粒度接口能加速早期学习并提升运动规律性，细粒度接口则保留反馈控制能力和最终任务精度。
◆论文还提出Residual Interfaces，使策略可同时使用粗层运动程序与细层残差修正，在结构化抽象和可控性之间取得平衡。</td></tr>
<tr><td>2026-06-16</td><td>Neural Tree Reconstruction for the Open Forest Observatory<br><a href='http://arxiv.org/pdf/2606.18153'>论文</a></td><td>◆本文面向开放森林观测站（OFO）的低成本无人机森林制图需求，指出现有基于传统运动恢复结构（SfM）的3D树木重建存在伪影多、细节不足和林下区域重建困难等问题。
◆论文的核心贡献是探索将神经辐射场（NeRF）等神经3D重建方法引入OFO数据流程，以提升森林三维地图质量。
◆其创新点在于利用NeRF对稀疏视角更鲁棒、可融入数据驱动先验的特点，改善传统航拍影像在复杂森林场景中的重建局限。
◆论文强调高质量3D树木重建对下游生态与气候应用的重要性，如野火模拟、碳汇监测和再造林规划。
◆此外，作者还提出未来将OFO平台扩展到支持更多先进3D视觉模型，为开放、可复用的森林制图工具链奠定基础。</td></tr>
<tr><td>2026-06-15</td><td>MVM-IOD: An Industrial Object-Centric Benchmark Dataset for the Evaluation of 3D Reconstruction Methods<br><a href='http://arxiv.org/pdf/2606.16638'>论文</a></td><td>本文针对工业3D重建缺乏真实场景数据集的问题，提出了机器视觉测量工业物体数据集MVM-IOD，核心创新点如下：
◆构建了首个面向典型工业物体的多视角基准数据集，包含9种物体与2种背景组合的18个场景，并提供高精度参考3D点云与相机位姿。
◆设计了系统化的数据采集方案，利用工业机械臂末端搭载相机沿半球轨迹精准拍摄，真实还原工业视觉检测设定。
◆全面评估了SfM、MVS、前馈模型及2D高斯溅射等现有先进方法，为工业场景的3D重建与位姿估计建立了基准。
◆揭示了此类工业图像会导致前馈方法出现分布外问题，验证了简单预处理可缓解该问题，为工业应用前馈方法提供了重要警示。</td></tr>
<tr><td>2026-06-13</td><td>PEARLS: NuSTAR and XMM-Newton Extragalactic Survey of the JWST North Ecliptic Pole Time Domain Field VI: Multiwavelength SED Analysis<br><a href='http://arxiv.org/pdf/2606.15365'>论文</a></td><td>本文对北黄极时间域场261个X射线源进行多波段SED分析，结合恒星形成主序与黑洞吸积率框架，揭示了星系与超大质量黑洞的演化联系。
◆发现相对于主序的恒星形成率与比AGN光度存在强相关性，具有最高比AGN光度的星系位于或高于主序。
◆揭示X射线光度与恒星形成率强相关，证认出符合短时标剧烈吸积事件的冷类星体群。
◆提出低质量星系呈现高于种群均值的快速生长期吸积，而高质量星系表现为维持模式吸积。
◆证明传统活动星系核分类无法揭示这些区别，凸显了X射线视角识别罕见且关键的AGN瞬时阶段的独特能力。</td></tr>
<tr><td>2026-06-12</td><td>A Lightweight Fiducial-Based Pipeline for 3D Hyperspectral Mapping of ex-vivo Lumpectomy Specimens<br><a href='http://arxiv.org/pdf/2606.14534'>论文</a></td><td>本文提出了一种全自动且无需标定的轻量级流程，通过消费级RGB图像和单次高光谱采集，生成离体乳房切除术标本的3D高光谱点云。
◆采用深度学习运动恢复结构骨干网络进行3D几何重建，并通过四个ArUco标记角点一致性的自定义光束法平差，在度量参考系中实现稳定。
◆提出无需恢复高光谱相机位姿的配准新方法，利用双模态可见的16个标记角点驱动平面单应性，并通过正交深度图查找恢复3D坐标。
在离体标本评估中，该流程的中位3D配准误差低于1毫米，2D重投影误差低于0.02毫米。
加速硬件下单标本处理时间不到4分钟，证明了将其应用于保乳手术术中切缘评估的可行性。</td></tr>
<tr><td>2026-06-12</td><td>MooMIns -- Monocular 3D Reconstruction and Object Pose Estimation from Multiple Instances<br><a href='http://arxiv.org/pdf/2606.14389'>论文</a></td><td>该论文针对单目图像同时进行3D重建与6D位姿估计的病态问题，提出MooMIns方法，利用工业料箱场景中单图隐含的同物体多视角信息实现联合重建与估计。
◆反转高斯溅射公式，将传统的多相机渲染单一场景转变为单相机渲染多个物体实例。
◆结合SAM3实例分割掩码与改进的运动恢复结构流程进行方法初始化。
◆采用基于图像证据的纯几何重建，有效避免了深度学习单目深度估计因训练数据先验产生的幻觉问题。
实验表明，该方法在合成与真实场景中均能准确重建未见物体并可靠估计各实例的6D位姿。</td></tr>
<tr><td>2026-06-16</td><td>Fast Speech Foundation Model Distillation Using Interleaved Stacking<br><a href='http://arxiv.org/pdf/2606.11766'>论文</a></td><td>本文探索了语音基础模型蒸馏的训练加速问题，旨在加快模型部署速度。
现有的堆叠方法虽然能通过逐渐增加模型深度来加速训练，但会导致模型性能下降。
◆提出了一种名为交错堆叠的新型方法，在堆叠过程中始终保持层位置不变。
◆该方法有效保留了语音基础模型每层编码的独特层特有知识，解决了传统堆叠导致的性能退化问题。
在SUPERB基准上的实验验证了该方法能在加速蒸馏训练的同时有效保持模型性能。</td></tr>
<tr><td>2026-06-09</td><td>Multi-Angular Reflectance Anisotropy Observed from UAV Multispectral Imagery<br><a href='http://arxiv.org/pdf/2606.10350'>论文</a></td><td>本文针对无人机多光谱影像因低空大视场产生的几何驱动辐射变异问题，提出了一种几何感知的多角度观测提取工作流程，从二向性反射分布函数视角量化观测几何效应。
◆提出基于运动恢复结构优化相机参数，并将正射影像均一区域重投影到多视点原始子图像的方法，实现同目标多视角下多波段反射率与几何参数的联合提取。
◆引入在观测天顶角与相对方位角域进行逐波段极坐标可视化的分析方法，直观揭示了几何效应对多角度反射率的影响规律。
◆通过草地目标实验发现十个波段均存在显著反射率各向异性，红边与近红外波段的反射率变异性高达119%至137%。
该研究证明了观测几何效应对辐射一致性具有不可忽视的影响，为无人机影像精准辐射校正提供了新依据。</td></tr>
<tr><td>2026-06-08</td><td>Minimal Solvers for Full-DoF Motion Estimation from Asynchronous Differential SfM<br><a href='http://arxiv.org/pdf/2606.09218'>论文</a></td><td>本文提出了一种基于异步光流直接进行全自由度自运动估计的新框架，旨在联合恢复角速度和线速度，以解决事件相机异步数据流对传统同步算法的挑战。
◆将微分对极约束解耦为独立的角速度和线速度分量，并推导了其面向异步数据的公式。
◆通过引入旋转动力学的一阶近似将约束方程转化为多项式形式，推导出首个代数最小五点求解器。
◆通过截断高阶角速度项，提出了一种加速求解器以满足高速场景的实时性需求。
实验表明该异步方法在精度和对时空噪声的鲁棒性上优于传统同步方法，为高速机器人的连续时间运动估计奠定了基础。</td></tr>
<tr><td>2026-06-04</td><td>S23DR 2026 Winning Solution<br><a href='http://arxiv.org/pdf/2606.06695'>论文</a></td><td>本文提出了S23DR 2026挑战赛的首胜方案，解决了从稀疏SfM、拟合深度和语义分割中进行结构化3D线框重建的问题。
◆将顶点视为条件集，利用基于Perceiver风格场景标记的条件流匹配DiT，对64个顶点标记进行去噪。
◆采用两阶段重建策略，首先通过全局通道预测粗略结构，接着利用裁剪外壳的第二通道进行细化。
◆引入小型多样本一致性步骤，有效保持了随机采样器的稳定行为。
该系统最终在私有排行榜上排名第一，取得了0.654的HSS成绩。</td></tr>
<tr><td>2026-06-02</td><td>Eliciting Complex Spatial Reasoning in MLLMs through Wide-Baseline Matching<br><a href='http://arxiv.org/pdf/2606.03577'>论文</a></td><td>本文针对多模态大语言模型在宽基线匹配中缺乏系统评估与训练框架的问题，深入探索并提升了其复杂空间推理能力。
◆构建了ReasonMatch-Bench基准，按视点位移和匹配粒度分层，揭示了当前模型在细粒度宽基线对应任务上远逊于人类的显著缺陷。
◆建立了可扩展的数据生成流水线，从大规模RGB-D视频和SfM重建等3D语料库中自动提取宽基线视图对，提供多样且可验证的监督信号。
◆提出了动态对应强化学习算法DCRL，结合图像级视点递进与点级对应课程，通过可验证奖励优化模型而无需显式思维链监督。
实验表明，DCRL显著提升了宽基线匹配及跨基准的空间推理性能，同时维持了良好的通用视觉理解能力。</td></tr>
<tr><td>2026-06-02</td><td>SAMatcher: Co-Visibility Modeling with Segment Anything for Robust Feature Matching<br><a href='http://arxiv.org/pdf/2606.03406'>论文</a></td><td>本文提出SAMatcher框架，将特征匹配转化为共可见性建模问题，突破了现有方法仅停留在像素级而缺乏跨视图共可见区域显式建模的局限。
◆不同于直接匹配局部特征，该方法首创预测共可见区域掩码和边界框作为对应估计的结构化先验。
◆基于SAM模型引入对称跨视图交互机制，实现了视图间的双向特征交换与跨视图语义对齐。
◆提出统一监督方案，通过掩码学习、框回归及掩码框一致性约束联合优化掩码预测与框定位。
实验表明该方法在大视角和尺度变化下显著优于现有方法，并证实单目分割模型可扩展至多视图推理，为图像匹配提供新视角。</td></tr>
<tr><td>2026-06-01</td><td>Edge Prediction for Roof Wireframe Reconstruction with Transformers<br><a href='http://arxiv.org/pdf/2606.02406'>论文</a></td><td>本文提出了一种受DETR启发的端到端Transformer编解码器架构，用于从稀疏SfM点云和地面语义数据中重建3D房屋屋顶线框模型。
◆提出基于语义优先级对稀疏SfM点云进行动态下采样，并融合格式塔与ADE20k类别特征进行增强。
◆将点云投影至冻结自编码器生成的潜特征图中提取额外格式塔特征编码，与点特征融合以丰富分割上下文。
◆利用交叉注意力机制，将学习到的查询嵌入直接解码为3D线框边缘。
该方法在HoHo 22k数据集上显著超越手工与学习基线，以0.6476的混合结构得分在S23DR挑战赛中夺得亚军。</td></tr>
<tr><td>2026-06-01</td><td>SAVMap: Structure-Aided Visual Mapping of Large-Scale 2.5D Manhattan Wireframes from Panoramic Video<br><a href='http://arxiv.org/pdf/2606.01939'>论文</a></td><td>本文提出了SAVMap方法，仅利用全景视频相机作为传感器输入，即可生成工业仓库货架和照明设施的语义线框地图。
◆结合语义分割网络前端，从全景视频校正图像中提取稀疏的语义结构特征点如货架角点和灯具中心，并在图像序列中对其进行跟踪。
◆提出一种结合曼哈顿网格等现实世界几何关系的约束运动恢复结构算法，从而计算构成线框地图的精确三维点。
该方法在拥有46排大型货架的仓库中得到了验证，仅用一小时全景视频便成功构建了超五千个货架元素的线框地图。
实验结果表明，该地图相对于真实值的总体平均绝对误差仅为4.8厘米，展现了出色的可扩展性与高精度。</td></tr>
<tr><td>2026-05-30</td><td>Optimizing 3D Gaussian Splatting via Point Cloud Upsampling<br><a href='http://arxiv.org/pdf/2606.00450'>论文</a></td><td>本文旨在解决3D高斯溅射性能严重依赖初始种子点质量的问题，通过点云上采样优化其初始化过程。研究评估了线性插值、三角插值、样条表面重建、移动最小二乘和Voronoi生成等多种点云上采样方法。
◆提出了一种深度引导的点提升方法，利用深度图保持与运动恢复结构重建的几何一致性。
◆揭示了不同上采样策略的适用场景，如表面重建方法适用于有机细节场景，简单插值适用于分段平滑几何。
◆证实深度引导方法在整个场景特别是无纹理区域能有效添加几何感知点。
研究最终基于场景特征和计算约束，为选择合适的上采样方法提供了实用指南，推进了对点云初始化影响3DGS质量的理解。</td></tr>
</tbody>
</table>
</div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-06-01</td><td>SOCO: Benchmarking Semantic Object Correspondence in Vision Foundation Models<br><a href='http://arxiv.org/pdf/2605.31597'>论文</a></td><td>本文提出SOCO基准，旨在解决视觉基础模型中结构化对象理解评估协议不一致和部件级监督有限的问题。
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
<tr><td>2026-05-06</td><td>Creative Robot Tool Use by Counterfactual Reasoning<br><a href='http://arxiv.org/pdf/2605.05411'>论文</a></td><td>◆ We propose a causal reasoning framework for creative robot tool use where a suitable tool for a task is correctly identified for use beyond its primary objectives.
◆ The proposed framework first discovers the causal relationships between the tool and the task by conducting simulated experiments in a dynamics model.
◆ We decouple the causal discovery problem into two complementary components: VLM-based feature suggestion and counterfactual tool generation via targeted geometric and physical feature perturbations.</td></tr>
<tr><td>2026-05-02</td><td>SIFT-VTON: Geometric Correspondence Supervision on Cross-Attention for Virtual Try-On<br><a href='http://arxiv.org/pdf/2605.01296'>论文</a> | <a href='https://github.com/takesukeDS/SIFT-VTON'>代码</a></td><td>◆ Diffusion-based virtual try-on methods achieve photorealistic synthesis through cross-attention mechanisms that transfer garment features to target body regions.
◆ However, these approaches rely on implicit learning of spatial correspondences, struggling to preserve fine details such as text and illustrations.
◆ We propose a novel approach, which we call SIFT-VTON, that utilizes SIFT keypoint matching to provide explicit geometric guidance for diffusion-based virtual try-on.</td></tr>
<tr><td>2026-05-01</td><td>TrueEBSD in MTEX: automatic image matching for correlative microscopy applications<br><a href='http://arxiv.org/pdf/2605.00703'>论文</a></td><td>◆ TrueEBSD is an open-source MATLAB program for image alignment and spatial distortion correction of images and electron backscatter diffraction (EBSD) maps.
◆ We have re-implemented TrueEBSD as an add-on to MTEX, an established toolbox for EBSD data analysis.
◆ Spatial alignment enables correlative analysis methods, such as augmenting EBSD orientation maps with data from other imaging modes.</td></tr>
<tr><td>2026-05-29</td><td>MAPRPose: Mask-Aware Proposal and Amodal Refinement for Multi-Object 6D Pose Estimation<br><a href='http://arxiv.org/pdf/2604.20650'>论文</a></td><td>本文针对杂乱场景中严重遮挡和噪声导致的6D姿态估计难题，提出了MAPRPose两阶段框架。
◆在姿态提案阶段，将2D对应关系提升至3D空间建立可靠关键点匹配，基于对应级评分生成几何一致的姿态假设选出Top-K候选。
◆在细化阶段引入AMPR模块，通过重建完整物体几何与动态调整ROI，有效缓解重度遮挡下的定位误差和空间错位。
◆设计GPU加速的RGB-XYZ重投影机制，在张量化渲染比较管线中实现单次前向传播同步细化所有姿态假设。
该方法在BOP基准上取得76.5%的最优平均召回率，精度超越FoundationPose 3.1%，且多目标推理速度提升43倍。</td></tr>
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
<tr><td>2026-06-25</td><td>Design and Performance Evaluation of Secure RF and WiFi-Based Communication in Drone Swarms via Testbed Implementation<br><a href='http://arxiv.org/pdf/2606.27028'>论文</a></td><td>◆ 论文在四架自研无人机集群上实现了RF与WiFi双链路安全通信测试床，将MAVShield及多种流加密方案集成到MAVLink遥测中进行真实飞行验证。
◆ 工作证明加密遥测数据可支持编队控制与避障等自主协同任务，而不仅限于静态通信测试。
◆ 提出改进人工势场避障算法，直接在大地坐标系计算引力和斥力，减少坐标转换、轨迹振荡和局部极小问题。
◆ 通过CPU、内存和PDR等指标系统比较MAVShield、AES-CTR、Speck-CTR、ChaCha20和Rabbit的开销与可靠性。
◆ 结果表明MAVShield性能接近明文通信，整体效率优于其他加密方案，同时经代数密码分析和Wireshark流量分析验证其抗密钥恢复与保密能力。</td></tr>
<tr><td>2026-06-25</td><td>G2DP: Diffusion Planning with Spatio-Temporal Grid Guidance<br><a href='http://arxiv.org/pdf/2606.26017'>论文</a></td><td>◆提出G2DP，一种网格引导的扩散式自动驾驶规划器，解决传统扩散规划随机性强、闭环执行中安全与路线约束不足的问题。
◆其核心创新是构建可微的时空代价体，将未来占用概率分布与路线进度图融合，形成密集环境约束。
◆方法把该代价体建模为连续安全能量函数，并在推理去噪过程中直接注入梯度，引导轨迹远离碰撞区域并保持路线进展。
◆相比依赖稀疏几何查询或后处理优化的方法，G2DP具备更强的场景感知能力，尤其适合复杂交互交通。
◆实验表明，G2DP在nuPlan闭环评测达到SOTA，并在interPlan和DeepScenario零样本迁移中保持优异鲁棒性。</td></tr>
<tr><td>2026-06-24</td><td>Explainable Control Framework (XCF) based on Fuzzy Model-Agnostic Explanation and LLM Agent-Supported Interface<br><a href='http://arxiv.org/pdf/2606.25941'>论文</a></td><td>论文提出面向复杂闭环控制器的可解释控制框架XCF，旨在让人类理解控制动作的产生原因和控制器工作机制。
◆XCF具有模型无关性，可解释黑箱或复杂控制器，并能结合系统响应动态进一步细化局部解释。
◆提出HFMAE-C方法，用模糊逻辑系统近似控制器行为与系统动力学，以IF-THEN规则揭示决策逻辑。
◆该方法提供样本、局部、域和全局多层级解释，并用显著性值量化各系统状态对控制动作的贡献。
◆构建LLM Agent支持的交互界面，可自动分析用户需求、选择算法、生成自然语言解释报告并支持咨询。
倒立摆和Turtlebot避障实验表明，该框架相比主流可解释控制方法具有更好的有效性与实用性。</td></tr>
<tr><td>2026-06-25</td><td>Large-Scale Tunnel Air-Ground Collaboration With FLISP: Fast LiDAR-IMU Synchronized Path Planner<br><a href='http://arxiv.org/pdf/2606.25393'>论文</a> | <a href='https://github.com/ArchibaldGuo/FLISP.git'>代码</a></td><td>◆ FLISP提出一种面向水电隧道巡检的无地图UGV-UAV协同路径规划框架，避免了传统建图、栅格化和采样规划带来的计算开销与不稳定性。
◆ 其核心创新是用车载单套LiDAR-IMU同时驱动地面车和无人机的同步路径生成，降低系统复杂度并减少状态估计漂移影响。
◆ 针对不同平台，FLISP为UGV设计增强萤火虫算法实现避障，为UAV设计动态迭代优化器生成可飞行轨迹。
◆ 论文还提出分层轨迹细化策略，在不依赖全局地图的情况下保证运动学可行性与协同一致性。
◆ 在1.2 km真实运行隧道中，FLISP实现100%成功率和约7 ms延迟，相比栅格法快7倍、相比采样法快约三个数量级，展示了在退化线性基础设施巡检中的可扩展性。</td></tr>
<tr><td>2026-06-23</td><td>Grounding Generative Policies in Physics: Optimization-Guided Diffusion for Robot Control<br><a href='http://arxiv.org/pdf/2606.24208'>论文</a></td><td>◆论文提出一种推理时优化引导的扩散框架，用于弥合生成式机器人策略与真实物理可执行性之间的“具身差距”。
◆其核心创新是将扩散反向采样中的随机扰动替换为优化得到的修正量，使生成结果在贴近学习先验的同时满足约束。
◆该方法无需重新训练扩散模型，即可在采样过程中加入可达性、避障、闭环可跟踪性等硬约束或软惩罚。
◆实验覆盖灵巧抓取和动态操作，并验证了方法在不同机器人具身形态上的迁移能力。
◆相比投影和梯度引导基线，该方法更好保持抓取质量，并显著提升控制器可执行性与任务成功率，最高提升20和23个百分点。</td></tr>
<tr><td>2026-06-22</td><td>Verifiable Foundation Models for Robot Safety<br><a href='http://arxiv.org/pdf/2606.23754'>论文</a></td><td>◆提出FEARL框架，将机器人策略拆分为大型Controller和小型Safety模块，兼顾基础模型的感知推理能力与安全可验证性。
◆Controller负责高维多模态感知和任务理解，Safety模块仅基于低维安全传感器信息及有界上下文嵌入输出最终动作。
◆该设计把碰撞避免、工作空间边界等安全约束的形式化验证范围缩小到Safety模块，使现有验证工具可实际应用。
◆论文证明这种模块化分解不会显著牺牲任务能力，并在三个仿真机器人任务中测试了多种控制器骨干和训练方式。
◆实验还包括现成视觉-语言-动作模型，并展示了从仿真到真实机器人的迁移，说明低维安全接口具有实践价值。</td></tr>
<tr><td>2026-06-22</td><td>LP-NavOA: Integrated Local Navigation and Obstacle Avoidance for Humanoid Robots under Limited Perception<br><a href='http://arxiv.org/pdf/2606.23249'>论文</a></td><td>◆ LP-NavOA面向短程、部分可观测感知下的人形机器人，实现了局部导航、避障与稳定全身运动的一体化框架。
◆ 其先训练射线感知条件下的PPO运动骨干，采用机器人中心的圆形航向-速度指令和共享安全过滤器，提升高速指令跟踪能力。
◆ 在冻结运动骨干后，利用A-star和航点教师数据蒸馏循环局部规划器，部署时仅改写航向指令，避免破坏全身控制策略。
◆ 系统运行只需本体感知、短程距离感知和机体坐标系目标方向，不依赖全局地图、连续航点流或外部规划器。
◆ 实验显示其能完成绕障和遮挡后目标恢复，将准时到达率从38–40%提升到85–97%，并减少擦碰式前进。
◆ 消融验证了动态路线塑形、教师主动数据采集和圆形指令接口的重要性，Unitree G1分析也表明其具备硬件可执行性。</td></tr>
<tr><td>2026-06-22</td><td>Scalable Online Flight Trajectory Optimization via Sequential Quadratic Programming for Urban Air Mobility in Ultra Low-Altitude Airspace<br><a href='http://arxiv.org/pdf/2606.23008'>论文</a></td><td>◆提出面向超低空城市空域UAM的在线轨迹优化框架，将城市几何约束、运行限制与飞行器全自由度动力学统一纳入SQP求解。

◆创新地不依赖预先生成的无障碍走廊，而是在每次迭代中实时重建分离超平面约束，实现障碍规避与动力学优化的联合在线求解。

◆引入可变尺度四叉树分解，在复杂城市级三维环境中控制计算规模，提升高密度、高速飞行场景下的实时性与可扩展性。

◆该方法能够随参考轨迹和环境变化动态更新约束，更适合真实UAM运行中的在线重规划需求。

◆在五个真实城市环境中与传统SQP、iLQR和DDP对比，CPU平台上实现100%成功率和安全净空率，验证了其鲁棒性与实用价值。</td></tr>
<tr><td>2026-06-21</td><td>Any-Body Guard: Universal Safeguarding for Manipulation Policies via Action Masking<br><a href='http://arxiv.org/pdf/2606.22278'>论文</a></td><td>◆论文提出X-Safe，一种面向机器人操作策略的通用安全保护方法，通过动作遮蔽在执行前过滤可能导致碰撞的动作。
◆其核心创新是直接在机器人构型空间中推理，从而为避碰提供形式化的概率安全保证。
◆该方法仅依赖物体级准静态场景表示和机械臂正运动学模型，不需要额外数据或针对不同机器人重新设计控制器。
◆相比启发式回退控制或复杂前向不变性分析，X-Safe更易迁移到不同形态、任务和场景，并减少对任务性能的保守影响。
◆作者在仿真和真实硬件上的多种机器人与策略中验证了方法，实验显示硬件无碰撞且安全保证得到经验支持。</td></tr>
<tr><td>2026-06-19</td><td>Backpropagating Through Simulation: Analytic Policy Gradients for Sample and Learning Efficient Differentiable Continuous Control<br><a href='http://arxiv.org/pdf/2606.21525'>论文</a></td><td>◆本文提出Analytic Policy Gradients（APG），利用可微环境将回报视为策略参数的可微函数，直接通过仿真反向传播计算精确梯度，替代高方差采样估计。

◆APG显著提升连续控制中的样本效率，针对PPO需要大量交互的问题，在多种任务上进行系统对比验证。

◆论文设计了包含环境步数与梯度步数的多轴评估协议，从而区分样本效率和计算效率。

◆为解决长时域任务中的梯度衰减问题，提出分段反向传播，并结合蒙特卡洛或critic引导的bootstrap机制。

◆实验覆盖从点质量导航到刚体推动和7自由度机械臂 reaching 的不同复杂度任务，并通过消融分析研究分段长度与bootstrap策略的影响。</td></tr>
<tr><td>2026-06-19</td><td>Reference-Free, Long-Horizon Trajectory Optimization for Aggressive Autonomous Driving in Milliseconds<br><a href='http://arxiv.org/pdf/2606.21486'>论文</a></td><td>◆论文面向激进自动驾驶，研究如何在无参考轨迹、无热启动条件下，毫秒级求解长视距、全车辆动力学的最优控制问题。
◆作者通过分析车辆动力学刚性特征，证明低阶A稳定积分方法更适合该类OCP，求解速度相比其他方法可提升最高两个数量级。
◆论文系统揭示了内点法中障碍参数更新策略和Hessian不定性保护机制对非线性求解鲁棒性的关键影响。
◆提出基于动态平衡的高效初值生成方法，将初始不可行性最多降低四个数量级，从而显著提升实时求解能力。
◆实验在高保真BeamNG仿真中实现260米视距仅55毫秒的计算时间，并展示高速避障中漂移可成为生成可行轨迹的必要行为。</td></tr>
<tr><td>2026-06-18</td><td>Agentic AutoResearch forSpace Autonomy: An Auditable, LLM-Driven Research Agent for Aerospace Control Problems<br><a href='http://arxiv.org/pdf/2606.20394'>论文</a></td><td>◆ 提出AutoResearch框架，用大语言模型作为离线研究代理，自动阅读问题描述、修改训练脚本、运行实验并记录结果，用于航天控制策略开发。

◆ 明确区分“研究代理”和“ onboard 控制器”：LLM只负责离线发现策略，最终部署的是训练好的控制策略，避免LLM直接操控航天器。

◆ 引入内嵌可信度审计层，要求结果通过种子噪声测量、最佳配置重采样验证和留一编辑剪枝三重检验后才被认可。

◆ 在相对交会和带安全约束的避障对接两个任务上，框架无需改动即可应用，并以最优控制基准校准性能。

◆ 实验显示，经审计的策略显著超过种子噪声，而无定向搜索无法达到同等效果；在对接任务中，随机搜索甚至找不到可行策略。</td></tr>
<tr><td>2026-06-18</td><td>Lagrange: An Open-Vocabulary, Energy-Based Sparse Framework for Generalized End-to-End Driving<br><a href='http://arxiv.org/pdf/2606.20274'>论文</a></td><td>◆ 提出Lagrange，一个面向开放世界端到端驾驶的开放词汇、能量驱动稀疏框架，兼顾计算效率与泛化能力。
◆ 采用Masked Latent Fields，利用VLM将类别无关目标提案编码为连续语义视觉token，避免依赖稠密占据或封闭类别查询。
◆ 设计意图驱动的掩码交叉注意力机制，按时间过滤与驾驶目标无关的实体，提升复杂场景下的决策聚焦性。
◆ 将感知结果解码为空间连续隐式能量场，使规划可在连续坐标中进行碰撞规避与语义推理。
◆ 将决策建模为跨能量场的拉格朗日作用量最小化问题，从而显式满足车辆运动学约束并生成可执行轨迹。
◆ 在nuScenes和长尾CODA基准上的离线实验表明，该方法在开放世界鲁棒性、可解释性和运动学可行性方面具有潜力。</td></tr>
<tr><td>2026-06-22</td><td>Stable Transformer-Actor-Critic Model Predictive Control: A Contraction Analysis Approach<br><a href='http://arxiv.org/pdf/2606.20197'>论文</a></td><td>◆提出了一种Transformer-Actor-Critic MPC架构，用于处理复杂非凸控制任务，并同时关注闭环稳定性与鲁棒性保证。
◆首次证明Transformer网络可满足全局增量输入到状态稳定性δISS，为序列模型用于控制提供理论基础。
◆利用黎曼收缩理论分析物理系统与预测神经网络之间的互联系统动态，建立稳定性判据。
◆将理论推导得到的稳定性与鲁棒性界作为训练正则项，使学习策略具备可认证的鲁棒性。
◆在非线性3D无人机目标到达与避障任务中验证了方法的有效性，展示其在复杂动态场景中的应用潜力。</td></tr>
<tr><td>2026-06-18</td><td>Frequency-Aware Flow Matching for Continuous and Consistent Robotic Action Generation<br><a href='http://arxiv.org/pdf/2606.20135'>论文</a></td><td>◆论文提出Frequency-Aware Flow Matching（FAFM），解决现有机器人流匹配/扩散策略依赖离散动作块、难以适配不同控制频率且动作不连续的问题。
◆方法将离散动作序列通过DCT变换到频域，在频域系数上进行流匹配，再用余弦基展开重建连续动作。
◆为提升时间一致性，FAFM加入一阶时间导数正则，相当于Sobolev约束，可抑制高频误差和突变动作。
◆该方法不增加额外网络参数，能无缝用于独立流匹配策略和视觉-语言-动作模型。
◆在仿真、LapGym、LIBERO及真实Franka机器人实验中，FAFM提升成功率、平滑性、收敛速度、多模态表达能力，并增强对机械偏差和混合频率数据的鲁棒性。</td></tr>
<tr><td>2026-06-18</td><td>Contraction-based Neural Control for Cooperative Aerial Payload Transportation with Variable-length Cables<br><a href='http://arxiv.org/pdf/2606.20127'>论文</a></td><td>◆ 提出一种面向多无人机变长度缆绳吊运刚体载荷的神经非线性控制框架，解决协同空运中的轨迹跟踪与避障问题。
◆ 将系统动力学重构为载荷运动与缆绳长度动力学解耦的形式，使不同控制通道可模块化设计。
◆ 针对载荷子系统，联合训练神经控制收缩度量控制器与神经反馈控制器，以满足收缩条件并提升非线性跟踪稳定性。
◆ 针对缆绳长度子系统，设计利用可变长度自由度的控制律，实现通过障碍或门洞时的空间调整。
◆ 仿真验证了该框架可实现刚体载荷轨迹跟踪和门洞穿越，展示了其在复杂环境协同运输中的潜力。</td></tr>
<tr><td>2026-06-17</td><td>One Demo is Worth a Thousand Trajectories: Action-View Augmentation for Visuomotor Policies<br><a href='http://arxiv.org/pdf/2606.19586'>论文</a></td><td>◆提出一种从单条真实眼在手示教中生成大量训练数据的动作-视角增强框架，缓解机器人初始位姿变化和未知障碍导致的分布外问题。
◆设计适用于大视场鱼眼相机的Gaussian Splatting重建方法，可生成逼真的鱼眼图像序列，并支持在三维场景中编辑加入未见物体。
◆结合轨迹优化生成平滑、无碰撞且适合视角渲染的动作轨迹，保证增强数据在视觉和物理执行上都更可信。
◆该方法仅需便携式夹爪和单个鱼眼相机采集演示，显著降低了大规模机器人示教数据收集成本。
◆仿真和真实实验表明，该增强框架能提升多种操作任务的成功率，尤其在含障碍物、需要避障的增强场景中效果明显。</td></tr>
<tr><td>2026-06-17</td><td>pdSTL: Probabilistic Differentiable Signal Temporal Logic for Stochastic Systems<br><a href='http://arxiv.org/pdf/2606.19561'>论文</a></td><td>◆ 提出pdSTL框架，将概率语义与可微鲁棒性统一起来，使随机动力学和感知噪声下的机器人能够在信念轨迹上进行时序逻辑约束优化。  
◆ 采用区间值概率语义，组合式地沿STL语法树传播保守满足概率边界，从而提供形式化的概率安全保证。  
◆ 将时序鲁棒性评估重构为类似LSTM的递归展开，实现线性时间、端到端可微的STL监测与轨迹优化。  
◆ 相比传统确定性可微STL，pdSTL显式考虑信念空间不确定性，因此在真实扰动环境中能更稳定地保持安全裕度。  
◆ 通过仿真避障、换道和Crazyflie四旋翼真实飞行实验验证了方法的效率、可优化性和在随机系统中的实际安全优势。</td></tr>
<tr><td>2026-06-17</td><td>Congestion-Aware Robot Tour Planning in Crowded Environments<br><a href='http://arxiv.org/pdf/2606.19031'>论文</a></td><td>◆本文提出了一种面向拥挤环境的概率式机器人巡游规划方法，专门解决人群对机器人导航效率和路径选择的影响。

◆其核心创新在于显式建模“人群拥堵”因素，而不是仅将行人视为局部避障中的动态障碍物。

◆论文利用CLiFF地图学习人流运动模式，可根据初始观测预测行人轨迹和未来拥堵分布。

◆基于这些预测，系统在线构建并求解马尔可夫决策过程，从而为机器人选择更高效、更少受人群干扰的巡游路线。

◆该方法具备可扩展性，能够随着新行人观测不断重新规划，并在真实购物中心人群数据集上验证了有效性。</td></tr>
<tr><td>2026-06-17</td><td>WST Multi-Object Spectrograph Fiber Positioners:Development of a 32,000-Unit Precision Robotic System<br><a href='http://arxiv.org/pdf/2606.18957'>论文</a></td><td>◆ 论文提出了面向WST多目标光谱仪的超大规模光纤定位系统方案，覆盖3.1平方度视场，包含3万台低分辨率和2000台高分辨率定位器。

◆ 其核心挑战是让每个密集排布的机器人定位器达到5微米RMS精度，规模较DESI、4MOST等现有装置提升六倍以上。

◆ 为降低32,000个精密机构量产风险，项目采用多概念并行开发策略，由EPFL、AIP、UKATC和AAO合作推进。

◆ 论文创新性比较了四种定位器架构，包括6.2毫米间距、63单元三角模块以及新的内联模块化概念。

◆ 研究建立了系统化测试指标，涵盖定位精度、重复性、重配置速度、避碰能力和可制造性，为2026–2027年概念筛选提供依据。

◆ 当前原型测试表明关键性能指标具备可行性，为WST在2040年代初实现首光奠定了技术基础。</td></tr>
</tbody>
</table>
</div>

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-25</td><td>Ordinal Neural Collapse as a Representation Prior for Visual Navigation<br><a href='http://arxiv.org/pdf/2606.26839'>论文</a></td><td>论文提出ORION，针对端到端视觉导航中编码器仅受动作损失间接监督、易学到动作无关表征的问题，引入更具结构性的表征先验。
◆ 将导航动作从Far Left到Far Right视为天然有序类别，显式利用动作间的序关系来组织视觉表征空间。
◆ 鼓励各类别表征沿单一判别轴顺序排列，同时压制类内离轴方差，减少模糊场景下的动作不一致。
◆ 将预训练编码器接入扩散式导航框架，并进行端到端微调，实现表征学习与策略生成的统一优化。
◆ 在仿真和真实环境中均取得更高成功率和目标推进效果，尤其在复杂多岔路口等视觉干扰强场景中优势明显。</td></tr>
<tr><td>2026-06-24</td><td>NavIsaacLab: Generating Realistic Crowd via Parallel Robot Learning for Benchmarking Human-aware Navigation<br><a href='http://arxiv.org/pdf/2606.26265'>论文</a></td><td>◆NavIsaacLab提出了一个面向人类感知导航的综合仿真、训练与基准测试框架，弥补了高质量多样化人群场景数据不足的问题。
◆框架基于Isaac Lab，支持GPU并行物理仿真和照片级真实渲染，可为机器人提供实时、准确的3D视觉传感反馈。
◆不同于依赖手工规则的传统平台，NavIsaacLab引入轨迹扩散模型生成更真实、可控的人群移动轨迹。
◆其结合对抗式运动学习控制器，实现具备物理一致性的人体行走与交互行为模拟。
◆通过整合多尺度、多样化场景，该框架为现有人类感知导航算法提供了更真实、系统且可复现的评测基准。</td></tr>
<tr><td>2026-06-24</td><td>Learning Robot Visual Navigation in Crowds via Intention-Aware Scene Representations<br><a href='http://arxiv.org/pdf/2606.26047'>论文</a></td><td>◆论文提出iCrowdNav，一种面向拥挤人群的视觉导航方法，使机器人能从第一视角视觉观测中同时理解行人意图与环境结构约束。
◆不同于将行人简化为2D点的传统方法，该方法利用更丰富的人体姿态、运动和场景视觉线索构建意图感知场景表征。
◆其时空编码器用于提取场景占据信息，帮助机器人理解可通行空间和动态障碍分布。
◆提出Intent-Interact Former，通过注意力机制建模人体姿态与人际交互，从而推断行人的运动意图。
◆这些特征被融合为紧凑状态嵌入，用于深度强化学习策略训练，并在仿真和真实部署中均优于基线方法。</td></tr>
<tr><td>2026-06-24</td><td>Event-Adaptive Motion Planning with Distilled Vision-Language Model in Safety-Critical Situations<br><a href='http://arxiv.org/pdf/2606.25629'>论文</a></td><td>本文提出EAMP框架，面向安全关键导航中由动态智能体异常行为引发的语义事件，实现高层语义推理与低层运动控制的实时协同。
◆设计提示可配置语义事件触发器PC-SET，仅在检测到短时行为异常时激活语义干预，避免频繁调用大VLM带来的控制延迟。
◆提出事件触发的蒸馏SemNav-VLM，通过物理验证的语义蒸馏，将异常事件映射为离散策略级决策。
◆构建语义模型预测控制SMPC，把策略决策转化为优化目标和几何参考的动态重配置。
◆实验表明，EAMP在安全关键物流场景中提升动态安全裕度，同时保持实时效率，优于现有基线方法。</td></tr>
<tr><td>2026-06-24</td><td>GROVE: Grounded Pedestrian Simulation via Natural Language for Interactive Social Robot Navigation<br><a href='http://arxiv.org/pdf/2606.25504'>论文</a></td><td>◆提出GROVE，一个基于自然语言的行人仿真框架，可将文本提示直接转化为面向社交机器人导航的复杂场景。
◆支持紧急、排队、常规等预设，也允许自由输入提示，从而降低手工构建行人场景的成本。
◆通过长程人类行为、中程行人导航和短程人机社交交互等模块，分别保证仿真的真实性与合理性。
◆各模块会根据文本意图进行调节，并动态选择合适的SotA方法，以刻画不同情境下的行人行为细节。
◆系统已集成到Isaac Sim、Gazebo和RViz，并在住宅、医院、办公室等环境中验证，生成更真实、多样且具挑战性的社交导航测试场景。</td></tr>
<tr><td>2026-06-23</td><td>From Open Waters to Enclosed Cabins: ProteusVPR for Cross-Scene Visual Place Recognition in Maritime Perception and Cabin Inspection<br><a href='http://arxiv.org/pdf/2606.24234'>论文</a></td><td>◆论文聚焦船舶开放甲板与封闭舱室之间的跨场景视觉地点识别难题，指出现有VPR方法在海事机器人巡检中泛化不足。
◆提出ProteusVPR两阶段框架，先用任意标准VPR模型进行候选检索，再通过精细化模块提升定位精度。
◆创新设计几何-视觉估计网络，融合检索图像与前两帧时序信息，并引入几何描述子、局部仿射坐标系和相机方位角编码。
◆构建XHZ数据集，包含8K全景船载图像、多层舱室、甲板过渡区域及严格查询/数据库划分，支持更真实评测。
◆实验表明ProteusVPR可稳定增强多种VPR骨干网络，平均定位误差降低超过60%，展现出强鲁棒性和实用价值。</td></tr>
<tr><td>2026-06-23</td><td>Deep Learning Approaches for 3D Medical Scene Completion: From Geometric Modeling to Generative Paradigms<br><a href='http://arxiv.org/pdf/2606.24180'>论文</a></td><td>◆本文系统梳理了2016—2026年3D医学场景补全的发展脉络，覆盖从SSCNet体素语义补全到生成式扩散先验与高斯泼溅渲染结合的新范式。

◆论文总结了体素网格、点云学习、隐式神经场、Transformer、扩散模型和3D高斯基元等表示范式的演进。

◆其核心贡献是构建了较完整的分类体系，帮助理解不同方法在几何建模、语义补全和生成能力上的差异。

◆论文强调了生成式模型与实时渲染技术融合对高质量、可交互3D场景补全的推动作用。

◆最后，论文归纳了当前挑战，并提出下一代3D医学场景补全系统的研究方向。</td></tr>
<tr><td>2026-06-23</td><td>NavWM: A Unified Navigation World Model for Foresight-Driven Planning<br><a href='http://arxiv.org/pdf/2606.24101'>论文</a></td><td>◆NavWM提出统一的导航世界模型，将感知、潜在世界推理、动作预测与可控视觉生成整合到同一框架中，缓解传统导航策略的短视决策问题。

◆其核心创新是引入潜在世界token，用于提炼环境中的几何与语义先验，增强智能体对空间结构和时序动态的理解。

◆论文设计了基于anchor的多模态轨迹预测机制，生成多样化候选动作，避免确定性策略导致的模式坍塌。

◆NavWM将生成式世界模型用于闭环规划，通过“视觉预见”模拟未来状态并评估不同路径，从而选择更优导航决策。

◆在多种机器人数据集上的实验表明，NavWM在高保真未来状态生成和零样本导航成功率上均显著优于现有方法。</td></tr>
<tr><td>2026-06-22</td><td>DVL-DeepONet: A Physics-Guided Operator Learning for Resilient Underwater Navigation<br><a href='http://arxiv.org/pdf/2606.23502'>论文</a></td><td>◆提出DVL-DeepONet，一种物理引导的深度神经算子框架，用于在DVL波束缺失、噪声干扰或传感器配置受限时实现鲁棒水下速度估计。

◆该方法学习从时序惯性/DVL观测到AUV速度向量的非线性算子，突破传统模型在复杂海洋环境中对完整波束和精确传感器的依赖。

◆引入DVL测量物理一致性约束，使网络预测不仅依赖数据驱动学习，还符合DVL几何与测量机理。

◆设计了三类应用变体，分别支持惯性/DVL融合下的抗噪估计、仅DVL条件下的速度学习，以及缺失波束测量恢复。

◆基于约10,000米真实AUV航行实验验证，结果显示其相较模型方法和学习基线整体性能提升约40%，增强了低成本和受损感知场景下的导航韧性。</td></tr>
<tr><td>2026-06-23</td><td>SkyJEPA: Learning Long-Horizon World Models for Zero-Shot Sim-to-Real Control of Quadrotors<br><a href='http://arxiv.org/pdf/2606.23444'>论文</a></td><td>◆提出SkyJEPA，将联合嵌入预测架构引入四旋翼高频实时控制，避免自回归预测误差随时间累积的问题。
◆构建潜在空间动力学模型，实现面向长时域的稳定预测，提升无人机在不确定环境中的决策能力。
◆设计物理启发式prober，将冻结的潜在表示映射为可解释状态，使长时域预测更具物理一致性。
◆将学习到的世界模型与采样式最优控制结合，并部署在嵌入式硬件上实现实时控制。
◆提出自动化、结构化数据生成流程，减少对昂贵且有风险的真实飞行数据采集依赖。
◆通过开环预测和户外闭环实验验证其零样本仿真到现实迁移能力及跨工况泛化性能。</td></tr>
<tr><td>2026-06-22</td><td>Humanoid-OmniOcc: Stereo-Based Full-View Occupancy Dataset for Embodied AI<br><a href='http://arxiv.org/pdf/2606.22971'>论文</a> | <a href='https://d-robotics-ai-lab.github.io/humanoid-omniocc'>代码</a></td><td>◆提出Humanoid-OmniOcc，一个面向类人机器人具身智能的全景双目体素占据数据集，弥补现有自动驾驶数据集在视角、场景和几何先验上的局限。

◆数据集覆盖15个多样化仿真室内场景和5个真实环境，包含超过15.5万样本，具备较强的场景与风格多样性。

◆引入Real2Sim2Real闭环范式，用真实传感器规格构建物理准确仿真，再生成大规模标注数据并在真实采集上验证。

◆提出Humanoid Surround Stereo-guided Occupancy模型，利用双目深度先验提升2D到3D占据预测的准确性。

◆实验表明该方法优于单目基线，并能泛化到未见仿真场景和真实环境，验证了数据集与闭环设计的有效性。</td></tr>
<tr><td>2026-06-19</td><td>Long-Distance Real-World Navigation of the Legged-Wheeled Robot Go2-W Using Deep Reinforcement Learning<br><a href='http://arxiv.org/pdf/2606.21387'>论文</a></td><td>◆本文面向商用腿轮机器人Go2-W，构建了基于深度强化学习的运动控制器与自主导航系统，验证其在真实长距离场景中的可用性。
◆作者将此前用于四足机器人的仅依赖本体感知的策略扩展到16自由度腿轮机器人，实现了无需外部地形感知的稳健运动控制。
◆论文发现轮式运动会使负载集中于髋关节并导致过热，提出通过负载分配来抑制热集中、提升持续行驶能力的策略。
◆系统在筑波挑战2025中完成约2.8公里自主导航，覆盖人行道、公园和楼梯等复杂环境。
◆实验表明，该方法能在不因过热停机的情况下完成长距离真实世界导航，推进了腿轮机器人从实验室控制到实际应用的落地。</td></tr>
<tr><td>2026-06-18</td><td>UNSEEN: Uncertainty-aware Navigation via Sparse Estimation in Unknown Environments<br><a href='http://arxiv.org/pdf/2606.20755'>论文</a></td><td>◆ UNSEEN提出一种仅依赖前置相机的统一导航框架，在未知环境中紧耦合定位、稀疏建图与规划，降低对多传感器和环境先验的依赖。
◆ 其核心创新是显式建模并传播位姿、地图和感知质量的不确定性，使规划不只追求到达目标，也主动选择有利于估计的运动。
◆ 系统以6Hz在线估计带不确定性的稀疏地图和机器人位姿，并在滚动时域内联合优化任务进展与定位精度。
◆ 相比传统松耦合管线和只优化单模块的感知感知方法，UNSEEN将运动指令与视觉感知的相互影响纳入同一决策闭环。
◆ 仿真和真实实验表明，UNSEEN-SLAM将绝对平移误差降低9.8%，UNSEEN-Plan最高提升45%估计精度，并实现100%任务成功率。</td></tr>
<tr><td>2026-06-18</td><td>Fast Human Attention Prediction for Fixation-guided Active Perception in Autonomous Navigation<br><a href='http://arxiv.org/pdf/2606.20491'>论文</a></td><td>◆提出GazeLNN，一种面向机器人主动感知的轻量级人类扫描路径预测模型，用Liquid Neural Networks作为循环核心，并结合MobileNetV3提取视觉特征。

◆模型以自回归方式根据当前图像和历史注视信息连续预测 fixation heatmap，从而模拟人类结构化视觉注意过程。

◆在仅需0.61 GFLOPs的计算量下，GazeLNN在MIT Low Resolution数据集上达到0.47 ScanMatch，取得领先性能。

◆相比现有循环式基线方法，该模型在多项指标上表现更优，同时将计算成本降低99.40%，推理速度最高提升6倍。

◆论文进一步将GazeLNN嵌入强化学习训练的主动相机-机器人控制策略，实现由人类注视引导的自主导航感知，并在真实空中机器人上完成验证。</td></tr>
<tr><td>2026-06-18</td><td>Slow Brain, Fast Planner: Latency-Resilient VLM-Augmented Urban Navigation<br><a href='http://arxiv.org/pdf/2606.20458'>论文</a></td><td>◆论文指出城市人行道导航中存在“轨迹评分鸿沟”：学习式规划器能生成好候选轨迹，但常因缺乏高层场景理解而选错。

◆提出VLM-Planner接口，让视觉语言模型从规划器候选轨迹中选择更合理的索引，而非用端到端VLA模型替代原规划器。

◆针对VLM 1–3秒推理延迟，设计无需训练的延迟鲁棒轨迹级融合层，将过期VLM选择通过几何相似度和指数衰减转化为实时评分。

◆实验显示，在约2000个真实复杂场景中，VLM选择相比规划器原最优输出将ADE降低30%，尤其改善路口和行人交互等难例。

◆仿真和实机验证表明，该方法在最高5秒延迟下仍保持80%以上成功率，并能在校园人行道上稳定运行。</td></tr>
<tr><td>2026-06-18</td><td>Vision-Reasoning-Guided Occlusion Removal from Light Fields<br><a href='http://arxiv.org/pdf/2606.19985'>论文</a></td><td>◆ 提出一种视觉推理引导的光场遮挡去除框架，将光场积分的物理可见性恢复能力与视觉语言模型的语义推理能力结合起来。

◆ 方法先利用多视角光场积分抑制前景植被等密集遮挡，生成可见性增强的初始场景表示。

◆ 引入视觉语言模型作为条件语义先验，在观测约束下修复退化结构并恢复细节，提升复杂自然场景中的重建质量。

◆ 设计多样本融合策略，将多个生成假设聚合为一致结果，从而减少幻觉伪影并增强恢复稳定性。

◆ 在合成和真实数据集上取得先进性能，在4个合成光场基准场景中获得最高平均SSIM，并展现出对结构化和非结构化采集条件的良好泛化能力。</td></tr>
<tr><td>2026-06-17</td><td>Sensor Configuration Matters: A Systematic Evaluation of Multimodal SLAM on Quadruped Robots<br><a href='http://arxiv.org/pdf/2606.19067'>论文</a></td><td>◆本文针对四足机器人在足端冲击、机械振动和快速旋转下SLAM性能不稳定的问题，系统评估了传感器硬件配置对多模态SLAM的影响。
◆作者基于ANYmal D的GrandTour数据集，对视觉、视觉惯性、激光-视觉-惯性SLAM方法进行了统一比较。
◆论文量化分析了相机模态、快门类型和IMU等级在定位精度、鲁棒性与计算资源消耗之间的权衡。
◆实验发现，双目配置整体优于单目和RGB-D，全局快门相比卷帘快门更能减少运动导致的跟踪失败。
◆一个关键发现是，在剧烈腿式运动中，标准惯性融合反而可能削弱以视觉为主的SLAM性能。
◆论文最终给出了面向敏捷四足机器人的传感器载荷设计建议，为可靠自主导航提供了实践依据。</td></tr>
<tr><td>2026-06-15</td><td>SidewalkBench: Benchmarking Visual Navigation on Urban Sidewalks<br><a href='http://arxiv.org/pdf/2606.16953'>论文</a></td><td>本文提出了SidewalkBench，一个专为城市人行道视觉导航设计的综合基准，填补了该领域缺乏统一评估标准的空白。
◆基于NVIDIA Isaac Sim构建，实现了对多样化高保真人行道环境（含程序生成和真实扫描场景）的GPU加速仿真。
◆引入了丰富的基于事件的反应式行人行为及灵活高效的动画，支持在逼真的真实设定下进行模型标准化评估。
研究在330个单元测试、800个行人反应场景和105个长视距场景上对9种模型进行了全面评估。
结果揭示行人交互与长视距鲁棒性是现有模型的关键瓶颈，而利用合成数据扩大训练规模是极具前景的解决方案。</td></tr>
<tr><td>2026-06-15</td><td>MVOFormer: Flow-Semantic Transformer for Robust Monocular Visual Odometry<br><a href='http://arxiv.org/pdf/2606.16474'>论文</a></td><td>本文提出MVOFormer框架，旨在解决现有单目视觉里程计方法缺乏可解释互补特征或架构过于复杂的问题，从而显著提升鲁棒性与跨域泛化能力。
◆提出流-语义双分支编码器，协同融合密集几何运动线索与面向对象的语义先验，显式区分静态结构与动态干扰物。
◆设计迭代多模态解码器，实现由粗到细的位姿细化，并在融合多模态表征时动态抑制对不可靠区域的注意力。
实验表明，在无需任何目标域微调的情况下，该方法展现出卓越的零样本泛化能力。
在TartanAir和KITTI等多个基准测试中，MVOFormer显著超越了以往基于学习的帧间方法。</td></tr>
<tr><td>2026-06-15</td><td>SemGeoNav:A Safety-Guided Visual Navigation Approach with Semantic Reasoning and Geometric Planning<br><a href='http://arxiv.org/pdf/2606.16400'>论文</a></td><td>现有端到端视觉导航模型缺乏显式几何约束导致避障不可靠，而传统几何规划器难以处理高维视觉目标。为此，本文提出了一种新型分层视觉导航框架SemGeoNav，实现了基于图像的鲁棒导航并显著提升了避障能力。
◆将端到端模型的高级语义推理与基于几何方法的可靠局部规划能力进行紧密集成。
◆引入时间轨迹平滑机制以确保机器人连续且稳定的运动。
真实环境中四足机器人的实验表明，SemGeoNav在成功率和导航时间上均优于ViNT和NoMaD等代表性方法。</td></tr>
</tbody>
</table>
</div>

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-25</td><td>BOWConnect: Parallel Bayesian Optimization over Windows with Learned Local Cost Maps for Sample-Efficient Kinodynamic Motion Planning<br><a href='http://arxiv.org/pdf/2606.27292'>论文</a> | <a href='https://bow-connect.github.io/'>代码</a></td><td>◆提出BOWConnect，一种面向动力学约束运动规划的双向并行采样框架，针对高维状态空间样本效率低、启发式代价不可靠和窄通道困难三大问题。
◆将“窗口贝叶斯优化”作为学习型转向函数，使各并行工作线程在线学习局部代价地图与约束，引导采样到可行、无碰撞控制。
◆采用从起点和目标区域同时扩展的双向树结构，显著提升复杂环境中的探索与连接效率。
◆引入空间哈希进行快速连接查询，并结合边值问题求解器生成满足运动学/动力学约束的桥接轨迹。
◆实验显示其在10个基准环境中达到100%成功率，并在窄通道、非凸空间及真实地面车和四旋翼部署中实现快速、无碰撞规划。</td></tr>
<tr><td>2026-06-25</td><td>PlanRL: A Trajectory Planning Architecture for Reinforcement Learning-based Driving Experts<br><a href='http://arxiv.org/pdf/2606.26858'>论文</a></td><td>◆论文提出PlanRL，将强化学习驾驶策略从直接输出油门/转向改为生成可规划的轨迹，提升了可解释性和与端到端规划架构的兼容性。
◆方法将RL策略与基于多项式的轨迹规划器结合，使驾驶专家能够在更高层次的轨迹空间中决策。
◆通过引入Frenet坐标系，复杂道路几何被转化为结构化的曲线坐标表示，降低了策略学习的空间复杂度。
◆规划阶段加入运动学可行性检查，确保轨迹满足车辆物理约束，并缓解规划跟踪中的累积误差。
◆在CARLA Offline Leaderboard v1和NoCrash基准上，PlanRL相比现有控制型RL专家显著提升驾驶分数和成功率，验证了其有效性。</td></tr>
<tr><td>2026-06-25</td><td>Learning Motion Feasibility from Point Clouds in Cluttered Environments<br><a href='http://arxiv.org/pdf/2606.26700'>论文</a></td><td>◆本文研究从原始RGB-D点云直接预测7自由度机械臂在杂乱场景中的抓取运动可行性，减少传统采样式运动规划器在不可行情形下的高计算开销。
◆作者提出首个面向真实杂乱桌面环境的大规模基准，包含88个扫描物体、190个场景和270万条抓取可行性标签。
◆论文系统比较了MLP、体素CNN和点云Transformer三类代表性模型，并在统一训练条件下评估其泛化能力。
◆最佳模型GRASPFC-PTX利用点云Transformer建模复杂几何关系，在新物体测试上达到0.996 AUROC。
◆该方法在保持高精度的同时显著快于SBMP，为任务与运动规划中的快速可行性筛选提供了实用学习方案。</td></tr>
<tr><td>2026-06-24</td><td>PRISM: Efficient and Locally Optimal Probabilistic Planning with Reachability Guarantees<br><a href='http://arxiv.org/pdf/2606.26413'>论文</a></td><td>◆ PRISM提出了一种面向受运动不确定性、状态与控制约束影响的信念空间多查询规划算法，兼顾高覆盖率与低轨迹成本。

◆ 论文给出了约束条件下状态协方差可控性的新理论结果，使信念空间规划可分解为确定性均值规划与协方差收缩。

◆ PRISM避免依赖低效的采样连通验证或高代价鲁棒控制，从而提升受限信念空间中的可达性覆盖。

◆ 算法引入在线局部优化机制，在保持可行性的同时降低信念空间轨迹的平均成本和成本方差。

◆ 在温和假设下，PRISM证明了即使存在执行器和障碍物约束也能实现完整覆盖，并在仿真实验中显著优于现有方法。</td></tr>
<tr><td>2026-06-24</td><td>Scaling Nonlinear Optimization: Many Problems One GPU<br><a href='http://arxiv.org/pdf/2606.26341'>论文</a> | <a href='https://github.com/johnviljoen/jaxipm'>代码</a></td><td>◆提出jaxipm：首个基于IPOPT思想、用JAX实现的GPU批量非线性规划求解器，可同时求解大量机器人NLP问题。
◆面向GPU并行框架重构传统CPU串行NLP求解流程，使其能融入强化学习、MPC和仿真批处理管线。
◆引入“异构迭代融合”以消除IPOPT中的复杂控制流，提升GPU可编译与并行执行效率。
◆提出“迭代级批处理”以减少GPU空闲时间，提高多问题并发求解吞吐量。
◆在多种四旋翼NMPC任务中验证，包括避障跟踪、多机无碰导航和杂乱环境导航，较IPOPT最高实现32.85倍吞吐提升。</td></tr>
<tr><td>2026-06-25</td><td>G2DP: Diffusion Planning with Spatio-Temporal Grid Guidance<br><a href='http://arxiv.org/pdf/2606.26017'>论文</a></td><td>◆ G2DP提出一种网格引导的扩散式自动驾驶规划器，解决现有扩散规划在去噪过程中缺乏密集环境约束、闭环执行不稳定的问题。
◆ 其核心创新是构建可微的时空代价体，将未来占用概率分布与路线进度图融合，形成统一的安全与导航约束表示。
◆ 该方法把代价体转化为连续安全能量函数，在推理阶段直接向扩散去噪过程注入密集梯度，引导轨迹避碰并沿路线高效前进。
◆ 相比依赖稀疏实体几何查询或事后优化的引导方式，G2DP具备更强的场景感知能力，尤其适合密集交互交通。
◆ 实验表明，G2DP在nuPlan闭环评测达到领先性能，并在interPlan和DeepScenario零样本迁移中保持高分，显著提升碰撞避免能力。</td></tr>
<tr><td>2026-06-24</td><td>Event-Adaptive Motion Planning with Distilled Vision-Language Model in Safety-Critical Situations<br><a href='http://arxiv.org/pdf/2606.25629'>论文</a></td><td>◆论文提出EAMP框架，面向安全关键场景中由动态智能体异常行为引发的碰撞风险，实现事件自适应导航。
◆其核心思想是避免在控制闭环中频繁调用大型VLM，从而降低推理延迟并保证实时执行稳定性。
◆设计了提示可配置的语义事件触发器PC-SET，通过短时序视觉片段持续监测行为异常并按需触发语义干预。
◆提出蒸馏版SemNav-VLM，利用物理验证的语义蒸馏将异常事件映射为离散策略级决策。
◆进一步通过SMPC把高层语义策略转化为优化目标和几何参考的动态重配置。
◆实验表明，该方法在物流安全关键场景中显著提升动态安全裕度，同时保持较高实时效率。</td></tr>
<tr><td>2026-06-24</td><td>AISPO: Enhancing Depth Reliability for Robotic Manipulation of Non-Lambertian Objects via Affine-Invariant Shape Prior<br><a href='http://arxiv.org/pdf/2606.25503'>论文</a></td><td>AISPO面向透明、高反光等非朗伯物体的机器人操作，解决原始深度缺失或畸变导致抓取规划失败的问题。
◆提出一种深度补全框架，将多尺度RGB-D特征融合用于在复杂感知条件下恢复更可靠的深度。
◆引入仿射不变形状先验，约束预测深度的几何一致性，减少灾难性深度错误。
◆相比仅追求平均深度精度的方法，AISPO更强调物理可行性和结构完整性，使深度结果更适合抓取与运动规划。
◆通过基准测试和真实抓取实验验证了其对未见物体、新场景的泛化能力，并显著提升透明物体操作成功率。</td></tr>
<tr><td>2026-06-23</td><td>CKM-Driven Communication-Aware UAV Intelligent Trajectory Optimization for Urban Inspection<br><a href='http://arxiv.org/pdf/2606.24979'>论文</a></td><td>◆提出面向城市巡检多无人机任务的CKM驱动通信感知轨迹规划框架，将信道建模与路径决策统一起来。

◆利用扩散模型构建时间累积信道知识地图，仅依靠稀疏观测即可重建高保真全局信道质量分布，降低飞行探测开销。

◆设计全局到局部的图注意力网络-软演员评论家算法，实现巡检目标排序与连续轨迹控制的协同优化。

◆图注意力网络解决复杂组合节点排序问题，生成兼顾任务效率和通信质量的巡检目标访问序列。

◆软演员评论家算法进一步优化平滑飞行动作，并动态避开通信衰减区域，使无人机无需依赖实时信道反馈也能提升轨迹效率和通信可靠性。</td></tr>
<tr><td>2026-06-23</td><td>Optimization-based Safe Trajectory Planning for Autonomous Ground Vehicle in Multi-Floor Scenarios<br><a href='http://arxiv.org/pdf/2606.24631'>论文</a></td><td>该论文面向多楼层场景下自主地面车辆的安全轨迹规划问题，提出了一个由任务规划和轨迹规划组成的整体框架。

◆提出基于广义Voronoi图和多目标算法的任务规划策略，用于在各楼层中合理选择出口。

◆采用优化方法生成高质量、安全可行的车辆轨迹，适应多楼层环境中的复杂约束。

◆设计了热启动的分层规划框架，以提升优化求解速度并保证快速收敛。

◆提出相关约束计算方法，减少复杂障碍物带来的约束数量，降低轨迹规划计算负担。

◆通过仿真实验验证了该框架在多楼层场景中的可行性、效率和安全性。</td></tr>
<tr><td>2026-06-23</td><td>Adaptive Machine Learning Framework for UAV Trajectory Optimization in O-RAN<br><a href='http://arxiv.org/pdf/2606.24483'>论文</a></td><td>◆论文提出面向O-RAN架构的无人机轨迹优化框架，将UAV作为开放无线单元用于6G动态覆盖增强。
◆核心创新是引入增强型持续迁移学习，避免每个新环境都从零训练，提升跨场景适应效率。
◆框架维护预训练模型库，并通过模型选择机制匹配最相似环境，实现更精准的知识迁移。
◆当缺乏相似模型时，系统使用可持续优化的备用模型，保证新场景下的基本轨迹规划性能。
◆论文结合真实城市地图和射线追踪提升训练可靠性，仿真显示其收敛时间较从零训练降低44%至56%，较传统迁移学习最多降低40%。</td></tr>
<tr><td>2026-06-23</td><td>Varying Bundle Size Reactive Multi-Task Assignment using Selective Cost Estimation for Multi-Agent Systems<br><a href='http://arxiv.org/pdf/2606.24462'>论文</a></td><td>◆提出一种面向多机器人系统的可扩展反应式多任务分配框架，解决高精度任务执行成本估计昂贵导致实时性不足的问题。
◆设计分布式两阶段、多保真度的任务束生成方法，先用低保真启发式快速搜索候选任务束，再对最有前景者进行高保真路径规划验证。
◆支持动态变化的任务束大小，缓解传统组合拍卖中任务束枚举带来的指数复杂度。
◆通过中央协调器求解集合打包问题，在保证全局可行性的同时最大化整体效用。
◆仿真结果表明，该方法在多种环境中提升了反应式拍卖分配性能，并且无需暴露智能体状态和内部成本模型。</td></tr>
<tr><td>2026-06-23</td><td>DriveStack-VLA: Render-Teacher Alignment for BEV-Based DeepStack Vision-Language-Action Model<br><a href='http://arxiv.org/pdf/2606.24051'>论文</a></td><td>◆ DriveStack-VLA面向VLA自动驾驶模型空间智能不足的问题，将BEV表征引入大语言模型解码器，使策略具备更强的度量几何和俯视场景理解能力。
◆ 其DeepStack式连接把顶视结构信息与视觉语言推理深度融合，弥补仅依赖透视图像token和语言先验的缺陷。
◆ 论文提出Render-Teacher Alignment，通过栅格化图像教师对齐真实图像的感知关注，提升对安全关键线索的覆盖与利用。
◆ 为解决多模态轨迹选择难题，作者设计head-based self-critique模块，对采样轨迹排序并按需细化最优轨迹。
◆ 实验显示该方法在NAVSIMv1、NAVSIMv2和闭环Bench2Drive上取得强性能，验证了BEV空间 grounding、感知对齐与自我评估规划的有效性。</td></tr>
<tr><td>2026-06-22</td><td>Decentralized Autonomous Traffic Management through Corridor Networks<br><a href='http://arxiv.org/pdf/2606.23585'>论文</a></td><td>◆论文提出一种面向高级空中交通走廊网络的去中心化自治交通管理方法，以应对高密度载人/无人航空器协同难题。  
◆其核心创新是将多智能体强化学习从单走廊场景扩展到包含汇入、分流等结构的多走廊网络。  
◆训练策略可在更复杂网络中零样本迁移，无需集中式协调或重新训练。  
◆实验表明，该方法对交通密度变化、网络几何差异和异构飞行器性能具有良好泛化能力。  
◆仅依赖局部的进入、穿越和退出协同行为，系统仍能实现较好的边界遵循、完成率、速度、路径效率和安全间隔保持。</td></tr>
<tr><td>2026-06-22</td><td>Dense Reward for Multi-View 3D Reasoning with Global Maps and Local Views<br><a href='http://arxiv.org/pdf/2606.23557'>论文</a></td><td>◆提出DR-MV3D，一个面向多视角3D视觉问答的地图驱动学习框架，用密集、可验证奖励缓解仅靠答案级监督导致的跨视角推理不一致问题。
◆将任务分解为全局3D地图构建、问题条件下的视角轨迹规划，以及基于局部视图的自我中心 grounding 与答案预测。
◆设计全局一致性奖励，利用冻结的3D视觉基础模型生成几何一致伪标签，监督模型学习可靠的场景地图。
◆设计局部轨迹奖励，直接约束有序视角选择过程，提升多步空间推理中的视角规划能力。
◆通过GRPO进行轨迹级策略优化，并在MindCube、VSI-Bench和BLINK(MV)上优于强多图像基线，证明过程级密集监督对MV3D-VQA有效。</td></tr>
<tr><td>2026-06-22</td><td>FPAS: Frontier-Based Path Planning with Adaptive Sampling for Large-Scale Unknown Environments<br><a href='http://arxiv.org/pdf/2606.22838'>论文</a></td><td>◆ FPAS提出了一种面向大规模未知环境的前沿驱动路径规划框架，专注于提升长距离目标到达任务的效率。
◆ 该方法重新定义并利用frontier概念，不仅用于探索未知区域，还用于引导机器人朝目标方向持续推进。
◆ 在遇到死胡同或低效路径时，FPAS可基于frontier选择更有潜力的子目标，从而实现有效回退与重规划。
◆ 论文引入基于frontier开放度指标的自适应采样机制，在开阔区域稀疏建图以降低计算开销，在狭窄通道保持较高采样密度以保证连通性。
◆ 实验表明，FPAS在保持较强目标到达能力的同时，相比基线方法显著提升了计算效率，适合大规模未知环境导航。</td></tr>
<tr><td>2026-06-21</td><td>Interpolations: a linear algebra approach<br><a href='http://arxiv.org/pdf/2606.22671'>论文</a></td><td>◆本文提出一个统一的线性代数插值框架，将拉格朗日插值、Hermite样条和三角插值等问题表述为有限维函数空间对偶空间中的线性泛函条件。
◆论文建立了通用的存在唯一性定理，使插值问题可通过维数匹配与泛函线性无关性来判定。
◆作者推导了与给定插值条件对偶的基函数显式公式，从而可高效构造插值函数。
◆该框架扩展到三角插值，给出闭式对偶基并分析退化条件。
◆论文还处理异构传感器场景，即不同位置给定函数值与导数，并展示其在轨迹规划和信号处理中的应用潜力。</td></tr>
<tr><td>2026-06-21</td><td>Semantic-Aware Autonomous Exploration for UAVs in Unknown Indoor Environments<br><a href='http://arxiv.org/pdf/2606.22670'>论文</a></td><td>◆提出一种面向未知室内环境的语义感知无人机自主探索框架，将语义信息融入传统基于几何的探索流程。
◆在Dynamic Exploration Planner基础上，增量构建PRM并增加语义层，使路线图同时表达空间连通性与场景语义价值。
◆设计语义奖励函数，优先引导无人机探索包含关键物体或结构的高信息量区域，从而提升探索效率。
◆通过持续更新路线图，实现更高效的前沿选择与路径规划，适应探索过程中不断变化的环境认知。
◆在ROS Noetic与Gazebo中基于RGB-D传感器验证，实验表明该方法达到90%至94%的覆盖率，并相比几何方法减少探索时间和飞行距离。</td></tr>
<tr><td>2026-06-21</td><td>LAWNs Meet SWIPT: Beamforming and Power Splitting Optimization for Predictive Control<br><a href='http://arxiv.org/pdf/2606.22534'>论文</a></td><td>◆论文首次面向SWIPT赋能的低空无线网络，研究多天线基站同时向多架UAS传输控制信息与无线能量的联合设计问题。

◆针对存在多个移动禁飞区的场景，引入流函数理论构造平滑且安全的参考轨迹，实现无碰撞路径规划。

◆建立实时联合优化框架，同时优化控制输入、发射波束成形向量和功率分割比例，以兼顾轨迹跟踪精度与能量可持续性。

◆提出两阶段求解方法：先基于MPC生成预测控制输入，再结合SDR与SCA高效优化通信与能量传输变量。

◆论文证明了所用SDR在该问题中的紧性，并通过仿真表明该方案在跟踪精度和能量收集方面显著优于基准方法。</td></tr>
<tr><td>2026-06-19</td><td>THREAD: Trajectory Planning for Hybrid Rigid-Soft Manipulators with Environment-Aware Diffusion<br><a href='http://arxiv.org/pdf/2606.21792'>论文</a></td><td>◆提出THREAD，首个面向刚柔混合机械臂的扩散式轨迹规划器，专门解决狭窄孔洞穿越等受限环境操作难题。
◆方法学习在局部环境几何条件下物理可实现的骨架轨迹生成先验，而非仅在自由空间规划。
◆将刚性段与软体段联合建模，避免独立规划带来的运动学耦合失配问题。
◆引入受物理启发的损失函数，同时约束曲率、轨迹平滑性和碰撞风险，提升可行性与安全性。
◆仿真结果显示THREAD达到92.4%任务成功率，碰撞次数比最强基线少5倍。
◆系统还能以少量在线更新实现跨本体真实迁移，并成功穿过仅为软体段直径1.3倍的小孔。</td></tr>
</tbody>
</table>
</div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-24</td><td>Calousel: Extrinsic Calibration of Non-overlapping Multi-camera Systems from Pure Rotation<br><a href='http://arxiv.org/pdf/2606.25646'>论文</a></td><td>◆论文提出Calousel，用纯旋转运动实现非重叠视场多相机外参标定，只需一块静态标定板，降低了传统大靶标或多靶标预先测量的部署成本。
◆其核心思想是让各相机在不同时间依次观测同一标定板，并通过共享几何参考把这些非同步观测统一起来。
◆方法引入潜在转台坐标系，并在SE(3)上构建三维误差的全局优化模型，以联合估计多相机外参。
◆相比常见运动标定方法，该方案缓解了漂移误差、尺度不确定性和运动退化等问题。
◆实验在受控相机架和真实车辆异构相机平台上验证，表明其在非理想旋转条件下仍具备较高精度和现场部署实用性。</td></tr>
<tr><td>2026-06-03</td><td>A Geometry-Informed Computer Vision Method for Detecting and Examining Overtaking Vehicles From A Bicycle<br><a href='http://arxiv.org/pdf/2606.23699'>论文</a></td><td>◆提出一种面向自行车后视视频的几何约束计算机视觉流水线，可自动检测机动车超车事件，无需多传感器或显式相机标定。
◆方法结合RT-DETR目标检测与ByteTrack跟踪，并用方位角变化、目标尺寸增长和空间位置确认三类透视几何规则过滤事件。
◆在315个真实城市超车事件上实现97.8%召回率且零误报，显著降低人工逐帧标注负担。
◆系统平均可在车辆通过前2.44秒识别超车意图，84.1%的事件早于1.5秒反应阈值，具备主动预警潜力。
◆论文还探索了免标定横向通过距离估计，误差约13–14厘米，可用于区分危险近距离超车并支撑大规模骑行安全研究。</td></tr>
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
<tr><td>2026-06-12</td><td>LV-Calib: LiDAR-Camera Extrinsic Calibration with Boundary-Response Modeling<br><a href='http://arxiv.org/pdf/2606.15010'>论文</a></td><td>本文提出了LV-Calib标定框架，利用可打印平面标定板实现了激光雷达与相机的外参估计及激光雷达边界响应标定。
◆提出基于强度与几何约束的迭代精化方法，自动裁剪背景并估计目标平面，显式处理反射率不连续处因光束足迹和混合回波导致的过渡带展宽与失真问题，提取精确的雷达3D特征点。
◆设计了加权重投影一致的外参优化策略，将图像观测保留在重投影域，并利用精化置信度对雷达特征残差进行加权，提升外参标定精度。
◆利用估计的外参和提取的过渡带，通过计算边界重叠样本的俯仰-偏航-距离残差统计量，实现了激光雷达边界响应的标定。
实验验证了该方法具备亚像素级重投影精度与毫米级特征一致性，并有效提升了里程计性能。</td></tr>
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
<tr><td>2026-06-11</td><td>RGB-S: Image-Aligned Tactile Saliency for Robust Dexterous Manipulation<br><a href='http://arxiv.org/pdf/2606.08765'>论文</a></td><td>本文提出RGB-S框架，旨在解决机器人灵巧操作中视觉遮挡下稀疏触觉与密集视觉难以对齐的问题。与隐式学习跨模态对应的方法不同，该框架通过将物理接触显式锚定在图像域中来提升空间推理能力。
◆利用机器人正运动学与相机校准，将触觉传感器位置直接投影到RGB图像平面，实现跨模态空间对齐。
◆渲染受力调制的高斯显著图，有效建模由运动学与校准误差带来的空间不确定性。
◆采用零初始化条件架构整合二维空间锚点，将物理接触先验注入视觉主干网络，同时保留预训练视觉表征。
在严重视觉遮挡的仿真与真实灵巧操作任务评估中，该方法展现出更强的抗遮挡鲁棒性，真实世界实验成功率较最强隐式基线提升了26.7个百分点。</td></tr>
<tr><td>2026-06-07</td><td>Language as a Sensor: Calibrated Spatial Belief Estimation in 3D Scenes from Natural Language<br><a href='http://arxiv.org/pdf/2606.08666'>论文</a></td><td>该论文提出将自然语言作为一种新型传感器，以解决机器人视场外3D空间推理与多传感器融合的难题。
◆提出语言传感器模型LSM，将语言描述及场景图上下文映射为多模态空间分布，通过混合权重编码指代歧义，分量协方差编码空间不确定性。
◆提出概率建图框架VL-Map，将语言预测视为随机观测，并与机载感知在统一的置信度地图中进行深度融合。
实验证明，LSM是唯一能够保持协方差估计处于校准状态的语言预测器。
将LSM融合进VL-Map后，系统对目标物体位置的预测更加准确，真值目标上的概率质量比最强基线高出约70%。</td></tr>
<tr><td>2026-06-06</td><td>Empowering Feed-Forward Reconstruction Models with Metric Scale via Satellite Images<br><a href='http://arxiv.org/pdf/2606.08205'>论文</a></td><td>该论文提出一种卫星引导框架，利用易获取的卫星图像作为全局度量参考，解决前馈3D重建模型中存在的尺度模糊问题。
◆创新性地引入卫星图像作为度量参考，无需昂贵的度量标注或高精度相机标定即可消除尺度模糊。
◆设计了双向跨视角交互机制，将局部卫星图像块与前馈重建主干网络深度融合，强制重建场景与卫星参考间的一致性。
◆实现在度量坐标系下同时推断绝对尺度、优化场景几何并估计相机姿态的能力。
实验表明，该方法在多数据集的深度估计、点云重建和定位任务上均取得显著提升，且保持了优异的跨域泛化性。</td></tr>
<tr><td>2026-06-06</td><td>SynthICL: Scalable In-context Imitation Learning with Synthetic Data<br><a href='http://arxiv.org/pdf/2606.08154'>论文</a></td><td>本文提出了SynthICL框架，解决了上下文模仿学习在泛化性和可扩展性上的挑战，实现了仅基于纯RGB合成数据训练策略。
◆构建高质量合成数据生成流水线并训练流匹配Transformer策略，摆脱了对深度传感、精确相机标定和真实训练数据的依赖，提供更简单可扩展的方案。
◆引入子目标预测机制，通过训练模型预测下一子目标图像，实现更精确且具有视觉基础的机器人控制。
◆在测试阶段仅需单次演示即可让机器人适应新任务，无需重新训练模型。
该方法在16项未见真实操作任务中取得79%的平均成功率，显著超越了现有方法。</td></tr>
<tr><td>2026-06-03</td><td>Multi-Camera AR Guidance System for Surgical Instrument Handling and Assembly: Investigating Workload and Efficiency<br><a href='http://arxiv.org/pdf/2606.04992'>论文</a></td><td>本文提出了一种用于手术器械处理与装配的多摄像头增强现实引导系统，旨在降低洗手护士的认知需求并提升操作效率。模拟手术的用户研究表明，该系统显著降低了护士的感知工作负荷，将任务完成时间缩短了21.3%，尤其使不熟悉器械的护士获益。
◆提出了无需额外标记的多摄像头6D位姿估计与头戴式显示器原位可视化相结合的手术引导方案。
◆采用纯合成数据训练6D位姿估计网络，利用已知物体实现连续相机校准，提升了算法的泛化能力与真实世界适用性。
◆设计了原位工具提示定位与逐步装配动画，并创新性结合凝视选择与脚踏板实现步进切换，满足术中无菌交互需求。</td></tr>
<tr><td>2026-06-03</td><td>FUSE-Flow: A Decoupled Framework for Calibration and Stateless Real-Time Multi-View Point Cloud Fusion<br><a href='http://arxiv.org/pdf/2606.04376'>论文</a></td><td>本文提出FUSE-Flow，一个将标定与实时多视角点云融合解耦的框架，解决了传统方法中二者紧密耦合导致的波动重建结果、累积误差和扩展性差的问题。核心贡献在于通过GMAC和FUSE两个协同模块，实现了无需标定板、密集图像或全局光束法平差的稀疏视角精确标定，以及线性时间内存消耗的无状态融合。框架中GMAC利用几何约束与多视图重建Transformer优化外参，FUSE则通过置信度加权和自适应空间哈希完成融合，且二者相互增强——精确位姿提升融合精度，置信感知融合修正标定偏差。在公共数据集和真实相机系统上的实验验证，FUSE-Flow在视觉效果、动态稳定性和可扩展性上均优于主流实时重建方法，为大规模实时三维重建提供了实用方案。
◆ 解耦设计：将标定与点云融合拆分为独立模块，避免冲突的优化目标，实现针对性改进。
◆ 几何对齐多视图标定（GMAC）：基于几何约束和Transformer实现稀疏视角标定，无需标定靶标、密集图像或全局BA。
◆ 置信引导无状态融合（FUSE）：结合置信度权重与自适应空间哈希，确保线性时间与内存开销，且支持实时运行。
◆ 双向增强机制：精确位姿提升融合准确性，同时置信度感知融合反向校正标定偏差，形成自优化闭环。</td></tr>
<tr><td>2026-06-06</td><td>Dexterity-BEV: Aligning 3D World and Actions for Generalizable Robot Policies Learning<br><a href='http://arxiv.org/pdf/2606.02274'>论文</a> | <a href='https://hnuzhy.github.io/projects/Dex-BEV'>代码</a></td><td>本文针对端到端操作策略依赖2D输入且缺乏跨机器人和相机的3D空间对齐的局限性，提出了Dexterity-BEV方法。
◆提出对齐顶点图与顶点频谱，利用相机标定和可选深度将2D视觉提升为像素级3D表示，融合了3D感知与2D大模型的泛化优势。
◆提出将操作策略的输入输出对齐至共享坐标系，并创新性地构建鸟瞰图图像，生成对相机位姿变化鲁棒的视角不变表示。
◆开发了全面的数据处理管线以实现大规模对齐，并引入了针对跨多种机器人、人类操作员和数据集轨迹的全新时间对齐方案。
这些贡献共同缓解了输入输出的时空不对齐问题，显著提升了真实世界机器人操作的连贯性与泛化能力。</td></tr>
<tr><td>2026-06-01</td><td>Effective Multi-sensor Conditioning for Street-view Novel-view Synthesis<br><a href='http://arxiv.org/pdf/2606.01590'>论文</a></td><td>本文提出StreetNVS视频扩散框架，解决现有街景新视角合成方法未充分利用多传感器信号导致偏离轨迹时画质下降的问题。该方法将稀疏激光雷达的精确度量几何、环视图像的密集外观与相机位姿进行有效融合。
◆基于相对光线级位置编码的参考增强相机注意力模块，实现对上述三种信号的联合条件化处理。
◆两阶段课程训练策略，通过逐步增加激光雷达稀疏度来提升模型鲁棒性。
在Waymo数据集上，该框架在稀疏激光雷达条件下大幅超越现有基线，媲美使用十至百倍密集点云的方法，并能合成升降或旋转等极端偏离轨迹的连贯视频。</td></tr>
<tr><td>2026-05-29</td><td>Joint Multi-Camera LiDAR Extrinsic Calibration via Learned Pairwise Initialization and Geometric Refinement<br><a href='http://arxiv.org/pdf/2605.31576'>论文</a></td><td>现有基于学习的相机与激光雷达标定方法通常独立处理各对数据，忽视了多相机平台的刚体几何耦合，导致系统层面不一致。
◆提出了一种联合多相机激光雷达外参标定的两阶段框架，克服了独立估计导致的系统性不一致问题。
◆结合深度学习匹配与几何优化，先利用CMRNext独立生成各相机的初始外参及密集2D-3D对应关系，再通过多帧光束法平差进行联合优化。
◆在优化阶段引入重投影、单相机先验及相对位姿先验约束，成功将局部成对预测转化为全局一致的标定结果。
实验表明该方法提升了单相机精度和相机间一致性，在KITTI数据集上实现了0.89厘米的平移误差。
在域外Walkley数据集上，该方法将平移误差从108.6厘米大幅降至3.1厘米，验证了显式多相机耦合在单相机预测不可靠时的巨大优势。</td></tr>
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
</tbody>
</table>
</div>

<h2 id='sensor-undistortion'>Sensor Undistortion</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-25</td><td>Confidence-Aware Tool Orchestration for Robust Video Understanding<br><a href='http://arxiv.org/pdf/2606.26904'>论文</a></td><td>◆论文指出视频推理模型的“盲目信任问题”：默认所有帧同等可靠，导致模糊、眩光、遮挡等扰动下准确率显著下降且无法自知。

◆提出Robust-TO框架，将逐帧可信度显式融入视频理解的证据选择、工具调用和最终推理全过程。

◆设计统一证据接口，协调检测、OCR、动作识别等异构视觉工具，使其输出预测结果、时间定位和校准可靠性分数。

◆引入可靠性-相关性评分选择可信帧，并用高/中/低三层证据综合机制按置信度加权推理。

◆提出置信度-成本GRPO奖励，同时优化答案正确性、证据可靠性和计算效率，在干净与受扰动视频上均取得领先表现。</td></tr>
<tr><td>2026-06-25</td><td>Event-based Gaze Control System for Accurate Real-time Spin Estimation in Professional Ball Games<br><a href='http://arxiv.org/pdf/2606.26780'>论文</a></td><td>◆提出一套事件相机主动视觉系统，结合高速振镜与可调焦长焦镜头，在高速球类运动中持续放大、对焦并跟踪未改装球体。
◆设计混合跟踪策略，将事件驱动的2D检测用于实时居中，并利用3D定位结果进行重初始化，提高比赛场景鲁棒性。
◆提出球面事件对比度最大化方法s-CMax，实现跨乒乓球、棒球、网球和高尔夫的高精度离线旋转估计。
◆面向实时乒乓球应用，构建由伪真值训练的不确定性感知CNN，并结合GPU批量对比度最大化进行快速精修。
◆系统在职业乒乓球三视角实验中达到3毫秒延迟、750Hz吞吐率，并取得8.8%转速幅值误差和6.4度旋转轴误差。</td></tr>
<tr><td>2026-06-25</td><td>Lattice Reconstruction and Orbital Hybridization Suppress Magnetism in TaCo$_2$Te$_2$<br><a href='http://arxiv.org/pdf/2606.26644'>论文</a></td><td>◆ 本文结合STM/STS、nc-AFM、ARPES和DFT，系统揭示了TaCo2Te2中晶格重构、电子结构与磁不稳定性的耦合关系。
◆ nc-AFM解析出畸变六角Te表面晶格，而STM/STS显示类方形电子对称性，说明电子态并不简单跟随原子结构。
◆ ARPES观测到强各向异性费米面和重构低能态，证明晶格重构显著改造其低能电子结构。
◆ 空间分辨谱学和轨道投影DFT表明，STM偏压衬度来自能量积分局域态密度中不同能量态的相反空间衬度，而非简单占据态/未占据态反转。
◆ DFT进一步发现，重构通过增强轨道杂化抑制未畸变结构中的磁不稳定性，稳定非磁基态，使TaCo2Te2成为结构调控磁性与关联相的模型体系。</td></tr>
<tr><td>2026-06-25</td><td>Temporally Consistent Label Interpolation for Robust Surgical Multi-Task Learning under Challenging Conditions<br><a href='http://arxiv.org/pdf/2606.26634'>论文</a></td><td>◆本文针对手术多任务学习中时间任务密集标注与空间任务稀疏标注不匹配的问题，提出了FAROS标签插值框架。

◆FAROS结合零样本分割掩码传播与光流估计，在遮挡、烟雾、运动模糊等复杂手术条件下生成时间一致的密集伪标签。

◆方法将插值后的器械掩码和动作标签融入统一的Transformer多任务模型，同时学习阶段、步骤、预测、器械分割和动作识别。

◆作者先在DAVIS 2017上验证了稀疏标注条件下的传播质量，证明其具备跨领域鲁棒性。

◆在GraSP、MISAW和AutoLaparo上的实验表明，FAROS显著提升了跨任务表征学习与整体手术场景理解性能。</td></tr>
<tr><td>2026-06-24</td><td>Edges Before Embeddings: A Confidence-Aware Blur Gate for Vision-Language Pipelines<br><a href='http://arxiv.org/pdf/2606.25838'>论文</a></td><td>◆ 提出MagikaDocumentFromPixel，一个轻量级CPU图像质量门控，可在约7ms内将输入判为清晰、模糊或不确定，避免下游OCR、检索和VLM在劣质图像上浪费计算。
◆ 通过46种配置、8轮实验搜索，发现输入分辨率是性能主导因素，模型容量只有在384px及以上时才明显收益。
◆ 引入基于选择性预测的置信度感知路由机制，使系统能对不确定样本进行保守处理。
◆ 设计Edge Prior Module，将拉普拉斯幅值作为辅助通道注入网络，直接利用模糊检测所需的边缘频谱证据，F1提升约1.3点。
◆ 最终方案以MobileNetV3-Large、384×384训练和5尺度测试增强达到F1=0.9803、AUC=0.9989，同时作者也明确指出数据分布、单随机种子和校准评估的局限。</td></tr>
<tr><td>2026-06-24</td><td>Shift Variant Image Degradation and Restoration Using Singular Value Decomposition<br><a href='http://arxiv.org/pdf/2606.25818'>论文</a></td><td>◆论文提出了一种基于奇异值分解的移变运动模糊图像复原框架，针对传统单一卷积核难以描述的空间变化退化问题。

◆其核心创新是用位置相关PSF构建移变成像算子，将退化过程统一建模为线性系统并进行SVD分析。

◆论文引入奇异值能量保留准则，系统选择小奇异值数量，以在抑制噪声放大和保留图像细节之间取得平衡。

◆方法覆盖双向线性运动、高斯运动和简谐运动三类一维移变PSF，验证了模型的适用性。

◆实验表明，该SVD稳定反演策略能够有效恢复图像细节、减轻模糊伪影，并揭示移变复原问题的病态特征。</td></tr>
<tr><td>2026-06-24</td><td>1000 Rallies: An Event-Camera Dataset and Real-Time Learned Ball-State Estimation for Robotic Table Tennis<br><a href='http://arxiv.org/pdf/2606.25620'>论文</a></td><td>◆ 提出首个面向乒乓球真实对打场景的大规模事件相机数据集“1000 Rallies”，涵盖1000多回合、不同水平运动员的击球数据。  
◆ 数据集同步采集事件流与14台200 FPS高速相机，并生成1 kHz的球位置、速度和旋转伪真值标签。  
◆ 基于该数据训练了卷积神经网络，可在复杂球员背景运动下从事件数据中联合估计球的图像平面位置与速度。  
◆ 将网络预测的速度作为卡尔曼滤波额外观测后，相比仅用位置的基线，落点预测误差降低36%。  
◆ 系统最终接入Stäubli机械臂，首次实现了由事件视觉驱动的实时人机乒乓球连续对打。</td></tr>
<tr><td>2026-06-24</td><td>EchoStyle: Unlocking High-Fidelity Video Stylization with Reverse Data Synthesis<br><a href='http://arxiv.org/pdf/2606.25465'>论文</a></td><td>◆ EchoStyle提出一个可扩展的文本驱动视频风格化框架，面向任意长度视频实现高保真、稳定的艺术风格迁移。
◆ 它设计了视频到视频架构，更合理地融合原视频内容与文本风格，缓解参考图方法常见的内容泄漏和运动失真。
◆ 论文首创自动化反向数据合成流程，构建了包含2万对高质量视频的V-Style20k数据集，显著缓解训练数据稀缺问题。
◆ 为处理长视频，提出init-follow-mode机制与滑动窗口推理策略，降低风格漂移并提升时序一致性。
◆ 实验证明EchoStyle可适配多种艺术风格，效果接近领先闭源方案，展示了较强的实用性和扩展性。</td></tr>
<tr><td>2026-06-21</td><td>A Theory-grounded Hybrid Neural Network Integrating Complementary Estimation Mechanisms for Stable Visual Object TrackingA<br><a href='http://arxiv.org/pdf/2606.22604'>论文</a></td><td>◆论文提出一种有理论支撑的ANN-CANN混合框架，将人工神经网络与连续吸引子神经网络在同一连续状态空间中对齐。
◆该框架突破了以往HNN主要停留在脉冲/神经元尺度混合的局限，探索了面向连续状态估计的群体尺度混合路径。
◆作者将该框架实例化为视觉目标跟踪网络HTNN，使ANN响应图与CANN动态通过共享状态表示交互。
◆论文揭示并利用了两类机制的偏差-方差互补性：ANN估计渐近无偏，CANN估计方差低但存在时间滞后。
◆实验显示HTNN在九个跟踪基准上稳定优于单一网络和已有混合模型，并在遮挡、运动模糊、背景干扰等复杂场景下保持鲁棒性能。</td></tr>
<tr><td>2026-06-19</td><td>Unsupervised Susceptibility Distortion Correction of EPI without Calibration Scans via Image Translation-Based Registration<br><a href='http://arxiv.org/pdf/2606.21588'>论文</a></td><td>◆ 提出SACRED，一种无需场图或反向相位编码等校准扫描的EPI磁敏感畸变校正框架，仅依赖常规T1w图像和单向PE BOLD图像。
◆ 通过基于图像翻译的配准，将BOLD与T1w之间的模态差异转化为可配准的单对比度问题。
◆ 采用可逆神经网络作为翻译骨干，并结合模态无关邻域描述子约束结构一致性，避免解剖结构被错误改变。
◆ 设计无监督训练目标，不需要真实无畸变BOLD图像即可学习畸变校正。
◆ 引入测试时自适应提升跨扫描仪、跨人群等分布外数据的鲁棒性，并在多个数据集上显著优于代表性方法。</td></tr>
<tr><td>2026-06-19</td><td>Context-Aware Autoregressive Diffusion for Gloss-Wise Sign Language Production<br><a href='http://arxiv.org/pdf/2606.21234'>论文</a></td><td>◆ 论文提出GARD，一种面向逐词素生成的上下文感知自回归扩散框架，用于提升句子级手语生成的自然性与可控性。
◆ 不同于一次性生成整段序列的方法，GARD按gloss逐段合成，有效缓解长句中的时间漂移和手部运动模糊问题。
◆ 模型同时利用语义语言上下文与运动学上下文建模词素间协同发音，使单个gloss生成更准确且与上下文一致。
◆ 论文设计Inter-Gloss Transition Guidance，通过梯度引导对齐相邻gloss边界姿态，增强过渡连续性。
◆ 还引入Global Motion Harmonizer，对整体运动序列进行全局细化，在Phoenix-T和CSL-Daily上取得优于现有方法的语言准确性与运动相似度。</td></tr>
<tr><td>2026-06-18</td><td>NeoLoc-68: End-to-end 68-point neonatal facial landmark localisation in neonatal clinical environments<br><a href='http://arxiv.org/pdf/2606.20823'>论文</a></td><td>◆提出首个端到端68点新生儿面部关键点定位模型NeoLoc-68，面向真实临床环境中的疼痛评估需求。
◆整合11个公开数据集的37,459张单脸图像，并加入1,123帧临床新生儿手工标注数据，统一为68点标注体系。
◆将YOLO关键点模型适配为新生儿面部关键点回归器，并利用预训练新生儿人脸检测器权重初始化，提升泛化能力。
◆模型在公开数据集上取得当前最优性能，NME、FR和AUC等指标均表现突出。
◆在临床测试集上，模型面对遮挡、姿态变化和运动模糊仍保持较低检测失败率，微调后性能进一步提升，为非接触式新生儿疼痛与健康监测提供基础。</td></tr>
<tr><td>2026-06-18</td><td>UNSEEN: Uncertainty-aware Navigation via Sparse Estimation in Unknown Environments<br><a href='http://arxiv.org/pdf/2606.20755'>论文</a></td><td>◆UNSEEN提出一种仅依赖前视相机的未知环境视觉导航框架，面向资源受限机器人降低传感器复杂度和部署成本。
◆其核心创新是将定位、建图与规划统一到不确定性感知框架中，显式建模运动指令与感知质量之间的耦合关系。
◆系统以6Hz估计稀疏地图、机器人位姿及其不确定性，并将这些信息持续传递到导航决策中。
◆UNSEEN-Plan采用滚动时域规划，同时优化任务推进和状态估计精度，从而主动选择更利于感知的轨迹。
◆实验表明，UNSEEN-SLAM将绝对平移误差降低9.8%，规划模块最高提升45%估计精度，并在真实未知环境中实现100%任务成功率。</td></tr>
<tr><td>2026-06-18</td><td>ARTEMIS: Agent-guided Reliability-aware Temporal Mask Evolution for Imperfectly Supervised Video Polyp Segmentation<br><a href='http://arxiv.org/pdf/2606.20161'>论文</a> | <a href='https://github.com/wangtong627/ARTEMIS'>代码</a></td><td>◆ ARTEMIS面向不完美监督的视频息肉分割，统一处理点、涂鸦和少量密集标注等低成本监督，缓解伪标签边界泄漏、形状退化和时序不一致问题。
◆ 提出“辩论-裁判”式视觉语言智能体，在弱监督下自动筛选可靠的时序锚点，提升伪标签初始化质量。
◆ 利用SAM2进行双向时序传播，从可靠锚点逐步修正不可靠或未标注帧，实现可靠性感知的时序掩码演化。
◆ 设计时序可靠性感知鲁棒学习机制，包括参考选择、参考原型传输模块和鲁棒损失，以传递目标身份并降低噪声监督影响。
◆ 在SUN-SEG和CVC-ClinicDB-612的涂鸦、点标注及少标签设置下取得领先性能，验证了框架的有效性与临床应用潜力。</td></tr>
<tr><td>2026-06-17</td><td>Optimal transport of signed fractal measures with dimensional distortion: a variational characterization<br><a href='http://arxiv.org/pdf/2606.19631'>论文</a></td><td>◆本文将带符号测度的最优传输理论扩展到Ahlfors正则分形支撑集之间，并允许源与目标存在可控的局部维数扭曲。

◆通过在跨符号传输成本中加入εΦ(ds(x)-dt(y))惩罚项，论文刻画了维数不匹配对最优传输结构的影响。

◆在H1--H7条件下，证明了任意ε&gt;0时最优传输映射Tε的存在性与唯一性。

◆论文推导出带维数扭曲修正项的耦合Monge--Ampère方程，推广了经典Brenier--Caffarelli框架。

◆核心创新是提出双Legendre--Fenchel表征，证明四种符号传输情形下最优势函数是共轭方程系统的唯一不动点。

◆该变分刻画为后续数值算法设计和ε渐近分析提供了统一理论基础。</td></tr>
<tr><td>2026-06-17</td><td>Pinning Down the Geometry of the Type Ic Broad-Line Supernova 2026gzf<br><a href='http://arxiv.org/pdf/2606.18881'>论文</a></td><td>◆论文首次对Ic-BL型超新星SN 2026gzf在X射线激波 breakout 后4.6天和16.5天开展成像偏振与光谱偏振观测，约束其早期爆炸几何。

◆持续较低的连续谱偏振表明其外层抛射物近似球形，说明爆炸未显著破坏前身星外壳结构。

◆第16.5天Ca II近红外三重线出现超过1.5%的高偏振，揭示氧燃烧产物的激发结构具有明确对称轴。

◆研究发现Ca II线同时包含高速主成分和更外层的次级成分，后者偏振显示外层激发几何非轴对称且更复杂。

◆通过三维蒙特卡洛建模，论文推断观测视角约为相对对称轴40度，可合理再现Ca II线的光谱与偏振特征。</td></tr>
<tr><td>2026-06-17</td><td>Learning to Distort: Weakly-Supervised Image Quality Transfer for Prostate DWI Correction<br><a href='http://arxiv.org/pdf/2606.18869'>论文</a></td><td>◆ 提出一种弱监督图像质量迁移框架，用图像级质量标签（失真/未失真）替代昂贵的体素级配对数据来学习前列腺DWI畸变相关表征。
◆ 在预训练特征空间中构建“质量原型”，利用IQA信号监督从未失真图像到失真图像的质量迁移。
◆ 提出弱监督原型流匹配算法，显式约束生成轨迹逼近失真原型，从而合成更真实的磁敏感伪影。
◆ 通过先“学习生成真实畸变”来构造伪配对数据，再训练正向校正模型，规避了直接无配对校正的不稳定性。
◆ 实验显示该方法生成的伪影能模拟真实临床诊断干扰，并在PI-RADS和Gleason评分等下游任务及外部数据上优于CycleGAN、UNIT-DDPM、OT-FM等方法。</td></tr>
<tr><td>2026-06-12</td><td>HumP-KD: A Hybrid Uncertainty-Aware Multi-Stage Progressive Knowledge Distillation Framework for Efficient Fire Classification<br><a href='http://arxiv.org/pdf/2606.14684'>论文</a></td><td>本文提出了HumP-KD框架，用于在资源受限硬件上实现高效且可部署的实时火灾分类。
◆提出混合异构教师知识蒸馏，将冻结的Swin-Tiny和ViT-Base及其Meta-MLP集成的知识蒸馏到轻量级MobileViT-S中。
◆设计层次渐进式知识蒸馏，通过层次特征构建器生成融合空间注意力掩码，选择性引导蒸馏关注判别性区域。
◆引入多阶段知识蒸馏机制，在训练中逐步激活三个蒸馏阶段。
实验表明该方法F1分数达0.9876，显著优于无蒸馏基线，且具备强鲁棒性与泛化能力。
学生模型仅4.94M参数，参数缩减最高达17.5倍，CPU帧率达37.72FPS，完全满足实时部署需求。</td></tr>
<tr><td>2026-06-12</td><td>FEMOT: Multi-Object Tracking using Frame and Event Cameras<br><a href='http://arxiv.org/pdf/2606.14094'>论文</a> | <a href='https://github.com/Event-AHU/FEMOT'>代码</a></td><td>针对RGB相机在复杂场景下性能受限且RGB-事件多目标跟踪缺乏数据的问题，本文提出了FEMOT数据集及FEMOTR框架。
◆构建了大规模RGB-事件多目标跟踪数据集FEMOT，涵盖多样真实场景与14个挑战属性，填补了该领域缺乏高质量标注数据的空白。
◆基于该数据集评估了十余种先进跟踪器，建立了全面的综合基准，为未来研究提供可靠平台。
◆提出多模态跟踪框架FEMOTR，在频域中对RGB和事件特征进行解耦与融合。
该机制有效利用了两者的互补特性，实现了更鲁棒的目标定位与身份关联。
在FEMOT和DSEC-MOT数据集上的广泛实验充分验证了所提方法的有效性。</td></tr>
<tr><td>2026-06-12</td><td>An ultra-wide-bandgap semiconductor photodetector for linear measurement of bright sub-bandgap light<br><a href='http://arxiv.org/pdf/2606.07807'>论文</a></td><td>本文提出了一种亚带隙氮化铝光电探测器，解决了传统探测器在中低强度光下易饱和的问题。
◆实现了对超过40瓦每平方厘米的超强蓝光的非饱和线性响应。
◆在高达300摄氏度的高温下依然保持无失真的线性响应。
◆揭示了金属-氮化铝肖特基结处深能级点缺陷介导光响应的物理机制。
◆通过掺杂和接触工程证明，窄空间电荷区是实现超强光探测与精确测量的关键。
该研究为超宽禁带半导体器件在航空航天及核电等极端条件下的可靠运行提供了工程策略。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>4853</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4261</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2416</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1609</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1608</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1431</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1268</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1255</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>958</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>943</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>918</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>795</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>780</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>742</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>723</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>709</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>638</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>638</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>622</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>593</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>568</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>555</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>538</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>501</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>491</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>438</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>415</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>343</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>341</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>264</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>252</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>245</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>235</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>223</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>201</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>201</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>168</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>146</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>142</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>119</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2846</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1643</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1353</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1095</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1036</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>871</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>699</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>657</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>649</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>621</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>585</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>573</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>567</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>562</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>551</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>516</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>485</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>461</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>446</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>443</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>335</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>312</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>298</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>283</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>279</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>257</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>222</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>206</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>202</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>187</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>176</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>169</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>166</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>159</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>153</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>137</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>136</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>132</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
<tr><td><a href='https://github.com/ethz-asl/phaser'>phaser</a></td><td>130</td><td>A robust pointcloud registration pipeline based on</td></tr>
<tr><td><a href='https://github.com/ethz-asl/data-driven-dynamics'>data-driven-dynamics</a></td><td>130</td><td>Data Driven Dynamics Modeling for Aerial Vehicles</td></tr>
<tr><td><a href='https://github.com/ethz-asl/ssc_exploration'>ssc_exploration</a></td><td>111</td><td>Incremental 3D Scene Completion for Safe and Effic</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waypoint_navigator'>waypoint_navigator</a></td><td>108</td><td>Stand-alone waypoint navigator</td></tr>
<tr><td><a href='https://github.com/ethz-asl/active_grasp'>active_grasp</a></td><td>108</td><td>Closed-loop next-best view planning for grasp dete</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waverider'>waverider</a></td><td>107</td><td>RMPs on multi-resolution occupancy maps for effici</td></tr>
<tr><td><a href='https://github.com/ethz-asl/reinmav-gym'>reinmav-gym</a></td><td>106</td><td>Reinforcement Learning framework for MAVs using th</td></tr>
<tr><td><a href='https://github.com/ethz-asl/navrep'>navrep</a></td><td>104</td><td>navrep</td></tr>
<tr><td><a href='https://github.com/ethz-asl/eth_supermegabot'>eth_supermegabot</a></td><td>102</td><td>Instructions for ETH center for robotics summer sc</td></tr>
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>102</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/3d_vsg'>3d_vsg</a></td><td>100</td><td>3D可变场景图，用于长期语义场景变化预测。</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.06.28
