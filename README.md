# 计算机视觉领域最新论文 (2026.06.02)

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
<tr><td>2026-06-01</td><td>Embedding Semantic Risk into Distance Fields and CBFs for Online Monocular Safe Control<br><a href='http://arxiv.org/pdf/2606.01605'>论文</a></td><td>本文提出一种在线单目感知至控制框架，将语义风险嵌入基于控制障碍函数的安全导航距离场中，克服了现有方法未在空间表征中编码风险的局限。
◆提出将语义信息直接嵌入欧几里得符号距离场，在控制优化前编码风险，使高风险物体在安全场中扩展更大的空间影响，且不损失运行时查询效率。
◆结合基础模型SLAM前端与逐帧语义分割，从单目RGB视频在线重建并融合密集的三维几何语义表征。
◆在距离场计算前对安全相关区域施加类别相关的膨胀，并通过类别相关增益进一步调节CBF控制器的响应。
仿真与硬件实验验证了该框架能在10至20赫兹下在线运行，并在遥操作与自主导航中实现语义感知的安全行为。</td></tr>
<tr><td>2026-05-31</td><td>One Channel to Rule Them All: Rethinking Input Representation for Visual Place Recognition<br><a href='http://arxiv.org/pdf/2606.00936'>论文</a></td><td>本文挑战了视觉位置识别必须依赖RGB输入的传统假设，系统探究了色彩信息的作用。
◆发现灰度图整体性能与RGB相当，在严重外观变化下甚至优于RGB，而色彩仅在具备持久区分性线索时才有增益。
◆验证了全灰度...[摘要不完整，待更新]</td></tr>
<tr><td>2026-05-30</td><td>SuperMemory-VQA: An Egocentric Visual Question-Answering Benchmark for Long-Horizon Memory<br><a href='http://arxiv.org/pdf/2606.00825'>论文</a></td><td>本文提出了SuperMemory-VQA，一个针对长期自我中心记忆任务的视觉问答数据集，旨在弥补现有数据集仅关注短视频理解而忽视真实人类记忆需求的不足。
◆构建了包含52.9小时多模态数据及4853对人工验证问答的大规模基准，全面涵盖物体位置、意图回忆及时间线重建等六类真实记忆需求。
◆创新性地引入带有明确无法回答选项的多项选择题格式，以严格测试模型在证据不足时的抗幻觉鲁棒性。
◆通过对前沿大模型和智能体框架的基准测试，揭示了现有系统在真实记忆任务上的不可靠性，指明需开发仅在证据充分时才作答的接地架构。
参与者调查进一步验证了该基准问题设计的现实性与实用性。</td></tr>
<tr><td>2026-05-30</td><td>Dynamic Resilient Spatio-Semantic Memory with Hybrid Localization for Mobile Manipulation<br><a href='http://arxiv.org/pdf/2606.00576'>论文</a></td><td>本文提出了DREAM框架，这是一个无需预建地图的实时移动操纵系统，整合了感知、记忆、定位、导航与操纵。
◆构建在线时空语义体素记忆，利用LiDAR-惯性-视觉SLAM后端配准RGB-D观测，实现几何一致与语义可查的场景表征。
◆引入姿态图感知的冗余感知记忆剪枝机制，在位姿修正后更新历史观测，保持长时序观测历史的计算与存储有界。
◆结合语言条件3D检索、开放词汇图像检测与多模...[摘要不完整，待更新]</td></tr>
<tr><td>2026-05-29</td><td>ScaRF-SLAM: Scale-Consistent Reconstruction with Feed-Forward Models and Classical Visual SLAM<br><a href='http://arxiv.org/pdf/2606.00307'>论文</a></td><td>本文提出一种将经典特征视觉SLAM与几何基础模型相集成的解耦框架，解决了GFM预测不准确易影响位姿估计的问题。
◆采用经典视觉SLAM进行鲁棒低延迟跟踪，而将GFM专用于建图，避免了几何误差向位姿估计传播。
◆将建图锚定于SLAM模块输出的位姿并跨深度尺度优化，从而对重建施加几何约束。
◆基于多个带位姿关键帧构建子图，通过轻量级帧和子...[摘要不完整，待更新]</td></tr>
<tr><td>2026-05-29</td><td>Geodesic Flow Matching for Denoising High-Dimensional Structured Representations<br><a href='http://arxiv.org/pdf/2606.00248'>论文</a> | <a href='https://github.com/kremHabashy/CleanupSSP'>代码</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-05-27</td><td>Provably Guaranteed Polytopic Uncertainty Quantification for SLAM<br><a href='http://arxiv.org/pdf/2605.28172'>论文</a> | <a href='https://github.com/LIAS-CUHKSZ/Polytopic-SLAM-Uncertainty-Quantification'>代码</a></td><td>本文提出了针对3D-3D基于地标的SLAM的可证明保证的不确定性量化算法，解决了现有方法缺乏形式化保证或仅关注位姿估计的局限。该算法包含前向UQ、后向UQ和位姿复合三个模块，能生成经过认证的不确定性集合。
◆提供确定性保证机制，当输入边界确定时，输出集合可证明包含真实的位姿和地标。
◆采用多面体表示不确定性集合，实现了计算可处理性以及对位姿不确定性的统一处理。
◆结合保形预测技术从数据中校准测量不确定性，在保持规定概率的同时显著提升了算法的实用性。</td></tr>
<tr><td>2026-05-27</td><td>SAFEVPR: Patch-Based Conformal Verification for Safe Cross-Condition Sequence Visual Place Recognition<br><a href='http://arxiv.org/pdf/2605.28048'>论文</a> | <a href='https://github.com/Hasar12139/SafeVPR'>代码</a></td><td>本文提出了SAFEVPR，一种用于跨条件序列视觉位置识别的非训练式验证与校准流水线，解决了传统保形预测在跨条件部署下因可交换性被破坏而失效的问题。
◆采用基于冻结DINOv2 ViT特征的互近邻图像块匹配分数，替代标准骨干网络的余弦相似度。
◆采用Mondrian保形Learn-Then-Test校准替代平坦校准，在不同分数区间拟合独立的Bonferroni校正阈值。
该方法在23个跨条件实验设置中均实现经验有效，目标错误发现率为0.10时平均FDR仅0.014且真阳性率达0.75。
研究表明仅靠高区分度不足以保证保形有效性，且本方法能在无纹理重复场景中安全放弃不可靠匹配。</td></tr>
<tr><td>2026-05-27</td><td>Con-DSO: Learning Short-Horizon Consistency Priors for RGB-D Direct Sparse Odometry<br><a href='http://arxiv.org/pdf/2605.27952'>论文</a></td><td>针对RGB-D直接法视觉里程计在动态物体、遮挡和光照变化等复杂环境下因一致性假设失效导致性能下降的问题，本文提出了Con-DSO框架。
◆提出一致性感知的里程计框架，通过时间相邻的RGB-D帧对预测稠密的光度与深度几何一致性不确定性，将一致性破坏表征为像素级不确定性。
◆利用光流引导的光度误差和投影深度一致性误差训练网络，并将成对不确定性预测转换为基于关键帧追踪的宿主端质量先验。
◆在位姿估计阶段通过质量感知的支撑像素选择和解耦的光度几何加权来应用该先验，实现对不可靠观测的连续衰减而非硬性拒绝或阈值门控。
实验表明该方法在五个公开基准上显著超越基线，在多个数据集上绝对轨迹误差降低了20%至80%。</td></tr>
<tr><td>2026-05-26</td><td>Trinity: Unifying Class-Agnostic Terrain and Semantic Segmentation for Unstructured Outdoor Environments by Leveraging Synthetic Data<br><a href='http://arxiv.org/pdf/2605.27644'>论文</a></td><td>本文提出了一种基于Transformer的Trinity架构，旨在解决现有可穿越性估计方法跨平台迁移性差及标准语义分割无法捕捉地形多样性的问题。
◆提出统一网络联合执行类特定语义分割和类无关地形分割，其中地形分割仅基于视觉外观，无需预定义标签或机器人特定分数，从而学习机器人无关的视觉地形先验，便于结合特定经验用于下游任务。
◆扩展了OAISYS模拟器并引入RUGDSynth合成数据集，提供大规模的类无关地形样本以支持模型训练。
◆发布了EXTerra真实世界数据集，包含类特定与类无关地形双重标注，填补了相关真实数据空白。
实验充分验证了该联合分割方法在复杂户外环境中的可行性与有效性。</td></tr>
<tr><td>2026-05-26</td><td>Gaussian Process-Based Extended Object Estimation for 6G ISAC at Millimeter-Wave Frequencies<br><a href='http://arxiv.org/pdf/2605.26915'>论文</a></td><td>本文提出了一种基于高斯过程的扩展目标估计方法，用于6G毫米波通感一体化场景。
◆突破了传统点散射体假设的限制，利用高斯过程实现了对扩展目标的更优估计。
◆结合符合5G新空口标准的双基地感知实际测量平台，验证了该方法在毫米波频段的实用性。
◆证明了通信网络能力增强与双基地感知及高斯过程估计相结合，可有效提升未来无线系统的环境感知能力。
研究结果表明，高斯过程在毫米波建图和同步定位与建图场景中均能有效完成扩展目标估计。</td></tr>
<tr><td>2026-05-25</td><td>G-DRAGON: Geospatial Reasoning and Dynamic Planning for Retrieval-Augmented Outdoor Navigation<br><a href='http://arxiv.org/pdf/2605.25646'>论文</a></td><td>本文提出了G-DRAGON框架，这是一种用于户外开放世界导航的检索增强系统，有效解决了长距离全局规划与精细最后一公里探索的双重挑战。
◆提出了基于轻量级大语言模型的生成式检索方法，将自然语言指令映射到本地OSM实体，避免了云端大模型的事实幻觉并生成准确的全局坐标。
◆设计了高级规划模块，成功将全局拓扑路线与SLAM系统桥接，把地理空间路径点投影到机器人的可导航坐标系中。
◆针对最后一公里探索，结合前沿探索与开放集语义体素建图技术，实现了对开放词汇目标的精准定位。
实验证明该框架在仿真中超越了现有基线，并在真实世界无人地面车辆上成功完成了长达500米的行人搜索任务。</td></tr>
<tr><td>2026-05-24</td><td>FusionCore: A 23-State Unscented Kalman Filter for IMU, Wheel Encoder, GPS, and Visual SLAM Fusion in ROS 2<br><a href='http://arxiv.org/pdf/2605.25239'>论文</a> | <a href='https://github.com/manankharwar/fusioncore'>代码</a></td><td>本文提出了FusionCore，这是一个开源的ROS 2传感器融合包，利用23状态无迹卡尔曼滤波器将IMU、轮式编码器、GPS和视觉SLAM位姿融合为100Hz的单一里程计流。</td></tr>
<tr><td>2026-05-24</td><td>A Decentralized LiDAR-SLAM System with Certifiably Optimal Pose Graph Optimization<br><a href='http://arxiv.org/pdf/2605.25051'>论文</a></td><td>本文提出首个集成可证明最优位姿图优化后端的去中心化多机器人LiDAR-SLAM系统，旨在解决现有方法在大规模或退化环境中全局一致性差的难题。
◆首次将可证明最优的PGO后端集成于去中心化LiDAR-SLAM中，克服了传统局部搜索易陷入次优解和长期不一致的缺陷。
◆创新性地采用黎曼块坐标下降算法，确保了全局一致的轨迹估计。
◆系统无需依赖精确的初始猜测即可实现优化，显著增强了在复杂场景下的鲁棒性。
实验表明，该系统轨迹均方根误差相比现有最先进的DiSCo-SLAM大幅降低了48.9%。</td></tr>
<tr><td>2026-05-23</td><td>LC-Flow: Learning Local Continuous Optical Flow and Confidence from events<br><a href='http://arxiv.org/pdf/2605.24604'>论文</a></td><td>LC-Flow是首个纯粹基于局部事件的时间连续学习型光流估计器，解决了现有方法无法充分利用事件时间连续性的问题。它在局部方法中表现最优，其聚合方法更在MVSEC数据集上超越了繁重的帧法网络，确立了新的整体最优性能。
◆提出连续局部循环网络，维持空间网格的持久隐藏状态以逐步积累时间上下文，可在任意时间戳输出稀疏局部光流，克服了固定累积窗口与无状态从头计算的缺陷。
◆联合学习置信度分数，量化局部预测的可靠性，显式处理了事件稀疏性与孔径问题带来的内在模糊性。
◆赋予置信度双重作用，既过滤不可靠估计以服务下游视觉里程计等任务，又为多尺度聚合提供权重，将稀疏局部光流重建为全局一致光流。</td></tr>
<tr><td>2026-05-21</td><td>Extending Deep Event Visual Odometry with Sparse Point-Cloud Export<br><a href='http://arxiv.org/pdf/2605.22890'>论文</a></td><td>本文在深度事件视觉里程计DEVO的基础上，提出了一种稀疏点云导出管线。该系统在不改变原有视觉里程计性能的前提下，成功实现了稀疏几何场景的输出。
◆提出一种无侵入式的稀疏点云导出管线，通过提取DEVO内部已估算的3D结构并将其转换为显式点云，实现了点云的可视化与后续处理，且无需修改核心里程计公式。
◆构建了一套完整的数据导出实用工作流，涵盖数据导出、格式转换及点云清理功能，增强了系统的工程可用性。
实验表明，导出的稀疏点云与EMVS重建结果局部一致且在5厘米阈值下具有高精度，但也揭示了其在点云密度、完整性及抗累积噪声方面的局限。</td></tr>
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
<tr><td>2026-06-01</td><td>Edge Prediction for Roof Wireframe Reconstruction with Transformers<br><a href='http://arxiv.org/pdf/2606.02406'>论文</a></td><td>本文提出了一种受DETR启发的端到端Transformer编解码器架构，用于从稀疏SfM点云和地面语义数据中重建3D房屋屋顶线框模型。
◆提出基于语义优先级对稀疏SfM点云进行动态下采样，并融合格式塔与ADE20k类别特征进行增强。
◆将点云投影至冻结自编码器生成的潜特征图中提取额外格式塔特征编码，与点特征融合以丰富分割上下文。
◆利用交叉注意力机制，将学习到的查询嵌入直接解码为3D线框边缘。
该方法在HoHo 22k数据集上显著超越手工与学习基线，以0.6476的混合结构得分在S23DR挑战赛中夺得亚军。</td></tr>
<tr><td>2026-06-01</td><td>SAVMap: Structure-Aided Visual Mapping of Large-Scale 2.5D Manhattan Wireframes from Panoramic Video<br><a href='http://arxiv.org/pdf/2606.01939'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-05-28</td><td>The JADES Mass-Metallicity and Fundamental Metallicity Relations at $z\gtrsim2$ Using New High-Redshift Metallicity Calibrations<br><a href='http://arxiv.org/pdf/2605.30513'>论文</a></td><td>本文基于JADES巡天601个星系的JWST/NIRSpec叠加光谱，在1.4至7.0的红移范围内测量了质量-金属丰度关系和基本金属丰度关系。
◆采用基于...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-05-16</td><td>RHINO: Reconstructing Human Interactions with Novel Objects from Monocular Videos<br><a href='http://arxiv.org/pdf/2605.17014'>论文</a> | <a href='https://lxxue.github.io/RHINO'>代码</a></td><td>本文提出了RHINO三步框架，从单目RGB视频中共同恢复人、未知物体和静态场景的3D重建，解决了深度模糊、遮挡和运动纠缠的难题。同时，该研究构建了包含手持单目视频与4D捕捉真值的新数据集，并在新视角合成与4D重建任务上超越了现有基线。
◆利用3D感知基础模型稳定结构恢复，分别从前景和背景像素提取粗糙物体形状与表观运动以及场景形状与相机运动。
◆通过估计人体并从表观运动中减去相机运动来提取物体真实运动，成功将人、物体和场景对齐到统一的世界坐标系中。
◆采用具有逐组件符号距离场的组合式神经场细化形状，并引入可微接触先验吸引表面同时惩罚穿透，提升重建的物理合理性。</td></tr>
<tr><td>2026-05-16</td><td>SemaVoice: Semantic-Aware Continuous Autoregressive Speech Synthesis<br><a href='http://arxiv.org/pdf/2605.16964'>论文</a></td><td>现有连续自回归语音合成存在语义建模与连续语音表示不匹配的问题，导致模型过度关注低级声学纹理而牺牲高级语义连贯性，加剧了生成误差累积。为解决此问题，本文提出SemaVoice，一种面向高保真零样本文本转语音的语义感知连续自回归框架。
◆引入语音基础模型引导的对齐机制，精炼连续语音表示以更好捕获局部语义一致性与全局结构关系。
◆在自回归框架内采用块级扩散头，基于精炼后的表示条件进行高质量语音合成。
实验表明，SemaVoice在Seed-TTS基准上取得1.71%的英文词错率，主客观评估均媲美前沿开源系统，且验证了该对齐机制在不同表示粒度下的显著提升效果。</td></tr>
<tr><td>2026-05-15</td><td>SCARED-C: Corrected Camera Poses for Endoscopic Depth Estimation<br><a href='http://arxiv.org/pdf/2605.16628'>论文</a></td><td>本论文指出了广泛使用的内窥镜深度估计基准SCARED数据集存在非关键帧位姿误差严重的问题，导致其可靠标注仅限35个关键帧。
◆提出SCARED-C修正数据集，利用运动恢复结构系统COLMAP重新估计所有帧的相机位姿，有效消除了原数据集由机器人运动学引入的误差。
◆设计了尺度恢复步骤，通过关键帧的真实深度图将重建结果对齐到度量空间，确保了深度数据的物理尺度准确性。
◆大幅扩充了高质量的可用数据，将可靠的RGB-D图像对数量从原本的35个增加至17135个。
该研究还通过立体视差评估和单目深度估计实验验证了修正位姿的有效性，并公开了数据集与代码。</td></tr>
<tr><td>2026-05-14</td><td>Denoising-GS: Gaussian Splatting with Spatial-aware Denoising<br><a href='http://arxiv.org/pdf/2605.14880'>论文</a></td><td>本文提出Denoising-GS框架，将3D高斯溅射的优化过程重新定义为基元去噪过程，解决了现有方法仅调整位置而忽略空间结构从而引入噪声的问题。
◆设计了保留空间优化流的优化器，实现连贯且有方向性的去噪而非随机扰动。
◆提出空间梯度去噪策略，结合基元的空间支撑确保梯度一致性更新。
◆引入基于不确定性的去噪模块，通过估计基元的不确定性来修剪冗余和噪声基元。
◆采用空间连贯性细化策略，在稀疏区域选择性地分裂基元以维持结构完整性。
实验表明该方法在提升新视角合成保真度的同时保持了表示紧凑性，在多个基准上达到最佳性能。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-05-31</td><td>Crazyflow: An Accurate, GPU-Accelerated, Differentiable Drone Simulator in JAX<br><a href='http://arxiv.org/pdf/2606.01478'>论文</a></td><td>本文提出了Crazyflow，一个基于JAX构建的GPU加速、高精度且可微的无人机仿真器，填补了现有仿真器无法统一支持保真度、可微性和集群模拟的空白。
◆实现了前所未有的仿真速度与并行规模，单机仿真比现有SOTA快超一个数量级，可同时模拟数千个含4000架无人机的集群。
◆同时兼顾了高精度与可微性，支持基于解析梯度的策略学习，在无需域随机化的情况下实现了亚厘米级的轨迹跟踪精度。
◆打破了传统先训练后部署的范式，凭借极高的仿真速度实现了飞行中在线强化学习，仅用0.38秒即可从零训练出无人机空中恢复策略并成功稳定。
◆具备出色的兼容性与易用性，直接兼容开源Crazyflie模型，并提供轻量级系统辨识流程，支持多级仿真抽象及跨平台快速重构。</td></tr>
<tr><td>2026-05-31</td><td>Time-Optimal Collision Avoidance Via a Greedy Polynomial Backward Sweep<br><a href='http://arxiv.org/pdf/2606.01169'>论文</a></td><td>本文针对低推力卫星碰撞规避问题，提出了一种贪婪时间最优反向扫描方法，用于求解确保安全的最晚机动启动时间。
◆该方法采用反向迭代传播策略，从名义最近接近时间起向后传播，每步贪婪选择局部最小化危险度量的推力方向。
◆引入微分代数技术高效传播状态敏感度，实现了最近接近时间的在线动态更新。
研究采用错过距离和碰撞概率作为安全度量，在大量交会数据集上对方法进行了验证。
实验表明该方法准确度高，与最优控制基准相比仅有极小的最优性损失。
其运算时间短，非常适合航天器星载环境的实时计算与实现。</td></tr>
<tr><td>2026-05-31</td><td>Tether-Aware Dynamic Collision Avoidance for USV-HROV Systems<br><a href='http://arxiv.org/pdf/2606.01112'>论文</a></td><td>本文针对无人水面艇跟踪混合遥控潜水器时面临的水下系绳易剐蹭且避障易致系绳绷紧的挑战，提出了一种系绳感知的动态避障方法。
◆引入了系绳安全感知平面域，在无需显式系绳形状模型的情况下，表征系绳与障碍船只之间的三维碰撞风险。
◆开发了系绳绷紧感知速度障碍方法，在实现安全避障的同时降低系绳绷紧的可能性。
◆将该方法与视线导引法相整合，有效协调了HROV跟踪与动态避障任务。
仿真结果表明，该方法在无人艇执行规避机动时，能成功避让动态障碍船只并保障系绳安全。</td></tr>
<tr><td>2026-05-31</td><td>Robust Integrated Planning and Control for Quadrotors in Dynamic Environments via NMPC with CBF Penalties<br><a href='http://arxiv.org/pdf/2606.01038'>论文</a></td><td>本文提出了一种针对四旋翼无人机在动态环境下的鲁棒集成规划与控制新策略。
◆将控制障碍函数作为指数惩罚项嵌入非线性模型预测控制中，在严格输入约束下改善了可行性并确保平滑避障，同时提供权衡跟踪精度与避障激进度的调节参数。
◆引入高增益扰动观测器估计并补偿外部扰动，显著提升了系统的鲁棒性。
◆结合卡尔曼滤波实现计算高效的障碍物运动实时预测，使无人机能够规避动态障碍物。
◆这是首个经过硬件实验验证的NMPC与CBF结合的集成规划控制框架，对比实验证明了其在可行性安全性和鲁棒性上的显著优势。</td></tr>
<tr><td>2026-05-31</td><td>OSCAR: Obstacle Survival Curves for Adaptive Robot Navigation<br><a href='http://arxiv.org/pdf/2606.00990'>论文</a></td><td>本文提出OSCAR框架，解决移动机器人在已知路线图上遇到临时障碍物时等待与重规划之间的低效决策问题。
◆提出基于障碍物类别的生存建模方法，从在线经验中学习残余清障时间分布，并引入右删失观测处理未观察到清障就重规划的情况。
◆将生存模型集成到时变图规划器中，动态计算被阻塞边的耐心阈值，从而自适应地决定等待时间或选择替代路线。
◆框架支持在多个导航回合中持续更新清障时间估计，实现导航策略的在线进化与优化。
仿真与真实机器人实验表明，该方法在每类障碍物不到20次观测后即可收敛至接近真实分布的最优水平，显著优于启发式基线。</td></tr>
<tr><td>2026-05-30</td><td>DriveAnchor: Progressive Anchor-based Flow Learning for Autonomous Driving Planning<br><a href='http://arxiv.org/pdf/2606.00519'>论文</a></td><td>DriveAnchor是一个三阶段自动驾驶规划框架，实现了行为多样性、可控性与安全性。
◆提出示范流预训练，用2398个轨迹形状词汇表替代无结构高斯先验，从结构上保障行为多样性。
◆提出引导流后训练，联合仅依赖静态道路几何的能量场与流匹配，将锚点重定位至指定走廊多边形，无需可微引导即可增加可控性。
◆提出奖励精炼流微调，利用...[摘要不完整，待更新]</td></tr>
<tr><td>2026-05-29</td><td>Constrained Whole-Body Tracking for Humanoid Robots<br><a href='http://arxiv.org/pdf/2606.00374'>论文</a></td><td>本文提出了ConstrainedMimic控制框架，旨在解决人形机器人在强化学习全身追踪中难以保证安全和满足训练后约束的问题。
◆结合操作空间控制与控制障碍函数，实现了对运动学参考动作和底层动力学上任意运行时约束的实时满足。
◆在约束激活时保持与当前接触模式和追踪目标的一致性，最小化对策略原有能力的限制。
◆该方法完全可微，支持CPU、GPU和TPU运行，并能以高达300至500赫兹的频率实时部署。
实验在仿真的Unitree G1机器人上验证了该框架在自碰撞与外部避障、关节限位和质心稳定等约束控制上的有效性。</td></tr>
<tr><td>2026-05-29</td><td>GLENS: Global Search via Learning from Solver Iterates with Diffusion Models<br><a href='http://arxiv.org/pdf/2606.00366'>论文</a></td><td>该论文提出了GLENS方法，用于为多模态非凸连续优化问题生成高质量且多样化的初始猜测，从而加速求解器收敛并支持灵活的下游决策。
◆提出利用求解器中间迭代数据作为免费数据增强的数据高效全局搜索框架，克服了现有方法仅使用最终收敛结果导致局部信息丢失和数据受限的缺陷。
◆设计了基于扩散模型的邻域结构模型，能够根据问题参数条件学习并刻画最优解周围的局部几何特征。
◆引入了求解器行为模型，在扩散采样过程中学习细化方向，从而引导样本向附近的最优解生成。
实验表明，GLENS在多个非凸基准和机器人避障导航任务中，均能生成兼顾高质量与多模态多样性的初始猜测，显著提升了求解器的收敛速度。</td></tr>
<tr><td>2026-05-29</td><td>BERS: Locally Optimal Continuous Algorithm for Maritime Weather Routing with Just-in-Time Arrival<br><a href='http://arxiv.org/pdf/2605.31533'>论文</a></td><td>该论文提出了一种名为BERS的气象航线优化框架，旨在解决动态风浪和障碍物约束下的准时到达航线规划问题。
◆提出了结合CMA-ES全局进化搜索与FMS局部变分细化的两阶段优化框架。
◆采用贝塞尔曲线参数化航线并进行密集路径采样，确保轨迹平滑且兼顾中段效应与可行性约束。
该方法在七项操作标准的基准测试中均匹配或超越已有基线，在复杂流场下保持鲁棒收敛。
真实海洋数据验证表明，仅航线优化即可降低23%至59%的推进能耗。
结合风辅助推进后总节能高达75%，证明了该框架在海事脱碳节能规划中的实用性与可扩展性。</td></tr>
<tr><td>2026-05-29</td><td>LiftNav: Path Planning via Semantic Lifting in TSDF-Guided Gaussian Splatting<br><a href='http://arxiv.org/pdf/2605.31376'>论文</a></td><td>本文提出了LiftNav框架，解决了传统TSDF缺乏语义与三维高斯泼溅几何偏软导致难以精确避障的矛盾。
◆构建基于TSDF+GS双地图的混合导航框架，兼顾了可靠的碰撞避障与物体级语义理解。
◆设计了结合YOLO检测与TSDF三维提升的实时流水线，无需密集三维嵌入即可实现灵活的语义导航。
◆引入了基于铰链损失的碰撞惩罚项，有效提升了B样条轨迹优化的平滑度与安全性。
实验表明，相较于最先进的辐射场基线，该方法实现了百分之百的轨迹可行率且路径更短。</td></tr>
<tr><td>2026-05-29</td><td>Simulation of collision avoidance behavior in crowd movement by data-driven approach<br><a href='http://arxiv.org/pdf/2605.31210'>论文</a></td><td>针对现有数据驱动人群模拟模型在双向和多向流中碰撞率过高的问题，本文提出了一种融合行人碰撞机制的新型数据驱动人群模拟模型CPGAN。
◆提出基于横向加速度的碰撞损失函数，将其融入生成对抗网络架构，显著降低了逆向行人碰撞率至与对照实验相当的水平。
◆提出基于Voronoi的运动特征提取方法，提升了模型对行人运动特征的捕捉能力。
实验表明，CPGAN在双向流场景中有效模拟了人群运动，成功重现了车道形成现象和N-t曲线。
本研究为将行人动力学机制整合到数据驱动人群模拟的损失函数中提供了重要启示。</td></tr>
<tr><td>2026-05-29</td><td>Trajectory Planning for Non-Communicating Mobile Robots using Inverse Optimal Control<br><a href='http://arxiv.org/pdf/2605.30906'>论文</a></td><td>本文核心贡献是提出了一种针对无通信移动机器人避碰场景的轨迹规划与预测结合算法。
◆基于逆最优控制，通过观察历史轨迹来估计所有机器人的未知目标状态。
◆每个机器人从他人视角出发，结合自我预测与估计的目标状态来求解联合预测问题。
◆将联合预测结果纳入自身的轨迹规划中进行考量，实现高效交互。
◆相比传统恒加速度估计方法，该方法使到达目标的时间中位数缩短9.8%，且求解器从未出现无法求解的情况，鲁棒性极高。</td></tr>
<tr><td>2026-05-29</td><td>GSAM: A Generalizable and Safe Robotic Framework for Articulated Object Manipulation<br><a href='http://arxiv.org/pdf/2605.30740'>论文</a></td><td>本文提出GSAM框架，旨在解决关节类物体操作中泛化能力有限和易发生破坏性碰撞的问题。
◆提出基于微调视觉语言模型的优化器，利用思维链常识推理修正视觉感知器的原始运动学参数估计。
◆设计交互约束函数生成器，结合物体与避障知识生成提示，由大语言模型将其函数化并应用于轨迹与姿态规划以防碰撞。
◆开发运动学感知操作规划器，以验证规划轨迹和姿态的可达性。
实验表明该框架将标准差降低了3.1%，操作成功率提升了36.0%，显著增强了实际场景中的物体泛化性与交互安全性。</td></tr>
<tr><td>2026-05-29</td><td>Geometry-Aware Control Barrier Functions for Collision Avoidance via Bernstein Polynomial Approximations<br><a href='http://arxiv.org/pdf/2605.30696'>论文</a></td><td>针对不规则几何形状机器人和障碍物的安全导航问题，传统控制障碍函数的形状代理往往过于保守或约束数量过多，影响实时性能。本文提出了一种基于伯恩斯坦多项式符号距离场的新型几何感知控制障碍函数。该研究的核心创新点如下：
◆提出统一表示方法，利用BP-SDFs统一表示障碍物和机器人，从而以统一的最小距离构建障碍函数，避免了多局部基元导致的约束膨胀。
◆实现闭环控制约束，利用伯恩斯坦多项式的可微特性，能够轻松地在闭环系统中强制执行控制约束，提升了算法实用性。
仿真实验在单机器人导航和异构多机器人避碰场景中验证了该方法的高效性与安全保障能力。</td></tr>
<tr><td>2026-05-28</td><td>Hybrid Digital and Analog Airy Beamforming for Near-Field Multi-User Communications<br><a href='http://arxiv.org/pdf/2605.29481'>论文</a></td><td>本文针对6G近场多用户通信中,高频聚焦波束因直线传播易受障碍物遮挡、导致频谱效率下降的问题,提出了一种基于Airy波束的混合数模波束赋形方案。该方案利用Airy波前的弯曲传播特性,使波束能够绕过障碍物并在用户处实现能量聚焦,同时通过分层波束训练和数模混合架构实现低复杂度的多用户接入与干扰抑制。仿真表明,在毫米波至太赫兹频段下,所提方案在波束方向图和频谱效率方面均优于传统聚焦波束赋形。

