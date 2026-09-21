# 计算机视觉领域最新论文 (2026.09.21)

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
<tr><td>2026-09-18</td><td>SFVO: Decoupled Confidence-Guided Stereo-Flow Visual Odometry with Bidirectional PnP<br><a href='http://arxiv.org/pdf/2609.21754'>论文</a></td><td>SFVO是一种对应关系驱动的立体视觉里程计框架，直接建立在预训练立体匹配与光流模型之上，以缓解单目尺度模糊并降低立体VO建模复杂度。
它不直接从图像学习位姿，而是把学习到的立体和时间对应关系映射为几何约束，并预测哪些点可信。
◆提出解耦置信图，分别建模旋转与平移的置信度，更好贴合视觉对应和6自由度变换的不同特性。
◆统一利用预训练立体匹配与光流的互补几何信息，构建稠密对应驱动的几何约束，而非端到端回归位姿。
◆在室内外数据集上实现鲁棒准确的位姿估计和强泛化能力，验证了对应驱动立体VO的有效性。</td></tr>
<tr><td>2026-09-18</td><td>HAT: Hypothesis-Anchored Tracking for Video Monocular Spacecraft Pose Estimation<br><a href='http://arxiv.org/pdf/2609.21597'>论文</a></td><td>论文提出HAT，一种利用帧间运动在配准与融合前筛选CAD姿态假设的因果视频单目航天器6DoF位姿估计框架。
◆ 不逐帧独立选择最高分假设，而是保留竞争方向历史，并以选定姿态锚定单目SLAM估计的相对轨迹。
◆ 通过稀疏锚点和姿态融合实现初始化后的逐帧输出，同时保持因果性，不修订过去估计。
◆ 仅需标定RGB序列、度量CAD模型和目标图像区域，预训练姿态与SLAM网络无需目标特定训练或微调。
在SPARK-2024、SwissCube、SHIRT和YCB-Video上，Mega-HAT与Pico-HAT相比独立MegaPose和PicoPose分别降低平均位姿误差9.4%和23.9%，持续FPS提升3.76倍和2.42倍，消融验证了组件贡献及不修订历史的影响。</td></tr>
<tr><td>2026-09-18</td><td>Adaptive World Memory 3D Foundation Model for Scalable 3D Mapping, Localization, and Rendering<br><a href='http://arxiv.org/pdf/2609.21502'>论文</a> | <a href='https://github.com/dtc111111/AWM-3DFM}{https://github.com/dtc111111/AWM-3DFM}'>代码</a></td><td>本文提出一个以记忆为中心的3D基础模型，面向可扩展机器人定位、重建与高斯渲染，弥补现有模型在持久记忆、可扩展性和可渲染场景建模上的不足。  
◆ 提出自适应世界记忆机制，结合Transformer门控更新与测试时时空调节，通过时间状态演化和空间观测—状态一致性控制长序列中的token更新与遗忘。  
◆ 将记忆组织为局部子图，并融合渐进式建图与跟踪、回环检测及基于SL(4)的全局优化，兼顾局部精度与全局一致性。  
◆ 设计高斯重建头，把记忆增强特征解码为可渲染图元，在单一模型中统一相机位姿估计、稠密点云重建和真实感渲染。  
在公开基准及多机器人平台自采数据上，该模型在轨迹精度、重建完整性和渲染质量上优于现有3D基础重建与SLAM基线。  
这些结果支持自适应记忆作为持久机器人世界建模的基础，且数据集和代码将公开。</td></tr>
<tr><td>2026-09-18</td><td>Cube-Splat: High-Fidelity 360° Gaussian Splatting SLAM via Cubemap Factorization and Adjoint-Consistent Optimization<br><a href='http://arxiv.org/pdf/2609.21347'>论文</a> | <a href='https://github.com/guoxf304/CubeSplat'>代码</a></td><td>Cube-Splat是首个面向全景图像的高斯泼溅SLAM框架，通过将每个360°帧分解为四个固定朝向、共享同一光心的虚拟针孔视图，解决了传统针孔SLAM难以直接处理全景输入的问题。
◆ 提出以立方图前脸作为主位姿状态，并利用伴随映射聚合各面梯度，使多面观测能一致更新单一状态并严格保持跨视图几何一致性。
◆ 设计基于聚合立方图光线的建图模块，稠密化并优化各向异性高斯，实现高保真、稠密的全景重建。
◆ 发布SynPano，一个可扩展、照片级真实、支持参数化复杂轨迹和多模态真值的合成全景数据集，用于严格评测全景SLAM。
◆ 在PALVIO、OmniBlender和SynPano等室内外基准上，Cube-Splat在跟踪精度与重建保真度上均达到SOTA。
◆ 开源代码与SynPano数据集，为全景高斯泼溅SLAM提供可复现平台。</td></tr>
<tr><td>2026-09-18</td><td>OmniCalib: Target-Free, Task-Structured Self-Calibration for Humanoid Robots<br><a href='http://arxiv.org/pdf/2609.19582'>论文</a></td><td>OmniCalib提出一种无标定物、任务结构化的人形机器人自校准流程，仅用机器人自身运动和板载传感，统一校准上肢14个臂关节零点及腕部、胸部相机外参，并扩展至下肢与多相机头部。
◆ 任务结构化建模：每个模块把机器人原生任务匹配到参数块，检查可观测性，并只将受支持的校正写回CAD模型。
◆ 无靶深度ICP：无需任何标定靶即可恢复14个臂关节零点和全部RGB-D外参，点面残差2.09 mm，左/右腕与胸相机外参修正约6.33–10.56 mm、0.929–1.74度。
◆ 下肢零位恢复：四个静态双支撑姿态恢复12个下肢关节零位，注入偏移RMS误差0.063度。
◆ 头部多相机标定：融合多相机视觉里程计、腿式里程计和动态补偿，仅平面行走取得平均SO(3)误差1.061度，最佳0.775度，接近iKalibr的0.902度。
◆ 可验证性：相同注入偏移下ICP与ArUco均以优于0.1度编码器分辨率恢复14个关节零点，注入恢复和留出测试验证各可观测块。</td></tr>
<tr><td>2026-09-17</td><td>Noctif3R: Feed-Forward Monocular Real-Time SLAM for Photon-Limited Scenes on Embedded Hardware<br><a href='http://arxiv.org/pdf/2609.21114'>论文</a></td><td>针对暗光下单目实时SLAM在嵌入式硬件上的交叉空白，论文量化了现有方法在低信噪比下常输出无信息轨迹：九个最暗档中DROID-SLAM全失败，VGGT-SLAM/CUT3R为八次、pi^3七次、DPV-SLAM四次。
作者提出Noctif3R（SYS），以低光前馈点图前端和显式匹配门控实现实时跟踪，在可跟踪时误差最低，并在86.5%全黑帧的真实Spot视频中停止输出而非给虚假位姿。
◆ 低光前馈点图前端与显式匹配门控，提升极暗低SNR下的有效跟踪并抑制无信息轨迹。
◆ Jetson AGX Orin嵌入式执行路径，将建图、关键帧和后端降至384像素、跟踪降至256像素。
◆ 两项逐帧位姿求解修复带来可复现帕累托改进，吞吐达1.28至1.42倍，误差降至0.964至0.68倍，峰值GPU显存少47%，每姿能耗少29%。
◆ 构建位精确可复现噪声阶梯、重标注真实暗曝光和Spot暗房视频阶梯，系统评测暗光SLAM。</td></tr>
<tr><td>2026-09-17</td><td>MAPLE-RF: Efficient Probabilistic RF Source Localization in Partially Explored Environments<br><a href='http://arxiv.org/pdf/2609.21026'>论文</a></td><td>本文聚焦部分探索地图中的单快照射频源定位，输出发射源位置的后验分布，并比较两种方法。  
◆ 将数字孪生式逐候选射线追踪定位扩展到部分地图，把未探索区域当作自由空间，并采用混合地图覆盖训练。  
◆ 提出MAPLE-RF，将估计到达路径角和信噪比编码为与地图已知度、占据及视距可见性对齐的网格通道，用U-Net一次前向为全部候选位置打分，推理时不做传播模拟。  
◆ 通过射线追踪仿真证明混合地图覆盖训练对两种方法都必要，且MAPLE-RF查询成本不依赖传播模型，比通用射线追踪全网格查询低两个数量级以上。  
实验显示数字孪生法在多数单快照指标上更准，MAPLE-RF精度接近；两者均优于高斯和高斯混合基线。  
在由自身估计引导的探索路径上，融合MAPLE-RF后验比对比方法在真实源附近赋予更高概率。</td></tr>
<tr><td>2026-09-17</td><td>Towards Effective Visual-Inertial SLAM with Passive-Only Sensors for Low-Cost Autonomous Underwater Vehicles<br><a href='http://arxiv.org/pdf/2609.21015'>论文</a></td><td>本文针对低成本自主水下航行器，研究仅依赖被动式消费级传感器的视觉惯性SLAM，以替代DVL、USBL等昂贵工业套件。作者在低于1万美元的开源AUV平台上，使用立体相机、MEMS IMU和深度传感器，在完全无约束6自由度水下环境中验证导航性能。
◆ 证明仅用被动式低成本传感器即可实现可用且高质量的VI-SLAM，无需DVL或USBL等昂贵硬件。
◆ 系统评估现成SLAM包在真实无缆水下任务中的表现，并针对水下视觉与物理挑战提出传感器融合优化。
◆ 提供面向大众的低成本水下SLAM基准，为苛刻实时海洋任务建立可复现的性能预期。
这些工作表明，先进海洋机器人导航可突破财务门槛，更广泛地服务科研与爱好者社区。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

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
<tr><td>2026-09-16</td><td>Cross-Lingual Parkinson&#x27;s Disease Severity Assessment Using Pre-trained Speech Embeddings: A Multi-Class Evaluation<br><a href='http://arxiv.org/pdf/2609.20875'>论文</a></td><td>本文针对语音基础模型在帕金森病严重程度跨语言多类评估中泛化性不足、标注数据有限且缺乏可解释性的问题，选取四个开源语音基础模型，在三个数据集上开展零样本与k-shot跨语言多类严重程度评估，并分析数据属性、预处理和适应策略的影响。
◆ 系统评估四类开源预训练语音嵌入在跨语言帕金森病严重程度多类分类中的迁移能力，填补该场景下多类跨语言评估的空白。
◆ 构建覆盖三个数据集、零样本与k-shot设置的跨语言多类评估框架，并揭示性能对数据集属性、预处理和适应策略高度敏感。
◆ 发现预训练语音嵌入可实现有意义的跨语言迁移，同时将误分类归因于说话人差异和非典型语音模式，强调更鲁棒的特征建模与可解释性对临床可靠洞见的重要性。
总体而言，该研究证明跨语言PD严重程度评估具有可行性，但稳健临床应用仍需进一步改进特征提取、模型适应与可解释方法。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

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

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

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

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vlm'>Robot VLM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-18</td><td>When Should a Failing Robot Ask? Initiating Corrective Human-Robot Dialogue from Audited Sensor Evidence<br><a href='http://arxiv.org/pdf/2609.21942'>论文</a></td><td>本研究构建了故障真因已知、可审计传感器证据的模拟基准，系统测量相机与力传感等对故障原因的可诊断性，并检查数据泄漏。
◆ 提出从注入真因的失败中量化各传感器证据价值，而非依赖模型自述置信。
◆ 揭示视觉语言模型诊断表面化：仅调整拒绝选项位置，拒绝率从78-100%降到0-6%，准确率不超多数类基线，置信无预测力。
◆ 发现将力数据以十行文本提供后，六个模型中四个首次超过基线，表明失败多因传感器数据缺失而非能力缺失。
◆ 将“行动、咨询自身传感器、问人”形式化为三动作决策，最优策略由实测准确率与问题成本决定，模型却不遵循且忽略四倍成本变化。
◆ 证明一问人可将准确率提至回答者可靠性0.70-0.81，主张问询决策应绑定实测准确率与成本，而非模型置信。</td></tr>
<tr><td>2026-09-18</td><td>Scaling Vision-Language Reward Learning for Robot Manipulation in Parallel Simulation<br><a href='http://arxiv.org/pdf/2609.21767'>论文</a> | <a href='https://github.com/rapid-vlm/rapid-vlm-rl'>代码</a></td><td>本文提出 RAPID，面向 VLM 替代人工标注的机器人操作偏好奖励学习，解决顺序 API 请求与单环境采集导致的慢和贵问题，并在 IsaacLab 五个 Franka Panda 任务上验证。

