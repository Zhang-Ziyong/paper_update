# 计算机视觉领域最新论文 (2026.07.03)

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
<tr><td>2026-07-02</td><td>A Stereo Visual SLAM System Using Object-Level Motion Estimation and Geometric Filtering Based on Cross Disparity<br><a href='http://arxiv.org/pdf/2607.02005'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-02</td><td>DL-SLAM: Enabling High-Fidelity Gaussian Splatting SLAM in Dynamic Environments based on Dual-Level Probability<br><a href='http://arxiv.org/pdf/2607.01860'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-02</td><td>DL-VINS-Factory: A Modular Framework for Learned Visual Front-Ends in Visual-Inertial SLAM<br><a href='http://arxiv.org/pdf/2607.01757'>论文</a> | <a href='https://github.com/limshoonkit/DL-VINS-Factory-ROS2/'>代码</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-30</td><td>VOCA: Visual Odometry with Codec Awareness<br><a href='http://arxiv.org/pdf/2607.00189'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-30</td><td>PRISM-VO: Scale-Aware Visual Odometry Using Photometric Plenoptic Bundle Adjustment<br><a href='http://arxiv.org/pdf/2607.00176'>论文</a> | <a href='https://prism-vo.github.io/'>代码</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-30</td><td>ForgeDrive: Bidirectional Cross-Conditioning for Unified Visual-Action Generation in Autonomous Driving<br><a href='http://arxiv.org/pdf/2606.31226'>论文</a></td><td>◆提出ForgeDrive，一个统一的自回归扩散框架，将未来建模为逐时刻的“图像帧-动作”对，实现视觉生成与动作规划的紧密耦合。
◆它用act-then-imagine范式替代传统imagine-then-act，避免视觉生成误差先行累积并传递到规划阶段。
◆训练中解耦视觉与动作的扩散时间步，并引入类似UniDiffuser的噪声调度，使模型能在两种模态间双向推断与交叉条件生成。
◆推理时先生成动作，再用动作提升未来帧生成质量，进而反哺下一步动作，形成视觉与行动的闭环增强。
◆模型还加入未来自车状态预测，进一步提升规划能力；在NAVSIM实验中同时统一驾驶仿真、规划和视觉里程计，并优于强基线规划器。</td></tr>
<tr><td>2026-06-29</td><td>Robust and Efficient Monocular 3D Gaussian SLAM for Kilometer-Scale Outdoor Scenes<br><a href='http://arxiv.org/pdf/2606.30436'>论文</a></td><td>◆提出KiloGS-SLAM，面向公里级室外场景解决单目3DGS-SLAM中长期位姿易漂移与大规模建图显存开销高的耦合难题。
◆设计运动自适应混合跟踪模块，通过条件触发的三层求解流程提升长序列位姿鲁棒性。
◆该跟踪模块可在Essential矩阵与PnP模型间动态切换，以应对不同运动模式和几何退化情况。
◆引入按需启动的基础模型，在轨迹发生灾难性漂移时进行恢复，增强系统长期运行稳定性。
◆提出生命周期管理的高斯建图策略，结合概率初始化、分块多视图增密与剪枝，在保留细节的同时显著减少冗余，实验表明其在单GPU上可处理超过1万帧并达到先进的跟踪和渲染效果。</td></tr>
<tr><td>2026-06-29</td><td>CSAR: Containerized System Architecture for Robotics<br><a href='http://arxiv.org/pdf/2606.30293'>论文</a> | <a href='https://github.com/goyoambrosio/CSAR'>代码</a></td><td>◆提出CSAR这一面向机器人团队与边缘-云连续体的容器化系统架构，解决依赖隔离、兼容性、复现性和异构部署难题。
◆将LXC/LXD系统容器、ROS 2/DDS通信和三层边缘基础设施结合，形成持久、硬件亲和且与实验负载解耦的运行环境。
◆通过基础设施核心、平台与多用户编排、计算与加速三层设计，实现强隔离、受控资源共享和拓扑感知网络。
◆在真实学术机器人实验室中部署验证，展示其对多用户协作开发、共享专用硬件和安全原型实验的支持。
◆通过边缘卸载3D SLAM和GPU加速语义建图案例评估，证明CSAR能提升资源利用率、简化集成并增强实验可复现性。</td></tr>
<tr><td>2026-06-29</td><td>Self-supervised Geometry Reasoning for LiDAR Simultaneous Localization and Mapping<br><a href='http://arxiv.org/pdf/2606.30166'>论文</a></td><td>◆提出一种用于LiDAR SLAM的自监督几何推理框架，解决传统手工局部几何估计在稀疏点云和低分辨率LiDAR下噪声大、不稳定的问题。
◆将每个点显式建模为高斯分布，用协方差表示局部几何，从而获得可解释的符号化几何表示。
◆无需密集几何标签或真实位姿，通过预测协方差、点对应关系和SLAM轨迹之间的一致性关系构造自监督信号。
◆设计几何学习与SLAM相互促进的递归闭环：更好的几何提升定位建图，更准确的轨迹又提供更干净的监督。
◆方法与后端无关，可直接插入现有LiDAR SLAM系统而无需改动架构。
◆在KITTI及不同LiDAR分辨率实验中，该方法同时提升了里程计精度和全局配准效果。</td></tr>
<tr><td>2026-06-29</td><td>MSFA-Net: An Advanced Deep Learning Model for Identifying Blue Horizontal-Branch Stars from LAMOST DR12<br><a href='http://arxiv.org/pdf/2606.29918'>论文</a></td><td>◆提出MSFA-Net两阶段框架，用于从LAMOST DR12低分辨率光谱中高可靠识别蓝水平分支星，缓解传统光谱分类难题。
◆模型融合多尺度卷积与软频率注意力，同时捕捉波长域和傅里叶频域中的判别特征。
◆在测试集中，初筛多分类精度达94.67%，二阶段二分类精度达98.07%，表现出较强筛选能力。
◆将模型应用于LAMOST DR12后获得27,853条BHB候选光谱，并经去重和已知源剔除发现3583颗新的BHB星。
◆论文结合Balmer线轮廓拟合、SLAM大气参数估计以及Gaia DR3测光交叉验证，构建了更大且较均一的BHB星表，为银河晕结构和恒星族群研究提供新数据基础。</td></tr>
<tr><td>2026-06-30</td><td>TACO: A Test and Check Framework for Robust Pose Graph Optimization<br><a href='http://arxiv.org/pdf/2606.29851'>论文</a></td><td>◆提出TACO（Test And Check Optimization），一个面向鲁棒位姿图优化的在线框架，用于在SLAM中抑制错误回环导致的外点影响。
◆其核心思想不是显式建模内点/外点，而是增量近似寻找最大一致测量集合。
◆“Test”部分设计了增量概率一致性算法IPC，可在线评估每个新回环约束的一致性。
◆“Check”部分提出Switchable Outlier Sanitization，周期性利用Switchable Constraints清理IPC误接纳的不一致约束。
◆实验表明，TACO在2D和3D数据集上兼具接近离线鲁棒方法的精度与在线部署所需的效率，并开源了实现。</td></tr>
<tr><td>2026-06-29</td><td>MyGO-Splat: Multi-Objective Closed-Loop Geometric Feedback for RGB-Only Gaussian SLAM<br><a href='http://arxiv.org/pdf/2606.29738'>论文</a></td><td>◆ MyGO-Splat提出一种面向RGB-only单目SLAM的闭环Gaussian SLAM框架，解决传统单目系统尺度不确定和几何漂移难以自校正的问题。
◆ 该方法将3D Gaussian原语解析光栅化为逐像素深度和表面法线，使已优化地图能够反向监督相机位姿跟踪。
◆ 论文引入尺度感知的自适应对齐机制，将基础模型预测的单目深度投影到全局一致的Gaussian空间中。
◆ 通过“深度先验—Gaussian优化—位姿反馈”的闭环设计，系统实现了尺度反馈和几何自校正，提升了尺度稳定性。
◆ 实验表明，MyGO-Splat在仅使用RGB输入的情况下，获得了接近RGB-D方法的表现，并改善了外观与几何的一致性。</td></tr>
<tr><td>2026-06-28</td><td>VCS-SLAM: Geometry-Validated Semantic Evidence Fusion for 3D Gaussian SLAM<br><a href='http://arxiv.org/pdf/2606.29494'>论文</a></td><td>◆提出VCS-SLAM，一个面向RGB-D 3D Gaussian SLAM的几何验证语义证据融合框架。
◆不同于统一加权融合2D语义先验，它显式评估在线语义观测的几何可靠性。
◆通过可见性一致性抑制遮挡区域的错误语义更新，减少全局地图中的持久伪影。
◆利用表面支撑的边界证据缓解语义边界外溢，并用射线级冲突不确定性延迟模糊区域的过早标注。
◆实验表明，该方法在Replica上提升语义一致性、边界保持和重建质量，在ScanNet真实RGB-D输入下仍保持有竞争力的跟踪性能。</td></tr>
<tr><td>2026-06-28</td><td>PL-LIT: A LiDAR-Inertial-Thermal SLAM Using Point-Line Features and Thermographic Mapping<br><a href='http://arxiv.org/pdf/2606.29259'>论文</a></td><td>◆ 提出PL-LIT通用LiDAR-惯性-热成像SLAM框架，可同时适配可见光与热红外相机，提升恶劣光照、雾等条件下的定位鲁棒性。
◆ 通过在线光度标定缓解热相机AGC和低对比度带来的亮度不一致问题。
◆ 引入深度网络提取点线特征，使热图像跟踪更稳定、可重复。
◆ 在ESIKF中构建紧耦合LiDAR-惯性-热成像状态估计，并设计可靠的线特征几何约束。
◆ 构建概率热强度体素地图，支持实时热异常检测与安全巡检。
◆ 实验证明其在可见光环境具备通用性，在长距离热红外数据集上达到先进性能。</td></tr>
<tr><td>2026-06-28</td><td>MoPe: Motion Permanence for Robust Monocular Gaussian Mapping in Dynamic Environments<br><a href='http://arxiv.org/pdf/2606.29237'>论文</a></td><td>该论文针对动态环境中单目Gaussian Splatting SLAM易把短暂停止或遮挡后重现的动态物体误融入地图、产生鬼影的问题，提出MoPe以提升建图稳定性与定位鲁棒性。
◆提出“运动永久性”原则，强调动态性应由历史运动状态决定，而非逐帧重新判断。
◆设计记忆感知不确定性滤波器，通过几何一致的SE(3)扭曲传播历史动态后验。
◆采用有界贝叶斯log-odds更新融合历史与当前观测，避免动态状态被短时静止外观覆盖。
◆将持久动态后验用于跟踪、建图、动态感知高斯插入和高斯级后处理清理。
实验在Wild-SLAM、Bonn和TUM上验证了MoPe能减少残留鬼影并提升跟踪鲁棒性，尤其适用于动态行人场景。</td></tr>
<tr><td>2026-06-27</td><td>How to Leverage Synthetic Speech for LLM-Based ASR Systems?<br><a href='http://arxiv.org/pdf/2606.29031'>论文</a></td><td>◆本文面向隐私受限的银行、医疗等场景，系统研究如何用合成语音训练基于LLM的ASR，并直面合成与真实语音的分布差距来源。

◆作者通过探测SLAM-ASR架构，定位出LLM骨干主要在早期到中层区分真实与合成语音。

◆研究发现，时间结构和韵律扰动最容易破坏这种判别信号，说明差距不仅来自音质自然度。

◆论文指出，表示层面的真实/合成可分性虽有参考价值，但不能直接预测最终ASR性能提升。

◆作者发现RIR卷积能通过模拟真实录音的声学不规则性缩小差距，并结合层选择模块，使系统仅用25%真实语音即可匹配全真实数据基线。</td></tr>
<tr><td>2026-06-27</td><td>J-LAW: Joint Localization and Actionable World Modeling via Coupled Latent Factor Graphs<br><a href='http://arxiv.org/pdf/2606.28712'>论文</a></td><td>◆ J-LAW将传统SLAM的度量定位建图与可用于规划的动作条件世界模型统一为同一个联合估计问题。
◆ 它提出耦合潜因子图，同时优化物体位姿、潜在世界状态和潜在地标嵌入。
◆ 关键创新是引入位姿条件潜编码器和位姿—潜变量耦合因子，使定位与世界模型相互校正、共同提升。
◆ 方法把观测、动作预测、里程计、潜在闭环和潜在地标观测等统一进单一MAP目标。
◆ 实验表明，J-LAW相比开环 rollout 显著降低潜预测误差和终点漂移，并提升全局轨迹一致性，生成兼具度量性和可行动性的地图。</td></tr>
<tr><td>2026-06-26</td><td>PinNet: Keypoint-Aware Learned Local Descriptors with Geometric Embedding for Loop Closure in LiDAR SLAM<br><a href='http://arxiv.org/pdf/2606.28637'>论文</a></td><td>◆PinNet面向仅依赖LiDAR几何信息的回环检测难题，学习生成适用于地点识别和scan-to-scan配准的局部几何描述子。
◆它将关键点检测与描述子提取整合在同一神经网络中，使特征更贴合点云中的稳定几何结构。
◆论文提出基于平面的几何自注意力模块，显式建模关键点之间的空间关系，从而增强描述子的判别性。
◆该方法不仅用于回环候选识别，还能支持精确相对位姿估计和单次定位，提升LiDAR SLAM的全局一致性。
◆在不同LiDAR传感器和多种环境数据集上的实验表明，PinNet具备较强的泛化性、地点识别能力和配准精度。</td></tr>
<tr><td>2026-06-26</td><td>LXD-SLAM: LiDAR+X Dense SLAM with $\sum_{i=0}^{5}C_5^i$ Configurable Sensor Combinations<br><a href='http://arxiv.org/pdf/2606.27811'>论文</a> | <a href='https://github.com/peterWon/LXD-SLAM'>代码</a></td><td>◆ LXD-SLAM提出以3D LiDAR为核心的高度模块化密集SLAM框架，可即插即用融合相机、IMU、轮速计和GNSS，支持最多32种传感器组合。
◆ 方法采用统一的迭代误差状态卡尔曼滤波，并通过自适应分层预测融合不同传感器观测，提升数学一致性与鲁棒性。
◆ 在更新阶段同时最小化点到网格距离和视觉重投影误差，实现几何与视觉信息的紧耦合优化。
◆ 论文用连续多层高斯过程子网格建模环境，支持高效射线到网格深度恢复，并生成高质量实时密集网格。
◆ 为保证全局一致性，提出基于GP子网格的ESC描述子和双向PnP优化，在混合位姿图中实现稳健多模态回环检测。
◆ 实验表明，LXD-SLAM在多种配置下达到或超过专用里程计方法，并能在真实场景中输出全局一致的高保真地图。</td></tr>
<tr><td>2026-06-26</td><td>RayPE: Ray-Space Positional Encoding for 3D-Aware Video Generation<br><a href='http://arxiv.org/pdf/2606.27345'>论文</a></td><td>◆ RayPE指出传统视频DiT仅在(u,v,t)网格上做RoPE，缺乏对场景三维几何关系的显式建模。
◆ 它将每个token对应的相机射线表示为6D Plücker坐标，并利用Plücker互易积与Transformer注意力点积同为双线性形式的联系。
◆ 方法把射线位置编码以加法方式注入Q/K，并设计query/key翻转结构，使对称恒等配置可精确对应互易积。
◆ 注入后注意力分解为内容项、几何项及两类内容-几何交叉项，实验表明这些部分都不可或缺。
◆ 为适配不同相机平移尺度，RayPE解耦射线方向与矩幅值，引入基于对数幅值的门控，并用RMSNorm稳定对齐内容分支。
◆ 该模块参数增加不到0.1%、可零初始化接入预训练视频DiT，并提升相机可控性、跨帧3D一致性和整体视频质量。</td></tr>
</tbody>
</table>
</div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-01</td><td>EPO: Boosting 3D Foundation Models with Edge-based Pose Optimization<br><a href='http://arxiv.org/pdf/2607.00579'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-01</td><td>Planar-SfM: Camera Pose Estimation via Homography Graph Embeddings<br><a href='http://arxiv.org/pdf/2606.31979'>论文</a></td><td>◆论文提出Planar-SfM，将传统SfM中被视为退化问题的平面场景转化为可利用的几何约束来源。

