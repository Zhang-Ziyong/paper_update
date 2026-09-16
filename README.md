# 计算机视觉领域最新论文 (2026.09.16)

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
<tr><td>2026-09-15</td><td>PanoGS-SLAM: Panoramic 3D Gaussian Splatting SLAM<br><a href='http://arxiv.org/pdf/2609.17387'>论文</a></td><td>PanoGS-SLAM是首个基于3D高斯泼溅的全景稠密SLAM系统，面向机器人实时定位与高质量建图需求。它直接在球面域进行可微渲染与位姿优化，利用全向光度约束提升快速运动和大视角变化下的跟踪稳定性。
◆ 提出球面一致光度损失，补偿等距柱状投影的面积畸变，增强几何一致性与鲁棒性。
◆ 提出深度引导的高斯初始化策略，稳定新观测区域中的增量建图。
在PALVIO和SynPano真实与合成全景基准上，其跟踪精度和渲染质量持续优于几何及GS基线，并实现快速前端收敛与实时性能。受控视场实验还表明，角覆盖增大会单调改善优化条件与收敛稳定性，凸显传感几何对可微高斯SLAM优化景观的关键影响。</td></tr>
<tr><td>2026-09-15</td><td>Online Geometric Change Detection via Scene Decomposition<br><a href='http://arxiv.org/pdf/2609.17302'>论文</a></td><td>本文提出CDSD，一种基于场景分解的在线几何变化检测框架，利用LiDAR或RGB-D帮助机器人在动态环境中实时识别倒树、开门等变化，服务于单会话和多会话自主任务规划。
针对全局地图比较计算昂贵且难以支持单会话在线检测的问题，CDSD将环境空间分解为独特场景，并只比较各场景的稠密局部子图，从而高效完成变化检测与实时地图重建。
◆ 首次提出基于子图的几何变化检测框架，避免全局地图比较，支持单会话在线检测。
◆ 通过场景分解选择冗余信息最少的局部场景，提高变化检测的效率和针对性。
◆ 为每个场景生成稠密且具代表性的子图，并检测不同视场子图之间的变化。
◆ 将检测变化用于实时地图重建，并在ARL自采数据集和开源多会话数据集上验证有效性。</td></tr>
<tr><td>2026-09-15</td><td>HuMemSLAM: Efficient Human-Inspired Semantic Place Recognition for Robust Visual SLAM<br><a href='http://arxiv.org/pdf/2609.17168'>论文</a></td><td>针对传统视觉SLAM在感知歧义和感知变化下地点识别脆弱、而学习型VPR难以兼顾精度与实时性的问题，本文提出人类记忆与感知启发的语义地点识别方法。

◆ 提出HuMem-VPR，融合自底向上的感知证据与自顶向下的上下文推理，利用二者双向关系实现高层地点语义理解。

◆ 将HuMem-VPR与ORB-SLAM3集成形成HuMemSLAM，为几何后端提供更可靠的语义地点识别前端。

◆ 在真实图像基准取得最高聚合检索精度，在CARLA保持竞争精度，并比评估的SOTA VPR降低约2至3倍延迟。

在多个数据集族和在线实验中，HuMemSLAM较ORB-SLAM3原生检索显著提升integrated Recall@1，同时减少提交给几何后端的候选proposals。</td></tr>
<tr><td>2026-09-14</td><td>SURE-Map: Self-Correcting Streaming Geometric Foundation Model<br><a href='http://arxiv.org/pdf/2609.15795'>论文</a> | <a href='https://mingkai-liu.github.io/projects/sure-map/'>代码</a></td><td>本文提出SURE-Map，一种面向流式几何基础模型的自校正框架，旨在解决有限上下文预测易受动态物体和弱纹理影响、局部误差累积导致几何畸变与长时尺度漂移的问题。
◆ 显式建模跨视角几何不确定性：不同于单视角深度或点置信度，它直接衡量联合预测的位姿与深度是否产生几何一致的跨视角像素对应。
◆ 提出多时间尺度自校正：快速连续帧推理保持流式效率，稀疏关键帧窗口推理提供更长程几何证据，周期性重校准近期轨迹尺度。
该框架在长时在线前馈重建基准上取得新的最优性能。
具体地，KITTI上ATE-RMSE从24.00降至17.24米，Oxford Spires从5.11降至4.74米，VBR从31.37降至28.58米。
结合回环优化后，三者进一步降至15.17、4.63和22.12米。</td></tr>
<tr><td>2026-09-14</td><td>P-POSEMEM: Projective Semantic Memory for Consistent Language Grounding under Pose-Graph Rewrites<br><a href='http://arxiv.org/pdf/2609.15475'>论文</a></td><td>论文提出P-POSEMEM，解决SLAM位姿图优化、闭环与压缩时语言接地对象命名漂移的问题，将语义观测存为出生关键帧上的不可变事件。
◆ 用Bayes-tree消除条件保留每个被边缘化关键帧的位姿后验，而非把检测钉死在会漂移的世界坐标。
◆ 在重建的位姿、锚点与身份联合后验上积分语义似然，使查询不受图重写影响。
◆ 提出Dproj，用推理等价全图与边缘化图间语言目标分布的总变差缺陷直接度量记忆一致性。
在40个HM3DSem场景和112000次查询中，它复现全图oracle并减少目标翻转；761次闭环改写地图达47米时Dproj低于10^-13且0/288翻转，在线有界求解器下也优于冻结坐标。
预注册阴性对照显示Dproj能捕捉与校准误差、导航成功不同的失败模式，且共享冻结检测器隔离出记忆一致性增益。</td></tr>
<tr><td>2026-09-14</td><td>Comparing Trajectories from Positions Alone: Curvature-Based Time Alignment and Drift Error Metric<br><a href='http://arxiv.org/pdf/2609.14936'>论文</a></td><td>论文针对机器人领域缺乏独立高精度参考轨迹，以及ATE/RPE评估中假设与参数常不明确的问题，提出面向状态估计、定位与SLAM的轨迹评估协议。
◆ 提出基于曲率信号的新型时间对齐方法，可仅从位置信息比较轨迹并降低对独立高精度参考的依赖。
◆ 提出按行驶距离归一化的漂移误差度量，使不同路径长度下的评估结果更可比。
◆ 将时间同步、采样对齐和外参校准显式纳入评估流程，减少隐含假设造成的误导。
◆ 通过敏感性分析定量刻画上述因素对评估结果的影响。
◆ 形成更严格、可复现且标准化的轨迹评估协议，支持公平比较。</td></tr>
<tr><td>2026-09-14</td><td>Valerant: An Automatic Navigable Game Map Generator via Action-Conditioned World Model Exploration<br><a href='http://arxiv.org/pdf/2609.09418'>论文</a></td><td>Valerant的核心贡献是提出一种无需训练的框架，将预训练动作条件世界模型转化为可通过探索构建3D游戏地图的WAM。
◆ 无需训练，直接把预训练动作条件世界模型改造成用于3D游戏地图探索与构建的WAM。
◆ 将预测性视觉推演与SLAM空间重建耦合，从动作条件视频中恢复持久3D几何与可导航空间。
◆ 引入探索驱动动作选择，使智能体自主探索并逐步扩展游戏地图。
◆ 实现从单张图像渐进生成持久、可移动和交互的3D游戏地图。
◆ 把WAM交互从2D视觉模拟扩展到显式3D空间实例化，并为降低3D游戏地图人工制作成本提供新途径。</td></tr>
<tr><td>2026-09-13</td><td>SCOUT-SLAM: Structurally-Coupled Dual Uncertainty-Aware 3DGS SLAM in the Wild<br><a href='http://arxiv.org/pdf/2609.14634'>论文</a></td><td>论文针对真实动态场景中3DGS-SLAM相机跟踪与重建质量相互拖累的循环依赖问题，提出SCOUT-SLAM。其核心是结构耦合双不确定性框架，让跟踪不确定性与重建不确定性由共享基础网络联合估计。  
◆ 设计低秩适配网络，并以多视图特征一致性训练，使跟踪不确定性不再单纯依赖重建质量。  
◆ 引入空间自适应先验调制共享网络训练目标，避免重建不稳定在静态区域抬高不确定性并破坏共享表示。  
该框架由此打破“重建不稳导致不确定性失真，进而拖累跟踪与静态重建”的恶性循环。  
在TUM RGB-D、Bonn Dynamic、Wild-SLAM MoCap等动态基准上，SCOUT-SLAM实现了当前最优的相机跟踪精度与无伪影静态场景重建。</td></tr>
<tr><td>2026-09-12</td><td>FFVO: A Feedforward Pose Decoder for Long-Horizon Visual Odometry<br><a href='http://arxiv.org/pdf/2609.13733'>论文</a></td><td>论文提出FFVO，一种面向长时序视觉里程计的前馈位姿解码器，旨在解决长视频中相机位姿估计计算成本高、长上下文歧义与时序不稳定等问题。它在联合重建架构基础上进行位姿专用适配，实现高效且时序稳定的相机位姿估计。
◆采用紧凑相机token表示，实现计算高效的时间聚合。
◆设计分层局部到全局时间解码器，分离短程运动聚合与序列级整合，缓解几何歧义。
◆引入中间轨迹监督，提升时序稳定性并减少抖动和漂移。
在Waymo Open Dataset、KITTI及大规模私有基准上，FFVO优于现有前馈方法，显著降低抖动与漂移，证明其适用于长时序视觉里程计。</td></tr>
<tr><td>2026-09-12</td><td>MomentBA: Second-order Spatial Moments for Anisotropic Correspondence Uncertainty in Differentiable Bundle Adjustment<br><a href='http://arxiv.org/pdf/2609.13691'>论文</a></td><td>MomentBA是一种几何感知的捆绑调整框架，用于解决视觉里程计中对应关系不确定性被忽略或均匀化的问题。它从局部相似度响应的二阶空间矩直接推导各向异性对应不确定性，并转化为可解释的协方差估计。  
◆ 无需额外协方差预测网络，直接从匹配响应分布得到各向异性协方差。  
◆ 将对应特定的信息矩阵引入捆绑调整，实现不确定性感知的残差加权。  
◆ 把该建模嵌入可微分优化框架，建立对应不确定性与几何估计的直接联系。  
在EuRoC MAV和TartanAir v1 Hard上，MomentBA提升了单目视觉里程计精度，并比固定或各向同性不确定性模型取得更低旋转误差和更鲁棒轨迹。</td></tr>
<tr><td>2026-09-11</td><td>Parameter Sensitivity Analysis for Aerial LiDAR-Inertial Odometries in low-altitude flights<br><a href='http://arxiv.org/pdf/2609.12837'>论文</a></td><td>论文针对低空无人机LiDAR-惯性里程计调参困难且性能依赖场景、LiDAR和运动的问题，系统分析了FAST-LIO2与Cartographer的LIO模块的参数敏感性。研究在多种低空飞行数据集上通过穷举网格搜索获取参数组合与绝对轨迹误差，并用Pearson相关和随机森林排列重要性量化各参数影响。分析识别出影响性能的关键参数，提出简化调参流程与调参建议，使两算法在94%案例中达到网格搜索最优性能5厘米内的ATE。
◆ 首次面向低空飞行空中LiDAR SLAM数据集，对EKF型FAST-LIO2和图优化型Cartographer的LIO模块进行系统参数敏感性对比分析。
◆ 融合穷举网格搜索、Pearson相关与随机森林排列重要性，量化单参数及参数组合对ATE的影响并识别关键参数。
◆ 提出可操作的简化调参流程与调参建议，在94%分析案例中取得与网格搜索最优值相差5厘米内的ATE。</td></tr>
<tr><td>2026-09-11</td><td>ProClosure: Hierarchical Room-Object Assignment using Progressive Boundary Closure from Monocular Video<br><a href='http://arxiv.org/pdf/2609.12614'>论文</a></td><td>论文提出ProClosure，从单目RGB视频恢复房间层并完成房间到物体的层次分配，以构建可用于机器人取物的3D场景图。  
◆ 统一处理门洞与未观测墙缺口，将两者都视为应封闭边界，避免把本应分开的房间错误合并。  
◆ 提出渐进边界闭包，逐步向内加厚边界并冻结已包围自由区域，使每个开口按自身尺度封闭，无需预设固定半径。  
◆ 以相机位姿作为房间种子，去除采样启发式，使房间分割具有确定性。  
◆ 利用开口处少视线穿越的特性分配物体，将物体归入覆盖其大部分范围的房间，提升房间与物体关联。  
在HM3D-Semantics的10层6场景上，与HOV-SG使用相同俯视图比较，房间F1从0.741升至0.890，物体到房间ARI从0.488升至0.696，且每层均领先。</td></tr>
<tr><td>2026-09-11</td><td>Visual-SLAM for the detection of hidden tomatoes in greenhouses by Hierarchical Localization and GLOMAP for robotized harvesting<br><a href='http://arxiv.org/pdf/2609.11766'>论文</a></td><td>本文提出面向温室番茄机器人采收的低成本单目Visual-SLAM系统，将GLOMAP与Hierarchical Localization集成，实现隐藏番茄检测与三维作物建图，并在Agroconnect真实温室验证了几何精度。
◆ 用单目相机替代LiDAR或立体相机，显著降低温室作物监测与建图的硬件成本。
◆ 集成基于Structure-From-Motion的GLOMAP与Hierarchical Localization，生成番茄作物三维地图。
◆ 采用粗到精分层定位：先全局检索生成位置假设，再在候选区域组合局部特征。
◆ 能正确识别番茄簇，并重建被遮挡、传统视觉技术难以获取的番茄。
◆ 通过人工真值测量果实尺寸、质心位置和朝向，验证低成本单目管线的几何精度。</td></tr>
<tr><td>2026-09-10</td><td>Chain-SLAM: Globally Consistent Backend for Multi-Session LiDAR SLAM via Chained Loop Closure<br><a href='http://arxiv.org/pdf/2609.12221'>论文</a> | <a href='https://ai4ce.github.io/Chain-SLAM/'>代码</a></td><td>Chain-SLAM提出面向大规模多会话LiDAR SLAM的全局一致后端，实现在线多会话地图对齐与复用。  
◆ 设计链式回环闭合机制，通过邻接图将几何约束跨会话关键帧高效传播，以可靠短时回环触发长期一致性。  
◆ 采用GNSS邻近位置识别初始化跨会话对齐，并在统一因子图中在线检测回环、联合优化已加载地图与新轨迹。  
◆ 同时保持会话内和会话间几何一致性，无需动态物体移除，具备跨平台鲁棒性和极少超参数调节。  
实验证明其在大规模数据集上提升轨迹精度并实现稳健多会话集成，代码已开源以支持可复现研究。</td></tr>
<tr><td>2026-09-09</td><td>Odometer-Agnostic Drift Correction Using OpenStreetMap Lane Geometry<br><a href='http://arxiv.org/pdf/2609.10336'>论文</a></td><td>本文提出一种轻量、开源且与里程计无关的漂移校正方法，通过将短轨迹段直接对齐到OpenStreetMap车道中心线来抑制长期漂移。
◆ 里程计无关：不绑定LiDAR或视觉等特定后端，可适配多种里程计。
◆ 稀疏地图先验：仅依赖OSM车道几何，无需稠密地图或昂贵预处理。
◆ 直接对齐建模：将漂移校正转化为近期里程计与车道中心线的直接对齐，而非复杂匹配管线。
◆ 在线高效运行：支持在线校正，适合大规模或无回环环境。
在LiDAR和视觉里程计实验中，该方法均稳定提升精度，且在严重漂移下增益尤其显著。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-14</td><td>CAL-MOS: Bridging Layers with Adapters for Robust MOS Prediction Across Speech Foundation Models<br><a href='http://arxiv.org/pdf/2609.14956'>论文</a></td><td>本文系统评测十种语音基础模型在四个MOS数据集上的层深选择与多层融合问题，覆盖全量微调、冻结编码器最后一层探测和朴素跨层加权聚合三种策略。实验发现最佳层强依赖骨干与数据集，朴素加权融合跨设置不稳定。为此作者提出CAL-MOS，在池化前用逐层适配器校准各层表征，以增强多层融合鲁棒性。
◆ 首次跨十种SFM与四个MOS数据集系统揭示MOS预测最佳层的不确定性及朴素融合的不稳定性。
◆ 提出逐层适配器校准聚合，将层间信息先校准再池化，提升跨骨干和跨数据集的融合可靠性。
◆ 在保持骨干冻结的同时缩小与全量微调的差距，为高效鲁棒MOS预测提供新方案。</td></tr>
<tr><td>2026-09-14</td><td>HiSfM: Disambiguating Structure-from-Motion via Scaffold-Anchored Hierarchical Reconstruction<br><a href='http://arxiv.org/pdf/2609.04718'>论文</a> | <a href='https://github.com/3dv-casia/HiSfM'>代码</a></td><td>HiSfM提出了一种面向视觉模糊场景的分层粗到细SfM框架，通过构建稳定的脚手架锚点，在显著提升鲁棒性的同时大幅降低计算开销。  
◆ 利用几何启发式规则生成强局部社区，有效聚合冗余图像并减少无效约束。  
◆ 使用边不相交生成树（EDST）连接社区，形成紧凑且强壮的骨架，并通过双视图消歧器验证骨架边，以排除歧义匹配。  
◆ 在验证后的骨架上重建稳定脚手架作为场景锚点，再高效注册剩余图像并完成三角化，兼顾全局一致性与细粒度补全。  
实验表明，该方法在歧义聚焦基准和通用数据集上能避免歧义引发的重建失败，相比已有方法显著缩短运行时间，同时比激进稀疏化方法获得更高的重建完整性。</td></tr>
<tr><td>2026-09-12</td><td>SkyAnchor: Updating Metric-scale Aerial 3D Gaussian Scenes from Unposed Ground-View Sequences<br><a href='http://arxiv.org/pdf/2609.13903'>论文</a></td><td>本文研究如何用新采集、无位姿且未知全局尺度的地面序列更新已有航空3D高斯场景，核心思路是把已有航空SfM与3DGS当作固定支架，而非从头联合重建航空和地面影像。
◆提出基于几何验证航空支撑的短帧组定位，生成稀疏锚点位姿，缓解单图跨视角定位脆弱问题。
◆通过锚点约束子图并固定前后锚点进行增量配准与光束法平差，恢复完整地面轨迹，抑制长轨迹漂移。
◆在保持航空视角的前提下插入过滤后的地面高斯，并进行轻量联合优化，实现街景外观更新且不破坏原航空渲染。
在七个真实航空—地面场景上，方法获得准确的米制地面轨迹，并在航空与地面视角均取得强渲染质量。</td></tr>
<tr><td>2026-09-11</td><td>NOVA-GS: Noise-Aware View-Consistent Gaussian Splatting for Low-Light Novel View Synthesis<br><a href='http://arxiv.org/pdf/2609.12682'>论文</a> | <a href='https://shaurya2524.github.io/nova-gs/'>代码</a></td><td>本文提出NOVA-GS，一种面向低光新视角合成的噪声感知统一3D高斯泼溅框架，将增强、去噪与几何优化整合于单流程，并利用VGGT前馈估计直接从退化输入获得稳健相机位姿与几何，无需SfM。
◆ 结构感知增强模块进行曝光校正，提升低光图像可见性并保持结构信息。
◆ 自监督盲点掩码去噪模块提供伪监督，在无干净标签下抑制传感器噪声。
◆ 一致性驱动高斯泼溅优化强制跨视角几何相干，稳定重建与新视角合成。
◆ 噪声引导球谐正则抑制噪声区域中视角相关伪影，改善光照与颜色一致性。
实验表明该方法在多种真实低光数据集上提升几何保真度、颜色一致性和鲁棒性，且无需配对监督或良好光照参考。</td></tr>
<tr><td>2026-09-11</td><td>Visual-SLAM for the detection of hidden tomatoes in greenhouses by Hierarchical Localization and GLOMAP for robotized harvesting<br><a href='http://arxiv.org/pdf/2609.11766'>论文</a></td><td>本文提出一种用于温室番茄机器人采摘的低成本单目Visual-SLAM系统，并在Agroconnect实验温室真实番茄串上验证。  
◆ 用单目相机替代LiDAR和立体相机，显著降低温室作物监测与建图成本。  
◆ 将Hierarchical Localization与基于Structure-From-Motion的GLOMAP结合，实现从图像采集到三维作物地图的完整流程。  
◆ 采用粗到精的层次定位策略，先全局检索生成位置假设，再在候选区域融合局部特征。  
◆ 能正确识别被遮挡、经典视觉难以触及的番茄簇，并重建其三维模型。  
重建结果通过人工真值测量果实尺寸、质心位置和朝向，确认了几何精度，为后续生长分析与农业管理优化奠定基础。</td></tr>
<tr><td>2026-09-08</td><td>Learning Global Camera Poses from Noisy View-Graphs for Structure from Motion<br><a href='http://arxiv.org/pdf/2609.09491'>论文</a></td><td>本文提出一种基于可学习视图图聚合的深度全局SfM框架，用于从含噪视图图中估计全局一致相机位姿。
◆ 采用置换等变、边条件图神经网络，以噪声相对位姿为输入直接输出全局相机外参。
◆ 训练无需真值监督，仅依赖相对位姿一致性目标，降低对标注数据的依赖。
◆ 网络输出后接三维点三角化和鲁棒光束法平差，形成完整全局SfM流程。
◆ 方法高效、可扩展至千张以上图像，并对视图图密度具有鲁棒性。
在MegaDepth、1DSfM、Strecha和BlendedMVS上，其旋转和平移精度优于以轨迹为中心的深度方法，能配准更多图像，并与先进经典流程竞争且速度更快。</td></tr>
<tr><td>2026-09-07</td><td>Multi-View Structure-from-Motion Enables Oriented Projective Shape Analysis in Three Dimensions<br><a href='http://arxiv.org/pdf/2609.13263'>论文</a></td><td>本文针对经典投影形状分析仅能由单立体像对重建、方向信息可能翻转的问题，利用多视图SfM捆绑调整仅确定到保向投影变换的性质，实现三维有向投影形状分析。
◆ 首次在三维中开展有向投影形状（OPS）分析，并计算外蕴总方差指数与进行统计推断。
◆ 使用Agisoft Metashape Professional 2.3.0对三立方体对象构建8个SfM重建，并通过复现原立体构造验证实现。
◆ 发现SfM数据高集中时OPS指数渐近为PS指数的一半，这是集中度导致的结构性结果而非对象属性。
◆ 对q=14个非框架地标的蓝图假设均未被拒绝，且SfM重建比立体重建约集中26倍，显著提升重建精度。
◆ 通过样本量、照片数量和框架排序分析，支持上述结论的稳健性。</td></tr>
<tr><td>2026-09-04</td><td>BLASt3R: Bundle Adjustment of Any Image Set with Multi-View Matching and Monocular Priors<br><a href='http://arxiv.org/pdf/2609.05210'>论文</a></td><td>该论文提出BLASt3R，一种正则化束调整框架，统一处理在线VSLAM与离线无序图像集重建，无需切换系统或调整超参数。核心在于利用快速多视图匹配器获取跨视图对应关系，并结合单目深度先验进行初始化和约束优化。  
◆提出统一的正则化BA框架，将传统几何优化与学习式先验结合，同时支持标定和未标定场景。  
◆设计快速的多视图匹配策略，显著降低稠密对应估计的计算成本，满足在线实时性要求。  
◆利用单目先验作为正则化项，提高初始化鲁棒性并约束无纹理或弱几何区域的漂移。  
◆实验显示本方法在VSLAM中无需内参标定即可超越此前所有需标定的方法，在精度与速度上取得更优折中。</td></tr>
<tr><td>2026-09-04</td><td>XDG: Accelerated Visual Disambiguation<br><a href='http://arxiv.org/pdf/2608.29733'>论文</a> | <a href='https://github.com/xtcpete/xdg'>代码</a></td><td>这篇论文针对三维重建中视觉混淆（doppelganger问题）导致误匹配的挑战，提出了高效的视觉消歧模型XDG。作者指出，已有方法在基础模型顶部叠加沉重的Transformer分类器代价高昂，而3D基础模型本身已具备跨视角几何推理能力，因此应直接利用骨干网络表征。

