# 计算机视觉领域最新论文 (2026.05.18)

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
<tr><td>2026-05-15</td><td>LAPS: Improving Incremental LiDAR Mapping using Active Pooling and Sampling for Neural Distance Fields<br><a href='http://arxiv.org/pdf/2605.15496'>论文</a> | <a href='https://github.com/dongjae0107/LAPS'>代码</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行</td></tr>
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
</tbody>
</table>
</div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-14</td><td>Denoising-GS: Gaussian Splatting with Spatial-aware Denoising<br><a href='http://arxiv.org/pdf/2605.14880'>论文</a></td><td>针对3D Gaussian Splatting在稀疏SfM初始化下产生的噪声基元问题，本文提出Denoising‑GS，将Gaussian优化视为空间感知去噪任务。该框架通过保持优化流的方向性、结合空间梯度、估计基元不确定性以及在稀疏区域选择性分裂，实现更紧凑且保真的新视角合成，并在多个基准数据集上取得领先性能。  
◆ 提出把3DGS优化建模为去噪过程，强调空间结构的保留与引导。  
◆ 设计保留空间优化流的优化器，使去噪过程连贯且方向明确。  
◆ 引入空间梯度去噪策略，确保相邻基元的梯度一致更新。  
◆ 开发不确定性驱动的去噪模块，对噪声或冗余基元进行剪枝，并采用空间一致性细化策略在稀疏区域选择性分裂，以维持结构完整。</td></tr>
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
<tr><td>2026-05-15</td><td>Beyond Collision Avoidance: Multi-Robot Yielding and Spatial Affordance in Emergency Evacuations<br><a href='http://arxiv.org/pdf/2605.16115'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行</td></tr>
<tr><td>2026-05-15</td><td>Constrained MPC-Based Motion Planning for Morphing Quadrotors in Ultra-Narrow Passages under Limited Perception<br><a href='http://arxiv.org/pdf/2605.15999'>论文</a> | <a href='https://github.com/harshjmodi1996/morphocopter_mpc}{Github'>代码</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行</td></tr>
<tr><td>2026-05-15</td><td>Reactive Robot-Centric Safety for Autonomous Navigation in Constrained and Dynamic Environments<br><a href='http://arxiv.org/pdf/2605.15782'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行</td></tr>
<tr><td>2026-05-15</td><td>PCASim: Promptable Closed-loop Adversarial Simulation for Urban Traffic Environment<br><a href='http://arxiv.org/pdf/2605.15654'>论文</a> | <a href='https://zhenhaooo.github.io/PCASim.github.io/'>代码</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行</td></tr>
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
<tr><td>2026-05-13</td><td>HCSG: Human-Centric Semantic-Geometric Reasoning for Vision-Language Navigation<br><a href='http://arxiv.org/pdf/2605.13321'>论文</a> | <a href='https://haoxuanxu1024.github.io/HCSG/'>代码</a></td><td>本文提出 HCSG，首个面向视觉‑语言导航的人类中心框架，旨在动态室内环境中实现安全、社交智能的导航。  
◆ 统一的人类理解模块融合几何预测与基于视觉‑语言模型的语义解释。  
◆ 将语义‑几何融合表示嵌入拓扑地图，实现指令条件的规划。  
◆ 引入社交距离损失约束，确保交互距离符合社会规范。  
◆ 在 HA‑VLNCE 基准上实现成功率提升 14%、碰撞率降低 34% 的显著改进。</td></tr>
</tbody>
</table>
</div>

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-15</td><td>Fast Expanding Safe Circular Regions for Efficient Local Path Planning<br><a href='http://arxiv.org/pdf/2605.16009'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行</td></tr>
<tr><td>2026-05-15</td><td>Reactive Robot-Centric Safety for Autonomous Navigation in Constrained and Dynamic Environments<br><a href='http://arxiv.org/pdf/2605.15782'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行</td></tr>
<tr><td>2026-05-15</td><td>NavRL++: A System-Level Framework for Improving Sim-to-Real Transfer in Reinforcement Learning-Based Robot Navigation<br><a href='http://arxiv.org/pdf/2605.15559'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行</td></tr>
<tr><td>2026-05-15</td><td>Terrain Consistent Reference-Guided RL for Humanoid Navigation Autonomy<br><a href='http://arxiv.org/pdf/2605.15517'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行</td></tr>
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
<tr><td>2026-05-13</td><td>Interactively visualizing biological multilayer networks using MiRA<br><a href='http://arxiv.org/pdf/2605.09597'>论文</a></td><td>本文提出 MiRA（Multilayer Interactive Rendering Application），一个无需安装、基于浏览器的生物多层网络可视化工具。MiRA 支持七种互补的可视化模式，能够在空间、时间和交互类型等维度上直观呈现网络结构。该系统提供交互式操作，包括缩放、筛选、节点高亮和路径追踪，帮助研究者快速探索复杂网络的细节。MiRA 采用轻量化前端技术，实现跨平台兼容和流畅渲染，适合科研与教学场景。通过提供即开即用的可视化环境，MiRA 降低了多层网络分析的技术门槛。

