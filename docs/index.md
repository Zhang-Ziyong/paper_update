# 计算机视觉领域最新论文 (2026.09.19)

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
<tr><td>2026-09-17</td><td>Semantic SLAM in Precision Agriculture using Bayesian Inference<br><a href='http://arxiv.org/pdf/2609.20604'>论文</a></td><td>本文提出一种面向精准农业自主机器人的实时语义世界建模框架，将物体及其语义属性的概率建图与基于g2o的图优化SLAM结合，并通过贝叶斯推断持续更新。系统利用植物类型、大小和健康等语义信息，使机器人在田间边执行任务边定位建图，从而降低对GPS的依赖。
◆ 提出贝叶斯推断驱动的语义概率建图，可动态更新物体类别与属性。
◆ 将语义建图与g2o图优化SLAM融合，实现不单纯依赖GPS的定位与建图。
◆ 引入YOLOv8n从深度相机观测中提取植物语义，支撑农业场景实时感知。
◆ 在Gazebo仿真和Spot机器人室内人工植物实验中验证，可实时建图至少400株植物。</td></tr>
<tr><td>2026-09-17</td><td>RawSLAM: Online HDR Gaussian SLAM from Linear Radiance<br><a href='http://arxiv.org/pdf/2609.20589'>论文</a></td><td>本文提出RawSLAM，是首个直接基于单曝光16位线性HDR图像进行在线跟踪与建图的Gaussian SLAM框架，突破现有密集SLAM依赖8位LDR输入及HDR重建离线处理的限制。其核心由三部分构成：无需MLP的对数高斯颜色参数化HDR高斯泼溅、Reinhard范围压缩光度目标，以及结构引导空间梯度加权。
◆ 提出架构无关的HDR高斯泼溅模块，采用无MLP的对数参数化表示高斯颜色特征，可原生渲染线性场景辐射度。
◆ 设计Reinhard范围压缩光度目标与结构引导空间梯度加权，提升极端光照下的跟踪与建图鲁棒性。
◆ 同一公式可直接处理标准8位输入，并无缝迁移到SplaTAM、Gaussian SLAM和DROID-W，消除挑战光照序列中的跟踪失败。
实验表明，该方法在轨迹和重建精度上优于直接HDR适配的MonoGS，在8位输入上约将MonoGS基线误差减半，并发布含10个真实室内序列的RawSLAM数据集，包括16位RAW图像、对齐深度、IMU和OptiTrack位姿。</td></tr>
<tr><td>2026-09-17</td><td>GRF-Recon: Global Ray-Field Optimization for Long-Sequence Feed-forward Reconstruction<br><a href='http://arxiv.org/pdf/2609.20012'>论文</a></td><td>本文提出面向长单目序列的统一前馈3D重建框架，缓解显存占用、局部几何退化和长期轨迹漂移问题。
◆ 采用粗到细轨迹对齐并注入轻量几何先验，提升长序列全局一致性。
◆ 通过LoRA适配将单目几何线索蒸馏进前馈主干，在保持推理效率的同时改善精细结构深度精度。
◆ 设计混合权重稀疏射线场优化，利用高频几何特征引导局部点云精修并施加帧间射线约束，实现强跨帧几何耦合且保持可扩展性。
◆ 提出高效轨迹拼接与联合射线误差优化策略，显式降低累积漂移。
实验表明该方法轨迹精度可与代表性SLAM系统竞争，并在大规模场景中保持全局一致的三维重建。</td></tr>
<tr><td>2026-09-17</td><td>VGGT-GS SLAM: Uncalibrated Monocular Gaussian Splatting SLAM with Feed-Forward Priors<br><a href='http://arxiv.org/pdf/2609.19628'>论文</a></td><td>本文提出VGGT-GS SLAM，一个面向未标定单目视频的3D高斯泼溅SLAM系统。它从VGGT前馈位姿与深度先验出发，构建子图可微捆绑调整，联合优化相机位姿和三维高斯地图。系统还通过解析标定雅可比在线优化子图共享内参及径向切向畸变，实现无需预标定的跟踪与建图。
◆ 将VGGT前馈位姿和深度先验引入单目3DGS SLAM，为未标定视频提供初始化与几何约束。
◆ 提出子图可微捆绑调整，联合精化相机位姿、三维高斯地图以及共享内参与径向切向畸变。
◆ 设计Gaussian-native alignment，实现序列子图间相机锚定尺度细化并验证回环候选以增强全局一致性。
在标准室内基准上，未标定设置下定位精度和渲染质量均获一致提升，形成有力基线。</td></tr>
<tr><td>2026-09-17</td><td>OmniCalib: Target-Free, Task-Structured Self-Calibration for Humanoid Robots<br><a href='http://arxiv.org/pdf/2609.19582'>论文</a></td><td>OmniCalib提出一种无标定物、任务结构化的人形机器人自校准流程，仅用机器人自身运动和板载传感，统一校准上肢14个臂关节零点及腕部、胸部相机外参，并扩展至下肢与多相机头部。
◆ 任务结构化建模：每个模块把机器人原生任务匹配到参数块，检查可观测性，并只将受支持的校正写回CAD模型。
◆ 无靶深度ICP：无需任何标定靶即可恢复14个臂关节零点和全部RGB-D外参，点面残差2.09 mm，左/右腕与胸相机外参修正约6.33–10.56 mm、0.929–1.74度。
◆ 下肢零位恢复：四个静态双支撑姿态恢复12个下肢关节零位，注入偏移RMS误差0.063度。
◆ 头部多相机标定：融合多相机视觉里程计、腿式里程计和动态补偿，仅平面行走取得平均SO(3)误差1.061度，最佳0.775度，接近iKalibr的0.902度。
◆ 可验证性：相同注入偏移下ICP与ArUco均以优于0.1度编码器分辨率恢复14个关节零点，注入恢复和留出测试验证各可观测块。</td></tr>
<tr><td>2026-09-17</td><td>SLAMSqueezeBench: Comparing SLAM Systems under Resource Constraints<br><a href='http://arxiv.org/pdf/2609.19533'>论文</a></td><td>本文提出SLAMSqueezeBench，一个在边缘硬件上测试SLAM系统现实资源约束的框架。现有SLAM系统多在孤立环境下构建和测试，现有基准也缺乏统一机制来比较资源受限下的SLAM性能。
◆ 它能在执行期间对SLAM系统施加计算和内存资源限制，模拟真实边缘部署条件。
◆ 它通过有限缓冲区满时丢帧来模拟真实相机帧采集过程。
◆ 它统一比较九种SLAM系统，覆盖经典方法、学习型方法和高斯泼溅方法。
作者表示该测试框架将在论文发表后向社区开放，以支持可复现和贴近实际的SLAM评估。</td></tr>
<tr><td>2026-09-17</td><td>AMB3R-SLAM: Kilometer-scale SLAM with Hierarchical Backend<br><a href='http://arxiv.org/pdf/2609.19518'>论文</a></td><td>AMB3R-SLAM提出一种可在单块消费级GPU上实时运行的单目SLAM系统，能从超1万帧中重建公里级轨迹。  
◆ 采用轻量前端实现低延迟在线跟踪，并用分层后端逐步强化局部、中层与全局一致性。  
◆ 摒弃依赖静态世界假设的捆绑调整，使系统无需额外设计即可自然应对复杂动态场景。  
◆ 支持将立体、RGB-D与LiDAR作为附加输入，具备多模态扩展能力。  
◆ 在9个数据集上取得强相机跟踪性能，将VBR和Oxford Spires上先前SOTA的ATE降低超70%。  
加入LiDAR后，在KITTI和VBR上进一步把ATE降至亚米级。</td></tr>
<tr><td>2026-09-16</td><td>Dynamic-LIVO: A Dynamic-Aware LiDAR-Inertial-Visual Odometry System Using Spatio-Temporal Normals<br><a href='http://arxiv.org/pdf/2609.19336'>论文</a></td><td>Dynamic-LIVO提出一种动态感知的激光-惯性-视觉里程计系统，用于动态环境中的鲁棒状态估计与静态彩色建图。  
其核心是利用时空法线分析识别动态激光点，并将分类结果传播到激光惯性和视觉惯性更新，避免动态观测污染状态估计与建图。  
◆ 采用时空法线分析检测动态激光点，并将动态分类贯穿激光惯性及视觉惯性更新，实现多模态一致过滤。  
◆ 提出时间延迟的时空法线估计策略，延迟对约束不足点的分类，待更多观测后再评估，提高动态分类可靠性并保留静态点用于建图。  
◆ 在公开和自采多传感器配置数据集上验证，系统提升动态环境定位精度并生成更干净的静态彩色地图。</td></tr>
<tr><td>2026-09-16</td><td>SOL-SLAM: Inverse Compositional Gauss-Newton Direct Registration for Fast Sonar-Only Local SLAM<br><a href='http://arxiv.org/pdf/2609.18893'>论文</a></td><td>本文针对仅前视声纳局部SLAM的研究空白，提出SOL-SLAM。
◆ 它采用密集直接配准，将完整声学强度扫描对齐到递归更新的局部地图，避免稀疏特征提取造成的信息丢失。
◆ 它引入逆组合高斯牛顿优化，实现实时直接配准并显著降低计算开销。
◆ 实验显示其平移误差显著优于稀疏关键点基线，并在大位移间隔下保持稳定亚米级跟踪。
◆ 其里程计性能可媲美FLS、DVL与IMU多传感器融合，并在嵌入式资源受限平台上完成AUV现场验证。</td></tr>
<tr><td>2026-09-15</td><td>Co-occurrence-Aware Quadratic Assignment for Local Feature Matching in Simultaneous Localization and Mapping<br><a href='http://arxiv.org/pdf/2609.17905'>论文</a></td><td>本文针对视觉SLAM中最近邻匹配在多个候选代价相近时容易选错关键点对的问题，提出一种共现感知的局部特征匹配方法。
◆ 将两对关键点之间的成对共现关系纳入匹配决策，以提升歧义场景下的匹配准确性。
◆ 把关键点匹配建模为二次分配问题，从而统一表达共现约束与匹配代价。
◆ 借助基于模拟分岔的Ising机器求解该NP-hard组合优化问题，突破传统计算机难以快速求解的限制。
◆ 在HPatches数据集上，该方法相比传统方法将匹配精度提升约8个百分点。
◆ 集成到ORB-SLAM3后，在KITTI中重复同形物体场景下，APE提升3.78倍，RPE提升2.85倍。</td></tr>
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
</tbody>
</table>
</div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-17</td><td>RawSLAM: Online HDR Gaussian SLAM from Linear Radiance<br><a href='http://arxiv.org/pdf/2609.20589'>论文</a></td><td>本文提出RawSLAM，首个直接在单曝光16位线性HDR图像上在线跟踪与建图的高斯SLAM框架，无需离线SfM且可应对大帧间运动和极端光照。
◆ 设计架构无关的HDR高斯泼溅模块，采用无MLP的对数高斯颜色参数化，并原生输出线性场景辐射。
◆ 提出Reinhard范围压缩光度目标与结构引导空间梯度加权，增强极端光照下的跟踪与建图鲁棒性。
◆ 该HDR高斯模块可无缝迁移至SplaTAM、Gaussian SLAM和DROID-W，消除它们在挑战光照序列中的跟踪失败。
方法在轨迹与重建精度上优于直接HDR改装的MonoGS，且同一公式在标准8位输入下将MonoGS基线误差约减半。
为支撑研究，发布RawSLAM数据集，包含10个真实室内序列的16位RAW图像、对齐深度、IMU测量和OptiTrack外部位姿。</td></tr>
<tr><td>2026-09-16</td><td>RAUL: Reference-Assisted Ureteroscopy Localization for Skill Assessment<br><a href='http://arxiv.org/pdf/2609.19236'>论文</a></td><td>本文提出RAUL参考辅助输尿管镜定位框架，仅用内窥镜视频在体模中重建输尿管镜轨迹，并据此评估导航技能。  
◆ 利用慢速高质量参考探索视频生成参考重建，再将后续探索视频定位到参考，实现无需外部跟踪的轨迹恢复。  
◆ 在9个体模上取得平均平移RMSE 0.5±0.1 mm，帧级定位覆盖率从标准SfM的50.5±14.9%提升至86.1±7.2%。  
◆ 从重建轨迹计算导航指标，可显著区分高经验与低经验住院医师的输尿管镜导航表现。  
◆ 首次实现仅用视频、无需外部跟踪传感器的输尿管镜轨迹恢复与技能评估，支持可扩展的自动化评估。</td></tr>
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
</tbody>
</table>
</div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-15</td><td>Co-occurrence-Aware Quadratic Assignment for Local Feature Matching in Simultaneous Localization and Mapping<br><a href='http://arxiv.org/pdf/2609.17905'>论文</a></td><td>论文针对Visual SLAM中最近邻匹配在多个相似代价候选下难以选出正确关键点对的问题，提出一种考虑两个关键点对之间成对共现关系的局部特征匹配方法。  
◆ 创新点一：将关键点匹配建模为二次分配问题，利用关键点对之间的共现约束提升匹配判别能力。  
◆ 创新点二：针对该NP-hard组合优化问题，采用基于模拟分岔的Ising机进行求解，实现快速近似优化。  
◆ 创新点三：在HPatches数据集上将匹配精度较传统方法提升约8个百分点，并成功集成到ORB-SLAM3中。  
在KITTI中多个同形状物体重复排列的困难场景下，该方法使绝对位姿误差改善3.78倍、相对位姿误差改善2.85倍。</td></tr>
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
</tbody>
</table>
</div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-15</td><td>GeomVLA: Unifying Scene, Motion, and Action in 3D<br><a href='http://arxiv.org/pdf/2609.13812'>论文</a></td><td>GeomVLA提出统一场景、运动与动作的VLA模型，在机器人中心3D坐标系中融合感知、潜在场景运动预测与动作生成。
◆ 将预训练VLM特征借助深度和相机标定提升为空间接地的3D场景token，同时保留VLM语义表征。
◆ 提出3D Scene Trajectory Denoiser，以任务为条件学习场景点未来3D运动的潜在表示。
◆ 不直接开环执行预测轨迹，而是提取中间运动token，通过几何感知注意力条件化3D flow-based动作去噪器。
实验上在CALVIN达SOTA，LIBERO和RoboTwin2.0有竞争力，真实操作无机器人动作预训练也超越强基线。
消融表明仅未来运动推理不够，主要增益来自场景表示、运动预测与动作在感知到动作全流程中保持几何一致。</td></tr>
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