◆其核心思想是利用多视图中每个可见平面，通过单应性分解独立估计相对相机位姿。

◆方法构建基于单应性估计的位姿图，并引入谱嵌入来识别和剔除不可靠边。

◆该框架可将几何与视觉一致性映射到实线上，从而高效提取最大一致生成树用于位姿恢复。

◆实验表明，该方法在篮球场等高度平面场景中显著优于传统方法，同时在IMC Phototourism等通用三维场景中达到或超过现有最优水平。</td></tr>
<tr><td>2026-07-01</td><td>AnyMatch: Supercharging Universal Multi-Modal Image Matching with Large-Scale Single-View Images<br><a href='http://arxiv.org/pdf/2606.31077'>论文</a></td><td>◆ AnyMatch提出一种利用海量单视图图像生成多模态匹配训练数据的新框架，显著降低对昂贵真实几何标注数据的依赖。
◆ 它结合单目深度估计、3D重投影、扩散式修复和跨模态图像翻译，合成具有多视角、多模态特征的图像对。
◆ 其关键创新在于通过显式3D重投影生成严格满足几何一致性的标注，避免SfM-MVS流程中的误差累积。
◆ 该框架具备强可扩展性，可通过输入图像和相机参数控制场景多样性与匹配难度。
◆ 作者构建了大规模合成数据集Any-syn，并验证其能显著提升LoFTR、EDM、RoMa等模型在多模态匹配任务中的泛化性和鲁棒性。</td></tr>
<tr><td>2026-06-29</td><td>Emergence of a Shared Canonical Object Frame from In-the-Wild Videos<br><a href='http://arxiv.org/pdf/2606.30058'>论文</a> | <a href='https://github.com/Fischer-Tom/Emergent-Canonical-Frame/'>代码</a></td><td>◆ 论文提出一种从野外物体视频中自监督学习共享规范物体坐标系的方法，避免了传统方法对人工规范姿态标注的依赖。
◆ 核心创新是将所有训练序列通过共享几何瓶颈，即一个不含类别细节的粗略规范网格，从而促使不同实例对齐到共同框架。
◆ 方法学习图像像素到规范网格的稠密对应关系，并利用SfM得到的噪声相机几何估计每个视频序列的对齐变换。
◆ 共享规范框架并非显式监督得到，而是从多视角一致性和预训练特征提取器的语义先验中自然涌现。
◆ 在16万个野外物体视频上训练后，该方法在类别级姿态估计基准上达到与依赖规范姿态监督的方法相竞争的性能，显著提升了可扩展性。</td></tr>
<tr><td>2026-06-26</td><td>RayPE: Ray-Space Positional Encoding for 3D-Aware Video Generation<br><a href='http://arxiv.org/pdf/2606.27345'>论文</a></td><td>◆论文指出现有视频DiT的RoPE仅编码(u,v,t)采样网格，缺乏场景3D几何信息，并将相机射线的Plücker互易积与注意力点积建立联系。
◆提出RayPE，将每个token的6D Plücker射线坐标加性注入自注意力的Query和Key，实现射线空间位置编码。
◆设计Query/Key翻转结构，使对称恒等配置下的几何注意力精确对应Plücker互易积。
◆证明注意力分数可分解为内容项、几何项及两类交叉项，实验表明这些组成均不可或缺。
◆为适配不同尺度的相机平移数据，解耦方向与矩量幅值，并引入log幅值门控和RMSNorm稳定训练。
◆该模块参数增量低于0.1%、可零初始化接入预训练视频DiT，并提升相机可控性、跨帧3D一致性和视频质量。</td></tr>
<tr><td>2026-06-25</td><td>PanoImager: Geometry-Guided Novel View Synthesis and Reconstruction from Sparse Panoramic Views<br><a href='http://arxiv.org/pdf/2606.27071'>论文</a></td><td>◆ PanoImager针对稀疏全景图在旋转主导、弱视差场景下SfM/SLAM初始化不稳定的问题，提出了一个无需SfM的三维重建框架。
◆ 方法将全景图分解为局部透视视图，并利用前馈式位姿与深度先验提供初始几何约束。
◆ 通过几何条件扩散模型合成辅助新视角，补充稀疏输入中缺失的观测信息。
◆ 结合深度引导的3D Gaussian Splatting优化，提升跨视角一致性并稳定重建过程。
◆ 实验表明，该方法在极端稀疏全景输入下具有更好的鲁棒性，可作为SfM/SLAM失败时的离线地图细化组件。</td></tr>
<tr><td>2026-06-22</td><td>The EDGE-CALIFA Survey: Star Formation Efficiency and Galaxy Quenching across 62 Main Sequence, Green Valley, and Red Galaxies<br><a href='http://arxiv.org/pdf/2606.23649'>论文</a></td><td>◆ 本文发布GBT-EDGE CO(1-0)巡天，首次用绿岸望远镜系统绘制62个近邻CALIFA星系的分子气体分布，覆盖主序、绿谷和红序星系。

◆ 研究创新性地结合CO观测与CALIFA积分场光谱，统一估计分子气体质量、恒星形成率、金属丰度和恒星质量面密度。

◆ 论文量化发现主序、绿谷和红色星系的分子气体耗尽时间依次显著增加，表明星系越偏离主序，恒星形成效率越低。

◆ 通过测试多种CO-H2转换因子，作者证明SFE下降趋势具有稳健性，不依赖特定转换因子假设。

◆ 核心结论是，部分淬火星系并非缺乏分子气体，而是保留可观气体储备但形成恒星效率低，可能源于低气体密度和形态淬火共同作用。</td></tr>
<tr><td>2026-06-22</td><td>G-MASt3R-SfM: Graph-based View Pruning and Multi-stage Optimization for Robust SfM<br><a href='http://arxiv.org/pdf/2606.22856'>论文</a></td><td>◆ 提出G-MASt3R-SfM，一种面向鲁棒Structure from Motion的新流程，针对MASt3R在非重叠图像对上产生错误匹配的问题进行改进。
◆ 设计Graph-based View Pruning模块，利用匹配置信度构建场景图，并通过几何一致性剪除异常视图和不可靠连接。
◆ 提出Multi-Stage Optimization模块，从局部一致性逐步扩展到全局一致性，分阶段优化相机参数，降低外点对整体估计的影响。
◆ 相比直接使用MASt3R匹配结果的MASt3R-SfM，该方法能更有效抑制错误对应关系带来的噪声和位姿退化。
◆ 在ETH3D数据集上取得相机位姿估计和三维重建的先进精度，验证了其在复杂匹配条件下的鲁棒性和实用价值。</td></tr>
<tr><td>2026-06-20</td><td>ACEsplat: Accelerated 3D Gaussian Scene Regression via RGB and Poses Only<br><a href='http://arxiv.org/pdf/2606.22091'>论文</a></td><td>◆ACEsplat提出了一种仅依赖RGB图像和相机位姿的逐场景3D Gaussian Splatting重建框架，避免了SfM点云、深度图等外部几何先验。
◆其核心创新是用自监督场景坐标回归模块在4–5分钟内构建内部几何先验，提升现场部署的鲁棒性。
◆论文进一步设计轻量级高斯初始化头，将SCR特征与坐标先验融合，为后续3DGS优化提供更好的初始表示。
◆在Wayspots、Cambridge Landmarks和RealEstate10K等数据集上，方法在静态视角渲染和稀疏视角新视角合成中取得有竞争力的画质。
◆整个场景映射与3DGS重建可在单GPU上15–25分钟完成，适合机器人和混合现实中的快速场景搭建。</td></tr>
<tr><td>2026-06-15</td><td>MotionPyramid: Hierarchical Motion Representation and Residual Interfaces<br><a href='http://arxiv.org/pdf/2606.20705'>论文</a></td><td>◆提出MotionPyramid，将类感知层级的表示思想引入运动控制，从数据中学习从即时电机命令到长时程行为片段的多层动作表征。
◆方法以运动跟踪教师为起点，训练递归潜变量解码器，使高层潜变量可经低层展开为 temporally extended 的全身运动程序。
◆预训练后的层级被冻结，并作为下游强化学习策略的多种动作接口，支持不同控制分辨率的复用。
◆实验表明，粗粒度接口能加速早期学习并提升运动规律性，细粒度接口则保留反馈控制能力和最终任务精度。
◆论文还提出Residual Interfaces，使策略可同时使用粗层运动程序与细层残差修正，在结构化抽象和可控性之间取得平衡。</td></tr>
<tr><td>2026-06-16</td><td>Neural Tree Reconstruction for the Open Forest Observatory<br><a href='http://arxiv.org/pdf/2606.18153'>论文</a></td><td>◆本文面向开放森林观测站（OFO）的低成本无人机森林制图需求，指出现有基于传统运动恢复结构（SfM）的3D树木重建存在伪影多、细节不足和林下区域重建困难等问题。
◆论文的核心贡献是探索将神经辐射场（NeRF）等神经3D重建方法引入OFO数据流程，以提升森林三维地图质量。
◆其创新点在于利用NeRF对稀疏视角更鲁棒、可融入数据驱动先验的特点，改善传统航拍影像在复杂森林场景中的重建局限。
◆论文强调高质量3D树木重建对下游生态与气候应用的重要性，如野火模拟、碳汇监测和再造林规划。
◆此外，作者还提出未来将OFO平台扩展到支持更多先进3D视觉模型，为开放、可复用的森林制图工具链奠定基础。</td></tr>
<tr><td>2026-06-15</td><td>MVM-IOD: An Industrial Object-Centric Benchmark Dataset for the Evaluation of 3D Reconstruction Methods<br><a href='http://arxiv.org/pdf/2606.16638'>论文</a></td><td>本文针对工业3D重建缺乏真实场景数据集的问题，提出了机器视觉测量工业物体数据集MVM-IOD，核心创新点如下：
◆构建了首个面向典型工业物体的多视角基准数据集，包含9种物体与2种背景组合的18个场景，并提供高精度参考3D点云与相机位姿。
◆设计了系统化的数据采集方案，利用工业机械臂末端搭载相机沿半球轨迹精准拍摄，真实还原工业视觉检测设定。
◆全面评估了SfM、MVS、前馈模型及2D高斯溅射等现有先进方法，为工业场景的3D重建与位姿估计建立了基准。
◆揭示了此类工业图像会导致前馈方法出现分布外问题，验证了简单预处理可缓解该问题，为工业应用前馈方法提供了重要警示。</td></tr>
<tr><td>2026-06-13</td><td>PEARLS: NuSTAR and XMM-Newton Extragalactic Survey of the JWST North Ecliptic Pole Time Domain Field VI: Multiwavelength SED Analysis<br><a href='http://arxiv.org/pdf/2606.15365'>论文</a></td><td>本文对北黄极时间域场261个X射线源进行多波段SED分析，结合恒星形成主序与黑洞吸积率框架，揭示了星系与超大质量黑洞的演化联系。
◆发现相对于主序的恒星形成率与比AGN光度存在强相关性，具有最高比AGN光度的星系位于或高于主序。
◆揭示X射线光度与恒星形成率强相关，证认出符合短时标剧烈吸积事件的冷类星体群。
◆提出低质量星系呈现高于种群均值的快速生长期吸积，而高质量星系表现为维持模式吸积。
◆证明传统活动星系核分类无法揭示这些区别，凸显了X射线视角识别罕见且关键的AGN瞬时阶段的独特能力。</td></tr>
<tr><td>2026-06-12</td><td>A Lightweight Fiducial-Based Pipeline for 3D Hyperspectral Mapping of ex-vivo Lumpectomy Specimens<br><a href='http://arxiv.org/pdf/2606.14534'>论文</a></td><td>本文提出了一种全自动且无需标定的轻量级流程，通过消费级RGB图像和单次高光谱采集，生成离体乳房切除术标本的3D高光谱点云。
◆采用深度学习运动恢复结构骨干网络进行3D几何重建，并通过四个ArUco标记角点一致性的自定义光束法平差，在度量参考系中实现稳定。
◆提出无需恢复高光谱相机位姿的配准新方法，利用双模态可见的16个标记角点驱动平面单应性，并通过正交深度图查找恢复3D坐标。
在离体标本评估中，该流程的中位3D配准误差低于1毫米，2D重投影误差低于0.02毫米。
加速硬件下单标本处理时间不到4分钟，证明了将其应用于保乳手术术中切缘评估的可行性。</td></tr>
<tr><td>2026-06-12</td><td>MooMIns -- Monocular 3D Reconstruction and Object Pose Estimation from Multiple Instances<br><a href='http://arxiv.org/pdf/2606.14389'>论文</a></td><td>该论文针对单目图像同时进行3D重建与6D位姿估计的病态问题，提出MooMIns方法，利用工业料箱场景中单图隐含的同物体多视角信息实现联合重建与估计。
◆反转高斯溅射公式，将传统的多相机渲染单一场景转变为单相机渲染多个物体实例。
◆结合SAM3实例分割掩码与改进的运动恢复结构流程进行方法初始化。
◆采用基于图像证据的纯几何重建，有效避免了深度学习单目深度估计因训练数据先验产生的幻觉问题。
实验表明，该方法在合成与真实场景中均能准确重建未见物体并可靠估计各实例的6D位姿。</td></tr>
<tr><td>2026-06-16</td><td>Fast Speech Foundation Model Distillation Using Interleaved Stacking<br><a href='http://arxiv.org/pdf/2606.11766'>论文</a></td><td>本文探索了语音基础模型蒸馏的训练加速问题，旨在加快模型部署速度。
现有的堆叠方法虽然能通过逐渐增加模型深度来加速训练，但会导致模型性能下降。
◆提出了一种名为交错堆叠的新型方法，在堆叠过程中始终保持层位置不变。
◆该方法有效保留了语音基础模型每层编码的独特层特有知识，解决了传统堆叠导致的性能退化问题。
在SUPERB基准上的实验验证了该方法能在加速蒸馏训练的同时有效保持模型性能。</td></tr>
<tr><td>2026-06-09</td><td>Multi-Angular Reflectance Anisotropy Observed from UAV Multispectral Imagery<br><a href='http://arxiv.org/pdf/2606.10350'>论文</a></td><td>本文针对无人机多光谱影像因低空大视场产生的几何驱动辐射变异问题，提出了一种几何感知的多角度观测提取工作流程，从二向性反射分布函数视角量化观测几何效应。
◆提出基于运动恢复结构优化相机参数，并将正射影像均一区域重投影到多视点原始子图像的方法，实现同目标多视角下多波段反射率与几何参数的联合提取。
◆引入在观测天顶角与相对方位角域进行逐波段极坐标可视化的分析方法，直观揭示了几何效应对多角度反射率的影响规律。
◆通过草地目标实验发现十个波段均存在显著反射率各向异性，红边与近红外波段的反射率变异性高达119%至137%。
该研究证明了观测几何效应对辐射一致性具有不可忽视的影响，为无人机影像精准辐射校正提供了新依据。</td></tr>
<tr><td>2026-06-08</td><td>Minimal Solvers for Full-DoF Motion Estimation from Asynchronous Differential SfM<br><a href='http://arxiv.org/pdf/2606.09218'>论文</a></td><td>本文提出了一种基于异步光流直接进行全自由度自运动估计的新框架，旨在联合恢复角速度和线速度，以解决事件相机异步数据流对传统同步算法的挑战。
◆将微分对极约束解耦为独立的角速度和线速度分量，并推导了其面向异步数据的公式。
◆通过引入旋转动力学的一阶近似将约束方程转化为多项式形式，推导出首个代数最小五点求解器。
◆通过截断高阶角速度项，提出了一种加速求解器以满足高速场景的实时性需求。
实验表明该异步方法在精度和对时空噪声的鲁棒性上优于传统同步方法，为高速机器人的连续时间运动估计奠定了基础。</td></tr>
<tr><td>2026-06-04</td><td>S23DR 2026 Winning Solution<br><a href='http://arxiv.org/pdf/2606.06695'>论文</a></td><td>本文提出了S23DR 2026挑战赛的首胜方案，解决了从稀疏SfM、拟合深度和语义分割中进行结构化3D线框重建的问题。
◆将顶点视为条件集，利用基于Perceiver风格场景标记的条件流匹配DiT，对64个顶点标记进行去噪。
◆采用两阶段重建策略，首先通过全局通道预测粗略结构，接着利用裁剪外壳的第二通道进行细化。
◆引入小型多样本一致性步骤，有效保持了随机采样器的稳定行为。
该系统最终在私有排行榜上排名第一，取得了0.654的HSS成绩。</td></tr>
<tr><td>2026-06-02</td><td>Eliciting Complex Spatial Reasoning in MLLMs through Wide-Baseline Matching<br><a href='http://arxiv.org/pdf/2606.03577'>论文</a></td><td>本文针对多模态大语言模型在宽基线匹配中缺乏系统评估与训练框架的问题，深入探索并提升了其复杂空间推理能力。
◆构建了ReasonMatch-Bench基准，按视点位移和匹配粒度分层，揭示了当前模型在细粒度宽基线对应任务上远逊于人类的显著缺陷。
◆建立了可扩展的数据生成流水线，从大规模RGB-D视频和SfM重建等3D语料库中自动提取宽基线视图对，提供多样且可验证的监督信号。
◆提出了动态对应强化学习算法DCRL，结合图像级视点递进与点级对应课程，通过可验证奖励优化模型而无需显式思维链监督。
实验表明，DCRL显著提升了宽基线匹配及跨基准的空间推理性能，同时维持了良好的通用视觉理解能力。</td></tr>
</tbody>
</table>
</div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-01</td><td>AnyMatch: Supercharging Universal Multi-Modal Image Matching with Large-Scale Single-View Images<br><a href='http://arxiv.org/pdf/2606.31077'>论文</a></td><td>◆论文提出AnyMatch框架，用低成本、易获取的单视图图像生成多视角、多模态图像匹配训练数据，缓解真实大规模标注数据稀缺问题。
◆方法结合单目深度估计、显式3D重投影、扩散式修复和跨模态图像翻译，同时保证外观多样性与几何一致性。
◆其标注由3D重投影直接产生，避免了传统SfM-MVS流程中的误差累积，更适合训练精确匹配模型。
◆AnyMatch具备强可扩展性，可通过输入图像、相机参数和视角设置控制场景多样性与匹配难度。
◆基于该框架构建的Any-syn数据集显著提升LoFTR、EDM、RoMa等模型在多模态匹配基准上的泛化性和鲁棒性。</td></tr>
<tr><td>2026-06-29</td><td>MF-UAVPose6D: A Model-Free Monocular 6-DoF Pose Estimation Framework for Fixed-Wing UAVs<br><a href='http://arxiv.org/pdf/2606.29697'>论文</a></td><td>◆ 提出MF-UAVPose6D，一个面向固定翼无人机的无模型单目6-DoF位姿估计框架，推理时仅需RGB图像和相机内参，无需CAD模型或关键点先验。
◆ 通过热图引导的中心定位获得稳定目标锚点，提升非合作目标在复杂视角和远距离条件下的检测与定位可靠性。
◆ 设计Perspective-Aware Module建模观测射线先验，使网络更好理解单目成像中的透视几何关系。
◆ 引入Dynamic Topological Sampling，补充机翼、机身、尾翼等弱结构线索，增强对固定翼外形拓扑的利用。
◆ 采用平移与旋转解耦的位姿解码机制，并构建FW-UAV6DPose合成数据集；实验表明该方法在旋转估计、深度恢复和整体位姿评估上兼具精度、效率与鲁棒性。</td></tr>
<tr><td>2026-06-26</td><td>KM-Speaker: Keypoint-Based Style Control for High-Quality Speech-Driven 3D Facial Animation and Dialogue Localization<br><a href='http://arxiv.org/pdf/2606.28568'>论文</a></td><td>◆ KM-Speaker提出一种基于关键点条件的流式生成框架，用参考表演同时实现全局风格引导和逐帧级表情控制。
◆ 该方法面向高质量语音驱动3D面部动画，解决现有可控模型依赖低质量野外数据而损害真实感的问题。
◆ 论文设计了解耦策略，将音频驱动的唇部运动与关键点驱动的上半脸动态分离，提升唇同步与表情控制精度。
◆ 通过全局风格上下文保持机制，模型能在细粒度控制下维持完整面部表现的一致性和连贯性。
◆ 实验表明，KM-Speaker在数据受限场景下仍优于现有方法，尤其在唇同步、风格遵循和对话本地化的时序表情匹配方面表现突出。</td></tr>
<tr><td>2026-06-22</td><td>G-MASt3R-SfM: Graph-based View Pruning and Multi-stage Optimization for Robust SfM<br><a href='http://arxiv.org/pdf/2606.22856'>论文</a></td><td>◆论文提出G-MASt3R-SfM，针对MASt3R在非重叠图像对上产生错误匹配、进而影响SfM位姿估计的问题，构建了更鲁棒的SfM流程。
◆其核心创新之一是Graph-based View Pruning模块，利用匹配置信度构建场景图，并结合几何一致性剔除离群视图和不可靠连接。
◆第二个创新是Multi-Stage Optimization模块，通过从局部一致性到全局一致性的逐阶段优化，逐步细化相机参数。
◆该方法避免将错误匹配直接纳入全局优化，从源头上抑制噪声传播，提高了复杂场景下的位姿估计稳定性。
◆在ETH3D数据集上的实验表明，G-MASt3R-SfM在相机位姿估计和三维重建精度上达到当前最优水平。</td></tr>
<tr><td>2026-06-18</td><td>Evaluation of Image Matching for Art Skills Assessment<br><a href='http://arxiv.org/pdf/2606.20199'>论文</a></td><td>◆本文提出一种基于图像匹配的绘画技能评估方法，通过比较手绘作品与原始模板的相似度来量化绘画水平。

