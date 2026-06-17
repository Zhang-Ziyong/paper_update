# 历史论文归档 (2026.06.17)

> 所有历史论文完整归档，按分类展示

<details>
<summary>分类目录</summary>
<ol>
<li><a href='#slam'>SLAM (53篇)</a></li>
<li><a href='#sfm'>SFM (40篇)</a></li>
<li><a href='#image-matching'>Image Matching (11篇)</a></li>
<li><a href='#obstacle-avoidance'>Obstacle Avoidance (79篇)</a></li>
<li><a href='#navigation'>Navigation (75篇)</a></li>
<li><a href='#motion-planning'>Motion Planning (110篇)</a></li>
<li><a href='#sensor-calibration'>Sensor Calibration (22篇)</a></li>
<li><a href='#sensor-undistortion'>Sensor Undistortion (42篇)</a></li>
</ol>
</details>

<h2 id='slam'>SLAM (53篇)</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-06-10</td><td>Triangle Splatting SLAM<br><a href='http://arxiv.org/pdf/2605.31419'>论文</a></td><td>本文提出了一种使用可微三角形作为三维地图表示的稠密RGB-D SLAM系统。与3D高斯溅射不同，三角形天然兼容传统渲染硬件及需要显式几何的下游任务。
◆首次提出基于三角形溅射的稠密SLAM系统，通过对无结构三角形汤进行在线可微渲染来联合执行追踪与建图。
◆利用受限德劳内三角剖分将地图在线转换为连通网格，赋予了系统在线网格变形和碰撞检查的新能力。
在Replica和TUM-RGBD数据集上，该系统在三维几何重建上优于基线，追踪精度与之持平，并实现了在线场景编辑。</td></tr>
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
<tr><td>2026-06-02</td><td>PixVOD: Pixel-Distributed Direct Visual Odometry and Depth Estimation<br><a href='http://arxiv.org/pdf/2606.03989'>论文</a></td><td>PixVOD 提出了一种面向焦平面传感器-处理器(focal-plane sensor-processors)的全并行视觉里程计与深度估计方法,将传统集中式的视觉计算下沉到每个像素内部完成,从而减少传感器原始数据的冗余传输,并为上层视觉任务提供更高层次的语义信号。该方法基于高斯置信传播(GBP)使各像素处理单元通过局部消息交换达成对相机运动的共识,并结合逐像素光度观测与表面法向先验推断深度。为保证优化过程中的几何稳定性,作者引入了一种类关键帧的锚定机制以调节有效基线长度,使运动与深度更新保持一致性。在真实数据集上的实验验证了该像素级分布式里程计与深度估计方案在传感器端的可行性。

◆ 首次提出在焦平面传感器-处理器上完全像素级并行执行直接视觉里程计与深度估计的框架。
◆ 利用高斯置信传播(GBP)实现像素间的局部消息传递,从分布式光度观测中协同求解相机运动并达成共识。
◆ 将每像素光度观测与表面法向先验结合,实现稠密的逐像素深度推断。
◆ 设计了类关键帧的锚定机制,有效调节帧间基线,提升分布式优化中的几何稳定性与收敛一致性。
◆ 在真实数据集上验证了片上像素分布式里程计与深度估计的可行性,为新型智能视觉传感器提供了算法范式。</td></tr>
<tr><td>2026-06-02</td><td>Autonomous Navigation System for Library Service Robot Based on Unitree Go2 Edu<br><a href='http://arxiv.org/pdf/2606.03340'>论文</a></td><td>本文基于Unitree Go2 Edu四足机器人，提出了一套适用于图书馆场景的ROS 2自主导航系统。系统集成了4D激光雷达、深度相机和IMU，利用RTAB-Map实现视觉与激光融合SLAM，结合AMCL和EKF定位，并通过Nav2栈实现路径规划与局部避障。
◆针对图书馆真实部署中的地面过渡、临时杂物和部分受阻通道等移动不连续性问题进行优化，克服了低底盘轮式平台的局限。
◆将四足机器人引入图书馆狭窄通道与动态人群环境，并通过多传感器融合方案提升了复杂场景下的导航鲁棒性。
◆在真实图书馆中验证了系统的卓越性能，静态、低动态和高动态场景下导航成功率分别达100%、96%和88%，建图平均度量误差仅3.7厘米。</td></tr>
<tr><td>2026-06-01</td><td>Embedding Semantic Risk into Distance Fields and CBFs for Online Monocular Safe Control<br><a href='http://arxiv.org/pdf/2606.01605'>论文</a></td><td>本文提出一种在线单目感知至控制框架，将语义风险嵌入基于控制障碍函数的安全导航距离场中，克服了现有方法未在空间表征中编码风险的局限。
◆提出将语义信息直接嵌入欧几里得符号距离场，在控制优化前编码风险，使高风险物体在安全场中扩展更大的空间影响，且不损失运行时查询效率。
◆结合基础模型SLAM前端与逐帧语义分割，从单目RGB视频在线重建并融合密集的三维几何语义表征。
◆在距离场计算前对安全相关区域施加类别相关的膨胀，并通过类别相关增益进一步调节CBF控制器的响应。
仿真与硬件实验验证了该框架能在10至20赫兹下在线运行，并在遥操作与自主导航中实现语义感知的安全行为。</td></tr>
<tr><td>2026-05-31</td><td>One Channel to Rule Them All: Rethinking Input Representation for Visual Place Recognition<br><a href='http://arxiv.org/pdf/2606.00936'>论文</a></td><td>本文挑战了视觉地点识别中必须依赖RGB输入的固有假设，系统性地探究了色彩信息在真实世界外观变化下的实际作用。
◆发现灰度图像在一般条件下性能与RGB持平，在严重外观变化下因避免了色彩干扰而优于RGB，颜色仅在具备持久区分度线索时才有增益。
◆验证了全灰度训练的模型能取得更高的Recall@1，且参数量减少60%的轻量级灰度变体即可超越较重的RGB模型。
◆证明了灰度输入在节省存储空间、降低带宽消耗以及适配资源受限系统方面具有显著的实际优势。
研究最终得出结论，对于面临光照和季节等剧烈变化的VPR任务，色彩贡献极小，单通道灰度足以实现可靠的地点识别。</td></tr>
<tr><td>2026-05-30</td><td>SuperMemory-VQA: An Egocentric Visual Question-Answering Benchmark for Long-Horizon Memory<br><a href='http://arxiv.org/pdf/2606.00825'>论文</a></td><td>本文提出了SuperMemory-VQA，一个针对长期自我中心记忆任务的视觉问答数据集，旨在弥补现有数据集仅关注短视频理解而忽视真实人类记忆需求的不足。
◆构建了包含52.9小时多模态数据及4853对人工验证问答的大规模基准，全面涵盖物体位置、意图回忆及时间线重建等六类真实记忆需求。
◆创新性地引入带有明确无法回答选项的多项选择题格式，以严格测试模型在证据不足时的抗幻觉鲁棒性。
◆通过对前沿大模型和智能体框架的基准测试，揭示了现有系统在真实记忆任务上的不可靠性，指明需开发仅在证据充分时才作答的接地架构。
参与者调查进一步验证了该基准问题设计的现实性与实用性。</td></tr>
<tr><td>2026-05-30</td><td>Dynamic Resilient Spatio-Semantic Memory with Hybrid Localization for Mobile Manipulation<br><a href='http://arxiv.org/pdf/2606.00576'>论文</a></td><td>本文提出了DREAM框架，一种无需预建图的在线移动操作框架，解决了动态室内环境中场景信息易过期或不对齐的问题。
◆构建基于多传感器融合SLAM的在线时空语义体素记忆，实现几何一致与语义可查的场景表征。
◆提出位姿图感知的冗余感知记忆修剪方法，在位姿修正后动态更新历史观测，并保持长时序记忆的计算有界。
◆设计结合语言条件3D检索、开放词汇检测及多模态大模型语义验证的混合目标定位与重获机制。
实验表明，该框架将长时序任务成功率提升至55%-70%，并维持了极低的内存占用与更新延迟。</td></tr>
<tr><td>2026-05-29</td><td>ScaRF-SLAM: Scale-Consistent Reconstruction with Feed-Forward Models and Classical Visual SLAM<br><a href='http://arxiv.org/pdf/2606.00307'>论文</a></td><td>本文提出ScaRF-SLAM,一种将经典基于特征的视觉SLAM与几何基础模型(GFM)解耦融合的框架,旨在解决直接使用GFM预测进行位姿跟踪时因模型不确定性导致的精度问题。该方法利用经典SLAM实现鲁棒低延迟的位姿跟踪,而将GFM专门用于稠密建图,从而避免GFM预测误差传播到位姿估计中,同时对重建施加几何约束。系统通过多关键帧构建子图,采用轻量级的帧与子图尺度优化保证尺度一致性,并支持在线更新以反映SLAM轨迹的修正。实验表明,该方法在建筑尺度数据集上每10米误差约2厘米,在大规模户外场景中每30米误差约10厘米,重建精度较现有方法提升10%-20%。

核心创新点如下:

◆ 提出跟踪与建图解耦的架构,经典特征SLAM负责位姿估计,GFM专注稠密重建,避免GFM预测误差对位姿的负面影响。

◆ 设计基于帧和子图的轻量级尺度优化机制,解决GFM预测中跨帧深度尺度不一致的问题,保证全局几何一致性。

◆ 采用基于投影的子图内点云融合,并支持在线更新子图以同步SLAM轨迹的回环修正,实现可扩展的稠密重建。

◆ 构建了一个富含回环、建筑级室内数据集,提供精确传感器轨迹与LiDAR真值,为稠密SLAM评测提供新基准。

◆ 在建筑级与大规模室外场景中均验证了优越的轨迹精度和重建精度,展现出良好的可扩展性与实用性。</td></tr>
<tr><td>2026-05-29</td><td>Geodesic Flow Matching for Denoising High-Dimensional Structured Representations<br><a href='http://arxiv.org/pdf/2606.00248'>论文</a> | <a href='https://github.com/kremHabashy/CleanupSSP'>代码</a></td><td>本文针对空间语义指针在连续环面流形上的去噪问题，指出标准流匹配方法基于欧几里得几何假设会导致线性插值破坏流形结构，进而损害解码所需的相位和幅度信息。
◆提出测地线流匹配方法，将黎曼传输动力学引入去噪过程，严格将去噪流约束在SSP环面流形上。
◆设计了流形感知的信号清理机制，有效避免了传统欧式插值对高维分布式表征内部结构的破坏。
该方法在脉冲神经SLAM系统中得到验证，证明其能够通过流形清理稳定路径积分以抵抗漂移。
实验表明，与竞争基线相比，该方法使跟踪误差降低了百分之七十二，同时神经效率提升了百分之四十。</td></tr>
<tr><td>2026-05-28</td><td>Exploiting Chordal Sparsity for Globally Optimal Estimation with Factor Graphs<br><a href='http://arxiv.org/pdf/2605.30617'>论文</a> | <a href='https://github.com/borglab/gtsam'>代码</a></td><td>该论文针对机器人状态估计中因子图局部求解器易陷入局部最优，而现有凸松弛技术构建复杂且计算成本高的问题提出了新方法。
◆在GTSAM框架内创建了一种新流程，能够针对包含常见因子和变量类型的任意因子图，自动构建凸半定规划松弛问题。
◆利用GTSAM原生的贝叶斯树构造来分解半定规划问题，通过挖掘弦稀疏性显著提升了求解器的计算速度。
论文通过三维位姿图SLAM和二维定位两个案例研究，验证了该全局估计器相较于标准局部求解器在扩展性上的优势。
相关软件框架已在GitHub开源。</td></tr>
<tr><td>2026-05-28</td><td>CoMo3R-SLAM: Collaborative Monocular Dense SLAM with Learned 3D Reconstruction Priors for Outdoor Multi-Agent Systems<br><a href='http://arxiv.org/pdf/2605.30488'>论文</a></td><td>论文提出CoMo3R-SLAM，这是首个针对室外多智能体系统的协作单目密集RGB SLAM系统，解决了传统方法依赖深度传感器以及室外单目SLAM面临尺度歧义与数据关联不可靠的难题。
◆引入学习到的前馈三维重建先验，设计了先验引导的前端，实现单目相机的实时跟踪与局部密集融合。
◆提出基于协调器的密集点图匹配机制，实现了跨智能体的鲁棒验证与闭式Sim(3)规范同步。
◆采用GPU加速的全局光束法平差并结合段级深度优化，从而生成全局一致的度量地图。
该系统无需深度传感器与参数化内参，仅依赖单目RGB即可输出鲁棒约束，在多数据集上精度超越或媲美最先进的RGB-D方法，且能以8FPS实现在线运行。</td></tr>
<tr><td>2026-05-27</td><td>PRISM-SLAM: Probabilistic Ray-Grounded Inference for Scale-aware Metric SLAM<br><a href='http://arxiv.org/pdf/2605.19257'>论文</a> | <a href='https://prismslam-cmd.github.io/prismslam_pr/'>代码</a></td><td>针对单目SLAM的尺度模糊与动态环境跟踪失败问题，本文提出PRISM-SLAM框架，通过将视觉基础模型先验严谨集成到贝叶斯因子图中，实现了尺度感知且度量一致的实时定位与建图。
◆引入普吕克光线距离因子，在全局度量坐标系中锚定单目观测，使度量尺度具备Fisher可辨识性，从数学上根本解决了尺度漂移问题。
◆提出动态场景不确定性门控机制，利用时间深度一致性推导认知不确定性代理，通过概率软门控降低动态干扰物权重，避免了传统语义分割的高昂计算开销。
系统采用多进程架构异步处理基础模型推理与几何跟踪，仅依赖RGB输入即可实现30帧每秒的实时度量输出。
实验表明其度量绝对轨迹误差几乎等同于无尺度对齐误差，无需任何事后尺度校正即可生成可直接部署的度量轨迹。</td></tr>
<tr><td>2026-05-27</td><td>Provably Guaranteed Polytopic Uncertainty Quantification for SLAM<br><a href='http://arxiv.org/pdf/2605.28172'>论文</a> | <a href='https://github.com/LIAS-CUHKSZ/Polytopic-SLAM-Uncertainty-Quantification'>代码</a></td><td>本文提出了针对3D-3D基于地标的SLAM的可证明保证的不确定性量化算法，解决了现有方法缺乏形式化保证或仅关注位姿估计的局限。该算法包含前向UQ、后向UQ和位姿复合三个模块，能生成经过认证的不确定性集合。
◆提供确定性保证机制，当输入边界确定时，输出集合可证明包含真实的位姿和地标。
◆采用多面体表示不确定性集合，实现了计算可处理性以及对位姿不确定性的统一处理。
◆结合保形预测技术从数据中校准测量不确定性，在保持规定概率的同时显著提升了算法的实用性。</td></tr>
<tr><td>2026-05-27</td><td>SAFEVPR: Patch-Based Conformal Verification for Safe Cross-Condition Sequence Visual Place Recognition<br><a href='http://arxiv.org/pdf/2605.28048'>论文</a> | <a href='https://github.com/Hasar12139/SafeVPR'>代码</a></td><td>本文提出了SAFEVPR，一种用于跨条件序列视觉位置识别的非训练式验证与校准流水线，解决了传统保形预测在跨条件部署下因可交换性被破坏而失效的问题。
◆采用基于冻结DINOv2 ViT特征的互近邻图像块匹配分数，替代标准骨干网络的余弦相似度。
◆采用Mondrian保形Learn-Then-Test校准替代平坦校准，在不同分数区间拟合独立的Bonferroni校正阈值。
该方法在23个跨条件实验设置中均实现经验有效，目标错误发现率为0.10时平均FDR仅0.014且真阳性率达0.75。
研究表明仅靠高区分度不足以保证保形有效性，且本方法能在无纹理重复场景中安全放弃不可靠匹配。</td></tr>
<tr><td>2026-05-27</td><td>Con-DSO: Learning Short-Horizon Consistency Priors for RGB-D Direct Sparse Odometry<br><a href='http://arxiv.org/pdf/2605.27952'>论文</a></td><td>针对RGB-D直接法视觉里程计在动态物体、遮挡和光照变化等复杂环境下因一致性假设失效导致性能下降的问题，本文提出了Con-DSO框架。
◆提出一致性感知的里程计框架，通过时间相邻的RGB-D帧对预测稠密的光度与深度几何一致性不确定性，将一致性破坏表征为像素级不确定性。
◆利用光流引导的光度误差和投影深度一致性误差训练网络，并将成对不确定性预测转换为基于关键帧追踪的宿主端质量先验。
◆在位姿估计阶段通过质量感知的支撑像素选择和解耦的光度几何加权来应用该先验，实现对不可靠观测的连续衰减而非硬性拒绝或阈值门控。
实验表明该方法在五个公开基准上显著超越基线，在多个数据集上绝对轨迹误差降低了20%至80%。</td></tr>
<tr><td>2026-05-26</td><td>Gaussian Process-Based Extended Object Estimation for 6G ISAC at Millimeter-Wave Frequencies<br><a href='http://arxiv.org/pdf/2605.26915'>论文</a></td><td>本文提出了一种基于高斯过程的扩展目标估计方法，用于6G毫米波通感一体化场景。
◆突破了传统点散射体假设的限制，利用高斯过程实现了对扩展目标的更优估计。
◆结合符合5G新空口标准的双基地感知实际测量平台，验证了该方法在毫米波频段的实用性。
◆证明了通信网络能力增强与双基地感知及高斯过程估计相结合，可有效提升未来无线系统的环境感知能力。
研究结果表明，高斯过程在毫米波建图和同步定位与建图场景中均能有效完成扩展目标估计。</td></tr>
<tr><td>2026-05-26</td><td>Trinity: Unifying Class-Agnostic Terrain and Semantic Segmentation for Unstructured Outdoor Environments by Leveraging Synthetic Data<br><a href='http://arxiv.org/pdf/2605.27644'>论文</a></td><td>该论文的核心贡献在于提出了Trinity，一种基于Transformer架构的统一网络，能够同时进行类别特定的语义分割和类无关的地形分割。地形分割仅依赖视觉外观，无需预定义语义标签或机器人特定的可通过性分数，从而学习到机器人无关的视觉地形先验，便于迁移至不同的下游任务。为支撑大规模训练，论文扩展了OAISYS模拟器并引入合成数据集RUGDSynth，同时构建了真实场景数据集EXTerra，包含类特定和类无关两种标注。实验验证了联合分割方法在复杂户外环境中的可行性。

◆ 首次提出在单一网络内联合执行类特定语义分割与类无关地形分割，打破传统方法对机器人依赖或预定义类别的限制。  
◆ 学习机器人无关的视觉地形先验，可灵活结合机器人自身经验用于可通过性估计、视觉里程计等任务，提升跨平台迁移能力。  
◆ 构建了大规模合成数据集RUGDSynth和真实数据集EXTerra，填补了类无关地形标注数据的空白，并开源代码与数据集以促进研究。</td></tr>
<tr><td>2026-05-25</td><td>G-DRAGON: Geospatial Reasoning and Dynamic Planning for Retrieval-Augmented Outdoor Navigation<br><a href='http://arxiv.org/pdf/2605.25646'>论文</a></td><td>本文提出了G-DRAGON框架，这是一种用于户外开放世界导航的检索增强系统，有效解决了长距离全局规划与精细最后一公里探索的双重挑战。
◆提出了基于轻量级大语言模型的生成式检索方法，将自然语言指令映射到本地OSM实体，避免了云端大模型的事实幻觉并生成准确的全局坐标。
◆设计了高级规划模块，成功将全局拓扑路线与SLAM系统桥接，把地理空间路径点投影到机器人的可导航坐标系中。
◆针对最后一公里探索，结合前沿探索与开放集语义体素建图技术，实现了对开放词汇目标的精准定位。
实验证明该框架在仿真中超越了现有基线，并在真实世界无人地面车辆上成功完成了长达500米的行人搜索任务。</td></tr>
<tr><td>2026-05-24</td><td>FusionCore: A 23-State Unscented Kalman Filter for IMU, Wheel Encoder, GPS, and Visual SLAM Fusion in ROS 2<br><a href='http://arxiv.org/pdf/2605.25239'>论文</a> | <a href='https://github.com/manankharwar/fusioncore'>代码</a></td><td>本文提出了FusionCore，这是一个开源的ROS 2传感器融合包，利用23状态无迹卡尔曼滤波器将IMU、轮式编码器、GPS和视觉SLAM位姿融合为100Hz的单一里程计流。</td></tr>
<tr><td>2026-05-24</td><td>A Decentralized LiDAR-SLAM System with Certifiably Optimal Pose Graph Optimization<br><a href='http://arxiv.org/pdf/2605.25051'>论文</a></td><td>本文提出首个集成可证明最优位姿图优化后端的去中心化多机器人LiDAR-SLAM系统，旨在解决现有方法在大规模或退化环境中全局一致性差的难题。
◆首次将可证明最优的PGO后端集成于去中心化LiDAR-SLAM中，克服了传统局部搜索易陷入次优解和长期不一致的缺陷。
◆创新性地采用黎曼块坐标下降算法，确保了全局一致的轨迹估计。
◆系统无需依赖精确的初始猜测即可实现优化，显著增强了在复杂场景下的鲁棒性。
实验表明，该系统轨迹均方根误差相比现有最先进的DiSCo-SLAM大幅降低了48.9%。</td></tr>
<tr><td>2026-05-23</td><td>LC-Flow: Learning Local Continuous Optical Flow and Confidence from events<br><a href='http://arxiv.org/pdf/2605.24604'>论文</a></td><td>LC-Flow是首个纯粹基于局部事件的时间连续学习型光流估计器，解决了现有方法无法充分利用事件时间连续性的问题。它在局部方法中表现最优，其聚合方法更在MVSEC数据集上超越了繁重的帧法网络，确立了新的整体最优性能。
◆提出连续局部循环网络，维持空间网格的持久隐藏状态以逐步积累时间上下文，可在任意时间戳输出稀疏局部光流，克服了固定累积窗口与无状态从头计算的缺陷。
◆联合学习置信度分数，量化局部预测的可靠性，显式处理了事件稀疏性与孔径问题带来的内在模糊性。
◆赋予置信度双重作用，既过滤不可靠估计以服务下游视觉里程计等任务，又为多尺度聚合提供权重，将稀疏局部光流重建为全局一致光流。</td></tr>
<tr><td>2026-05-21</td><td>Extending Deep Event Visual Odometry with Sparse Point-Cloud Export<br><a href='http://arxiv.org/pdf/2605.22890'>论文</a></td><td>本文在深度事件视觉里程计DEVO的基础上，提出了一种稀疏点云导出管线。该系统在不改变原有视觉里程计性能的前提下，成功实现了稀疏几何场景的输出。
◆提出一种无侵入式的稀疏点云导出管线，通过提取DEVO内部已估算的3D结构并将其转换为显式点云，实现了点云的可视化与后续处理，且无需修改核心里程计公式。
◆构建了一套完整的数据导出实用工作流，涵盖数据导出、格式转换及点云清理功能，增强了系统的工程可用性。
实验表明，导出的稀疏点云与EMVS重建结果局部一致且在5厘米阈值下具有高精度，但也揭示了其在点云密度、完整性及抗累积噪声方面的局限。</td></tr>
<tr><td>2026-05-21</td><td>FRED: A Multi-Modal Autonomous Driving Dataset for Flooded Road Environments<br><a href='http://arxiv.org/pdf/2605.22018'>论文</a></td><td>本文提出了FRED数据集，据我们所知，这是首个专门针对道路积水灾害场景收集数据的多模态自动驾驶数据集。
◆首次提供涵盖洪涝期间及事后五个地点的多模态数据，包含高分辨率相机图像、64线激光雷达点云及RTK GNSS校正的IMU数据。
◆数据集同时采用KITTI风格与RTMaps两种格式发布，兼顾了现有工具的易集成性与车辆数据的直接回放需求。
◆提供语义标注以支持水害检测的训练与评估，兼容单传感器及传感器融合方法。
◆额外提供位置、速度及干燥条件数据，不仅助力结合地图的基于位置检测方法开发，还能评估定位与SLAM等任务。</td></tr>
<tr><td>2026-05-21</td><td>FUSE: A Framework for Unified State Estimation in Vehicular and Robotic SLAM Systems<br><a href='http://arxiv.org/pdf/2605.18047'>论文</a></td><td>本文提出了一种名为FUSE的统一状态估计框架，旨在解决传统紧耦合SLAM中各模块高度绑定导致难以独立修改设计的问题。
◆提出FUSE框架，通过观测摄取、传播、更新和状态查询接口，将时间处理、局部几何关联、估计器公式与地图更新策略彻底解耦。
◆开发LiDAR-IMU实例，在统一接口边界下实现了高频惯性传播、LiDAR几何更新、残差筛选与退化感知校正的协同运作。
◆在混合频率感知和方向退化场景中，有效正则化弱可观方向的更新，增强了系统的鲁棒性。
实验表明，在418米闭环走廊序列中，该实例相比最优基线Faster-LIO实现了7.9%的相对误差降低。
这证明了FUSE为组织状态估计设计提供了有效框架，并能提升实际SLAM系统的估计精度。</td></tr>
<tr><td>2026-05-20</td><td>SubTGraph: Large-Scale Subterranean Environment Synthesis with Controllable Topological Variability for Robotic Autonomy Validation<br><a href='http://arxiv.org/pdf/2605.20917'>论文</a> | <a href='https://github.com/LTU-RAI/SubTGraph.git'>代码</a></td><td>本文针对地下环境机器人研究缺乏大规模仿真基准的问题，提出了SubTGraph框架。
◆该框架能够根据用户对拓扑、维度和纹理等参数的设定，快速合成具有高变异性的多层地下环境。
◆该方法创新地从结构约束构建成本矩阵，引导Dijkstra算法结合DARPA拓扑贴片进行程序化生成。
研究通过语义分割、多智能体路径规划和LIO SLAM三个案例，验证了该框架对机器人自主系统各层严格评估的有效性。
最后，作者开源了世界创建代码库及包含150个高变异地下环境的数据库。</td></tr>
<tr><td>2026-05-19</td><td>Depth2Pose: A Pose-Based Benchmark for Monocular Depth Estimation without Ground-Truth Depth<br><a href='http://arxiv.org/pdf/2605.19797'>论文</a> | <a href='https://kocurvik.github.io/depth2pose'>代码</a></td><td>本文针对单目深度估计传统评估指标无法反映下游几何任务实用性的问题，提出了Depth2Pose评估框架。
◆提出以相对相机位姿估计精度作为任务驱动的代理指标，结合深度预测与特征对应关系评估深度质量，取代了传统全局深度误差指标。
◆该框架仅需通过运动恢复结构等方法获取相机位姿，免去了昂贵且难以获取的密集真实深度图，使其适用于大尺度或严重遮挡等复杂场景。
◆构建了包含分布外挑战性场景的D2P数据集，揭示了在现有基准上表现优异的方法难以泛化到该更具挑战性的数据集上。
研究还提供了简单且可扩展的评估框架，并开源了代码与数据集，为深度估计的下游实用性评估建立了新标准。</td></tr>
<tr><td>2026-05-19</td><td>Enhancing Graph-Based SLAM in GNSS-Denied environments by leveraging leg odometry<br><a href='http://arxiv.org/pdf/2605.20484'>论文</a></td><td>本文针对足式机器人在拒止GNSS环境中LiDAR易产生高程漂移的问题，提出了一种基于因子图架构的SLAM增强方法。
◆在LIO-SAM框架中引入了由本体感受腿部里程计驱动的并行运动学通道。
◆通过带有选择性噪声模型的恒等相对位姿约束，将腿部运动学通道与主LiDAR-惯性通道有效耦合。
◆将步态控制中已计算的本体感受数据作为SLAM的轻量级垂直锚点，无需额外计算负担。
在四足平台超过1公里的户外测试中，该方法将高程漂移从30多米大幅降至30厘米以内。
在基线方法完全失效的几何稀疏场景下，本方法依然能成功收敛并实现鲁棒定位。</td></tr>
<tr><td>2026-05-19</td><td>Multi-Session Ground Texture SLAM in Low-Dynamic Environments<br><a href='http://arxiv.org/pdf/2605.19701'>论文</a></td><td>本文针对现有地面纹理SLAM系统尚未应用于多会话低动态变化环境的问题，研究了三种技术对轨迹估计精度的影响。研究发现，使用库尔巴克-莱布勒散度作为相似度评分和影响回环闭合置信度的偏差取得了最大成功。该工作的核心创新点如下：
◆首次将库尔巴克-莱布勒散度引入多会话低动态地面纹理SLAM中，全面分析了多种方法，并深入探索了该散度作为相似度评分与回环置信度偏差以提升轨迹估计精度的机制。
◆发布了一个全新的多会话地面纹理数据集，包含会话间地面发生变化的图像以及用于评估的高精度位姿信息，为机器人社区提供了宝贵的评估基准。</td></tr>
<tr><td>2026-05-19</td><td>EpiDiffVO: Geometry-Aware Epipolar Diffusion for Robust Visual Odometry<br><a href='http://arxiv.org/pdf/2605.19556'>论文</a></td><td>针对现有学习型视觉里程计依赖稠密匹配导致冗余且几何可解释性差的问题，本文提出了一种基于几何感知对极扩散的稀疏匹配框架。
◆引入对极扩散过程，通过建模对应点不确定性将关键点细化至对极一致性，以解决残差噪声与未对齐问题。
◆提出Steiner图表示法，将细化后的对应点与深度线索结合，利用图神经网络学习并筛选出信息量大的紧凑对应点子集。
筛选出的子集被输入可微奇异值分解求解器，实现端到端的相对位姿估计。
实验表明，该方法在减少匹配冗余的同时，能在具有挑战性的基线下保持鲁棒的位姿估计。</td></tr>
<tr><td>2026-05-19</td><td>Smartphone-based Circular Plot Sampling for Forest Inventory<br><a href='http://arxiv.org/pdf/2605.19213'>论文</a></td><td>本文提出了一种基于智能手机的轻量级圆形样地森林清查方法，解决了传统方法成本高或劳动强度大的问题。
◆提出仅需消费级手机与便携支架，通过单次穿行视频即可完成样地树木测量的轻量级流程。
◆创新性地将单目深度估计和树木实例分割与SLAM框架结合，联合优化相机轨迹与深度。
◆通过融合SLAM位姿和分割深度图恢复树木位置及胸径，并利用校准参考长度锚定绝对真实尺度。
实验表明，该方法在人工林和天然林的胸径测量平均绝对误差分别为1.51厘米和2.30厘米，且跨视频测量一致性强。
该系统实现了与传统方法相当的精度，但大幅降低了设备成本与操作复杂性，使专业和非专业用户均能广泛使用。</td></tr>
<tr><td>2026-05-18</td><td>Towards Ubiquitous Mapping and Localization for Dynamic Indoor Environments<br><a href='http://arxiv.org/pdf/2605.18385'>论文</a></td><td>该论文提出了UbiSLAM系统，旨在解决动态室内环境下的实时建图与定位问题。
◆采用部署固定RGB-D摄像机网络的方法，摆脱了对移动单元传感器的依赖，克服了传统SLAM对环境变化敏感的局限。
◆构建并持续更新集中式全局地图，为机器人提供准确的实时全局视图，从而提升导航精度、减少碰撞并优化人机交互。
◆将计算负载从机器人转移至固定网络，使低复杂度机器人平台也能高效运行，显著增强了系统的整体鲁棒性。
针对空间覆盖盲区挑战，论文探讨了整合机器人数据、自动校验相机布局及增强通信协议等潜在解决方案。
这些工作为实现泛在化的室内建图与定位提供了全新范式。</td></tr>
<tr><td>2026-05-17</td><td>Mono-Hydra++: Real-Time Monocular Scene Graph Construction with Multi-Task Learning for 3D Indoor Mapping<br><a href='http://arxiv.org/pdf/2605.17661'>论文</a></td><td>Mono-Hydra++提出了一种仅依赖单目RGB与IMU输入的...[摘要不完整，待更新]</td></tr>
<tr><td>2026-05-17</td><td>Stretch-ICP: A Continuous-Trajectory Registration and Deskewing Algorithm in Scenarios of Aggressive Motions<br><a href='http://arxiv.org/pdf/2605.17264'>论文</a></td><td>针对复杂环境中机器人剧烈运动导致传感器测量受损和状态估计退化的问题，本文提出了提升SLAM算法鲁棒性的方法。
◆提出TIGS数据集，包含激光雷达与IMU滚落山坡的记录，其最高角速度达同类数据集四倍且已公开。
◆提出饱和感知角速度估计算法SAAVE，在陀螺仪测量饱和时仍能准确估计角速度，将估计误差降低83.4%。
◆提出新型配准与去畸变算法Stretch-ICP，能在剧烈运动下重建更平滑的六自由度连续轨迹。
该算法将扫描边界处的线速度和角速度误差分别大幅降低了95.2%和94.8%。
综合来看，本文显著提升了剧烈运动场景下激光雷达惯性状态估计的鲁棒性与一致性。</td></tr>
<tr><td>2026-05-16</td><td>Rethinking the State Update Gate for Long-Sequence Recurrent 3D Reconstruction<br><a href='http://arxiv.org/pdf/2605.16981'>论文</a></td><td>本文揭示了长序列循环三维重建中现有逐令牌状态更新门存在幅值受限且随帧不变的结构瓶颈，导致有效记忆范围极短并引发长序列漂移。其根源在于现有方法仅在帧内逐令牌级别调节更新，忽略了每帧对状态贡献强度的帧级问题。
◆提出一种标量帧级门控机制，通过内部特征的帧间变化推导出闭式解，相当于经典SLAM关键帧选择的连续松弛。
◆该门控机制无需额外参数、训练或额外前向传播，在零训练成本下维持了严格的恒定内存预算。
在长达4541帧的六项基准测试中，该方法将长序列位姿误差降低51%，视频深度误差降低12.8%，性能全面超越现有基线。</td></tr>
<tr><td>2026-05-15</td><td>LAPS: Improving Incremental LiDAR Mapping using Active Pooling and Sampling for Neural Distance Fields<br><a href='http://arxiv.org/pdf/2605.15496'>论文</a> | <a href='https://github.com/dongjae0107/LAPS'>代码</a></td><td>本文提出LAPS框架，解决增量激光雷达建图中神经距离场在线优化易受灾难性遗忘影响的问题。现有方法采用被动缓冲区和均匀采样，导致内存浪费在冗余观测且对欠约束区域训练不足。
◆基于可靠性的主动池化机制，在有限内存下优先保留可靠的历史样本以改进回放保留。
◆基于不确定性的主动采样机制，引导优化过程聚焦于约束不足的区域以改进回放分配。
实验表明，LAPS在保持几何精度的同时显著提升了重建完整性，在Oxford Spires数据集上其召回率和F1分数均大幅超越PIN-SLAM。</td></tr>
<tr><td>2026-05-13</td><td>LEXI-SG: Monocular 3D Scene Graph Mapping with Room-Guided Feed-Forward Reconstruction<br><a href='http://arxiv.org/pdf/2605.13741'>论文</a> | <a href='https://ori-drs.github.io/lexisg-web/'>代码</a></td><td>LEXI‑SG 首次实现仅使用单目RGB相机的开放式词汇三维场景图稠密映射。  
◆ 通过开放式词汇基础模型将场景先划分为房间，在完整观测到房间后才进行前馈重建，避免了滑动窗口导致的比例不一致。  
◆ 提出基于房间的因子图框架，在全局对齐房间重建的同时保持局部地图一致并自然约束语义层次结构。  
◆ 在每个房间内部支持开放式词汇的物体分割与跟踪，实现细粒度目标层级的场景图。  
◆ 在 Habitat‑Matterport 3D 数据集和自采集的办公室序列上验证，显著提升轨迹估计和稠密重建质量，且在开放式词汇分割任务上表现具有竞争力。</td></tr>
<tr><td>2026-05-08</td><td>AERO-VIS: Asynchronous Event-based Real-time Onboard Visual-Inertial SLAM<br><a href='http://arxiv.org/pdf/2605.07885'>论文</a> | <a href='https://ethz-mrl.github.io/AERO-VIS'>代码</a></td><td>◆ The robustness of event cameras to high dynamic range and motion blur holds the potential to improve visual odometry systems in challenging environments.
◆ Although their high temporal resolution does not require synchronous processing, most event-based odometry methods still run at fixed rates, which simplifies system design but restricts latency and throughput.
◆ In this work, we present AERO-VIS, a stereo event-inertial SLAM system with an integrated, data-driven, robust, and performance-optimized keypoint detector.</td></tr>
<tr><td>2026-05-06</td><td>Dr-PoGO: Direct Radar Pose-Graph Optimization<br><a href='http://arxiv.org/pdf/2605.04806'>论文</a> | <a href='https://github.com/utiasASRL/dr_pogo'>代码</a></td><td>◆ This paper introduces Dr-PoGO, a method for Simultaneous Localization And Mapping (SLAM) using a 2D spinning radar.
◆ Unlike cameras or lidars that require line-of-sight, millimetre-wave radars can `see&#x27; through dust, falling snow, rain, etc.
◆ Accordingly, it is a great modality for robust perception regardless of the weather conditions.</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sfm'>SFM (40篇)</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-16</td><td>Fast Speech Foundation Model Distillation Using Interleaved Stacking<br><a href='http://arxiv.org/pdf/2606.11766'>论文</a></td><td>本文探索了语音基础模型蒸馏的训练加速问题，旨在加快模型部署速度。
现有的堆叠方法虽然能通过逐渐增加模型深度来加速训练，但会导致模型性能下降。
◆提出了一种名为交错堆叠的新型方法，在堆叠过程中始终保持层位置不变。
◆该方法有效保留了语音基础模型每层编码的独特层特有知识，解决了传统堆叠导致的性能退化问题。
在SUPERB基准上的实验验证了该方法能在加速蒸馏训练的同时有效保持模型性能。</td></tr>
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
<tr><td>2026-05-28</td><td>City-Mesh3R: Simulation-Ready City-Scale 3D Mesh Reconstruction from Multi-View Images<br><a href='http://arxiv.org/pdf/2605.30310'>论文</a></td><td>本文提出City-Mesh3R框架，实现从大规模无序图像直接重建适用于仿真的城市级高保真水密三维网格，克服了现有方法几何缺失和表面噪声的问题。
◆采用基于分治策略的端到端图像到网格重建流程，取代传统的全局稀疏SfM初始化与分布式稠密重建，使模型可扩展至任意大规模场景。
◆利用拓扑图像聚类进行聚类独立稀疏SfM与地图合并，无需穷举图像特征匹配即可构建稀疏城市地图。
◆结合几何感知相机选择与曲率感知自适应顶点密度重网格化技术进行表面细化，有效保障网格几何规则且细节精细。
◆通过空间分区与网格缝合技术无缝拼接局部网格，生成全局水密城市网格，验证了分布式端到端处理的卓越扩展性与重建保真度。</td></tr>
<tr><td>2026-05-28</td><td>The JADES Mass-Metallicity and Fundamental Metallicity Relations at $z\gtrsim2$ Using New High-Redshift Metallicity Calibrations<br><a href='http://arxiv.org/pdf/2605.30513'>论文</a></td><td>本文基于JWST先进深场河外巡天(JADES)的NIRSpec光谱数据,对601个星形成星系进行叠加分析,系统测量了红移1.4&lt;z&lt;7.0范围内的质量-金属丰度关系(MZR)与基本金属丰度关系(FMR),揭示了高红移宇宙中星系化学演化的规律。研究发现MZR斜率从z~0到z~5演化较弱(γ~0.21),归一化随红移以d log(O/H)/dz~-0.1的速率平滑下降;在z≳5以上,低质量端金属丰度持续下降而高质量端保持稳定,导致MZR整体变陡。研究还发现z~1.4-5存在MZR残差与主序偏移之间的弱反相关性,表明FMR在z~5时已开始显现。

◆ 首次采用基于高红移星系校准的最新强线金属丰度诊断方法,克服了以往使用本地校准外推到高红移的系统性偏差。

◆ 利用JADES提供的601个星系的大样本NIRSpec光谱,通过按恒星质量、红移和主序偏移的三维分箱叠加,首次在z≳5实现对FMR的统计性约束。

◆ 揭示了z≳5时MZR形态发生显著变化(低质量端持续贫金属化、高质量端停滞),为高红移星系受爆发式恒星形成与强反馈调控的图景提供了关键观测证据。

◆ 发现高红移FMR中SFR耦合强度弱于本地宇宙,表明气体调节机制在z~5左右才开始建立,为星系演化理论提供新约束。

◆ 系统对比多种宇宙学模拟,指出现有模拟均无法同时再现各红移下的MZR斜率与归一化,凸显了反馈物理模型的不足。</td></tr>
<tr><td>2026-05-27</td><td>CLEAR-NeRF: Collinearity and Local-region Enhanced Accurate 3D Reconstruction in Unbounded Scenes<br><a href='http://arxiv.org/pdf/2605.28125'>论文</a></td><td>本研究提出CLEAR-NeRF方法，将基于NeRF的三维重建应用于多关注区域的无界场景，提升了应对光照和位姿变化的鲁棒性，并确保了适用于数字孪生的度量精度。
◆自动局部区域定位检测与重建，无需增加子模块即可无缝优先处理关注区域。
◆共线性强制的射线采样，以学习平滑的平面和曲面。
◆深度定位邻域点提取，有效抑制表面伪影。
◆几何相关颜色聚合，缓解由光照和位姿引起的颜色变化。
实验表明该方法的性能显著优于基线NeRF模型和传统SfM-MVS解决方案。</td></tr>
<tr><td>2026-05-26</td><td>Global Structure-from-Motion Meets Feedforward Reconstruction<br><a href='http://arxiv.org/pdf/2605.26103'>论文</a> | <a href='https://github.com/colmap/gluemap'>代码</a></td><td>该论文深入分析了传统运动恢复结构方法在低纹理和对称等复杂场景易失败，而前馈重建方法虽能应对这些挑战却受限于可扩展性与精度的现状。
为此，论文提出了一种全新的SfM流程，成功将传统方法与前馈方法的优势相结合。
◆系统性分析了两类方法的局限性，并创新性地融合了传统SfM与前馈3D重建技术。
◆设计出优势互补的全新管线，既具备前馈方法在退化场景下的强鲁棒性，又保留了传统方法在标准场景下的高精度与可扩展性。
实验证明该方法在广泛场景中均达到了最先进水平，并且已将系统开源供社区使用。</td></tr>
<tr><td>2026-05-26</td><td>Joint 2D-3D Segmentation and Association in Street-level Imaging<br><a href='http://arxiv.org/pdf/2605.26725'>论文</a></td><td>本文提出了一种联合2D-3D分割与关联的统一框架，将视觉语义与多视图几何推理相结合以解析街景图像。
◆提出基于零样本检测分割与运动恢复结构重建的跨视图对应方法，摆脱了传统对时序帧跟踪的依赖。
◆设计了3D驱动的关联机制取代传统2D多目标跟踪，利用几何一致性在宽基线视角和多变条件下稳健保持目标身份。
该流水线融合了2D纹理线索与全局3D上下文，具备高度扩展性且适用于多种对象类型。
实验证明，该框架在真实序列覆盖度上大幅提升，在复杂城市场景中较纯2D跟踪方法实现了22%的性能增益。</td></tr>
<tr><td>2026-05-24</td><td>Geometry-Aware Image Flow Matching<br><a href='http://arxiv.org/pdf/2605.25294'>论文</a></td><td>本文针对自然图像生成领域局限于欧几里得假设而忽略数据内在几何结构的问题展开研究。研究发现自然图像的语义信息主要编码在方向分量中，范数分量可由全局平均值近似，这表明自然图像能在超球面上被有效建模。
◆提出球面最优传输流匹配方法，利用角距离实现几何感知的生成建模。
◆提出球面流匹配方法，将动态过程直接约束在流形上进行求解。
实验证明这些几何感知方法的性能显著优于欧几里得基线模型。本工作为弥合黎曼流形建模与自然图像生成之间的鸿沟提供了全新视角。</td></tr>
<tr><td>2026-05-22</td><td>Joint Target-Less Intrinsic and Extrinsic Camera-LiDAR Calibration using Deep Point Correspondences<br><a href='http://arxiv.org/pdf/2605.23397'>论文</a></td><td>本文提出首个完全无需标定板的相机与激光雷达联合标定流程，突破了现有基于深度点对应的标定方法需已知内参的局限。该方法利用深度像素点对应关系，可同时估计包含径向与切向畸变的针孔相机内参以及相机与激光雷达的外参。
◆通过运动恢复结构实现相机内参的自动初始化。
◆将相机与激光雷达特征匹配推广至包含畸变且内参未知的原始图像。
◆将对应点估计与内参及外参的联合非线性优化进行紧密耦合。
在KITTI数据集上的实验表明，该联合标定方法在恢复精确内参的同时有效提升了外参的标定精度。</td></tr>
<tr><td>2026-05-20</td><td>Sensitivity analysis of Stochastic Fluid Models: Stationary and transient quantities with applications<br><a href='http://arxiv.org/pdf/2605.21209'>论文</a></td><td>本文首次针对随机流体模型建立了敏感性分析的理论与结果。
◆推导了该类模型中关键稳态量和瞬态量的敏感性分析表达式。
◆构建数值算例验证了该方法在劣化系统与保险风险过程等排队系统中的应用潜力。
◆为更广泛的马尔可夫调制模型的敏感性分析研究奠定了理论基础。
这些成果不仅填补了随机流体模型敏感性分析的空白，也拓宽了相关理论在复杂系统中的应用边界。</td></tr>
<tr><td>2026-05-20</td><td>Transcoding a 3D Gaussian Splatting Model from a Plenoptic Point Cloud or Mesh without the Original Multi-view Images<br><a href='http://arxiv.org/pdf/2605.21051'>论文</a></td><td>本文提出了一种端到端的转码管线，在无法获取原始多视图图像的情况下，可直接从现有的全光点云或网格模型生成3D高斯溅射模型。
◆提出一种自定义初始化策略，有效引导3DGS模型的学习过程。
◆引入几何约束机制，确保最终生成的3DGS模型与输入的点云或网格表面紧密对齐。
实验表明，该管线生成的3DGS模型不仅视觉质量高，其使用的高斯点数量也远少于原始密集点云。
与传统SfM初始化方法相比，该自定义初始化显著加快了模型的收敛速度，并实现了更清晰的表面表示。</td></tr>
<tr><td>2026-05-20</td><td>JWST Advanced Deep Extragalactic Survey (JADES) Data Release 5: stellar population catalogue for galaxies in GOODS-N and GOODS-S<br><a href='http://arxiv.org/pdf/2605.21599'>论文</a></td><td>本文发布了JADES第五次数据释放的星系恒星种群星表，利用深空JWST成像和多波段数据对GOODS-N和GOODS-S区域约50万个源进行了均匀的贝叶斯物理性质推断。
星表推导了恒星质量、恒星形成率及尘埃消光等参数的后验分布，推进了对z=1至9约35万个星系低质量极限的测量和近期恒星形成约束。
◆创新性地采用随红移演化的星系主序先验来建模非参数化星系恒星形成历史，在保留非参数灵活性的同时为其提供了物理驱动的长期形状。
◆该先验将恒星质量增长与恒星形成率相联系，允许数据支持下的显著偏离，有效缓解了暗弱源的非物理解并减少了红移、年龄、尘埃与金属丰度间的简并性。
经过验证的公开星表为研究宇宙演化中星系生长、熄灭及恒星质量积累提供了可靠的统计样本。</td></tr>
<tr><td>2026-05-19</td><td>Depth2Pose: A Pose-Based Benchmark for Monocular Depth Estimation without Ground-Truth Depth<br><a href='http://arxiv.org/pdf/2605.19797'>论文</a> | <a href='https://kocurvik.github.io/depth2pose'>代码</a></td><td>该论文提出Depth2Pose框架，将单目深度估计的评估与下游几何任务结合，解决了传统深度误差指标无法反映深度对下游任务有用性的问题。
◆提出以相对相机位姿估计精度作为任务驱动的深度质量代理指标，通过结合深度预测与特征对应关系来评估单目深度估计器。
◆打破对昂贵逐像素真实深度标注的依赖，仅需通过运动恢复结构获取相机位姿即可评估，使框架适用于大尺度或严重遮挡等困难场景。
◆构建了D2P数据集，包含常见训练数据分布之外的极具挑战性的场景。
实验表明，在传统基准上表现优异的方法在相同数据集上位姿指标良好，却难以泛化到D2P数据集，该评估框架及代码已开源。</td></tr>
<tr><td>2026-05-18</td><td>Efficient 3D Content Reconstruction and Generation<br><a href='http://arxiv.org/pdf/2605.18052'>论文</a></td><td>该论文致力于推动自动3D内容创建技术的发展，以替代耗时的人工建模和扫描流程。论文的核心贡献涵盖了3D生成与3D重建这两个互补的研究范式。
◆在3D生成方面，提出了Instant3D方法，创新性地将多视角扩散与前馈稀疏视角3D重建相结合，在5至20秒内即可生成高质量的3D资产。
◆在3D重建方面，开发了FastMap运动恢复结构流程，通过广泛结合一阶优化与融合GPU内核，相比现有最优方法实现了高达10倍的加速。
◆FastMap在实现极致加速的同时，依然保持了与之前方法相当的相机位姿估计精度和下游新视角合成质量。</td></tr>
<tr><td>2026-05-16</td><td>RHINO: Reconstructing Human Interactions with Novel Objects from Monocular Videos<br><a href='http://arxiv.org/pdf/2605.17014'>论文</a> | <a href='https://lxxue.github.io/RHINO'>代码</a></td><td>本文提出了RHINO三步框架，从单目RGB视频中共同恢复人、未知物体和静态场景的3D重建，解决了深度模糊、遮挡和运动纠缠的难题。同时，该研究构建了包含手持单目视频与4D捕捉真值的新数据集，并在新视角合成与4D重建任务上超越了现有基线。
◆利用3D感知基础模型稳定结构恢复，分别从前景和背景像素提取粗糙物体形状与表观运动以及场景形状与相机运动。
◆通过估计人体并从表观运动中减去相机运动来提取物体真实运动，成功将人、物体和场景对齐到统一的世界坐标系中。
◆采用具有逐组件符号距离场的组合式神经场细化形状，并引入可微接触先验吸引表面同时惩罚穿透，提升重建的物理合理性。</td></tr>
<tr><td>2026-05-16</td><td>SemaVoice: Semantic-Aware Continuous Autoregressive Speech Synthesis<br><a href='http://arxiv.org/pdf/2605.16964'>论文</a></td><td>现有连续自回归语音合成存在语义建模与连续语音表示不匹配的问题，导致模型过度关注低级声学纹理而牺牲高级语义连贯性，加剧了生成误差累积。为解决此问题，本文提出SemaVoice，一种面向高保真零样本文本转语音的语义感知连续自回归框架。
◆引入语音基础模型引导的对齐机制，精炼连续语音表示以更好捕获局部语义一致性与全局结构关系。
◆在自回归框架内采用块级扩散头，基于精炼后的表示条件进行高质量语音合成。
实验表明，SemaVoice在Seed-TTS基准上取得1.71%的英文词错率，主客观评估均媲美前沿开源系统，且验证了该对齐机制在不同表示粒度下的显著提升效果。</td></tr>
<tr><td>2026-05-15</td><td>SCARED-C: Corrected Camera Poses for Endoscopic Depth Estimation<br><a href='http://arxiv.org/pdf/2605.16628'>论文</a></td><td>本论文指出了广泛使用的内窥镜深度估计基准SCARED数据集存在非关键帧位姿误差严重的问题，导致其可靠标注仅限35个关键帧。
◆提出SCARED-C修正数据集，利用运动恢复结构系统COLMAP重新估计所有帧的相机位姿，有效消除了原数据集由机器人运动学引入的误差。
◆设计了尺度恢复步骤，通过关键帧的真实深度图将重建结果对齐到度量空间，确保了深度数据的物理尺度准确性。
◆大幅扩充了高质量的可用数据，将可靠的RGB-D图像对数量从原本的35个增加至17135个。
该研究还通过立体视差评估和单目深度估计实验验证了修正位姿的有效性，并公开了数据集与代码。</td></tr>
<tr><td>2026-05-14</td><td>Denoising-GS: Gaussian Splatting with Spatial-aware Denoising<br><a href='http://arxiv.org/pdf/2605.14880'>论文</a></td><td>本文提出Denoising-GS框架，将3D高斯溅射的优化过程重新定义为基元去噪过程，解决了现有方法仅调整位置而忽略空间结构从而引入噪声的问题。
◆设计了保留空间优化流的优化器，实现连贯且有方向性的去噪而非随机扰动。
◆提出空间梯度去噪策略，结合基元的空间支撑确保梯度一致性更新。
◆引入基于不确定性的去噪模块，通过估计基元的不确定性来修剪冗余和噪声基元。
◆采用空间连贯性细化策略，在稀疏区域选择性地分裂基元以维持结构完整性。
实验表明该方法在提升新视角合成保真度的同时保持了表示紧凑性，在多个基准上达到最佳性能。</td></tr>
<tr><td>2026-05-14</td><td>Efficient Dense Matching for Enhanced Gaussian Splatting Using AV1 Motion Vectors<br><a href='http://arxiv.org/pdf/2605.14629'>论文</a></td><td>本文针对3D高斯泼溅依赖初始点云质量且传统SfM管道计算成本高、无纹理区域点云稀疏的问题，提出了一种基于AV1的特征检测与匹配管道。
◆利用AV1视频编解码器固有的运动向量进行特征匹配，绕过了计算昂贵的穷举匹配，同时保持了几何鲁棒性。
◆该管道能生成比传统SfM密集最多八倍的点云，有效解决了无纹理区域的稀疏性问题。
这种增强的密集初始化直接提升了3DGS的整体性能表现。
实验表明，该方法使VMAF指标提升了9分，且达到基准质量所需的平均训练时间减少了63%，显著提高了重建效率和视觉保真度。</td></tr>
<tr><td>2026-05-12</td><td>WildPose: A Unified Framework for Robust Pose Estimation in the Wild<br><a href='http://arxiv.org/pdf/2605.12774'>论文</a></td><td>本文提出了WildPose，一个统一的单目位姿估计框架，有效解决了动态环境下的位姿估计难题，同时在纯静态和低自运动场景中保持SOTA性能。
◆创新性地将前馈模型的丰富感知前端与可微束调整的端到端优化两种强大范式相连接。
◆基于冻结的预训练MASt3R特征骨干构建了3D感知更新算子，强化了模型的3D空间理解与特征关联能力。
◆设计了高容量运动掩码检测器，利用同一骨干网络提取的多级3D感知特征精准识别并屏蔽动态物体干扰。
广泛的实验证明，该框架在动态、静态及低自运动等多种基准测试上均持续超越现有方法。</td></tr>
<tr><td>2026-05-12</td><td>3D Gaussian Splatting for Efficient Retrospective Dynamic Scene Novel View Synthesis with a Standardized Benchmark<br><a href='http://arxiv.org/pdf/2605.12437'>论文</a></td><td>本文针对同步多视角动态场景的回顾式新视角合成问题，提出在具备强几何约束的同步多视角设置下，无需使用显式时间耦合或复杂多体约束。
◆提出一种无时间变形约束的3D高斯溅射方法，通过初始化起始时刻的SfM点云并随时间传播优化高斯，实现高效的动态场景新视角合成。
◆构建基于Blender的动态多视角数据集生成框架，能生成高质量同步摄像机阵列并以标准格式导出，消除坐标系与数据流水线的不一致性。
◆利用该框架创建动态基准测试套件，在受控条件下对代表性NeRF和3DGS方法进行标准化评估，推动动态新视角合成方法可复现性研究。
研究表明，在同步多视角配置下仅用3D高斯溅射即可高效实现动态场景合成，同时提供的数据框架填补了该领域标准化基准的空白。</td></tr>
<tr><td>2026-05-12</td><td>Compositional Neural Operators for Multi-Dimensional Fluid Dynamics<br><a href='http://arxiv.org/pdf/2605.11691'>论文</a></td><td>本文针对科学基础模型预训练成本高且缺乏可解释性的问题，提出了用于二维流体动力学的组合神经算子框架。该框架的核心思想是将复杂偏微分方程分解并预训练为一系列基础物理算子。
◆构建了包含对流、扩散、非线性对流专用算子及泊松求解器的模块化库，有效解决了不可压缩流体中的压力与速度耦合问题。
◆设计了带有聚合器的适应模块，通过最小化数据损失和源自控制方程的物理残差来学习基础算子间的非线性相互作用。
在对流扩散、伯格斯和纳维-斯托克斯方程上的实验表明，该方法显著提升了模型对新物理系统的适应性与可解释性，并促进了预训练模块的高效复用。</td></tr>
<tr><td>2026-05-11</td><td>3DReflecNet: A Large-Scale Dataset for 3D Reconstruction of Reflective, Transparent, and Low-Texture Objects<br><a href='http://arxiv.org/pdf/2605.10204'>论文</a></td><td>本文针对反射、透明和弱纹理物体3D重建的难题，提出了超大规模混合数据集3DReflecNet。
◆构建了超22TB的大规模混合数据集，包含逾12万个基于物理渲染的合成实例与1千多个真实世界物体，总计超700万帧多视角图像。
◆数据涵盖多种材质、复杂光照及广泛几何形态，并创新性地利用扩散模型管道从真实与LLM合成的2D图像生成3D形状。
◆为图像匹配、运动恢复结构、新视角合成、反射去除和重照明五个核心任务设计了评估基准。
大量实验证明现有先进方法在这些复杂材质下难以保持精度，凸显了该数据集对推动鲁棒3D视觉模型发展的重要价值。</td></tr>
<tr><td>2026-05-11</td><td>BathyFacto: Refraction-Aware Two-Media Neural Radiance Fields for Bathymetry<br><a href='http://arxiv.org/pdf/2605.10174'>论文</a></td><td>BathyFacto是一种集成于Nerfstudio的折射感知双介质神经辐射场方法，旨在解决浅水测深中水面折射导致的深度偏差，生成高精度水下点云。
◆提出基于共享哈希网格密度场与介质条件颜色头的双段光线追踪机制，依斯涅尔定律将光线分为空气直线段与水中折射段渲染。
◆设计折线密度包装...[摘要不完整，待更新]</td></tr>
<tr><td>2026-05-08</td><td>TriP: A Triangle Puzzle Approach to Robust Translation Averaging<br><a href='http://arxiv.org/pdf/2605.07143'>论文</a></td><td>本文提出了TriP，一种基于三角形的鲁棒平移平均框架，旨在从成对相对平移方向中恢复相机位置。
◆利用三角形几何推断局部边尺度，并在对数域同步重叠三角形的尺度以恢复全局边长，通过高阶一致性有效对抗恶意与结构化腐蚀。
◆无需额外反塌缩约束即可避免塌缩问题，因为对数尺度同步在构造上直接排除了退化的零尺度解。
◆为精确的相机位置恢复提供了极强的理论保证。
该方法完全可并行化且计算高效，能自然扩展至数百万相机的图。
在合成和真实数据集上的实验表明，TriP大幅超越了所有现有的平移平均方法。</td></tr>
<tr><td>2026-05-06</td><td>egenioussBench: A New Dataset for Geospatial Visual Localisation<br><a href='http://arxiv.org/pdf/2605.05351'>论文</a> | <a href='https://github.com/fratopa/egenioussBench'>代码</a></td><td>◆ We present egenioussBench, a visual localisation benchmark built on geospatial reference data: a city-scale airborne 3D mesh and a CityGML LoD2 model.
◆ This pairing reflects deployable mapping assets and supports true scalability beyond traditional SfM-based approaches.
◆ The query data comprise smartphone images with centimetre-accurate, map-independent ground truth obtained via PPK and GCP/CP-aided adjustment.</td></tr>
<tr><td>2026-05-03</td><td>DP-SfM: Dual-Pixel Structure-from-Motion without Scale Ambiguity<br><a href='http://arxiv.org/pdf/2605.01852'>论文</a> | <a href='https://github.com/lilika-makabe/dp-sfm-tpami.git'>代码</a></td><td>◆ Multi-view 3D reconstruction, namely, structure-from-motion followed by multi-view stereo, is a fundamental component of 3D computer vision.
◆ In general, multi-view 3D reconstruction suffers from an unknown scale ambiguity unless a reference object of known size is present in the scene.
◆ In this article, we show that multi-view images captured using a dual-pixel (DP) sensor can automatically resolve the scale ambiguity, without requiring a reference object or prior calibration.</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='image-matching'>Image Matching (11篇)</h2>

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
<tr><td>2026-06-01</td><td>SOCO: Benchmarking Semantic Object Correspondence in Vision Foundation Models<br><a href='http://arxiv.org/pdf/2605.31597'>论文</a></td><td>本文提出SOCO基准，旨在解决视觉基础模型中结构化对象理解评估协议不一致和部件级监督有限的问题。
◆构建了包含对应类型分类法的语义对象对应基准，在100个类别和超百万对应对上提供一致且具功能意义的关键点标注。
◆引入关键点语言描述，支持对大型视觉语言模型细粒度部件级理解能力的系统评估。
◆揭示视觉骨干网络虽编码强语义结构，但跨类别迁移对应能力差且仅部分捕获部件位置。
◆发现大视觉语言模型擅长文本提示定位但视觉参考跨图匹配较弱，暴露语言接地与视觉对应间的鸿沟。
◆证明对应性能比ImageNet分类性能更能强有力地预测分割、跟踪及3D检测等密集下游任务的表现。</td></tr>
<tr><td>2026-05-30</td><td>BEVIO: Efficient Bird&#x27;s-Eye-View based Sparse-Update Visual-Inertial Odometry for Lunar Day-Night Navigation<br><a href='http://arxiv.org/pdf/2606.00709'>论文</a></td><td>本文针对月球漫游车计算资源受限及昼夜自带光源下特征关联困难的挑战，提出了基于鸟瞰图的稀疏更新视觉惯性里程计BEVIO。
◆提出基于鸟瞰图的图像匹配方案，有效增强了对更大帧间运动的鲁棒性。
◆在显著视觉外观变化下实现了更可靠的特征匹配，克服了夜间自带光源照明的干扰。
◆支持在极稀疏视觉更新率下进行可靠的里程计估计，大幅降低了对计算资源和功耗的依赖。
通过高保真月球仿真和半比例漫游车在真实环境中的长期昼夜部署实验，验证了该方法在低至0.25赫兹更新频率下仍能实现可靠的昼夜导航。</td></tr>
<tr><td>2026-05-29</td><td>MAPRPose: Mask-Aware Proposal and Amodal Refinement for Multi-Object 6D Pose Estimation<br><a href='http://arxiv.org/pdf/2604.20650'>论文</a></td><td>本文针对杂乱场景中严重遮挡和噪声导致的6D姿态估计难题，提出了MAPRPose两阶段框架。
◆在姿态提案阶段，将2D对应关系提升至3D空间建立可靠关键点匹配，基于对应级评分生成几何一致的姿态假设选出Top-K候选。
◆在细化阶段引入AMPR模块，通过重建完整物体几何与动态调整ROI，有效缓解重度遮挡下的定位误差和空间错位。
◆设计GPU加速的RGB-XYZ重投影机制，在张量化渲染比较管线中实现单次前向传播同步细化所有姿态假设。
该方法在BOP基准上取得76.5%的最优平均召回率，精度超越FoundationPose 3.1%，且多目标推理速度提升43倍。</td></tr>
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
<tr><td>2026-05-01</td><td>Are Pretrained Image Matchers Good Enough for SAR-Optical Satellite Registration?<br><a href='http://arxiv.org/pdf/2604.10217'>论文</a></td><td>◆ Cross-modal optical-SAR (Synthetic Aperture Radar) registration is a bottleneck for disaster-response via remote sensing, yet modern image matchers are developed and benchmarked almost exclusively on natural-image domains.
◆ We evaluate twenty-four pretrained matcher families--in a zero-shot setting with no fine-tuning or domain adaptation on satellite or SAR data--on SpaceNet9 and two additional cross-modal benchmarks under a deterministic protocol with tiled large-image inference, robust geometric filtering, and tie-point-grounded metrics.
◆ Our results reveal asymmetric transfer--matchers with explicit cross-modal training do not uniformly outperform those without it.</td></tr>
<tr><td>2026-05-01</td><td>TrueEBSD in MTEX: automatic image matching for correlative microscopy applications<br><a href='http://arxiv.org/pdf/2605.00703'>论文</a></td><td>◆ TrueEBSD is an open-source MATLAB program for image alignment and spatial distortion correction of images and electron backscatter diffraction (EBSD) maps.
◆ We have re-implemented TrueEBSD as an add-on to MTEX, an established toolbox for EBSD data analysis.
◆ Spatial alignment enables correlative analysis methods, such as augmenting EBSD orientation maps with data from other imaging modes.</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='obstacle-avoidance'>Obstacle Avoidance (79篇)</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-06-14</td><td>Act on What You See: Unlocking Safe Social Navigation in Vision-Language-Action Models<br><a href='http://arxiv.org/pdf/2606.10495'>论文</a></td><td>本文提出SALSA框架，解决了预训练视觉-语言-动作模型虽已编码行人区分与碰撞信号，但行为克隆无法将其转化为安全社交动作的问题。
◆社交行为对齐，将中间层社交特征桥接至动作头，并利用反事实人-物场景对进行训练以打破视觉显著性捷径。
◆时序安全对齐，通过自动生成的未来风险监督信号，使模型能够实现前瞻性的碰撞规避。
实验表明，SALSA在无需额外标注的情况下将近距离碰撞减少了86.4%，并将社交反事实准确率从53%提升至93%。
该研究证明，通过更好地对齐潜层表征与动作生成，即可让模型依据已有表征行动，成功解锁预训练VLA策略的安全社交导航潜能。</td></tr>
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
<tr><td>2026-06-13</td><td>GuideWalk: Learning Unified Autonomous Navigation and Locomotion for Humanoid Robots across Versatile Terrains<br><a href='http://arxiv.org/pdf/2606.10449'>论文</a></td><td>本文提出了GuideWalk框架，这是一个将可穿越性感知导航引导与地形自适应运动教师相结合的统一端到端人形机器人导航框架。
◆引入提供显式速度引导的导航模块，将避障与地形条件解耦，从而在多样环境中实现鲁棒规划。
◆提出复合教师蒸馏方案，将目标导向指令与动态一致动作聚合并蒸馏至单一策略中。
◆采用强化学习和辅助行为克隆目标精炼蒸馏策略，在促进探索的同时保留教师的优良行为。
实验表明，该框架能够在各种复杂地形上实现稳定且有效的人形机器人导航与运动控制。</td></tr>
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
<tr><td>2026-06-09</td><td>NOVA: Symbolic Regression Discovery of Interpretable Car-Following and Lane-Change Models with Driver Heterogeneity<br><a href='http://arxiv.org/pdf/2606.10583'>论文</a></td><td>本文提出了NOVA自主符号回归框架，能在极少先验下从原始轨迹数据中发掘可解释的跟车与换道模型。
◆开发了基于Rust的确定性搜索引擎，在海量数据中评估万级代数结构，提取出紧凑的双项加速度模型。
◆在跟车预测任务上超越现有最优基线，并发现一个鲁棒的主导非线性项作为跟车骨架，残差分析揭示了其与碰撞避让心理物理学理论的联系。
◆发现的特征算子在不同高速公路场景间具备零样本迁移能力，泛化性能损失极小。
◆将模型扩展至换道建模，结合多项逻辑斯蒂框架在未知驾驶员测试上取得67.4%的平衡准确率，大幅超越现有基线近三十个百分点。</td></tr>
<tr><td>2026-06-08</td><td>Your Model Already Knows: Attention-Guided Safety Filter for Vision-Language-Action Models<br><a href='http://arxiv.org/pdf/2606.09749'>论文</a></td><td>该论文提出了一种免训练的注意力引导安全过滤框架，解决了视觉语言动作模型无法实时避开任务无关物体的问题。作者发现VLA模型内部的少数注意力头能够可靠地定位策略意图接近的目标物体。
◆提出利用VLA模型内部注意力头实时提取活跃目标，无需额外训练或调用缓慢的视觉语言模型。
◆将提取的目标与轻量级实时跟踪器及控制障碍函数过滤器结合，实现了对非静态障碍物的实时避碰。
◆扩展了包含移动障碍物的动态评估基准，在动态场景中比依赖初始化识别的预言机方法平均性能提升43%。</td></tr>
<tr><td>2026-06-08</td><td>Safe Polytope-in-Polytope Motion Planning and Control with Control Barrier Functions<br><a href='http://arxiv.org/pdf/2606.09719'>论文</a></td><td>本文提出了一种基于控制屏障函数的安全多面体内多面体局部运动规划与控制方法，确保多面体形状的机器人足迹始终保持在持续更新的凸自由空间区域内。该方法将包容条件转化为模型预测控制器中的离散时间控制屏障函数约束，克服了传统简化几何模型在狭窄环境中过于保守的问题。
◆安全约束数量仅取决于局部自由空间几何复杂度和机器人形状，而非障碍物数量，有效降低了计算维度。
◆所提出的自由空间公式化无需进行任何障碍物检测或分割，简化了系统的处理流程。
◆与传统的多面体避障公式相比，该方法计算时间最高可缩减91倍，显著提升了规划效率。
该方法在仿真和硬件平台上均得到验证，成功在嵌入式计算机上实现了10Hz的实时安全规划及动态障碍物反应式避障。</td></tr>
<tr><td>2026-06-08</td><td>Motion planning for hundreds of floating robots<br><a href='http://arxiv.org/pdf/2606.09620'>论文</a></td><td>本文解决了大规模水面浮动机器人集群因避障产生强耦合而导致的运动规划难题，实现秒级生成跨越数千时间步的无碰撞轨迹。
◆提出了一种可扩展的运动规划流水线，能够根据稀疏关键帧快速为数百个机器人生成编舞轨迹。
◆通过构建碰撞图将强耦合问题分解为多个交互簇，使得各簇能够独立且并行地求解，大幅提升了计算效率。
◆设计了针对常见分解病理的鲁棒性机制，确保了并行求解过程和最终轨迹的可靠性。
该方法在多达500个机器人的仿真中得到验证，并成功部署于苏黎世湖24艘船只及2025年威尼斯双年展的真实场景中。</td></tr>
<tr><td>2026-06-08</td><td>Shape Formation for the Cooperative Transportation of Arbitrary Objects Using Multi-Agent Reinforcement Learning<br><a href='http://arxiv.org/pdf/2606.09610'>论文</a></td><td>本文针对具有任意形状和非均匀质量分布的现实物体协作运输挑战，提出了一种新颖的多智能体强化学习方法来解决模式编队控制问题。该方法使多机器人系统能够自主移动到物体下方以安全支撑其重量。
◆创新性地解决了现实物体任意形状与非均匀质量分布带来的支撑难题，使机器人能够自主定位以平衡支撑物体重量。
◆将编队控制与避障相结合，使机器人在形成支撑编队的过程中能够有效避开环境障碍物。
◆提出的策略展现出强大的泛化能力，在多样环境与不同数量机器人下，能够可靠生成平衡编队，并成功适用于杂乱场景及复杂物体。</td></tr>
<tr><td>2026-06-08</td><td>LAEI: Layered Autonomous Edge Intelligence Framework for Robust UAV Swarm Operations<br><a href='http://arxiv.org/pdf/2606.09099'>论文</a></td><td>本文提出了分层自主边缘智能LAEI框架，旨在解决无人机集群在通信受限与故障场景下的协调难题，克服了集中式易受单点影响与完全去中心化缺乏全局一致性的缺陷。该框架的核心创新如下。
◆提出机载学习与轻量级监督相结合的分层架构，无人机本地执行感知避障与动作选择，监督层提供自适应目标重分配和策略指导但不干预底层动作。
◆设计故障感知恢复机制，集成动态重关联、备份监督支持与局部自主降级策略，有效保障故障场景下的任务连续性。
◆在保障分布式防碰撞决策的前提下，显著缩短任务完成时间并提升整体运行效率。</td></tr>
<tr><td>2026-06-08</td><td>Autonomous FPV Flight with Translational Optical Flow and Uncertainty Mask<br><a href='http://arxiv.org/pdf/2606.09088'>论文</a></td><td>本文提出一种基于平移光流和不确定性掩膜的单目RGB四旋翼自主避障与高速飞行系统。
◆提出将光流分解为平移和旋转分量，仅使用捕捉场景几何与深度线索的平移光流作为输入，解决了障碍物光流与自运动背景光流难以分离的问题。
◆引入由前向和后向光流估计不一致性导出的不确定性掩膜，有效凸显了包括扩展焦点区域在内的障碍物结构，克服了该区域信噪比低的瓶颈。
◆将上述线索输入基于可微分仿真框架训练的控制策略，实现了感知与控制模块之间的高效一阶优化。
实验表明，该系统在真实森林环境中实现了11.79米/秒的高速飞行，成功率达93.3%，将单目光流无人机的真实世界飞行速度记录几乎提升了一倍。</td></tr>
<tr><td>2026-06-08</td><td>FlexPath: Learned Semantic Path Priors for Image-Based Planning<br><a href='http://arxiv.org/pdf/2606.10167'>论文</a> | <a href='https://github.com/FraunhoferIVI/FlexPath'>代码</a></td><td>◆ FlexPath提出两阶段图像规划框架，将“路径可行性”与“任务偏好”解耦，突破了以往学习式规划器受最短路径监督目标限制的问题。
◆ 第一阶段通过模仿学习从视觉地图中学习任务无关的可行路径空间先验，获得可复用的路径结构知识。
◆ 第二阶段引入可微的路径形状目标（PSOs），无需重新学习模型即可将同一先验适配到最短路、避障间隙、语义避让和航点引导等不同目标。
◆ 在最短路径任务中，FlexPath相比TransPath在TMP上减少14.3%的搜索开销，同时平均路径成本更低，并在三个未见域中表现出强零样本泛化能力。
◆ 该方法还能与经典规划器在推理阶段兼容，兼具学习方法的灵活性和传统搜索的可靠性。</td></tr>
<tr><td>2026-06-07</td><td>IR-SIM: A Lightweight Skill-Native Simulator for Navigation, Learning, and Benchmarking<br><a href='http://arxiv.org/pdf/2606.08729'>论文</a> | <a href='https://github.com/hanruihua/ir-sim'>代码</a></td><td>本文提出了一个轻量级技能原生导航仿真器IR-SIM，旨在解决现有仿真器接口复杂阻碍快速原型开发的问题。
◆场景完全由YAML文件定义，使仿真完全可描述和可复现，并通过智能体技能支持直接从文本提示生成和修改场景。
◆支持导航算法的自动化基准测试以及机器人学习训练数据的自动生成，极大提升了算法评估与模型训练效率。
◆提供通向高保真仿真器和真实世界部署的桥梁，用户无需额外编码即可在更真实的环境中验证原型算法。
多项实验充分验证了IR-SIM在自然语言构建场景、避碰策略训练及虚实迁移等任务上的便捷性与多功能性。</td></tr>
<tr><td>2026-06-07</td><td>Real-Time and Accurate Collision-Free Teleoperation via Differentiable Constraint-Based Trajectory Planning<br><a href='http://arxiv.org/pdf/2606.08725'>论文</a></td><td>本文针对遥操作中仅控制末端执行器易导致机械臂碰撞的问题，提出了一种基于可微约束的实时无碰撞轨迹规划方法。
◆将基于凸优化对偶性的可微避碰约束公式引入遥操作场景，避免了传统方法因近似导数导致的收敛差与计算耗时问题。
◆采用胶囊体近似机械臂和多面体表示环境障碍物，克服了传统球体近似几何精度低的缺陷，实现了更准确的障碍物建模。
仿真与真实UR5e机械臂的实验结果表明，该方法在多变障碍物环境中具有更低的计算延迟。
最终实现了更平滑且完全无碰撞的末端执行器遥操作，有效提升了系统的安全性与实时性。</td></tr>
<tr><td>2026-06-07</td><td>Towards End to End Motion Planning and Execution for Autonomous Underwater Vehicles Using Reinforcement Learning<br><a href='http://arxiv.org/pdf/2606.08513'>论文</a></td><td>该论文提出了一种面向自主水下航行器(AUV)的端到端深度强化学习运动规划与执行框架,旨在减少传统流水线中繁重的人工工程设计,直接将原始传感器数据映射为推进器指令。作者设计了分层强化学习架构,将问题拆分为两个马尔可夫决策过程,并在高保真HoloOcean仿真器中验证。实验结果显示,该方法在轨迹长度上接近RRT*基线(差距仅4%-6%),并对传感器噪声和能见度下降表现出较强鲁棒性,但在新颖障碍物形状的未知场景中泛化能力有限。整体上,该工作展示了样本高效的端到端DRL在水下导航中的可行性,且仅需极少计算硬件。

◆ 提出双层级HRL架构:高层策略以2Hz处理原始单目相机图像、前视声呐和本体感知数据生成空间子目标,低层策略以10Hz将子目标转换为推进器指令,实现感知到控制的端到端闭环。

◆ 高层策略采用基于先验示范的强化学习(RLPD),并在改进的SERL框架内训练,显著提升了样本效率。

◆ 低层策略结合Soft Actor-Critic与Hindsight Experience Replay,有效处理稀疏奖励下的子目标到达问题。

◆ 首次在高保真HoloOcean仿真器中实现融合视觉与声呐多模态原始输入的端到端AUV避障导航,且性能可媲美经典RRT*规划。

◆ 系统验证了该方法对传感器噪声及低能见度等水下典型扰动的鲁棒性,并明确指出当前方法在未知几何环境中的泛化局限。</td></tr>
<tr><td>2026-06-06</td><td>A Barrier-Modulated Architecture for Safe Affine Formation Control in Second-Order Multi-Agent Systems<br><a href='http://arxiv.org/pdf/2606.08137'>论文</a></td><td>本文针对二阶多智能体系统，提出了一种结合高阶控制障碍函数与自适应动态规划的安全仿射编队控制框架，解决了参数不确定性下的避碰挑战。
◆引入障碍调制控制架构，在智能体接近安全边界时平滑衰减名义编队跟踪目标，有效防止控制输入冲突。
◆开发了解析型障碍梯度排斥控制器，具有计算高效的特点，为安全控制提供了严格的数学基准。
◆设计了基于执行器-评论家神经网络的数据驱动最优安全控制器，通过在线求解HJB方程实现未知参数下的最优避碰。
理论证明上述控制器均能保证安全集前向不变性以实现绝对避碰，并维持编队跟踪误差一致最终有界，仿真验证了其鲁棒性。</td></tr>
<tr><td>2026-06-06</td><td>Learning Predictive Control with Deep Koopman Operators for Autonomous Vehicle Motion Planning<br><a href='http://arxiv.org/pdf/2606.08136'>论文</a></td><td>本文提出了基于深度Koopman算子的学习预测控制框架，以解决传统模型预测控制实时性差和强化学习缺乏控制理论结构的问题。
◆提出基于深度Koopman的预测器，以数据驱动方式将非线性不确定车辆动力学提升至可解释的线性可观空间。
◆通过滚动时域Actor-Critic学习，在每个预测区间内生成闭环状态反馈策略，克服了传统MPC仅计算开环控制序列的局限。
◆针对非凸环境约束构建障碍物的凸局部替代表示并定义势场函数，将其与梯度直接嵌入Actor-Critic结构以实现安全感知的策略学习。
仿真与红旗实车实验表明，该框架在复杂避障场景下的安全性计算效率和舒适性均优于现有基准方法。</td></tr>
<tr><td>2026-06-05</td><td>Spline Policy: A Structured Representation for Robot Policies<br><a href='http://arxiv.org/pdf/2606.07386'>论文</a></td><td>本论文提出 Spline Policy (SP),一种用于机器人操控的结构化策略表示方法。该方法以样条参数取代传统模仿学习中固定分辨率的动作块 (action chunks),在保持策略主干网络不变的前提下,显式暴露出机器人动作的几何与时间结构,从而支持紧凑解码、时间重采样、参数空间编辑、不确定性传播以及与经典控制器的兼容融合。作者将 SP 应用于扩散模型、流匹配、Transformer 及视觉-语言-动作等多种主流策略框架,并在低维运动学习、仿真操控、灵巧操控和真实机器人任务中验证了其有效性。

◆ 提出样条参数化策略表示 SP,替代固定分辨率动作块,可在执行前显式呈现动作的几何与时间结构,并能以任意时间分辨率查询和编辑。
◆ 针对二次样条输出,设计了基于解析距离场的构造方法,将样条转化为状态相关的向量场,在正则性与投影假设下保证诱导动力学不会增加到预测轨迹的距离,从而提供有原则的局部纠偏机制。
◆ 支持从观测到样条参数、轨迹及流场的不确定性传播,为策略输出提供可量化的可信度评估。
◆ 可与零空间避障等经典控制机制无缝结合,无需重新训练策略主干即可实现安全约束。
◆ 该表示具有良好通用性,可即插即用地嵌入扩散、流匹配、Transformer 及 VLA 等多种现代策略学习框架。</td></tr>
<tr><td>2026-06-05</td><td>Task Editing for Generalizable 3D Visuomotor Policy Learning<br><a href='http://arxiv.org/pdf/2606.07012'>论文</a></td><td>这篇论文针对3D视觉运动策略学习中真实世界示范数据收集成本高、现有数据增强方法仅做局部物体变换而难以合成多样化场景-技能-物体组合的问题,提出了一种名为Task-Edit的新型示范生成框架。该框架从任务中心的编辑视角出发,将任务分解为场景、技能和物体三个组件,并通过灵活重组这些组件来生成多样化的轨迹数据,从而实现可扩展的示范生成,显著提升了长时序操作任务的泛化能力。作者通过大量真实世界实验验证了方法在多种任务和机器人本体上的有效性、跨场景的泛化性,以及在抗干扰、避障和未见杂乱场景等难以采集真实数据的场景下的适用性。

核心创新点如下:

◆ 提出任务中心的示范编辑视角,突破了以往仅做物体姿态或尺度等局部变换的局限,能够合成更丰富的场景-技能-物体组合。

◆ 将任务解耦为场景、技能、物体三个独立组件并支持灵活重组,这种结构化分解为可扩展的示范生成提供了新思路。

◆ 构建了Task-Edit示范生成框架,显著提升3D视觉运动策略在长时序复杂操作任务中的数据效率与泛化性能。

◆ 使模型能够处理真实世界中难以采集数据的复杂场景,包括抗干扰、动态避障以及未见过的杂乱环境。

◆ 在多种真实世界任务和不同机器人本体上验证了方法的通用性,展现出良好的跨平台适配能力。</td></tr>
<tr><td>2026-06-04</td><td>AIS-Based Vessel Trajectory Prediction Using Memory-Augmented Neural Networks<br><a href='http://arxiv.org/pdf/2606.06311'>论文</a></td><td>船舶轨迹预测对海事安全和效率至关重要。本文的核心贡献是首次实证验证了记忆增强神经网络在基于AIS数据的船舶轨迹预测中的显著优势。
◆将原本应用于行人和车辆轨迹预测的记忆增强神经网络创新性地引入船舶轨迹预测，填补了该技术在海事领域的应用空白。
◆利用外部记忆模块选择性检索相关信息，有效增强了模型对复杂船舶运动模式的捕捉与预测能力。
◆在墨西哥湾和纽约湾的真实AIS数据集上进行广泛实验，证明了该方法相比未使用外部记忆的深度学习基线模型具有一致且显著的性能提升。</td></tr>
<tr><td>2026-06-04</td><td>Preparing for the Next Carrington: Spatiotemporal Agent-Based Modeling for Safeguarding Satellite Infrastructure Under Extreme Space Weather Disturbances<br><a href='http://arxiv.org/pdf/2606.05732'>论文</a></td><td>本论文针对极端空间天气(如卡灵顿级太阳风暴)对卫星基础设施的潜在威胁,构建了一种新颖的时空智能体建模框架,用于预测灾害影响并为卫星提供实时机动指导。研究基于41,644条卫星记录、5次近期空间天气事件的历史数据及大气密度模型,模拟了具有物理驱动行为的独立卫星智能体决策过程。情景分析显示,低地球轨道95%的卫星将面临8倍基线水平的大气阻力增强,碰撞风险提升2-3倍,单颗受影响卫星的直接经济损失约为4000万美元,而模型机动建议准确率达92%。该研究首次为抵御下一次卡灵顿级灾难提供了实时自适应决策系统的原型框架。

核心贡献和创新点如下:

◆ 首次将时空智能体建模(ABM)方法应用于极端空间天气下的卫星基础设施安全研究,突破了以往仅依赖统计群体模型的局限,实现对单颗卫星个体行为的精细化模拟。

◆ 构建了具有物理驱动行为的卫星智能体,能够根据推进剂约束和碰撞规避阈值动态做出独立决策,真实反映卫星在灾害情境下的自适应响应。

◆ 整合了41,644条真实卫星数据、5次历史空间天气事件记录和大气密度模型,通过蒙特卡洛模拟量化了灾害的物理影响与经济损失,为风险评估提供了定量依据。

◆ 提出了具备92%准确率的实时机动推荐机制,首创性地为卫星运营商提供应对卡灵顿级事件的实时自适应决策原型系统,具有重要的工程与战略价值。</td></tr>
<tr><td>2026-06-03</td><td>DiffSlack: Learning under Nonlinear Inequality Constraints via Learnable Slack Variables<br><a href='http://arxiv.org/pdf/2606.05247'>论文</a></td><td>本文提出了一种名为DiffSlack的可微投影层，旨在解决神经网络中非线性不等式约束执行困难的问题。
◆通过引入可学习的松弛变量将不等式转化为等式，将其作为增强网络输出进行预测，为阻尼高斯-牛顿投影提供数据驱动的热启动。
◆设计投影层将原始预测映射到增强可行流形上，同时保持端到端的可微性。
◆提出两阶段课程学习策略，进一步稳定训练过程并提升约束满足能力。
在包含两百个非线性约束的车辆路径规划实验中，DiffSlack在同等推理预算下实现了更高的规划成功率和约束满足度。
消融实验表明硬投影层降低了对监督质量的敏感性，且闭环与实车实验证实了该方法的可执行性与实用价值。</td></tr>
<tr><td>2026-06-03</td><td>MAD: Mapping-Aware World Models for Agile Quadrotor Flight<br><a href='http://arxiv.org/pdf/2606.04534'>论文</a></td><td>论文核心贡献总结:

本文提出了Mapping-Aware Dreamer(MAD),一种面向视觉四旋翼飞行的几何感知世界模型。该方法摒弃了传统世界模型以原始图像重建作为自监督目标的做法,转而利用循环潜在动力学重建机器人中心的占用栅格图、可见性栅格图以及本体感知状态,从而使潜在表征直接编码局部几何、可见性历史和自运动信息。MAD在DiffAero仿真平台中训练,并支持三种策略学习模式(MAD-Dreamer想象式训练以及基于PPO和SHAC的特征提取器变体),最终在仿真中达到9.66 m/s、真实森林环境中达到5.05 m/s的飞行速度。

◆ 提出以占用栅格与可见性栅格重建替代原始图像重建作为世界模型的自监督目标,使潜在状态显式编码避障所需的几何与可见性信息。
◆ 设计了GPU并行的地图构建模块,在DiffAero中提供高吞吐的占用与可见性监督信号,解决了大规模训练的数据效率问题。
◆ 将学习到的几何感知表征灵活应用于想象式策略学习(MAD-Dreamer)和作为PPO、SHAC的特征提取器三种模式,展示了表征的通用性。
◆ 在视觉导航与竞速任务中相较纯视觉基线实现了更高成功率、更快速度以及更好的跨任务迁移能力,并产出可解释的地图预测与精准的自运动估计。
◆ 在配备Intel RealSense D435i的真实四旋翼上完成室内外部署,验证了该方法作为模块化导航与端到端学习之间实用折中方案的可行性。</td></tr>
<tr><td>2026-06-03</td><td>AgenticRL: Self-Refining Agentic Reinforcement Learning for Vision-Conditioned UAV Navigation<br><a href='http://arxiv.org/pdf/2606.03963'>论文</a></td><td>本文提出AgenticRL框架，解决了无人机导航中强化学习严重依赖人工奖励设计与微调的痛点，实现了奖励生成、策略优化和真实部署的自主化。
◆提出基于多模态GPT智能体的闭环自优化奖励设计机制，由智能体自动生成奖励、评估训练策略并诊断失败模式，从而自我完善奖励函数。
◆引入推理阶段的智能策略调度机制，利用多模态智能体融合真实图像与自然语言自动识别当前场景，动态选择最匹配的策略执行。
实验表明该闭环优化过程使策略表现较初始奖励提升了71%。
框架还成功实现了仿真到现实的迁移，真实世界成功率达91%，虚实迁移准确率达94%。</td></tr>
<tr><td>2026-06-02</td><td>RSC: Decentralized Rigid Formation Flocking for Large-Scale Swarms via Hybrid Predictive Control and Online Reconfiguration<br><a href='http://arxiv.org/pdf/2606.04248'>论文</a></td><td>本文针对分散式刚性编队集群在杂乱环境中易陷入局部最小值死锁、控制振荡及避障灵活性差等问题，提出了大规模群体分散式控制框架RSC。
◆提出混合控制架构，将有限时域轨迹预测与响应式人工势场安全控制器相结合，通过长期规划逃离局部最小值并确保短期安全。
◆引入基于稳定角色交换的在线领航-跟随重构机制，在穿越障碍后加速编队重聚且不中断任务执行。
在25架无人机的挑战性环境测试中，该框架可靠地统一了刚性编队保持、避障与目标追踪。
在无碰撞且最大相对边长误差低于10%的严格标准下，RSC成功率达83%，显著优于成功率不足5%的现有基线方法。</td></tr>
<tr><td>2026-06-02</td><td>Distribution-Free Risk-Aware Planning and Control Under Uncertainty Using Conformal Spectral Risk Control<br><a href='http://arxiv.org/pdf/2606.04185'>论文</a></td><td>动态不确定环境下的安全导航常依赖对真实不确定性分布的准确估计，但有限数据往往导致分布假设错误从而引发危险决策。本文提出了一种结合预测集的风险感知模型预测控制框架，无需假设底层不确定性分布即可保证风险低于用户设定阈值。
◆将共形风险控制扩展至一般谱风险度量，开发了无分布的风险量化框架来生成预测集。
◆证明将预测集引入控制框架，即使不确定性设定错误也能在谱风险约束满足方面提供统计安全性保证。
仿真实验验证了该框架在车辆避障场景中的有效性，相比基线方法显著提升了安全性并缩短了求解时间。</td></tr>
<tr><td>2026-06-02</td><td>Throughput Optimization for Multi-AP IEEE P802.11bq Networks Based on Combinatorial Multi-Armed Bandits<br><a href='http://arxiv.org/pdf/2606.03528'>论文</a></td><td>本文致力于解决密集多AP IEEE P802.11bq网络的分布式吞吐量优化问题。
◆构建了全新的包级模型，联合刻画了跨链路CSMA/CA、RTS/CTS交换、波束训练开销、定向毫米波干扰、基于SINR的MCS选择及重传机制。
◆将网络配置问题创新性地建模为多组组合多臂老虎机，使每个AP能从有限候选集中选择竞争窗口、CCA阈值、波束宽度和MCS预留裕量。
◆提出基于Hadamard引导可行探索的分组可行CSAR变体算法，通过估计经验排名分数高效淘汰各组内低效候选参数。
仿真表明，该方法较Thompson采样基线提升了吞吐量，且稳定时间缩短约49%。
研究还揭示了高吞吐量需平衡控制信道激进性、空间复用、波束成本与鲁棒性，而非单纯减少碰撞或最大化物理速率。</td></tr>
<tr><td>2026-05-31</td><td>Crazyflow: An Accurate, GPU-Accelerated, Differentiable Drone Simulator in JAX<br><a href='http://arxiv.org/pdf/2606.01478'>论文</a></td><td>本文提出了Crazyflow，一个基于JAX构建的GPU加速、高精度且可微的无人机仿真器，填补了现有仿真器无法统一支持保真度、可微性和集群模拟的空白。
◆实现了前所未有的仿真速度与并行规模，单机仿真比现有SOTA快超一个数量级，可同时模拟数千个含4000架无人机的集群。
◆同时兼顾了高精度与可微性，支持基于解析梯度的策略学习，在无需域随机化的情况下实现了亚厘米级的轨迹跟踪精度。
◆打破了传统先训练后部署的范式，凭借极高的仿真速度实现了飞行中在线强化学习，仅用0.38秒即可从零训练出无人机空中恢复策略并成功稳定。
◆具备出色的兼容性与易用性，直接兼容开源Crazyflie模型，并提供轻量级系统辨识流程，支持多级仿真抽象及跨平台快速重构。</td></tr>
<tr><td>2026-05-31</td><td>Time-Optimal Collision Avoidance Via a Greedy Polynomial Backward Sweep<br><a href='http://arxiv.org/pdf/2606.01169'>论文</a></td><td>本文针对低推力卫星碰撞规避问题，提出了一种贪婪时间最优反向扫描方法，用于求解确保安全的最晚机动启动时间。
◆该方法采用反向迭代传播策略，从名义最近接近时间起向后传播，每步贪婪选择局部最小化危险度量的推力方向。
◆引入微分代数技术高效传播状态敏感度，实现了最近接近时间的在线动态更新。
研究采用错过距离和碰撞概率作为安全度量，在大量交会数据集上对方法进行了验证。
实验表明该方法准确度高，与最优控制基准相比仅有极小的最优性损失。
其运算时间短，非常适合航天器星载环境的实时计算与实现。</td></tr>
<tr><td>2026-05-31</td><td>Tether-Aware Dynamic Collision Avoidance for USV-HROV Systems<br><a href='http://arxiv.org/pdf/2606.01112'>论文</a></td><td>本文针对无人水面艇跟踪混合遥控潜水器时面临的水下系绳易剐蹭且避障易致系绳绷紧的挑战，提出了一种系绳感知的动态避障方法。
◆引入了系绳安全感知平面域，在无需显式系绳形状模型的情况下，表征系绳与障碍船只之间的三维碰撞风险。
◆开发了系绳绷紧感知速度障碍方法，在实现安全避障的同时降低系绳绷紧的可能性。
◆将该方法与视线导引法相整合，有效协调了HROV跟踪与动态避障任务。
仿真结果表明，该方法在无人艇执行规避机动时，能成功避让动态障碍船只并保障系绳安全。</td></tr>
<tr><td>2026-05-31</td><td>Robust Integrated Planning and Control for Quadrotors in Dynamic Environments via NMPC with CBF Penalties<br><a href='http://arxiv.org/pdf/2606.01038'>论文</a></td><td>本文提出了一种针对四旋翼无人机在动态环境下的鲁棒集成规划与控制新策略。
◆将控制障碍函数作为指数惩罚项嵌入非线性模型预测控制中，在严格输入约束下改善了可行性并确保平滑避障，同时提供权衡跟踪精度与避障激进度的调节参数。
◆引入高增益扰动观测器估计并补偿外部扰动，显著提升了系统的鲁棒性。
◆结合卡尔曼滤波实现计算高效的障碍物运动实时预测，使无人机能够规避动态障碍物。
◆这是首个经过硬件实验验证的NMPC与CBF结合的集成规划控制框架，对比实验证明了其在可行性安全性和鲁棒性上的显著优势。</td></tr>
<tr><td>2026-05-31</td><td>OSCAR: Obstacle Survival Curves for Adaptive Robot Navigation<br><a href='http://arxiv.org/pdf/2606.00990'>论文</a></td><td>本文提出OSCAR框架，解决移动机器人在已知路线图上遇到临时障碍物时等待与重规划之间的低效决策问题。
◆提出基于障碍物类别的生存建模方法，从在线经验中学习残余清障时间分布，并引入右删失观测处理未观察到清障就重规划的情况。
◆将生存模型集成到时变图规划器中，动态计算被阻塞边的耐心阈值，从而自适应地决定等待时间或选择替代路线。
◆框架支持在多个导航回合中持续更新清障时间估计，实现导航策略的在线进化与优化。
仿真与真实机器人实验表明，该方法在每类障碍物不到20次观测后即可收敛至接近真实分布的最优水平，显著优于启发式基线。</td></tr>
<tr><td>2026-05-30</td><td>DriveAnchor: Progressive Anchor-based Flow Learning for Autonomous Driving Planning<br><a href='http://arxiv.org/pdf/2606.00519'>论文</a></td><td>DriveAnchor提出了一个三阶段的自动驾驶规划框架，在可组合流水线中实现了行为多样性、可控性与安全性。
◆提出示范流预训练，用最远点采样构建的2398个轨迹形状词汇表替代非结构化高斯先验，从结构上保证行为多样性。
◆提出引导流后训练，联合训练能量场与流匹配，仅依据静态道路几何将锚点重定位至用户指定走廊，无需可微引导即可实现可控性且新预设无需重训练流匹配。
◆提出奖励精炼流微调，利用零阶强化学习对齐避撞目标，将单步流匹配的奖励优化简化为锚点空间的方向搜索，无需计算对数似然或ODE转SDE。
该方法在约两百万测试场景中将近距碰撞率降低89%，平均奖励提升32%且不损失模仿精度。
其推理速度达2.06毫秒，并通过实车测试证实了量产部署的实用性。</td></tr>
<tr><td>2026-05-29</td><td>BERS: Locally Optimal Continuous Algorithm for Maritime Weather Routing with Just-in-Time Arrival<br><a href='http://arxiv.org/pdf/2605.31533'>论文</a></td><td>该论文提出了一种名为BERS的气象航线优化框架，旨在解决动态风浪和障碍物约束下的准时到达航线规划问题。
◆提出了结合CMA-ES全局进化搜索与FMS局部变分细化的两阶段优化框架。
◆采用贝塞尔曲线参数化航线并进行密集路径采样，确保轨迹平滑且兼顾中段效应与可行性约束。
该方法在七项操作标准的基准测试中均匹配或超越已有基线，在复杂流场下保持鲁棒收敛。
真实海洋数据验证表明，仅航线优化即可降低23%至59%的推进能耗。
结合风辅助推进后总节能高达75%，证明了该框架在海事脱碳节能规划中的实用性与可扩展性。</td></tr>
<tr><td>2026-05-29</td><td>LiftNav: Path Planning via Semantic Lifting in TSDF-Guided Gaussian Splatting<br><a href='http://arxiv.org/pdf/2605.31376'>论文</a></td><td>本文提出了LiftNav框架，解决了传统TSDF缺乏语义与三维高斯泼溅几何偏软导致难以精确避障的矛盾。
◆构建基于TSDF+GS双地图的混合导航框架，兼顾了可靠的碰撞避障与物体级语义理解。
◆设计了结合YOLO检测与TSDF三维提升的实时流水线，无需密集三维嵌入即可实现灵活的语义导航。
◆引入了基于铰链损失的碰撞惩罚项，有效提升了B样条轨迹优化的平滑度与安全性。
实验表明，相较于最先进的辐射场基线，该方法实现了百分之百的轨迹可行率且路径更短。</td></tr>
<tr><td>2026-05-29</td><td>Simulation of collision avoidance behavior in crowd movement by data-driven approach<br><a href='http://arxiv.org/pdf/2605.31210'>论文</a></td><td>针对现有数据驱动人群模拟模型在双向和多向流中碰撞率过高的问题，本文提出了一种融合行人碰撞机制的新型数据驱动人群模拟模型CPGAN。
◆提出基于横向加速度的碰撞损失函数，将其融入生成对抗网络架构，显著降低了逆向行人碰撞率至与对照实验相当的水平。
◆提出基于Voronoi的运动特征提取方法，提升了模型对行人运动特征的捕捉能力。
实验表明，CPGAN在双向流场景中有效模拟了人群运动，成功重现了车道形成现象和N-t曲线。
本研究为将行人动力学机制整合到数据驱动人群模拟的损失函数中提供了重要启示。</td></tr>
<tr><td>2026-05-29</td><td>Trajectory Planning for Non-Communicating Mobile Robots using Inverse Optimal Control<br><a href='http://arxiv.org/pdf/2605.30906'>论文</a></td><td>本文核心贡献是提出了一种针对无通信移动机器人避碰场景的轨迹规划与预测结合算法。
◆基于逆最优控制，通过观察历史轨迹来估计所有机器人的未知目标状态。
◆每个机器人从他人视角出发，结合自我预测与估计的目标状态来求解联合预测问题。
◆将联合预测结果纳入自身的轨迹规划中进行考量，实现高效交互。
◆相比传统恒加速度估计方法，该方法使到达目标的时间中位数缩短9.8%，且求解器从未出现无法求解的情况，鲁棒性极高。</td></tr>
<tr><td>2026-05-29</td><td>GSAM: A Generalizable and Safe Robotic Framework for Articulated Object Manipulation<br><a href='http://arxiv.org/pdf/2605.30740'>论文</a></td><td>本文提出GSAM框架，旨在解决关节类物体操作中泛化能力有限和易发生破坏性碰撞的问题。
◆提出基于微调视觉语言模型的优化器，利用思维链常识推理修正视觉感知器的原始运动学参数估计。
◆设计交互约束函数生成器，结合物体与避障知识生成提示，由大语言模型将其函数化并应用于轨迹与姿态规划以防碰撞。
◆开发运动学感知操作规划器，以验证规划轨迹和姿态的可达性。
实验表明该框架将标准差降低了3.1%，操作成功率提升了36.0%，显著增强了实际场景中的物体泛化性与交互安全性。</td></tr>
<tr><td>2026-05-29</td><td>Geometry-Aware Control Barrier Functions for Collision Avoidance via Bernstein Polynomial Approximations<br><a href='http://arxiv.org/pdf/2605.30696'>论文</a></td><td>针对不规则几何形状机器人和障碍物的安全导航问题，传统控制障碍函数的形状代理往往过于保守或约束数量过多，影响实时性能。本文提出了一种基于伯恩斯坦多项式符号距离场的新型几何感知控制障碍函数。该研究的核心创新点如下：
◆提出统一表示方法，利用BP-SDFs统一表示障碍物和机器人，从而以统一的最小距离构建障碍函数，避免了多局部基元导致的约束膨胀。
◆实现闭环控制约束，利用伯恩斯坦多项式的可微特性，能够轻松地在闭环系统中强制执行控制约束，提升了算法实用性。
仿真实验在单机器人导航和异构多机器人避碰场景中验证了该方法的高效性与安全保障能力。</td></tr>
<tr><td>2026-05-29</td><td>Constrained Whole-Body Tracking for Humanoid Robots<br><a href='http://arxiv.org/pdf/2606.00374'>论文</a></td><td>这篇论文提出了ConstrainedMimic,一个面向人形机器人全身运动跟踪的实时约束执行控制框架,旨在解决强化学习策略在训练后难以满足新增安全约束的问题。该方法结合操作空间控制(OSC)与控制屏障函数(CBF)的思想,在RL跟踪策略之上施加运行时约束,既约束运动学参考也约束底层动力学,从而在保证安全的同时最小化对策略原有能力的限制。作者在仿真Unitree G1上完成了全身运动跟踪与遥操作实验,验证了自碰撞与外部障碍物避让、关节限位以及质心稳定性等多种约束的有效性。

◆ 提出ConstrainedMimic框架,首次将OSC与CBF原理统一融入RL全身跟踪策略,实现训练后可任意指定的运行时约束执行。
◆ 同时在运动学参考层和动力学执行层施加约束,使安全保障贯穿整个控制流程,而非仅修正最终动作。
◆ 通过保持与当前接触模式及跟踪目标的一致性,实现约束激活时对策略能力的最小侵入式干预。
◆ 方法完全可微,支持CPU、GPU和TPU多平台部署,运行频率可达300-500Hz,具备良好的实时性与可扩展性。
◆ 在统一框架下验证了自碰撞避让、外部障碍避让、关节限位与质心稳定等多类异构约束,展示了方法的通用性。</td></tr>
<tr><td>2026-05-29</td><td>GLENS: Global Search via Learning from Solver Iterates with Diffusion Models<br><a href='http://arxiv.org/pdf/2606.00366'>论文</a></td><td>本文针对多峰非凸连续优化问题,提出了一种名为GLENS(基于求解器迭代学习的全局搜索)的数据高效全局搜索方法,旨在生成大量高质量(求解器快速收敛)且多样化(覆盖多个局部最优)的初始猜测,以支持灵活的下游决策。该方法的核心思想是利用求解器在离线运行过程中产生的中间迭代点作为&quot;免费&quot;的数据增强,从而克服了现有方法仅使用最终收敛解、丢失局部邻域信息且训练数据有限的不足。实验在改进的非凸基准问题和双机器人避障导航问题上验证了方法的有效性,表明GLENS能在保持多峰分布多样性的同时显著加快求解器收敛速度,并在不同问题设置和求解器下均具有良好表现。

◆ 首次提出将求解器的中间迭代点而非仅最终收敛解作为训练数据,实现了&quot;免费&quot;的数据增强,显著提升了数据利用效率。

◆ 设计了邻域结构模型,利用扩散模型在问题参数条件下学习局部最优解周围的几何结构,从而保留了解的邻域分布信息。

◆ 提出了求解器行为模型,在扩散采样过程中学习并引入精化方向,引导样本进一步逼近附近的局部最优解。

◆ 将神经网络生成模型与传统数值求解器的迭代行为深度耦合,实现了高质量与多样性兼顾的全局初始猜测生成。

◆ 在非凸基准问题和实际双机器人避障导航场景中均验证了方法的通用性,并系统分析了关键超参数对性能的影响。</td></tr>
<tr><td>2026-05-28</td><td>Trust, Geometry, and Rules: A Credibility-Aware Reinforcement Learning Framework for Safe USV Navigation under Uncertainty<br><a href='http://arxiv.org/pdf/2605.26974'>论文</a></td><td>本文提出了一种融合可信度感知学习、几何安全屏蔽与连续规则嵌入的强化学习框架，解决了无人艇在感知不确定性下的安全合规导航难题。
◆提出可信度加权价值学习，利用滤波协方差与经验误差的差异推导动态信任因子，调节评论家损失以防止策略对噪声样本过拟合。
◆提出协方差膨胀速度障碍方法，将位置估计不确定性映射为角度边界，构建保守的几何屏蔽以覆盖危险的探索动作。
◆提出风险感知的避碰规则职责嵌入，将二元相遇职责松弛为连续的规则感知信号，提供平滑扇区转换并抑制稀疏奖励引起的振荡。
仿真实验表明该框架提升了对抗感知不一致的训练鲁棒性，在避碰与规则合规性上显著优于基线方法。</td></tr>
<tr><td>2026-05-28</td><td>Hybrid Digital and Analog Airy Beamforming for Near-Field Multi-User Communications<br><a href='http://arxiv.org/pdf/2605.29481'>论文</a></td><td>本文针对6G近场多用户通信中,高频聚焦波束因直线传播易受障碍物遮挡、导致频谱效率下降的问题,提出了一种基于Airy波束的混合数模波束赋形方案。该方案利用Airy波前的弯曲传播特性,使波束能够绕过障碍物并在用户处实现能量聚焦,同时通过分层波束训练和数模混合架构实现低复杂度的多用户接入与干扰抑制。仿真表明,在毫米波至太赫兹频段下,所提方案在波束方向图和频谱效率方面均优于传统聚焦波束赋形。

◆ 首次将Airy波束引入近场多用户通信,构建了兼具绕障传播与能量聚焦双重能力的近场Airy波前模型。
◆ 设计了分层Airy波束训练方法,可快速搜索能够绕过障碍物并与用户对齐的最优波束,无需获取完整信道状态信息。
◆ 提出了基于选定Airy波束配置模拟波束赋形器、再利用数字波束赋形器抑制用户间干扰的低复杂度混合架构。
◆ 解决了传统聚焦波束在多用户链路存在遮挡时频谱效率严重退化的瓶颈问题。
◆ 验证了该方案在毫米波至太赫兹宽频段下相较传统聚焦波束赋形的性能优势,拓展了近场通信的应用场景。</td></tr>
<tr><td>2026-05-27</td><td>EventShiftFlow: Towards Hardware-efficient FPGA-based Flow Estimation<br><a href='http://arxiv.org/pdf/2605.28312'>论文</a></td><td>本文提出了一种面向FPGA的流式速度估计器EventShiftFlow，旨在解决现有事件相机运动估计算法计算量大且难以硬件映射的问题。该方法将异步事件离散化为固定时长的时间窗并构建1位空间占用网格，通过并行评估多个速度假设来输出稀疏量化的速度估计。
◆提出纯整数逻辑的数据通路设计，仅使用移位寄存器、计数器、比较器和LUT映射的小型乘法器，无需浮点运算、除法器、DSP模块、帧重建和迭代优化。
◆在算法与硬件间进行针对性权衡，放弃稠密亚像素光流，换取每个活跃像素的稀疏量化速度估计，满足低延迟和资源受限平台的实时避障需求。
◆实现极低硬件开销的FPGA部署，数据通路存储需求小于2kB，并在低成本FPGA上完成原型验证，同时在真实数据集中达到了99.5%的方向准确率。</td></tr>
<tr><td>2026-05-26</td><td>Look Further: Socially-Compliant Navigation System in Residential Buildings<br><a href='http://arxiv.org/pdf/2605.26710'>论文</a></td><td>本文核心贡献在于证明了在住宅楼走廊环境中，将移动机器人对人的反应距离延长至八米以上能显著改善人类对机器人运动的感知。与关注短距离避让的传统社交导航方法不同，该研究通过远距离提前反应优化了人机交互体验。
◆提出主动换道运动模式，机器人在八米外识别到迎面而来的人时，便从走廊中心横向移动至侧边。
◆构建了利用该模式的导航系统，突破了典型交互距离限制，实现远距离的社会合规导航。
通过四十二名参与者的用户研究评估了安全、平滑和礼貌三个服务目标，结果表明在直走廊迎面场景下该系统显著优于传统模式，但在盲区转角场景中各方法无显著差异。</td></tr>
<tr><td>2026-05-25</td><td>Safety-Critical Whole-Body Control for Humanoid Robots via Input-to-State Safe Control Barrier Functions<br><a href='http://arxiv.org/pdf/2605.25546'>论文</a> | <a href='https://kwlee365.github.io/SafeWBC-Website/'>代码</a></td><td>本文针对人形机器人在未知干扰下运动学安全保证易降级的问题，提出了一种基于输入状态安全控制障碍函数的分层安全关键全身控制框架。
◆提出了结合运动学级全身控制器、ISSf-CBF安全滤波器和动力学级全身控制器的分层架构，实现从任务生成到动态执行的闭环安全控制。
◆引入输入状态安全控制障碍函数（ISSf-CBF），在有限未知干扰下对参考轨迹进行最小修改，确保运动学安全约束不被破坏。
◆通过保守调节ISSf-CBF参数，将基于全身运动学模型的安全保证成功转移到全阶动力学模型中，保障了动态可行性与接触稳定性。
仿真与真实机器人实验表明，该框架在模型失配下能提升安全裕度，并在运动、遥操作等任务中实时可靠地满足多重安全约束。</td></tr>
<tr><td>2026-05-24</td><td>Communication-Constrained Energy-Optimal Trajectory Generation for Quadrotor UAVs in Urban Environments<br><a href='http://arxiv.org/pdf/2605.24865'>论文</a></td><td>本文针对城市环境中的四旋翼无人机，提出了一个通信受限的能量最优轨迹生成框架。
◆将全刚体飞行动力学、城市无线通信模型、累积数据吞吐量约束与避障要求统一纳入自由终点时间的最优控制框架。
◆突破了基于简化运动学或质点模型的传统方法局限，生成了适用于实际无人机平台的动力学可行轨迹。
◆采用序列凸规划迭代求解通信与飞行动力学高度耦合的非凸最优控制问题，使系统能根据数据中继需求自适应调整任务时长。
该研究有效平衡了能量消耗与通信质量，为密集城市中需要可靠通信的自主无人机作业提供了实用的解决方案。</td></tr>
<tr><td>2026-05-23</td><td>A Reinforcement Learning Inspired Latent Yield Based Adaptive Algorithm Switching Mechanism<br><a href='http://arxiv.org/pdf/2605.24436'>论文</a></td><td>针对动态环境中仅依赖瞬时性能指标导致算法切换过于反应性且不稳定的问题，本文提出了一种基于潜在收益的自适应算法切换机制。该方法通过计算高效的方式跨多个问题实例聚合算法性能，对实例特征的剧烈变动具有极强的免疫力。
◆受强化学习启发，将奖惩信息封装为潜在收益，通过该收益触发探索与利用机制，从而实现自适应的算法切换。
◆受遗传算法启发，引入岛屿模型，以促进局部算法种群间的并行探索与性能交换。
在排序算法和机器人避障任务上的实验充分验证了该方法的可行性与有效性，展现了其在需要自适应算法选择领域的重要应用潜力。</td></tr>
<tr><td>2026-05-22</td><td>On the Performance of DCF in Full Duplex WLANs with Hidden Terminals<br><a href='http://arxiv.org/pdf/2605.23276'>论文</a></td><td>本文研究了在存在隐藏终端的全双工无线局域网中分布式协调功能机制的吞吐量性能。虽然全双工技术理论上能提升系统吞吐量，但其实际运行需要MAC层允许两个节点同时接入共享介质，而标准DCF机制恰恰是为避免这种并发而设计的。作者基于性能建模，深入对比分析了CSMA/CA协议在隐藏终端场景下全双工与半双工的表现差异。
◆构建了结合隐藏终端与全双工通信特征的CSMA/CA协议性能分析模型。
◆揭示了在现有DCF机制约束下，全双工技术的饱和吞吐量相比半双工仅有极微小提升，指出了传统MAC避免并发的逻辑与全双工需求存在的冲突。</td></tr>
<tr><td>2026-05-21</td><td>Superhuman Safe and Agile Racing through Multi-Agent Reinforcement Learning<br><a href='http://arxiv.org/pdf/2605.22748'>论文</a></td><td>本文证明了多智能体强化学习能为真实世界交互提供关键的安全支撑，打破了传统单智能体范式将其他主体视作环境噪声的局限。
◆提出基于联赛自博弈的多智能体强化学习框架，训练智能体在高速无人机竞速中应对复杂的空气动力学交互与战略机动。
◆智能体涌现出主动避撞、超车及处理气动下洗等高级预期行为，在超22米每秒的竞速中击败人类冠军，且碰撞率较单智能体基线降低50%。
◆通过与多样化的人工智能体共同训练，实现了向更安全的人机交互场景的零样本泛化。
这些成果表明，实现机器人在现实中的稳健共存不应依赖孤立的安全约束，而是源于多智能体交互的严格考验。</td></tr>
<tr><td>2026-05-21</td><td>N3P: Accelerated Automated Parking via a Learning-Based Naturalistic Three-Stage Scheme<br><a href='http://arxiv.org/pdf/2605.22722'>论文</a></td><td>本文提出了N3P，一个基于学习的快速三阶段自动泊车框架，旨在解决传统Hybrid A*计算昂贵以及强化学习方法缺乏可靠性和轨迹次优的问题。
◆提出三阶段分解机制，通过引入中间准备姿态将复杂的泊车操作简化为更易求解的子问题。
◆引入学习模块来预测该中间准备姿态，有效降低了计算复杂度并加速了路径生成。
◆显著提升规划效率，结合Hybrid A*算法后使泊车规划速度提升超过80%。
◆相比强化学习基线，在成功率、轨迹长度和换挡次数等指标上均表现更优，且规划时间相当或更短。</td></tr>
<tr><td>2026-05-21</td><td>Perceived Safety of Workers in Encounters with Large Industrial AGVs<br><a href='http://arxiv.org/pdf/2605.22461'>论文</a></td><td>本文研究了工人在共享空间中与大型工业自动导引车相遇时的感知安全问题，填补了现有研究空白。
◆聚焦大型载荷AGV，并以真实产业工人而非学生作为实验参与者，克服了既往研究的对象局限。
◆对比了真实场景与虚拟现实环境，发现VR中感知威胁略高但偏好一致，验证了VR实验结果的可转移性。
◆创新性地结合手持压敏触发器与问卷进行评估，并让工人自主设定避撞参数以反映真实偏好。
研究最终得出1.5至2米是工人在预设和自定义轨迹下均最偏好的安全通过距离。</td></tr>
<tr><td>2026-05-20</td><td>Safe and Steerable Geometric Motion Policies for Robotic Dexterous Manipulation<br><a href='http://arxiv.org/pdf/2605.21811'>论文</a></td><td>本文提出了安全拉回丛动力系统框架，用于解决机器人灵巧操作中异构几何空间目标与约束的协调问题，能够从任意任务流形上的目标与安全需求计算出最优且安全可证的构型流形加速度。
◆提出拉回控制障碍函数构造方法，将任务流形的安全条件转化为构型流形加速度上的线性约束。
◆设计了任务流形动作接口，允许高级策略注入低维残差运动以引导探索，且在任意输入下均能保证安全性，零输入则恢复自主行为。
实验在23自由度灵巧手平台上验证了该框架，在20种物体的灵巧抓取任务中取得了92.5%的成功率。
该方法还通过一维动作接口实现94.4%的三指抓取成功率，并首次实现了基于模型的全驱动掌下物体重定向，支持双向超过360度的偏航旋转。</td></tr>
<tr><td>2026-05-20</td><td>Flying Together: Human-Guided Immersive Shared Control for Aerial Robot Teams in Unknown Environments<br><a href='http://arxiv.org/pdf/2605.21680'>论文</a></td><td>本文提出了一种基于虚拟现实的无人机集群共享控制框架，旨在解决多机器人在非结构化环境中难以适应突发状况和捕捉操作员目标的问题。
◆提出了一种基于运动原语的用户引导规划器，可在持续融合操作员输入的同时计算连续且无碰撞的轨迹。
◆将上述规划器与导纳控制器相结合，使操作员能灵活影响集群行为并引导无人机前往自主规划易忽略的兴趣区域。
◆开发了双通道VR交互界面，支持物理与模拟无人机混合编队，允许操作员通过迁移点引导集群并获取即时视觉反馈。
实验表明，该沉浸式人机协同导航方法不仅提升了避障能力和机间间距保持效果，还显著降低了操作员的工作负荷。</td></tr>
<tr><td>2026-05-20</td><td>Design for Manufacturing: A Manufacturability Knowledge-Integrated Reinforcement Learning Framework for Free-Form Pipe Routing in Aeroengines<br><a href='http://arxiv.org/pdf/2605.20644'>论文</a></td><td>本文提出FPRO框架，将制造知识融入强化学习，解决航空发动机管路设计与制造脱节导致反复试错的问题。
◆将布线问题转化为Frenet坐标系下的边值问题，用曲率和挠率轮廓表示管路路径。
◆将领域制造知识作为曲率和挠率的约束条件嵌入设计中，实现设计与制造的有效集成。
◆采用含阶段引导奖励机制的近端策略优化算法进行路径寻优，并将路径直接映射为六轴自由弯曲机的运动轨迹。
实验表明该方法能生成更平滑且可制造的管路，收敛更快，并在真实制造中验证了其实用性。</td></tr>
<tr><td>2026-05-20</td><td>Time-To-Reach Separation and Safety Filtering for Safe, Fair, and Efficient Multi-Agent Coordination<br><a href='http://arxiv.org/pdf/2605.20625'>论文</a></td><td>本文针对高密度城市空域的多飞行器协调问题，提出了一种基于最小到达时间的多智能体协调框架。
◆创新点在于将最小到达时间作为统一度量，用于优先级分配、时间分离和安全过滤，并基于此分配到达一致的优先级。
◆创新点在于通过目标到达时间值强制执行时间间隔，从而转化为飞行器间的安全空间分离。
◆创新点在于构建了基于汉密尔顿-雅可比可达性值函数的优先级一致安全过滤层，在保证避碰的同时最小化修改参考引导指令。
仿真结果表明，该方法在拥堵走廊汇入场景下，相比传统时间最优引导和优先级无关安全过滤方法，有效提升了系统的安全性、公平性与效率。</td></tr>
<tr><td>2026-05-20</td><td>Intent-First Aerial V2V for Tactical Coordination and Separation: Protocol and Performance Under Density and Disturbance<br><a href='http://arxiv.org/pdf/2605.20595'>论文</a></td><td>本文针对密集低空飞行作业，提出了首个与控制器耦合的全空中意图优先车联网战术邻区交换协议栈。
◆不同于仅感知广播，该协议结合了刷新的状态与意图信标，实现本地感知、协同感知及降级模式评估。
◆引入事件触发消息机制，用于避让、排序、释放和应急协调等战术交互。
◆采用具有认证新鲜度检查的直通链路级C-V2X模块实现全空中V2V栈，确保信息的实时与可信。
实验表明该栈能减少过时信息分歧、保持可观测性并抑制虚假推断，在低中密度下提供可行通信层，高复杂度下转为防御性回退，是受干扰城市空域扩展战术协调的有界赋能者。</td></tr>
<tr><td>2026-05-19</td><td>D-CLING: Prior-Preserving Depth-Conditioned Fine-Tuning for Navigation Foundation Models<br><a href='http://arxiv.org/pdf/2605.19690'>论文</a> | <a href='https://toyotafrc.github.io/DCLING-Proj/'>代码</a></td><td>本文提出了D-CLING微调方法，旨在解决导航基础模型微调时预训练先验被侵蚀及避障失效的问题。该方法让模型在新场景中高效学习的同时，保持预训练的泛化能力以实现鲁棒的长期导航。
◆受ControlNet启发，附加预训练骨干的可训练副本并采用零初始化残差路径连接，使模型高效学习域内几何线索。
◆在获取新环境几何信息的同时，有效保留模型原有的各种预训练行为知识，防止微调破坏先验。
◆实验证明该方法显著减少了真实导航中的碰撞与人工干预，并在微调数据集外维持或提升了动作预测能力，为持续学习提供了重要见解。</td></tr>
<tr><td>2026-05-19</td><td>Hamilton--Jacobi Reachability for Spacecraft Collision Avoidance<br><a href='http://arxiv.org/pdf/2605.20138'>论文</a></td><td>本文提出了一个基于哈密顿-雅可比可达性的同圆轨道双星避碰框架。
该框架使用平面HCW动力学建模，并依据FCC标准定义了不安全的相对构型。
◆将航天器交互创新性地建模为控制卫星与有界对抗干扰间的零和微分博弈，以应对未知意图。
◆通过计算后向可达集，精确刻画了最坏干扰下无法避免碰撞的相对状态。
◆证明了后向可达集外的状态容许可证明的无碰撞轨迹，确保了安全性。
◆将可达集与监督混合控制逻辑集成，确定规避机动的触发时机，提供了数学上可靠的安全保证。</td></tr>
<tr><td>2026-05-18</td><td>ManiSoft: Towards Vision-Language Manipulation for Soft Continuum Robotics<br><a href='http://arxiv.org/pdf/2605.18617'>论文</a> | <a href='https://buaa-colalab.github.io/ManiSoft'>代码</a></td><td>本文提出了ManiSoft，一个针对软体连续体机器人的视觉语言操作基准，旨在解决软体臂本体感知不可靠和分布式驱动带来的挑战。
◆提出了一种定制仿真器，通过弹性力约束将逼真的软体动力学与丰富接触交互相结合。
◆定义了四个展示可变形控制不同方面的任务，并构建了自动化流程生成6300个多样化场景及专家轨迹。
◆采用分层方法大规模生成高质量轨迹，即高级规划器分解任务为路径点，低级强化学习策略生成力矩命令进行追踪。
基准测试表明现有模型在随机化下性能显著下降，主要归因于视觉本体感知估计不准及未充分利用软体可变形性避障。
该基准为弥合刚性臂与软体臂在视觉语言操作领域的鸿沟提供了宝贵测试平台。</td></tr>
<tr><td>2026-05-18</td><td>Adversarial Stress Testing of SPARK Humanoid Safety Filters<br><a href='http://arxiv.org/pdf/2605.19009'>论文</a></td><td>本文研究了SPARK人形机器人安全滤波器的鲁棒性，指出现有基准评分无法全面揭示其在严苛环境下的真实安全行为。
◆在MuJoCo中复现了SPARK基准用例，并在受控随机种子下系统评估了六种主流安全滤波方法。
◆构建了专用的后处理流程，将原始运行日志转化为目标跟踪、最小距离和碰撞步数等可量化的核心指标。
◆引入对抗性压力测试，揭示了障碍物拥挤、距离估计噪声及信息延迟等极端条件对安全行为的显著影响。
实验表明不同方法在目标跟踪与碰撞规避上存在权衡，强调人形机器人部署前必须超越标称性能，采用能暴露故障模式的指标进行严格评估。</td></tr>
<tr><td>2026-05-18</td><td>The distance-based formation controller design for multi-agent systems in port-Hamiltonian form<br><a href='http://arxiv.org/pdf/2605.18502'>论文</a></td><td>本文针对端口哈密顿多智能体系统，研究了基于距离的编队控制与防碰撞集成问题，提出了一种统一控制器同时实现速度跟踪、目标编队获取及智能体间安全。
◆构造了具有满列秩性质的符号关联矩阵，其对应有向无环图，为控制器设计奠定基础。
◆引入仅吸引势场设计，有效克服了传统人工势场中普遍存在的局部极小值问题。
◆结合安全屏障机制，在无排斥势场的情况下严格保障了防碰撞约束。
闭环系统稳定性由LaSalle不变集原理保证，数值仿真验证了该策略的有效性。</td></tr>
<tr><td>2026-05-18</td><td>Assessing Localization Technologies for Pedestrian Collision Avoidance<br><a href='http://arxiv.org/pdf/2605.18295'>论文</a></td><td>本文核心贡献是评估了超宽带和蓝牙6.0技术在行人防碰撞预警系统中的定位精度，并将其与全球导航卫星系统进行了性能基准测试。实验重点考察了这两种技术在关键指标上的表现，包括定位精度和对环境条件的鲁棒性。
◆创新性地将超宽带和蓝牙6.0应用于车辆行人碰撞预警系统，发挥其高精度测距与低延迟通信优势。
◆在多种环境条件下，对上述技术与传统全球导航卫星系统开展了定位性能的基准对比评估。
◆证实上述技术可作为传统系统的可行替代或补充方案，有效提升态势感知能力并实现及时的行人预警。</td></tr>
<tr><td>2026-05-15</td><td>Constrained MPC-Based Motion Planning for Morphing Quadrotors in Ultra-Narrow Passages under Limited Perception<br><a href='http://arxiv.org/pdf/2605.15999'>论文</a> | <a href='https://github.com/harshjmodi1996/morphocopter_mpc}{Github'>代码</a></td><td>本文提出了一个针对变形四旋翼在极受限环境和有限感知条件下的形态与轨迹运动规划框架。
◆提出了一种用于非线性模型预测控制的平滑指数障碍物代价函数，克服了传统人工势场在狭窄通道中代价过高而阻断路径的问题，在保持强避碰能力的同时维持低遍历代价。
◆该公式避免了硬激活阈值，并引入了代价降低因子，有效降低了狭窄通道内部的通行代价。
◆将二维激光雷达测量数据直接应用于模型预测控制中，实现了对任意形状障碍物的导航规避。
该方法嵌入基于acados的非线性模型预测控制框架，不仅适用于变形四旋翼，也广泛适用于其他移动机器人。
仿真与实验结果验证了该计算高效且实用的方案能成功穿越典型排斥代价函数失效的狭窄走廊。</td></tr>
<tr><td>2026-05-15</td><td>PCASim: Promptable Closed-loop Adversarial Simulation for Urban Traffic Environment<br><a href='http://arxiv.org/pdf/2605.15654'>论文</a> | <a href='https://zhenhaooo.github.io/PCASim.github.io/'>代码</a></td><td>本文提出了PCASim框架，旨在解决城市自动驾驶闭环测试中对抗场景生成与安全智能体训练难以协同进化的挑战。
◆构建了基于规则过滤开源数据集的对抗行为知识库，并结合了适配仿真环境的知识检索模块。
◆利用大语言模型融合知识驱动、数据驱动和对抗驱动方法，生成符合用户定制需求的安全关键交通场景。
◆采用强化学习模型训练各类车辆行为，在保持真实性的同时显著提升了仿真场景的多样性。
实验表明，该框架将领域语言生成准确率提升了12%，新场景转换成功率提高了8%，且避障能力增强了30%。</td></tr>
<tr><td>2026-05-13</td><td>HCSG: Human-Centric Semantic-Geometric Reasoning for Vision-Language Navigation<br><a href='http://arxiv.org/pdf/2605.13321'>论文</a> | <a href='https://haoxuanxu1024.github.io/HCSG/'>代码</a></td><td>本文提出 HCSG，首个面向视觉‑语言导航的人类中心框架，旨在动态室内环境中实现安全、社交智能的导航。  
◆ 统一的人类理解模块融合几何预测与基于视觉‑语言模型的语义解释。  
◆ 将语义‑几何融合表示嵌入拓扑地图，实现指令条件的规划。  
◆ 引入社交距离损失约束，确保交互距离符合社会规范。  
◆ 在 HA‑VLNCE 基准上实现成功率提升 14%、碰撞率降低 34% 的显著改进。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='navigation'>Navigation (75篇)</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-06-15</td><td>VISTA: Scale-Aware Visual Navigation via Action History Conditioning<br><a href='http://arxiv.org/pdf/2606.17294'>论文</a></td><td>◆ VISTA针对视觉导航基础模型中“归一化动作”带来的尺度部署脆弱性，指出相同归一化轨迹在不同缩放因子下会改变真实运动几何并增加碰撞风险。
◆ 论文提出将归一化动作历史与图像观测共同作为条件输入，使模型显式理解预测动作与机器人实际位移之间的尺度关系。
◆ 该方法提升了跨机器人、跨环境部署时的尺度感知能力，从而增强零样本导航的稳定性和安全性。
◆ 为解决视觉重复、缺乏显著特征场景中的感知困难，VISTA集成DINOv3编码器以获得更丰富的空间与几何表征。
◆ 实验表明，VISTA在室外、森林和办公室等真实未见环境中实现100%零样本目标预测准确率，并平均通过95%的检查点，展现出强泛化和路径跟随能力。</td></tr>
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
<tr><td>2026-06-13</td><td>GuideWalk: Learning Unified Autonomous Navigation and Locomotion for Humanoid Robots across Versatile Terrains<br><a href='http://arxiv.org/pdf/2606.10449'>论文</a></td><td>本文提出了GuideWalk，一个统一的端到端框架，将可穿越性感知的导航引导与地形自适应运动教师相结合，以解决人形机器人在复杂地形上难以协调避障与动态可行运动的导航挑战。
◆提出一种提供显式速度引导的导航模块，将避障与地形条件解耦，从而实现跨多样环境的鲁棒规划。
◆设计了复合教师蒸馏方案，将目标导向指令和动态一致动作聚合并蒸馏至单一策略中。
◆结合强化学习和辅助行为克隆目标对蒸馏策略进行优化，在促进探索的同时保留了教师的优秀行为，进一步提升了鲁棒性。
实验证明，GuideWalk能够在保持人形机器人稳定运动的同时，实现有效且稳健的导航。</td></tr>
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
<tr><td>2026-06-10</td><td>MB-Loc: Multi-planar Bird&#x27;s-eye-view Localization in outdoor LiDAR scenes<br><a href='http://arxiv.org/pdf/2606.08744'>论文</a></td><td>本文提出了MB-Loc框架，解决了现有场景坐标回归方法计算效率低且对视角变化敏感的问题。
◆提出2.5D多平面鸟瞰图表示法，将点云沿Z轴切片并映射带符号深度至2D平面，在保留3D几何的同时利用2D卷积提升计算效率。
◆引入KL正则化潜在瓶颈模块，显式建模空间不确定性且不引入随机噪声，有效应对室外LiDAR的稀疏性。
◆在平面投影前应用3D空间增强策略，迫使网络隐式学习视角不变特征，显著提升旋转鲁棒性。
实验表明该方法在NCLT数据集上达到最优，且以实时推理速度实现了比传统3D架构更高的计算效率。</td></tr>
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
<tr><td>2026-06-09</td><td>MARCH: Model-Assisted Reinforcement Learning for the Perceptive Control of Humanoids over Sparse Footholds<br><a href='http://arxiv.org/pdf/2606.10288'>论文</a></td><td>本文提出了一种模型辅助的强化学习框架MARCH，旨在解决人形机器人在稀疏落脚点上感知行走的难题，有效结合了基于模型方法的精确性与无模型方法的鲁棒性。
◆利用简化模型生成安全参考轨迹，为安全关键的约束运动提供基础引导。
◆构建基于控制李雅普诺夫函数的奖励机制，以此引导特权教师策略的训练，确保运动的安全与精确。
◆将特权教师策略蒸馏为基于视觉的学生策略，实现从感知输入到动作控制的端到端部署。
该框架不仅提高了样本效率并减少了对复杂学习课程的依赖，还能生成更平滑的步态并在踏脚石任务上达到与无模型基线相当的精度。
该方法在仿真和实物中均得到验证，成功实现了Unitree G1人形机器人在带横向约束的稀疏落脚点上的安全导航。</td></tr>
<tr><td>2026-06-08</td><td>QuadVerse: An Integrated Framework Aligning Visual-Physical Reality for Quadruped Simulation<br><a href='http://arxiv.org/pdf/2606.07118'>论文</a></td><td>QuadVerse 是一个面向四足机器人仿真的集成框架,旨在解决仿真到现实(sim-to-real)迁移中视觉与动力学差距相互耦合、累积传播的问题。该框架以重建场景作为统一的校准基底,将视觉感知、物理交互与执行器动力学三方面对齐,从而显著缩小仿真与真实环境的差距。实验证明,QuadVerse 在重建质量与运动跟踪精度上均优于相关基线方法,并可在无需任务级真实环境采样的情况下,实现零样本视觉导航策略的稳健部署。

核心贡献与创新点如下:

◆ 提出 QuadVerse 集成框架,首次将视觉、接触物理与执行器动力学三类 sim-to-real 差距统一在同一校准基底上对齐,避免了传统方法分别处理所导致的误差累积与耦合问题。

◆ 基于 RGB 视频构建几何约束的 3D 高斯泼溅(3DGS)场景,既支持批量化的高真实感第一视角渲染,又可提取带语义的可碰撞网格,实现&quot;视觉渲染&quot;与&quot;物理仿真&quot;的双重可用性。

◆ 提出基于语义网格的接触校准方法:利用空间可变摩擦先验进行初始化,再通过轨迹后验搜索进行精细化优化,实现地形接触参数的精准建模。

◆ 设计残差动力学补偿器,在已完成接触校准的地形上回放真实轨迹进行训练,有效解耦地形接触误差与执行器非理想特性,使补偿更具针对性。

◆ 在上述基础上实现了无需任务级真实采样的零样本视觉导航策略部署,验证了该框架在真实机器人任务中的实用性与泛化能力。</td></tr>
<tr><td>2026-06-08</td><td>Efficient Minimal Solvers for Relative Pose Estimation in Autonomous Driving Applications<br><a href='http://arxiv.org/pdf/2606.09569'>论文</a></td><td>本文针对自动驾驶中相对位姿估计计算成本高且依赖大量特征匹配的局限，提出了一种基于新型平移参数化和一阶旋转近似的高效统一框架。
◆提出结合惯性测量单元垂直方向先验的高效最小求解器。
◆提出利用转向时旋转轴方向先验的高效最小求解器。
◆提出针对地面车辆平面运动假设的高效最小求解器。
这些方法通过减少所需的最小点对应数量并降低代数复杂度，显著加速了RANSAC流程中的假设生成。
实验证明，与现有算法相比，所提求解器在速度和精度间取得了更优的平衡，高度适用于实时自动驾驶系统。</td></tr>
<tr><td>2026-06-08</td><td>Virtual-point-based Solutions to Handle Generalized Absolute Pose Problem<br><a href='http://arxiv.org/pdf/2606.09294'>论文</a></td><td>针对现有PnP求解器无法处理多相机系统多投影中心的问题，本文提出了一种基于虚拟点的公式化方法。
◆创新地构建虚拟点公式，搭建了标准PnP与广义位姿问题之间的桥梁，提出可将现有PnP求解器转化为广义位姿求解器的统一流程。
◆基于该框架推导出三种虚拟点广义位姿求解器，即基于Cayley参数化的VGPc、四元数参数化的VGPq和旋转矩阵参数化的VGPr。
◆提出的求解器继承了原PnP算法的精度与效率并显著优于现有广义求解器，其中VGPc在异方差噪声下精度更高，VGPq保持全局最优，VGPr具备卓越计算效率且精度无损。
这项工作为多相机广义绝对位姿估计提供了统一且高性能的解决方案。</td></tr>
<tr><td>2026-06-08</td><td>VGP-Nav: Metric-Aware Visual Geometric Perception for Robot Navigation<br><a href='http://arxiv.org/pdf/2606.09268'>论文</a></td><td>本文提出了VGP-Nav框架，仅依赖单目RGB输入即可同时实现机器人的全局定位与度量一致的障碍物感知。
◆将基于定位的视觉几何锚定到由地平面几何推导出的物理尺度约束上，为单目感知提供了可靠的度量参考。
◆在线解决单目尺度歧义问题，生成可直接用于下游规划的基于定位的度量障碍物表示。
该方法避免了多传感器融合带来的复杂标定与高部署成本，克服了传统单目视觉系统无法兼顾全局定位与度量感知的缺陷。
广泛实验证明该框架在多种环境中具有强泛化能力，并在真实移动机器人上成功部署，实现了低成本且安全的自主导航。</td></tr>
<tr><td>2026-06-08</td><td>A Geometric Framework for Absolute Pose and Velocity Estimation with Event Cameras<br><a href='http://arxiv.org/pdf/2606.09139'>论文</a> | <a href='https://github.com/Zibin6/EventPoseVelocity'>代码</a></td><td>针对事件相机绝对位姿与速度同时估计的难题，本文提出了一种基于场景3D直线及其触发事件的几何框架。
◆提出了两个核心几何约束：3D直线与其对应事件平面法向量的正交性，以及事件与其关联直线2D投影的共线性。
◆针对绝对位姿估计，设计了高效的线性求解器和提供旋转全局最优解的多项式求解器。
◆针对速度估计，开发了兼顾效率的线性求解器和提升精度的基于优化的求解器，以恢复角速度和线速度。
该方法仅需最少三个事件与直线的对应关系即可独立确定6自由度绝对位姿或速度。
实验表明该方法实现了目前最优性能，在精度和计算效率上均显著优于现有方法。</td></tr>
<tr><td>2026-06-08</td><td>Bayesian Optimization for Learning Nonlinear MPC in Autonomous Agent Navigation<br><a href='http://arxiv.org/pdf/2606.14763'>论文</a></td><td>◆提出一种无地图自主导航框架，将基于LiDAR的高斯占据表示、滚动时域A*反应式规划与非线性MPC紧密结合，实现动态未知环境中的实时避障与轨迹跟踪。
◆在MPC中引入平滑sigmoid障碍物屏障，并通过CasADi/IPOPT求解，提高了碰撞约束处理的连续性与控制可实现性。
◆采用基于TPE的离线贝叶斯优化，自动寻找对导航综合目标近优的控制器参数，缓解MPC参数敏感问题。
◆利用高斯过程代理模型分析参数敏感性和优化景观，为参数选择提供可解释性。
◆该方法具有机器人无关性，并在Unitree Go2仿真和实机上验证，显示仿真调参可有效迁移到硬件，部署成功率最高达90.0%，仿真指标平均提升38.9%。</td></tr>
<tr><td>2026-06-04</td><td>Towards Realistic 3D Sonar Simulation<br><a href='http://arxiv.org/pdf/2606.06130'>论文</a></td><td>现有三维声纳仿真通常依赖几何驱动渲染，将其视为水下激光雷达，忽略了折射和多径干涉等基本声学现象。
◆提出一种结合GPU加速图形引擎与物理声学传播原理的模块化真实三维声纳仿真架构。
◆在NVIDIA Isaac Sim中实现了基于Water Linked 3D-15的体积三维声纳模型并集成到水下仿真框架中。
◆通过硬件在环配置验证系统，在Jetson Orin Nano上运行改进的FastLIO2融合多源合成数据。
最后通过与真实港口检测数据的对比，刻画了仿真与现实的差距，并为全声学驱动的体积感知指明了路线图。</td></tr>
<tr><td>2026-06-04</td><td>LongSpace: Exploring Long-Horizon Spatial Memory from Perception to Recall in Video<br><a href='http://arxiv.org/pdf/2606.05677'>论文</a></td><td>针对现有多模态大语言模型在长视距任务中缺乏对先前空间布局和视角变化等空间记忆进行检索与回忆的能力，本文进行了深入研究。
◆提出LongSpace-Bench基准，这是一个基于房间漫游视频的长视距空间记忆评测数据集，全面覆盖场景感知、空间关系和空间记忆三大维度。
◆提出LongSpace记忆框架，将长视频建模为序列块进行处理，突破了长视频空间推理的瓶颈。
◆在解码器早期层引入3D结构线索，增强了模型对底层空间结构的感知与建模能力。
◆构建层感知记忆机制，实现了问题引导下的精准空间信息检索与召回。
实验表明该框架显著提升了长视频空间理解能力，证明了显式空间记忆是长视距视频模型的关键能力。</td></tr>
<tr><td>2026-06-03</td><td>WAM-Nav: Asymmetric Latent World-Action Modeling for Unified Visual Navigation<br><a href='http://arxiv.org/pdf/2606.04907'>论文</a></td><td>本文提出WAM-Nav，一种用于具身视觉导航的潜在世界-动作模型，通过联合学习动作生成与潜在视觉预见，解决了现有反应式策略缺乏前瞻性和模块化方法易产生误差累积的问题。
◆采用共享扩散Transformer进行非对称联合扩散，同时生成长视界动作与短视界视觉预见，有效降低了多步自回归带来的推理延迟与视觉误差累积。
◆引入双流上下文条件机制，将片段级自运动历史与序列视觉观察相融合，促使生成更加平滑且一致的导航轨迹。
◆设计统一目标对齐模块，保持不同目标类型的平衡表征，使单一策略即可同时支持图像目标、点目标及无目标探索任务。
实验证实该模型泛化性优异，图像目标与点目标导航成功率分别提升15.7%和3.3%，并在真实场景中实现了85%的零样本迁移成功率。</td></tr>
<tr><td>2026-06-03</td><td>Recent Advances and Trends in Learning-based 3D Representations<br><a href='http://arxiv.org/pdf/2606.04871'>论文</a></td><td>本文系统综述了基于学习的三维表示方法，涵盖从传统离散显式格式到新兴连续隐式场及基元泼溅的演进。论文详细阐述了各类表示的公式变体、优缺点及关键应用，并总结了开放挑战与未来方向。与广泛讨论三维重建的综述不同，本文核心贡献在于聚焦表示本身的演进。
◆聚焦三维表示自身的演进过程，而非宽泛地讨论三维物体与场景重建。
◆着重强调向隐式表示和基于基元的表示的范式转变。
◆提供新兴三维格式如何从根本上改变三维与四维工作流的新颖视角。</td></tr>
<tr><td>2026-06-03</td><td>MineXplore: An Open-Source Reinforcement Learning Exploration Benchmark for GNSS-Denied Underground Environment<br><a href='http://arxiv.org/pdf/2606.04569'>论文</a></td><td>本文提出了MineXplore，首个基于真实生产矿山几何结构且兼容GPU加速的开源强化学习探索基准，解决了地下无GNSS环境下缺乏高保真仿真平台的问题。
◆提出六阶段轮廓到MJCF的转换流程，构建了超十万平方米的隧道网络，并引入八边形截面、激光雷达锯齿墙壁、多摩擦区、全局倾斜和周期性光照等真实矿井特征。
◆通过高达0.9538的交并比和79.4%的六维表面纹理相似度，严格验证了环境重建的高几何与视觉保真度。
◆基于RLlib的单智能体PPO基线实现了88.89%的最佳滚动覆盖率，证实该基准能支持在真实地下感知与拓扑约束下进行稳定且可复现的策略学习。
MineXplore填补了开源生态系统的空白，为极端地下环境下的自主导航研究提供了标准化的测试平台。</td></tr>
<tr><td>2026-06-03</td><td>MAD: Mapping-Aware World Models for Agile Quadrotor Flight<br><a href='http://arxiv.org/pdf/2606.04534'>论文</a></td><td>本文提出了MAD，一种用于敏捷四旋翼飞行的建图感知世界模型，解决了传统纯反应式方法在杂乱场景中面临的部分可视和高延迟问题。
◆摒弃原始图像重建，通过学习循环潜在动力学来重建以机器人为中心的占据栅格图、可视栅格图及本体感受状态，强制潜在状态编码与避障直接相关的局部几何和可视历史。
◆在DiffAero框架中利用GPU并行建图模块进行训练，为占据和可视状态提供高吞吐量的监督信号。
基于该模型的智能体在导航和竞速任务中实现了更高的成功率和更快的飞行速度，展现出优越的跨任务迁移能力，并能生成可解释的地图预测和精准的自运动估计。
策略成功部署于实体四旋翼，在有限感知下实现安全飞行，仿真与真实森林实验最高速度分别达9.66m/s和5.05m/s。
这项工作证明了建图感知世界模型在模块化导航与端到端学习之间提供了实用的折中方案。</td></tr>
<tr><td>2026-06-03</td><td>Uncertainty-Aware Adaptive Sensor Fusion for Autonomous Navigation<br><a href='http://arxiv.org/pdf/2606.05437'>论文</a></td><td>本文提出一种结合混合深度学习与无迹卡尔曼滤波的方法，以提升视觉惯性里程计在自主导航中的姿态估计精度。该模型采用视觉Transformer网络提取IMU数据的时间依赖性，并利用多尺度卷积神经网络学习视觉数据的光流运动线索。
◆提出自适应传感器融合模块，通过利用估计的不确定性对视觉和惯性特征进行动态加权，增强了复杂环境下的鲁棒性。
◆设计新颖的不确定性感知损失函数，将预测不确定性显式融入学习过程，有效应对噪声或不完整的传感器输入。
在KITTI数据集上的评估表明该方法在绝对轨迹与相对位姿误差上显著超越基线，且在A100上达155帧每秒的高效处理速度，极适于资源受限系统。</td></tr>
<tr><td>2026-06-02</td><td>Autonomous Navigation System for Library Service Robot Based on Unitree Go2 Edu<br><a href='http://arxiv.org/pdf/2606.03340'>论文</a></td><td>本文提出了一种基于Unitree Go2 Edu四足机器人的ROS 2自主导航系统，专为图书馆狭窄过道和动态环境设计。该系统集成了4D激光雷达、深度相机和IMU，并融合了RTAB-Map视觉激光SLAM、AMCL与EKF定位以及基于Nav2的A*和DWA规划算法。
◆突破传统将图书馆视为崎岖地形的假设，专注解决实际部署中的移动不连续性问题，如地面过渡、临时杂物和部分受阻通道，克服了低底盘轮式平台的局限。
◆构建了针对四足机器人的多传感器融合与完整导航堆栈，实现了复杂室内场景下的精准建图、定位与动态避障。
◆在真实图书馆中进行了严格验证，系统在静态、低密度动态和高密度动态场景下的导航成功率分别达到100%、96%和88%，且建图平均误差仅为3.7厘米，证明了其高效性与准确性。</td></tr>
<tr><td>2026-06-01</td><td>Adversarial Dual On-Policy Distillation from Expressive Teacher<br><a href='http://arxiv.org/pdf/2605.27095'>论文</a> | <a href='https://github.com/vanzll/FA-OPD'>代码</a></td><td>针对现有具身控制模仿学习方法仅依赖离线专家数据而缺乏在线纠正信号，且标准在线策略蒸馏无法适用于仅有演示场景的问题，本文提出了FA-OPD方法。该方法从演示中学习流匹配教师并与轻量级MLP学生共同训练，在学生交互过程中提供双通道互补信号。
◆设计奖励通道，通过学习状态-动作对的专家相似性目标来驱动长视野策略优化，促进在线探索。
◆设计动作通道，在学生实际访问的状态上提供密集的局部目标，稳定策略的利用。
◆将双通道巧妙耦合，使奖励蒸馏能够泛化超越逐点演示，同时动作蒸馏将探索锚定在类专家行为附近。
实验表明，在六个机器人导航、操作和运动基准测试中，FA-OPD超越了强基线，并在噪声或有限演示条件下展现出显著增强的鲁棒性。</td></tr>
<tr><td>2026-06-01</td><td>Co-training with Ego-centric Video and Demonstration for Robot Navigation Task<br><a href='http://arxiv.org/pdf/2606.01951'>论文</a></td><td>现有的视觉语言动作模型依赖昂贵的真实机器人数据，且将第一人称人类视频应用于移动机器人导航面临视角变化的挑战。本文提出了一种将第一人称行走视频转换为移动机器人模仿学习数据集的框架。
◆该方法通过估计人类视频中的相机运动，将其转换为与地面移动机器人兼容的动作表示。
◆通过联合训练人类衍生数据与机器人收集数据，克服了单一数据源的局限，提升了模型的语言理解与动作生成鲁棒性。
实验验证了第一人称人类视频作为移动机器人学习有效且可扩展数据源的潜力。</td></tr>
<tr><td>2026-06-01</td><td>Adversarial Attacks on Robot Localization Systems via Deep Feature Perturbation<br><a href='http://arxiv.org/pdf/2606.01892'>论文</a></td><td>本文研究了基于深度学习的机器人定位系统面对对抗攻击的脆弱性，提出了一种针对视觉定位中乘积量化的对抗查询生成框架。
◆提出轻量级乘积量化网络（LPQN）来扰动查询特征编码，误导检索过程返回语义无关的数据库条目。
◆设计了前向与反向两阶段生成程序，前向传播扰动特征分布，反向传播通过优化细化扰动。
◆LPQN的轻量化设计能够在极小的计算开销下，生成细微却高效的对抗性扰动。
大量受控与真实机器人环境实验证明，该方法显著降低了定位系统性能，暴露了实际应用中的关键安全漏洞。</td></tr>
<tr><td>2026-06-01</td><td>PlatonicNav: Unveiling Semantic Correspondence in Navigation with Platonic Topological Maps<br><a href='http://arxiv.org/pdf/2606.01788'>论文</a> | <a href='https://github.com/AIGeeksGroup/PlatonicNav'>代码</a></td><td>本文将柏拉图表示假设扩展至具身导航领域，把纯视觉对象导航、跨模态对象导航和视觉语言导航统一为同一对象中心语义流形的三种接口，提出了免训练的PlatonicNav框架。该框架通过构建柏拉图拓扑图并融合几何与语义节点距离，在仿真基准和实体机器人上验证了其无需显式跨模态训练即可跨任务、跨模态与跨实体泛化的能力。
◆提出免训练框架PlatonicNav，构建柏拉图拓扑图，融合自监督视觉编码器中的几何与语义节点距离。
◆利用盲匹配机制实现语言目标对齐，无需任何配对的视觉-语言数据或显式跨模态监督。
◆验证了独立训练的视觉与语言编码器共享通用语义结构，揭示了纯视觉建图即可实现语言对齐的潜力。</td></tr>
<tr><td>2026-06-01</td><td>Embedding Semantic Risk into Distance Fields and CBFs for Online Monocular Safe Control<br><a href='http://arxiv.org/pdf/2606.01605'>论文</a></td><td>本文提出了一个在线单目感知到控制框架，将语义风险直接嵌入到控制障碍函数所使用的欧几里得符号距离场中，实现了语义感知的安全导航与遥操作。
◆提出将语义信息直接编码到ESDF中，在控制优化前融合语义风险，使高风险物体在安全场中产生更大的空间影响。
◆结合基础模型SLAM前端与逐帧语义分割，从单目RGB视频在线重建并融合具有像素级类别标签的密集3D几何结构。
◆在ESDF计算前施加依赖类别的膨胀，并通过依赖类别的增益进一步调节CBF控制器的响应，改变了以往仅在下游调整控制器的方式。
实验表明该框架能以10至20赫兹的频率在线运行，并在遥操作和自主导航中成功展现出语义感知的安全行为。</td></tr>
<tr><td>2026-06-01</td><td>Hierarchical Object Representation for Spatial Robot Perception: Points, Meshes, and Superquadrics<br><a href='http://arxiv.org/pdf/2606.01545'>论文</a> | <a href='https://github.com/perceptica-robotics/Hickory'>代码</a></td><td>本文提出了一种用于空间机器人感知的层次化物体表示方法，解决了现有三维场景图中物体几何表示过于简化的问题。该表示方法能够支持高保真物体重建、鲁棒重定位与安全导航规划。
◆设计了四层渐进式抽象的几何表示结构，从原始传感器数据逐步过渡到密集三维网格，最终提炼为超二次曲面解析基元，实现了稀疏且解析的几何表达。
◆开发了直接从机器人RGB-D图像流构建该层次化表示的完整处理流程，验证了其在室内外开放集物体场景中的有效性。
◆提出基于超二次曲面的地图对齐方法，在多种数据集上的表现超越了当前最先进方法ROMAN，并实现了密集环境下高效且解析的碰撞检查。</td></tr>
<tr><td>2026-05-31</td><td>DeepIPCv3: Event-Aware Multi-Modal Sensor Fusion for Sudden Pedestrian Crossing Avoidance<br><a href='http://arxiv.org/pdf/2606.01277'>论文</a> | <a href='https://github.com/oskarnatan/DeepIPCv3'>代码</a></td><td>本文提出了DeepIPCv3多模态自动驾驶框架，旨在解决传统帧传感器在突发行人穿越场景下存在的感知延迟和运动模糊问题。
◆提出受Transformer启发的跨模态注意力机制，动态关联激光雷达的稠密三维空间几何与动态视觉传感器的微秒级异步事件流，在保留场景结构感知的同时优先处理高速动态更新。
◆设计混合策略网络，将启发式轨迹跟踪与直接神经预测相结合，把融合后的潜表征精准映射为安全局部航点和可执行控制命令。
◆构建涵盖正午和夜间挑战性条件的自定义多模态数据集进行严格离线评估，证明该融合方式能消除曝光失效与运动模糊，取得最低的轨迹和控制命令误差。
该框架不受环境光照影响，能够实现高度敏捷且数学上有界的规避机动，相关代码即将开源。</td></tr>
<tr><td>2026-05-31</td><td>OSCAR: Obstacle Survival Curves for Adaptive Robot Navigation<br><a href='http://arxiv.org/pdf/2606.00990'>论文</a></td><td>该论文提出了OSCAR框架，解决移动机器人在图导航中遇到临时障碍物时等待与绕行决策效率低下的问题。传统方法通常采用固定规则，忽略了不同类型障碍物持续时间的差异。
◆引入生存建模方法，利用在线经验学习基于障碍物类别的剩余清除时间分布，并创新性地处理了机器人提前绕行时产生的右删失观测数据。
◆将生存模型集成到时间相关的图规划器中，为每个被阻塞的边动态计算耐心阈值，智能平衡等待与绕行的时间成本。
◆框架具备持续更新能力，能够跨导航回合不断优化清除时间估计。实验表明，该方法在仿真中不到20次观测即可收敛至接近真实分布的Oracle水平，真实部署也验证了其在线学习与自适应优化的有效性。</td></tr>
<tr><td>2026-05-30</td><td>BEVIO: Efficient Bird&#x27;s-Eye-View based Sparse-Update Visual-Inertial Odometry for Lunar Day-Night Navigation<br><a href='http://arxiv.org/pdf/2606.00709'>论文</a></td><td>针对月球车在极端资源限制下视觉更新稀疏以及昼夜自照明导致特征关联困难的问题，本文提出了BEVIO算法。
◆提出基于鸟瞰图的图像匹配方案，增强了对较大帧间运动的鲁棒性。
◆在视觉外观发生显著变化时，依然能实现可靠的特征匹配，克服了昼夜及自照明环境的挑战。
通过高保真月面仿真和半比例月球车真实长时昼夜部署实验进行了广泛评估。
结果表明，该方法在视觉更新率低至0.25赫兹时仍能实现可靠的昼夜导航，非常适合算力与功耗受限的月球车。</td></tr>
<tr><td>2026-05-29</td><td>Collaborative Navigation and Exploration with $β$-Sparse Gaussian Processes<br><a href='http://arxiv.org/pdf/2605.26304'>论文</a></td><td>针对未知环境下异构机器人协同导航面临传感、通信和计算限制的问题，本文提出了一种领航机器人与移动传感器机器人的协同导航框架。该框架使传感器能在带宽受限的情况下，在线联合选择传输的地图点与导航动作，并预测未探索区域。
◆提出β-稀疏高斯过程模型，这是一种用于任务感知诱导点选择的新颖且鲁棒的变分稀疏高斯过程模型。
◆开发了一种动作选择策略，有效平衡了任务相关性与环境探索。
仿真实验表明，该框架相比无通信场景可减少18%的路径成本，相比原始数据传输基线可减少76%的信息传输量。</td></tr>
<tr><td>2026-05-29</td><td>Replicable Simulation-Based Robot Validation through Provenance<br><a href='http://arxiv.org/pdf/2605.29973'>论文</a></td><td>该论文针对基于仿真的机器人测试可复现性不足的问题，提出将数据溯源与FAIR原则相结合以提升测试文档的透明度。
◆提出将数据溯源与FAIR原则深度融合，通过追踪产物关联和添加关于文件来源与设计决策的机器可读元数据来保障验证的可复现性。
◆强调溯源与元数据不应作为最终数据集的事后补充，而必须内嵌于生成数据集的测试流程中，从而实现测试证据的端到端重建。
论文通过扩展现有仿真测试框架引入溯源跟踪与元数据收集机制，成功对移动机器人导航数据集进行了结构化溯源与FAIR元数据的丰富。
最后，论文总结了集成过程中遇到的词汇对齐、属性选择与领域标准采用等障碍，并为在机器人验证工作流中实施以溯源为中心的FAIR元数据提供了可操作建议。</td></tr>
<tr><td>2026-05-29</td><td>AR Forcing: Towards Long-Horizon Robot Navigation World Model<br><a href='http://arxiv.org/pdf/2605.31314'>论文</a></td><td>本文针对基于扩散的机器人导航世界模型中训练与推理存在的分布偏移导致长程预测不稳定的问题，提出了AR Forcing自回归训练策略。
◆将标准扩散损失整合到自回归训练循环中，消除了并行监督与自回归推理之间的不一致。
◆模型每一步利用自身预测更新上下文并优化单步噪声预测目标，使训练显式暴露于推理状态分布。
◆无需引入额外判别器或分布匹配损失，保留了原始扩散框架与采样器，易于集成。
实验表明，该方法在多域导航数据集上显著提升了长程导航的图像生成一致性与轨迹预测精度，增强了模型在复杂环境下的鲁棒性。</td></tr>
<tr><td>2026-05-29</td><td>Geometry-Aware Control Barrier Functions for Collision Avoidance via Bernstein Polynomial Approximations<br><a href='http://arxiv.org/pdf/2605.30696'>论文</a></td><td>针对具有不规则几何形状机器人和障碍物的安全导航问题，传统控制障碍函数的形状代理往往过于保守或导致约束数激增。本文提出了一种基于伯恩斯坦多项式符号距离场的几何感知控制障碍函数。
◆提出基于BP-SDF的统一表示方法，将障碍物与机器人统一建模，并以统一的最小距离来表示障碍函数。
◆利用伯恩斯坦多项式的可微性，可以轻松地以闭环方式强制执行控制约束。
仿真结果表明，该方法在单机器人导航和异构多机器人避碰场景中均能高效保障安全。</td></tr>
<tr><td>2026-05-29</td><td>Predicted-Flow Control Barrier Functions for Real-Time Safe Optimal Control<br><a href='http://arxiv.org/pdf/2606.00297'>论文</a></td><td>该论文针对传统控制屏障函数(CBF)难以构造且具有短视性的问题,提出了预测流控制屏障函数(P-CBF)框架,将CBF从当前状态的函数推广为有限预测时域内参数化控制规划下预测流的泛函,使安全保证覆盖整个预测时域,并通过单一凸优化(在多面体约束下退化为二次规划)统一了有限时域积分代价优化与安全认证,所提出的FlowBarrier算法在非完整地面机器人密集环境导航实验中相比非线性MPC和两种CBF安全滤波方法实现了最高目标到达率、零安全违例和最低计算耗时。

◆ 提出预测流控制屏障函数(P-CBF)概念,将传统基于当前状态的CBF推广为基于参数化控制规划下预测流的泛函,克服了CBF的短视性缺陷。

◆ 引入终端候选P-CBF机制,要求预测流在终端时刻进入备份安全集,从而解决了控制约束下P-CBF有效性难以保证的问题。

◆ 创新性地提出规划时移(planning-time shift)概念,通过调节预测时域长度提供额外自由度,确保优化问题的可行性。

◆ 实时控制量、控制规划参数与规划时移由单一凸优化联合求解,保证可行性并使关联安全集前向不变,在多面体控制约束下可简化为QP问题。

◆ 实现了有限时域积分代价优化与全时域安全认证的统一框架,并通过FlowBarrier算法在100次实验中验证了其在到达率、安全性和计算效率上的全面优势。</td></tr>
<tr><td>2026-05-28</td><td>Trust, Geometry, and Rules: A Credibility-Aware Reinforcement Learning Framework for Safe USV Navigation under Uncertainty<br><a href='http://arxiv.org/pdf/2605.26974'>论文</a></td><td>本文针对无人水面艇在感知不确定性下安全且符合COLREGs规则的导航难题，提出了一种融合感知可信学习、几何安全屏蔽与连续规则感知嵌入的强化学习框架。
◆可信度加权价值学习通过滤波协方差与经验误差的差异推导动态信任因子，调节评论家异方差损失，防止策略对噪声过拟合。
◆协方差膨胀速度障碍将位置估计不确定性映射为角度裕度，构建保守的几何屏蔽以覆盖危险探索动作。
◆风险感知的COLREGs责任嵌入将二元相遇责任松弛为连续规则信号，提供平滑扇区转换信息并抑制稀疏奖励引起的振荡。
仿真实验表明，该框架能有效提升应对感知不一致的训练鲁棒性，并在避碰与规则合规性上显著优于基线方法。</td></tr>
<tr><td>2026-05-28</td><td>Fisher-Preserving Guidance: Training-Free Manifold Constraints for Safe Diffusion Control<br><a href='http://arxiv.org/pdf/2605.29937'>论文</a></td><td>本文针对扩散模型在视觉导航中因更新偏离训练流形而导致轨迹不可靠的问题，提出了一种无需训练的推理方法。
◆提出基于外积跨度投影的费雪保持引导机制，在优化任务目标的同时避免离分布动作引起的费雪漂移，确保更新不偏离流形。
◆利用低秩雅可比分解计算费雪保持更新，每步仅需单次反向传播，满足实时应用要求。
◆引入截断费雪去噪敏感度作为不确定性信号，以此实现鲁棒的多样本动作混合策略。
实验表明，该方法在多种仿真和真实机器人导航任务中，无需额外训练即可显著优于强扩散策略基线。</td></tr>
<tr><td>2026-05-28</td><td>How to Relieve Distribution Shifts in Semantic Segmentation for Off-Road Environments<br><a href='http://arxiv.org/pdf/2605.29599'>论文</a></td><td>本文针对越野环境语义分割中由域差异和传感器损坏引起的分布偏移问题，提出了ST-Seg框架。该框架通过显式扩展源分布来提升分割的鲁棒性和越野导航的安全性。
◆提出风格扩展方法，通过生成多样化的逼真风格拓宽域覆盖范围，有效增强源域有限的风格信息。
◆引入纹理正则化技术，利用深度纹理流形稳定受风格增强学习影响的局部纹理表示。
◆打破以往在固定源分布内隐式泛化的局限，提供了一种直观且显式扩展源分布以应对分布偏移的新思路。
实验证明该框架在多种分布偏移的目标域上均显著优于现有方法。</td></tr>
<tr><td>2026-05-28</td><td>GUITestScape: Towards Open-set Evaluation on Exploratory GUI Testing<br><a href='http://arxiv.org/pdf/2605.29532'>论文</a></td><td>当前探索性GUI测试评估存在两大不足，即仅关注交互缺陷而忽视显示缺陷，且评估受限于预定义标注而无法区分不同的失效模式。
◆提出交互式基准GUITestScape，涵盖61个真实安卓应用及508个交互与显示类型的预设缺陷，弥补了现有基准的缺陷类型局限。
◆引入开放集评估器GUIJudge，将智能体的测试轨迹分解为独立可诊断的能力，实现了超越预定义标注的过程感知评估。
实验表明，GUIJudge大幅优于所有基线，提供了可靠的评估结果。
此外，基准测试揭示了现有模型在两类缺陷上的检测瓶颈，且将GUIJudge的验证器集成至现有智能体中无需重训即可显著提升其检测性能。</td></tr>
<tr><td>2026-05-28</td><td>Learning-Based Navigation for Indoor Mobile Robots<br><a href='http://arxiv.org/pdf/2605.30468'>论文</a> | <a href='https://ntdathp.github.io/rl_robot_web/'>代码</a></td><td>该论文提出了一种面向室内移动机器人的学习式导航框架,将全局规划与局部控制相结合,通过监督学习训练全局路径规划器,并采用行为克隆与强化学习相结合的方式优化局部规划器。该方法在仿真与真实室内环境中均得到验证,能够生成可行的全局路径并输出安全可靠的运动指令,实现避障与目标导向的自主导航,展示了学习式全局规划与强化学习精调局部控制相结合的有效性。

核心贡献与创新点如下:

◆ 提出了一种端到端的学习式室内导航框架,将神经网络全局规划器与学习式局部规划器有机整合,实现从路径生成到运动控制的统一学习方案。

◆ 设计了基于代价感知A*专家轨迹监督训练的神经全局规划器,使网络在模仿专家的同时学习到代价信息,从而生成更优的全局路径。

◆ 提出了Learning-Based DWA局部规划器,将传统动态窗口法的连续控制问题转化为在DWA动作格上的离散候选选择问题,既保留了DWA的可行性优势又引入了学习能力。

◆ 采用两阶段训练策略,先通过行为克隆获得初始策略,再使用带可行性掩码的PPO进行强化学习精调,提升了训练稳定性与最终性能。

◆ 引入可行性感知掩码机制,在强化学习过程中过滤不安全或不可行动作,保障了学习过程与执行阶段的安全性。

◆ 在仿真与真实室内环境中均完成了系统部署与验证,并开源代码,体现了方法的实用性与可复现性。</td></tr>
<tr><td>2026-05-27</td><td>Chance-Constrained MPPI under State and Dynamic Object Prediction Uncertainty and the Evaluation of Collision Risk Calibration<br><a href='http://arxiv.org/pdf/2605.28330'>论文</a></td><td>现有机会约束MPPI控制隐式假设上游定位与感知不确定性已良好标定，但实际估计器常标定不当，导致过度自信引发安全违规或缺乏自信引发保守冻结。
◆提出一种严谨的评估方法，应用严格评分规则来评估闭环执行期间预测碰撞风险的统计有效性。
◆提出双不确定性机会约束管MPPI实时风险感知规划架构，通过单管无迹变换近似联合整合定位不确定性，并利用蒙特卡洛聚合整合动态障碍物预测不确定性。
在高度杂乱环境中，该框架实现了稳健的失效缓解，能安全过渡至保守机动而不陷入死锁。
其导航成功率较基线提升近28%，且旅行时间最短、社会作用力最小，证明可靠的概率安全性需要整个技术栈具备统计有效的不确定性估计。</td></tr>
<tr><td>2026-05-27</td><td>STR Robot: Design of an Autonomous Mobile Robot from Simulation to Reality<br><a href='http://arxiv.org/pdf/2605.28110'>论文</a> | <a href='https://ntdathp.github.io/outdoor-robot-web'>代码</a></td><td>本文核心贡献是实现了基于现有机械平台的自主移动机器人从仿真到现实的完整部署。研究未聚焦机械设计，而是重点开发了机载控制、自定位与自主导航系统。
◆创新性地将机载感知与计算相结合，实现了无需外部辅助的机器人位姿估计与自主导航。
◆验证了一套仿真优先的开发框架，即先在仿真中构建与测试整体系统，再成功部署至真实机器人，证明了仿真是开发可靠系统的有效基础。
项目代码即将开源，为相关研究提供了可复用的资源。</td></tr>
<tr><td>2026-05-27</td><td>Ontology-Guided Reasoning for Affordance-Based Explanations of Robot Navigation<br><a href='http://arxiv.org/pdf/2606.00117'>论文</a></td><td>本文提出了一种基于本体引导推理的机器人导航可供性解释方法，使机器人在路线受阻时能推理环境物体的可供性与状态变化以寻找安全通过方式。
◆构建局部可供性本体，对附近实体、可供性、可供性状态及定性空间关系进行统一的结构化表示。
◆提出假设评估机制，通过评估假设的对象与可供性状态变化作为候选解释因子，生成语义基础扎实且具有可操作性的解释。
◆突破传统局限，将可供性本体从单纯的环境语义描述提升为支持可解释性与可靠自主性的推理基础。
在图书管理员机器人场景的测试中，该方法比纯语义基线更准确地识别解释因子，并在语义杂乱增加时保持强鲁棒性。</td></tr>
<tr><td>2026-05-26</td><td>Orion: Enabling Self-adaptive Memory Management for On-device Online Continual Learning<br><a href='http://arxiv.org/pdf/2605.26473'>论文</a></td><td>本文提出了Orion框架，旨在严格内存约束下协同优化在线持续学习的训练延迟、可塑性与稳定性，实现可行的设备端部署。
◆提出基于木桶效应的统一运行时指标URGE，动态地为在线持续学习各组件重新分配内存。
◆在操作系统和应用层面联合协调批处理、回放缓冲区和优化策略，以自适应应对动态内存压力与工作负载变化。
◆引入系统级数据预取技术，最大化提升执行效率。
实验证明，Orion能显著加速训练并保持性能平衡，同时运行时和能耗开销极低，是设备端持续学习的实用解决方案。</td></tr>
<tr><td>2026-05-25</td><td>G-DRAGON: Geospatial Reasoning and Dynamic Planning for Retrieval-Augmented Outdoor Navigation<br><a href='http://arxiv.org/pdf/2605.25646'>论文</a></td><td>该论文提出了G-DRAGON框架，解决了户外导航中长距离全局规划与最后一步精细探索的挑战。
◆基于轻量级大模型的生成式检索方法，将自然语言指令映射到本地OSM实体以获取准确坐标，有效缓解了云端大模型的幻觉问题。
◆高级规划模块将全局拓扑路线与SLAM系统结合，把地理空间航点投影到机器人可导航坐标系，实现全局到局部的桥接。
◆针对最后一步探索，框架无缝切换至基于边界的探索与开放集语义体素建图，精准定位开放词汇目标。
实验表明该框架性能超越现有基线，并在真实世界无人车上成功完成长达500米的行人搜索任务。</td></tr>
<tr><td>2026-05-25</td><td>RCSP: Risk-Sensitive Conjectural Scenario Planning for Safe Dynamic Robot Navigation<br><a href='http://arxiv.org/pdf/2605.26348'>论文</a></td><td>本文研究了动态导航中的预测性近距交错承诺问题，即当前安全速度可能使机器人驶入即将被移动障碍物封堵的通道，并提出了风险敏感推测场景规划方法RCSP。
◆提出RCSP规划层，通过评估候选指令与短期障碍物未来轨迹的交互来提前预判风险。
◆维持局部运动推测的轻量级信念，通过采样未来交互并惩罚高风险尾部实现风险敏感决策。
◆结合局部安全检查层执行指令，可作为补充模块集成至现有导航技术栈中提升动态安全性。
在MuJoCo和ROS2实验中RCSP实现了零碰撞并减少近距交错失败，但在严苛基准成功率上略逊于调优算法。
该方法被定位为在动态瓶颈环境下有效补充现有导航系统的预测性风险模块。</td></tr>
<tr><td>2026-05-25</td><td>NightSight: Passive Computation for Navigation in Dark Using Events<br><a href='http://arxiv.org/pdf/2605.26330'>论文</a></td><td>本文针对小型无人机在完全黑暗环境中难以自主导航的挑战，提出了一种结合单目事件相机、编码孔径镜头和红外点投影仪的轻量级感知方案。
◆提出基于结构光与编码光学的隐式几何编码机制，红外图案经编码孔径产生深度依赖的模糊特征以隐式编码场景几何。
◆设计了极简的训练范式，仅用平面墙生成的合成数据训练卷积神经网络解码稠密深度图，即可实现对复杂真实场景的零样本泛化。
◆构建了适用于资源受限平台的高效实时系统，在边缘计算设备上以20赫兹运行，2.5米内深度估计绝对误差仅7.0厘米。
该研究还深入分析了不同编码孔径设计对深度估计性能的影响，展示了结构照明、编码光学与事件感知结合在暗光导航中的巨大潜力。</td></tr>
<tr><td>2026-05-24</td><td>GreenSeg: Ground Segmentation Algorithm for Agricultural Robots in Mediterranean Greenhouses using RGB-D Point Clouds<br><a href='http://arxiv.org/pdf/2605.25279'>论文</a></td><td>本文针对地中海温室环境通道狭窄、地形异构且塑料覆膜导致深度传感器产生严重光学干扰的问题，提出了基于RGB-D点云的GreenSeg地面分割算法，替代了昂贵的3D激光雷达方案。
◆提出结合鲁棒全局平面拟合与表面曲率滤波的双层验证策略，以适应从混凝土到耕地等复杂的异构地形。
◆引入基于种子点的区域生长约束，确保可行驶平面的空间连续性。
在AGRICOBIOT I平台上四种不同太阳高度角的昼夜场景中进行的实验验证了该算法的有效性。
结果表明，GreenSeg在走廊尽头关键旋转操作中表现优异，平均召回率和mIoU分别最高提升11.58%和19.24%，显著超越基准方法。
这证实了该算法能够在预算受限且对光照敏感的非结构化动态农业环境中实现稳定安全的自主导航。</td></tr>
<tr><td>2026-05-24</td><td>Micro-Swarm Locomotion Optimization in Dynamic Flow using Multi-Objective Multi-Agent Reinforcement Learning<br><a href='http://arxiv.org/pdf/2605.25025'>论文</a></td><td>本文提出了一个混合计算流体动力学与多目标多智能体强化学习框架，首次将高保真不可压缩Navier-Stokes求解器与分散式近端策略优化直接耦合，解决了动态生理流体环境下微型集群协调的难题。
◆引入PCGrad梯度冲突解决机制，证明在同时优化上游前进、能量守恒和运动平滑度时，梯度冲突解决是该领域的结构性必要条件，有效避免了效率和平滑度奖励的崩溃。
◆实现了多目标优化的卓越性能，收敛策略在前进奖励、能量效率和运动平滑度上均表现优异，而暴力基线的能量效率始终为负。
◆揭示了三种涌现的物理行为，包括抑制前向流速的集体双层流体动力学节流阵型、利用逆流重定位的周期同步棘轮机制，以及接近目标时的个体化最终趋近策略。
该研究确立了依赖时间的流体与智能体交互可直接纳入多目标强化学习循环，为生物医学导航和微流体控制等领域提供了基于物理的全新范式。</td></tr>
<tr><td>2026-05-24</td><td>Performance Comparison of Classical and Neural Sampling Algorithms for Robotic Navigation<br><a href='http://arxiv.org/pdf/2605.25010'>论文</a></td><td>本文系统比较了经典算法RRT*与神经网络采样算法Neural RRT*及Neural Informed RRT*在机器人导航中的性能表现。实验在包含不同密度凸面和凹面障碍物的环境中进行综合评估。
◆揭示了神经引导采样策略能显著提升路径质量，使路径缩短达14%，轨迹平滑度提高55%至75%。
◆验证了Neural Informed RRT*算法在路径长度与轨迹平滑度上取得了最优综合性能。
◆证明了即便计算时间略增，AI引导策略仍能有效提升机器人和无人机导航的可靠性与轨迹效率。</td></tr>
<tr><td>2026-05-24</td><td>Convex-Neural RRT*: Fast and Reliable Learning-Guided Sampling for High-Quality Robot Path Planning<br><a href='http://arxiv.org/pdf/2605.25006'>论文</a></td><td>针对基于采样的机器人路径规划算法获取高质量解需大量迭代的问题，本文提出了Convex-Neural RRT*算法。
◆引入神经引导机制预测高质量路径附近的信息丰富航点区域。
◆从预测结果中提取凸候选区域，使规划器在聚焦几何相关区域探索的同时保留全局探索能力。
实验表明，该算法相比神经引导变体和LTA*分别减少30%至75%和88%至98%的计算时间。
同时，其路径长度比传统RRT*平均缩短约5%，整体成功率保持在99%以上，有效平衡了计算效率与求解质量。</td></tr>
<tr><td>2026-05-23</td><td>Vision-Guided Outdoor Flight and Obstacle Evasion via Reinforcement Learning<br><a href='http://arxiv.org/pdf/2605.24449'>论文</a></td><td>本文提出了一种基于立体视觉和视觉惯性里程计的感觉运动策略，解决了四旋翼在无GNSS和遥测信号环境下的自主导航与避障问题。
◆设计了一种结合预训练自编码器感知头与LSTM规划控制网络的架构，可直接输出供商用无人机执行的速度指令。
◆提出两阶段强化与特权学习训练范式，先利用全局规划器最优轨迹作为监督主干进行初始训练，再在课程环境中微调。
◆通过引入领域随机化和奖励塑形技术，有效缩小了仿真到现实的差距，增强了策略对噪声和域偏移的鲁棒性。
该方法在室外实验中实现了零样本迁移，成功在训练时未见过的障碍物环境和无人机平台上完成自主飞行任务。</td></tr>
<tr><td>2026-05-22</td><td>MASt3R-Nav: WayPixel Navigation in Relative 3D Maps<br><a href='http://arxiv.org/pdf/2605.24111'>论文</a></td><td>本文提出了一种基于像素相对连接性的新型地图表示，解决了传统3D地图需全局一致性以及拓扑图缺乏几何理解限制导航能力的问题。
◆提出像素相对连接性地图表示，兼具几何准确性且无需全局几何一致性。
◆基于3D图像匹配技术，利用图像对相对3D坐标系中的像素对应关系构建图像间连接性与地图。
◆通过逼近和稀疏化图像内像素连接性进行全局路径规划，推导出WayPixel代价图表示。
◆训练以该稠密像素级代价图为条件的控制器预测轨迹展开，证明相对几何代价图比图像及物体级的条件变量更准确。
该导航系统在模拟器四种任务及真实世界演示中均得到验证，展现出强大的导航能力。</td></tr>
<tr><td>2026-05-20</td><td>Flying Together: Human-Guided Immersive Shared Control for Aerial Robot Teams in Unknown Environments<br><a href='http://arxiv.org/pdf/2605.21680'>论文</a></td><td>本文提出了一种基于虚拟现实的无人机团队共享控制框架，旨在解决自主多机器人在非结构化环境中难以适应未知条件和捕捉操作员意图的问题，实现实时用户引导探索。
◆提出用户引导的基于运动基元的规划器，在持续融合操作员输入的同时计算连续无碰撞轨迹。
◆结合导纳控制器，使操作员能灵活影响团队行为并引导无人机前往自主规划器易忽略的关注区域。
◆构建支持物理与仿真无人机混合现实操作的双边VR界面，操作员可通过迁移点引导团队并获取即时视觉反馈。
实验结果表明，该沉浸式人在回路系统有效改善了避障性能，保持了智能体间距，并显著降低了操作员负担。</td></tr>
<tr><td>2026-05-20</td><td>ArchSIBench: Benchmarking the Architectural Spatial Intelligence of Vision-Language Models<br><a href='http://arxiv.org/pdf/2605.20837'>论文</a></td><td>本文提出了ArchSIBench基准，旨在填补现有视觉语言模型在高级建筑空间认知评估上的空白。
◆创新性地融合建筑学、认知科学与心理学视角，构建了涵盖感知、推理、导航、变换和构型五个核心维度及十七个细粒度子任务的系统评估框架。
◆通过建筑背景专家的精细手工标注，构建了包含三千个问答对的高质量专业数据集，确保了评估的权威性与准确性。
◆基于该基准对多款模型进行全面评测，首次系统揭示了模型与人类在建筑空间智能上的差异，以及模型在不同能力维度上的显著波动。
评测发现，最先进模型虽能接近未受专业训练的人类水平，但在空间变换和构型推理上与受过专业训练的建筑师仍存在明显差距。
该研究为衡量和提升视觉语言模型的建筑空间智能提供了重要的系统资源与方向。</td></tr>
<tr><td>2026-05-20</td><td>Q-SpiRL: Quantum Spiking Reinforcement Learning for Adaptive Robot Navigation<br><a href='http://arxiv.org/pdf/2605.20801'>论文</a></td><td>本文针对动态环境中自适应机器人导航的可靠性与轨迹效率问题，提出了Q-SpiRL量子脉冲强化学习框架。
◆创新性地提出了量子增强脉冲神经网络作为核心架构，将脉冲驱动的时序处理与变分量子特征变换有效结合。
◆构建了包含表格Q学习、经典MLP、经典SNN、量子MLP和QSNN五种智能体的统一训练与评估管线，并在多尺寸及动静障碍物混合的网格世界中进行了系统对比。
◆实验表明QSNN在任务完成率、轨迹效率和运动平滑度间取得了最优的整体权衡，在最具挑战性的环境中成功率达99%且维持了高路径效率。
◆在IBM真实量子硬件上的成功执行，验证了该混合策略在真实量子设备条件下实际部署的可行性。</td></tr>
<tr><td>2026-05-19</td><td>KappaPlace: Learning Hyperspherical Uncertainty for Visual Place Recognition via Prototype-Anchored Supervision<br><a href='http://arxiv.org/pdf/2605.19435'>论文</a> | <a href='https://github.com/mayayank95/UncertaintyAwareVPR'>代码</a></td><td>针对现有视觉位置识别方法缺乏校准的不确定性估计这一问题，本文提出了KappaPlace框架以学习不确定性感知的表征。
◆提出原型锚定监督策略，利用潜在类别代表作为概率优化目标的锚点。
◆将图像描述子建模为von Mises-Fisher变量，通过轻量级模块预测浓度参数作为偶然不确定性的直接代理。
◆推导出新颖的匹配级公式，突破了现有方法仅限查询视角的局限，能够量化特定查询与参考图对的匹配可靠性。
该方法提供联合训练与后训练扩展两种模式，在五个基准上将期望校准误差降低高达百分之五十，同时保持或提升检索召回率。
实验证明该框架为位置识别流程提供了鲁棒且校准良好的信号，保障了安全关键应用中的可靠决策。</td></tr>
<tr><td>2026-05-19</td><td>Enhancing Graph-Based SLAM in GNSS-Denied environments by leveraging leg odometry<br><a href='http://arxiv.org/pdf/2605.20484'>论文</a></td><td>本文针对足式机器人在GNSS拒止环境中因几何稀疏或重复场景导致激光雷达产生高程漂移的问题，提出了一种增强图优化SLAM的新架构。该方法通过融合本体感知的腿部里程计，有效弥补了外部感知传感器的垂直漂移缺陷。实验表明，在超过一公里的户外测试中，该方法将高程漂移从30多米降至30厘米以内，并使基线方法完全失效的场景成功收敛。
◆在LIO-SAM框架中引入由腿部里程计驱动的并行运动学通道。
◆通过带有选择性噪声模型的恒等相对位姿约束，将运动学通道与主激光雷达惯性通道耦合。
◆挖掘用于步态控制的本体感知数据，为SLAM提供轻量且有效的垂直锚点。</td></tr>
<tr><td>2026-05-19</td><td>Minimalist Visual Inertial Odometry<br><a href='http://arxiv.org/pdf/2605.19990'>论文</a></td><td>本文提出一种极简的平面视觉惯性里程计方法，证明仅用四个视觉测量值与IMU即可实现差速机器人的鲁棒运动估计，大幅降低了传统VIO处理高像素图像的资源消耗。
◆创新性地使用四个朝下的光电二极管透过光学盖伯掩膜感知环境，产生直接编码速度的信号以替代传统相机。
◆提出在物理仿真器中联合优化盖伯掩膜参数与时序卷积网络，使模型仅凭四个测量值即可解码出线速度。
通过将解码的线速度与IMU的角速度结合即可生成连续轨迹。经室内外多地形测试，该系统无需真实数据微调即可准确跟踪真值，验证了极简感知实现高效里程计的可行性。</td></tr>
<tr><td>2026-05-18</td><td>Qumus: Realization of An Embodied AI Quantum Material Experimentalist<br><a href='http://arxiv.org/pdf/2605.18407'>论文</a></td><td>本文介绍了首个AI量子材料实验学家Qumus，它是一个物理具身于机器人微型实验室的智能多模态多智能体系统，专用于原子级薄二维材料的创建与纳米加工。
◆实现了从假设生成、方案规划到多步实验执行、结果分析与报告的全科学周期自主导航。
◆首次达成了AI创造石墨烯，以及通过范德华堆叠制造原子层级场效应晶体管等复杂纳米器件的突破。
◆具备自主纠错和闭环实验的卓越能力，有效整合了高层推理、多模态信息处理与实时物理执行。
该成果为直接从量子世界学习的自我改进型具身AI系统建立了通用化框架，为加速量子材料与电子学等领域的发现开辟了新途径。</td></tr>
<tr><td>2026-05-16</td><td>NORM-Nav: Zero-Shot Mobile Robot Navigation with Natural Language Behavioral Constraints<br><a href='http://arxiv.org/pdf/2605.16979'>论文</a> | <a href='https://ei-nav.github.io/NORM-Nav'>代码</a></td><td>本文提出NORM-Nav框架，解决了传统基于代价图的导航仅关注几何可行性而忽视社会行为规范的问题，实现了零样本自然语言行为约束的移动机器人导航。
◆利用大语言模型解析自然语言指令生成结构化约束，并借助实时视觉与激光雷达感知完成约束落地。
◆将行为约束编码为包含几何、语义、方向及速度线索的多层代价图，且与标准网格规划器直接兼容。
仿真与真实世界实验证明，该框架有效提高了任务成功率。
其生成的轨迹也显著比代表性基线方法更接近人类参考行为。</td></tr>
<tr><td>2026-05-13</td><td>LEXI-SG: Monocular 3D Scene Graph Mapping with Room-Guided Feed-Forward Reconstruction<br><a href='http://arxiv.org/pdf/2605.13741'>论文</a> | <a href='https://ori-drs.github.io/lexisg-web/'>代码</a></td><td>近年来，场景图成为机器人导航的标准层次化表示，但多数方法依赖深度传感器。  
◆首次提出仅用单目RGB实现开放词汇密集3D场景图映射的系统LEXI‑SG。  
◆利用基础模型的语义先验将场景划分为房间，并在房间完整观测后进行前馈重建，避免滑动窗口尺度不一致。  
◆构建房间级因子图实现全局对齐，保持局部地图一致性和语义层次结构。  
◆在每个房间内支持开放词汇对象分割与跟踪，实现细粒度物体理解。  
实验在Habitat‑Matterport 3D和自采办公场景上验证，显示轨迹估计和密集重建精度提升，开放词汇分割性能具有竞争力。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='motion-planning'>Motion Planning (110篇)</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-06-15</td><td>Intermittent Strategic Cooperation of Two Selfish Agents on Graphs<br><a href='http://arxiv.org/pdf/2606.17216'>论文</a></td><td>◆论文提出IC2PP问题，将两个自利智能体在图上的路径规划建模为带有间歇性合作机会的最短路博弈。

◆其核心创新在于刻画了纯纳什均衡联合策略的结构，指出稳定合作只能以高度受限的形式出现。

◆论文证明任意IC2PP实例中至少存在一个纯纳什均衡，为该类合作博弈提供了存在性保证。

◆作者设计了多项式时间算法，用于枚举所有相关纯纳什均衡，提升了该问题的可计算性。

◆在存在多个均衡时，论文引入基于议价理论的均衡选择机制，并通过实验比较个体旅行时间与社会福利表现。</td></tr>
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
<tr><td>2026-06-12</td><td>Bounding Boxes as Goals: Language-Conditioned Grasping via Neuro-Symbolic Planning<br><a href='http://arxiv.org/pdf/2606.12910'>论文</a></td><td>论文核心贡献总结:

该论文提出了GRASP(Grounded Reasoning and Symbolic Planning)框架,旨在实现开放词汇的桌面机器人操作任务。该方法利用预训练的视觉-语言模型(VLM)将自然语言指令转换为神经符号目标状态,并通过边界框检测管道将其与物理世界相对应,从而使机器人能够实时响应自然语言提示。在90次真实机器人实验中,该框架在三个难度等级上实现了73.3%的总体成功率,且无需任何任务特定的训练或微调。

主要创新点如下:

◆ 提出神经符号规划框架,将VLM的语言理解能力与符号化目标表示相结合,把自然语言查询转化为可执行的符号目标状态。

◆ 采用边界框作为目标表示形式,通过检测管道将抽象语言概念与物理空间精准对接,避免了传统方法对固定颜色列表或硬编码坐标的依赖。

◆ 实现真正的零样本开放词汇操作能力,无需数千次演示数据训练,即可解释&quot;顶层货架&quot;等抽象空间概念。

◆ 相比于当前计算密集型的SOTA方法,该框架更加轻量化,降低了计算开销,更适合实时部署。

◆ 在真实机器人平台上完成了多难度等级的系统性验证,证明了方法在实际场景中的可行性与泛化性。</td></tr>
<tr><td>2026-06-12</td><td>Short-Horizon Position Accuracy of Single-Track Models: Implications for Motion Planning of Autonomous Vehicles<br><a href='http://arxiv.org/pdf/2606.14216'>论文</a></td><td>自动驾驶运动规划依赖计算高效且准确的车辆模型，但目前缺乏针对模型短时域位置精度的系统性实车评估。本文通过实车专用实验识别参数，在多种驾驶工况下将三种单轨模型的短时域位置预测与实车测量数据进行了系统比较。
◆首次系统性地评估了单轨车辆模型在短时域内的位置精度，填补了模型预测与真实测量数据对比的空白。
◆揭示了模型复杂度、参数化质量与位置精度之间的权衡关系，打破了寻找单一最优模型的局限。
◆为模型预测控制等运动规划应用中的车辆模型选择，提供了基于实际精度权衡的指导性见解。</td></tr>
<tr><td>2026-06-12</td><td>Semidefinite Relaxations for Collision-Free Motion Planning<br><a href='http://arxiv.org/pdf/2606.14063'>论文</a></td><td>本文研究了无碰撞运动规划的半定松弛方法，将点机器人穿越球形障碍物的问题精确建模为多项式曲线上的非凸问题，并提出自然半定松弛。
◆首次从理论证明，求解该凸松弛等价于在更高维空间中全局求解相关的运动规划问题，给出了松弛紧致性的充要条件与直观解释。
◆提出对称性约简方法，使半定正定锥的规模仅与多项式阶数线性相关且独立于环境维度，显著缩小了问题规模。
实验表明，该方法比直接使用SNOPT和IPOPT求解非线性规划快十至百倍，方差更低，能可靠找到原问题的局部最优路径。
最后，该方法被成功用作RRT规划器中的凸转向函数，实现了具有C4连续轨迹的四旋翼最小抖动规划。</td></tr>
<tr><td>2026-06-12</td><td>ParkingTransformer: LLM-Enhanced End-to-End Trajectory Planning for Autonomous Parking<br><a href='http://arxiv.org/pdf/2606.17082'>论文</a></td><td>◆提出ParkingTransformer端到端自主泊车框架，将多视角感知与大语言模型的场景理解能力结合，提升长距离泊车任务的语义理解与可解释性。
◆方法直接利用历史信息和原始传感器数据，通过轨迹查询融合LLM隐式状态特征生成规划轨迹，避免依赖稠密BEV表示。
◆为弥补LLM空间推理不足，引入3D位置编码，显式注入几何空间信息，增强车辆对泊车场景结构的理解。
◆设计固定窗口流式历史信息处理机制，提高长时序建模效率和推理速度，更适合实际在线部署。
◆采用粗到细解码策略逐步优化轨迹精度，并在CARLA和真实车辆实验中取得较高驾驶得分与88.70%的平均成功率，验证了方法有效性。</td></tr>
<tr><td>2026-06-11</td><td>Mana: Dexterous Manipulation of Articulated Tools<br><a href='http://arxiv.org/pdf/2606.13677'>论文</a></td><td>论文核心贡献总结:

该论文提出了Mana(Manipulation Animator),一个面向铰接式工具灵巧操作的通用sim-to-real框架,旨在解决灵巧机器人领域中协调内部自由度与接触丰富交互的难题。作者将灵巧操作重新诠释为动画生成问题,借鉴计算机动画的思想,采用由粗到细的流程,将程序化生成的抓取关键帧通过运动规划与强化学习转化为完整的操作轨迹。该方法在四种不同尺度和关节类型的铰接工具上均实现了抓取与手内操作的零样本sim-to-real迁移,为可扩展的铰接工具灵巧操作提供了新思路。

主要创新点:

◆ 首次将铰接式工具的灵巧操作问题重新表述为动画生成问题,借鉴计算机动画中的关键帧思想构建操作轨迹生成范式。

◆ 提出由粗到细的Mana流程,将程序化生成的抓取关键帧通过运动规划和强化学习相结合,转化为高质量的操作轨迹。

◆ 数据生成过程高度自动化,用户仅需几次鼠标点击即可指定功能性可供性,每个工具配置耗时不到一分钟,大幅降低人工成本。

◆ 在四种不同尺度与关节类型的铰接工具上验证了零样本sim-to-real迁移能力,包括抓取与手内操作两类任务。

◆ 填补了以往研究主要聚焦于刚性物体的空白,首次系统地解决铰接式工具功能性抓取与操作策略的学习难题,具有良好的可扩展性。</td></tr>
<tr><td>2026-06-11</td><td>Distribution-Agnostic Robust Trajectory Optimization via Chance-Constrained Reinforcement Learning<br><a href='http://arxiv.org/pdf/2606.13605'>论文</a></td><td>本文提出了一种基于机会约束强化学习的分布无关鲁棒轨迹优化框架,通过对不确定性仅要求可采样的方式,突破了传统方法对高斯分布等特定假设的依赖。该框架先离线计算确定性标称轨迹,再利用强化学习对其进行鲁棒化增强,并通过两个差异显著的航天轨迹问题(三维多脉冲地火转移与大气层精确定点火箭着陆)验证了方法的通用性与有效性,在保持概率可行性的同时,在上尾燃料成本上仍具竞争力。

◆ 提出分布无关的鲁棒轨迹优化框架,初始条件与过程噪声仅需可采样,无需已知概率分布形式。

◆ 采用&quot;标称轨迹+鲁棒化增强&quot;的两阶段设计,强化学习仅用于在确定性基线上施加结构化的仿射闭环修正律,包含前馈控制调整与时变反馈增益。

◆ 通过基于轨迹采样的上尾分位数经验性地强制概率可行性,并利用协方差可行性惩罚约束终端散布。

◆ 同一鲁棒化架构无需重新设计核心随机控制结构,即可跨异构航天轨迹规划问题(脉冲深空转移与连续推力大气着陆)迁移使用。

◆ 在训练中未见的过程扰动以及有界均匀不确定性等非高斯场景下,验证了方法的泛化与鲁棒能力。</td></tr>
<tr><td>2026-06-11</td><td>SPARC: Reliable Spatial Annotations from Robot Demonstrations at Scale<br><a href='http://arxiv.org/pdf/2606.13497'>论文</a> | <a href='https://intuitive-robots.github.io/sparc-labeling'>代码</a></td><td>本文提出了SPARC(带可靠性校准的机器人演示空间标注框架),这是一个风险感知的自动化标注系统,能够为机器人演示数据生成结构化空间标注(如边界框、物体轨迹、操作阶段标签)并为每条标注分配可靠性评分。针对现有自动化标注流程缺乏可靠质量信号、检测器置信度无法准确反映标注正确性的问题,SPARC利用机器人任务固有的时空结构生成可靠性信号,在减少噪声标签的同时保留更多有用样本。在涵盖多种机器人形态和场景的1.7k人工标注演示上,SPARC显著优于仅依赖检测的基线方法,且在高精度工作点下保留了三倍以上的样本。

◆ 提出了首个面向机器人演示的风险感知空间标注框架SPARC,首次将可靠性校准引入自动化标注流程。
◆ 创新性地利用机器人任务的时空结构作为可靠性信号来源,突破了传统检测器置信度校准不准确的瓶颈。
◆ 提出Interaction-Aware Bench(IA-Bench)新基准,专门评估模型对机器人演示中被交互物体位置的定位能力。
◆ 验证了无需人工标注或验证数据,基于SPARC标注微调的模型即可在物体定位和指向基准上达到同规模模型的SOTA水平。
◆ 证明了基于SPARC标注训练的策略在杂乱、视觉模糊的真实场景中显著超越基线方法,具备实际落地价值。</td></tr>
<tr><td>2026-06-11</td><td>Proprioceptive-visual correspondence enables self-other distinction in humanoid robots<br><a href='http://arxiv.org/pdf/2606.13222'>论文</a> | <a href='https://euron-zc.github.io/humanoid-self-model/'>代码</a></td><td>这篇论文研究了人形机器人如何在共享工作空间中实现自我与他者的区分,这是社交智能的基础前提。作者提出通过本体感觉与视觉的对应关系,使机器人无需身份标签或运动学模型即可自主学习自我识别能力。一旦建立自我区分,系统便能引导构建预测性自我模型,将关节配置映射到三维身体占据空间,从而捕捉身体随动作的变化。该方法在涉及人类或形态相同机器人的多智能体场景中均能可靠识别自身,并支持目标到达、避碰运动规划以及人机动作重定向等下游任务,为机器人在共享物理环境中与他者协同行动提供了具身自我表征的可行路径。

核心创新点如下:

◆ 首次提出基于本体感觉与视觉对应关系的自我-他者区分机制,完全摆脱对身份标签和预设运动学模型的依赖,实现真正自监督的自我识别。

◆ 构建了从关节配置到三维身体占据空间的预测性自我模型,使机器人能够动态捕捉身体随动作变化的空间形态。

◆ 验证了该方法在多智能体复杂场景下的鲁棒性,即使面对形态完全相同的同类机器人,系统仍能准确识别自身。

◆ 将自我模型成功应用于目标到达、碰撞感知运动规划和人到机器人动作重定向等多种下游任务,展现了具身自我表征的实用价值与通用性。</td></tr>
<tr><td>2026-06-11</td><td>Computing Smooth Geodesics under Two-Sided Curvature Bounds with Applications to Robotics and Image Analysis<br><a href='http://arxiv.org/pdf/2606.14794'>论文</a></td><td>本文致力于解决计算物理与几何中极具挑战性的问题，即追踪受任意上下界曲率约束的极小路径。
◆提出了一种基于哈密顿-雅可比-贝尔曼偏微分方程框架的新型曲率有界测地线模型，通过强制曲率范围约束对极小路径实现强几何控制，保证路径平滑且曲率受限。
◆设计了针对哈密顿量及结合曲率边界的HJB PDE的离散化方案，为模型数值解的估计提供了高效求解器。
该模型在机器人路径规划和图像曲线结构追踪等应用中展现出强大的能力。
数值实验证明该曲率有界测地线模型是寻找满意路径的强大且鲁棒的工具。</td></tr>
<tr><td>2026-06-10</td><td>Fibration Trees: A Unified Approach to Multi-Robot Motion Planning<br><a href='http://arxiv.org/pdf/2606.12070'>论文</a></td><td>本文针对多机器人运动规划中投影与分解缺乏统一框架的问题，提出了纤维化树这一全新方法。纤维化树由状态空间节点和表示高维到低维投影的纤维化边构成，为高维规划提供了统一的拓扑结构。
◆通过将投影建模为纤维化，首次将顺序优先化、并行分解和任务空间投影统一在一个连贯的形式化框架中。
◆提出基于快速探索随机纤维化树的Fibration-RRT规划器，该算法不仅推广了商空间RRT和离散RRT的策略并支持任务空间投影，还被严格证明具有概率完备性。
在高达96自由度的32个场景中的实验表明，该算法能高效解决高维问题，确立了纤维化树作为多机器人运动规划统一框架的地位。</td></tr>
<tr><td>2026-06-10</td><td>Learning Unions of Convex Sets via Invertible Latent Decomposition for Path Planning<br><a href='http://arxiv.org/pdf/2606.12027'>论文</a></td><td>本文提出ILD框架，弥合了显式表示扩展性差与隐式表示缺乏硬保证之间的鸿沟。
◆联合学习可逆映射与潜空间中显式凸多面体的组合，在潜空间规划后将路径解码回原空间，兼顾了复杂几何的扩展性与显式约束的安全可行性。
◆提出能见度引导采样策略，有效保持凸集间的连通性以满足路径规划需求。
实验表明，该方法在2D至14自由度环境中实现了更广覆盖、更好连通性与更高规划成功率，且测试细化后零假阳性。
在14自由度双臂机械臂上，该方法实现了实时无碰撞规划，并能在真实部署中适应场景几何变化。</td></tr>
<tr><td>2026-06-10</td><td>MPPI-based Informative Trajectory Planning for Search and Capture of Drifting Targets with ASVs<br><a href='http://arxiv.org/pdf/2606.12019'>论文</a></td><td>本文针对自主水面航行器(ASV)在开放水域中搜索与捕获多个漂移目标(如海洋垃圾)的问题,提出了一种混合规划框架,通过结合长时域信息性轨迹规划与纯追踪制导控制,有效平衡了未知区域探索与已知目标跟踪之间的矛盾。该方法在动态环境下兼顾了搜索效率与捕获精度,并通过仿真实验和实船现场试验验证了其相较基线方法的优越性。

核心贡献与创新点如下:

◆ 提出了一种基于模型预测路径积分(MPPI)控制的时空信息性规划方法,利用采样式模型预测控制在长时域内直接优化连续轨迹,生成运动学层级的控制指令,克服了传统方法仅依赖简单制导行为和短期预测的局限。

◆ 设计了一种多目标代价函数,融合搜索、跟踪以及安全可行性约束,使规划器能够在漂移目标动态变化的环境中自适应地权衡探索与跟踪。

◆ 构建了搜索与捕获两阶段的混合规划框架,在拦截阶段切换至纯追踪制导控制器,实现对运动目标的物理捕获,提高了系统在实际任务中的完整性与实用性。

◆ 在仿真和真实ASV的现场试验中均验证了该方法的有效性,证明其性能优于所选基线规划方法,具备工程应用价值。</td></tr>
<tr><td>2026-06-10</td><td>G-MAPP: GPU-accelerated Multi-Agent Planning and Perception for Reactive Motion Generation<br><a href='http://arxiv.org/pdf/2606.12579'>论文</a></td><td>该论文提出了G-MAPP,一个基于GPU加速的多智能体规划与感知框架,旨在解决非结构化动态环境中实时反应式运动生成的挑战。论文指出现有方法的主要瓶颈在于高保真环境下规划模块的运行时性能,以及感知与规划模块之间的时序集成问题。作者通过GPU并行化加速世界建模和基于向量场的规划过程,实现了在保持高质量世界表征的前提下的高效运算。该框架在7自由度Franka Emika机器人上进行了真实世界实验验证,GPU版本相比CPU版本达到最高5倍加速,并能在复杂杂乱场景下成功避障。

核心创新点如下:

◆ 提出了GPU加速的世界建模方法,在不牺牲环境表征精度的情况下显著提升运算效率,解决了高保真感知与实时规划之间的矛盾。

◆ 设计了基于GPU并行化的向量场规划算法,通过并行状态探索实现准全局轨迹规划,相比CPU版本实现最高5倍的加速。

◆ 实现了感知-动作环路的紧耦合时序集成,使用现成的深度传感器即可在动态杂乱环境中完成实时反应式运动生成。

◆ 在真实7自由度Franka Emika机械臂上进行了定量与定性实验验证,证明该框架在简单和复杂物理场景下均能稳定避障。</td></tr>
<tr><td>2026-06-10</td><td>Foresight: Iterative Reasoning About Clues that Matter for Navigation<br><a href='http://arxiv.org/pdf/2606.12550'>论文</a></td><td>论文《Foresight: Iterative Reasoning About Clues that Matter for Navigation》针对开放世界中基于稀疏语言指令的无地图导航问题,提出了一种测试时迭代推理框架。该方法利用预训练视觉语言模型(VLM)发现与指令相关的新型环境线索(如坡道、标识、绕行路径等),并通过&quot;提议-批判&quot;循环不断优化运动规划,在6个真实环境中相较最先进基线平均任务成功率提升37%,每次任务干预次数减少52%,并能在Jetson AGX Orin上实时运行。

◆ 提出Foresight测试时推理框架,让微调后的VLM在图像空间中交替执行运动规划提议与基于语言目标和视觉上下文的批判,实现执行前的迭代式规划精炼。

◆ 突破以往方法依赖已知导航因素和闭集类别的局限,利用VLM发现开放集的、与指令相关的新颖线索。

◆ 将线索识别与运动规划深度耦合,捕获依赖于具体规划的线索,而非传统方法中规划前一次性识别线索。

◆ 通过人类反馈学习奖励模型,并在&quot;规划-批判&quot;循环中使用强化学习对VLM进行后训练,使批判与精炼过程对齐开放集的行为偏好。

◆ 在离线评估与6个真实世界环境中验证了方法的有效性,且具备实时部署能力。</td></tr>
<tr><td>2026-06-09</td><td>Combining Reinforcement Learning with Arc-search Interior-Point Method for Path Planning<br><a href='http://arxiv.org/pdf/2606.07920'>论文</a></td><td>本文针对含障碍物环境下的非线性和非凸路径规划问题，提出了一种结合强化学习与弧搜索内点法的新框架。该框架的核心贡献在于有效克服了单一方法的局限性，实现了两者的优势互补。
◆创新性地将强化学习的实时决策能力与弧搜索内点法的寻优性能相融合，解决了机器学习路径非最优与优化方法实时性差的问题。
◆利用强化学习在无需高保真模型的情况下快速生成可行路径，满足系统的实时性要求。
◆引入弧搜索内点法对生成的路径进行进一步优化，确保路径在长度或时间等性能指标上达到最优或近最优。
仿真结果表明，该方法显著提升了路径规划的综合性能。</td></tr>
<tr><td>2026-06-09</td><td>Diffusion Forcing Planner: History-Annealed Planning with Time-Dependent Guidance for Autonomous Driving<br><a href='http://arxiv.org/pdf/2606.11019'>论文</a></td><td>该论文提出Diffusion Forcing Planner框架，旨在解决基于学习的运动规划器在自动驾驶中因帧间扰动累积导致的时间不一致与轨迹不稳定问题。现有方法将历史作为静态条件易使模型盲目复制历史而无法适应新环境，DFP则通过历史引导控制来解决此局限。
◆提出异构联合扩散过程，将轨迹分解为历史、当前与未来段并赋予独立噪声水平，对历史与未来段进行联合去噪。
◆引入时间依赖的引导机制，在推理时应用无分类器引导，利用退火历史以可控方式引导未来轨迹采样。
在nuPlan数据集上的闭环评估与消融实验表明，DFP在复杂驾驶场景中不仅取得了极具竞争力的性能，还能生成连续、稳定且可控的运动规划。</td></tr>
<tr><td>2026-06-09</td><td>Multi-UAV Active Sensing with Information Gain-based Planning and Belief Fusion<br><a href='http://arxiv.org/pdf/2606.10986'>论文</a></td><td>本文在真实精准农业场景中验证了一个多无人机主动感知框架，用于概率二元地形映射。
◆提出基于因子图构建概率信念地图以有效表征空间依赖关系。
◆引入基于信息增益的启发式路径规划引导无人机决策，其性能优于随机游走和扫描覆盖基线。
◆系统评估了多无人机信息共享的空间权重与融合规则，发现简单权重比自适应权重更鲁棒，且贝叶斯等融合规则性能最优。
实验表明该规划方法能更有效降低地图熵与误差，同时更宽视野提升了真实环境的覆盖与精度。</td></tr>
<tr><td>2026-06-09</td><td>LieIPM: Lie Group Interior Point Method for Direct Trajectory Optimization of Rigid Bodies<br><a href='http://arxiv.org/pdf/2606.10579'>论文</a></td><td>本文提出了一种直接在矩阵李群上进行刚体约束轨迹优化的结构感知框架，解决了传统欧式空间优化器忽略流形结构而导致的奇异性与病态问题。
◆基于李群结构的二阶刚体模型，实现了高效的牛顿型更新并保留了底层几何特性。
◆提出线搜索李群内点法以直接处理流形上的约束问题。
◆利用李群变分积分器实例化该框架，并推导出利用群对称性的闭式内蕴导数。
该方法从根本上保留了旋转运动的拓扑结构并避免了奇异性，数值实验证明其比现有方法具备更强的鲁棒性与更快的收敛速度。</td></tr>
<tr><td>2026-06-09</td><td>A Modular Dual-Camera Pipeline for Micro-Inspection Using Aerial Robots<br><a href='http://arxiv.org/pdf/2606.11419'>论文</a> | <a href='https://github.com/SaxionMechatronics/aerial_micro_inspection'>代码</a></td><td>本文提出了一种名为aerial_micro_inspection的模块化双摄像头无人机微检管道，解决了传统巡检需近距离飞行、依赖先验几何信息及易受干扰丢失目标的问题。
◆提出了双摄像头协同架构，利用广角立体导航相机获取目标表面、估计距离并分区，结合变焦云台检查相机在安全距离外捕捉微小细节。
◆设计了基于视觉的反馈回路，在检查相机对大表面进行分区扫描时，有效补偿无人机运动带来的干扰，提升了窄视角下的覆盖鲁棒性。
◆构建了基于ROS 2的开源模块化系统，无需目标先验信息，只需替换表面分割和微目标检测的模型权重即可快速适配不同应用场景。
仿真与真实实验表明，该管道在干扰下具有鲁棒的覆盖率，并在树木害虫检测和温室昆虫高精度成像中表现出色。</td></tr>
<tr><td>2026-06-08</td><td>Safe Polytope-in-Polytope Motion Planning and Control with Control Barrier Functions<br><a href='http://arxiv.org/pdf/2606.09719'>论文</a></td><td>本文提出了一种针对多面体外形机器人的安全局部运动规划与控制方法，确保机器人始终位于持续更新的凸自由空间区域内，避免了将机器人简化为点或圆的保守性。
◆将包含条件表述为模型预测控制器中的离散时间控制障碍函数约束。
◆安全约束的数量仅取决于局部自由空间几何与机器人形状，而非障碍物数量，且无需进行障碍物检测或分割。
◆与传统基于多面体的避障方法相比，该方法的计算时间大幅缩减，最高可达91倍。
该方法在仿真和硬件实验中均得到验证，在嵌入式计算机上实现了10赫兹的安全实时运动规划与控制，并能有效应对动态障碍物。</td></tr>
<tr><td>2026-06-08</td><td>Motion planning for hundreds of floating robots<br><a href='http://arxiv.org/pdf/2606.09620'>论文</a></td><td>本文针对大规模机器人舰队防碰撞运动规划中因智能体强耦合导致的计算困难，提出了一种面向水面全向漂浮机器人的可扩展规划框架。该框架能够在分钟级过渡和数千时间步下，根据稀疏关键帧在数秒内快速生成轨迹。
◆基于初始化构建碰撞图，将强耦合问题分解为交互簇，并对其进行独立且并行的求解，有效提升了计算扩展性。
◆引入鲁棒性机制处理常见的解耦病理问题，确保了复杂情况下的规划成功率。
该方法在多达500个机器人的仿真中得到了验证，并成功应用于苏黎世湖24艘船只及2025年威尼斯双年展的真实世界演示。</td></tr>
<tr><td>2026-06-08</td><td>MASS: Deep Research for Social Sciences with Memory-Augmented Social Simulation<br><a href='http://arxiv.org/pdf/2606.09198'>论文</a></td><td>本文提出名为MASS的记忆增强型社会模拟新范式，解决了现有大模型深度研究智能体在社会科学领域缺乏洞察力与创造力的问题。该范式通过高真实度且面向研究的社会模拟，增强了智能体生成研究的创造力与实证基础。
◆引入带有多层次社会规范约束的动态目标-路径规划，以有效引导模拟过程。
◆构建多学科行为数据集，用于实现智能体记忆的冷启动。
◆提出受艾宾浩斯曲线启发的结构化遗忘机制，确保模拟真实性。
实验结果证明该方法有效，其整体生成质量较基础大模型提升6.81%，洞察力较强基线提升17.19%。</td></tr>
<tr><td>2026-06-08</td><td>Trajectory Optimization in Single and Dual-UAV Bearing-Only Target Localization<br><a href='http://arxiv.org/pdf/2606.09188'>论文</a></td><td>本文提出一种针对单和双无人机仅测角目标定位的轨迹优化方法，利用费舍尔信息矩阵将几何构型与飞行器机动性动态融合到优化框架中。
◆提出谱加权FIM目标函数，在退化构型附近提供更优的梯度动态，使规划器能迅速脱离不良观测条件。
◆在双无人机场景中引入交角正弦项，通过改善视线交角来优化三角测量几何，从而有效防止轨迹聚合。
◆提出结合运动模型约束与粒子归一化的改进粒子群优化算法，确保轨迹的物理可行性并提升与目标函数的兼容性。
仿真结果表明，该方法在单和双无人机场景下分别将中位定位误差降低了99.21%和69.70%，在远距离机动目标的长时定位中表现卓越。</td></tr>
<tr><td>2026-06-08</td><td>Deterministic versus Stochastic Optimization for Joint Path Planning and Dynamic Time Splitting in Multiple-UAV-Cached IoT Networks<br><a href='http://arxiv.org/pdf/2606.09014'>论文</a></td><td>本文研究了配备反向散射与缓存技术的多无人机无线供电物联网网络，旨在联合优化动态时间分割比、轨迹和发射功率以最大化总吞吐量。针对该非凸优化问题的挑战，论文的核心创新点如下：
◆提出基于块坐标下降法的交替优化算法，并利用KKT条件推导出最优动态时间分割比的闭式表达式，大幅减少了计算时间。
◆引入采用单点交叉、值变异和排序选择的遗传算法，全面评估并提供了该问题的随机优化求解方案。
数值结果表明，这两种算法较基准方法实现了至少31%的吞吐量提升且计算时间更短。这充分验证了所提方案在缓存使能的无人机辅助物联网网络中的性能增益与实际可行性。</td></tr>
<tr><td>2026-06-08</td><td>Submodular Optimization with Applications to Decision and Control<br><a href='http://arxiv.org/pdf/2606.10192'>论文</a></td><td>本文综述了次模优化在决策与控制领域的理论、算法及应用，为子集选择问题提供了统一的组合框架。
◆系统梳理了次模函数的结构特性、实际约束条件及单调与非单调最大化的最新近似算法与理论界限。
◆强调实用且具近似保证的贪心算法，并通过曲率和次模比实现了依赖实例的算法精细化改进。
◆明确了典型控制目标的次模性，指出可控性格拉姆矩阵的对数行列式等具有次模性，而稳态卡尔曼滤波误差等则不具备。
此外，文章还探讨了传感器调度与多智能体协调等应用，并指出了跨领域的未来开放研究方向。</td></tr>
<tr><td>2026-06-08</td><td>FlexPath: Learned Semantic Path Priors for Image-Based Planning<br><a href='http://arxiv.org/pdf/2606.10167'>论文</a> | <a href='https://github.com/FraunhoferIVI/FlexPath'>代码</a></td><td>该论文提出了FlexPath，一个两阶段的路径规划框架，将路径的可行性与偏好解耦，解决了现有学习型规划器局限于最短路径目标的问题。
◆提出两阶段解耦架构，第一阶段利用模仿学习从视觉地图中获取与任务无关的可行路径空间先验。
◆引入可微路径形状目标，在第二阶段仅需在目标层面进行高效适应，无需重新学习路径结构，单一预训练模型即可适配多种规划标准。
实验表明，在最短路径规划上，该方法比现有最优方法减少14.3%的搜索量并找到更低成本路径，同时在三个未见领域展现出强零样本泛化能力。
在障碍物间隙任务中实现96.8%完全避障与低搜索成本，还可扩展至语义避障和航路点引导，且推理时与经典规划器兼容。</td></tr>
<tr><td>2026-06-08</td><td>Uncertainty-Aware Motion Planning for Autonomous Driving in Mixed Traffic Environment<br><a href='http://arxiv.org/pdf/2606.09958'>论文</a></td><td>这篇论文针对混合交通环境下自动驾驶运动规划问题,提出了一种考虑人类意图预测不确定性的强化学习方法UAMP。现有基于强化学习的方法通常将预测的人类意图作为确定性状态直接纳入观测,忽略了由行为多样性、感知噪声和部分可观测性带来的固有不确定性,容易导致不安全的决策。UAMP通过量化交互条件下的意图不确定性,并在价值学习中校正由此引发的偏差,从而在保持交通效率的同时显著提升了行驶安全性和舒适性。

◆ 提出了面向混合交通的不确定性感知运动规划框架UAMP,首次将人类意图预测的不确定性显式建模并融入自动驾驶决策。

◆ 设计了邻近感知的不确定性估计器,量化交互条件下的意图不确定性,并构建周围人驾车辆的联合意图分布。

◆ 提出不确定性校准价值学习方法UCVL,针对将不确定意图直接纳入观测所导致的价值函数学习偏差进行修正。

◆ 在多种混合交通场景下的大量实验表明,该方法相比现有方法在安全性和舒适性上有显著提升,同时保持了通行效率。</td></tr>
<tr><td>2026-06-07</td><td>Video2Sim2Real: Full-Stack Autonomous Dexterous Skill Acquisition from a Single Human Video<br><a href='http://arxiv.org/pdf/2606.08828'>论文</a></td><td>本文提出了Video2Sim2Real全栈框架，实现了从单个人类视频中自主获取机器人灵巧操作技能，克服了感知误差与具身鸿沟的挑战。
◆提出以物体为中心的关键帧优化策略，在模拟器中利用物体信息优化机器人配置作为锚点来细化运动轨迹，确保操作对环境产生预期影响。
◆设计了解耦的虚实迁移策略，通过模仿学习从含噪点云重校准配置以应对感知误差，并结合残差强化学习进行局部手指适应以克服交互动态变化。
◆引入碰撞感知的运动规划模块，使习得的技能能够空间泛化至未见过的物体配置。
实验表明该框架在多项任务中显著提升了模拟与真实环境下的成功率、安全性与轨迹连贯性。</td></tr>
<tr><td>2026-06-07</td><td>Real-Time and Accurate Collision-Free Teleoperation via Differentiable Constraint-Based Trajectory Planning<br><a href='http://arxiv.org/pdf/2606.08725'>论文</a></td><td>遥操作中仅控制末端执行器易导致机械臂自碰撞与环境碰撞，而现有的最优控制轨迹规划方法常采用球体近似降低几何精度，或近似导数导致收敛慢及计算耗时增加。本文提出了一种基于可微约束轨迹规划的实时无碰撞遥操作方法来解决上述问题。
◆将基于凸优化对偶性的可微避碰约束新公式引入遥操作场景。
◆采用胶囊体近似机械臂并用多面体表示环境，在保持可微性的同时显著提升了障碍物建模的几何精度。
仿真和真实UR5e机械臂实验表明，该方法计算时间更短，实现了更平滑准确的无碰撞遥操作。</td></tr>
<tr><td>2026-06-07</td><td>Towards End to End Motion Planning and Execution for Autonomous Underwater Vehicles Using Reinforcement Learning<br><a href='http://arxiv.org/pdf/2606.08513'>论文</a></td><td>该论文提出一种端到端深度强化学习方法，直接将原始传感器数据映射为水下自主航行器的推进器指令，以替代传统复杂的工程流水线。
◆提出分层强化学习架构，将任务分解为两个马尔可夫决策过程，即处理视觉声纳数据生成子目标的高层策略与将子目标转为推进器指令的低层策略。
◆在训练框架上进行针对性设计，高层策略采用基于先验演示的强化学习与改进的SERL框架，低层策略结合软演员评论家算法与事后经验回放。
在高保真模拟器中，该方法实现了成功避障，且轨迹长度与RRT星基线仅相差百分之四至百分之六。
此外，该策略对模拟传感器噪声和低能见度展现出强鲁棒性，尽管在未见过的复杂障碍物形状上存在泛化局限。
该研究最终证明了在极低计算硬件下，样本高效的端到端强化学习在水下导航任务中的巨大潜力。</td></tr>
<tr><td>2026-06-06</td><td>SIMPLE: Simulation-Based Policy Learning and Evaluation for Humanoid Loco-manipulation<br><a href='http://arxiv.org/pdf/2606.08278'>论文</a></td><td>本文提出了SIMPLE，一个用于人形机器人全身移动操作策略学习与评估的统一仿真试验台，解决了该领域缺乏可扩展和可复现基准的问题。
◆该框架将MuJoCo的精确接触动力学与IsaacSim的照片级真实渲染相结合，构建了包含60项任务、50个室内场景和超千种物体的大规模环境。
◆集成了基于运动规划的自动化轨迹生成和低延迟VR遥操作两条数据采集流水线，实现了高效且可扩展的数据收集。
◆大规模集成并基准测试了包括轻量级模仿网络、视觉语言动作模型和世界动作模型在内的主流人形策略。
实验证明仿真与真实世界性能高度相关，且在SIMPLE中训练的策略可零样本迁移至物理人形机器人，为人形机器人研究提供了坚实基础。</td></tr>
<tr><td>2026-06-06</td><td>Learning Predictive Control with Deep Koopman Operators for Autonomous Vehicle Motion Planning<br><a href='http://arxiv.org/pdf/2606.08136'>论文</a></td><td>本文针对自动驾驶运动规划中传统模型预测控制实时性差及强化学习缺乏控制理论结构的问题，提出了基于深度Koopman算子的学习预测控制框架。
◆提出深度Koopman预测器，以数据驱动方式将非线性不确定车辆动力学提升至可解释的线性可观空间。
◆通过滚动时域Actor-Critic学习，在每个预测区间生成闭环状态反馈策略，突破了传统MPC仅计算开环序列的局限。
◆针对非凸环境约束，构建障碍物凸局部代理表示并定义势场函数，将其与梯度直接嵌入Actor-Critic结构实现安全感知策略学习。
仿真与实车实验表明，该框架在多样避障场景中的安全性、计算效率和舒适性均优于基准方法。</td></tr>
<tr><td>2026-06-05</td><td>Lane Change Trajectory Planning for Personalized Driving Comfort and Mobility Efficiency<br><a href='http://arxiv.org/pdf/2606.06805'>论文</a></td><td>该论文针对换道轨迹规划中纵横向运动耦合及驾驶员个性化差异显著的问题,提出了一种神经网络驱动的轨迹规划方法,将三阶多项式轨迹生成器与学习模块相结合,能够在多样化驾驶条件下推断最优轨迹参数,从而同时兼顾驾驶舒适性与通行效率。通过代表性案例和蒙特卡洛仿真验证,该规划器在个性化数据充足时可实现个性化的舒适性与机动效率,在数据不足或不可获取的条件下也能保证轨迹的可行性。

核心贡献与创新点如下:

◆ 提出了融合三阶多项式轨迹生成器与神经网络学习模块的换道轨迹规划框架,实现了纵横向耦合运动的个性化参数推断。

◆ 设计了共享主干加双分支头部的网络结构,一个分支负责保证全工况下的基础可行性,另一个分支负责捕获驾驶员对舒适性或通行效率的个性化偏好。

◆ 引入基于误差胜出逻辑回归的统计门控机制,实现头部之间的自适应切换,使规划器能够根据驾驶情境上下文动态选择合适的输出分支。

◆ 构建了在个性化数据稀缺或不可访问时仍能保证轨迹可行性的兜底机制,提升了方法在真实场景中的鲁棒性与适用性。

◆ 通过代表性案例与蒙特卡洛仿真系统验证了该方法在个性化舒适性、机动效率和工况适应性方面的综合优势。</td></tr>
<tr><td>2026-06-05</td><td>Path Planning Using Deep Deterministic Policy Gradient: A Reinforcement Learning Approach<br><a href='http://arxiv.org/pdf/2606.07855'>论文</a></td><td>本文针对威胁环境下自动驾驶车辆路径规划计算慢的问题，提出了一种基于深度确定性策略梯度的强化学习方法。该方法将威胁建模为圆形禁区，通过试错训练使智能体学习从当前状态到可行动作的直接映射以安全抵达目标。
◆设计了包含终点吸引场、障碍物排斥场和控制能量惩罚的三部分奖励函数，有效引导智能体规划出倾向直线的安全路径。
◆通过训练寻找能保证安全到达目的地的最大起始点集合，从而为任务规划提供关键的事前可行性评估信息。
◆与传统伪谱最优控制方法对比表明，该方法在生成有效路径的同时计算速度显著更快，更适合实时应用场景。</td></tr>
<tr><td>2026-06-04</td><td>Waypoints Matter: A Systematic Study for Sampling-Based Trajectory Planning<br><a href='http://arxiv.org/pdf/2606.06366'>论文</a></td><td>本文首次将采样式轨迹规划中的路标点放置视为一等设计变量，系统研究了其对规划器性能的直接影响。在固定轨迹基元和候选预算的条件下，研究跨越449种配置和五种地图，对比了三种路标点放置策略。
◆揭示了路标点标称间距是驱动规划性能的核心因素，仅放置方式的差异就会导致规划可靠性产生巨大变化。
◆发现调优后的均匀采样性能优于RDP*变体，且本文提出的曲率条件分配策略在复杂道路下具有稳定优势。
研究结论指出间距应作为首要调优参数，几何感知策略仅适用于曲率密集且可行性受限的特殊走廊区域。</td></tr>
<tr><td>2026-06-04</td><td>3D Underwater Path Planning via Generative Flow Field Surrogates<br><a href='http://arxiv.org/pdf/2606.06077'>论文</a></td><td>该论文针对自主水下航行器(AUV)在前进母船尾部进行发射与回收时需穿越复杂三维螺旋桨尾流的路径规划难题,提出用条件生成对抗网络(cGAN)替代高保真RANS CFD仿真,从而在保证流场精度的同时满足机载实时计算需求。作者将生成式流场代理模型嵌入三维能量加权A*路径规划框架,并在四种环境感知层级(均匀流、真实CFD、PatchGAN、2D3DGAN-SA)下对550种流况、共19800条轨迹进行了系统性基准测试,验证了生成模型在能量节省与高速尾流核心规避方面的实用价值。

◆ 首次将两种cGAN架构(正则化PatchGAN和带自注意力的2D3DGAN)作为RANS CFD的即插即用代理,集成进三维水下路径规划框架。
◆ 提出分层生成管线,仅依靠标量工况输入即可合成完整的128³体素三维流场,推理时间仅28-146微秒,相较RANS的数小时计算实现数量级加速。
◆ 设计三维能量加权A*规划器,可直接利用生成的流场体积进行能量最优路径搜索,适配边缘计算设备部署。
◆ 首次系统量化了cGAN预测流场在三维海事机器人路径规划下游任务中的实际价值:完整CFD感知可降低5.7-12.5%能耗、减少最高77.8%的高速尾流核心穿越,而cGAN代理可恢复其中约45-60%的收益。
◆ 建立了覆盖550种流况、19800条独立轨迹的大规模对比评测基准,为生成式流场模型在水下机器人规划中的应用提供了量化证据。</td></tr>
<tr><td>2026-06-04</td><td>Sample-efficient Low-level Motion Planning for Robotic Manipulation Tasks via Zero-shot Transfer Learning<br><a href='http://arxiv.org/pdf/2606.06041'>论文</a></td><td>本文针对复杂机器人操作任务中样本高效的交叉熵方法性能受限的问题，提出了一种结合零样本迁移学习的iCEM+TL框架。
◆提出iCEM+TL框架，通过将简单上游任务的关键iCEM参数迁移至复杂下游任务，实现知识的高效重用与零样本引导规划。
◆引入奖励重设计机制，针对堆叠和货架放置等复杂操作进行任务分解，优化了特定任务的奖励函数以提升规划性能。
仿真实验表明，该框架在复杂场景下的任务成功率最高提升了23%。
在真实Franka Emika机器人堆叠任务上的进一步验证，证明了该方法的实际部署可行性。</td></tr>
<tr><td>2026-06-04</td><td>IDDMBSE: Integrating Data-Driven and Model-Based Systems Engineering for Trusted Autonomous Cyber-Physical Systems<br><a href='http://arxiv.org/pdf/2606.06727'>论文</a></td><td>该论文针对自主信息物理系统(CPS)开发中基于模型的系统工程(MBSE)与数据驱动的机器学习/人工智能方法长期割裂的问题,提出了一种名为IDDMBSE的集成方法论。该方法在传统MBSE的V型流程每一步骤中嵌入数据驱动闭环,以SysML、自主性栈以及混合式架构为支撑,并通过一套开源工具链加以实现,最后在受争议地形的Isaac Sim测试场中以可信自主地面机器人为案例验证了全生命周期的有效性。

核心贡献与创新点如下:

◆ 首次提出IDDMBSE方法论,在严谨的MBSE V型流程的每个环节原生融入数据驱动循环,填补了MBSE与ML/AI在系统工程层面缺乏统一方法的空白。

◆ 开发了PERFECT工具,可将SysML系统架构自动映射为可执行的ROS自主性栈,实现大规模性能评估。

◆ 提出TRADES-X工具,将设计空间探索分解为&quot;基于模型的优化&quot;与&quot;数据驱动评估&quot;两阶段,实现混合式权衡分析。

◆ 构建了VERITAS统一保证工作流,将形式化验证、数据驱动验证与运行时验证整合到单一框架中。

◆ 以可信自主地面机器人为完整案例,涵盖传感器选型、风险敏感路径规划、行为树任务验证、基于共形预测的鲁棒感知及多机器人协同保证等环节,并开源了配套的Isaac Sim测试场。

◆ 展望了基于SysML v2/KerML重构IDDMBSE的路径,以实现语言原生的可组合性与更紧密的ML/AI集成。</td></tr>
<tr><td>2026-06-03</td><td>DiffSlack: Learning under Nonlinear Inequality Constraints via Learnable Slack Variables<br><a href='http://arxiv.org/pdf/2606.05247'>论文</a></td><td>本文提出DiffSlack可微投影层，解决神经网络中非线性不等式约束难以强制执行的问题。
◆将不等式转化为带可学习松弛变量的等式，并作为网络输出预测，为阻尼高斯-牛顿投影提供数据驱动的热启动。
◆设计可微投影层，将原始预测映射至增广可行流形，同时保持端到端可微性。
◆引入两阶段课程学习策略，稳定训练并提升约束满足能力。
在含200个非线性约束的路径规划中，该方法在同等预算下取得更高成功率与约束满足度，并降低对监督质量的敏感性。
实车实验进一步验证了其生成轨迹的可执行性与工程实用价值。</td></tr>
<tr><td>2026-06-03</td><td>Joint 3D Trajectory and Power Allocation for HAPs-UAV Bistatic ISARAC in Low-Altitude Networks<br><a href='http://arxiv.org/pdf/2606.04600'>论文</a></td><td>本论文提出了一种高海拔平台与无人机协同的双基地集成合成孔径雷达与通信系统架构，其中HAPs负责广域通信与波形发射，UAV利用机动性近距离接收回波以实现高分辨率SAR成像。核心贡献在于联合优化了UAV的三维飞行轨迹与系统的功率分配，以最大化地面用户的总通信速率，同时满足SAR成像的信噪比与分辨率约束、总能量预算以及无人机动力学限制。为解决这一非凸问题，作者开发了交替优化框架：功率分配子问题可得到闭式水填充解，而轨迹优化子问题则通过逐次凸近似和凸差规划高效求解。仿真结果证实了该方法在低空网络中同时保障连续通信覆盖与高精度感知的有效性。

◆ 创新性地将HAPs与UAV结合构成双基地ISARAC系统，兼顾广域覆盖与近距离高分辨率感知优势。
◆ 首次联合考虑通信速率最大化与SAR成像质量约束，建立了三维轨迹与功率分配的协同优化模型。
◆ 提出基于交替优化、逐次凸近似和凸差规划的求解算法，功率分配获得闭式解，显著降低了计算复杂度。</td></tr>
<tr><td>2026-06-03</td><td>Discussion on the Physics Problem of a Boat Crossing a River<br><a href='http://arxiv.org/pdf/2606.04515'>论文</a></td><td>该论文研究了非均匀流速下的船只过河问题，构建了恒定水流、线性分布和偶次幂函数分布三种流速模型。
◆构建了包含偶次幂可调参数的多模型分析框架，有效模拟真实河流复杂的流速分布场景。
◆结合矢量叠加与微积分方法，推导出固定航向角下船只空间轨迹的解析表达式。
◆引入拉格朗日乘数法构建约束优化模型，求得了满足到达正对岸边界条件的最短时间最优航向角解析解。
这些研究成果为内河船舶智能导航系统的路径规划提供了重要的理论支持。</td></tr>
<tr><td>2026-06-03</td><td>Think Fast and Far: Long-Horizon Online POMDP Planning via Rapid State Sampling<br><a href='http://arxiv.org/pdf/2606.04355'>论文</a> | <a href='https://github.com/RDLLab/ROPRAS3}'>代码</a></td><td>本文提出了一种名为ROP-RAS3的新型近似在线POMDP求解器，旨在解决长视野部分可观察马尔可夫决策过程难以求解的问题。
◆引入极快的基于采样的运动规划技术来采样状态空间并在线生成多样化的宏动作，利用这些宏动作引导信念空间采样并推断高质量策略，免去了现代求解器必须穷举动作空间的根本限制。
◆在理论收敛性上，该方法收敛到近优参考解的速率取决于采样动作的数量而非动作空间的大小，从而大幅提升了规划效率。
实验表明，在长达3000步前瞻和35维状态空间的复杂混合空间长视野POMDP中，该方法的成功率成倍超越其他最先进方法。
此外，该方法的实用性也在真实物理机器人演示中得到了成功验证。</td></tr>
<tr><td>2026-06-02</td><td>Multi-Agent Next-Best-View Optimization for Risk-Averse Planning<br><a href='http://arxiv.org/pdf/2606.04158'>论文</a></td><td>本文提出了一种分布式风险感知多智能体下一最佳视角框架，用于未知环境下的安全路径规划，克服了集中式方法通信开销大与可扩展性差的缺陷。
◆构建了基于局部三维高斯溅射地图的分布式协作机制，通过共识ADMM求解器联合最大化轨迹遮罩区域的预期信息增益。
◆设计了极低通信开销的交互策略，各机器人仅需交换候选视角、轨迹描述符与标量信息增益值，无需共享原始传感器数据。
◆提出了基于平均风险价值的碰撞风险建模方法，利用局部地图评估风险并动态调整遮罩半径与路径评分，确保轨迹安全性。
◆多规模团队实验表明，该分布式方案在地图质量与安全性能上逼近集中式基线，同时将通信量降低了数个数量级。</td></tr>
<tr><td>2026-06-02</td><td>AgenticDiffusion: Agentic Diffusion-based Path Planning for Vision-Based UAV Navigation<br><a href='http://arxiv.org/pdf/2606.04111'>论文</a></td><td>本文提出AgenticDiffusion框架，解决了室内无人机导航中单视角观察导致的遮挡和全局场景推理受限问题。
◆提出了多视角无人机导航框架，将语言引导推理、开放词汇目标定位、视觉扩散规划与NMPC控制整合于统一管线。
◆设计了基于第一人称视角和俯视图的自适应视角选择机制，在轨迹执行前确定最具信息量的视角并生成任务计划。
◆开发了视角特异性的扩散规划器，利用互补视角生成轨迹，减少了重复目标探索并提升了复杂室内环境下的导航效率。
实验表明，该框架在四类真实场景的四十次试验中，实现了百分之八十的整体任务成功率和百分之百的轨迹生成成功率。</td></tr>
<tr><td>2026-06-02</td><td>Neural Navigation Functions for Zero-Shot Generalizable Motion Planning<br><a href='http://arxiv.org/pdf/2606.03756'>论文</a></td><td>本文提出了神经导航函数，这是一种能够在未知环境几何中实现零样本迁移的学习型反应式导航函数。
◆将数据驱动的适应性与结构化椭圆规划器结合，在学习目标的同时通过构造保留规划器结构。
◆将内在拉普拉斯特征映射为局部偏微分方程系数，通过求解边界值问题生成全局一致的值函数。
◆通过构造保证生成的策略无碰撞、具有单调下降性，且在目标处具有全局最小值。
◆在任何参数设置下，该方法都具有线性可解的最优控制解释。
实验表明，该方法实现了强大的零样本迁移，性能比直接预测值函数的规划器提升了高达五倍。</td></tr>
<tr><td>2026-06-02</td><td>SPADE: Sketch-guided Path Planning Augmented with Diffusion Experts<br><a href='http://arxiv.org/pdf/2606.03512'>论文</a></td><td>针对现有模仿学习路径规划方法在未见环境中泛化能力有限及演示收集鲁棒性低的问题，本文提出了SPADE框架。
◆基于ROS 2构建了一款全面改进的标注工具，提升了专家演示数据收集的鲁棒性。
◆提出了一种新颖的训练策略，将基于扩散模型的增强技术集成到基线行为克隆模型中。
实验表明，该方法的绝对位姿误差和弗雷歇特起始距离分别降低了39.1%和33.5%，且可训练参数减少了93.8%。
此外，该框架在实现扩散级别泛化能力的同时，成功保留了最先进模型的实时边缘计算特性。</td></tr>
<tr><td>2026-06-02</td><td>Grasp-Then-Plan with Failure Attribution: A Closed Two-Stage Framework for Precise and Generalizable Robotic Manipulation<br><a href='http://arxiv.org/pdf/2606.03385'>论文</a></td><td>本文针对机器人操作中抓取与运动规划耦合导致失败源模糊和低效试错的问题，提出了GTP-FA闭环两阶段操作框架。
◆创新点一是学习失败归因模型，能泛化至未见抓取并生成稳定的失败模式分布以指导诊断优化。
◆创新点二是在抓取模块注入任务级先验和风险惩罚，抑制不稳定或任务不兼容的抓取候选。
◆创新点三是在规划模块针对高风险初始状态进行定向数据收集和微调，解决真正的规划瓶颈。
仿真与真实实验表明，该框架在强化学习、模仿学习、扩散策略和VLA等多种基线设置下均显著提升了任务成功率。</td></tr>
<tr><td>2026-06-02</td><td>Bridging Predictive Uncertainty and Safe Action: Sample-Conditioned Differentiable Planning for Autonomous Driving<br><a href='http://arxiv.org/pdf/2606.03296'>论文</a></td><td>本文提出一种新颖的样本条件可微分规划框架，成功弥合了高表达不确定性建模与可解释安全运动规划之间的脱节。
◆提出基于条件扩散模型的样本条件规划机制，将生成的多样化未来轨迹样本直接输入可微分规划器，避免压缩为单一结果或依赖黑盒架构。
◆引入经验条件风险价值尾风险约束显式缓解预测不确定性，使规划器能优化出对罕见且安全关键交互具有鲁棒性的物理可解释轨迹。
◆提出场景上下文的有向图表示方法，显著提升了预测效果与计算效率。
在Waymo和Argoverse 2数据集上的广泛开闭环评估表明，该框架在安全性、效率和舒适度上均显著超越现有基线。</td></tr>
<tr><td>2026-06-01</td><td>Evaluating Real-World Generalizability of Algorithm Selection Models<br><a href='http://arxiv.org/pdf/2606.02016'>论文</a></td><td>本文系统性地研究了算法选择模型在合成与真实世界优化景观之间的泛化能力。研究跨越了学术基准与实际应用场景，揭示了现有模型在跨域迁移时的真实表现。
◆构建了涵盖BBOB和CEC学术基准以及机器人轨迹优化和无人机路径规划等真实问题集的综合评估框架。
◆通过系统的跨基准评估，深入分析了AS模型的跨域迁移表现，明确识别出泛化成功与失效的具体场景。
◆揭示了当前AS方法在现实特定领域应用中面临的挑战，为开发更可靠且广泛适用的真实世界优化AS系统提供了重要指导。</td></tr>
<tr><td>2026-06-01</td><td>Motion Planning in Dynamic Environments: A Survey from Classical to Modern Methods<br><a href='http://arxiv.org/pdf/2606.02677'>论文</a></td><td>本文对2015至2025年间138篇动态环境运动规划文献进行了全面综述，弥补了现有研究多关注静态环境的不足。
◆系统梳理了从经典到学习的各类方法，将其划分为采样、图搜索、模型预测控制、学习及传统局部规划五大类别。
◆深入探讨了动态感知在运动规划中的关键作用，涵盖了利用相机、激光雷达和事件传感器检测与建模移动障碍物的技术。
◆重点剖析了动态环境特有的挑战，如预测不确定性、人机交互和机器人冻结问题，并详细评估了各方法的原理与优劣。
该综述为研究人员构建了理解动态环境下运动规划方法的结构化参考框架。</td></tr>
<tr><td>2026-05-31</td><td>Mean-Field Diffuser: Scaling Offline MARL to Thousands of Agents<br><a href='http://arxiv.org/pdf/2605.30190'>论文</a></td><td>这篇论文针对扩散式规划在多智能体离线强化学习中因联合轨迹空间维度爆炸而难以扩展的问题,提出了MF-Diffuser框架,将轨迹规划提升至轨迹分布的Wasserstein空间,利用混沌传播性质,仅用少量代表性智能体即可刻画整个种群的动态,从而支撑千级以上规模的离线多智能体强化学习。论文同时建立了端到端的次优性理论界,并通过三个均值场基准实验验证了方法在大规模和次优数据场景下的显著优势。

核心贡献和创新点如下:

◆ 首次将扩散规划提升至轨迹分布的Wasserstein空间,借助混沌传播性质用小规模代表性智能体子集刻画全种群动态,突破联合空间维度灾难,使离线MARL可扩展至上千智能体。

◆ 提出价值加权的混沌熵目标函数,在保证生成保真度的同时实现回报最大化,协调了扩散模型的生成质量与策略优化目标。

◆ 设计了分层的由粗到细策略,在去噪过程中渐进式扩展智能体种群规模,提升大规模场景下的生成效率与稳定性。

◆ 给出包含四个可解释项的端到端次优性理论界,证明均值场近似误差以O(H²/√N)规模下降,且离线分布偏移不随种群规模N增长,理论上保证生成策略为近似均值场纳什均衡并给出显式收敛保证。

◆ 在涵盖阶段博弈、序列动态与对抗团队竞争的三类均值场基准上取得多数最优表现,在次优离线数据和N≥10³的极端规模下增益最为显著。</td></tr>
<tr><td>2026-05-31</td><td>Learning-based Directed Graph Abstraction of Combinatorial Spaces for Order-Preserving Search in Mixed-Combinatorial Nonlinear Optimization<br><a href='http://arxiv.org/pdf/2606.01425'>论文</a></td><td>针对混合组合非线性规划问题中传统编码方式引入伪关系、增加维度且需额外约束的缺陷，本文提出了一种基于学习的组合空间抽象方法。
◆首次提出使用边场图网络对组合空间进行结构化抽象，将无向全连接组合图映射为指示改进方向的有向图。
◆将该方向感知的抽象模型作为推荐系统，在仅搜索连续变量的优化框架中检索最适组合，提升了检索的可扩展性与可解释性。
实验将该方法与粒子群和遗传算法求解器结合，在三个基准非线性问题上进行了测试。
结果表明，相比使用索引组合的基线求解器，基于图神经网络的推荐系统在平均最优值和鲁棒性上均取得更优表现。</td></tr>
<tr><td>2026-05-31</td><td>ActMVS: Active Scene Reconstruction with Monocular Multi-View Stereo<br><a href='http://arxiv.org/pdf/2606.01367'>论文</a> | <a href='https://github.com/TrickyGo/ActMVS'>代码</a></td><td>该论文提出了ActMVS，这是首个仅依赖单目视觉的主动场景重建框架，解决了传统方法依赖深度传感器增加成本，以及现有单目方法无法实时提供全局一致稠密深度的问题。
◆提出视图因子图构建方法，用于指导多视图立体的深度预测。
◆引入全局深度优化机制，实现在线生成高质量且全局一致的稠密深度图。
这些创新使单目机器人或无人机能够实时维护高置信度的占据地图，实现安全的无碰撞轨迹规划与自主重建。
实验证明该方法性能可媲美基于RGB-D的方案，极大提升了单目视觉的空间智能与实用性。</td></tr>
<tr><td>2026-05-31</td><td>Make Your VLA More Robust Without More Data By Interleaving Motion Planning<br><a href='http://arxiv.org/pdf/2606.00985'>论文</a></td><td>视觉-语言-动作模型在长视距任务中因目标难以维持和误差累积导致表现不佳，单纯增加微调数据无法解决此问题。为此，本文提出无需额外训练的运动规划与VLA交织框架MPVI。
◆将基于模型的运动规划与VLA结合，利用开放词汇目标检测、前沿探索与运动规划，实现在杂乱场景中对远处或遮挡目标的定位与导航。
◆设计了基于视觉语言模型的完成度检查与本体感受触发机制，有效解决模块间可靠切换的难题。
实验表明，该方法在BEHAVIOR-1K基准上，任务进度相比顶级端到端基线提升了113%。这充分证明了MPVI框架在不增加数据前提下提升VLA鲁棒性的显著效果。</td></tr>
<tr><td>2026-05-30</td><td>Generative Multi-Robot Motion Planning via Diffusion Modeling with Multi-Agent Reinforcement Learning Guidance<br><a href='http://arxiv.org/pdf/2606.00933'>论文</a></td><td>本文提出了一种结合去中心化生成式轨迹规划与多智能体强化学习引导的协调框架，用于解决多机器人运动规划中的交互与可扩展性难题。
◆利用仅在单智能体数据上训练的扩散模型为每个机器人独立生成可行且多样的候选轨迹，保留了去中心化规划的可扩展性。
◆通过多智能体强化学习训练的集中式价值函数引导反向扩散过程，采用基于梯度的策略和指数倾斜公式，将去噪分布偏向具有更高多智能体期望回报的轨迹。
◆无需进行集中式联合规划或重新训练生成模型，即可实现具备交互意识的轨迹生成，有效减少智能体间冲突。
实验表明，该价值引导规划将四机器人环境中的智能体干扰率从55.4%降至41.8%，成功在保持去中心化扩展性的同时实现了有效协调。</td></tr>
<tr><td>2026-05-30</td><td>From Cues to Horizons: Dynamic Risk Horizon Profiling for Trajectory Prediction<br><a href='http://arxiv.org/pdf/2606.00857'>论文</a> | <a href='https://github.com/bilab-nyu/RHP'>代码</a></td><td>本文提出了一种名为风险水平剖面（RHP）的模块，通过连续可学习的势场模型来动态刻画未来时空的风险分布，从而将风险演化与不确定性引入轨迹预测任务，显著提升了预测精度与泛化能力。该方法在highD高速公路和SHRP2城市道路两个不同场景的数据集上进行了评估，相较基线实现了5秒RMSE降低25.0%和5秒minFDE降低29.1%的显著效果，证明了其对短时和长时预测的有效性以及跨场景的鲁棒性。该工作为自动驾驶车辆路径规划和战略选择提供了更贴近人类驾驶认知的风险感知支持。

◆ 首次提出将未来风险水平剖面作为动态可学习的特征，而不仅仅将过去风险作为辅助信号，实现了对风险时空演化的显式建模。
◆ 采用连续可学习的势场模型来量化车辆间时空接近度，避免了传统离散风险度量的局限性，支持自适应识别关键风险时刻。
◆ 在highD和SHRP2两个不同驾驶环境数据集上验证了方法的通用性，并在近碰撞、碰撞等多样化风险场景中均取得显著性能提升。</td></tr>
<tr><td>2026-05-30</td><td>A Framework for Motion Planning with Temporal Logic Precedence Specifications via Augmented Graphs of Convex Sets<br><a href='http://arxiv.org/pdf/2606.00842'>论文</a></td><td>本文提出了一种运动规划框架，能够在避障的同时满足由信号时序逻辑片段表达的逻辑先后约束。该框架对包含障碍物、钥匙和门的环境进行建模，其中获取钥匙可解锁对应门并可能开辟通往目标的更短路径。
◆基于对自由空间的精确凸分割，构建了增广凸集图，其分层结构精确编码了钥匙与门的先后逻辑。
◆通过在增广凸集图中寻找最短路径，实现了同时选择最优钥匙收集序列与计算最优连续轨迹。
该方法在有限的贝塞尔曲线参数化下提供了精确解，有效解决了具有时序先决条件的复杂运动规划问题。</td></tr>
<tr><td>2026-05-30</td><td>ROG-Grasp: Root-Oriented Geometry for Robotic Grasping and Placement<br><a href='http://arxiv.org/pdf/2606.00449'>论文</a></td><td>本文提出了ROG-Grasp框架，这是一种基于几何的机器人抓取与放置方法，通过RGB-D感知从农产品根部表面几何形状估计其朝向，解决了农业加工中的朝向感知操作问题。
◆提出结合YOLO根部检测器与点云平面拟合推断根部法线，从而实现稳定的抓取姿态生成。
◆设计了受朝向约束的笛卡尔运动规划，确保农产品能以一致的构型被放置。
◆与视觉语言动作策略相比，该方法在抓取可靠性和准确性上更优，且执行速度更快。
在番茄和洋葱的实验中，该框架在孤立与杂乱场景下均展现出高成功率和稳定的执行时间。
这些结果证明了几何驱动感知在实际朝向控制操作任务中的有效性和实用性。</td></tr>
<tr><td>2026-05-29</td><td>LiftNav: Path Planning via Semantic Lifting in TSDF-Guided Gaussian Splatting<br><a href='http://arxiv.org/pdf/2605.31376'>论文</a></td><td>本文提出了LiftNav混合导航框架，解决了传统TSDF缺乏语义和高斯溅射几何软导致避障不精确的问题。该框架基于TSDF与高斯溅射双地图构建，实现了可靠的碰撞避障与物体级理解。
◆设计了基于YOLO检测与TSDF三维提升的实时管线，无需密集三维嵌入即可实现灵活的语义导航。
◆引入了基于铰链损失的碰撞惩罚机制，有效提升了轨迹的平滑度与安全性。
◆结合B样条轨迹优化，在仿真实验中相比现有基线实现了百分之百的轨迹可行率和更短的路径。</td></tr>
<tr><td>2026-05-29</td><td>Haptic Sorter: A Unified Planning Framework for Online Shape Estimation and Real-Time Pose Inference<br><a href='http://arxiv.org/pdf/2605.31352'>论文</a></td><td>本文针对机器人操作中物体形状与姿态先验未知及传感器遮挡问题，提出了一个融合触觉感知、建模与操作规划的统一几何框架。
◆引入贝叶斯优化指导触觉探索以推断物体形状，并利用超椭圆近似几何边界。
◆自适应地构建编码物体几何的操作势函数，用于准静态机器人与物体交互。
◆提出基于模型预测和触觉反馈的在线常微分方程，实现物体实时姿态推断。
该框架在二维机器人分拣任务的仿真与真实多臂平台上进行了验证，证明了其在不同几何形状下的鲁棒性与泛化能力。</td></tr>
<tr><td>2026-05-29</td><td>AR Forcing: Towards Long-Horizon Robot Navigation World Model<br><a href='http://arxiv.org/pdf/2605.31314'>论文</a></td><td>该论文指出了基于扩散的机器人导航世界模型中，并行监督训练与自回归推理间的分布偏移导致长程预测不稳定的问题。为此，论文提出了AR Forcing自回归训练策略来消除这一偏差。
◆将标准扩散损失整合进自回归训练循环，模型每步利用自身预测更新上下文并优化单步噪声预测，使其在训练时显式暴露于推理状态分布。
◆无需引入额外判别器或分布匹配损失，完全保留原始扩散框架与采样器，方法简单且极易集成。
◆在多个导航数据集上的实验表明，该方法显著提升了长程导航中图像生成的一致性与轨迹预测精度，增强了模型在复杂及未知环境下的鲁棒性。</td></tr>
<tr><td>2026-05-29</td><td>DriveMA: Driving Vision-Language-Action Models with verifiable Meta-Actions<br><a href='http://arxiv.org/pdf/2605.31271'>论文</a></td><td>本文提出DriveMA框架，旨在解决驾驶视觉语言动作模型中语言与动作间的鸿沟问题，并在Waymo等数据集上取得了最先进的端到端规划性能。
◆提出可验证的元动作，将未来自车运动转化为紧凑的语言域意图，并可通过轨迹标注管线构建以及基于规则的投影进行验证。
◆引入动作中心的监督训练，有效利用元动作的可验证性来指导模型学习。
◆设计数据高效的回合级信用分配强化学习框架，通过密集奖励与精确信用分配，显式对齐高级决策与低级轨迹规划。
实验结果表明，即使是简单的元动作接口，只要具备可验证性并针对语言动作对齐进行优化，即可实现卓越的自动驾驶规划效果。</td></tr>
<tr><td>2026-05-29</td><td>Trajectory Planning for Non-Communicating Mobile Robots using Inverse Optimal Control<br><a href='http://arxiv.org/pdf/2605.30906'>论文</a></td><td>该论文提出了一种新颖的轨迹规划与预测组合算法，以解决非通信移动机器人避障场景下的高效交互问题。
◆利用逆最优控制方法，基于观测到的历史轨迹来估计所有机器人的未知目标状态。
◆引入视角转换机制，每个机器人从其他机器人视角出发进行自我预测，并结合估计目标状态求解联合预测问题。
◆将联合预测结果直接融入自身的轨迹规划中，实现预测与规划的深度耦合。
仿真实验表明，在2至8个机器人的场景下，该方法使所有机器人到达目标的中位耗时缩短了9.8%。
同时，该算法确保求解器始终能成功找到规划或预测问题的解，彻底避免了无解情况的发生。</td></tr>
<tr><td>2026-05-29</td><td>Coupling Language Models with Physics-based Simulation for Synthesis of Inorganic Materials<br><a href='http://arxiv.org/pdf/2606.00315'>论文</a></td><td>机器学习虽能提出新型无机材料，但复杂的物理过程和计算工具的缺乏使得合成规划极具挑战。本文提出了一个新型混合框架，通过结合热力学数据库与简化动力学模型来评估大语言模型在无机合成规划中的表现。
◆将大语言模型与基于物理的模拟相耦合，构建了能够近似真实合成条件的评估框架。
◆通过对比经典路径规划算法，揭示了大语言模型的隐式先验知识能够生成更具可行性的合成策略。
该研究以铌氧系统为案例，突显了在复杂合成问题中大语言模型隐式先验的独特价值，为无机材料合成规划提供了新思路。</td></tr>
<tr><td>2026-05-28</td><td>Multi-Robot Box Transport over Different Surfaces with Decentralized Role-based Proportional Control<br><a href='http://arxiv.org/pdf/2605.26430'>论文</a></td><td>该论文提出了一种名为R2P2的异步分散式任务与运动规划方法，解决多机器人在不同倾斜度与摩擦力表面上协同运输箱子的挑战。
◆提出去中心化架构，免除机器人间的通信同步与共识需求，有效规避单点故障。
◆设计基于操作模式动态分配角色的机制，根据旋转或平移需求赋予机器人推、支撑或阻止等角色。
◆融合基于规则的控制与比例速度控制，机器人仅需观测自身与箱子的位置及朝向即可执行动作。
◆方法在多变的地形摩擦、倾斜度及箱子质量场景中展现强泛化能力，成功率优于传统虚拟领导者跟随者方法。
◆通过六台机器人的仿真测试与四台Turtlebot的实物实验，充分验证了该策略的有效性与实用性。</td></tr>
<tr><td>2026-05-28</td><td>A Radius-Sensitive Approximation Algorithm for Connected Submodular Maximization<br><a href='http://arxiv.org/pdf/2605.30053'>论文</a></td><td>本文研究连通子模最大化问题(CSM)及其有向版本(DCSM)和有向有根版本(DRCSM)。该问题在无线网络部署、路径规划、疫情传播和癌症基因组研究等领域具有重要应用。论文针对以最优解半径r为参数的近似比进行了显著改进,突破了此前最优的Ω(1/r)和Ω(1/√k)近似界。作者提出了一个多项式时间框架,对于(有向)CSM达到Ω(ε³/r^ε)的近似比,对于DRCSM达到Ω(δε³/r^ε)的双准则近似,其中规模约束最多被违反1+δ倍。

◆ 首次将CSM的近似比从Ω(1/r)改进到Ω(ε³/r^ε),由于r≤k,该结果同时优于以k为参数的现有最优界Ω(1/√k)。

◆ 提出核心算法GreedyRadius,可将任意以k为参数的双准则近似算法转化为以r为参数的同等近似比算法(至多相差常数因子),具有良好的通用性和可扩展性。

◆ 为DRCSM设计了灵活的双准则近似框架,允许在近似比与规模约束违反程度之间进行可调节的权衡(δ可在[1/k,1]之间取值)。

◆ 将算法框架统一推广到无向、有向以及有向有根三种CSM变体,扩展了问题的适用范围。

◆ 引入参数ε实现近似比的精细调控,为不同应用场景下的算法性能优化提供了理论基础。</td></tr>
<tr><td>2026-05-28</td><td>FLIP: Real-Time and Resilient Formation Planning for Large-Scale DIstributed Swarms via Point Cloud Registration<br><a href='http://arxiv.org/pdf/2605.29704'>论文</a></td><td>该论文提出了FLIP,一种面向大规模分布式无人机集群的实时、弹性编队规划方法,通过将编队位置分配问题转化为时空点云配准问题,实现了高性能且大规模的协同轨迹规划。核心思路是让每个智能体分布式地计算自身当前位置与所有其他智能体期望编队位置之间的匹配结果,从而获得最优编队位置序列(OFPS),并基于此优化协同编队轨迹。论文采用带有外点剔除机制的点云配准方法,有效阻止次优轨迹和失效智能体在协同网络中的传播扩散。最终通过120架无人机的大规模仿真验证了方法的有效性,并与SOTA方法进行了严格对比基准测试,展示了其优越性。

◆ 首次将最优编队位置序列(OFPS)计算问题创新性地转化为时空点云配准(PCR)问题,为大规模编队分配提供了全新求解范式。

◆ 提出基于带外点剔除的点云配准方法,可快速完成大规模编队位置匹配,显著降低计算复杂度。

◆ 设计了具有弹性的分布式协同机制,通过外点剔除阻断次优轨迹和失败智能体在协作网络中的扩散影响,提升集群鲁棒性。

◆ 实现了弹性、高效与分布式三者统一的轨迹规划框架,突破了传统方法在表示简化与全协作计算负担之间的权衡难题。

◆ 在120架无人机规模的仿真场景中验证了方法的可扩展性,并通过严格基准测试证明其相较于SOTA方法的显著优势。</td></tr>
<tr><td>2026-05-28</td><td>The Open Motion Planning Library 2.0<br><a href='http://arxiv.org/pdf/2605.29301'>论文</a></td><td>本文介绍了开放运动规划库(OMPL)的重大升级版本OMPL 2.0。OMPL自2008年首次发布以来,已成为运动规划领域的基石,提供了广泛的基于采样的最先进算法实现。经过近二十年的持续开发,该库不断扩展新的规划器、状态空间和问题表述,涵盖从渐近最优规划、惰性规划到约束运动规划及时序逻辑目标规划等多种功能。OMPL 2.0在此基础上进行了重大演进,旨在通过硬件加速实现实时运动规划,并与现代AI研究工作流无缝集成。论文同时回顾了OMPL与运动规划领域共同成长的历程,并讨论了该库对研究界的广泛影响。

核心创新点如下:

◆ 推出OMPL 2.0版本,作为运动规划库的重大演进,标志着该领域工具链的全新升级。

◆ 通过硬件加速技术实现实时运动规划能力,显著提升了规划效率与响应速度。

◆ 与现代AI研究工作流无缝集成,促进了传统运动规划方法与人工智能技术的深度融合。

◆ 持续扩展多样化的规划器与状态空间,涵盖渐近最优、惰性规划、约束运动规划以及基于时序逻辑目标的规划等前沿方向。

◆ 系统性回顾了OMPL与运动规划领域协同发展的历程,为后续研究提供了重要的参考与反思视角。</td></tr>
<tr><td>2026-05-27</td><td>Integrated Exploration-Aware UAV Route Optimization and Path Planning<br><a href='http://arxiv.org/pdf/2605.28654'>论文</a></td><td>本文提出了一个集成探索感知的无人机路线优化与路径规划框架，用于解决先验信息不确定且动态变化下的危险环境监测问题。核心贡献在于将有限的飞行续航合理分配于检查已知危险区域和探索未知信息区域之间。
◆将报告的危险源建模为不确定的感兴趣区域而非确认目标，要求无人机在检查报告区域的同时探索信息量大的区域。
◆通过在路线中增加辅助伪节点来提升空间覆盖率，并优化动态可行的B样条轨迹以进行局部探索。
◆引入在线重规划机制，根据无人机实时测量更新网格信念图，并在新信息和剩余预算允许时自适应调整后续轨迹。
实验表明，该方法在四十八种场景配置下表现优异，在线重规划比离线优化和直线遍历的平均KL散度降低效果分别提升了15.9%和48.6%。</td></tr>
<tr><td>2026-05-27</td><td>Accelerating Robot Path Planning via Connectivity-Preserving Region Proposal Network<br><a href='http://arxiv.org/pdf/2605.28362'>论文</a></td><td>本文提出连接性保持区域提议网络CP-RPN，通过预测紧凑且拓扑连通的候选区域，有效解决了传统采样算法延迟高和学习方法区域碎片化的问题，显著压缩了搜索空间。
◆设计了结合可变形注意力Transformer与反卷积解码器的分割模型，前者捕捉长距离依赖以获取全局连通性，后者保留细粒度空间细节。
◆提出融合交叉熵损失、连通性感知损失和基于持久同调的拓扑连续性损失的复合损失函数，从局部到全局严格保证预测掩膜的连通性。
◆构建基于高连通走廊区域的Voronoi图规划与局部A*回退相结合的机制，兼顾了路径规划的高效性与鲁棒性。
实验表明，该方法将候选区域缩减超60.13%，实现平均0.11秒的低延迟规划及99.60%的高成功率，表现优于传统算法。</td></tr>
<tr><td>2026-05-27</td><td>Deconstructing Spatial Complexity: Hierarchical Decomposition for LLM Spatial Reasoning<br><a href='http://arxiv.org/pdf/2605.28144'>论文</a></td><td>本文针对大语言模型空间推理能力不足的问题，提出了一种受分层强化学习启发的分层任务分解方法，引导模型通过识别关键中间状态和生成简化子环境来处理复杂任务。
然而，由于模型缺乏充足的空间先验，往往难以推导出最优中间状态从而导致次优分解。
◆提出MCTS引导的群组相对策略优化算法，通过将模型的先验预测概率与认知不确定性结合来改进UCT公式，从而优化中间状态生成并增强规划能力。
◆设计了更细粒度的优势函数，使模型能够有效学习并生成最优路径规划策略。
实验表明，该方法在导航、规划和策略游戏等空间任务上大幅提升了模型性能并达到业界最优，为具身智能等现实应用铺平了道路。</td></tr>
<tr><td>2026-05-26</td><td>TCBiRRT: Rapid Motion Planning for Tightly Coupled Dual-arm Space Manipulator Using Task-space Random Expansion<br><a href='http://arxiv.org/pdf/2605.27167'>论文</a></td><td>本文针对紧密耦合双臂空间机械臂在闭链约束下难以高效规划运动的问题，提出了任务空间约束双向快速扩展随机树算法TCBiRRT。
◆不同于传统高维构型空间方法，该算法直接在由操作物体位姿定义的任务空间内进行随机采样与节点扩展。
◆开发了任务空间节点扩展策略生成候选物体运动，并利用路径逆运动学算法将其映射为连续的关节路径。
◆将上述方法与双向RRT框架及重抓取机制相结合，高效实现了两棵随机树的连接。
实验表明，TCBiRRT在复杂轨道装配场景中不仅成功率显著更高，且规划时间相比现有算法提升了数个数量级。</td></tr>
<tr><td>2026-05-26</td><td>Provably Safe Motion Planning Under Unknown Disturbances<br><a href='http://arxiv.org/pdf/2605.26625'>论文</a></td><td>本文提出了一种针对受未知分布随机扰动影响的机器人系统的可证明安全的运动规划算法，将安全性要求表述为机会约束。该方法利用系统轨迹数据学习Wasserstein模糊管，以高置信度包含状态分布轨迹，并将其应用于生成满足约束的概率完备采样规划树。
◆通过学习多个低维模糊管代替单一高维模糊管，有效降低了规划保守性并提升了算法可扩展性。
◆设计了高效的基于强盗的有效性检查器，在不牺牲概率完备性的前提下显著提升了经验性能。
实验表明该算法能在严格安全阈值与杂乱环境中规划出有效路径，性能优于现有方法。</td></tr>
<tr><td>2026-05-26</td><td>AURA: Asymptotically Optimal Uncertainty-Robust Replanning Algorithm for Kinodynamic Systems<br><a href='http://arxiv.org/pdf/2605.27699'>论文</a></td><td>本文提出了AURA框架，这是一个针对运动学动态系统的渐近最优元规划器，解决了传统离线规划无法即时执行以及运动不确定性导致跟踪偏差的两大局限。
◆提出一种重规划方法，在执行过程中持续探索状态空间并优化轨迹，实现了渐近最优的在线规划。
◆引入优化过程，通过细化未来控制输入来减少跟踪误差，有效提升了运动不确定性下的执行精度。
该框架将重规划与控制优化相统一，使系统能够在发挥在线渐近最优规划优势的同时提高执行准确性。
仿真和真实世界的多系统实验表明，AURA在轨迹质量、跟踪精度和整体性能上均显著优于基线方法。</td></tr>
<tr><td>2026-05-26</td><td>Simulation-Informed Diffusion for Decentralized Multi-robot Motion Planning<br><a href='http://arxiv.org/pdf/2605.27697'>论文</a></td><td>本文针对去中心化多机器人运动规划中现有方法无法预测邻居未来行为的局限，提出了仿真信息扩散框架。该框架基于约束感知扩散模型，有效提升了对未来动态的预判与安全规划能力。
◆提出仿真与规划双阶段机制，先模拟邻居机器人的未来轨迹，再依据仿真结果与安全约束规划自身轨迹。
◆设计了一种最小通信方案，借助精确的邻居仿真，仅在高度拥挤时才触发必要的通信协调。
◆在扩展性与规划性能上取得突破，在108台机器人和160个障碍物的大规模场景中，其规划有效性与约束满足度显著优于基线方法。</td></tr>
<tr><td>2026-05-25</td><td>Fast-dDrive: Efficient Block-Diffusion VLM for Autonomous Driving<br><a href='http://arxiv.org/pdf/2605.23163'>论文</a></td><td>本文提出Fast-dDrive，一种用于自动驾驶的块扩散视觉语言动作模型，解决了自回归模型内存受限和全序列扩散模型逻辑泄漏的问题，实现了轨迹规划与高效推理的平衡。
◆提出块扩散机制，在语义单元内进行双向细化，同时跨单元保持严格的因果顺序。
◆针对结构化输出冻结结构标记为段落支架，并采用优先安全关键规划的段落感知训练策略。
◆引入支架投机解码，在保证自回归相当质量的同时显著提升推理吞吐量。
◆提出低开销测试时扩展方案，通过共享前缀KV缓存分叉并平均N个随机轨迹来抑制预测方差。
实验表明该模型在WOD-E2E和nuScenes上取得SOTA精度，结合SGLang实现12倍吞吐量提升，满足实时车载部署需求。</td></tr>
<tr><td>2026-05-25</td><td>Totoro$^+$: An Adaptive and Scalable Edge Federated Learning System<br><a href='http://arxiv.org/pdf/2605.26323'>论文</a></td><td>Totoro+ 是一个新型可扩展的边缘联邦学习系统,旨在支持大规模联邦学习应用在边缘网络上同时运行。其核心思路是利用基于分布式哈希表(DHT)的点对点(P2P)模型,将传统集中式联邦学习架构重构为完全去中心化的架构,为每个应用分配专属参数服务器,任何边缘节点都可担任协调者、聚合者、客户端选择器或工作节点等任意角色,从而显著提升系统的可扩展性与适应性。在500台Amazon EC2服务器上的真实实验表明,该系统能够随应用数量优雅扩展,将训练总时间加速1.2至14倍,在百万节点规模下实现O(log N)跳的模型分发与梯度聚合,并能高效适应实际边缘网络与节点动态变化。

核心创新点如下:

◆ 提出基于DHT的P2P去中心化架构,摒弃传统单一集中式参数服务器,为每个联邦学习应用配置独立参数服务器,从根本上突破了可扩展性瓶颈。

◆ 设计了具备位置感知能力的P2P多环结构,使节点组织能够感知网络拓扑,有效降低跨区域通信开销。

◆ 提出基于发布/订阅机制的森林抽象模型,用于高效支持模型分发与梯度聚合,实现对数级通信复杂度。

◆ 引入基于博弈论的路径规划模型,并理论上证明可达到ε近似纳什均衡,实现节点间通信路径的优化决策。

◆ 实现任意边缘节点可灵活承担多种角色的统一调度机制,使系统能够动态适应实际边缘网络环境与节点频繁加入退出的churn现象。</td></tr>
<tr><td>2026-05-25</td><td>Collaborative Threat-Aware Autonomy (CTAA)<br><a href='http://arxiv.org/pdf/2605.25741'>论文</a></td><td>本文提出协作威胁感知自主框架，解决无人机群在动态对抗武器交战区中单机易失效的根本挑战。
◆提出角色分化的多智能体协同轨迹规划框架，为机群分配主拦截、护航和诱饵三种角色，以提高团队任务成功率并管理个体威胁暴露。
◆基于碰撞球边界逃避零集推导出反应式引导律，该引导律考虑了最小转弯半径带来的机动性约束，引导车辆驶向兼顾安全与目标推进的最优航向。
◆通过角色分配与空间路线分离，引入概率冗余效应，即利用多条独立路径提升团队整体成功概率。
◆同时实现威胁饱和效应，即利用低优先级的护航和诱饵吸引敌方注意力，保障主车辆不受阻碍地通行。</td></tr>
<tr><td>2026-05-24</td><td>Performance Comparison of Classical and Neural Sampling Algorithms for Robotic Navigation<br><a href='http://arxiv.org/pdf/2605.25010'>论文</a></td><td>本文的核心贡献是在包含不同密度凸凹障碍物的环境中，系统评估并对比了RRT*、Neural RRT*和Neural Informed RRT*三种经典与神经采样算法的性能。
◆证明了神经引导规划器能显著提升路径质量，使路径缩短达14%，轨迹平滑度提升55%至75%。
◆明确了Neural Informed RRT*算法在路径长度和轨迹平滑度上具备最优的综合表现。
◆验证了AI引导采样策略对提升机器人和无人机导航可靠性与轨迹效率的有效性，即便存在计算时间的轻微增加。
该研究突显了AI在实时机器人路径规划应用中日益重要的作用。</td></tr>
<tr><td>2026-05-24</td><td>Convex-Neural RRT*: Fast and Reliable Learning-Guided Sampling for High-Quality Robot Path Planning<br><a href='http://arxiv.org/pdf/2605.25006'>论文</a></td><td>传统基于采样的机器人路径规划算法往往需要大量迭代才能获得高质量解，计算效率较低。本文提出了Convex-Neural RRT*算法，通过引入神经引导来预测高质量路径附近的有用航点区域。
◆从神经网络的预测结果中提取凸候选区域，使规划器能够集中探索几何相关区域。
◆在聚焦局部高价值区域探索的同时，保留了算法的全局探索能力，确保了寻路成功率。
实验表明，该算法相比神经引导变体和LTA*分别减少30%至75%和88%至98%的计算时间，且路径长度平均缩短约5%，在复杂环境中改善更大。该算法在计算效率和路径质量间取得了有效平衡，整体成功率超99%，非常适合对时间敏感的机器人导航任务。</td></tr>
<tr><td>2026-05-24</td><td>Scaling up Energy-Aware Multi-Agent Reinforcement Learning for Mission-Oriented Drone Networks with Individual Reward<br><a href='http://arxiv.org/pdf/2605.24992'>论文</a></td><td>本文针对无人机网络中动态环境和有限电池容量限制下的协同任务挑战，提出了一种能量感知的多智能体强化学习模型。该模型基于深度Q网络，有效提升了无人机群协作执行任务的效率。
◆设计了由任务执行进度和无人机剩余电量共同驱动的个体奖励函数，解决了传统共享奖励中信用分配不清的问题。
◆在环境规模扩展时表现出显著优势，对环境大小和智能体数量的变化具备更强的鲁棒性。
◆通过明确个体目标减少了任务执行步数，在保持高成功率的同时进一步提升了能量效率。</td></tr>
<tr><td>2026-05-24</td><td>Learning Transferable Motor Skills for Geometry-Aware Robotic Surface Tasks<br><a href='http://arxiv.org/pdf/2605.24881'>论文</a></td><td>本文针对机器人表面交互任务中几何规划与运动执行耦合导致可迁移性差的问题，提出了一种将几何运动规划与执行级专业知识解耦的模块化框架。
◆提出将专家行为表示为可解释的原子运动规则词汇表，如速度缩放和姿态偏移，从而系统性地修改几何规划的参考路径。
◆训练了多模态神经网络，能够从运动轨迹数据和CAD模型几何形状中联合推断出运动规则的参数。
◆通过解耦规划与执行并引入几何感知的规则推断机制，打破了传统模仿学习对特定训练几何形状的依赖。
在L形和窗形物体上的仿真实验表明，该模型能成功跨越不同拓扑结构提取速度和姿态规则，实现了运动技能的有效迁移。</td></tr>
<tr><td>2026-05-23</td><td>SparseWorld: Enhancing End-to-End Autonomous Driving via World Models with Sparse Scene Representation<br><a href='http://arxiv.org/pdf/2605.24354'>论文</a> | <a href='https://wryzju.github.io/SparseWorld/'>代码</a></td><td>本文提出了SparseWorld，一个轻量级的自动驾驶世界模型，通过稀疏场景表示仅预测关键场景布局，解决了现有稠密表示计算成本高和信息冗余的问题。
◆提出Sparse Dreamer模块，通过联合时间与空间注意力机制在潜空间中预测未来实例。
◆采用自回归展开方式预测未来地图元素和周围智能体，使模型学习驾驶场景的时间演变规律。
◆使运动规划器与预测的未来实例进行交互，从而捕捉更准确的运动模式并生成更具安全意识的轨迹。
实验表明，该方法大幅降低了碰撞风险，在nuScenes开环规划中达到0.05%碰撞率的领先水平，并在Bench2Drive闭环基准上显著超越基线方法。</td></tr>
<tr><td>2026-05-23</td><td>Sum of Costs Diffusion with Dynamic Guidance for Motion Planning<br><a href='http://arxiv.org/pdf/2605.24690'>论文</a></td><td>该论文针对机器人操作中的运动规划问题,提出了一种基于扩散模型的高泛化能力轨迹生成方法。该方法通过总碰撞代价的梯度引导去噪过程,从而生成无碰撞轨迹,并设计了动态选择梯度引导起始步骤的策略,以提升模型在多样化场景下的鲁棒性。实验在Mπnets数据集的多种测试设置中验证了方法的有效性,结果表明该方法相比现有竞争方法具有更强的泛化性能,取得了最佳表现,有效克服了传统方法和已有深度学习方法在跨场景适应性方面的不足。

核心创新点如下:

◆ 提出基于扩散模型的运动规划框架,利用总碰撞代价(Sum of Costs)的梯度对去噪过程进行引导,从而生成无碰撞的可行轨迹。

◆ 设计了一种动态确定梯度引导起始步骤的机制,而非采用固定起始点,使引导过程更加灵活并适应不同场景。

◆ 通过将碰撞代价信息融入扩散模型的采样过程,显著提升了模型在多样化环境下的泛化能力,克服了现有方法在跨场景适应性方面的局限。

◆ 在Mπnets数据集的多种测试设置中达到了同类方法中的最优性能,验证了该方法在复杂操作任务中的鲁棒性与有效性。</td></tr>
<tr><td>2026-05-22</td><td>MASt3R-Nav: WayPixel Navigation in Relative 3D Maps<br><a href='http://arxiv.org/pdf/2605.24111'>论文</a></td><td>本文提出了一种新型导航系统MASt3R-Nav，旨在解决传统3D地图依赖全局一致性而拓扑图缺乏几何理解导致导航能力受限的问题。
◆提出像素相对连通性的新型地图表示方法，在保证几何精度的同时免去了对全局几何一致性的需求。
◆通过图像对相对3D坐标系中的像素对应关系构建图像间连通性，并稀疏化图像内连通性进行全局路径规划，推导出WayPixel Costmap。
◆基于该密集像素级代价图训练条件控制器以预测轨迹，证明了相对几何的像素级条件变量比图像或对象级更准确。
该系统在四种仿真导航任务及真实世界演示中得到验证，展现了卓越的导航能力。</td></tr>
<tr><td>2026-05-22</td><td>How Many Training Samples Are Needed for the Inverse Kinematics Solutions by Artificial Neural Networks<br><a href='http://arxiv.org/pdf/2605.23583'>论文</a></td><td>本文研究了人工神经网络求解逆运动学问题时训练样本数量与预测精度之间的关系。研究通过关节型机械臂生成不同数量的关节位置数据对来训练前馈神经网络，并评估了其精度、收敛性与泛化能力。
◆建立了关联训练数据集大小与神经网络逆运动学求解器精度的数学框架。
◆揭示了数据效率的临界点，发现当训练样本超过125个时，继续增加数据量不再提升模型的近似精度与整体效率。
该研究为优化神经网络求解逆运动学的数据规模提供了实用指导，有效平衡了实际机器人应用中的计算成本与模型精度。</td></tr>
<tr><td>2026-05-22</td><td>Signal Temporal Logic Motion Planning via Graphs of Convex Sets<br><a href='http://arxiv.org/pdf/2605.23240'>论文</a></td><td>本文提出了一种结合定时自动机推理与凸集图的高效框架，用于解决信号时序逻辑规范下的连续时间运动规划问题。
◆将STL运动规划问题转化为凸集图上的最短路径问题，通过联合定时自动机与构型空间凸分解构建转移系统，从而生成满足逻辑时序规范、平滑性及速度约束的贝塞尔样条轨迹。
◆证明了该方法的可靠性并分析了计算复杂度，表明在自动机和凸分解固定时，其凸松弛随构型空间维度和贝塞尔度数呈多项式级扩展。
◆针对富有表现力的STL片段，利用专用模板和布尔组合开发了一种紧凑的定时自动机构造方法。
多场景数值实验与硬件测试验证了该方法能高效解决复杂STL运动规划问题并生成平滑可执行轨迹。</td></tr>
<tr><td>2026-05-21</td><td>Scene Reconstruction as Mapping Priors for 3D Detection<br><a href='http://arxiv.org/pdf/2605.22997'>论文</a></td><td>本文提出了一种可扩展的解决方案，通过利用场景重建的地图先验来提升3D目标检测性能，克服了传统高精地图维护成本高的局限。
◆提出一种自动构建密集地图先验的流程，通过聚合传感器数据生成先验，消除了人工标注的需求。
◆设计了新颖的地图先验增强3D检测框架MPA3D，能够有效将地图先验与不同传感器模态进行融合。
在Waymo开放数据集上的广泛实验表明，该方法取得了全新的最优结果。
这证明了可扩展的重建场景先验对于增强3D检测的有效性。</td></tr>
<tr><td>2026-05-21</td><td>Verified Task-Space Motion Planning Under Joint-Space Constraints<br><a href='http://arxiv.org/pdf/2605.22991'>论文</a></td><td>针对反应式任务空间规划器因固定笛卡尔步长和忽略关节极限而导致跟踪漂移及目标不可达的问题，本文提出一种在关节位移边界下计算经认证可达的最大笛卡尔超长方体的方法。
◆利用逆运动学的二阶多项式近似和S-procedure，构建了求解认证步长半宽的小型半定规划问题。
◆提出一种利用二次结构的等效二分法，将认证求解时间缩短至亚毫秒级以适应实时需求。
将此认证机制与Bug2结合，使规划器步长能根据局部运动学条件自适应调整。
在94个对抗场景测试中，该SOS验证规划器实现了零关节极限违反和百分之百的目标到达率，彻底解决了标准Bug2算法的违规与失败问题。</td></tr>
<tr><td>2026-05-21</td><td>N3P: Accelerated Automated Parking via a Learning-Based Naturalistic Three-Stage Scheme<br><a href='http://arxiv.org/pdf/2605.22722'>论文</a></td><td>本文提出了N3P，一种基于学习的自然三阶段自动泊车框架，旨在解决传统Hybrid A*算法计算昂贵以及强化学习方法可靠性差和轨迹次优的问题。
◆引入中间准备姿态并利用学习模块进行预测，将复杂的泊车操作分解为简单的子问题，从而有效降低了计算复杂度。
◆将学习预测模块与Hybrid A*算法深度集成，大幅加速了路径的生成过程。
◆实验验证N3P增强的Hybrid A*规划速度提升超过80%，显著优于传统方法。
◆相比强化学习基线，该方法具有更高的成功率，且生成的轨迹更短、换挡次数更少，同时保持了相近或更低的规划时间。</td></tr>
<tr><td>2026-05-21</td><td>Branch-Stochastic Model Predictive Control for Motion Planning under Multi-Modal Uncertainty with Scenario Clustering<br><a href='http://arxiv.org/pdf/2605.22600'>论文</a></td><td>该论文针对自动驾驶运动规划中多模态不确定性导致传统方法过于保守的问题，提出了一种结合随机模型预测控制与分支结构的新方法。
◆将SMPC与分支结构相结合，为不同意图生成专属轨迹，在保证轨迹安全的同时克服了意图层面的保守性。
◆提出基于高级决策相似度的场景聚类方法，通过合并预测场景确保了算法的实时计算可行性。
◆引入自适应分支时间计算机制，将分离规划的时机推迟到意图不确定性充分降低之后。
仿真结果表明，该方法有效提升了安全性，减少了保守性，并实现了实时计算。</td></tr>
<tr><td>2026-05-20</td><td>Benchmarking Empirical and Learning-Based Approaches for Feedforward Steering Control in Autonomous Racing<br><a href='http://arxiv.org/pdf/2605.21111'>论文</a> | <a href='https://github.com/TUMRT/steering_ff_control'>代码</a></td><td>本文系统性地基准测试了两种基于学习和两种基于经验的前馈转向控制器，以评估其在自动驾驶赛车中减少反馈转向修正的能力。研究在基于真实阿布扎比自动驾驶赛车联赛的高保真双轨车辆动力学模拟器中，对这些控制器进行了开环与闭环测试。
◆提出了一种基于多项式曲面拟合的新型EHD公式，该公式能以最少的参数化捕捉依赖速度的非线性转向行为。
◆揭示了学习型控制器在开环评估中虽预测误差最低，但此优势无法转化为闭环路径跟踪性能或圈速的提升。
◆提出的新型EHD方法取得了最佳的闭环鲁棒性和圈速，突显了必须在完整的轨迹规划与控制软件栈中评估前馈策略的必要性。</td></tr>
<tr><td>2026-05-20</td><td>SubTGraph: Large-Scale Subterranean Environment Synthesis with Controllable Topological Variability for Robotic Autonomy Validation<br><a href='http://arxiv.org/pdf/2605.20917'>论文</a> | <a href='https://github.com/LTU-RAI/SubTGraph.git'>代码</a></td><td>本文提出了SubTGraph框架，填补了地下环境缺乏大规模仿真基准以进行机器人自主性严格统计评估的空白。◆创新性地基于用户结构约束构建代价矩阵，结合Dijkstra算法与拓扑度量瓦片程序化生成多层次地下环境。◆支持高变异性与可控参数合成，用户可根据拓扑、维度和纹理等规范生成矿井、自然洞穴和熔岩管道等不同场景。◆通过语义分割真值验证、多智能体路径规划趋势识别和LIO SLAM极限压力测试三个案例，全面验证了框架对自主栈各层级的评估能力。◆开源了环境生成代码库并发布了包含150个高变异性地下世界的数据库，为该领域提供了关键的基准测试资源。</td></tr>
<tr><td>2026-05-20</td><td>MC-Risk: Multi-Component Risk Fields for Risk Identification and Motion Planning<br><a href='http://arxiv.org/pdf/2605.21406'>论文</a></td><td>本文提出了MC-Risk，一种与规划器对齐的鸟瞰图多组件风险场，能够实现早期校准且类别感知的风险定位。
◆提出机动车辆风险场，融合多模态轨迹预测与高斯环面结构，使横向宽度随速度和曲率增加，高度随前视距离衰减。
◆设计弱势道路使用者风险场，采用与航向和速度对齐的各向异性前偏核，替代了传统的各向同性行人斑块。
◆构建道路惩罚场，利用高精地图拓扑施加偏离道路惩罚及车道感知风险暴露，区分同向与反向车道风险。
本研究首次在RiskBench碰撞子集上进行风险场的标准化定量评估，取得了最佳风险定位与最早危险指示效果。
最后，将该风险场作为模型预测控制的代价密度，无需额外训练即可实现风险感知轨迹生成的插拔式规划接口。</td></tr>
<tr><td>2026-05-19</td><td>Trajectory Planning and Control near the Limits: an Open Experimental Benchmark on the RoboRacer Platform<br><a href='http://arxiv.org/pdf/2605.19881'>论文</a> | <a href='https://roboracer-benchmark.github.io/planning_control_benchmark/'>代码</a></td><td>本文提出了一个模块化框架，用于在极限高加速机动下对自动驾驶轨迹规划和控制方法进行基准测试，并基于1比10比例的RoboRacer平台进行了实验验证。
◆提出一种新型模型结构化神经网络来学习转向控制的逆动力学，显著提高了跟踪精度，减少了转向振荡，且具备物理可解释性。
◆引入在线时间最优速度重规划机制，通过补偿执行误差有效缩短圈速，使车辆能安全达到更高的速度和加速度。
研究通过谨慎与激进赛车线的消融实验，深入分析了各独立模块及其组合的性能表现。
为支持未来研究，作者公开了代码与数据集等资源，为该领域建立了一个开放的实验基准。</td></tr>
<tr><td>2026-05-18</td><td>REACT: Environment-Adaptive Architecture for Continuous Formation Navigation of Wheeled Mobile Robots<br><a href='http://arxiv.org/pdf/2605.18441'>论文</a> | <a href='https://dongjh20.github.io/REACT-website'>代码</a></td><td>针对轮式移动机器人现有编队控制难以适应复杂环境的问题，本文提出了REACT分层架构，集成了集中式编队生成与分布式编队维持。
◆在上层，该架构按需生成环境自适应新编队，并提出TCF-R2T算法在多项式时间内计算无轨迹冲突的机器人目标分配，实现无冲突的及时编队转换。
◆在下层，各机器人执行提出的JSTP方法，通过同时优化空间位置与时间持续时间来维持编队，显著增强了多机器人间的协调性。
这种联合时空轨迹规划使机器人能够在密集静态和动态障碍物场景中实现连续导航。
仿真与真实世界实验充分验证了该架构的有效性与实际应用价值。</td></tr>
<tr><td>2026-05-15</td><td>Constrained MPC-Based Motion Planning for Morphing Quadrotors in Ultra-Narrow Passages under Limited Perception<br><a href='http://arxiv.org/pdf/2605.15999'>论文</a> | <a href='https://github.com/harshjmodi1996/morphocopter_mpc}{Github'>代码</a></td><td>本文提出了一种针对可变形四旋翼在极受限环境和有限感知条件下的形态与轨迹运动规划框架。
◆提出了一种用于非线性模型预测控制的平滑指数障碍物代价函数，通过引入代价降低因子且无硬激活阈值，在保持强避碰能力的同时，解决了传统人工势场在狭窄通道中代价过高阻断路径的问题。
◆将二维激光雷达测量值直接应用于模型预测控制中，使机器人能够有效绕过任意形状的障碍物。
该方法基于acados框架实现，计算高效且实用，实验和仿真结果均验证了其在典型排斥代价函数失效的狭窄走廊中成功穿越的能力。
此外，该代价函数具有通用性，不仅限于可变形四旋翼，还可广泛应用于任何移动机器人。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration (22篇)</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-12</td><td>Fully Distributed Multi-View 3D Tracking in Real-Time<br><a href='http://arxiv.org/pdf/2606.13127'>论文</a></td><td>本文提出MV3DT,一个面向重叠视野多摄像头网络的全分布式实时三维多目标跟踪框架。该方法摒弃传统集中式融合架构,通过点对点协同实现身份传播与遮挡恢复,有效解决了集中式方法在大规模部署时的计算瓶颈问题。在WILDTRACK数据集上达到94.3%的IDF1和93.3%的MOTA,性能与最先进的集中式方法相当,同时在100个摄像头规模下仍能保持30 FPS的实时性能,摄像头间延迟低于10毫秒,通信开销仅为2.2%。此外,该方法无需场景特定训练,仅依赖摄像头标定即可零样本部署于新环境。

核心创新点如下:

◆ 首次提出完全分布式的多视角三维跟踪架构,通过点对点协调机制取代中心节点聚合,从根本上消除了集中式方法的计算瓶颈。

◆ 设计了轻量级模块化流水线,在每个摄像头节点本地执行单目三维感知、分布式多视图关联与协同融合,通过轻量消息传递实现跨节点协作。

◆ 实现卓越的可扩展性,在100摄像头规模下维持30 FPS实时性能,通信开销仅2.2%,显著优于集中式方案。

◆ 采用零样本运行模式,仅依赖摄像头标定信息,无需任何场景特定的训练或学习,可直接部署到新环境。

◆ 在WILDTRACK基准上取得与集中式SOTA方法相竞争的精度,验证了分布式架构在保持高精度的同时具备规模化部署的实用价值。</td></tr>
<tr><td>2026-06-12</td><td>StereoGeo: an end-to-end stereo camera calibration method<br><a href='http://arxiv.org/pdf/2606.14619'>论文</a> | <a href='https://github.com/meddourimane/StereoGeo-dataset'>代码</a></td><td>本文提出了StereoGeo，一种基于端到端网络的立体相机标定方法。该方法能够同时估计左右相机的焦距与重力方向，以及它们之间的相对外参变换。
◆突破了现有方法依赖标定板或结构化环境的限制，无需多视角设置即可完成双目标定。
◆打破了传统方法仅局限于单目内参或外参估计的不足，实现了双目内外参的联合估计。
◆扩展了GeoCalib算法，将深度神经网络特征提取与可微优化器进行有效整合。
实验证明该方法在内参标定上极具竞争力，在外参估计上更超越了现有限于单目的方法。</td></tr>
<tr><td>2026-06-12</td><td>LV-Calib: LiDAR-Camera Extrinsic Calibration with Boundary-Response Modeling<br><a href='http://arxiv.org/pdf/2606.15010'>论文</a></td><td>本文提出了LV-Calib标定框架，利用可打印平面标定板实现了激光雷达与相机的外参估计及激光雷达边界响应标定。
◆提出基于强度与几何约束的迭代精化方法，自动裁剪背景并估计目标平面，显式处理反射率不连续处因光束足迹和混合回波导致的过渡带展宽与失真问题，提取精确的雷达3D特征点。
◆设计了加权重投影一致的外参优化策略，将图像观测保留在重投影域，并利用精化置信度对雷达特征残差进行加权，提升外参标定精度。
◆利用估计的外参和提取的过渡带，通过计算边界重叠样本的俯仰-偏航-距离残差统计量，实现了激光雷达边界响应的标定。
实验验证了该方法具备亚像素级重投影精度与毫米级特征一致性，并有效提升了里程计性能。</td></tr>
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
<tr><td>2026-06-06</td><td>Dexterity-BEV: Aligning 3D World and Actions for Generalizable Robot Policies Learning<br><a href='http://arxiv.org/pdf/2606.02274'>论文</a> | <a href='https://hnuzhy.github.io/projects/Dex-BEV'>代码</a></td><td>本文针对端到端操作策略依赖2D输入且缺乏跨机器人和相机的3D空间对齐的局限性，提出了Dexterity-BEV方法。
◆提出对齐顶点图与顶点频谱，利用相机标定和可选深度将2D视觉提升为像素级3D表示，融合了3D感知与2D大模型的泛化优势。
◆提出将操作策略的输入输出对齐至共享坐标系，并创新性地构建鸟瞰图图像，生成对相机位姿变化鲁棒的视角不变表示。
◆开发了全面的数据处理管线以实现大规模对齐，并引入了针对跨多种机器人、人类操作员和数据集轨迹的全新时间对齐方案。
这些贡献共同缓解了输入输出的时空不对齐问题，显著提升了真实世界机器人操作的连贯性与泛化能力。</td></tr>
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
<tr><td>2026-05-06</td><td>Optimal Uncertainty-Aware Calibration for the AX=YB Problem<br><a href='http://arxiv.org/pdf/2605.04809'>论文</a></td><td>◆论文提出了一个面向AX=YB手眼标定问题的通用优化框架，可同时处理标定参数的求解与迭代优化。

◆方法基于李代数设计迭代算法，在优化过程中严格保持旋转和平移等结构约束，并实现参数的同步更新。

◆针对实际工业机器人场景中数据不确定性强且难以精确建模的问题，论文避免显式建模噪声，而引入相对不确定性度量来动态调节优化过程。

◆论文还设计了有效的初始解生成方法，以提升算法的收敛效率、稳定性和最终估计精度。

◆仿真和真实实验表明，该方法在高不确定性条件下显著优于现有方法，合成数据中估计精度至少提升67%。</td></tr>
<tr><td>2026-05-02</td><td>TT4D: A Pipeline and Dataset for Table Tennis 4D Reconstruction From Monocular Videos<br><a href='http://arxiv.org/pdf/2605.01234'>论文</a></td><td>本文提出了TT4D，这是一个大规模高保真的乒乓球4D重建数据集，包含逾140小时的单双打比赛视频及多模态标注。
◆提出先提升后分割的全新重建流水线，通过学习型网络先将未分割的2D轨迹提升至3D再进行时间分割，解决了传统2D分割在遮挡和多视角下易失效的问题。
◆设计的学习型提升网络具备推断球体旋转、处理不可靠检测以及在高遮挡下成功重建轨迹的能力。
这种核心设计使该流水线成为目前唯一能从通用视角单目广播视频中重建乒乓球比赛的方法。
通过球拍撞击时的姿态与速度估计及训练对抗回合生成模型两项下游任务，验证了该数据集的高保真度。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-undistortion'>Sensor Undistortion (42篇)</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-12</td><td>An ultra-wide-bandgap semiconductor photodetector for linear measurement of bright sub-bandgap light<br><a href='http://arxiv.org/pdf/2606.07807'>论文</a></td><td>本文提出了一种亚带隙氮化铝光电探测器，解决了传统探测器在中低强度光下易饱和的问题。
◆实现了对超过40瓦每平方厘米的超强蓝光的非饱和线性响应。
◆在高达300摄氏度的高温下依然保持无失真的线性响应。
◆揭示了金属-氮化铝肖特基结处深能级点缺陷介导光响应的物理机制。
◆通过掺杂和接触工程证明，窄空间电荷区是实现超强光探测与精确测量的关键。
该研究为超宽禁带半导体器件在航空航天及核电等极端条件下的可靠运行提供了工程策略。</td></tr>
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
<tr><td>2026-06-11</td><td>Revisiting Vehicle Color Recognition in Long-Tailed Surveillance Scenarios<br><a href='http://arxiv.org/pdf/2606.13625'>论文</a> | <a href='https://github.com/viniciusorru/vcr-synthetic'>代码</a></td><td>该论文针对监控场景下车辆颜色识别中存在的严重类别不平衡问题,基于真实世界数据集 UFPR-VeSV 开展了系统性研究。作者结合生成式数据增强、现代视觉表征、损失重加权、学习率调度、颜色安全增强、前景感知预处理与集成融合等多种策略,显著提升了对稀有颜色类别的识别性能。最终方法在微观准确率上达到 94.6%,宏观准确率达 79.7%,相比最新文献宏观准确率提升 8.2 个百分点。此外,作者通过人工错误分析指出,部分剩余错误即使对人类标注者也存在视觉模糊性,从而揭示了基于颜色的车辆识别在非受限监控图像中的实际局限。

核心创新点如下:

◆ 首次系统性地将文本条件生成(RunDiffusion/JuggernautXL)与图像条件颜色编辑(Gemini 2.0 Flash)两种现成生成式策略应用于车辆颜色少数类的合成增强。

◆ 提出综合性训练流程,将合成数据与损失重加权、颜色安全数据增强、前景感知预处理及集成融合相结合,有效缓解长尾分布问题。

◆ 在 UFPR-VeSV 数据集上取得 SOTA 性能,宏观准确率较已有文献提升 8.2 个百分点,显著改善稀有颜色类别的识别效果。

◆ 通过人工错误分析揭示了颜色识别任务的固有视觉模糊性,为该领域的性能上限提供了实证依据。

◆ 开源了所生成的合成图像与完整源码,促进后续在长尾监控场景下的可复现研究。</td></tr>
<tr><td>2026-06-11</td><td>Observation of intertwined charge density wave order and superconductivity in Janus monolayer<br><a href='http://arxiv.org/pdf/2606.13828'>论文</a></td><td>◆本文首次基于第一性原理系统研究了Janus单层1T-ZrSeTe中电荷密度波与超导不稳定性的共存和相互关联。
◆发现其声子谱在M点存在显著软化，源于增强的电子-声子耦合以及带间、带内散射共同导致的电子不稳定性。
◆揭示2×2×1晶格畸变会重构能带并打开小的间接带隙，使体系由半金属性转变为半导体。
◆与ZrTe2单层相比，Se替代一层Te显著降低畸变能量收益，说明Janus结构削弱了CDW不稳定性。
◆论文进一步证明电子关联和双轴应变可有效调控CDW与超导不稳定性。
◆在高温未畸变相中，ZrSeTe表现出声子介导的双能隙超导，主要来自M点软模与Zr d、Te p轨道费米面能带的强耦合，而SOC会降低超导转变温度。</td></tr>
<tr><td>2026-06-10</td><td>Spatially Coupled Phase-to-Depth Calibration for Fringe Projection Profilometry<br><a href='http://arxiv.org/pdf/2606.11601'>论文</a></td><td>针对条纹投影轮廓术中逐像素独立拟合导致的空间不一致和结构化伪影问题，本文提出了一种空间耦合的相位深度标定方法。
◆提出空间耦合的相位深度变换模型，所有像素共享由全局相位标量与仿射空间项构成的单个低维映射，替代独立的逐像素拟合，并可选附加有界平滑修正场。
◆引入原生网格配对方案，直接在参考相机网格上构建相位深度标定对，将立体三维平面沿原生光线采样回相机网格，从而避免对相位图进行纠正。
在具备高分辨率真值的牙科目标上，该方法取得了与主动立体参考相当的点对面均方根误差（约12微米）。
相比传统逐像素标定法，它不仅大幅提升了空间一致性，还将运行时映射简化为少量的逐像素元素级操作，参数存储几乎可忽略。</td></tr>
<tr><td>2026-06-10</td><td>TESS detection of periodic brightness variations during the rise of classical nova PGIR22akgylf<br><a href='http://arxiv.org/pdf/2606.12532'>论文</a></td><td>这篇论文利用TESS空间望远镜对缓慢上升型经典新星PGIR22akgylf进行了高精度光度监测,覆盖了新星发现后3到16天的关键阶段,并辅以地面观测追踪了其长达约133天的完整上升过程。研究团队探测到周期为0.1802±0.0012天、峰峰振幅约0.02星等的周期性亮度变化,该信号在TESS观测的两周内保持稳定,暗示其源于双星轨道运动。作者据此推断伴星为矮星,并提出周期性信号是由于双星轨道运动使新星包层(此时尺度与双星轨道间距相当)发生形变所致,从而揭示了公共包层相互作用在该新星壳层抛射中的重要作用。

◆ 首次在经典新星上升阶段利用TESS高精度光度数据探测到稳定的周期性亮度调制信号,为研究新星包层结构提供了新观测窗口。

◆ 提出周期性光变源自双星轨道运动对膨胀新星包层的形变作用这一新颖物理解释,将光变特征与包层几何结构直接关联。

◆ 首次为经典新星缓慢上升阶段提供了公共包层相互作用参与壳层抛射的直接观测证据。

◆ 打破了缓慢上升现象仅存在于共生双星热核爆发中的传统认知,证明该现象同样可发生于含矮星伴星的紧致双星系统中。

◆ 通过周期稳定性和轨道动力学分析,首次利用上升阶段光变对新星伴星性质(矮星)做出限定,为新星双星系统参数测定提供了新方法。</td></tr>
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
<tr><td>2026-05-29</td><td>Omni-Supervised Motion Editing: Balancing Change and Invariance through Positive-Negative Learning<br><a href='http://arxiv.org/pdf/2605.30969'>论文</a> | <a href='https://github.com/rocket-ycyer/OmniME.git'>代码</a></td><td>本文针对文本驱动的人体运动编辑中难以平衡改变与不变性的核心挑战，提出了全监督正负学习框架OmniME。
◆提出回溯特征监督，在Transformer层间强制执行从粗到细的特征一致性。
◆设计运动保留机制，根据源与目标的相似度关注细微变化以保留未编辑部分。
◆引入基于三元组的语义对齐，增强文本与运动之间的语义对应关系。
这三个互补组件共同构成了统一监督范式，有效平衡了目标区域的精准编辑与未编辑部分的完整保留。
在多个数据集上的广泛实验证明，OmniME实现了最先进的编辑对齐性能。</td></tr>
<tr><td>2026-05-29</td><td>Magnetic self-frustration from spontaneous structural distortion<br><a href='http://arxiv.org/pdf/2606.00339'>论文</a></td><td>本文提出并证实了一种与常规认知相反的物理现象，即自发结构畸变不仅未消除磁简并，反而诱导了新的阻挫。
◆首次提出“磁性自阻挫”概念，打破了结构畸变通常作为逃逸磁简并度途径的传统观点。
◆发现具有平凡最近邻伊辛铁磁作用的kagome晶格会发生磁结构相变进入呼吸状相，其中一个子晶格自发膨胀为等腰三角形并作为刚性拼图块决定另一收缩子晶格的几何结构。
◆证明该畸变后的磁系统可映射为有效的反铁磁三角晶格，在低温下保持无序并保留三分之一的万尼尔剩余熵。
研究还表明，这种自阻挫相存在于中等磁弹性耦合区间，介于弱耦合的无畸变铁磁相与强耦合的规则二聚化反铁磁有序相之间。</td></tr>
<tr><td>2026-05-28</td><td>Resolution-free neural surrogates for geometric parameterization and mapping with spatially varying fields<br><a href='http://arxiv.org/pdf/2605.28551'>论文</a></td><td>针对空间变化场引起的几何映射问题，传统变分模型在处理高分辨率且参数场变化的实例时计算成本极高。本文提出一种分辨率无关的神经代理模型，可在任意结构化或非结构化点集上直接预测映射位置。
◆采用多分辨率几何编码策略，以坐标增强的参数场样本为网络条件，摆脱了对固定网格的依赖。
◆无需带标签的解数据进行训练，而是通过强制执行源自变分能量、扩散密度均衡和拟共形理论的几何感知约束来优化模型。
实验表明该方法在拟共形映射和密度均衡映射问题上具有显著有效性。</td></tr>
<tr><td>2026-05-28</td><td>Turbulence-Robust Dynamic Object Segmentation with Multi-Signal Priors and SAM2 Refinement<br><a href='http://arxiv.org/pdf/2605.29292'>论文</a></td><td>本文提出了针对湍流环境下动态目标分割的免训练多信号分割流水线。
◆融合多信号先验，结合RAFT的密集运动响应、DINOv2的语义目标先验与ViBe的免训练背景建模，解决了单一运动线索在强湍流下不可靠的问题。
◆采用纯推理模式设计，完全无需端到端网络优化或针对特定任务的模型训练与微调，适应了湍流导致的伪运动、模糊和目标间歇可见等复杂情况。
◆引入人工校准的候选融合策略，并结合预训练的SAM2模型通过框提示进行掩膜精修，有效提升了分割边界的准确性。
该方法在CVPR 2026挑战赛中取得了0.425的mIoU和0.457的mDice。</td></tr>
<tr><td>2026-05-26</td><td>Can We Hear from Events? Generating Speech from Event Camera<br><a href='http://arxiv.org/pdf/2605.26672'>论文</a> | <a href='https://xrfang-0102.github.io/EventSpeechWeb/'>代码</a></td><td>本文提出EventSpeech框架，首次利用微秒精度的神经形态事件相机进行文本条件驱动的情感语音生成，解决传统RGB相机因固定曝光导致的高频发音瞬态模糊问题。
◆提出基于事件相机的语音生成新范式，利用微秒级事件与声学波形动态自然对齐的特性，打破了传统视觉语音生成的时间粒度限制。
◆设计了包含专用事件编码器和多尺度音频编码器的架构，引入分层小波上下文化器与双向对齐机制，实现语言内容、视觉动态与声学特征的精准同步。
◆构建了首个事件相机语音生成基准数据集EVT-SPK，涵盖大规模合成数据与神经形态硬件真实录音。
实验证明，该方法在保留细粒度情感和抗运动模糊方面显著优于现有基线，确立了多模态语音生成的新范式。</td></tr>
<tr><td>2026-05-25</td><td>Event-based Batting Impact Estimation<br><a href='http://arxiv.org/pdf/2605.25656'>论文</a></td><td>本文针对RGB相机和IMU在估计击球冲击时机上的局限性，提出了一种基于事件相机的全新框架。
◆提出利用事件相机微秒级分辨率优势，通过检测球和球棒的加权质心距离来估计击打时机。
◆为克服事件帧与RGB图像间的域鸿沟导致的分割精度下降问题，提出生成高密度事件帧的方法。
◆引入一种掩码细化网络，利用高密度事件帧和双向掩码信息，并配合新型损失函数进行优化。
真实数据集实验表明，该方法在低光和严重遮挡等挑战条件下优势显著，将平均绝对误差降低了约百分之六十三。</td></tr>
<tr><td>2026-05-23</td><td>COD10K-C: Benchmarking Robustness of Camouflaged Object Detection Under Natural Image Corruptions<br><a href='http://arxiv.org/pdf/2606.02603'>论文</a></td><td>该论文针对伪装目标检测(COD)模型在真实场景下鲁棒性评估缺失的问题,构建了首个系统性的腐蚀鲁棒性基准 COD10K-C,并提出了一个轻量级鲁棒模型 RobustCODLite。作者基于 COD10K 数据集引入 8 种腐蚀类型和 5 个严重级别,共生成 40 种测试条件和 81,040 对评估样本,对 SINet-v2、PFNet 和 ZoomNet 三种主流模型进行了系统评测,发现所有模型在腐蚀图像上均出现显著性能下降,其中运动模糊和高斯模糊影响最大(SINet-v2 在运动模糊下 Dice 下降 18.5 分),而亮度变化和雾效影响较小。RobustCODLite 在腐蚀条件下保持了 92.3% 的清洁 Dice 分数,显著优于对比模型,并在最难的腐蚀场景下达到或超越在清洁数据上表现更好的模型。

核心创新点如下:

◆ 首次提出面向伪装目标检测的腐蚀鲁棒性基准 COD10K-C,涵盖 8 种腐蚀类型和 5 个严重级别,共 81,040 对评估样本,填补了 COD 领域在真实成像退化下评估缺失的空白。

◆ 系统量化了三种主流 COD 模型在不同腐蚀类型下的性能衰减规律,揭示了模糊类腐蚀对 COD 任务的破坏性远大于光照与天气类腐蚀。

◆ 提出轻量级鲁棒模型 RobustCODLite,融合腐蚀数据增强、频率先验分支和不确定性一致性损失三种机制,提升模型对退化输入的稳定性。

◆ 实验证明 RobustCODLite 在腐蚀保持率上显著优于更大规模的 SOTA 模型,在最严重腐蚀条件下甚至超越清洁数据上表现更优的模型,验证了鲁棒性导向设计的有效性。

◆ 将公开发布 COD10K-C 代码仓库,为后续鲁棒伪装目标检测研究提供标准化评估工具。</td></tr>
<tr><td>2026-05-21</td><td>SpaceDG: Benchmarking Spatial Intelligence under Visual Degradation<br><a href='http://arxiv.org/pdf/2605.22536'>论文</a></td><td>本文提出了SpaceDG，首个针对视觉退化条件下空间理解的大规模数据集与基准，填补了现有空间推理基准忽视真实世界视觉退化的空白。
◆首创物理驱动的退化合成引擎，将退化形成过程嵌入3D高斯溅射渲染中，真实模拟九种退化类型并生成约百万问答对。
◆构建了经人工验证的SpaceDG-Bench基准，涵盖11个推理类别与9种退化类型，产生逾万条视觉问答实例。
◆对25个多模态大模型的全面评估揭示了视觉退化会显著损害空间推理能力，暴露出模型关键的鲁棒性缺陷。
◆证实了退化感知训练的潜力，在SpaceDG上微调不仅能大幅提升退化条件下的鲁棒性甚至超越人类，且不牺牲清晰图像的性能。</td></tr>
<tr><td>2026-05-20</td><td>DarkShake-DVS: Event-based Human Action Recognition under Low-light andShaking Camera Conditions<br><a href='http://arxiv.org/pdf/2605.20680'>论文</a></td><td>本文针对低光照和相机剧烈抖动下人体动作识别易失效的难题，提出了新的解决方案。
◆提出EIS-HAR方法，其事件惯性稳定模块通过非线性变形函数减少运动模糊以重构运动补偿输入，动作识别模块采用四阶段混合架构高效提取时空特征。
◆构建DarkShake-DVS数据集，这是首个结合低光照、六自由度相机运动及同步IMU数据的大规模事件相机动作识别基准，含超一万八千个真实片段。
该研究有效填补了现有研究缺乏综合基准与运动补偿技术的空白。
三个数据集的大量实验表明，EIS-HAR方法的性能持续优于现有最先进算法。</td></tr>
<tr><td>2026-05-18</td><td>Open-source segmentation and biometry dataset using spectrally-multiplexed whole-eye optical coherence tomography<br><a href='http://arxiv.org/pdf/2605.19191'>论文</a></td><td>本文针对全眼OCT系统在成像性能上的权衡以及前节标注数据匮乏的问题，提出了新型频分复用WEOCT系统并开源了大规模数据集。
◆采用1310nm和1060nm双同步200kHz扫频光源，突破了现有系统在信噪比、速度与运动伪影间的局限。
◆构建了包含深度学习分割、3D畸变校正及光线追踪折射校正的端到端自动化流水线，实现了解剖学精确的眼球分层3D重建。
◆通过超300人的用户及体模研究，验证了系统能够同时精准测量角膜地形图与3D瞳孔中心。
◆发布了目前稀缺的大规模开源综合数据集，包含276名受试者的6621个标注体积及校准的3D前节点云。</td></tr>
<tr><td>2026-05-18</td><td>See Silhouettes in Motion with Neuromorphic Vision<br><a href='http://arxiv.org/pdf/2605.17984'>论文</a></td><td>本文针对移动平台上传统帧成像因运动模糊和恶劣光照导致准双峰物体二值化失效的问题，提出一种基于神经形态视觉的帧与事件双模态二值化方法。该方法能在仅CPU设备上实现实时高帧率二值化，为资源受限边缘平台的轻量级感知与交互铺平了道路。
◆提出帧与事件协同的双模态机制，利用事件相机的高时间分辨率和高动态范围优势，有效减少运动模糊并显著提升恶劣光照下的二值化表现。
◆设计异步工作流，规避了传统时间分箱重建在事件稀缺时易崩溃的缺陷，确保在极端千赫兹帧率下依然维持清晰的目标轮廓。
◆实现轻量化高效计算，在仅CPU设备上达成实时高帧率处理，且输出的二值结果可作为可靠表征直接赋能多种下游任务。</td></tr>
<tr><td>2026-05-17</td><td>Channel Modeling and LED Spot Detection for Dense Image-Sensor Visible Light Communication<br><a href='http://arxiv.org/pdf/2605.17375'>论文</a></td><td>针对高密度LED阵列可见光通信中光斑模糊重叠引发严重符号间干扰，以及径向畸变与暗角效应阻碍信号检测的问题，本文提出一种保持全信令密度的鲁棒解码框架。
◆提出导频辅助的几何识别方法，结合点扩散函数约束的霍夫变换与圆心对齐细化技术。
◆引入径向畸变校正与暗角感知补偿机制，恢复几何一致性并抑制边缘检测误差。
◆利用导频帧的先验结构知识，在严重光学畸变下有效分离重叠的LED信号。
实验表明该方法解码精度和吞吐量显著优于传统基线方法，在干扰环境下具备高效应用潜力。</td></tr>
<tr><td>2026-05-15</td><td>DepthPolyp: Pseudo-Depth Guided Lightweight Segmentation for Real-Time Colonoscopy<br><a href='http://arxiv.org/pdf/2605.16519'>论文</a> | <a href='https://github.com/ReaganWu/DepthPolyp/'>代码</a></td><td>本文提出了DepthPolyp，一个基于伪深度引导多任务学习的轻量级鲁棒息肉分割框架，旨在解决真实临床环境中运动模糊和光照不稳导致的性能下降问题。
◆引入层级Ghost分解，实现了紧凑高效的视觉特征生成。
◆提出交错混洗融合机制，以极低计算成本完成跨尺度特征交互。
◆设计动态分组门控模块，实现了自适应的分组特征权重分配与调制。
实验表明，该方法在跨数据集泛化测试中表现优异，在真实手术视频评估中甚至超越了20倍参数量的模型。
该模型仅需3.57M参数和0.86 GMACs，移动端帧率超180 FPS，极具资源受限临床环境下的实时部署潜力。</td></tr>
<tr><td>2026-05-13</td><td>What Limits Vision-and-Language Navigation ?<br><a href='http://arxiv.org/pdf/2605.13328'>论文</a> | <a href='https://yunheng-wang.github.io/stereonav-public.github.io'>代码</a></td><td>本文提出StereoNav框架，解决了视觉语言导航中从仿真到真实部署时因感知不稳定和指令模糊导致的性能下降问题。
◆引入目标位置先验作为合成训练与物理执行间的持久桥梁，提供跨域不变的稳定视觉引导，在指令模糊时实现可靠的空间定位。
◆利用立体视觉构建语义与几何的统一表示，通过增强深度感知减轻运动模糊和光照变化的干扰，实现精确的动作预测。
该方法在R2R-CE和RxR-CE数据集上以更少的参数和训练数据取得了最先进的性能。
真实机器人部署也证实了其在复杂非结构化环境中显著提升了导航的可靠性。</td></tr>
<tr><td>2026-05-12</td><td>EgoEV-HandPose: Egocentric 3D Hand Pose Estimation and Gesture Recognition with Stereo Event Cameras<br><a href='http://arxiv.org/pdf/2605.12297'>论文</a> | <a href='https://github.com/ZJUWang01/EgoEV-HandPose'>代码</a></td><td>本文提出了EgoEV-HandPose端到端框架，旨在解决传统相机运动模糊及现有事件相机自我运动干扰与深度模糊等限制，实现立体事件流下的3D双手姿态估计与手势识别。
◆提出KeypointBEV立体融合模块，将特征提升至鸟瞰图空间，并利用迭代重投影引导的细化循环逐步解决深度不确定性及强化运动学一致性。
◆构建EgoEVHands数据集，这是首个大规模真实世界自我中心立体事件相机手部感知数据集，包含5419个标注序列及38种手势类别的密集3D与2D关键点。
实验证明，该方法以30.54毫米的MPJPE和86.87%的手势识别准确率取得了最优性能。
特别是在低光照和双手遮挡场景下，该框架显著超越了现有基于RGB和事件相机的方案，为事件相机自我中心感知设立了新基准。</td></tr>
<tr><td>2026-05-12</td><td>BronchoLumen: Analysis of recent YOLO-based architectures for real-time bronchial orifice detection in video bronchoscopy<br><a href='http://arxiv.org/pdf/2605.11748'>论文</a></td><td>本文提出了BronchoLumen，一个基于YOLO的实时支气管镜视频支气管开口检测系统，旨在辅助呼吸道导航和计算机辅助诊断。
◆首次仅利用有限的公开数据集，探索并验证了最先进的目标检测架构在不同图像域中鲁棒检测支气管开口的可行性。
◆深入对比了广泛使用的YOLOv8与集成注意力模块的最新架构YOLOv12，揭示出YOLOv12虽精度略低，但具有更优的目标定位准确性。
◆开发了具有高准确性和效率的跨域开源权重解决方案，且系统在运动模糊和低对比度等挑战下仍展现出整体鲁棒性。
该研究通过公开发布模型，为支气管镜导航领域的进一步研究提供了重要基准和工具。</td></tr>
<tr><td>2026-05-11</td><td>Computational Design of a Low-Visibility UAV Using a Human-Aligned Perceptual Metric<br><a href='http://arxiv.org/pdf/2605.11296'>论文</a></td><td>本文提出了一种名为Phantom Twist的单旋翼无人机，通过高速旋转利用运动模糊效应实现低可见度。
◆首创利用高速旋转与运动模糊来降低无人机视觉可见度的单旋翼设计概念。
◆开发了基于人类对齐感知度量LPIPS的两阶段自动化设计流水线，以优化功能组件的布局。
◆在最小化视觉感知度的同时，严格满足稳定飞行所需的惯性与空气动力学约束。
◆通过制作并飞行测试多个原型机，验证了该流水线生成的无人机具备稳定可控的飞行能力。
实验最终证实，这种优化设计的无人机相比传统四旋翼具有显著更低的视觉可感知性。</td></tr>
<tr><td>2026-05-11</td><td>VVitCutLER: Towards Unsupervised Object Detection and Segmentation in Videos<br><a href='http://arxiv.org/pdf/2605.17584'>论文</a></td><td>本文针对无监督视频理解中因运动模糊和遮挡导致伪标签时序漂移与闪烁的问题，提出了无监督视频目标检测与实例分割框架VVitCutLER。
◆提出时序稳定的伪标签生成器VitCut，通过跨帧区域一致性来减少退化过程中的误差累积。
◆设计了蒸馏解码器，以实现高效准确的实例掩码预测。
◆在VVitCutLER框架中集成了跨帧特征聚合机制，进一步增强了视频级别的鲁棒性。
实验证明该方法显著提升了检测与分割性能并降低了时序不稳定性，凸显了时序一致性监督对于鲁棒视频理解的重要性。</td></tr>
<tr><td>2026-05-09</td><td>Kinematics-Driven Gaussian Shape Deformation for Blurry Monocular Dynamic Scenes<br><a href='http://arxiv.org/pdf/2605.08635'>论文</a></td><td>本文提出了Kinematics-GS框架，解决模糊单目视频重建动态3D场景时运动与几何纠缠阻碍一致性的难题。
◆将模糊建模为运动对齐的变形，并引入运动学先验沿运动轨迹重新参数化高斯形状，无需辅助运动监督即可缓解退化形状坍缩。
◆利用时间变形方差将场景分解为动态与静态成分，并采用由粗到细的变形策略，稳定优化并兼顾全局运动与精细细节。
◆构建了一个极具挑战性的真实世界数据集，包含具有非刚体运动和空间非均匀运动模糊的可变形弹性物体。
实验证明该方法在真实模糊基准上显著超越现有方法，有效处理了复杂非刚体运动场景。</td></tr>
<tr><td>2026-05-09</td><td>Egocentric Whole-Body Human Mesh Recovery with Prior-Guided Learning<br><a href='http://arxiv.org/pdf/2605.08606'>论文</a> | <a href='https://github.com/naso06/EgoSMPLX'>代码</a></td><td>本文致力于解决单目头戴式相机图像中缺乏可靠真实标注且难以恢复手部和面部细节的自我中心全身人体网格恢复问题。为此，作者提出了一种基于先验引导的学习框架，从单张自我中心图像中恢复全身网格。
◆构建了与三维关节监督对齐的基于优化的伪真实标注，比现有基于回归的伪标注大幅提升了准确性。
◆通过适配第三人称人体网格恢复基础模型并结合基于扩散模型的姿态先验，充分利用了多种先验知识。
◆引入了确定性去畸变模块，有效处理了自我中心图像中的鱼眼畸变问题。
实验表明该方法在多个基准上实现了优于现有技术的全身重建效果，并已开源代码与数据。</td></tr>
<tr><td>2026-05-08</td><td>AERO-VIS: Asynchronous Event-based Real-time Onboard Visual-Inertial SLAM<br><a href='http://arxiv.org/pdf/2605.07885'>论文</a> | <a href='https://ethz-mrl.github.io/AERO-VIS'>代码</a></td><td>本文提出了AERO-VIS系统，这是一种异步事件驱动的实时机载视觉-惯性SLAM系统，突破了传统固定频率处理带来的延迟和吞吐量限制。
◆集成了一种数据驱动、鲁棒且性能优化的关键点检测器，提升了特征提取的稳定性与准确性。
◆采用异步方式处理事件流，使系统能够动态适应下游计算需求，确保低延迟和实时性能。
◆在无人机平台上部署时，实现了机载事件SLAM前所未有的高精度。
◆成为首个仅依赖机载计算实现闭环无人机控制和大规模状态估计的纯事件驱动惯性SLAM系统。</td></tr>
<tr><td>2026-05-08</td><td>A Task-Agnostic Algebraic Integrity Metric for Event-Camera Streams Toward SOTIF-Compliant Perception using Pearson Correlation Coefficient<br><a href='http://arxiv.org/pdf/2605.21500'>论文</a></td><td>本文针对事件相机异步流缺乏任务无关的质量评估指标问题，提出统一代数框架以满足自动驾驶SOTIF认证需求。
◆创新性地将皮尔逊相关系数提升至时间面、事件帧和体素网格三种标准事件表示形式。
◆推导出用于流完整性监控的r-TS、仅需整数比较的自适应ROI指标r2-EF，以及时间冗余门控指标r-VG。
◆建立了事件相机对比度阈值机制与基于PCC变化准则的结构同构性，并对流水线延迟与信息损失进行对称分析。
通过直接模拟发射模型生成的合成事件流验证了指标，在隧道异常场景中指标成功从0.93降至负值并触发报警。</td></tr>
<tr><td>2026-05-08</td><td>AsyncEvGS: Asynchronous Event-Assisted Gaussian Splatting for Handheld Motion-Blurred Scenes<br><a href='http://arxiv.org/pdf/2605.07192'>论文</a> | <a href='https://openimaginglab.github.io/AsyncEvGS/'>代码</a></td><td>本文针对严重运动模糊导致3D重建失败的问题，提出了一种灵活的高分辨率异步RGB-Event双摄系统及对应重建框架。
◆提出高分辨率异步RGB-Event双摄系统与重建框架，打破了传统方法对低分辨率传感器和严格硬件同步的依赖，提升了手持拍摄的实用性。
◆设计基于VGGT的跨域位姿估计模块，先利用事件数据重建清晰图像，从而为3DGS提供鲁棒的初始化。
◆引入结构驱动的事件损失和视角特定一致性正则化器，有效缓解传统损失函数的病态行为，确保稳定且高保真的重建。
◆构建了全新的高分辨率异步RGB-Event去模糊数据集AsyncEv-Deblur，实验验证了该方法在严重模糊场景下实现了最先进的重建鲁棒性。</td></tr>
<tr><td>2026-05-07</td><td>Advancing Reliable Synthetic Video Detection: Insights from the SAFE Challenge<br><a href='http://arxiv.org/pdf/2605.06912'>论文</a></td><td>本文核心贡献在于组织并总结了ICCV 2025上的SAFE合成视频检测挑战赛，为评估合成媒体检测算法提供了重要基准。
◆构建了包含13种现代高质量生成模型和21种真实来源的6000个视频数据集，总计20小时，全面覆盖多样化生成源。
◆设计了双任务评估体系，不仅考察跨生成器检测能力，还专门测试对缩放、重压缩和运动模糊等后处理操作的鲁棒性。
◆采用全盲评估条件，依托Hugging Face平台在90天内收集12个团队的600余次提交，确保了评估的客观与广泛性。
◆揭示了当前检测方法的关键特性，即跨生成器泛化能力取得进步，但在面对后处理伪影时仍存在持续脆弱性。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

---
> 更新于: 2026.06.17