◆ 完全基于浏览器，无需本地安装，降低使用门槛  
◆ 提供七种互补的可视化模式，覆盖空间、时间、交互类型等多维度网络展示  
◆ 支持交互式操作（缩放、筛选、高亮、路径追踪等），提升复杂网络的导航效率  
◆ 采用轻量化前端技术，实现跨平台兼容和流畅渲染性能  
◆ 专为生物学多层网络设计，兼顾教学演示和科研探索的双重需求</td></tr>
</tbody>
</table>
</div>

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-05-15</td><td>Fast Expanding Safe Circular Regions for Efficient Local Path Planning<br><a href='http://arxiv.org/pdf/2605.16009'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行</td></tr>
<tr><td>2026-05-15</td><td>Constrained MPC-Based Motion Planning for Morphing Quadrotors in Ultra-Narrow Passages under Limited Perception<br><a href='http://arxiv.org/pdf/2605.15999'>论文</a> | <a href='https://github.com/harshjmodi1996/morphocopter_mpc}{Github'>代码</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行</td></tr>
<tr><td>2026-05-15</td><td>Optimizing Line Segment Inspection with Limited-Range Drones<br><a href='http://arxiv.org/pdf/2605.15765'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行</td></tr>
<tr><td>2026-05-15</td><td>Wind-Aware Optimal Trajectory Planning for Efficient Gliding of Fixed-Wing Aerial Systems<br><a href='http://arxiv.org/pdf/2605.15619'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行</td></tr>
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
</tbody>
</table>
</div>


<h2>GitHub 实验室仓库监控</h2>

<h3>HKU-MARS (港大火星实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>4677</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4053</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2400</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1603</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1589</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1399</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1245</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1201</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>913</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>912</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>881</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>789</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>781</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>737</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>718</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>696</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>629</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>619</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>613</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>583</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>558</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>548</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>526</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>498</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>458</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>431</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>381</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>342</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>331</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>260</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>250</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>233</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>218</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>201</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>197</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>194</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>146</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>144</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>140</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>116</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2837</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1625</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1351</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1097</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1032</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>866</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>695</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>655</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>653</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>617</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>582</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>572</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>562</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>557</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>549</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>511</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>478</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>462</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>439</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>437</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>334</td><td>A flexible submap-based framework towards spatio-t</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/reinmav-gym'>reinmav-gym</a></td><td>106</td><td>Reinforcement Learning framework for MAVs using th</td></tr>
<tr><td><a href='https://github.com/ethz-asl/active_grasp'>active_grasp</a></td><td>106</td><td>Closed-loop next-best view planning for grasp dete</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waverider'>waverider</a></td><td>106</td><td>RMPs on multi-resolution occupancy maps for effici</td></tr>
<tr><td><a href='https://github.com/ethz-asl/navrep'>navrep</a></td><td>104</td><td>navrep</td></tr>
<tr><td><a href='https://github.com/ethz-asl/eth_supermegabot'>eth_supermegabot</a></td><td>102</td><td>Instructions for ETH center for robotics summer sc</td></tr>
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>101</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.05.18
