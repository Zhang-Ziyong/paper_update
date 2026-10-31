# 计算机视觉领域最新论文 (2026.10.31)

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
<tr><td>2026-10-29</td><td>Smartphone Indoor Localization Enhanced by Hierarchical Multi-Sensor Context Recognition<br><a href='http://arxiv.org/pdf/2610.39691'>论文</a></td><td>本文提出一种由分层多传感器上下文识别增强的智能手机室内定位框架，针对PDR在航向漂移、结构转换和携带模式变化下的误差累积问题，将多传感器信息识别为环境、场景和活动概率，并转换为场景事件段与动作上下文段。其核心贡献在于用分层语义为不同类型定位误差提供定位专用校正线索，而非将所有上下文视为单一事件流或局部修正信号。实验在跨楼层与多动作轨迹上以LiDAR-SLAM为参考，验证该方法优于PDR和代表性学习惯性里程计基线。
◆ 构建数据与模型联合驱动的分层上下文识别模型，输出环境、场景和活动概率并形成两类语义段。
◆ 提出场景事件段约束的PDR校正机制，融合走廊航向约束、地标吸引、固定滞后回溯和垂直过渡处理。
◆ 提出动作上下文段驱动的RoNIN位置补偿，针对携带模式相关漂移实现动作感知修正。</td></tr>
<tr><td>2026-10-29</td><td>UMI-Live for In-The-Wild Bimanual Robotics Data Collection<br><a href='http://arxiv.org/pdf/2610.39385'>论文</a> | <a href='https://umi-live.github.io/}{\text{project'>代码</a></td><td>论文提出UMI-Live，一个面向野外双臂机器人数据采集的全栈开源UMI系统，覆盖硬件、采集界面、数据处理、遥操作与策略训练推理。
◆ 定制UMI-Live硬件集成相机、LiDAR-惯性传感、板载计算与供电，无需外部追踪设备或采集环境内标定。
◆ 设计简洁录制界面，并以异步流水线并行执行SLAM重建，发布可直接用于训练的数据集。
◆ 开源软件支持双YAM遥操作及VLA策略训练和推理，形成从采集到部署的闭环工具链。
◆ 通过微调π0.5和MolmoAct2，在双臂抓取放置任务上分别达到10/10和8/10成功率，验证数据质量。
◆ 公开40小时三任务数据、完整硬件设计、软件与复现指南，降低野外双臂数据采集门槛。</td></tr>
<tr><td>2026-10-28</td><td>SKiD-SLAM: Resource-Aware Distributed Multi-Robot LiDAR SLAM for Planetary Missions with Field Deployments at Analog Sites<br><a href='http://arxiv.org/pdf/2610.38141'>论文</a> | <a href='https://sparolab.github.io/research/skid_slam/'>代码</a></td><td>本文提出SKiD-SLAM，一种面向行星探索的分布式多机器人LiDAR SLAM系统，目标是在严重通信受限、机载计算受限且无中心基础设施的环境中协同建图。
◆ 系统调研实际行星任务的通信与计算预算，并据此选择适配模块完成机器人间地点识别、相对位姿估计和分布式轨迹融合。
◆ 在部署前结合类行星环境公开数据集和基于NASA JPL开源漫游车的模拟器完成系统验证。
◆ 在韩国济州岛熔岩管洞穴和延川KICT行星模拟地形分别用轮式漫游车与四足机器人开展实地任务验证。
结果表明，SKiD-SLAM能在250 kbps机器人间通信预算内可靠执行分布式多机器人LiDAR SLAM，验证了其在挑战性野外条件下的可行性，并公开了代码与现场数据。</td></tr>
<tr><td>2026-10-27</td><td>A Stochastic LineseArch Method (SLAM) for Minimizing Expectation Residuals: Weakening Boundedness of Gradient<br><a href='http://arxiv.org/pdf/2610.37947'>论文</a></td><td>本文为随机线搜索方法SLAM建立非凸复合随机优化的收敛保证，并在更弱假设下保持原分析的迭代与样本复杂度阶数。该分析不要求真实梯度有界，也不要求凸非光滑项r满足Lipschitz连续性。在采样梯度一致Lipschitz连续、无偏且方差一致有界，且小批量与迭代预算成比例时，SLAM达到期望近端梯度残差范数不超过ε的迭代复杂度O(ε^-2)与样本复杂度O(ε^-4)。
◆ 弱化真实梯度有界性假设，在无梯度有界条件下仍证明收敛。
◆ 去除凸非光滑项r的Lipschitz连续性要求，扩大方法适用性。
◆ 在更弱假设下保持原复杂度阶，并以期望近端梯度残差给出明确收敛保证。</td></tr>
<tr><td>2026-10-27</td><td>RAVEN: A Unified Active SLAM System for Rapid Autonomous Visual Exploration with Aerial Robots under Localization Uncertainty<br><a href='http://arxiv.org/pdf/2610.37111'>论文</a></td><td>本文提出RAVEN，一个面向四旋翼机器人在定位不确定性下快速自主视觉探索的统一主动SLAM框架，系统性地将定位不确定性纳入探索规划。
◆ 统一识别前沿与主动回环候选并生成全局巡回候选，在同一框架中权衡探索未知区域与利用已访问区域进行主动回环。
◆ 设计分别量化探索效率与定位精度的效用向量，并引入0到1的优先级参数选择最终巡回，使系统可按任务偏好自适应调整性能。
◆ 提出基于在线Fisher信息场的感知感知导航规划器，实时生成平滑执行轨迹以最小化视觉状态估计误差。
◆ 基准测试表明其优于现有主动SLAM方法，并通过定制双目惯性四旋翼的全机载实地实验验证了挑战环境下的实用性。</td></tr>
<tr><td>2026-10-27</td><td>HoloRecon: Incremental Reconstruction of Long-Range Panoramas with Global Consistency<br><a href='http://arxiv.org/pdf/2610.36876'>论文</a> | <a href='https://zhuoxiaoli.github.io/HoloRecon_page/'>代码</a></td><td>HoloRecon提出一种面向长序列全景的增量重建框架，将ORB稀疏全景建图前端与微调前馈模型耦合，实现长距离重访下的全局一致位姿估计与稠密建图。
◆利用前馈模型预测的局部几何对远距离重访特征匹配进行3D验证，从而在重复结构和部分重叠困难时建立长程相机约束。
◆使用稀疏地标校准预测深度，并将验证后的连接加入全局位姿图优化，再用校正位姿更新稠密几何。
◆构建PanoRecon七场景基准，包含重复建筑、大小回环及参考相机位姿和LiDAR几何，用于评估全局一致性。
实验表明，该方法在评估方法中取得最低平均绝对轨迹误差和较高F-1 Score。</td></tr>
<tr><td>2026-10-27</td><td>LingGS: Decoupling Feed-Forward Geometry Prediction from Camera Tracking for High-Fidelity Gaussian SLAM<br><a href='http://arxiv.org/pdf/2610.36853'>论文</a></td><td>本文提出LingGS，一种面向单目RGB高斯泼溅SLAM的在线系统，在有限优化预算下兼顾高质量重建与响应式相机跟踪。
◆将前馈几何预测与相机跟踪解耦，用显式几何跟踪替代学习式相机预测以提升跟踪精度。
◆采用冻结的流式3D基础模型作为虚拟RGB-D传感器，从单目视频提供深度估计。
◆设计显式几何求解器，通过特征重投影估计相机运动。
◆构建流式高斯建图器，将观测融合为稠密场景表示。
◆验证几何跟踪可跨代表性流式几何骨干提升位姿精度，体现方法普适性。
实验表明其在室内外数据集上显著提升重建质量，单RTX 4090约7 FPS，吞吐量为对比SLAM系统的2至3倍。</td></tr>
<tr><td>2026-10-27</td><td>SVIn+: Multi-Modal Framework for Robust Underwater State Estimation using 3D Sonar, Visual-Inertial, Water-Pressure, and DVL<br><a href='http://arxiv.org/pdf/2610.36454'>论文</a> | <a href='https://cmburgul.github.io/projects/svin+/'>代码</a></td><td>本文提出SVIn+，一个融合IMU、相机、水压传感器、DVL与紧凑型3D声纳的AUV鲁棒状态估计多传感器框架。该工作扩展开源视觉惯性SLAM系统SVIn，将水压与DVL测量紧耦合进非线性优化，以提升估计精度。
◆ 将水压和DVL观测集成到紧耦合非线性优化中，扩展SVIn并改善状态估计。
◆ 设计层次化架构，将KISS-ICP解耦前端估计作为因子图中的相对位姿因子，从而利用3D声纳结构信息并保持计算效率。
◆ 通过沉船与珊瑚礁实地部署验证漂移抑制和全局一致性，并公开代码与数据集以促进水下多模态融合研究。</td></tr>
<tr><td>2026-10-26</td><td>SG^2SLAM: Spatial Geometry-Informed 3D Gaussian Splatting SLAM for Monocular Outdoor Navigation<br><a href='http://arxiv.org/pdf/2610.36312'>论文</a></td><td>本文提出SG^2SLAM，一种面向单目户外导航的空间几何引导3D高斯泼溅SLAM，旨在解决逐帧2D-3D关联将跟踪误差吸收进地图并引发级联退化的问题。
◆ 采用流式空间几何，以块级度量先验替代逐帧跨维对应，从同一来源同时监督跟踪与建图，减少误差累积。
◆ 设计射线条件3DGS核，为每个图元增加视角方向子空间，使其感知单目相机视点并增强几何表达。
◆ 联合优化空间几何与相机位姿，保证地图和轨迹的全局一致性。
在KITTI和Waymo Open数据集上，该方法在单目户外导航任务中优于逐帧关联基线。</td></tr>
<tr><td>2026-10-26</td><td>VPR-Space: A Benchmark for Visual Place Recognition in Space Analog Domains<br><a href='http://arxiv.org/pdf/2610.35642'>论文</a> | <a href='https://github.com/rfechner/VPR-Space}$'>代码</a></td><td>本文提出VPR-Space，一个面向太空类比域（SAD，即类似月面或火星地表的地球环境）的视觉位置识别基准，用于评估现有VPR在特征稀缺的外星表面环境中的能力。
◆ 构建了基于现有太空类比域数据的16个VPR数据库-查询数据集，系统覆盖环境、视角变化和光照条件等多类挑战。
◆ 提出一种面向下游SLAM价值的VPR真值生成方法，不再仅以固定位姿阈值判定是否同一地点，而要求匹配对后续相对位姿估计能提供有价值的位姿估计。
◆ 通过集成多种先进相对位姿估计器生成真值矩阵，避免在SLAM系统中闭环评估VPR的开销与限制，并据此定义基准评价目标。
论文评估了九种先进VPR方法，结果显示现有方法仍有明显提升空间，并指出了未来研究方向。
作者还发布了该数据集的预发布版本，便于社区复现和后续研究。</td></tr>
<tr><td>2026-10-26</td><td>PosePlaner: Denoising Any Feed-Forward Pose Predictor from Pairwise Planar Geometry<br><a href='http://arxiv.org/pdf/2610.34845'>论文</a></td><td>PosePlaner针对DUSt3R、VGGT等前馈位姿预测器将对应、几何与位姿纠缠于单次前向、测试时缺乏几何纠正机制的问题。其核心贡献是重新建立对应关系与位姿之间的经典耦合，把位姿精化建模为条件生成问题。
◆ 用flow matching将粗几何匹配和初始位姿作为条件，生成并融合多个位姿假设为单一精化结果。
◆ 提供RANSAC投票的连续、数据驱动类比，使测试时可利用几何证据纠正前馈预测。
◆ 仅在两视图数据上高效训练，却可无需重训地作为流式多视图位姿估计器的周期精化模块。
实验表明它能纠正前馈预测失败、显著提升基于对应的求解器，并减少长流式序列的累积漂移。</td></tr>
<tr><td>2026-10-25</td><td>T-ConSG: A LiDAR-Based Real-Time Temporal Construction Scene Graph for Dynamic and Evolving Environments<br><a href='http://arxiv.org/pdf/2610.34041'>论文</a></td><td>论文提出基于LiDAR的实时时序施工场景图T-ConSG，统一表示自由空间、静态物体、动态物体与环境事件。
◆ 构建带空间关系边和事件参与边的场景图，将短期动态与长期环境演化纳入同一表示。
◆ 从LiDAR几何证据增量建图，持续维护自由空间和静态物体信息并实时跟踪动态物体。
◆ 将累积空间证据变化显式建模为安装与移除事件，使图能同时捕获瞬态动态和持久变化。
作者通过砌墙试验台动态感知导航、ConSLAM施工进度监测和仿真环境在线变化检测三项应用验证了方法。
结果表明T-ConSG能统一组织时空信息，并支持同时包含短期动态和持久变化的机器人推理。</td></tr>
<tr><td>2026-10-23</td><td>TinyFlow: Breaking the Warping Bottleneck for Edge Optical Flow<br><a href='http://arxiv.org/pdf/2610.33338'>论文</a></td><td>TinyFlow 提出一种仅1.26M参数的无warp光流网络，在保持迭代式粗到细精炼的同时，解决边缘加速器上流依赖重采样和数据相关访存导致的部署瓶颈。
◆ 用固定窗口相关替代基于当前流的warp，并采用常量偏移，使网络可编译为单一静态INT8计算图。
◆ 结合量化感知微调、warp教师蒸馏和模型汤，将Float32到INT8的精度损失在MPI-Sintel上降至0.2 EPE以内。
◆ 在Sintel Clean/Final和FlyingChairs上，Float32与INT8均优于EdgeFlowNet和NanoFlowNet，且参数比EdgeFlowNet少54%，INT8 EPE达6.29/7.13。
◆ 在TartanAir和UZH-FPV的纯光流单目视觉里程计中，同一INT8模型在11个序列中的7个取得最低轨迹误差。</td></tr>
<tr><td>2026-10-23</td><td>Bracketing Shows the Way: Adaptive Multi-Exposure Policy as Input for Robust Visual SLAM<br><a href='http://arxiv.org/pdf/2610.33174'>论文</a> | <a href='https://github.com/norlab-ulaval/bracketing-shows-the-way'>代码</a></td><td>本文针对快速光照变化导致图像饱和、自动曝光来不及适应并造成视觉SLAM丢失对应的问题，提出从曝光策略和状态估计两个层面提升鲁棒性。  
◆ B-Adapt通过获取自适应曝光包围来覆盖场景动态范围，同时促进相邻曝光间的光度重叠。  
◆ BVSLAM将多曝光序列直接作为因子图状态估计中的约束，无需依赖HDR合并。  
作者在常规环境和模拟32 m/s车速下重复隧道出口过渡场景中与先进方法进行了对比验证。  
结果表明，B-Adapt与BVSLAM结合相比自动曝光图像将状态估计误差降低78%，并在常规条件下保持较低误差。  
这些结果说明曝光包围能有效提升视觉位姿估计对快速光照扰动的鲁棒性。</td></tr>
<tr><td>2026-10-22</td><td>Consistent Distributed Invariant EKF SLAM with Point and Object Features<br><a href='http://arxiv.org/pdf/2610.31221'>论文</a></td><td>本文提出Joint-CI，一种面向点特征、物体特征及混合地图的分布式RI-EKF SLAM统一融合方法，解决邻居地图估计因与自身位姿相关而无法直接使用CI融合的问题。
◆ 在接收机器人误差坐标下，利用邻居局部后验和机器人间观测构建接收机器人位姿与共同特征的联合估计，从而保留机器人—特征及特征—特征相关性。
◆ 提出部分状态协方差交集融合框架，将上述联合估计与接收机器人局部后验融合，实现点、物体和混合地图的统一处理。
◆ 理论证明该统一建模与融合保持全局旋转和平移对应的六个不可观方向，并在局部后验一致时保持一阶协方差一致性。
◆ 蒙特卡洛仿真和真实数据集实验表明，Joint-CI在保持一致且轻度保守不确定性的同时提升了估计精度。</td></tr>
</tbody>
</table>
</div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-28</td><td>Environmental Quenching of Satellite Galaxies out to z~0.4 with GAMA and DEVILS<br><a href='http://arxiv.org/pdf/2610.38836'>论文</a></td><td>本文利用GAMA与DEVILS在星系属性和环境度量上的一致处理，将卫星星系环境淬灭研究拓展到z~0.4，并降低跨巡天比较的系统偏差。
◆ 实现GAMA与DEVILS之间采用一致样本选择和环境指标的跨红移卫星星系淬灭比较。
◆ 以投影相空间作为入群时间代理，定量刻画淬灭比例演化及卫星星系相对恒星形成主序的偏离。
◆ 测得卫星星系入群后恒星形成率相对SFMS以约0.14 dex/Gyr的速率持续下降。
◆ 发现早型和晚型卫星星系均呈类似下降趋势，且两巡天间无显著红移演化，表明过去约45亿年群团环境对卫星恒星形成活动影响相当。</td></tr>
<tr><td>2026-10-27</td><td>HoloRecon: Incremental Reconstruction of Long-Range Panoramas with Global Consistency<br><a href='http://arxiv.org/pdf/2610.36876'>论文</a> | <a href='https://zhuoxiaoli.github.io/HoloRecon_page/'>代码</a></td><td>本文提出HoloRecon，一个面向长序列全景场景的增量重建框架，将ORB稀疏全景建图前端与微调前馈重建模型耦合，以兼顾准确定位和全局一致稠密建图。
◆ 利用前馈模型预测的局部几何对远距离回访的ORB特征匹配进行3D验证，从而在重复结构和部分重叠困难下建立长程相机约束。
◆ 用稀疏地标校准预测深度，并将验证后的远距离连接加入全局位姿图优化，再用校正位姿更新稠密几何。
◆ 提出PanoRecon七场景基准，涵盖重复建筑、大/小回环，并提供参考相机位姿与LiDAR几何用于全局一致性评测。
该方法在评测中取得最低平均绝对轨迹误差和较高F-1 Score，验证了其长程全景重建的全局一致性。</td></tr>
<tr><td>2026-10-27</td><td>Metric Scale for Insta360 Structure-from-Motion from the Camera&#x27;s Embedded IMU<br><a href='http://arxiv.org/pdf/2610.35554'>论文</a></td><td>本文评估Insta360 X5/X6内置1 kHz IMU作为自包含度量尺度来源，替代手机ARKit/ARCore位姿，通过线性视觉惯性对齐从SfM位姿恢复尺度。◆提出仅依赖360相机内置IMU的自包含度量尺度恢复方案，摆脱对外部手机位姿的依赖。◆完成IMU噪声、相机-IMU同步、加速度计尺度因子和偏置稳定性表征，并从数据估计相机-IMU旋转与帧时序。◆发现全测量共享重力和加速度计偏置会使尺度平均高估3.4%，提出分段独立估计再平均以消除偏差。◆在LiDAR、基准轨迹和生产测量中系统验证，惯性尺度平均绝对误差0.74%，优于手机尺度的1.94%。◆完成窗口构建消融及与单目度量深度网络比较，并分析生产数据中惯性尺度与手机尺度差异的来源。</td></tr>
<tr><td>2026-10-26</td><td>Synthetic Deformable Tubular Benchmark: A mechanically annotated dataset for evaluating deformable 3D reconstruction<br><a href='http://arxiv.org/pdf/2610.35621'>论文</a></td><td>本文提出合成可变形管状基准，用开源工具LumenMorph生成、标注并评估管状场景，包含5580张RGB图像，为可变形三维重建提供受控合成参考。
◆构建跨三种表面运动条件与移动/静止相机的六类场景基线，并提供四类场景的匹配外观变体，系统覆盖相机与表面运动耦合。
◆公开接口给出相机位姿、几何、深度、变形场、持久材质对应及离散有限元记录，支持跨帧追踪同一表面位置及其三维轨迹。
◆引入持久三角形身份与材质权重，并设置独立几何和机械一致性检查，便于核验标注与生成模型的一致性。
◆通过SfM、光流和给定几何位移插值实验，区分配准覆盖与几何精度，揭示相机与表面运动效应，并检验机械先验的收益与失配。
作者明确数据完整性、固定环境重复性和预测分数回放各有验证范围，且不宣称解剖或临床真实性。</td></tr>
<tr><td>2026-10-26</td><td>Generative Structure from Motion with Native 3D Diffusion<br><a href='http://arxiv.org/pdf/2610.35522'>论文</a> | <a href='https://dotb1ue.github.io/GenSfm/'>代码</a></td><td>GenSfM 将基于图像的3D重建与原生3D扩散模型统一起来，用于从少量未标定视图联合恢复物体3D结构和相机运动，避免重建与生成两阶段拼接导致的误差级联。
◆ 提出多模态扩散Transformer，在共享自注意力下联合去噪形状潜变量与每视图位姿潜变量，使生成几何既受输入视图约束，又能借助物体级先验推断未观察区域。
◆ 设计紧凑的3D原生UV-volume tokenization，使联合序列在增加视图时仍保持较小规模，提升多视图联合建模效率。
◆ 引入位姿感知细化阶段，在恢复的相机位姿下采样逐体素图像特征，进一步优化几何与纹理。
在Toys4k和GSO上使用4个未标定视图时，新视角PSNR提升3.2至4.5 dB，中位Chamfer距离降低2.8至3.8倍，输入视图位姿恢复达到96%以上Acc@5°，且无需外部位姿估计骨干、后处理优化或已知内参。</td></tr>
<tr><td>2026-10-26</td><td>Learning Scene Coordinate Reconstruction from Unposed Images via Pose Graph Optimization<br><a href='http://arxiv.org/pdf/2610.35501'>论文</a></td><td>论文提出一种混合框架，将位姿图优化（PGO）引入ACE-Zero，用于从无位姿图像中学习场景坐标重建并优化相机位姿。该方法针对ACE-Zero缺乏全局和多视图一致性约束、易产生位姿漂移和错位的问题，利用ACE-Zero预测的场景坐标直接构建位姿图并提取相对位姿约束。
◆ 将PGO集成到ACE-Zero中，形成学习推理与全局几何优化互补的混合结构，以抑制错误优化和位姿漂移。
◆ 直接从ACE-Zero输出构建位姿图，从预测场景坐标中提取相对位姿约束，避免依赖额外位姿标注。
◆ 引入不确定性感知优化策略，利用对极几何和光流一致性等几何先验估计置信度，提高优化鲁棒性。
实验表明，该方法提升了无监督结构运动恢复中位姿估计的鲁棒性和准确性，说明全局几何推理能有效补充学习式推理。</td></tr>
<tr><td>2026-10-26</td><td>PosePlaner: Denoising Any Feed-Forward Pose Predictor from Pairwise Planar Geometry<br><a href='http://arxiv.org/pdf/2610.34845'>论文</a></td><td>现有前馈多视图位姿预测器将对应、几何与位姿纠缠在单次前向中，难以在测试时利用几何证据校正，主要依赖监督微调。本文提出PosePlaner，将位姿细化建模为条件生成，用流匹配重新耦合粗几何匹配与初始位姿，并融合多个位姿假设形成连续数据驱动的RANSAC式投票。
◆ 以流匹配重新耦合对应与位姿，把位姿精化转化为条件生成问题。
◆ 以粗几何匹配和初始位姿为条件，融合位姿假设得到单一精化估计，提供RANSAC投票的连续数据驱动类比。
◆ 仅在两视图数据上高效训练，却能作为任意前馈n视图流式位姿估计器的周期精化器且无需重训。
◆ 实验证明其能纠正前馈预测失败、提升基于对应求解器，并减少长流式序列的累积漂移。</td></tr>
<tr><td>2026-10-25</td><td>No Cones, No Duals: A Fast and Scalable Solver for NRSfM<br><a href='http://arxiv.org/pdf/2610.34403'>论文</a></td><td>本文提出一种快速、可扩展的NRSfM求解器，避开传统SDP锥求解与ADMM形状恢复，从而克服长序列和密集轨迹下的扩展性瓶颈。
◆ 旋转估计采用可微欧氏校正，直接优化每条序列的小规模因子，并用行极投影将相机块映射为最近的行正交矩阵。
◆ 形状估计提出展开式谱近端求解器，在重排形状域中结合重投影梯度步与加权奇异值收缩。
◆ 该求解器引入FISTA式重启与延续策略，并将经典谱收缩嵌入固定的可微求解框架，同时保持NRSfM几何约束。
◆ 方法类别无关、无需外部训练数据，且自然映射到适合现代加速器的线性代数原语。
在稀疏、密集、噪声、缺失数据和长序列基准上，它以有竞争力的精度实现显著加速，密集序列最高达7至1000倍运行时提升。</td></tr>
<tr><td>2026-10-23</td><td>FlexGlue: Sparse-to-Dense Feature Matching and Visual Disambiguation<br><a href='http://arxiv.org/pdf/2610.32976'>论文</a> | <a href='https://github.com/cvg/flexglue'>代码</a></td><td>本文提出FlexGlue，一种面向非对称稀疏到稠密匹配与视觉消歧的神经网络，旨在同时解决稀疏匹配重复性不足、稠密匹配开销大以及仅用匹配对训练导致难以拒绝视觉对称误匹配的问题。
◆ 采用稀疏到稠密匹配范式：仅输入第一幅图的点坐标，在第二幅图稠密像素中搜索有限对应，兼顾稀疏匹配的速度与稠密匹配的亚像素精度。
◆ 将匹配与消歧统一在同一网络中：在估计对应坐标的同时判断并拒绝非匹配对，提高对视觉对称等错误配对的高精度拒绝能力。
◆ 通过有限对应搜索实现快速且有效的匹配与消歧，在多个数据集上推进相对位姿估计的Pareto前沿，并在SfM和视觉定位中显著优于现有方法，代码已公开。</td></tr>
<tr><td>2026-10-23</td><td>Localization and Neural Splatting on the Edge: An FPGA Scene Memory for Robots<br><a href='http://arxiv.org/pdf/2610.25068'>论文</a></td><td>LENS是部署在AMD KR260上的低功耗FPGA/ARM边缘场景记忆加速系统，将ACEsplat风格相机定位与近邻视图渲染带到无桌面GPU的机器人平台，核心不是提出新场景模型，而是让两个主导内核与板级数据路径协同设计。
◆ 设计INT16 SCR加速器，在25.42 ms内保持DSAC*定位精度，解决SCR姿态敏感带来的边缘部署难题。
◆ 设计位精确定点有序3DGS渲染器，将alpha透射率改写为log-sum-exp递推，并剔除可证明无用的流式高斯。
◆ 全部延迟、功耗和质量结果均板级实测，实现相对Jetson Orin NX每瓦性能1.9至5.7倍提升，功耗约四分之一。
渲染质量上，Cambridge达34.11 dB高于ACEsplat的33.20 dB，RealEstate10K达27.84 dB高于26.11 dB，十个Wayspots场景均达目标。
其端上训练可达ACEsplat级质量，但时间和能耗仍不及GPU，指明未来训练加速器的边界。</td></tr>
<tr><td>2026-10-22</td><td>MVLoMa: Multi-View Local Feature Matching with Any Geometry Foundation Model<br><a href='http://arxiv.org/pdf/2610.31321'>论文</a></td><td>MVLoMa将局部特征匹配从图像对扩展到由中心图像和多个邻域构成的稀疏星图，用单次前向完成中心图与所有邻居的匹配，避免逐边重复计算并利用多视图互补几何证据。
◆ 使用冻结的多视图几何基础模型联合描述星图内所有图像，并把跨视图几何上下文注入局部描述子。
◆ 设计每视图自注意力和双向中心—邻域交叉注意力，在一次前向中联合匹配中心图与所有邻居。
◆ 仅从深度有效且相互可见的稠密warp生成正对应，并显式惩罚违反对极几何的高置信匹配，同时支持DA3、π^3、VGGT、VGGT-Ω等冻结几何编码器。
在HyperSim、ScanNet++、Mip-NeRF 360和Tanks and Temples的25视图星图上，该方法在三个阈值下取得最佳宏平均相对位姿AUC（58.65/85.41/90.99），匹配速度比顺序评估24条中心—邻域边快2.20倍。
受控消融进一步分离了几何感知描述子、可见性过滤、几何负监督和联合多视图推理的贡献。</td></tr>
<tr><td>2026-10-20</td><td>CrossFit-GS: Out-of-Fold Pose Estimation for COLMAP-Free 3D Gaussian Splatting<br><a href='http://arxiv.org/pdf/2610.28190'>论文</a></td><td>CrossFit-GS提出一种延迟提交的渐进式无位姿3DGS框架，可在无COLMAP/SfM条件下从无位姿图像序列直接重建场景。
◆将输入序列划分为交错子集并维护两个互补子图，使候选位姿在从未用目标帧优化过的冻结对侧子图上交叉细化，从而获得独立几何参考。
◆引入棋盘验证和空间覆盖保障机制，拒绝不可靠位姿更新，仅将验证通过的位姿提交到所属子图，以打断畸变地图误差自增强循环。
◆在轨迹精炼后丢弃中间子图，并利用固定的精炼位姿从头训练最终全局表示，避免中间误差残留。
实验表明该方法在多个基准上显著降低累计轨迹漂移，并稳定提升相机位姿估计与新视角合成性能。</td></tr>
<tr><td>2026-10-19</td><td>RoboCloth: A Large-Scale Real Cloth Material Dataset for Neural Reflectance Reconstruction<br><a href='http://arxiv.org/pdf/2610.21090'>论文</a></td><td>RoboCloth提出了一个大规模真实布料材质数据集，包含500种布料在机器人控制相机与光照下采集的约580张HDR帧，覆盖广视角-光照半球。数据经SfM细化相机位姿并对齐机器人坐标系，提供每材质稀疏几何和结构化逐点反射观测，可直接用于神经材质训练。论文设计两阶段神经重建流程，先训练共享MLP解码器学习布料材质先验，再冻结解码器并为目标材质拟合2048x2048密集潜纹理。在自留出材料和UBO2014基准上，该方法优于现有测量反射数据集训练的解码器及解析PBR拟合，并能迁移到未见采集系统。数据集、标定文件、观测张量和训练测试划分以CC BY 4.0在Hugging Face Hub发布。
◆构建了机器人控制采集的大规模真实布料反射数据集，覆盖丰富视角-光照条件并提供标定与结构化观测。
◆提出两阶段神经材质重建方法，利用数据先验实现密集潜纹理拟合和跨采集系统迁移。</td></tr>
<tr><td>2026-10-16</td><td>Ionic switching between supermagnetic states<br><a href='http://arxiv.org/pdf/2610.23829'>论文</a></td><td>论文首次展示利用室温锂离子传输，在不重新合成、不持续外部刺激下实现超铁磁态与超自旋玻璃态的可逆磁离子切换并可保持。  
◆ 提出通过NiO不完全锂化生成纳米Ni和Li2O，实现两种超磁态相互转化的新机制。  
◆ 揭示锂化形成碎片化纳米Ni网络增强偶极相互作用，稳定超铁磁态并提升室温磁矩与记忆。  
◆ 发现脱锂部分再生NiO驱动超自旋玻璃态，获得更高低温矫顽力和更尖锐温度选择性记忆，且多轮循环可逆。  
该工作建立了超磁态可逆切换的通用框架，为磁离子器件设计提供新思路。</td></tr>
<tr><td>2026-10-14</td><td>Why 3D Reconstruction Breaks Down on Under-Ice AUV Video, and How to Predict It<br><a href='http://arxiv.org/pdf/2610.19993'>论文</a></td><td>本文系统检验冰下AUV视频三维重建不准是方法缺陷还是采集系统固有限制，并在同一段南极Icefin/Kamb冰流视频上测试经典特征匹配SfM、可微分光度splatting、体深度融合和无位姿前馈基础模型四类方法。四类方法均失败，分别呈现近乎无配准、光度指标健康但几何破碎、持续覆盖伪影和跨块尺度不稳定，且都可归因于相机基线相对场景深度过小的同一采集机制。作者据此提出快速检测系统，能在几分钟内标记此类失败，避免数小时无效计算。
◆ 首次统一评测四类代表性重建范式，揭示冰下AUV视频的共性失败与不同失效模式。
◆ 将失败根源归因于小相机基线-场景深度比这一采集条件，而非单一算法缺陷。
◆ 提出分钟级失败预警检测系统，显著减少无效算力消耗。</td></tr>
</tbody>
</table>
</div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-29</td><td>Luggage re-identification: A study of strategies towards a real-world application<br><a href='http://arxiv.org/pdf/2610.40643'>论文</a></td><td>本文面向真实视频监控场景，研究从多路视频流到行李检测与重识别的端到端行李ReID流程，弥补现有方法多依赖干净裁剪图像外观匹配、忽视多镜头多视角互补的不足。作者在真实环境基准数据集上系统评估不同流程变体，分析同一行李多视角与多镜头观测的选择和融合方式，并考察跨环境数据集训练对整体ReID性能的影响。核心贡献在于将多视频流互补信息纳入实际行李ReID应用，并给出可操作的策略评估。
◆ 提出面向真实应用的端到端多视频流行李检测与重识别流程。
◆ 系统研究并利用同一行李的多镜头、多视角和多观测互补信息进行选择与融合。
◆ 在真实环境基准上评估跨环境数据集训练等策略，为提升实际场景行李ReID性能提供依据。</td></tr>
<tr><td>2026-10-29</td><td>Comprehensive empirical evaluation of feature extractors in computer vision<br><a href='http://arxiv.org/pdf/2610.39551'>论文</a></td><td>本文对传统特征检测与描述子进行系统实证评估，覆盖SIFT、SURF、BRIEF、ORB、BRISK、KAZE、AKAZE、FREAK、DAISY、FAST和STAR，并从架构设计与复杂度分析其计算效率和鲁棒性。研究基于Image Matching Challenge Photo Tourism 2020中超过150万张图像，完成超过200万次比较，系统考察旋转、缩放、模糊、亮度变化、仿射、透视、鱼眼和椒盐噪声等条件。结果表明FAST检测器配合ORB描述子和BF匹配器速度最快，ORB在仿射变换和亮度增强图像上表现突出，AKAZE在模糊、鱼眼畸变、旋转和透视畸变下更优。
◆ 构建了覆盖多类传统特征提取器与多种图像变换的大规模统一实证基准。
◆ 揭示了检测器、描述子与匹配器组合对效率和鲁棒性的综合影响。
◆ 给出了面向不同退化与几何变换场景的特征提取方案选型依据。</td></tr>
<tr><td>2026-10-28</td><td>Aligning Misaligned Benchmarks for Single-View Novel View Synthesis<br><a href='http://arxiv.org/pdf/2610.38349'>论文</a></td><td>论文针对单视图新视角合成评测中参考系与真值位姿对齐这一关键但未标准化的问题，系统分析了现有测试时位姿优化和依赖全场景重建对齐策略的缺陷。
◆提出用传统2D-to-2D与2D-to-3D图像匹配技术对齐三维重建，避免病态的测试时位姿优化和不可行的全场景重建。
◆提出仅在视图间共视区域进行评估，因为只有该区域能够定义正确的真值。
◆发现正确坐标对齐后，显式3D高斯方法达到当前最优，纠正了其此前被纯图像2D方法超越的结论。
◆给出直接利用现成视频生成器和前馈几何估计器的简单基线，无需任务特定训练即可与专门方法相当。</td></tr>
<tr><td>2026-10-28</td><td>WovenAnchor Matcher: Specialized Intra- and Inter-Image Context Modeling for Feature Matching<br><a href='http://arxiv.org/pdf/2610.30799'>论文</a> | <a href='https://github.com/mmaiLab/WovenAnchorMatcher'>代码</a></td><td>本文提出WovenAnchor Matcher（WAM）半稠密匹配框架，核心是按图像内与图像间上下文的不同角色进行专门化聚合。
◆ 设计角色分工的WAM框架，将图像内空间证据传播与图像间对应区域信息检索解耦。
◆ 提出WovenMamba，以先水平后垂直的状态空间传播实现图像内聚合，形成结构化二维感受野偏置。
◆ 提出AnchorCrossAttention，在局部代表锚点上进行跨注意力，从可能对应区域聚集信息并抑制无关噪声。
在MegaDepth上，WAM取得66.1 pose AUC@5°，较JamMa基线提升2.0个AUC点。
消融实验表明移除或替换任一专用组件都会降低精度，验证了角色专门化聚合设计的有效性。</td></tr>
<tr><td>2026-10-23</td><td>ACVA-Bench: Beyond Prompt Following in Abstract Concept Visualization Ability for Text-to-Image Models<br><a href='http://arxiv.org/pdf/2610.32058'>论文</a></td><td>本文定义抽象概念可视化能力（ACVA），即T2I模型在无固定视觉参照下将“忠诚”等抽象概念转化为准确、多样且可区分视觉表征的能力，并构建类别平衡的ACVA-Bench进行系统评测。
◆ 提出基于心理语言学规范的ACVA-Bench，在低干预设置下不提供具体物体、场景或视觉隐喻，从语义充分性、表征多样性、概念区分性三个维度评估ACVA。
◆ 针对抽象概念缺乏唯一参考图，提出受概念语义约束的细粒度视觉语义评估方法，将概念语义分解为可独立验证的视觉语义问题，并经人工评估验证有效性。
◆ 系统基准主流T2I模型，揭示其依赖少量原型视觉模式，在表征多样性和概念区分性上仍有明显提升空间。
◆ 提供可解释、可复现的抽象概念可视化评测基础，推动T2I从提示跟随走向更深层的概念理解。</td></tr>
<tr><td>2026-10-22</td><td>MVLoMa: Multi-View Local Feature Matching with Any Geometry Foundation Model<br><a href='http://arxiv.org/pdf/2610.31321'>论文</a></td><td>本文提出MVLoMa，一种稀疏星图局部特征匹配器，将LoMa从图像对扩展到一中心多邻居的多视图匹配，避免逐边独立匹配的参考侧重复计算并利用多视图几何证据。
◆ 使用冻结的多视图几何基础模型联合描述星图中的所有图像，并将跨视图几何上下文注入局部描述子。
◆ 通过每视图自注意力和双向中心—邻居交叉注意力，在单次前向中完成中心图像与全部邻居的匹配。
◆ 仅从深度有效且相互可见的稠密warp生成正对应，并显式惩罚违反极几何的高置信匹配。
◆ 同一设计兼容DA3、π^3、VGGT和VGGT-Ω等冻结几何编码器，且DA3-Giant表现最佳。
在HyperSim、ScanNet++、Mip-NeRF 360和Tanks and Temples的25视图星图上，MVLoMa在三个阈值取得最佳相对位姿AUC（58.65/85.41/90.99），匹配器比顺序评估24条中心—邻居边快2.20倍，消融验证了几何感知描述子、可见性过滤、几何负监督和联合多视图推理的有效性。</td></tr>
<tr><td>2026-10-22</td><td>HimmBO: High-Dimensional Interactive Model-Merging Bayesian Optimization for Image Generation<br><a href='http://arxiv.org/pdf/2610.30875'>论文</a></td><td>HimmBO提出一种面向图像生成的两阶段高维交互式适配器合并贝叶斯优化方法，将偏好驱动的模型合并扩展到更大适配器集合并显著降低图像生成开销。
◆筛选阶段利用预生成图像上的水平集估计恢复活跃适配器集合，整个阶段无需生成新图像。
◆精炼阶段在恢复的低维子空间中优化合并系数，避免直接在高维全集合上搜索。
◆两阶段均采用风格感知核，使偏好信息能在视觉相似的适配器之间迁移复用。
实验表明，HimmBO在模拟用户图像匹配中最终相似度优于所有对比方法，达到给定相似度所需图像生成次数不足先前方法的十分之一。
其性能在适配器集合扩展到1080个时仍保持稳定，而竞争方法明显退化。</td></tr>
<tr><td>2026-10-18</td><td>LateMatch: Breaking the Interaction Bottleneck via Cacheable Matching for Efficient Visual Localization<br><a href='http://arxiv.org/pdf/2610.25358'>论文</a></td><td>论文针对现有深度特征匹配器在每层紧耦合图像内上下文与跨图匹配、对K张库图需重复执行完整网络且无法缓存的问题，指出严重交互瓶颈。  
◆提出可缓存图像匹配新范式，将跨图交互推迟到网络末层，使图像内处理可离线缓存、在线仅执行少量交互计算。  
◆提出LateMatch，通过Context Blocks与Interaction Blocks解耦重构现有匹配器，实现通用且高效的视觉定位部署。  
◆提出E-SToRE，利用晚期交互块香农熵下降，在跨图交互前动态进行空间token缩减与扩展。  
在HPatches、ScanNet、MegaDepth、ETH-3D和Aachen上验证，LateMatch相较标准深度匹配器降低有效计算成本2倍以上。  
E-SToRE进一步带来10%至14%额外节省且精度几乎不退化。</td></tr>
<tr><td>2026-10-16</td><td>DinoMUSE: A DINOv2-guided Framework for Unsupervised Lateral Motion Estimation in Ultrasound Elastography<br><a href='http://arxiv.org/pdf/2610.24020'>论文</a></td><td>论文提出DinoMUSE，一种DINOv2引导的混合专家无监督框架，用于超声弹性成像中的横向运动估计。针对横向分辨率低、采样频率低且缺乏相位信息，现有局部匹配与物理约束方法上下文不足的问题，该方法引入DINOv2高层视觉表征为运动估计提供全局上下文引导。
◆ 将DINOv2学习到的可迁移高层视觉表示融入运动估计网络，以全局上下文弥补局部匹配信息不足。
◆ 设计基于混合专家的特征融合模块，自适应变换并整合DINOv2特征与局部匹配特征，促进两类表示有效交互。
◆ 构建无监督横向位移与应变估计框架，在仿真和活体乳腺数据上验证其横向精度显著优于NCC、GLUE、RAFT和sPICTURE等方法。
实验表明，DinoMUSE在仿真数据上将横向位移和应变估计的MSE分别降低60%和65%，并在活体乳腺数据中提升应变SNR、CNR及病灶可视化效果，同时保持有竞争力的轴向性能。</td></tr>
<tr><td>2026-10-15</td><td>CLAD: Keypoint Matching Using Global Line Correspondences<br><a href='http://arxiv.org/pdf/2610.21409'>论文</a></td><td>论文提出CLAD，用全局线对应为关键点匹配提供几何上下文，以克服SIFT、ORB等局部描述子在重复纹理或弱纹理下不稳定的问题。
◆ 将关键点表示成到匹配线邻近度的向量，编码其与场景线性结构的空间关系。
◆ 使用HOME检测清晰和弱线性结构，建立足够线-关键点关联以形成全局上下文。
◆ 把全局几何一致性引入匹配，补充传统局部描述子，提高重复场景的匹配可靠性。
◆ 方法计算轻量、易于实现，并在TUM RGB-D SLAM和户外视频上验证有效性。</td></tr>
<tr><td>2026-10-12</td><td>The Value of Being Wrong: Self-Mined Visual In-Context Learning from Errors<br><a href='http://arxiv.org/pdf/2610.16977'>论文</a> | <a href='https://tree-shu-zhao.github.io/SMILE/'>代码</a></td><td>本文提出 SMILE，一种利用模型自身错误进行自挖掘视觉上下文学习的方法，以更简单方式提升视觉语言模型的 ICL 效果。  
◆利用目标 VLM 自身预测错误作为天然反事实示例，直接编码其失败模式，避免属性提取、描述工程和组合图像匹配等多阶段管线。  
◆离线构建模型特定的困难负例池，记录该模型过去的错误，使示例选择与具体模型能力绑定。  
◆测试时将当前预测作为方向信号，在语义嵌入空间中检索最可能复发的历史错误，形成预测条件化的示例识别机制。  
◆该机制统一支持闭集分类和开放式视觉问答，无需任务特定设计。  
在四个基准和四个 VLM 上，SMILE 相比 SOTA 基线平均任务得分提升 3.09 分，同时延迟降低 5 倍。</td></tr>
<tr><td>2026-10-09</td><td>Efficient Confidence-Aware Densification for 3DGS<br><a href='http://arxiv.org/pdf/2610.13541'>论文</a></td><td>本文针对3DGS-MCMC按透明度采样致新图元偏向前景、背景欠重建的问题，提出面向固定预算MCMC的置信度感知误差驱动致密化。它在保持固定预算与渐进增长的前提下，用图像误差而非透明度决定图元放置。
◆ 以屏幕空间梯度大且学习置信度低的区域作为新图元采样位置，优先重建当前解释较差的区域。
◆ 将对渲染贡献最小的图元重定位到高误差区域，实现误差驱动而非透明度驱动的密度控制。
◆ 无需先验或单独初始化，在100k至2M各预算下平均PSNR、SSIM、LPIPS均超3DGS-MCMC；100k恢复ConeGS领先PSNR的0.84dB，500k起PSNR/SSIM在固定预算方法中领先。
◆ 可兼容先验：从ConeGS或EDGS初始化后，100k匹配ConeGS，500k三项指标最佳。</td></tr>
<tr><td>2026-10-05</td><td>WildMatch: Weakly Supervised Image Matcher Adaptation for Wildlife Re-Identification<br><a href='http://arxiv.org/pdf/2610.07384'>论文</a></td><td>WildMatch研究仅用身份标签对预训练关键点匹配器进行弱监督适配，以提升野生动物个体重识别。
现有方法要么依赖大量标注学习全局嵌入且忽略局部证据，要么直接使用领域无关的现成匹配器。
该方法利用预训练匹配器挖掘信息图像对，从身份一致性生成弱正负监督，并对比微调匹配网络，强化同身份对应、抑制异身份对应。
◆ 首次提出匹配器层面的身份监督适配框架，用于动物重识别。
◆ 无需关键点级或几何对应标注，仅凭监测数据中已有的身份标签实现数据高效领域特化。
◆ 在多个开源数据集上超越现成匹配器和先进局部-全局融合方法，并在开放世界协议下展现对未见个体的可迁移对应先验。</td></tr>
<tr><td>2026-10-02</td><td>Geometry-Aligned Semantic Matching for Cross-Modal Planar Image Registration<br><a href='http://arxiv.org/pdf/2610.03167'>论文</a> | <a href='https://warren-wzw.github.io/CDPM/'>代码</a></td><td>本文提出CDPM，用于跨模态平面图像配准，解决语义相似未必几何对应、CNN细节缺乏全局跨模态语义引导的问题。该方法先建立几何一致的语义表示，并在细粒度定位中保持其在对应估计中的主导作用。
◆ 采用几何一致的跨模态图像块对渐进适配DINOv3，使语义特征相似度更真实反映跨模态空间对应关系。
◆ 构建DINO为中心的跨模态特征金字塔，用多尺度DINO表示维持稳定跨模态对应，并用轻量CNN分支补充结构细节以精化局部定位。
在三个跨模态数据集上，CDPM均取得更优性能。在VIS-IR上，相比RoMa，其AUC@3/5/10/20分别提升7.36、13.40、13.75和10.42个百分点，mACE从5.83像素降至2.78像素。它还在所有指标上超过RoMa v2，并减少45.6%的FLOPs。</td></tr>
<tr><td>2026-09-30</td><td>EPIC: Epipolar-Consistent 360° Immersive Stereo Video Generation<br><a href='http://arxiv.org/pdf/2609.38689'>论文</a></td><td>论文针对现有视频扩散模型只面向传统显示、无法生成高分辨率立体360°内容，且时间与立体不一致在沉浸式头显中更突兀的问题，提出EPIC零样本生成管线。
其核心贡献是把现有视频扩散模型扩展为4K立体360°视频生成，用于按需沉浸式内容。
◆ 提出受双目视觉与深度感知启发的极线感知360°图像匹配度量，可捕捉跨视图的时序与立体几何不一致。
◆ 将该度量作为偏好信号，在有限训练数据下进行直接偏好优化，提升时空与立体一致性。
◆ 构建零样本管线，无需从头训练即可生成4K立体360°视频，并提供可扩展的沉浸式生成路径。
该工作实现了360°立体视频生成，并为混合现实等沉浸式显示带来多样化按需体验。</td></tr>
</tbody>
</table>
</div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-27</td><td>Generalizable Target-Less Joint Intrinsic-Extrinsic Camera-LiDAR Calibration using Deep Pixel-Point Correspondences<br><a href='http://arxiv.org/pdf/2610.37350'>论文</a></td><td>本文提出一种全自动、无目标的相机-LiDAR联合标定框架，可直接从原始图像和LiDAR扫描中联合估计相机内参、径向切向畸变及相机-LiDAR外参。
◆ 将基于深度像素点对应的无目标标定从校正图像扩展到原始相机，通过合成增强实现内参与畸变感知的对应学习。
◆ 在标定过程中迭代耦合对应预测与非线性优化，联合精化相机参数和相对传感器变换。
◆ 在未见KITTI配置和三个真实机器人平台上零样本验证，联合标定在恢复准确内参的同时提升了外参精度。
实验表明该方法优于依赖预标定相机的对应标定方法，并具备跨配置与跨平台的泛化能力。</td></tr>
<tr><td>2026-10-27</td><td>ActiveAlign: Aligning Egocentric Manipulation via Active Perception<br><a href='http://arxiv.org/pdf/2610.36859'>论文</a></td><td>本文针对Real2Sim2Real中被动感知导致real2sim差距的问题，提出基于主动感知的对齐框架ActiveAlign，通过机器人交互主动缩小仿真与现实差异。
◆ 提出ActiveAlign-Waving，利用主动手部运动与可微渲染完成手眼标定，减少未标定观测带来的对齐误差。
◆ 提出ActiveAlign-Touching，借助触觉反馈精化物体对齐，实现毫米级精度。
两个模块互补，共同提升real2sim对齐质量，使仿真表示更利于规划、可解释与安全执行。
作者还利用ActiveAlign-Waving为开源未标定机器人操作数据集整理仿真环境，并在真实Unitree G1上验证按按钮、移动滑块等毫米级细操作。
整体上，该工作将主动感知引入Real2Sim2Real对齐，为精细机器人操作提供可落地的校准与对齐方案。</td></tr>
<tr><td>2026-10-27</td><td>OmniGlimpse: Asymmetric Identity Memory for Online Multi-View Tracking<br><a href='http://arxiv.org/pdf/2610.36785'>论文</a></td><td>论文研究在线多视角身份维护OMIM：目标在每个视角仅初始化一次，之后不再提供身份标签，且不依赖离线场景训练或相机标定，需在遮挡和出视野情况下维持跨视角身份一致。为此提出OmniGlimpse非对称提议-验证框架，将自适应关联与稳定身份整合解耦。
◆表示层：用短期局部与跨视角证据在目标自适应空间生成关联提议，同时用冻结编码器定义的标准空间维护长期身份分布用于验证。
◆更新层：短期证据仅指导当前关联，自举后只有经过验证的观测才能更新持久记忆或驱动自适应。
◆在线机制：无需离线场景特定训练和标定，兼顾外观变化适应与可靠证据向稳定身份锚点的巩固。
实验在统一目标指定协议下，M3Track较最佳在线基线提升9.1 IDF1和22.1 CVIDF1，MvMHAT提升20.3和26.2，且IDF1超过离线训练参考并保持跨视角关联竞争力。</td></tr>
<tr><td>2026-10-26</td><td>Spectral fingerprint recognition of mobile signals via Rydberg atomic sensors<br><a href='http://arxiv.org/pdf/2610.35301'>论文</a></td><td>本文提出一种基于里德堡电磁诱导透明光谱与深度学习的量子移动信号分类框架，实现对真实无线信号的智能识别与频谱监测。
◆构建了涵盖蜂窝语音通话、Wi-Fi及三个商用手机品牌5G信号的频谱指纹数据集，并验证里德堡原子传感器用于移动信号分类的可行性。
◆采用卷积神经网络在该数据集上取得93.44%的初始基线分类准确率。
◆提出渐进微调策略持续适应由时间和环境变化引起的光谱漂移，使预训练模型在多样部署场景下保持稳健分类。
◆在蜂窝语音、Wi-Fi及其共存等动态无线条件下实现连续实时监测，60秒测量中获得87.67%的整体帧级识别准确率。
◆打通了里德堡原子射频传感与智能无线信号感知的路径，为实时频谱监测和量子射频感知应用提供新方案。</td></tr>
<tr><td>2026-10-22</td><td>GelSlim 5.0: Unifying Vision and Touch with a Single Fingertip Camera<br><a href='http://arxiv.org/pdf/2610.31334'>论文</a></td><td>GelSlim 5.0提出一种仅用单个固定相机的指尖传感器，通过切换照明，在同一视点依次获取透过膜的视觉图像与接触敏感触觉图像，从而避免多相机外参标定。
◆ 用单一相机与连续UV响应接触层统一视觉和触觉观测，实现共享视点下的序列采集。
◆ 提出VisTacFusion多模态Transformer，为平面物体位姿和接触几何设置独立预测路径。
◆ 设计非对称瓶颈融合，在引入视觉上下文的同时保留触觉空间特征，以估计深度和表面法线。
◆ 引入模态丢弃机制，使模型支持成对输入或任一单模态推理。
在12个已知物体的真实验证中，成对输入相对纯触觉将深度MSE、角度误差和平移L1分别降低61.2%、72.3%、61.3%；相对纯视觉分别降低93.7%、6.1%、8.6%。</td></tr>
<tr><td>2026-10-22</td><td>WildDepth-v2: A Synchronized RGB--LiDAR--Radar Dataset and Benchmark for Metric Depth, Motion, and Tracking of Wildlife<br><a href='http://arxiv.org/pdf/2610.31123'>论文</a></td><td>本文提出WildDepth-v2，在同步RGB-LiDAR野生动物数据集基础上扩展成像雷达、标准化基准及度量运动与跟踪能力，为动物距离、运动和生态监测提供带度量真值的数据与评测框架。
◆ 新增37个RGB-LiDAR-4D雷达序列共19716帧，提供逐点多普勒速度和实测误差预算，据称是首个成像雷达野生动物记录。
◆ 构建冻结且校验的隐藏测试集，分别面向纯RGB距离估计与RGB加稀疏LiDAR深度补全，并在动物像素和背景像素上分开评估。
◆ 利用LiDAR、雷达或单目深度将2D跟踪提升为度量3D轨迹，形成跨431条轨迹的运动与跟踪基准。
实验表明，对象级雷达校准可在推理不用LiDAR时优于场景级LiDAR校准（AbsRel 0.120对0.198），动物级LiDAR仍最优（0.052）；每轨雷达缩放将3D位置误差从2.20米降至0.58米，并把检测函数偏差从-13%降至-2%，雷达多普勒迁移到LiDAR还使运动掩码更密、动物累积误差降低37%并估计径向速度（r=0.60，约低估50%）。</td></tr>
<tr><td>2026-10-22</td><td>SpatialScout: Can VLM Agents Actively Explore and Map 3D Scenes?<br><a href='http://arxiv.org/pdf/2610.26659'>论文</a> | <a href='https://github.com/JesseZZZZZ/SpatialScout'>代码</a></td><td>本文提出SpatialScout，一个评估VLM智能体主动进行物体级3D建图的基准。该基准包含80个室内场景和3140个目标物体，要求智能体在有限交互预算下控制相机探索并估计共享坐标系中的物体中心。评估采用惩罚漏检的物体尺度重叠分数，同时衡量定位精度与目标覆盖率；实验显示最强模型Claude Opus 5.5平均重叠分数仅41.71%，IoU超0.5和0.9的目标分别占47.23%和3.25%。
◆ 构建覆盖多场景多目标、带交互预算约束的主动物体级3D建图量化测试平台。
◆ 设计联合定位精度与目标覆盖率的物体尺度重叠评估，惩罚漏检并区分粗布局与精确度量地图。
◆ 揭示前沿VLM在视角选择、跨视图关联、几何估计和地图修正上的显著能力缺口。</td></tr>
<tr><td>2026-10-21</td><td>A2I-Calib++: A Kinematics-Driven Anti-noise Active Calibration Framework for Whole-Body Multi-IMU Systems on Legged Robots<br><a href='http://arxiv.org/pdf/2610.29438'>论文</a></td><td>针对腿足机器人全身多IMU标定中运动激励不足及足滑、冲击和振动噪声问题，论文提出运动学驱动的抗噪主动标定框架A2I-Calib++，可在无人工标靶和目标IMU复杂调参下估计时间偏移、外参旋转平移与惯性偏置。
◆ 设计受噪声各向同性启发的轨迹，并给出有限时域条件性命题，以生成足量激励并降低噪声敏感性。
◆ 提出约束感知对抗运动先验控制器，将抗噪激励与滚动接触奖励结合，实现接触感知执行。
◆ 构建接触约束虚拟IMU，融合预标定小腿IMU与关节运动学并基于滚动接触模型生成标定参考。
仿真与真实四足平台实验表明，该方法显著降低噪声敏感性和标定误差，实现可重复的实机标定并提升腿足机器人本体感知里程计精度。</td></tr>
<tr><td>2026-10-20</td><td>VeriCalib: Verifiable Target-Based LiDAR-Camera Calibration<br><a href='http://arxiv.org/pdf/2610.28791'>论文</a></td><td>本文提出VeriCalib，将基于靶标的外参标定建模为可验证估计问题，并输出可指导接受、重提取、重采集或补采的标定状态，而非仅依赖同一批观测上的残差RMSE。
◆ 揭示两级外参补偿机制：残差级由外参补偿观测误差的刚体部分，参数级旋转与平移相互补偿，说明拟合残差无法反映观测与模型不一致及各方向可靠性。
◆ 构建结构化协方差，联合传播相机与LiDAR靶标特征不确定性及已知几何先验，并从残差估计方差分量尺度。
◆ 基于该协方差解耦旋转与平移，量化各方向精度并引导数据采集至最弱方向。
◆ 提出视内与跨视一致性检查，分别检验内部残差和观测间刚性差异，阈值在未知噪声下保持显著性水平。
◆ 将最小可检测偏差扩展到外参，给出各方向最小可检测故障边界，并据上述准则形成接受或补采的标定状态。</td></tr>
<tr><td>2026-10-20</td><td>Can a Display Be Used for Rapid LiDAR-Camera Extrinsic Calibration?<br><a href='http://arxiv.org/pdf/2610.28571'>论文</a> | <a href='https://github.com/ZuhaoZou2026/ScreenCalib'>代码</a></td><td>ScreenCalib提出用普通可编程显示屏完成LiDAR-相机外参标定，相机观测屏幕显示的AprilTag，LiDAR测量屏幕物理表面与边界，从而减少专用标定板准备并实现间接跨模态关联。针对显示几何关联歧义和室内杂乱干扰，方法采用标签引导的显示屏提取、几何假设生成与优化，并利用周围场景边缘消歧。实验覆盖仿真及三种传感器平台、机械与非重复LiDAR、干净与杂乱环境，平移精度优于竞争标定板方法，联合多姿态优化进一步降低旋转和平移误差并改善渲染地图对齐。创新点：
◆以普通显示屏作为可编程标定物，兼顾已知视觉标记与可控几何，减少专用靶标准备。
◆通过标签引导提取、几何假设生成优化及场景边缘消歧，稳健解决LiDAR与相机间的间接跨模态关联歧义。
◆提出单姿态静态标定与多姿态共识联合优化，后者无需连续运动或轨迹估计，并降低标签尺寸测量误差敏感性。</td></tr>
<tr><td>2026-10-20</td><td>SynCalib: Breaking Dataset Shortcuts in LiDAR-Camera Calibration via Extrinsic-Controllable Synthesis<br><a href='http://arxiv.org/pdf/2610.27547'>论文</a></td><td>论文针对现有学习式LiDAR-Camera标定方法因训练数据外参多样性不足而过度拟合固定标称外参、产生数据集捷径并导致泛化差的问题，提出SynCalib数据生成框架。该框架利用带深度真值的全向图像数据集，在严格外参约束下合成多模态标定数据，以增强训练数据的外参多样性。
◆提出外参可控的多模态标定数据合成框架，从数据源头打破固定标称外参导致的数据集捷径。
◆在严格外参约束下生成LiDAR-Camera标定样本，提升外参多样性，使网络不再依赖单一标定配置。
◆验证仅用合成数据训练的模型可在多种真实相机-LiDAR配置上零样本迁移，显著提升泛化性与鲁棒性。
实验表明该数据能增强典型学习式标定网络的泛化与鲁棒性，作者还将公开数据生成代码、预训练模型和在线基准数据集。</td></tr>
<tr><td>2026-10-20</td><td>Visual-Inertial Odometry for Ground Robots with Dynamic Camera-IMU Extrinsic Calibration<br><a href='http://arxiv.org/pdf/2610.25397'>论文</a></td><td>本文针对视觉惯性里程计中传感器刚性安装假设限制适应性、难以应对结构运动的问题，研究时变相机-IMU外参标定，以提升地面机器人在动态结构运动场景下的定位适应性。
◆ 提出基于Denavit-Hartenberg约定并融合机器人运动模型的动态相机-IMU外参标定方法，将外参随关节运动变化纳入建模。
◆ 设计两步初始化策略高效估计初始关节角，为后续外参优化提供可靠起点，并支持时变相机-IMU外参的在线估计。
仿真实验表明，该框架能有效适应相机-IMU外参变化，同时保持具有竞争力的定位精度。
该工作的核心创新在于将机器人运动学引入动态外参标定，并通过初始化与在线优化结合实现时变外参的实用估计。</td></tr>
<tr><td>2026-10-20</td><td>HexaShell: A Thin Harness for Exploring the Limits of VLM Agents as Robot Coding Agents<br><a href='http://arxiv.org/pdf/2610.23479'>论文</a> | <a href='https://github.com/HexaFuture/HexaShell'>代码</a></td><td>HexaShell提出一种面向机器人操作的“薄封装”编码智能体框架，让VLM智能体通过单一命令行把代码命令转为机器人动作，框架自身不做决策。
◆ 它采用行动智能体与优化智能体协作：行动智能体执行每个回合，失败后优化智能体读取含命令、图像和消息的完整记录，定位原因并编写或修复带测试的小工具。
◆ 学到的经验以代码形式沉淀，无需演示或训练，运行工具只依赖真实机器人也可获得的RGB图像、相机标定和机械臂状态。
◆ 工具通过多视角三角定位找物体，仿真与硬件的输入一致，因此迁移到不同机械臂只需少量适配。
◆ 在RoboDojo官方隐藏种子评测的42个任务各50回合中，HexaShell取得46.9%成功率和53.2进度分，达到官方榜单SOTA。
实验表明其上限受接触操作限制而非推理：记忆任务达81.0%，精度任务仅32.0%，并开源已演化工具。</td></tr>
<tr><td>2026-10-14</td><td>FOMI: A Force-Feedback Manipulation Interface for Teaching Contact-Rich Manipulation<br><a href='http://arxiv.org/pdf/2610.19839'>论文</a></td><td>本文提出FOMI，一种面向接触丰富操作教学的力反馈操作接口，旨在解决现有手持界面力反馈不足、演示采集困难的问题。其核心贡献是设计剪刀形机构，通过执行连杆将物体交互力直接传递到操作者双手，无需力传感器即可实现直觉力反馈，支持采集中的实时动作调整。
◆ 采用无传感器力反馈机械结构，将交互力直接传给人手，增强接触丰富演示采集的直觉性与可调性。
◆ 构建集成传感器标定、数据采集与同步的无机器人采集系统，并支持位姿与夹爪映射下的遥操作。
在四个接触丰富任务上，FOMI在无机器人采集和遥操作中分别比最佳基线提升约29%和18%的采集效率。基于FOMI采集的演示可训练策略，在挑战性接触丰富操作任务中取得高成功率。</td></tr>
<tr><td>2026-10-10</td><td>HumanPhys: A Human-Centric Physical-World Perception Benchmark for Real-World Visual Reasoning<br><a href='http://arxiv.org/pdf/2610.14679'>论文</a></td><td>本文提出HumanPhys，一个以人为中心的真实世界物理感知基准及同管线生成的训练语料。它系统探测空间状态、运动学、眨眼事件、形变、光照和相机姿态六个维度，问题涵盖深度、人际距离、注视角、位移、速度、朝向步态轨迹、眨眼次数、接触形变强度及光照与相机自运动。所有标签均由传感器标定、源元数据或渲染器状态程序化生成，而非人工标注或基于基准帧的估计器。
◆ 首次构建联合监督上述六类人类中心物理量的MLLM基准与训练语料，填补现有基准仅部分覆盖的空白。
◆ 通过直接元数据或渲染器状态获得物理接地标签，避免标注偏差并支持可扩展生成。
◆ 全面评测开源与闭源MLLM，发现六个能力维度仍具挑战且仅部分可分离，为多模态物理感知研究提供新基准。</td></tr>
</tbody>
</table>
</div>

