# 计算机视觉领域最新论文 (2026.06.18)

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
<tr><td>2026-06-17</td><td>FAST-LIVGO: A Degeneracy-Robust LiDAR-Inertial-Visual-GNSS Fusion Odometry<br><a href='http://arxiv.org/pdf/2606.19190'>论文</a></td><td>◆ FAST-LIVGO提出一种基于误差状态迭代卡尔曼滤波的紧耦合LiDAR-惯性-视觉-GNSS融合里程计，面向长距离、大尺度和动态环境中的稳健定位建图。
◆ 其在线时空对齐模块引入动态时间规整，提升多传感器在高速和强动态条件下的同步与融合可靠性。
◆ 方法设计了基于多普勒频移和固定锚点时间差分载波相位的GNSS观测模型，在不增广历史状态的情况下提供毫米级相对约束。
◆ 针对几何退化或纹理缺失场景，提出退化感知的双模式外点剔除策略，可在LIVO先验引导和GNSS辅助恢复之间自适应切换。
◆ 在M3DGR和20 m/s固定翼无人机数据集上的实验表明，该系统显著降低累计漂移和地图重影，精度与鲁棒性优于现有方法。</td></tr>
<tr><td>2026-06-17</td><td>Sensor Configuration Matters: A Systematic Evaluation of Multimodal SLAM on Quadruped Robots<br><a href='http://arxiv.org/pdf/2606.19067'>论文</a></td><td>◆论文针对四足机器人腿式运动带来的冲击、振动和快速旋转问题，系统研究了不同传感器硬件配置对多模态SLAM性能的影响。

◆作者基于ANYmal D四足机器人采集的GrandTour数据集，对视觉、视觉惯性和LiDAR-视觉-惯性SLAM方法进行了统一评测。

◆研究定量比较了相机模态、快门类型和不同等级IMU在定位精度、鲁棒性和计算资源消耗上的权衡。

◆实验发现，双目配置整体优于单目和RGB-D，全局快门相比卷帘快门能显著减少运动导致的跟踪失败。

◆一个重要结论是，在剧烈腿式运动下，常规惯性融合反而可能削弱以视觉为主的SLAM系统性能，为四足机器人传感器载荷设计提供了实用指南。</td></tr>
<tr><td>2026-06-17</td><td>A High-accuracy Event-based Underwater SLAM System<br><a href='http://arxiv.org/pdf/2606.18951'>论文</a></td><td>◆提出首个高精度事件相机水下双目SLAM系统，针对水下速度波动、宽基线和重复纹理导致的TS质量下降与匹配失败问题进行系统性解决。
◆设计基于结构张量相干性与梯度的TS结构感知度量，用于量化时间表面中的结构信息密度。
◆将最优TS生成按初始化前后解耦：初始化前用贝叶斯优化预测先验TS，跟踪阶段用异步在线局部搜索实时更新合适TS。
◆引入先验视差保障精确数据关联，并采用“最新观测优先”的三角化机制提升三维点构建稳定性。
◆构建并开源首个高质量真实水下事件数据集UWE，覆盖可变运动、复杂纹理和多类轨迹，实验表明系统精度达到或优于现有事件SLAM方法。</td></tr>
<tr><td>2026-06-17</td><td>C-ARC: Continuous-Adaptive Range Clustering for Non-Repetitive LiDAR Sensors<br><a href='http://arxiv.org/pdf/2606.18948'>论文</a></td><td>◆ C-ARC面向非重复式Risley棱镜LiDAR，解决其无规则扫描线、无明确帧边界和点云分布不均导致传统聚类方法失效的问题。  
◆ 提出连续自适应距离聚类框架，在滑动窗口中维护持久化双图结构，将高频点插入与按需簇提取解耦，适配SLAM和目标跟踪等实时任务。  
◆ 设计自适应距离网格分辨率机制，通过初始化阶段的指数控制循环自动校准网格尺寸，无需预知扫描模式。  
◆ 该机制在稀疏性与网格碰撞之间取得平衡，并可提升现有网格聚类方法在非重复LiDAR数据上的聚类质量。  
◆ 系统以开源单线程C++17库实现，可在普通硬件上对Livox Mid-360实现20 Hz实时聚类，同时评估指出强集中扫描传感器中无界单元占用是主要限制。</td></tr>
<tr><td>2026-06-16</td><td>RICH-SLAM: Radar SLAM with Incremental and Continuous Hilbert Mapping<br><a href='http://arxiv.org/pdf/2606.17534'>论文</a></td><td>◆ RICH-SLAM提出了一种面向雷达传感器的SLAM框架，旨在解决雷达数据稀疏、噪声大而难以构建稠密一致地图的问题。
◆ 其后端采用Rao-Blackwellized粒子滤波结构，用粒子滤波估计机器人位姿，并用卡尔曼滤波增量更新地图参数。
◆ 论文引入基于Hilbert空间低秩高斯过程的增量映射方法，可从稀疏雷达观测中生成连续、稠密且带不确定性的占据地图。
◆ 作者设计了后验感知的粒子权重计算机制，利用地图参数的完整后验分布进行似然评估，从而提升定位与建图的鲁棒性。
◆ 在自采数据和公开ColoRadar数据集上的实验表明，RICH-SLAM能有效构建连续雷达占据地图，并支持移动机器人的不确定性感知规划。</td></tr>
<tr><td>2026-06-15</td><td>CrossMaps: Confidence-Aware Open-Vocabulary Semantic Mapping for Rover Navigation<br><a href='http://arxiv.org/pdf/2606.16935'>论文</a></td><td>本文提出了CrossMaps，一个用于探测车导航的实时置信度感知开放词汇语义建图管线，能够基于RGB-D数据构建支持自然语言查询的地图。
◆创新性地将多尺度CLIP嵌入与置信度感知融合相结合，利用几何、语义和时间置信度线索来有效聚合噪声视觉观测。
◆提出了双记忆架构，短期记忆处理动态噪声观测，长期记忆则将高置信度且连贯的单元提升为持久语义地标。
◆实现了在Jetson Orin边缘平台与SLAM协同的实时部署方案，生成可查询语义热图引导导航。
该系统有效解决了部分可观测环境下感知与导航的耦合问题，提升了探测车导航的可靠性。</td></tr>
<tr><td>2026-06-15</td><td>SGM-SLAM: Scene Graph Matching for Data-Efficient Distributed SLAM<br><a href='http://arxiv.org/pdf/2606.16881'>论文</a></td><td>本文提出了一种面向多机器人团队的数据高效分布式SLAM框架，利用场景图匹配来识别机器人间的测量约束。
◆首次仅利用对象标签和质心进行场景图匹配以识别机器人间约束，区别于以往依赖特征级匹配的方法。
◆创新性地通过融合RGB-LiDAR点云构建场景图，生成语义分割点云层与离散有界对象层伴随机器人轨迹。
◆通过协作交换与匹配邻居机器人的对象数据完成场景图匹配，并采用多步数据交换与优化过程最大化通信效率。
该框架在室内外真实腿式机器人及仿真数据集上均验证了其有效性与高效性。</td></tr>
<tr><td>2026-06-15</td><td>MVOFormer: Flow-Semantic Transformer for Robust Monocular Visual Odometry<br><a href='http://arxiv.org/pdf/2606.16474'>论文</a></td><td>本文提出了一种用于鲁棒单目视觉里程计的新型Transformer框架MVOFormer，解决了现有学习方法缺乏可解释互补特征和架构复杂的问题。
◆提出流语义双分支编码器，协同融合密集几何运动线索与以物体为中心的语义先验，显式区分静态结构与动态干扰物。
◆设计迭代多模态解码器，融合上述表征实现由粗到细的位姿细化，并动态抑制对不可靠区域的注意力。
该框架无需任何目标域微调，即可在多种基准测试中实现卓越的零样本泛化能力与鲁棒性。
在TartanAir等四个多样化数据集上的广泛评估表明，MVOFormer显著优于以往基于学习的帧到帧方法。</td></tr>
<tr><td>2026-06-14</td><td>A Smart-Scheduled Hybrid (SSH) EKF-FGO State Estimation<br><a href='http://arxiv.org/pdf/2606.16057'>论文</a></td><td>该论文针对状态估计中精度与计算成本的平衡问题，提出一种智能调度混合SSH EKF-FGO框架，作为显式研究优化调度作用的受控测试平台。
◆将优化调度作为独立设计变量进行实验性表征，明确其如何控制中间估计精度与计算成本的权衡。
◆通过固定求解器结构与计算量，结合EKF状态传播与周期性批处理优化，成功剥离并孤立出优化调度变量。
◆基于平面SLAM仿真，揭示了优化调度对优化前漂移、瞬态误差及运行时的强烈影响。
研究发现了能以极小计算成本保留大部分全局优化收益的运行机制，凸显了优化调度在混合状态估计中是未被充分探索却至关重要的因素。</td></tr>
<tr><td>2026-06-13</td><td>FD-SLAM: Fast Dense Radar-Inertial SLAM with Frequency-Domain Loop Closure and Pose Graph Optimization<br><a href='http://arxiv.org/pdf/2606.15491'>论文</a></td><td>◆ 提出FD-SLAM，一种快速稠密雷达-惯性SLAM系统，在稠密雷达-惯性里程计基础上加入频域回环检测与位姿图优化，面向视觉退化环境下的地面车辆定位建图。

◆ 设计了紧凑的频域极坐标描述子，保留扫描雷达数据的类图像结构，用于高效检索长轨迹中的回环候选，提升雷达测量匹配的可靠性。

◆ 构建多阶段回环验证流程，包括时间滤波、相位相关筛选、扫描对齐相似度评估和几何一致性检查，从而降低雷达噪声和误匹配带来的影响。

◆ 将验证后的回环作为非连续约束加入SE(2)位姿图，并与雷达-惯性里程计因子联合优化，有效减小累计漂移。

◆ 在公开数据集上使用KITTI指标评估，结果表明FD-SLAM相比FD-RIO基线有明显提升，并在多条驾驶轨迹上展现出具有竞争力的精度，尤其是旋转精度表现较好。