◆ 首次将Airy波束引入近场多用户通信,构建了兼具绕障传播与能量聚焦双重能力的近场Airy波前模型。
◆ 设计了分层Airy波束训练方法,可快速搜索能够绕过障碍物并与用户对齐的最优波束,无需获取完整信道状态信息。
◆ 提出了基于选定Airy波束配置模拟波束赋形器、再利用数字波束赋形器抑制用户间干扰的低复杂度混合架构。
◆ 解决了传统聚焦波束在多用户链路存在遮挡时频谱效率严重退化的瓶颈问题。
◆ 验证了该方案在毫米波至太赫兹宽频段下相较传统聚焦波束赋形的性能优势,拓展了近场通信的应用场景。</td></tr>
<tr><td>2026-05-27</td><td>EventShiftFlow: Towards Hardware-efficient FPGA-based Flow Estimation<br><a href='http://arxiv.org/pdf/2605.28312'>论文</a></td><td>本文提出了一种面向FPGA的流式速度估计器EventShiftFlow，旨在解决现有事件相机运动估计算法计算量大且难以硬件映射的问题。该方法将异步事件离散化为固定时长的时间窗并构建1位空间占用网格，通过并行评估多个速度假设来输出稀疏量化的速度估计。
◆提出纯整数逻辑的数据通路设计，仅使用移位寄存器、计数器、比较器和LUT映射的小型乘法器，无需浮点运算、除法器、DSP模块、帧重建和迭代优化。
◆在算法与硬件间进行针对性权衡，放弃稠密亚像素光流，换取每个活跃像素的稀疏量化速度估计，满足低延迟和资源受限平台的实时避障需求。
◆实现极低硬件开销的FPGA部署，数据通路存储需求小于2kB，并在低成本FPGA上完成原型验证，同时在真实数据集中达到了99.5%的方向准确率。</td></tr>
<tr><td>2026-05-28</td><td>Trust, Geometry, and Rules: A Credibility-Aware Reinforcement Learning Framework for Safe USV Navigation under Uncertainty<br><a href='http://arxiv.org/pdf/2605.26974'>论文</a></td><td>本文提出了一种融合可信度感知学习、几何安全屏蔽与连续规则嵌入的强化学习框架，解决了无人艇在感知不确定性下的安全合规导航难题。
◆提出可信度加权价值学习，利用滤波协方差与经验误差的差异推导动态信任因子，调节评论家损失以防止策略对噪声样本过拟合。
◆提出协方差膨胀速度障碍方法，将位置估计不确定性映射为角度边界，构建保守的几何屏蔽以覆盖危险的探索动作。
◆提出风险感知的避碰规则职责嵌入，将二元相遇职责松弛为连续的规则感知信号，提供平滑扇区转换并抑制稀疏奖励引起的振荡。
仿真实验表明该框架提升了对抗感知不一致的训练鲁棒性，在避碰与规则合规性上显著优于基线方法。</td></tr>
<tr><td>2026-05-26</td><td>Look Further: Socially-Compliant Navigation System in Residential Buildings<br><a href='http://arxiv.org/pdf/2605.26710'>论文</a></td><td>本文核心贡献在于证明了在住宅楼走廊环境中，将移动机器人对人的反应距离延长至八米以上能显著改善人类对机器人运动的感知。与关注短距离避让的传统社交导航方法不同，该研究通过远距离提前反应优化了人机交互体验。
◆提出主动换道运动模式，机器人在八米外识别到迎面而来的人时，便从走廊中心横向移动至侧边。
◆构建了利用该模式的导航系统，突破了典型交互距离限制，实现远距离的社会合规导航。
通过四十二名参与者的用户研究评估了安全、平滑和礼貌三个服务目标，结果表明在直走廊迎面场景下该系统显著优于传统模式，但在盲区转角场景中各方法无显著差异。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-01</td><td>Co-training with Ego-centric Video and Demonstration for Robot Navigation Task<br><a href='http://arxiv.org/pdf/2606.01951'>论文</a></td><td>现有的视觉语言动作模型依赖昂贵的真实机器人数据，且将第一人称人类视频应用于移动机器人导航面临视角变化的挑战。本文提出了一种将第一人称行走视频转换为移动机器人模仿学习数据集的框架。
◆该方法通过估计人类视频中的相机运动，将其转换为与地面移动机器人兼容的动作表示。
◆通过联合训练人类衍生数据与机器人收集数据，克服了单一数据源的局限，提升了模型的语言理解与动作生成鲁棒性。
实验验证了第一人称人类视频作为移动机器人学习有效且可扩展数据源的潜力。</td></tr>
<tr><td>2026-06-01</td><td>Adversarial Attacks on Robot Localization Systems via Deep Feature Perturbation<br><a href='http://arxiv.org/pdf/2606.01892'>论文</a></td><td>本文研究了基于深度学习的机器人定位系统面对对抗攻击的脆弱性，提出了一种针对视觉定位中乘积量化的对抗查询生成框架。
◆提出轻量级乘积量化网络（LPQN）来扰动查询特征编码，误导检索过程返回语义无关的数据库条目。
◆设计了前向与反向两阶段生成程序，前向传播扰动特征分布，反向传播通过优化细化扰动。
◆LPQN的轻量化设计能够在极小的计算开销下，生成细微却高效的对抗性扰动。
大量受控与真实机器人环境实验证明，该方法显著降低了定位系统性能，暴露了实际应用中的关键安全漏洞。</td></tr>
<tr><td>2026-06-01</td><td>PlatonicNav: Unveiling Semantic Correspondence in Navigation with Platonic Topological Maps<br><a href='http://arxiv.org/pdf/2606.01788'>论文</a> | <a href='https://github.com/AIGeeksGroup/PlatonicNav'>代码</a></td><td>该论文针对当前具身视觉导航方法过度依赖架构融合或显式跨模态监督来统一任务和语言定位的局限性提出新视角。论文将柏拉图表征假设扩展至具身导航，将纯视觉ObjNav、跨模态Obj...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-01</td><td>Embedding Semantic Risk into Distance Fields and CBFs for Online Monocular Safe Control<br><a href='http://arxiv.org/pdf/2606.01605'>论文</a></td><td>本文提出了一种在线单目感知到控制框架，将语义风险嵌入到基于控制障碍函数的安全导航距离场中。该框架克服了现有方法对所有障碍物分配相同安全裕度或仅在下游使用语义的局限性，直接在空间表示中编码语义风险。
◆将语义信息直接嵌入欧氏符号距离场，在控制优化前预编码语义风险，使高风险物体在安全场中具有更大空间影响，同时保持高效的运行时查询。
◆结合基于基础模型的SLAM前端与逐帧语义分割，从单目RGB视频中在线重建并融合密集三维几何与像素级类别标签。
◆在距离场计算前对安全相关区域施加类别依赖的膨胀，并结合类别依赖增益进一步调节CBF控制器响应。
实验证明该框架能以十到二十赫兹的频率在线运行，并在遥操作和自主导航中...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-01</td><td>Hierarchical Object Representation for Spatial Robot Perception: Points, Meshes, and Superquadrics<br><a href='http://arxiv.org/pdf/2606.01545'>论文</a> | <a href='https://github.com/perceptica-robotics/Hickory'>代码</a></td><td>本文提出了一种用于空间机器人感知的层次化物体表示方法，解决了现有三维场景图中物体几何表示过于简化的问题。该表示方法能够支持高保真物体重建、鲁棒重定位与安全导航规划。
◆设计了四层渐进式抽象的几何表示结构，从原始传感器数据逐步过渡到密集三维网格，最终提炼为超二次曲面解析基元，实现了稀疏且解析的几何表达。
◆开发了直接从机器人RGB-D图像流构建该层次化表示的完整处理流程，验证了其在室内外开放集物体场景中的有效性。
◆提出基于超二次曲面的地图对齐方法，在多种数据集上的表现超越了当前最先进方法ROMAN，并实现了密集环境下高效且解析的碰撞检查。</td></tr>
<tr><td>2026-05-31</td><td>DeepIPCv3: Event-Aware Multi-Modal Sensor Fusion for Sudden Pedestrian Crossing Avoidance<br><a href='http://arxiv.org/pdf/2606.01277'>论文</a> | <a href='https://github.com/oskarnatan/DeepIPCv3'>代码</a></td><td>针对传统端到端自动驾驶系统在突发行人穿越时存在感知延迟和运动模糊的安全隐患，本文提出了DeepIPCv3多模态自主导航框架。
◆将激光雷达的密集三维空间几何与动态视觉传感器的微秒级异步事件流相融合，有效消除了传统帧传感器的曝光失效与运动模糊。
◆引入受Transformer启发的跨模态注意力机制，动态关联异构模态，使网络在不牺牲结构场景感知的前提下瞬时优先处理高速动态更新。
◆设计了融合启发式轨迹跟踪与直接神经预测的混合策略网络，将融合特征映射为安全的局部路径点和可执行控制指令。
在自建的多...[摘要不完整，待更新]</td></tr>
<tr><td>2026-05-31</td><td>OSCAR: Obstacle Survival Curves for Adaptive Robot Navigation<br><a href='http://arxiv.org/pdf/2606.00990'>论文</a></td><td>该论文提出了OSCAR框架，解决移动机器人在图导航中遇到临时障碍物时等待与绕行决策效率低下的问题。传统方法通常采用固定规则，忽略了不同类型障碍物持续时间的差异。
◆引入生存建模方法，利用在线经验学习基于障碍物类别的剩余清除时间分布，并创新性地处理了机器人提前绕行时产生的右删失观测数据。
◆将生存模型集成到时间相关的图规划器中，为每个被阻塞的边动态计算耐心阈值，智能平衡等待与绕行的时间成本。
◆框架具备持续更新能力，能够跨导航回合不断优化清除时间估计。实验表明，该方法在仿真中不到20次观测即可收敛至接近真实分布的Oracle水平，真实部署也验证了其在线学习与自适应优化的有效性。</td></tr>
<tr><td>2026-05-30</td><td>BEVIO: Efficient Bird&#x27;s-Eye-View based Sparse-Update Visual-Inertial Odometry for Lunar Day-Night Navigation<br><a href='http://arxiv.org/pdf/2606.00709'>论文</a></td><td>针对月球车在极端资源限制下视觉更新稀疏以及昼夜自照明导致特征关联困难的问题，本文提出了BEVIO算法。
◆提出基于鸟瞰图的图像匹配方案，增强了对较大帧间运动的鲁棒性。
◆在视觉外观发生显著变化时，依然能实现可靠的特征匹配，克服了昼夜及自照明环境的挑战。
通过高保真月面仿真和半比例月球车真实长时昼夜部署实验进行了广泛评估。
结果表明，该方法在视觉更新率低至0.25赫兹时仍能实现可靠的昼夜导航，非常适合算力与功耗受限的月球车。</td></tr>
<tr><td>2026-05-29</td><td>Predicted-Flow Control Barrier Functions for Real-Time Safe Optimal Control<br><a href='http://arxiv.org/pdf/2606.00297'>论文</a></td><td>本文针对传统控制障碍函数合成困难且目光短浅的问题，提出了预测流控制障碍函数(P-CBF)。
◆将CBF从当前状态的函数推广为有限预测时域内参数化控制计划下预测流的泛函，从而在整个预测时域内提供安全保证。
◆为解决控制约束导致的可行性挑战，引入要求预测流终端进入备用安全集的终端候选P-CBF，并提出调节预测时域的规划时移以确保可行性。
◆通过单个保证可行的凸优化问题联合确定实时控制、控制计划参数与规划时移，使安全集前向不变，并统一了有限时域积分代价优化与安全认证。
该方法的二次规划实现FlowBarrier在机器人导航实验中达到了零安全违规与最低计算时间，综合表现优于现有方法。</td></tr>
<tr><td>2026-05-29</td><td>AR Forcing: Towards Long-Horizon Robot Navigation World Model<br><a href='http://arxiv.org/pdf/2605.31314'>论文</a></td><td>本文针对基于扩散的机器人导航世界模型中训练与推理存在的分布偏移导致长程预测不稳定的问题，提出了AR Forcing自回归训练策略。
◆将标准扩散损失整合到自回归训练循环中，消除了并行监督与自回归推理之间的不一致。
◆模型每一步利用自身预测更新上下文并优化单步噪声预测目标，使训练显式暴露于推理状态分布。
◆无需引入额外判别器或分布匹配损失，保留了原始扩散框架与采样器，易于集成。
实验表明，该方法在多域导航数据集上显著提升了长程导航的图像生成一致性与轨迹预测精度，增强了模型在复杂环境下的鲁棒性。</td></tr>
<tr><td>2026-05-29</td><td>Geometry-Aware Control Barrier Functions for Collision Avoidance via Bernstein Polynomial Approximations<br><a href='http://arxiv.org/pdf/2605.30696'>论文</a></td><td>针对具有不规则几何形状机器人和障碍物的安全导航问题，传统控制障碍函数的形状代理往往过于保守或导致约束数激增。本文提出了一种基于伯恩斯坦多项式符号距离场的几何感知控制障碍函数。
◆提出基于BP-SDF的统一表示方法，将障碍物与机器人统一建模，并以统一的最小距离来表示障碍函数。
◆利用伯恩斯坦多项式的可微性，可以轻松地以闭环方式强制执行控制约束。
仿真结果表明，该方法在单机器人导航和异构多机器人避碰场景中均能高效保障安全。</td></tr>
<tr><td>2026-05-28</td><td>Learning-Based Navigation for Indoor Mobile Robots<br><a href='http://arxiv.org/pdf/2605.30468'>论文</a> | <a href='https://ntdathp.github.io/rl_robot_web/'>代码</a></td><td>本文提出了一种用于室内移动机器人的基于学习的导航框架，结合了监督神经全局规划器与强化学习优化的局部规划器，并在仿真和真实环境中验证了其安全避障导航的有效性。
◆提出基于代价感知A星专家轨迹训练的监督神经全局规划器，以生成可行的全局路线。
◆提出基于学习的DWA局部规划器，将其表述为动态窗口法动作格上的离散候选选择问题。
◆在局部策略训练中，先利用行为克隆初始化，再结合可行性感知掩码通过近端策略优化算法进行精炼。
◆有效整合了基于学习的全局规划与强化学习优化的局部控制，实现了室内环境下的安全目标导向导航。</td></tr>
<tr><td>2026-05-29</td><td>Replicable Simulation-Based Robot Validation through Provenance<br><a href='http://arxiv.org/pdf/2605.29973'>论文</a></td><td>该论文针对基于仿真的机器人测试可复现性不足的问题，提出将数据溯源与FAIR原则相结合以提升测试文档的透明度。
◆提出将数据溯源与FAIR原则深度融合，通过追踪产物关联和添加关于文件来源与设计决策的机器可读元数据来保障验证的可复现性。
◆强调溯源与元数据不应作为最终数据集的事后补充，而必须内嵌于生成数据集的测试流程中，从而实现测试证据的端到端重建。
论文通过扩展现有仿真测试框架引入溯源跟踪与元数据收集机制，成功对移动机器人导航数据集进行了结构化溯源与FAIR元数据的丰富。
最后，论文总结了集成过程中遇到的词汇对齐、属性选择与领域标准采用等障碍，并为在机器人验证工作流中实施以溯源为中心的FAIR元数据提供了可操作建议。</td></tr>
<tr><td>2026-05-28</td><td>Fisher-Preserving Guidance: Training-Free Manifold Constraints for Safe Diffusion Control<br><a href='http://arxiv.org/pdf/2605.29937'>论文</a></td><td>本文针对扩散模型在视觉导航中因更新偏离训练流形而导致轨迹不可靠的问题，提出了一种无需训练的推理方法。
◆提出基于外积跨度投影的费雪保持引导机制，在优化任务目标的同时避免离分布动作引起的费雪漂移，确保更新不偏离流形。
◆利用低秩雅可比分解计算费雪保持更新，每步仅需单次反向传播，满足实时应用要求。
◆引入截断费雪去噪敏感度作为不确定性信号，以此实现鲁棒的多样本动作混合策略。
实验表明，该方法在多种仿真和真实机器人导航任务中，无需额外训练即可显著优于强扩散策略基线。</td></tr>
<tr><td>2026-05-28</td><td>How to Relieve Distribution Shifts in Semantic Segmentation for Off-Road Environments<br><a href='http://arxiv.org/pdf/2605.29599'>论文</a></td><td>本文针对越野环境语义分割中由域差异和传感器损坏引起的分布偏移问题，提出了ST-Seg框架。该框架通过显式扩展源分布来提升分割的鲁棒性和越野导航的安全性。
◆提出风格扩展方法，通过生成多样化的逼真风格拓宽域覆盖范围，有效增强源域有限的风格信息。
◆引入纹理正则化技术，利用深度纹理流形稳定受风格增强学习影响的局部纹理表示。
◆打破以往在固定源分布内隐式泛化的局限，提供了一种直观且显式扩展源分布以应对分布偏移的新思路。
实验证明该框架在多种分布偏移的目标域上均显著优于现有方法。</td></tr>
<tr><td>2026-05-28</td><td>GUITestScape: Towards Open-set Evaluation on Exploratory GUI Testing<br><a href='http://arxiv.org/pdf/2605.29532'>论文</a></td><td>当前探索性GUI测试评估存在两大不足，即仅关注交互缺陷而忽视显示缺陷，且评估受限于预定义标注而无法区分不同的失效模式。
◆提出交互式基准GUITestScape，涵盖61个真实安卓应用及508个交互与显示类型的预设缺陷，弥补了现有基准的缺陷类型局限。
◆引入开放集评估器GUIJudge，将智能体的测试轨迹分解为独立可诊断的能力，实现了超越预定义标注的过程感知评估。
实验表明，GUIJudge大幅优于所有基线，提供了可靠的评估结果。
此外，基准测试揭示了现有模型在两类缺陷上的检测瓶颈，且将GUIJudge的验证器集成至现有智能体中无需重训即可显著提升其检测性能。</td></tr>
<tr><td>2026-05-27</td><td>Chance-Constrained MPPI under State and Dynamic Object Prediction Uncertainty and the Evaluation of Collision Risk Calibration<br><a href='http://arxiv.org/pdf/2605.28330'>论文</a></td><td>现有机会约束MPPI控制隐式假设上游定位与感知不确定性已良好标定，但实际估计器常标定不当，导致过度自信引发安全违规或缺乏自信引发保守冻结。
◆提出一种严谨的评估方法，应用严格评分规则来评估闭环执行期间预测碰撞风险的统计有效性。
◆提出双不确定性机会约束管MPPI实时风险感知规划架构，通过单管无迹变换近似联合整合定位不确定性，并利用蒙特卡洛聚合整合动态障碍物预测不确定性。
在高度杂乱环境中，该框架实现了稳健的失效缓解，能安全过渡至保守机动而不陷入死锁。
其导航成功率较基线提升近28%，且旅行时间最短、社会作用力最小，证明可靠的概率安全性需要整个技术栈具备统计有效的不确定性估计。</td></tr>
<tr><td>2026-06-01</td><td>Adversarial Dual On-Policy Distillation from Expressive Teacher<br><a href='http://arxiv.org/pdf/2605.27095'>论文</a> | <a href='https://github.com/vanzll/FA-OPD'>代码</a></td><td>针对现有具身控制模仿学习方法仅依赖离线专家数据而缺乏在线纠正信号，且标准在线策略蒸馏无法适用于仅有演示场景的问题，本文提出了FA-OPD方法。该方法从演示中学习流匹配教师并与轻量级MLP学生共同训练，在学生交互过程中提供双通道互补信号。
◆设计奖励通道，通过学习状态-动作对的专家相似性目标来驱动长视野策略优化，促进在线探索。
◆设计动作通道，在学生实际访问的状态上提供密集的局部目标，稳定策略的利用。
◆将双通道巧妙耦合，使奖励蒸馏能够泛化超越逐点演示，同时动作蒸馏将探索锚定在类专家行为附近。
实验表明，在六个机器人导航、操作和运动基准测试中，FA-OPD超越了强基线，并在噪声或有限演示条件下展现出显著增强的鲁棒性。</td></tr>
<tr><td>2026-05-28</td><td>Trust, Geometry, and Rules: A Credibility-Aware Reinforcement Learning Framework for Safe USV Navigation under Uncertainty<br><a href='http://arxiv.org/pdf/2605.26974'>论文</a></td><td>本文针对无人水面艇在感知不确定性下安全且符合COLREGs规则的导航难题，提出了一种融合感知可信学习、几何安全屏蔽与连续规则感知嵌入的强化学习框架。
◆可信度加权价值学习通过滤波协方差与经验误差的差异推导动态信任因子，调节评论家异方差损失，防止策略对噪声过拟合。
◆协方差膨胀速度障碍将位置估计不确定性映射为角度裕度，构建保守的几何屏蔽以覆盖危险探索动作。
◆风险感知的COLREGs责任嵌入将二元相遇责任松弛为连续规则信号，提供平滑扇区转换信息并抑制稀疏奖励引起的振荡。
仿真实验表明，该框架能有效提升应对感知不一致的训练鲁棒性，并在避碰与规则合规性上显著优于基线方法。</td></tr>
<tr><td>2026-05-29</td><td>Collaborative Navigation and Exploration with $β$-Sparse Gaussian Processes<br><a href='http://arxiv.org/pdf/2605.26304'>论文</a></td><td>针对未知环境下异构机器人协同导航面临传感、通信和计算限制的问题，本文提出了一种领航机器人与移动传感器机器人的协同导航框架。该框架使传感器能在带宽受限的情况下，在线联合选择传输的地图点与导航动作，并预测未探索区域。
◆提出β-稀疏高斯过程模型，这是一种用于任务感知诱导点选择的新颖且鲁棒的变分稀疏高斯过程模型。
◆开发了一种动作选择策略，有效平衡了任务相关性与环境探索。
仿真实验表明，该框架相比无通信场景可减少18%的路径成本，相比原始数据传输基线可减少76%的信息传输量。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-01</td><td>Evaluating Real-World Generalizability of Algorithm Selection Models<br><a href='http://arxiv.org/pdf/2606.02016'>论文</a></td><td>本文系统性地研究了算法选择模型在合成与真实世界优化景观之间的泛化能力。研究跨越了学术基准与实际应用场景，揭示了现有模型在跨域迁移时的真实表现。
◆构建了涵盖BBOB和CEC学术基准以及机器人轨迹优化和无人机路径规划等真实问题集的综合评估框架。
◆通过系统的跨基准评估，深入分析了AS模型的跨域迁移表现，明确识别出泛化成功与失效的具体场景。
◆揭示了当前AS方法在现实特定领域应用中面临的挑战，为开发更可靠且广泛适用的真实世界优化AS系统提供了重要指导。</td></tr>
<tr><td>2026-05-31</td><td>Learning-based Directed Graph Abstraction of Combinatorial Spaces for Order-Preserving Search in Mixed-Combinatorial Nonlinear Optimization<br><a href='http://arxiv.org/pdf/2606.01425'>论文</a></td><td>针对混合组合非线性规划问题中传统编码方式引入伪关系、增加维度且需额外约束的缺陷，本文提出了一种基于学习的组合空间抽象方法。
◆首次提出使用边场图网络对组合空间进行结构化抽象，将无向全连接组合图映射为指示改进方向的有向图。
◆将该方向感知的抽象模型作为推荐系统，在仅搜索连续变量的优化框架中检索最适组合，提升了检索的可扩展性与可解释性。
实验将该方法与粒子群和遗传算法求解器结合，在三个基准非线性问题上进行了测试。
结果表明，相比使用索引组合的基线求解器，基于图神经网络的推荐系统在平均最优值和鲁棒性上均取得更优表现。</td></tr>
<tr><td>2026-05-31</td><td>ActMVS: Active Scene Reconstruction with Monocular Multi-View Stereo<br><a href='http://arxiv.org/pdf/2606.01367'>论文</a> | <a href='https://github.com/TrickyGo/ActMVS'>代码</a></td><td>该论文提出了ActMVS，这是首个仅依赖单目视觉的主动场景重建框架，解决了传统方法依赖深度传感器增加成本，以及现有单目方法无法实时提供全局一致稠密深度的问题。
◆提出视图因子图构建方法，用于指导多视图立体的深度预测。
◆引入全局深度优化机制，实现在线生成高质量且全局一致的稠密深度图。
这些创新使单目机器人或无人机能够实时维护高置信度的占据地图，实现安全的无碰撞轨迹规划与自主重建。
实验证明该方法性能可媲美基于RGB-D的方案，极大提升了单目视觉的空间智能与实用性。</td></tr>
<tr><td>2026-05-31</td><td>Make Your VLA More Robust Without More Data By Interleaving Motion Planning<br><a href='http://arxiv.org/pdf/2606.00985'>论文</a></td><td>视觉-语言-动作模型在长视距任务中因目标难以维持和误差累积导致表现不佳，单纯增加微调数据无法解决此问题。为此，本文提出无需额外训练的运动规划与VLA交织框架MPVI。
◆将基于模型的运动规划与VLA结合，利用开放词汇目标检测、前沿探索与运动规划，实现在杂乱场景中对远处或遮挡目标的定位与导航。
◆设计了基于视觉语言模型的完成度检查与本体感受触发机制，有效解决模块间可靠切换的难题。
实验表明，该方法在BEHAVIOR-1K基准上，任务进度相比顶级端到端基线提升了113%。这充分证明了MPVI框架在不增加数据前提下提升VLA鲁棒性的显著效果。</td></tr>
<tr><td>2026-05-30</td><td>Generative Multi-Robot Motion Planning via Diffusion Modeling with Multi-Agent Reinforcement Learning Guidance<br><a href='http://arxiv.org/pdf/2606.00933'>论文</a></td><td>本文提出了一种结合去中心化生成式轨迹规划与多智能体强化学习引导的协调框架，用于解决多机器人运动规划中的交互与可扩展性难题。
◆利用仅在单智能体数据上训练的扩散模型为每个机器人独立生成可行且多样的候选轨迹，保留了去中心化规划的可扩展性。
◆通过多智能体强化学习训练的集中式价值函数引导反向扩散过程，采用基于梯度的策略和指数倾斜公式，将去噪分布偏向具有更高多智能体期望回报的轨迹。
◆无需进行集中式联合规划或重新训练生成模型，即可实现具备交互意识的轨迹生成，有效减少智能体间冲突。
实验表明，该价值引导规划将四机器人环境中的智能体干扰率从55.4%降至41.8%，成功在保持去中心化扩展性的同时实现了有效协调。</td></tr>
<tr><td>2026-05-30</td><td>From Cues to Horizons: Dynamic Risk Horizon Profiling for Trajectory Prediction<br><a href='http://arxiv.org/pdf/2606.00857'>论文</a> | <a href='https://github.com/bilab-nyu/RHP'>代码</a></td><td>本文针对现有风险感知轨迹预测方法仅将历史风险作为辅助信号而忽略其未来演变与不确定性的问题，提出了一种新的解决方案。
◆提出了风险视野画像（RHP）模块，将连续可学习的势场模型引入风险感知轨迹预测中。
◆该模块通过计算周围物体的时空接近度来描绘未来视野内的风险分布，自适应地识别人类驾驶员感知的关键时刻。
模型在涵盖高速与城市场景的highD和SHRP2数据集上进行验证，5秒预测的RMSE和minFDE分别降低了25.0%和29.1%。
实验表明该方法在长短视野预测上均表现优异且泛化能力强，为更真实的自动驾驶路径规划和更安全的辅助驾驶系统提供了支持。</td></tr>
<tr><td>2026-05-30</td><td>A Framework for Motion Planning with Temporal Logic Precedence Specifications via Augmented Graphs of Convex Sets<br><a href='http://arxiv.org/pdf/2606.00842'>论文</a></td><td>本文提出了一种运动规划框架，能够在避障的同时满足由信号时序逻辑片段表达的逻辑先后约束。该框架对包含障碍物、钥匙和门的环境进行建模，其中获取钥匙可解锁对应门并可能开辟通往目标的更短路径。
◆基于对自由空间的精确凸分割，构建了增广凸集图，其分层结构精确编码了钥匙与门的先后逻辑。
◆通过在增广凸集图中寻找最短路径，实现了同时选择最优钥匙收集序列与计算最优连续轨迹。
该方法在有限的贝塞尔曲线参数化下提供了精确解，有效解决了具有时序先决条件的复杂运动规划问题。</td></tr>
<tr><td>2026-05-30</td><td>ROG-Grasp: Root-Oriented Geometry for Robotic Grasping and Placement<br><a href='http://arxiv.org/pdf/2606.00449'>论文</a></td><td>本文提出了ROG-Grasp框架，这是一种基于几何的机器人抓取与放置方法，通过RGB-D感知从农产品根部表面几何形状估计其朝向，解决了农业加工中的朝向感知操作问题。
◆提出结合YOLO根部检测器与点云平面拟合推断根部法线，从而实现稳定的抓取姿态生成。
◆设计了受朝向约束的笛卡尔运动规划，确保农产品能以一致的构型被放置。
◆与视觉语言动作策略相比，该方法在抓取可靠性和准确性上更优，且执行速度更快。
在番茄和洋葱的实验中，该框架在孤立与杂乱场景下均展现出高成功率和稳定的执行时间。
这些结果证明了几何驱动感知在实际朝向控制操作任务中的有效性和实用性。</td></tr>
<tr><td>2026-05-29</td><td>Coupling Language Models with Physics-based Simulation for Synthesis of Inorganic Materials<br><a href='http://arxiv.org/pdf/2606.00315'>论文</a></td><td>机器学习虽能提出新型无机材料，但复杂的物理过程和计算工具的缺乏使得合成规划极具挑战。本文提出了一个新型混合框架，通过结合热力学数据库与简化动力学模型来评估大语言模型在无机合成规划中的表现。
◆将大语言模型与基于物理的模拟相耦合，构建了能够近似真实合成条件的评估框架。
◆通过对比经典路径规划算法，揭示了大语言模型的隐式先验知识能够生成更具可行性的合成策略。
该研究以铌氧系统为案例，突显了在复杂合成问题中大语言模型隐式先验的独特价值，为无机材料合成规划提供了新思路。</td></tr>
<tr><td>2026-05-29</td><td>LiftNav: Path Planning via Semantic Lifting in TSDF-Guided Gaussian Splatting<br><a href='http://arxiv.org/pdf/2605.31376'>论文</a></td><td>本文提出了LiftNav混合导航框架，解决了传统TSDF缺乏语义和高斯溅射几何软导致避障不精确的问题。该框架基于TSDF与高斯溅射双地图构建，实现了可靠的碰撞避障与物体级理解。
◆设计了基于YOLO检测与TSDF三维提升的实时管线，无需密集三维嵌入即可实现灵活的语义导航。
◆引入了基于铰链损失的碰撞惩罚机制，有效提升了轨迹的平滑度与安全性。
◆结合B样条轨迹优化，在仿真实验中相比现有基线实现了百分之百的轨迹可行率和更短的路径。</td></tr>
<tr><td>2026-05-29</td><td>Haptic Sorter: A Unified Planning Framework for Online Shape Estimation and Real-Time Pose Inference<br><a href='http://arxiv.org/pdf/2605.31352'>论文</a></td><td>本文针对机器人操作中物体形状与姿态先验未知及传感器遮挡问题，提出了一个融合触觉感知、建模与操作规划的统一几何框架。
◆引入贝叶斯优化指导触觉探索以推断物体形状，并利用超椭圆近似几何边界。
◆自适应地构建编码物体几何的操作势函数，用于准静态机器人与物体交互。
◆提出基于模型预测和触觉反馈的在线常微分方程，实现物体实时姿态推断。
该框架在二维机器人分拣任务的仿真与真实多臂平台上进行了验证，证明了其在不同几何形状下的鲁棒性与泛化能力。</td></tr>
<tr><td>2026-05-29</td><td>AR Forcing: Towards Long-Horizon Robot Navigation World Model<br><a href='http://arxiv.org/pdf/2605.31314'>论文</a></td><td>该论文指出了基于扩散的机器人导航世界模型中，并行监督训练与自回归推理间的分布偏移导致长程预测不稳定的问题。为此，论文提出了AR Forcing自回归训练策略来消除这一偏差。
◆将标准扩散损失整合进自回归训练循环，模型每步利用自身预测更新上下文并优化单步噪声预测，使其在训练时显式暴露于推理状态分布。
◆无需引入额外判别器或分布匹配损失，完全保留原始扩散框架与采样器，方法简单且极易集成。
◆在多个导航数据集上的实验表明，该方法显著提升了长程导航中图像生成的一致性与轨迹预测精度，增强了模型在复杂及未知环境下的鲁棒性。</td></tr>
<tr><td>2026-05-29</td><td>DriveMA: Driving Vision-Language-Action Models with verifiable Meta-Actions<br><a href='http://arxiv.org/pdf/2605.31271'>论文</a></td><td>本文提出DriveMA框架，旨在解决驾驶视觉语言动作模型中语言与动作间的鸿沟问题，并在Waymo等数据集上取得了最先进的端到端规划性能。
◆提出可验证的元动作，将未来自车运动转化为紧凑的语言域意图，并可通过轨迹标注管线构建以及基于规则的投影进行验证。
◆引入动作中心的监督训练，有效利用元动作的可验证性来指导模型学习。
◆设计数据高效的回合级信用分配强化学习框架，通过密集奖励与精确信用分配，显式对齐高级决策与低级轨迹规划。
实验结果表明，即使是简单的元动作接口，只要具备可验证性并针对语言动作对齐进行优化，即可实现卓越的自动驾驶规划效果。</td></tr>
<tr><td>2026-05-29</td><td>Trajectory Planning for Non-Communicating Mobile Robots using Inverse Optimal Control<br><a href='http://arxiv.org/pdf/2605.30906'>论文</a></td><td>该论文提出了一种新颖的轨迹规划与预测组合算法，以解决非通信移动机器人避障场景下的高效交互问题。
◆利用逆最优控制方法，基于观测到的历史轨迹来估计所有机器人的未知目标状态。
◆引入视角转换机制，每个机器人从其他机器人视角出发进行自我预测，并结合估计目标状态求解联合预测问题。
◆将联合预测结果直接融入自身的轨迹规划中，实现预测与规划的深度耦合。
仿真实验表明，在2至8个机器人的场景下，该方法使所有机器人到达目标的中位耗时缩短了9.8%。
同时，该算法确保求解器始终能成功找到规划或预测问题的解，彻底避免了无解情况的发生。</td></tr>
<tr><td>2026-05-31</td><td>Mean-Field Diffuser: Scaling Offline MARL to Thousands of Agents<br><a href='http://arxiv.org/pdf/2605.30190'>论文</a></td><td>这篇论文针对扩散式规划在多智能体离线强化学习中因联合轨迹空间维度爆炸而难以扩展的问题,提出了MF-Diffuser框架,将轨迹规划提升至轨迹分布的Wasserstein空间,利用混沌传播性质,仅用少量代表性智能体即可刻画整个种群的动态,从而支撑千级以上规模的离线多智能体强化学习。论文同时建立了端到端的次优性理论界,并通过三个均值场基准实验验证了方法在大规模和次优数据场景下的显著优势。