◆研究将计算机视觉用于替代传统人工评估，降低了评估过程的复杂性和主观性。

◆论文实现并对比了SIFT特征匹配与孪生网络两类图像相似度方法。

◆实验结果表明，利用图像相似度评估艺术技能是可行的，能够反映绘画与模板之间的差异。

◆关键发现是SIFT关键点匹配在该任务中表现更有效，更适合用于检测和衡量绘画技能。</td></tr>
<tr><td>2026-06-10</td><td>SalArt-VQA: Diagnosing Whether VLMs Understand Salient Artifacts in Generated Images<br><a href='http://arxiv.org/pdf/2606.12671'>论文</a></td><td>这篇论文针对视觉语言模型(VLMs)在AI生成图像伪影检测中的细粒度理解能力进行了诊断性研究。作者指出,尽管VLMs在图像级伪影检测上表现良好,但其判断可能依赖错误的视觉线索或区域,导致正确结论背后隐藏着推理失败。为此,论文构建了SalArt-VQA基准,包含950张图像和3681道人工标注的多项选择题,覆盖伪影图像、真实参考图像和配对生成参考图像,从存在性检测、语义定位、空间定位和证据支撑的缺陷识别四个维度系统评估模型。对20个VLMs的测试揭示,最强模型虽达到99.37%的检测召回率,但仅在53.26%的图像上同时答对四类问题,且模型存在敏感性与校准之间的权衡。

◆ 提出首个面向AI生成图像显著伪影细粒度理解的诊断性基准SalArt-VQA,填补了仅依赖图像级检测准确率所掩盖的评估盲区。
◆ 设计四类对齐问题(存在性检测、语义定位、空间定位、证据支撑的缺陷识别),系统检验VLMs的伪影判断是否建立在局部视觉证据之上。
◆ 引入伪影图像、真实参考图像和配对生成参考图像三类对照划分,可定量评估模型在无伪影场景下的校准能力与拒答行为。
◆ 揭示了VLMs普遍存在的敏感性-校准权衡现象:敏感模型易做出无依据的伪影声明,保守模型则通过漏检来规避误报。
◆ 实验证明高检测准确率并不等同于具备扎实的伪影理解能力,为后续模型改进指明方向。</td></tr>
<tr><td>2026-06-02</td><td>SAMatcher: Co-Visibility Modeling with Segment Anything for Robust Feature Matching<br><a href='http://arxiv.org/pdf/2606.03406'>论文</a></td><td>该论文提出SAMatcher框架，将图像匹配问题转化为共视性建模问题，通过预测跨视图共视区域作为结构化先验来指导匹配。
◆突破传统像素级匹配局限，首次利用共视区域掩码和边界框作为结构化先验进行对应点估计。
◆提出基于SAM的对称跨视图交互机制，实现双向特征交换与跨视图语义对齐。
◆设计统一监督方案，通过掩码学习、框回归及掩码-框一致性约束联合优化掩码预测与框定位。
实验表明该方法在大视角和尺度变化下优势显著，证明了单目分割基础模型可有效扩展至多视图推理，为图像匹配提供了新视角。</td></tr>
<tr><td>2026-05-30</td><td>BEVIO: Efficient Bird&#x27;s-Eye-View based Sparse-Update Visual-Inertial Odometry for Lunar Day-Night Navigation<br><a href='http://arxiv.org/pdf/2606.00709'>论文</a></td><td>本文针对月球漫游车计算资源受限及昼夜自带光源下特征关联困难的挑战，提出了基于鸟瞰图的稀疏更新视觉惯性里程计BEVIO。
◆提出基于鸟瞰图的图像匹配方案，有效增强了对更大帧间运动的鲁棒性。
◆在显著视觉外观变化下实现了更可靠的特征匹配，克服了夜间自带光源照明的干扰。
◆支持在极稀疏视觉更新率下进行可靠的里程计估计，大幅降低了对计算资源和功耗的依赖。
通过高保真月球仿真和半比例漫游车在真实环境中的长期昼夜部署实验，验证了该方法在低至0.25赫兹更新频率下仍能实现可靠的昼夜导航。</td></tr>
<tr><td>2026-07-01</td><td>SOCO: Benchmarking Semantic Object Correspondence in Vision Foundation Models<br><a href='http://arxiv.org/pdf/2605.31597'>论文</a></td><td>本文提出SOCO基准，旨在解决视觉基础模型中结构化对象理解评估协议不一致和部件级监督有限的问题。
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

<h2 id='obstacle-avoidance'>Obstacle Avoidance</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-01</td><td>Neuro-Symbolic Safety Guidance for Vision-Language-Action Models via Constrained Flow Matching<br><a href='http://arxiv.org/pdf/2607.01378'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-01</td><td>Distributed Containment of a Compromised Agent through Repulsive Cages<br><a href='http://arxiv.org/pdf/2607.01230'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-01</td><td>FastBridge: Closing the Model-Based Realization Gap in Safety Filters on 3D Gaussian Splatting for Fast Quadrotor Flight<br><a href='http://arxiv.org/pdf/2607.01200'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-01</td><td>Robots Ask the Way: Communication-Enabled Social Navigation<br><a href='http://arxiv.org/pdf/2607.01044'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-29</td><td>Multi-UAV Formation Cooperative Obstacle Avoidance and Adaptive Shape Deformation Control in Complex Environments Based on BI-APF-RRT and Affine Transformation<br><a href='http://arxiv.org/pdf/2606.29755'>论文</a></td><td>◆论文提出一种融合BI-APF-RRT与仿射变换的多无人机编队协同避障方法，兼顾复杂环境中的避障灵活性与编队完整性。
◆采用目标偏置的双向APF-RRT替代传统APF质心规划，提升全局路径搜索效率并降低陷入局部最优的风险。
◆通过改进人工势场与三次B样条插值，增强质心路径的平滑性、收敛速度和可飞行性。
◆引入包含非均匀缩放与旋转的仿射变换矩阵，使编队能根据障碍物距离自适应变形。
◆设计分布式跟踪控制律，使跟随者协同跟踪领航者，实现编队在不解散的情况下安全穿越复杂障碍区域。</td></tr>
<tr><td>2026-06-28</td><td>LAMP: Long-Horizon Adaptive Manipulation Planning for Multi-Robot Collaboration in Cluttered Space<br><a href='http://arxiv.org/pdf/2606.29358'>论文</a></td><td>◆论文提出LAMP框架，面向密集杂乱空间中的长时域多机器人协同操作，联合考虑接触构型、机器人运动、耦合动力学与避碰。

◆核心创新是将学习到的生成式操作模型嵌入规划过程，从而在完整的物体—机器人耦合空间中进行更可 tractable 的搜索。

◆提出LAMPA*规划器，系统化搜索长时域任务中的接触与运动决策，避免仅规划简化物体轨迹带来的局限。

◆提出LAMP-Lazy惰性规划器，通过延迟评估降低计算开销，支持实时重规划。

◆实验表明，该方法能解决以往强化学习或短视接触原语方法难以处理的高密度、长时域多机器人操作任务。</td></tr>
<tr><td>2026-06-27</td><td>When Stopping Fails: Rethinking Minimal Risk Conditions through Human-Interactive Autonomous Driving for Safe Transportation Systems<br><a href='http://arxiv.org/pdf/2606.29115'>论文</a></td><td>◆论文指出，自动驾驶现有“最小风险状态”过度依赖减速或停车，虽能降低碰撞风险，却可能引发交通阻塞、影响应急通行和造成无障碍问题。
◆作者基于公开案例分析AV停车行为失效与人车交互失败，并从感知、规划、控制三个层面建立事件分类框架。
◆论文创新性地将“理解人类权威与社会交通规则”纳入AV安全框架，强调不能只关注物理避障。
◆研究总结了人机交互感知、语言指令理解、无障碍规划、远程协助与遥操作等新方向。
◆核心贡献在于提出从被动停车式安全转向人类交互式自治，以支持AV在复杂城市道路中的可靠部署。</td></tr>
<tr><td>2026-06-27</td><td>LNN-Fly: Continuous-Time UAV Navigation for Robust Obstacle Avoidance under Timing Mismatch<br><a href='http://arxiv.org/pdf/2606.28827'>论文</a></td><td>◆本文提出LNN-Fly，一种面向真实部署的连续时间LiDAR无人机避障导航策略，重点解决仿真到现实中的时间不匹配、传感不规则和控制频率变化问题。
◆其核心创新是将动态规划启发的结构化循环更新、显式控制间隔Δt条件化，以及输入驱动的自适应遗忘门结合起来。
◆该遗忘门能在接近障碍时快速刷新陈旧隐状态，同时在持续机动中保持时序一致性。
◆训练阶段引入可微分 rollout，并模拟真实部署中的感知扰动和时序扰动，从而提升鲁棒性。
◆实验表明，LNN-Fly在低控制频率、稀疏观测和控制周期抖动下表现更稳，并能从简化仿真零样本迁移到真实四旋翼，室内跨频率测试20次飞行成功率达100%。</td></tr>
<tr><td>2026-06-27</td><td>Hierarchical Decision Making with Structured Policies: A Principled Design via Inverse Optimization<br><a href='http://arxiv.org/pdf/2606.28764'>论文</a></td><td>◆提出一种原则化的分层决策框架，将高层目标抽象与低层结构化优化策略系统结合，用于复杂控制任务分解。