◆ 运行时间分析显示，其雷达-惯性前端可在纯CPU环境下超过雷达采样率运行，回环检测和图优化也适合并行后台执行，具备较好的实时应用潜力。</td></tr>
<tr><td>2026-06-09</td><td>Information-Preserving Continuous Occupancy Mapping with Variance-Weighted Submap Joining<br><a href='http://arxiv.org/pdf/2606.10442'>论文</a></td><td>本文提出了首个连续概率子图拼接框架，在隐对数几率空间联合优化子图位姿和全局占据率场，解决了离散网格方法梯度不平滑及忽略估计不确定性的问题。
◆提出信息保留的稀疏贝叶斯公式，将原始观测压缩为充分统计量对数几率元组，有效保留了原始观测的后验信息。
◆推导出占据率映射的闭式预测均值和方差估计，直接实现了具有解析雅可比矩阵的子图拼接公式。
◆在位姿收敛时可直接获得闭式最优全局地图，提高了地图优化的准确性与效率。
实验表明，该方法比网格方法具有更高的位姿精度和全局一致性，同时比现有连续方法生成的地图更紧凑且不确定性校准更好。</td></tr>
<tr><td>2026-06-08</td><td>Efficient Minimal Solvers for Visual-Inertial Relative Pose Estimation in Multi-Camera Systems<br><a href='http://arxiv.org/pdf/2606.09477'>论文</a></td><td>本文针对多相机系统相对位姿估计计算复杂度高和依赖过多点对应的问题，提出了两种基于新型参数化的高效最小求解器。
◆利用惯性测量单元提供的垂直方向先验设计第一种求解器。
◆利用惯性测量单元提供的旋转轴方向先验设计第二种求解器。
◆仅需四个点对应即可完成估计，并将问题降阶为求解单变量六次多项式，显著优于现有方法的八次多项式。
上述创新大幅降低了计算复杂度与数据需求，使其在RANSAC框架中表现优异，非常适合视觉里程计应用。
在合成数据和KITTI数据集上的实验验证了该方法具备卓越的计算效率与极具竞争力的精度。</td></tr>
<tr><td>2026-06-06</td><td>G2G: Exploiting Intra-Group Geometry for Inter-Group Pose Estimation<br><a href='http://arxiv.org/pdf/2606.08284'>论文</a> | <a href='https://github.com/WeiYuFei0217/G2G'>代码</a></td><td>本文提出G2G方法解决跨图像组的6自由度相对位姿估计问题，弥补了现有模型将视图视为无结构集合而忽略跨组推理的不足。该方法在冻结视觉基础模型的同时，以极低的参数量和纯位姿监督实现了跨越多个数据集的最先进精度。
◆设计三个轻量级模块，包括感知重采样器、含合并自注意力的跨组桥接和多帧位姿头，有效建立了组间联系。
◆保持预训练基础模型完全冻结，仅新增约3200万可训练参数，占比不足6%，极大降低了计算与存储开销。
◆仅需相对位姿进行监督，无需额外复杂监督，并在室内外仿真、跨季节实景及零样本迁移等四项测试中超越了全量监督重训的基线模型。</td></tr>
<tr><td>2026-06-06</td><td>X-OP: Cross-Morphology Whole-Body Teleoperation via MPC Retargeting<br><a href='http://arxiv.org/pdf/2606.07934'>论文</a></td><td>本文提出了一种由单个XR设备驱动的分层全身遥操作框架，解决了现有方法成本高、需重训策略及忽略动态可行性等问题，实现了跨机器人形态的泛化。
◆提出基于模型预测控制的运动重定向器，联合优化操作意图对齐与机器人动态可行性，为底层控制器生成最优指令。
◆引入状态同步机制与基于SLAM的全局位姿反馈，前者在每个MPC步长重置仿真器状态以应对噪声与接触敏感性，后者缓解长期漂移，确保鲁棒的在线执行。
仿真实验表明该方法表现优异，使人形机器人完成时间降超30%、功耗降20%，移动机械臂实现零碰撞。
真实世界实验进一步验证了其有效性与灵活性，该即插即用框架支持跨平台部署及用户偏好定制，提供了可扩展的通用解决方案。</td></tr>
<tr><td>2026-06-04</td><td>RadiusFPS: Efficient Farthest Point Sampling on CPUs and GPUs via Spherical Voxel Pruning<br><a href='http://arxiv.org/pdf/2606.06255'>论文</a></td><td>针对最远点采样在处理大规模点云时时间复杂度高导致实时机器人感知受限的问题，本文提出了基于球面体素剪枝的FPS加速框架RadiusFPS。
◆通过球面体素索引推导保守的几何边界，在每次迭代中剪枝冗余的距离计算。
◆引入坐标级点跳过测试，进一步消除残差更新。
◆提出RadiusFPS-G，一种warp级GPU实现，将体素选择、剪枝和距离更新融合到内存合并的内核中，避免高开销的全局内存往返。
实验表明，RadiusFPS-G相比GPU版FPS实现高达2.5倍加速，在保持精度的同时比QuickFPS节省近一半显存且速度更优。
结合FastPoint采样器后，该流水线实现了最快的端到端推理，使高质量FPS在资源受限的机器人视觉中变得实用。</td></tr>
<tr><td>2026-06-04</td><td>Breaking Time: A Fully Gaussian Framework for Distributed and Continuous-Time SLAM<br><a href='http://arxiv.org/pdf/2606.06250'>论文</a></td><td>本文提出了G-solver，一个全高斯且分布式的连续时间SLAM框架，旨在解决异构异步传感器的轨迹估计问题。
◆结合高斯置信传播与高斯过程运动先验，实现了连续时间轨迹的分布式估计。
◆利用高斯过程模型提供轨迹的概率表示，支持一致性插值及数据驱动超参数的使用。
◆采用高斯置信传播的消息传递机制，提升了求解器的可扩展性并适用于去中心化场景。
◆该框架能自然扩展至多相机场景，免去了繁琐的专门同步与工程处理。
实验表明该方法在卷帘快门和分布式多相机优化中估计准确稳定，运行效率与现有方法相当并已开源。</td></tr>
<tr><td>2026-06-04</td><td>Towards Realistic 3D Sonar Simulation<br><a href='http://arxiv.org/pdf/2606.06130'>论文</a></td><td>针对现有3D声纳仿真多采用几何驱动渲染而忽略折射和多径干扰等基础声学现象的问题，本文提出了一种结合物理声学传播原理与GPU加速图形引擎的模块化逼真3D声纳仿真架构。
◆提出并实现了基于物理的体积3D声纳模型，弥补了传统方法将其简单等同于水下激光雷达的不足。
◆在NVIDIA Isaac Sim环境中构建了综合水下仿真框架，并集成了参考真实传感器Water Linked 3D-15的模型。
◆采用硬件在环配置进行系统验证，在边缘计算平台上成功运行修改版FastLIO2 SLAM以融合合成声纳及多传感器数据。
论文还通过仿真结果与真实港口板桩检测数据的定性对比，深入剖析了当前仍存的虚实差距。
该研究为未来迈向完全声学驱动的体积传感建立了清晰的路线图。</td></tr>
<tr><td>2026-06-03</td><td>Teaching Robots to Say &#x27;I Don&#x27;t Know&#x27; : SENTINEL for Uncertainty-Aware SLAM<br><a href='http://arxiv.org/pdf/2606.04853'>论文</a></td><td>本文提出SENTINEL框架，解决了低成本2D激光雷达缺乏强度通道而无法诊断测量失效的问题。
◆该框架免训练且免标签，创新性地结合基于几何的扫描统计量与激光雷达和RGB-D相机的跨模态深度一致性，计算零到一的逐扫描可靠性评分。
◆当评分低于阈值时，系统主动拒绝损坏的扫描数据并退回校准的轮式里程计，有效防止无声的SLAM损坏。
◆针对仿真中缺失的透明和反光等失效模式，该研究完全在真实硬件上验证，生成的空间可靠性图谱能清晰分离正常与失效情况。
这使得机器人具备不确定性感知能力，能够识别并拒绝噪声区域，显著提升了低端平台SLAM的鲁棒性。</td></tr>
<tr><td>2026-06-03</td><td>BPDA-GMM: Bayesian Probabilistic Data Association via Gaussian Mixture Models for Semantic SLAM<br><a href='http://arxiv.org/pdf/2606.04618'>论文</a> | <a href='https://github.com/thanhnguyencanh/BPDA-SLAM'>代码</a></td><td>本文提出了一种用于语义SLAM的在线贝叶斯概率数据关联框架BPDA-GMM，解决了现有方法假设固定路标、重复计算权重或依赖人工调参的局限。
◆引入基于狄利克雷过程先验的中国餐馆过程关联模型，自动分配新旧路标概率，无需人工调整零假设权重。
◆结合语义几何门控与CRP权重计算关联概率，以闭式更新语义高斯路标，构建高斯混合模型并提取主成分作为最大混合因子传给后端。
◆当关联权重模糊时，引入由模糊性触发的alpha散度回火步骤以增强路标区分能力。
◆设计解耦后端，将语义因子的位姿雅可比矩阵置零，使噪声检测能优化路标而不直接扰动轨迹。
实验证明该方法在轨迹精度、语义建图质量及鲁棒性上均优于现有基线。</td></tr>
<tr><td>2026-06-10</td><td>Triangle Splatting SLAM<br><a href='http://arxiv.org/pdf/2605.31419'>论文</a></td><td>本文提出了一种使用可微三角形作为三维地图表示的稠密RGB-D SLAM系统。与3D高斯溅射不同，三角形天然兼容传统渲染硬件及需要显式几何的下游任务。
◆首次提出基于三角形溅射的稠密SLAM系统，通过对无结构三角形汤进行在线可微渲染来联合执行追踪与建图。
◆利用受限德劳内三角剖分将地图在线转换为连通网格，赋予了系统在线网格变形和碰撞检查的新能力。
在Replica和TUM-RGBD数据集上，该系统在三维几何重建上优于基线，追踪精度与之持平，并实现了在线场景编辑。</td></tr>
</tbody>
</table>
</div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-05-29</td><td>Beyond Instance-Level Alignment and Uniformity: Semantic Factor Learning for Collaborative Filtering<br><a href='http://arxiv.org/pdf/2605.31414'>论文</a></td><td>本文提出SaFeAU框架，通过语义因子增强对齐与均匀性，解决传统协同过滤实例级学习导致的假阴性标签问题，使矩阵分解无需图邻域聚合即可捕获高阶协同过滤信号。
◆提出语义因子路由，将物品表示解耦为独立的全局语义因子。
◆设计语义因子匹配，识别与已交互物品共享语义因子的未交互物品作为潜在正样本，丰富稀疏监督信号。
◆构建语义对齐，同时对观测和潜在正样本对进行对齐，并促进用户与物品表示的均匀性。
实验表明，该框架在稀疏数据集上的推荐准确度和计算效率均优于现有的图卷积与矩阵分解方法。</td></tr>
<tr><td>2026-05-28</td><td>The JADES Mass-Metallicity and Fundamental Metallicity Relations at $z\gtrsim2$ Using New High-Redshift Metallicity Calibrations<br><a href='http://arxiv.org/pdf/2605.30513'>论文</a></td><td>本文基于JWST先进深场河外巡天(JADES)的NIRSpec光谱数据,对601个星形成星系进行叠加分析,系统测量了红移1.4&lt;z&lt;7.0范围内的质量-金属丰度关系(MZR)与基本金属丰度关系(FMR),揭示了高红移宇宙中星系化学演化的规律。研究发现MZR斜率从z~0到z~5演化较弱(γ~0.21),归一化随红移以d log(O/H)/dz~-0.1的速率平滑下降;在z≳5以上,低质量端金属丰度持续下降而高质量端保持稳定,导致MZR整体变陡。研究还发现z~1.4-5存在MZR残差与主序偏移之间的弱反相关性,表明FMR在z~5时已开始显现。

◆ 首次采用基于高红移星系校准的最新强线金属丰度诊断方法,克服了以往使用本地校准外推到高红移的系统性偏差。

◆ 利用JADES提供的601个星系的大样本NIRSpec光谱,通过按恒星质量、红移和主序偏移的三维分箱叠加,首次在z≳5实现对FMR的统计性约束。

◆ 揭示了z≳5时MZR形态发生显著变化(低质量端持续贫金属化、高质量端停滞),为高红移星系受爆发式恒星形成与强反馈调控的图景提供了关键观测证据。

◆ 发现高红移FMR中SFR耦合强度弱于本地宇宙,表明气体调节机制在z~5左右才开始建立,为星系演化理论提供新约束。

◆ 系统对比多种宇宙学模拟,指出现有模拟均无法同时再现各红移下的MZR斜率与归一化,凸显了反馈物理模型的不足。</td></tr>
<tr><td>2026-05-28</td><td>City-Mesh3R: Simulation-Ready City-Scale 3D Mesh Reconstruction from Multi-View Images<br><a href='http://arxiv.org/pdf/2605.30310'>论文</a></td><td>本文提出City-Mesh3R框架，实现从大规模无序图像直接重建适用于仿真的城市级高保真水密三维网格，克服了现有方法几何缺失和表面噪声的问题。
◆采用基于分治策略的端到端图像到网格重建流程，取代传统的全局稀疏SfM初始化与分布式稠密重建，使模型可扩展至任意大规模场景。
◆利用拓扑图像聚类进行聚类独立稀疏SfM与地图合并，无需穷举图像特征匹配即可构建稀疏城市地图。
◆结合几何感知相机选择与曲率感知自适应顶点密度重网格化技术进行表面细化，有效保障网格几何规则且细节精细。
◆通过空间分区与网格缝合技术无缝拼接局部网格，生成全局水密城市网格，验证了分布式端到端处理的卓越扩展性与重建保真度。</td></tr>
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
</tbody>
</table>
</div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-06-16</td><td>VEGA: Learning Navigation VLAs from In-the-Wild Egocentric Video with Geometric Trajectory Supervision<br><a href='http://arxiv.org/pdf/2606.18426'>论文</a></td><td>◆ VEGA提出了一种从未标注的第一人称野外导航视频中训练导航Vision-Language-Action模型的方法，利用互联网规模视频作为可扩展数据源。

◆ 它通过单目视频重建局部场景几何，并基于文本、图像或空间路标采样导航目标，生成机器人坐标系下的避障轨迹监督。