◆ 创新点1：基于Depth Anything 3这一3D基础模型进行微调，而非在其上重新学习成对推理逻辑，从而避免使用重型解码器。

◆ 创新点2：采用轻量级LoRA适配器对基础模型进行参数高效微调，显著降低计算开销。

◆ 创新点3：创新性地将基础模型中的相机令牌重新用作紧凑的成对分类令牌，配合小型MLP头即可预测图像对是否观测同一三维表面。

实验结果表明，XDG在成对消歧和重建基准上与当前最优方法性能相当，同时推理速度提升超过3倍，在包含数千张图像的LaMAR场景中可节省超过10小时的消歧处理时间，展现了出色的精度-效率权衡，具备大规模SfM应用潜力。</td></tr>
<tr><td>2026-09-02</td><td>AutoCompass: Accurate Visual Localization on Public Maps by Learning from Weak Labels<br><a href='http://arxiv.org/pdf/2609.02798'>论文</a></td><td>AutoCompass提出了一种针对神经地图匹配器的新型监督训练方法,旨在解决训练数据中绝对位姿标签存在的噪声问题。该方法在多个驾驶和第一人称视角基准测试中均显著优于依赖高精度绝对位姿标签的传统训练方案。

◆ 不需要显式的朝向标签:仅使用原始GPS位置标签进行训练,模型便能自动学习预测准确的朝向,证明了朝向监督的冗余性。

◆ 引入位置容差区域机制:在原始GPS坐标周围定义合理的容差范围,有效提升了模型的位置定位精度。

◆ 融合相对位姿作为更可靠的监督信号:当数据中存在通过SLAM或SfM获得的图像间相对位姿时,将其纳入训练,可提供比绝对位姿更精确的学习监督。

◆ 整体框架降低了对高质量标注数据的依赖,使得在噪声较大或标注不精确的大规模地理参考图像数据集上训练高性能地图匹配模型成为可能。</td></tr>
<tr><td>2026-09-02</td><td>MV-dVRK: A Multi-Viewpoint Benchmark for Spatial Surgical Perception<br><a href='http://arxiv.org/pdf/2609.02717'>论文</a></td><td>本文针对手术场景中多视角三维重建缺乏基准数据集的问题，提出了MV-dVRK数据集和系统性评估方法。

核心贡献包括以下几个方面。

◆ 首次构建了包含多台曝光同步立体内窥镜视角、精确表面几何与相机位姿的体外手术多视角基准数据集，填补了真实内窥镜图像多视角重建评估的空白。

◆ 提供经过工业级3D扫描仪验证的稠密SfM参考几何与真值相机位姿，包含静态和动态两大子集，覆盖多种手术任务与组织形变场景。

◆ 系统比较了单目、双目、多目立体及多视角重建方法随视角数量增加的零样本性能，揭示了多目立体在两台内窥镜下覆盖度最高、而加入第三视角后优化式多视角方法在1毫米容差下覆盖率达67%，显著优于前馈式基础模型的43%。

