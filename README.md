# 计算机视觉领域最新论文 (2026.09.24)

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
<tr><td>2026-09-23</td><td>DAVIO: Dense Monocular-Inertial SLAM with Feed-Forward Initialization and Pose-Conditioned Mapping<br><a href='http://arxiv.org/pdf/2609.27702'>论文</a></td><td>本文提出DAVIO，一种仅用相机和IMU即可实时运行的稠密米制SLAM系统，解决传统VIO依赖视差且只能稀疏建图、前馈深度模型又缺乏米制尺度和重力的问题。
◆ 采用单一多视图深度模型Depth Anything 3同时完成启动初始化与姿态条件化建图。
◆ 启动时用五图像窗口与预积分IMU构成无特征线性系统，经鲁棒条件检查求解后，通过缓冲回放引导VIO滤波器，实现无需等待视差的快速米制启动。
◆ 跟踪时以滤波器米制位姿条件化深度模型，残差尺度仅沿视线校正，保留米制相机基线。
◆ 构建保重力子图图与漂移门控重访，持续精炼稠密地图。
在EuRoC上，DAVIO启动更早、定位误差更低，且在相同位姿下建图优于SOTA前馈建图器；在ORI上达到或优于SOTA，GT位姿换成真实里程计时退化更小，并开源了实时稠密米制SLAM代码。</td></tr>
<tr><td>2026-09-23</td><td>Know-Your-Scene (KYS)-SLAM: Hierarchical Semantic-Motion Priors for Feature Matching in Stereo Visual SLAM<br><a href='http://arxiv.org/pdf/2609.27509'>论文</a></td><td>本文提出KYS-SLAM，作为ORB-SLAM3的模块化扩展，把语义、全景与运动上下文从二元特征剔除重构为连续对应代价，在特征匹配阶段调制而非丢弃特征。
◆ 将上下文可信度表达为分级匹配代价，替代传统语义/动态SLAM的特征拒绝，保留BA依赖的几何支撑。
◆ 融合语义类别、实例身份与零样本运动分数的分层兼容性先验，约束结构合理性并降低独立运动物体特征权重。
◆ 设计训练无关运动评分模块，用深度感知自运动模型拟合背景光流，并以自校准、覆盖感知阈值分类全景段，仅惩罚有充分运动证据者。
◆ 在固定配置、无需逐序列调参下，21个双目序列上KITTI户外ATE RMSE降17.4%，EuRoC室内降27.7%，动态KITTI Tracking降6.6%，Virtual KITTI 2降17.8%至31.2%，无回归。</td></tr>
<tr><td>2026-09-22</td><td>TM-APR: Thermal Temporal-Memory Localization via Analytic Online Adaptation<br><a href='http://arxiv.org/pdf/2609.26766'>论文</a></td><td>本文针对热视觉位置识别在自主导航中环境依赖强、在线重训练开销大及动态非线性偏移难建模的问题，提出TM-APR框架。
◆ 首次将解析类增量学习（ACIL）与域不变VPR结合，揭示无梯度矩阵更新可形成优于常规微调的强基线。
◆ 发现ACIL与现代控制理论的代数等价，并将无迹传播、高斯混合划分与极小极大H∞优化嵌入更新循环，形成U-ACIL、GMM-ACIL和H∞-ACIL。
◆ 这些机制增强了对极端非线性热波动的鲁棒建模，缓解标准ACIL因线性假设导致的在线失效。
◆ 框架保证O(1)复杂度的精确闭式矩阵更新，无需反向传播，使在线学习延迟严格低于传感器采集间隔，消除实时SLAM轨迹跳变。</td></tr>
<tr><td>2026-09-22</td><td>ArborSplat: Online Semantic Gaussian Splatting SLAM for Orchards<br><a href='http://arxiv.org/pdf/2609.26315'>论文</a></td><td>ArborSplat提出面向果园的在线语义3D高斯泼溅SLAM，解决树干、棚架、果实等细长结构语义转移不可靠的问题。  
◆ 以LiDAR里程计跟踪，并直接在高斯地图上优化语义，摆脱纯外观驱动的优化限制。  
◆ 利用每个关键帧立体点云拟合地平面，并用类别特定高度带约束语义优化。  
◆ 在线融合多视图证据为语义点云，同时拒绝与局部地面或单目深度不一致的标签。  
◆ 通过类别约束细化为欠代表结构保留高斯容量，在低预算下提升树类训练视图精度。  
在苹果和梨园休眠、开花、采收期，12条全程路线ATE均低于0.5米；301帧共享片段上mIoU优于SGS-SLAM和GS3LAM，训练视图高0.23至0.50、留出高0.15至0.36，速度快1.7至7.5倍，SemGauss-SLAM全部显存不足。</td></tr>
<tr><td>2026-09-22</td><td>Unsigned Distance Maps on 2D Point Cloud Registration<br><a href='http://arxiv.org/pdf/2609.25932'>论文</a></td><td>本文面向激光里程计与SLAM中的二维点云配准，针对ICP每次迭代需最近邻搜索重算对应关系的问题，提出基于无符号距离图的方法。
◆ 在离散网格上预计算到最近参考点的欧氏距离及其空间导数，将逐迭代最近邻搜索替换为O(1)查表。
◆ 在SE(2)流形上推导点对点与点对平面误差模型，并用高斯-牛顿优化求解。
在合成基准与真实IILABS 3D数据集上，预计算点对点变体优于其解析对应版本，并与点对平面方法取得有竞争力的激光里程计漂移。
◆ 预计算梯度能在传感器噪声下正则化对应关系，提升配准稳健性。</td></tr>
<tr><td>2026-09-22</td><td>Dual Covariance Gaussian Splatting SLAM: Decoupling Rendering and Registration for Robust Real-Time Tracking<br><a href='http://arxiv.org/pdf/2609.25746'>论文</a></td><td>论文提出双协方差高斯泼溅SLAM，解决3DGS SLAM中同一高斯协方差既要优化渲染又要服务配准所导致的冲突。
◆ 每个高斯只保留一个均值，但设置两个协方差：渲染协方差由建图器优化，跟踪协方差来自RGB-D传感器噪声模型。
◆ 将跟踪协方差作为图像角点的高斯锚点，在深度几何较弱的约束方向上补充配准信息。
◆ 在TUM RGB-D、ScanNet、Replica以及RealSense D435i采集的轮式与手持户外序列上验证，实现多场景鲁棒跟踪并降低里程计漂移。
◆ 系统保持约60 FPS实时跟踪，兼顾鲁棒性与实时性。</td></tr>
<tr><td>2026-09-21</td><td>Range-Aided SLAM Initialization Exploiting Accurate Heading Information<br><a href='http://arxiv.org/pdf/2609.24846'>论文</a></td><td>本文针对距离辅助SLAM提出一种利用高精度航向信息的新型初始化方法。
◆ 利用已知高精度航向将SLAM的可分离结构扩展到距离辅助场景，避免直接求解非线性RA-SLAM。
◆ 第一阶段采用广义信赖域子问题，从非线性距离测量中求解应答器相对AUV的位置。
◆ 第二阶段结合相对应答器位置与AUV已知航向，通过线性最小二乘同时估计应答器和AUV位置。
◆ 将两阶段估计与高精度航向结合，为一般非线性RA-SLAM提供可靠初始化。
该方法在真实AUV长基线距离测量与INS高精度航向数据集上验证了有效性。</td></tr>
<tr><td>2026-09-21</td><td>SPARSER: Sparse Variable Projection by Exploiting Separable Structure in Robotic Perception<br><a href='http://arxiv.org/pdf/2609.24708'>论文</a></td><td>本文针对机器人感知中的大规模非线性最小二乘问题，提出SPARSER框架，联合利用可分离结构与稀疏性，通过变量投影解析消去线性变量，从而在规范对称问题中实现降维求解。
◆ 面向存在全局平移旋转等规范对称性的问题，构建了保持稀疏性的变量投影与矩阵自由Schur补框架，使VarPro可稳健用于SLAM等感知任务。
◆ 设计无矩阵Schur补算子，高效计算约简代价、梯度及Hessian-向量积，可与迭代非线性最小二乘求解器集成。
◆ 刻画了适用问题类别，识别可进一步解析简化的常见情形，并证明基于IRLS的鲁棒代价仍保留大部分可利用结构。
◆ 在合成与真实SLAM、SNL、SfM基准上平均比先进基线快5至7倍，CPU和GPU均有效，个别数据集加速超40倍；异常值多机器人SLAM中鲁棒变体比先进GNC求解器快2至16倍。
◆ 开源C++代码与全部数据集，促进可复现研究与实际部署。</td></tr>
<tr><td>2026-09-21</td><td>BayesianGS-SLAM: Uncertainty-Aware Neural Rendering SLAM via Probabilistic Formulation<br><a href='http://arxiv.org/pdf/2609.24140'>论文</a></td><td>◆提出BayesianGS-SLAM，一种不确定性感知的3D高斯泼溅SLAM框架，在概率形式下同时估计颜色与深度的预测不确定性，并贯穿整个SLAM流程复用。
◆构建可处理概率公式，将传感器噪声不确定性与不透明度诱导的地图表示不确定性结合，并通过渲染过程传播。
◆不同于仅关注颜色不确定性或仅在建图中使用不确定性的方法，该框架将预测不确定性同时集成到建图、跟踪与关键帧选择。
◆在建图阶段用不确定性增强优化，在跟踪阶段以鲁棒位姿目标归一化渲染残差，抑制不可靠残差对位姿估计的影响。
◆提出基于预测惊奇度的关键帧准则，利用不确定性判断新帧是否已被当前地图充分解释，从而减少冗余关键帧与建图调用。
在真实RGB-D数据集上，该方法的深度不确定性-误差排序显著优于现有不确定性感知SLAM方法，并在保持有竞争力跟踪与渲染性能的同时降低关键帧和建图调用数量。</td></tr>
<tr><td>2026-09-20</td><td>Elevator-VIGS: Separating Elevator Motion from Robot Motion in Visual-Inertial Gaussian Splatting SLAM<br><a href='http://arxiv.org/pdf/2609.23491'>论文</a> | <a href='https://ruizhou-cn.github.io/elevator-vigs/'>代码</a></td><td>Elevator-VIGS针对电梯内视觉与IMU观测冲突导致跟踪失败的问题，提出在视觉惯性高斯泼溅SLAM中持续跟踪与建图。其核心思路是不再把两种观测强行统一到同一坐标系，而是分离机器人相对电梯的运动与电梯相对世界的运动。
◆ 将机器人位姿放在电梯坐标系中估计，并把电梯相对世界的运动建模为逐关键帧运输状态，包含上升位移与垂直速度，嵌入稠密视觉惯性光束法平差。
◆ 利用视觉语言模型和深度网络零样本检测电梯乘坐，并在出发与到达时刻约束运输状态，从而稳定求解。
◆ 在真实与模拟电梯序列上取得最优跟踪和渲染性能，同时在四个无电梯公开基准上保持VIGS-SLAM的先进水平。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-23</td><td>AstraLOD3: Zero-shot multimodal agentic reconstruction of LOD3 building models<br><a href='http://arxiv.org/pdf/2609.28061'>论文</a></td><td>本文提出AstraLOD3，探索通用多模态基础模型Astra在有限自主智能体框架下零样本重建LOD3建筑模型。
◆ 将LOD3重建从固定专用流程重构为受约束的智能体过程，由Astra动态选择并执行Python与Blender程序。
◆ 融合多视图图像、标定相机、过滤稀疏SfM点云和自然语言重建规范，实现多模态证据驱动的零样本重建。
◆ 在35次运行含24栋基准建筑中取得平均FRDS 0.9647，几何一致性可与以往专用方法相媲美。
◆ 通过受控消融揭示重建引导、证据模态、模型配置及运行随机性对结果的影响。
未来将研究自适应细化、用户引导修正、任务特化及损伤感知重建。</td></tr>
<tr><td>2026-09-21</td><td>SPARSER: Sparse Variable Projection by Exploiting Separable Structure in Robotic Perception<br><a href='http://arxiv.org/pdf/2609.24708'>论文</a></td><td>论文提出SPARSER，一个面向机器人感知中规范对称非线性最小二乘问题的变量投影框架，联合利用可分离性与稀疏性，突破标准VarPro在全局平移旋转不变性下的限制。
它通过解析消去线性变量（如视觉路标）实现降维，同时保留位姿等非线性变量，并可接入迭代NLS求解器。
◆ 构造无矩阵Schur补算子，高效评估降维后的代价、梯度和Hessian向量乘积，避免显式构造大规模矩阵。
◆ 刻画适用问题类别，识别可进一步解析简化的常见情形，并证明IRLS鲁棒代价仍能保留大部分可利用结构。
◆ 在SLAM、SNL、SfM合成与真实基准上，CPU和GPU平均提速5至7倍，个别数据集超过40倍；在多机器人SLAM抗离群值场景中，鲁棒变体比先进GNC求解器快2至16倍。
◆ 开源C++代码与全部数据集，推动变量投影在机器人感知中的实用化。</td></tr>
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
<tr><td>2026-08-12</td><td>NPLSD: Accelerating Line-Segment Detection on NPU Microcontrollers<br><a href='http://arxiv.org/pdf/2609.25022'>论文</a></td><td>论文指出Transformer线段检测器在STM32N6的Neural-ART NPU上，因attention、grid-sampling和normalization缺少加速原语而难以实用，并逐算子刻画该架构失配。作者据此提出NPLSD，用统一方法构建一对NPU兼容线段检测器。
◆ 提出NPLSD-H，保留LINEA的HGNetv2卷积骨干，用全卷积特征金字塔和F-Clip密集头替换Transformer头。
◆ 提出NPLSD-M，将M-LSD-tiny主干适配到NPU支持的算子集合，实现轻量化。
◆ 通过ImageNet热启动和ShanghaiTech Wireframe训练，2.63M参数的NPLSD-H达sAP10=37.9，int8为35.9；0.62M参数的NPLSD-M达41.9，int8为41.1。
◆ 控制消融将主干设为唯一变量，并发现仅初始化就贡献4.6个点，验证训练策略重要性。</td></tr>
<tr><td>2026-08-11</td><td>TRACE: Transparent Retrieval for Abstract Concept Evaluation<br><a href='http://arxiv.org/pdf/2609.26168'>论文</a></td><td>论文在十二个七巧板剪影的单轮指称任务上，比较六个现成视觉语言模型与一个不使用学习视觉表征的透明基线，追问该任务是否真需大型预训练VLM。
◆ 提出透明检索基线：仅用经典SIFT关键点匹配与检索图像信号质量指数，无需学习视觉表示且可检查。
◆ 在相同试次上，该基线匹配最强VLM SigLIP-large并显著优于其余五个CLIP/OpenCLIP变体，即便它额外检索了外部图像。
◆ 结果表明学习到的视觉表征不是该任务瓶颈，给定检索图像后形状适配的经典相似度已足够。
◆ 发现抽象落地能力在VLM间差异大，从15%到39%，说明弱点模型特定而非对比预训练固有，并在KiloGram上对CLIP泛化且逐形状难度与人类可命名性相关。
最后提出以显式可检查的听者侧约定状态表示，将方法拓展至交互式多轮指称，作为未来工作。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-22</td><td>Laser-Tracker-Assisted Camera-to-Robot Calibration for Mobile Robots<br><a href='http://arxiv.org/pdf/2609.27006'>论文</a></td><td>本文提出一种激光跟踪仪辅助的移动机器人相机手眼标定方法，将激光跟踪仪的三维计量与相机的二维观测相结合。该方法在作者此前面向地面观测移动机器人的标定工作基础上，给出了在跟踪仪定位的移动机器人坐标系中估计相机位姿的广义公式。  
◆ 将激光跟踪仪三维计量与相机二维观测融合，用于移动机器人上的相机外参标定。  
◆ 通过串联多个标定目标，放松了先前方法对机器人和相机配置的假设与限制。  
◆ 提出更通用的相机到机器人标定框架，可支持多种配备相机的移动机器人系统。</td></tr>
<tr><td>2026-09-22</td><td>From Instrument-Mounted Demonstrations to In-Vivo Execution: Learning Bimanual Laparoscopic Appendectomy Without Robot-Collected Demonstrations<br><a href='http://arxiv.org/pdf/2609.25625'>论文</a></td><td>本文提出从手持腹腔镜器械演示到活体执行的端到端流程，将术中器械运动捕获并用于训练手术机器人策略，在活兔上验证。
◆ 设计仅装在标准腹腔镜器械杆上的状态记录器，融合惯性、飞行时间与霍尔传感器，无外部相机或追踪器即可恢复器械位姿和钳口状态。
◆ 构建传感器延迟测量与对齐数据管道，以机器人真值校准各通道并生成观察-动作对。
◆ 使用微调DINOv3骨干的扩散策略，并通过由离体兔阑尾深度图重建的物理模拟器闭环选择设计。
◆ 在849条四只活兔演示上重训练，部署于另四只活兔并带电外科，医生选择手术阶段，四只中三只完成阑尾切除。
◆ 证明机器人无需采集演示，仅作校准时序参考和执行器，医生自身器械演示足以训练、选择并部署双臂活体手术策略，且公开两个演示数据集。</td></tr>
<tr><td>2026-09-20</td><td>HEARTH: An Object-Centric RGB-Thermal-3D Dataset for Temperature-Aware Robot Manipulation<br><a href='http://arxiv.org/pdf/2609.23418'>论文</a></td><td>HEARTH 是一个以物体为中心、同时包含 RGB、热成像与 3D 几何并带真实温度测量的机器人操作数据集，覆盖 18 类日常物品的 90 个物体和 145 个状态。
◆ 构建了将表观表面温度经相机标定和位姿迁移映射到重建网格的采集流程，并提供原始温度、相机参数、RGB 纹理网格与热纹理。
◆ 基于这些资产构建三个 LIBERO 衍生任务并采集 1,200 条演示，用于微调预训练 VLA 模型 π0.5。
◆ 通过消融证明热观测对温度相关物体选择任务有效，成功率从仅 RGB 基线的 35.0% 提升到 75.0%。
这些贡献表明 HEARTH 能支持温度感知的机器人操作学习，并可用于训练策略遵循温度相关指令。</td></tr>
<tr><td>2026-09-20</td><td>P$^2$Calib: Utilizing Pattern Priors for LiDAR-Camera Extrinsic Calibration<br><a href='http://arxiv.org/pdf/2609.07516'>论文</a></td><td>本文提出P2Calib，一种利用标定板CAD模型提供的模式先验来提升激光雷达与相机外参标定精度的方法。针对传统四孔标定流程中激光雷达侧孔中心提取受稀疏角覆盖与混合像素影响的问题，该方法将已知孔半径作为拟合约束，有效防止中心估计在数据稀疏时发生退化。进一步地，P2Calib将四个孔的刚性矩形布局作为全局一致性约束，用于修正各孔之间的残余误差。上述两种先验被集成到一个包含完整标定流程的交互式工具中。在模拟与真实数据集上的实验表明，相比基线，联合配准残差分别降低90%和82%，留出重投影误差分别降低96%和77%。代码与数据已公开。
◆创新点一：将已知孔半径作为拟合约束，缓解稀疏角覆盖导致的孔中心估计退化。
◆创新点二：利用四孔刚性矩形布局作为全局一致约束，消除跨孔残余误差，提升整体标定精度。</td></tr>
<tr><td>2026-09-18</td><td>GaitVista: Reliability-Aware AI Measurement toward Accessible Longitudinal Gait Assessment<br><a href='http://arxiv.org/pdf/2609.22619'>论文</a></td><td>GaitVista提出一种面向可及纵向步态评估的可靠性感知测量层，核心是避免传感失效被误判为患者变化。
◆ 它用轻量门控按关节和帧分配视觉贡献，综合相机覆盖、局部视觉质量、跨模态不一致和根运动连续性来估计可靠性。
◆ 它将关节-帧可靠性显式暴露供检查，使多模态融合不再条件盲，并提升可解释性。
◆ 在七种干净与退化传感条件下，它降低全身和下半身平均误差27.7%和27.8%，取得融合方法中最差条件最低误差，并将与关节-帧oracle差距从2.76至5.33厘米降至1.11厘米。
在MoVi上，它是唯一可部署且同时优于两个单模态流的融合方法，标记支持误差较最强学习融合基线降低6.4%，并在TotalCapture上使双膝屈曲波形精度提升18.9%。
惯性数据中位置和时间变化的磁干扰支持其可靠性前提，但研究仅限健康受控参与者且保留个体IMU校准，因此是迈向可及步态评估的进展，而非已验证临床应用。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vlm'>Robot VLM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-23</td><td>TANDEM: Task and Motion Planning with As-Needed Demonstrations for Efficient Vision-Language-Action Model Fine-tuning<br><a href='http://arxiv.org/pdf/2609.28314'>论文</a></td><td>TANDEM提出将任务与运动规划TAMP与选择性人类遥操作结合，为超出规划器能力的长时操作任务收集演示。  
◆ 将人类协助建模为按需规划能力，而非依赖任务特定的固定干预点。  
◆ 利用预训练视觉语言模型扩展规划域，补充缺失谓词和由人类执行的magic算子，使自主与人工阶段可交错进行。  
◆ 每个阶段后重新感知场景并验证预期效果，再恢复自主规划，保证长时任务连贯执行。  
◆ 使用示例预训练轨迹对齐规划器生成运动与目标VLA模型预训练分布，提升微调效率。  
实验表明，在五个长时任务上，同等人工干预时间可收集2.9倍演示，用每任务20条演示微调π0.5-DROID，平均成功率从0%提升到60%。</td></tr>
<tr><td>2026-09-23</td><td>VLMs Can Describe, But Not Measure: Object-Centric Scene Understanding for Robotic Manipulation<br><a href='http://arxiv.org/pdf/2609.28184'>论文</a></td><td>论文提出一个VLM驱动、模块化的机器人场景理解框架，以同时满足语义理解和可靠度量需求。它从单张RGB-D观测出发，先分割物体级区域，再由VLM标注，并利用深度信息构建任务无关的物体中心表示。在151个桌面场景实验中，该方法保持强语义性能，同时显著提升定位与深度估计，并能接入任务规划用于机器人执行。
◆ 采用VLM负责语义、深度负责几何的模块化分工，避免直接依赖VLM进行度量。
◆ 构建任务无关的物体中心表示，兼顾语义标注与度量接地。
◆ 验证该分解在桌面场景中优于直接VLM推断，并支持机器人任务执行。</td></tr>
<tr><td>2026-09-22</td><td>Generalizing Manipulation Skills with a Local Coding Agent<br><a href='http://arxiv.org/pdf/2609.26499'>论文</a></td><td>本文研究本地开放权重视觉语言模型能否仅靠编码代理控制机械臂，并在无需人工编程或额外训练下一次性泛化到任务新变化。  
◆ 提出由本地Qwen3.8-27B驱动UR3e机械臂，通过编码代理自行编写并执行代码，而不依赖固定动作接口或训练策略。  
◆ 将运动学、安全限制和经典计算机视觉封装为底层服务，让模型在其上生成代码完成任务。  
◆ 在九类儿童玩具任务中跨颜色、大小、形状和任务变化测试，45次试验有30次泛化成功，耗时3.4至67.5分钟。  
◆ 发现成功完成后再次执行同类任务，耗时减少约50%，表明系统具有自改进能力。  
◆ 系统暴露本地编码代理的局限，并指出解决这些问题加上持续自改进研究，是通向真实部署的路径。</td></tr>
<tr><td>2026-09-22</td><td>SparseNav: Instruction-conditioned Sparse Semantic Perception for Training-Free Vision-Language Navigation<br><a href='http://arxiv.org/pdf/2609.26408'>论文</a></td><td>SparseNav提出一种无需训练、指令条件化的稀疏语义感知框架，用于基于地图的视觉语言导航。它遵循“少即是多”原则，仅维护轻量几何BEV地图和稀疏地标记忆，按当前活跃子指令按需获取语义，避免无关物体带来的感知成本与表示杂乱。
◆ 提出指令条件化按需感知：仅当查询地标可见且其度量位置能辅助下一步决策时，才调用开放词汇分割。
◆ 设计指令管理器，持续跟踪导航进度并识别活跃地标查询，使感知与语言指令动态对齐。
◆ 构建稀疏地标记忆，支持VLM在混合前沿与局部方向航点候选中选择，实现无训练规划与语义grounding结合。
◆ 无需额外训练即在R2R-CE和RxR-CE Val-Unseen达42.8%和40.7%，消融验证各组件，并完成Unitree Go2四足机器人无预建地图室内部署验证。</td></tr>
<tr><td>2026-09-22</td><td>Hierarchical Floorplan-Guided Vision-Language Exploration for Embodied Question Answering<br><a href='http://arxiv.org/pdf/2609.26360'>论文</a></td><td>本文提出HFLEX-EQA，一个面向具身问答的分层探索框架，利用环境结构先验提升未知环境中的信息获取与问答能力。针对现有方法仅依赖局部观察、未充分利用结构先验的问题，该框架融合在线场景图构建、VLM规划、语义前沿探索与平面图先验。系统从RGB-D观测增量构建分层场景图和开放词汇占据图，使VLM联合推理场景图、任务相关视觉信息、探索历史和估计的拓扑平面图。  
◆ 引入平面图引导的分层VLM探索，将结构先验与在线场景图结合用于规划。  
◆ 提出基于平面图和开放词汇前沿语义的房间发现策略，主动探索语义相关但尚未观察的房间类型。  
◆ 在OpenEQA和ExploreEQA上验证，并在真实室内环境的四足机器人上部署，证明VLM分层规划与结构平面图先验结合的有效性。</td></tr>
<tr><td>2026-09-22</td><td>Metric-Bench: Exploring In-context Spatial Metric Reasoning in VLMs for Indoor Scenes<br><a href='http://arxiv.org/pdf/2609.25841'>论文</a></td><td>论文提出 Metric-Bench，一个利用图像内已知物理尺寸参考物来引导室内场景上下文空间度量推理的 VLM 基准。
◆ 它通过参考物引导模型隐式学习无需相机内参的 2D 到 3D 映射，摆脱刚性像素级监督。
◆ 作者提出 MetricReasoner，一种结合结构化提示与可验证数值奖励的参考物接地度量推理强化微调方法。
实验显示该方法在 Metric-Bench 上显著提升空间度量理解，超过现有甚至更大专有模型 43.1%。
它还提升下游具身性能，RoboSpatial 总体准确率较空间专用模型高 30.4%，ERQA 高 9.3%。
同时在 V*Bench、BLINK 等通用基准上也取得增益，表明该适配不一定损害通用 VLM 能力。</td></tr>
<tr><td>2026-09-22</td><td>Sometimes You Gotta Run Before You Can Walk: Run-then-Walk Scheduling Strategy for VLM Autonomous Driving<br><a href='http://arxiv.org/pdf/2609.25831'>论文</a></td><td>现有VLM自动驾驶GRPO规划器在效率与安全间难以平衡，要么冒险求进度，要么过度保守，且训练周期长。论文揭示GRPO存在Run-GRPO进步探索与Walk-GRPO安全恢复两种RL机制，并提出Run-then-Walk两阶段奖励调度，先跑后走以兼顾性能与收敛。
◆ 揭示进步型Run-GRPO与安全型Walk-GRPO两种机制，为奖励调度提供依据。
◆ 提出Run-then-Walk，显式分离进步发现与安全修复，避免单阶段混合优化。
◆ Run阶段专注进步以逃离保守偏差，Walk阶段用端点和安全策略修复不安全行为，反转顺序克服先走保守与联合优化不安全。
◆ 在NAVSIMv1、NAVSIMv2、Navhard、nuScenes及多种VLM规划器上验证，性能提升且RL训练轮次减少40-50%。</td></tr>
<tr><td>2026-09-22</td><td>RoboFollow: Unveiling the Instruction Following Mirage in Embodied Agents<br><a href='http://arxiv.org/pdf/2609.25636'>论文</a> | <a href='https://github.com/AutoLab-SAI-SJTU/RoboFollow'>代码</a></td><td>论文指出现有具身智能体高成功率掩盖了真实指令遵循能力的薄弱，根源是“低场景熵”：视觉场景仅对应一个有效任务时语言冗余，策略可不用语言也拿高分，并提出RoboFollow诊断基准来暴露这一“海市蜃楼”。
◆ 高场景熵：每个训练场景支持多个运动学上不同的任务分支，使视觉不足以独立决策，迫使策略依赖语言。
◆ 分层诊断协议：设计L0至L3四级协议，逐步扰动视觉布局与语义，检验等价指令行为一致、不同指令行为可区分，覆盖空间关系、属性、轨迹约束和逻辑。
◆ 混杂控制诊断：简化交互对象，限制动作于训练动作库，并分阶段报告Intent与Execution得分，隔离理解与执行。
对九种VLA和WAM策略的评测显示，L0表现即使较强也未必迁移到L1-L3，更强VLM骨干、QA协同训练、LangForce和Classifier-Free Guidance等缓解措施均未能弥合差距，RoboFollow由此揭示真实指令遵循是被忽视的关键瓶颈。</td></tr>
<tr><td>2026-09-22</td><td>HABILIS Brain 0: Geometry-Change Supervision for Vision-Language-Action and Residual Flow Recovery<br><a href='http://arxiv.org/pdf/2609.25558'>论文</a></td><td>本文提出GC-VLA，通过从当前观测预测多视角未来-当前几何变化令牌，实现不依赖具体本体的视觉接口预训练。
◆ 提出几何变化视觉语言模型GC-VLM，利用离线帧对构造0.5秒预测视野，未来观测仅用于训练目标。
◆ 设计四阶段训练：先训GC-VLM，再引入ActionExpert对齐机器人动作并阻断接口梯度，随后联合更新，最后冻结模型应用GCRF。
◆ 提出几何条件残差流GCRF，用二元干预路由和单一有界残差速度策略，从闭环反馈学习残差恢复。
◆ 在LIBERO上，GC-VLA达95.20%成功率，结合GCRF达99.55%。
推理仅用当前观测和学习到的GC表示，无需执行离线目标编码器，兼顾具身无关预训练与机器人动作对齐。</td></tr>
<tr><td>2026-09-21</td><td>Capability-Aware Arbitration for Semantic Intent-Based Shared Control<br><a href='http://arxiv.org/pdf/2609.25369'>论文</a></td><td>论文针对共享控制中仅按人类意图置信度分配权限、忽视自主执行可靠性而导致过度帮助的问题。  
◆ 提出能力感知仲裁框架，由VLM推断语义意图并给出意图置信度，由VLA策略生成自主动作。  
◆ 在线从随机动作轨迹的离散度与局部不稳定性估计VLA能力置信度。  
◆ 设计非线性仲裁策略，通过Sigmoid映射融合贝叶斯滤波后的语义意图置信度与VLA能力置信度，动态调节机器人权限。  
在12人参与的抓放和双向堆叠实验中，该方法在分布内与分布外条件下取得最高任务成功率92%，高于遥操作83%、仅意图仲裁44%和固定等权融合10%。  
结果表明，将VLA能力纳入权限分配可缓解过度帮助，并提升控制友好性、降低权威加权分歧。</td></tr>
<tr><td>2026-09-21</td><td>X-Planner: Event-Structured Task Planning for Embodied Intelligence<br><a href='http://arxiv.org/pdf/2609.25187'>论文</a></td><td>X-Planner面向长时程具身操作，提出事件结构化的任务规划前端，显式桥接高层指令与可执行行为，弥补VLA系统中间规划结构隐含和CoT规划标注粗、推理冗长的问题。
◆构建融合Ego、UMI与遥操作的层次化规划数据，按来源控制标注深度，并用接管时间与人工设计失败监督持续错误识别。
◆基于共享VLM骨干提供两种事件结构化规划形式：离散接口输出可解释事件状态，潜在接口传递连续CoT状态。
◆采用Staircase Decoding在交错Transformer深度间传递连续CoT状态，实现潜在规划表示。
◆引入冻结的潜文本重建目标，为潜在表示提供语义锚点。
离线两步规划评估中，X-Planner在BERTScore-F1和裁判总体分上居四个模型第二；真实机器人实验优于评估基线，验证规划文本质量与下游执行效果。</td></tr>
<tr><td>2026-09-21</td><td>MIGU: Multimodal Instruction Grounding under Uncertainty for Manipulation Planning<br><a href='http://arxiv.org/pdf/2609.24995'>论文</a></td><td>MIGU研究人类自然指令下语言与手势互补但存在不确定性的多模态指令 grounding。该工作提出模块化框架，将语义与几何证据融合为统一 grounding belief 并接入操作规划，真实 benchmark 上优于所有基线，消融验证显式不确定性建模的价值。
◆ 构建基于眼-手指几何的3D几何似然，传播视线方向与深度不确定性，并显式考虑手方向估计误差。
◆ 用VLM提供候选物体和区域的语义先验，通过贝叶斯启发式融合与几何似然结合成统一目标信念。
◆ 让信念支持行为规划，可判断直接下游规划或请求澄清，降低误执行风险。
◆ 将 grounded targets 转为移动操作和桌面任务运动规划目标，打通从多模态理解到操作执行的链路。</td></tr>
<tr><td>2026-09-21</td><td>What do VLM-Based Vision-Language Navigation Models Rely on: Interpreting and Steering Policy Behavior<br><a href='http://arxiv.org/pdf/2609.24576'>论文</a></td><td>本文研究基于VLM的视觉语言导航模型的可解释性与可操控性，关注其决策依赖哪些模态及内部机制。  
作者使用干预式指标，因果度量视觉观测、指令和视觉记忆对导航决策的影响，发现策略对所有输入模态均敏感而非依赖单一模态。  
结果还表明，智能体编码导航进度并保留VLM骨干的语义结构，可通过内部激活进行概念级操控。  
◆ 提出干预式因果度量，量化视觉、指令与视觉记忆对VLM-VLN导航决策的影响。  
◆ 揭示VLN策略编码导航进度和语义结构，并支持通过内部激活实现概念级行为操控。  
◆ 提取抽象行为的激活向量，可零样本迁移到分布外真实场景，无需微调即提升性能。</td></tr>
<tr><td>2026-09-21</td><td>RoboTalk: Learning Multi-Robot Communication and Coordination from Multimodal Demonstrations<br><a href='http://arxiv.org/pdf/2609.23997'>论文</a></td><td>RoboTalk面向部分可观测下的多机器人协作，提出从多模态演示中学习显式机器人间通信与技能级动作选择的方法。  
◆构建合成数据生成流水线，并发布7,950条多模态轨迹数据集，覆盖53个移动操作厨房任务。  
◆设计领导者-跟随者规划协议，统一支持感知、操作、导航和通信等工具调用。  
◆引入推理轨迹与多样化自然语言通信，使小规模VLM能学习可解释的协调策略。  
◆在开源小VLM上微调后，新留出任务成功率达77%，远高于未微调的约2%。  
这表明面向端侧部署的小VLM可通过数据驱动方式获得多机器人通信与协调能力。</td></tr>
<tr><td>2026-09-20</td><td>Topology-Informed Visual Prompting For Vision Language Action Policies<br><a href='http://arxiv.org/pdf/2609.23944'>论文</a></td><td>论文针对复杂障碍几何下VLA策略因部分可观测而难以区分相似观测却需不同动作的问题，提出拓扑引导的视觉提示框架。
◆ 利用仿真规划与特权几何信息增强原始演示数据集，生成先移动到已示范拓扑签名再继续任务的轨迹。
◆ 采用高斯链接积分拓扑签名，量化环境关键拓扑属性，为相似视觉状态提供可区分线索。
◆ 微调VLM从实时相机观测预测拓扑签名与末端执行器路点，并将路点渲染为视觉提示来引导VLA。
◆ 在三个仿真双臂任务和真实抓箱任务中验证，硬件成功率超最强基线40%。
结果优于仅用名义演示微调的VLA及会移除拓扑信息的VLM提示基线。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-visual-semantic-recognition'>Robot Visual Semantic Recognition</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-23</td><td>Privacy-Preserving Semantic Segmentation from High-Resolution Depth and Ultra-Low-Resolution RGB<br><a href='http://arxiv.org/pdf/2609.28360'>论文</a></td><td>本文针对移动机器人摄像头隐私风险，提出高分辨率深度与超低分辨率RGB相结合的非对称隐私保护感知设定，在保留密集几何的同时限制细粒度外观，从源头降低视觉隐私暴露。
◆ 提出HR深度与ULR RGB的非对称传感范式，在几何可用性与隐私保护之间取得平衡。
◆ 设计HR几何引导的联合2D框架，同时进行语义导向RGB重建和RGB-D分割，缓解模态信息失衡。
◆ 构建端到端2D到3D分割流程，整合2D语义特征以提升场景级3D理解一致性。
◆ 通过隐私可恢复性分析、跨数据集零样本迁移和真机object-goal navigation验证隐私、泛化与实用性。
在ScanNet上，该方法取得隐私保护方法中最佳2D和3D分割性能，并最强零样本迁移至SUN RGB-D与SceneNN。</td></tr>
<tr><td>2026-09-23</td><td>NaviScale: Generating Large-Scale Semantic Map Datasets for Object Navigation<br><a href='http://arxiv.org/pdf/2609.27218'>论文</a></td><td>NaviScale提出面向语义地图ObjectNav的大规模数据生成框架，预测器仅需部分与完整语义地图配对训练，无需为每个样本重建完整3D环境。
◆ 组合真实住宅平面图与MP3D、HM3DSem的房间级语义和障碍地图，低成本生成大规模多样化语义地图数据。
◆ 房间间缩放改变平面图结构，提升平面图级布局多样性。
◆ 房间内缩放按房间类别匹配不同房间地图，填充同一固定平面图以增加房间组合多样性。
◆ VisRC通过射线投射将组合地图转为部分观测，并显式考虑视场、感知范围和遮挡。
生成192,000张语义地图、24,000个平面图和12,794处房产；在HM3D达64.3% SR/34.8% SPL，MP3D达43.1% SR/16.8% SPL，且不改变预测架构，并验证地图质量、语义分割误差和实机部署。</td></tr>
<tr><td>2026-09-22</td><td>SparseNav: Instruction-conditioned Sparse Semantic Perception for Training-Free Vision-Language Navigation<br><a href='http://arxiv.org/pdf/2609.26408'>论文</a></td><td>SparseNav提出一种免训练、指令条件下的稀疏语义感知框架，用于视觉语言导航，遵循“少即是多”原则。它仅持续维护轻量级几何BEV地图和稀疏地标记忆，并按需获取语义，避免无关对象累积带来的计算浪费和表示干扰。
◆ 通过指令管理器跟踪导航进度并识别当前活跃的地标查询，实现以子指令决定什么值得定位。
◆ 采用指令条件感知机制，仅在查询地标可见且其度量位置能影响下一步决策时，才调用开放词汇分割。
◆ 地标记忆支持VLM在混合前沿与局部方向路点候选中进行选择，无需额外训练。
在R2R-CE和RxR-CE Val-Unseen上分别达到42.8%和40.7%成功率，并成功部署于Unitree Go2四足机器人，在无预建地图的多种室内环境中验证有效。</td></tr>
<tr><td>2026-09-21</td><td>Impact of Data Compression on Downstream AI Tasks: A Study using Teleoperated Driving over 5G<br><a href='http://arxiv.org/pdf/2609.25290'>论文</a></td><td>本文研究5G远程驾驶中传感器数据压缩对边缘或云端下游AI任务性能的影响。作者以目标识别和语义分割为例，覆盖视频、LiDAR单模态及视频加LiDAR多模态，分析压缩对AI性能的作用。结果显示，有损压缩通常降低AI任务性能，且敏感度因数据源类型和压缩程度而异，并可为多模态视觉任务找到经验最优权衡点。
◆ 系统量化传感器压缩对远程驾驶下游AI任务的影响，连接通信约束与安全告警。
◆ 联合比较视频、LiDAR及多模态数据，揭示不同数据源对压缩的差异化敏感度。
◆ 为多模态视觉任务识别出压缩率与AI性能的经验最优权衡点，支撑远程驾驶压缩策略。</td></tr>
<tr><td>2026-09-20</td><td>Which Terrain Is Better? Preference Learning with VLM Prototypes for Off-Road Traversability Ranking<br><a href='http://arxiv.org/pdf/2609.23673'>论文</a></td><td>论文将越野可通行性从语义类别或freespace置信度转为视觉可通行性排序，用区域比较监督偏好方向。
◆ 提出TravPro，把标准标注转化为有序区域对，并在冻结视觉语言模型的patch token上训练小型读出器。
◆ 将VLM token一次性聚类为固定原型库，让读出器为每个原型学习偏好分数。
◆ 以读出器为教师，把稀疏比较生成密集偏好伪标签，并蒸馏到RGB学生，同时学习非地面掩码排除障碍和背景。
在五个未见域上，TravPro平均成对准确率达0.915，最强基线为0.783，能产生对表面条件敏感而按类赋值无法表达的排序。
同一VLM和同一监督若仅用提示或当作密集目标并不能得到该排序，关键在如何使用。</td></tr>
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
<tr><td>2026-09-17</td><td>PAANI : On Device Visual Evidence Fusion and Explainable Guidance for River Robot Simulation<br><a href='http://arxiv.org/pdf/2609.22353'>论文</a></td><td>PAANI提出一种在资源受限Arduino UNO Q上运行的端侧感知到制导架构，用于河流机器人模拟中融合视觉证据并生成可解释引导。
◆将项目训练的YOLO11n检测器与定制MobileNetV3 Small语义分割器按时间戳对齐融合，并用有界跟踪维持目标连续性。
◆设计显式走廊策略，综合水面标签、接受检测、紧迫度与掩码不确定性，且每条最终建议都公开其证据和政策理由。
◆通过ROS 2把本地AI管线接入独立Gazebo船体、定位与控制测试台，形成可复用边缘机器人基础。
训练与评估使用WaterScenes 10000张四类检测和MaSTr1325 1127张分割图像，ONNX模型共14.817 MB，检测mAP@0.5为0.7388/0.7367，分割mIoU为0.9750。
五分钟UNO Q录制在0.5 Hz下中位和95分位延迟为467.8 ms与580.3 ms，同时发现黑输入误分类和采样率不匹配问题；结果区分了模型精度、板载执行与已验证的水上避碰。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vpr'>Robot VPR</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-09-23</td><td>Geometry-Conditioned Visual Place Recognition in Natural Environments<br><a href='http://arxiv.org/pdf/2609.27370'>论文</a></td><td>本文提出面向自然环境的视觉地点识别方法，利用几何结构比视觉外观更持久的特性，应对重复植被、稀疏地标和显著视角变化。
◆ 提出Depth-Aware Distillation，用几何基础模型推断几何并条件化视觉基础模型的token表示，且无需深度传感器。
◆ 不把几何作为额外输入模态，而是将图像对齐深度投影到VFM token空间，通过通道式几何条件调制视觉表示。
◆ 设计两阶段教师引导学习，先将几何条件表示锚定到预训练外观空间，再精炼以增强地点判别能力。
在WildCross基准上，DAD将平均跨序列Recall@1从61.41%提升至66.37%，Recall@5从65.86%提升至72.49%，逆序和长期外观变化下增益最大。
结果表明，GFM派生几何能在外观不可靠时为VPR提供持久的结构先验。</td></tr>
<tr><td>2026-09-22</td><td>TM-APR: Thermal Temporal-Memory Localization via Analytic Online Adaptation<br><a href='http://arxiv.org/pdf/2609.26766'>论文</a></td><td>本文提出TM-APR，面向热视觉位置识别实现鲁棒域不变地点识别与在线自适应定位。
◆ 首次将解析类增量学习ACIL与域不变VPR结合，发现无梯度矩阵更新可构成优于传统微调的强基线。
◆ 建立ACIL与现代控制理论的代数等价关系，突破其线性假设对极端非线性热波动的脆弱性。
◆ 将无迹传播U-ACIL、高斯混合划分GMM-ACIL与极小极大H∞优化H∞-ACIL直接嵌入ACIL更新循环。
◆ 保证O(1)闭式矩阵更新并绕过反向传播，使在线学习延迟严格低于传感器采集间隔。
该框架消除实时SLAM轨迹跳变，为热VPR在线部署提供高效、鲁棒的新范式。</td></tr>
<tr><td>2026-09-22</td><td>Route-MHT: Multimodal Transformer Guardrails for Thermal Visual Place Recognition<br><a href='http://arxiv.org/pdf/2607.04745'>论文</a></td><td>本文针对热红外视觉位置识别（TIR-VPR）在分布外条件下产生的过度自信强制匹配失败问题，提出了一种名为轨迹锚定优化（TAO）的新型后端处理方法。TAO将传统多假设跟踪（MHT）中指数级复杂度的并行轨迹评估问题，转化为批量化SE(2) Procrustes对齐问题，通过张量级向量化与单次调用的批量SVD计算，绕开动态树扩展过程，实现了严格的每帧O(KN)实时性能。在零泄漏评估协议下，论文揭示了一个关键发现：在5米以下的微观尺度，由于局部视觉歧义性，被动几何后端无法数学分离度量定位误差与连贯性幻觉；而在宏观尺度上，K=100条分散假设会打破滑动窗口内的刚性时序共视约束，使联合优化残差急剧上升。TAO由此构建了一个10米的宏观收敛盆地，能够可靠地隔离灾难性拓扑断裂并抑制关键误接受。

