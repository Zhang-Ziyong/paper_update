# 计算机视觉领域最新论文 (2026.05.22)

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
</ol>
</details>

<h2 id='slam'>SLAM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-05-19</td><td>Multi-Session Ground Texture SLAM in Low-Dynamic Environments<br><a href='http://arxiv.org/pdf/2605.19701'>论文</a></td><td>针对现有地面纹理SLAM系统无法应对多会话低动态环境变化的问题，本文研究了三种技术对轨迹估计精度的影响。
◆提出将Kullback-Leibler散度作为相似性评分和影响回环闭合置信度的偏差，此方法在实验中取得了最成功的效果。
本文不仅对这三种方法进行了全面分析，还对Kullback-Leibler散度的影响机制进行了深入探索。
◆发布了一个全新的多会话地面纹理数据集，包含会话间地面变化图像和高精度位姿信息。
该数据集为机器人社区在低动态环境下的SLAM系统评估提供了重要支持。</td></tr>
<tr><td>2026-05-19</td><td>EpiDiffVO: Geometry-Aware Epipolar Diffusion for Robust Visual Odometry<br><a href='http://arxiv.org/pdf/2605.19556'>论文</a></td><td>本文提出了一种用于视觉里程计的稀疏极线匹配框架，旨在解决现有学习方法依赖密集匹配导致的冗余和几何可解释性降低的问题。
◆引入极线扩散过程，对对应点的不确定性进行建模，并将关键点精炼至极线一致性。
◆将精炼后的对应点与深度线索结合，构建出编码点间关系结构的斯坦纳图表示。
◆利用图神经网络学习紧凑的对应点子集，并通过可微奇异值分解求解器实现端到端的几何估计。
实验表明，该方法有效减少了对应点冗余，并在挑战性基线上保持了稳健的位姿估计。</td></tr>
<tr><td>2026-05-19</td><td>PRISM-SLAM: Probabilistic Ray-Grounded Inference for Scale-aware Metric SLAM<br><a href='http://arxiv.org/pdf/2605.19257'>论文</a> | <a href='https://prismslam-cmd.github.io/prismslam_pr/'>代码</a></td><td>针对单目SLAM的尺度模糊与动态环境跟踪失败问题，本文提出PRISM-SLAM框架，通过将视觉基础模型先验严谨集成到贝叶斯因子图中，实现了尺度感知且度量一致的实时定位与建图。
◆引入普吕克光线距离因子，在全局度量坐标系中锚定单目观测，使度量尺度具备Fisher可辨识性，从数学上根本解决了尺度漂移问题。
◆提出动态场景不确定性门控机制，利用时间深度一致性推导认知不确定性代理，通过概率软门控降低动态干扰物权重，避免了传统语义分割的高昂计算开销。
系统采用多进程架构异步处理基础模型推理与几何跟踪，仅依赖RGB输入即可实现30帧每秒的实时度量输出。
实验表明其度量绝对轨迹误差几乎等同于无尺度对齐误差，无需任何事后尺度校正即可生成可直接部署的度量轨迹。</td></tr>
<tr><td>2026-05-20</td><td>FUSE: A Framework for Unified State Estimation in Vehicular and Robotic SLAM Systems<br><a href='http://arxiv.org/pdf/2605.18047'>论文</a></td><td>现有的紧耦合SLAM方法通常将时间处理、几何关联、估计器公式与地图更新策略深度绑定，导致难以单独修改某一设计而无需重构整个系统。本文提出了FUSE，一个面向车辆与机器人SLAM系统的统一状态估计框架。
◆通过构建观测摄取、传播、更新与状态查询的接口，成功解耦了时间处理、残差就绪的局部几何关联、估计器公式与地图更新策略。
◆开发了一种LiDAR-IMU实例化方案，验证了框架在混合频率感知与方向退化条件下的有效性，实现了退化感知校正与残差筛选。
在418米的回环走廊测试中，该实例相较于最低误差基线Faster-LIO实现了7.9%的相对误差降低，端到端轨迹误差为1.626米。结果表明FUSE不仅能有效组织状态估计的设计选择，还能在弱可观测方向上正则化更新。</td></tr>
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

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-05-18</td><td>Efficient 3D Content Reconstruction and Generation<br><a href='http://arxiv.org/pdf/2605.18052'>论文</a></td><td>该论文致力于解决自动3D内容创建中流程繁琐的问题，推动了从文本或图像直接合成3D资产的高效化。论文在3D生成与3D重建两个互补的范式上均做出了核心贡献。
◆在生成方面，提出Instant3D方法，将多视角扩散与前馈稀疏视角3D重建结合，仅需5至20秒即可生成高质量3D资产。
◆在重建方面，开发FastMap运动恢复结构流程，通过广泛使用融合GPU核心的一阶优化，实现比先前最优技术高达10倍的加速。
并且，该重建方法在大幅提升计算速度的同时，仍保持了相当的位姿估计精度和下游新视角合成质量。</td></tr>
<tr><td>2026-05-16</td><td>RHINO: Reconstructing Human Interactions with Novel Objects from Monocular Videos<br><a href='http://arxiv.org/pdf/2605.17014'>论文</a> | <a href='https://lxxue.github.io/RHINO'>代码</a></td><td>本文提出了RHINO三步框架，从单目RGB视频中共同恢复人、未知物体和静态场景的3D重建，解决了深度模糊、遮挡和运动纠缠的难题。同时，该研究构建了包含手持单目视频与4D捕捉真值的新数据集，并在新视角合成与4D重建任务上超越了现有基线。
◆利用3D感知基础模型稳定结构恢复，分别从前景和背景像素提取粗糙物体形状与表观运动以及场景形状与相机运动。
◆通过估计人体并从表观运动中减去相机运动来提取物体真实运动，成功将人、物体和场景对齐到统一的世界坐标系中。
◆采用具有逐组件符号距离场的组合式神经场细化形状，并引入可微接触先验吸引表面同时惩罚穿透，提升重建的物理合理性。</td></tr>
<tr><td>2026-05-16</td><td>SemaVoice: Semantic-Aware Continuous Autoregressive Speech Synthesis<br><a href='http://arxiv.org/pdf/2605.16964'>论文</a></td><td>本文提出SemaVoice框架，解决了连续自回归语音合成中语义韵律建模与重建驱动表示之间的不匹配问题，避免了模型过度关注低级声学纹理而牺牲语义连贯性，从而缓解了自回归生成的误差累积。
◆引入语音基础模型引导的对齐机制，优化连续语音表示，使其更好地捕捉局部语义一致性与全局结构关系。
◆在自回归框架内采用条件块级扩散头，实现高质量的语音合成。
在Seed-TTS基准测试中，该方法英文词错率低至1.71%，在客观与主观评估上均与最先进开源系统极具竞争力。
此外，在固定信息率约束下的不同表示粒度中，该对齐机制均带来了显著提升，进一步验证了其有效性。</td></tr>
<tr><td>2026-05-15</td><td>SCARED-C: Corrected Camera Poses for Endoscopic Depth Estimation<br><a href='http://arxiv.org/pdf/2605.16628'>论文</a></td><td>原SCARED数据集虽是内窥镜深度估计的常用基准，但其非关键帧深度图依赖机器人运动学导致位姿误差大，仅有35个关键帧可用。
本文提出了SCARED-C数据集，将可靠的RGB-D对数量从35个大幅扩展至17135个。
◆采用COLMAP运动恢复结构系统重新估计所有帧的相机位姿，克服了原机器人运动学引入的误差。
◆设计尺度恢复步骤，利用关键帧真值深度图将重建结果对齐至度量空间，确保深度数据的物理准确性。
通过立体视差评估和单目深度估计实验验证了纠正位姿的有效性，并已向社区公开数据集与代码。</td></tr>
<tr><td>2026-05-06</td><td>egenioussBench: A New Dataset for Geospatial Visual Localisation<br><a href='http://arxiv.org/pdf/2605.05351'>论文</a> | <a href='https://github.com/fratopa/egenioussBench'>代码</a></td><td>◆ We present egenioussBench, a visual localisation benchmark built on geospatial reference data: a city-scale airborne 3D mesh and a CityGML LoD2 model.
◆ This pairing reflects deployable mapping assets and supports true scalability beyond traditional SfM-based approaches.
◆ The query data comprise smartphone images with centimetre-accurate, map-independent ground truth obtained via PPK and GCP/CP-aided adjustment.</td></tr>
<tr><td>2026-05-19</td><td>Permutation Routing on Ramanujan Hypergraphs with Applications to Neutral Atom Quantum Architectures<br><a href='http://arxiv.org/pdf/2605.02498'>论文</a></td><td>本文将中性原子量子架构上的量子比特路由问题重构为超图变换，核心证明了拉马努金超图的对数级路由界限。
◆提出基于特征值居中的单侧条件替代双侧谱隙假设，证明拉马努金超图路由数为Θ(log N)。
◆为三维声光透镜架构建立虚拟叠加定理，利用O(log N)独立层实现Θ(log N)路由。
◆发现阿贝尔Alon-Boppana壁垒并应用仿射去随机化降低拥塞，利用k重覆盖塔递归提升实现O(log N)路由。
◆提出纠缠辅助路由以O(log N)深度实现隐形传态，并设计混合贪心-Valiant协议实现约3倍加速。
◆提出分层多尺度路由方案，在最优块大小下实现O(log N)深度。</td></tr>
<tr><td>2026-05-03</td><td>DP-SfM: Dual-Pixel Structure-from-Motion without Scale Ambiguity<br><a href='http://arxiv.org/pdf/2605.01852'>论文</a> | <a href='https://github.com/lilika-makabe/dp-sfm-tpami.git'>代码</a></td><td>◆ Multi-view 3D reconstruction, namely, structure-from-motion followed by multi-view stereo, is a fundamental component of 3D computer vision.
◆ In general, multi-view 3D reconstruction suffers from an unknown scale ambiguity unless a reference object of known size is present in the scene.
◆ In this article, we show that multi-view images captured using a dual-pixel (DP) sensor can automatically resolve the scale ambiguity, without requiring a reference object or prior calibration.</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-05-21</td><td>Superhuman Safe and Agile Racing through Multi-Agent Reinforcement Learning<br><a href='http://arxiv.org/pdf/2605.22748'>论文</a></td><td>本文提出利用多智能体强化学习为真实世界动态交互提供安全保障，打破了传统单智能体范式忽视其他参与者的局限。
◆提出基于联赛的自博弈训练方法，使智能体在高速四旋翼竞速中进化出主动避撞、超车与处理气动下洗等复杂</td></tr>
<tr><td>2026-05-21</td><td>N3P: Accelerated Automated Parking via a Learning-Based Naturalistic Three-Stage Scheme<br><a href='http://arxiv.org/pdf/2605.22722'>论文</a></td><td>本文提出了一种基于学习的自然主义三阶段自动泊车框架N3P，旨在解决传统Hybrid A*算法计算昂贵和强化学习方法可靠性差且难以处理长视距约束的问题。
◆创新性地引入中间准备姿态，将复杂的泊车操作分解为更简单的子问题，有效降低了计算复杂度。
◆利用学习模块预测该中间准备姿态，实现了路径生成的大幅加速。
该框架与Hybrid A*算法结合进行了验证，实验表明N3P增强的Hybrid A*在垂直和平行泊车场景中规划速度提升超过80%。
此外，该方法在成功率和轨迹质量上优于强化学习基线，能生成更短且换挡次数更少的轨迹，同时保持相近或更低的规划时间</td></tr>
<tr><td>2026-05-21</td><td>Perceived Safety of Workers in Encounters with Large Industrial AGVs<br><a href='http://arxiv.org/pdf/2605.22461'>论文</a></td><td>本文研究了工业工人与大型自动导引车在共享空间互动时的感知安全问题，填补了现有研究对大型AGV及真实职业工人关注不足的空白。
◆首次聚焦大型AGV与真实职业工人的近距离互动，克服了以往研究多基于小型AGV和学生群体的局限性。
◆通过对比真实世界与虚拟现实环境下的实验，探讨了VR安全性感知结果向真实场景转移的有效性。
◆采用手持压力敏感触发接口结合问卷评估威胁，并创新性地让工人根据经验自定义避碰参数。
研究发现VR中的威胁感知略高于真实环境，且无论在预设还是自定义轨迹中，1.5至2米的通过距离最受工人偏好。</td></tr>
<tr><td>2026-05-20</td><td>Design for Manufacturing: A Manufacturability Knowledge-Integrated Reinforcement Learning Framework for Free-Form Pipe Routing in Aeroengines<br><a href='http://arxiv.org/pdf/2605.20644'>论文</a></td><td>本文提出了FPRO框架，解决了航空发动机管路布线与下游制造脱节的问题，实现了设计与制造的一体化。
◆在Frenet坐标系下将管路布线问题转化为边值问题，利用曲率和挠率剖面结合三次Hermite插值表示管路路径。
◆将领域特定的制造知识作为曲率和挠率容许范围的约束嵌入强化学习，确保生成的路径直接满足可制造性要求。
◆采用结合随机探索与阶段引导奖励机制的近端策略优化算法进行路径寻优，显著提升了收敛速度和综合性能。
◆提出统一映射公式，将优化路径直接转换为弯模运动轨迹，实现六轴自由弯管机的直接加工制造。
实验表明该框架能稳定生成无碰撞且平滑的可制造路径，实际制造验证了数字设计与实体管路的高度一致性及其实用可行性。</td></tr>
<tr><td>2026-05-19</td><td>D-CLING: Prior-Preserving Depth-Conditioned Fine-Tuning for Navigation Foundation Models<br><a href='http://arxiv.org/pdf/2605.19690'>论文</a> | <a href='https://toyotafrc.github.io/DCLING-Proj/'>代码</a></td><td>本文提出了D-CLING微调方法，旨在解决导航基础模型微调时预训练先验被侵蚀及避障失效的问题。该方法让模型在新场景中高效学习的同时，保持预训练的泛化能力以实现鲁棒的长期导航。
◆受ControlNet启发，附加预训练骨干的可训练副本并采用零初始化残差路径连接，使模型高效学习域内几何线索。
◆在获取新环境几何信息的同时，有效保留模型原有的各种预训练行为知识，防止微调破坏先验。
◆实验证明该方法显著减少了真实导航中的碰撞与人工干预，并在微调数据集外维持或提升了动作预测能力，为持续学习提供了重要见解。</td></tr>
<tr><td>2026-05-18</td><td>ManiSoft: Towards Vision-Language Manipulation for Soft Continuum Robotics<br><a href='http://arxiv.org/pdf/2605.18617'>论文</a> | <a href='https://buaa-colalab.github.io/ManiSoft'>代码</a></td><td>本文提出了ManiSoft，一个针对软体连续体机器人的视觉语言操作基准，旨在解决软体臂本体感知不可靠和分布式驱动带来的挑战。
◆提出了一种定制仿真器，通过弹性力约束将逼真的软体动力学与丰富接触交互相结合。
◆定义了四个展示可变形控制不同方面的任务，并构建了自动化流程生成6300个多样化场景及专家轨迹。
◆采用分层方法大规模生成高质量轨迹，即高级规划器分解任务为路径点，低级强化学习策略生成力矩命令进行追踪。
基准测试表明现有模型在随机化下性能显著下降，主要归因于视觉本体感知估计不准及未充分利用软体可变形性避障。
该基准为弥合刚性臂与软体臂在视觉语言操作领域的鸿沟提供了宝贵测试平台。</td></tr>
<tr><td>2026-05-20</td><td>CosFly-Track: A Large-Scale Multi-Modal Dataset for UAV Visual Tracking via Multi-Constraint Trajectory Optimization<br><a href='http://arxiv.org/pdf/2605.17776'>论文</a></td><td>针对无人机视觉跟踪缺乏专用训练数据的问题，本文提出了CosFlyTrack大规模多模态数据集及其可扩展生成流程。该数据集基于六千条行人路径生成约一万两千条无人机轨迹，包含二百四十万个时间步及七种对齐数据通道。
◆开发了MuCO多约束优化器，在连续三维空间直接规划轨迹，结合BVH加速查询同时满足目标可见性、视点质量、避障、平滑与运动学可行性。
◆克服了传统网格规划器的离散化伪影和事后平滑缺陷，实现了高质量专家轨迹的生成。
微调实验表明，该数据集将七个视觉语言模型的跟踪成功率提升了五十三至六十九个百分点，有效验证了其对动态目标跟踪智能体的训练价值。</td></tr>
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

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-20</td><td>ArchSIBench: Benchmarking the Architectural Spatial Intelligence of Vision-Language Models<br><a href='http://arxiv.org/pdf/2605.20837'>论文</a></td><td>现有视觉语言模型的评测多停留在基础空间认知，忽略了更高阶的建筑空间认知能力。本文提出基于建筑学、认知科学和心理学视角的建筑空间智能基准ArchSIBench。◆构建了涵盖感知、推理、导航、变换和构型五个核心维度及17个细粒度子任务的系统化评测体系。◆由建筑学专家人工标注构建了3000个高质量问答对，填补了高阶建筑空间认知评测数据的空白。◆通过全面评测揭示了现有模型与人类的显著差距及模型内部能力的不均衡，指出现有先进模型在空间变换和构型推理上远不及专业建筑师水平。</td></tr>
<tr><td>2026-05-20</td><td>Q-SpiRL: Quantum Spiking Reinforcement Learning for Adaptive Robot Navigation<br><a href='http://arxiv.org/pdf/2605.20801'>论文</a></td><td>本文提出了Q-SpiRL框架，用于解决动态环境中自适应机器人导航的可靠性与轨迹效率问题。
◆结合基于脉冲的时间处理与变分量子特征变换，提出量子增强脉冲神经网络QSNN作为核心架构。
◆构建了包含五种智能体家族的统一训练与评估管线，实现了从经典到量子脉冲强化学习模型的全面对比。
◆在IBM真实量子硬件上执行策略，验证了混合量子脉冲策略在实际设备条件下部署的可行性。
实验表明，在包含动静态障碍物的</td></tr>
<tr><td>2026-05-19</td><td>Enhancing Graph-Based SLAM in GNSS-Denied environments by leveraging leg odometry<br><a href='http://arxiv.org/pdf/2605.20484'>论文</a></td><td>本文提出了一种增强图优化SLAM的因子图架构，以解决足式机器人在GNSS拒止环境中LiDAR容易产生高程漂移的问题。
◆创新性地在LIO-SAM框架中引入了由本体感受腿里程计驱动的并行运动学通道。
◆通过带有选择性噪声模型的全等相对位姿约束，将该运动学通道与主LiDAR-惯性通道进行有效耦合。
在四足平台超过一公里的室外测试中，该方法将高程漂移从三十多米降至三十厘米以内，并使基线方法完全失效的场景成功收敛。
研究表明，原本用于步态控制的本体感受数据可作为轻量有效的垂直锚点，显著提升GNSS拒止环境下的SLAM鲁棒性。</td></tr>
<tr><td>2026-05-19</td><td>Minimalist Visual Inertial Odometry<br><a href='http://arxiv.org/pdf/2605.19990'>论文</a></td><td>本文提出了一种极简的平面视觉惯性里程计方法，仅用四个视觉测量值与IMU即可为差速驱动机器人提供稳健的运动估计。
◆提出利用四个朝下的光电二极管结合光学盖伯掩码感知外界，产生能直接编码速度的信号。
◆通过物理模拟器联合优化掩码参数与时间卷积网络，使模型能仅从这四个测量值中解码出速度。
◆将解码的速度估计值与IMU提供的角速度相配对，成功生成连续的平面运动轨迹。
实验表明，该原型系统无需任何真实世界数据微调，便能在多种室内外地面上紧密跟踪真实轨迹，证明了极简感知能实现高效且准确的里程计。</td></tr>
<tr><td>2026-05-19</td><td>KappaPlace: Learning Hyperspherical Uncertainty for Visual Place Recognition via Prototype-Anchored Supervision<br><a href='http://arxiv.org/pdf/2605.19435'>论文</a> | <a href='https://github.com/mayayank95/UncertaintyAwareVPR'>代码</a></td><td>针对现有视觉位置识别方法缺乏校准的不确定性估计这一问题，本文提出了KappaPlace框架以学习不确定性感知的表征。
◆提出原型锚定监督策略，利用潜在类别代表作为概率优化目标的锚点。
◆将图像描述子建模为von Mises-Fisher变量，通过轻量级模块预测浓度参数作为偶然不确定性的直接代理。
◆推导出新颖的匹配级公式，突破了现有方法仅限查询视角的局限，能够量化特定查询与参考图对的匹配可靠性。
该方法提供联合训练与后训练扩展两种模式，在五个基准上将期望校准误差降低高达百分之五十，同时保持或提升检索召回率。
实验证明该框架为位置识别流程提供了鲁棒且校准良好的信号，保障了安全关键应用中的可靠决策。</td></tr>
<tr><td>2026-05-18</td><td>Qumus: Realization of An Embodied AI Quantum Material Experimentalist<br><a href='http://arxiv.org/pdf/2605.18407'>论文</a></td><td>本文介绍了首个AI量子材料实验学家Qumus，它将智能多智能体系统与机器人微型实验室相融合。该系统突破了高水平推理与实时物理执行的壁垒，实现了从假设生成到结果报告的全科学周期自主导航。
◆首次实现了由AI创造石墨烯以及通过范德华堆叠制造原子级薄场效应晶体管等复杂纳米器件。
◆展现出自主纠错和闭环实验能力，能够直接从量子世界的物理反馈中学习并自我改进。
◆建立了一个可通用化的具身AI框架，为加速量子材料与电子学等领域的科学发现开辟了新路径。</td></tr>
<tr><td>2026-05-18</td><td>DocOS: Towards Proactive Document-Guided Actions in GUI Agents<br><a href='http://arxiv.org/pdf/2605.18048'>论文</a></td><td>现有GUI智能体依赖静态参数知识，难以处理缺乏程序性知识的长尾任务，常导致低效试错。
为解决此限制，本文提出面向动态开放网络环境的主动文档引导动作新范式，使智能体能像人类一样自主搜索文档来解决问题。
◆提出主动文档引导动作范式，突破传统静态知识限制，赋予GUI智能体自主搜寻并利用外部文档解决长尾任务的能力。
◆构建DocOS基准测试，在完全交互式环境中评估智能体网页导航、文档定位、指令理解及转化为可执行GUI动作的全流程能力。
◆揭示制约智能体发展的双重瓶颈，即难以可靠定位相关信息以及将检索指令精准转化为动作，为自演化GUI智能体指明关键方向。</td></tr>
<tr><td>2026-05-17</td><td>MUSE: Multimodal Uncertainty Quantification of State Estimation<br><a href='http://arxiv.org/pdf/2605.17421'>论文</a></td><td>该论文提出了MUSE，一个用于视觉状态估计的多模态不确定性量化实时学习框架。
◆提出基于Mamba的序列建模方法，能够从多个异步传感器流中实时估计定位不确定性。
◆有效应对了视觉惯性里程计中异方差和多模态特性带来的不确定性量化与故障检测难题。
实验表明，与现有方法相比，MUSE在公开和内部数据集上均展现出更高的可靠性与鲁棒性。
此外，消融研究也充分验证了该框架关键设计选择的合理性。</td></tr>
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

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-21</td><td>N3P: Accelerated Automated Parking via a Learning-Based Naturalistic Three-Stage Scheme<br><a href='http://arxiv.org/pdf/2605.22722'>论文</a></td><td>本文提出了N3P，一种基于学习的快速三阶段自动停车框架，解决了传统Hybrid A*计算昂贵与强化学习可靠性差的问题。
◆引入中间预备位姿并通过学习模块预测，将复杂停车机动分解为更简单的子问题。
◆利用该分解策略有效降低计算复杂度，从而大幅加速路径生成过程。
◆将学习模块与Hybrid A*算法结合，在垂直和平行停车场景中实现了超过80%的规划加速。
◆相比强化学习方法，该框架具有更高的成功率，且生成的轨迹更短、换挡次数更少，轨迹质量显著提升。</td></tr>
<tr><td>2026-05-21</td><td>Branch-Stochastic Model Predictive Control for Motion Planning under Multi-Modal Uncertainty with Scenario Clustering<br><a href='http://arxiv.org/pdf/2605.22600'>论文</a></td><td>该论文针对自动驾驶运动规划中多模态不确定性问题，指出传统随机模型预测控制虽能降低轨迹层面的保守性，但在意图不确定性上仍显保守。为此，论文核心贡献是提出结合随机模型预测控制与分支结构的新方法，使规划器能为不同意图生成独立轨迹并保证轨迹不确定性下的安全性。
◆提出基于高层决策相似性的场景聚类方法，通过合并预测场景确保算法的实时可解性。
◆设计自适应分支时间计算机制，推迟到意图不确定性充分降低时才决定执行分离规划以避免过早承诺。
仿真结果表明，该方法有效提升了安全性，显著降低了保守性，并实现了实时计算性能。</td></tr>
<tr><td>2026-05-20</td><td>MC-Risk: Multi-Component Risk Fields for Risk Identification and Motion Planning<br><a href='http://arxiv.org/pdf/2605.21406'>论文</a></td><td>本文提出了MC-Risk，一种与规划器对齐的鸟瞰图多组件风险场，可实现早期、校准且类别感知的风险定位。
◆针对机动车代理，融合黑盒多模态轨迹预测与解析式高斯环面结构，横向宽度随速度和曲率增加，高度随前视距离衰减。
◆针对弱势道路使用者，用与朝向和速度对齐的前向偏置各向异性核替换传统的各向同性行人斑块。
◆针对道路惩罚，利用高清地图拓扑施加偏路惩罚，以及针对同向和反向的车道感知风险暴露。
该研究首次在RiskBench碰撞子集上对风险场进行了标准化定量评估，取得最佳整体风险定位和最早危险指示。
最后，将该风险场作为MPC代价密度，展示了即插即用的规划接口，无需额外训练即可生成风险感知轨迹。</td></tr>
<tr><td>2026-05-20</td><td>Benchmarking Empirical and Learning-Based Approaches for Feedforward Steering Control in Autonomous Racing<br><a href='http://arxiv.org/pdf/2605.21111'>论文</a> | <a href='https://github.com/TUMRT/steering_ff_control'>代码</a></td><td>本文系统性地基准测试了两种基于学习和两种基于经验的前馈转向控制器，以评估其在自动驾驶赛车中减少反馈转向修正的能力。研究在基于真实阿布扎比自动驾驶赛车联赛的高保真双轨车辆动力学模拟器中，对这些控制器进行了开环与闭环测试。
◆提出了一种基于多项式曲面拟合的新型EHD公式，该公式能以最少的参数化捕捉依赖速度的非线性转向行为。
◆揭示了学习型控制器在开环评估中虽预测误差最低，但此优势无法转化为闭环路径跟踪性能或圈速的提升。
◆提出的新型EHD方法取得了最佳的闭环鲁棒性和圈速，突显了必须在完整的轨迹规划与控制软件栈中评估前馈策略的必要性。</td></tr>
<tr><td>2026-05-20</td><td>Grounding Driving VLA via Inverse Kinematics<br><a href='http://arxiv.org/pdf/2605.21061'>论文</a></td><td>该论文揭示了现有驾驶视觉语言模型在预测轨迹时忽视视觉标记的问题，指出其根源在于任务构建的结构不适定性而非训练不足。从逆运动学视角分析，轨迹恢复需要当前与未来视觉状态作为边界条件，而现有模型仅提供当前状态，导致模型仅靠自车状态和文本指令走捷径。
◆提出了下一视觉状态预测目标，强制大语言模型预测未来视觉场景，提供密集视觉监督并抑制捷径路径。
◆设计了独立的逆运动学网络，该基于交叉注意力的条件扩散模型仅以当前和未来视觉状态为输入，消除轨迹解码对自车状态和文本捷径的依赖。
仅凭上述创新，该0.5B规模模型成功恢复了视觉基础能力，在NAVSIM-v2和nuScenes基准上取得了媲美7B至8B模型的轨迹规划性能，且在转弯等动态场景中提升尤为显著。</td></tr>
<tr><td>2026-05-20</td><td>SubTGraph: Large-Scale Subterranean Environment Synthesis with Controllable Topological Variability for Robotic Autonomy Validation<br><a href='http://arxiv.org/pdf/2605.20917'>论文</a> | <a href='https://github.com/LTU-RAI/SubTGraph.git'>代码</a></td><td>本文提出了SubTGraph框架，填补了地下环境缺乏大规模仿真基准以进行机器人自主性严格统计评估的空白。◆创新性地基于用户结构约束构建代价矩阵，结合Dijkstra算法与拓扑度量瓦片程序化生成多层次地下环境。◆支持高变异性与可控参数合成，用户可根据拓扑、维度和纹理等规范生成矿井、自然洞穴和熔岩管道等不同场景。◆通过语义分割真值验证、多智能体路径规划趋势识别和LIO SLAM极限压力测试三个案例，全面验证了框架对自主栈各层级的评估能力。◆开源了环境生成代码库并发布了包含150个高变异性地下世界的数据库，为该领域提供了关键的基准测试资源。</td></tr>
<tr><td>2026-05-19</td><td>Variance-Reduced Manifold Sampling via Polynomial-Maximization Density Estimation<br><a href='http://arxiv.org/pdf/2605.19938'>论文</a></td><td>针对隐式流形均匀采样中MASEM方法因k近邻密度估计误差易被放大而影响性能的问题，本文探索了多项式最大化矩估计器替代插入式密度规则的可行性。
◆提出PMM-MASEM模块，通过嵌套k近邻半径计算壳间距并估计标准化累积量，在分布偏离平坦指数分布时启用PMM2或PMM3估计器，否则回退至最大似然估计。
◆引入自适应门控与回退机制，确保在平坦均匀流形上直接使用已是最大似然估计的插入式规则，避免不必要的性能损失。
◆通过蒙特卡洛实验验证门控策略有效性，证明在非对称伽马和边界间距情况下能将密度均方误差降低22%至36%。
实验也揭示了方法在均匀间距下性能退化等局限，因此本文核心贡献在于明确了该方法的适用边界而非提供通用的改进方案。</td></tr>
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


<h2>GitHub 实验室仓库监控</h2>

<h3>HKU-MARS (港大火星实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>4701</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4080</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2403</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1604</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1591</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1403</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1246</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1209</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>914</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>914</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>890</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>789</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>781</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>737</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>721</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>699</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>629</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>620</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>617</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>583</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>559</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>549</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>529</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>498</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>460</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>431</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>384</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>342</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>335</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>260</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>251</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>233</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>218</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>204</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>197</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>194</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>147</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>146</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>141</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>116</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2839</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1627</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1351</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1097</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1034</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>867</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>695</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>654</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>653</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>618</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>582</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>572</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>562</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>559</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>549</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>512</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>479</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>462</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>440</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>438</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>335</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>311</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>299</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>280</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>274</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>258</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>221</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>205</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>201</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>185</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>176</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>168</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>166</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>159</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>150</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>137</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>133</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>101</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.05.22