<h2 id='robot-vlm'>Robot VLM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-29</td><td>Surrogate Uncertainty for Black-box Visual Grounding<br><a href='http://arxiv.org/pdf/2610.39798'>论文</a></td><td>论文针对机器人使用黑盒视觉语言模型进行视觉grounding时的不确定性问题，指出现有方法从VLM自身导出不确定性会继承其参数与结构偏差。◆将VLM预测视为观测，给出形式化贝叶斯定义，并用外部代理贝叶斯模型在留出校准集的局部邻域量化每个查询的不确定性，分解为偶然与认知两部分。◆设计跨输入模态的分层检索，构建紧凑的联合空间邻域，缓解维度灾难。◆将该估计器与共形预测或基于模型的规划结合，支持机器人通过语言或物理动作进行主动视觉grounding。◆在多个基准和先进VLM上持续改善校准与任务性能，并在真实Fetch机器人开放世界指令中实现自信行动与信息收集的原则性权衡，显著提升鲁棒性。</td></tr>
<tr><td>2026-10-29</td><td>From Reasoning to Action: Consequence-Grounded Alignment for Vision-Language-Action Models<br><a href='http://arxiv.org/pdf/2610.39543'>论文</a> | <a href='https://onlyxingxingzyx.github.io/CoRAct/'>代码</a></td><td>论文指出，现有VLA模型虽用ECoT引导动作生成，但动作仅以推理为条件，未显式优化与推理意图及预期后果对齐。为此提出CoRAct，一个在动作噪声空间通过奖励引导优化实现推理与动作显式对齐的后果锚定框架。
◆将ECoT中的movement和waypoints分别建模为表示意图运动与预期空间后果的可验证信号。
◆设计统一Mixture-of-Transformers联合建模ECoT推理、动作生成及动作条件未来预测。
◆对采样噪声生成的候选动作，依据运动一致性和预测结果与路点一致性计算对齐奖励，并用组相对优化初始噪声分布以引导动作生成。
在RoboCasa、VLABench和真实操作任务上，CoRAct提升任务成功率、泛化与推理执行对齐，并能将外部ECoT落地为可执行行为以实现新场景零样本适应。</td></tr>
<tr><td>2026-10-29</td><td>PRIME W0: Physical Priors from World Models for Embodied Manipulation<br><a href='http://arxiv.org/pdf/2610.39528'>论文</a></td><td>PRIME W0提出分层条件流匹配框架，解决现有VLA仅依赖当前观测、丢弃长时程时序上下文和VLM层级结构的问题。其核心是把预训练VLM多层表示、世界模型子目标预测和历史帧语义统一注入动作生成，并通过四阶段训练完成具身操作策略学习。
◆ 将预训练VLM的逐层KV注入自适应MoE动作专家，实现层级视觉语言表征到动作专家的条件传递。
◆ 采用异步世界模型子目标图像预测和DINOv2历史帧语义桥进行动力学感知条件建模，引入长时程时序信息。
◆ 提出动作动态流形流匹配与协方差结构噪声，使生成动作尊重机器人运动学耦合。
◆ 设计VLM预训练、DAT/NTP视觉运动预训练、DiT流匹配解码器组装与WM注入、端到端SFT四阶段训练，并在LIBERO和真实机器人基准取得SOTA，消融验证各组件有效性。</td></tr>
<tr><td>2026-10-29</td><td>Decoding Geometry, Not Tokens: Efficient VLMs for Robot Affordance and Trajectory Prediction<br><a href='http://arxiv.org/pdf/2610.39416'>论文</a></td><td>本文指出视觉语言模型将抓取与移动预测当作坐标token自回归生成，忽视空间结构、截断连续精度且误差逐token累积，核心贡献是改用几何方式直接预测。  
◆ 发现0.5-2B紧凑现成VLM的中间隐状态已蕴含丰富空间信息，并定位自回归解码是轨迹预测主要瓶颈，affordance还受特征深度和解码器结构影响。  
◆ 提出附着于冻结骨干的轻量几何兼容预测头，读取中间层特征，以任务指令条件化学习查询，并通过视觉token交叉注意力直接回归连续affordance框和轨迹路点。  
◆ 在ShareRobot-Bench和AGD20K上验证，2B模型较自回归基线轨迹误差降超60%、affordance mAP升85%，轨迹DFD为0.251，接近RoboBrain的0.191且吞吐高3.8倍。  
结果表明，无需修改骨干即可实现精度与效率更优的指令条件二维几何预测。</td></tr>
<tr><td>2026-10-28</td><td>Open-World Object Motion Anticipation via Meta-Learned Semantic Adaptation<br><a href='http://arxiv.org/pdf/2610.38993'>论文</a></td><td>论文面向机器人导航中的开放世界物体运动预测，提出仅用仿真训练即可在线适应新物体的方法，以判断物体何时开始运动并避免保守或冒险规划。核心方法是元学习图神经网络，融合物体的语义、几何与关系历史，从少量在线观察中推断新环境物体的运动倾向及物体间带动关系。
◆ 采用元学习实现无需微调的在线语义适应，使模型能预测训练时未见过的物体。
◆ 构建图神经网络编码语义、几何和关系历史，捕捉如人操作叉车移动托盘等对象间交互。
◆ 仅用仿真数据训练即可迁移到真实硬件，并在仿真和硬件中优于视觉语言模型和类频率基线。
实验表明该方法支持闭环导航中的无碰撞通行，性能接近最快但易碰撞规划器，且规划时间差在四秒以内。</td></tr>
<tr><td>2026-10-28</td><td>SaiVLA-JEPA: Evaluating Future Latent Prediction in JEPA-Conditioned VLA Control<br><a href='http://arxiv.org/pdf/2610.38508'>论文</a></td><td>论文提出SaiVLA-JEPA，将冻结V-JEPA视觉表示、视觉语言模型与扩散Transformer动作专家结合，构建JEPA条件化的VLA流策略。
◆ 在闭环控制中系统比较无JEPA特征、当前JEPA条件与额外未来表示监督三种方案。
◆ 设计训练时轻量辅助头预测未来潜在表示，推理时移除且不改变动作采样器。
在10030对LIBERO-Plus episodes上，当前JEPA条件约82.5%成功率，高于无JEPA的71.6%，但未来监督在评估训练预算下无显著总体增益。
◆ 提出TCA潜在上下文适配与TPA参数适配变体，发现参数适配无一致优势，context-retry增益是更大尝试预算下的系统级结果。
论文强调应通过成对闭环rollout而非仅潜在损失来评估潜在预测目标。</td></tr>
<tr><td>2026-10-27</td><td>Perceiving and Predicting Dynamic Sports: Spatiotemporal Intelligence in Vision Models for Egocentric Tennis Video<br><a href='http://arxiv.org/pdf/2610.37619'>论文</a></td><td>论文面向移动自视角机器人，构建带标注的自视角网球视频数据集，系统评估基础视觉模型在动态体育场景中的时空感知与预测能力。
◆ 数据集同步五路第三人称视频、全局位置、触球时刻和击球类型，为自视角时空推理提供多模态真值。
◆ 设计并评测七项自视角预测任务，涵盖2D/3D球员与球定位、未来轨迹、正反手击球预判、下次触球时间和触球点3D位置。
◆ 提出条件扩散模型，将视觉编码器预测转化为实时全身网球动作，并能随预测更新自适应调整。
实验表明最佳模型可实现厘米至米级定位与轨迹误差、约0.14秒触球时间误差。
结果还揭示辅助深度显著改善3D球定位，而更长图像历史不提升球预测，说明模型更依赖场景上下文。</td></tr>
<tr><td>2026-10-27</td><td>Which Hand Was Late? Diagnosis for Robot Failure Recovery in Bimanual Tool Use<br><a href='http://arxiv.org/pdf/2610.37533'>论文</a></td><td>本文针对双臂工具使用中不同于单臂扰动的失败类型，构建可读取记录轨迹中真实失败原因的模拟诊断任务，系统评估各传感通道能揭示哪些失败信息。