核心贡献和创新点如下:

◆ 首次将扩散规划提升至轨迹分布的Wasserstein空间,借助混沌传播性质用小规模代表性智能体子集刻画全种群动态,突破联合空间维度灾难,使离线MARL可扩展至上千智能体。

◆ 提出价值加权的混沌熵目标函数,在保证生成保真度的同时实现回报最大化,协调了扩散模型的生成质量与策略优化目标。

◆ 设计了分层的由粗到细策略,在去噪过程中渐进式扩展智能体种群规模,提升大规模场景下的生成效率与稳定性。

◆ 给出包含四个可解释项的端到端次优性理论界,证明均值场近似误差以O(H²/√N)规模下降,且离线分布偏移不随种群规模N增长,理论上保证生成策略为近似均值场纳什均衡并给出显式收敛保证。

◆ 在涵盖阶段博弈、序列动态与对抗团队竞争的三类均值场基准上取得多数最优表现,在次优离线数据和N≥10³的极端规模下增益最为显著。</td></tr>
<tr><td>2026-05-28</td><td>A Radius-Sensitive Approximation Algorithm for Connected Submodular Maximization<br><a href='http://arxiv.org/pdf/2605.30053'>论文</a></td><td>本文研究连通子模最大化问题(CSM)及其有向版本(DCSM)和有向有根版本(DRCSM)。该问题在无线网络部署、路径规划、疫情传播和癌症基因组研究等领域具有重要应用。论文针对以最优解半径r为参数的近似比进行了显著改进,突破了此前最优的Ω(1/r)和Ω(1/√k)近似界。作者提出了一个多项式时间框架,对于(有向)CSM达到Ω(ε³/r^ε)的近似比,对于DRCSM达到Ω(δε³/r^ε)的双准则近似,其中规模约束最多被违反1+δ倍。