◆ VEGA仅在训练阶段使用几何信息，将避障规划能力蒸馏到纯视觉策略中，并采用flow-matching训练VLA导航策略。

◆ 论文还构建了VEGA-Bench，包含25万场景和约500万导航目标，用于系统评估目标推进、碰撞避免和障碍间距。

◆ 实验表明，VEGA在基准测试中显著减少碰撞并提升避障间距，在真实世界试验中也大幅提高成功率，证明视频派生几何监督是训练避障导航VLA的有效可扩展信号。</td></tr>
<tr><td>2026-06-15</td><td>Optimal Bounded Thrust Powered Descent with Analytical Ground-Collision Avoidance<br><a href='http://arxiv.org/pdf/2606.17050'>论文</a></td><td>本文提出了一种解决有界推力动力下降并确保避撞的新方法，通过质量多项式近似构建了有界线性二次最优控制问题。该方法的核心是推力分配的分层分离，对水平推力施加硬约束而保持垂直推力无约束。
◆与基于数值优化和轨迹成型的现有方法不同，该方法提供了显式的解析避撞条件。
◆制导律能预测饱和与未饱和弧段的切换时间并塑造推力曲线，在控制器长时间饱和时仍可实现软着陆。
由于具有解析特性，该制导律计算高效且推力曲线连续，便于实时应用，仿真验证了其在扰动下精确的无碰撞软着陆性能。</td></tr>
<tr><td>2026-06-15</td><td>Instance-Aware Knowledge Distillation for Semi-Supervised Learning of an On-Board Multi-Task Dense Prediction Model for Collision Avoidance System<br><a href='http://arxiv.org/pdf/2606.16414'>论文</a></td><td>◆提出面向碰撞避免系统的实例感知知识蒸馏半监督框架，降低目标场景大规模标注需求。
◆伪标签生成同时利用教师模型的领域先验与基础模型的实例级知识，从而缓解教师偏差并提升实例分割质量。
◆训练得到轻量级车载多任务密集预测学生模型，可同时执行前方障碍物检测/实例分割与单目深度估计。
◆构建大规模乡村俱乐部场景数据集，并将模型集成到实际系统中，通过CAN消息编码障碍物空间信息以支持AGV运行。
◆实验表明学生模型在实例分割上超过大教师模型，同时显著降低深度估计性能退化，并以22.68倍FLOPs和14.33倍参数压缩实现低成本边缘设备实时运行。</td></tr>
<tr><td>2026-06-15</td><td>SemGeoNav:A Safety-Guided Visual Navigation Approach with Semantic Reasoning and Geometric Planning<br><a href='http://arxiv.org/pdf/2606.16400'>论文</a></td><td>针对端到端模型缺乏几何约束导致避障不可靠，以及传统几何规划难以处理高维视觉目标的问题，本文提出了SemGeoNav分层视觉导航框架。该框架将端到端模型的高级语义推理与基于几何的可靠局部规划紧密结合，实现了鲁棒的图像导航并显著提升了避障能力。
◆提出语义推理与几何规划紧耦合的分层架构，兼顾高维语义目标处理与物理避障安全。
◆引入时序轨迹平滑机制，确保机器人运动的连续性与稳定性。
在真实环境四足机器人上的实验表明，该方法在成功率和导航时间上均优于ViNT和NoMaD等现有方法。</td></tr>
<tr><td>2026-06-15</td><td>PolyMerge: Compressing 3D Gaussian Splats with Polytope Coverings for Provably Safe Resource-Constrained Navigation<br><a href='http://arxiv.org/pdf/2606.16232'>论文</a> | <a href='https://athlon76.github.io/PolyMerge-website/'>代码</a></td><td>本文提出PolyMerge方法，将大规模的3D高斯溅射模型转换为轻量级的凸多面体表示，以解决3DGS模型在机载感知路径规划中计算和内存开销过大的问题。
◆提出基于凸多面体覆盖的3DGS压缩方法，其多面体合集可证明对原3DGS模型中的所有障碍物进行保守包络。
◆支持调节多面体数量，灵活权衡避障的保守性与计算成本。
◆将多面体表示与控制障碍函数深度融合，实现可证明安全的无碰撞路径规划。
无人机硬件与仿真实验表明，该方法在极严苛的机载算力下实现了实时安全轨迹规划，在保证安全的同时运行速度超越基线方法。</td></tr>
<tr><td>2026-06-14</td><td>$λ$-Reachability: Geometric-Horizon Safety Bellman Equations for Humanoid Safety<br><a href='http://arxiv.org/pdf/2606.16022'>论文</a></td><td>本文提出了λ-Reachability方法，为高维机器人系统提供了一种可扩展的哈密顿-雅可比安全分析方案。
◆不同于先前依赖固定单步贝尔曼更新的折扣公式，该方法采用具有几何分布推演视界和随机吸收终端的随机多步安全值估计器。
◆通过可解释的视界控制参数，该方法在局部自洽更新与长视界最大化轨迹安全目标之间进行插值。
◆不同于TD(λ)总包含终端值，其终端安全值仅在参数δ控制的概率下使用，在δ小于1时产生支持时序差分学习的收缩映射，且当λ趋于1时能恢复无折扣可达性目标。
实验表明，该方法在仿真与真实人形机器人的平衡和避障任务中，显著提升了安全集边界分类与安全裕度估计的准确性。</td></tr>
<tr><td>2026-06-14</td><td>FlashNav: Ultra-Fast Policy Training for Robot Navigation within 20 Seconds<br><a href='http://arxiv.org/pdf/2606.15846'>论文</a></td><td>本文提出了FlashNav，这是首个实现秒级策略训练的基于深度强化学习的机器人导航框架，最快可在20秒内完成部署级策略的训练。
◆提出与导航马尔可夫决策过程对齐的轻量化仿真思想，保留占据几何和运动动力学等核心组件，剔除了冗余渲染和高保真物理细节。
◆构建基于批量位图仿真器和全GPU驻留训练管线的架构，结合FastDSAC学习器，实现导航经验在GPU上的大规模并行生成。
◆首次在桌面级显卡上将深度强化学习导航训练时间缩短至20秒内，且策略在标准测试中达到百分之百成功率。
实验表明，该框架训练出的策略可直接迁移至真实的轮式和足式机器人，在静态和动态室内场景中均展现出鲁棒的避障导航能力。</td></tr>
<tr><td>2026-06-14</td><td>Can Causal Models Enhance Robot Navigation? Online Causal Adaptation for Real-Robot Navigation<br><a href='http://arxiv.org/pdf/2606.15691'>论文</a></td><td>本文探索了将因果模型迁移至真实机器人导航场景的挑战，证明了用于行为解释的因果模型能成功整合到实际导航系统中。核心贡献在于通过离线与在线两种方式验证了因果模型对导航性能的提升作用。具体创新点如下：
◆将因果模型作为离线评估模块，预测真实导航轨迹的胜任度并关联其定量表现，发现该预测与路径效率正相关、与不规则性负相关，且与人类标注高度一致。
◆将因果模型作为在线自适应模块，在默认导航预测胜任度低时实施干预，在转弯和避障等复杂场景中有效提升了导航指标，而在简单场景提升有限。
结果表明因果模型在任务复杂性增加时对增强导航尤为有效。</td></tr>
<tr><td>2026-06-13</td><td>Hamilton-Jacobi Reachability-Based Safe Reinforcement Learning for Emergency Collision Avoidance<br><a href='http://arxiv.org/pdf/2606.15311'>论文</a></td><td>本文提出了一种基于哈密顿-雅可比可达性运动安全集引导的安全强化学习框架，用于解决极端驾驶条件下紧急避障的前瞻性安全控制问题。
◆构建了结合几何碰撞边界与底盘稳定性极限的统一符号安全函数，并通过可达性分析将其扩展为有限时域运动安全集，以表征未来车辆状态演化下的安全性。
◆利用离线极端驾驶数据近似运动安全集，有效减轻了传统基于网格的HJ求解器带来的巨大计算负担。
◆将学习到的安全集作为连续安全代价嵌入约束马尔可夫决策过程，并采用PID-拉格朗日策略优化方案自适应调节拉格朗日乘子以严格执行安全约束。
仿真与实车实验表明，该方法在低附着避障场景下实现了更高的目标到达率、更平滑的避障动作以及更大的统一安全裕度。</td></tr>
<tr><td>2026-06-12</td><td>Sensitivity Shaping for Latent Modeling<br><a href='http://arxiv.org/pdf/2606.14585'>论文</a></td><td>现有生成动力学模型在安全部署时需检测策略引发的分布外转移，但传统后验支持代理在动力学对关键动作局部不敏感时会失效，导致异常控制动作产生的潜在预测掩盖了真实的预测误差。本文针对此问题，提出了一种支持条件控制敏感度正则化方法来塑造潜在建模的敏感度。
◆引入支持条件控制敏感度正则化，促进高支持训练区域中动力学对控制输入变化的敏感局部响应。
◆在保留控制引起变异的同时，有效限制了由于经验支持不足导致的不稳定外推。
实验表明，该方法在视觉避障、操作和真实机器人导航任务中，显著提升了分布外检测能力与闭环规划的安全性。</td></tr>
<tr><td>2026-06-12</td><td>ForestBack: Breadcrumb-Based Pedestrian Dead Reckoning for Infrastructure-Free Return Navigation<br><a href='http://arxiv.org/pdf/2606.14421'>论文</a></td><td>该论文提出了ForestBack，一种无需基础设施支持的面包屑式行人航位推算返回导航框架，解决了无GPS等外部信号环境下的可靠返回导航难题。
◆创新性地将用户行走路线记录为可逆的面包屑节点序列，无需预装基础设施即可生成反向路径引导。
◆融合了加速度计步频检测、自适应步长估计、磁力计辅助航向估计、气压计高度校正以及双向面包屑路径重构技术，提升了轨迹重建精度。
实验结果表明，与传统PDR相比，该系统平均RMSE降低了15.76%，终点位置误差降至1.388米，转向事件检测一致性达99.90%。
此外，论文公开了包含多传感器数据的测试数据集及分析代码，为后续研究提供了可复现的基准。</td></tr>
<tr><td>2026-06-12</td><td>Robustness without Wrinkles: Parallel Simulation and Robust MPC for Certified Deformable Manipulation<br><a href='http://arxiv.org/pdf/2606.14188'>论文</a></td><td>本文提出了CORD-SLS方法，实现了对绳索和布料等可变形物体的安全实时控制。
◆开发了带有接触平滑技术的GPU并行可微模拟器，实现了间歇接触下的高效梯度规划。
◆提出了一种实时GPU并行输出反馈鲁棒模型预测控制算法，以应对模型与感知不确定性并满足约束。
◆利用保角预测校准视觉反馈与感知误差界限，构建可达管道以实现高概率的认证安全控制。
◆证明该模拟器可加速基于模型的强化学习，从而高效训练神经操纵策略。
实验表明该方法在高维接触丰富的任务中实现了毫秒级规划，在安全性速度和成功率上均超越基线。</td></tr>
<tr><td>2026-06-11</td><td>EmbodiSteer: Steering Embodiment-Agnostic Visuomotor Policies with Joint-Space Guidance for Zero-Shot Cross-Embodiment Deployment<br><a href='http://arxiv.org/pdf/2606.12965'>论文</a> | <a href='https://frankwang67.github.io/EmbodiSteer-Page'>代码</a></td><td>论文核心贡献总结:

该论文提出了EmbodiSteer,一个无需训练的框架,用于将与机器人本体无关的视觉运动策略零样本部署到不同机器人上,同时实现本体感知的安全执行。该方法在笛卡尔空间中保持策略学习的可扩展性,并在推理阶段通过正向运动学和雅可比矩阵将扩散采样过程提升到目标机器人的关节空间,从而在保留末端执行器行为的同时避免全身碰撞。实验表明,相比仅笛卡尔执行,该方法在9个仿真机器人上降低碰撞率46.1%、提升任务成功率28.5%,在两个真实机器人的高约束场景下分别达到90.0%碰撞率降低和36.7%成功率提升。

创新点:

◆ 提出训练免费的引导框架,在保持笛卡尔空间策略学习优势的同时,实现推理阶段对目标机器人本体的感知与适配,解决了末端执行器抽象忽略机器人本体约束的核心难题。

