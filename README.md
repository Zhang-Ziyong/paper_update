# 计算机视觉领域最新论文 (2026.06.09)

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
<tr><td>2026-05-29</td><td>Triangle Splatting SLAM<br><a href='http://arxiv.org/pdf/2605.31419'>论文</a></td><td>本文提出了一种使用可微三角形作为三维地图表示的稠密RGB-D SLAM系统。与3D高斯溅射不同，三角形天然兼容传统渲染硬件及需要显式几何的下游任务。
◆首次提出基于三角形溅射的稠密SLAM系统，通过对无结构三角形汤进行在线可微渲染来联合执行追踪与建图。
◆利用受限德劳内三角剖分将地图在线转换为连通网格，赋予了系统在线网格变形和碰撞检查的新能力。
在Replica和TUM-RGBD数据集上，该系统在三维几何重建上优于基线，追踪精度与之持平，并实现了在线场景编辑。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-05-24</td><td>Geometry-Aware Image Flow Matching<br><a href='http://arxiv.org/pdf/2605.25294'>论文</a></td><td>本文针对自然图像生成领域局限于欧几里得假设而忽略数据内在几何结构的问题展开研究。研究发现自然图像的语义信息主要编码在方向分量中，范数分量可由全局平均值近似，这表明自然图像能在超球面上被有效建模。
◆提出球面最优传输流匹配方法，利用角距离实现几何感知的生成建模。
◆提出球面流匹配方法，将动态过程直接约束在流形上进行求解。
实验证明这些几何感知方法的性能显著优于欧几里得基线模型。本工作为弥合黎曼流形建模与自然图像生成之间的鸿沟提供了全新视角。</td></tr>
<tr><td>2026-05-22</td><td>Joint Target-Less Intrinsic and Extrinsic Camera-LiDAR Calibration using Deep Point Correspondences<br><a href='http://arxiv.org/pdf/2605.23397'>论文</a></td><td>本文提出首个完全无需标定板的相机与激光雷达联合标定流程，突破了现有基于深度点对应的标定方法需已知内参的局限。该方法利用深度像素点对应关系，可同时估计包含径向与切向畸变的针孔相机内参以及相机与激光雷达的外参。
◆通过运动恢复结构实现相机内参的自动初始化。
◆将相机与激光雷达特征匹配推广至包含畸变且内参未知的原始图像。
◆将对应点估计与内参及外参的联合非线性优化进行紧密耦合。
在KITTI数据集上的实验表明，该联合标定方法在恢复精确内参的同时有效提升了外参的标定精度。</td></tr>
<tr><td>2026-05-20</td><td>JWST Advanced Deep Extragalactic Survey (JADES) Data Release 5: stellar population catalogue for galaxies in GOODS-N and GOODS-S<br><a href='http://arxiv.org/pdf/2605.21599'>论文</a></td><td>本文发布了JADES第五次数据释放的星系恒星种群星表，利用深空JWST成像和多波段数据对GOODS-N和GOODS-S区域约50万个源进行了均匀的贝叶斯物理性质推断。
星表推导了恒星质量、恒星形成率及尘埃消光等参数的后验分布，推进了对z=1至9约35万个星系低质量极限的测量和近期恒星形成约束。
◆创新性地采用随红移演化的星系主序先验来建模非参数化星系恒星形成历史，在保留非参数灵活性的同时为其提供了物理驱动的长期形状。
◆该先验将恒星质量增长与恒星形成率相联系，允许数据支持下的显著偏离，有效缓解了暗弱源的非物理解并减少了红移、年龄、尘埃与金属丰度间的简并性。
经过验证的公开星表为研究宇宙演化中星系生长、熄灭及恒星质量积累提供了可靠的统计样本。</td></tr>
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
<tr><td>2026-05-19</td><td>Depth2Pose: A Pose-Based Benchmark for Monocular Depth Estimation without Ground-Truth Depth<br><a href='http://arxiv.org/pdf/2605.19797'>论文</a> | <a href='https://kocurvik.github.io/depth2pose'>代码</a></td><td>该论文提出Depth2Pose框架，将单目深度估计的评估与下游几何任务结合，解决了传统深度误差指标无法反映深度对下游任务有用性的问题。
◆提出以相对相机位姿估计精度作为任务驱动的深度质量代理指标，通过结合深度预测与特征对应关系来评估单目深度估计器。
◆打破对昂贵逐像素真实深度标注的依赖，仅需通过运动恢复结构获取相机位姿即可评估，使框架适用于大尺度或严重遮挡等困难场景。
◆构建了D2P数据集，包含常见训练数据分布之外的极具挑战性的场景。
实验表明，在传统基准上表现优异的方法在相同数据集上位姿指标良好，却难以泛化到D2P数据集，该评估框架及代码已开源。</td></tr>
<tr><td>2026-05-18</td><td>Efficient 3D Content Reconstruction and Generation<br><a href='http://arxiv.org/pdf/2605.18052'>论文</a></td><td>该论文致力于推动自动3D内容创建技术的发展，以替代耗时的人工建模和扫描流程。论文的核心贡献涵盖了3D生成与3D重建这两个互补的研究范式。
◆在3D生成方面，提出了Instant3D方法，创新性地将多视角扩散与前馈稀疏视角3D重建相结合，在5至20秒内即可生成高质量的3D资产。
◆在3D重建方面，开发了FastMap运动恢复结构流程，通过广泛结合一阶优化与融合GPU内核，相比现有最优方法实现了高达10倍的加速。
◆FastMap在实现极致加速的同时，依然保持了与之前方法相当的相机位姿估计精度和下游新视角合成质量。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='obstacle-avoidance'>Obstacle Avoidance</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-06-07</td><td>IR-SIM: A Lightweight Skill-Native Simulator for Navigation, Learning, and Benchmarking<br><a href='http://arxiv.org/pdf/2606.08729'>论文</a> | <a href='https://github.com/hanruihua/ir-sim'>代码</a></td><td>针对现有机器人模拟器接口复杂阻碍快速原型开发的问题，本文提出了轻量级技能原生导航模拟器IR-SIM。
◆该模拟器完全通过YAML配置文件定义场景与机器人模块，使仿真过程完全可描述与可复现。
◆其技能原生设计支持直接通过自然语言文本提示生成和修改仿真场景，极大便利了大模型驱动的自动化开发。
◆系统能够...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-07</td><td>Real-Time and Accurate Collision-Free Teleoperation via Differentiable Constraint-Based Trajectory Planning<br><a href='http://arxiv.org/pdf/2606.08725'>论文</a></td><td>本文针对遥操作中仅控制末端执行器易导致机械臂碰撞的问题，提出了一种基于可微约束的实时无碰撞轨迹规划方法。
◆将基于凸优化对偶性的可微避碰约束公式引入遥操作场景，避免了传统方法因近似导数导致的收敛差与计算耗时问题。
◆采用胶囊体近似机械臂和多面体表示环境障碍物，克服了传统球体近似几何精度低的缺陷，实现了更准确的障碍物建模。
仿真与真实UR5e机械臂的实验结果表明，该方法在多变障碍物环境中具有更低的计算延迟。
最终实现了更平滑且完全无碰撞的末端执行器遥操作，有效提升了系统的安全性与实时性。</td></tr>
<tr><td>2026-06-07</td><td>Towards End to End Motion Planning and Execution for Autonomous Underwater Vehicles Using Reinforcement Learning<br><a href='http://arxiv.org/pdf/2606.08513'>论文</a></td><td>本文提出一种端到端深度强化学习方法，将自主水下航行器的原始传感器数据直接映射为推进器指令，从而减少了传统复杂人工工程设计。
◆提出分层强化学习架构，将导航拆分为两个马尔可夫决策过程，由2Hz的高层策略处理图像与声纳等数据生成空间子目标，10Hz的低层策略将子目标转为推进器指令。
◆采用定制化高效训练框架，高层策略在改进的样本高效机器人强化学习框架内用先验演示强化学习训练，低层策略结合软演员评论家与后见经验回放算法优化。
◆展现出优越的导航性能与鲁棒性，轨迹长度与RRT星基线仅差4%至6%，且对模拟传感器噪声和低...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-06-02</td><td>RSC: Decentralized Rigid Formation Flocking for Large-Scale Swarms via Hybrid Predictive Control and Online Reconfiguration<br><a href='http://arxiv.org/pdf/2606.04248'>论文</a></td><td>本文针对分散式刚性编队集群在杂乱环境中易陷入局部最小值死锁、控制振荡及避障灵活性差等问题，提出了大规模群体分散式控制框架RSC。
◆提出混合控制架构，将有限时域轨迹预测与响应式人工势场安全控制器相结合，通过长期规划逃离局部最小值并确保短期安全。
◆引入基于稳定角色交换的在线领航-跟随重构机制，在穿越障碍后加速编队重聚且不中断任务执行。
在25架无人机的挑战性环境测试中，该框架可靠地统一了刚性编队保持、避障与目标追踪。
在无碰撞且最大相对边长误差低于10%的严格标准下，RSC成功率达83%，显著优于成功率不足5%的现有基线方法。</td></tr>
<tr><td>2026-06-02</td><td>Distribution-Free Risk-Aware Planning and Control Under Uncertainty Using Conformal Spectral Risk Control<br><a href='http://arxiv.org/pdf/2606.04185'>论文</a></td><td>动态不确定环境下的安全导航常依赖对真实不确定性分布的准确估计，但有限数据往往导致分布假设错误从而引发危险决策。本文提出了一种结合预测集的风险感知模型预测控制框架，无需假设底层不确定性分布即可保证风险低于用户设定阈值。
◆将共形风险控制扩展至一般谱风险度量，开发了无分布的风险量化框架来生成预测集。
◆证明将预测集引入控制框架，即使不确定性设定错误也能在谱风险约束满足方面提供统计安全性保证。
仿真实验验证了该框架在车辆避障场景中的有效性，相比基线方法显著提升了安全性并缩短了求解时间。</td></tr>
<tr><td>2026-06-03</td><td>AgenticRL: Self-Refining Agentic Reinforcement Learning for Vision-Conditioned UAV Navigation<br><a href='http://arxiv.org/pdf/2606.03963'>论文</a></td><td>本文提出AgenticRL框架，解决了无人机导航中强化学习严重依赖人工奖励设计与微调的痛点，实现了奖励生成、策略优化和真实部署的自主化。
◆提出基于多模态GPT智能体的闭环自优化奖励设计机制，由智能体自动生成奖励、评估训练策略并诊断失败模式，从而自我完善奖励函数。
◆引入推理阶段的智能策略调度机制，利用多模态智能体融合真实图像与自然语言自动识别当前场景，动态选择最匹配的策略执行。
实验表明该闭环优化过程使策略表现较初始奖励提升了71%。
框架还成功实现了仿真到现实的迁移，真实世界成功率达91%，虚实迁移准确率达94%。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-06-07</td><td>MB-Loc: Multi-planar Bird&#x27;s-eye-view Localization in outdoor LiDAR scenes<br><a href='http://arxiv.org/pdf/2606.08744'>论文</a></td><td>本文提出了MB-Loc框架，解决了现有场景坐标回归方法计算效率低且对视角变化敏感的问题。
◆提出2.5D多平面鸟瞰图表示法，将点云沿Z轴切片并映射带符号深度至2D平面，在保留3D几何的同时利用2D卷积提升计算效率。
◆引入KL正则化潜在瓶颈模块，显式建模空间不确定性且不引入随机噪声，有效应对室外LiDAR的稀疏性。
◆在平面投影前应用3D空间增强策略，迫使网络隐式学习视角不变特征，显著提升旋转鲁棒性。
实验表明该方法在NCLT数据集上达到最优，且以实时推理速度实现了比传统3D架构更高的计算效率。</td></tr>
<tr><td>2026-06-08</td><td>QuadVerse: An Integrated Framework Aligning Visual-Physical Reality for Quadruped Simulation<br><a href='http://arxiv.org/pdf/2606.07118'>论文</a></td><td>QuadVerse 是一个面向四足机器人仿真的集成框架,旨在解决仿真到现实(sim-to-real)迁移中视觉与动力学差距相互耦合、累积传播的问题。该框架以重建场景作为统一的校准基底,将视觉感知、物理交互与执行器动力学三方面对齐,从而显著缩小仿真与真实环境的差距。实验证明,QuadVerse 在重建质量与运动跟踪精度上均优于相关基线方法,并可在无需任务级真实环境采样的情况下,实现零样本视觉导航策略的稳健部署。

