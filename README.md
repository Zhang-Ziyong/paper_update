# 计算机视觉领域最新论文 (2026.05.26)

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
<tr><td>2026-05-25</td><td>G-DRAGON: Geospatial Reasoning and Dynamic Planning for Retrieval-Augmented Outdoor Navigation<br><a href='http://arxiv.org/pdf/2605.25646'>论文</a></td><td>本文提出G-DRAGON，一个用于户外开放世界导航的检索增强框架，解决了现有视觉语言导航缺乏长距离地理空间基础以及云端大模型易产生幻觉且无法进行“最后一公里”探索的问题。
◆提出基于轻量级大模型的生成式检索方法，将自然语言指令映射到本地OSM实体以生成准确坐标，避免了事实幻觉并实现全局路线规划。
◆设计高级规划模块，将地理空间航点投影到机器人可导航坐标系中，成功桥接全局拓扑路线与SLAM系统。
◆针对“最后一公里”任务，</td></tr>
<tr><td>2026-05-24</td><td>FusionCore: A 23-State Unscented Kalman Filter for IMU, Wheel Encoder, GPS, and Visual SLAM Fusion in ROS 2<br><a href='http://arxiv.org/pdf/2605.25239'>论文</a> | <a href='https://github.com/manankharwar/fusioncore'>代码</a></td><td>本文提出了FusionCore，一个开源的ROS 2传感器融合包，通过23状态无迹卡尔曼滤波器将IMU、轮式编码器、GPS和视觉SLAM位姿融合为100Hz里程计流。在NCLT</td></tr>
<tr><td>2026-05-24</td><td>A Decentralized LiDAR-SLAM System with Certifiably Optimal Pose Graph Optimization<br><a href='http://arxiv.org/pdf/2605.25051'>论文</a></td><td>本文提出首个集成可证明最优位姿图优化后端的去中心化多机器人LiDAR-SLAM系统，旨在解决现有方法在大规模或退化环境中全局一致性差的难题。
◆首次将可证明最优的PGO后端集成于去中心化LiDAR-SLAM中，克服了传统局部搜索易陷入次优解和长期不一致的缺陷。
◆创新性地采用黎曼块坐标下降算法，确保了全局一致的轨迹估计。
◆系统无需依赖精确的初始猜测即可实现优化，显著增强了在复杂场景下的鲁棒性。
实验表明，该系统轨迹均方根误差相比现有最先进的DiSCo-SLAM大幅降低了48.9%。</td></tr>
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
<tr><td>2026-05-23</td><td>PRISM-SLAM: Probabilistic Ray-Grounded Inference for Scale-aware Metric SLAM<br><a href='http://arxiv.org/pdf/2605.19257'>论文</a> | <a href='https://prismslam-cmd.github.io/prismslam_pr/'>代码</a></td><td>针对单目SLAM的尺度模糊与动态环境跟踪失败问题，本文提出PRISM-SLAM框架，通过将视觉基础模型先验严谨集成到贝叶斯因子图中，实现了尺度感知且度量一致的实时定位与建图。
◆引入普吕克光线距离因子，在全局度量坐标系中锚定单目观测，使度量尺度具备Fisher可辨识性，从数学上根本解决了尺度漂移问题。
◆提出动态场景不确定性门控机制，利用时间深度一致性推导认知不确定性代理，通过概率软门控降低动态干扰物权重，避免了传统语义分割的高昂计算开销。
系统采用多进程架构异步处理基础模型推理与几何跟踪，仅依赖RGB输入即可实现30帧每秒的实时度量输出。
实验表明其度量绝对轨迹误差几乎等同于无尺度对齐误差，无需任何事后尺度校正即可生成可直接部署的度量轨迹。</td></tr>
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
<tr><td>2026-05-22</td><td>Joint Target-Less Intrinsic and Extrinsic Camera-LiDAR Calibration using Deep Point Correspondences<br><a href='http://arxiv.org/pdf/2605.23397'>论文</a></td><td>本文提出首个完全无需标定板的相机与激光雷达联合标定流程，突破了现有基于深度点对应的标定方法需已知内参的局限。该方法利用深度像素点对应关系，可同时估计包含径向与切向畸变的针孔相机内参以及相机与激光雷达的外参。
◆通过运动恢复结构实现相机内参的自动初始化。
◆将相机与激光雷达特征匹配推广至包含畸变且内参未知的原始图像。
◆将对应点估计与内参及外参的联合非线性优化进行紧密耦合。
在KITTI数据集上的实验表明，该联合标定方法在恢复精确内参的同时有效提升了外参的标定精度。</td></tr>
<tr><td>2026-05-20</td><td>JWST Advanced Deep Extragalactic Survey (JADES) Data Release 5: stellar population catalogue for galaxies in GOODS-N and GOODS-S<br><a href='http://arxiv.org/pdf/2605.21599'>论文</a></td><td>本文发布了JADES第五次数据发布的星系恒星星族星表，利用深度JWST成像与多波段数据对GOODS-N和GOODS-S中约50万个源进行了均匀的贝叶斯物理性质推断，模型包含了星云发射、尘埃及中红外活动星系核等复杂物理过程。
◆采用随红移演化的星系主序先验对非参数化恒星形成历史进行建模，提供了物理驱动的长期形态，同时保留灵活性并允许数据支持的偏离。
◆利用该物理先验有效缓解了非物理拟合解，显著减少了红移、年龄、尘埃和金属丰度间的简并度，对暗弱源尤为有效。
依托JADES数据的深度和广度，该研究实现了对低质量星系恒星质量的稳健测量，并改善了红移1至9约35万个星系近期恒星活动的约束。
公开发布的增值星表提供了统一的恒星星族参数集，为跨宇宙时间的星系生长、熄灭与质量累积的统计研究奠定了基础。</td></tr>
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
<tr><td>2026-05-22</td><td>MASt3R-Nav: WayPixel Navigation in Relative 3D Maps<br><a href='http://arxiv.org/pdf/2605.24111'>论文</a></td><td>本文提出MASt3R-Nav导航</td></tr>
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
<tr><td>2026-05-22</td><td>On the Performance of DCF in Full Duplex WLANs with Hidden Terminals<br><a href='http://arxiv.org/pdf/2605.23276'>论文</a></td><td>本文研究了存在隐藏终端的全双工WLAN中DCF协议的性能表现。研究采用性能建模方法，将全双工场景与传统半双工场景进行了对比分析。结果表明在DCF机制下，全双工技术的饱和吞吐量相比半双工仅有极微小的提升。
◆本文创新性地针对存在隐藏终端的全双工WLAN环境构建了CSMA/CA协议的性能评估模型。
◆研究揭示了全双工同时接入需求与DCF避免同时接入设计之间的根本矛盾，证实了FD在现有机制下的性能局限。</td></tr>
<tr><td>2026-05-21</td><td>Superhuman Safe and Agile Racing through Multi-Agent Reinforcement Learning<br><a href='http://arxiv.org/pdf/2605.22748'>论文</a></td><td>本文提出利用多智能体强化学习为真实世界动态交互提供安全保障，打破了传统单智能体范式忽视其他参与者的局限。
◆提出基于联赛的自博弈训练方法，使智能体在高速四旋翼竞速中进化出主动避撞、超车与处理气动下洗等复杂</td></tr>
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
<tr><td>2026-05-25</td><td>G-DRAGON: Geospatial Reasoning and Dynamic Planning for Retrieval-Augmented Outdoor Navigation<br><a href='http://arxiv.org/pdf/2605.25646'>论文</a></td><td>该论文提出了G-DRAGON框架，解决了户外导航中长距离全局规划与最后一步精细探索的挑战。
◆基于轻量级大模型的生成式检索方法，将自然语言指令映射到本地OSM实体以获取准确坐标，有效缓解了云端大模型的幻觉问题。
◆高级规划模块将全局拓扑路线与SLAM系统结合，把地理空间航点投影到机器人可导航坐标系，实现全局到局部的桥接。
◆针对最后一步探索，框架无缝切换至基于边界的探索与开放集语义体素建图，精准定位开放词汇目标。
实验表明该框架性能超越现有基线，并在真实世界无人车上成功完成长达500米的行人搜索任务。</td></tr>
<tr><td>2026-05-24</td><td>GreenSeg: Ground Segmentation Algorithm for Agricultural Robots in Mediterranean Greenhouses using RGB-D Point Clouds<br><a href='http://arxiv.org/pdf/2605.25279'>论文</a></td><td>针对地中海温室狭窄通道、地形混杂以及聚乙烯覆盖物导致深度传感器产生严重光学干扰和鬼点的问题，本文提出了基于RGB-D点云的低成本自主导航感知框架GreenSeg。
◆提出双层验证策略，结合鲁棒的全局平面拟合与表面曲率滤波器，以适应异构地形。
◆引入基于种子点的区域生长约束，确保可通行平面的空间连续性。
实验在AGRICOBIOT I平台上跨越四个不同太阳高度角的场景进行了验证。
结果表明，GreenSeg显著优于基准方法，在走廊尽头的关键旋转机动中平均召回率和平均交并比分别最高提升了11.58%和19.24%。
该算法有效解决了传统3D LiDAR成本过高的问题，在预算受限且光照敏感的非结构化农业环境中实现了稳定安全的自主导航。</td></tr>
<tr><td>2026-05-24</td><td>Micro-Swarm Locomotion Optimization in Dynamic Flow using Multi-Objective Multi-Agent Reinforcement Learning<br><a href='http://arxiv.org/pdf/2605.25025'>论文</a></td><td>本文提出一种混合计算流体动力学与多目标多智能体强化学习框架，解决了动态生理流体环境中微型机器人集群的协调控制难题。该框架将高保真Navier-Stokes求解器与去中心化强化学习直接耦合，在脉动流中同时优化上游前进、能量效率和运动平滑度。
◆首创CFD与MOMARL直接耦合架构，将时变流体与智能体交互纳入学习循环，为微集群控制提供物理基础范式。
◆证实PCGrad梯度冲突解决是多目标优化的结构必需而非可选优化，成功平衡多目标并使性能远超基线。
◆发现三种涌现的集群物理机制：抑制顺流的双层节流编队、利用逆流的周期同步棘轮机制与个性化的最终逼近。</td></tr>
<tr><td>2026-05-24</td><td>Performance Comparison of Classical and Neural Sampling Algorithms for Robotic Navigation<br><a href='http://arxiv.org/pdf/2605.25010'>论文</a></td><td>本文在包含不同密度凸凹障碍物的环境中，实现并对比评估了RRT*、Neural RRT*和Neural Informed RRT*三种运动规划算法。
研究证实，将人工智能集成到基于采样的规划中，能有效提升自主导航的路径质量。
◆神经引导的规划器显著提升了路径质量，与传统RRT*相比，路径长度最多缩短14%，轨迹平滑度提升55%至75%。
◆Neural Informed RRT*算法在路径长度和轨迹平滑度两项指标上均取得了最佳的总体表现。
◆验证了AI引导的采样策略在提升机器人与无人机导航可靠性和轨迹效率方面的有效性，尽管会带来轻微的计算时间增加。</td></tr>
<tr><td>2026-05-24</td><td>Convex-Neural RRT*: Fast and Reliable Learning-Guided Sampling for High-Quality Robot Path Planning<br><a href='http://arxiv.org/pdf/2605.25006'>论文</a></td><td>针对基于采样的机器人路径规划算法获取高质量解所需迭代次数多的问题，本文提出了融合神经引导的增强型RRT*变体算法Convex-Neural RRT*。
◆引入神经引导机制预测高质量路径附近的信息丰富的路径点区域。
◆从预测结果中提取凸候选区域，使规划器集中探索几何相关区域，同时保留全局探索能力。
实验表明，该算法相较于其他神经引导变体计算时间减少30%至75%，相较于LTA*计算时间减少高达98%，且比经典RRT*路径长度平均缩短约5%。
该方法在不同障碍物密度下均保持99%以上的</td></tr>
<tr><td>2026-05-23</td><td>Vision-Guided Outdoor Flight and Obstacle Evasion via Reinforcement Learning<br><a href='http://arxiv.org/pdf/2605.24449'>论文</a></td><td>本文提出了一种新型感知运动策略，解决了四旋翼在无GNSS和遥测信号场景下的自主导航与避障问题。
◆设计了预训练自编码器感知头结合规划控制LSTM网络的新架构，可直接输出适配商业无人机的速度指令。
◆引入两阶段强化与特权学习训练范式，先利用全局规划器最优轨迹作为监督骨干进行初始训练，再通过课程学习微调。
◆结合域随机化与奖励整形技术缩小仿真到现实差距，提升了策略对噪声和域偏移的鲁棒性。
该方法在户外实验中成功实现了向未见障碍环境和无人机平台的零样本迁移。</td></tr>
<tr><td>2026-05-22</td><td>MASt3R-Nav: WayPixel Navigation in Relative 3D Maps<br><a href='http://arxiv.org/pdf/2605.24111'>论文</a></td><td>本文提出一种新型地图表示方法，解决了传统3D地图需全局一致性而拓扑图缺乏几何理解导致导航能力受限的问题。
◆提出像素相对连接性地图表示，基于图像对相对3D坐标系中的像素对应关系构建图像间连接性，在保证几何准确性的同时无需全局一致性。
◆通过近似和稀疏化图像内像素连接性执行全局路径规划，推导出航点像素代价图。
◆训练以密集像素级代价图为条件的控制器来预测轨迹展开，证明基于相对几何的像素级代价图比图像或对象级条件更精确。
该导航系统在四种仿真任务和真实世界演示中均得到验证，展现出卓越的导航能力。</td></tr>
<tr><td>2026-05-19</td><td>KappaPlace: Learning Hyperspherical Uncertainty for Visual Place Recognition via Prototype-Anchored Supervision<br><a href='http://arxiv.org/pdf/2605.19435'>论文</a> | <a href='https://github.com/mayayank95/UncertaintyAwareVPR'>代码</a></td><td>针对现有视觉位置识别方法缺乏校准的不确定性估计这一问题，本文提出了KappaPlace框架以学习不确定性感知的表征。
◆提出原型锚定监督策略，利用潜在类别代表作为概率优化目标的锚点。
◆将图像描述子建模为von Mises-Fisher变量，通过轻量级模块预测浓度参数作为偶然不确定性的直接代理。
◆推导出新颖的匹配级公式，突破了现有方法仅限查询视角的局限，能够量化特定查询与参考图对的匹配可靠性。
该方法提供联合训练与后训练扩展两种模式，在五个基准上将期望校准误差降低高达百分之五十，同时保持或提升检索召回率。
实验证明该框架为位置识别流程提供了鲁棒且校准良好的信号，保障了安全关键应用中的可靠决策。</td></tr>
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
<tr><td>2026-05-25</td><td>Collaborative Threat-Aware Autonomy (CTAA)<br><a href='http://arxiv.org/pdf/2605.25741'>论文</a></td><td>本文提出了协同威胁感知自主性框架，解决了无人车队在动态对抗武器交战区中单车易成单点故障的挑战。该框架的核心贡献是构建了角色分化的多智能体协同轨迹规划机制。在此机制下，车队被分配为主拦截、护航和诱饵等不同角色，从而提升团队任务成功率并管控个体威胁暴露。
◆提出角色分配与空间路线分离机制，产生概率冗余与威胁饱和两种互补效应，即多独立路径提高团队成功率，低优先级角色吸引敌方火力保障主车辆通行。
◆设计了基于碰撞球边界逃避者零集的反应式制导律，该制导律考虑了最小转弯半径带来的追击者机动性约束，引导车辆驶向兼顾最安全与目标导向的航向。</td></tr>
<tr><td>2026-05-24</td><td>Performance Comparison of Classical and Neural Sampling Algorithms for Robotic Navigation<br><a href='http://arxiv.org/pdf/2605.25010'>论文</a></td><td>本文核心贡献是在包含不同密度和形状障碍物的环境中，系统比较了经典RRT*与两种神经采样算法在机器人导航中的性能表现。
◆验证了神经引导规划器能显著提升路径质量，使路径长度缩短达14%，轨迹平滑度提升55%至75%。
◆明确了Neural Informed RRT*算法在路径长度和平滑度上取得了最佳的综合性能。
◆证明了AI引导采样策略在计算时间略增的情况下，仍能有效提升机器人与无人机导航的可靠性和轨迹效率。
◆突出了人工智能在实时机器人路径规划应用中日益增长的重要性与潜力。</td></tr>
<tr><td>2026-05-24</td><td>Convex-Neural RRT*: Fast and Reliable Learning-Guided Sampling for High-Quality Robot Path Planning<br><a href='http://arxiv.org/pdf/2605.25006'>论文</a></td><td>本文提出Convex-Neural RRT*算法，通过引入神经引导预测高质量路径附近的信息丰富航点区域，解决了传统采样算法迭代次数多的问题。
◆创新性地从神经预测结果中提取凸候选区域，使规划器将探索聚焦于几何相关的区域。
◆在集中局部探索的同时保留了全局探索能力，实现了计算效率与解质量的有效平衡。
实验证实，相比其他神经引导变体和LTA*算法，该算法的计算时间分别大幅减少30-75%和88-98%。
同时，其路径长度比经典RRT*平均缩短约5%，在复杂环境中改善更显著，且整体成功率保持在99%以上。
这表明凸引导神经采样机制非常适合时间敏感的机器人导航任务。</td></tr>
<tr><td>2026-05-23</td><td>SparseWorld: Enhancing End-to-End Autonomous Driving via World Models with Sparse Scene Representation<br><a href='http://arxiv.org/pdf/2605.24354'>论文</a> | <a href='https://wryzju.github.io/SparseWorld/'>代码</a></td><td>本文提出了SparseWorld，一个轻量级的自动驾驶世界模型，通过稀疏场景表示仅预测关键场景布局，解决了现有稠密表示计算成本高和信息冗余的问题。
◆提出Sparse Dreamer模块，通过联合时间与空间注意力机制在潜空间中预测未来实例。
◆采用自回归展开方式预测未来地图元素和周围智能体，使模型学习驾驶场景的时间演变规律。
◆使运动规划器与预测的未来实例进行交互，从而捕捉更准确的运动模式并生成更具安全意识的轨迹。
实验表明，该方法大幅降低了碰撞风险，在nuScenes开环规划中达到0.05%碰撞率的领先水平，并在Bench2Drive闭环基准上显著超越基线方法。</td></tr>
<tr><td>2026-05-25</td><td>Fast-dDrive: Efficient Block-Diffusion VLM for Autonomous Driving<br><a href='http://arxiv.org/pdf/2605.23163'>论文</a></td><td>本文提出Fast-dDrive模型，这是一种用于自动驾驶的块扩散视觉语言动作模型，通过在语义单元内</td></tr>
<tr><td>2026-05-20</td><td>Benchmarking Empirical and Learning-Based Approaches for Feedforward Steering Control in Autonomous Racing<br><a href='http://arxiv.org/pdf/2605.21111'>论文</a> | <a href='https://github.com/TUMRT/steering_ff_control'>代码</a></td><td>本文系统性地基准测试了两种基于学习和两种基于经验的前馈转向控制器，以评估其在自动驾驶赛车中减少反馈转向修正的能力。研究在基于真实阿布扎比自动驾驶赛车联赛的高保真双轨车辆动力学模拟器中，对这些控制器进行了开环与闭环测试。
◆提出了一种基于多项式曲面拟合的新型EHD公式，该公式能以最少的参数化捕捉依赖速度的非线性转向行为。
◆揭示了学习型控制器在开环评估中虽预测误差最低，但此优势无法转化为闭环路径跟踪性能或圈速的提升。
◆提出的新型EHD方法取得了最佳的闭环鲁棒性和圈速，突显了必须在完整的轨迹规划与控制软件栈中评估前馈策略的必要性。</td></tr>
<tr><td>2026-05-20</td><td>SubTGraph: Large-Scale Subterranean Environment Synthesis with Controllable Topological Variability for Robotic Autonomy Validation<br><a href='http://arxiv.org/pdf/2605.20917'>论文</a> | <a href='https://github.com/LTU-RAI/SubTGraph.git'>代码</a></td><td>本文提出了SubTGraph框架，填补了地下环境缺乏大规模仿真基准以进行机器人自主性严格统计评估的空白。◆创新性地基于用户结构约束构建代价矩阵，结合Dijkstra算法与拓扑度量瓦片程序化生成多层次地下环境。◆支持高变异性与可控参数合成，用户可根据拓扑、维度和纹理等规范生成矿井、自然洞穴和熔岩管道等不同场景。◆通过语义分割真值验证、多智能体路径规划趋势识别和LIO SLAM极限压力测试三个案例，全面验证了框架对自主栈各层级的评估能力。◆开源了环境生成代码库并发布了包含150个高变异性地下世界的数据库，为该领域提供了关键的基准测试资源。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>4708</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4098</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2405</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1605</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1594</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1405</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1248</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1223</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>915</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>914</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>893</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>790</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>781</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>737</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>722</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>699</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>629</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>622</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>617</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>583</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>561</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>549</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>530</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>498</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>463</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>431</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>388</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>342</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>336</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>261</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>252</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>233</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>221</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>208</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>197</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>194</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>148</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2841</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1628</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1352</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1096</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1035</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>868</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>696</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>654</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>653</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>618</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>582</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>572</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>563</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>559</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>549</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>513</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>479</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>462</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>440</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>439</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>335</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>311</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>299</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>281</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
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
> 更新于: 2026.05.26