◆ 通过正向运动学和基于雅可比矩阵的更新,高效地将扩散采样过程从笛卡尔空间提升至目标机器人的关节空间,实现跨本体推理时的空间转换。

◆ 在每个去噪步骤后引入全身碰撞感知的关节轨迹引导机制,使机械臂在保留已学习末端行为的前提下主动避开碰撞。

◆ 实现真正的零样本跨本体部署,在9个仿真机器人和2个真实机器人上验证了显著的碰撞率降低和成功率提升,展示了方法的通用性与实用性。</td></tr>
<tr><td>2026-06-10</td><td>Koopman-based NMPC for Virtually Coupled Train Control System<br><a href='http://arxiv.org/pdf/2606.11858'>论文</a></td><td>该论文针对虚拟编组列车控制系统的跟踪控制问题,提出了一种基于Koopman算子的解析型非线性模型预测控制(K-NMPC)方法。作者将包含列车动力学、速度与控制输入约束、乘客舒适度约束以及避碰约束的非线性列车运动模型,通过闭式可观测函数系统性地提升到有限维Koopman空间中,从而将原非线性控制问题转化为可高效求解的二次规划问题。仿真结果表明,所提方法在控制性能上与传统时间离散NMPC方案相当,但在线计算时间显著减少,展现出良好的实时应用潜力。

核心贡献和创新点如下:

◆ 首次将解析型Koopman算子方法应用于虚拟编组列车控制系统,为列控领域提供了新的建模与控制思路。

◆ 通过闭式可观测函数将含多类约束的非线性列车运动模型系统性地提升到有限维Koopman空间,避免了传统数据驱动Koopman方法对大量训练数据的依赖。

◆ 提出沿移位预测轨迹冻结仿射参数变化提升预测器的策略,将在线优化问题转化为可高效求解的二次规划问题。

◆ 在保证与传统NMPC相当控制性能的前提下,显著降低了在线计算时间,为虚拟编组列控系统的实时实现提供了可行方案。</td></tr>
<tr><td>2026-06-09</td><td>Free Parametrization of L_2-Bounded Structured State-Space Controllers for Nonlinear Control with Stability Guarantees<br><a href='http://arxiv.org/pdf/2606.11049'>论文</a></td><td>本文针对非线性系统控制中神经网络易失稳和现有约束方法计算开销大的问题，提出了基于结构化状态空间模型的自由参数化方法。
◆提出具有预定L2增益的线性时不变系统的新型自由参数化方法。
◆构建L2循环单元，该状态空间模型层在设计上天然强制执行L2界限。
◆结合小增益定理或性能提升框架，在无需约束优化参数的情况下保证闭环稳定性，实现完全无约束优化。
◆所提参数化结构支持并行扫描算法，能够高效处理长输入序列。
移动机器人编队控制实验验证了该方法在保证稳定性和性能的同时能有效避障。</td></tr>
<tr><td>2026-06-09</td><td>Language-Driven Cost Optimization for Autonomous Driving<br><a href='http://arxiv.org/pdf/2606.10974'>论文</a></td><td>本文提出了一种用于自动驾驶自适应代价设计的语言驱动框架，解决了传统代价参数调整依赖专业知识且难以适应动态场景与用户偏好的问题。
◆利用大语言模型解释结构化场景描述和自然语言查询，为风险感知MPPI控制器自动生成代价参数。
◆引入人机回环验证机制，在部署前用非技术语言向用户描述行为变更并获取确认。
◆支持用户在部署前后提供反馈，实现了车辆运动行为的持续迭代优化。
仿真结果表明该系统能直观地实现符合意图的行为改变，有效弥合了智能车辆控制系统与终端用户之间的鸿沟。</td></tr>
<tr><td>2026-06-14</td><td>Act on What You See: Unlocking Safe Social Navigation in Vision-Language-Action Models<br><a href='http://arxiv.org/pdf/2606.10495'>论文</a></td><td>本文提出SALSA框架，解决了预训练视觉-语言-动作模型虽已编码行人区分与碰撞信号，但行为克隆无法将其转化为安全社交动作的问题。
◆社交行为对齐，将中间层社交特征桥接至动作头，并利用反事实人-物场景对进行训练以打破视觉显著性捷径。
◆时序安全对齐，通过自动生成的未来风险监督信号，使模型能够实现前瞻性的碰撞规避。
实验表明，SALSA在无需额外标注的情况下将近距离碰撞减少了86.4%，并将社交反事实准确率从53%提升至93%。
该研究证明，通过更好地对齐潜层表征与动作生成，即可让模型依据已有表征行动，成功解锁预训练VLA策略的安全社交导航潜能。</td></tr>
<tr><td>2026-06-13</td><td>GuideWalk: Learning Unified Autonomous Navigation and Locomotion for Humanoid Robots across Versatile Terrains<br><a href='http://arxiv.org/pdf/2606.10449'>论文</a></td><td>本文提出了GuideWalk框架，这是一个将可穿越性感知导航引导与地形自适应运动教师相结合的统一端到端人形机器人导航框架。
◆引入提供显式速度引导的导航模块，将避障与地形条件解耦，从而在多样环境中实现鲁棒规划。
◆提出复合教师蒸馏方案，将目标导向指令与动态一致动作聚合并蒸馏至单一策略中。
◆采用强化学习和辅助行为克隆目标精炼蒸馏策略，在促进探索的同时保留教师的优良行为。
实验表明，该框架能够在各种复杂地形上实现稳定且有效的人形机器人导航与运动控制。</td></tr>
</tbody>
</table>
</div>

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-17</td><td>Sensor Configuration Matters: A Systematic Evaluation of Multimodal SLAM on Quadruped Robots<br><a href='http://arxiv.org/pdf/2606.19067'>论文</a></td><td>◆本文针对四足机器人在足端冲击、机械振动和快速旋转下SLAM性能不稳定的问题，系统评估了传感器硬件配置对多模态SLAM的影响。
◆作者基于ANYmal D的GrandTour数据集，对视觉、视觉惯性、激光-视觉-惯性SLAM方法进行了统一比较。
◆论文量化分析了相机模态、快门类型和IMU等级在定位精度、鲁棒性与计算资源消耗之间的权衡。
◆实验发现，双目配置整体优于单目和RGB-D，全局快门相比卷帘快门更能减少运动导致的跟踪失败。
◆一个关键发现是，在剧烈腿式运动中，标准惯性融合反而可能削弱以视觉为主的SLAM性能。
◆论文最终给出了面向敏捷四足机器人的传感器载荷设计建议，为可靠自主导航提供了实践依据。</td></tr>
<tr><td>2026-06-15</td><td>VISTA: Scale-Aware Visual Navigation via Action History Conditioning<br><a href='http://arxiv.org/pdf/2606.17294'>论文</a></td><td>◆ VISTA针对视觉导航基础模型中“归一化动作”带来的尺度部署脆弱性，指出相同归一化轨迹在不同缩放因子下会改变真实运动几何并增加碰撞风险。
◆ 论文提出将归一化动作历史与图像观测共同作为条件输入，使模型显式理解预测动作与机器人实际位移之间的尺度关系。
◆ 该方法提升了跨机器人、跨环境部署时的尺度感知能力，从而增强零样本导航的稳定性和安全性。
◆ 为解决视觉重复、缺乏显著特征场景中的感知困难，VISTA集成DINOv3编码器以获得更丰富的空间与几何表征。
◆ 实验表明，VISTA在室外、森林和办公室等真实未见环境中实现100%零样本目标预测准确率，并平均通过95%的检查点，展现出强泛化和路径跟随能力。</td></tr>
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
<tr><td>2026-06-15</td><td>Embedded Arena: Iterative Optimization via Hardware Feedback<br><a href='http://arxiv.org/pdf/2606.16190'>论文</a></td><td>本文核心贡献是提出一种基于硬件在环的智能体框架，以替代人类专家自主完成边缘微控制器上的AI模型与固件协同优化。
◆提出硬件在环的智能体竞技场机制，利用真实硬件的编译烧录与测量反馈，指导大语言模型进行模型与固件的闭环迭代协同优化。
◆验证了纯大语言模型完全无法完成部署，而引入硬件反馈后仅需3次迭代即可成功部署，7次迭代即可超越人类专家水平。
◆实现了极高的模型压缩比且精度损失极小，视觉模型压缩250倍而精度损失不足3.3%，音频模型压缩400倍，使商用微控制器能依靠太阳能实现无电池运行。
该方法在麋鹿检测相机和语音转录可穿戴设备等真实系统中的成功应用，充分证明了其实用价值与工程意义。</td></tr>
<tr><td>2026-06-14</td><td>FlashNav: Ultra-Fast Policy Training for Robot Navigation within 20 Seconds<br><a href='http://arxiv.org/pdf/2606.15846'>论文</a></td><td>本文提出了FlashNav框架，首次将基于深度强化学习的机器人导航策略训练时间缩短至20秒以内。
该框架训练出的策略能够成功迁移至真实的轮式和足式机器人，在静态与动态室内场景中均展现出可靠的避障能力。
◆提出与导航MDP对齐的仿真理念，保留占据几何与测距感知等核心组件，移除冗余的渲染与高保真物理细节。
◆设计基于批量位图仿真器的全GPU常驻训练流水线，结合FastDSAC学习器在GPU上生成海量并行导航交互数据。
实验表明该框架在多种桌面GPU上均能实现数十秒内的极速训练，并在高端显卡上达到百分之百的成功率。</td></tr>
<tr><td>2026-06-14</td><td>Can Causal Models Enhance Robot Navigation? Online Causal Adaptation for Real-Robot Navigation<br><a href='http://arxiv.org/pdf/2606.15691'>论文</a></td><td>本文核心贡献在于成功将因果模型集成到真实机器人导航系统中，解决了因果模型在真实环境中部署研究不足的问题。
◆提出将因果模型作为离线评估模块，能准确预测导航轨迹的能力，其预测结果与路径效率正相关且与人类标注高度一致。
◆提出将因果模型作为在线自适应模块，在默认导航能力预测较低时进行干预，显著提升了转弯和避障等复杂场景的导航性能。
实验表明因果模型在任务复杂性增加时对导航的增强尤为有效，而在基线已近最优的简单场景中提升有限。
综上，本研究证明了用于行为解释的因果模型能够成功融入并增强真实机器人的导航系统。</td></tr>
<tr><td>2026-06-13</td><td>G2IA: Geometry-Guided Instance-Aware Retrieval and Refinement for Cross-Modal Place Recognition<br><a href='http://arxiv.org/pdf/2606.15287'>论文</a></td><td>本文提出了一种用于跨模态地点识别的几何引导实例感知框架G2IA，突破了传统单一全局描述符匹配的局限，有效应对图像与点云间的模态差异和感知歧义问题。
◆在检索阶段，该框架创新性地将VGGT的视觉几何先验与实例特征相融合，构建出与激光雷达地图表征高度兼容的地点描述符。
◆在精炼阶段，提出通过显式验证局部实例形状及其相对空间布局在跨模态间的一致性，对检索候选进行细粒度重排。
实验证明，G2IA在不同定位阈值下均持续提升了图像到点云的地点识别性能。
同时，该框架还展现出了优异的跨数据集泛化能力。</td></tr>
<tr><td>2026-06-13</td><td>Driving, Fast or Slow? Neuro-Symbolic Guidance for Motion Prediction in Multi-Modal Ground Mobility<br><a href='http://arxiv.org/pdf/2606.15251'>论文</a></td><td>本文提出轨迹合规塑造神经符号框架，通过可解释的概率一阶逻辑增强黑盒运动预测主干网络，解决了现有方法缺乏现实交通规则与行为约束显式编码的问题。
◆提出智能体代码生成流水线，成功将交通规则的自然语言描述转化为概率运动预测的约束。
◆引入反应式数据流推理引擎，能够在场景演进时高效维护并更新合规态势。
◆设计神经置信度评分机制，通过上下文感知衰减合规信号，防止过度自信地误导主干网络的预测方向。
在Argoverse 2基准上的实验表明，该框架能持续提升最先进预测主干的性能，是纯神经预测器的有效且高效的补充。</td></tr>
<tr><td>2026-06-12</td><td>Sensitivity Shaping for Latent Modeling<br><a href='http://arxiv.org/pdf/2606.14585'>论文</a></td><td>本文针对生成式动力学模型中安全检测策略引发的分布外转换问题进行了研究。
现有方法在动力学对关键动作局部不敏感时会失效，导致未支持的动作产生类似演示的预测，从而掩盖了真实的预测误差。
◆揭示了现有固定动力学模型附加事后支持代理时，因局部控制不敏感导致分布外检测信号被抑制的失效机理。
◆提出了支持条件控制灵敏度正则化方法，在高等支持训练区域促进动力学对控制输入变化的敏感局部响应。
◆通过该正则化机制，有效保留了控制引起的变异，同时限制了因经验支持不足导致的不稳定外推。
实验表明该方法显著提升了分布外检测的准确性和闭环规划的安全性。</td></tr>
<tr><td>2026-06-12</td><td>SplatlessDF: Continuous Distance Field Mapping with Non-Splatting Gaussians<br><a href='http://arxiv.org/pdf/2606.13990'>论文</a></td><td>本文提出了SplatlessDF，一个从空间视角利用各向异性高斯元素的连续距离场建图框架。
◆直接参数化高斯并优化恢复可微分距离场，支持在空间域查询距离和梯度，满足机器人导航等下游任务需求。
◆将该方法与二维高斯泼溅耦合，构建仅基于高斯基元的统一框架，同时实现连续距离场学习、表面建模和光度渲染。
◆提出独立距离场与联合渲染两种设置，独立模式提供高效准确的查询，联合模式在改善渲染几何的同时建模距离场。
该研究证明了高斯表示不仅限于表面建模与渲染，在机器人导航建图中同样极具潜力。</td></tr>
<tr><td>2026-06-11</td><td>NavWAM: A Navigation World Action Model for Goal-Conditioned Visual Navigation<br><a href='http://arxiv.org/pdf/2606.13494'>论文</a> | <a href='https://dachii-azm.github.io/navwam/'>代码</a></td><td>这篇论文针对目标条件视觉导航任务,提出了导航世界动作模型(NavWAM),将原本仅用于预测的导航世界模型升级为可直接驱动闭环控制的策略模型,解决了传统世界模型必须依赖外部规划器(如CEM采样搜索)才能转化为可执行动作的问题。作者通过仿真预训练与真实机器人适配相结合的方式构建该模型,并在离线基准测试和真实机器人闭环部署中验证其在图像目标导航任务上优于基于规划的世界模型基线及代表性直接导航策略。