核心贡献与创新点如下:

◆ 提出 QuadVerse 集成框架,首次将视觉、接触物理与执行器动力学三类 sim-to-real 差距统一在同一校准基底上对齐,避免了传统方法分别处理所导致的误差累积与耦合问题。

◆ 基于 RGB 视频构建几何约束的 3D 高斯泼溅(3DGS)场景,既支持批量化的高真实感第一视角渲染,又可提取带语义的可碰撞网格,实现&quot;视觉渲染&quot;与&quot;物理仿真&quot;的双重可用性。

◆ 提出基于语义网格的接触校准方法:利用空间可变摩擦先验进行初始化,再通过轨迹后验搜索进行精细化优化,实现地形接触参数的精准建模。

◆ 设计残差动力学补偿器,在已完成接触校准的地形上回放真实轨迹进行训练,有效解耦地形接触误差与执行器非理想特性,使补偿更具针对性。

◆ 在上述基础上实现了无需任务级真实采样的零样本视觉导航策略部署,验证了该框架在真实机器人任务中的实用性与泛化能力。</td></tr>
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
<tr><td>2026-06-03</td><td>Uncertainty-Aware Adaptive Sensor Fusion for Autonomous Navigation<br><a href='http://arxiv.org/pdf/2606.05437'>论文</a></td><td>本文提出一种结合混合深度学习与无迹卡尔曼滤波的方法，以提升视觉惯性里程计在自主导航中的姿态估计精度。该模型采用视觉Transformer网络提取IMU数据的时间依赖性，并利用多尺度卷积神经网络学习视觉数据的光流运动线索。
◆提出自适应传感器融合模块，通过利用估计的不确定性对视觉和惯性特征进行动态加权，增强了复杂环境下的鲁棒性。
◆设计新颖的不确定性感知损失函数，将预测不确定性显式融入学习过程，有效应对噪声或不完整的传感器输入。
在KITTI数据集上的评估表明该方法在绝对轨迹与相对位姿误差上显著超越基线，且在A100上达155帧每秒的高效处理速度，极适于资源受限系统。</td></tr>
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
<tr><td>2026-06-02</td><td>Autonomous Navigation System for Library Service Robot Based on Unitree Go2 Edu<br><a href='http://arxiv.org/pdf/2606.03340'>论文</a></td><td>本文提出了一种基于Unitree Go2 Edu四足机器人的ROS 2自主导航系统，专为图书馆狭窄过道和动态环境设计。该系统集成了4D激光雷达、深度相机和IMU，并融合了RTAB-Map视觉激光SLAM、AMCL与EKF定位以及基于Nav2的A*和DWA规划算法。
◆突破传统将图书馆视为崎岖地形的假设，专注解决实际部署中的移动不连续性问题，如地面过渡、临时杂物和部分受阻通道，克服了低底盘轮式平台的局限。
◆构建了针对四足机器人的多传感器融合与完整导航堆栈，实现了复杂室内场景下的精准建图、定位与动态避障。
◆在真实图书馆中进行了严格验证，系统在静态、低密度动态和高密度动态场景下的导航成功率分别达到100%、96%和88%，且建图平均误差仅为3.7厘米，证明了其高效性与准确性。</td></tr>
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
<tr><td>2026-06-01</td><td>Adversarial Dual On-Policy Distillation from Expressive Teacher<br><a href='http://arxiv.org/pdf/2605.27095'>论文</a> | <a href='https://github.com/vanzll/FA-OPD'>代码</a></td><td>针对现有具身控制模仿学习方法仅依赖离线专家数据而缺乏在线纠正信号，且标准在线策略蒸馏无法适用于仅有演示场景的问题，本文提出了FA-OPD方法。该方法从演示中学习流匹配教师并与轻量级MLP学生共同训练，在学生交互过程中提供双通道互补信号。
◆设计奖励通道，通过学习状态-动作对的专家相似性目标来驱动长视野策略优化，促进在线探索。
◆设计动作通道，在学生实际访问的状态上提供密集的局部目标，稳定策略的利用。
◆将双通道巧妙耦合，使奖励蒸馏能够泛化超越逐点演示，同时动作蒸馏将探索锚定在类专家行为附近。
实验表明，在六个机器人导航、操作和运动基准测试中，FA-OPD超越了强基线，并在噪声或有限演示条件下展现出显著增强的鲁棒性。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-06-07</td><td>Video2Sim2Real: Full-Stack Autonomous Dexterous Skill Acquisition from a Single Human Video<br><a href='http://arxiv.org/pdf/2606.08828'>论文</a></td><td>本文提出了Video2Sim2Real框架，实现了从单个人类操作视频到机器人自主灵巧技能获取的全栈流程，有效解决了感知误差和具身差异的挑战。
◆提出以物体为中心的关键帧优化机制，不盲从提取的运动轨迹，而是利用仿真器物体信息优化机器人配置作为锚点来修正运动，确保对环境产生预期影响。
◆设计了解耦的sim-to-real策略，通过模仿学习从含噪点云重新校准配置以应对感知噪声，并利用残差强化学习进行局部手指适应以弥补交互动力学差异。
◆引入碰撞感知运动规划模块，使习得的技能能够泛化到全新的物体空间配置。
实验表明，该框架在多项日常任务中显著提升了仿真成功率、安全性和轨迹连贯性。
与现有技术相比，它实现了更优的仿真到现实迁移效果，为从人类视频自主获取灵巧技能...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-06-06</td><td>Combining Reinforcement Learning with Arc-search Interior-Point Method for Path Planning<br><a href='http://arxiv.org/pdf/2606.07920'>论文</a></td><td>本文针对含障碍物环境下的非线性和非凸路径规划问题，提出了一种结合强化学习与弧搜索内点法的新框架。该框架的核心贡献在于有效克服了单一方法的局限性，实现了两者的优势互补。
◆创新性地将强化学习的实时决策能力与弧搜索内点法的寻优性能相融合，解决了机器学习路径非最优与优化方法实时性差的问题。
◆利用强化学习在无需高保真模型的情况下快速生成可行路径，满足系统的实时性要求。
◆引入弧搜索内点法对生成的路径进行进一步优化，确保路径在长度或时间等性能指标上达到最优或近最优。
仿真结果表明，该方法显著提升了路径规划的综合性能。</td></tr>
<tr><td>2026-06-05</td><td>Path Planning Using Deep Deterministic Policy Gradient: A Reinforcement Learning Approach<br><a href='http://arxiv.org/pdf/2606.07855'>论文</a></td><td>本文针对威胁环境下自动驾驶车辆路径规划计算慢的问题，提出了一种基于深度确定性策略梯度的强化学习方法。该方法将威胁建模为圆形禁区，通过试错训练使智能体学习从当前状态到可行动作的直接映射以安全抵达目标。
◆设计了包含终点吸引场、障碍物排斥场和控制能量惩罚的三部分奖励函数，有效引导智能体规划出倾向直线的安全路径。
◆通过训练寻找能保证安全到达目的地的最大起始点集合，从而为任务规划提供关键的事前可行性评估信息。
◆与传统伪谱最优控制方法对比表明，该方法在生成有效路径的同时计算速度显著更快，更适合实时应用场景。</td></tr>
<tr><td>2026-06-05</td><td>Lane Change Trajectory Planning for Personalized Driving Comfort and Mobility Efficiency<br><a href='http://arxiv.org/pdf/2606.06805'>论文</a></td><td>该论文针对换道轨迹规划中纵横向运动耦合及驾驶员个性化差异显著的问题,提出了一种神经网络驱动的轨迹规划方法,将三阶多项式轨迹生成器与学习模块相结合,能够在多样化驾驶条件下推断最优轨迹参数,从而同时兼顾驾驶舒适性与通行效率。通过代表性案例和蒙特卡洛仿真验证,该规划器在个性化数据充足时可实现个性化的舒适性与机动效率,在数据不足或不可获取的条件下也能保证轨迹的可行性。