◆ 提出涵盖工具滑脱、双手时序错位与多因并发失败的双臂工具使用诊断设定，并基于记录轨迹获得真实原因。
◆ 刻画传感可辨识性边界：工具手可读滑脱，双臂可判哪只手晚，单传感器仅知自身延迟及部分对侧延迟，工具手晚时弱推不可被动识别。
◆ 提出不可识别即升级的修复策略，在两次尝试内达到与已知真实原因相当的修复效果。
◆ 发现VLM内部状态几乎完美编码晚手，但其方向与答案读取方向无特殊接近，且是否报告受问题措辞影响。</td></tr>
<tr><td>2026-10-27</td><td>World Dreamer v5-lite: A Multi-Robot World Action Model with One Dreamer<br><a href='http://arxiv.org/pdf/2610.37518'>论文</a></td><td>World Dreamer v5-lite提出面向多机器人控制的统一世界动作模型，通过共享世界状态为各机器人预测独立动作序列。  
◆以预训练视频编码器的校准特征构建工作空间坐标下的共享世界状态，新增视角时空间尺寸保持固定。  
◆由视觉语言模型提供场景上下文并为每个机器人生成查询，查询读取共享状态并交换位姿感知信息，但动作流保持分离。  
◆采用掩蔽视角协同训练，在视觉分支中遮蔽部分相机视角而保留全部动作目标，促进利用其他机器人共享观测。  
模型使用超过1万小时、20种仿真机器人、RoboFactory和真实机器人轨迹预训练。  
在RoboFactory、四项真实机器人任务和RoboCasa365上分别达到74.0%、78.8%和58.08%，显著优于基线。</td></tr>
<tr><td>2026-10-27</td><td>Vision-Language-Action or World-Action? Just Action Models<br><a href='http://arxiv.org/pdf/2610.37219'>论文</a> | <a href='https://y0uroy.github.io/JAM'>代码</a></td><td>论文提出Just Action Model（JAM），将VLA与WAM之争拆解为骨干初始化、未来观测目标及推理是否保留相关机制三个可分离选择，并给出统一框架。
◆ 将预训练视觉骨干与动作专家结合，用动作损失和前瞻损失联合训练，且前瞻预测头训练后丢弃，训练和推理均不涉及视觉生成。
◆ 在固定策略架构内比较目标函数，并跨骨干家族验证前瞻训练配方，说明其不依赖特定初始化。
◆ JAM在LIBERO和LIBERO-Plus上优于匹配的FastWAM与ImageWAM，在RoboTwin上成功率相近或略高；相较FastWAM，三组成功率由97.0%/55.3%/91.2%提升至98.2%/64.5%/91.4%。
◆ 借助缓存前瞻目标，JAM将每样本每次更新的估计在线训练FLOPs较FastWAM降低73%。
结果表明，未来监督无需视觉生成或额外推理机制即可提升控制性能，且生成器初始化与视觉语言骨干均可获得强前瞻表现。</td></tr>
<tr><td>2026-10-27</td><td>Pretraining Knows What, Simulation Teaches How: Compositional Generalization in a Sim-Trained Robot Agent<br><a href='http://arxiv.org/pdf/2610.35817'>论文</a></td><td>论文提出ZAP，一种通过简单工具接口让现成小型视觉语言模型控制机器人的训练配方，将“理解任务要什么”与“学会机器人怎么动”解耦。它先用27B预训练模型引导世界理解与推理，再通过简单仿真任务上的监督微调和GRPO教会动作，训练中不使用真实机器人数据。真实任务成功率达96.7%，与GPT-6 Astra持平，显著高于MolmoAct2 VLA的33.3%，且快3倍、便宜17倍。
◆用预训练模型提供“What”理解、用仿真训练教授“How”控制，实现无需真实机器人数据的策略学习。
◆在简单仿真任务上完成小模型工具化控制训练，并展现出对新物体、新目标、新策略和新语言的组合泛化，如试管换孔、空中交接、井字棋画X和国际象棋。
◆策略可迁移到未见过的单臂Franka实体，在RoboLab-120上达55.9%，领先最强VLA/WAM基线4.9个百分点。</td></tr>
<tr><td>2026-10-26</td><td>E0.5: From Reconstructive to Future-Predictive 3D Foundations for Robotic World-Action Modeling<br><a href='http://arxiv.org/pdf/2610.36011'>论文</a></td><td>论文提出E0.5，一种直接构建在3D基础模型上的几何原生世界-动作模型，区别于以视频基础模型或VLM为主干、将3D几何作为辅助输入或预测目标的主流方案。
◆ 创新点一：采用3D基础模型作为主骨干，使3D几何成为世界建模与动作预测的原生表示。
◆ 创新点二：显式联合预测未来3D状态与动作，从而捕获超越纯动作建模或未来视频预测的几何世界动态。
在RoboTwin 2.0上，E0.5无需具身数据预训练即在干净和随机设置下分别取得89.90%和50.09%的成功率。
进一步在AgiBotWorld-Beta超过16万条机器人轨迹上预训练，并在预训练3D基础模型内联合学习动作与未来几何，使AgileX Piper和Zerith H1真实操作平均成功率分别提升约15和7个百分点。
结果证明几何原生基础模型能够获取机器人交互知识并迁移到物理操作，展现了VWA系列世界-动作模型的潜力。</td></tr>
<tr><td>2026-10-26</td><td>TrySee: Modular Perception-Enhanced VLM Grounding for Closed-Loop Robot Task Planning in Specialized Domains<br><a href='http://arxiv.org/pdf/2610.35687'>论文</a></td><td>本文提出TrySee，一种模块化闭环机器人任务规划管道，将通用VLM推理与领域专用感知及成熟机器人组件相结合，以应对专业领域中的图像解释与grounding难题。
◆ 构建本质反应式的循环规划管道，并引入领域专用模块化视觉预处理，为规划提供在线grounding。
◆ 设计动态预处理选择机制，提升管道在不同专业场景下的可扩展性。
◆ 系统无需VLM微调或端到端演示，可通过替换感知模块和运动规划组件实现自适应。
作者在5个差异显著领域的规划任务及真实机器人拆解任务上评估，现场测试表明该方法能在领域训练数据有限时，将VLM规划实用地集成到专业机器人系统中。</td></tr>
<tr><td>2026-10-26</td><td>From Language to Drives: A Multimodal Framework for Aligning Autonomous Robots with Human Purposes<br><a href='http://arxiv.org/pdf/2610.35629'>论文</a></td><td>本文提出一种面向开放式学习自主机器人的人机目的对齐多模态框架，利用大语言模型和视觉语言模型作为文化使能器，把自然语言表达的人类目的转化为机器人架构中的使命与驱力。系统分为语义对齐、使命生成和驱力建模三层，形成人类定义高层目的、机器人扩展为可执行使命、反馈维持意图对齐的双向交互闭环。仿真和实体机器人实验表明，该方法能生成有效使命与行为，支持交互场景中的人机对齐。
◆创新一：将LLM/VLM中的通用与文化知识引入机器人动机系统，实现从自然语言目的到使命和驱力的多模态转化。
◆创新二：设计语义对齐、使命生成、驱力建模三层架构及双向交互反馈循环，使高层人类意图可持续约束机器人行为。
◆创新三：在仿真与物理机器人上验证该对齐流程可产生有效使命和行为，提升开放式自主机器人与人类目的的一致性。</td></tr>
<tr><td>2026-10-26</td><td>Benchmarking Obstacle-Conditioned Safety in Household Robot Navigation<br><a href='http://arxiv.org/pdf/2610.34674'>论文</a></td><td>论文针对现有评测无法检验语义安全区分能否转化为连续运动的问题，提出面向家庭机器人导航的障碍物条件安全运动适应评测框架。  
◆提出OSMA-Bench基准，用空间匹配、仅障碍物类型不同的场景集，系统评测机器人能否按障碍物安全语义调节间隙与速度。  
◆提出语义敏感指数SSI，度量间隙以及随距离变化的速度与平滑性是否遵循障碍物的谨慎排序。  
◆对VLM和VLA策略的评测发现，二者即使有显式安全提示也不能稳定按障碍物安全属性调整运动，且能识别障碍安全相关性却未体现在运动参数或动作中。  
◆针对VLM策略，在障碍识别与导航程序生成之间加入显式参数推断步骤可改善安全运动适应。  
论文揭示语义到运动落地的缺口，强调需将语义谨慎转化为适当的安全运动。</td></tr>
</tbody>
</table>
</div>