◆ 提出TAO框架，将多假设跟踪的组合爆炸问题转化为批量化SE(2) Procrustes对齐，实现O(KN)严格实时的每帧执行复杂度。
◆ 揭示了5米微观尺度下几何一致性的固有盲区，明确界定10米宏观收敛盆地为幻觉检测的有效工作区间。
◆ 在零泄漏评估协议下，证明了多视图几何一致性可作为高效的失效安全滤波器，有效抑制过自信的误匹配。</td></tr>
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
<tr><td>2026-06-14</td><td>VL2Spike: Spike-driven Distillation from VLMs for Low-Power Visual Perception in Embodied AI<br><a href='http://arxiv.org/pdf/2606.15898'>论文</a></td><td>本文提出VL2Spike，一种新颖的脉冲驱动知识蒸馏框架，旨在将视觉语言模型（VLM）的多模态知识迁移到紧凑的Spikformer模型中，在保留脉冲神经网络能效优势的同时显著提升其视觉感知能力，为低功耗机器人感知提供了实用路径。

◆空间-时间视觉脉冲（SVS）蒸馏：实现VLM图像特征与脉冲token的共享流形对齐，并在膜电位和脉冲率上构建热启动的时间一致性机制。

◆脉冲原型引导的语言（SPL）蒸馏：将Spikformer的类别原型与logits与VLM的可提示文本嵌入对齐，实现跨模态语义知识的有效迁移。