◆ 将 GPU 并行 rollout 与数据感知策略更新耦合，首次大幅压缩训练时间，匹配两阶段提示下平均运行从 9.18 小时降至 3.13 小时。
◆ 采用单请求偏好标注替代顺序 API 调用，在 Gemma 3 12B 与 GPT-4.1 mini 上均降低标注延迟和成本。
◆ 引入自动奖励稳定机制，提升奖励学习稳定性。
◆ 使用代表性图像采样，提高 VLM 标注数据的信息密度与多样性。

全部组件启用后，训练仅需 1.15 小时，每轮 API 调用从 19840 降至 896，最终成功率从 86.3% 升至 98.7%，实现 8.0 倍端到端加速和 95.5% API 使用降低。</td></tr>
<tr><td>2026-09-18</td><td>ForceTwin: Physics-informed Digital Twins for Robotic Manipulation from Instrumented Human Interaction<br><a href='http://arxiv.org/pdf/2609.21751'>论文</a> | <a href='https://timengelbracht.github.io/forcetwin-website/'>代码</a></td><td>本文提出ForceTwin，一种从带力传感手持夹爪的人机交互中识别铰接物体物理信息数字孪生的系统，可同步获取位姿与交互力并估计运动学及参数化动力学。
◆ 构建物理信息数字孪生识别流程，利用仪器化人类交互而非仅视觉语言先验，直接观测操纵所需力。
◆ 在惯性、库仑摩擦、粘滞阻尼等参数之外，引入结构化神经残差，捕捉随构型与速度变化的状态依赖机构力。
◆ 相比VLM先验，惯性参数误差近乎减半，并弥补标准资产格式无法表达状态依赖机构动力学的不足。
◆ 将孪生作为阻抗控制前馈动力学模型，在Spot和Franka FR3九组物体上实现87%目标完成率，优于VLM先验60%和仅运动学57%，强机构物体提升最大。
◆ 利用识别孪生训练全身门穿越策略并成功真机部署，验证了从人类交互到机器人操纵的迁移价值。</td></tr>
<tr><td>2026-09-18</td><td>DPed-VLN: A Benchmark for Socially Compliant Vision-and-Language Navigation in Dynamic Pedestrian Environments<br><a href='http://arxiv.org/pdf/2609.21504'>论文</a></td><td>本文提出DPed-VLN，一个基于Habitat 3.0的动态行人视觉语言导航基准，包含33,093个导航回合、全局与先验增强配对指令、ORCA控制人形行人、社会约束专家路径，以及联合评估导航效率与社交安全的指标。
◆ 将动态行人线索通过先验增强指令与普通目标导向路线引导分离，支持受控分析。
◆ 采用ORCA控制人形行人与社会约束专家路径，并设计兼顾效率与安全的评价体系。
◆ 提出DPet动态行人感知策略网络，以强化学习和模仿学习训练。
◆ 将NaVILA、StreamVLN等VLM导航模型经LoRA适配到该基准，实验显示适配可提升成功与安全指标，尤其降低StreamVLN碰撞率。
实验表明，DPet-RL在SR、SPL和STL上取得最高结果，验证该基准对社会合规动态行人VLN研究的价值。</td></tr>
<tr><td>2026-09-18</td><td>FORTE: Task-Adaptive Force Capability Optimization for Mobile Manipulators<br><a href='http://arxiv.org/pdf/2609.21497'>论文</a> | <a href='https://github.com/yeying256/FORTE'>代码</a></td><td>本文提出面向冗余移动机械臂的任务自适应力能力优化框架FORTE，解决现有方法忽略任务力需求或盲目最大化力能力、牺牲灵巧性的问题。
◆利用视觉语言模型从RGB图像和任务描述推断物体物理属性，生成包含重力和惯性需求的目标任务力序列。
◆定义任务导向力能力指标，即任务力不确定球与动态残余力多面体之间的有符号距离，衡量任务需求与剩余驱动能力的匹配度。
◆将该指标与可操作度、关节限位规避、轨迹平滑和基座振荡抑制结合，构建全身多目标轨迹优化问题。
在移动机械臂举升与单点保持实验中，不同负载下均能重载提供足够力能力、轻载保持高可操作度，形成任务自适应平衡，优于固定最大化力能力与仅可操作度基线。
核心实现已开源。</td></tr>
<tr><td>2026-09-18</td><td>A Scene Language Model for Open-Vocabulary Scene Mapping<br><a href='http://arxiv.org/pdf/2609.21400'>论文</a> | <a href='https://goldengait.github.io/scenelm/'>代码</a></td><td>SceneLM的核心是用单一视觉语言模型直接维护开放词汇3D场景地图，将完整场景表示为结构化文本对象列表并作为唯一持久记忆。
◆ 摒弃传统工程化建图与特征存储，只保留轻量文本场景地图，显著降低内存和复杂度。
◆ 对每张输入图像读取当前场景状态，并通过添加、编辑、删除对象来迭代更新地图。
◆ 提出迭代式地图维护监督任务和自动标注流水线，可从无人工标签图像生成训练数据。
◆ 在语言检索与定位基准上以6至12倍更紧凑表示取得与完整专用系统相当的性能，并能在四足边缘设备在线运行。
这些结果表明，持久开放词汇3D场景地图可由单一视觉语言模型以轻量文本表示直接维护。</td></tr>
<tr><td>2026-09-18</td><td>ProTracer: Proprioception-Guided Failure Diagnosis in Robot Manipulation<br><a href='http://arxiv.org/pdf/2609.21369'>论文</a></td><td>本文提出面向机器人操作失败分析的 ProTracer 框架，覆盖二值失败检测、失败分类、解释生成与失败起点定位。
◆ 提出免训练的失败诊断方法，复用现有视觉语言模型并引入本体感觉信号，无需额外模型训练。
◆ 利用本体感觉动力学识别具有时间信息量的动作边界，并把机器人状态转化为结构化自然语言描述，与视觉观察联合推理。
◆ 构建 FailTime 基准，提供同步视觉与本体感觉观测，同时评估传统失败诊断和失败起点定位。
实验表明 ProTracer 在传统诊断与新起点定位任务上均表现良好，说明本体感觉推理对细粒度时序失败分析至关重要。</td></tr>
<tr><td>2026-09-18</td><td>NaViRrator: Robot Navigation from Human-Readable Maps through a Learned Visual Route<br><a href='http://arxiv.org/pdf/2609.21316'>论文</a></td><td>本文提出NaViRrator，将人类可读地图上用户指定的起点和终点转化为预训练VLN策略可用的导航指令。  
◆ RouteScribe分离路线推断与语言描述，先在地图图像坐标中生成显式路线脚手架，再由预训练VLM转换为导航指令。  
◆ 提出起终点连线条件流匹配SGL-CFM，将直线起终点航点序列变形为地图条件路线。  
◆ 执行时VLN策略仅接收指令和第一视角观测，地图与脚手架留在上游，支持替换执行器而无需重训地图到语言模块。  
真实实验表明其成功率和SPL优于直接地图生成指令、A*脚手架及Gaussian-source CFM。  
定性结果显示它能呈现更清晰显著转弯并更好保持预期动作序列，验证路线锚定语言是连接人类可读地图与预训练导航策略的模块化接口。</td></tr>
<tr><td>2026-09-18</td><td>KnowDemo: Knowledge-Guided Robot Demonstration Generation from Human Videos<br><a href='http://arxiv.org/pdf/2609.21229'>论文</a> | <a href='https://zhiyuan-gao.github.io/knowdemo/'>代码</a></td><td>论文针对从人类视频生成机器人演示时，运动参考适配限制行为多样性且任务与场景理解不足导致无效候选的问题，提出 KnowDemo，利用人类视频中的结构化操作知识为目标工作空间生成多样演示。
◆ 提出基于VLM的知识抽取与推理模块，区分任务需求与演示特定选择，并推断任务条件、演示参考和允许执行变化。
◆ 将结构化知识解析到目标场景实体与几何，引导候选生成和筛选，再经运动规划与仿真验证，减少无效候选。
◆ 生成演示具有多模态行为，包括替代接触策略和有效子任务顺序，并带结构化执行标签。
实验表明，该方法能发现仅靠参考配置无法获得的额外可执行模式，并通过任务引导抓取采样提升候选规划成功率；用仿真数据微调预训练π0.5后，在三个任务上实现仿真到真实迁移。</td></tr>
<tr><td>2026-09-18</td><td>FOCAL-VLA: Subtask-Guided Geometry Distillation and Implicit World Modeling for Vision-Language-Action Models<br><a href='http://arxiv.org/pdf/2609.21228'>论文</a> | <a href='https://zhiyuan-gao.github.io/FOCAL-VLA/'>代码</a></td><td>现有VLA直接由当前2D观测映射动作，空间与时间理解不足，且全场景几何监督和未来预测易受冗余信息干扰。FOCAL-VLA提出子任务引导几何蒸馏与隐式世界建模，学习当前空间结构和未来交互动态，并联合指导动作生成。
◆ 子任务引导几何蒸馏：将VGGT几何知识迁移至VLA，通过几何隐变量与子任务相关图像区域特征对齐，使几何学习聚焦当前交互。
◆ 隐式世界建模：利用Track4World提取当前与未来演示帧特征，捕捉当前交互的未来3D演化。
◆ 双表示联合驱动且推理高效：两种互补表示共同生成动作，推理时无需运行VGGT或Track4World，避免额外开销。
◆ 实验验证：在仿真基准和真实操作任务上均超越基线，证明其能提升精确与长程操作性能。</td></tr>
<tr><td>2026-09-17</td><td>DEXTERA: From a Single Image to Deployable Dexterous Manipulation via Real-to-Sim-to-Real<br><a href='http://arxiv.org/pdf/2609.21045'>论文</a></td><td>DEXTERA提出自动化real-to-sim-to-real框架，仅凭单张RGB图像即可生成灵巧操作的可部署策略，并用四阶段统一流程完成单图场景分解与VLM物理参数推断、度量对齐与机器人校准、仿真任务基元与VR轨迹合成、共享多模态策略接口。实验覆盖13个任务-本体对、2个灵巧机器人平台和6种策略架构，验证了优于生成基线的视觉与几何重建、跨域轨迹重放的物理一致性，以及零样本真机部署和联合训练带来的成功率提升。
◆ 单图自动构建带物理参数的交互式数字孪生，降低人工建模成本并缩小sim-to-real差距。
◆ 度量场景对齐、物体规范化与形态平衡机器人校准，提升跨域交互一致性。
◆ 可扩展仿真任务基元、VR遥操作与物体中心轨迹合成，统一支持模仿学习和强化学习。
◆ 仿真-真实联合训练将平均物理策略成功率从29.2%提升至61.9%，并适配多样策略架构。</td></tr>
<tr><td>2026-09-17</td><td>Catch Me If You Can: Real-Time Feedback Denoising for Responsive VLAs<br><a href='http://arxiv.org/pdf/2609.21022'>论文</a></td><td>论文提出VLA-Feedback，以双时间尺度架构应对扩散式VLA动作块开环执行时动态场景响应不足的问题。
◆ 将低频扩散规划与高频视觉反馈结合，在保持规划表达力的同时实现实时校正。
◆ 保留扩散模型最后一步去噪作为轻量反馈接口，用最新观测在执行前修正每个动作。
◆ 无需重跑完整视觉-语言扩散模型，即可完成实时动作纠错并提升响应性。
在静态LIBERO任务上匹配GR00T，动态仿真平均成功率从27.5%提升到85.0%，真实机器人从51%提升到73%。</td></tr>
<tr><td>2026-09-17</td><td>PIVOT: Physically Informed Vision-Language Off-Road Traversability for Field Robot Navigation<br><a href='http://arxiv.org/pdf/2609.20983'>论文</a></td><td>本文提出PIVOT，一种物理信息引导的视觉语言越野可通行性导航系统，用VLM语义推理增强传统几何规划。其核心贡献在于让VLM地形评估与真实物理测量挂钩，而非仅依赖语义判断。
◆ 提出基于预测—测量相关性的物理接地方法，将VLM预测的通行能量成本、机器人振动和车轮打滑与实测数据关联，并按相关性加权为统一可通行性分数。
◆ 设计两级导航架构，默认使用几何规划，仅当几何模式找不到路径时才触发VLM语义重规划，从而兼顾鲁棒性与计算效率。
在混合地形约6.4公里路线五次闭环试验中，系统将整体自主性从59.6%提高到97.0%，人工干预从11次降至3次。同时平均干预间隔从69.2米提高到412.9米，表明物理接地VLM评估能显著突破纯几何导航局限，并保持高效规划。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-visual-semantic-recognition'>Robot Visual Semantic Recognition</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-18</td><td>AgenticSwarm: Semantic Perception and Adaptive Task Allocation for Heterogeneous Multi-UAV Missions<br><a href='http://arxiv.org/pdf/2609.21716'>论文</a></td><td>AgenticSwarm提出面向异构多无人机任务的智能体框架，将语义感知、约束任务分配与自适应执行统一起来。
◆它用智能体解析航拍图像和自然语言指令，构建连接感知对象、区域、任务需求、能力约束与任务依赖的落地任务表示。
◆它在分配前纳入障碍感知路径可行性、能耗和保护返航要求，实现受约束的可行任务分配。
◆它在无人机故障、电池退化或任务变更时，从当前系统状态重建剩余任务，同时保留已完成工作和侦察进度。
◆它采用SAM3感知管线，相比Grounding DINO+SAM2.1，类感知召回提高25.2个百分点，语义标签准确率提高29.5个百分点，并在五个Gazebo环境和室内真实环境验证。
消融显示，残差任务重规划使平均重复工作从0%升至61.7%，事件后恢复时间增加58.6%。</td></tr>
<tr><td>2026-09-18</td><td>PerSeM: Persistent Semantic Memory for Long-Horizon Open-Vocabulary UAV Mapping<br><a href='http://arxiv.org/pdf/2609.19542'>论文</a></td><td>PerSeM是一种免训练的持久语义记忆框架，面向长时程开放词汇无人机建图，旨在解决逐帧语义预测在重复观测和视角变化下的时序不一致问题。
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vpr'>Robot VPR</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-18</td><td>Multi-viewpoint Geo-localization with Event Cameras<br><a href='http://arxiv.org/pdf/2609.21219'>论文</a> | <a href='https://github.com/AdamDHines/megaevent'>代码</a></td><td>本文提出MegaEvent，一个面向多视角变化的事件相机视觉位置识别系统，旨在解决事件定位器视角鲁棒性不足与相关数据集稀缺问题。
◆ 将五个大规模带地理标签的帧式定位数据集通过Image-to-Event转换为合成事件流，用于预训练事件ViT骨干的微调。
◆ 采用多损失函数训练，使MegaEvent学习对视角变化鲁棒的场所识别特征。
◆ 提出Springfield-Event-VPR数据集，包含3.7km步行路线、三种相机朝向，总计11.1km，用于挑战多视角定位。
◆ 在三个事件定位数据集上取得平均82% Recall@1，领先次优事件方法20个召回点，并优于帧式VPR直接用于事件帧8至26个召回点；在新数据集上领先最强基线9个召回点。
代码已开源。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5201</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4662</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2454</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1643</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1621</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1510</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1335</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1299</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1083</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>1042</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>943</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>809</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>783</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>747</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>742</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>727</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>680</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>666</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>632</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>619</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>609</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>580</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>570</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>533</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>510</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>461</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>454</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>364</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>348</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>277</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>272</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>258</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>242</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>229</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>223</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>221</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>211</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>191</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1060</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>882</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>710</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>667</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>664</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>624</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>605</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>577</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>572</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>571</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>553</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>518</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>510</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>464</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>456</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>451</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>334</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>313</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>307</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>301</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>285</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>279</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>258</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>224</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>208</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/data-driven-dynamics'>data-driven-dynamics</a></td><td>134</td><td>Data Driven Dynamics Modeling for Aerial Vehicles</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>132</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
<tr><td><a href='https://github.com/ethz-asl/phaser'>phaser</a></td><td>132</td><td>A robust pointcloud registration pipeline based on</td></tr>
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
> 更新于: 2026.09.21