◆ 发布了配套项目网站，为未来手术多视角感知研究提供了开放资源。</td></tr>
<tr><td>2026-09-02</td><td>Inside-out growth and the kiloparsec-scale star formation main sequence for low-surface-brightness disk galaxies in MaNGA<br><a href='http://arxiv.org/pdf/2609.02378'>论文</a></td><td>本文利用MaNGA巡天数据,选取38个低表面亮度星系(LSBGs)和216个高表面亮度星系(HSBGs),系统研究了两类星系在千秒差距尺度上的恒星形成主序关系及径向结构特征。◆研究发现LSBGs的恒星形成率密度(Σ_SFR)径向梯度极平(斜率约-0.1至-0.2),表明恒星形成在整个盘上均匀分布,而其比恒星形成率密度(Σ_sSFR)呈正梯度,首次清晰地揭示了LSBGs存在明显的&quot;由内向外&quot;生长模式。◆LSBGs和HSBGs遵循相同的全局和分辨恒星形成主序,中心表面亮度μ₀对主序关系无显著影响,说明表面亮度不是决定星系恒星形成活动的本质因素。◆全局主序与分辨主序的斜率一致,表明恒星形成主序在千秒差距尺度上依然成立,恒星形成活动受局部物理过程调控。◆在方法论上,论文指出仅使用恒星形成区域测量主序斜率更为合理,不同电离源的选取会显著影响结果。该工作为理解LSBG的形成与演化提供了重要的观测约束。</td></tr>
<tr><td>2026-09-01</td><td>TAPVid-MV: A Benchmark for Tracking Any Point in 3D Across Multiple Views<br><a href='http://arxiv.org/pdf/2609.01899'>论文</a></td><td>本文提出了TAPVid-MV，这是首个针对多视角同步视频中长期3D点跟踪任务的基准，填补了现有基准仅支持单视频或静态多相机系统的空白。该基准包含284个序列、1142路校准相机流以及109769条点轨迹，覆盖室内外、机器人、驾驶、人体动作和合成场景等七个子集。数据构建利用各数据集特有的辅助模态生成轨迹，并通过人工逐条视觉验证，保证了标注质量。实验显示超过30种基线方法均无法接近解决该任务，且现有多视角点跟踪器并未稳定优于单目跟踪器，揭示了领域挑战的难度。通过在同一数据集上联合评估重建与点跟踪，该基准能够区分几何恢复误差与点对应误差，并识别出几何恢复是准确3D点跟踪的主要瓶颈。◆首个支持相机运动下多视角长期3D点跟踪的基准。◆联合分析重建与跟踪以定位误差来源。◆释放的标注可复用于2D/3D跟踪、未来预测和4D重建任务。</td></tr>
<tr><td>2026-09-01</td><td>Linking neutral gas inflows and outflows to offsets in the star-forming main sequence and mass-metallicity relation<br><a href='http://arxiv.org/pdf/2609.01707'>论文</a></td><td>本文利用DESI DR2中约6000个具有Na I D吸收的恒星形成星系，首次在大样本上建立了观测到的中性气体流入流出与恒星形成主序(SFMS)及质量–金属丰度关系(MZR)偏离之间的统计联系。

◆将样本按气体流速分为缓慢流入、快速流入和流出三类宿主星系，并与恒星质量和红移匹配的对照样本进行比较，发现不同流动类型在SFMS和MZR上呈现系统而不同的偏离模式。

◆流出宿主(≤-50 km/s)使sSFR升高0.25–0.40 dex，并在低红移样本中金属丰度升高0.04–0.06 dex；缓慢流入宿主(0–100 km/s)同样使sSFR升高0.20–0.30 dex，但金属丰度无显著偏离；快速流入宿主(≥100 km/s)恒星形成增强较弱且金属丰度略低。

◆结合D_n4000的微小系统性偏移，结果表明缓慢流入支撑了增强的恒星形成而未稀释中心金属丰度，说明流入气体可能已预富集或在延长时间尺度上完成混合；而流出则位于SFMS上端1σ包络附近，符合反馈调节后续增长的图景。

◆整体上，这些观测支持了中性气体流作为重子循环不同阶段的示踪器，并对SFMS和MZR的散射贡献了系统性偏离，从而为重子循环&quot;调节器&quot;模型提供了直接的群体层面观测证据。</td></tr>
<tr><td>2026-08-29</td><td>Ground-to-Satellite Localization in Unconstrained Image Collections for 3D Scene Reconstruction<br><a href='http://arxiv.org/pdf/2608.29211'>论文</a></td><td>该论文针对无约束图像集合中实现度量精确、地理定位的3D场景重建难题，提出了一种基于跨视角（地面到卫星）定位的鲁棒层次化框架。

◆ 提出层次化跨视角定位框架，通过粗到精的位姿假设生成策略，实现地面图像到卫星图像的可靠定位，突破了对全景图像和已知初始位置等严格条件的限制。

◆ 利用Structure-from-Motion（SfM）模型提供的几何约束，结合核密度估计（KDE）对多个SfM模型中的噪声预测进行聚合，从而识别共识对齐并有效过滤异常值。

◆ 借助卫星参考对齐实现了米制尺度估计、相似场景（doppelgänger）检测以及不连续SfM重建的合并。

实验结果表明，该方法在具有挑战性的图像集合上能实现可靠的定位，生成比单纯使用SfM更完整、地理定位更精确的场景模型。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-08</td><td>RoMa-$Ω$: What Feed-Forward 3D Models Know About Image Matching<br><a href='http://arxiv.org/pdf/2609.09507'>论文</a></td><td>本文探究前馈3D重建模型对图像匹配的知识，并分析零样本patch特征匹配、3D点预测直接匹配和基于学习表示训练完整匹配器三种场景。
◆系统评估VGGT等前馈3D模型在图像匹配中的零样本、线性探测和端到端训练表现。
◆发现其零样本匹配较弱且深层更差，但学习表示对线性探测和完整匹配流程具有强迁移价值。
◆证明无需训练，其原始3D点预测在中等视角变化和模态差异下也能取得有竞争力的匹配结果。
◆提出RoMa-Ω，用VGGT-Ω替换RoMa v2的DINO骨干，在多个基准上超越现有匹配器，WxBS较RoMa v2提升8.1 mAA。</td></tr>
<tr><td>2026-09-06</td><td>Back to the Feature: Zero-Shot 6DoF Pose Estimation via Dense Local Features<br><a href='http://arxiv.org/pdf/2609.06726'>论文</a></td><td>B2TFPose是一种无需训练的零样本6DoF位姿估计方法，仅利用单个冻结的DINOv3视觉Transformer提取密集局部特征，即可跨越合成到真实的领域差异，无需任何任务微调。该方法重新审视经典局部特征匹配范式，并借助大规模自监督基础模型实现对新物体的位姿估计。在BOP基准的七个核心数据集上，B2TFPose无需精修即达到40.7平均AR，加入精修后达到56.4，超越现有无训练方法，并优于部分有监督方法，且推理速度具有竞争力。其核心贡献包含以下三点：
◆ 提出测地线非极大值抑制策略，用于选取视角多样化的模板集，支撑由粗到精的对应匹配。
◆ 提出渲染引导的重新对应机制，在估计位姿处合成物体特定视图并重建密集2D-3D对应，无需额外参数即可锐化初始位姿。
◆ 设计多掩膜假设选择策略，联合评分多个分割候选，有效解决分割模糊问题。</td></tr>
<tr><td>2026-09-06</td><td>Radiation, Rotation and Scale Invariant Feature Descriptor for Multimodal Image Matching<br><a href='http://arxiv.org/pdf/2609.06343'>论文</a> | <a href='https://github.com/yeyuanxin110/RRSI'>代码</a></td><td>本文提出一种面向多模态图像匹配的辐射、旋转与尺度不变特征描述子RRSI，有效应对几何形变和非线性辐射差异的挑战。其核心贡献在于设计了一个端到端的深度学习框架，能够联合编码模态间的几何与辐射关系。◆ 提出双头区域采样模块，同时进行笛卡尔和对数极坐标采样，兼顾空间结构并增强对旋转和尺度的鲁棒性。◆ 在统一深度特征空间中实现模态内、双头采样和模态间区域的联合特征编码、交互与融合，提升匹配精度。◆ 引入双向跨模态生成式重建约束，通过解码隐特征生成对应模态的结构块，锚定模态不变的几何拓扑，且推理时无额外开销。实验表明该方法在光学红外与光学SAR数据集上性能优越，支持0到360度全旋转及最高四倍尺度变化，并在计算机视觉、遥感和医学图像上展现良好泛化性。</td></tr>
<tr><td>2026-09-04</td><td>ARC-Loc: Leveraging Azimuthal Ray Convergence as a Geometric Cue for Direct Cross-View Localization<br><a href='http://arxiv.org/pdf/2609.04965'>论文</a></td><td>ARC-Loc提出一种全新的跨视角定位范式，无需BEV变换或外部深度模型，即可直接匹配地面图像与卫星图像。其核心思想借鉴人类“后方交会”定位技巧，将地面关键点转为卫星地图上的方位射线，并通过射线汇聚于用户位置这一几何约束完成定位。该方法设计了最小方位射线汇聚求解器确定交点，同时引入ARC损失来优化匹配网络，实现了显式的线到点对应。◆ 创新性地将地面到卫星匹配简化为二维方位射线求交，绕开病态的2D到3D提升过程，避免几何畸变与计算开销。◆ 提出轻量级ARC求解器和配套ARC损失，使网络训练可直接优化定位目标，且无需外部深度先验。◆ 在保持竞争精度的前提下，推理更快、内存更省，并能轻松嵌入现有跨视角定位框架，工程实用性突出。</td></tr>
<tr><td>2026-09-04</td><td>XDG: Accelerated Visual Disambiguation<br><a href='http://arxiv.org/pdf/2608.29733'>论文</a> | <a href='https://github.com/xtcpete/xdg'>代码</a></td><td>该论文针对三维重建中视觉混淆（doppelganger问题）导致错误匹配的难题，提出了一种高效的可扩展视觉消歧模型XDG。其核心洞察是3D基础模型已具备跨视角几何推理能力，因此消歧任务应直接适配骨干网络的表征，而非额外训练庞大的解码器重新学习配对关系。

◆ 创新点一：XDG采用轻量化的LoRA适配器对Depth Anything 3进行微调，避免了传统方法在骨干网络之上叠加重型Transformer分类器带来的巨大计算开销。

◆ 创新点二：创造性地将Depth Anything 3中的相机令牌重新用作紧凑的配对级分类令牌，再通过小型MLP头预测候选图像对是否观测到同一三维表面。

实验结果表明，XDG在保持与当前最优消歧方法相当精度的同时，实现了超过3倍的推理加速，在包含数千张图像的LaMAR场景中可节省十余小时处理时间，展现了出色的精度-效率权衡。</td></tr>
<tr><td>2026-09-02</td><td>Scalable Bayesian Optimization of Composite Functions for Image-Based Inverse Problems in Materials Characterization<br><a href='http://arxiv.org/pdf/2609.02126'>论文</a></td><td>本文针对材料表征中从科学图像反演物理参数的难题,提出了一种可扩展的复合函数贝叶斯优化方法SBOCF,用于电子显微学中样品厚度和晶体倾转角等关键参数的估计。该方法通过利用图像匹配目标的已知复合结构以及模拟图像中的中间信息,将原本需要建模的输出维度从24,649个像素大幅压缩至11个,显著提升了计算效率。

◆ 提出SBOCF方法,利用块级图像摘要加两项修正项,在保持原始像素级目标的同时将建模输出从24,649降至11,大幅降低计算开销。

◆ 在仅50次模拟器评估的预算下,SBOCF在SrTiO3基准测试中将最终SSE中位数降低最高达290倍,显著优于标准期望改进贝叶斯优化。

◆ 无需针对特定任务的预训练即可在实验数据上获得与文献一致的参数估计,并能直接用于下游叠层成像重建,恢复原本模糊的原子结构。</td></tr>
<tr><td>2026-09-02</td><td>GeoStore: Finding Small Storefronts in Large Scenes -- A Fine-Grained POI Localization Benchmark with Global-to-Local Asymmetric Matching<br><a href='http://arxiv.org/pdf/2609.02012'>论文</a></td><td>该论文针对POI本地化任务,指出其与视觉位置识别(VPR)的本质差异:查询图像是目标占据画面主体的近景特写,而参考图像是目标仅占小区域且周围有大量视觉相似店铺的远景街景,呈现显著的非对称细粒度匹配特性。现有面向VPR的全局描述子方法因单一向量难以突出小目标而表现受限。

◆ 提出了首个面向该非对称细粒度开放集设定的基准GeoStore,填补了POI本地化系统化评测的空白。

◆ 提出了GLAM全局到局部非对称匹配框架,结合检索锚定的全局描述子与局部非对称通路,将参考图像编码为压缩的区域token集合,通过可学习的软晚期交互与单查询探针进行匹配。

◆ 推理阶段复用同一组token实现轻量的互最近邻重排序,在Recall@1/5/10和mAP上超越强基线,同时重排序特征量减少约5倍、每对匹配成本降低约两个数量级。</td></tr>
<tr><td>2026-08-30</td><td>SGFormer: Structure-Guided Transformer for Robust Local Feature Matching<br><a href='http://arxiv.org/pdf/2608.03423'>论文</a></td><td>该论文针对局部特征匹配中现有无检测器方法(如LoFTR)在大幅视角变化场景下出现的注意力发散问题,提出了一种新颖的结构引导Transformer网络SGFormer。研究发现,标准Transformer的无约束全局注意力机制会使部分高置信度匹配落在重叠区域之外,降低匹配可靠性。

◆提出Triple-Structure-Attention(TSA)模块,利用网络浅层局部特征强化显著结构区域的特征表达,引导后续Transformer阶段将注意力聚焦于具有显著结构的重叠区域。

◆采用半稠密的由粗到精匹配流水线,自适应地更新显著结构附近的注意力,在提升全局建模能力的同时抑制非重叠区域的干扰。

◆在多个具有挑战性的摄影测量基准数据集上的实验表明,SGFormer有效缓解了注意力发散现象,显著提升了匹配精度与鲁棒性。</td></tr>
<tr><td>2026-08-27</td><td>SSMB: Self-Supervised Local Feature Detection under Motion Blur<br><a href='http://arxiv.org/pdf/2608.27181'>论文</a></td><td>本文针对运动模糊下关键点检测难题,提出去模糊化、自监督的检测器SSMB,无需手工检测器或外部伪标签,直接对模糊图像进行检测。现有方法多依赖耗时的去模糊后处理或回归手工关键点位置,前者易引入伪影,后者继承了手工检测器的假设偏差。

◆ 提出完全自监督的模糊鲁棒关键点检测框架,无需去模糊步骤或外部伪标签
◆ 设计局部判别性增强(LDE)模块,在全局特征混合后有效恢复细粒度局部判别能力
◆ 采用两阶段训练机制:合成几何形状预训练引导空间判别性,真实锐-糊图像对实现模糊不变检测
◆ 设计多组件自监督损失函数,联合约束跨域一致性、几何对齐与空间覆盖

在关键点检测、图像匹配、相对位姿估计和视觉定位等任务上,SSMB均刷新了稀疏关键点检测器的最优性能,一致超越现有监督与自监督基线方法。</td></tr>
<tr><td>2026-08-24</td><td>Misanthrope: A Privacy-Preserving Keypoint Detector<br><a href='http://arxiv.org/pdf/2608.23012'>论文</a> | <a href='https://github.com/fratopa/misanthrope'>代码</a></td><td>本文提出Misanthrope，一种面向图像匹配任务的隐私保护关键点检测器。针对分布式计算场景下本地图像特征易遭受反演攻击、泄露人像隐私的问题，Misanthrope通过自蒸馏训练策略，从源头避免在人体上检测关键点，而非依赖事后模糊处理。