◆针对现有RL难以严格满足约束、OC方法短视且计算昂贵的问题，构建了兼顾安全约束与决策效率的分层RL-OC架构。

◆核心创新是引入逆优化方法，从专家示范中学习低层优化问题的目标结构，使低层策略与长期任务目标保持一致，而非依赖启发式设计。

◆该方法提升了低层决策的可解释性和任务相关性，同时保留优化控制在约束处理方面的优势。

◆在网络资源分配和连续碰撞规避任务中，实验表明该框架在效率和决策质量上均优于端到端RL、学习增强OC和现有分层RL基线。</td></tr>
<tr><td>2026-06-27</td><td>Vision-Language Models for Deployable Social Robot Navigation: Bridging Semantic Reasoning and Low-Level Control<br><a href='http://arxiv.org/pdf/2606.28760'>论文</a></td><td>◆本文系统梳理了视觉语言模型在可部署社会机器人导航中的作用，强调其可弥补传统导航缺乏语义理解与社会常识推理的不足。
◆论文提出统一视角，将相关方法划分为高层VLM语义推理、低层规划控制，以及连接二者的中间机制。
◆核心创新在于构建了一条VLM与导航系统耦合的结构化路线图，涵盖语义评估、空间落地、中间表示和控制模块。
◆论文强调实际部署需要混合架构，把VLM的推理能力与实时、安全、可验证的控制系统结合。
◆此外，论文综述了SRN相关数据集与评测平台，并总结了可靠性、实时性、安全性和社会合规性等开放挑战。</td></tr>
<tr><td>2026-06-26</td><td>Bearing-based Circumnavigation with Collision Avoidance in Time-varying Graphs under Limited Target Information<br><a href='http://arxiv.org/pdf/2606.27719'>论文</a></td><td>◆论文研究了异构多智能体对静止目标的分布式环绕问题，并将智能体建模为具有半径的圆盘，更贴近真实物理约束。
◆在目标信息受限条件下，仅少数领导者可直接获取目标位置，跟随者只依赖交互图中指定出邻居的局部信息实现协同。
◆提出了一种仅控制角速度的基于方位的分布式制导律，适用于静态和时变最近邻交互拓扑。
◆通过引入对数型障碍李雅普诺夫函数，显式保证智能体间避碰，并证明无碰撞集合的前向不变性。
◆理论上证明在可行初始条件下，每个跟随者最终会围绕其有向路径末端领导者所对应的同一目标实现环绕运动，仿真验证了方法在不同拓扑下的有效性。</td></tr>
<tr><td>2026-06-25</td><td>Design and Performance Evaluation of Secure RF and WiFi-Based Communication in Drone Swarms via Testbed Implementation<br><a href='http://arxiv.org/pdf/2606.27028'>论文</a></td><td>◆ 论文在四架自研无人机集群上实现了RF与WiFi双链路安全通信测试床，将MAVShield及多种流加密方案集成到MAVLink遥测中进行真实飞行验证。
◆ 工作证明加密遥测数据可支持编队控制与避障等自主协同任务，而不仅限于静态通信测试。
◆ 提出改进人工势场避障算法，直接在大地坐标系计算引力和斥力，减少坐标转换、轨迹振荡和局部极小问题。
◆ 通过CPU、内存和PDR等指标系统比较MAVShield、AES-CTR、Speck-CTR、ChaCha20和Rabbit的开销与可靠性。
◆ 结果表明MAVShield性能接近明文通信，整体效率优于其他加密方案，同时经代数密码分析和Wireshark流量分析验证其抗密钥恢复与保密能力。</td></tr>
<tr><td>2026-06-25</td><td>G2DP: Diffusion Planning with Spatio-Temporal Grid Guidance<br><a href='http://arxiv.org/pdf/2606.26017'>论文</a></td><td>◆提出G2DP，一种网格引导的扩散式自动驾驶规划器，解决传统扩散规划随机性强、闭环执行中安全与路线约束不足的问题。
◆其核心创新是构建可微的时空代价体，将未来占用概率分布与路线进度图融合，形成密集环境约束。
◆方法把该代价体建模为连续安全能量函数，并在推理去噪过程中直接注入梯度，引导轨迹远离碰撞区域并保持路线进展。
◆相比依赖稀疏几何查询或后处理优化的方法，G2DP具备更强的场景感知能力，尤其适合复杂交互交通。
◆实验表明，G2DP在nuPlan闭环评测达到SOTA，并在interPlan和DeepScenario零样本迁移中保持优异鲁棒性。</td></tr>
<tr><td>2026-06-24</td><td>Explainable Control Framework (XCF) based on Fuzzy Model-Agnostic Explanation and LLM Agent-Supported Interface<br><a href='http://arxiv.org/pdf/2606.25941'>论文</a></td><td>论文提出面向复杂闭环控制器的可解释控制框架XCF，旨在让人类理解控制动作的产生原因和控制器工作机制。
◆XCF具有模型无关性，可解释黑箱或复杂控制器，并能结合系统响应动态进一步细化局部解释。
◆提出HFMAE-C方法，用模糊逻辑系统近似控制器行为与系统动力学，以IF-THEN规则揭示决策逻辑。
◆该方法提供样本、局部、域和全局多层级解释，并用显著性值量化各系统状态对控制动作的贡献。
◆构建LLM Agent支持的交互界面，可自动分析用户需求、选择算法、生成自然语言解释报告并支持咨询。
倒立摆和Turtlebot避障实验表明，该框架相比主流可解释控制方法具有更好的有效性与实用性。</td></tr>
<tr><td>2026-06-25</td><td>Large-Scale Tunnel Air-Ground Collaboration With FLISP: Fast LiDAR-IMU Synchronized Path Planner<br><a href='http://arxiv.org/pdf/2606.25393'>论文</a> | <a href='https://github.com/ArchibaldGuo/FLISP.git'>代码</a></td><td>◆ FLISP提出一种面向水电隧道巡检的无地图UGV-UAV协同路径规划框架，避免了传统建图、栅格化和采样规划带来的计算开销与不稳定性。
◆ 其核心创新是用车载单套LiDAR-IMU同时驱动地面车和无人机的同步路径生成，降低系统复杂度并减少状态估计漂移影响。
◆ 针对不同平台，FLISP为UGV设计增强萤火虫算法实现避障，为UAV设计动态迭代优化器生成可飞行轨迹。
◆ 论文还提出分层轨迹细化策略，在不依赖全局地图的情况下保证运动学可行性与协同一致性。
◆ 在1.2 km真实运行隧道中，FLISP实现100%成功率和约7 ms延迟，相比栅格法快7倍、相比采样法快约三个数量级，展示了在退化线性基础设施巡检中的可扩展性。</td></tr>
<tr><td>2026-06-23</td><td>Grounding Generative Policies in Physics: Optimization-Guided Diffusion for Robot Control<br><a href='http://arxiv.org/pdf/2606.24208'>论文</a></td><td>◆论文提出一种推理时优化引导的扩散框架，用于弥合生成式机器人策略与真实物理可执行性之间的“具身差距”。
◆其核心创新是将扩散反向采样中的随机扰动替换为优化得到的修正量，使生成结果在贴近学习先验的同时满足约束。
◆该方法无需重新训练扩散模型，即可在采样过程中加入可达性、避障、闭环可跟踪性等硬约束或软惩罚。
◆实验覆盖灵巧抓取和动态操作，并验证了方法在不同机器人具身形态上的迁移能力。
◆相比投影和梯度引导基线，该方法更好保持抓取质量，并显著提升控制器可执行性与任务成功率，最高提升20和23个百分点。</td></tr>
<tr><td>2026-06-22</td><td>Verifiable Foundation Models for Robot Safety<br><a href='http://arxiv.org/pdf/2606.23754'>论文</a></td><td>◆提出FEARL框架，将机器人策略拆分为大型Controller和小型Safety模块，兼顾基础模型的感知推理能力与安全可验证性。
◆Controller负责高维多模态感知和任务理解，Safety模块仅基于低维安全传感器信息及有界上下文嵌入输出最终动作。
◆该设计把碰撞避免、工作空间边界等安全约束的形式化验证范围缩小到Safety模块，使现有验证工具可实际应用。
◆论文证明这种模块化分解不会显著牺牲任务能力，并在三个仿真机器人任务中测试了多种控制器骨干和训练方式。
◆实验还包括现成视觉-语言-动作模型，并展示了从仿真到真实机器人的迁移，说明低维安全接口具有实践价值。</td></tr>
<tr><td>2026-06-22</td><td>LP-NavOA: Integrated Local Navigation and Obstacle Avoidance for Humanoid Robots under Limited Perception<br><a href='http://arxiv.org/pdf/2606.23249'>论文</a></td><td>◆ LP-NavOA面向短程、部分可观测感知下的人形机器人，实现了局部导航、避障与稳定全身运动的一体化框架。
◆ 其先训练射线感知条件下的PPO运动骨干，采用机器人中心的圆形航向-速度指令和共享安全过滤器，提升高速指令跟踪能力。
◆ 在冻结运动骨干后，利用A-star和航点教师数据蒸馏循环局部规划器，部署时仅改写航向指令，避免破坏全身控制策略。
◆ 系统运行只需本体感知、短程距离感知和机体坐标系目标方向，不依赖全局地图、连续航点流或外部规划器。
◆ 实验显示其能完成绕障和遮挡后目标恢复，将准时到达率从38–40%提升到85–97%，并减少擦碰式前进。
◆ 消融验证了动态路线塑形、教师主动数据采集和圆形指令接口的重要性，Unitree G1分析也表明其具备硬件可执行性。</td></tr>
<tr><td>2026-06-22</td><td>Scalable Online Flight Trajectory Optimization via Sequential Quadratic Programming for Urban Air Mobility in Ultra Low-Altitude Airspace<br><a href='http://arxiv.org/pdf/2606.23008'>论文</a></td><td>◆提出面向超低空城市空域UAM的在线轨迹优化框架，将城市几何约束、运行限制与飞行器全自由度动力学统一纳入SQP求解。

◆创新地不依赖预先生成的无障碍走廊，而是在每次迭代中实时重建分离超平面约束，实现障碍规避与动力学优化的联合在线求解。

◆引入可变尺度四叉树分解，在复杂城市级三维环境中控制计算规模，提升高密度、高速飞行场景下的实时性与可扩展性。

◆该方法能够随参考轨迹和环境变化动态更新约束，更适合真实UAM运行中的在线重规划需求。

◆在五个真实城市环境中与传统SQP、iLQR和DDP对比，CPU平台上实现100%成功率和安全净空率，验证了其鲁棒性与实用价值。</td></tr>
<tr><td>2026-06-22</td><td>Stable Transformer-Actor-Critic Model Predictive Control: A Contraction Analysis Approach<br><a href='http://arxiv.org/pdf/2606.20197'>论文</a></td><td>◆提出了一种Transformer-Actor-Critic MPC架构，用于处理复杂非凸控制任务，并同时关注闭环稳定性与鲁棒性保证。
◆首次证明Transformer网络可满足全局增量输入到状态稳定性δISS，为序列模型用于控制提供理论基础。
◆利用黎曼收缩理论分析物理系统与预测神经网络之间的互联系统动态，建立稳定性判据。
◆将理论推导得到的稳定性与鲁棒性界作为训练正则项，使学习策略具备可认证的鲁棒性。
◆在非线性3D无人机目标到达与避障任务中验证了方法的有效性，展示其在复杂动态场景中的应用潜力。</td></tr>
</tbody>
</table>
</div>

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-02</td><td>ACID: Action Consistency via Inverse Dynamics for Planning with World Models<br><a href='http://arxiv.org/pdf/2607.02403'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-02</td><td>SPLC: Social Preference Learning for Crowd Robot Navigation<br><a href='http://arxiv.org/pdf/2607.01925'>论文</a> | <a href='https://github.com/sklus949/SPLC'>代码</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-02</td><td>Lightweight Safe Reinforcement Learning for End-to-End UAV Navigation<br><a href='http://arxiv.org/pdf/2607.01794'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-02</td><td>SpaceEra++: A Unified Framework Towards 3D Spatial Reasoning in Video<br><a href='http://arxiv.org/pdf/2607.01784'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-01</td><td>Context-Triggered Robust MPC for Temporal Logic Specifications<br><a href='http://arxiv.org/pdf/2607.01515'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-01</td><td>BIFROST: Bridging Invariant Feature Representation for Observation-space Sim2Real Transfer<br><a href='http://arxiv.org/pdf/2607.01410'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-01</td><td>Path Planning in Physically Viable World Models<br><a href='http://arxiv.org/pdf/2607.00673'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-30</td><td>LeCropFollow: Latent Space Planning for Navigation in Unstructured Crop Fields<br><a href='http://arxiv.org/pdf/2606.31941'>论文</a> | <a href='https://felipe-tommaselli.github.io/lecropfollow'>代码</a></td><td>◆提出LeCropFollow框架，用学习到的潜在表示替代显式几何建模，面向不规则种植、断行等非结构化田间导航难题。
◆将自监督语义热图提取器与TD-MPC2模型式强化学习规划器结合，使机器人能直接在潜在流形中优化轨迹。
◆保留未压缩的语义热图信号，避免传统几何方法在降维为关键点或路径参考时丢失不确定性与语义上下文。
◆实现从简化仿真到真实玉米田的零样本迁移，无需额外微调。
◆田间实验表明，其在非结构化行间表现接近最优基线，并在种植缺口场景中显著降低语义失败率，相比关键点方法减少2.4倍。</td></tr>
<tr><td>2026-06-30</td><td>Scenario Generation for Testing of Autonomous Driving Systems Using Real-World Failure Records<br><a href='http://arxiv.org/pdf/2606.31131'>论文</a> | <a href='https://github.com/anjaliParashar/crash2scenario'>代码</a></td><td>◆ 论文提出利用真实世界ADS历史故障/事故记录生成仿真测试场景，将自然语言记录转化为可执行测试输入。
◆ 核心创新是构建模块化LLM场景生成流水线，提取类别与上下文信息，并适配具体系统的测试约束。
◆ 方法减少了人工设计场景模板的负担，同时突破传统仿真测试依赖固定场景表示的限制。
◆ 在NHTSA ADS事故记录和Metadrive仿真器上验证，生成了涵盖4类道路、3类非自车运动及施工区异常的多样场景。
◆ 实验表明，生成场景与测试条件一致，并在仅20个场景的有限预算下发现了自动驾驶导航系统的有意义失效。</td></tr>
<tr><td>2026-06-29</td><td>Vision-Language Procedural Reasoning for Context-Aware Reward Modeling of Robotic Endovascular Guidewire Navigation<br><a href='http://arxiv.org/pdf/2606.30698'>论文</a></td><td>◆ 论文提出VL-PR框架，将视觉-语言程序推理引入机器人血管内导丝自主导航，以提升复杂血管环境中的上下文感知能力。
◆ 其核心创新是不让多模态大模型直接输出底层控制，而是根据实时视觉观察推断导航阶段、解剖语境和任务进展。
◆ 基于这些高层程序理解，系统动态调整不同奖励项的权重，实现上下文自适应奖励建模。
◆ 该方法使单一策略能够在推进效率、安全性、稳定性等竞争目标之间灵活权衡，并处理复杂阶段切换。
◆ 物理机器人平台实验表明，相比静态奖励方法，该框架提高了任务可靠性和导航效率，具备扩展到多任务血管介入流程的潜力。</td></tr>
<tr><td>2026-06-29</td><td>MOAR Planner: Multi-Objective and Adaptive Risk-Aware Path Planning for Infrastructure Inspection with a UAV<br><a href='http://arxiv.org/pdf/2606.30575'>论文</a></td><td>◆提出MOAR路径规划器，面向基础设施巡检中无人机近障飞行需求，同时考虑安全、时间与能耗等多目标优化。
◆引入风险感知代价函数，将预计算代价地图与天气、通信、电池等动态风险因素结合。
◆提出“损伤成本”和“插入成本”概念，用于更细致地刻画路径风险和任务执行代价。
◆设计自适应速度规划框架，使无人机可根据风险变化实时调整轨迹与飞行速度。
◆通过仿真和真实飞行测试验证，结果表明该方法能实时生成覆盖多类指标表现范围约90%的可靠轨迹，提升关键巡检任务的自主性与鲁棒性。</td></tr>
<tr><td>2026-06-29</td><td>Pondering the Way: Spatial-perceiving World Action Model for Embodied Navigation<br><a href='http://arxiv.org/pdf/2606.29908'>论文</a></td><td>◆论文提出SWAM空间感知世界动作模型，将视觉导航从“候选轨迹验证”转为“任务目标驱动”的联合生成范式。