<h2 id='robot-vlm'>Robot VLM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-17</td><td>Workspace Models: Lightweight Robotic Memory via Saliency-Driven Supervision<br><a href='http://arxiv.org/pdf/2609.20820'>论文</a></td><td>复杂机器人操作常需长期记忆，但以完整历史为条件会引入虚假相关并损害策略性能。本文提出训练时用VLM识别完成任务所需的当前和历史显著信息，再通过集合重建解码损失将其蒸馏为轻量潜记忆，即workspace token。部署时该token可作为观测的即插即用替代，无需在策略循环中调用VLM，并在仿真和硬件上解决记忆密集型任务。
◆ 提出workspace token这一轻量机器人记忆表示，实现部署时高效查询且避免在线VLM推理。
◆ 设计显著性驱动的监督与集合重建解码蒸馏，把训练时昂贵VLM查询转化为部署时低成本潜记忆。
◆ 发现并验证workspace token不仅更轻量，还比依赖完整历史或在线VLM的策略取得更好性能。</td></tr>
<tr><td>2026-09-17</td><td>StageGuard: Learning Stage Transitions for Long-Horizon Robot Tasks via Agentic Distillation<br><a href='http://arxiv.org/pdf/2609.20791'>论文</a></td><td>论文面向长时机器人任务中“何时结束当前技能并进入下一子任务”的关键难题，提出 StageGuard 智能体蒸馏框架，以准确且高效地预测阶段转移。
◆ 将教师模型推理与演示轨迹结合，自动生成子任务完成与策略切换的结构化解释，缓解人工完成信号检查器难获取的问题。
◆ 设计轻量学生视觉语言模型，利用上述解释生成紧凑自解释并进行监督微调，实现低延迟在线监控。
◆ 通过智能体蒸馏把大模型推理迁移到小模型，使阶段转移决策边界更贴近任务完成标准，并避免云端大模型的长推理延迟。
◆ 在多个基准轨迹上显著提升阶段转移预测，并集成到 BEHAVIOR-1K 分层控制与真实机器人中验证闭环任务成功率。
结果表明，StageGuard 在提升阶段转移准确性的同时，能够支持高效的在线监控与长时机器人任务执行。</td></tr>
<tr><td>2026-09-17</td><td>V2-STRep: VLM-Grounded Structured Task Representations for Reusable Robot Skills Acquired from Generated Videos<br><a href='http://arxiv.org/pdf/2609.20582'>论文</a></td><td>V2-STRep提出零样本框架，将生成视频中的单次场景动作转化为可复用机器人技能，核心是视觉语言模型接地的结构化任务表示。
◆ 用结构化任务表示显式编码运动阶段、参考目标与任务相关约束，避免仅依赖隐式视频运动。
◆ 以点、点法线、轴、平面和完整6D位姿等最小几何结构描述目标，并用VLM的2D图像线索结合RGB-D提升到3D，重建任务几何与候选抓取位姿。
◆ 通过几何特定规则将动作迁移到新场景，并用任务约束轨迹优化耦合抓取选择与完整机器人运动规划。
◆ 在满足任务要求的同时利用剩余旋转自由度适应关节限制，且更新部署接地与约束即可复用新兼容指令，无需重新生成视频。
六个真实操作任务实验表明，该方法执行成功率优于基线，支持成功技能的跨场景迁移，并能适应变化的部署指令。</td></tr>
<tr><td>2026-09-17</td><td>Spatial-Semantic Uncertainty in VLM-Based Target Search: Balancing Exploration and Identification<br><a href='http://arxiv.org/pdf/2609.20443'>论文</a></td><td>本文提出空间-语义不确定性框架，用于VLM机器人目标搜索中平衡探索与识别。
◆ 将空间位置不确定性与目标身份语义不确定性显式分离，并分别维护概率信念，避免二者混同。
◆ 把概率化VLM证据融入全局目标身份后验，并为未发现目标保留概率质量。
◆ 基于空间与语义期望信息增益设计信息论规划器，分别评估候选发现和目标消歧，显式权衡探索与识别。
◆ 在六种VLM不确定性接口和退化观察搜索实验中，EIG规划器置信决策率达75.0%至92.5%，远超随机搜索的20.0%，且增强语义权重可减少无效探索与VLM查询而不损识别质量。
这些结果强调不确定性表示与不确定性驱动规划在具身VLM系统中的不同作用。</td></tr>
<tr><td>2026-09-17</td><td>Imagine-TAMP: Imagination-Guided Task and Motion Planning in Partial Observability<br><a href='http://arxiv.org/pdf/2609.20396'>论文</a></td><td>Imagine-TAMP提出一种在部分可观测环境中交错规划与执行的框架，用语义和几何想象在昂贵运动规划前比较不同任务级策略。
◆ 用视觉语言模型结合目标与可见物体的常识关系，塑造目标位置的粒子信念。
◆ 用生成式场景模型估计未观测区域的合理几何，支撑对遮挡目标的想象。
◆ 基于目标假设和想象场景生成多种符号计划骨架，并赋予非单位成本以近似操作代价和感知动作揭示目标的可见性。
◆ 将选中的骨架细化为可行连续计划并执行，新观测用于更新信念并在必要时重规划。
实验表明，想象引导评估能改善先观察还是先操作的决策：货架场景成功率从46.0%提升到84.0%，语义信念进一步减少操作和重规划，真机规划时间比仅几何消融减少32%。</td></tr>
<tr><td>2026-09-17</td><td>Uni-LaDiR: Latent Diffusion Unifies Multimodal Reasoning<br><a href='http://arxiv.org/pdf/2609.19878'>论文</a></td><td>Uni-LaDiR提出统一潜在扩散推理框架，将多模态推理的思维统一到共享潜在空间，而非拼接各模态思维token。
◆ 共享潜在空间统一多模态思维，缓解跨模态表示差异。
◆ 统一编码器把不同模态教师推理步骤映射为共享thought tokens，并保留后续推理及答案或动作所需信息。
◆ 扩散模型从输入和前序块预测下一块thought tokens，建模同一上下文下的多种有效下一步。
◆ 编码器与扩散推理器共享权重联合训练，使thought tokens兼具任务有用性与上下文可预测性。
推理时无需教师观察即可生成token，并在11个VLM基准和2个VLA套件上相对最强基线提升视觉推理7.3%、机器人操作6.1%。</td></tr>
<tr><td>2026-09-17</td><td>TADreamer: Zero-Shot Language-Guided 3D Navigation for Terrestrial-Aerial Bimodal Robots via Video Imagination<br><a href='http://arxiv.org/pdf/2609.19824'>论文</a></td><td>TADreamer提出一种面向陆空双模态机器人的零样本语言引导3D导航框架，无需任务特定训练或微调，即可把视频想象转化为可执行导航参考。
◆ 利用视觉语言模型将机载观测与指令转为导航提示，筛选有效生成视频，并在需要时提供纠正反馈以触发重生成。
◆ 将所选视频重建为带地面或空中模式标签的3D航点，使视频想象具备可规划的运动语义。
◆ 设计两阶段校准，先用视场约束初始化尺度，再通过点云配准到实测几何，细化轴相关尺度、旋转和平移，缓解尺度模糊与几何畸变。
◆ 将校准航点和模式标签接入结合实测几何的规划器，实现陆空双模态机器人在真实场景中的导航执行。
真实实验中，七类室内外场景均可在两轮内获得可用视频；相比NavDreamer，平均绝对深度误差降低87.7%，平均绝对相对深度误差降低86.3%。</td></tr>
<tr><td>2026-09-17</td><td>ReShoot: Generative Visual Domain Randomization of Recorded Robot Demonstrations for Visuomotor Policy Learning<br><a href='http://arxiv.org/pdf/2609.19661'>论文</a></td><td>ReShoot提出一种生成式视觉域随机化框架，将已录制机器人演示在改变外观后重新渲染，从而低成本合成视觉多样性并缓解模仿学习策略的视觉过拟合。
◆ 用视觉语言模型自动描述场景并编辑目标属性，如背景、物体颜色或材质，实现可控的外观随机化。
◆ 用边缘条件视频生成器重渲染两路相机视角，并同步更新语言指令，使画面与任务描述保持一致。
◆ 直接复制原演示的动作序列和本体感受轨迹，无需重新标注，使每个生成回合保留原始动作标签。
◆ 在LIBERO、LIBERO-Plus和两个真实平台上验证，混合录制与重渲染数据可保持原性能并提升鲁棒性。
实验显示，LIBERO混合训练达到96.5%对96.9%，LIBERO-Plus鲁棒性85.5%对82.3%；真实平台对重着色物体成功率从0.0%升至42.9%和47.5%，同时保持原外观性能。</td></tr>
<tr><td>2026-09-17</td><td>TacSushi: Tactile-Grounded World-Action Modeling for Dexterous Sushi Manipulation<br><a href='http://arxiv.org/pdf/2609.19613'>论文</a></td><td>TacSushi是触觉接地的、基于Cosmos3的世界-动作策略，行动时仅用当前观测，训练时则利用记录的未来后果监督。  
◆ 提出特征级门控融合，把指尖触觉融入动作表示，而非直接拼接。  
◆ 设计训练专用解码器，用动作块预测未来视觉、任务进度、接触风险与触觉摘要，部署时移除。  
◆ 让失败试验只提供后果监督，其动作不进入模仿学习。  
◆ 构建锚定视觉质量协议，等权融合五项人工与三项VLM评分来评估食品终端质量。  
在340成功和50失败真实机器人试验上训练，600次rollout显示其分布内/外成功率68.3%/37.5%，优于无未来监督的36.7%/10.0%和直接触觉拼接的25.0%/17.5%，证明门控触觉融合与训练期预测监督互补有效。</td></tr>
<tr><td>2026-09-17</td><td>Learning from Success and Failure: Acquiring Adaptive Dialogue Strategies for Social Robots<br><a href='http://arxiv.org/pdf/2609.19570'>论文</a></td><td>本文针对社交机器人传统对话系统依赖专家分别设计对话策略和识别用户属性、真实部署数据收集昂贵且含大量失败案例的问题，提出利用成功与失败交互自动获取对话策略。作者构建了VLM与LLM协同架构：VLM识别用户属性，并将其与对话历史输入LLM，以生成适配特定用户属性的对话策略，同时从田野实验数据集中提取策略并评估效果。
◆ 创新在于同时利用成功和失败交互学习对话策略，突破仅依赖成功样本的局限。
◆ 提出VLM识别用户属性、LLM生成个性化策略的协同架构，实现策略自动获取。
◆ 将失败策略显式纳入策略表示，证明其能补充成功策略并提升整体性能。
◆ 形成从真实部署日志构建可解释策略库、回收失败交互为可复用约束的实用流程，降低开发成本。</td></tr>
<tr><td>2026-09-16</td><td>Pose-aware Legged Robot Semantic Exploration with Omnidirectional Perception in Confined Unknown Environments<br><a href='http://arxiv.org/pdf/2609.19460'>论文</a></td><td>本文提出POSE，一种面向受限未知环境的腿式机器人姿态感知语义探索系统，利用机体俯仰/横滚与全向相机-LiDAR感知提升目标观测覆盖。
◆ 提出姿态感知视点采样模块，依据部分物体地图的预期覆盖增益选择身体姿态，并通过瞄准对齐执行减少多余姿态调整。
◆ 设计物体中心视点剪枝策略，借助视觉语言模型、持续观察历史和BEV地图，减少冗余检查访问。
◆ 将语义探索视点与几何探索视点统一纳入全局探索规划器，实现探索与精细观测协同。
仿真表明，POSE相比平面规划基线将最终目标表面覆盖率提高8-10个百分点，探索时间降低17-32%，并取得最高平均物体覆盖AUC。
真实机器车间实验验证了该系统在腿式机器人上的适用性，支持通过自适应身体姿态规划改善覆盖效率权衡。</td></tr>
<tr><td>2026-09-16</td><td>From Wizard-of-Oz Human-Robot Dialogue Collection to a Taxonomy of Robot Response Decisions: A Retrospective Analysis of Assistive Pilot Interactions<br><a href='http://arxiv.org/pdf/2609.19447'>论文</a></td><td>论文回顾性分析五名参与者在轮椅机械臂辅助室内任务中的Wizard-of-Oz对话，发现无正式通信策略虽保留真实行为，却导致机器人响应决策不一致，并由此从40个episode构建响应决策分类法。
◆ 从真实辅助交互中提炼层次化分类法，涵盖ANSWER、REPORT_DONE、REFUSE、CONFIRM、CLARIFY、ACT六种响应模式。
◆ 同时定义intent、referential、spatial、intelligibility四类歧义，为机器人何时行动、确认、澄清或拒绝提供实践判据。
◆ 用两名人类和一名AI标注者验证方案，clean-label率达91%和89%，Cohen&#x27;s kappa在决策点、模式和歧义层面为0.72至0.95。
◆ 微调LLaVA-1.6-7B于分类标签，在ACT与CLARIFY上证明用该分类法训练视觉语言模型可行。
◆ 识别决策点与REPORT_DONE的边界案例，提出约束协议以提升后续对话采集一致性。</td></tr>
<tr><td>2026-09-16</td><td>In-Context Robot Learning with VLM Agents<br><a href='http://arxiv.org/pdf/2609.19138'>论文</a></td><td>本文提出GPT-Policy，一个面向机器人的通用智能体框架，旨在无需梯度更新或持久修改任务参数的情况下实现部署时情境学习。
◆ 集成上下文编译器，保留任务相关视觉转变，把演示、示例和交互反馈转化为可迁移线索。
◆ 以视觉语言模型为决策核心，根据上下文提议可执行的机器人工具动作。
◆ 引入约束控制器，对每个动作进行验证、执行并报告结果，形成可闭环纠错的机器人行为。
◆ 在真实机器人上系统评估成功率、效率、跨模型表现和上下文消融，验证情境学习的可靠性与局限。
◆ 实验发现，人类视频演示即使无机器人动作标签也能提升任务完成，对齐动作参考在接触敏感任务上增益更大，为VLM通用能力落地物理行为提供实证基础并揭示部署挑战。</td></tr>
<tr><td>2026-09-16</td><td>PhysVGGT: Feed-Forward Dense Physical Property Estimation from A Single Image<br><a href='http://arxiv.org/pdf/2609.18920'>论文</a></td><td>PhysVGGT提出一种从单张RGB图像一次前向预测稠密物理属性图与物体级质量的前馈模型，可估计摩擦系数、邵氏硬度、杨氏模量和密度，避免现有方法的高计算开销。
◆ 将物理属性估计建模为逐像素稠密预测问题，并利用视觉几何Transformer提取几何感知token。
◆ 设计稠密预测分支估计局部物理属性，同时用全局预测分支估计物体级质量。
◆ 构建可扩展伪标签生成流程，支持大规模弱监督训练，显著减少昂贵物理测量需求。
在ABO-500上取得最优性能，并有效泛化到分布外NeRF2Physics，且无需逐物体重建和测试时优化，单图推理仅0.13秒，比先前最优快27倍。</td></tr>
<tr><td>2026-09-16</td><td>KINO: A Keyframe Interface for VLM Planning and Whole-Body Control in Humanoid Loco-Manipulation<br><a href='http://arxiv.org/pdf/2609.18869'>论文</a></td><td>论文提出一种面向人形移动操作的分层框架，把运动关键帧作为VLM任务规划与RL全身控制之间的中间表示。
◆ 以关键帧统一表达目标全身姿态及可选物体姿态，桥接语言规划、场景理解与全身控制。
◆ VLM依据语言指令、场景观测和执行反馈，从预定义库中选择连续任务相关关键帧，并重定向到当前物体位姿与尺寸。
◆ 关键帧条件全身策略将选定关键帧转化为关节级动作，实现协调的全身移动与操作。
◆ 提出基于显著性的关键帧采样策略训练低层策略，在稀疏VLM关键帧下将端到端任务成功率从44%提升到92%。
论文在仿真与Unitree G1上验证取物、运输和放置任务，支持单手与双手操作，并可泛化到训练参考之外的放置位置。</td></tr>
</tbody>
</table>
</div>