<h2 id='robot-visual-semantic-recognition'>Robot Visual Semantic Recognition</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-29</td><td>LiDAR-SHIELD: A Fully Dockerized Adversarial Robustness Assessment Framework for LiDAR-Based 3D Perception Models<br><a href='http://arxiv.org/pdf/2610.39848'>论文</a> | <a href='https://github.com/alexandrosgk/LiDAR-shield'>代码</a></td><td>LiDAR-SHIELD是面向LiDAR 3D感知模型的全Docker化统一对抗鲁棒性评估框架，用于部署前系统压力测试。
◆ 它逆转传统流程，不把目标模型装入工具包，而通过/info、/forward、/gradient三个轻量HTTP端点暴露任意模型。
◆ 新模型或数据集接入仅需一个加载函数或适配器，显著降低模型特定集成与环境重建成本。
◆ 同一引擎-服务协议同时支持3D语义分割和3D目标检测，并可覆盖异构LiDAR骨干。
◆ 集成任务感知的先进攻击：分割用PGD和Square Attack，检测用点扰动、点移除、点注入和LiDAttack。
◆ 全Docker化统一碎片化攻击实现，提升可复现性与部署便利性，并系统暴露角落案例和漏洞，代码已开源。</td></tr>
<tr><td>2026-10-28</td><td>Safe and Fuel-Efficient Motion Planning for Lunar Propulsive Drones<br><a href='http://arxiv.org/pdf/2610.22225'>论文</a></td><td>本文提出面向月球推进无人机的自主运动规划框架，通过视觉引导最优控制在指定航点间完成安全且省燃料的跳跃。  
◆ 统一融合全局航点规划、抛物线跳跃最优控制与自主改向着陆，兼顾任务连续性与安全性。  
◆ 构建面向月面航拍图像的定制语义分割模型，用于识别障碍并评估候选着陆点安全性。  
◆ 提出快速计算可达地形的方法，以判断航点或着陆点是否安全可达。  
◆ 采用模型预测控制鲁棒跟踪跳跃轨迹，引导无人机飞向安全着陆点并降低跟踪误差。  
在高保真月球仿真中，该框架生成了安全、省燃料且可快速低误差跟踪的跳跃轨迹。</td></tr>
<tr><td>2026-10-22</td><td>RaSFNet: Ray-aligned and Scan-aware Fusion Network for LiDAR Semantic Segmentation<br><a href='http://arxiv.org/pdf/2610.31186'>论文</a></td><td>针对投影式LiDAR语义分割中多点聚合遮蔽几何差异、跨扫描区域空间关系建模不足及点-投影特征交互易混淆不同距离信息的问题，论文提出融合点云几何与LiDAR扫描特性的RaSFNet。
◆ 提出射线对齐几何分布编码RAGDE，在射线对齐坐标系中刻画每个视锥内的点分布，增强几何差异表达。
◆ 设计扫描拓扑感知Mamba模块STAM，按LiDAR方位角采样模式组织视锥特征并捕获跨扫描区域的长程依赖。
◆ 提出距离约束的点-视锥融合机制RCPFF，利用共享距离信息引导点特征与视锥特征交换并保持空间对应。
RaSFNet在SemanticKITTI和nuScenes验证集上分别取得70.2%和77.7%的mIoU，表现出有竞争力的分割性能。</td></tr>
<tr><td>2026-10-22</td><td>RangeNav: Task-Aligned LiDAR Range-Image Pretraining for Robot Navigation<br><a href='http://arxiv.org/pdf/2610.29845'>论文</a> | <a href='https://rangenav.github.io/'>代码</a></td><td>本文提出RangeNav，一个仅183k参数、完全基于合成数据预训练的紧凑型LiDAR距离图像编码器，用于提升机器人在密集人群和杂乱场景中的360度导航感知与策略学习效率。
◆ 采用各向异性卷积和循环填充，专门处理距离图像的极端长宽比与方位接缝问题。
◆ 设计导航对齐的预训练目标，联合距离重建、语义分割和鸟瞰图预测，再将编码器冻结用于强化学习策略。
◆ 以轻量化架构支持大规模并行仿真训练，并具备从仿真到真实机器人部署的零样本迁移能力。
仿真实验表明，加入语义和BEV监督较仅重建基线在程序生成训练环境和分布外真实测试环境中分别平均提升32.03和23.73个百分点。
在Unitree B2-W四足机器人上的零样本真实部署显示，其能在密集人群、低光和施工区中稳健导航，优于有限视场深度策略。</td></tr>
<tr><td>2026-10-21</td><td>AOV-GS: Active Open-Vocabulary Semantic Mapping with 3D Gaussian Splatting<br><a href='http://arxiv.org/pdf/2610.29374'>论文</a> | <a href='https://github.com/OptimusFaber/AOV-GS'>代码</a></td><td>AOV-GS面向人本环境机器人建图，提出无需人工掩码和闭集类别的主动开放词汇语义建图系统，兼顾几何导航与开放词汇查询。
◆ 利用冻结SAM实例分割与CLIP掩码嵌入计算语义新颖度，对几何候选视角重排序，使探索偏向语义信息丰富区域。
◆ 在粗探索和建图全程复用冻结SAM/CLIP提供实例掩码与语言对齐嵌入，避免监督语义分割和手工标注。
◆ 离线将轻量场景特定语言场直接拟合到采集的CLIP嵌入而非人工掩码，从而支持新视角开放词汇文本查询分割。
实验在Replica和Matterport3D上以相同SAM-CLIP感知栈比较，语言场mIoU分别提升1.3和1.8个百分点，CorrCLIP下Replica达35.6%，同时新视角PSNR相当且Replica深度L1改善。</td></tr>
<tr><td>2026-10-15</td><td>SpaceCache: Intermediate Feature Reuse for Efficient Semantic Segmentation on Point Cloud Streams<br><a href='http://arxiv.org/pdf/2610.21207'>论文</a></td><td>该论文面向点云流语义分割，发现连续帧高度重叠且点云Transformer中间特征对相同空间区域跨帧语义一致，尤其深层阶段。
◆ 提出免训练的SpaceCache，跨帧直接复用中间特征，无需重新训练或微调。
◆ 设计跳过式计算：已观察区域token跳过若干Transformer块并读取缓存特征，仅计算剩余token，再恢复完整token布局用于密集预测。
◆ 引入轻量缓存管理，通过限制条目年龄和淘汰低置信条目，保证复用特征可靠。
◆ 与token merging不同，其token选择代价极低，且缓存操作每个编码器阶段仅执行一次。
在nuScenes、Waymo、ScanNet及Utonia、LitePT-B上，SpaceCache最高达1.65倍加速，mIoU下降不足1点，并持续优于token merging方法。</td></tr>
<tr><td>2026-10-14</td><td>MultiFly: A Real-World Multimodal Aerial Dataset with Annotation-Efficient Label Transfer and Cross-Modal Semantic Consistency<br><a href='http://arxiv.org/pdf/2610.10359'>论文</a> | <a href='https://github.com/markus-42/multifly'>代码</a></td><td>本文提出MultiFly，一个面向低空无人机语义感知的真实世界多模态数据集，覆盖RGB、热红外、LiDAR和雷达。
◆ 数据集包含四个郊区场景的17,272个同步样本，提供15类逐帧语义标注以及标定和GNSS-RTK/IMU测量。
◆ 提出标注高效标签迁移方法，仅用115张人工标注RGB图像，通过共享几何表示将标签传播到全部四种模态。
◆ 该方法额外生成17,157张RGB、17,272张热红外、8.4亿LiDAR点和340万雷达点的语义标签，迁移标注平均一致率达89.93%，六种模态对平均语义一致性达90.94%。
◆ 建立四种模态的语义分割基准，揭示密集LiDAR与稀疏雷达数据需要不同架构行为。
综上，MultiFly是首个公开的真实低空航空多模态基准，为可扩展多模态空中感知提供基础。</td></tr>
<tr><td>2026-10-11</td><td>GNFormer: Gaussian Neural Field Transformer for Efficient Camera-based Occupancy Prediction<br><a href='http://arxiv.org/pdf/2610.15522'>论文</a></td><td>本文提出用于相机占据预测的GNFormer，核心是解决现有高斯方法基元利用率低与表达力不足的问题。
◆ 提出Gaussian Neural Field（GNF）三维表示，由高斯基元与神经网络联合参数化占据场，高斯基元定义空间支撑并提供特征，神经网络负责更表达力强的语义占据解码。
◆ 开发Gaussian Neural Field Transformer（GNFormer），一种简洁灵活的框架，可直接预测GNF并完成相机占据预测。
◆ 在Occ-ScanNet、SSCBench-KITTI-360和nuScenes-SurroundOcc上，GNFormer在对比单帧方法中取得最高IoU、mIoU和最快推理速度。
◆ 实验仅用256个室内和1024个室外高斯基元即可表示场景，显著少于先前高斯方法，并提升基元利用率。
本文主要贡献是提出GNF与GNFormer，实现高效、准确的相机占据预测。</td></tr>
<tr><td>2026-10-09</td><td>ForeAct3D: Policy-Grounded Future World Modeling for VLA Policies<br><a href='http://arxiv.org/pdf/2610.04607'>论文</a> | <a href='https://github.com/anthonytao80-crypto/ForeAct3D'>代码</a></td><td>ForeAct3D提出一种嵌入VLA策略、由策略动作接地的未来世界建模框架，训练时用未来语义3D预测和物理约束塑造动作生成表征，推理时无需未来预测。
◆ 用可学习几何查询从策略表征解码当前与未来的深度、语义分割和相机位姿，构建语义3D场景状态。
◆ 将未来查询条件于策略生成的动作块，使未来预测与实际计划执行的交互直接绑定。
◆ 引入背景静态性和实例级刚性的物理一致性约束，并把腕部相机位姿锚定到末端执行器运动学。
训练中这些目标共同塑造动作生成共享表征；无机器人预训练时LIBERO平均成功率98.3%，CALVIN平均任务长度3.73，真实世界成功率从6.7%升至37.8%，消融证明语义3D监督、物理一致性和动作条件均有效。</td></tr>
<tr><td>2026-10-02</td><td>CORNAV: Construction-Aware Reasoning for Robot Navigation on Active Worksites<br><a href='http://arxiv.org/pdf/2610.03622'>论文</a></td><td>施工行业长期面临劳动力短缺、低生产率和事故率高等问题，但现有语言导航只依赖语义场景理解，缺少建筑图纸、进度和安全约束等施工上下文，难以在活跃工地安全导航。为此，论文提出 CORNAV，一种仅用二维 CAD 图纸和项目进度、无需 BIM 的蓝图接地且日程感知导航框架。
◆ 将建筑蓝图与层级开放词汇三维场景图对齐，用对象查询接地提升永久建筑特征的定位与任务成功率。
◆ 把项目进度转化为随时间变化的导航约束，使机器人能响应动态施工状态。
◆ 融合 LLM 安全验证与 A* 规划，规划前拒绝危险请求，并强制排除区、优先避开高风险区。
在室内办公室和真实工地实验中，蓝图接地将任务成功率从 13.0% 提升至 72.2%，日程感知消除所有硬区违规，安全模块能正确拒绝因进度误标产生的危险请求。</td></tr>
<tr><td>2026-10-02</td><td>EmbPASS: Towards Cross-Embodiment Open Panoramic Segmentation<br><a href='http://arxiv.org/pdf/2610.03248'>论文</a> | <a href='https://github.com/guopj1/EmbPASS'>代码</a></td><td>论文针对异质具身平台在观察视点与空间布局上的差异所导致的跨具身观察偏移，提出跨具身开放全景分割这一新任务，以推动一致可靠的全景感知研究。
◆ 提出跨具身开放全景分割任务，系统定义并研究异质具身观测下的全景语义分割问题。
◆ 构建 EmbPASS 多平台全景语义分割基准，覆盖车辆、无人机、可穿戴设备与四足平台，并采用统一语义分类体系。
◆ 提出 EPONet 开放词汇全景语义分割网络，融合关系感知度量适配器 RAMA 与内容自适应语义迁移 CAST，增强异质观测下的空间建模和语义迁移。
实验表明 EPONet 在 EmbPASS 上取得 35.82% mIoU 的最佳平台均衡性能，超过最强基线 1.10%，并在现有全景分割基准上保持竞争力。
源码与 EmbPASS 基准将公开。</td></tr>
<tr><td>2026-10-01</td><td>Lang3DSeg: Annotation-Free Open-Vocabulary 3D Segmentation with Point Transformers<br><a href='http://arxiv.org/pdf/2610.00855'>论文</a></td><td>Lang3DSeg 提出一种无需人工标注的开放词汇室外3D LiDAR语义分割框架，首次以点Transformer为主干并完全从头训练。
◆ 首次把点Transformer用于室外稀疏、无界的LiDAR开放词汇分割，突破体素稀疏卷积和室内点Transformer的局限。
◆ 针对2D到3D标签投影的深度歧义，使用显式类别优先规则合成掩码，避免物体后方点被误赋标签。
◆ 在投影实例深度分布的第一个间隙处截断，直接修正投影误差，而非在配准序列中平均。
该方法在nuScenes验证集达到52.8% mIoU，在SemanticKITTI达到41.4%，为已发表无标注方法最高。
每次分割仅用单帧LiDAR，推理实时且无需运行视觉语言模型。</td></tr>
<tr><td>2026-09-30</td><td>NaviScale: Generating Large-Scale Semantic Map Datasets for Object Navigation<br><a href='http://arxiv.org/pdf/2609.27218'>论文</a></td><td>NaviScale提出面向语义地图ObjectNav的大规模数据生成框架，预测器仅需部分与完整语义地图配对训练，无需为每个样本重建完整3D环境。
◆ 组合真实住宅平面图与MP3D、HM3DSem的房间级语义和障碍地图，低成本生成大规模多样化语义地图数据。
◆ 房间间缩放改变平面图结构，提升平面图级布局多样性。
◆ 房间内缩放按房间类别匹配不同房间地图，填充同一固定平面图以增加房间组合多样性。
◆ VisRC通过射线投射将组合地图转为部分观测，并显式考虑视场、感知范围和遮挡。
生成192,000张语义地图、24,000个平面图和12,794处房产；在HM3D达64.3% SR/34.8% SPL，MP3D达43.1% SR/16.8% SPL，且不改变预测架构，并验证地图质量、语义分割误差和实机部署。</td></tr>
<tr><td>2026-09-29</td><td>HIGS: Hierarchical Implicit Grids for Joint Geometric and Semantic Scene Understanding<br><a href='http://arxiv.org/pdf/2609.38620'>论文</a></td><td>本文提出HIGS，一种面向联合几何与语义场景理解的分层隐式网格表示，核心是用多分辨率子图和统一查询解码机制同时支持几何与语义特征。
◆ 采用多分辨率重叠子图分解与分层局部优化，使大规模场景的隐式表示具备可扩展计算能力。
◆ 设计统一查询与解码流程，将可学习地图特征转换为几何和语义输出，训练与推理机制一致。
◆ 引入特征编码器预测初始分层网格特征，显著减少子图特征从头优化所需时间。
◆ 在隐式特征空间内对齐并融合子图，避免解码最终输出，从而加速估计漂移校正。
◆ 将几何特征与视觉语言潜特征嵌入地图，支持SDF构建和开放词汇物体定位，提升计算内存效率并保持估计精度。</td></tr>
<tr><td>2026-09-29</td><td>When to Adapt: Multi-Signal Domain Shift Detection for Efficient Training-Free Adaptation in Open-Vocabulary Segmentation<br><a href='http://arxiv.org/pdf/2609.37602'>论文</a></td><td>论文针对真实机器人长期部署中开放词汇语义分割的域偏移问题，研究何时触发免训练持续测试时适应。现有方法多逐帧适应，在资源受限硬件上不实用。为此，作者提出多信号域偏移检测方法，通过跨连续帧的时间一致性监控并融合视觉变化、适配器不匹配和语义漂移，仅必要时触发适应。
◆ 提出用于免训练持续测试时适应的多信号域偏移检测框架，将适应触发从逐帧改为按需。
◆ 创新性联合视觉变化、适配器不匹配和语义漂移三类互补信号，提升触发判断可靠性。
◆ 在室内外基准及真实机器人数据上验证，保持分割精度同时大幅减少适应次数，使长期部署更可行。</td></tr>
</tbody>
</table>
</div>