◆SWAM仅需起点和目标RGB图像，即可单次推理同时生成中间RGB-D观测序列与对应动作轨迹，提升目标一致性和规划效率。

◆模型在训练中利用深度伪标签学习空间先验，但推理阶段只依赖单目RGB输入，兼顾空间可行性与实际部署便利性。

◆论文设计视觉引导的动作细化模块，使动作预测与视觉变化更精细对齐，减少轨迹与生成画面不一致的问题。

◆还引入轨迹尺度正则化损失，增强不同导航距离下的预测稳定性，并在成功率、轨迹精度、推理效率和零样本泛化上优于现有两阶段方法。</td></tr>
<tr><td>2026-06-28</td><td>CORE Planner: Contextual-memory Oriented Reinforcement-learning in Unknown Environments for Robot Navigation<br><a href='http://arxiv.org/pdf/2606.29222'>论文</a> | <a href='https://github.com/BBD00/core_planner'>代码</a></td><td>◆ CORE Planner将传统规划的结构化表示与强化学习决策相结合，使机器人能在无先验地图的未知环境中高效导航到目标。

◆ 方法采用稀疏可见性图表示环境，相比稠密栅格地图降低计算开销，同时保留关键拓扑信息。

◆ 论文引入Transformer进行全局环境理解，并结合上下文记忆机制，缓解环境记忆不足和局部最优问题。

◆ 提出的可见性图稀疏化方法提升了大规模复杂场景中的计算效率和可扩展性。

◆ 该方法仅在图像仿真环境中训练即可实现零样本sim-to-real迁移，实验中路径长度较FAR Planner减少13%，较学习基线最高减少48%。</td></tr>
<tr><td>2026-06-28</td><td>Empowering a Single-Frequency GNSS Receiver to Achieve High-Precision Positioning with Relative Observations<br><a href='http://arxiv.org/pdf/2606.29192'>论文</a></td><td>◆提出一种紧耦合状态估计框架，使低成本单频GNSS接收机可结合轮速计、相机、LiDAR等相对运动传感器实现高精度定位。
◆设计滑动窗口因子图，将通用相对运动约束与由连续载波相位跟踪生成的全局“历元到锚点”约束统一融合。
◆引入虚拟锚点机制，在首次观测卫星时锁定其状态作为参考，从而摆脱物理基站依赖。
◆用单频多模态运动先验和鲁棒周跳恢复技术替代多频硬件冗余，保障廉价接收机的载波相位完整性。
◆大量真实实验表明，该方法可将单频GNSS定位精度从数米提升到分米级，为自主导航提供低成本可靠替代方案。</td></tr>
<tr><td>2026-06-27</td><td>Vision-Language Models for Deployable Social Robot Navigation: Bridging Semantic Reasoning and Low-Level Control<br><a href='http://arxiv.org/pdf/2606.28760'>论文</a></td><td>◆本文系统梳理了视觉语言模型在社会机器人导航中的作用，强调其可补足传统导航在语义理解、常识推理和自然语言交互方面的不足。
◆论文提出统一视角，将相关方法划分为高层VLM推理、低层规划控制，以及连接两者的中间机制三部分。
◆其核心创新在于给出一条面向部署的结构化路线图，涵盖语义推理、评估器、空间 grounding、中间表示和控制模块。
◆论文突出混合架构的重要性，指出VLM不能直接替代安全关键控制，而应与经典规划、避障和实时控制协同。
◆此外，文章综述了SRN相关数据集与评测平台，并总结了可靠性、实时性、安全性和社会规范适配等开放挑战。</td></tr>
<tr><td>2026-06-27</td><td>He3-Seeker: Robotic Information Planning for Lunar Helium-3 Distribution Mapping<br><a href='http://arxiv.org/pdf/2606.28746'>论文</a> | <a href='https://github.com/OpenSpace-Lab/He3-Seeker'>代码</a></td><td>◆论文首次形式化定义了月球氦-3主动探测与分布制图问题，针对传统遥感方法精度低、可靠性不足的缺陷提出新思路。
◆提出He3-Seeker框架，通过多点钻探、采样与原位分析实现更直接的氦-3分布获取。
◆引入机器人信息规划方法，指导机器人自主导航和主动感知，使采样路径更具信息增益。
◆设计了基于低分辨率轨道遥感数据生成高可信参考氦-3分布的方法，用于算法评估。
◆仿真实验证明He3-Seeker可快速、高保真地完成氦-3分布制图，并公开代码与仿真环境以促进复现。</td></tr>
<tr><td>2026-06-26</td><td>Regularized Reward-Punishment Reinforcement Learning<br><a href='http://arxiv.org/pdf/2606.28152'>论文</a></td><td>◆ 论文提出KL-Coupled Policy Regularization（KCPR），让奖励策略与惩罚策略互为动态学习的先验，实现策略层面的直接协同。
◆ 基于KCPR推导KL-Coupled Soft Optimality（KCSO），形成耦合软最优策略和KL正则化Bellman算子，使奖励与惩罚信息共同影响价值传播。
◆ 作者进一步实现深度算法klDMP，用于在复杂环境中训练兼顾任务收益与安全约束的智能体。
◆ 为提升稳定性，论文引入伴随先验软化机制，并研究分离回放缓冲区以平衡奖励和惩罚经验。
◆ 在网格世界和Gazebo机器人导航实验中，klDMP相比DQN、SQL和softDMP表现出更好的安全性与学习稳定性，同时保持有竞争力的任务性能。</td></tr>
<tr><td>2026-06-26</td><td>RS-Diffuser: Risk-Sensitive Diffusion Planning with Distributional Value Guidance<br><a href='http://arxiv.org/pdf/2606.27766'>论文</a></td><td>◆ 提出RS-Diffuser，将扩散式轨迹生成与风险敏感离线强化学习结合，面向安全关键场景处理罕见但灾难性的风险。

◆ 方法学习未来状态轨迹扩散模型，并通过独立逆动力学模型将规划轨迹解码为动作，提高规划与控制的模块化能力。

◆ 引入基于分位数回归的蒙特卡洛分布式价值评论器，用于估计候选轨迹的完整回报分布，而非仅关注期望回报。

◆ 在采样去噪过程中加入CVaR等尾部风险目标的梯度引导，使生成轨迹可按风险偏好进行调整。

◆ 单个训练好的模型仅需改变推理时风险参数，即可产生风险规避、风险中性或风险偏好行为。

◆ 在风险敏感D4RL和机器人导航任务中取得领先表现，同时提升平均回报、最坏情况鲁棒性并减少安全违规。</td></tr>
<tr><td>2026-06-25</td><td>Ordinal Neural Collapse as a Representation Prior for Visual Navigation<br><a href='http://arxiv.org/pdf/2606.26839'>论文</a></td><td>论文提出ORION，针对端到端视觉导航中编码器仅受动作损失间接监督、易学到动作无关表征的问题，引入更具结构性的表征先验。
◆ 将导航动作从Far Left到Far Right视为天然有序类别，显式利用动作间的序关系来组织视觉表征空间。
◆ 鼓励各类别表征沿单一判别轴顺序排列，同时压制类内离轴方差，减少模糊场景下的动作不一致。
◆ 将预训练编码器接入扩散式导航框架，并进行端到端微调，实现表征学习与策略生成的统一优化。
◆ 在仿真和真实环境中均取得更高成功率和目标推进效果，尤其在复杂多岔路口等视觉干扰强场景中优势明显。</td></tr>
<tr><td>2026-06-24</td><td>Learning Robot Visual Navigation in Crowds via Intention-Aware Scene Representations<br><a href='http://arxiv.org/pdf/2606.26047'>论文</a></td><td>◆论文提出iCrowdNav，一种面向拥挤人群的视觉导航方法，使机器人能从第一视角视觉观测中同时理解行人意图与环境结构约束。
◆不同于将行人简化为2D点的传统方法，该方法利用更丰富的人体姿态、运动和场景视觉线索构建意图感知场景表征。
◆其时空编码器用于提取场景占据信息，帮助机器人理解可通行空间和动态障碍分布。
◆提出Intent-Interact Former，通过注意力机制建模人体姿态与人际交互，从而推断行人的运动意图。
◆这些特征被融合为紧凑状态嵌入，用于深度强化学习策略训练，并在仿真和真实部署中均优于基线方法。</td></tr>
</tbody>
</table>
</div>

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-02</td><td>Path planning for unmanned naval surface vehicles<br><a href='http://arxiv.org/pdf/2607.01631'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-01</td><td>SE(2) Navigation Mesh<br><a href='http://arxiv.org/pdf/2607.01454'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-01</td><td>CommonRoad-Game: A Human-in-the-Loop Simulation Framework for Autonomous Driving<br><a href='http://arxiv.org/pdf/2607.01382'>论文</a> | <a href='https://github.com/Yunfei-Bi8/CommonRoad-Game'>代码</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-01</td><td>From Prediction Uncertainty to Conformalized Distance Fields for Safe Motion Planning<br><a href='http://arxiv.org/pdf/2607.00776'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-01</td><td>Path Planning in Physically Viable World Models<br><a href='http://arxiv.org/pdf/2607.00673'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-01</td><td>From Real-Time Planning to Reliable Execution:Scalable Coordination for Heterogeneous Multi-Robot Fleets in Industrial Environments<br><a href='http://arxiv.org/pdf/2607.00591'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-01</td><td>Search-Based Spatiotemporal and Multi-Robot Motion Planning on Graphs of Space-Time Convex Sets<br><a href='http://arxiv.org/pdf/2607.00444'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-01</td><td>NeHMO: Neural Hamilton-Jacobi Reachability Learning for Decentralized Safe Multi-Arm Motion Planning<br><a href='http://arxiv.org/pdf/2607.00326'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-30</td><td>ELMP: Efficient Learning for Motion Planning via Analytical Policy Gradients<br><a href='http://arxiv.org/pdf/2607.00215'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-30</td><td>Optimal any-angle path planning in static and dynamic environments<br><a href='http://arxiv.org/pdf/2607.00065'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-30</td><td>Solution space path planning for supporting en-route air traffic control<br><a href='http://arxiv.org/pdf/2607.00064'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-30</td><td>RRT-Rope: A deterministic shortening approach for fast near-optimal path planning in large-scale uncluttered 3D environments<br><a href='http://arxiv.org/pdf/2606.31948'>论文</a></td><td>◆本文提出RRT-Rope，面向大型、较少障碍的三维环境，实现快速近最优路径规划。
◆方法先用改进的RRT-connect快速生成可行路径，再进行高效后处理缩短。
◆其核心创新是确定性shortcutting策略，利用树枝中加入的中间节点更系统地拉直路径。
◆相比依赖随机收敛的Informed RRT*、RRT#等方法，RRT-Rope显著降低计算时间和路径代价。
◆实验显示该方法在多种仿真环境中均优于常见RRT变体和缩短技术，在代表性采场中最快可比次优算法快70%。</td></tr>
<tr><td>2026-06-30</td><td>Energy-Optimal Spatial Iterative Learning within a Virtual Tube<br><a href='http://arxiv.org/pdf/2606.31487'>论文</a></td><td>◆提出一种面向无人机的无模型在线空间迭代学习框架，在虚拟管道约束内逐次优化路径以降低能耗。
◆方法不依赖显式的无人机动力学模型或能耗模型，降低了建模误差和工程部署门槛。
◆相比传统基于模型的轨迹优化，该方法每次迭代计算复杂度仅为O(n)，适合实时或在线应用。
◆在测试案例中，其计算速度比IPOPT基准方法快约50至60倍，显著提升优化效率。
◆仿真和多平台真实飞行实验验证了该方法在节能效果、计算效率和实际适用性方面的有效性。</td></tr>
<tr><td>2026-06-30</td><td>Efficient Sim-to-Real Transfer of World-Action Models from Synthetic Priors<br><a href='http://arxiv.org/pdf/2606.31101'>论文</a></td><td>◆论文首次验证了世界-动作模型可仅依赖合成先验实现真实机器人操作的零样本迁移。

◆方法基于Cosmos Policy，将视频扩散模型适配为视觉-运动控制策略，用于生成和执行动作。

◆作者构建了带大规模域随机化的仿真环境，并利用AnyTask运动规划流水线自动生成示范数据。

◆在物体举升、开抽屉和抓取放置任务中，每个任务仅使用约800条合成示范，完全不依赖真实示范。

◆真实Franka机器人零样本部署平均成功率达到35%，表明该路线可显著降低真实数据采集成本。</td></tr>
<tr><td>2026-06-29</td><td>Motion Planning in Compressed Representation Spaces<br><a href='http://arxiv.org/pdf/2606.30940'>论文</a></td><td>◆论文提出了一种生成式运动规划框架，将深度学习的数据先验与基于搜索/优化的模型规划方法统一起来。

◆其核心是训练高压缩率自编码器，把轨迹表示为具有层级粗到细结构的离散潜空间token。

◆规划阶段不直接在原始轨迹空间搜索，而是在压缩后的token空间中搜索，从而显著降低维度并提升效率。

◆该方法支持在测试时优化任意目标函数，无需针对特定任务重新训练，兼具灵活性和泛化能力。