<h2 id='robot-visual-semantic-recognition'>Robot Visual Semantic Recognition</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-17</td><td>PerSeM: Persistent Semantic Memory for Long-Horizon Open-Vocabulary UAV Mapping<br><a href='http://arxiv.org/pdf/2609.19542'>论文</a></td><td>PerSeM是一种免训练的持久语义记忆框架，面向长时程开放词汇无人机建图，旨在解决逐帧语义预测在重复观测和视角变化下的时序不一致问题。
◆将逐帧开放词汇语义观测关联到持久世界空间体素，并通过多数投票构建世界一致的语义记忆。
◆提出历史保留空间细化、信任感知回放与上下文引导验证，对不确定记忆进行保守精炼，避免错误固化。
◆在Forest和UAVScenes上，持久3D记忆相较逐帧预测显著提升语义正确性与时序稳定性。
◆作为强持久记忆基线，PerSeM在全部五个UAVScenes序列上仍取得一致额外提升，且无需重训练或额外神经网络推理。
◆独立区域分析显示，增益集中于语义困难且时序不稳定区域，说明保守精炼对不确定记忆尤其有效。</td></tr>
<tr><td>2026-09-16</td><td>4D Radar Perception Algorithms for Autonomous Driving: A Review<br><a href='http://arxiv.org/pdf/2609.19216'>论文</a></td><td>本文系统综述面向自动驾驶的4D毫米波雷达感知算法，按感知任务与算法演进梳理领域发展。
◆ 提出以任务演进为主线，从信号处理、目标检测延伸到语义分割、运动估计、占据预测和动态场景重建。
◆ 系统比较仅雷达学习、多模态融合、跨模态监督与知识蒸馏三类范式。
◆ 重点分析高度、多普勒测量和雷达物理先验在不同感知任务中的利用方式。
◆ 汇总现有数据集的任务覆盖、输入数据、标注与评估协议，明确各方向的经验支撑。
◆ 给出从稀疏目标感知走向动态空间理解的任务导向视角，并总结挑战与未来方向。</td></tr>
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
</tbody>
</table>
</div>

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

<h2 id='archive'>归档</h2>

> [点击查看所有历史论文归档](./docs/archive.md)


<h2>GitHub 实验室仓库监控</h2>

<h3>HKU-MARS (港大火星实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5192</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4652</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2452</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1639</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1621</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1506</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1334</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1298</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1079</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>1041</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>942</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>808</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>783</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>747</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>742</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>727</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>679</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>665</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>630</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>618</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>607</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>578</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>570</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>532</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>509</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>461</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>454</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>364</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>348</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>277</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>272</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>257</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>242</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>228</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>223</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>221</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>211</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>189</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2875</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1671</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1368</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1096</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1059</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>881</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>709</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>667</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>662</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>623</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>605</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>577</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>572</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>571</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>553</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>518</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>508</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>464</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>456</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>451</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>334</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>313</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>306</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>301</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>170</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>169</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
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
> 更新于: 2026.09.19