<h2 id='robot-vpr'>Robot VPR</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-10-26</td><td>VPR-Space: A Benchmark for Visual Place Recognition in Space Analog Domains<br><a href='http://arxiv.org/pdf/2610.35642'>论文</a> | <a href='https://github.com/rfechner/VPR-Space}$'>代码</a></td><td>论文提出VPR-Space，一个面向地外表面及太空模拟域的视觉地点识别新基准，用于评估VPR在特征贫乏环境中的能力。
◆收集了16个基于太空模拟域现有数据的VPR数据库-查询数据集，覆盖环境、视角变化和光照条件等多类挑战。
◆提出一种面向下游SLAM价值的VPR真值生成方法，利用先进相对位姿估计器集成性能构建GT矩阵，替代固定位姿阈值判定。
◆系统评估了9种先进VPR方法，结果显示现有方法仍有较大提升空间，并为未来研究指明方向。
该工作还公开了数据集预发布版本，为月球或火星等极端环境下的VPR与SLAM研究提供评测基础。</td></tr>
<tr><td>2026-10-12</td><td>Removing the Compute Bottleneck for Event-based Visual Place Recognition with Spiking Neural Networks<br><a href='http://arxiv.org/pdf/2610.16022'>论文</a></td><td>本文针对事件视觉地点识别下游仍采用稠密类帧计算、丢失低延迟优势的问题，提出在普通CPU上数十微秒内完成查询的稀疏脉冲神经网络方案。
◆ 采用加性STDP训练两层SNN，使权重矩阵形成强双峰分布，便于激进幅度剪枝。
◆ 推理时仅读取查询活跃像素对应的剪枝权重，避免稠密计算和无效访存。
◆ 由于存活权重幅度接近均匀，神经元打分简化为匹配突触的整数计数，而非加权求和，从而降低单查询延迟。
◆ 该稀疏计算规模小到可常驻CPU片上高速缓存，支持低延迟执行。
在三个事件VPR基准上，该方法召回超过LENS，延迟降低5.5至6.2倍至数十微秒，并匹配稠密版本和SAD基线召回，同时读取权重少10倍，表明事件输入与学习权重的稀疏性已可用于传统处理器低延迟推理。</td></tr>
<tr><td>2026-10-07</td><td>Fast and Robust Teach-and-Repeat Navigation Using MixVPR Visual Place Recognition*<br><a href='http://arxiv.org/pdf/2610.09631'>论文</a></td><td>本文针对现有深度学习 teach-and-repeat 导航计算量大、实际部署受限的问题，提出了基于 MixVPR 视觉地点识别的新型导航系统。该系统面向长期移动机器人导航，可在非结构化和动态环境中完成定位与重复路径跟踪。  
◆ 将现代视觉地点识别方法 MixVPR 引入 teach-and-repeat 框架，实现快速且鲁棒的视觉定位。  
◆ 在保持与先进系统相当的导航精度和鲁棒性同时，显著降低计算与硬件需求。  
◆ 通过真实室内外环境测试验证了系统的通用性，使其适合多种机器人平台和实际应用。  
实验表明，该系统兼具高精度、强鲁棒性和低部署门槛，为实用化 teach-and-repeat 导航提供了高效方案。</td></tr>
<tr><td>2026-09-28</td><td>MarsLab: A Martian Rover Simulator for Planetary Rover Autonomous Navigation<br><a href='http://arxiv.org/pdf/2609.34702'>论文</a> | <a href='https://kimhoyun-robotair.github.io/MarsLab/'>代码</a></td><td>MarsLab是面向火星车自主导航的开源ROS2原生模拟器，用于在部署前研究非结构化地形、光照变化、大气尘埃和通信受限等条件。  
◆ 它将HiRISE衍生地形与程序化地形结合，并支持岩石、陨石坑、太阳光照和大气尘埃等参数化定制。  
◆ 它在NVIDIA Isaac Sim中运行毅力号级火星车，并通过标准ROS2话题发布RGB、深度、RGB-D点云、LiDAR、IMU、轮式里程计和GT位姿。  
◆ 它提供统一SLAM基准，覆盖不同传感模态、尘埃水平、场景几何和路线长度。  
◆ 它提供VPR基准，在重复火星基地遍历中考察光照与尘埃变化下的地点识别。  
最后，它用共享GT轨迹在同一模拟器中比较轨迹级估计与图像级地点识别，并开源项目页面。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5325</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4824</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2484</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1663</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1627</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1535</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1372</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1319</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1123</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>1095</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>953</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>816</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>785</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>748</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>747</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>735</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>698</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>673</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>636</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>627</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>624</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>591</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>572</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>545</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>514</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>479</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>466</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>374</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>350</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>281</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>275</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>260</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>243</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>232</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>229</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>223</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>221</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>213</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>151</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>147</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>124</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2888</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1679</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1368</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1098</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1062</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>886</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>714</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>673</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>670</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>623</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>612</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>579</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>576</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>572</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>554</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>521</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>521</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>464</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>457</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>456</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>341</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>334</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>310</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>305</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>290</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>278</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>258</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>246</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>224</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>208</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>203</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>187</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>177</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>171</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>169</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>160</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>156</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>142</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>139</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/data-driven-dynamics'>data-driven-dynamics</a></td><td>134</td><td>Data Driven Dynamics Modeling for Aerial Vehicles</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>132</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
<tr><td><a href='https://github.com/ethz-asl/phaser'>phaser</a></td><td>132</td><td>A robust pointcloud registration pipeline based on</td></tr>
<tr><td><a href='https://github.com/ethz-asl/ssc_exploration'>ssc_exploration</a></td><td>112</td><td>Incremental 3D Scene Completion for Safe and Effic</td></tr>
<tr><td><a href='https://github.com/ethz-asl/active_grasp'>active_grasp</a></td><td>111</td><td>Closed-loop next-best view planning for grasp dete</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waypoint_navigator'>waypoint_navigator</a></td><td>108</td><td>Stand-alone waypoint navigator</td></tr>
<tr><td><a href='https://github.com/ethz-asl/reinmav-gym'>reinmav-gym</a></td><td>106</td><td>Reinforcement Learning framework for MAVs using th</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waverider'>waverider</a></td><td>106</td><td>RMPs on multi-resolution occupancy maps for effici</td></tr>
<tr><td><a href='https://github.com/ethz-asl/navrep'>navrep</a></td><td>106</td><td>navrep</td></tr>
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>104</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/eth_supermegabot'>eth_supermegabot</a></td><td>102</td><td>Instructions for ETH center for robotics summer sc</td></tr>
<tr><td><a href='https://github.com/ethz-asl/3d_vsg'>3d_vsg</a></td><td>102</td><td>3D可变场景图，用于长期语义场景变化预测。</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.10.31