实验结果表明，VL2Spike在三个静态数据集上取得6.81%的性能提升，能耗仅为原来的15.7%，并在机器人视觉位置识别任务中实现6.63%的增益，展现出优异的泛化能力与应用潜力。</td></tr>
<tr><td>2026-06-11</td><td>Visual Place Recognition in Forests with Depth-Aware Distillation<br><a href='http://arxiv.org/pdf/2606.13206'>论文</a></td><td>本文针对自然森林环境中视觉位置识别面临的植被重复、结构线索弱以及外观变化大等挑战，提出了一种轻量化的深度感知蒸馏框架。该方法将几何线索注入基于DINOv2的位置识别模型中，同时保留了预训练描述符空间，从而兼顾几何感知能力与原有表征的稳定性。在WildCross基准上的实验表明，该方法相较于仅依赖外观信息的方法取得了显著提升，对外观变化表现出更强的鲁棒性。论文的核心贡献可总结如下：

◆ 提出面向森林环境的轻量化深度感知蒸馏框架，将几何深度信息有效融入视觉位置识别流程。
◆ 创新性地在DINOv2描述符空间中执行蒸馏操作，既引入深度线索又避免破坏原有预训练特征的泛化能力。
◆ 验证了深度模态作为外观信息互补手段在自然场景位置识别中的关键作用。
◆ 在WildCross基准上证明了所提方法在跨次遍历场景下具有更优的鲁棒性与识别精度。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5213</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4682</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2457</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1643</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1621</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1512</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1337</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1300</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1085</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>1046</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>943</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>809</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>783</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>747</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>742</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>727</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>684</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>667</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>632</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>621</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>611</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>582</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>571</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>534</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>510</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>463</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>455</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>364</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>348</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>277</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>272</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>258</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>242</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>229</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>221</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>212</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>204</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>148</td><td>iBTC</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2876</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1673</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1368</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1096</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1059</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>882</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>711</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>667</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>666</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>625</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>604</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>578</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>572</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>571</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>554</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>518</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>510</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>465</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>456</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>452</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>334</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>313</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>311</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>177</td><td>Integrates an IMU to predict future odometry readi</td></tr>
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
> 更新于: 2026.09.24