◆ 创新点一：提出从源头规避隐私风险的检测思路，使反演攻击无法重建人物内容
◆ 创新点二：采用自蒸馏训练框架实现&quot;避人&quot;关键点检测，无需人工标注隐私敏感区域
◆ 创新点三：证明传统特征管道的反演图像可用于检测和重识别场景中的人物
◆ 创新点四：在人物作为干扰物的困难场景下，匹配性能超越现有最优方法

在Image Matching Challenge 2021 Phototourism测试集9个场景中，Misanthrope在7个场景上取得稀疏特征提取器最优表现，同时有效缓解了隐私反演攻击风险。</td></tr>
<tr><td>2026-08-23</td><td>CausalCache: Conditional High-Fidelity Restoration for Long-Horizon GUI Agents<br><a href='http://arxiv.org/pdf/2608.22577'>论文</a></td><td>CausalCache 针对长程 GUI 智能体在视觉上下文预算受限时难以兼顾历史保真度的问题，提出了条件保真度恢复框架：每个事件以摘要形式存储并链接归档截图，预算 B 决定哪些事件被提升为&quot;摘要+图像&quot;形式。与 Recent-B 将所有槽位分配给最近事件不同，CausalCache 跨完整轨迹重新分配预算，仅当远距事件的条件边际效用更高时才替换近期图像。方法在 OSWorld-Verified 上比纯摘要记忆提升约 13 个成功率点；在跨应用移动基准上整体提升 3.7 分，记忆关键子集提升 8.6 分，匹配对照组无显著差异。

核心创新点：

◆ 提出条件保真度恢复机制，根据条件边际效用跨完整轨迹动态分配视觉预算，使高保真图像资源从机械偏向近期事件转向任务相关的关键事件。

◆ 设计历史门控键值适配器（HGKV），仅修改被恢复的历史图像令牌，无历史图像时完全旁路，对冻结策略影响最小。

◆ 引入匹配预算对照组与按臂锚定的双重差分监督，确保预算开销相同情况下，仅真正的选择性恢复才获得增益。

◆ 构建预算感知选择器，在摘要事件中自动挑选最值得恢复为高保真的目标，提升决策可解释性与效率。</td></tr>
<tr><td>2026-08-19</td><td>Evaluation of Image Matching Methods for Visual Odometry on UAVs<br><a href='http://arxiv.org/pdf/2608.18624'>论文</a></td><td>本文针对无人机在GNSS信号失效场景下的导航难题，研究了视觉里程计作为关键替代方案。论文系统评估了多种当前最先进的图像匹配方法在无人机下视相机位置追踪任务中的表现，并构建了专用合成数据集进行测试验证。

◆构建了用于无人机视觉里程计评估的合成数据集，解决了真实飞行数据采集成本高、场景受限的问题
◆对深度学习与传统图像匹配方法在VO任务中进行了系统全面的对比评估
◆研究发现虽然最新RoMa匹配器效果最佳，但传统SIFT特征在特定场景下仍能超越部分最新的深度学习方法

该工作为深度学习方法与传统特征方法在无人机视觉导航系统中的实际应用选择提供了重要参考依据。</td></tr>
<tr><td>2026-08-11</td><td>Multi-Level Evidence Aggregation for Robust Facial Phenotype Retrieval in Rare Genetic Disorder Prioritization<br><a href='http://arxiv.org/pdf/2608.11037'>论文</a></td><td>本文针对罕见遗传疾病的面部表型检索任务，提出了一种推理阶段的多层级证据聚合框架。该框架在不修改现有GestaltMatcher-Arc编码器的前提下，从患者和疾病两个层级整合多源证据，核心创新包括：

◆ 嵌入级患者聚合：融合同一患者的多张图像信息，增强个体表征的鲁棒性
◆ 患者加权的疾病质心表示：整合多个确诊患者的证据构建疾病级全局表征
◆ 混合个体-质心评分机制：结合全局疾病证据与局部近邻信息，提升检索判别力

实验在GMDB v1.1.4多个子集上验证，top-1准确率在GMDB-Freq上从38.52%提升至48.82%，GMDB-Rare上从19.38%提升至23.79%，多图像子集提升尤为显著，分别达到60.94%和26.71%。该方法无需重新训练编码器，推动了面部表型检索从孤立单图匹配向多层级证据聚合的范式转变。</td></tr>
<tr><td>2026-08-10</td><td>XFeat Revisited: Reproducibility and Evaluation of a Lightweight Image Matcher<br><a href='http://arxiv.org/pdf/2608.09519'>论文</a></td><td>本文对轻量级图像匹配方法XFeat进行了系统的可复现性研究。研究者基于论文与补充材料重新实现了网络架构，并独立再评估了作者发布的官方预训练权重，揭示出论文、补充材料与公开代码在骨干布局、融合模块和训练损失等方面存在多处实现差异。复现模型在MegaDepth-1500和ScanNet-1500基准上与原版结果相当，部分情况下甚至更优，验证了XFeat在精度与效率上的良好折中。

◆通过架构消融实验，澄清了原始论文未充分论证的设计选择：并行关键点分支对半稠密匹配确实重要，但其优势程度不如原作者声称的显著；而关于单一跳跃连接最佳放置位置的证据则不充分。

◆在下游任务复现中，单应性估计结果与原文高度一致，但Aachen视觉定位即使使用官方权重也低于论文报告，提示评估流程对未明确说明的细节较为敏感。

◆首次将XFeat拓展至零样本跨域和跨模态匹配场景，涵盖视网膜成像、热红外-可见光以及多模态遥感影像，发现其在一般跨域条件下仍具一定有效性，但在严重模态差异下性能急剧退化。</td></tr>
<tr><td>2026-08-06</td><td>A Low-Latency ASIC Architecture for Real-Time Line Segment Detection<br><a href='http://arxiv.org/pdf/2608.06439'>论文</a></td><td>本文针对嵌入式视觉中线段检测对实时性与低功耗的严苛需求，提出了一种基于步长算法的低延迟ASIC架构。该架构采用全流水线设计，每时钟周期处理一个像素，具有确定性延迟，便于系统级集成。在45nm CMOS工艺下综合后，设计在VGA分辨率下可达325 FPS、Full HD下48 FPS，功耗仅25.54 mW，面积0.412 mm²；频率提升至125 MHz时，VGA帧率可达406 FPS。

主要创新点如下：
◆ 基于寄存器的行缓冲与数据复用机制，有效降低存储访问开销
◆ 无乘法器的MCM滤波器设计，显著简化硬件实现
◆ 8类角度量化策略，减少计算复杂度并提升匹配效率
◆ 类CAM关联存储器，实现单周期快速匹配
◆ 优化的重复线段去除机制，提升输出结果质量

相比基于Line Hough变换的90nm ASIC方案，本设计功耗降低49%，帧率提升超过1.6倍，非常适合自动驾驶、视觉SLAM等边缘计算应用。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-14</td><td>Closed-form Bayesian homography estimation from noisy point correspondences<br><a href='http://arxiv.org/pdf/2609.15227'>论文</a></td><td>本文针对传统单应估计多只给点估计、不直接量化噪声不确定性的问题，提出一种快速的贝叶斯单应估计方法。该方法在点对应中显式融合测量不确定性与先验知识，并输出单应参数的后验分布，从而将不确定性传播到后续任务。
◆ 提出面向噪声点对应的贝叶斯单应估计框架，可同时给出参数后验分布与不确定性量化。
◆ 在齐次坐标下推导出单应后验均值的闭式解，显著提高计算效率。
◆ 结合迭代贝叶斯策略处理模型非线性，扩展闭式结果的适用性。
◆ 合成实验表明其在不同噪声条件下精度优于DLT，图像拼接实验验证了真实图像适用性并能额外提供不确定性信息。</td></tr>
<tr><td>2026-09-14</td><td>Comparing Trajectories from Positions Alone: Curvature-Based Time Alignment and Drift Error Metric<br><a href='http://arxiv.org/pdf/2609.14936'>论文</a></td><td>本文针对机器人领域参考轨迹难以获取、ATE/RPE依赖未明假设与参数而可能导致误导比较的问题，提出一套标准化、可靠的轨迹评估协议。  
◆ 提出基于曲率信号的新型时间对齐方法，仅凭位置信息即可比较轨迹。  
◆ 提出按行驶距离归一化的漂移误差度量，提升不同长度轨迹间的可比性。  
◆ 显式处理时间同步、采样对齐与外参标定，并通过敏感性分析量化其影响。  
该协议提升了状态估计、定位与SLAM中轨迹评估的严谨性、可复现性和标准化程度。</td></tr>
<tr><td>2026-09-14</td><td>Semantic Fibers and Cross-Gram Interference: A Calculus of Safety Drift in Overcomplete Representations<br><a href='http://arxiv.org/pdf/2609.14861'>论文</a></td><td>论文针对模型英文拒绝但忠实翻译下遵从的跨语言安全失败，提出用审计等价关系而非仅输出行为来刻画安全漂移。
◆ 在给定商、表示、度量、特征字典、评分头、阈值和对比模型下，将安全漂移精确刻画为纤维内对比的交叉Gram泛函，其最坏值为支撑函数，间隔不变性由零化子条件给出。
◆ 引入受杠杆对偶χ²=1/ℓ-1支配的内在校准暴露度量，把观察漂移分成可重校准的读取器故障、病态不可靠的精确校正和读取器无法消除的表示层碰撞三类。
◆ 该分类表明相同观察暴露可能对应根本不同的修复判决，从而改变安全干预选择。
◆ 框架可扩展到锥值安全头，并用非绑定换序恒等式诊断线性控制接口，其校准残差可预测未见状态与目标上的三控制组合误差。
◆ 实验上该残差的中位Spearman相关达0.964，显著优于静态交叉Gram基线的0.269，验证其诊断与预测价值。</td></tr>
<tr><td>2026-09-12</td><td>GeomVLA: Unifying Scene, Motion, and Action in 3D<br><a href='http://arxiv.org/pdf/2609.13812'>论文</a></td><td>GeomVLA提出统一场景、运动与动作的VLA模型，在机器人中心3D坐标系中融合感知、潜在场景运动预测与动作生成。
◆ 将预训练VLM特征借助深度和相机标定提升为空间接地的3D场景token，同时保留VLM语义表征。
◆ 提出3D Scene Trajectory Denoiser，以任务为条件学习场景点未来3D运动的潜在表示。
◆ 不直接开环执行预测轨迹，而是提取中间运动token，通过几何感知注意力条件化3D flow-based动作去噪器。
实验上在CALVIN达SOTA，LIBERO和RoboTwin2.0有竞争力，真实操作无机器人动作预训练也超越强基线。
消融表明仅未来运动推理不够，主要增益来自场景表示、运动预测与动作在感知到动作全流程中保持几何一致。</td></tr>
<tr><td>2026-09-11</td><td>DRS-VPT: Directly Relocalizing in a Scan with Vision Point Transformers<br><a href='http://arxiv.org/pdf/2609.12557'>论文</a></td><td>DRS-VPT是一种面向基础图像到扫描配准的前馈Transformer架构。
◆ 它统一预测扫描位姿、扫描点图及每台相机位姿和点图，并将它们统一表示在第一相机坐标系中。
◆ 它引入粗到细的逐点与逐像素特征金字塔，实现扫描到首张图像的直接重投影对齐。
◆ 该统一公式连接自动驾驶相机-LiDAR标定与室内相机到地图重定位等下游任务。
实验表明，单一DRS-VPT在自动驾驶图像-LiDAR配准上达到最优，在室内重定位中无需训练地图特定权重也具竞争力，并具有强零样本迁移能力。
定性结果还显示模型学到背面点遮挡等复杂扫描到图像投影特性。</td></tr>
<tr><td>2026-09-09</td><td>Automatic Reproducible Camera Intrinsic Calibration<br><a href='http://arxiv.org/pdf/2609.10082'>论文</a></td><td>本文提出全自动相机内参标定流程，可从采集数据中自动决定高质量图像与径向畸变阶数。核心贡献是无需人工筛选图像或指定畸变阶数，并通过迭代剔除与留出验证提升标定可靠性。
◆ 采用迭代剔除机制，在当前候选图像集估计参数，并移除平均残差超过中位数若干倍的视图，且在每个候选畸变阶数下独立运行，使保留图像集与该阶数残差尺度一致。
◆ 通过留出图像选择畸变阶数，固定内参与畸变、仅重估标定板位姿，确保新增畸变系数得到独立观测支持。
◆ 集成上述步骤为交互式标定工具，支持全流程数据检查和参数估计。
实验在自有相机数据与五个公开真实数据集上表明，图像筛选使留出重投影误差降低25%，阶数选择再降低5%，在四种配置中取得最低留出均值，且无需人工选图，并计划公开代码和数据。</td></tr>
<tr><td>2026-09-07</td><td>P$^2$Calib: Utilizing Pattern Priors for LiDAR-Camera Extrinsic Calibration<br><a href='http://arxiv.org/pdf/2609.07516'>论文</a> | <a href='https://github.com/JokerJohn/P2Calib.git'>代码</a></td><td>本文提出P2Calib，一种利用标定板CAD模型提供的模式先验来提升激光雷达与相机外参标定精度的方法。针对传统四孔标定流程中激光雷达侧孔中心提取受稀疏角覆盖与混合像素影响的问题，该方法将已知孔半径作为拟合约束，有效防止中心估计在数据稀疏时发生退化。进一步地，P2Calib将四个孔的刚性矩形布局作为全局一致性约束，用于修正各孔之间的残余误差。上述两种先验被集成到一个包含完整标定流程的交互式工具中。在模拟与真实数据集上的实验表明，相比基线，联合配准残差分别降低90%和82%，留出重投影误差分别降低96%和77%。代码与数据已公开。
◆创新点一：将已知孔半径作为拟合约束，缓解稀疏角覆盖导致的孔中心估计退化。
◆创新点二：利用四孔刚性矩形布局作为全局一致约束，消除跨孔残余误差，提升整体标定精度。</td></tr>
<tr><td>2026-09-03</td><td>Object Concepts Emerge from Motion<br><a href='http://arxiv.org/pdf/2609.04348'>论文</a></td><td>该论文提出一种受生物启发的自监督框架，从原始视频中的运动信息学习单张图像的物体中心表征，无需人工标注或相机标定。核心思路是用光流与聚类生成伪实例掩码，并通过像素级成对度量学习训练单图编码器，使静态图像也能保留实例身份与一致性。作者构建了七千多小时视频产生的四点二一亿帧带伪标签数据，并提出运动验证自训练方法，结合模型提议与运动证据扩展监督规模。最终将学习到的表征蒸馏至多种Swin骨干网络，在深度估计、三维检测、占用预测及规划任务上取得优于或媲美强基线的结果。  
◆ 首次利用运动边界作为物体级分组信号，将视频中的光流转化为监督静态图像编码器的伪实例掩码。  
◆ 提出运动验证自训练，融合模型输出与运动线索生成更可靠的大规模伪标签，覆盖四亿余帧。  
◆ 无需语义标注与相机参数，仅靠运动即可学习几何与实例敏感表征，开辟了视觉预训练的互补新路线。</td></tr>
<tr><td>2026-09-03</td><td>Principia: Relational Physics Tests for Video Models<br><a href='http://arxiv.org/pdf/2609.04200'>论文</a></td><td>本文针对视频模型物理推理评估的难题,提出了一种基于相对关系而非绝对运动的新评估范式。核心思想是同一场景中两个遵循相同物理定律的物体,其运动关系应当具有可预测的标定无关性。