◆ 首次将CSM的近似比从Ω(1/r)改进到Ω(ε³/r^ε),由于r≤k,该结果同时优于以k为参数的现有最优界Ω(1/√k)。

◆ 提出核心算法GreedyRadius,可将任意以k为参数的双准则近似算法转化为以r为参数的同等近似比算法(至多相差常数因子),具有良好的通用性和可扩展性。

◆ 为DRCSM设计了灵活的双准则近似框架,允许在近似比与规模约束违反程度之间进行可调节的权衡(δ可在[1/k,1]之间取值)。

◆ 将算法框架统一推广到无向、有向以及有向有根三种CSM变体,扩展了问题的适用范围。

◆ 引入参数ε实现近似比的精细调控,为不同应用场景下的算法性能优化提供了理论基础。</td></tr>
<tr><td>2026-05-28</td><td>FLIP: Real-Time and Resilient Formation Planning for Large-Scale DIstributed Swarms via Point Cloud Registration<br><a href='http://arxiv.org/pdf/2605.29704'>论文</a></td><td>该论文提出了FLIP,一种面向大规模分布式无人机集群的实时、弹性编队规划方法,通过将编队位置分配问题转化为时空点云配准问题,实现了高性能且大规模的协同轨迹规划。核心思路是让每个智能体分布式地计算自身当前位置与所有其他智能体期望编队位置之间的匹配结果,从而获得最优编队位置序列(OFPS),并基于此优化协同编队轨迹。论文采用带有外点剔除机制的点云配准方法,有效阻止次优轨迹和失效智能体在协同网络中的传播扩散。最终通过120架无人机的大规模仿真验证了方法的有效性,并与SOTA方法进行了严格对比基准测试,展示了其优越性。