◆ 提出基于扩散Transformer的导航世界动作模型NavWAM,首次将未来观测预测、目标进度价值估计与动作序列统一编码到共享的潜在序列中进行联合学习。
◆ 通过将未来预测与决定闭环行为的动作目标、价值目标联合训练,使视觉前瞻能力可直接用于机器人控制,无需额外规划模块。
◆ 摆脱了对CEM式动作搜索的依赖,采用默认策略模式即可实现高效推理,在性能上反超基于规划的世界模型方法。
◆ 设计了仿真预训练加真实机器人适配的两阶段训练流程,有效弥合了仿真到现实的差距,实现了真实场景下的闭环部署验证。</td></tr>
<tr><td>2026-06-11</td><td>Traceable Virtual Sea Trials in the Marine Robotics Unity Simulator for Manoeuvring Assessment of Unmanned Surface Vehicles<br><a href='http://arxiv.org/pdf/2606.12349'>论文</a></td><td>本文扩展了开源MARUS模拟器，提出一种标准化的虚拟海试框架，用于无人水面艇回转和Z形试验的自动执行与数据生成。
◆开发了专门的TC与ZZ数据采集及后处理管道，生成面向系统辨识的即用型数据集，提升了模拟器操纵的重复性与可审计性。
◆实现了可追溯的指令与执行日志记录，并自动提取符合IMO和ITTC标准的操纵性指标。
◆针对差动推力转向提出了指令与执行的分离机制，将操纵输入记录为等效舵指令，实际执行记录为推力衍生的执行层代理。
案例研究验证了该框架可生成符合IMO标准的可重复操纵行为，有效支持水动力导数辨识与数字孪生工作流。</td></tr>
<tr><td>2026-06-10</td><td>Embodied-BenchClaw: An Autonomous Multi-Agent System for Embodied Spatial Intelligence Benchmark Construction<br><a href='http://arxiv.org/pdf/2606.11909'>论文</a></td><td>本文针对现有具身空间智能基准构建费时费力且易饱和的问题，提出了Embodied-BenchClaw这一自主多智能体基准构建系统。
◆提出了由规划、构建和评估三个智能体协调的五阶段自动化流水线，可根据用户评估意图端到端生成可更新的完整基准包。
◆引入了可扩展的技能库，提升了基准构建的可复用性和组合性。
◆设计了过程质量控制机制，确保基准构建过程可验证且可修复。
通过实例化多种跨载体和空间能力的基准并结合全面实验验证，表明该系统能显著减少人工成本，构建出可靠、可维护且具诊断价值的具身空间基准。</td></tr>
<tr><td>2026-06-10</td><td>SAFER-Nav: Enhancing Safety for Visual Robot Navigation via Segmentation-Aware Fine-Tuning<br><a href='http://arxiv.org/pdf/2606.11636'>论文</a></td><td>本文提出SAFER-Nav模型，通过分割感知微调增强视觉机器人导航的安全性。
◆该模型创新性地通过微调将障碍物边界与可通行自由空间结构显式且直接地融入导航策略中。
◆该方法具有高度的架构通用性，能够广泛兼容多种基于RGB的视觉导航主干网络。
这一设计克服了现有方法仅依赖外部轨迹修正或内部几何先验而未能显式表征安全空间的局限。
实验证明，在多平台和动静障碍物场景下，该方法在保持目标到达性能的同时显著降低了碰撞频率。</td></tr>
<tr><td>2026-06-09</td><td>AgniNav: Configuration-Driven Cross-Embodiment Local Planning for Robot Navigation<br><a href='http://arxiv.org/pdf/2606.10903'>论文</a></td><td>本文提出了AgniNav框架，解决了现有单目导航策略难以跨具身迁移且需重新训练的问题。
◆首次将感知和规划联合条件化于共享的四参数碰撞包络配置，实现跨轮式、四足和人形平台的零重训练部署。
◆在感知端，利用高度参数调节网络从单目图像预测一维碰撞相关伪激光扫描；在规划端，利用其余占地参数配置尺寸感知的局部规划器进行碰撞检查。
◆提出基于高度条件的列最小扫描标签训练法，同一图像可监督不同安全包络，免除了特定机器人数据的采集。
真实机器人实验表明该框架成功率高且碰撞率低，并在边缘计算设备上实现了30赫兹的实时运行。</td></tr>
<tr><td>2026-06-09</td><td>GUIDE: Goal-Initialized Directional Understanding for End-to-End Visual Navigation<br><a href='http://arxiv.org/pdf/2606.10832'>论文</a></td><td>传统基于学习的视觉导航依赖连续目标更新，不仅增加计算开销，且易在部分可观察下陷入局部短视与死胡同。为此，本文提出GUIDE框架，采用仅开局输入一次目标的目标初始化设定，培育机器人的内在方向感知以实现完全端到端的导航。
◆提出空间锚点预测器，利用多频率本体感受历史提取自运动表征，从而维持长视野的空间上下文与持久方向感。
◆结合原始深度流感知局部几何结构，使策略能够在无后续目标更新与先验地图的情况下克服短视行为。
实验证明，GUIDE使四足机器人能在密集障碍与结构化迷宫中安全导航，验证了其可靠的自运动与方向感知能力。</td></tr>
<tr><td>2026-06-13</td><td>GuideWalk: Learning Unified Autonomous Navigation and Locomotion for Humanoid Robots across Versatile Terrains<br><a href='http://arxiv.org/pdf/2606.10449'>论文</a></td><td>本文提出了GuideWalk，一个统一的端到端框架，将可穿越性感知的导航引导与地形自适应运动教师相结合，以解决人形机器人在复杂地形上难以协调避障与动态可行运动的导航挑战。
◆提出一种提供显式速度引导的导航模块，将避障与地形条件解耦，从而实现跨多样环境的鲁棒规划。
◆设计了复合教师蒸馏方案，将目标导向指令和动态一致动作聚合并蒸馏至单一策略中。
◆结合强化学习和辅助行为克隆目标对蒸馏策略进行优化，在促进探索的同时保留了教师的优秀行为，进一步提升了鲁棒性。
实验证明，GuideWalk能够在保持人形机器人稳定运动的同时，实现有效且稳健的导航。</td></tr>
<tr><td>2026-06-10</td><td>MB-Loc: Multi-planar Bird&#x27;s-eye-view Localization in outdoor LiDAR scenes<br><a href='http://arxiv.org/pdf/2606.08744'>论文</a></td><td>本文提出了MB-Loc框架，解决了现有场景坐标回归方法计算效率低且对视角变化敏感的问题。
◆提出2.5D多平面鸟瞰图表示法，将点云沿Z轴切片并映射带符号深度至2D平面，在保留3D几何的同时利用2D卷积提升计算效率。
◆引入KL正则化潜在瓶颈模块，显式建模空间不确定性且不引入随机噪声，有效应对室外LiDAR的稀疏性。
◆在平面投影前应用3D空间增强策略，迫使网络隐式学习视角不变特征，显著提升旋转鲁棒性。
实验表明该方法在NCLT数据集上达到最优，且以实时推理速度实现了比传统3D架构更高的计算效率。</td></tr>
</tbody>
</table>
</div>

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-17</td><td>Admittance-Based Surface Alignment for Human-in-the-Loop Robotic Visual Inspection<br><a href='http://arxiv.org/pdf/2606.18601'>论文</a></td><td>◆提出一种面向人机协同机器人视觉检测的实时闭环姿态控制流程，解决感知噪声、表面不规则和人工遥操作共同作用下的表面对齐问题。
◆将操作员输入与视觉感知得到的表面法向对齐目标统一到导纳控制框架中，实现共享自治下的柔顺响应。
◆创新性地把末端执行器建模为在黏性介质中运动的虚拟球体，用可解释的质量-阻尼系统生成同步、平滑的姿态调整。
◆相比纯离线规划，该方法能够根据实时表面几何误差和人工指令动态修正运动，更适合工业在线检测场景。
◆在6自由度机械臂上验证了系统的稳定法向跟踪能力，最终平均姿态误差达到0.4°，体现出较高精度。</td></tr>
<tr><td>2026-06-16</td><td>Task Allocation and Motion Planning in Dynamic, Cluttered Environments via CBBA and Graphs of Convex Sets<br><a href='http://arxiv.org/pdf/2606.18516'>论文</a></td><td>◆论文提出一种面向动态、杂乱环境的多智能体任务分配与运动规划联合框架，将CBBA分布式任务分配与GCS轨迹优化相结合。

◆利用时间扩展的3D+time配置空间，GCS能够在存在静态和动态障碍的场景中生成安全且时间高效的最优轨迹。

◆方法将任务分配与轨迹规划紧密耦合，使CBBA在决策时不仅考虑任务归属，还考虑智能体到达动态任务的时间和位置可行性。

◆该框架支持动态任务如会合目标的分配，能够提供更准确的任务完成时间估计，从而提升分配质量。