◆ 创新点一:提出Principia基准,涵盖重力、弹性恢复、摩擦、转动惯量、抛体运动、动量、摆动和弹簧振子等八种牛顿物理现象,跨越平移、旋转、碰撞和振荡四类动力学,采用受控协议录制的真实场景。

◆ 创新点二:设计了一种标定无关的一致性评分方法,直接在图像空间中量化物理违反程度,规避了帧率、物体尺度和相机标定等模糊因素的影响。

◆ 创新点三:对六个当前最先进的视频生成器进行大规模评测,结果显示所有模型在Principia上得分均不超过0.42,而在VBench上却普遍达到0.8左右,暴露了现有模型物理推理能力的严重不足。

◆ 创新点四:评估了视觉语言模型检测关系性物理违反的能力,最佳模型准确率仅为67%,多数模型表现接近随机水平,表明当前多模态模型对物理一致性的判别能力同样有限。</td></tr>
<tr><td>2026-09-02</td><td>A Top-Down Framework for Metric-Scale Athlete Localization from Single Broadcast Frames<br><a href='http://arxiv.org/pdf/2609.02705'>论文</a></td><td>本文针对超高清广播画面中运动员的尺度极端变化问题，提出了一种自顶向下的米制尺度定位框架，实现了从单帧图像恢复运动员世界坐标的精准定位。核心思路是将复杂的定位问题拆解为尺度归一化、关键点估计和几何反投影三个可控步骤，从而逐一攻克难点。

◆ 提出边界感知自适应分块（Boundary-Aware Adaptive Tiling）方法，通过粗检测迭代扩展分块边界，保证目标完整包含，有效缓解极端尺度差异下的召回率下降。

◆ 将RTMPose-X改造为骨盆与地面投影点的双关键点估计器，并重新设计门控注意力单元以适配这两个几何耦合点的联合预测。

◆ 利用相机标定参数，通过确定性光线投射将二维地面投影反演为三维世界坐标，简洁地消除了透视畸变带来的残余误差。

在公开测试集上，该方法取得LocSim 97.44和mAP 0.9128的成绩，较基线提升超过21%，为高分辨率体育分析提供了鲁棒解决方案。</td></tr>
<tr><td>2026-09-01</td><td>Feed-Forward Multi-view Multi-person Reconstruction with Contrastive Human-Aware 3D Representation<br><a href='http://arxiv.org/pdf/2609.00745'>论文</a></td><td>本文针对非受限环境下多视图多人体重建的难题,提出了一种基于对比学习的自顶向下新范式,实现了鲁棒且高效的人体重建。

◆ 提出统一的实例中心化人体感知三维空间,将多视图观测提升并融合到该共享空间中,通过跨模态对比学习同时完成相机标定、跨视图关联与人体重建,避免了传统自底向上方法对精确标定和显式匹配的依赖。

◆ 设计空间对比学习策略,在三维空间中实现跨视图、跨模态的实例级特征对齐与分离,使对应关系推理、语义聚合和实例判别均可原生在三维空间内完成,显著提升了严重遮挡下的跨视图一致性与鲁棒性。

◆ 以前馈方式从实例级三维人体token中回归SMPL参数,实现结构化人体模型的快速恢复,无需复杂的后处理优化流程。

大量实验表明,该方法在具有挑战性的真实场景中能够实现准确、鲁棒且高效的多视图多人体重建。</td></tr>
<tr><td>2026-08-28</td><td>Observability Analysis of Joint Steering and Extrinsic Calibration<br><a href='http://arxiv.org/pdf/2609.05498'>论文</a></td><td>本文针对平面自行车模型车辆，在同时估计车辆位姿、平面激光雷达外参和转向角偏差时，系统研究了系统的局部弱可观性。通过基于李导数的非线性可观性分析，分别考察了静止、直线、定曲率圆弧以及直线加圆弧组合运动。研究发现，静止和单一运动基元均存在不可观方向，而直线与圆弧组合运动可消除这些退化特性，使七状态系统达到完全局部弱可观。该工作为选取能充分激励转向与传感器外参的标定轨迹提供了理论依据。  
◆首次在统一框架下分析了转向角偏差与激光雷达外参联合标定的可观性耦合关系。  
◆明确了不同运动基元下位姿、外参平移与偏航角、转向偏差之间的不可观方向及耦合结构。  
◆证明了直线与圆弧组合运动能实现七状态系统的完全局部弱可观，并给出了理论判据。</td></tr>
<tr><td>2026-08-28</td><td>Adversarial Calibration Attack on Autonomous Vehicles<br><a href='http://arxiv.org/pdf/2608.28778'>论文</a></td><td>本文针对自动驾驶车辆相机-激光雷达在线标定过程，提出了一种新型物理攻击方法——对抗标定攻击（ACA）。传统AV攻击多假设标定准确，而本文创新性地揭示了在线标定模块作为新攻击面的安全风险，指出被污染的标定更新会在后续融合操作中持续传播，影响感知到规划控制的整个系统。

◆首次将在线传感器标定识别为自动驾驶的关键攻击面，揭示被篡改的标定结果可在融合模块中长期持续造成系统性错误。

◆提出ACA攻击，仅需单张对抗海报即可同时欺骗标定异常检测器以触发标定流程，并诱导标定估计器输出错误的变换矩阵。

◆设计统一的联合优化框架，同时优化海报的几何形状与纹理，以满足欺骗检测器和误导估计器双重目标。

◆在KITTI、nuScenes数据集上实现最高33.9度的旋转标定误差，CARLA仿真中导致车辆碰撞，并在真实Husky机器人上通过物理实验验证了攻击的有效性，充分证明在线标定是实际可利用且危及安全的关键攻击面。</td></tr>
<tr><td>2026-08-28</td><td>From Perspective to Fisheye Depth Estimation and Open-Vocabulary Segmentation<br><a href='http://arxiv.org/pdf/2608.27860'>论文</a> | <a href='https://github.com/Suchisrit/DEX'>代码</a></td><td>本文针对视觉基础模型在鱼眼图像上因径向畸变导致的性能下降问题，提出了一种将透视图像训练模型泛化到鱼眼相机的方法。该方法的核心是一组可学习参数 DEX，通过建模鱼眼畸变系数及潜在空间中的分布偏移，并利用自监督对齐损失将鱼眼图像的潜在特征转化为接近透视图像的特征，从而恢复高保真估计。DEX 具有架构无关和任务无关的特性，作者在单目深度估计和开放词汇分割任务上同时验证了卷积网络和 Transformer 架构的效果，在室内外鱼眼数据集上均显著优于基线方法。

◆ 提出可学习的 DEX 轻量模块，显式建模鱼眼畸变系数与潜在空间分布偏移，将鱼眼特征向透视特征空间对齐，无需重新训练基础模型。
◆ 设计自监督对齐损失，无需鱼眼真值标签即可实现跨域特征匹配，具有良好的实用性与可扩展性。
◆ 方法具备架构与任务无关性，可同时适配卷积与 Transformer 框架，并覆盖深度估计与开放词汇分割两类任务。
◆ DEX 的激活值可被解码为畸变系数，天然支持相机标定功能，实现一物多用。</td></tr>
<tr><td>2026-08-27</td><td>GeoMAD: Geometry-Aware Multi-View Anomaly Detection via Deformable Fusion and Distributional Alignment<br><a href='http://arxiv.org/pdf/2608.26724'>论文</a></td><td>GeoMAD针对多视角异常检测中的几何对应与分布一致性问题，提出了一个统一的多视角多类别框架，在2D特征空间内实现了兼具几何感知与分布一致性的高效融合。

现有方法要么依赖体素融合带来高计算成本和类别特定假设，要么采用轻量级patch融合但缺乏连续的跨视角对应。GeoMAD通过两个核心模块解决了这一矛盾。

◆ 提出跨视角可变形融合模块(CDFM)，直接在2D特征图上学习内容自适应、视角对特定的采样偏移，并结合多尺度窗口金字塔与图像全局参考采样，实现无需相机标定、体素构建或3D监督的层次化跨视角几何对应。

◆ 引入分布视角对齐损失(DVA)，通过自监督方式将每个视角的瓶颈分布对齐至逐实例的视角中心目标，在无需像素级对应的情况下强制全局一致性。

◆ 将局部几何对应与全局分布一致性结合，在保持2D特征学习效率的同时，桥接了两类极端方法的优缺点。