◆实验在nuPlan和Waymo Open Motion Dataset上验证了其在闭环运动规划与多智能体场景生成中的有效性，能生成真实且高质量的行为。</td></tr>
<tr><td>2026-06-29</td><td>TAPE: Tether-Aware Path Planning for Autonomous Exploration of Unknown 3D Cavities Using a Tangle-Compatible Tethered Aerial Robot<br><a href='http://arxiv.org/pdf/2606.30817'>论文</a></td><td>◆提出TAPE，首个面向未知三维洞穴自主探索的系绳感知路径规划方法，同时优化飞行距离与放绳长度。
◆采用两级层次架构，基于“缠绕主要受局部路径影响”的观察，将全局探索与局部系绳管理解耦。
◆全局层使用前沿点规划并求解TSP，以尽量缩短整体探索路径。
◆局部层通过可调决策函数在路径代价和系绳长度之间权衡，提升对最大系绳长度约束的满足能力。
◆仿真与实地测试表明，该方法仅比纯TSP路径平均多4.1%距离，却将系绳超限问题从47%案例降至0%。</td></tr>
<tr><td>2026-06-29</td><td>DSIP: A Dynamic Coordination Planner for Signal-Free Intersections using Diffusion-Model-Based Multi-Agent Motion Planning<br><a href='http://arxiv.org/pdf/2606.30694'>论文</a></td><td>◆论文提出DSIP，一种基于扩散模型的无信号交叉口多智能体运动规划框架，将路口控制从传统相位切换转向连续车辆轨迹协同优化。
◆DSIP利用生成式扩散过程同时规划多车轨迹，在理想通信与执行条件下评估该策略的理论性能上限。
◆该方法面向联网自动驾驶车辆，通过软件定义的轨迹级协调减少停车等待和启停行为，释放路口潜在通行能力。
◆作者在SUMO中针对多种四岔路口场景进行实验，验证了DSIP在不同交通密度下的适用性。
◆结果表明，DSIP相比固定配时信号和先进强化学习控制器显著降低平均延误、提高平均速度，尤其在中高流量下优势更明显。</td></tr>
<tr><td>2026-06-29</td><td>MOAR Planner: Multi-Objective and Adaptive Risk-Aware Path Planning for Infrastructure Inspection with a UAV<br><a href='http://arxiv.org/pdf/2606.30575'>论文</a></td><td>◆提出MOAR路径规划器，面向基础设施巡检中无人机近距离避障与动态风险并存的自主导航问题。
◆构建多目标风险感知框架，可在任务过程中实时权衡安全性、飞行时间与能耗。
◆设计融合预计算代价地图、损伤代价和插入代价的风险感知代价函数，以刻画天气、通信、电池等变化风险。
◆引入自适应速度规划机制，使轨迹不仅调整空间路径，也能根据风险和资源状态动态调整飞行速度。
◆通过离散化状态与动作空间进行图搜索，并在仿真和真实飞行测试中验证其可实时生成性能覆盖约90%主流算法指标范围的轨迹。</td></tr>
<tr><td>2026-06-29</td><td>ReactiveBFM: Reactive Closed-Loop Motion Planning Towards Universal Humanoid Whole-Body Control<br><a href='http://arxiv.org/pdf/2606.30362'>论文</a></td><td>◆提出ReactiveBFM，将生成式运动规划与行为基础模型控制先验整合为实时闭环规划-控制框架，使人形机器人不再局限于预定义参考动作。

◆通过“调度式前缀采样”课程训练，让规划器从带误差的物理状态中学习恢复策略，有效缓解级联开环方法的累积暴露偏差。

◆设计异步重规划机制，解决自回归规划低频与全身控制高频之间的严重延迟不匹配问题。

◆结合轨迹分块与时序集成，生成更连续稳定的空间参考，减少执行抖动，实现流畅的全身协调运动。

◆在Unitree G1上实现大规模文本条件闭环动作，并支持零样本移动目标触达；仿真扰动测试中成功率达93.1%，较开环基线提升28.6%。</td></tr>
<tr><td>2026-06-29</td><td>Multi-UAV Formation Cooperative Obstacle Avoidance and Adaptive Shape Deformation Control in Complex Environments Based on BI-APF-RRT and Affine Transformation<br><a href='http://arxiv.org/pdf/2606.29755'>论文</a></td><td>◆论文提出一种融合BI-APF-RRT与仿射变换的多无人机编队协同避障框架，兼顾复杂环境中的避障灵活性与编队完整性。
◆以目标偏置的双向APF-RRT替代传统APF质心规划，提升全局路径搜索能力并缓解局部最优问题。
◆通过改进人工势场和三次B样条插值，提高质心路径的平滑性、收敛速度和可飞行性。
◆利用包含非均匀缩放与旋转的仿射变换矩阵，使编队可根据障碍物距离自适应变形。
◆结合分布式跟踪控制律，使跟随者稳定跟踪领导者，实现编队不解散地安全穿越复杂障碍区域。</td></tr>
</tbody>
</table>
</div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-02</td><td>Bridging 3D Gaussians and Semantic Occupancy for Comprehensive Open-Vocabulary Scene Understanding from Unposed Images<br><a href='http://arxiv.org/pdf/2607.01633'>论文</a></td><td>◆ 中文摘要生成失败，请检查 API 配置后重新运行...[摘要不完整，待更新]</td></tr>
<tr><td>2026-06-30</td><td>Ground Plane-Aided Extrinsic Calibration of Inertial and RGB-D Sensors for Uncrewed Aerial Vehicles<br><a href='http://arxiv.org/pdf/2606.31019'>论文</a></td><td>◆本文提出了一种面向无人机IMU与RGB-D相机的无标靶外参标定方法，避免依赖棋盘格、专用设备和初始参数估计。
◆方法利用深度学习进行地面分割，从RGB-D深度图中提取地面点并估计其法向量。
◆核心创新是将地面法向量与加速度计测得的重力方向相结合，在鲁棒估计框架下求解传感器外参。
◆该方法特别适合无人机在自然环境中的快速部署与在线/离线标定需求。
◆实验表明，其性能优于MATLAB工具箱，并在无需棋盘格目标的情况下接近Kalibr的标定效果。</td></tr>
<tr><td>2026-06-28</td><td>HiReFF: High-Resolution Feedforward Human Reconstruction from Uncalibrated Sparse-View Video<br><a href='http://arxiv.org/pdf/2606.29333'>论文</a> | <a href='https://iridescentjiang.github.io/HiReFF'>代码</a></td><td>◆ HiReFF提出面向未标定稀疏视角视频的前馈式人体重建框架，可从四个相隔90°视角实现2K、360°动态人体视频重建。
◆ 它将任务分解为稀疏视频前景3D Gaussian重建和高效高分辨率合成，避免传统逐场景优化或依赖相机标定。
◆ 提出Scale-synchronized Camera Calibration，在多视角监督中同步尺度，缓解未标定输入带来的尺度歧义。
◆ 提出Gaussian-wise Foreground Masking，通过调制每个Gaussian参数获得更干净的前景重建并抑制背景干扰。
◆ 提出High-resolution Side-tuning，在主干保持0.5K计算量的同时实现低开销2K渲染，并显著优于现有方法。</td></tr>
<tr><td>2026-06-26</td><td>Robotic Arm-Based Spectral Sensing for Strawberry Positioning and Non-Destructive Sweetness Measurement<br><a href='http://arxiv.org/pdf/2606.28555'>论文</a></td><td>◆提出了一套基于机械臂的草莓光谱感知系统，实现草莓检测、定位、接近与无损甜度估计的闭环集成。
◆系统结合YOLOv11s实时检测、RGB-ToF标定和掩膜-深度对齐，提升了果实三维定位的几何一致性。
◆设计了定制化eye-in-hand手眼标定流程，将目标从相机坐标可靠转换到机器人基坐标，支撑稳定操作。
◆采用路点搜索与增量式闭环接近策略，使传感器能够自动到达适合甜度测量的工作距离。
◆实验达到88.10%的端到端成功率，检测成功率95.24%，目标被检测后的接近成功率为100%，验证了系统可行性。
◆论文还指出当前主要瓶颈在复杂深度和反射条件下的有效感测区域提取，并为未来引入学习型策略提供了可扩展基线。</td></tr>
<tr><td>2026-06-26</td><td>Co-Optimization of Analog Kolmogorov-Arnold Networks for Low-Power Function Approximation in Flexible Electronics<br><a href='http://arxiv.org/pdf/2606.27892'>论文</a></td><td>◆提出模拟Kolmogorov-Arnold网络（AKANs），面向柔性电子中的低功耗多变量函数近似，适用于可穿戴与IoT传感端计算。

◆通过硬件-软件协同优化，将电路级非理想误差纳入训练过程，使模型在实际模拟硬件偏差下仍保持较高精度。

◆设计了软件与硬件双层剪枝方法，在减少样条参数和电路资源的同时降低面积与功耗。

◆实验表明，剪枝不仅压缩硬件开销，还能通过正则化效应提升函数近似精度。

◆在多个基准任务上实现最高55%面积节省和50%功耗降低，平均节省近30%，证明AKANs具备通用性和实用价值。</td></tr>
<tr><td>2026-06-24</td><td>Calousel: Extrinsic Calibration of Non-overlapping Multi-camera Systems from Pure Rotation<br><a href='http://arxiv.org/pdf/2606.25646'>论文</a></td><td>◆论文提出Calousel，用纯旋转运动实现非重叠视场多相机外参标定，只需一块静态标定板，降低了传统大靶标或多靶标预先测量的部署成本。
◆其核心思想是让各相机在不同时间依次观测同一标定板，并通过共享几何参考把这些非同步观测统一起来。
◆方法引入潜在转台坐标系，并在SE(3)上构建三维误差的全局优化模型，以联合估计多相机外参。
◆相比常见运动标定方法，该方案缓解了漂移误差、尺度不确定性和运动退化等问题。
◆实验在受控相机架和真实车辆异构相机平台上验证，表明其在非理想旋转条件下仍具备较高精度和现场部署实用性。</td></tr>
<tr><td>2026-06-03</td><td>A Geometry-Informed Computer Vision Method for Detecting and Examining Overtaking Vehicles From A Bicycle<br><a href='http://arxiv.org/pdf/2606.23699'>论文</a></td><td>◆提出一种面向自行车后视视频的几何约束计算机视觉流水线，可自动检测机动车超车事件，无需多传感器或显式相机标定。
◆方法结合RT-DETR目标检测与ByteTrack跟踪，并用方位角变化、目标尺寸增长和空间位置确认三类透视几何规则过滤事件。
◆在315个真实城市超车事件上实现97.8%召回率且零误报，显著降低人工逐帧标注负担。
◆系统平均可在车辆通过前2.44秒识别超车意图，84.1%的事件早于1.5秒反应阈值，具备主动预警潜力。
◆论文还探索了免标定横向通过距离估计，误差约13–14厘米，可用于区分危险近距离超车并支撑大规模骑行安全研究。</td></tr>
<tr><td>2026-06-22</td><td>IOI: Decoupling Kinematics and Physics for Interactive World Models<br><a href='http://arxiv.org/pdf/2606.23296'>论文</a></td><td>◆ IOI提出一种混合式交互世界模型，将解析运动学先验与学习到的物理动态解耦结合，提升控制对齐和视觉物理合理性。
◆ 它由动作序列显式计算正向运动学轨迹，避免纯数据驱动方法常见的时空漂移。
◆ 论文将轨迹渲染为前、侧、顶三视角正交投影，无需外参标定，并通过多视角运动学聚合与注入模块引导视频生成。
◆ 这种设计让生成器专注建模随机物理交互，而确定性运动由运动学先验保证，形成解析仿真与世界模型的协同。
◆ 在RoboTwin和真实平台实验中，IOI实现了SOTA仿真效果、OOD零样本泛化，并可作为可靠策略评估器和合成数据来源。</td></tr>
<tr><td>2026-06-19</td><td>Online Learning of Robust Legged Odometry with Minimal Exteroceptive Supervision<br><a href='http://arxiv.org/pdf/2606.21669'>论文</a></td><td>◆提出一种即插即用的腿式里程计框架，无需显式外感-本体传感器标定，也不依赖平台特定运动学模型。

◆利用成熟外感运动估计管线作为连续弱监督信号，在线训练仅基于本体感知数据的速度神经网络。

◆将学习到的本体速度、可用外感速度与IMU通过Invariant EKF融合，提高状态估计稳定性与一致性。

◆当视觉/激光等外感在退化环境中失效时，系统可自动切换到学习的本体模型，实现鲁棒连续里程计。

◆在不同四足机器人上验证了方法的平台无关性和快速部署能力，展示其在复杂场景下的可靠运动估计效果。</td></tr>
<tr><td>2026-06-18</td><td>Geometry-Preserving in 3D Gaussian Splatting for LiDAR-Camera Extrinsic Calibration<br><a href='http://arxiv.org/pdf/2606.20103'>论文</a></td><td>◆ 论文针对无标靶LiDAR-相机外参标定中跨模态特征不足的问题，利用3D Gaussian Splatting构建可微的几何代理以支持外参优化。
◆ 作者指出现有3DGS方法过度追求图像渲染质量，容易使高斯空间结构偏离真实LiDAR几何，从而影响标定精度。
◆ 提出通过聚合多视角LiDAR观测生成稠密深度监督，增强高斯代理对真实度量几何的保持能力。
◆ 设计了阻断光度梯度更新高斯空间参数的机制，避免视觉重建目标破坏LiDAR几何结构。
◆ 在公开自动驾驶数据集上的实验表明，该方法在无标靶标定精度上稳定优于现有方法。</td></tr>
<tr><td>2026-06-12</td><td>LV-Calib: LiDAR-Camera Extrinsic Calibration with Boundary-Response Modeling<br><a href='http://arxiv.org/pdf/2606.15010'>论文</a></td><td>本文提出了LV-Calib标定框架，利用可打印平面标定板实现了激光雷达与相机的外参估计及激光雷达边界响应标定。
◆提出基于强度与几何约束的迭代精化方法，自动裁剪背景并估计目标平面，显式处理反射率不连续处因光束足迹和混合回波导致的过渡带展宽与失真问题，提取精确的雷达3D特征点。
◆设计了加权重投影一致的外参优化策略，将图像观测保留在重投影域，并利用精化置信度对雷达特征残差进行加权，提升外参标定精度。
◆利用估计的外参和提取的过渡带，通过计算边界重叠样本的俯仰-偏航-距离残差统计量，实现了激光雷达边界响应的标定。
实验验证了该方法具备亚像素级重投影精度与毫米级特征一致性，并有效提升了里程计性能。</td></tr>
<tr><td>2026-06-12</td><td>StereoGeo: an end-to-end stereo camera calibration method<br><a href='http://arxiv.org/pdf/2606.14619'>论文</a> | <a href='https://github.com/meddourimane/StereoGeo-dataset'>代码</a></td><td>本文提出了StereoGeo，一种基于端到端网络的立体相机标定方法。该方法能够同时估计左右相机的焦距与重力方向，以及它们之间的相对外参变换。
◆突破了现有方法依赖标定板或结构化环境的限制，无需多视角设置即可完成双目标定。
◆打破了传统方法仅局限于单目内参或外参估计的不足，实现了双目内外参的联合估计。
◆扩展了GeoCalib算法，将深度神经网络特征提取与可微优化器进行有效整合。
实验证明该方法在内参标定上极具竞争力，在外参估计上更超越了现有限于单目的方法。</td></tr>
<tr><td>2026-06-12</td><td>Fully Distributed Multi-View 3D Tracking in Real-Time<br><a href='http://arxiv.org/pdf/2606.13127'>论文</a></td><td>本文提出MV3DT,一个面向重叠视野多摄像头网络的全分布式实时三维多目标跟踪框架。该方法摒弃传统集中式融合架构,通过点对点协同实现身份传播与遮挡恢复,有效解决了集中式方法在大规模部署时的计算瓶颈问题。在WILDTRACK数据集上达到94.3%的IDF1和93.3%的MOTA,性能与最先进的集中式方法相当,同时在100个摄像头规模下仍能保持30 FPS的实时性能,摄像头间延迟低于10毫秒,通信开销仅为2.2%。此外,该方法无需场景特定训练,仅依赖摄像头标定即可零样本部署于新环境。