◆通过在3D+time空间中协调路径，系统可降低多智能体间碰撞风险，并在仿真杂乱环境中验证了有效性。</td></tr>
<tr><td>2026-06-16</td><td>LAGO Policy: Latency-Aware Asynchronous Diffusion Policies with Goal-Directed Collision-Free Planning for Smooth Manipulation<br><a href='http://arxiv.org/pdf/2606.17982'>论文</a> | <a href='https://lago-policy.github.io/'>代码</a></td><td>LAGO Policy针对异步扩散视觉运动策略在真实机器人中易出现动作块间不连续、运动抖动和碰撞的问题，提出了一个兼顾平滑性、安全性与实时执行的统一框架。
◆ 通过延迟感知的classifier-free guidance，将未来动作作为条件引入扩散策略，显著提升异步推理下的动作块间一致性。
◆ 从示范数据中预测任务相关交互目标，使策略具备面向目标的避障与无碰撞轨迹规划能力。
◆ 引入时空轨迹优化，对即将执行的动作进行低加加速度、可行性和安全性约束下的细化。
◆ 将扩散策略生成、目标推断与轨迹优化整合到同一异步动作生成流程中，提升真实场景部署可靠性。
实验表明，LAGO Policy在多种复杂操作任务中实现了更平滑、更安全的执行，并保持较高任务成功率。</td></tr>
<tr><td>2026-06-16</td><td>FLAP: FOV-Constrained Active Perception Planning for Prior-Map-Free 3D Navigation<br><a href='http://arxiv.org/pdf/2606.17630'>论文</a></td><td>◆本文提出FLAP框架，将主动感知直接融入未知复杂3D环境中的无人机轨迹优化，以兼顾安全性与飞行效率。
◆其感知约束由无人机动力学推导，并在传感器坐标系中建模，从而更精确处理有限视场和探测距离。
◆论文设计了速度触发的感知约束激活机制，使规划器能根据运动状态动态权衡避障感知与轨迹效率。
◆方法引入带参数化起始时间优化的主动感知子轨迹段，降低因障碍物发现过晚导致的碰撞风险。
◆该框架支持任意3D机动中的主动感知，无需依赖昂贵的感知感知前端路径生成器，并在仿真和真实实验中验证了对不同环境与传感器配置的鲁棒性。</td></tr>
<tr><td>2026-06-15</td><td>Intermittent Strategic Cooperation of Two Selfish Agents on Graphs<br><a href='http://arxiv.org/pdf/2606.17216'>论文</a></td><td>◆论文提出IC2PP问题，将两个自利智能体在图上的路径规划建模为带有间歇性合作机会的最短路博弈。

◆其核心创新在于刻画了纯纳什均衡联合策略的结构，指出稳定合作只能以高度受限的形式出现。

◆论文证明任意IC2PP实例中至少存在一个纯纳什均衡，为该类合作博弈提供了存在性保证。

◆作者设计了多项式时间算法，用于枚举所有相关纯纳什均衡，提升了该问题的可计算性。

◆在存在多个均衡时，论文引入基于议价理论的均衡选择机制，并通过实验比较个体旅行时间与社会福利表现。</td></tr>
<tr><td>2026-06-12</td><td>ParkingTransformer: LLM-Enhanced End-to-End Trajectory Planning for Autonomous Parking<br><a href='http://arxiv.org/pdf/2606.17082'>论文</a></td><td>◆提出ParkingTransformer端到端自主泊车框架，将多视角感知与大语言模型的场景理解能力结合，提升长距离泊车任务的语义理解与可解释性。
◆方法直接利用历史信息和原始传感器数据，通过轨迹查询融合LLM隐式状态特征生成规划轨迹，避免依赖稠密BEV表示。
◆为弥补LLM空间推理不足，引入3D位置编码，显式注入几何空间信息，增强车辆对泊车场景结构的理解。
◆设计固定窗口流式历史信息处理机制，提高长时序建模效率和推理速度，更适合实际在线部署。
◆采用粗到细解码策略逐步优化轨迹精度，并在CARLA和真实车辆实验中取得较高驾驶得分与88.70%的平均成功率，验证了方法有效性。</td></tr>
<tr><td>2026-06-15</td><td>DIFF-IPPO: Diffusion-Based Informative Path Planning with Open-Vocabulary Belief Maps<br><a href='http://arxiv.org/pdf/2606.16780'>论文</a></td><td>本文提出了DIFF-IPPO框架，将开放词汇信念图生成器与基于扩散的规划器相结合用于信息性路径规划。
◆提出将基于扩散模型的规划器引入信息性路径规划，突破了现有方法难以直接基于非高斯多模态信念图生成全局轨迹的局限。
◆构建了结合开放词汇感知与扩散规划的流水线，使生成的轨迹能将传感器覆盖集中于高信念区域。
该方法在多场景中取得了81.49%至86.55%的归一化检测得分。
在模拟搜救任务中，五架无人机利用批处理条件轨迹生成，仅3.5分钟即可首次定位目标。</td></tr>
<tr><td>2026-06-15</td><td>WaveSync: Constrained Wavefront Optimization for Synchronized Co-Speech Gestures in Humanoid Robots<br><a href='http://arxiv.org/pdf/2606.16600'>论文</a> | <a href='https://github.com/pairs-lab/WaveSync}{WaveSync}'>代码</a></td><td>本文提出了WaveSync混合框架，解决了人形机器人生成共语手势时难以兼顾语音同步与硬件运动约束的耦合难题。
◆利用大语言模型将对话分解为结构化语义模式并分配逐词重要性权重，创新性地构建出连续的语义重要性波形。
◆采用动态运动基元塑造手势轨迹，在增强手势表现力的同时严格保证了运动的运动学可行性。
◆引入波前优化阶段，通过手势时长压缩与前向传播机制，实现手势与语音的峰值对齐并解决残余的运动学违规问题。
实验表明该方法实现了高同步精度，在客观与主观评估中均超越基线，且各组件对生成富有表现力且符合运动学规范的手势均不可或缺。</td></tr>
<tr><td>2026-06-15</td><td>Steering Emotional Dynamics for Art Therapy: Controllable Narrative Script Generation through Hierarchically Guided LLM Agents<br><a href='http://arxiv.org/pdf/2606.16481'>论文</a></td><td>本文提出了EC-Script框架，一种基于大语言模型智能体的分层控制框架，解决了现有文本生成方法无法遵循指定情感轨迹以满足艺术治疗需求的问题。
◆通过情感轨迹规划建立整体叙事方向，确保叙事的宏观情感走向受控。
◆采用角色驱动的场景生成推进场景级情节发展，使情节逻辑与角色状态契合。
◆利用情感控制的剧本编写调节角色局部情感变化，精细管理微观情感波动。
实验表明，该框架生成的逐场景剧本与预设轨迹高度一致，在情感轨迹遵循度上显著优于基线方法。
该研究实现了叙事生成中情感动态的有效导向，为AI辅助情感疗愈提供了可靠技术支持。</td></tr>
<tr><td>2026-06-15</td><td>HOLO-MPPI: Multi-Scenario Motion Planning via Hierarchical Policy Optimization<br><a href='http://arxiv.org/pdf/2606.16480'>论文</a></td><td>◆ 提出HOLO-MPPI框架，将离线高层策略学习与在线低层MPPI随机最优控制结合，用于无需逐场景调参的多场景运动规划。

◆ 离线阶段学习一个在抽象动作空间中生成鲁棒计划的高层策略，并配合学习到的世界模型支持在线预测与评估。

◆ 在线阶段让高层策略作为数据驱动的先验生成器，根据当前观测和目标动态参数化MPPI的采样分布，避免手工设计先验难以扩展的问题。

◆ 通过MPPI在高层先验附近实时优化低层控制序列，使系统既具备跨场景泛化能力，又能适应局部扰动和随机交互。

◆ 在自动驾驶任务中，论文设计了有效的高层动作空间和针对性的模型结构，并在多种驾驶场景中验证其优于传统MPPI和端到端RL基线，同时保持实时控制性能。</td></tr>
<tr><td>2026-06-15</td><td>Game-Theoretic Multi-Agent Reinforcement Learning for Swarm Trajectory Planning in Low-Altitude Wireless Networks<br><a href='http://arxiv.org/pdf/2606.16386'>论文</a></td><td>本文针对低空无线网络中多小区场景下无人机群轨迹规划存在资源块分配引发强战略耦合的问题进行研究。为了在通信吞吐量和任务完成效率之间取得平衡并解决多小区资源拥塞问题，作者提出了一种基于博弈论的多智能体强化学习框架。
◆将多小区拥塞感知的无人机轨迹规划问题构建为具有通信与任务感知效用函数的合作随机拥塞博弈。
◆提出一种集中训练分布式执行的多智能体近端策略优化算法，以在多小区资源拥塞下最大化社会效益。
仿真结果表明，该方法在总体效用和任务成功率上优于多种基线算法，且能在实际训练预算内实现稳定收敛。</td></tr>
<tr><td>2026-06-15</td><td>GraphWorld: Long-Horizon Planning with World Models for End-to-End Autonomous Driving<br><a href='http://arxiv.org/pdf/2606.16274'>论文</a></td><td>针对现有端到端自动驾驶方法局限于短期规划且缺乏长期时序依赖建模的问题，本文提出了GraphWorld框架，通过隐式世界模型显式增强长视距规划能力。
◆提出以自车为中心的交互图，基于空间距离自适应建模关键相邻智能体，并通过跨节点交叉注意力将关系上下文传播至规划查询。
◆提出世界状态条件规划，通过建模自车与周围智能体的交互来学习以自车为中心的隐式世界表征。
该表征捕捉了关键的交互动态与安全语义，并作为条件信号引导具有安全意识的长视距轨迹规划。
实验表明，GraphWorld显著降低了碰撞率并提升了长视距规划性能，验证了其在复杂驾驶环境中的有效性。</td></tr>
<tr><td>2026-06-15</td><td>PolyMerge: Compressing 3D Gaussian Splats with Polytope Coverings for Provably Safe Resource-Constrained Navigation<br><a href='http://arxiv.org/pdf/2606.16232'>论文</a> | <a href='https://athlon76.github.io/PolyMerge-website/'>代码</a></td><td>◆ PolyMerge将高保真的3D Gaussian Splatting场景压缩为轻量级凸多面体集合，显著降低导航所需的存储与计算开销。

◆ 其核心创新是用凸多面体并集对3DGS中的障碍物进行可证明的保守外包络，从而保证不会低估碰撞风险。

◆ 方法允许调节多面体数量，在表示保守性、路径可行性和实时计算成本之间灵活权衡。

◆ PolyMerge进一步与控制屏障函数（CBF）结合，使无人机能够基于压缩场景模型规划可证明安全的无碰撞轨迹。