核心贡献与创新点如下:

◆ 提出了融合三阶多项式轨迹生成器与神经网络学习模块的换道轨迹规划框架,实现了纵横向耦合运动的个性化参数推断。

◆ 设计了共享主干加双分支头部的网络结构,一个分支负责保证全工况下的基础可行性,另一个分支负责捕获驾驶员对舒适性或通行效率的个性化偏好。

◆ 引入基于误差胜出逻辑回归的统计门控机制,实现头部之间的自适应切换,使规划器能够根据驾驶情境上下文动态选择合适的输出分支。

◆ 构建了在个性化数据稀缺或不可访问时仍能保证轨迹可行性的兜底机制,提升了方法在真实场景中的鲁棒性与适用性。

◆ 通过代表性案例与蒙特卡洛仿真系统验证了该方法在个性化舒适性、机动效率和工况适应性方面的综合优势。</td></tr>
<tr><td>2026-06-04</td><td>IDDMBSE: Integrating Data-Driven and Model-Based Systems Engineering for Trusted Autonomous Cyber-Physical Systems<br><a href='http://arxiv.org/pdf/2606.06727'>论文</a></td><td>该论文针对自主信息物理系统(CPS)开发中基于模型的系统工程(MBSE)与数据驱动的机器学习/人工智能方法长期割裂的问题,提出了一种名为IDDMBSE的集成方法论。该方法在传统MBSE的V型流程每一步骤中嵌入数据驱动闭环,以SysML、自主性栈以及混合式架构为支撑,并通过一套开源工具链加以实现,最后在受争议地形的Isaac Sim测试场中以可信自主地面机器人为案例验证了全生命周期的有效性。