在Real-IAD和MANTA-Tiny上的实验表明，GeoMAD在统一多视角异常检测中取得了优异的检测与定位性能。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vlm'>Robot VLM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-15</td><td>DriveMCP: An Agentic AI framework for Advanced Driver Assistance System<br><a href='http://arxiv.org/pdf/2609.17247'>论文</a></td><td>DriveMCP提出一种模块化、可审计的智能体驾驶辅助框架，将感知、合规推理、车辆状态解释与安全仲裁统一为一条流水线。
◆ 以DriveLM作为视觉语言前端生成图结构场景理解与语言化驾驶信息，并通过结构化解析层从模型输出中提取限速与辖区线索，而非直接注入仿真真值。
◆ 采用有状态编排层统一调度三类MCP专家服务：规则服务器做辖区交通法规与标志约定的检索增强合规推理，天气服务器估计牵引风险与限速建议，MCP-CAN服务器接入CAN/OBD遥测与诊断上下文进行健康感知风险塑形。
◆ 将专家输出融合为结构化决策与建议动作，再由受RSS启发的护栏在有限在线自适应下仲裁“告知”与“执行”。
◆ 在CARLA多语言、跨境和动态限速场景中验证，相较VLM-Direct、VLM-Direct+RAG和VLM-Tools-NoArbiter基线，减少交通违规与超速，提升危险响应时间，并保持亚秒级建议延迟。</td></tr>
<tr><td>2026-09-15</td><td>sensVLA: Spatially-Grounded Vision-Language-Action Model for Autonomous Wheel Loader<br><a href='http://arxiv.org/pdf/2609.17021'>论文</a></td><td>sensVLA是面向自主轮式装载机的视觉-语言-动作架构，核心是在统一决策中融合任务语义、第一视角、本体感受与3D场景几何。
◆ 它结合Qwen3-2B视觉语言模型与全可训练Transformer动作专家，并用流匹配速度回归训练动作专家。
◆ 它将前后激光雷达融合得到的BEV特征，经专用交叉注意力通路直接送入动作专家，同时让视觉语言模型处理前后RGB以提供任务条件语义。
◆ 该设计解耦空间定位与语言推理，但在决策时保留两流交互，从而显式增强空间grounding。
◆ 动作专家预测纵向速度、转向、车体位移、臂速率和铲斗速率六个控制维度。
◆ 在真实装载机数据上，加载场景纵向速度RMSE降低28%、位移误差降低9%，相机流损坏或移除时退化减少29%。</td></tr>
<tr><td>2026-09-15</td><td>Search-Based Metamorphic Testing of Vision-Language Models in Autonomous Underwater Robotic Software<br><a href='http://arxiv.org/pdf/2609.17007'>论文</a></td><td>本文聚焦自主水下机器人软件中视觉语言模型质量保障不足，提出搜索式蜕变测试方法 MetaVLM。该方法通过识别水下图像的最小变换集来诱发错误预测，从而暴露 VLM 失效。它使用 NSGA-II 多目标搜索，并在 BLIP 和 CLIP 上与随机搜索基线对比。
◆ 面向 AUR 水下环境，将蜕变测试与搜索优化结合用于 VLM 质量评估。
◆ 以最小图像变换集为目标，用 NSGA-II 多目标搜索高效诱导并暴露模型误判。
◆ 在 BLIP 和 CLIP 上实证对比随机搜索，揭示 VLM 强弱并为软件工程实践与研究提炼经验。</td></tr>
<tr><td>2026-09-15</td><td>Bridging Learned Visual Perception and Symbolic Belief-Space Planning<br><a href='http://arxiv.org/pdf/2609.16884'>论文</a></td><td>论文关注部分可观测环境下，智能体如何在不完整状态知识下获得可验证的符号规划。现有 VLM-as-planner 和 VLM-as-grounder 两类范式虽连接视觉感知与符号推理，却忽略规划中的不确定性，导致鲁棒性不足。
◆ 提出第三种范式 VLM-as-probabilistic-grounder，将 VLM 谓词 grounding 的不确定性建模为符号状态上的概率分布。
◆ 使规划器能在信念空间而非确定性初始状态下规划，从而生成对感知不确定性更鲁棒的计划。
◆ 在模拟家庭机器人实验中，该方法相比确定性 grounding 提升了鲁棒性和任务成功率，表明基础模型可用于不确定环境下的可靠规划。
总体而言，其核心贡献是桥接学习视觉感知与符号信念空间规划，为不确定感知下的可验证规划提供了新路径。</td></tr>
<tr><td>2026-09-15</td><td>MessyMem: Learning-from-Doing Memory for Mobile Manipulation<br><a href='http://arxiv.org/pdf/2609.15976'>论文</a></td><td>论文提出MessyMem，一个面向移动机械臂的持久记忆系统，使机器人能从交互经验中学习并跨未来任务重用知识。  
◆维护空间接地的3D场景图，持续记录物体与位置信息。  
◆将交互中学到的物体属性和操作结果增强到场景图中。  
◆链接视觉观察，支持从历史关键帧中进行细粒度回忆与证据检索。  
在仿真和真实移动机械臂上评估，连续25任务、超3小时的模拟中达到80.0%任务进度。  
它比最强消融高14.8个百分点、比最强外部基线高28.9个百分点，并能从数千关键帧及一小时以上历史中检索任务相关证据。</td></tr>
<tr><td>2026-09-14</td><td>UDAV: Uncertainty-Driven Adaptive VLM Waypoint Planner<br><a href='http://arxiv.org/pdf/2609.16368'>论文</a></td><td>UDAV面向无人机引导无人车越野导航，利用VLM从航拍图像生成航点，并解决其预测缺乏可靠性指示的问题。
◆ 提出多次随机轨迹采样并选取medoid作为自一致名义路线，以优于单次确定性预测。
◆ 基于随机轨迹空间离散度估计航点预测不确定性，并在内部航点最大不确定性超阈值时触发重考虑阶段。
在400条两架无人机飞行保留轨迹查询上，随机medoid将ADE从147.4降至115.9像素，完整规划器平均ADE为110.4像素，较确定性规划降低25.1%，且全部查询均产生有效轨迹。
UDAV还取得最低90分位和95分位误差，优于K=10共识基线，并以K=5 medoid为参照将这两项误差从225.3和326.0降至199.0和290.8像素。
◆ 证明随机VLM预测既能提供更强名义路线，也能提供可操作的不确定性信号，以选择性缓解大规划误差。</td></tr>
<tr><td>2026-09-14</td><td>WLA$^3$: World Latent Action Modeling for Semantics, Dynamics, and Kinematics<br><a href='http://arxiv.org/pdf/2609.15870'>论文</a> | <a href='https://wla-3.github.io/'>代码</a></td><td>论文提出WLA^3框架，以世界状态转移中的潜在动作作为跨异构数据的统一低噪监督，缓解通用策略模型动作标签稀缺且不统一的问题。WLAM从局部多模态世界状态变化中学习紧凑潜在动作和转移特征，并用部分模态重建与重叠窗口一致性增强鲁棒性。
◆ 统一世界潜在动作表示：把同步相机视角与可用具身状态变化编码为紧凑局部潜在动作及更丰富转移特征。
◆ 跨语义、动态和运动学复用：局部潜在动作支持物理动态建模，段级特征经SLA监督VLM，动作专家联合预测潜在动作与机器人控制。
◆ 人类视频与机器人轨迹协同：人类视频提供可扩展转移监督，机器人轨迹把共享表示落地为可执行原生控制并支持人到机器人迁移。
实验显示，LARYBench上32维潜在动作平均分类准确率达67.89%；六项真实机器人任务平均成功率81.9%，优于π0.5的66.2%，且随中期数据规模提升而改善。</td></tr>
<tr><td>2026-09-14</td><td>Planning in the Backbone: DiffAdapterVLA for Native Continuous Trajectory Generation with Driving VLMs<br><a href='http://arxiv.org/pdf/2609.15322'>论文</a></td><td>本文提出DiffAdapterVLA，将驾驶规划直接嵌入VLM骨干，实现Planning in the Backbone。  
◆将显式轨迹token注入VLM后层，使轨迹状态在骨干前向计算中与不同深度驾驶条件共同演化。  
◆用轻量逐层DiffAdapter把该计算组织为递归轨迹精炼，实现连续轨迹生成。  
◆设计非对称联合注意力，保持条件流对轨迹规划的有向指导。  
◆仅适配轻量轨迹模块，无需独立规划器，把已有驾驶先验转成高效连续规划能力。  
NAVSIM实验表明，该方法以少量可训练参数实现高质量闭环规划和低端到端延迟，验证了后层联合演化的有效性。</td></tr>
<tr><td>2026-09-14</td><td>GRAVA: Grounded Reasoning-to-Action Representation and Learning for Autonomous Driving<br><a href='http://arxiv.org/pdf/2609.15169'>论文</a></td><td>本文提出GRAVA，围绕Grounded Reasoning-to-Action，将grounding、reasoning与动作生成统一在单一自回归流中。
◆ 将动作相关语言指代链接到2D视觉区域和自车物理状态，并以轨迹锚定类型图组织对象交互与决策，再序列化为grounded reasoning。
◆ 让单一VLM先输出grounded reasoning，再生成紧凑Executable Planner动作，并确定性解码为连续轨迹，紧密连接推理与可执行行为。
◆ 提出agentic GRA数据构建流程，融合前向场景grounding与后向轨迹anchoring，构建含220万grounded QA和7万GRA推理轨迹的GR-NavSim。
◆ 设计渐进训练策略，先预训练建立grounded cognition，再通过模仿建立推理到动作接口，最后用强化学习与探索提升驾驶行为。
GRAVA-8B仅用约60%人类驾驶示范做动作监督，就在NAVSIM纯自回归驾驶模型中达SOTA，并在内部长尾上使关键物体合规率和闭环驾驶分数较仅动作预测分别提升19.3%和20.5%，表明保留动作相关物理证据贯穿grounded reasoning到可执行动作具有显著收益。</td></tr>
<tr><td>2026-09-14</td><td>C$^2$Nav: Compare Before You Commit for Zero-Shot Vision-and-Language Navigation<br><a href='http://arxiv.org/pdf/2609.15142'>论文</a></td><td>C2Nav提出一种让VLM只比较控制器构造备选、而把几何量、阈值、动作幅度与执行留给物理侧的互补型模型-机器人接口，并实现为免训练框架。
◆ 看：对经过物理校验的候选视角做序数Gaze Election，把选择转化为相对比较而非直接输出路点或朝向。
◆ 记：维护紧凑路线草图，并比较相邻指令段假设，以支持长程导航中的指令分解与状态追踪。
◆ 到：结合犹豫阶梯、回看比较和可撤销回退，将停止判断变为可复核、可撤回的决策。
在OpenNav R2R-CE 100上，C2Nav搭配Qwen3-VL-8B-Instruct达到41.0% OSR、31.0% SR、16.7% SPL，搭配GPT-5.5达到54.0% OSR、44.0% SR、29.0% SPL。
消融和角色反转显示，去掉三大模块或把比较式回答换成基数/绝对式回答都会显著降低SR，说明受约束决策接口与更强VLM推理互补而非可互换。</td></tr>
<tr><td>2026-09-14</td><td>PhysBrain 1.5: From Vision-Language Models to Physical Foundation Models<br><a href='http://arxiv.org/pdf/2609.14973'>论文</a></td><td>PhysBrain 1.5提出统一物理基础模型，将物理环境理解、动作生成与未来状态预测整合进同一学习框架，并围绕观察、交互、环境变化的物理闭环建模。
◆ 以通用视觉语言模型为起点，把语言响应、末端运动与密集视觉目标编码成离散序列，通过自回归下一token预测联合优化。
◆ 预训练仅用人类交互视频提供具身监督，以任务为中心的情节关联语义空间上下文、恢复运动和后续观察。
◆ 通过混合人类演示、机器人轨迹和模拟经验的监督微调，模型获得跨源适应能力。
在28个具身理解基准上，8B模型均分72.5，创开源新SOTA，与GPT-6-Astra、Gemini 3.6 Flash等领先闭源模型相当，并在14项基准上取得开源最佳，同时保留通用多模态能力。
定性结果表明，它能生成末端执行器轨迹，并通过空间对齐的RGB、深度和机器人掩码输出预测未来场景。</td></tr>
<tr><td>2026-09-13</td><td>NavPatch: Evidence-Guided Object-Level Costmap Correction with Vision-Language Models<br><a href='http://arxiv.org/pdf/2609.14543'>论文</a></td><td>本文提出NavPatch，一种面向移动机器人代价地图的对象级修正层，用于弥合几何障碍表示与导航语义需求之间的差距。
它利用视觉语言模型进行周期场景理解，对导航相关物体赋予ADD、REMOVE或EXTEND修正，并用开放词汇定位、LiDAR/RGB-D三维支撑和跨帧维护保证证据可靠。
◆ 将代价地图修正从像素/几何层面提升到对象语义层面，显式处理低矮电缆漏检、柔性窗帘误阻塞和交通锥需扩展禁行区等问题。
◆ 融合开放词汇grounding与多模态三维观测，并设计观测质量过滤和跨帧提交、替换、撤销机制，降低瞬时误判。
◆ 在50次真实机器人试验中取得86.0%总成功率；200次消融显示成功率由70.0%升至86.0%，误提交率由68.4%降至40.7%。
上述结果验证了证据引导的对象级修正能提升导航鲁棒性，并优于仅依赖当前观测的更新策略。</td></tr>
<tr><td>2026-09-12</td><td>GeomVLA: Unifying Scene, Motion, and Action in 3D<br><a href='http://arxiv.org/pdf/2609.13812'>论文</a></td><td>GeomVLA提出一个在机器人中心3D坐标系内统一感知、潜在场景运动预测与动作生成的VLA模型。  
◆ 用深度和相机标定将预训练VLM特征提升为空间落地的3D场景token，同时保留VLM语义。  
◆ 引入任务条件化的3D Scene Trajectory Denoiser，学习场景点在3D中预期运动的潜在表示。  
◆ 不将预测轨迹作为开环计划执行，而是抽取中间运动token，经几何感知注意力条件化3D流动作去噪器。  
◆ 在CALVIN达SOTA，LIBERO和RoboTwin2.0有竞争力，真实操作中无需机器人动作预训练也优于强基线。  
消融表明仅未来运动推理不足，主要增益来自场景表示、运动预测与动作在感知到动作全流程中的几何一致性。</td></tr>
<tr><td>2026-09-11</td><td>From Vision to Harvest: Benchmarking Vision-Language Models for Multi-Arm Robotic Fruit Harvesting<br><a href='http://arxiv.org/pdf/2609.13606'>论文</a></td><td>本文提出首个评估预训练视觉语言模型零样本多臂水果采摘规划的综合基准，采用真实苹果和柑橘园图像，并与传统感知加规划流程对比。
◆ 首次构建面向多臂水果采摘的VLM零样本规划基准，填补系统评测空白。
◆ 设计VLM直接生成采摘序列和各机械臂路径点、轻量轨迹验证器检查碰撞的规划流程。
◆ 使用真实苹果与柑橘园图像，覆盖多样环境并增强基准现实性。
◆ 系统比较VLM流程与传统感知加规划流程，揭示前沿VLM的零样本规划能力。
◆ 实验表明前沿VLM可生成有效多臂计划，但三维路径点精度与碰撞感知协调仍是实际部署瓶颈。</td></tr>
<tr><td>2026-09-10</td><td>GroundBench: A Factorized, Counterfactual Benchmark for Locating VLM Affordance Failures<br><a href='http://arxiv.org/pdf/2609.13308'>论文</a></td><td>论文提出 GroundBench，用于诊断视觉语言模型操作可供性失败，核心是把“命名目标部件”带来的增益分解为视觉定位、机械推理与类别到动作关联。
◆ 构建六分支合并条件，逐步加入受控信息包，系统隔离不同信息源对动作预测的影响。
◆ 设计反事实重问，要求模型针对同一图像中可见的另一真实部件作答，以检测文本捷径。
◆ 在1068条预测中发现：只给区域不给身份时准确率不超0.53多数基线，只给身份不给位置则提升至0.74、0.68、0.68，且增益多由部件类别直接决定动作，表明类别到动作关联主导。
◆ 无视觉控制下GPT-5分数不变或提升，但GPT-4o mini下降，且关节类型与运动轴信息无增益，揭示该解释并非普遍。
◆ 在32个物体的74对反事实样本上，GPT-5达到0.86成对合规、0.07捷径率，但推转抬升垂直案例全失败，证明基准能定位真实可供性失败。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-visual-semantic-recognition'>Robot Visual Semantic Recognition</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-11</td><td>CoralscapesV2: Panoptic and Fine-Grained Visual Scene Understanding in Coral Reefs<br><a href='http://arxiv.org/pdf/2609.12826'>论文</a></td><td>CoralscapesV2是面向珊瑚礁通用视觉场景理解的数据集扩展，旨在支持大规模生态监测与保护。该数据集扩大了规模、范围和标签完整性与质量，并将语义分割类别从39类扩展到95个细粒度类别。
◆ 将珊瑚礁语义分割类别从39类扩展到95个细粒度视觉类别。
◆ 提供约6.5万条鱼类实例掩码标注，并借助视频确保标注完整性，揭示仅用静态图像标注鱼类不足。
◆ 构建首个珊瑚礁全景分割数据集，覆盖多种野外场景，形成具挑战性的语义与实例分割基准。
它推动珊瑚礁通用全景分割，可用于底栖覆盖制图、鱼类行为与鱼礁互动自动量化理解，助力珊瑚礁监测规模化。</td></tr>
<tr><td>2026-09-09</td><td>CLFTv2: Efficient Camera-LiDAR Fusion for Semantic Segmentation via Hierarchical Feature Pyramids<br><a href='http://arxiv.org/pdf/2609.09881'>论文</a></td><td>CLFTv2提出一种面向自动驾驶语义分割的高效相机-LiDAR分层融合框架，旨在提升弱势道路使用者召回并缓解类别不平衡。
◆ 以Swin多尺度编码器替代全局ViT注意力，利用移位窗口注意力在多尺度上提取几何线索。
◆ 采用轻量FPN式残差解码器，在2D透视域进行逐尺度残差融合，避免查询匹配解码器的高计算开销。
◆ 通过模态隔离研究指出，ViT全局感受野仅在LiDAR返回密集时带来更强融合增益。
在ZOD、Waymo等三个驾驶数据集上，CLFTv2-Large于ZOD达53.5% mIoU，行人IoU由35.5%升至44.9%，Waymo达61.7% mIoU；相比基于Swin的Mask2Former适配，所需GFLOPs约少29%，吞吐量高2.2倍且总体精度相当。
这些结果表明，分层局部注意力融合是实时车载感知中替代全局注意力和查询式解码器的可扩展高效方案，代码已公开。</td></tr>
<tr><td>2026-09-03</td><td>Automated Weld Seam Recognition and 3D Mapping for Robotic Post Processing Using Photogrammetry and Semantic Segmentation<br><a href='http://arxiv.org/pdf/2609.03970'>论文</a></td><td>该论文提出一种面向机器人后处理作业的焊缝自动识别与三维映射视觉流程，核心贡献在于将语义分割与摄影测量技术结合，实现大型工件焊缝的近似定位，为后续高精度测量提供高效预处理阶段。其方法通过多视角图像采集、像素级焊缝分割、摄影测量三维重建以及焊缝标签向模型投影，完成从二维图像到三维空间的焊缝映射。◆提出将低成本的摄影测量作为高成本激光扫描的前置环节，显著减少扫描数据量与整体采集时间。◆采用语义分割网络直接从二维图像提取焊缝区域，避免了对完整三维点云做无关处理。◆实现了焊缝识别结果与三维重建模型的自动对齐，无需额外配准步骤。◆该流程针对大型工件设计，有效解决全表面高精度扫描效率低、数据冗余大的工程难题。</td></tr>
<tr><td>2026-09-02</td><td>What Does the Encoder Actually Decide? A Controlled Comparison of Vision Backbones on Joint Tree Segmentation and Stereo Depth<br><a href='http://arxiv.org/pdf/2609.13232'>论文</a></td><td>论文在固定数据集、解码器、损失、训练计划和评估的前提下，仅替换视觉编码器，用单编码器硬参数共享网络联合完成树木语义分割与立体深度估计，量化编码器选择对细薄植被任务的影响。
◆ 提出控制变量式骨干横向比较，覆盖CNN、Transformer、混合、MLP-mixer、状态空间模型等约2500万参数预算架构，并从零训练。
◆ 设计联合分割与立体深度的共享评估协议，深度仅在树像素评价，分割用边界F1和背景IoU抑制“全标为树”的捷径。
◆ 发现最强编码器多为卷积和混合架构，而非纯Transformer，多个普通ViT从零训练会显著崩溃。
◆ 发现参数量不能预测质量，小模型可超过大两个数量级的模型，且分割与深度排名强一致，说明两任务无冲突。
◆ 揭示K/N编码器退化为全树分割，该失败被边界F1暴露却被区域IoU掩盖。</td></tr>
<tr><td>2026-09-02</td><td>Towards Trustworthy Autonomous Robots: An Explainable AI-Based Decision Framework<br><a href='http://arxiv.org/pdf/2609.02861'>论文</a></td><td>该论文针对深度学习驱动的自主机器人面临的可审计性挑战，提出了TRACE（透明推理可信执行架构）决策框架，旨在确保每一个自主行为都能通过文档化的因果链条回溯到传感器证据。框架将决策过程组织为四个可审计层级：语义感知、信念推理、动作合成与执行验证，形成端到端可追溯链路。