◆ 论文通过仿真和Crazyflie无人机硬件实验验证了该方法在严苛机载算力限制下仍能实时运行，并在速度上优于基线方法。</td></tr>
<tr><td>2026-06-14</td><td>Identification of a Physics-Based Electrical Power Consumption Model for the Unitree G1 Humanoid Arm<br><a href='http://arxiv.org/pdf/2606.15915'>论文</a></td><td>本文针对Unitree G1仿人机器人的七自由度左臂，提出了一种基于物理的参数线性电功耗预测模型。
◆该模型结合了执行器损耗项与基线扭矩校正，有效捕捉了重力补偿负载变化，并能准确预测负净功率轨迹。
◆引入了成对交互项，成功建模了多关节同时运动时的功率耦合效应。
模型参数通过机器人机载功率测量数据进行辨识，在897条多速度轨迹测试中R平方达0.933，且在未见速度轨迹上R平方达0.965，展现了出色的泛化能力。
此外，对辨识参数的分析揭示了手臂各异的功耗特征，即粘性摩擦主导肩俯仰与腕关节，铜损主导肩偏航与肘部，库仑摩擦则主导肩横滚。</td></tr>
<tr><td>2026-06-14</td><td>Pixels to Proofs: Probabilistically-Safe Latent World Model Control via Parallel Conformal Robust MPC<br><a href='http://arxiv.org/pdf/2606.15594'>论文</a></td><td>◆ 提出SLS²框架，实现从像素输入到安全反馈运动规划的端到端控制，将学习型潜在世界模型与鲁棒MPC结合。
◆ 训练动作条件联合嵌入世界模型，获得紧凑且近似马尔可夫的潜在状态，使梯度轨迹优化更高效。
◆ 引入保形预测校准潜在动力学误差，为真实系统的不确定性构造概率有效的鲁棒误差界。
◆ 结合GPU加速的系统级综合鲁棒MPC，在潜在空间中施加鲁棒约束以提升闭环安全性。
◆ 进一步学习并保形化潜在约束检查器，使规划器能处理概率安全约束；实验显示其在视觉控制任务中同时提升到达目标能力和安全性。</td></tr>
<tr><td>2026-06-13</td><td>Task-Aware Environment Augmentation for Reliable Navigation via Shielded Conditional Diffusion<br><a href='http://arxiv.org/pdf/2606.15154'>论文</a> | <a href='https://scoda-diffusion.github.io/}'>代码</a></td><td>本文提出了任务感知环境增强这一全新问题，即在给定地图和规划轨迹下，通过在环境中布置有限数量的视觉标记来保障机器人在不确定性下的可靠执行，并提出了SCoDA方法予以解决。
◆翻转了传统研究视角，不再让机器人去适应缺乏观测的固定环境，而是通过优化标记布局让环境主动支持机器人的任务执行。
◆利用条件扩散模型学习高性能标记布局的条件分布，并以环境、轨迹、扰动上下文和期望执行特征为条件进行生成。
◆提出屏蔽采样器，通过推理执行过程中需要姿态纠正的关键位置，将扩散分布引导至任务相关且符合有限预算的增强方案。
仿真和硬件实验表明，该方法显著提升了轨迹执行的可靠性并缩短了完成时间。</td></tr>
<tr><td>2026-06-12</td><td>Short-Horizon Position Accuracy of Single-Track Models: Implications for Motion Planning of Autonomous Vehicles<br><a href='http://arxiv.org/pdf/2606.14216'>论文</a></td><td>自动驾驶运动规划依赖计算高效且准确的车辆模型，但目前缺乏针对模型短时域位置精度的系统性实车评估。本文通过实车专用实验识别参数，在多种驾驶工况下将三种单轨模型的短时域位置预测与实车测量数据进行了系统比较。
◆首次系统性地评估了单轨车辆模型在短时域内的位置精度，填补了模型预测与真实测量数据对比的空白。
◆揭示了模型复杂度、参数化质量与位置精度之间的权衡关系，打破了寻找单一最优模型的局限。
◆为模型预测控制等运动规划应用中的车辆模型选择，提供了基于实际精度权衡的指导性见解。</td></tr>
<tr><td>2026-06-12</td><td>Semidefinite Relaxations for Collision-Free Motion Planning<br><a href='http://arxiv.org/pdf/2606.14063'>论文</a></td><td>本文研究了无碰撞运动规划的半定松弛方法，将点机器人穿越球形障碍物的问题精确建模为多项式曲线上的非凸问题，并提出自然半定松弛。
◆首次从理论证明，求解该凸松弛等价于在更高维空间中全局求解相关的运动规划问题，给出了松弛紧致性的充要条件与直观解释。
◆提出对称性约简方法，使半定正定锥的规模仅与多项式阶数线性相关且独立于环境维度，显著缩小了问题规模。
实验表明，该方法比直接使用SNOPT和IPOPT求解非线性规划快十至百倍，方差更低，能可靠找到原问题的局部最优路径。
最后，该方法被成功用作RRT规划器中的凸转向函数，实现了具有C4连续轨迹的四旋翼最小抖动规划。</td></tr>
<tr><td>2026-06-11</td><td>Mana: Dexterous Manipulation of Articulated Tools<br><a href='http://arxiv.org/pdf/2606.13677'>论文</a></td><td>论文核心贡献总结:

该论文提出了Mana(Manipulation Animator),一个面向铰接式工具灵巧操作的通用sim-to-real框架,旨在解决灵巧机器人领域中协调内部自由度与接触丰富交互的难题。作者将灵巧操作重新诠释为动画生成问题,借鉴计算机动画的思想,采用由粗到细的流程,将程序化生成的抓取关键帧通过运动规划与强化学习转化为完整的操作轨迹。该方法在四种不同尺度和关节类型的铰接工具上均实现了抓取与手内操作的零样本sim-to-real迁移,为可扩展的铰接工具灵巧操作提供了新思路。

主要创新点:

◆ 首次将铰接式工具的灵巧操作问题重新表述为动画生成问题,借鉴计算机动画中的关键帧思想构建操作轨迹生成范式。

◆ 提出由粗到细的Mana流程,将程序化生成的抓取关键帧通过运动规划和强化学习相结合,转化为高质量的操作轨迹。

◆ 数据生成过程高度自动化,用户仅需几次鼠标点击即可指定功能性可供性,每个工具配置耗时不到一分钟,大幅降低人工成本。

◆ 在四种不同尺度与关节类型的铰接工具上验证了零样本sim-to-real迁移能力,包括抓取与手内操作两类任务。

◆ 填补了以往研究主要聚焦于刚性物体的空白,首次系统地解决铰接式工具功能性抓取与操作策略的学习难题,具有良好的可扩展性。</td></tr>
<tr><td>2026-06-12</td><td>Bounding Boxes as Goals: Language-Conditioned Grasping via Neuro-Symbolic Planning<br><a href='http://arxiv.org/pdf/2606.12910'>论文</a></td><td>论文核心贡献总结:

该论文提出了GRASP(Grounded Reasoning and Symbolic Planning)框架,旨在实现开放词汇的桌面机器人操作任务。该方法利用预训练的视觉-语言模型(VLM)将自然语言指令转换为神经符号目标状态,并通过边界框检测管道将其与物理世界相对应,从而使机器人能够实时响应自然语言提示。在90次真实机器人实验中,该框架在三个难度等级上实现了73.3%的总体成功率,且无需任何任务特定的训练或微调。

主要创新点如下:

◆ 提出神经符号规划框架,将VLM的语言理解能力与符号化目标表示相结合,把自然语言查询转化为可执行的符号目标状态。

◆ 采用边界框作为目标表示形式,通过检测管道将抽象语言概念与物理空间精准对接,避免了传统方法对固定颜色列表或硬编码坐标的依赖。

◆ 实现真正的零样本开放词汇操作能力,无需数千次演示数据训练,即可解释&quot;顶层货架&quot;等抽象空间概念。

◆ 相比于当前计算密集型的SOTA方法,该框架更加轻量化,降低了计算开销,更适合实时部署。

◆ 在真实机器人平台上完成了多难度等级的系统性验证,证明了方法在实际场景中的可行性与泛化性。</td></tr>
</tbody>
</table>
</div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
</tbody>
</table>
</div>

<h2 id='sensor-undistortion'>Sensor Undistortion</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-06-11</td><td>Observation of intertwined charge density wave order and superconductivity in Janus monolayer<br><a href='http://arxiv.org/pdf/2606.13828'>论文</a></td><td>◆本文首次基于第一性原理系统研究了Janus单层1T-ZrSeTe中电荷密度波与超导不稳定性的共存和相互关联。
◆发现其声子谱在M点存在显著软化，源于增强的电子-声子耦合以及带间、带内散射共同导致的电子不稳定性。
◆揭示2×2×1晶格畸变会重构能带并打开小的间接带隙，使体系由半金属性转变为半导体。
◆与ZrTe2单层相比，Se替代一层Te显著降低畸变能量收益，说明Janus结构削弱了CDW不稳定性。
◆论文进一步证明电子关联和双轴应变可有效调控CDW与超导不稳定性。
◆在高温未畸变相中，ZrSeTe表现出声子介导的双能隙超导，主要来自M点软模与Zr d、Te p轨道费米面能带的强耦合，而SOC会降低超导转变温度。</td></tr>
<tr><td>2026-06-11</td><td>Revisiting Vehicle Color Recognition in Long-Tailed Surveillance Scenarios<br><a href='http://arxiv.org/pdf/2606.13625'>论文</a> | <a href='https://github.com/viniciusorru/vcr-synthetic'>代码</a></td><td>该论文针对监控场景下车辆颜色识别中存在的严重类别不平衡问题,基于真实世界数据集 UFPR-VeSV 开展了系统性研究。作者结合生成式数据增强、现代视觉表征、损失重加权、学习率调度、颜色安全增强、前景感知预处理与集成融合等多种策略,显著提升了对稀有颜色类别的识别性能。最终方法在微观准确率上达到 94.6%,宏观准确率达 79.7%,相比最新文献宏观准确率提升 8.2 个百分点。此外,作者通过人工错误分析指出,部分剩余错误即使对人类标注者也存在视觉模糊性,从而揭示了基于颜色的车辆识别在非受限监控图像中的实际局限。

核心创新点如下:

◆ 首次系统性地将文本条件生成(RunDiffusion/JuggernautXL)与图像条件颜色编辑(Gemini 2.0 Flash)两种现成生成式策略应用于车辆颜色少数类的合成增强。

◆ 提出综合性训练流程,将合成数据与损失重加权、颜色安全数据增强、前景感知预处理及集成融合相结合,有效缓解长尾分布问题。

◆ 在 UFPR-VeSV 数据集上取得 SOTA 性能,宏观准确率较已有文献提升 8.2 个百分点,显著改善稀有颜色类别的识别效果。

◆ 通过人工错误分析揭示了颜色识别任务的固有视觉模糊性,为该领域的性能上限提供了实证依据。

◆ 开源了所生成的合成图像与完整源码,促进后续在长尾监控场景下的可复现研究。</td></tr>
<tr><td>2026-06-10</td><td>TESS detection of periodic brightness variations during the rise of classical nova PGIR22akgylf<br><a href='http://arxiv.org/pdf/2606.12532'>论文</a></td><td>这篇论文利用TESS空间望远镜对缓慢上升型经典新星PGIR22akgylf进行了高精度光度监测,覆盖了新星发现后3到16天的关键阶段,并辅以地面观测追踪了其长达约133天的完整上升过程。研究团队探测到周期为0.1802±0.0012天、峰峰振幅约0.02星等的周期性亮度变化,该信号在TESS观测的两周内保持稳定,暗示其源于双星轨道运动。作者据此推断伴星为矮星,并提出周期性信号是由于双星轨道运动使新星包层(此时尺度与双星轨道间距相当)发生形变所致,从而揭示了公共包层相互作用在该新星壳层抛射中的重要作用。

◆ 首次在经典新星上升阶段利用TESS高精度光度数据探测到稳定的周期性亮度调制信号,为研究新星包层结构提供了新观测窗口。

◆ 提出周期性光变源自双星轨道运动对膨胀新星包层的形变作用这一新颖物理解释,将光变特征与包层几何结构直接关联。

◆ 首次为经典新星缓慢上升阶段提供了公共包层相互作用参与壳层抛射的直接观测证据。

◆ 打破了缓慢上升现象仅存在于共生双星热核爆发中的传统认知,证明该现象同样可发生于含矮星伴星的紧致双星系统中。