核心贡献与创新点如下:

◆ 首次提出IDDMBSE方法论,在严谨的MBSE V型流程的每个环节原生融入数据驱动循环,填补了MBSE与ML/AI在系统工程层面缺乏统一方法的空白。

◆ 开发了PERFECT工具,可将SysML系统架构自动映射为可执行的ROS自主性栈,实现大规模性能评估。

◆ 提出TRADES-X工具,将设计空间探索分解为&quot;基于模型的优化&quot;与&quot;数据驱动评估&quot;两阶段,实现混合式权衡分析。

◆ 构建了VERITAS统一保证工作流,将形式化验证、数据驱动验证与运行时验证整合到单一框架中。

◆ 以可信自主地面机器人为完整案例,涵盖传感器选型、风险敏感路径规划、行为树任务验证、基于共形预测的鲁棒感知及多机器人协同保证等环节,并开源了配套的Isaac Sim测试场。

◆ 展望了基于SysML v2/KerML重构IDDMBSE的路径,以实现语言原生的可组合性与更紧密的ML/AI集成。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-07</td><td>RGB-S: Image-Aligned Tactile Saliency for Robust Dexterous Manipulation<br><a href='http://arxiv.org/pdf/2606.08765'>论文</a></td><td>本文提出RGB-S框架，旨在解决机器人灵巧操作中视觉遮挡下稀疏触觉与密集视觉难以对齐的问题。与隐式学习跨模态对应的方法不同，该框架通过将物理接触显式锚定在图像域中来提升空间推理能力。
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
<tr><td>2026-05-06</td><td>Optimal Uncertainty-Aware Calibration for the AX=YB Problem<br><a href='http://arxiv.org/pdf/2605.04809'>论文</a></td><td>本文提出了一种求解手眼标定问题的通用优化框架。
◆基于李代数开发了一种迭代算法，在严格保持标定参数结构约束的同时实现参数同步更新，从而获得近似全局最优解。
◆针对现实数据不确定性建模困难的问题，摒弃显式建模，引入不确定性度量评估数据源间的相对不确定性，并据此动态优化迭代过程。
◆设计了一种有效的初始解生成方法，显著提升了算法的收敛效率、整体稳定性和准确性。
数值仿真与真实实验验证了该方法的有效性，其在高不确定性条件下的估计精度相比现有方法至少提升了67%。</td></tr>
<tr><td>2026-05-02</td><td>TT4D: A Pipeline and Dataset for Table Tennis 4D Reconstruction From Monocular Videos<br><a href='http://arxiv.org/pdf/2605.01234'>论文</a></td><td>本文提出了TT4D，这是一个大规模高保真的乒乓球4D重建数据集，包含逾140小时的单双打比赛视频及多模态标注。
◆提出先提升后分割的全新重建流水线，通过学习型网络先将未分割的2D轨迹提升至3D再进行时间分割，解决了传统2D分割在遮挡和多视角下易失效的问题。
◆设计的学习型提升网络具备推断球体旋转、处理不可靠检测以及在高遮挡下成功重建轨迹的能力。
这种核心设计使该流水线成为目前唯一能从通用视角单目广播视频中重建乒乓球比赛的方法。
通过球拍撞击时的姿态与速度估计及训练对抗回合生成模型两项下游任务，验证了该数据集的高保真度。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-undistortion'>Sensor Undistortion</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-06-05</td><td>An ultra-wide-bandgap semiconductor photodetector for linear measurement of bright sub-bandgap light<br><a href='http://arxiv.org/pdf/2606.07807'>论文</a></td><td>本文提出了一种亚带隙氮化铝光电探测器，解决了传统探测器在中低强度光下易饱和的问题。
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
<tr><td>2026-05-23</td><td>COD10K-C: Benchmarking Robustness of Camouflaged Object Detection Under Natural Image Corruptions<br><a href='http://arxiv.org/pdf/2606.02603'>论文</a></td><td>该论文针对伪装目标检测(COD)模型在真实场景下鲁棒性评估缺失的问题,构建了首个系统性的腐蚀鲁棒性基准 COD10K-C,并提出了一个轻量级鲁棒模型 RobustCODLite。作者基于 COD10K 数据集引入 8 种腐蚀类型和 5 个严重级别,共生成 40 种测试条件和 81,040 对评估样本,对 SINet-v2、PFNet 和 ZoomNet 三种主流模型进行了系统评测,发现所有模型在腐蚀图像上均出现显著性能下降,其中运动模糊和高斯模糊影响最大(SINet-v2 在运动模糊下 Dice 下降 18.5 分),而亮度变化和雾效影响较小。RobustCODLite 在腐蚀条件下保持了 92.3% 的清洁 Dice 分数,显著优于对比模型,并在最难的腐蚀场景下达到或超越在清洁数据上表现更好的模型。

