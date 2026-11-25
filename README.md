# 计算机视觉领域最新论文 (2026.11.25)

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
<tr><td>2026-11-24</td><td>SpatialArena: Where Do Geometric Foundation Models Stand?<br><a href='http://arxiv.org/pdf/2611.32816'>论文</a></td><td>该论文指出当前几何基础模型评测因采样、分辨率和测试划分不一致而不可比，且对齐方式脆弱、场景覆盖有限。作者提出SpatialArena，用统一指标和规则、稳健且确定性的对齐来评测几何模型，覆盖从单目深度到SLAM的五类任务、23个公开数据集共418,929张图像，并加入自有精确位姿与深度采集数据。评测52个模型后发现，单图深度在公开基准上接近饱和，但在大规模非受控场景中仍未饱和，进展正转向跨帧与跨视图一致性，前馈3D/4D模型可匹配或超越单目专家并超过视频深度模型。
◆ 建立统一评测协议与稳健确定性对齐，消除不可比性和对齐敏感偏差。
◆ 构建覆盖多任务、多场景的大规模基准，并补充自有精确位姿与深度数据。
◆ 揭示一致性驱动的新趋势，并将公开基准、工具箱和排行榜。</td></tr>
<tr><td>2026-11-24</td><td>Seeing to Drive on a Single Board: Attention-Free Depth for Onboard Robot Navigation<br><a href='http://arxiv.org/pdf/2611.32718'>论文</a> | <a href='https://github.com/itaim18/DANIEL'>代码</a></td><td>论文提出一套可在Raspberry Pi 5加Hailo-8L单板上运行的实时深度感知与导航方案，核心是以蒸馏替代量化，把Depth Anything V2-Large转成无注意力的ResNet-34 U-Net学生模型。
◆ 以24.5M参数的无注意力学生网络实现整型推理，在Hailo-8L上达27.1 FPS，int8输出与浮点孪生高度一致（Pearson 0.99993）。
◆ 定量揭示ViT深度模型量化失效机理：449个token时91%的softmax权重低于一个int8步长，却承载17%至33%的注意力质量。
◆ 设计仅需相机高度的地面交点障碍测距方法，使建图、混合A*规划与SLAM可在Pi自身CPU上运行。
◆ 在仿真院落、真实户外驾驶与Gaussian-splat硬件在环中验证：仿真AbsRel 0.269优于0.354至0.530，真实户外与厂商Depth Anything V2-Small无可分辨差异且更快（27.1对21.6 FPS）。
最终导航栈在真实院落重构中10个场景无接触到目标7.9±1.1个，真实Pi与Hailo-8L闭环为8.2±0.4个，并开源代码、模型与数据。</td></tr>
<tr><td>2026-11-24</td><td>AirLeg: A Robust and Accurate Self-Supervised Visual-Inertial-Leg SLAM System<br><a href='http://arxiv.org/pdf/2611.32523'>论文</a></td><td>AirLeg提出一种面向腿式机器人的自监督视觉-惯性-腿SLAM系统，使视觉与腿本体感知在训练和部署中相互促进。
◆ 设计仿真预训练加imperative learning的无真值适配框架，用多传感器光束法平差让腿里程计细化视觉地图，再由地图反向监督腿里程计网络。
◆ 部署阶段利用融合估计在线自适应腿里程计网络，形成从训练到部署的持续自监督闭环。
◆ 提出双窗口估计器融合视觉、IMU和腿里程计，并通过变形感知约束把受载足与视觉重建地形关联。
◆ 采用方差分量估计对多源约束动态加权，以同时提升定位与网络监督质量。
在GrandTour全部17个序列上取得19种方法中最低平均误差0.19米，并在低成本四足机器人上用0.5小时无标签数据实现0.6%漂移和嵌入式实时运行。</td></tr>
<tr><td>2026-11-24</td><td>ROVO: Robust Rotation-Only Visual Odometry for UAVs at Low and Moderate Altitudes<br><a href='http://arxiv.org/pdf/2611.32475'>论文</a> | <a href='https://github.com/sssxxxkkkk/ROVO'>代码</a></td><td>本文提出面向低中空无人机单目图像的仅旋转视觉里程计ROVO，旨在抑制图像噪声引起的旋转与平移估计混淆，避免不确定地标深度向后传播。
◆提出仅估计并保留朝向状态的视觉里程计框架，从轨迹状态中剔除不确定深度，提升旋转估计鲁棒性。
◆设计基于重叠窗口的成对旋转鲁棒平均与共享帧窗口对齐机制，实现连续窗口间的稳定旋转估计。
◆利用长距离视觉感知中的角度线索构建旋转约束，在高噪声和窄视场条件下保持较高相对旋转精度。
仿真中滑动窗口ROVO平均朝向误差仅为传统SLAM基线的10.7%，真实飞行数据上旋转精度与ORB-SLAM3和DPVO相当。
在窄视场或更高飞行高度下，ROVO相较各对比中次优方法将相对旋转RMSE降低19.7%至69.4%，并开源代码与仿真工具。</td></tr>
<tr><td>2026-11-24</td><td>GOLD-SLAM: Gaussian-splatting Omnidirectional LiDAR-Depth SLAM<br><a href='http://arxiv.org/pdf/2611.32335'>论文</a></td><td>本文提出GOLD-SLAM，一种融合全景相机与LiDAR深度先验的全向高斯泼溅SLAM系统，在球形域完成跟踪与建图，兼顾高质量渲染和几何重建。
◆ 在LiDAR覆盖不足区域利用跟踪到的视觉特征辅助位姿估计，缓解全景视场与LiDAR视场不匹配问题。
◆ 提出深度感知地图扩展与修剪DAEP，抑制新观测表面覆盖不足和增量建图中的漂浮伪影。
◆ 构建WHOLE无人机数据集，覆盖弱几何、高动态、全向、低光和简单场景，支持更全面评测。
◆ 在公开基准与WHOLE上取得有竞争力渲染质量，较现有全景基线平均PSNR提升5.56至9.10 dB，平均Depth-L1降低71.9%至83.9%。
此外，在Jetson Orin NX上验证嵌入配置可在线运行，但重建质量有所折衷。</td></tr>
<tr><td>2026-11-24</td><td>View Management with Gaussian Placement and Opacity Regularization for Online 3DGS<br><a href='http://arxiv.org/pdf/2611.32025'>论文</a></td><td>论文针对在线3DGS地图参数多、视角稀疏易过拟合且受实时预算约束的问题，从视图管理与模型复杂度控制两方面提出改进。  
◆提出渐进接纳非关键帧参与建图更新，并按不同帧组提供的监督量分配有限更新，以兼顾地图结构与视图监督。  
◆提出边缘引导初始化，将新高斯放置在图像细节真正需要的区域，从而控制地图模型复杂度。  
◆提出自参考不透明度正则化SOR，利用累积渲染证据且不增加额外渲染成本，抑制持续位于地图表面参考前方的高斯不透明度，以补偿前端深度不确定性。  
这些设计在实时预算内协同提升了在线3DGS地图的外观与几何质量。</td></tr>
<tr><td>2026-11-23</td><td>OmniSLAM: Evidence-Authorized Revision of Persistent Object Maps<br><a href='http://arxiv.org/pdf/2611.30184'>论文</a></td><td>本文提出OmniSLAM地图修订模块，将历史身份变更与新表面准入分离，以在保留有效身份的同时吸收新表面并纠正旧关联。
◆ 采用跨视图共享与分离掩码解释检验候选合并，仅当移除任一观测帧后证据裕度仍为正才允许合并。
◆ 通过局部身份竞争为新测点分配身份，并结合掩码见证与种子帧稳定性检查。
◆ 利用受控输出干预将增益归因于碎片合并、防止有害覆盖和新点局部分配。
在KITTI-360两个窗口上，建筑/汽车实例AP50:90均值由17.259升至18.762；四个空间留出集由20.263升至23.171，但无条件修订略高为23.251。
额外种子帧检查未带来AP增益，330帧车库记录验证了与LiDAR—惯性—视觉里程计的离线集成，也表明保守决策仍限制恢复。</td></tr>
<tr><td>2026-11-23</td><td>Confidently Lost: Silent Failure and Edge Deployment of Dense Visual SLAM under Photon Starvation<br><a href='http://arxiv.org/pdf/2611.30173'>论文</a></td><td>论文揭示：基于学习双视图几何的稠密视觉SLAM在低光下会“静默失败”，网络把无结构的量化噪声也解释成跨视图一致几何，系统因信任该一致性而不报错。暗序列中系统处理1605帧仅输出7个关键帧、不拒绝任何因子图边并报告满帧率，但超过95%被接受的对应关系违反真值极线几何。
◆揭示同一膨胀的几何自洽统计被关键帧与重定位以相反阈值读取，造成关键帧饥饿而重定位几乎全收的失败机制。
◆提出以关键帧对基线上的该统计作为无需真值和额外计算的自检信号，可在ETH3D暗序列区分自信崩溃与正常工作（样本内）。
◆证明低光适配权重或阈值重调虽把跟踪轨迹从1/6提升到5/6，却只是撤回错误几何上的置信，不能恢复准确几何。
◆在Jetson AGX Orin腿足机器人回放中复现该签名，并发现其表现面随路线几何与传感器编码变化。</td></tr>
<tr><td>2026-11-22</td><td>GravHMR: Coupling SLAM and Human Mesh Recovery in a Shared Gravity Frame<br><a href='http://arxiv.org/pdf/2611.29614'>论文</a></td><td>论文提出GravHMR，一个无需训练、即插即用的框架，通过共享的重力对齐参考系耦合SLAM与人体网格恢复，以缓解动态相机下全局一致3D人体运动恢复中的朝向不一致和轨迹漂移问题。其关键思想是让重力独立于HMR主干估计，从而兼容带或不带显式重力视角表示的世界接地HMR模型。
◆ 提出偏航感知朝向优化YAOO，围绕共享重力轴校正人体与速度朝向，解决航向不一致。
◆ 提出重力感知轨迹优化GATO，在度量SLAM世界中联合利用2D重投影、人体隐含度量尺度和自身运动锚定根轨迹。
在EMDB-2上，GravHMR使用ViPE达到154.0毫米W-MPJPE100，使用masked DROID-SLAM达到189.8毫米，优于同相机估计下TRAM的222.4毫米。相同HMR主干下，其W-MPJPE100较GVHMR的276.5毫米降低44.3%，较GVHMR+HTD-Refine的192.4毫米降低20.0%，实现最先进性能。</td></tr>
<tr><td>2026-11-20</td><td>BRINA: Bottom-Referenced Inertial Navigation with AKAZE, a Sonar SLAM for Autonomous Marine Vehicles<br><a href='http://arxiv.org/pdf/2611.27817'>论文</a></td><td>本文提出BRINA，一种以前视声呐为唯一外感传感器的声呐-惯性SLAM系统，面向自主海洋航行器导航。针对声呐回波高度不可观测导致运动估计存在未知米制尺度、通常依赖DVL的问题，BRINA利用每束首次海底回波估计声呐高度，并将匹配特征投影至海底，从而在无DVL条件下获得米制里程计。
◆ 提出基于首次海底回波估计声呐高度并投影匹配特征的声呐惯性SLAM方法，实现无需DVL的米制尺度运动估计。
◆ 推导剩余尺度误差与海底倾斜及坡度变化之间的关系界限，为方法适用性提供理论依据。
◆ 在AUV仿真以及两类前视声呐、十次无人水面艇现场任务中验证系统性能与鲁棒性。</td></tr>
<tr><td>2026-11-20</td><td>Instant-LIVO: Efficient LiDAR-Inertial-Visual Odometry with Compact Geometry and a Bounded Single-Reference-Frame Map<br><a href='http://arxiv.org/pdf/2611.27633'>论文</a> | <a href='https://github.com/Faker-0714/Instant-LIVO.git'>代码</a></td><td>本文提出Instant-LIVO，一种面向资源受限平台的紧耦合、高速、实时LiDAR-惯性-视觉里程计系统。
◆ 构建基于空间哈希OctVox的紧凑几何地图，并通过缓存辅助的启发式分阶段KNN加速局部邻域检索与平面拟合。
◆ 设计有界单参考帧视觉地图，依据跟踪状态自适应更新参考帧，并采用Schmidt型不确定性感知光度融合保持参考位姿与当前状态的相关性。
◆ 采用IMU预测、LiDAR几何校正、视觉光度校正的顺序多传感器融合流程。
在32个公开基准和自建数据集上，X86与ARM平台均保持有竞争力精度，平均处理速度分别提升约2.3倍和2.1倍，峰值内存降至约1/20和1/13。
结果表明该方法在精度与计算效率上优于现有LIO和LIVO基线，适合资源受限平台部署。</td></tr>
<tr><td>2026-11-20</td><td>EgoSurgHands: An Egocentric 3D Hand Pose Dataset &amp; Benchmark for Open Surgery Training<br><a href='http://arxiv.org/pdf/2611.27101'>论文</a></td><td>EgoSurgHands提出了首个真实采集的自我中心开放手术训练3D手部姿态数据集与基准，旨在支撑技能评估、AR引导和机器人示范学习。
◆ 数据集覆盖55段录制、13类任务、3种手套颜色和4名不同年资受训者，含41909条训练手实例与9476条人工验证评估行，并为每帧提供内参、手部关键点及置信度、时间戳、眼动和可用时的SLAM外参。
◆ 评估标签融合传感器伪真值、逐帧人工交叉复核、外科医生裁决和多视角三角化独立参考，显著提升真值可靠性。
◆ 评测协议同时采用过程不相交划分和留一佩戴者协议，可检验对新受训者的泛化能力。
◆ 对八种方法零样本评测发现，自我中心预训练普遍提升跨佩戴者迁移，JointTransformer最佳达14.95毫米，MediaPipe仅检测到24.1%评估行，并给出JRN残差校正基线。
数据集与基准代码已公开，揭示手术域差距仍是后续关键挑战。</td></tr>
<tr><td>2026-11-20</td><td>RoboCap-10k: A Metrically Accurate Egocentric Dataset for Robot Learning<br><a href='http://arxiv.org/pdf/2611.26916'>论文</a></td><td>论文提出RoboCap-10k，一个面向机器人学习的大规模第一视角操作数据集，包含1万小时精选的无脚本操作数据。  
◆ 数据覆盖11个国家工人带薪班次中的真实操作，涵盖18个任务族、200种任务类型和2000个任务，强调可扩展的真实监督来源。  
◆ 全部数据由统一设备RoboCap采集，该设备是250克帽子，集成六个同步全局快门相机和双IMU，减少异构设备差异。  
◆ 通过在线校准将每台设备极线误差控制在1像素以下，并用视觉惯性SLAM获得重力对齐的6自由度头部轨迹。  
◆ 采用多视角手部跟踪器生成厘米级度量精度手部姿态，并为每个片段提供任务与子任务语言描述。  
这些设计使数据集同时具备度量3D标签、统一硬件和语言标注，为第一视角机器人学习提供高质量监督。</td></tr>
<tr><td>2026-11-19</td><td>Stereo Visual Odometry with In-the-Loop Geometric Feed-Forward Models Towards Dense Metric Mapping<br><a href='http://arxiv.org/pdf/2611.25445'>论文</a></td><td>本文提出一种立体视觉里程计框架，将几何前馈模型的稠密深度预测与基于因子图的视觉里程计紧耦合，实现准确定位和稠密度量建图。
◆利用立体与时序多视图观测得到的稀疏但可靠度量几何来标定稠密深度预测，而非直接将预测条件于可能含噪的立体深度，并在每个局部子图内对所有关键帧联合估计尺度-平移变换，获得度量一致的稠密深度。
◆设计分层因子图架构：局部层通过滑动窗口优化估计高频相机位姿和多视图精化三维路标，仅对选定关键帧生成稠密预测，并用SE(3)广义ICP在子图内配准。
◆在连续子图间利用共享几何进行Sim(3)对齐，校正残余尺度不一致，并将子图内与子图间约束统一纳入全局因子图，得到一致轨迹和稠密度量重建。
◆在公开和自采数据集上，该方法定位精度与几何及学习型基线具有竞争力，同时提供准确稠密度量重建，并提升了对学习深度预测失败的鲁棒性。</td></tr>
<tr><td>2026-11-18</td><td>Accord: Universal Online Metric Localization and Dense Mapping from one Camera and an IMU<br><a href='http://arxiv.org/pdf/2611.25279'>论文</a></td><td>Accord提出一种仅依赖任意单相机与IMU的在线稠密度量建图系统，解决VIO度量位姿但几何稀疏、前馈深度稠密却缺乏度量尺度的问题。
◆ 以VIO滤波器输出的度量位姿为条件，用深度基础模型对短关键帧窗口预测深度，并通过因子图融合子图。
◆ 提出多视图一致性机制：将每个关键帧窗口锚定到由滤波器位姿三角化的度量3D点，并利用共视图像间双向稠密深度一致性估计与校正逐图像尺度误差，同时保持锚点建立的度量尺度。
◆ 引入上下文关键帧改善深度预测，并将所得子图在因子图中融合以构建在线稠密度量地图。
在五个公开相机-IMU设置及新Phone-rig/GoPro数据集上，单一映射配置无需逐数据集调参、仅用自身轨迹对齐，即在5cm平均F-score上稳定取得最佳或次佳。
系统与手机架数据集开源，便于社区研究。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-24</td><td>ST-SfM: Spatio-Temporal Structure-from-Motion for Initialising 4D Gaussian Splatting<br><a href='http://arxiv.org/pdf/2611.32231'>论文</a></td><td>本文提出ST-SfM，一种面向同步标定多相机视频的稀疏时空SfM方法，为4D高斯泼溅提供包含运动信息的初始化。
◆ 将场景分为静态与动态两分支，分别估计静态三维结构和动态四维点。
◆ 静态分支在每相机时序中值图像上检测结构，经时序稳定性门控后沿极线匹配。
◆ 动态分支以视频体中的时空兴趣点为候选，用HOG3D描述，并仅在极线与时间均一致的候选间匹配。
◆ 采用拒绝不一致合并的并查集跟踪，并用RANSAC跨所有视角对三角化，得到静态3D点和含亚帧时间的动态4D点。
用ST-SfM所得稀疏4D点云初始化4D高斯泼溅。
在N3DV场景上，相较随机初始化，方法在PSNR、SSIM和LPIPS上均取得提升。</td></tr>
<tr><td>2026-11-23</td><td>InitFree-SfM: When Initialization-Free Bundle Adjustment meets Learned Structure-from-Motion<br><a href='http://arxiv.org/pdf/2611.31516'>论文</a></td><td>本文针对无初始化BA从随机初始化联合恢复位姿与结构时优化目标与重建精度不匹配的问题，指出现有InitFree BA在现代SfM基准上难以获得准确重建，并表明引入学习度量深度可显著提升实用性。
◆提出完整无初始化SfM流程InitFree-SfM，融合学习对应、度量深度、深度一致轨迹构建与联合度量优化。
◆提出深度增强OSE目标dOSE，在OSE方向约束之外增加地标沿视线方向的定位约束。
实验表明该方法大幅优于现有InitFree BA，并在包括低重叠图像集的挑战场景中达到与成熟SfM流程相当的精度。
分析进一步挑战以往对代理目标的过度强调，揭示几何约束对准确重建起核心作用，OSE优化带来额外提升。</td></tr>
<tr><td>2026-11-23</td><td>Screening for nonrigidity in structure from motion using projected reprojection residuals<br><a href='http://arxiv.org/pdf/2611.30769'>论文</a></td><td>论文针对稀疏SfM默认静态场景、但变形仍可能产生看似合理重建的问题，指出现有重投影误差汇总忽略了误差在点与视角间的排列信息。
◆提出基于投影重投影残差的非刚性筛查诊断，先剔除可由小点/相机调整及随时间变化的简单空间趋势解释的成分，再衡量残差与固定时空模式的对齐。
◆该诊断仅使用一次估计的SfM重建，定位为筛查证据而非物理变形估计。
在四组合成管状数据中，它检出全部8个预设运动采集，而误差幅度汇总仅检出5或6个；每族阈值取其他三族最高静态分数，因此最高静态样本也会阳性。
在20个外观与流程变化的重建变体中，同阈值下保持19个阳性、1个数值弃权。
结果表明误差排列能揭示幅度汇总遗漏的不一致，可用估计相机、3D点和图像观测标记需进一步检查的合理重建。</td></tr>
<tr><td>2026-11-19</td><td>SGAR: Feed-Forward 3D Reconstruction via Sparse Geometry-Guided Attention<br><a href='http://arxiv.org/pdf/2611.26493'>论文</a></td><td>论文针对前馈三维重建中密集全局注意力随视图数平方增长的问题，提出从运动恢复结构视角看多数密集计算并不必要，因为三维结构源于二维几何匹配区域。
◆提出SGAR，用几何相似性引导的稀疏注意力替代密集全局注意力，使每个patch token仅关注其他视图中少量相关token。
◆设计轻量级可学习key选择模块，预测跨视图token的三维邻近关系，从而为稀疏注意力选取几何相关token。
◆该方法具有通用性，可通过微调应用于不同前馈重建模型。
实验表明SGAR在稠密和稀疏方法中速度最快、稀疏方法中最准确，在1000视图下比密集注意力快至多12倍并保持稳定位姿精度，同等时间预算下重建更完整几何。</td></tr>
<tr><td>2026-11-19</td><td>Reference-Twist-Based Velocity-Domain Spatiotemporal Calibration for mmWave Radar, Event Camera, and IMU<br><a href='http://arxiv.org/pdf/2611.26083'>论文</a></td><td>论文针对毫米波雷达、事件相机与IMU跨模态标定中目标、特征、点云或位姿关联难以建立的问题，提出参考twist条件下的速度域时空标定框架。该方法利用刚性套件共享运动，将雷达多普勒、事件法向流和惯性测量回归到同一可信参考体twist，联合估计相对旋转、杆臂、时间偏移及传感器偏置与尺度，无需人工靶标、运动恢复结构或跨模态点云配准。
◆ 将参考体twist作为条件输入而非待标定传感器，建立参考条件化的速度域跨模态标定模型。
◆ 对比联合估计与参考条件估计，推导条件可辨识性、CRLB级协方差和偏差界，并明确条件信息有效的工况。
◆ 利用室内和森林轴分离运动数据系统评估初始化、时间对齐、运动退化、参考输入敏感性和残差一致性。
由于参考不增加物理可观性，估计仍受参考精度、同步、运动激励和投影多样性约束。</td></tr>
<tr><td>2026-11-17</td><td>Refin3R: Geometry-Guided Refinement for Feed-Forward 3D Reconstruction<br><a href='http://arxiv.org/pdf/2611.23051'>论文</a></td><td>Refin3R针对前馈三维重建点图跨视角不一致且精度不足的问题，提出用SfM点精化点图并将SfM几何传播到图像网格。其双分支架构让2D分支借助几何感知骨干特征扩展SfM覆盖，3D分支对所有视图SfM点推理以捕获多视图结构，两分支双向交换信息并联合精化每个视图，输出密集准确点图。
◆ 以SfM点引导前馈点图精化，并将SfM几何传播到图像网格，而非仅作辅助输入。
◆ 设计2D-3D双分支架构，分别扩展SfM覆盖范围并推理多视图SfM结构。
◆ 通过两分支双向信息交换实现逐视图联合精化，生成密集且准确的点图。
实验表明，Refin3R在ScanNet++、ETH3D、Tanks&amp;Temples及域外人体和手术场景中精度持续领先，且快于最强几何引导基线。</td></tr>
<tr><td>2026-11-16</td><td>Pointillist Maize: 3D Reconstruction of Field-Grown Maize Using RGB UAV Imagery<br><a href='http://arxiv.org/pdf/2611.20502'>论文</a></td><td>本文评估消费级无人机RGB视频结合SfM与MVS能否重建田间玉米并恢复可识别器官，系统考察飞行轨迹与帧采样对重建质量的影响。
◆验证了该流程可恢复叶片、茎、雄穗分枝、果穗、花丝和气生根等田间玉米器官级结构。
◆通过等帧对比量化了单轨道与ribbon skirt轨迹在点云集中度、可见空洞和孤立散点之间的取舍。
◆揭示增加蛇形航线和提高帧采样率能降低密植苗行渲染空洞，但也会因植株运动增加点云弥散。
◆展示curlicue轨迹可在另一田块区分单株且无明显重复结构，同时指出土壤表面仍存在较大空洞。
◆明确当前重建在定量表型前仍需独立几何验证，并给出采集策略、重建完整性与点弥散之间的权衡。</td></tr>
<tr><td>2026-11-15</td><td>Remember, Replay, Adapt: Learning from Past Experience in Online Vision-and-Language Navigation<br><a href='http://arxiv.org/pdf/2611.19901'>论文</a></td><td>论文针对在线VLN中已有反馈未被充分利用的问题，受人类情景记忆启发提出R2A在线适应框架，持续复用成功与失败导航经验进行策略学习。
◆ 提出成功-失败记忆SFM，保留带反馈的成功和失败导航片段，并依据新指令检索任务相关经验，使历史反馈指导后续导航。
◆ 提出先验锚定适应PAA，以冻结预训练策略为锚，相对其强化成功轨迹、抑制失败轨迹，并正则化行为漂移。
二者结合实现了无需源域数据和专家监督的持续反馈复用与稳定策略适应。
在REVERIE、R2R、R2R-CE及五个导航骨干上实验验证一致提升，REVERIE验证未见集上DUET的SR从46.98%升至69.84%，SPL从33.73%升至50.98%。</td></tr>
<tr><td>2026-11-13</td><td>Interpreting JWST UV luminosity functions and angular correlation functions via a &quot;universal language&quot; for high-redshift galaxies<br><a href='http://arxiv.org/pdf/2611.18850'>论文</a></td><td>论文提出连接暗晕质量、恒星质量、恒星形成率和UV星等的“通用语言”，以跨模型与数据一致定义的条件分布链，并用五个流体模拟构建宽先验，联合z&gt;6 JWST的UV光度函数与角相关函数推断星系种群参数。
◆ 建立可跨模型与观测同口径比较的柔性星系种群框架，缓解不同物理过程却给出相似压缩统计量而难以判别的问题。
◆ 联合UV LF与质量完备的ACF进行贝叶斯推断，发现大SHMR弥散被ACF显著压低。
◆ 在模拟先验下得到SFMS恒星形成时标约一个暗晕动力学时标，且SFMS弥散随恒星质量降低而增大，并量化其为固定暗晕质量下UV星等随机性的主源（MUV=-20处约61%，SHMR约36%）。
◆ 贝叶斯模型选择未发现SHMR随红移演化或SFMS斜率偏离1的证据，且z~20预测UV LF比候选体估计低数个量级，指出z≥14 UV LF估计需达成共识。
整体上，该工作提供了统一、可检验的高红移星系统计建模与解释框架。</td></tr>
<tr><td>2026-11-13</td><td>Deep Bundle Adjustment<br><a href='http://arxiv.org/pdf/2611.18256'>论文</a> | <a href='https://cphjsn.github.io/deep-ba/'>代码</a></td><td>DeepBA提出一种图神经网络，将捆绑调整摊销为可学习的图网络，从任意数量视图的2D匹配中恢复相机位姿、内参和场景结构。它不逐场景求解非线性最小二乘，而是基于几何残差迭代精化估计，并能从冷启动收敛。模型采用尺度不变监督（真值旋转、平移方向、内参及重投影自洽），可混合任意度量单位数据集，且与匹配器解耦。
◆ 将BA摊销为学习式GNN，用几何残差迭代精化位姿、内参和结构，无需逐场景非线性优化与细致初始化。
◆ 采用尺度不变监督和重投影自洽，支持任意度量单位数据集混合训练，并实现与匹配器解耦。
◆ 仅2.04M参数即优于已有学习式SfM，在多数位姿指标和重建上领先，中等精度下与经典SfM相当、随视图数增加耗时反超，并接近VGGT等大模型但模块化更强。</td></tr>
<tr><td>2026-11-09</td><td>Budget-aware Correspondence-driven View Selection for Real-time 3D Perception of Mobile Robots<br><a href='http://arxiv.org/pdf/2611.11809'>论文</a></td><td>本文提出预算感知、对应关系驱动的视图采样算法BCVS，用于移动机器人实时3D感知中的在线图像序列过滤。  
◆ 不依赖完整SfM流程或相机位姿估计，仅用纯对应关系评分选择视图，在保持几何稳定性所需重叠的同时优先选择新颖视图。  
◆ 根据用户给定预算迭代选取最独特帧并抑制近重复帧，生成紧凑子集以保持连通性并最小化重建损失。  
◆ 算法CPU上可达22+ FPS，支持在线过滤，并在紧预算下优于CPU友好基线，预算增大时仍具竞争力。  
基准实验验证了BCVS在紧预算下的性能优势与可扩展性。  
大型航空和海洋机器人实地试验表明，其可减少最高16%冗余，同时保持稳健SfM配准和高质量3D重建。</td></tr>
<tr><td>2026-11-09</td><td>Towards Rotation-Only Imaging Geometry: Multi-View Pose Estimation<br><a href='http://arxiv.org/pdf/2611.11770'>论文</a></td><td>本文提出以旋转为核心的多视图位姿估计框架，将全局旋转估计与全局平移恢复统一到仅旋转成像几何中。  
◆提出GRAM，直接利用初始相对旋转和内点匹配，通过最小化边级旋转仅代数残差估计全局旋转。  
◆用单阶段替代传统两视图相对位姿优化加旋转平均流程，减少分步误差累积。  
◆将仅旋转成像几何扩展至多视图，提出MORE，以多视图旋转仅重投影误差非线性精化全局旋转。  
◆提出ART，从LiGT约束推导局部尺度三视图平移，并用加权最小二乘恢复全局平移。  
合成与真实实验验证了方法在精度、鲁棒性和效率上的优势。</td></tr>
<tr><td>2026-11-07</td><td>VAComp: View-Aware Full Projector Compensation<br><a href='http://arxiv.org/pdf/2611.10637'>论文</a> | <a href='https://realkaizhou.github.io/VAComp/'>代码</a></td><td>VAComp是首个面向移动观看者、裸眼场景的视角感知全投影仪补偿框架，可在观看者移动时实现虚拟物体替代真实物体或视角一致的外观与材质修改。
◆ 针对SfM全局尺度未知问题，引入度量标定作为参考恢复全局尺度。
◆ 针对与投影仪反向相机的标定难题，设计分别面向RGB相机和深度相机的双棋盘标定方案。
◆ 提出两种非迭代混合方法VAComp-SD和VAComp-SI，将基于2D高斯、视角条件化的几何校正与学习式光度补偿结合。
◆ 两种方法均通过单次前向推理预测补偿图像，无需逐帧迭代优化，其中VAComp-SD支持实时更新，VAComp-SI达到交互级速率。
真实实验验证两种方法具有有竞争力的补偿质量与运行效率。</td></tr>
<tr><td>2026-11-06</td><td>OfficeTwin: Realizing 3D Reconstruction of Redundant Scenes through Partial Viewpoint Perception<br><a href='http://arxiv.org/pdf/2611.10241'>论文</a></td><td>OfficeTwin面向机器人原生采集的冗余办公场景，解决部分视角、弱纹理和重复结构下难以获得仿真可用3D模型的问题。它提出将不完整单目观测转化为仿真就绪数字孪生的机器人原生重建框架，并强调对象身份、物理属性与水密体积等下游需求。
◆ 先施加度量与结构约束，使重建结果具备真实尺度和结构一致性。
◆ 利用办公室重复隔间的结构冗余，将多次部分观测配准到共享规范帧，以互补信息恢复单视角遮挡几何，避免生成式幻觉。
◆ 在真实办公室扫描中把每个隔间重建为独立、水密、度量的实体，性能优于前馈重建和生成式基线。</td></tr>
<tr><td>2026-11-05</td><td>Degree-Equalized View-Graph Selection under Tight Pair Budgets<br><a href='http://arxiv.org/pdf/2611.07498'>论文</a></td><td>本文针对SfM中全量图像对匹配呈二次增长、需在紧预算下筛选视图图的问题，指出一次性选择器常忽略各图像已获配度数，导致边集中在少数图像并影响重建。作者提出无需训练的贪心规则Degree-Equalized Allocation（DEAL），在选择过程中对端点已被充分覆盖的图像对进行指数式降权，以实现度数均衡的视图图选择。
◆ 将“已分配度数”纳入预算化视图图选择，缓解覆盖选择器的度数集中问题。
◆ 设计无训练的指数降权贪心分配规则，可直接增强同一先验下的一次性选择器。
◆ 在九个1DSfM数据集B=2N上将同先验选择器从0.776提升到0.929，并在标准基准取得无训练选择器最高均值0.875。
实验表明DEAL在共享后端下接近SfM监督边先验的平均注册图像比例（0.929对0.930），且无需训练。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-24</td><td>Learning Agent States for Latent Action Modeling<br><a href='http://arxiv.org/pdf/2611.32017'>论文</a> | <a href='https://github.com/Mid-Push/Agent-State-LAM'>代码</a></td><td>论文指出，潜在动作模型若在纠缠智能体物理状态与背景、持续外观等视觉上下文的空间中推断动作和预测转移，潜变量会编码与动作无关的信息。为此提出Agent-State LAM，联合学习紧凑的智能体状态表示和建模其转移的潜在动作。
◆联合学习紧凑智能体状态与潜在动作，使动作推断和前向预测共享同一紧凑状态空间。
◆提出空间匹配时间判别SMTD，利用冻结局部视觉特征进行空间灵活匹配，并按最强局部匹配为帧打分以区分源帧与邻近帧。
◆通过让背景和持续外观在帧间仍可匹配而降低其判别性，促使表示聚焦智能体不断演化的物理状态。
实验在干扰控制任务和六个真实机器人视频数据集上验证了动作恢复、下游控制与世界模型预测的改进。</td></tr>
<tr><td>2026-11-22</td><td>Separating Action Allocation from Image Matching in Visual Token Routing<br><a href='http://arxiv.org/pdf/2611.29477'>论文</a></td><td>论文将视觉token路由中的“动作分配”与“图像匹配”两个因素拆开评估，以解释平均分提升究竟来自更优匹配还是更频繁使用高分辨率。  
◆ 提出在每类任务内固定动作计数，并将路由分配与同动作、同图像的随机配对比较，从而分离匹配收益与动作频率影响。  
◆ 发现在ChartQA和TextVQA等权设置下，Qwen2.5-VL-3B/7B均从匹配中获益，但相对任务表的动作频率带来更大损失，7B上分别为1.71点增益和3.95点损失。  
◆ 通过替换CARES选择的连续分辨率进行检验，发现这种外部选择在7B上也会降低质量。  
◆ 当请求带有任务标签时，任务表比离散路由器高1.92点，并在完整7B请求上平均节省31.76毫秒。  
◆ 核心创新是揭示路由收益的关键分解，并说明任务级动作分配表在带标签场景下更有效且更省时。</td></tr>
<tr><td>2026-11-20</td><td>Which Dwarf Is This? Doppeldwarf-306 and Near-Identical Instance Retrieval<br><a href='http://arxiv.org/pdf/2611.27490'>论文</a></td><td>论文发布Doppeldwarf-306：波兰弗罗茨瓦夫306尊青铜小矮人雕像的1691张开放许可照片，多数属同风格系列且记录摄影师，为近似相同实例检索提供新基准。
◆ 构建视觉高度相似的小雕塑细粒度检索数据集与留一查询协议，补充以地标为主的实例检索评测。
◆ 无训练冻结DINOv2最近邻首名准确率达93.1%，13个骨干最佳94.7%，并发现候选翻倍仅约降0.8个百分点。
◆ 证实按用户附近雕像过滤会被随机子采样高估；位置作权重可在25米模拟用户下把DINOv2从93.4%提至98.7%。
◆ 隐藏摄影师后局部特征匹配将DINOv2从81.8%提至85.5%并改善DINOv3；比较前两名候选在90%已知接受率下把未知误接受率从38.3%降至19.6%。</td></tr>
<tr><td>2026-11-19</td><td>LBW-NPS: A Local Band-Weighted Noise Power Spectrum Loss for Texture-Preserving Low-Dose CT Denoising<br><a href='http://arxiv.org/pdf/2611.25548'>论文</a></td><td>本文提出一种面向低剂量CT去噪的局部频带加权噪声功率谱损失LBW-NPS，在抑制噪声的同时更好地保留参考图像局部纹理。  
◆ 以重叠Hann窗局部patch内谱能量比较替代全局池化谱匹配，缓解区域纹理差异被平均忽略的问题。  
◆ 每个有效patch对三个频带的加权平方对数能量差进行约束，并与L1重建项联合训练。  
◆ 该方法无需组织特异性损失条件，且不改变原有U-Net去噪架构。  
◆ 通过patch尺度消融及肺、软组织、骨区域评估，验证局部频带功率匹配的有效性。  
实验表明，在220张测试切片上，LBW-NPS使64×64评估窗内相关局部谱差距较池化频带加权NPS降低31.9%，PSNR无统计显著变化，并在未参与损失的平均NPS频率和GLCM指标上降低均匀软组织误差。  
因此，其核心贡献是提升区域纹理一致性而不牺牲去噪架构与整体保真度。</td></tr>
<tr><td>2026-11-17</td><td>Automated open-set multi-view seahorse re-identification from underwater photograph sequences<br><a href='http://arxiv.org/pdf/2610.39857'>论文</a></td><td>论文提出面向水下照片序列的自动化开放集多视角海马重识别方法，并在35914张照片、474只野生海马的数据集上训练与评估。
◆ 构建大规模野生海马照片序列数据集，并统一处理物种分类、性别判定和开放集重识别任务。
◆ 将一次观察中的多张照片聚合起来，显著提升物种、性别和重识别性能。
◆ 物种与性别分类采用DINOv3嵌入的线性探针逐图分类，再对观察内照片的logits取平均。
◆ 重识别先用微调MiewID描述子检索候选，并用学习到的相关性分数对照片加权，再以ALIKED与LightGlue局部匹配和RANSAC几何校验重排候选。
◆ 用逻辑模型估计个体是否已在图库，并通过最大后验规则在最佳匹配身份与新个体之间决策。
观察级物种和性别平衡准确率分别达0.97和0.90；开放集重识别归一化准确率在图库含全部历史观察时为0.90，仅含一次观察时为0.83。</td></tr>
<tr><td>2026-11-15</td><td>Mock Observations: Morphological Analysis of Galactic Bars in IllustrisTNG Simulations<br><a href='http://arxiv.org/pdf/2611.19884'>论文</a></td><td>论文利用IllustrisTNG的TNG100/TNG50生成匹配SDSS观测条件的合成r波段图像，并以统一的源分割、形态分类和等相椭圆拟合流程比较z~0.1星系棒的统计与性质。结果显示SDSS、TNG100、TNG50全局棒分数约为26.68%、24.96%、13.42%，TNG100在约10^10至10^11.2太阳质量与SDSS较一致但更高质量偏高，TNG50多数质量段偏低。
◆构建了从模拟图像、观测条件匹配到统一形态测量的可比框架，系统比较模拟与SDSS的星系棒。
◆揭示棒分数差异与核球集中度和盘尺度相关：TNG100高n核球偏少且大质量盘更延展，TNG50高n核球偏多。
◆量化了棒长定义的系统偏差，发现外椭圆率下降估计R0.85max系统大于椭圆率峰值估计。
◆强调观测条件、样本选择和棒识别方法对棒分数与棒长推断的影响，并指出SDSS分辨率可能低估棒分数。</td></tr>
<tr><td>2026-11-06</td><td>OfficeTwin: Realizing 3D Reconstruction of Redundant Scenes through Partial Viewpoint Perception<br><a href='http://arxiv.org/pdf/2611.10241'>论文</a></td><td>OfficeTwin提出一种面向机器人原生采集的部分视角感知框架，可将不完整单目观测转化为可用于仿真的数字孪生。
◆它先施加度量与结构约束，为重建提供稳定的物理尺度与场景结构先验。
◆它利用办公室重复隔间的结构冗余，将重复实例配准到共享规范帧，并通过互补观测恢复单视角中被遮挡的几何，避免生成式幻觉。
◆它面向仿真就绪资产，输出每个隔间独立、水密且具有度量尺度的实体模型。
在真实办公室扫描中，该方法成功恢复每个隔间，优于前馈重建和生成式基线。</td></tr>
<tr><td>2026-11-05</td><td>Federated training performs as well as centralized for 3D Latent Diffusion for Diagnosis-Conditioned Brain MRI Synthesis<br><a href='http://arxiv.org/pdf/2611.08771'>论文</a></td><td>本文提出并验证了一种面向诊断条件脑MRI合成的3D条件潜在扩散模型联邦训练方案。
◆ 首次系统比较联邦训练与集中式训练在该3D条件生成任务上的效果，证明无需共享数据也能获得相近性能。
◆ 采用条件保真度、多尺度SSIM多样性和FID真实性三类指标，从分类有效性、分布匹配和图像真实感多角度评估生成质量。
◆ 结果表明联邦训练可有效利用多站点数据，同时保持数据本地隐私。
因此，联邦学习是构建多站点脑MRI生成模型的可行路径，为稀缺和不均衡神经影像数据增强提供了新思路。</td></tr>
<tr><td>2026-11-05</td><td>USB Gym: A Gymnasium Testbed for Closed-Loop Ultrasound View Matching<br><a href='http://arxiv.org/pdf/2611.08352'>论文</a></td><td>论文提出USB Gym，用于闭环超声视图匹配的标准化测试平台，旨在检验将已发表方法组合成完整引导流程后是否足够有效。  
◆ 构建基于公开患者CT及标签驱动纹理网络的超声仿真引擎，统一模拟并评估探头移动到目标视图的闭环引导。  
◆ 将引导流程拆分为器官分割器、控制器和奖励三个可替换槽位，在同一60个episode、6名留出患者上公平接入20种已发表方法，仅在可检测更优时替换原方法。  
◆ 以20个新CT上“组合方法对比原始引导”的较优者作为基准，并用仅仿真可得的位姿oracle设定参考上限。  
实验显示探头初始平均距目标16.0 mm，oracle可达1.5 mm；仅SSIM奖励略有可检测优势，最终基准停在13.7 mm，仅为oracle进展的16%。  
结论是未调优的已发表方法组合仍无法将探头引导至目标附近，该任务仍待探索，平台可接纳新方法但尚未进行硬件验证。</td></tr>
<tr><td>2026-11-03</td><td>Sparse Anchors for Visual Multi-Session Registration in Changing Environments<br><a href='http://arxiv.org/pdf/2611.05084'>论文</a></td><td>论文面向环境变化下的视觉多会话配准，提出用稀疏可靠绝对锚点结合会话内相对位姿约束，将新查询会话的完整轨迹配准到已有参考地图。
◆ 构建了“稀疏绝对锚点+会话内相对位姿”的鲁棒轨迹配准框架，可在跨会话可靠对应仅覆盖部分轨迹时仍恢复完整轨迹。
◆ 通过视觉位置识别、局部特征匹配和几何验证生成绝对对齐假设，并用序列一致性剔除不一致假设，保留可靠绝对锚点。
◆ 对锚点采用高斯特征场上的特征度量对齐进行精化，再与相对位姿约束联合进行鲁棒位姿图优化。
在HILTI26建筑工地数据集的15组跨会话实验中，该方法1米内召回94.4%、5米内100.0%，显著优于独立图像定位和直接配准独立SfM几何。
结果表明，稀疏而可靠的绝对锚点能够在剧烈场景变化和部分可匹配条件下实现准确且完整的轨迹配准。</td></tr>
<tr><td>2026-11-03</td><td>Manifold Embedding of Deep Image Features for Image Matching via Neural Adjoint Maps<br><a href='http://arxiv.org/pdf/2611.05083'>论文</a> | <a href='https://github.com/NafieAmrani/NAMI'>代码</a></td><td>本文针对真实图像中同类不同实例间的语义对应问题，指出现有基础模型特征常因正则不足导致最近邻匹配噪声大，尤其密集对应更明显。作者将3D形状匹配中的功能映射引入图像匹配，但需为规则图像网格构造有信息量的非平凡几何。
◆提出基于深度图像特征流形嵌入，并用Galerkin有限元方法推导离散Laplace-Beltrami算子，从而赋予图像网格有意义的流形结构。
◆引入神经伴随映射以表示功能映射中的非线性映射，突破传统线性表示限制。
◆在多个真实图像密集对应基准上实现零样本图像对应新SOTA，并公开代码。
该方法核心贡献是构建了面向图像匹配的流形功能映射框架，将特征流形几何与神经非线性映射结合，提升了对应正则化和密集匹配质量。</td></tr>
<tr><td>2026-11-01</td><td>Accurate automated photo-identification of Near Eastern and European fire salamanders<br><a href='http://arxiv.org/pdf/2611.01601'>论文</a></td><td>论文提出一套面向近东火蝾螈、可跨物种迁移的自动照片识别与数据库审计流程，以零样本局部特征匹配解决人工识别慢且易错的问题。
◆ 创新点：采用SuperPoint与LightGlue进行零样本局部特征匹配，无需物种特异性训练即可完成个体重识别。
◆ 创新点：先分离黄色斑点图案，再以高置信关键点匹配数评分，降低多斑点个体累积虚假匹配的混杂，并用两级聚类分配身份。
◆ 创新点：将流程与专家复核结合，可纠正误识别并审计既有数据库，使身份数减少近四分之一。
在留出个体上正确个体排名第一达95.2%、ARI为0.958，未修改迁移至欧洲火蝾螈时两个数据集top-1为95.1%和91.7%，一个数据集重捕识别93.7%（优于五种现有程序的38%–77%，接近人工目检的93.9%）。
这表明该方法无需训练数据、能跨相关物种迁移、可扩展至千个体级数据库，并可在捕获-重捕分析前用于数据库审计。</td></tr>
<tr><td>2026-10-30</td><td>A Generalized Sparse Fuzzy Clustering Framework with Automated Cluster Cardinality Estimation Ability<br><a href='http://arxiv.org/pdf/2611.00159'>论文</a></td><td>本文提出广义稀疏模糊聚类GSFC框架，通过在模糊目标函数中引入连续稀疏惩罚，克服传统模糊聚类隶属度全稠密、抗噪性弱且难以估计真实簇数的问题。
◆ 构建统一的连续稀疏惩罚模糊聚类目标，并针对模糊指数与稀疏指数并存导致无闭式解的问题，设计原始-对偶二分搜索与专用解析路径，严格满足划分约束并将迹隶属度精确驱动为零。
◆ 利用数学强制稀疏性，在初始簇数大于真实簇数时动态剪枝冗余簇，从而自动估计真实簇数。
◆ 引入虚拟噪声汇，将离群点与正常数据隔离，提高高噪声场景下的鲁棒性。
◆ 将框架扩展至线段检测任务，并通过合成数据、高噪声几何压力测试、UCI wine和高光谱图像等实验验证其优于传统模糊基准及现有稀疏可能性与概率软聚类方法。</td></tr>
<tr><td>2026-10-29</td><td>Luggage re-identification: A study of strategies towards a real-world application<br><a href='http://arxiv.org/pdf/2610.40643'>论文</a></td><td>本文面向真实视频监控场景，研究从多路视频流到行李检测与重识别的端到端行李ReID流程，弥补现有方法多依赖干净裁剪图像外观匹配、忽视多镜头多视角互补的不足。作者在真实环境基准数据集上系统评估不同流程变体，分析同一行李多视角与多镜头观测的选择和融合方式，并考察跨环境数据集训练对整体ReID性能的影响。核心贡献在于将多视频流互补信息纳入实际行李ReID应用，并给出可操作的策略评估。
◆ 提出面向真实应用的端到端多视频流行李检测与重识别流程。
◆ 系统研究并利用同一行李的多镜头、多视角和多观测互补信息进行选择与融合。
◆ 在真实环境基准上评估跨环境数据集训练等策略，为提升实际场景行李ReID性能提供依据。</td></tr>
<tr><td>2026-10-29</td><td>Comprehensive empirical evaluation of feature extractors in computer vision<br><a href='http://arxiv.org/pdf/2610.39551'>论文</a></td><td>本文对传统特征检测与描述子进行系统实证评估，覆盖SIFT、SURF、BRIEF、ORB、BRISK、KAZE、AKAZE、FREAK、DAISY、FAST和STAR，并从架构设计与复杂度分析其计算效率和鲁棒性。研究基于Image Matching Challenge Photo Tourism 2020中超过150万张图像，完成超过200万次比较，系统考察旋转、缩放、模糊、亮度变化、仿射、透视、鱼眼和椒盐噪声等条件。结果表明FAST检测器配合ORB描述子和BF匹配器速度最快，ORB在仿射变换和亮度增强图像上表现突出，AKAZE在模糊、鱼眼畸变、旋转和透视畸变下更优。
◆ 构建了覆盖多类传统特征提取器与多种图像变换的大规模统一实证基准。
◆ 揭示了检测器、描述子与匹配器组合对效率和鲁棒性的综合影响。
◆ 给出了面向不同退化与几何变换场景的特征提取方案选型依据。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-24</td><td>Reading Geometric Anchors: Viewpoint Generalization in Imitation Learning for Robotic Manipulation with RGB-Only Deployment<br><a href='http://arxiv.org/pdf/2611.32162'>论文</a></td><td>本文提出ReGeoAnch几何锚定模仿学习框架，旨在仅用RGB部署时提升机器人操作策略的视角泛化能力。
◆构建机器人基座坐标系下的全局锚与夹爪坐标系下的局部锚，为不同视角提供共享物理参考。
◆提出解耦外观引导几何读出，通过点到锚聚合在锚周围获得可比且稳定的几何表示，超越逐点对应。
◆设计锚到策略读出模块，以视角不变的机器人状态查询视角相关外观并选择任务相关锚，仅用几何值形成最终策略读出。
◆引入跨视角读出一致性，对齐源视图与合成目标视图的策略读出方向。
在MetaWorld和ManiSkill3的12个操作任务上，该方法相较基线提升了视角泛化性能。</td></tr>
<tr><td>2026-11-23</td><td>FGSCalib: Targetless Camera-LiDAR Extrinsic Calibration from Foreground Segmentation<br><a href='http://arxiv.org/pdf/2611.30935'>论文</a></td><td>论文提出FGSCalib，一种无需标定靶标的相机-LiDAR外参标定方法，可利用场景中任意运动物体对固定安装的相机-LiDAR对进行周期重标定，避免靶标导致设备停用。
◆ 不依赖物体类别，仅通过各传感器分离运动前景与静态背景，并利用正确外参下LiDAR前景点应投影到相机前景的一致性进行标定。
◆ 将相机掩膜转化为边界邻近场，采用两阶段模拟退火在选定帧对上搜索外参，无需测量初始外参，随机初始化也能得到相近结果。
◆ 方法同时适用于旋转式和非重复扫描LiDAR，并在21个仿真场景和72个真实场景（9组相机-LiDAR、8个场景）上验证。
仿真中位误差为5.3 cm和0.19°；真实数据中位误差为9.5 cm和0.9°，五轮取最低成本时72个场景中51个满足18 cm/1.8°容差，优于多数基线并接近单次人工标定。</td></tr>
<tr><td>2026-11-23</td><td>Active Observation for Robust Visual Servoing in Robotic Manipulation<br><a href='http://arxiv.org/pdf/2611.30658'>论文</a></td><td>论文提出面向双臂机器人抓取的主动观察视觉伺服框架，由一臂携带RGB-D相机作为主动观察者、另一臂执行抓取，以缓解接近阶段遮挡对闭环控制的干扰。观察者在可行共享视图工作空间内重定位，以保持或恢复目标与夹爪同时可见的共享视图，并在可见性下降时暂停工作臂进行恢复。
◆提出两阶段主动视点策略，将高精度RGB-D轴与任务相关误差分量对齐，提高初始伺服精度。
◆设计遮挡触发的探索模块，暂停工作臂并按观察质量评分候选视点，以恢复共享目标-夹爪视图。
◆利用单幅RGB-D图像同时检测目标与夹爪并构造相对伺服误差，避免对两个独立变换估计做差分带来的误差放大。
在双6-DoF Piper平台使用开放词汇检测器和文本提示、无需任务微调或演示，每物体50次随机试验取得94%抓取成功率，优于反应式视点基线76%和固定相机64%，严重遮挡触发后平均1.8±0.6秒恢复。</td></tr>
<tr><td>2026-11-23</td><td>StereoVLM: Binocular Vision-Language Models for Metric 3D Spatial Reasoning<br><a href='http://arxiv.org/pdf/2611.27915'>论文</a></td><td>本文提出StereoVLM，首个几何感知双目视觉语言模型，面向标定双目观测下的度量3D空间推理。
◆ 设计从跨视图对应与视差估计到标定条件度量深度感知、再到语义空间推理的分层学习范式，使模型直接学习可迁移的3D表征。
◆ 发现视差监督在未见环境中的泛化显著优于直接双目深度监督，为几何监督选择提供依据。
◆ 构建Stereo3D-Bench三级基准，覆盖点级几何到物体级空间推理，StereoVLM-8B取得95.17%深度δ1和66.98物体级均分。
◆ 干预实验证明性能提升依赖有效跨视图几何而非额外视觉token或语义先验，且分层几何监督在五个空间基准平均提升3.54分、RoboCasa操作成功率提升4.3个百分点。</td></tr>
<tr><td>2026-11-20</td><td>Quantitative Measurement of Pavement Distress based on Vehicle Camera and Perspective Correction<br><a href='http://arxiv.org/pdf/2611.27728'>论文</a></td><td>本文提出一种无需现场相机标定的车载相机路面病害定量测量方法，可直接从车辆图像获取长度、面积等指标。  
◆ 基于车道检测识别四边形感兴趣区域并构建透视变换矩阵，实现车载图像透视校正。  
◆ 利用道路标线比例和指定尺度进行尺寸校正，并可估计所选区域的实际宽度。  
◆ 将校正图像与目标检测算法结合，在无需现场标定下直接输出病害定量测量，并支持同一相机图像的低人工批量处理。  
该方法仅依靠图像信息完成车辆相机标定，避免额外现场实验，适合大规模车载图像数据处理。  
实测路面修补长度与路面摩擦数据趋势一致，为车联网产生的大量未标定道路图像提供了实用解决方案。</td></tr>
<tr><td>2026-11-20</td><td>GGDriver: Glance at What Is Shared, Gaze at What Differs for Perception-Free Planning<br><a href='http://arxiv.org/pdf/2611.27330'>论文</a></td><td>GGDriver提出“共享初看、差异凝视”的端到端规划机制，使每个候选轨迹选择与自身相关的视觉证据，而非所有轨迹共用同一压缩场景表示。
◆以全局共享场景特征生成轨迹假设，实现高效初看。
◆将每条轨迹投影为相机视图中的走廊掩码，在骨干原生分辨率上关注路径对齐的patch特征，用于轨迹细化与评分，且仅依赖预测轨迹和相机标定。
◆在评分阶段再次按最终提案投影，并沿自身路径取证排序；消融表明该凝视用于排序的增益大于仅用于细化，路径对齐patch优于随机或全patch注意力。
该方法可接入学习寄存器、感知监督BEV网格和粗粒度图像token网格三类规划器，并稳定提升规划分数。
在ViT-S骨干且无感知标签下，于WOD-E2E、NAVSIM-v1/v2和Bench2Drive分别取得8.110、94.2 PDMS、48.6 EPDMS和72.18闭环驾驶分数。</td></tr>
<tr><td>2026-11-19</td><td>Multiple-Camera Tracking of Rigid Objects<br><a href='http://arxiv.org/pdf/2611.25904'>论文</a></td><td>本文提出一种基于三维模型与图像轮廓对齐的单/多相机刚性物体跟踪方法，通过最小化预测模型点与图像轮廓间的误差，并以视觉伺服闭环方式逐帧更新相机内外参数。
◆系统分析点到点与点到轮廓匹配下的Jacobian矩阵，确定所需最小匹配数及导致秩亏的奇异配置。
◆建立点到点与点到轮廓两类匹配之间的数学联系，并证明后者具有与前者同类的奇异性。
◆研究多相机配置以优化方法鲁棒性，有效应对单相机奇异、坏数据、噪声及缺失数据。
◆用复杂船件和最多三台相机开展大量实验验证方法，并表明该跟踪器可用作相机标定程序。</td></tr>
<tr><td>2026-11-19</td><td>Homeward: No Place Like the Training View<br><a href='http://arxiv.org/pdf/2611.24455'>论文</a></td><td>Homeward提出一种无需训练、即插即用的观测适配器，可将未标定部署相机画面规范化回训练视角，使冻结VLA策略在相机被碰撞、重装或更换后仍能工作。
◆ 通过闭环诊断揭示“理想几何重渲染有效、现成前馈3D模型反而有害”的矛盾，并定位退化主要集中于细长机械臂。
◆ 利用“未知的相机参数与静态场景深度需估计、已知的机器人连杆3D状态可由运动学直接渲染”的非对称性，融合RGB帧与单张训练视角参考完成校正。
◆ 无需场景微调或部署相机标定，即可扩展到6自由度随机位姿、焦距变化及连续相机漂移。
在约30万闭环episode、四种冻结VLA和LIBERO-Plus全部1599种相机变体上，成功率由62.5%、76.5%、68.0%、3.6%提升至77.6%、95.1%、91.2%、26.4%。
在三/四个策略上匹配或超过已标定、场景训练的视角合成基线。</td></tr>
<tr><td>2026-11-18</td><td>Meta-LSQ: A Closed-Form Sobolev Inner Solver for Few-Shot Meta-Learning<br><a href='http://arxiv.org/pdf/2611.24718'>论文</a></td><td>Meta-LSQ提出一种用于少样本元学习的闭式Sobolev内层求解器，用固定随机Fourier基上的正则最小二乘替代需反向传播的梯度内循环，并仅元学习带宽、岭系数和导数权重三个标量。
◆以单次闭式最小二乘拟合每个任务，避免MAML式内环梯度微分和全网元学习。
◆利用正弦函数导数仍为正弦的性质，使同一求解器可吸收导数观测并给出任意阶精确闭式导数。
◆在任务间共享同一核，少量标量即可实现快速元学习，在正弦回归和ARES波束调优中优于一阶MAML或ALPaCA类基线。
◆真实传感器校准中学习先验均值可改善部分目标，但整体仍逊于精确GP/ALPaCA，且非光滑目标和基外无噪目标会暴露岭选择失效。
总体而言，其核心是以极低参数量的闭式谱基求解换取高效、可导且可融合导数的少样本适应。</td></tr>
<tr><td>2026-11-18</td><td>Object Pose: The Link between Weak Perspective, Paraperspective, and Full Perspective<br><a href='http://arxiv.org/pdf/2611.24095'>论文</a></td><td>本文对DeMenthon和Davis的位姿估计方法给出代数推导，说明其通过迭代改进弱透视位姿并逼近透视相机位姿。论文证明该方法属于更一般框架：透视相机模型可零阶近似为弱透视，或一阶近似为平行透视。
◆ 提出并详细描述面向非共面与共面物体点的迭代平行透视位姿计算方法。
◆ 分析并比较收敛性，证明迭代平行透视法比迭代弱透视法具有更好的收敛性质。
◆ 给出简单引入旋转矩阵正交约束的方式，并分析标定误差敏感性、定义最优实验设置。
最后与非线性优化方法比较实验结果，验证所提方法的性能与适用性。</td></tr>
<tr><td>2026-11-18</td><td>Agreement Is Not Accuracy: LiDAR Elevation Errors Hidden in LiDAR-Camera Extrinsics<br><a href='http://arxiv.org/pdf/2611.23972'>论文</a></td><td>论文指出LiDAR与相机观测一致并不代表内部几何准确，系统性LiDAR高程偏差会被外参吸收。
◆ 提出利用同步LiDAR强度与相机估计棋盘位姿，联合估计跨记录的传感器高程修正和逐记录外参。
◆ 用射线-平面交会定位棋盘格且不依赖报告距离，避免距离误差直接移动查表，并获得更小相机一致性残差。
◆ 在六个同构平台中将平均平移参考距离由7.57mm降至3.04mm。
◆ 在独立结构上降低平面间夹角误差并改善图像边缘对齐，旋转平台时最大角改善平面对按高程修正预测移动。
◆ 揭示外参标定后目标投影与回环一致性变化很小，说明标定一致不等于LiDAR内部几何正确，并提供无需大型标定场的实用估计与检验途径。</td></tr>
<tr><td>2026-11-17</td><td>UnrealEvent: Synthetic Dataset Generation and Annotation for Event-Based Vision<br><a href='http://arxiv.org/pdf/2611.23078'>论文</a></td><td>本文提出UnrealEvent，一个基于Unreal Engine 5.5的合成数据集生成与自动标注流水线，用于缓解事件相机目标检测标注数据稀缺问题。
◆ 将受V2E启发的事件帧生成器与EasySynth语义渲染通道结合，可直接把渲染关卡序列转换为成对事件表示和YOLO格式边界框标注，无需人工标注。
◆ 基于相邻帧逐像素对数亮度差生成事件，并从正态分布独立采样对比度阈值，以模拟真实传感器制造导致的阈值失配。
◆ 提供合成数据集，并在eTraM上系统评估YOLOv8在合成训练、零样本真实和真实微调三种设置下的表现。
实验显示合成域内性能较强，但合成到真实存在明显差距，行人尤为突出。
小规模真实子集微调可提升真实域性能，剩余差距说明资产多样性和传感器校准的重要性。</td></tr>
<tr><td>2026-11-16</td><td>SiGMA: Site-Grounded Multi-Modal ISAC Data Generation for Environment-Aware Communications<br><a href='http://arxiv.org/pdf/2611.20665'>论文</a> | <a href='https://github.com/Trans-cending/SiGMA-main'>代码</a></td><td>SiGMA提出面向环境感知通信的站点锚定多模态ISAC数据生成框架，解决新站点数据获取中传感器校准、协同测量和跨模态关联难题。
◆融合OpenStreetMap、Overture Maps与程序化3D重建生成地理参考城市场景，并以共享场景几何和时间索引的动作者状态统一多模态数据。
◆同步生成RGB图像、LiDAR点云、定位记录、FMCW雷达IQ样本和射线追踪无线信道，实现同一站点与动态场景状态下的跨模态关联。
◆支持在直连链路阻塞下按配置生成RIS分量信道，用于共享场景状态下的相位配置评估与相机辅助的传感关联监督。
实验表明该框架在真实DeepSense 6G测量上的零样本波束预测性能优于基于OSM的合成数据基线。
数据集生成流程已开源，便于复现、评估和扩展。</td></tr>
<tr><td>2026-11-12</td><td>NonSense: On the (In)security of FPGA Anti-tamper Sensors<br><a href='http://arxiv.org/pdf/2611.17065'>论文</a></td><td>本文系统性地挑战了FPGA防篡改传感器天然可信的假设，将其视为一个脆弱且未被充分探索的独立攻击面，并呼吁把传感器自身安全纳入威胁模型与防护设计。
◆揭示最先进的硬IP与软IP传感器，其检测和响应机制均可在非侵入式条件下被绕过。
◆指出供电网络的空间与频率相关特性可将故障导向目标而避开邻近传感器，从而降低检测可靠性。
◆揭示温度变化会偏移检测阈值，长期老化会导致校准漂移并可能形成静默检测缺口。
◆提出针对检测与响应机制的加固对策，以提升传感器在物理攻击和环境漂移下的可信性。</td></tr>
<tr><td>2026-11-12</td><td>VBot Exo2Ego Policy: Lightweight Data Collection and Exocentric-to-Egocentric Video Generation<br><a href='http://arxiv.org/pdf/2611.16417'>论文</a></td><td>本文提出VBot Exo2Ego Policy，将第三人称视频生成选定演员的第一人称观测，以低成本扩展第一人称操作数据。
◆ 设计轻量数据采集管线与移动应用，支持第一人称、第三人称及双视角同步采集，并结合配对RGB与相机几何学习跨视图对应。
◆ 基于预训练视频扩散Transformer引入几何引导，以及语义掩码和手部关键点辅助监督，提升手物交互生成保真度。
◆ 训练时随机注入相机几何并逐步移除，使推理阶段无需目标相机标定。
◆ 面向互联网视频多样性，融合源视频感知推理、可选演员参考和多镜头适应，识别目标演员并跨镜头跟踪操作过程。
该系统与模型为跨任务、场景和参与者扩展第一人称操作数据提供了实用基础。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vlm'>Robot VLM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-24</td><td>ROAM-Bench: Evaluating Embodied Active Spatial Intelligence through Evidence Verification<br><a href='http://arxiv.org/pdf/2611.33143'>论文</a></td><td>论文提出ROAM-Bench，在机器人运动与碰撞约束下评估具身主动空间智能。
◆创新在于用仿真状态与回合记录进行独立检查，将结果正确性与任务要求完成度解耦，并强化几何、覆盖和放置验证。
◆构建了含250个手工验证任务、11类任务、5组任务和27个室内环境的基准，覆盖物体与房间搜索、计数、几何判断、方向推理和重定位。
◆通过人类评测达到84%严格任务成功率且所有正确结果均满足检查，验证了评测协议的有效性。
◆在七个前沿视觉语言模型上揭示两类互补失败模式：结果正确但要求未满足，以及虽通过更强检查却结果错误。
◆利用oracle输入诊断表明更完整的目标观察与校准反馈能改善最终空间判断。</td></tr>
<tr><td>2026-11-24</td><td>CAPER: PartGround and PlanRefine for Reliable Manual-Guided Robotic Assembly Planning<br><a href='http://arxiv.org/pdf/2611.32986'>论文</a> | <a href='https://xhzzzz123.github.io/CAPER/'>代码</a></td><td>本文提出CAPER，一个面向手册引导机器人装配规划的VLM框架，用于解决零件身份混淆、无依据Part ID和跨步骤零件不一致等问题。
◆ PartGround将步骤级手册证据与产品专属库存和零件参考信息对齐，识别精确Part ID与数量，把自由形式硬件预测转化为证据引导分配并写入共享Assembly IR。
◆ PlanRefine依据有限库存审计PartGround分配，剔除最低置信度分配，并在Assembly IR中标记不确定身份案例供复核。
◆ CAPER以共享Assembly IR和证据约束实现零件级可追溯规划，提升有限库存条件下的可靠性。
在IAW数据集上，CAPER达到83.33%有限库存一致性率，未观察到超出库存的Part-ID，并将库存过度使用对9→0、多余单元51→0。
结果表明PartGround与PlanRefine提升了零件可靠性、有限库存一致性和局部预测准确率。</td></tr>
<tr><td>2026-11-24</td><td>Atomic Policy: Composing Atomic Manipulation Skills with Agentic Reasoning<br><a href='http://arxiv.org/pdf/2611.32813'>论文</a> | <a href='https://aaronzkd.github.io/atomic-policy/'>代码</a></td><td>Atomic Policy提出一个面向长程操作的分层技能组合框架，将VLM的语义空间推理与视动策略的精细控制相衔接。
◆用VLM估计符号状态与目标，并由PDDL求解器生成技能计划，从而把任务意图转化为可执行的动作序列。
◆引入agentic harness，通过语言、视觉指向或二者结合引导每项技能，并验证执行结果以驱动阶段转换和重规划。
◆设计统一的阶段级接口，兼容专用操作策略与通用动作模型，提升技能组合的扩展性。
仿真和真机实验表明，该框架能改善任务遵循性，并在复杂长程操作中支持失败恢复与重规划。
这些设计共同缓解了模糊目标与动作依赖带来的集成难题，实现了学习技能与智能体推理的闭环组合。</td></tr>
<tr><td>2026-11-24</td><td>CoFiNav: VLM-Guided Coarse-to-Fine Semantic Navigation for Open-Ended Last-Mile UAV Delivery<br><a href='http://arxiv.org/pdf/2611.32493'>论文</a></td><td>论文针对现有无人机末端配送依赖精确坐标、预定义终端规格或任务专用定位流程的问题，提出支持开放语义描述终端的语义导航新范式。作者设计了CoFiNav，一个由视觉语言模型引导的粗到细无人机语义导航框架，通过层级语义搜索和主动三维观察逐步定位由空间关系定义的配送目的地。
◆ 创新性地利用VLM根据任务描述、OSM粗先验地图和累积观察，自主决定下一步应验证的未解析实体或空间关系。
◆ 提出几何感知模块，将语义观察请求转化为基于RGB图像和LiDAR的可行视点，并由常规运动规划保障安全执行。
◆ 构建了面向开放词汇末端导航的粗到细语义搜索机制，降低对精确终端坐标和预定义规格的依赖。
实验表明，CoFiNav在多个城市环境中相较代表性适配基线具有更高成功率，同时飞行路径更短、所需观察次数更少。</td></tr>
<tr><td>2026-11-24</td><td>LookAnything: A Foundation Model for Holistic Gaze Following<br><a href='http://arxiv.org/pdf/2611.32351'>论文</a></td><td>LookAnything提出面向整体视线跟随的基础模型，统一多样以视线为中心的任务，突破传统方法依赖头部裁剪或深度图等辅助输入、单域训练和单一热图输出的局限。  
◆ 设计可学习视线先验查询，促进视线感知表征学习，从模型层面消除外部辅助输入依赖并减少级联误差与推理开销。  
◆ 构建HoliGaze大规模多任务跨域语料与基准，包含31.1万问答对、5种能力维度和9类任务，支撑统一训练与系统评测。  
◆ 通过大规模多任务跨域训练，模型可灵活生成点、框、热图和语言等多样输出，覆盖视线定位、描述与推理等广泛场景。  
实验表明LookAnything在整体视线跟随上持续优于33个领先视觉语言模型，并在5个传统目标检测基准上与专用专家保持竞争力，且在未见数据集和真实机器人部署中展现强跨域泛化与灵活适应。</td></tr>
<tr><td>2026-11-24</td><td>VLAs Execute, Code Recovers: 3D Skill Envelopes Bridge the Compositional Gap in Agentic Manipulation<br><a href='http://arxiv.org/pdf/2611.32245'>论文</a></td><td>标准重定位或语言前置条件忽略了接缝失败的物理原因：冻结VLA即使重新归位仍会刚性重放习惯轨迹，并碰撞被位移的场景残留。
◆提出Skill Envelope，即由策略测量、刻画冻结技能成功执行时扫过体积的3D几何前置条件。
◆利用刚性使冻结技能轨迹可提前预测，将包络暴露为CHECK检测阻挡残留和FREE定位安全放置区，形成VLA执行分布内操作、代码修复分布外状态的分工。
◆在LIBERO-Goal冻结π0.5上，零失败包络以0.946 AUROC预测碰撞（单RGB-D视图0.944），接缝准备度0.902超过前沿VLM的0.793。
◆用于技能排序与代码修复后，两步接缝成功率由82.8%升至92.3%，含抽屉的3-4步链由29.7%升至93.8%，匹配特权世界重置。
结论是可靠VLA组合的关键在于测量策略的物理工作空间，而非用语言猜测前置条件。</td></tr>
<tr><td>2026-11-24</td><td>Seeing Is Not Reaching: Instruction Shortcuts Override Visual Grounding in Vision-Language-Action Models<br><a href='http://arxiv.org/pdf/2611.32206'>论文</a></td><td>论文揭示视觉-语言-动作模型在物体被移动后常仍伸向训练位置，提出“Seeing Is Not Reaching”，说明视觉定位未必转化为正确动作。
◆识别出场景捷径和指令捷径两类问题：前者使机械臂沿用场景原任务而忽略新指令，后者使指令直接检索物体的训练位置。
◆通过分别掩蔽图像介导的定位通路和直接指令到动作通路，证明视觉定位已能引导动作，但常被指令捷径经直接通路覆盖。
◆提出Pathway-Separated Guidance（PSG），无需训练或外部目标位置，即可放大视觉定位并抑制指令捷径。
◆在LIBERO-PRO Object位置扰动任务上，PSG将目标到达率从22.0%提升至52.6%，任务成功率从16.6%提升至40.8%，并基本保持原任务性能。
总体而言，论文不仅诊断了VLA中“看见但够不到”的捷径机制，还给出了无需训练的干预方法。</td></tr>
<tr><td>2026-11-24</td><td>RoboProbe: Benchmarking Physical Plausibility of Robot World Models<br><a href='http://arxiv.org/pdf/2611.32152'>论文</a></td><td>本文面向机器人世界模型生成视频的物理合理性评估，指出现有VLM难以完成证据驱动的时空推理，未检测的物理违例会危害动作可行性与安全性判断。
◆提出接触保真、物体持久性、固体性、机器人形变和物体形变五项物理规律专用指标，融合分割、跟踪、3D几何或外观比较与定向VLM推理。
◆构建RoboProbe智能体评估框架，协调各指标执行，并通过受限动作选择性细化评估。
◆发布RP-Bench基准，包含761个人工标注生成视频，以及来自12个机器人数据集、239项操作任务的130条真实演示。
实验表明五项指标AUROC均超0.85，优于学习型评判器、已有评估器和仅用帧的Gemini基线。
将其用于五种视频生成器，揭示不同模型在物理违例类型与频率上的显著差异。</td></tr>
<tr><td>2026-11-24</td><td>RoboHarness-RL: Agentic Reinforcement Learning for VLM-Based Robot Manipulation<br><a href='http://arxiv.org/pdf/2611.32016'>论文</a> | <a href='https://aim-uofa.github.io/RoboHarness-RL/'>代码</a></td><td>本文提出RoboHarness-RL，一个面向基于VLM的机器人操作的智能体强化学习框架，通过工具调用完成感知、规划与控制。
◆ 采用“教师示范监督微调+多轮任务结果奖励强化学习”的两阶段训练，使紧凑开源VLM无需VLA或世界动作模型也能提升操作能力。
◆ 设计LiteHarness，用分层记忆压缩多轮交互上下文，在保持任务性能的同时支持高效多轮训练。
◆ 在Qwen3.5-9B上，RoboTwin 2.0成功率由31.2%升至44.0%，LIBERO-Pro由57.8%升至73.3%，随机化RoboTwin场景由26.4%升至38.0%。
◆ 行为分析表明RL将重复调用率最多降低4倍，缩短成功执行时长，并增强从负反馈中恢复的能力。
核心贡献在于验证了基于工具调用的智能体RL可显著提升紧凑开源VLM的机器人操作表现并具备泛化收益。</td></tr>
<tr><td>2026-11-24</td><td>VLG-Drive: Unifying Vision-Language and Geometric Priors for Autonomous Driving<br><a href='http://arxiv.org/pdf/2611.31952'>论文</a></td><td>本文提出VLG-Drive，将视觉语言模型的场景语义与几何基础模型的空间结构统一用于自动驾驶规划，并在冻结两个基础模型的前提下仅训练融合接口和规划器。◆设计几何锚定的残差融合接口，在每个相机网格单元将配对的VLM特征与几何特征融合为联合token。◆采用命令条件规划器读取联合token并预测自车轨迹，使轻量规划器能直接利用冻结多模态特征。◆通过点式融合验证联合token优于独立VLM流和几何流，为融合两类基础模型提供了有效接口。在NavHard扰动初始状态下取得31.78 EPDMS，在NavTest仅用摄像头取得88.27 PDMS。在420个HUGSIM闭环场景中优于所有对比规划器，表明融合冻结视觉语言与几何基础模型特征并训练轻量规划器，是替代适配任一模型进行规划的有效方案。</td></tr>
<tr><td>2026-11-23</td><td>Pruning Autonomous Driving VLAs: What to Preserve for Reasoning and Action<br><a href='http://arxiv.org/pdf/2611.31240'>论文</a></td><td>论文针对推理型自动驾驶VLA模型的高内存与计算开销，系统研究结构化剪枝，并强调同时保留场景理解与轨迹预测能力。
◆通过分析Alpamayo-1.5-10B中的Taylor重要性，揭示推理与轨迹目标对同一VLM结构赋予不同重要性，且动作专家中MLP通道跨去噪步的重要性排序比query头更稳定，少量通道承载大部分重要性。
◆提出MoOP方法，融合推理与轨迹两种目标的重要性排名进行VLM剪枝，并聚合逐步重要性以选择固定的专家MLP通道子集。
在总参数减少24.0%时，仅剪VLM的MoOP在驾驶性能上可比或略优于最强基线，并保留94.0%的LingoQA分数，显著优于其他方法。
在30.0%更高压缩下，MoOP退化最小且是唯一推理不崩溃的方法；移除93.75%专家MLP通道后总参数减少39.4%，开环误差几乎不变且闭环表现有竞争力。
最终模型无需剪枝后微调即实现1.37倍端到端推理加速和36.6%的峰值内存降低。</td></tr>
<tr><td>2026-11-23</td><td>EmboEagle: An Efficient Agentic Embodied Framework for Long-horizon Robotic Manipulation<br><a href='http://arxiv.org/pdf/2611.31173'>论文</a></td><td>EmboEagle提出面向长时程机器人操作的闭环智能体框架，统一子任务条件WAM控制、潜空间自适应监督与记忆引导几何恢复。
◆采用解耦两阶段流匹配适配序列WAM，保留跨阶段视觉历史并在子任务边界校准截断动作监督。
◆无需辅助视觉编码器，将教师干预决策蒸馏为轻量路由门，仅依赖WAM动作专家块前后潜在转移和子任务嵌入。
◆VLM调用时将诊断状态与离散路由动作解耦，基于结构化记忆执行参数化恢复原语并强制修复后验证。
在RMBench和LIBERO-Mem上平均成功率分别达91.3%和90.6%，较最强基线提升8.0和9.8个百分点；相同执行器权重下真实世界优于VoLoAgent，自适应门控较逐块监控减少74.2%的VLM调用。</td></tr>
<tr><td>2026-11-23</td><td>FATCAT: Fault Injection Attacks Targeting Chip-level Alignment<br><a href='http://arxiv.org/pdf/2611.31129'>论文</a></td><td>本文提出FATCAT，首个能消除现代大语言模型和视觉语言模型拒绝行为的物理故障注入攻击。
◆首次实现面向可物理接触GPU加速SoC的非侵入式电磁故障注入，无需软件执行权限和模型层访问。
◆设计自主RF侧信道触发器，将电磁故障同步到提示词预填充阶段，精准破坏片外LPDDR5 DRAM和片上LPDDR物理接口中的安全关键内存事务，且不使系统崩溃并保持模型连贯。
◆在NVIDIA Jetson Orin Nano与AGX Thor上运行Llama 3.2 1B和Gemma 3 1B验证，局部物理故障可可靠迫使模型执行受限请求。
◆在6自由度机械臂的SmolVLA策略上展示真实后果，攻击可静默诱发突发危险动作，甚至造成人身伤害风险。
这表明模型级对齐在缺乏硬件级容错时无法提供稳健安全保证。</td></tr>
<tr><td>2026-11-23</td><td>SurgeCount: A Protocol-Guided Composition Harness for Bimanual Surgical Sponge Counting<br><a href='http://arxiv.org/pdf/2611.31037'>论文</a></td><td>SurgeCount提出一种面向机器人手术海绵计数的可审计系统，在书面流程协议指导下组合已学习技能，让机器人反复从纠缠海绵堆中分离单个可变形海绵并放入下一个编号托盘槽。
◆ 它将11个短技能统一训练为一个子任务条件策略，并学习每个技能的终止边界，从而形成对子任务的时间承诺。
◆ 在每个学习到的技能边界，由有状态视觉语言模型依据操作者编写的步骤顺序、视觉验证和恢复规范选择下一技能，实现协议引导的长程组合。
◆ 失败恢复不依赖专用恢复策略，而是通过重新组合已有技能完成，增强了系统的可审计性和复用性。
在100次真实机器人试验和20种匹配布局中，SurgeCount填充47/60个有序槽并完成12/20次流程，显著优于同数据训练的最强端到端策略（27/60和3/20）；将详细协议提示替换为最小提示后降至29/60和5/20。
结果表明长程性能不仅取决于视觉运动能力，还取决于学习技能如何被承诺、验证和组合；该工作作为桌面概念验证，支持在更接近临床场景中进一步评估协议引导的机器人海绵计数。</td></tr>
<tr><td>2026-11-23</td><td>Parsing Visual Latents for Multimodal Spatial Reasoning<br><a href='http://arxiv.org/pdf/2611.31021'>论文</a> | <a href='https://github.com/Harvard-AI-and-Robotics-Lab/LatentParse'>代码</a></td><td>论文提出无需训练的LatentParse框架，将CLIP、DINOv3和VGGT等预训练视觉编码器中的潜在特征解析为显式空间证据，供视觉语言模型使用。
◆利用分析VLM和预定义工具探测多编码器特征，实现物体定位、跨视角跟踪和视角间运动测量。
◆将工具探测结果蒸馏为简洁文本报告，并与图像共同输入VLM，解决直接输入灰度特征图无效的问题。
◆在MMSI-Bench、MV-RoboBench和SPAR-Bench上，使五个VLM平均提升0.7至2.4个百分点。
在MMSI-Bench上，Qwen3.8-27B从34.4%提升至39.5%，相机相关问题最大提升19.2个百分点。
结果表明，潜在特征一旦被解析为关系证据，无需训练即可有效增强多视角空间推理。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-visual-semantic-recognition'>Robot Visual Semantic Recognition</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-18</td><td>Does the Action Matter? Probing Action-Conditioned Semantic Forecasting as a World Model for Autonomous Driving<br><a href='http://arxiv.org/pdf/2611.24840'>论文</a> | <a href='https://github.com/binayksingh/does-action-matter'>代码</a></td><td>论文核心贡献是提出并检验动作条件语义预测是否真正依赖动作，而非仅评估预测精度与规划性能。作者比较特征级与输入级动作条件模型和无动作输入的相同模型，用测试时动作干预和分割指标量化动作依赖性，并在合成环境、Cityscapes、BDD100K及跨车辆平台上验证。实验表明执行动作带来的mIoU提升有限，而错误动作会显著降低性能甚至低于无动作模型；真实数据上特征级条件比输入级条件更依赖动作约1.6倍，说明精度增益不能代表动作依赖强度。
◆提出以测试时动作干预衡量动作条件世界模型依赖性的评估框架。
◆系统比较特征级与输入级动作条件方式，并揭示真实数据与合成环境中的依赖差异。
◆发现预测精度与动作依赖强度解耦，为自动驾驶世界模型评估提供新准则。</td></tr>
<tr><td>2026-11-18</td><td>ALIVE: Bring Foundation Features to Life with Events<br><a href='http://arxiv.org/pdf/2611.24579'>论文</a></td><td>论文提出ALIVE，一种基于事件的方法，在两次图像观测之间增量更新视觉基础模型特征，避免反复运行昂贵的图像编码器。
◆ 利用后续事件对冻结DINOv3编码器提取的多层锚点图像特征进行传输与校正，实现基础模型特征的持续刷新。
◆ 设计轻量级特征更新器，仅用合成数据端到端训练，无需下游任务监督，并可零适配直接迁移到真实事件流。
◆ 在检测、语义分割和深度估计等五个任务-数据集设置中，ALIVE在所有指标上均优于所有评估的基于事件方法。
在DSEC上，当锚点帧已过时200ms，ALIVE使检测提升30.9 mAP、分割提升11.6 mIoU、深度AbsRel改善15.9%。
相比图像重编码，ALIVE减少82.4% FLOPs并将延迟降低2.5倍。</td></tr>
<tr><td>2026-11-10</td><td>HiPFuse: Real-Time LiDAR Semantic Segmentation for Robotic Perception on Edge Devices<br><a href='http://arxiv.org/pdf/2611.14025'>论文</a> | <a href='https://github.com/haiyang2022/HiPFuse'>代码</a></td><td>本文提出HiPFuse，一种面向边缘设备机器人实时感知的点-BEV融合LiDAR语义分割框架，在单帧扫描中兼顾点级细节与二维空间上下文。
◆ 设计跨水平尺度的点与高度划分BEV特征交换机制，减少BEV列内不同标签表面混合。
◆ 采用固定高度分配保留独立垂直聚合组，并用同一3D单元目标对初始BEV特征进行辅助监督。
◆ 引入双尺度BEV上下文模块，从更粗网格获取更广空间上下文。
在SemanticKITTI和MCD上分别达到63.7%和62.5% mIoU，Jetson AGX Orin上达14.2和22.4 FPS，超过10 Hz扫描率，并验证室内适用性。
仅替换固定机器人系统中的基线语义前端，即可使两个室外序列ATE RMSE平均降低10.6%，SemanticKITTI闭环召回提升8.7个百分点，语义地图道路标注更连续。</td></tr>
<tr><td>2026-11-06</td><td>ATLAS: A Multi-Procedure Benchmark and Context-Aware Model for Surgical Anatomy Segmentation<br><a href='http://arxiv.org/pdf/2611.10182'>论文</a> | <a href='https://github.com/TimJaspers0801/ATLAS'>代码</a></td><td>本文针对微创手术解剖识别受限于小型单术式数据集和自然场景分割方法的问题，提出跨术式数据集与上下文感知视频分割模型。
◆ 构建ATLAS-120k数据集：含100段手术视频、121,018帧、14种腹腔镜与机器人辅助术式及41类，标注流程融合人工标注、跟踪传播和外科医生审核。
◆ 提出ATLAS模型：基于域内基础模型嵌入，加入术式与手术阶段上下文查询，并用帧间查询传播形成短期记忆。
实验表明ATLAS在分割精度和时序一致性上优于自然图像及域内基础模型，ViT-L达Dice 0.70且76.2 FPS实时；消融验证上下文查询提升精度、查询传播提升时序一致性。
它还能零样本在CholecSeg8k上匹配专用模型，并在AutoLaparo阶段识别上优于SurgeNet初始化，相关权重、标注和工具已开源。</td></tr>
<tr><td>2026-11-03</td><td>Role-based Effectiveness of an Epistemic Uncertainty Estimate in Training Models for Semantic Segmentation of 3D LiDAR Point Clouds<br><a href='http://arxiv.org/pdf/2611.05569'>论文</a></td><td>本文系统研究认知不确定性估计在3D LiDAR点云语义分割训练中的多重作用，而不仅将其用于提升精度。
◆首次将显式建模的认知不确定性同时作为额外输入特征和逐样本置信权重引入分割训练，比较其不同角色效果。
◆在四个跨机载与移动采集的大规模LiDAR基准上，采用空间不相交训练测试划分，并对比PointNet++、RandLA-Net及其不确定性增强版本进行统一评估。
◆实验表明不确定性感知建模可提升平均IoU，并恢复基线完全漏判的少数类。
◆在一半配置中，该方法还改善了预测误差与估计不确定性之间的对齐，以Patch Accuracy versus Patch Uncertainty衡量。
总体贡献是揭示不确定性可作为分割流程中的多角色信息，而不仅是精度提升装置。</td></tr>
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
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vpr'>Robot VPR</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-11-18</td><td>What Should Visual Place Recognition Be Invariant To? Rethinking Condition Invariance in Visual Place Recognition<br><a href='http://arxiv.org/pdf/2608.06847'>论文</a></td><td>这篇论文针对长期视觉位置识别（VPR）中的关键问题展开研究，指出当前VPR方法在匹配过程中容易受光照、天气、季节等条件信息干扰，可能依据条件相似性而非地点身份进行检索。