◆ 提出四层可审计决策架构TRACE，将感知、推理、规划与执行各环节均纳入因果链记录，实现从传感器输入到动作输出的全程证据贯通。

◆ 设计模型无关的集成方案，可兼容CNN、Transformer等学习式感知模块，在保留决策级可审计性的同时不牺牲模型灵活性。

◆ 首次系统定义三项可量化审计指标——证据可追溯性、决策可重构性与时序连续性，弥补了LIME等事后归因方法缺乏决策级重建所需产物结构的不足。

◆ 在仓储机器人导航场景的500个仿真决策周期中，框架在三项指标上分别达到98.6%、99.0%和98.1%，并满足欧盟AI法案对高风险系统透明性的合规要求，为安全关键自主系统的可解释AI提供了实用路径。</td></tr>
<tr><td>2026-09-02</td><td>Toward Robust LiDAR Semantic Segmentation for Real-World Deployment: Evaluation under Coarse Labels, Adverse Conditions, and Domain Shifts<br><a href='http://arxiv.org/pdf/2609.02830'>论文</a></td><td>这篇论文针对LiDAR语义分割在真实场景部署中的可靠性问题,提出了一个结构化的评估协议,旨在系统衡量模型的部署就绪度。该协议从三个互补维度展开评估:与自动驾驶安全优先级对齐的粗粒度标签评估、八种LiDAR退化扰动下的鲁棒性测试,以及跨数据集的域泛化能力,并结合嵌入式Jetson AGX Orin平台的推理速度进行综合考量。

◆ 提出了统一的三维度评估协议,涵盖安全语义标签粒度、传感器退化鲁棒性和跨域泛化能力,弥补了现有评估仅关注干净单一域基准的不足。
◆ 设计了八种LiDAR损坏类型,模拟大气、几何和传感器退化等真实世界条件。
◆ 在嵌入式Jetson AGX Orin平台上直接测量推理速度,反映实际部署约束。

研究发现,细粒度基准排名并不总是反映安全相关性能,所有方法在扰动下均出现显著退化且鲁棒性呈现架构依赖性,当前域泛化能力仍不足以支持可靠部署,暴露了基准性能与部署就绪度之间的具体差距,为更贴合实际的LiDAR语义分割评估提供了参考协议。</td></tr>
<tr><td>2026-09-01</td><td>Situation Awareness for Intelligent Data Distribution in Connected Vehicles<br><a href='http://arxiv.org/pdf/2609.05521'>论文</a> | <a href='https://github.com/akshaynarla/DySi_Select'>代码</a></td><td>本论文针对车载传感器视野受限及遮挡导致感知质量下降的问题，提出一种基于鸟瞰图的车载交通情境识别概念，用于智能数据分发。通过结合目标检测与语义分割理解车辆周围环境，再利用Cam2BEV投影网络和情境识别神经网络构成的情境识别模块，判断当前交通场景。研究在CARLA模拟器上利用内置RGB相机和语义分割相机进行了验证，并在Cityscapes和nuScenes真实城市驾驶数据集上检验了模块的可移植性。结果表明，该情境识别方法能依据当前交通态势优先处理相关数据，从而实现高效的传感器数据管理。其核心创新在于将鸟瞰图投影变换与神经网络结合用于交通情境分类，而非简单的目标级感知。  
◆ 提出将Cam2BEV投影网络与情境识别网络串联，直接从多视角图像生成统一鸟瞰情境表示，提升对复杂道路上下文的语义理解。  
◆ 设计分层处理流程：先做目标检测和语义分割获取局部细节，再通过投影变换获得全局空间关系，最终输出可指导数据选择的情境类别。  
◆ 跨仿真与实际数据集验证了情境识别模块的领域可迁移性，证明其具备面向真实车联网部署的潜力。  
◆ 开创性将“情境感知”与“数据分发决策”关联，为按需式V2X通信减少冗余传输提供了新思路。</td></tr>
<tr><td>2026-08-29</td><td>SGE: Semantically-Guided Exploration for Unstructured Environments via Image-Space Waypoint Sampling<br><a href='http://arxiv.org/pdf/2608.29315'>论文</a></td><td>SGE提出了一种面向地面车辆在非结构化环境中探索的模块化框架,其核心创新在于将像素级语义分割深度融合到基于采样的路径点选择与滚动时域路径优化中。该方法直接在图像空间评估候选探索目标,通过综合考虑地形可通行性、障碍物距离、感兴趣目标及深度探索奖励的语义感知效用函数,实现超越传统纯几何方法的探索决策。

◆ 在图像空间直接进行语义感知的候选路点效用评估,集成可通行性、障碍接近度、目标语义与深度探索奖励

◆ 采样路点投影到三维后通过实时旅行商问题(TSP)排序,实现滚动时域目标选择

◆ 引入临时禁忌区域机制处理导航失败,以及基于图的回溯策略实现已探索区域的高效重定位

◆ 支持语义任务偏好引导,这是纯几何方法无法实现的能力

框架在标准化仿真基准上与前沿探索规划器对比表现出竞争力,并通过室内校园建筑、石灰岩矿和煤矿等多平台真实实验验证了跨场景的鲁棒性与适应性。</td></tr>
<tr><td>2026-08-29</td><td>RoSe-SLAM: Robust Semantic-Aware Gaussian Splatting SLAM from Dynamic Monocular Videos<br><a href='http://arxiv.org/pdf/2608.29003'>论文</a></td><td>RoSe-SLAM针对动态非结构化环境中传统SLAM因静态假设导致的精度退化问题，提出了一种基于高斯泼溅的鲁棒语义感知单目SLAM系统，利用2D基础模型的语义特征实现对未标定单目输入的整体语义理解，从而在动态场景下实现精确的相机跟踪与高质量几何重建。系统将丰富的语义特征蒸馏到高斯场中，有效识别动态干扰物并实现语义感知的多视角一致性。

◆提出空间-时间运动掩码生成模块，同时支持长期运动监测与短期瞬态动态捕捉，实现动态物体与静态背景的鲁棒有效解耦。

◆设计遮挡感知的关键帧选择机制，以遮挡程度作为关键帧筛选的度量标准，提升全局束调整的效率与鲁棒性。

◆引入多视角语义一致性模块，结合几何运动线索与语义先验，动态过滤不可靠观测，重建准确的静态场景几何结构。

在TUM、Bonn和Wild-Mocap等动态基准数据集上的大量实验表明，该方法在长时动态室内环境中的轨迹估计与静态场景建图性能均优于现有动态RGB SLAM基线方法。</td></tr>
<tr><td>2026-08-26</td><td>EgoNav: Bridging Learned Waypoints and Geometry-Aware Local Control for Robust Indoor Navigation<br><a href='http://arxiv.org/pdf/2608.25642'>论文</a></td><td>EgoNav是面向室内机器人图像目标导航的层次化系统，旨在解决学习型路标预测器可能违反几何约束或偏离全局路径的难题。该系统通过语义分割生成可通行区域的候选路径点，并从几何安全性、方向一致性以及对学习先验的忠实度三个维度对其进行评分筛选，从而获得既保留导航直觉又满足物理可行性的精细化路标。在执行层面，本文提出了一种自适应局部路径规划器，能够根据路标精炼的结果动态调整规划参数，使机器人在狭窄空间中也能安全通行。

核心创新点如下：

◆ 提出层次化路标精炼框架，将学习型路标预测与基于几何约束的候选筛选相结合，有效缓解预测器输出违反物理约束的问题。

◆ 设计多准则评分机制，从可通行区域语义分割中生成候选点，并综合几何安全、方向一致性和先验忠实度进行选择。

◆ 引入自适应局部路径规划器，根据路标精炼结果动态调节规划参数，提升系统在复杂狭窄环境中的鲁棒性。

◆ 在Habitat仿真平台和真实人形机器人上均验证了方法在成功率和路径效率方面优于现有基线。</td></tr>
<tr><td>2026-08-24</td><td>Spotter: Efficient Urban Visual Localization via Geo-Referenced Facade Landmarks in GPS-Degraded Environments<br><a href='http://arxiv.org/pdf/2608.23290'>论文</a></td><td>Spotter是一个针对城市GPS信号退化环境下的视觉定位框架，利用建筑立面作为可靠的全局地理参考，同时保留在可用时融合GPS信号的能力。

◆ 离线阶段通过语义分割立面并结合多视角立体重深度与地图数据，从Google街景全景图构建紧凑的度量数据库

◆ 运行时采用级联检索与几何验证流水线，实现细粒度全局相机定位的实时匹配

◆ 发布了在巴塞罗那多个区域使用可穿戴智能眼镜采集的行人序列数据集作为基准

◆ 在该数据集上，Spotter性能优于基于视觉里程计的基线方法，定位精度达到当前最优地图匹配方法的水平，同时帧率显著更高，整体框架适合边缘设备实时部署。</td></tr>
<tr><td>2026-08-24</td><td>Contextrast++: Robust Multi-Scale Contextual Contrastive Learning for Semantic Segmentation<br><a href='http://arxiv.org/pdf/2608.22679'>论文</a></td><td>Contextrast++是一种用于语义分割的鲁棒对比学习方法，旨在同时解决多尺度上下文建模与长尾分布两大难题。该方法由上下文对比学习（CCL）和边界感知负样本（BANE）采样两大核心组件构成。

◆ 提出自适应融合模块，动态平衡局部与全局特征集成，增强上下文感知表征能力
◆ 设计像素到锚点（PA）损失与锚点到锚点（AA）损失，前者利用多尺度融合特征改善表征学习，后者借助存储类别平衡代表性锚点的内存库，有效缓解长尾分布问题
◆ 提出边界感知负样本（BANE）采样策略，从易误分类的边界区域选取困难负样本，细化分割细节

在多个公开数据集上的广泛实验表明，Contextrast++显著优于现有基于对比学习的先进方法，且在推理阶段不引入额外计算开销。</td></tr>
<tr><td>2026-08-23</td><td>Understanding Temporal Semantic Stability in Open-Vocabulary UAV Perception through Metric 3D Fusion<br><a href='http://arxiv.org/pdf/2608.28665'>论文</a></td><td>无人机开放词汇分割在连续观测中常出现时间语义不一致问题。本文通过度量三维融合将逐帧预测关联到持久世界空间位置，系统研究开放词汇无人机感知中的时间语义稳定性。

◆ 提出基于体素的评估框架，联合刻画最终语义一致性、语义信念漂移(SBD)、观测持久性(OP)及语义不确定性四个维度。

◆ 强调观测持久性作为长时程语义可靠性评估的关键调节变量，揭示仅依赖聚合世界空间一致性指标会高估真实稳定性。