核心创新点如下:

◆ 首次提出完全分布式的多视角三维跟踪架构,通过点对点协调机制取代中心节点聚合,从根本上消除了集中式方法的计算瓶颈。

◆ 设计了轻量级模块化流水线,在每个摄像头节点本地执行单目三维感知、分布式多视图关联与协同融合,通过轻量消息传递实现跨节点协作。

◆ 实现卓越的可扩展性,在100摄像头规模下维持30 FPS实时性能,通信开销仅2.2%,显著优于集中式方案。

◆ 采用零样本运行模式,仅依赖摄像头标定信息,无需任何场景特定的训练或学习,可直接部署到新环境。

◆ 在WILDTRACK基准上取得与集中式SOTA方法相竞争的精度,验证了分布式架构在保持高精度的同时具备规模化部署的实用价值。</td></tr>
<tr><td>2026-06-11</td><td>RGB-S: Image-Aligned Tactile Saliency for Robust Dexterous Manipulation<br><a href='http://arxiv.org/pdf/2606.08765'>论文</a></td><td>本文提出RGB-S框架，旨在解决机器人灵巧操作中视觉遮挡下稀疏触觉与密集视觉难以对齐的问题。与隐式学习跨模态对应的方法不同，该框架通过将物理接触显式锚定在图像域中来提升空间推理能力。
◆利用机器人正运动学与相机校准，将触觉传感器位置直接投影到RGB图像平面，实现跨模态空间对齐。
◆渲染受力调制的高斯显著图，有效建模由运动学与校准误差带来的空间不确定性。
◆采用零初始化条件架构整合二维空间锚点，将物理接触先验注入视觉主干网络，同时保留预训练视觉表征。
在严重视觉遮挡的仿真与真实灵巧操作任务评估中，该方法展现出更强的抗遮挡鲁棒性，真实世界实验成功率较最强隐式基线提升了26.7个百分点。</td></tr>
<tr><td>2026-06-07</td><td>Language as a Sensor: Calibrated Spatial Belief Estimation in 3D Scenes from Natural Language<br><a href='http://arxiv.org/pdf/2606.08666'>论文</a></td><td>该论文提出将自然语言作为一种新型传感器，以解决机器人视场外3D空间推理与多传感器融合的难题。
◆提出语言传感器模型LSM，将语言描述及场景图上下文映射为多模态空间分布，通过混合权重编码指代歧义，分量协方差编码空间不确定性。
◆提出概率建图框架VL-Map，将语言预测视为随机观测，并与机载感知在统一的置信度地图中进行深度融合。
实验证明，LSM是唯一能够保持协方差估计处于校准状态的语言预测器。
将LSM融合进VL-Map后，系统对目标物体位置的预测更加准确，真值目标上的概率质量比最强基线高出约70%。</td></tr>
<tr><td>2026-06-06</td><td>Empowering Feed-Forward Reconstruction Models with Metric Scale via Satellite Images<br><a href='http://arxiv.org/pdf/2606.08205'>论文</a></td><td>该论文提出一种卫星引导框架，利用易获取的卫星图像作为全局度量参考，解决前馈3D重建模型中存在的尺度模糊问题。
◆创新性地引入卫星图像作为度量参考，无需昂贵的度量标注或高精度相机标定即可消除尺度模糊。
◆设计了双向跨视角交互机制，将局部卫星图像块与前馈重建主干网络深度融合，强制重建场景与卫星参考间的一致性。
◆实现在度量坐标系下同时推断绝对尺度、优化场景几何并估计相机姿态的能力。
实验表明，该方法在多数据集的深度估计、点云重建和定位任务上均取得显著提升，且保持了优异的跨域泛化性。</td></tr>
<tr><td>2026-06-06</td><td>SynthICL: Scalable In-context Imitation Learning with Synthetic Data<br><a href='http://arxiv.org/pdf/2606.08154'>论文</a></td><td>本文提出了SynthICL框架，解决了上下文模仿学习在泛化性和可扩展性上的挑战，实现了仅基于纯RGB合成数据训练策略。
◆构建高质量合成数据生成流水线并训练流匹配Transformer策略，摆脱了对深度传感、精确相机标定和真实训练数据的依赖，提供更简单可扩展的方案。
◆引入子目标预测机制，通过训练模型预测下一子目标图像，实现更精确且具有视觉基础的机器人控制。
◆在测试阶段仅需单次演示即可让机器人适应新任务，无需重新训练模型。
该方法在16项未见真实操作任务中取得79%的平均成功率，显著超越了现有方法。</td></tr>
<tr><td>2026-06-03</td><td>Multi-Camera AR Guidance System for Surgical Instrument Handling and Assembly: Investigating Workload and Efficiency<br><a href='http://arxiv.org/pdf/2606.04992'>论文</a></td><td>本文提出了一种用于手术器械处理与装配的多摄像头增强现实引导系统，旨在降低洗手护士的认知需求并提升操作效率。模拟手术的用户研究表明，该系统显著降低了护士的感知工作负荷，将任务完成时间缩短了21.3%，尤其使不熟悉器械的护士获益。
◆提出了无需额外标记的多摄像头6D位姿估计与头戴式显示器原位可视化相结合的手术引导方案。
◆采用纯合成数据训练6D位姿估计网络，利用已知物体实现连续相机校准，提升了算法的泛化能力与真实世界适用性。
◆设计了原位工具提示定位与逐步装配动画，并创新性结合凝视选择与脚踏板实现步进切换，满足术中无菌交互需求。</td></tr>
<tr><td>2026-06-03</td><td>FUSE-Flow: A Decoupled Framework for Calibration and Stateless Real-Time Multi-View Point Cloud Fusion<br><a href='http://arxiv.org/pdf/2606.04376'>论文</a></td><td>本文提出FUSE-Flow，一个将标定与实时多视角点云融合解耦的框架，解决了传统方法中二者紧密耦合导致的波动重建结果、累积误差和扩展性差的问题。核心贡献在于通过GMAC和FUSE两个协同模块，实现了无需标定板、密集图像或全局光束法平差的稀疏视角精确标定，以及线性时间内存消耗的无状态融合。框架中GMAC利用几何约束与多视图重建Transformer优化外参，FUSE则通过置信度加权和自适应空间哈希完成融合，且二者相互增强——精确位姿提升融合精度，置信感知融合修正标定偏差。在公共数据集和真实相机系统上的实验验证，FUSE-Flow在视觉效果、动态稳定性和可扩展性上均优于主流实时重建方法，为大规模实时三维重建提供了实用方案。
◆ 解耦设计：将标定与点云融合拆分为独立模块，避免冲突的优化目标，实现针对性改进。
◆ 几何对齐多视图标定（GMAC）：基于几何约束和Transformer实现稀疏视角标定，无需标定靶标、密集图像或全局BA。
◆ 置信引导无状态融合（FUSE）：结合置信度权重与自适应空间哈希，确保线性时间与内存开销，且支持实时运行。
◆ 双向增强机制：精确位姿提升融合准确性，同时置信度感知融合反向校正标定偏差，形成自优化闭环。</td></tr>
<tr><td>2026-06-06</td><td>Dexterity-BEV: Aligning 3D World and Actions for Generalizable Robot Policies Learning<br><a href='http://arxiv.org/pdf/2606.02274'>论文</a> | <a href='https://hnuzhy.github.io/projects/Dex-BEV'>代码</a></td><td>本文针对端到端操作策略依赖2D输入且缺乏跨机器人和相机的3D空间对齐的局限性，提出了Dexterity-BEV方法。
◆提出对齐顶点图与顶点频谱，利用相机标定和可选深度将2D视觉提升为像素级3D表示，融合了3D感知与2D大模型的泛化优势。
◆提出将操作策略的输入输出对齐至共享坐标系，并创新性地构建鸟瞰图图像，生成对相机位姿变化鲁棒的视角不变表示。
◆开发了全面的数据处理管线以实现大规模对齐，并引入了针对跨多种机器人、人类操作员和数据集轨迹的全新时间对齐方案。
这些贡献共同缓解了输入输出的时空不对齐问题，显著提升了真实世界机器人操作的连贯性与泛化能力。</td></tr>
</tbody>
</table>
</div>

<h2 id='sensor-undistortion'>Sensor Undistortion</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-30</td><td>Distortion-Corrected Diffusion MRI Using Rotated-View EPI and Joint Field-Map/Image Estimation with Gaussian Primitives<br><a href='http://arxiv.org/pdf/2606.31521'>论文</a></td><td>本文提出一种面向扩散EPI的畸变校正框架，直接从k空间联合估计B0场和无畸变图像，避免传统“先重建、再校正”对中间图像质量的依赖。  
◆ 将图像与B0场表示为高斯基元叠加，并嵌入MRI物理前向模型，实现连续、显式且能兼顾平滑区域和组织边界的参数化。  
◆ 连续模型天然支持旋转视角EPI，无需插值，利用多相位编码方向分散畸变，使点扩散函数更各向同性。  
◆ 将扩散加权图像建模为实值非负，并把相位吸收到每次激发的相位因子中，增强低SNR和高b值条件下的稳健性。  
◆ 在体脑扩散实验中，该方法相比顺序校正方法更接近无畸变结构参考，尤其在高加速和高b值下提升最大，并表现出更好的细节保真和降噪效果。</td></tr>
<tr><td>2026-07-01</td><td>A First Exploration of Neuromorphic OT-CFM for Multi-Speaker VSR<br><a href='http://arxiv.org/pdf/2606.31225'>论文</a></td><td>◆论文提出LipsFlow，将RGB视频转为高时间分辨率事件流，利用神经形态视觉捕捉微秒级唇部动态，提升多说话人VSR在运动模糊、遮挡和细微发音下的鲁棒性。
◆系统结合ByteTrack与TalkNet，对多说话人场景进行跟踪和主动说话人检测，切分为单说话人片段以实现更聚焦的识别。
◆引入OT-CFM在语义潜空间中建模事件特征，通过确定性直线轨迹生成，将推理压缩到仅两步ODE，显著降低延迟。
◆设计双层语义监督，将token级BERT权重绑定与句子级先验结合，缓解同唇形词歧义问题。
◆实验表明该方法在240 ms延迟下达到22.3% WER，建立了高效且鲁棒的事件驱动多说话人VSR新范式。</td></tr>
<tr><td>2026-06-29</td><td>Your Data Manifold is Secretly a Reward Model: Shell-LCC for Text-to-Video Generation<br><a href='http://arxiv.org/pdf/2606.30248'>论文</a></td><td>◆论文提出“数据流形本身就是奖励模型”的观点，通过显式建模高质量SFT数据的流形结构，为T2V扩散模型提供密集、可微且低成本的奖励信号。
◆方法基于Local Coordinate Coding捕捉数据流形的“骨架”，引导视频潜变量靠近高质量数据分布，从而提升生成真实感。
◆针对传统LCC容易产生均值回归、导致细节丢失的问题，论文提出Shell-LCC，将流形表面建模为各向同性“壳层”，更贴近真实高密度区域。
◆该方法无需额外奖励模型、大规模人工标注或昂贵DPO训练，即可改善视频质量，尤其缓解低层次失真问题。
◆实验表明，Shell-LCC能增强高频细节、减少过平滑伪影，并有效减轻运动模糊，提升文本到视频生成的整体视觉质量。</td></tr>
<tr><td>2026-06-28</td><td>Again-Pose: Anchor-Guided Adaptive Inter-Frame Motion Cues Propagating for High-quality Human Pose Reconstruction<br><a href='http://arxiv.org/pdf/2606.29230'>论文</a></td><td>◆Again-Pose面向严重运动模糊、遮挡等退化视频中的连续3D人体姿态重建，指出现有隐式时序注意力在特征崩塌时难以区分有效信号与噪声。
◆论文将退化帧姿态估计重新定义为“运动引导的恢复”任务，而不是简单进行跨帧特征平滑。
◆方法通过特征显著性显式筛选高质量Anchor Frames，并利用其可靠运动与运动学线索修复中间退化帧姿态。
◆提出Dual-path Motion-aware Module捕获细粒度帧间动态，同时用Difference-weighted Fusion Module自适应传播线索并抑制漂移。
◆在Human3.6M、3DPW、PoseTrack和FineDiving等数据集上，Again-Pose在鲁棒性、稳定性和极端场景下的重建质量上显著优于现有方法。</td></tr>
<tr><td>2026-06-25</td><td>Confidence-Aware Tool Orchestration for Robust Video Understanding<br><a href='http://arxiv.org/pdf/2606.26904'>论文</a></td><td>◆论文指出视频推理模型的“盲目信任问题”：默认所有帧同等可靠，导致模糊、眩光、遮挡等扰动下准确率显著下降且无法自知。

◆提出Robust-TO框架，将逐帧可信度显式融入视频理解的证据选择、工具调用和最终推理全过程。

◆设计统一证据接口，协调检测、OCR、动作识别等异构视觉工具，使其输出预测结果、时间定位和校准可靠性分数。

◆引入可靠性-相关性评分选择可信帧，并用高/中/低三层证据综合机制按置信度加权推理。

◆提出置信度-成本GRPO奖励，同时优化答案正确性、证据可靠性和计算效率，在干净与受扰动视频上均取得领先表现。</td></tr>
<tr><td>2026-06-30</td><td>Event-based Gaze Control System for Accurate Real-time Spin Estimation in Professional Ball Games<br><a href='http://arxiv.org/pdf/2606.26780'>论文</a></td><td>◆提出一套事件相机主动视觉系统，结合高速振镜与可调焦长焦镜头，在高速球类运动中持续放大、对焦并跟踪未改装球体。
◆设计混合跟踪策略，将事件驱动的2D检测用于实时居中，并利用3D定位结果进行重初始化，提高比赛场景鲁棒性。
◆提出球面事件对比度最大化方法s-CMax，实现跨乒乓球、棒球、网球和高尔夫的高精度离线旋转估计。
◆面向实时乒乓球应用，构建由伪真值训练的不确定性感知CNN，并结合GPU批量对比度最大化进行快速精修。
◆系统在职业乒乓球三视角实验中达到3毫秒延迟、750Hz吞吐率，并取得8.8%转速幅值误差和6.4度旋转轴误差。</td></tr>
<tr><td>2026-06-25</td><td>Lattice Reconstruction and Orbital Hybridization Suppress Magnetism in TaCo$_2$Te$_2$<br><a href='http://arxiv.org/pdf/2606.26644'>论文</a></td><td>◆ 本文结合STM/STS、nc-AFM、ARPES和DFT，系统揭示了TaCo2Te2中晶格重构、电子结构与磁不稳定性的耦合关系。
◆ nc-AFM解析出畸变六角Te表面晶格，而STM/STS显示类方形电子对称性，说明电子态并不简单跟随原子结构。
◆ ARPES观测到强各向异性费米面和重构低能态，证明晶格重构显著改造其低能电子结构。
◆ 空间分辨谱学和轨道投影DFT表明，STM偏压衬度来自能量积分局域态密度中不同能量态的相反空间衬度，而非简单占据态/未占据态反转。
◆ DFT进一步发现，重构通过增强轨道杂化抑制未畸变结构中的磁不稳定性，稳定非磁基态，使TaCo2Te2成为结构调控磁性与关联相的模型体系。</td></tr>
<tr><td>2026-06-25</td><td>Temporally Consistent Label Interpolation for Robust Surgical Multi-Task Learning under Challenging Conditions<br><a href='http://arxiv.org/pdf/2606.26634'>论文</a></td><td>◆本文针对手术多任务学习中时间任务密集标注与空间任务稀疏标注不匹配的问题，提出了FAROS标签插值框架。