◆ 首次将最优编队位置序列(OFPS)计算问题创新性地转化为时空点云配准(PCR)问题,为大规模编队分配提供了全新求解范式。

◆ 提出基于带外点剔除的点云配准方法,可快速完成大规模编队位置匹配,显著降低计算复杂度。

◆ 设计了具有弹性的分布式协同机制,通过外点剔除阻断次优轨迹和失败智能体在协作网络中的扩散影响,提升集群鲁棒性。

◆ 实现了弹性、高效与分布式三者统一的轨迹规划框架,突破了传统方法在表示简化与全协作计算负担之间的权衡难题。

◆ 在120架无人机规模的仿真场景中验证了方法的可扩展性,并通过严格基准测试证明其相较于SOTA方法的显著优势。</td></tr>
<tr><td>2026-05-28</td><td>The Open Motion Planning Library 2.0<br><a href='http://arxiv.org/pdf/2605.29301'>论文</a></td><td>本文介绍了开放运动规划库(OMPL)的重大升级版本OMPL 2.0。OMPL自2008年首次发布以来,已成为运动规划领域的基石,提供了广泛的基于采样的最先进算法实现。经过近二十年的持续开发,该库不断扩展新的规划器、状态空间和问题表述,涵盖从渐近最优规划、惰性规划到约束运动规划及时序逻辑目标规划等多种功能。OMPL 2.0在此基础上进行了重大演进,旨在通过硬件加速实现实时运动规划,并与现代AI研究工作流无缝集成。论文同时回顾了OMPL与运动规划领域共同成长的历程,并讨论了该库对研究界的广泛影响。