◆ 提出Distractor-Augmented Recall（DAR）评估指标，通过向数据库注入干扰图像来分离和量化干扰物的影响，揭示现有方法在标准Recall@1下的排名与DAR@1排名存在显著差异。

◆ 提出对VPR描述子进行条件抑制，采用INLP和LEACE方法去除描述子中编码的照明、天气、季节等条件信息。

◆ 在11种VPR方法和6个数据集上的实验表明，条件抑制普遍提升DAR@1性能而不降低标准R@1，证实抗干扰鲁棒性与标准检索性能是相互独立的维度。

该研究的核心贡献在于揭示了VPR模型&quot;识别地点还是识别条件&quot;这一被忽视的问题，为构建更鲁棒的VPR系统提供了新的评估框架和解决方案。</td></tr>
<tr><td>2026-11-16</td><td>Beyond Appearance: Where Forest Visual Place Recognition Actually Fails<br><a href='http://arxiv.org/pdf/2611.21996'>论文</a></td><td>本文在WildCross基准上以MegaLoc为外观基线，系统评估时序、语言、结构与几何上下文能否超越纯外观森林视觉位置识别，并分析各表示的失效边界。
◆ 构建统一评估框架，联合考察score/descriptor序列匹配、视觉语言描述与重排、场景图及LiDAR深度茎干图等多类上下文表示。
◆ 发现同向重访中score-space序列匹配在高精度区显著优于单帧基线，100%精度下召回率由50.9%升至71.6%，而descriptor-space反而降至36.5%。
◆ 揭示其余上下文缺乏稳定增益：描述地点判别力有限、重排受初始候选表约束、茎干图即使有LiDAR深度仍较弱。
结论表明森林VPR的瓶颈不仅在外观相似，更在于上下文表示的判别力与候选覆盖不足。</td></tr>
<tr><td>2026-11-14</td><td>Breaking Déjà Vu: Independent Auditing of Visual Place Recognition through Vision-Language Reasoning<br><a href='http://arxiv.org/pdf/2607.12818'>论文</a></td><td>本文针对真实部署中VPR匹配阈值依赖标注验证数据、环境变化下不可靠的问题，提出独立的后检索验证框架Visual Place Recognition Auditing。
◆ 将视觉语言模型引入VPR验证，通过联合推理查询图像与候选图像实现实例级匹配审核，而非依赖传统置信度或固定阈值。
◆ 该方法无需架构特定置信度、数据集相关阈值或部署环境先验知识，可作为独立模块对现有VPR方法进行事后验证。
◆ 在六个基准数据集上结合五种先进VPR方法和四种视觉语言模型进行系统评估。
结果显示，该方法相较先进方法平均提升recall@1 13.6%，将误接受率降至12%，同时保持精度高于95%、覆盖率高于75%。
这提升了环境变化和安全关键场景下VPR部署的可靠性。</td></tr>
<tr><td>2026-11-03</td><td>Sparse Anchors for Visual Multi-Session Registration in Changing Environments<br><a href='http://arxiv.org/pdf/2611.05084'>论文</a></td><td>论文面向变化环境下的视觉多会话注册，将新查询会话轨迹对齐到已有参考地图，解决显著视觉与结构变化导致跨会话对应仅部分可用的问题。  
◆提出以稀疏但可靠的绝对位姿锚点结合会话内相对位姿约束，通过鲁棒位姿图优化完成整条查询轨迹的注册。  
◆利用视觉地点识别、局部特征匹配和几何验证生成绝对对齐假设，并用序列一致性剔除不一致假设以保留锚点。  
◆采用高斯特征场上的特征度量对齐对锚点进行细化，提高绝对约束精度。  
◆在HILTI26的15个跨会话实验上验证，1米召回率达94.4%、5米召回率达100.0%，优于独立图像定位和直接SfM几何注册。  
总体贡献是证明即使仅部分查询会话存在可靠跨会话对应，稀疏可靠锚点也能实现准确且完整的轨迹注册。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5414</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4907</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2493</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1665</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1632</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1546</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1394</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1323</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1151</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>1122</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>957</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>820</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>786</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>752</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>748</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>737</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>709</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>682</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>640</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>636</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>626</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>597</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>573</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>551</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>518</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>485</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>472</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>377</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>351</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>282</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>275</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>259</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>245</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>235</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>231</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>223</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>223</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>217</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>156</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>148</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>124</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2893</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1689</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1374</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1099</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1065</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>889</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>715</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>674</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>671</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>623</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>621</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>582</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>579</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>571</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>556</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>525</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>520</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>466</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>459</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>455</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>356</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>334</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>310</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>305</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>292</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>278</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>259</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>246</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>224</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>208</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>203</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>188</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>177</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>171</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>169</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>160</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>157</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>143</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>139</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/data-driven-dynamics'>data-driven-dynamics</a></td><td>135</td><td>Data Driven Dynamics Modeling for Aerial Vehicles</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>132</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
<tr><td><a href='https://github.com/ethz-asl/phaser'>phaser</a></td><td>132</td><td>A robust pointcloud registration pipeline based on</td></tr>
<tr><td><a href='https://github.com/ethz-asl/ssc_exploration'>ssc_exploration</a></td><td>112</td><td>Incremental 3D Scene Completion for Safe and Effic</td></tr>
<tr><td><a href='https://github.com/ethz-asl/active_grasp'>active_grasp</a></td><td>112</td><td>Closed-loop next-best view planning for grasp dete</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waypoint_navigator'>waypoint_navigator</a></td><td>108</td><td>Stand-alone waypoint navigator</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waverider'>waverider</a></td><td>107</td><td>RMPs on multi-resolution occupancy maps for effici</td></tr>
<tr><td><a href='https://github.com/ethz-asl/reinmav-gym'>reinmav-gym</a></td><td>106</td><td>Reinforcement Learning framework for MAVs using th</td></tr>
<tr><td><a href='https://github.com/ethz-asl/navrep'>navrep</a></td><td>106</td><td>navrep</td></tr>
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>105</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/eth_supermegabot'>eth_supermegabot</a></td><td>102</td><td>Instructions for ETH center for robotics summer sc</td></tr>
<tr><td><a href='https://github.com/ethz-asl/3d_vsg'>3d_vsg</a></td><td>102</td><td>3D可变场景图，用于长期语义场景变化预测。</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.11.25
