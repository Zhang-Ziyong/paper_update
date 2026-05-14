# 计算机视觉领域最新论文 (2026.05.14)

> 每日自动更新计算机视觉领域的最新arXiv论文

> 使用说明: [点击查看](./docs/README.md#usage)

<details>
<summary>分类目录</summary>
<ol>
<li><a href='#slam'>SLAM</a></li>
<li><a href='#sfm'>SFM</a></li>
<li><a href='#visual-localization'>Visual Localization</a></li>
<li><a href='#image-matching'>Image Matching</a></li>
<li><a href='#nerf'>NeRF</a></li>
<li><a href='#keypoint-detection'>Keypoint Detection</a></li>
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
<tr><td>2026-05-06</td><td>A Closed-Form Dual-Barrier CBF Safety Filter for Holonomic Robots on Incrementally Built Occupancy Grid Maps<br><a href='http://arxiv.org/pdf/2605.05182'>论文</a></td><td>◆ We present a dual-barrier control barrier function (CBF) safety filter for real-time, safety-critical velocity control of holonomic robots operating in incrementally built occupancy grid maps.
◆ As a robot explores an unknown environment, unmapped regions introduce irreducible uncertainty, since obstacle geometry beyond the explored frontier is unknown, making entry into such regions a source of collision risk, especially with front-facing sensors.
◆ To address this, we enforce two constraints: avoidance of mapped obstacles and restriction from unexplored regions.</td></tr>
<tr><td>2026-05-06</td><td>Dr-PoGO: Direct Radar Pose-Graph Optimization<br><a href='http://arxiv.org/pdf/2605.04806'>论文</a> | <a href='https://github.com/utiasASRL/dr_pogo'>代码</a></td><td>◆ This paper introduces Dr-PoGO, a method for Simultaneous Localization And Mapping (SLAM) using a 2D spinning radar.
◆ Unlike cameras or lidars that require line-of-sight, millimetre-wave radars can `see&#x27; through dust, falling snow, rain, etc.
◆ Accordingly, it is a great modality for robust perception regardless of the weather conditions.</td></tr>
<tr><td>2026-05-07</td><td>Hardware-Aware Neural Feature Extraction for Resource-Constrained Devices<br><a href='http://arxiv.org/pdf/2605.04282'>论文</a></td><td>◆ Visual SLAM is a core component of spatial computing systems, yet deploying learned local feature extractors on microcontroller-class hardware remains challenging due to memory, bandwidth, and quantization constraints.
◆ While modern neural descriptors provide strong robustness, their practical adoption is often hindered by system-level bottlenecks that are not captured by FLOP-based efficiency metrics.
◆ In this work, we introduce Gideon, a hardware-aware neural feature extractor explicitly designed for resource-constrained devices.</td></tr>
<tr><td>2026-05-05</td><td>Robust Visual SLAM for UAV Navigation in GPS-Denied and Degraded Environments: A Multi-Paradigm Evaluation and Deployment Study<br><a href='http://arxiv.org/pdf/2605.03678'>论文</a></td><td>◆ Reliable localization in GPS-denied, visually degraded environments is critical for autonomous UAV opera- tions.
◆ This paper presents a systematic comparative evaluation of five V-SLAM systems ORB-SLAM3, DPVO, DROID-SLAM, DUSt3R, and MASt3R spanning classical, deep learning, recurrent, and Vision Transformer (ViT) paradigms.
◆ Experiments are conducted on curated sequences from four public benchmarks (TUM RGB-D, EuRoC MAV, UMA-VI, SubT-MRS) and a custom monocular indoor dataset under five controlled degradation conditions (normal, low light, dust haze, motion blur, and combined), with sub-millimeter Vicon ground truth.</td></tr>
<tr><td>2026-05-04</td><td>DynoSLAM: Dynamic SLAM with Generative Graph Neural Networks for Real-World Social Navigation<br><a href='http://arxiv.org/pdf/2605.02759'>论文</a></td><td>◆ Traditional Simultaneous Localization and Mapping (SLAM) algorithms rely heavily on the static environment assumption, which severely limits their applicability in real-world spaces populated by moving entities, such as pedestrians.
◆ In this work, we propose DynoSLAM, a tightly-coupled Dynamic GraphSLAM architecture that integrates socially-aware Graph Neural Networks (GNNs) directly into the factor graph optimization.
◆ Unlike conventional approaches that use rigid constant-velocity heuristics or deterministic single-agent neural priors, our framework formulates pedestrian motion forecasting as a stochastic World Model.</td></tr>
<tr><td>2026-05-04</td><td>Multi-User XR Offloading via Massive MIMO: A System-Level Analysis using a Real-Life Dataset<br><a href='http://arxiv.org/pdf/2605.02631'>论文</a></td><td>◆ SLAM is one of the biggest bottlenecks of XR devices, which have strict requirements for latency, power consumption, and user satisfaction.
◆ A solution that has been proposed and studied to meet the requirements is to offload SLAM to a remote server, which leverages computational hardware but may suffer due to incurred delays and transmission power.
◆ In this work, we propose offloading SLAM using Massive MIMO, which is attractive due to lower latencies, transmission power, and a more reliable link for multiple users.</td></tr>
<tr><td>2026-05-04</td><td>Change-Robust Online Spatial-Semantic Topological Mapping<br><a href='http://arxiv.org/pdf/2605.02227'>论文</a></td><td>◆ Autonomous robots require change-robust spatial-semantic reasoning: using spatial and semantic knowledge to decide where to go, how to get there, and where the robot is despite environmental change.
◆ Existing approaches typically attach semantics to SLAM-built metric maps, but these pipelines are brittle under appearance shifts and scene dynamics, where data association and relocalization degrade.
◆ We propose a Change-Robust Online Spatial-Semantic (CROSS) representation that replaces a globally consistent metric substrate with an online, pose-aware topological graph of RGB-D keyframes.</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-05-05</td><td>Permutation Routing on Ramanujan Hypergraphs with Applications to Neutral Atom Quantum Architectures<br><a href='http://arxiv.org/pdf/2605.02498'>论文</a></td><td>◆ We consider the routing of neutral atoms on a reconfigurable lattice in terms of hypergraph transformations.
◆ We prove the routing number of a Ramanujan $(d,r)$-regular hypergraph on $N$ vertices satisfies $\mathrm{rt}(H) = Θ(\log N)$, where routing is via matchings in the clique expansion graph $G_{\mathrm{cl}}(H)$.
◆ Hypergraphs reframe the qubit routing problem by replacing Nenadov&#x27;s two-sided spectral gap hypothesis with a one-sided condition based on eigenvalue centering.</td></tr>
<tr><td>2026-05-03</td><td>DP-SfM: Dual-Pixel Structure-from-Motion without Scale Ambiguity<br><a href='http://arxiv.org/pdf/2605.01852'>论文</a> | <a href='https://github.com/lilika-makabe/dp-sfm-tpami.git'>代码</a></td><td>◆ Multi-view 3D reconstruction, namely, structure-from-motion followed by multi-view stereo, is a fundamental component of 3D computer vision.
◆ In general, multi-view 3D reconstruction suffers from an unknown scale ambiguity unless a reference object of known size is present in the scene.
◆ In this article, we show that multi-view images captured using a dual-pixel (DP) sensor can automatically resolve the scale ambiguity, without requiring a reference object or prior calibration.</td></tr>
<tr><td>2026-05-01</td><td>PEARLS: Two Distinct Populations of AGN Hosts Moving Between Star Formation and Quiescence<br><a href='http://arxiv.org/pdf/2605.00822'>论文</a></td><td>◆ We present the results of AGN--host-galaxy decomposition using JWST/NIRCam, HST/ACS, and HST/WFC3 imaging of the North Ecliptic Pole Time Domain Field (NEP-TDF).
◆ The light-profiles of 36 NIRCam-selected AGN candidates are modeled for measurement of their point sources, and point source-subtracted host-galaxy emission is used in SED modeling for star formation rate (SFR) estimation.
◆ Offsets from the canonical star-forming main sequence (SFMS) show that the host galaxies form two distinct groups distinguished by their star formation: a ``bridge&#x27;&#x27; between the moderate SFRs of radio sources and low SFRs of X-ray sources, and a cleanly-separated ``branch&#x27;&#x27; above $Δ\rm SFMS = -1$ whose SFR trends positively with AGN fraction.</td></tr>
<tr><td>2026-05-01</td><td>2D-SuGaR: Surface-Aware Gaussian Splatting for Geometrically Accurate Mesh Reconstruction<br><a href='http://arxiv.org/pdf/2605.00569'>论文</a></td><td>◆ 3D Gaussian Splatting (3DGS) has emerged as a powerful technique for generating photorealistic renderings of a scene in real-time.
◆ However, the volumetric nature of 3DGS limits its ability to accurately capture surface geometry.
◆ To address this, 2D Gaussian Splatting (2DGS) was proposed to enable view-consistent and geometrically accurate surface reconstruction from multi-view images.</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='visual-localization'>Visual Localization</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-13</td><td>Same Image, Different Meanings: Toward Retrieval of Context-Dependent Meanings<br><a href='http://arxiv.org/pdf/2605.12905'>论文</a></td><td>本文首次系统探讨图像在不同叙事上下文中的意义漂移，并提出检索难题。  
观察到图像的语义抽象层次与上下文依赖度正相关：具体对象保持跨情境一致，而抽象氛围和意图随叙事改变。  
◆ 提出L1–L4语义分层框架，将图像语义从上下文无关到高度依赖划分为四个层次，为定量研究提供统一结构。  
◆ 设计基于合成故事上下文和查询的受控评测，揭示仅在具体层（L1-L2）即可无需上下文检索，而抽象层（L3-L4）必须依赖叙事注入。  
◆ 实验表明图像侧注入上下文比查询侧更有效，且最高抽象层（L4）即使完整上下文仍难以准确检索，指出该问题仍是开放挑战。</td></tr>
<tr><td>2026-05-12</td><td>PoseCompass: Intelligent Synthetic Pose Selection for Visual Localization<br><a href='http://arxiv.org/pdf/2605.12144'>论文</a></td><td>◆ 提出价值导向的姿态排名机制，融合定位难度、覆盖新颖性和渲染可视性三维指标，实现对合成姿态的精准评估。  
◆ 设计轨迹约束候选生成和Top‑K选择策略，保证生成的姿态既符合运动轨迹又具信息量。  
◆ 引入轻量级扩散对齐的3DGS视图合成，显著提升合成图像质量并过滤噪声。  
◆ 在7‑Scenes上实现约3倍加速（适配时间从15.2降至5.1分钟）并降低中位姿态误差53.8%。  
◆ 将真实与合成数据混合微调姿态回归器，显著优于随机采样基线，提升定位鲁棒性。</td></tr>
<tr><td>2026-05-12</td><td>Logit-Attention Divergence: Mitigating Position Bias in Multi-Image Retrieval via Attention-Guided Calibration<br><a href='http://arxiv.org/pdf/2605.11591'>论文</a> | <a href='https://github.com/brightXian/LAD'>代码</a></td><td>◆发现并形式化了Logit‑Attention Divergence现象：模型输出的logits受输入顺序偏置严重，而内部注意力图仍与语义相关的视觉证据保持一致。  
◆揭示了现有logit层校准方法（如PriDe）的根本局限，指出必须利用注意力信息进行纠正才能有效去偏。  
◆提出一种无需训练的注意力引导去偏框架，仅需极少的校准样本，即可在推理阶段实现实例级校准。  
◆利用模型内在的注意力信号进行校准，计算开销几乎可忽略，满足实际部署的效率需求。  
◆在MS‑COCO等基准上实验表明，所提方法显著提升排列不变性，精度提升超过40%，达到最新最优水平。  
◆代码已在GitHub公开，便于复现和进一步应用。</td></tr>
<tr><td>2026-05-11</td><td>BGG: Bridging the Geometric Gap between Cross-View images by Vision Foundation Model Adaptation for Geo-Localization<br><a href='http://arxiv.org/pdf/2605.10345'>论文</a></td><td>本文针对跨视角图像（如无人机和卫星视图）之间的几何差异导致跨视角地理定位（CVGL）困难的问题，提出一种基于视觉基础模型（VFM）的参数高效适配框架 BGG。  
BGG 在保持 VFM 通用视觉表征的同时，通过多粒度特征增强适配器（MFEA）和频域感知结构聚合（FASA）模块实现跨视角几何间隙的有效桥接，并显著降低训练成本。  
◆ MFEA 采用多层次空洞卷积提升特征的尺度适应性和视角鲁棒性，以小规模参数实现跨视角几何差异的对齐。  
◆ FASA 通过在频域调制 patch token 并进行自适应聚合，增强局部结构特征，弥补 [CLS] token 缺乏空间细节的不足。  
◆ BGG 将增强的局部特征与 [CLS] token 融合，实现更精准的跨视角检索与定位，并在 University‑1652 和 SUES‑200 数据集上取得了最优性能。  
实验结果表明，BGG 在定位精度上领先于现有方法，且仅需极低的训练成本。</td></tr>
<tr><td>2026-05-11</td><td>Hystar: Hypernetwork-driven Style-adaptive Retrieval via Dynamic SVD Modulation<br><a href='http://arxiv.org/pdf/2605.10009'>论文</a></td><td>◆ Query-based image retrieval (QBIR) requires retrieving relevant images given diverse and often stylistically heterogeneous queries, such as sketches, artworks, or low-resolution previews.
◆ While large-scale vision--language representation models (VLRMs) like CLIP offer strong zero-shot retrieval performance, they struggle with distribution shifts caused by unseen query styles.
◆ In this paper, we propose the Hypernetwork-driven Style-adaptive Retrieval (Hystar), a lightweight framework that dynamically adapts model weights to each query&#x27;s style.</td></tr>
<tr><td>2026-05-11</td><td>Learning to Align Generative Appearance Priors for Fine-grained Image Retrieval<br><a href='http://arxiv.org/pdf/2605.09859'>论文</a></td><td>◆ Fine-grained image retrieval (FGIR) typically relies on supervision from seen categories to learn discriminative embeddings for retrieving unseen categories.
◆ However, such supervision often biases retrieval models toward the semantics of seen categories rather than the underlying appearance characteristics that generalize across categories, thereby limiting retrieval performance on unseen categories.
◆ To tackle this, we propose GAPan, a Generative Appearance Prior alignment network that reformulates the learning objective from category prediction toward appearance modeling.</td></tr>
<tr><td>2026-05-08</td><td>CapCLIP: A Vision-Language Representation Alignment Approach for Wireless Capsule Endoscopy Analysis<br><a href='http://arxiv.org/pdf/2605.08493'>论文</a></td><td>◆ Wireless capsule endoscopy (WCE) enables non-invasive visual assessment of the small bowel, but its clinical utility is constrained by the large volume of frames generated per examination and the difficulty of recognising subtle abnormalities under highly variable imaging conditions.
◆ Existing learning-based approaches for WCE are predominantly vision-only, often confined to narrow pathology sets, and show limited transfer across datasets and centres.
◆ To address these limitations, this study introduces CapCLIP, a domain-specific vision-language representation learning framework for WCE.</td></tr>
<tr><td>2026-05-08</td><td>Decoupling Endpoint and Semantic Transition Learning for Zero-Shot Composed Image Retrieval<br><a href='http://arxiv.org/pdf/2605.08389'>论文</a></td><td>◆ Zero-shot composed image retrieval (ZS-CIR) retrieves a target image from a reference image and a text modification without human-annotated CIR triplets.
◆ Projection-based ZS-CIR methods are attractive because they do not rely on LLMs at inference and remain lightweight, but they often underperform LLM-based approaches on complex semantic modifications.
◆ This gap reflects a semantic transition bottleneck in projection-based ZS-CIR: endpoint-level matching can let the edit text act as a target-side attribute cue rather than grounding it as a source-conditioned semantic transition.</td></tr>
<tr><td>2026-05-08</td><td>Disambiguating 2D-3D Correspondences in Gaussian Splatting-based Feature Fields for Visual Localization<br><a href='http://arxiv.org/pdf/2605.07351'>论文</a></td><td>◆ While Gaussian Splatting-based Feature Fields (GSFFs) have shown promise for visual localization, this paper highlights that photometrically optimized GSFFs are inherently ill-suited for 2D-3D matching.
◆ The volumetric extent of each Gaussian induces many-to-one pixel-to-point mappings that destabilize PnP-based pose estimation, while photometric optimization gives rise to superfluous Gaussians devoid of multi-view consistency.
◆ To address these issues, we propose SplitGS-Loc, a localization-specialized GSFFs construction framework that disambiguates 2D-3D correspondences by exploiting Gaussian attributes.</td></tr>
<tr><td>2026-05-08</td><td>Zero-Shot Satellite Image Retrieval through Joint Embeddings: Application to Crisis Response<br><a href='http://arxiv.org/pdf/2605.05405'>论文</a></td><td>◆ Semantic search of Earth observation archives remains challenging.
◆ Visual foundation models such as CLAY produce rich embeddings of satellite imagery but lack the natural-language grounding needed for intuitive query, and full contrastive training of a remote-sensing CLIP-style model requires paired data and compute that are unavailable at global scale.
◆ We present GeoQuery, a zero-shot retrieval system that sidesteps this constraint through prompt-aligned text proxies.</td></tr>
<tr><td>2026-05-06</td><td>Open-SAT: LLM-Guided Query Embedding Refinement for Open-Vocabulary Object Retrieval in Satellite Imagery<br><a href='http://arxiv.org/pdf/2605.05344'>论文</a></td><td>◆ In satellite applications, user queries often take the form of open-ended natural language, extending beyond a fixed set of predefined categories.
◆ This open-vocabulary nature poses significant challenges for retrieving relevant image tiles, as the retrieval system must generalize to a wide range of unseen objects and concepts.
◆ While vision-language models (VLMs) such as CLIP are widely used for text-image retrieval, even fine-tuned variants often struggle to accurately align such queries with satellite imagery.</td></tr>
<tr><td>2026-05-06</td><td>MIRAGE: Retrieval and Generation of Multimodal Images and Texts for Medical Education<br><a href='http://arxiv.org/pdf/2605.04772'>论文</a></td><td>◆ Access to diverse, well-annotated medical images with interactive learning tools is fundamental for training practitioners in medicine and related fields to improve their diagnostic skills and understanding of anatomical structures.
◆ While medical atlases are valuable, they are often impractical due to their size and lack of interactivity, whereas online image search may provide mislabeled or incomplete material.
◆ To address this, we propose MIRAGE, a multimodal medical text and image retrieval and generation system that allows users to find and generate clinically relevant images from trustworthy sources by mapping both text and images to a shared latent space, enabling semantically meaningful queries.</td></tr>
<tr><td>2026-05-06</td><td>ULF-Loc: Unbiased Landmark Feature for Robust Visual Localization with 3D Gaussian Splatting<br><a href='http://arxiv.org/pdf/2605.04730'>论文</a></td><td>◆ Visual localization is a core technology for augmented reality and autonomous navigation.
◆ Recent methods combine the efficient rendering of 3D Gaussian Splatting (3DGS) with feature-based localization.
◆ These methods rely on direct matching between 2D query features and the 3D Gaussian feature field, but this often results in mismatches due to an inherent bias in the learned Gaussian feature.</td></tr>
<tr><td>2026-05-06</td><td>Multi-Level Bidirectional Biomimetic Learning for EEG-Based Visual Decoding<br><a href='http://arxiv.org/pdf/2605.04680'>论文</a></td><td>◆ EEG-based visual neural decoding aims to align neural responses with visual stimuli for tasks such as image retrieval.
◆ However, limited paired data and a fundamental mismatch between high-fidelity digital images and biological visual perception - distorted by retinotopic mapping and subject-specific neuroanatomy - severely impede cross-modal alignment.
◆ To address this, we propose MB2L, a Multi-Level Bidirectional Biomimetic Learning framework that incorporates structured physiological inductive biases into representation learning.</td></tr>
<tr><td>2026-05-04</td><td>AlbumFill: Album-Guided Reasoning and Retrieval for Personalized Image Completion<br><a href='http://arxiv.org/pdf/2605.02892'>论文</a></td><td>◆ Personalized image completion aims to restore occluded regions in personal photos while preserving identity and appearance.
◆ Existing methods either rely on generic inpainting models that often fail to maintain identity consistency, or assume that suitable reference images are explicitly provided.
◆ In practice, suitable references are often not explicitly provided, requiring the system to search for identity-consistent images within personal photo collections.</td></tr>
<tr><td>2026-05-04</td><td>StableMind: Source-Free Cross-Subject fMRI Decoding with Regularized Adaptation<br><a href='http://arxiv.org/pdf/2605.02586'>论文</a> | <a href='https://github.com/lingeringlight/StableMind'>代码</a></td><td>◆ Existing cross-subject fMRI decoding methods typically train a model on multiple scanned subjects and then adapt it to a new subject using substantial paired fMRI-image data.
◆ However, in realistic scenarios, new-subject fMRI data are often limited due to costly data acquisition, and raw data from previous subjects may be inaccessible, leading existing methods to suffer performance degradation during new-subject adaptation.
◆ In this paper, we identify that this degradation stems from two key issues: brain-side instability caused by large subject differences in fMRI responses, and image-side supervision unreliability caused by fine-grained visual details that are not reliably supported by limited fMRI signals.</td></tr>
<tr><td>2026-05-04</td><td>Rethinking Electro-Optical Vision Foundation Models for Remote Sensing Retrieval: A Controlled Comparison with Generalist VFM<br><a href='http://arxiv.org/pdf/2605.02283'>论文</a></td><td>◆ Vision foundation models have attracted significant attention for their ability to leverage large-scale unlabeled visual data.
◆ This advantage is particularly important in remote sensing, where data acquisition is costly and annotation often requires expert knowledge.
◆ Recent electro-optical vision foundation models aim to learn domain-specific representations from remote sensing imagery, but it remains unclear whether they are more effective than strong generalist vision foundation models under retrieval-based evaluation.</td></tr>
<tr><td>2026-05-02</td><td>X-ray dark-field imaging from intensity flow: A Fokker-Planck approach to grating interferometry<br><a href='http://arxiv.org/pdf/2605.01265'>论文</a></td><td>◆ Grating interferometry is a promising diagnostic technique that enables simultaneous acquisition of three complementary, synergistic X-ray images: transmission, differential phase, and dark-field.
◆ Its key advantage over other setups is its ability to use large pixels and, hence, large-area detectors, as well as its compatibility with low-coherence, compact X-ray sources, both of which are key factors for human-scale imaging.
◆ It has already demonstrated strong potential for chest imaging applications, including the diagnosis of pulmonary emphysema, fibrosis, and cancer.</td></tr>
<tr><td>2026-05-01</td><td>Depth-Guided Privacy-Preserving Visual Localization Using 3D Sphere Clouds<br><a href='http://arxiv.org/pdf/2605.00562'>论文</a></td><td>◆ The emergence of deep neural networks capable of revealing high-fidelity scene details from sparse 3D point clouds has raised significant privacy concerns in visual localization involving private maps.
◆ Lifting map points to randomly oriented 3D lines is a well-known approach for obstructing undesired recovery of the scene images, but these lines are vulnerable to a density-based attack that can recover the point cloud geometry by observing the neighborhood statistics of lines.
◆ With the aim of nullifying this attack, we present a new privacy-preserving scene representation called \emph{sphere cloud}, which is constructed by lifting all points to 3D lines crossing the centroid of the map, resembling points on the unit sphere.</td></tr>
<tr><td>2026-05-01</td><td>MSACT: Multistage Spatial Alignment for Stable Low-Latency Fine Manipulation<br><a href='http://arxiv.org/pdf/2605.00475'>论文</a></td><td>◆ Real-world fine manipulation, particularly in bimanual manipulation, typically requires low-latency control and stable visual localization, while collecting large-scale data is costly and limited demonstrations may lead to localization drift.
◆ Existing approaches make different trade-offs: action-chunking policies such as ACT enable low-latency execution and data efficiency but rely on dense visual features without explicit spatial consistency, generative methods such as Diffusion Policy improve expressiveness but can incur iterative sampling latency, vision-language-action and voxel-based methods enhance generalization and geometric grounding but require higher computational cost and system complexity.
◆ We introduce a multistage spatial attention module that extracts stable 2D attention points and jointly predicts future attention sequences with a temporal alignment loss.</td></tr>
<tr><td>2026-05-01</td><td>SIMON: Saliency-aware Integrative Multi-view Object-centric Neural Decoding<br><a href='http://arxiv.org/pdf/2605.00401'>论文</a></td><td>◆ Recent EEG-to-image retrieval methods leverage pretrained vision encoders and foveation-inspired priors, but typically assume a fixed, center-focused view.
◆ This center bias conflicts with content-driven human attention, creating a geometric-semantic dissociation between visual features and EEG responses.
◆ We propose SIMON, a saliency-aware multi-view framework for zero-shot EEG-to-image retrieval.</td></tr>
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

<h2 id='nerf'>NeRF</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-13</td><td>GuardMarkGS: Unified Ownership Tracing and Edit Deterrence for 3D Gaussian Splatting<br><a href='http://arxiv.org/pdf/2605.12919'>论文</a></td><td>本文首次提出统一框架GuardMarkGS，将所有权追溯水印与编辑抑制结合到同一优化过程，实现对3D Gaussian Splatting资产的全方位版权保护。  
框架在全部高斯上施加场景级水印目标，保证在任意视角下都能恢复出高准确度的比特信息。  
同时通过潜空间锚点分离、去噪轨迹偏离和跨注意力偏离三个对抗分支，配合更新显著性引导的高斯选择策略，强化对指令驱动编辑的抑制作用。  
◆ 将所有权追踪水印与编辑威慑目标在单一优化中联合学习。  
◆ 采用潜锚分离、去噪轨迹偏离和跨注意力偏离的多支路对抗实现强效编辑阻断。  
◆ 通过更新显著性驱动的高斯筛选，对关键高斯赋予更强的对抗更新，兼顾水印恢复、编辑抑制与渲染质量。</td></tr>
<tr><td>2026-05-12</td><td>3D Gaussian Splatting for Efficient Retrospective Dynamic Scene Novel View Synthesis with a Standardized Benchmark<br><a href='http://arxiv.org/pdf/2605.12437'>论文</a></td><td>本文针对体育等多视角同步场景，指出在每个时刻已有强几何约束，因而无需显式的时间耦合或多体运动约束，即可实现高效的回顾性动态场景新视角合成。为此提出一种基于3D Gaussian Splatting的同步多视角方法：从起始帧的SfM点云初始化高斯，并沿时间直接传播优化，省去时间变形约束。与此同时构建了基于Blender的Dynamic MV数据集框架，提供同步相机姿态、标准坐标格式及完整训练数据，消除已有数据管道的不一致性。在该框架下设计了动态基准套件，对典型NeRF和3DGS方法进行受控评估，验证了所提方法在速度和渲染质量上的优势。实验表明，在同步多视角设定下，仅依赖空间几何约束即可实现高效、真实的动态场景新视角合成。  
◆ 在同步多视角场景下证明时间耦合非必要，省去复杂约束；  
◆ 基于Sf</td></tr>
<tr><td>2026-05-11</td><td>Predicting 3D structure by latent posterior sampling<br><a href='http://arxiv.org/pdf/2605.10830'>论文</a></td><td>本文提出将NeRF的体素渲染与扩散模型的概率后验采样相结合，以实现三维结构的感知推理。将三维场景建模为可学习的随机潜在变量，学习潜在</td></tr>
<tr><td>2026-05-12</td><td>DySurface: Consistent 4D Surface Reconstruction via Bridging Explicit Gaussians and Implicit Functions<br><a href='http://arxiv.org/pdf/2605.10360'>论文</a></td><td>◆ 提出 DySurface 框架，通过将显式 3D Gaussian 与隐式 SDF 结合，实现动态场景的 4D 表面一致重建。  
◆ 针对 3DGS 前向形变（canonical→dynamic）与体渲染 SDF 反向形变（dynamic→canonical）之间的结构不匹配，设计了统一的双向形变映射机制。  
◆ 引入 VoxGS‑DSDF 分支，利用变形的高斯构建动态稀疏体素网格，为隐式 SDF 提供显式几何约束。  
◆ 显式的体素‑高斯锚定有效正则化体渲染过程，显著提升表面完整性，实现水密边界和细节保持。  
◆ 实验表明，DySurface 在几何精度指标上超越现有最优方法，同时保持竞争力的渲染性能。  
◆ 该工作为时序一致的动态几何重建提供新思路，展示了显‑隐融合在 4D 场景中的潜力。</td></tr>
<tr><td>2026-05-10</td><td>Low-Cost Neural Radiance Fields<br><a href='http://arxiv.org/pdf/2605.09312'>论文</a></td><td>本文对三种加速NeRF变体DS‑NeRF、TensoRF和HashNeRF进行系统性比较，探索低计算、低数据条件下的改进方案。  
◆为TensoRF引入基于COLMAP关键点的深度监督损失（TensoRF‑DS），在视角稀疏时显著提升PSNR。  
◆对TensoRF的特征解码MLP进行消融实验，发现输入降采样可在保持PSNR的同时缩短训练时间。  
◆提出HashNeRF的四 种结构变体，包括残差和卷积设计，在相同迭代预算下实现PSNR与训练时间的权衡。  
实验表明，等时评估下这些扩展未显著超越原始基线，但系统化了在不同受限环境下的适用性，为后续模型设计提供参考。</td></tr>
<tr><td>2026-05-06</td><td>Low-Cost Stereo Vision for Robust 3D Positioning of Thin Radiata Pine Branches in Autonomous Drone Pruning<br><a href='http://arxiv.org/pdf/2605.08213'>论文</a></td><td>◆ Manual pruning of radiata pine, a species of major economic importance to New Zealand forestry, is hazardous, labour-intensive, and increasingly constrained by workforce shortages.
◆ Existing autonomous pruning platforms typically rely on expensive sensors such as LiDAR and are limited to thick branches, which restricts their wider adoption.
◆ This paper investigates whether a single low-cost stereo camera mounted on a drone can provide sufficiently accurate branch detection and three-dimensional positioning to support autonomous pruning of branches as thin as 10 mm, thereby removing the need for auxiliary depth sensors.</td></tr>
<tr><td>2026-05-08</td><td>PropSplat: Map-Free RF Field Reconstruction via 3D Gaussian Propagation Splatting<br><a href='http://arxiv.org/pdf/2605.08035'>论文</a></td><td>◆ Building a site-specific propagation model typically requires either ray-tracing over detailed 3D maps or dense measurement campaigns.
◆ Both approaches are expensive and often infeasible for rapid deployments where geographic data is unavailable or outdated.
◆ We present PropSplat, a map-free propagation modeling method that reconstructs radio frequency (RF) fields using 3D anisotropic Gaussian primitives.</td></tr>
<tr><td>2026-05-08</td><td>High-Fidelity Surface Splatting-Based 3D Reconstruction from Multi-View Images<br><a href='http://arxiv.org/pdf/2605.07254'>论文</a></td><td>◆ Multi-view mesh reconstruction remains a core challenge in computer graphics and vision, especially for recovering high-frequency geometry from sparse observations.
◆ Recent methods such as 3D Gaussian Splatting (3DGS) and Neural Radiance Fields (NeRF) rely on post-processing for mesh extraction, thereby limiting joint optimization of geometry and appearance.
◆ Implicit Moving Least Squares (IMLS) instead enables direct conversion of point clouds into signed distance and texture fields, supporting end-to-end reconstruction and rendering.</td></tr>
<tr><td>2026-05-08</td><td>AsyncEvGS: Asynchronous Event-Assisted Gaussian Splatting for Handheld Motion-Blurred Scenes<br><a href='http://arxiv.org/pdf/2605.07192'>论文</a> | <a href='https://openimaginglab.github.io/AsyncEvGS/'>代码</a></td><td>◆ 3D reconstruction methods such as 3D Gaussian Splatting (3DGS) and Neural Radiance Fields (NeRF) achieve impressive photorealism but fail when input images suffer from severe motion blur.
◆ While event cameras provide high-temporal-resolution motion cues, existing event-assisted approaches rely on low-resolution sensors and strict synchronization, limiting their practicality for handheld 3D capture on common devices, such as smartphones.
◆ We introduce a flexible, high-resolution asynchronous RGB-Event dual-camera system and a corresponding reconstruction framework.</td></tr>
<tr><td>2026-05-04</td><td>HumanSplatHMR: Closing the Loop Between Human Mesh Recovery and Gaussian Splatting Avatar<br><a href='http://arxiv.org/pdf/2605.02784'>论文</a></td><td>◆ Accurately recovering human pose and appearance from video is an essential component of scene reconstruction, with applications to motion capture, motion prediction, virtual reality, and digital twinning.
◆ Despite significant interest in building realistic human avatars from video, this paper demonstrates that existing methods do not accurately recover the 3D geometry of humans.
◆ ViT-based approaches are not consistently reliable and can overfit to 2D views, while NeRF- and Gaussian Splatting-based avatars treat pose and appearance separately, limiting rendering generalization to new poses.</td></tr>
<tr><td>2026-05-03</td><td>GETA-3DGS: Automatic Joint Structured Pruning and Quantization for 3D Gaussian Splatting<br><a href='http://arxiv.org/pdf/2605.02086'>论文</a></td><td>◆ 3D Gaussian splatting (3DGS) is a state-of-the-art representation for real-time photorealistic novel-view synthesis, yet a single high-fidelity scene typically occupies hundreds of megabytes to several gigabytes, exceeding the budgets of mobile, immersive, and volumetric video platforms.
◆ Existing 3DGS compression methods (e.g., HAC++, FlexGaussian, LP-3DGS) treat pruning, quantization, and entropy coding as separate stages and rely on hand-tuned heuristics (opacity thresholds, fixed bit-widths, SH truncation), limiting cross-scene generalization and preventing users from specifying a target rate or quality budget.
◆ We propose GETA-3DGS, to our knowledge the first end-to-end automatic joint structured pruning and quantization framework for 3DGS.</td></tr>
<tr><td>2026-05-01</td><td>GOR-IS: 3D Gaussian Object Removal in the Intrinsic Space<br><a href='http://arxiv.org/pdf/2605.00498'>论文</a> | <a href='https://applezyh.github.io/GOR-IS-project-page/'>代码</a></td><td>◆ Recent advances in Neural Radiance Fields (NeRF) and 3D Gaussian Splatting (3DGS) have made it standard practice to reconstruct 3D scenes from multi-view images.
◆ Removing objects from such 3D representations is a fundamental editing task that requires complete and seamless inpainting of occluded regions, ensuring consistency in geometry and appearance.
◆ Although existing methods have made notable progress in improving inpainting consistency, they often neglect global lighting effects, leading to physically implausible results.</td></tr>
<tr><td>2026-05-11</td><td>Beyond Heuristics: Learnable Density Control for 3D Gaussian Splatting<br><a href='http://arxiv.org/pdf/2605.00408'>论文</a> | <a href='https://github.com/AaronNZH/LeGS'>代码</a></td><td>◆ While 3D Gaussian Splatting (3DGS) has demonstrated impressive real-time rendering performance, its efficacy remains constrained by a reliance on heuristic density control.
◆ Despite numerous refinements to these handcrafted rules, such methods inherently lack the flexibility to adapt to diverse scenes with complex geometries.
◆ In this paper, we propose a paradigm shift for density control from rigid heuristics to fully learnable policies.</td></tr>
<tr><td>2026-05-04</td><td>Safe Navigation using Neural Radiance Fields via Reachable Sets<br><a href='http://arxiv.org/pdf/2604.26899'>论文</a></td><td>◆ Safe navigation in cluttered environments is an important challenge for autonomous systems.
◆ Robots navigating through obstacle ridden scenarios need to be able to navigate safely in the presence of obstacles, goals, and ego objects of varying geometries.
◆ In this work, reachable set representations of the robot&#x27;s real-time capabilities in the state space can be utilized to capture safe navigation requirements.</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='keypoint-detection'>Keypoint Detection</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-12</td><td>Fast and Accurate Prediction of Lattice Thermal Conductivity via Machine Learning Surrogates<br><a href='http://arxiv.org/pdf/2605.11610'>论文</a></td><td>◆ 本文首次对15种晶格热导率预测替代模型在Phonix数据库（6,966条目）上进行系统基准测试，评估其在随机、空间群分离和分布外（OOD）划分下的性能。  
◆ 将模型明确划分为三类：基于物理信息的特征描述+机器学习、端到端深度神经网络、预训练MLIP嵌入+机器学习，建立了统一的模型分类框架。  
◆ 通过空间群分离和OOD划分揭示了模型在未见晶体对称性和极端热导率区间的外推能力，发现端到端深度神经网络（尤其是ALiEGNN）在OOD条件下表现最为鲁棒。  
◆ 发现结构表示的简化（如减少描述符维度）会导致模型性能系统性下降，强调了高质量结构特征的重要性。  
◆ 虽然替代模型的精度略低于第一性原理直接计算，但其计算成本降低数个数量级，可实现高效的高通量热电材料筛选，显著加速新材料发现。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.05.14