核心创新点如下:

◆ 首次提出面向伪装目标检测的腐蚀鲁棒性基准 COD10K-C,涵盖 8 种腐蚀类型和 5 个严重级别,共 81,040 对评估样本,填补了 COD 领域在真实成像退化下评估缺失的空白。

◆ 系统量化了三种主流 COD 模型在不同腐蚀类型下的性能衰减规律,揭示了模糊类腐蚀对 COD 任务的破坏性远大于光照与天气类腐蚀。

◆ 提出轻量级鲁棒模型 RobustCODLite,融合腐蚀数据增强、频率先验分支和不确定性一致性损失三种机制,提升模型对退化输入的稳定性。

◆ 实验证明 RobustCODLite 在腐蚀保持率上显著优于更大规模的 SOTA 模型,在最严重腐蚀条件下甚至超越清洁数据上表现更优的模型,验证了鲁棒性导向设计的有效性。

◆ 将公开发布 COD10K-C 代码仓库,为后续鲁棒伪装目标检测研究提供标准化评估工具。</td></tr>
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
<tr><td>2026-05-29</td><td>Magnetic self-frustration from spontaneous structural distortion<br><a href='http://arxiv.org/pdf/2606.00339'>论文</a></td><td>本文提出并证实了一种与常规认知相反的物理现象，即自发结构畸变不仅未消除磁简并，反而诱导了新的阻挫。
◆首次提出“磁性自阻挫”概念，打破了结构畸变通常作为逃逸磁简并度途径的传统观点。
◆发现具有平凡最近邻伊辛铁磁作用的kagome晶格会发生磁结构相变进入呼吸状相，其中一个子晶格自发膨胀为等腰三角形并作为刚性拼图块决定另一收缩子晶格的几何结构。
◆证明该畸变后的磁系统可映射为有效的反铁磁三角晶格，在低温下保持无序并保留三分之一的万尼尔剩余熵。
研究还表明，这种自阻挫相存在于中等磁弹性耦合区间，介于弱耦合的无畸变铁磁相与强耦合的规则二聚化反铁磁有序相之间。</td></tr>
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
<tr><td>2026-05-28</td><td>Turbulence-Robust Dynamic Object Segmentation with Multi-Signal Priors and SAM2 Refinement<br><a href='http://arxiv.org/pdf/2605.29292'>论文</a></td><td>本文提出了针对湍流环境下动态目标分割的免训练多信号分割流水线。
◆融合多信号先验，结合RAFT的密集运动响应、DINOv2的语义目标先验与ViBe的免训练背景建模，解决了单一运动线索在强湍流下不可靠的问题。
◆采用纯推理模式设计，完全无需端到端网络优化或针对特定任务的模型训练与微调，适应了湍流导致的伪运动、模糊和目标间歇可见等复杂情况。
◆引入人工校准的候选融合策略，并结合预训练的SAM2模型通过框提示进行掩膜精修，有效提升了分割边界的准确性。
该方法在CVPR 2026挑战赛中取得了0.425的mIoU和0.457的mDice。</td></tr>
<tr><td>2026-05-28</td><td>Resolution-free neural surrogates for geometric parameterization and mapping with spatially varying fields<br><a href='http://arxiv.org/pdf/2605.28551'>论文</a></td><td>针对空间变化场引起的几何映射问题，传统变分模型在处理高分辨率且参数场变化的实例时计算成本极高。本文提出一种分辨率无关的神经代理模型，可在任意结构化或非结构化点集上直接预测映射位置。
◆采用多分辨率几何编码策略，以坐标增强的参数场样本为网络条件，摆脱了对固定网格的依赖。
◆无需带标签的解数据进行训练，而是通过强制执行源自变分能量、扩散密度均衡和拟共形理论的几何感知约束来优化模型。
实验表明该方法在拟共形映射和密度均衡映射问题上具有显著有效性。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>4770</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4166</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2407</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1608</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1601</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1416</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1254</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1233</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>927</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>919</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>916</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>793</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>780</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>739</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>723</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>702</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>631</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>630</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>621</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>586</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>562</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>551</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>536</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>499</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>475</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>435</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>400</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>342</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>337</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>261</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>252</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>236</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>235</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>222</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>198</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>196</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>156</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>146</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>142</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>116</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2843</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1640</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1351</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1096</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1036</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>870</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>697</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>655</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>649</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>620</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>582</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>572</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>567</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>561</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>550</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>514</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>481</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>462</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>443</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>440</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>335</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>311</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>298</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>281</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>277</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>258</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>221</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>206</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>201</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>187</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>176</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>169</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>166</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>159</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>151</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>137</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>135</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>131</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
<tr><td><a href='https://github.com/ethz-asl/phaser'>phaser</a></td><td>130</td><td>A robust pointcloud registration pipeline based on</td></tr>
<tr><td><a href='https://github.com/ethz-asl/data-driven-dynamics'>data-driven-dynamics</a></td><td>130</td><td>Data Driven Dynamics Modeling for Aerial Vehicles</td></tr>
<tr><td><a href='https://github.com/ethz-asl/ssc_exploration'>ssc_exploration</a></td><td>111</td><td>Incremental 3D Scene Completion for Safe and Effic</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waypoint_navigator'>waypoint_navigator</a></td><td>107</td><td>Stand-alone waypoint navigator</td></tr>
<tr><td><a href='https://github.com/ethz-asl/active_grasp'>active_grasp</a></td><td>107</td><td>Closed-loop next-best view planning for grasp dete</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waverider'>waverider</a></td><td>107</td><td>RMPs on multi-resolution occupancy maps for effici</td></tr>
<tr><td><a href='https://github.com/ethz-asl/reinmav-gym'>reinmav-gym</a></td><td>106</td><td>Reinforcement Learning framework for MAVs using th</td></tr>
<tr><td><a href='https://github.com/ethz-asl/navrep'>navrep</a></td><td>104</td><td>navrep</td></tr>
<tr><td><a href='https://github.com/ethz-asl/eth_supermegabot'>eth_supermegabot</a></td><td>102</td><td>Instructions for ETH center for robotics summer sc</td></tr>
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>102</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.06.09