◆ 通过周期稳定性和轨道动力学分析,首次利用上升阶段光变对新星伴星性质(矮星)做出限定,为新星双星系统参数测定提供了新方法。</td></tr>
<tr><td>2026-06-10</td><td>Spatially Coupled Phase-to-Depth Calibration for Fringe Projection Profilometry<br><a href='http://arxiv.org/pdf/2606.11601'>论文</a></td><td>针对条纹投影轮廓术中逐像素独立拟合导致的空间不一致和结构化伪影问题，本文提出了一种空间耦合的相位深度标定方法。
◆提出空间耦合的相位深度变换模型，所有像素共享由全局相位标量与仿射空间项构成的单个低维映射，替代独立的逐像素拟合，并可选附加有界平滑修正场。
◆引入原生网格配对方案，直接在参考相机网格上构建相位深度标定对，将立体三维平面沿原生光线采样回相机网格，从而避免对相位图进行纠正。
在具备高分辨率真值的牙科目标上，该方法取得了与主动立体参考相当的点对面均方根误差（约12微米）。
相比传统逐像素标定法，它不仅大幅提升了空间一致性，还将运行时映射简化为少量的逐像素元素级操作，参数存储几乎可忽略。</td></tr>
<tr><td>2026-06-09</td><td>A Multimodal RGB and Events Dataset for Hand Detection in First-Person View<br><a href='http://arxiv.org/pdf/2606.10790'>论文</a></td><td>该论文针对事件相机在手部检测中训练数据匮乏的瓶颈，提出了一种合成第一人称视角事件数据集的方法。
◆提出利用现有RGB Egohands数据集结合v2e工具箱，合成第一人称视角事件相机手部数据集的方法。
◆通过变化v2e工具箱参数，生成了涵盖不同光照条件和尺度的多版本数据集，增强了数据多样性。
◆设计了结合微调YOLOv8模型与时间插值的标注策略，实现了高时间分辨率事件数据的真值生成。
研究最终构建了多模态RGB与事件数据集，并利用现有多模态算法验证了其有效性，达到了与前沿方法媲美的检测性能。</td></tr>
<tr><td>2026-06-08</td><td>Dense Force Estimation with an Event-based Optical Tactile Sensor<br><a href='http://arxiv.org/pdf/2606.09451'>论文</a></td><td>本文提出了首个基于事件光学触觉传感器的密集三维力场重建框架，解决了现有事件传感器仅能预测整体净力的问题。
◆提出基于事件的标记跟踪算法以恢复触觉表面的剪切位移。
◆利用卷积神经网络预测法向位移，并收集了同步的力-位移-事件数据集用于训练。
◆创新性地通过逆有限元法将三维表面位移映射为物理受力。
实验表明该框架在最高20N受力范围内实现了低误差精准重建，平均运行频率达100Hz。
此工作为机器人抓取与灵巧操作的高频控制迈出了密集力反馈的第一步。</td></tr>
<tr><td>2026-06-08</td><td>Beyond Humans: Multispecies Animal Face Recognition Using Transfer Learning<br><a href='http://arxiv.org/pdf/2606.09353'>论文</a></td><td>该论文针对传统动物识别物理设备不实用且现有动物面部数据集规模小难以训练深度学习模型的问题，提出利用迁移学习实现多物种动物面部识别的方法。
◆创新性地探索了利用在大规模人类面部或通用物体数据集上预训练的模型作为骨干网络，解决动物面部数据不足的迁移学习方案。
◆首次系统比较了专门针对人类面部训练的FaceNet与在通用物体类别上预训练的Vision Transformer在跨物种动物面部识别上的性能差异。
研究在狗、灵长类和牛这三个图像质量与捕获条件差异极大的数据集上进行了验证。
结果表明，Vision Transformer在狗和牛的数据集上表现优异且超越了现有最优方法，而在图像质量较差的灵长类数据集上虽具鼓励性但表现波动。</td></tr>
<tr><td>2026-06-07</td><td>Magnetic Brunn-Minkowski inequalities<br><a href='http://arxiv.org/pdf/2606.08626'>论文</a></td><td>本文研究了黎曼流形上的闵可夫斯基平均，其中插值由给定磁势下作用量最小化的磁测地线实现。
◆建立了该操作的布鲁恩-闵可夫斯基不等式与磁里奇曲率下界之间的等价关系。
◆探讨了Kähler流形和Sasakian流形上的自然磁场等多种实例。
◆为海森堡群上的接触磁测地线证明了一个尖锐且无畸变的布鲁恩-闵可夫斯基不等式。
◆发现来自不同上同调类的闭磁势可能会产生不同的测地线闵可夫斯基平均。</td></tr>
<tr><td>2026-06-12</td><td>An ultra-wide-bandgap semiconductor photodetector for linear measurement of bright sub-bandgap light<br><a href='http://arxiv.org/pdf/2606.07807'>论文</a></td><td>本文提出了一种亚带隙氮化铝光电探测器，解决了传统探测器在中低强度光下易饱和的问题。
◆实现了对超过40瓦每平方厘米的超强蓝光的非饱和线性响应。
◆在高达300摄氏度的高温下依然保持无失真的线性响应。
◆揭示了金属-氮化铝肖特基结处深能级点缺陷介导光响应的物理机制。
◆通过掺杂和接触工程证明，窄空间电荷区是实现超强光探测与精确测量的关键。
该研究为超宽禁带半导体器件在航空航天及核电等极端条件下的可靠运行提供了工程策略。</td></tr>
<tr><td>2026-06-05</td><td>TraRA: Trajectory-level Recognition Aggregation for Video Text Spotting in Urban Surveillance<br><a href='http://arxiv.org/pdf/2606.07161'>论文</a> | <a href='https://github.com/trid2912/TraRA'>代码</a></td><td>这篇论文针对城市监控场景中视频文本识别(VTS)面临的运动模糊、遮挡、尺度变化等挑战,提出了TraRA(轨迹级识别聚合)方法。现有VTS方法通常在每一帧上独立进行文本识别,导致序列间结果不一致且不准确。TraRA作为一种即插即用的方法,通过利用时间和多模态一致性,在整个文本轨迹层面进行识别聚合,从而在复杂监控条件下实现鲁棒的文本识别。作者在RoadText、BOVText、ArTVideo和ICDAR15四个公共基准上进行了大量实验,证明TraRA在跟踪和识别性能上均优于现有最先进的VTS方法。

核心贡献与创新点如下:

◆ 提出了TraRA框架,首次将视频文本识别从帧级独立处理提升到轨迹级聚合识别,利用时序和多模态一致性显著提升监控视频中的文本识别鲁棒性。

◆ 设计了时序聚类模块(Temporal Clustering),通过将时间上和视觉上一致的文本实例进行分组,有效净化和细化噪声轨迹,缓解跟踪结果不稳定的问题。

◆ 提出了视觉-语言聚合模块(Vision-Language Aggregation),采用LoRA(低秩适应)增强的视觉-语言模型,跨帧融合视觉线索与语言上下文,实现多模态信息的有效整合。

◆ 该方法具备即插即用的特性,可灵活适配现有VTS方法,在四个公共数据集上的实验均验证了其在跟踪与识别任务上的一致性能提升。</td></tr>
<tr><td>2026-06-03</td><td>IMPose: Interactive Multi-person Pose Estimation with Dynamic Correction Propagation<br><a href='http://arxiv.org/pdf/2606.04480'>论文</a></td><td>IMPose是一款面向多人动态姿态标注的交互式工具,旨在解决现有标注工具在多人场景下缺乏时序传播能力、依赖大量人工干预的问题。该工具通过双层级跟踪机制,将标注员在单帧上的多人姿态修正自动传播至整段视频,显著降低了跨帧重复修正的成本。实验表明,IMPose在3DPW数据集上仅需每1050帧视频27次点击,在PoseTrack21上每条轨迹84帧仅需3次点击即可实现高精度标注。作者还借助该工具,以10名标注员10小时的极低成本将PoseTrack21扩展了18.8万个姿态实例(355万关键点)。

◆ 提出双层级跟踪机制:关键点层级通过序列建模实现修正的时序传播,实例层级利用关键点感知嵌入与相对位置编码保持多人跨帧一致性。

◆ 设计轨迹库(trajectory bank)存储历史姿态与实例线索,增强长程时序关联,在遮挡和运动模糊等困难场景下稳定标注效果。

◆ 将稀疏的人工修正转化为稠密、连贯的姿态轨迹,在不同交互预算下均取得优异的精度-效率权衡,尤其在低点击数场景下优势显著。

◆ 基于该工具发布了大规模扩展版PoseTrack21数据集,并开源标注工具、代码与数据,为社区提供了高效的多人动态姿态标注方案。</td></tr>
<tr><td>2026-05-31</td><td>DeblurNVS: Geometric Latent Diffusion for Novel View Synthesis from Sparse Motion-Blurred Images<br><a href='http://arxiv.org/pdf/2606.01315'>论文</a> | <a href='https://github.com/PKU-YuanGroup/DeblurNVS'>代码</a></td><td>本文提出DeblurNVS框架，实现了直接从稀疏运动模糊图像合成高保真新视图，且无需耗时的逐场景优化。
◆提出恢复中间几何表征的方法，从模糊输入中重建可靠的结构与对应线索，并结合目标相机信息重构清晰的新视图。
◆基于DL3DV-10K构建了运动模糊新视图合成数据集，利用插值有限曝光模糊合成技术实现了大规模训练。
实验证明该方法在合成和真实模糊场景基准上均优于现有基线。
它有效克服了传统方法依赖逐场景优化的局限，生成了感知更清晰且结构更稳定的视图。</td></tr>
<tr><td>2026-05-31</td><td>Event-Based Vision in Space: Applications, Trends, and Future Directions<br><a href='http://arxiv.org/pdf/2606.01280'>论文</a></td><td>传统帧式光学传感器在挑战性的轨道环境中常面临运动模糊、高功耗和极端数据冗余等问题。事件相机作为一种受生物启发的异步传感器，仅捕获局部光照变化，从而提供微秒级时间分辨率、极高动态范围和卓越的能效。针对当前空间应用科学文献零散的现状，本文全面综述了空间领域事件视觉的最新进展。
◆构建了涵盖大气与高速观测、环境监测与变化检测、运行支持与星载处理、地理空间建模与预测分析四个主要领域的分类法。
◆强调神经形态工程不仅是补充性成像技术，更是解决现代遥感和可持续太空探索关键瓶颈的范式转变。</td></tr>
<tr><td>2026-05-31</td><td>DeepIPCv3: Event-Aware Multi-Modal Sensor Fusion for Sudden Pedestrian Crossing Avoidance<br><a href='http://arxiv.org/pdf/2606.01277'>论文</a> | <a href='https://github.com/oskarnatan/DeepIPCv3'>代码</a></td><td>针对传统基于帧传感器在突发行人横穿场景下存在感知延迟和运动模糊的安全隐患，本文提出了DeepIPCv3多模态自动驾驶导航框架。
◆引入了受Transformer启发的跨模态注意力机制，动态融合激光雷达的稠密3D空间几何与动态视觉传感器的微秒级异步事件流，在不损失结构感知的前提下优先处理高速动态更新。
◆设计了混合策略网络，将启发式轨迹跟踪与直接神经预测相结合，把融合特征映射为安全的局部路径点和可执行控制指令。
本文在自建的涵盖白天与夜间条件的多模态数据集上进行了离线严格验证。
实验表明该框架实现了最先进的预测性能，有效消除了曝光失效和运动模糊。
其在轨迹与控制指令误差上达到最低，使车辆能在任意环境光照下完成高响应且数学有界的规避机动，并即将开源代码。</td></tr>
<tr><td>2026-05-31</td><td>Rank-Aware Quantile Activation for Motion-Robust Crop Segmentation in UAV Imagery<br><a href='http://arxiv.org/pdf/2606.01118'>论文</a></td><td>针对高速无人机运动模糊破坏高频幅度特征从而导致稀有农作物信号被抹除的问题，本文提出了双分位数激活机制。
◆提出秩感知模块QAct，利用实例级秩归一化替代传统CNN中易受模糊影响的幅度门控。
◆揭示并验证了秩感知激活与模糊域训练是两种互补的鲁棒性来源，而非相互替代。
实验表明QAct是提升性能的主导架构因素，在中等模糊下零样本QAct甚至超越了经蒸馏训练的ReLU。
结合两者的Distill-QAct在所有模糊严重度下均取得最佳性能，在稀有结构和纹理类别上实现了持续的mIoU提升。</td></tr>
<tr><td>2026-05-29</td><td>Towards Neuromorphic Event-Based Sensing for High-Speed Multi-Spectral Classification and Tracking of Microparticles<br><a href='http://arxiv.org/pdf/2605.31038'>论文</a></td><td>本文针对传统微流控成像系统在速度与带宽间的权衡，以及现有事件相机仅能追踪单一球形粒子的局限，提出了一种新型神经形态微流控传感平台。
◆创新性地集成空间复用RGB滤光片与异步事件传感器，在传感阶段直接编码多分散微粒的光谱特征与运动，免除了图像重建或学习推理的需求。
◆实现了亚毫秒级时间分辨率，在广泛尺寸与流速（含非层流）下保持鲁棒，对0.08至0.18毫米彩色粒子的分类准确率达82%。
◆事件驱动架构将数据带宽降低超240倍，同时维持460平方毫米每秒的面积吞吐量。
该框架为临床诊断与环境监测中的高速无标记异构分析物筛选提供了高效低延迟的可扩展方案。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>4810</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4217</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2410</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1611</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1604</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1425</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1260</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1246</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>942</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>939</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>917</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>795</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>780</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>742</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>723</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>706</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>638</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>635</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>622</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>591</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>564</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>553</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>536</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>500</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>484</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>437</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>409</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>342</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>340</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>263</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>252</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>241</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>235</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>222</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>199</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>198</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>161</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2845</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1641</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1351</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1095</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1037</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>871</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>697</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>656</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>649</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>620</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>583</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>573</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>567</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>561</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>551</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>514</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>483</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>461</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>445</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>442</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>335</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>312</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>298</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>281</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>278</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>258</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>221</td><td>Efficient local and global exploration on submap c</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>152</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>137</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>136</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>131</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
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
> 更新于: 2026.06.18