实验在UAVid-3D数据集上验证，发现显著帧间语义闪烁现象，且结论在多种分割骨干网络、体素分辨率、几何关联与时间采样密度下保持一致。持续性分层分析表明，反复观测的体素暴露出更大语义分歧，而信念漂移随证据累积而下降。研究表明语义一致性必须与观测支持联合解读，才能准确反映长时程感知可靠性。</td></tr>
<tr><td>2026-08-21</td><td>The Coastline as a Structural Constraint: Harnessing Scene Geometry for Autonomous Surface Vessel Localization<br><a href='http://arxiv.org/pdf/2608.21276'>论文</a></td><td>本文针对GPS拒止环境下自主水面船的定位问题，提出了两套互补的定位框架，充分挖掘海岸线与水面几何结构作为全局参考信息源的潜力。第一个框架基于LiDAR观测，通过水面几何估计船体的横滚、俯仰和升沉运动，并直接将岸线观测与卫星海岸线地图配准以恢复全局位置和航向。第二个框架仅依赖被动图像，利用语义分割检测岸线与地平线，从单目图像中推断岸线距离，并将短期局部子地图与卫星海岸线地图配准，在分层因子图中进行融合。◆创新点一：提出利用水面与岸线双重几何作为结构约束，实现LiDAR下姿态与全局位姿的联合估计。◆创新点二：设计仅依赖单目相机的海岸定位流程，通过几何推理从图像恢复岸线距离并构建局部子地图。◆创新点三：构建分层因子图融合机制，将岸线观测与卫星海岸线地图进行全局配准，有效抑制长期漂移。◆创新点四：验证了零样本基础模型在不同海岸环境中提取岸线观测的可靠性。在三个真实海岸数据集上的实验表明，LiDAR流程持续优于基线方法，单目架构保持有界长期漂移，证明海岸几何是GPS拒止下海上定位的可靠全局参考信息源。</td></tr>
<tr><td>2026-08-17</td><td>Cyclops: LiDAR as a Camera That Dreams in Color<br><a href='http://arxiv.org/pdf/2608.16264'>论文</a></td><td>论文提出Cyclops框架,通过将稀疏非重复扫描LiDAR强度数据转化为RGB视频,实现无需相机的全天候感知任务,有效弥合了LiDAR数据与RGB视觉模型之间的模态鸿沟,在低光和高动态范围场景中显著优于传统相机方案。

◆利用冻结的预训练稠化模块,将稀疏LiDAR强度投影转化为密集表示,作为几何信息丰富的源条件输入。
◆在潜空间采用Latent Bridge Matching (LBM)与学习的速度场,经少量ODE积分步骤即可将密集强度潜变量映射至目标RGB分布,大幅提升推理效率。
◆通过时序注意力层注入先验帧上下文信息,有效缓解生成视频中的帧间闪烁现象。
◆将速度场建模为可微终端奖励优化的策略,沿ODE轨迹进行反向传播以增强终端帧的生成保真度。
◆在语义分割、车道检测和点云着色等多项任务上,所合成RGB使标准RGB感知模型在多种光照条件下均显著超越LiDAR基线与传统相机表现。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vpr'>Robot VPR</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-07-15</td><td>Breaking Déjà Vu: Independent Auditing of Visual Place Recognition through Vision-Language Reasoning<br><a href='http://arxiv.org/pdf/2607.12818'>论文</a></td><td>本文针对视觉位置识别(VPR)在实际部署中依赖固定图像匹配阈值、难以应对环境变化的问题，提出了视觉位置识别审计(Visual Place Recognition Auditing)框架。该方法利用视觉语言模型(VLM)在检索后对查询图像和候选图像进行联合推理，实现独立于特定架构的实例级验证。核心创新包括：◆ 提出了一种独立于VPR架构的事后审计验证框架，无需数据集相关的阈值或部署环境的先验知识。◆ 利用视觉语言模型对查询与候选图像进行联合推理，实现跨环境的鲁棒验证。◆ 在六个基准数据集和五种先进VPR方法上验证，平均将recall@1提升13.6%，同时将误接受率降至12%，保持精度高于95%、覆盖率高于75%。该工作为安全关键机器人系统中环路闭合检测的可靠性提供了新的解决方案。</td></tr>
<tr><td>2026-07-07</td><td>From Open Waters to Enclosed Cabins: ProteusVPR for Cross-Scene Visual Place Recognition in Maritime Perception and Cabin Inspection<br><a href='http://arxiv.org/pdf/2606.24234'>论文</a></td><td>本文针对海上机器人巡检中开放甲板与封闭舱室之间跨场景视觉位置识别的难题，提出ProteusVPR两阶段检索-精修框架。该方法通过几何-视觉估计网络融合时序多帧信息，引入局部仿射坐标系和相机方位角编码实现精确定位。

◆ 提出ProteusVPR两阶段框架，第一阶段使用标准VPR模型完成初步检索，第二阶段利用融合检索图像与两帧时序前帧的几何-视觉估计网络进行精修。
◆ 设计局部仿射坐标系与相机方位角编码机制，增强跨场景几何一致性表达与定位鲁棒性。
◆ 构建XHZ船舶全景数据集（8K图像），涵盖多层舱室结构与甲板过渡区域，并采用严格查询-数据库分离的评估协议。
◆ 实验证明该方法在多种VPR骨干网络上将平均定位误差降低超过60%，在跨场景海事环境中表现出有效性与鲁棒性。</td></tr>
<tr><td>2026-07-06</td><td>Trajectory-Anchor Optimization for Overconfident Thermal Visual Place Recognition: Zero-Leakage OOD Auditing and Kidnapped-Robot Recovery<br><a href='http://arxiv.org/pdf/2607.04745'>论文</a></td><td>本文针对热红外视觉位置识别（TIR-VPR）在分布外条件下产生的过度自信强制匹配失败问题，提出了一种名为轨迹锚定优化（TAO）的新型后端处理方法。TAO将传统多假设跟踪（MHT）中指数级复杂度的并行轨迹评估问题，转化为批量化SE(2) Procrustes对齐问题，通过张量级向量化与单次调用的批量SVD计算，绕开动态树扩展过程，实现了严格的每帧O(KN)实时性能。在零泄漏评估协议下，论文揭示了一个关键发现：在5米以下的微观尺度，由于局部视觉歧义性，被动几何后端无法数学分离度量定位误差与连贯性幻觉；而在宏观尺度上，K=100条分散假设会打破滑动窗口内的刚性时序共视约束，使联合优化残差急剧上升。TAO由此构建了一个10米的宏观收敛盆地，能够可靠地隔离灾难性拓扑断裂并抑制关键误接受。

◆ 提出TAO框架，将多假设跟踪的组合爆炸问题转化为批量化SE(2) Procrustes对齐，实现O(KN)严格实时的每帧执行复杂度。
◆ 揭示了5米微观尺度下几何一致性的固有盲区，明确界定10米宏观收敛盆地为幻觉检测的有效工作区间。
◆ 在零泄漏评估协议下，证明了多视图几何一致性可作为高效的失效安全滤波器，有效抑制过自信的误匹配。</td></tr>
<tr><td>2026-06-14</td><td>VL2Spike: Spike-driven Distillation from VLMs for Low-Power Visual Perception in Embodied AI<br><a href='http://arxiv.org/pdf/2606.15898'>论文</a></td><td>本文提出VL2Spike，一种新颖的脉冲驱动知识蒸馏框架，旨在将视觉语言模型（VLM）的多模态知识迁移到紧凑的Spikformer模型中，在保留脉冲神经网络能效优势的同时显著提升其视觉感知能力，为低功耗机器人感知提供了实用路径。

◆空间-时间视觉脉冲（SVS）蒸馏：实现VLM图像特征与脉冲token的共享流形对齐，并在膜电位和脉冲率上构建热启动的时间一致性机制。

◆脉冲原型引导的语言（SPL）蒸馏：将Spikformer的类别原型与logits与VLM的可提示文本嵌入对齐，实现跨模态语义知识的有效迁移。

实验结果表明，VL2Spike在三个静态数据集上取得6.81%的性能提升，能耗仅为原来的15.7%，并在机器人视觉位置识别任务中实现6.63%的增益，展现出优异的泛化能力与应用潜力。</td></tr>
<tr><td>2026-06-11</td><td>Visual Place Recognition in Forests with Depth-Aware Distillation<br><a href='http://arxiv.org/pdf/2606.13206'>论文</a></td><td>本文针对自然森林环境中视觉位置识别面临的植被重复、结构线索弱以及外观变化大等挑战，提出了一种轻量化的深度感知蒸馏框架。该方法将几何线索注入基于DINOv2的位置识别模型中，同时保留了预训练描述符空间，从而兼顾几何感知能力与原有表征的稳定性。在WildCross基准上的实验表明，该方法相较于仅依赖外观信息的方法取得了显著提升，对外观变化表现出更强的鲁棒性。论文的核心贡献可总结如下：

◆ 提出面向森林环境的轻量化深度感知蒸馏框架，将几何深度信息有效融入视觉位置识别流程。
◆ 创新性地在DINOv2描述符空间中执行蒸馏操作，既引入深度线索又避免破坏原有预训练特征的泛化能力。
◆ 验证了深度模态作为外观信息互补手段在自然场景位置识别中的关键作用。
◆ 在WildCross基准上证明了所提方法在跨次遍历场景下具有更优的鲁棒性与识别精度。</td></tr>
<tr><td>2026-05-31</td><td>One Channel to Rule Them All: Rethinking Input Representation for Visual Place Recognition<br><a href='http://arxiv.org/pdf/2606.00936'>论文</a></td><td>本文针对视觉位置识别（VPR）领域长期依赖RGB输入的假设提出了系统性挑战。研究通过跨训练范式、模型架构和标准基准的全面实验，考察了颜色信息在真实场景外观变化下的实际作用，发现灰度图像在多数情况下与RGB表现相当，甚至在光照、天气、季节等剧烈外观变化下更优，因为颜色不变性难以充分学习。

◆ 首次系统性质疑VPR对彩色输入的必要性，揭示颜色信息在全局位置识别中的贡献被高估。

◆ 实验证明灰度训练的MixVPR模型平均Recall@1达82.4%，优于RGB版本（81.2%），且参数量减少60%的轻量灰度模型可超越重型RGB模型。

◆ 发现颜色仅在场景具有持久且具判别性的色彩线索时才有意义贡献，在外观多变场景中作用极小。

◆ 提出灰度输入在存储、带宽和资源受限系统部署上具有显著实用优势，为VPR系统设计提供新方向。</td></tr>
<tr><td>2026-05-29</td><td>DisPlace: Discriminative Place Projections for Multi-Reference Visual Place Recognition<br><a href='http://arxiv.org/pdf/2605.30769'>论文</a></td><td>本文针对视觉位置识别(VPR)中多参考图像融合的难题,提出了一种名为DisPlace的新框架。核心思想是将多参考描述子的融合建模为广义特征值问题,旨在最大化不同地点之间的可分离性,同时抑制同一地点在不同参考遍历中由于光照、视角变化引起的描述子差异。与现有方法不同,DisPlace不再保留描述子整体方差,而是区分哪些维度组合保留了稳定的位置身份,哪些维度仅反映条件或视角的特定变化。

◆提出将多参考描述子融合形式化为广义特征值问题,直接优化类间可分性与类内一致性,而非传统的方差保留策略。

◆利用跨参考遍历的变化来识别保留位置身份的关键维度组合,有效分离位置判别信息与环境/视角变化信息。

◆在Oxford RobotCar、Nordland、Pittsburgh30k和Google Landmarks v2四个基准上,配合六种先进VPR描述子均取得一致提升,在49/54外观变化场景中优于七种基线方法。

◆融合后输出单一紧凑的地点表示,推理时存储开销低于所有对比的融合方法,具备实际部署优势。</td></tr>
<tr><td>2026-05-27</td><td>SAFEVPR: Patch-Based Conformal Verification for Safe Cross-Condition Sequence Visual Place Recognition<br><a href='http://arxiv.org/pdf/2605.28048'>论文</a> | <a href='https://github.com/Hasar12139/SafeVPR'>代码</a></td><td>SAFEVPR是首个面向跨条件序列视觉位置识别的安全验证框架，利用共形预测做出可靠的接受/拒绝决策，应对条件偏移下校准与部署数据交换性被破坏的难题。

◆ 提出用基于冻结DINOv2 ViT特征的互近邻块匹配分数替代传统骨干网络余弦相似度，增强跨条件匹配的判别鲁棒性。

◆ 采用Mondrian共形Learn-Then-Test策略，按分数箱分别拟合并经Bonferroni校正的阈值，提供更细致的FDR控制。

◆ 揭示了原始判别能力AUROC不足以保证共形有效性：AnyLoc-VLAD和SuperPoint+LightGlue虽AUROC相当却在相同校准下失败更多场景。

在Oxford RobotCar、NCLT、St Lucia三数据集的23个跨条件测试中，SAFEVPR在目标FDR为0.10下全部经验有效，平均接受FDR仅0.014、TPR达0.75，并能在纹理匮乏的重复场景中安全弃权而非冒险接受。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5181</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4638</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2450</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1638</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1621</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1503</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1333</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1297</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1068</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>1036</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>941</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>808</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>783</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>746</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>739</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>727</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>676</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>665</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>630</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>616</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>607</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>578</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>568</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>532</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>509</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>461</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>454</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>363</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>348</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>276</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>271</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>257</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>242</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>228</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>223</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>221</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>211</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>188</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>147</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>146</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>121</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2873</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1671</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1367</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1096</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1058</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>881</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>708</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>667</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>661</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>623</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>604</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>577</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>571</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>571</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>553</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>518</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>508</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>464</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>456</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>451</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>334</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>313</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>301</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>300</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>285</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>279</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>258</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>224</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>207</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>202</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>185</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>176</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>169</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>169</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>160</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>156</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>142</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>139</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>132</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
<tr><td><a href='https://github.com/ethz-asl/phaser'>phaser</a></td><td>132</td><td>A robust pointcloud registration pipeline based on</td></tr>
<tr><td><a href='https://github.com/ethz-asl/data-driven-dynamics'>data-driven-dynamics</a></td><td>132</td><td>Data Driven Dynamics Modeling for Aerial Vehicles</td></tr>
<tr><td><a href='https://github.com/ethz-asl/ssc_exploration'>ssc_exploration</a></td><td>112</td><td>Incremental 3D Scene Completion for Safe and Effic</td></tr>
<tr><td><a href='https://github.com/ethz-asl/active_grasp'>active_grasp</a></td><td>109</td><td>Closed-loop next-best view planning for grasp dete</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waypoint_navigator'>waypoint_navigator</a></td><td>108</td><td>Stand-alone waypoint navigator</td></tr>
<tr><td><a href='https://github.com/ethz-asl/reinmav-gym'>reinmav-gym</a></td><td>107</td><td>Reinforcement Learning framework for MAVs using th</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waverider'>waverider</a></td><td>106</td><td>RMPs on multi-resolution occupancy maps for effici</td></tr>
<tr><td><a href='https://github.com/ethz-asl/navrep'>navrep</a></td><td>106</td><td>navrep</td></tr>
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>104</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/eth_supermegabot'>eth_supermegabot</a></td><td>102</td><td>Instructions for ETH center for robotics summer sc</td></tr>
<tr><td><a href='https://github.com/ethz-asl/3d_vsg'>3d_vsg</a></td><td>101</td><td>3D可变场景图，用于长期语义场景变化预测。</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.09.16
