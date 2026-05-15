# 计算机视觉领域最新论文 (2026.05.15)

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
<tr><td>2026-05-13</td><td>LEXI-SG: Monocular 3D Scene Graph Mapping with Room-Guided Feed-Forward Reconstruction<br><a href='http://arxiv.org/pdf/2605.13741'>论文</a> | <a href='https://ori-drs.github.io/lexisg-web/'>代码</a></td><td>LEXI‑SG 首次实现仅使用单目RGB相机的开放式词汇三维场景图稠密映射。  
◆ 通过开放式词汇基础模型将场景先划分为房间，在完整观测到房间后才进行前馈重建，避免了滑动窗口导致的比例不一致。  
◆ 提出基于房间的因子图框架，在全局对齐房间重建的同时保持局部地图一致并自然约束语义层次结构。  
◆ 在每个房间内部支持开放式词汇的物体分割与跟踪，实现细粒度目标层级的场景图。  
◆ 在 Habitat‑Matterport 3D 数据集和自采集的办公室序列上验证，显著提升轨迹估计和稠密重建质量，且在开放式词汇分割任务上表现具有竞争力。</td></tr>
<tr><td>2026-05-12</td><td>WildPose: A Unified Framework for Robust Pose Estimation in the Wild<br><a href='http://arxiv.org/pdf/2605.12774'>论文</a></td><td>◆ 提出WildPose，一个统一的单目姿态估计框架，同时兼顾动态环境和静态/低自运动场景。  
◆ 将前馈模型的丰富感知前端与可微分束束调整（BA）的端到端优化相结合，构建3D感知更新算子。  
◆ 基于冻结的MASt3R特征骨干网络提取多层次3D感知特征，实现高容量运动掩码检测器。  
◆ 在动态（Wild‑SLAM、Bonn）、静态（TUM、7‑Scenes）和低自运动（Sintel）基准上均取得领先性能。  
◆ 通过统一框架实现鲁棒性与精度的双重提升，兼容现有SLAM/SfM系统。</td></tr>
<tr><td>2026-05-11</td><td>MAGS-SLAM: Monocular Multi-Agent Gaussian Splatting SLAM for Geometrically and Photometrically Consistent Reconstruction<br><a href='http://arxiv.org/pdf/2605.10760'>论文</a></td><td>MAGS‑SLAM是首个仅使用RGB图像实现多智能体协同3DGS SLAM的框架，可在无深度传感器的情况下完成高精度几何与外观重建。  
◆ 采用轻量级子地图压缩通信，仅传输子地图摘要，显著降低带宽需求。  
◆ 引入几何‑外观感知的闭环验证机制，提升多智能体间的尺度与位姿对齐鲁棒性。  
◆ 设计占用感知的Gaussian融合策略，实现全局一致的稠密重建而不依赖深度测量。  
◆ 提出ReplicaMultiagent Plus基准，支持对协同Gaussian SLAM的跟踪精度与渲染质量进行系统评估。</td></tr>
<tr><td>2026-05-10</td><td>Above and Below: Heterogeneous Multi-robot SLAM Across Surface and Underwater Domains<br><a href='http://arxiv.org/pdf/2605.09811'>论文</a></td><td>◆ Multi-robot simultaneous localization and mapping (SLAM) is a fundamental task in multi-robot operations.
◆ Robots must have a common understanding of their location and that of their team members to complete coordinated actions.
◆ However, multi-robot SLAM between Uncrewed Surface Vessels (USVs) and Autonomous Underwater Vehicles (AUVs) has primarily been achieved through acoustic pinging between robots to retrieve range measurements; a measurement technique requires that robots to be in similar locations simultaneously, have an uninterrupted path for signal propagation, and may necessitate synchronized clocks.</td></tr>
<tr><td>2026-05-08</td><td>AERO-VIS: Asynchronous Event-based Real-time Onboard Visual-Inertial SLAM<br><a href='http://arxiv.org/pdf/2605.07885'>论文</a> | <a href='https://ethz-mrl.github.io/AERO-VIS'>代码</a></td><td>◆ The robustness of event cameras to high dynamic range and motion blur holds the potential to improve visual odometry systems in challenging environments.
◆ Although their high temporal resolution does not require synchronous processing, most event-based odometry methods still run at fixed rates, which simplifies system design but restricts latency and throughput.
◆ In this work, we present AERO-VIS, a stereo event-inertial SLAM system with an integrated, data-driven, robust, and performance-optimized keypoint detector.</td></tr>
<tr><td>2026-05-07</td><td>GA3T: A Ground-Aerial Terrain Traversability Dataset for Heterogeneous Robot Teams in Unstructured Environments<br><a href='http://arxiv.org/pdf/2605.06478'>论文</a></td><td>◆ Heterogeneous air-ground robot teams combine complementary sensing modalities, mobility characteristics, and spatial viewpoints that can significantly enhance perception in complex outdoor environments.
◆ However, progress in multi-robot collaborative perception has been constrained by the lack of real-world datasets featuring overlapping multi-modal observations from platforms operating in unstructured terrain.
◆ We present GA3T (Ground-Aerial Team for Terrain Traversal), a real-world multi-robot collaborative perception dataset collected using a Clearpath Husky UGV and an Autel EVO~II UAV across diverse unstructured environments, including forest trails, rocky paths, muddy terrain, snow piles, and grass-covered fields.</td></tr>
<tr><td>2026-05-07</td><td>Indoor 60 GHz Radio Channel Dataset Enabling Digital Twin Construction<br><a href='http://arxiv.org/pdf/2605.05824'>论文</a></td><td>◆ The ambitious performance targets of modern wireless networks, including 6G and Industrial IoT (IIoT) systems, necessitate advanced hardware platforms utilizing millimeter-wave (mmWave) technology.
◆ High-frequency signals provide the bandwidth and low latency required for these systems, but rely on beamforming to overcome path loss and exploit channel sparsity.
◆ This kind of architecture provides all the specifications needed to build a SLAM (Simultaneous Localization and Mapping) system.</td></tr>
<tr><td>2026-05-08</td><td>SLAM: Structural Linguistic Activation Marking for Language Models<br><a href='http://arxiv.org/pdf/2605.05443'>论文</a></td><td>◆ LLM watermarks must be detectable without compromising text quality, yet most existing schemes bias the next-token distribution and pay for detection with measurable quality loss.
◆ We present SLAM (Structural Linguistic Activation Marking), a novel white-box watermarking scheme that sidesteps this cost by writing the mark into structural geometry rather than token frequencies: sparse autoencoders identify residual-stream directions encoding linguistic structure (e.g., voice, tense, clause order), and we causally steer those directions at generation time, leaving lexical sampling and semantics unconstrained.
◆ On Gemma-2 2B and 9B, SLAM achieves 100% detection accuracy with a quality cost of only 1-2 reward points - compared to 7.5-11.5 for KGW, EWD, and Unigram - with naturalness and diversity preserved at near-unwatermarked levels across both models.</td></tr>
<tr><td>2026-05-06</td><td>Dr-PoGO: Direct Radar Pose-Graph Optimization<br><a href='http://arxiv.org/pdf/2605.04806'>论文</a> | <a href='https://github.com/utiasASRL/dr_pogo'>代码</a></td><td>◆ This paper introduces Dr-PoGO, a method for Simultaneous Localization And Mapping (SLAM) using a 2D spinning radar.
◆ Unlike cameras or lidars that require line-of-sight, millimetre-wave radars can `see&#x27; through dust, falling snow, rain, etc.
◆ Accordingly, it is a great modality for robust perception regardless of the weather conditions.</td></tr>
<tr><td>2026-05-07</td><td>Hardware-Aware Neural Feature Extraction for Resource-Constrained Devices<br><a href='http://arxiv.org/pdf/2605.04282'>论文</a></td><td>◆ Visual SLAM is a core component of spatial computing systems, yet deploying learned local feature extractors on microcontroller-class hardware remains challenging due to memory, bandwidth, and quantization constraints.
◆ While modern neural descriptors provide strong robustness, their practical adoption is often hindered by system-level bottlenecks that are not captured by FLOP-based efficiency metrics.
◆ In this work, we introduce Gideon, a hardware-aware neural feature extractor explicitly designed for resource-constrained devices.</td></tr>
</tbody>
</table>
</div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-14</td><td>Efficient Dense Matching for Enhanced Gaussian Splatting Using AV1 Motion Vectors<br><a href='http://arxiv.org/pdf/2605.14629'>论文</a></td><td>本文提出利用AV1运动矢量实现高效密集匹配，以改进3D Gaussian Splatting的初始化。核心思路是通过视频解码器的运动矢量直接获取像素对应关系，避免传统SfM的高成本特征提取与匹配。通过该方法生成的点云比COLMAP稀疏点云多约八倍，有效提升了后续重建的细节与收敛速度。实验结果显示，在保持视觉质量的前提下，VMAF提升约9点，训练时间平均下降63%。整体流程实现了实时性的大幅提升，兼顾精度和效率。

◆ 基于AV1运动矢量的密集特征匹配，显著降低计算开销  
◆ 生成比传统SfM更密集的点云，达到约8倍点数提升  
◆ 将密集点云直接用于3DGS初始化，实现收敛速度提升63%  
◆ 在保持质量的同时，VMAF提升约9点，验证了方法有效性</td></tr>
<tr><td>2026-05-12</td><td>WildPose: A Unified Framework for Robust Pose Estimation in the Wild<br><a href='http://arxiv.org/pdf/2605.12774'>论文</a></td><td>WildPose针对动态环境下的单目姿态估计难题，提出统一框架，将前馈感知与可微分捆绑调整的端到端优化相结合，兼顾鲁棒性与高精度。 
◆基于冻结的MASt3R预训练特征构建3D感知的更新算子，实现前馈感知层与端到端优化的深度耦合。 
◆利用多层次3D感知特征驱动高容量运动掩码检测，精准分割并抑制动态物体对姿态估计的干扰。 
◆在保持对静态和低自运动场景最优性能的同时，显著提升动态场景（如Wild‑SLAM、Bonn）的姿态估计精度。 
实验在Wild‑SLAM、Bonn、TUM、7‑Scenes和Sintel等基准上验证，WildPose始终超越现有方法，展示了统一框架的广泛适用性。</td></tr>
<tr><td>2026-05-12</td><td>3D Gaussian Splatting for Efficient Retrospective Dynamic Scene Novel View Synthesis with a Standardized Benchmark<br><a href='http://arxiv.org/pdf/2605.12437'>论文</a></td><td>◆提出在同步多视角体育场景中，利用3DGS直接进行回顾性新视角合成，无需显式的时间耦合约束。  
◆通过在首帧使用结构‑from‑运动（SfM）点云初始化，随后在时间轴上直接传播优化的高斯基元，实现高效的动态场景建模。  
◆发布基于Blender的动态多视角（Dynamic MV）数据集框架，提供同步相机姿态、标准化坐标及可直接导入的训练数据，显著提升实验可重复性。  
◆构建包含多种运动模式的动态基准套件，并在同一环境下系统评测NeRF与3DGS等代表性方法，验证同步多视角约束的有效性。  
◆实验表明，在同步多视角设置下，3DGS即可实现高质量回顾性动态场景新视角合成，且无需复杂的多体时序约束，显著提升渲染效率。</td></tr>
<tr><td>2026-05-12</td><td>Compositional Neural Operators for Multi-Dimensional Fluid Dynamics<br><a href='http://arxiv.org/pdf/2605.11691'>论文</a></td><td>◆ 提出Compositional Neural Operators (CompNO)框架，将二维PDE系统分解为可组合的基础块，实现模块化求解。  
◆ 基础块覆盖对流、扩散、非线性对流和泊松求解等基本物理单元，并通过预训练捕获单元级动力学。  
◆ 引入适配块（Adaptation Block）与聚合器（Aggregator），以数据损失和物理残差联合优化，学习块间的非线性交互。  
◆ 在对流‑扩散、Burgers及不可压缩Navier‑Stokes方程上验证，表明基于元素算子学习显著提升泛化性和计算效率。  
◆ 框架支持预训练块的跨任务复用，增强模型可解释性并降低针对新系统的训练成本。</td></tr>
<tr><td>2026-05-11</td><td>3DReflecNet: A Large-Scale Dataset for 3D Reconstruction of Reflective, Transparent, and Low-Texture Objects<br><a href='http://arxiv.org/pdf/2605.10204'>论文</a></td><td>◆ Accurate 3D reconstruction of objects with reflective, transparent, or low-texture surfaces still remains notoriously challenging.
◆ Such materials often violate key assumptions in multi-view reconstruction pipelines, such as photometric consistency and the availability on distinct geometric texture cues.
◆ Existing datasets primarily focus on diffuse, textured objects, and therefore provide limited insight into performance under real-world material complexities.</td></tr>
<tr><td>2026-05-11</td><td>BathyFacto: Refraction-Aware Two-Media Neural Radiance Fields for Bathymetry<br><a href='http://arxiv.org/pdf/2605.10174'>论文</a></td><td>◆ Through-water photogrammetry based on UAV imagery enables shallow-water bathymetry, but refraction at the air-water interface violates the straight-ray assumption of Structure-from-Motion and causes systematic depth bias.
◆ We present BathyFacto, a refraction-aware two-media extension of Nerfacto integrated into Nerfstudio that targets metrically precise underwater point clouds.
◆ BathyFacto uses a shared hash-grid-based density field with a medium-conditioned color head that receives a one-bit medium flag (air or water) and traces each camera ray as two segments: a straight segment in air up to a planar water surface and a refracted segment in water computed via Snell&#x27;s law with known refractive indices.</td></tr>
<tr><td>2026-05-08</td><td>TriP: A Triangle Puzzle Approach to Robust Translation Averaging<br><a href='http://arxiv.org/pdf/2605.07143'>论文</a></td><td>◆ Translation averaging aims to recover camera locations from pairwise relative translation directions and is a fundamental component of global Structure-from-Motion pipelines.
◆ The problem is challenging because direction measurements contain no distance information, making the estimation problem highly ill-conditioned and highly sensitive to corrupted observations.
◆ In this paper, we propose TriP, a triangle-based framework for robust translation averaging.</td></tr>
<tr><td>2026-05-07</td><td>TriDE: Triangle-Consistent Translation Directions for Global Camera Pose Estimation<br><a href='http://arxiv.org/pdf/2605.06889'>论文</a></td><td>◆ Pairwise translation directions are a key input to camera location estimation in global structure-from-motion.
◆ Existing estimators usually process each image pair independently, producing directions that may be locally plausible but inconsistent with the other relative directions in the viewing graph.
◆ To jointly estimate the direction, we propose TriDE, which exploits camera-triangle consistency as an efficient higher-order verification signal.</td></tr>
<tr><td>2026-05-06</td><td>egenioussBench: A New Dataset for Geospatial Visual Localisation<br><a href='http://arxiv.org/pdf/2605.05351'>论文</a> | <a href='https://github.com/fratopa/egenioussBench'>代码</a></td><td>◆ We present egenioussBench, a visual localisation benchmark built on geospatial reference data: a city-scale airborne 3D mesh and a CityGML LoD2 model.
◆ This pairing reflects deployable mapping assets and supports true scalability beyond traditional SfM-based approaches.
◆ The query data comprise smartphone images with centimetre-accurate, map-independent ground truth obtained via PPK and GCP/CP-aided adjustment.</td></tr>
<tr><td>2026-05-03</td><td>DP-SfM: Dual-Pixel Structure-from-Motion without Scale Ambiguity<br><a href='http://arxiv.org/pdf/2605.01852'>论文</a> | <a href='https://github.com/lilika-makabe/dp-sfm-tpami.git'>代码</a></td><td>◆ Multi-view 3D reconstruction, namely, structure-from-motion followed by multi-view stereo, is a fundamental component of 3D computer vision.
◆ In general, multi-view 3D reconstruction suffers from an unknown scale ambiguity unless a reference object of known size is present in the scene.
◆ In this article, we show that multi-view images captured using a dual-pixel (DP) sensor can automatically resolve the scale ambiguity, without requiring a reference object or prior calibration.</td></tr>
</tbody>
</table>
</div>

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

<h2 id='obstacle-avoidance'>Obstacle Avoidance</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-14</td><td>CaMeRL: Collision-Aware and Memory-Enhanced Reinforcement Learning for UAV Navigation in Multi-Scale Obstacle Environments<br><a href='http://arxiv.org/pdf/2605.14810'>论文</a></td><td>本文针对无人机在多尺度障碍环境中的避障导航问题，提出 CaMeRL 框架。CaMeRL 通过冲突感知的潜在表示对细粒度障碍结构进行编码，显著提升对小障碍的感知能力。◆ 冲突感知潜在表示：利用风险敏感的深度线索保留细粒度障碍信息，增强对小障碍的敏感度。◆ 时间记忆模块：跨帧融合观测信息，缓解大障碍遮挡导致的局部可观测性缺失。实验结果表明，CaMeRL 在极小和极大障碍场景下成功率分别提升 0.48 与 0.28，并在复杂户外环境中实现可靠导航。</td></tr>
<tr><td>2026-05-14</td><td>SR-Platform: An Agentic Pipeline for Natural Language-Driven Robot Simulation Environment Synthesis<br><a href='http://arxiv.org/pdf/2605.14700'>论文</a></td><td>◆ SR-Platform 是一个生产级代理系统，将自然语言描述直接转化为可执行的 MuJoCo 仿真场景。  
◆ LLM 编排器把用户意图解析为结构化场景计划，并调度资产检索或 CadQuery 生成流程。  
◆ 资产铸造模块支持缓存的 3D 资产快速复用，同时通过 LLM→CadQuery 合成新几何体，降低首次尝试失败率至 11.3%。  
◆ 布局建筑师负责对象位姿分配并自动验证工业约束，确保物理有效性和碰撞避免。  
◆ 桥接层将资产、布局与机器人模型组装为完整 MJCF 文件，实现一次性可执行仿真；系统以九服务 Docker 栈部署，提供 WebSocket 进度流、MinIO、Qdrant、Redis、InfluxDB 等组件，实现缓存加速（30‑40 s）和约 50 s 端到端延迟。</td></tr>
<tr><td>2026-05-14</td><td>Capacity Characterization and Formation Optimization for Multi-User MIMO Communications with UAV Swarm<br><a href='http://arxiv.org/pdf/2605.14298'>论文</a></td><td>◆本文针对可控制位置的无人航空机群（UAV）作为用户的多用户MIMO系统，首次推导了闭式求和容量表达式，揭示了协同移动带来的额外自由度。  
◆对于配备M元素均匀线性阵列（ULA）的基站，实现了完整的空间复用增益M与波束形成增益M的同步获取；对于配备均匀平面阵列（UPA）的基站，理论上可容纳约πM/4个用户同时获得全波束形成增益M。  
◆为最大化逐次干扰抵消（SIC）下的总容量和把干扰视为噪声（TIN）下的总速率，提出了考虑碰撞避免和编队凝聚约束的UAV编队优化框架。  
◆通过利用阵列响应向量随UAV方向的流形结构，将非凸编队优化问题转化为流形优化问题，并设计了高效迭代算法。  
◆大规模仿真验证了该算法在各种天线配置下均能达到接近理论最优的容量和速率性能。</td></tr>
<tr><td>2026-05-14</td><td>Reactive Planning based Control for Mobile Robots in Obstacle-Cluttered Environments<br><a href='http://arxiv.org/pdf/2605.14232'>论文</a></td><td>本文针对仅有局部环境信息的移动机器人在障碍物密集场景下的运动控制问题，提出一种反应式规划控制策略（RPCS）。该策略首先生成一条连接起点和目标的参考轨迹，然后利用反应式规划策略（RPS）对轨迹进行实时局部修正，以实现安全避障。为实现精准跟踪，进一步设计了基于离散化技术的自适应跟踪控制策略（ATCS），能够在轨迹被修改后快速响应并保持跟踪精度。最终，将RPS与ATCS结合形成完整的RPCS，并通过数值仿真验证其在复杂环境中的有效性和优势。

◆ 结合参考轨迹生成与局部反应式规划的统一控制框架
◆ 基于部分环境信息的实时局部轨迹修改的反应式规划策略（RPS）
◆ 采用离散化技术的自适应跟踪控制策略（ATCS），保证对修改后轨迹的精准跟踪
◆ 将RPS和ATCS深度集成，实现端到端的避障与轨迹跟踪协同控制
◆ 通过数值仿真验证了所提方法在障碍物密集环境中的鲁棒性和实时性</td></tr>
<tr><td>2026-05-13</td><td>Motion Planning for Autonomous Vehicles using Optimization over Graphs of Convex Sets<br><a href='http://arxiv.org/pdf/2605.14199'>论文</a></td><td>本文提出一种基于图凸集（GCS）优化的自动驾驶车辆运动规划方法，能够在复杂环境中生成无碰撞、动态可行的轨迹。  
◆通过将自由空间划分为有限凸区域并组织为有向图，将非凸几何离散连通决策与凸轨迹约束统一在同一优化框架中。  
◆采用Bézier曲线描述空间路径并结合多项式时间尺度函数，实现轨迹的凸参数化并便于求解。  
◆在简化的小滑移线性轮胎假设下，使用自行车模型将动力学约束转化为凸约束，确保动态可行性。  
◆在CommonRoad标准场景中进行验证，实验表明该方法在保持与非线性最优控制相近轨迹质量的同时，计算效率提升且对初始化的敏感度显著降低。</td></tr>
<tr><td>2026-05-13</td><td>TinySDP: Real Time Semidefinite Optimization for Certifiable and Agile Edge Robotics<br><a href='http://arxiv.org/pdf/2605.13748'>论文</a></td><td>针对现有半定规划求解器计算成本过高、难以在资源受限嵌入式系统上运行的问题，本文提出了首个专为嵌入式系统设计的半定规划求解器TinySDP，实现了非凸障碍物约束下的实时模型预测控制。
◆将半正定锥投影集成到基于缓存Riccati的ADMM求解器中，利用计算结构提升了嵌入式设备上的求解可行性。
◆结合事后秩1证明方法，在每个时间步将松弛解转换为显式的几何保证，从而提供运动规划的安全性认证。
在死胡同和动态避障等容易导致局部方法失效的挑战性场景中，TinySDP实现了无碰撞导航，且路径比最先进基线缩短达73%。
在Crazyflie四旋翼飞行器上的实验验证了该求解器能以实时速率执行半定约束，满足敏捷边缘机器人的控制需求。</td></tr>
<tr><td>2026-05-13</td><td>Uncertainty-Aware 3D Position Refinement for Multi-UAV Systems<br><a href='http://arxiv.org/pdf/2605.13500'>论文</a></td><td>◆ 提出一种去中心化的轻量级3D位置细化层，融合本机估计与邻居共享的状态摘要及距离约束，提升多无人机系统的鲁棒定位。  
◆ 采用不确定性感知融合，根据协方差、链路质量和学习信任分数为每个邻居分配权重，实现精准的信息聚合。  
◆ 设计弱先验膨胀或替换机制，使系统在冷启动或临时定位失效时能够通过可信的邻居约束快速恢复稳定估计。  
◆ 引入时间平滑的范围一致性检验，动态下权重或排除报告位置与实测距离不符的故障/恶意节点，增强安全性。  
◆ 在10机3D仿真中验证，所提方法在冷启动阶段显著降低平均定位误差，并在恶意节点比例增加时保持误差低于传统融合方案。</td></tr>
<tr><td>2026-05-13</td><td>HCSG: Human-Centric Semantic-Geometric Reasoning for Vision-Language Navigation<br><a href='http://arxiv.org/pdf/2605.13321'>论文</a> | <a href='https://haoxuanxu1024.github.io/HCSG/'>代码</a></td><td>本文提出 HCSG，首个面向视觉‑语言导航的人类中心框架，旨在动态室内环境中实现安全、社交智能的导航。  
◆ 统一的人类理解模块融合几何预测与基于视觉‑语言模型的语义解释。  
◆ 将语义‑几何融合表示嵌入拓扑地图，实现指令条件的规划。  
◆ 引入社交距离损失约束，确保交互距离符合社会规范。  
◆ 在 HA‑VLNCE 基准上实现成功率提升 14%、碰撞率降低 34% 的显著改进。</td></tr>
<tr><td>2026-05-13</td><td>Conveyor Parcel Routing with Order-Contiguous Arrivals<br><a href='http://arxiv.org/pdf/2605.13035'>论文</a></td><td>针对仓库物流中包裹路由的订单连续到达约束，该研究提出了在线多智能体路径寻找与订单连续性问题（online MAPF-OC）的形式化框架，要求同一订单的包裹在交付点必须连续到达以减少下游分拣成本。
◆首次将订单连续到达约束引入在线多智能体路径规划领域，建立了包裹作为动态出现且交付后退出的智能体模型。
◆提出双排序优先规划算法（DOPP），通过三级结构分别处理订单级到达序列搜索、智能体级优先级细化及可行解合成。
◆证明DOPP具有完整性和多项式时间复杂度，在保证完备性的同时实现高效求解。
实验表明，DOPP在实际仓库输送网络布局上具有良好的可扩展性，能够在严格时间预算内生成高质量的路由方案。</td></tr>
<tr><td>2026-05-12</td><td>Hierarchical LLM-Driven Control for HAPS-Assisted UAV Networks: Joint Optimization of Flight and Connectivity<br><a href='http://arxiv.org/pdf/2605.11509'>论文</a></td><td>◆ 提出层次化多目标部分可观测马尔可夫决策过程（H‑MO‑POMDP），将UAV运动控制与通信耦合建模。  
◆ 设计基于大语言模型的全局‑局部双层控制框架：HAPS上的LLM负责长期负载均衡和切换规划，UAV端结合慢时标LLM与强化学习实现快速运动与U2I通信。  
◆ 构建融合gym‑PyBullet‑Drones与3GPP RF/THz信道的高保真3D仿真平台，支持动态与部分可观测环境验证。  
◆ 通过数值实验证明，相比现有基线，方案提升14%交通效率、25%通信吞吐量，并降低23%碰撞率，具强切换稳定性和零样本迁移能力。  
◆ 首次在多UAV网络中实现LLM驱动的层次化控制，为未来ITNTN下的自主空中交通提供可扩展解决方案。</td></tr>
</tbody>
</table>
</div>

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-14</td><td>Chrono-Gymnasium: An Open-Source, Gymnasium-Compatible Distributed Simulation Framework<br><a href='http://arxiv.org/pdf/2605.14911'>论文</a></td><td>Chrono‑Gymnasium是一种基于Ray的分布式高保真多体动力学仿真框架，旨在缩小机器人与复杂机械系统的仿真‑现实差距。  
该框架通过大规模计算集群并行执行Project Chrono的物理模型，显著降低高保真仿真的墙钟时间。  
Chrono‑Gymnasium提供符合Gymnasium标准的接口，可直接与主流机器学习库（如Stable‑Baselines3、Ray RLlib）无缝对接。  
◆基于Ray的分布式调度实现大规模并行仿真，提升计算资源利用率。  
◆统一的Gymnasium接口内置同步与消息原语，简化分布式执行和数据交换。  
◆在自主机器人导航和行星着陆器设计参数贝叶斯优化中验证可扩展性，兼顾高精度与高效性。</td></tr>
<tr><td>2026-05-14</td><td>Towards Real-Time Autonomous Navigation: Transformer-Based Catheter Tip Tracking in Fluoroscopy<br><a href='http://arxiv.org/pdf/2605.14253'>论文</a></td><td>本文提出了一种基于透视图像的实时导管尖端追踪流程，旨在解决低对比度、噪声和器械遮挡等挑战，为基于强化学习的自主机械取栓机器人系统奠定基础。
◆设计了包含帧读取、预处理、推理和后处理的多线程追踪流程，确保了实时追踪的高效与稳定。
◆引入基于Transformer的SegFormer模型进行导管分割，其双类别追踪平均绝对误差仅4.44毫米，显著优于U-Net等模型。
◆提出了结合两步组件过滤、单像素中轴骨架化及贪心弧长路径跟随的创新后处理算法，精准提取尖端坐标。
该框架在复杂成像条件下表现稳健，在分割任务上超越当前最优结果达5%，有效推动了自主导航技术的发展。</td></tr>
<tr><td>2026-05-13</td><td>Safety-Constrained Reinforcement Learning with Post-Training Reachability Verification for Robot Navigation<br><a href='http://arxiv.org/pdf/2605.14174'>论文</a></td><td>◆ 在TD3基础上引入CVaR约束，对累计成本分布的尾部风险进行直接优化，提升策略对高危情形的敏感度。  
◆ 采用后训练的Taylor Model可达性分析，在有界观测不确定下计算动作可达集，实现可量化的安全率指标。  
◆ 通过安全率度量证实CVaR训练策略在多种导航场景中保持更大障碍物安全裕度，显著提升形式化可达性验证通过率。  
◆ 在10个导航场景和6个基准方法对比实验中取得98.3%成功率与最高安全验证率，证明平均成本指标与安全评估可出现分歧。  
◆ 将训练好的策略成功部署到真实Clearpath Jackal机器人，实现仿真到真实环境的无缝迁移。</td></tr>
<tr><td>2026-05-13</td><td>LEXI-SG: Monocular 3D Scene Graph Mapping with Room-Guided Feed-Forward Reconstruction<br><a href='http://arxiv.org/pdf/2605.13741'>论文</a> | <a href='https://ori-drs.github.io/lexisg-web/'>代码</a></td><td>近年来，场景图成为机器人导航的标准层次化表示，但多数方法依赖深度传感器。  
◆首次提出仅用单目RGB实现开放词汇密集3D场景图映射的系统LEXI‑SG。  
◆利用基础模型的语义先验将场景划分为房间，并在房间完整观测后进行前馈重建，避免滑动窗口尺度不一致。  
◆构建房间级因子图实现全局对齐，保持局部地图一致性和语义层次结构。  
◆在每个房间内支持开放词汇对象分割与跟踪，实现细粒度物体理解。  
实验在Habitat‑Matterport 3D和自采办公场景上验证，显示轨迹估计和密集重建精度提升，开放词汇分割性能具有竞争力。</td></tr>
<tr><td>2026-05-12</td><td>EvoNav: Evolutionary Reward Function Design for Robot Navigation with Large Language Models<br><a href='http://arxiv.org/pdf/2605.11859'>论文</a></td><td>EvoNav是一种利用大型语言模型进行机器人导航奖励函数进化的自动化框架。  
该方法通过LLM生成候选奖励函数，并采用进化搜索策略进行迭代优化。  
◆利用LLM生成和进化奖励函数，实现无需领域专家的自动奖励设计。  
◆提出渐进式三阶段热身‑提升评价流程（低代价代理→轻量rollout→完整策略训练），显著降低训练成本。  
◆在早期阶段通过分析规则和小数据集快速筛选有效候选，提升搜索效率。  
实验表明，EvoNav生成的导航策略在成功率和鲁棒性上优于手工RL奖励和最新奖励设计方法。</td></tr>
<tr><td>2026-05-12</td><td>NavOL: Navigation Policy with Online Imitation Learning<br><a href='http://arxiv.org/pdf/2605.11762'>论文</a></td><td>本文提出NavOL在线模仿学习范式，基于预训练的导航扩散策略解决离线模仿学习的分布偏移与强化学习的奖励工程问题。
◆提出推演与更新的在线模仿循环机制，策略在模拟器中交互并查询全局规划器的最优路径作为在线标签进行训练。
◆通过在策略自身探索的轨迹上进行训练，有效缓解分布偏移与复合误差，提升学习效率且无需人工设计奖励。
◆基于IsaacLab构建高效并行渲染仿真系统，结合领域随机化实现多场景多GPU的大规模轨迹生成。
◆引入包含预定起终点的室内视觉导航基准，以评估模型的零样本泛化能力。
仿真与真实世界的广泛实验均验证了NavOL的有效性与一致性能提升</td></tr>
<tr><td>2026-05-11</td><td>Nano-U: Efficient Terrain Segmentation for Tiny Robot Navigation<br><a href='http://arxiv.org/pdf/2605.10210'>论文</a></td><td>本文针对现有地形分割模型无法在微型机器人微控制器上运行的难题，提出了一个适用于低成本微控制器的鲁棒二值地形分割完整框架。
◆设计了仅含数千参数的超紧凑二值分割网络Nano-U，极大降低了模型对内存和算力的需求。
◆提出了量化感知蒸馏训练方法QAD，通过结合知识蒸馏与量化感知训练，有效弥补了极小网络容量带来的性能损失。
◆扩展了基于Rust的编译器级推理引擎MicroFlow，在商用微控制器上消除了解释器开销和动态内存分配。
该量化模型在标准及高难度农业数据集上均表现出色，实现了极小内存占用与低延迟推理。
此项工作为低成本微型机器人平台验证了一种可行且高能效的感知部署方案。</td></tr>
<tr><td>2026-05-13</td><td>Interactively visualizing biological multilayer networks using MiRA<br><a href='http://arxiv.org/pdf/2605.09597'>论文</a></td><td>本文提出 MiRA（Multilayer Interactive Rendering Application），一个无需安装、基于浏览器的生物多层网络可视化工具。MiRA 支持七种互补的可视化模式，能够在空间、时间和交互类型等维度上直观呈现网络结构。该系统提供交互式操作，包括缩放、筛选、节点高亮和路径追踪，帮助研究者快速探索复杂网络的细节。MiRA 采用轻量化前端技术，实现跨平台兼容和流畅渲染，适合科研与教学场景。通过提供即开即用的可视化环境，MiRA 降低了多层网络分析的技术门槛。

◆ 完全基于浏览器，无需本地安装，降低使用门槛  
◆ 提供七种互补的可视化模式，覆盖空间、时间、交互类型等多维度网络展示  
◆ 支持交互式操作（缩放、筛选、高亮、路径追踪等），提升复杂网络的导航效率  
◆ 采用轻量化前端技术，实现跨平台兼容和流畅渲染性能  
◆ 专为生物学多层网络设计，兼顾教学演示和科研探索的双重需求</td></tr>
<tr><td>2026-05-10</td><td>Safety-Critical LiDAR-Inertial Odometry with On-Manifold Deterministic Protection Level<br><a href='http://arxiv.org/pdf/2605.09383'>论文</a></td><td>本文提出一种安全关键的激光‑惯性里程计（LIO）框架，能够在未知但有界的噪声假设下提供确定性的保护水平。  
◆ 基于点云噪声的有界模型，导出ICP算法估计误差与噪声之间的闭式关系，实现了从噪声到状态不确定性的显式映射。  
◆ 设计了流形上的椭球集合成员滤波，直接在李群/流形空间融合LiDAR和IMU数据，保证估计结果始终位于可行的姿态集合内。  
◆ 将集合成员滤波嵌入LIO，实现实时输出的位置可行集作为确定性保护水平，为下游安全决策提供可靠的上、下界参考。  
◆ 在多机器人、多种复杂环境中进行实验验证，证明了系统在在线安全评估中的有效性、鲁棒性以及广泛的适用性。</td></tr>
<tr><td>2026-05-10</td><td>PECMAN: Perception-enabled Collaborative Multi-Agent Navigation in Unknown Environments<br><a href='http://arxiv.org/pdf/2605.09344'>论文</a></td><td>◆ 将 SMART-3D 的树形重规划方法扩展为多智能体协同感知系统 PECMAN，实现未知环境下的实时协作导航。  
◆ 采用分布式树形变形技术，每台机器人仅在本地树中删除失效节点并修复子树，显著降低重规划计算开销。  
◆ 引入共享感知策略，机器人将新发现的障碍结构广播给团队其他成员，使其能够提前在未探索区域进行预测性重规划，避免冗余反应。  
◆ 通过 28,000 次多智能体仿真验证，PECMAN 在七种 2D 场景下实现最高 52% 的团队完成时间削减，且保持近 100% 成功率。  
◆ 实际机器人实验在真实建筑环境中成功演示了系统的可靠性和鲁棒性，展示了从仿真到硬件的直接迁移能力。</td></tr>
</tbody>
</table>
</div>

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-14</td><td>SOCC-ICP: Semantics-Assisted Odometry based on Occupancy Grids and ICP<br><a href='http://arxiv.org/pdf/2605.15074'>论文</a></td><td>◆ SOCC‑ICP 将语义占据栅格映射与 LiDAR 扫描对齐统一在单一表示中，实现 odometry 与下游任务可直接使用的地图。  
◆ 在占据栅格中记录几何和语义统计信息，实现基于局部平面性的自适应点对点或点对平面 ICP，显著提升匹配精度。  
◆ 通过射线投射更新自由空间，自然过滤动态物体，增强系统对动态环境的鲁棒性。  
◆ 即使在缺乏语义标签的退化几何环境中仍保持竞争性能，语义标签可用时进一步提升定位精度。  
◆ 统一的地图结构消除冗余，直接为运动规划等后续应用提供语义占据栅格，提升整体系统效率。</td></tr>
<tr><td>2026-05-14</td><td>EponaV2: Driving World Model with Comprehensive Future Reasoning<br><a href='http://arxiv.org/pdf/2605.14696'>论文</a></td><td>◆ 提出EponaV2，一种无需感知标注的驾驶世界模型范式，通过综合未来推理实现高质量轨迹规划。  
◆ 通过同时预测未来3D几何与语义地图，构建多模态未来表征，显著提升对周围环境的深层理解。  
◆ 引入流匹配群体相对策略优化机制，借鉴大规模语言模型的训练配方，增强策略学习的稳定性和规划精度。  
◆ 采用大规模预训练与流匹配正则化技术，使模型具备更强的泛化能力和真实世界推理能力。  
◆ 在NAVSIM三个基准上刷新感知无关模型的SOTA，PDMS提升+1.3、EPDMS提升+5.5，验证了方法的卓越效果。</td></tr>
<tr><td>2026-05-14</td><td>Systematic Discovery of Semantic Attacks in Online Map Construction through Conditional Diffusion<br><a href='http://arxiv.org/pdf/2605.14396'>论文</a></td><td>MIRAGE提出一种基于扩散模型潜空间寻找语义攻击的系统框架，能够生成保持道路拓扑但误导高精地图预测的逼真环境变化（如阴影、湿润路面）。在nuScenes上实现了两类攻击：边界移除导致57.7%检测抑制并破坏96%规划轨迹；边界注入首次成功植入虚假车道边界，而像素PGD和AdvPatch均失效。实验表明，这两类攻击在多种对抗防御下仍保持高度有效性，揭示了语义层扰动比像素层扰动更难被当前防御所缓解。通过两个独立视觉语言模型评判，MIRAGE生成的场景在80-84%时间内被认定为真实，而AdvPatch仅为0-9%，进一步验证了其逼真度。  
◆ 创新点1: 采用扩散模型潜空间进行语义变异搜索，生成保持道路拓扑的真实感场景。  
◆ 创新点2: 将攻击发现建模为在真实数据流形上寻找邻近恶意样本的系统化过程。  
◆ 创新点3: 首次实现可注入虚假车道边界的攻击，显著超越传统像素扰动和对抗贴片方法的有效性。</td></tr>
<tr><td>2026-05-13</td><td>Motion Planning for Autonomous Vehicles using Optimization over Graphs of Convex Sets<br><a href='http://arxiv.org/pdf/2605.14199'>论文</a></td><td>本文研究了利用凸集图优化（GCS）近似非线性最优控制问题，以实现自动驾驶车辆在复杂环境下的实时运动规划。  
◆ 将自由空间表示为由凸区域组成的有向图，离散连通性决策处理非凸几何，保持区域内轨迹约束的凸性。  
◆ 采用Bezier曲线参数化空间路径并配合多项式时间尺度，实现轨迹的光滑且计算友好的表达。  
◆ 在小滑移和线性轮胎假设下，利用简化的动态自行车模型将动力学可行性转化为凸约束，对轨迹导数施加限制。  
◆ 在CommonRoad基准上与离散非线性最优控制方法对比，验证了GCS方法在碰撞规避、动力学一致性以及计算效率和初始化鲁棒性方面的优势。</td></tr>
<tr><td>2026-05-13</td><td>Receding Horizon Multi-Agent Deceptive Path Planner<br><a href='http://arxiv.org/pdf/2605.14085'>论文</a></td><td>本文提出了一种基于滚动时域的多智能体欺骗性路径规划框架，利用短时段轨迹优化替代传统的全时段计算，显著提升了在线规划的计算效率与可扩展性。该框架基于玻尔兹曼分布构建统一成本函数，生成平衡最优性与欺骗性的随机策略，无需训练即可本地更新。
◆ 首创将滚动时域优化机制引入欺骗性路径规划领域，通过短视界迭代计算规避全时段重计算开销，实现实时在线决策
◆ 构建基于玻尔兹曼分布的统一成本函数框架，灵活整合欺骗性、资源消耗、路径平滑度及多智能体耦合约束于一体
◆ 提出无需训练的本地策略更新方法，支持欺骗水平与约束条件的在线动态调节，有效适应环境突变与目标变更</td></tr>
<tr><td>2026-05-13</td><td>LMPath: Language-Mediated Priors and Path Generation for Aerial Exploration<br><a href='http://arxiv.org/pdf/2605.13782'>论文</a></td><td>◆ 引入语言模型来根据目标描述推理可能包含该对象的区域，形成语义驱动的先验。  
◆ 将生成式语言模型与基础视觉模型结合，在卫星图像上实现细粒度区域分割。  
◆ 提出多种路径生成目标，包括最小期望搜索时间、限定距离内最高发现概率以及聚焦高可能性子区域。  
◆ 设计完整的端到端管道，从自然语言提示直接生成UAV可执行路径。  
◆ 在真实大规模环境中进行实物UAV实验，验证了所提路径相较于传统几何覆盖方法显著提升搜索效率。</td></tr>
<tr><td>2026-05-13</td><td>Manipulation Planning for Construction Activities with Repetitive Tasks<br><a href='http://arxiv.org/pdf/2605.13754'>论文</a></td><td>本文针对建筑施工中的重复性操作（如砌墙、安装天花板），提出一种基于单次示范的机器人操作技能获取与运动规划框架。 在虚拟现实（VR）环境中收集用户的抓取‑放置演示，利用螺旋几何描述动作，将其分解为若干恒定螺旋运动序列。 通过螺旋线性插值（ScLERP）生成连续的任务实例，并结合分辨率运动速率控制（RMRC）在关节空间实现精确、平滑的轨迹跟踪。 只需一次砖块放置或单块天花板安装的示范，即可推广到任意长度、任意布局的墙体和天花板任务。 在7自由度机器人仿真与实物平台上验证，系统对重复任务的高精度、鲁棒性以及实时控制表现出显著优势。

◆ 在VR环境中实现直观的操作示范，直接获取人类动作的螺旋几何特征。  
◆ 将演示动作近似为恒定螺旋序列，实现运动的可参数化、可复用。  
◆ 提出基于螺旋线性插值（ScLERP）的任务实例生成方法，仅凭单次示范即可生成完整施工序列。  
◆ 将ScLERP与RMRC结合，实现从任务空间到关节空间的闭环运动规划，保证精度和实时性。  
◆ 展示对任意长度、布局的重复性建筑任务（如砌墙、天花板）的高鲁棒泛化能力。</td></tr>
<tr><td>2026-05-13</td><td>TinySDP: Real Time Semidefinite Optimization for Certifiable and Agile Edge Robotics<br><a href='http://arxiv.org/pdf/2605.13748'>论文</a></td><td>◆ TinySDP是首个面向嵌入式系统的半定规划求解器，实现了在微控制器上实时模型预测控制。  
◆ 通过将正半定锥投影与缓存Riccati的ADMM求解相结合，显著降低了计算复杂度，满足嵌入式平台的算力约束。  
◆ 提出后验秩‑1证明机制，能够在每个时间步将松弛解转化为几何冲突保证，提供可验证的安全性。  
◆ 在障碍物规避的弯道和动态障碍场景中，TinySDP相比现有局部规划方法实现碰撞自由导航，路径长度最高缩短73%。  
◆ 在Crazyflie四旋翼平台上验证，半定约束能够在实时速率下执行，展示了敏捷嵌入式机器人的实际可行性。</td></tr>
<tr><td>2026-05-13</td><td>Asymptotically Optimal Ergodic Coverage on Generalized Motion Fields<br><a href='http://arxiv.org/pdf/2605.13442'>论文</a></td><td>◆ 将自适应搜索问题重新建模为在时变流场中的遍历覆盖问题，采用最大均值偏差（MMD）作为功能遍历性度量。  
◆ 提出了流场自适应遍历覆盖目标函数，显式考虑域演化与流动动力学，实现对环境时空过程的闭环覆盖保证。  
◆ 在仅需开环或欠驱动的规划设置下，证明了该方法仍能保持遍历覆盖的渐近最优性。  
◆ 通过仿真验证了算法在海洋自主潜航、人类和牲畜移动等多类时空过程上的鲁棒性与通用性。  
◆ 物理实验在非凸、受限流场的无人机和足式机器人平台上实现了有效遍历覆盖，验证了方法对机器人动力学的兼容性。</td></tr>
<tr><td>2026-05-13</td><td>Multi-Depth Uniform Coverage Path Planning for Unmanned Surface Vehicle Surveying<br><a href='http://arxiv.org/pdf/2605.13123'>论文</a></td><td>本文提出了一种用于无人艇测深的新型自动覆盖路径规划算法，解决了传统海面均匀规划无法保证海底均匀覆盖的问题。
◆融合粗略的先验深度信息来预处理目标区域，自适应地引导路径生成与感知范围配置。
◆通过显式考虑深度变化，优化测量航线间距并动态调整探测波束孔径，以实现更一致的海底覆盖。
◆实现全自动化设计，无需人工选择航点，直接适用于自主航海器的实际应用。
验证表明该方法显著优于传统牛耕式规划，在合成地形和真实港口模拟中覆盖率分别超过99%和92%，远超传统方法。</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.05.15