核心创新点如下:

◆ 推出OMPL 2.0版本,作为运动规划库的重大演进,标志着该领域工具链的全新升级。

◆ 通过硬件加速技术实现实时运动规划能力,显著提升了规划效率与响应速度。

◆ 与现代AI研究工作流无缝集成,促进了传统运动规划方法与人工智能技术的深度融合。

◆ 持续扩展多样化的规划器与状态空间,涵盖渐近最优、惰性规划、约束运动规划以及基于时序逻辑目标的规划等前沿方向。

◆ 系统性回顾了OMPL与运动规划领域协同发展的历程,为后续研究提供了重要的参考与反思视角。</td></tr>
<tr><td>2026-05-27</td><td>Integrated Exploration-Aware UAV Route Optimization and Path Planning<br><a href='http://arxiv.org/pdf/2605.28654'>论文</a></td><td>本文提出了一个集成探索感知的无人机路线优化与路径规划框架，用于解决先验信息不确定且动态变化下的危险环境监测问题。核心贡献在于将有限的飞行续航合理分配于检查已知危险区域和探索未知信息区域之间。
◆将报告的危险源建模为不确定的感兴趣区域而非确认目标，要求无人机在检查报告区域的同时探索信息量大的区域。
◆通过在路线中增加辅助伪节点来提升空间覆盖率，并优化动态可行的B样条轨迹以进行局部探索。
◆引入在线重规划机制，根据无人机实时测量更新网格信念图，并在新信息和剩余预算允许时自适应调整后续轨迹。
实验表明，该方法在四十八种场景配置下表现优异，在线重规划比离线优化和直线遍历的平均KL散度降低效果分别提升了15.9%和48.6%。</td></tr>
<tr><td>2026-05-28</td><td>Multi-Robot Box Transport over Different Surfaces with Decentralized Role-based Proportional Control<br><a href='http://arxiv.org/pdf/2605.26430'>论文</a></td><td>该论文提出了一种名为R2P2的异步分散式任务与运动规划方法，解决多机器人在不同倾斜度与摩擦力表面上协同运输箱子的挑战。
◆提出去中心化架构，免除机器人间的通信同步与共识需求，有效规避单点故障。
◆设计基于操作模式动态分配角色的机制，根据旋转或平移需求赋予机器人推、支撑或阻止等角色。
◆融合基于规则的控制与比例速度控制，机器人仅需观测自身与箱子的位置及朝向即可执行动作。
◆方法在多变的地形摩擦、倾斜度及箱子质量场景中展现强泛化能力，成功率优于传统虚拟领导者跟随者方法。
◆通过六台机器人的仿真测试与四台Turtlebot的实物实验，充分验证了该策略的有效性与实用性。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-01</td><td>Dexterity-BEV: Aligning 3D World and Actions for Generalizable Robot Policies Learning<br><a href='http://arxiv.org/pdf/2606.02274'>论文</a> | <a href='https://hnuzhy.github.io/projects/Dex-BEV'>代码</a></td><td>本文针对端到端操作策略依赖2D输入且缺乏跨机器人和相机的3D空间对齐的局限性，提出了Dexterity-BEV方法。
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
<tr><td>2026-05-18</td><td>Open-source segmentation and biometry dataset using spectrally-multiplexed whole-eye optical coherence tomography<br><a href='http://arxiv.org/pdf/2605.19191'>论文</a></td><td>本文针对全眼OCT系统在成像性能上的权衡以及前节标注数据匮乏的问题，提出了新型频分复用WEOCT系统并开源了大规模数据集。
◆采用1310nm和1060nm双同步200kHz扫频光源，突破了现有系统在信噪比、速度与运动伪影间的局限。
◆构建了包含深度学习分割、3D畸变校正及光线追踪折射校正的端到端自动化流水线，实现了解剖学精确的眼球分层3D重建。
◆通过超300人的用户及体模研究，验证了系统能够同时精准测量角膜地形图与3D瞳孔中心。
◆发布了目前稀缺的大规模开源综合数据集，包含276名受试者的6621个标注体积及校准的3D前节点云。</td></tr>
<tr><td>2026-05-18</td><td>See Silhouettes in Motion with Neuromorphic Vision<br><a href='http://arxiv.org/pdf/2605.17984'>论文</a></td><td>本文针对移动平台上传统帧成像因运动模糊和恶劣光照导致准双峰物体二值化失效的问题，提出一种基于神经形态视觉的帧与事件双模态二值化方法。该方法能在仅CPU设备上实现实时高帧率二值化，为资源受限边缘平台的轻量级感知与交互铺平了道路。
◆提出帧与事件协同的双模态机制，利用事件相机的高时间分辨率和高动态范围优势，有效减少运动模糊并显著提升恶劣光照下的二值化表现。
◆设计异步工作流，规避了传统时间分箱重建在事件稀缺时易崩溃的缺陷，确保在极端千赫兹帧率下依然维持清晰的目标轮廓。
◆实现轻量化高效计算，在仅CPU设备上达成实时高帧率处理，且输出的二值结果可作为可靠表征直接赋能多种下游任务。</td></tr>
<tr><td>2026-05-17</td><td>Channel Modeling and LED Spot Detection for Dense Image-Sensor Visible Light Communication<br><a href='http://arxiv.org/pdf/2605.17375'>论文</a></td><td>针对高密度LED阵列可见光通信中光斑模糊重叠引发严重符号间干扰，以及径向畸变与暗角效应阻碍信号检测的问题，本文提出一种保持全信令密度的鲁棒解码框架。
◆提出导频辅助的几何识别方法，结合点扩散函数约束的霍夫变换与圆心对齐细化技术。
◆引入径向畸变校正与暗角感知补偿机制，恢复几何一致性并抑制边缘检测误差。
◆利用导频帧的先验结构知识，在严重光学畸变下有效分离重叠的LED信号。
实验表明该方法解码精度和吞吐量显著优于传统基线方法，在干扰环境下具备高效应用潜力。</td></tr>
<tr><td>2026-05-15</td><td>DepthPolyp: Pseudo-Depth Guided Lightweight Segmentation for Real-Time Colonoscopy<br><a href='http://arxiv.org/pdf/2605.16519'>论文</a> | <a href='https://github.com/ReaganWu/DepthPolyp/'>代码</a></td><td>本文提出了DepthPolyp，一个基于伪深度引导多任务学习的轻量级鲁棒息肉分割框架，旨在解决真实临床环境中运动模糊和光照不稳导致的性能下降问题。
◆引入层级Ghost分解，实现了紧凑高效的视觉特征生成。
◆提出交错混洗融合机制，以极低计算成本完成跨尺度特征交互。
◆设计动态分组门控模块，实现了自适应的分组特征权重分配与调制。
实验表明，该方法在跨数据集泛化测试中表现优异，在真实手术视频评估中甚至超越了20倍参数量的模型。
该模型仅需3.57M参数和0.86 GMACs，移动端帧率超180 FPS，极具资源受限临床环境下的实时部署潜力。</td></tr>
<tr><td>2026-05-13</td><td>What Limits Vision-and-Language Navigation ?<br><a href='http://arxiv.org/pdf/2605.13328'>论文</a> | <a href='https://yunheng-wang.github.io/stereonav-public.github.io'>代码</a></td><td>本文提出StereoNav框架，解决了视觉语言导航中从仿真到真实部署时因感知不稳定和指令模糊导致的性能下降问题。
◆引入目标位置先验作为合成训练与物理执行间的持久桥梁，提供跨域不变的稳定视觉引导，在指令模糊时实现可靠的空间定位。
◆利用立体视觉构建语义与几何的统一表示，通过增强深度感知减轻运动模糊和光照变化的干扰，实现精确的动作预测。
该方法在R2R-CE和RxR-CE数据集上以更少的参数和训练数据取得了最先进的性能。
真实机器人部署也证实了其在复杂非结构化环境中显著提升了导航的可靠性。</td></tr>
<tr><td>2026-05-12</td><td>EgoEV-HandPose: Egocentric 3D Hand Pose Estimation and Gesture Recognition with Stereo Event Cameras<br><a href='http://arxiv.org/pdf/2605.12297'>论文</a> | <a href='https://github.com/ZJUWang01/EgoEV-HandPose'>代码</a></td><td>本文提出了EgoEV-HandPose端到端框架，旨在解决传统相机运动模糊及现有事件相机自我运动干扰与深度模糊等限制，实现立体事件流下的3D双手姿态估计与手势识别。
◆提出KeypointBEV立体融合模块，将特征提升至鸟瞰图空间，并利用迭代重投影引导的细化循环逐步解决深度不确定性及强化运动学一致性。
◆构建EgoEVHands数据集，这是首个大规模真实世界自我中心立体事件相机手部感知数据集，包含5419个标注序列及38种手势类别的密集3D与2D关键点。
实验证明，该方法以30.54毫米的MPJPE和86.87%的手势识别准确率取得了最优性能。
特别是在低光照和双手遮挡场景下，该框架显著超越了现有基于RGB和事件相机的方案，为事件相机自我中心感知设立了新基准。</td></tr>
<tr><td>2026-05-12</td><td>BronchoLumen: Analysis of recent YOLO-based architectures for real-time bronchial orifice detection in video bronchoscopy<br><a href='http://arxiv.org/pdf/2605.11748'>论文</a></td><td>本文提出了BronchoLumen，一个基于YOLO的实时支气管镜视频支气管开口检测系统，旨在辅助呼吸道导航和计算机辅助诊断。
◆首次仅利用有限的公开数据集，探索并验证了最先进的目标检测架构在不同图像域中鲁棒检测支气管开口的可行性。
◆深入对比了广泛使用的YOLOv8与集成注意力模块的最新架构YOLOv12，揭示出YOLOv12虽精度略低，但具有更优的目标定位准确性。
◆开发了具有高准确性和效率的跨域开源权重解决方案，且系统在运动模糊和低对比度等挑战下仍展现出整体鲁棒性。
该研究通过公开发布模型，为支气管镜导航领域的进一步研究提供了重要基准和工具。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>4736</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4136</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2406</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1605</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1598</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1412</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1251</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1227</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>920</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>915</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>910</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>793</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>780</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>736</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>722</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>701</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>629</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>626</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>620</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>583</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>561</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>551</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>530</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>498</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>471</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>433</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>395</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>341</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>336</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>261</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>252</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>234</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>229</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>222</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>197</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>195</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>153</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2842</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1631</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1351</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1096</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1035</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>869</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>696</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>654</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>649</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>618</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>582</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>571</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>565</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>560</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>549</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>513</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>480</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>461</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>440</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>440</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>335</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>311</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>298</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>281</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>276</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>258</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>221</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>206</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>201</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>186</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>176</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>168</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>166</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>159</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>150</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
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
> 更新于: 2026.06.02