◆FAROS结合零样本分割掩码传播与光流估计，在遮挡、烟雾、运动模糊等复杂手术条件下生成时间一致的密集伪标签。

◆方法将插值后的器械掩码和动作标签融入统一的Transformer多任务模型，同时学习阶段、步骤、预测、器械分割和动作识别。

◆作者先在DAVIS 2017上验证了稀疏标注条件下的传播质量，证明其具备跨领域鲁棒性。

◆在GraSP、MISAW和AutoLaparo上的实验表明，FAROS显著提升了跨任务表征学习与整体手术场景理解性能。</td></tr>
<tr><td>2026-06-24</td><td>Edges Before Embeddings: A Confidence-Aware Blur Gate for Vision-Language Pipelines<br><a href='http://arxiv.org/pdf/2606.25838'>论文</a></td><td>◆ 提出MagikaDocumentFromPixel，一个轻量级CPU图像质量门控，可在约7ms内将输入判为清晰、模糊或不确定，避免下游OCR、检索和VLM在劣质图像上浪费计算。
◆ 通过46种配置、8轮实验搜索，发现输入分辨率是性能主导因素，模型容量只有在384px及以上时才明显收益。
◆ 引入基于选择性预测的置信度感知路由机制，使系统能对不确定样本进行保守处理。
◆ 设计Edge Prior Module，将拉普拉斯幅值作为辅助通道注入网络，直接利用模糊检测所需的边缘频谱证据，F1提升约1.3点。
◆ 最终方案以MobileNetV3-Large、384×384训练和5尺度测试增强达到F1=0.9803、AUC=0.9989，同时作者也明确指出数据分布、单随机种子和校准评估的局限。</td></tr>
<tr><td>2026-07-02</td><td>Shift Variant Image Degradation and Restoration Using Singular Value Decomposition<br><a href='http://arxiv.org/pdf/2606.25818'>论文</a></td><td>◆论文提出了一种基于奇异值分解的移变运动模糊图像复原框架，针对传统单一卷积核难以描述的空间变化退化问题。

◆其核心创新是用位置相关PSF构建移变成像算子，将退化过程统一建模为线性系统并进行SVD分析。

◆论文引入奇异值能量保留准则，系统选择小奇异值数量，以在抑制噪声放大和保留图像细节之间取得平衡。

◆方法覆盖双向线性运动、高斯运动和简谐运动三类一维移变PSF，验证了模型的适用性。

◆实验表明，该SVD稳定反演策略能够有效恢复图像细节、减轻模糊伪影，并揭示移变复原问题的病态特征。</td></tr>
<tr><td>2026-06-24</td><td>1000 Rallies: An Event-Camera Dataset and Real-Time Learned Ball-State Estimation for Robotic Table Tennis<br><a href='http://arxiv.org/pdf/2606.25620'>论文</a></td><td>◆ 提出首个面向乒乓球真实对打场景的大规模事件相机数据集“1000 Rallies”，涵盖1000多回合、不同水平运动员的击球数据。  
◆ 数据集同步采集事件流与14台200 FPS高速相机，并生成1 kHz的球位置、速度和旋转伪真值标签。  
◆ 基于该数据训练了卷积神经网络，可在复杂球员背景运动下从事件数据中联合估计球的图像平面位置与速度。  
◆ 将网络预测的速度作为卡尔曼滤波额外观测后，相比仅用位置的基线，落点预测误差降低36%。  
◆ 系统最终接入Stäubli机械臂，首次实现了由事件视觉驱动的实时人机乒乓球连续对打。</td></tr>
<tr><td>2026-06-24</td><td>EchoStyle: Unlocking High-Fidelity Video Stylization with Reverse Data Synthesis<br><a href='http://arxiv.org/pdf/2606.25465'>论文</a></td><td>◆ EchoStyle提出一个可扩展的文本驱动视频风格化框架，面向任意长度视频实现高保真、稳定的艺术风格迁移。
◆ 它设计了视频到视频架构，更合理地融合原视频内容与文本风格，缓解参考图方法常见的内容泄漏和运动失真。
◆ 论文首创自动化反向数据合成流程，构建了包含2万对高质量视频的V-Style20k数据集，显著缓解训练数据稀缺问题。
◆ 为处理长视频，提出init-follow-mode机制与滑动窗口推理策略，降低风格漂移并提升时序一致性。
◆ 实验证明EchoStyle可适配多种艺术风格，效果接近领先闭源方案，展示了较强的实用性和扩展性。</td></tr>
<tr><td>2026-06-21</td><td>A Theory-grounded Hybrid Neural Network Integrating Complementary Estimation Mechanisms for Stable Visual Object TrackingA<br><a href='http://arxiv.org/pdf/2606.22604'>论文</a></td><td>◆论文提出一种有理论支撑的ANN-CANN混合框架，将人工神经网络与连续吸引子神经网络在同一连续状态空间中对齐。
◆该框架突破了以往HNN主要停留在脉冲/神经元尺度混合的局限，探索了面向连续状态估计的群体尺度混合路径。
◆作者将该框架实例化为视觉目标跟踪网络HTNN，使ANN响应图与CANN动态通过共享状态表示交互。
◆论文揭示并利用了两类机制的偏差-方差互补性：ANN估计渐近无偏，CANN估计方差低但存在时间滞后。
◆实验显示HTNN在九个跟踪基准上稳定优于单一网络和已有混合模型，并在遮挡、运动模糊、背景干扰等复杂场景下保持鲁棒性能。</td></tr>
<tr><td>2026-06-19</td><td>Unsupervised Susceptibility Distortion Correction of EPI without Calibration Scans via Image Translation-Based Registration<br><a href='http://arxiv.org/pdf/2606.21588'>论文</a></td><td>◆ 提出SACRED，一种无需场图或反向相位编码等校准扫描的EPI磁敏感畸变校正框架，仅依赖常规T1w图像和单向PE BOLD图像。
◆ 通过基于图像翻译的配准，将BOLD与T1w之间的模态差异转化为可配准的单对比度问题。
◆ 采用可逆神经网络作为翻译骨干，并结合模态无关邻域描述子约束结构一致性，避免解剖结构被错误改变。
◆ 设计无监督训练目标，不需要真实无畸变BOLD图像即可学习畸变校正。
◆ 引入测试时自适应提升跨扫描仪、跨人群等分布外数据的鲁棒性，并在多个数据集上显著优于代表性方法。</td></tr>
<tr><td>2026-06-19</td><td>Context-Aware Autoregressive Diffusion for Gloss-Wise Sign Language Production<br><a href='http://arxiv.org/pdf/2606.21234'>论文</a></td><td>◆ 论文提出GARD，一种面向逐词素生成的上下文感知自回归扩散框架，用于提升句子级手语生成的自然性与可控性。
◆ 不同于一次性生成整段序列的方法，GARD按gloss逐段合成，有效缓解长句中的时间漂移和手部运动模糊问题。
◆ 模型同时利用语义语言上下文与运动学上下文建模词素间协同发音，使单个gloss生成更准确且与上下文一致。
◆ 论文设计Inter-Gloss Transition Guidance，通过梯度引导对齐相邻gloss边界姿态，增强过渡连续性。
◆ 还引入Global Motion Harmonizer，对整体运动序列进行全局细化，在Phoenix-T和CSL-Daily上取得优于现有方法的语言准确性与运动相似度。</td></tr>
<tr><td>2026-06-18</td><td>NeoLoc-68: End-to-end 68-point neonatal facial landmark localisation in neonatal clinical environments<br><a href='http://arxiv.org/pdf/2606.20823'>论文</a></td><td>◆提出首个端到端68点新生儿面部关键点定位模型NeoLoc-68，面向真实临床环境中的疼痛评估需求。
◆整合11个公开数据集的37,459张单脸图像，并加入1,123帧临床新生儿手工标注数据，统一为68点标注体系。
◆将YOLO关键点模型适配为新生儿面部关键点回归器，并利用预训练新生儿人脸检测器权重初始化，提升泛化能力。
◆模型在公开数据集上取得当前最优性能，NME、FR和AUC等指标均表现突出。
◆在临床测试集上，模型面对遮挡、姿态变化和运动模糊仍保持较低检测失败率，微调后性能进一步提升，为非接触式新生儿疼痛与健康监测提供基础。</td></tr>
<tr><td>2026-06-18</td><td>UNSEEN: Uncertainty-aware Navigation via Sparse Estimation in Unknown Environments<br><a href='http://arxiv.org/pdf/2606.20755'>论文</a></td><td>◆UNSEEN提出一种仅依赖前视相机的未知环境视觉导航框架，面向资源受限机器人降低传感器复杂度和部署成本。
◆其核心创新是将定位、建图与规划统一到不确定性感知框架中，显式建模运动指令与感知质量之间的耦合关系。
◆系统以6Hz估计稀疏地图、机器人位姿及其不确定性，并将这些信息持续传递到导航决策中。
◆UNSEEN-Plan采用滚动时域规划，同时优化任务推进和状态估计精度，从而主动选择更利于感知的轨迹。
◆实验表明，UNSEEN-SLAM将绝对平移误差降低9.8%，规划模块最高提升45%估计精度，并在真实未知环境中实现100%任务成功率。</td></tr>
<tr><td>2026-06-18</td><td>ARTEMIS: Agent-guided Reliability-aware Temporal Mask Evolution for Imperfectly Supervised Video Polyp Segmentation<br><a href='http://arxiv.org/pdf/2606.20161'>论文</a> | <a href='https://github.com/wangtong627/ARTEMIS'>代码</a></td><td>◆ ARTEMIS面向不完美监督的视频息肉分割，统一处理点、涂鸦和少量密集标注等低成本监督，缓解伪标签边界泄漏、形状退化和时序不一致问题。
◆ 提出“辩论-裁判”式视觉语言智能体，在弱监督下自动筛选可靠的时序锚点，提升伪标签初始化质量。
◆ 利用SAM2进行双向时序传播，从可靠锚点逐步修正不可靠或未标注帧，实现可靠性感知的时序掩码演化。
◆ 设计时序可靠性感知鲁棒学习机制，包括参考选择、参考原型传输模块和鲁棒损失，以传递目标身份并降低噪声监督影响。
◆ 在SUN-SEG和CVC-ClinicDB-612的涂鸦、点标注及少标签设置下取得领先性能，验证了框架的有效性与临床应用潜力。</td></tr>
<tr><td>2026-06-17</td><td>Pinning Down the Geometry of the Type Ic Broad-Line Supernova 2026gzf<br><a href='http://arxiv.org/pdf/2606.18881'>论文</a></td><td>◆论文首次对Ic-BL型超新星SN 2026gzf在X射线激波 breakout 后4.6天和16.5天开展成像偏振与光谱偏振观测，约束其早期爆炸几何。

◆持续较低的连续谱偏振表明其外层抛射物近似球形，说明爆炸未显著破坏前身星外壳结构。

◆第16.5天Ca II近红外三重线出现超过1.5%的高偏振，揭示氧燃烧产物的激发结构具有明确对称轴。

◆研究发现Ca II线同时包含高速主成分和更外层的次级成分，后者偏振显示外层激发几何非轴对称且更复杂。

◆通过三维蒙特卡洛建模，论文推断观测视角约为相对对称轴40度，可合理再现Ca II线的光谱与偏振特征。</td></tr>
<tr><td>2026-06-17</td><td>Learning to Distort: Weakly-Supervised Image Quality Transfer for Prostate DWI Correction<br><a href='http://arxiv.org/pdf/2606.18869'>论文</a></td><td>◆ 提出一种弱监督图像质量迁移框架，用图像级质量标签（失真/未失真）替代昂贵的体素级配对数据来学习前列腺DWI畸变相关表征。
◆ 在预训练特征空间中构建“质量原型”，利用IQA信号监督从未失真图像到失真图像的质量迁移。
◆ 提出弱监督原型流匹配算法，显式约束生成轨迹逼近失真原型，从而合成更真实的磁敏感伪影。
◆ 通过先“学习生成真实畸变”来构造伪配对数据，再训练正向校正模型，规避了直接无配对校正的不稳定性。
◆ 实验显示该方法生成的伪影能模拟真实临床诊断干扰，并在PI-RADS和Gleason评分等下游任务及外部数据上优于CycleGAN、UNIT-DDPM、OT-FM等方法。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>4887</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4295</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2421</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1613</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1609</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1436</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1269</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1265</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>971</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>950</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>920</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>796</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>780</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>743</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>723</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>713</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>640</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>639</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>623</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>594</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>570</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>557</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>541</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>501</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>495</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>440</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>418</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>343</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>343</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>264</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>253</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>247</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>237</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>223</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>203</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>202</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>169</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>146</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>142</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>119</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2848</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1646</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1354</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1095</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1037</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>868</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>700</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>656</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>649</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>622</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>586</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>573</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>567</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>562</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>551</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>516</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>487</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>463</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>446</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>444</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>335</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>312</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>299</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>283</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>279</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>257</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>222</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>207</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>202</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>186</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>177</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>169</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>167</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>160</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>153</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>138</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>137</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>132</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
<tr><td><a href='https://github.com/ethz-asl/phaser'>phaser</a></td><td>130</td><td>A robust pointcloud registration pipeline based on</td></tr>
<tr><td><a href='https://github.com/ethz-asl/data-driven-dynamics'>data-driven-dynamics</a></td><td>130</td><td>Data Driven Dynamics Modeling for Aerial Vehicles</td></tr>
<tr><td><a href='https://github.com/ethz-asl/ssc_exploration'>ssc_exploration</a></td><td>111</td><td>Incremental 3D Scene Completion for Safe and Effic</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waypoint_navigator'>waypoint_navigator</a></td><td>108</td><td>Stand-alone waypoint navigator</td></tr>
<tr><td><a href='https://github.com/ethz-asl/active_grasp'>active_grasp</a></td><td>108</td><td>Closed-loop next-best view planning for grasp dete</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waverider'>waverider</a></td><td>107</td><td>RMPs on multi-resolution occupancy maps for effici</td></tr>
<tr><td><a href='https://github.com/ethz-asl/reinmav-gym'>reinmav-gym</a></td><td>106</td><td>Reinforcement Learning framework for MAVs using th</td></tr>
<tr><td><a href='https://github.com/ethz-asl/navrep'>navrep</a></td><td>104</td><td>navrep</td></tr>
<tr><td><a href='https://github.com/ethz-asl/eth_supermegabot'>eth_supermegabot</a></td><td>102</td><td>Instructions for ETH center for robotics summer sc</td></tr>
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>102</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/3d_vsg'>3d_vsg</a></td><td>100</td><td>3D可变场景图，用于长期语义场景变化预测。</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.07.03
