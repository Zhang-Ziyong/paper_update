# 计算机视觉领域最新论文 (2026.06.23)

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
<tr><td>2026-06-22</td><td>HERCULES: An Open-Source Simulation Framework for Heterogeneous Multi-Robot SLAM, Collaborative Perception, and Exploration<br><a href='http://arxiv.org/pdf/2606.22756'>论文</a> | <a href='https://lunarlab-gatech.github.io/HERCULES-website'>代码</a></td><td>◆ HERCULES提出了一个开源的异构多机器人仿真与数据采集框架，支持UAV与UGV在大规模、照片级真实、动态环境中并发运行。

◆ 它突破了AirSim/Cosys-AirSim的架构限制，引入与UAV接口一致的UGV航点跟踪控制器，并提供跨平台共享的导航、建图、可通行性分析、规划与控制栈。

◆ 框架扩展了传感器能力，加入物理建模的长波红外相机和可配置夜视模式，增强了退化视觉环境下的感知研究能力。

◆ HERCULES提供轻量API、ROS 2封装和严格的多传感器多平台时间同步，并集成行人、交通、野生动物、火灾、洪水等高保真动态要素。

◆ 它支持离线轨迹回放的数据生成模式和在线闭环规划模式，并通过SLAM、协同感知和探索实验验证了其在异构多机器人自主研究中的实用价值。</td></tr>
<tr><td>2026-06-21</td><td>Reference-Free Assessment of Physical Consistency in World Model-based Video Generation<br><a href='http://arxiv.org/pdf/2606.22363'>论文</a></td><td>◆本文提出一种无需参考视频的生成视频物理一致性评估框架，用于衡量世界模型视频生成中的物理保真度。
◆方法结合相对评估与绝对评估，避免依赖昂贵的人类投票或难以获得的真实参考视频。
◆其核心技术利用DROID-SLAM和SEA-RAFT量化几何、运动等物理不一致性，受WorldScore思想启发。
◆实验表明，经相对一致性筛选的视频可使任务成功率提升超过8%，有效缩小仿真到现实的差距。
◆绝对评估还能进行时空定位，直观显示物理伪影出现的时间和位置，增强评估的可解释性。</td></tr>
<tr><td>2026-06-20</td><td>ACEsplat: Accelerated 3D Gaussian Scene Regression via RGB and Poses Only<br><a href='http://arxiv.org/pdf/2606.22091'>论文</a></td><td>◆ ACEsplat提出了一种仅依赖RGB图像和相机位姿的快速逐场景3D Gaussian重建框架，避免了SfM点云、深度图等外部几何先验。

◆ 其核心创新是两阶段流程：先用自监督场景坐标回归模块在数分钟内构建内部几何先验，再用于后续高斯初始化与优化。

◆ 论文设计了轻量级Gaussian初始化头，将SCR特征与坐标先验融合，提升无外部3D信息条件下的3DGS初始化质量。

◆ 实验表明，该方法在Wayspots、Cambridge Landmarks和RealEstate10K等数据集上取得有竞争力的渲染质量，适用于静态视角和稀疏视角新视角合成。

◆ ACEsplat可在单GPU上15到25分钟内完成场景映射与3DGS重建，为机器人和混合现实中的快速现场建图提供了实用方案。</td></tr>
<tr><td>2026-06-20</td><td>GeoFlow-SLAM++: A Robust Multi-Camera Visual-Inertial SLAM System with Relocalization<br><a href='http://arxiv.org/pdf/2606.22051'>论文</a></td><td>◆提出GeoFlow-SLAM++，将原GeoFlow-SLAM从单RGB-D扩展为标定多相机视觉惯性SLAM，并采用统一的以机体为中心的紧耦合状态表示。
◆系统在同一多相机框架下支持可互换的ORB前端与基于SuperPoint/LightGlue的神经网络特征前端，增强了外观变化场景下的鲁棒性。
◆统一整合跟踪、建图与重定位，结合多相机重投影约束、IMU预积分、跨视角地点识别和光流/NN特征双流跟踪。
◆引入可选的跨视角一致伪深度约束，使仅RGB输入也能获得额外几何信息辅助定位。
◆在EuRoC、OpenLORIS、TUM、Hilti及自采多相机数据集上的实验表明，该方法在鲁棒性、定位精度和跨会话重定位方面均具有竞争力，手持数据上达到接近LiDAR的表现。</td></tr>
<tr><td>2026-06-19</td><td>Spectral GS-SLAM: Observability-Aware, Degeneracy-Robust Tracking for Real-Time 3D Gaussian Splatting SLAM<br><a href='http://arxiv.org/pdf/2606.21258'>论文</a></td><td>◆提出Spectral GS-SLAM，将ICP跟踪与互补的特征约束结合，面向实时3D Gaussian Splatting SLAM中的退化与弱纹理场景。
◆通过可观测性/谱分析识别ICP优化中的欠约束方向，并自适应补偿信息，缓解几何退化导致的病态和数值不稳定。
◆补偿机制不干扰用于建图的共享高斯表示，在增强跟踪鲁棒性的同时保持3DGS实时建图框架的简洁性。
◆引入高斯感知的平面性加权，利用3D高斯协方差刻画局部几何结构，指导几何与特征信息融合。
◆在TUM RGB-D挑战序列上实现40.14 FPS，并在结构缺失和特征缺失环境中保持稳定跟踪。
◆总体上，该方法在退化场景中保持轨迹完整性，同时在常规场景下维持有竞争力的精度与实时性。</td></tr>
<tr><td>2026-06-19</td><td>Ultra-Fusion: A Resilient Tightly-Coupled Multi-Sensor Fusion SLAM Framework under Sensor Degradation and Spatiotemporal Perturbation for Intelligent Transportation Systems<br><a href='http://arxiv.org/pdf/2606.21223'>论文</a></td><td>◆提出Ultra-Fusion，一个面向智能交通场景的紧耦合多传感器SLAM框架，旨在应对光照差、LiDAR退化、轮滑、GNSS中断等传感器失效问题。
◆设计统一滑动窗口估计器，将异步传感器数据按时间戳排序并转化为可选因子，统一支持WIO、VIO、LIO、LVIO及轮速/GNSS增强。
◆引入可观测性感知初始化机制，可根据场景条件自适应选择更可靠的启动模式，提升系统冷启动鲁棒性。
◆提出因子级可靠性调度，对退化测量进行门控或降权，减少异常传感器对定位结果的破坏。
◆实现在线LiDAR-IMU时空标定，可在运行中修正时间偏移和旋转外参，并通过多数据集与60余种开源SLAM对比验证了跨平台、长时高速和退化场景下的竞争性精度与可用性。</td></tr>
<tr><td>2026-06-18</td><td>UNSEEN: Uncertainty-aware Navigation via Sparse Estimation in Unknown Environments<br><a href='http://arxiv.org/pdf/2606.20755'>论文</a></td><td>◆提出UNSEEN，一个仅依赖前视相机的统一导航框架，将定位、建图与规划显式耦合，面向未知环境中的轻量化移动机器人。
◆方法以6Hz估计稀疏地图、机器人位姿及其不确定性，并将这些信息贯穿整个导航链路。
◆在规划层采用滚动时域优化，同时权衡任务推进与感知/估计质量，避免盲目执行导致定位退化。
◆相比传统松耦合或单模块感知-aware方法，UNSEEN能一致传播不确定性，更好应对运动模糊、弱纹理和光照变化。
◆实验表明，UNSEEN-SLAM将绝对平移误差降低9.8%，UNSEEN-Plan最高提升45%估计精度，并实现100%任务成功率。</td></tr>
<tr><td>2026-06-18</td><td>Towards 3D karst underwater scene reconstruction from rotating sonar data<br><a href='http://arxiv.org/pdf/2606.20322'>论文</a></td><td>本文面向喀斯特含水层水下探测中声呐稀疏、噪声强且导航漂移严重的问题，提出了一套从旋转声呐数据重建三维水下通道场景的完整流程。
◆ 将连续时间SLAM用于校正水下航迹漂移，提高了声呐剖面在三维空间中的配准精度。
◆ 提出两阶段深度学习表面重建方法，从稀疏噪声声呐观测中恢复更连续的洞穴/管道表面。
◆ 将运动估计校正与学习式几何重建结合，突破传统三维重建方法对精确导航和密集观测的依赖。
◆ 最终生成可沉浸式浏览和导航的三维网格，为水文地质分析和喀斯特管道结构理解提供支持。</td></tr>
<tr><td>2026-06-18</td><td>Gaussian Process Prior Variational Autoencoder for Endoscopic Videos<br><a href='http://arxiv.org/pdf/2606.19908'>论文</a></td><td>◆论文提出面向内窥镜视频修复的GPVAE框架，用时间高斯过程先验替代传统VAE的独立潜变量先验，从而更好利用视频帧间连续性。

◆该方法支持缺失帧插值和不确定性感知重建，可为恢复结果提供逐帧置信度估计。

◆模型结合EndoVAE卷积编码器与GastroNet-5M预训练ViT编码器，并引入HPA和SPA两种可扩展GP近似以提升实用性。

◆针对镜面反射，论文使用DUCKNet掩膜管线在训练目标中排除受污染像素，增强了内窥镜场景适配性。

◆在C3VDv2数据集上，GPVAE相较匹配VAE基线平均降低重建RMSE 21.9%，最高达26.1%，同时下游轨迹RMSE平均降低12.7%，代价是每轮训练时间平均增加27.3%。</td></tr>
<tr><td>2026-06-18</td><td>MMD-SLAM: Structure-Enhanced Multi-Meta Gaussian Distribution-Guided Visual SLAM<br><a href='http://arxiv.org/pdf/2606.19874'>论文</a></td><td>◆ 提出MMD-SLAM，一个结构增强的3DGS视觉SLAM框架，利用Atlanta World假设引入场景主方向先验，提升地图一致性与渲染质量。
◆ 设计点-线融合位姿优化策略，将3D线段纳入跟踪过程，为相机位姿估计提供更强几何约束。
◆ 提出Multi-Meta Gaussian表示，显式编码主导方向和结构信息，使高斯地图更符合真实场景布局。
◆ 引入自适应Gaussian evolution策略，根据场景几何动态优化高斯，并在全局优化中融入结构线索。
◆ 实验表明该方法在跟踪精度和建图质量上达到先进水平，相比MonoGS在ScanNet上ATE RMSE降低48.56%，在Replica上PSNR提升5.71%。</td></tr>
<tr><td>2026-06-17</td><td>FAST-LIVGO: A Degeneracy-Robust LiDAR-Inertial-Visual-GNSS Fusion Odometry<br><a href='http://arxiv.org/pdf/2606.19190'>论文</a></td><td>◆ FAST-LIVGO提出一种基于误差状态迭代卡尔曼滤波的紧耦合LiDAR-惯性-视觉-GNSS融合里程计，面向长距离、大尺度和动态环境中的稳健定位建图。
◆ 其在线时空对齐模块引入动态时间规整，提升多传感器在高速和强动态条件下的同步与融合可靠性。
◆ 方法设计了基于多普勒频移和固定锚点时间差分载波相位的GNSS观测模型，在不增广历史状态的情况下提供毫米级相对约束。
◆ 针对几何退化或纹理缺失场景，提出退化感知的双模式外点剔除策略，可在LIVO先验引导和GNSS辅助恢复之间自适应切换。
◆ 在M3DGR和20 m/s固定翼无人机数据集上的实验表明，该系统显著降低累计漂移和地图重影，精度与鲁棒性优于现有方法。</td></tr>
<tr><td>2026-06-17</td><td>Sensor Configuration Matters: A Systematic Evaluation of Multimodal SLAM on Quadruped Robots<br><a href='http://arxiv.org/pdf/2606.19067'>论文</a></td><td>◆论文针对四足机器人腿式运动带来的冲击、振动和快速旋转问题，系统研究了不同传感器硬件配置对多模态SLAM性能的影响。

◆作者基于ANYmal D四足机器人采集的GrandTour数据集，对视觉、视觉惯性和LiDAR-视觉-惯性SLAM方法进行了统一评测。

◆研究定量比较了相机模态、快门类型和不同等级IMU在定位精度、鲁棒性和计算资源消耗上的权衡。

◆实验发现，双目配置整体优于单目和RGB-D，全局快门相比卷帘快门能显著减少运动导致的跟踪失败。

◆一个重要结论是，在剧烈腿式运动下，常规惯性融合反而可能削弱以视觉为主的SLAM系统性能，为四足机器人传感器载荷设计提供了实用指南。</td></tr>
<tr><td>2026-06-18</td><td>A High-accuracy Event-based Underwater SLAM System<br><a href='http://arxiv.org/pdf/2606.18951'>论文</a></td><td>◆提出首个高精度事件相机水下双目SLAM系统，针对水下速度波动、宽基线和重复纹理导致的TS质量下降与匹配失败问题进行系统性解决。
◆设计基于结构张量相干性与梯度的TS结构感知度量，用于量化时间表面中的结构信息密度。
◆将最优TS生成按初始化前后解耦：初始化前用贝叶斯优化预测先验TS，跟踪阶段用异步在线局部搜索实时更新合适TS。
◆引入先验视差保障精确数据关联，并采用“最新观测优先”的三角化机制提升三维点构建稳定性。
◆构建并开源首个高质量真实水下事件数据集UWE，覆盖可变运动、复杂纹理和多类轨迹，实验表明系统精度达到或优于现有事件SLAM方法。</td></tr>
<tr><td>2026-06-17</td><td>C-ARC: Continuous-Adaptive Range Clustering for Non-Repetitive LiDAR Sensors<br><a href='http://arxiv.org/pdf/2606.18948'>论文</a></td><td>◆ C-ARC面向非重复式Risley棱镜LiDAR，解决其无规则扫描线、无明确帧边界和点云分布不均导致传统聚类方法失效的问题。  
◆ 提出连续自适应距离聚类框架，在滑动窗口中维护持久化双图结构，将高频点插入与按需簇提取解耦，适配SLAM和目标跟踪等实时任务。  
◆ 设计自适应距离网格分辨率机制，通过初始化阶段的指数控制循环自动校准网格尺寸，无需预知扫描模式。  
◆ 该机制在稀疏性与网格碰撞之间取得平衡，并可提升现有网格聚类方法在非重复LiDAR数据上的聚类质量。  
◆ 系统以开源单线程C++17库实现，可在普通硬件上对Livox Mid-360实现20 Hz实时聚类，同时评估指出强集中扫描传感器中无界单元占用是主要限制。</td></tr>
<tr><td>2026-06-16</td><td>RICH-SLAM: Radar SLAM with Incremental and Continuous Hilbert Mapping<br><a href='http://arxiv.org/pdf/2606.17534'>论文</a></td><td>◆ RICH-SLAM提出了一种面向雷达传感器的SLAM框架，旨在解决雷达数据稀疏、噪声大而难以构建稠密一致地图的问题。
◆ 其后端采用Rao-Blackwellized粒子滤波结构，用粒子滤波估计机器人位姿，并用卡尔曼滤波增量更新地图参数。
◆ 论文引入基于Hilbert空间低秩高斯过程的增量映射方法，可从稀疏雷达观测中生成连续、稠密且带不确定性的占据地图。
◆ 作者设计了后验感知的粒子权重计算机制，利用地图参数的完整后验分布进行似然评估，从而提升定位与建图的鲁棒性。
◆ 在自采数据和公开ColoRadar数据集上的实验表明，RICH-SLAM能有效构建连续雷达占据地图，并支持移动机器人的不确定性感知规划。</td></tr>
<tr><td>2026-06-15</td><td>CrossMaps: Confidence-Aware Open-Vocabulary Semantic Mapping for Rover Navigation<br><a href='http://arxiv.org/pdf/2606.16935'>论文</a></td><td>本文提出了CrossMaps，一个用于探测车导航的实时置信度感知开放词汇语义建图管线，能够基于RGB-D数据构建支持自然语言查询的地图。
◆创新性地将多尺度CLIP嵌入与置信度感知融合相结合，利用几何、语义和时间置信度线索来有效聚合噪声视觉观测。
◆提出了双记忆架构，短期记忆处理动态噪声观测，长期记忆则将高置信度且连贯的单元提升为持久语义地标。
◆实现了在Jetson Orin边缘平台与SLAM协同的实时部署方案，生成可查询语义热图引导导航。
该系统有效解决了部分可观测环境下感知与导航的耦合问题，提升了探测车导航的可靠性。</td></tr>
<tr><td>2026-06-15</td><td>SGM-SLAM: Scene Graph Matching for Data-Efficient Distributed SLAM<br><a href='http://arxiv.org/pdf/2606.16881'>论文</a></td><td>本文提出了一种面向多机器人团队的数据高效分布式SLAM框架，利用场景图匹配来识别机器人间的测量约束。
◆首次仅利用对象标签和质心进行场景图匹配以识别机器人间约束，区别于以往依赖特征级匹配的方法。
◆创新性地通过融合RGB-LiDAR点云构建场景图，生成语义分割点云层与离散有界对象层伴随机器人轨迹。
◆通过协作交换与匹配邻居机器人的对象数据完成场景图匹配，并采用多步数据交换与优化过程最大化通信效率。
该框架在室内外真实腿式机器人及仿真数据集上均验证了其有效性与高效性。</td></tr>
<tr><td>2026-06-15</td><td>MVOFormer: Flow-Semantic Transformer for Robust Monocular Visual Odometry<br><a href='http://arxiv.org/pdf/2606.16474'>论文</a></td><td>本文提出了一种用于鲁棒单目视觉里程计的新型Transformer框架MVOFormer，解决了现有学习方法缺乏可解释互补特征和架构复杂的问题。
◆提出流语义双分支编码器，协同融合密集几何运动线索与以物体为中心的语义先验，显式区分静态结构与动态干扰物。
◆设计迭代多模态解码器，融合上述表征实现由粗到细的位姿细化，并动态抑制对不可靠区域的注意力。
该框架无需任何目标域微调，即可在多种基准测试中实现卓越的零样本泛化能力与鲁棒性。
在TartanAir等四个多样化数据集上的广泛评估表明，MVOFormer显著优于以往基于学习的帧到帧方法。</td></tr>
<tr><td>2026-06-18</td><td>A Smart-Scheduled Hybrid (SSH) EKF-FGO State Estimation<br><a href='http://arxiv.org/pdf/2606.16057'>论文</a></td><td>该论文针对状态估计中精度与计算成本的平衡问题，提出一种智能调度混合SSH EKF-FGO框架，作为显式研究优化调度作用的受控测试平台。
◆将优化调度作为独立设计变量进行实验性表征，明确其如何控制中间估计精度与计算成本的权衡。
◆通过固定求解器结构与计算量，结合EKF状态传播与周期性批处理优化，成功剥离并孤立出优化调度变量。
◆基于平面SLAM仿真，揭示了优化调度对优化前漂移、瞬态误差及运行时的强烈影响。
研究发现了能以极小计算成本保留大部分全局优化收益的运行机制，凸显了优化调度在混合状态估计中是未被充分探索却至关重要的因素。</td></tr>
<tr><td>2026-06-13</td><td>FD-SLAM: Fast Dense Radar-Inertial SLAM with Frequency-Domain Loop Closure and Pose Graph Optimization<br><a href='http://arxiv.org/pdf/2606.15491'>论文</a></td><td>◆ 提出FD-SLAM，一种快速稠密雷达-惯性SLAM系统，在稠密雷达-惯性里程计基础上加入频域回环检测与位姿图优化，面向视觉退化环境下的地面车辆定位建图。

◆ 设计了紧凑的频域极坐标描述子，保留扫描雷达数据的类图像结构，用于高效检索长轨迹中的回环候选，提升雷达测量匹配的可靠性。

◆ 构建多阶段回环验证流程，包括时间滤波、相位相关筛选、扫描对齐相似度评估和几何一致性检查，从而降低雷达噪声和误匹配带来的影响。

◆ 将验证后的回环作为非连续约束加入SE(2)位姿图，并与雷达-惯性里程计因子联合优化，有效减小累计漂移。

◆ 在公开数据集上使用KITTI指标评估，结果表明FD-SLAM相比FD-RIO基线有明显提升，并在多条驾驶轨迹上展现出具有竞争力的精度，尤其是旋转精度表现较好。

◆ 运行时间分析显示，其雷达-惯性前端可在纯CPU环境下超过雷达采样率运行，回环检测和图优化也适合并行后台执行，具备较好的实时应用潜力。</td></tr>
</tbody>
</table>
</div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-06-02</td><td>SAMatcher: Co-Visibility Modeling with Segment Anything for Robust Feature Matching<br><a href='http://arxiv.org/pdf/2606.03406'>论文</a></td><td>本文提出SAMatcher框架，将特征匹配转化为共可见性建模问题，突破了现有方法仅停留在像素级而缺乏跨视图共可见区域显式建模的局限。
◆不同于直接匹配局部特征，该方法首创预测共可见区域掩码和边界框作为对应估计的结构化先验。
◆基于SAM模型引入对称跨视图交互机制，实现了视图间的双向特征交换与跨视图语义对齐。
◆提出统一监督方案，通过掩码学习、框回归及掩码框一致性约束联合优化掩码预测与框定位。
实验表明该方法在大视角和尺度变化下显著优于现有方法，并证实单目分割模型可扩展至多视图推理，为图像匹配提供新视角。</td></tr>
<tr><td>2026-06-01</td><td>Edge Prediction for Roof Wireframe Reconstruction with Transformers<br><a href='http://arxiv.org/pdf/2606.02406'>论文</a></td><td>本文提出了一种受DETR启发的端到端Transformer编解码器架构，用于从稀疏SfM点云和地面语义数据中重建3D房屋屋顶线框模型。
◆提出基于语义优先级对稀疏SfM点云进行动态下采样，并融合格式塔与ADE20k类别特征进行增强。
◆将点云投影至冻结自编码器生成的潜特征图中提取额外格式塔特征编码，与点特征融合以丰富分割上下文。
◆利用交叉注意力机制，将学习到的查询嵌入直接解码为3D线框边缘。
该方法在HoHo 22k数据集上显著超越手工与学习基线，以0.6476的混合结构得分在S23DR挑战赛中夺得亚军。</td></tr>
<tr><td>2026-06-01</td><td>SAVMap: Structure-Aided Visual Mapping of Large-Scale 2.5D Manhattan Wireframes from Panoramic Video<br><a href='http://arxiv.org/pdf/2606.01939'>论文</a></td><td>本文提出了SAVMap方法，仅利用全景视频相机作为传感器输入，即可生成工业仓库货架和照明设施的语义线框地图。
◆结合语义分割网络前端，从全景视频校正图像中提取稀疏的语义结构特征点如货架角点和灯具中心，并在图像序列中对其进行跟踪。
◆提出一种结合曼哈顿网格等现实世界几何关系的约束运动恢复结构算法，从而计算构成线框地图的精确三维点。
该方法在拥有46排大型货架的仓库中得到了验证，仅用一小时全景视频便成功构建了超五千个货架元素的线框地图。
实验结果表明，该地图相对于真实值的总体平均绝对误差仅为4.8厘米，展现了出色的可扩展性与高精度。</td></tr>
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
<tr><td>2026-05-28</td><td>City-Mesh3R: Simulation-Ready City-Scale 3D Mesh Reconstruction from Multi-View Images<br><a href='http://arxiv.org/pdf/2605.30310'>论文</a></td><td>本文提出City-Mesh3R框架，实现从大规模无序图像直接重建适用于仿真的城市级高保真水密三维网格，克服了现有方法几何缺失和表面噪声的问题。
◆采用基于分治策略的端到端图像到网格重建流程，取代传统的全局稀疏SfM初始化与分布式稠密重建，使模型可扩展至任意大规模场景。
◆利用拓扑图像聚类进行聚类独立稀疏SfM与地图合并，无需穷举图像特征匹配即可构建稀疏城市地图。
◆结合几何感知相机选择与曲率感知自适应顶点密度重网格化技术进行表面细化，有效保障网格几何规则且细节精细。
◆通过空间分区与网格缝合技术无缝拼接局部网格，生成全局水密城市网格，验证了分布式端到端处理的卓越扩展性与重建保真度。</td></tr>
</tbody>
</table>
</div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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

<h2 id='obstacle-avoidance'>Obstacle Avoidance</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-06-21</td><td>Any-Body Guard: Universal Safeguarding for Manipulation Policies via Action Masking<br><a href='http://arxiv.org/pdf/2606.22278'>论文</a></td><td>◆论文提出X-Safe，一种面向机器人操作策略的通用安全保护方法，通过动作遮蔽在执行前过滤可能导致碰撞的动作。
◆其核心创新是直接在机器人构型空间中推理，从而为避碰提供形式化的概率安全保证。
◆该方法仅依赖物体级准静态场景表示和机械臂正运动学模型，不需要额外数据或针对不同机器人重新设计控制器。
◆相比启发式回退控制或复杂前向不变性分析，X-Safe更易迁移到不同形态、任务和场景，并减少对任务性能的保守影响。
◆作者在仿真和真实硬件上的多种机器人与策略中验证了方法，实验显示硬件无碰撞且安全保证得到经验支持。</td></tr>
<tr><td>2026-06-19</td><td>Backpropagating Through Simulation: Analytic Policy Gradients for Sample and Learning Efficient Differentiable Continuous Control<br><a href='http://arxiv.org/pdf/2606.21525'>论文</a></td><td>◆本文提出Analytic Policy Gradients（APG），利用可微环境将回报视为策略参数的可微函数，直接通过仿真反向传播计算精确梯度，替代高方差采样估计。

◆APG显著提升连续控制中的样本效率，针对PPO需要大量交互的问题，在多种任务上进行系统对比验证。

◆论文设计了包含环境步数与梯度步数的多轴评估协议，从而区分样本效率和计算效率。

◆为解决长时域任务中的梯度衰减问题，提出分段反向传播，并结合蒙特卡洛或critic引导的bootstrap机制。

◆实验覆盖从点质量导航到刚体推动和7自由度机械臂 reaching 的不同复杂度任务，并通过消融分析研究分段长度与bootstrap策略的影响。</td></tr>
<tr><td>2026-06-19</td><td>Reference-Free, Long-Horizon Trajectory Optimization for Aggressive Autonomous Driving in Milliseconds<br><a href='http://arxiv.org/pdf/2606.21486'>论文</a></td><td>◆论文面向激进自动驾驶，研究如何在无参考轨迹、无热启动条件下，毫秒级求解长视距、全车辆动力学的最优控制问题。
◆作者通过分析车辆动力学刚性特征，证明低阶A稳定积分方法更适合该类OCP，求解速度相比其他方法可提升最高两个数量级。
◆论文系统揭示了内点法中障碍参数更新策略和Hessian不定性保护机制对非线性求解鲁棒性的关键影响。
◆提出基于动态平衡的高效初值生成方法，将初始不可行性最多降低四个数量级，从而显著提升实时求解能力。
◆实验在高保真BeamNG仿真中实现260米视距仅55毫秒的计算时间，并展示高速避障中漂移可成为生成可行轨迹的必要行为。</td></tr>
<tr><td>2026-06-18</td><td>Agentic AutoResearch forSpace Autonomy: An Auditable, LLM-Driven Research Agent for Aerospace Control Problems<br><a href='http://arxiv.org/pdf/2606.20394'>论文</a></td><td>◆ 提出AutoResearch框架，用大语言模型作为离线研究代理，自动阅读问题描述、修改训练脚本、运行实验并记录结果，用于航天控制策略开发。

◆ 明确区分“研究代理”和“ onboard 控制器”：LLM只负责离线发现策略，最终部署的是训练好的控制策略，避免LLM直接操控航天器。

◆ 引入内嵌可信度审计层，要求结果通过种子噪声测量、最佳配置重采样验证和留一编辑剪枝三重检验后才被认可。

◆ 在相对交会和带安全约束的避障对接两个任务上，框架无需改动即可应用，并以最优控制基准校准性能。

◆ 实验显示，经审计的策略显著超过种子噪声，而无定向搜索无法达到同等效果；在对接任务中，随机搜索甚至找不到可行策略。</td></tr>
<tr><td>2026-06-18</td><td>Lagrange: An Open-Vocabulary, Energy-Based Sparse Framework for Generalized End-to-End Driving<br><a href='http://arxiv.org/pdf/2606.20274'>论文</a></td><td>◆ 提出Lagrange，一个面向开放世界端到端驾驶的开放词汇、能量驱动稀疏框架，兼顾计算效率与泛化能力。
◆ 采用Masked Latent Fields，利用VLM将类别无关目标提案编码为连续语义视觉token，避免依赖稠密占据或封闭类别查询。
◆ 设计意图驱动的掩码交叉注意力机制，按时间过滤与驾驶目标无关的实体，提升复杂场景下的决策聚焦性。
◆ 将感知结果解码为空间连续隐式能量场，使规划可在连续坐标中进行碰撞规避与语义推理。
◆ 将决策建模为跨能量场的拉格朗日作用量最小化问题，从而显式满足车辆运动学约束并生成可执行轨迹。
◆ 在nuScenes和长尾CODA基准上的离线实验表明，该方法在开放世界鲁棒性、可解释性和运动学可行性方面具有潜力。</td></tr>
<tr><td>2026-06-22</td><td>Stable Transformer-Actor-Critic Model Predictive Control: A Contraction Analysis Approach<br><a href='http://arxiv.org/pdf/2606.20197'>论文</a></td><td>◆提出了一种Transformer-Actor-Critic MPC架构，用于处理复杂非凸控制任务，并同时关注闭环稳定性与鲁棒性保证。
◆首次证明Transformer网络可满足全局增量输入到状态稳定性δISS，为序列模型用于控制提供理论基础。
◆利用黎曼收缩理论分析物理系统与预测神经网络之间的互联系统动态，建立稳定性判据。
◆将理论推导得到的稳定性与鲁棒性界作为训练正则项，使学习策略具备可认证的鲁棒性。
◆在非线性3D无人机目标到达与避障任务中验证了方法的有效性，展示其在复杂动态场景中的应用潜力。</td></tr>
<tr><td>2026-06-18</td><td>Frequency-Aware Flow Matching for Continuous and Consistent Robotic Action Generation<br><a href='http://arxiv.org/pdf/2606.20135'>论文</a></td><td>◆论文提出Frequency-Aware Flow Matching（FAFM），解决现有机器人流匹配/扩散策略依赖离散动作块、难以适配不同控制频率且动作不连续的问题。
◆方法将离散动作序列通过DCT变换到频域，在频域系数上进行流匹配，再用余弦基展开重建连续动作。
◆为提升时间一致性，FAFM加入一阶时间导数正则，相当于Sobolev约束，可抑制高频误差和突变动作。
◆该方法不增加额外网络参数，能无缝用于独立流匹配策略和视觉-语言-动作模型。
◆在仿真、LapGym、LIBERO及真实Franka机器人实验中，FAFM提升成功率、平滑性、收敛速度、多模态表达能力，并增强对机械偏差和混合频率数据的鲁棒性。</td></tr>
<tr><td>2026-06-18</td><td>Contraction-based Neural Control for Cooperative Aerial Payload Transportation with Variable-length Cables<br><a href='http://arxiv.org/pdf/2606.20127'>论文</a></td><td>◆ 提出一种面向多无人机变长度缆绳吊运刚体载荷的神经非线性控制框架，解决协同空运中的轨迹跟踪与避障问题。
◆ 将系统动力学重构为载荷运动与缆绳长度动力学解耦的形式，使不同控制通道可模块化设计。
◆ 针对载荷子系统，联合训练神经控制收缩度量控制器与神经反馈控制器，以满足收缩条件并提升非线性跟踪稳定性。
◆ 针对缆绳长度子系统，设计利用可变长度自由度的控制律，实现通过障碍或门洞时的空间调整。
◆ 仿真验证了该框架可实现刚体载荷轨迹跟踪和门洞穿越，展示了其在复杂环境协同运输中的潜力。</td></tr>
<tr><td>2026-06-17</td><td>One Demo is Worth a Thousand Trajectories: Action-View Augmentation for Visuomotor Policies<br><a href='http://arxiv.org/pdf/2606.19586'>论文</a></td><td>◆提出一种从单条真实眼在手示教中生成大量训练数据的动作-视角增强框架，缓解机器人初始位姿变化和未知障碍导致的分布外问题。
◆设计适用于大视场鱼眼相机的Gaussian Splatting重建方法，可生成逼真的鱼眼图像序列，并支持在三维场景中编辑加入未见物体。
◆结合轨迹优化生成平滑、无碰撞且适合视角渲染的动作轨迹，保证增强数据在视觉和物理执行上都更可信。
◆该方法仅需便携式夹爪和单个鱼眼相机采集演示，显著降低了大规模机器人示教数据收集成本。
◆仿真和真实实验表明，该增强框架能提升多种操作任务的成功率，尤其在含障碍物、需要避障的增强场景中效果明显。</td></tr>
<tr><td>2026-06-17</td><td>pdSTL: Probabilistic Differentiable Signal Temporal Logic for Stochastic Systems<br><a href='http://arxiv.org/pdf/2606.19561'>论文</a></td><td>◆ 提出pdSTL框架，将概率语义与可微鲁棒性统一起来，使随机动力学和感知噪声下的机器人能够在信念轨迹上进行时序逻辑约束优化。  
◆ 采用区间值概率语义，组合式地沿STL语法树传播保守满足概率边界，从而提供形式化的概率安全保证。  
◆ 将时序鲁棒性评估重构为类似LSTM的递归展开，实现线性时间、端到端可微的STL监测与轨迹优化。  
◆ 相比传统确定性可微STL，pdSTL显式考虑信念空间不确定性，因此在真实扰动环境中能更稳定地保持安全裕度。  
◆ 通过仿真避障、换道和Crazyflie四旋翼真实飞行实验验证了方法的效率、可优化性和在随机系统中的实际安全优势。</td></tr>
<tr><td>2026-06-17</td><td>Congestion-Aware Robot Tour Planning in Crowded Environments<br><a href='http://arxiv.org/pdf/2606.19031'>论文</a></td><td>◆本文提出了一种面向拥挤环境的概率式机器人巡游规划方法，专门解决人群对机器人导航效率和路径选择的影响。

◆其核心创新在于显式建模“人群拥堵”因素，而不是仅将行人视为局部避障中的动态障碍物。

◆论文利用CLiFF地图学习人流运动模式，可根据初始观测预测行人轨迹和未来拥堵分布。

◆基于这些预测，系统在线构建并求解马尔可夫决策过程，从而为机器人选择更高效、更少受人群干扰的巡游路线。

◆该方法具备可扩展性，能够随着新行人观测不断重新规划，并在真实购物中心人群数据集上验证了有效性。</td></tr>
<tr><td>2026-06-17</td><td>WST Multi-Object Spectrograph Fiber Positioners:Development of a 32,000-Unit Precision Robotic System<br><a href='http://arxiv.org/pdf/2606.18957'>论文</a></td><td>◆ 论文提出了面向WST多目标光谱仪的超大规模光纤定位系统方案，覆盖3.1平方度视场，包含3万台低分辨率和2000台高分辨率定位器。

◆ 其核心挑战是让每个密集排布的机器人定位器达到5微米RMS精度，规模较DESI、4MOST等现有装置提升六倍以上。

◆ 为降低32,000个精密机构量产风险，项目采用多概念并行开发策略，由EPFL、AIP、UKATC和AAO合作推进。

◆ 论文创新性比较了四种定位器架构，包括6.2毫米间距、63单元三角模块以及新的内联模块化概念。

◆ 研究建立了系统化测试指标，涵盖定位精度、重复性、重配置速度、避碰能力和可制造性，为2026–2027年概念筛选提供依据。

◆ 当前原型测试表明关键性能指标具备可行性，为WST在2040年代初实现首光奠定了技术基础。</td></tr>
<tr><td>2026-06-16</td><td>VEGA: Learning Navigation VLAs from In-the-Wild Egocentric Video with Geometric Trajectory Supervision<br><a href='http://arxiv.org/pdf/2606.18426'>论文</a></td><td>◆ VEGA提出了一种从未标注的第一人称野外导航视频中训练导航Vision-Language-Action模型的方法，利用互联网规模视频作为可扩展数据源。

◆ 它通过单目视频重建局部场景几何，并基于文本、图像或空间路标采样导航目标，生成机器人坐标系下的避障轨迹监督。

◆ VEGA仅在训练阶段使用几何信息，将避障规划能力蒸馏到纯视觉策略中，并采用flow-matching训练VLA导航策略。

◆ 论文还构建了VEGA-Bench，包含25万场景和约500万导航目标，用于系统评估目标推进、碰撞避免和障碍间距。

◆ 实验表明，VEGA在基准测试中显著减少碰撞并提升避障间距，在真实世界试验中也大幅提高成功率，证明视频派生几何监督是训练避障导航VLA的有效可扩展信号。</td></tr>
<tr><td>2026-06-15</td><td>Optimal Bounded Thrust Powered Descent with Analytical Ground-Collision Avoidance<br><a href='http://arxiv.org/pdf/2606.17050'>论文</a></td><td>本文提出了一种解决有界推力动力下降并确保避撞的新方法，通过质量多项式近似构建了有界线性二次最优控制问题。该方法的核心是推力分配的分层分离，对水平推力施加硬约束而保持垂直推力无约束。
◆与基于数值优化和轨迹成型的现有方法不同，该方法提供了显式的解析避撞条件。
◆制导律能预测饱和与未饱和弧段的切换时间并塑造推力曲线，在控制器长时间饱和时仍可实现软着陆。
由于具有解析特性，该制导律计算高效且推力曲线连续，便于实时应用，仿真验证了其在扰动下精确的无碰撞软着陆性能。</td></tr>
<tr><td>2026-06-15</td><td>Instance-Aware Knowledge Distillation for Semi-Supervised Learning of an On-Board Multi-Task Dense Prediction Model for Collision Avoidance System<br><a href='http://arxiv.org/pdf/2606.16414'>论文</a></td><td>◆提出面向碰撞避免系统的实例感知知识蒸馏半监督框架，降低目标场景大规模标注需求。
◆伪标签生成同时利用教师模型的领域先验与基础模型的实例级知识，从而缓解教师偏差并提升实例分割质量。
◆训练得到轻量级车载多任务密集预测学生模型，可同时执行前方障碍物检测/实例分割与单目深度估计。
◆构建大规模乡村俱乐部场景数据集，并将模型集成到实际系统中，通过CAN消息编码障碍物空间信息以支持AGV运行。
◆实验表明学生模型在实例分割上超过大教师模型，同时显著降低深度估计性能退化，并以22.68倍FLOPs和14.33倍参数压缩实现低成本边缘设备实时运行。</td></tr>
<tr><td>2026-06-15</td><td>SemGeoNav:A Safety-Guided Visual Navigation Approach with Semantic Reasoning and Geometric Planning<br><a href='http://arxiv.org/pdf/2606.16400'>论文</a></td><td>针对端到端模型缺乏几何约束导致避障不可靠，以及传统几何规划难以处理高维视觉目标的问题，本文提出了SemGeoNav分层视觉导航框架。该框架将端到端模型的高级语义推理与基于几何的可靠局部规划紧密结合，实现了鲁棒的图像导航并显著提升了避障能力。
◆提出语义推理与几何规划紧耦合的分层架构，兼顾高维语义目标处理与物理避障安全。
◆引入时序轨迹平滑机制，确保机器人运动的连续性与稳定性。
在真实环境四足机器人上的实验表明，该方法在成功率和导航时间上均优于ViNT和NoMaD等现有方法。</td></tr>
<tr><td>2026-06-15</td><td>PolyMerge: Compressing 3D Gaussian Splats with Polytope Coverings for Provably Safe Resource-Constrained Navigation<br><a href='http://arxiv.org/pdf/2606.16232'>论文</a> | <a href='https://athlon76.github.io/PolyMerge-website/'>代码</a></td><td>本文提出PolyMerge方法，将大规模的3D高斯溅射模型转换为轻量级的凸多面体表示，以解决3DGS模型在机载感知路径规划中计算和内存开销过大的问题。
◆提出基于凸多面体覆盖的3DGS压缩方法，其多面体合集可证明对原3DGS模型中的所有障碍物进行保守包络。
◆支持调节多面体数量，灵活权衡避障的保守性与计算成本。
◆将多面体表示与控制障碍函数深度融合，实现可证明安全的无碰撞路径规划。
无人机硬件与仿真实验表明，该方法在极严苛的机载算力下实现了实时安全轨迹规划，在保证安全的同时运行速度超越基线方法。</td></tr>
<tr><td>2026-06-14</td><td>Act on What You See: Unlocking Safe Social Navigation in Vision-Language-Action Models<br><a href='http://arxiv.org/pdf/2606.10495'>论文</a></td><td>本文提出SALSA框架，解决了预训练视觉-语言-动作模型虽已编码行人区分与碰撞信号，但行为克隆无法将其转化为安全社交动作的问题。
◆社交行为对齐，将中间层社交特征桥接至动作头，并利用反事实人-物场景对进行训练以打破视觉显著性捷径。
◆时序安全对齐，通过自动生成的未来风险监督信号，使模型能够实现前瞻性的碰撞规避。
实验表明，SALSA在无需额外标注的情况下将近距离碰撞减少了86.4%，并将社交反事实准确率从53%提升至93%。
该研究证明，通过更好地对齐潜层表征与动作生成，即可让模型依据已有表征行动，成功解锁预训练VLA策略的安全社交导航潜能。</td></tr>
</tbody>
</table>
</div>

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-22</td><td>DVL-DeepONet: A Physics-Guided Operator Learning for Resilient Underwater Navigation<br><a href='http://arxiv.org/pdf/2606.23502'>论文</a></td><td>◆提出DVL-DeepONet，一种物理引导的深度神经算子框架，用于在DVL波束缺失、噪声干扰或传感器配置受限时实现鲁棒水下速度估计。

◆该方法学习从时序惯性/DVL观测到AUV速度向量的非线性算子，突破传统模型在复杂海洋环境中对完整波束和精确传感器的依赖。

◆引入DVL测量物理一致性约束，使网络预测不仅依赖数据驱动学习，还符合DVL几何与测量机理。

◆设计了三类应用变体，分别支持惯性/DVL融合下的抗噪估计、仅DVL条件下的速度学习，以及缺失波束测量恢复。

◆基于约10,000米真实AUV航行实验验证，结果显示其相较模型方法和学习基线整体性能提升约40%，增强了低成本和受损感知场景下的导航韧性。</td></tr>
<tr><td>2026-06-22</td><td>SkyJEPA: Learning Long-Horizon World Models for Zero-Shot Sim-to-Real Control of Quadrotors<br><a href='http://arxiv.org/pdf/2606.23444'>论文</a></td><td>◆提出SkyJEPA，将联合嵌入预测架构引入四旋翼高频实时控制，避免自回归预测误差随时间累积的问题。
◆构建潜在空间动力学模型，实现面向长时域的稳定预测，提升无人机在不确定环境中的决策能力。
◆设计物理启发式prober，将冻结的潜在表示映射为可解释状态，使长时域预测更具物理一致性。
◆将学习到的世界模型与采样式最优控制结合，并部署在嵌入式硬件上实现实时控制。
◆提出自动化、结构化数据生成流程，减少对昂贵且有风险的真实飞行数据采集依赖。
◆通过开环预测和户外闭环实验验证其零样本仿真到现实迁移能力及跨工况泛化性能。</td></tr>
<tr><td>2026-06-22</td><td>Humanoid-OmniOcc: Stereo-Based Full-View Occupancy Dataset for Embodied AI<br><a href='http://arxiv.org/pdf/2606.22971'>论文</a> | <a href='https://d-robotics-ai-lab.github.io/humanoid-omniocc'>代码</a></td><td>◆提出Humanoid-OmniOcc，一个面向类人机器人具身智能的全景双目体素占据数据集，弥补现有自动驾驶数据集在视角、场景和几何先验上的局限。

◆数据集覆盖15个多样化仿真室内场景和5个真实环境，包含超过15.5万样本，具备较强的场景与风格多样性。

◆引入Real2Sim2Real闭环范式，用真实传感器规格构建物理准确仿真，再生成大规模标注数据并在真实采集上验证。

◆提出Humanoid Surround Stereo-guided Occupancy模型，利用双目深度先验提升2D到3D占据预测的准确性。

◆实验表明该方法优于单目基线，并能泛化到未见仿真场景和真实环境，验证了数据集与闭环设计的有效性。</td></tr>
<tr><td>2026-06-19</td><td>Long-Distance Real-World Navigation of the Legged-Wheeled Robot Go2-W Using Deep Reinforcement Learning<br><a href='http://arxiv.org/pdf/2606.21387'>论文</a></td><td>◆本文面向商用腿轮机器人Go2-W，构建了基于深度强化学习的运动控制器与自主导航系统，验证其在真实长距离场景中的可用性。
◆作者将此前用于四足机器人的仅依赖本体感知的策略扩展到16自由度腿轮机器人，实现了无需外部地形感知的稳健运动控制。
◆论文发现轮式运动会使负载集中于髋关节并导致过热，提出通过负载分配来抑制热集中、提升持续行驶能力的策略。
◆系统在筑波挑战2025中完成约2.8公里自主导航，覆盖人行道、公园和楼梯等复杂环境。
◆实验表明，该方法能在不因过热停机的情况下完成长距离真实世界导航，推进了腿轮机器人从实验室控制到实际应用的落地。</td></tr>
<tr><td>2026-06-18</td><td>UNSEEN: Uncertainty-aware Navigation via Sparse Estimation in Unknown Environments<br><a href='http://arxiv.org/pdf/2606.20755'>论文</a></td><td>◆ UNSEEN提出一种仅依赖前置相机的统一导航框架，在未知环境中紧耦合定位、稀疏建图与规划，降低对多传感器和环境先验的依赖。
◆ 其核心创新是显式建模并传播位姿、地图和感知质量的不确定性，使规划不只追求到达目标，也主动选择有利于估计的运动。
◆ 系统以6Hz在线估计带不确定性的稀疏地图和机器人位姿，并在滚动时域内联合优化任务进展与定位精度。
◆ 相比传统松耦合管线和只优化单模块的感知感知方法，UNSEEN将运动指令与视觉感知的相互影响纳入同一决策闭环。
◆ 仿真和真实实验表明，UNSEEN-SLAM将绝对平移误差降低9.8%，UNSEEN-Plan最高提升45%估计精度，并实现100%任务成功率。</td></tr>
<tr><td>2026-06-18</td><td>Fast Human Attention Prediction for Fixation-guided Active Perception in Autonomous Navigation<br><a href='http://arxiv.org/pdf/2606.20491'>论文</a></td><td>◆提出GazeLNN，一种面向机器人主动感知的轻量级人类扫描路径预测模型，用Liquid Neural Networks作为循环核心，并结合MobileNetV3提取视觉特征。

◆模型以自回归方式根据当前图像和历史注视信息连续预测 fixation heatmap，从而模拟人类结构化视觉注意过程。

◆在仅需0.61 GFLOPs的计算量下，GazeLNN在MIT Low Resolution数据集上达到0.47 ScanMatch，取得领先性能。

◆相比现有循环式基线方法，该模型在多项指标上表现更优，同时将计算成本降低99.40%，推理速度最高提升6倍。

◆论文进一步将GazeLNN嵌入强化学习训练的主动相机-机器人控制策略，实现由人类注视引导的自主导航感知，并在真实空中机器人上完成验证。</td></tr>
<tr><td>2026-06-18</td><td>Slow Brain, Fast Planner: Latency-Resilient VLM-Augmented Urban Navigation<br><a href='http://arxiv.org/pdf/2606.20458'>论文</a></td><td>◆论文指出城市人行道导航中存在“轨迹评分鸿沟”：学习式规划器能生成好候选轨迹，但常因缺乏高层场景理解而选错。

◆提出VLM-Planner接口，让视觉语言模型从规划器候选轨迹中选择更合理的索引，而非用端到端VLA模型替代原规划器。

◆针对VLM 1–3秒推理延迟，设计无需训练的延迟鲁棒轨迹级融合层，将过期VLM选择通过几何相似度和指数衰减转化为实时评分。

◆实验显示，在约2000个真实复杂场景中，VLM选择相比规划器原最优输出将ADE降低30%，尤其改善路口和行人交互等难例。

◆仿真和实机验证表明，该方法在最高5秒延迟下仍保持80%以上成功率，并能在校园人行道上稳定运行。</td></tr>
<tr><td>2026-06-18</td><td>Vision-Reasoning-Guided Occlusion Removal from Light Fields<br><a href='http://arxiv.org/pdf/2606.19985'>论文</a></td><td>◆ 提出一种视觉推理引导的光场遮挡去除框架，将光场积分的物理可见性恢复能力与视觉语言模型的语义推理能力结合起来。

◆ 方法先利用多视角光场积分抑制前景植被等密集遮挡，生成可见性增强的初始场景表示。

◆ 引入视觉语言模型作为条件语义先验，在观测约束下修复退化结构并恢复细节，提升复杂自然场景中的重建质量。

◆ 设计多样本融合策略，将多个生成假设聚合为一致结果，从而减少幻觉伪影并增强恢复稳定性。

◆ 在合成和真实数据集上取得先进性能，在4个合成光场基准场景中获得最高平均SSIM，并展现出对结构化和非结构化采集条件的良好泛化能力。</td></tr>
<tr><td>2026-06-17</td><td>Sensor Configuration Matters: A Systematic Evaluation of Multimodal SLAM on Quadruped Robots<br><a href='http://arxiv.org/pdf/2606.19067'>论文</a></td><td>◆本文针对四足机器人在足端冲击、机械振动和快速旋转下SLAM性能不稳定的问题，系统评估了传感器硬件配置对多模态SLAM的影响。
◆作者基于ANYmal D的GrandTour数据集，对视觉、视觉惯性、激光-视觉-惯性SLAM方法进行了统一比较。
◆论文量化分析了相机模态、快门类型和IMU等级在定位精度、鲁棒性与计算资源消耗之间的权衡。
◆实验发现，双目配置整体优于单目和RGB-D，全局快门相比卷帘快门更能减少运动导致的跟踪失败。
◆一个关键发现是，在剧烈腿式运动中，标准惯性融合反而可能削弱以视觉为主的SLAM性能。
◆论文最终给出了面向敏捷四足机器人的传感器载荷设计建议，为可靠自主导航提供了实践依据。</td></tr>
<tr><td>2026-06-15</td><td>VISTA: Scale-Aware Visual Navigation via Action History Conditioning<br><a href='http://arxiv.org/pdf/2606.17294'>论文</a></td><td>◆ VISTA针对视觉导航基础模型中“归一化动作”带来的尺度部署脆弱性，指出相同归一化轨迹在不同缩放因子下会改变真实运动几何并增加碰撞风险。
◆ 论文提出将归一化动作历史与图像观测共同作为条件输入，使模型显式理解预测动作与机器人实际位移之间的尺度关系。
◆ 该方法提升了跨机器人、跨环境部署时的尺度感知能力，从而增强零样本导航的稳定性和安全性。
◆ 为解决视觉重复、缺乏显著特征场景中的感知困难，VISTA集成DINOv3编码器以获得更丰富的空间与几何表征。
◆ 实验表明，VISTA在室外、森林和办公室等真实未见环境中实现100%零样本目标预测准确率，并平均通过95%的检查点，展现出强泛化和路径跟随能力。</td></tr>
<tr><td>2026-06-15</td><td>SidewalkBench: Benchmarking Visual Navigation on Urban Sidewalks<br><a href='http://arxiv.org/pdf/2606.16953'>论文</a></td><td>本文提出了SidewalkBench，一个专为城市人行道视觉导航设计的综合基准，填补了该领域缺乏统一评估标准的空白。
◆基于NVIDIA Isaac Sim构建，实现了对多样化高保真人行道环境（含程序生成和真实扫描场景）的GPU加速仿真。
◆引入了丰富的基于事件的反应式行人行为及灵活高效的动画，支持在逼真的真实设定下进行模型标准化评估。
研究在330个单元测试、800个行人反应场景和105个长视距场景上对9种模型进行了全面评估。
结果揭示行人交互与长视距鲁棒性是现有模型的关键瓶颈，而利用合成数据扩大训练规模是极具前景的解决方案。</td></tr>
<tr><td>2026-06-15</td><td>MVOFormer: Flow-Semantic Transformer for Robust Monocular Visual Odometry<br><a href='http://arxiv.org/pdf/2606.16474'>论文</a></td><td>本文提出MVOFormer框架，旨在解决现有单目视觉里程计方法缺乏可解释互补特征或架构过于复杂的问题，从而显著提升鲁棒性与跨域泛化能力。
◆提出流-语义双分支编码器，协同融合密集几何运动线索与面向对象的语义先验，显式区分静态结构与动态干扰物。
◆设计迭代多模态解码器，实现由粗到细的位姿细化，并在融合多模态表征时动态抑制对不可靠区域的注意力。
实验表明，在无需任何目标域微调的情况下，该方法展现出卓越的零样本泛化能力。
在TartanAir和KITTI等多个基准测试中，MVOFormer显著超越了以往基于学习的帧间方法。</td></tr>
<tr><td>2026-06-15</td><td>SemGeoNav:A Safety-Guided Visual Navigation Approach with Semantic Reasoning and Geometric Planning<br><a href='http://arxiv.org/pdf/2606.16400'>论文</a></td><td>现有端到端视觉导航模型缺乏显式几何约束导致避障不可靠，而传统几何规划器难以处理高维视觉目标。为此，本文提出了一种新型分层视觉导航框架SemGeoNav，实现了基于图像的鲁棒导航并显著提升了避障能力。
◆将端到端模型的高级语义推理与基于几何方法的可靠局部规划能力进行紧密集成。
◆引入时间轨迹平滑机制以确保机器人连续且稳定的运动。
真实环境中四足机器人的实验表明，SemGeoNav在成功率和导航时间上均优于ViNT和NoMaD等代表性方法。</td></tr>
<tr><td>2026-06-15</td><td>Embedded Arena: Iterative Optimization via Hardware Feedback<br><a href='http://arxiv.org/pdf/2606.16190'>论文</a></td><td>本文核心贡献是提出一种基于硬件在环的智能体框架，以替代人类专家自主完成边缘微控制器上的AI模型与固件协同优化。
◆提出硬件在环的智能体竞技场机制，利用真实硬件的编译烧录与测量反馈，指导大语言模型进行模型与固件的闭环迭代协同优化。
◆验证了纯大语言模型完全无法完成部署，而引入硬件反馈后仅需3次迭代即可成功部署，7次迭代即可超越人类专家水平。
◆实现了极高的模型压缩比且精度损失极小，视觉模型压缩250倍而精度损失不足3.3%，音频模型压缩400倍，使商用微控制器能依靠太阳能实现无电池运行。
该方法在麋鹿检测相机和语音转录可穿戴设备等真实系统中的成功应用，充分证明了其实用价值与工程意义。</td></tr>
<tr><td>2026-06-14</td><td>FlashNav: Ultra-Fast Policy Training for Robot Navigation within 20 Seconds<br><a href='http://arxiv.org/pdf/2606.15846'>论文</a></td><td>本文提出了FlashNav框架，首次将基于深度强化学习的机器人导航策略训练时间缩短至20秒以内。
该框架训练出的策略能够成功迁移至真实的轮式和足式机器人，在静态与动态室内场景中均展现出可靠的避障能力。
◆提出与导航MDP对齐的仿真理念，保留占据几何与测距感知等核心组件，移除冗余的渲染与高保真物理细节。
◆设计基于批量位图仿真器的全GPU常驻训练流水线，结合FastDSAC学习器在GPU上生成海量并行导航交互数据。
实验表明该框架在多种桌面GPU上均能实现数十秒内的极速训练，并在高端显卡上达到百分之百的成功率。</td></tr>
<tr><td>2026-06-14</td><td>Can Causal Models Enhance Robot Navigation? Online Causal Adaptation for Real-Robot Navigation<br><a href='http://arxiv.org/pdf/2606.15691'>论文</a></td><td>本文核心贡献在于成功将因果模型集成到真实机器人导航系统中，解决了因果模型在真实环境中部署研究不足的问题。
◆提出将因果模型作为离线评估模块，能准确预测导航轨迹的能力，其预测结果与路径效率正相关且与人类标注高度一致。
◆提出将因果模型作为在线自适应模块，在默认导航能力预测较低时进行干预，显著提升了转弯和避障等复杂场景的导航性能。
实验表明因果模型在任务复杂性增加时对导航的增强尤为有效，而在基线已近最优的简单场景中提升有限。
综上，本研究证明了用于行为解释的因果模型能够成功融入并增强真实机器人的导航系统。</td></tr>
<tr><td>2026-06-13</td><td>G2IA: Geometry-Guided Instance-Aware Retrieval and Refinement for Cross-Modal Place Recognition<br><a href='http://arxiv.org/pdf/2606.15287'>论文</a></td><td>本文提出了一种用于跨模态地点识别的几何引导实例感知框架G2IA，突破了传统单一全局描述符匹配的局限，有效应对图像与点云间的模态差异和感知歧义问题。
◆在检索阶段，该框架创新性地将VGGT的视觉几何先验与实例特征相融合，构建出与激光雷达地图表征高度兼容的地点描述符。
◆在精炼阶段，提出通过显式验证局部实例形状及其相对空间布局在跨模态间的一致性，对检索候选进行细粒度重排。
实验证明，G2IA在不同定位阈值下均持续提升了图像到点云的地点识别性能。
同时，该框架还展现出了优异的跨数据集泛化能力。</td></tr>
<tr><td>2026-06-13</td><td>Driving, Fast or Slow? Neuro-Symbolic Guidance for Motion Prediction in Multi-Modal Ground Mobility<br><a href='http://arxiv.org/pdf/2606.15251'>论文</a></td><td>本文提出轨迹合规塑造神经符号框架，通过可解释的概率一阶逻辑增强黑盒运动预测主干网络，解决了现有方法缺乏现实交通规则与行为约束显式编码的问题。
◆提出智能体代码生成流水线，成功将交通规则的自然语言描述转化为概率运动预测的约束。
◆引入反应式数据流推理引擎，能够在场景演进时高效维护并更新合规态势。
◆设计神经置信度评分机制，通过上下文感知衰减合规信号，防止过度自信地误导主干网络的预测方向。
在Argoverse 2基准上的实验表明，该框架能持续提升最先进预测主干的性能，是纯神经预测器的有效且高效的补充。</td></tr>
<tr><td>2026-06-12</td><td>Sensitivity Shaping for Latent Modeling<br><a href='http://arxiv.org/pdf/2606.14585'>论文</a></td><td>本文针对生成式动力学模型中安全检测策略引发的分布外转换问题进行了研究。
现有方法在动力学对关键动作局部不敏感时会失效，导致未支持的动作产生类似演示的预测，从而掩盖了真实的预测误差。
◆揭示了现有固定动力学模型附加事后支持代理时，因局部控制不敏感导致分布外检测信号被抑制的失效机理。
◆提出了支持条件控制灵敏度正则化方法，在高等支持训练区域促进动力学对控制输入变化的敏感局部响应。
◆通过该正则化机制，有效保留了控制引起的变异，同时限制了因经验支持不足导致的不稳定外推。
实验表明该方法显著提升了分布外检测的准确性和闭环规划的安全性。</td></tr>
<tr><td>2026-06-13</td><td>GuideWalk: Learning Unified Autonomous Navigation and Locomotion for Humanoid Robots across Versatile Terrains<br><a href='http://arxiv.org/pdf/2606.10449'>论文</a></td><td>本文提出了GuideWalk，一个统一的端到端框架，将可穿越性感知的导航引导与地形自适应运动教师相结合，以解决人形机器人在复杂地形上难以协调避障与动态可行运动的导航挑战。
◆提出一种提供显式速度引导的导航模块，将避障与地形条件解耦，从而实现跨多样环境的鲁棒规划。
◆设计了复合教师蒸馏方案，将目标导向指令和动态一致动作聚合并蒸馏至单一策略中。
◆结合强化学习和辅助行为克隆目标对蒸馏策略进行优化，在促进探索的同时保留了教师的优秀行为，进一步提升了鲁棒性。
实验证明，GuideWalk能够在保持人形机器人稳定运动的同时，实现有效且稳健的导航。</td></tr>
</tbody>
</table>
</div>

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-06-22</td><td>Decentralized Autonomous Traffic Management through Corridor Networks<br><a href='http://arxiv.org/pdf/2606.23585'>论文</a></td><td>◆论文提出一种面向高级空中交通走廊网络的去中心化自治交通管理方法，以应对高密度载人/无人航空器协同难题。  
◆其核心创新是将多智能体强化学习从单走廊场景扩展到包含汇入、分流等结构的多走廊网络。  
◆训练策略可在更复杂网络中零样本迁移，无需集中式协调或重新训练。  
◆实验表明，该方法对交通密度变化、网络几何差异和异构飞行器性能具有良好泛化能力。  
◆仅依赖局部的进入、穿越和退出协同行为，系统仍能实现较好的边界遵循、完成率、速度、路径效率和安全间隔保持。</td></tr>
<tr><td>2026-06-22</td><td>Dense Reward for Multi-View 3D Reasoning with Global Maps and Local Views<br><a href='http://arxiv.org/pdf/2606.23557'>论文</a></td><td>◆提出DR-MV3D，一个面向多视角3D视觉问答的地图驱动学习框架，用密集、可验证奖励缓解仅靠答案级监督导致的跨视角推理不一致问题。
◆将任务分解为全局3D地图构建、问题条件下的视角轨迹规划，以及基于局部视图的自我中心 grounding 与答案预测。
◆设计全局一致性奖励，利用冻结的3D视觉基础模型生成几何一致伪标签，监督模型学习可靠的场景地图。
◆设计局部轨迹奖励，直接约束有序视角选择过程，提升多步空间推理中的视角规划能力。
◆通过GRPO进行轨迹级策略优化，并在MindCube、VSI-Bench和BLINK(MV)上优于强多图像基线，证明过程级密集监督对MV3D-VQA有效。</td></tr>
<tr><td>2026-06-22</td><td>FPAS: Frontier-Based Path Planning with Adaptive Sampling for Large-Scale Unknown Environments<br><a href='http://arxiv.org/pdf/2606.22838'>论文</a></td><td>◆ FPAS提出了一种面向大规模未知环境的前沿驱动路径规划框架，专注于提升长距离目标到达任务的效率。
◆ 该方法重新定义并利用frontier概念，不仅用于探索未知区域，还用于引导机器人朝目标方向持续推进。
◆ 在遇到死胡同或低效路径时，FPAS可基于frontier选择更有潜力的子目标，从而实现有效回退与重规划。
◆ 论文引入基于frontier开放度指标的自适应采样机制，在开阔区域稀疏建图以降低计算开销，在狭窄通道保持较高采样密度以保证连通性。
◆ 实验表明，FPAS在保持较强目标到达能力的同时，相比基线方法显著提升了计算效率，适合大规模未知环境导航。</td></tr>
<tr><td>2026-06-21</td><td>Interpolations: a linear algebra approach<br><a href='http://arxiv.org/pdf/2606.22671'>论文</a></td><td>◆本文提出一个统一的线性代数插值框架，将拉格朗日插值、Hermite样条和三角插值等问题表述为有限维函数空间对偶空间中的线性泛函条件。
◆论文建立了通用的存在唯一性定理，使插值问题可通过维数匹配与泛函线性无关性来判定。
◆作者推导了与给定插值条件对偶的基函数显式公式，从而可高效构造插值函数。
◆该框架扩展到三角插值，给出闭式对偶基并分析退化条件。
◆论文还处理异构传感器场景，即不同位置给定函数值与导数，并展示其在轨迹规划和信号处理中的应用潜力。</td></tr>
<tr><td>2026-06-21</td><td>Semantic-Aware Autonomous Exploration for UAVs in Unknown Indoor Environments<br><a href='http://arxiv.org/pdf/2606.22670'>论文</a></td><td>◆提出一种面向未知室内环境的语义感知无人机自主探索框架，将语义信息融入传统基于几何的探索流程。
◆在Dynamic Exploration Planner基础上，增量构建PRM并增加语义层，使路线图同时表达空间连通性与场景语义价值。
◆设计语义奖励函数，优先引导无人机探索包含关键物体或结构的高信息量区域，从而提升探索效率。
◆通过持续更新路线图，实现更高效的前沿选择与路径规划，适应探索过程中不断变化的环境认知。
◆在ROS Noetic与Gazebo中基于RGB-D传感器验证，实验表明该方法达到90%至94%的覆盖率，并相比几何方法减少探索时间和飞行距离。</td></tr>
<tr><td>2026-06-21</td><td>LAWNs Meet SWIPT: Beamforming and Power Splitting Optimization for Predictive Control<br><a href='http://arxiv.org/pdf/2606.22534'>论文</a></td><td>◆论文首次面向SWIPT赋能的低空无线网络，研究多天线基站同时向多架UAS传输控制信息与无线能量的联合设计问题。

◆针对存在多个移动禁飞区的场景，引入流函数理论构造平滑且安全的参考轨迹，实现无碰撞路径规划。

◆建立实时联合优化框架，同时优化控制输入、发射波束成形向量和功率分割比例，以兼顾轨迹跟踪精度与能量可持续性。

◆提出两阶段求解方法：先基于MPC生成预测控制输入，再结合SDR与SCA高效优化通信与能量传输变量。

◆论文证明了所用SDR在该问题中的紧性，并通过仿真表明该方案在跟踪精度和能量收集方面显著优于基准方法。</td></tr>
<tr><td>2026-06-19</td><td>THREAD: Trajectory Planning for Hybrid Rigid-Soft Manipulators with Environment-Aware Diffusion<br><a href='http://arxiv.org/pdf/2606.21792'>论文</a></td><td>◆提出THREAD，首个面向刚柔混合机械臂的扩散式轨迹规划器，专门解决狭窄孔洞穿越等受限环境操作难题。
◆方法学习在局部环境几何条件下物理可实现的骨架轨迹生成先验，而非仅在自由空间规划。
◆将刚性段与软体段联合建模，避免独立规划带来的运动学耦合失配问题。
◆引入受物理启发的损失函数，同时约束曲率、轨迹平滑性和碰撞风险，提升可行性与安全性。
◆仿真结果显示THREAD达到92.4%任务成功率，碰撞次数比最强基线少5倍。
◆系统还能以少量在线更新实现跨本体真实迁移，并成功穿过仅为软体段直径1.3倍的小孔。</td></tr>
<tr><td>2026-06-19</td><td>Temporal logics and formal synthesis for robot planning and control<br><a href='http://arxiv.org/pdf/2606.21438'>论文</a></td><td>◆论文系统阐述了时序逻辑，尤其是线性时序逻辑和信号时序逻辑，如何用于精确描述机器人随时间变化的复杂行为需求。

◆其核心贡献是将机器人规划与控制问题统一到“形式化规约—自动合成—可证明保证”的框架中。

◆论文梳理了多类形式化合成方法，包括离散图搜索、博弈模型、采样式运动规划、轨迹优化和基于控制证书的方法。

◆创新点在于强调从高层逻辑任务到低层连续控制之间的衔接，使机器人行为不仅可执行，而且可验证。

◆论文还指出真实机器人部署中的关键挑战：模型精度、计算复杂度与可获得的严格保证之间需要权衡。</td></tr>
<tr><td>2026-06-18</td><td>Increasing Resilience of Continuum Robots via Motion Planning Algorithms<br><a href='http://arxiv.org/pdf/2606.20495'>论文</a></td><td>◆ 本文面向连续体机器人韧性提升问题，系统研究了运动规划算法在多准则决策下对路径质量与执行时间的影响。

◆ 作者将层次分析法AHP引入遗传算法和A星算法，用距离、电机损伤、机械臂损伤和精度四项指标综合评估路径优劣。

◆ 论文的核心创新在于把“减少维护需求、延长运行时间”的韧性目标转化为可量化的路径规划评价准则。

◆ 实验在两个模拟环境中进行，并结合真实机器人原型特征设计单路径点和多路径点场景，提高了验证的针对性。

◆ 结果表明，遗传算法的运行时间对环境规模不敏感，且能生成更多样化路径，相比A星更有利于提升连续体机器人的韧性。</td></tr>
<tr><td>2026-06-18</td><td>Autonomous Driving with Priority-Ordered STL Specifications Under Multimodal Uncertainty<br><a href='http://arxiv.org/pdf/2606.20336'>论文</a></td><td>◆提出一种面向自动驾驶的轨迹规划框架，将多项Signal Temporal Logic规范按词典序优先级组织，用于处理安全、舒适性和交通规则之间的冲突。

◆该方法在规划中显式考虑周围交通参与者轨迹预测的多模态不确定性，使规范满足性在不确定环境下仍具有意义。

◆框架能够在无法同时满足所有要求时，优先保证更高优先级规范，例如安全约束，再尽量优化低优先级目标。

◆作者将该优先级STL formulation与Model Predictive Path Integral控制结合，实现可用于在线轨迹生成的求解方案。

◆仿真实验表明，该方法能在现实多模态不确定场景中高效处理冲突目标，并生成更符合安全关键需求的驾驶行为。</td></tr>
<tr><td>2026-06-17</td><td>Admittance-Based Surface Alignment for Human-in-the-Loop Robotic Visual Inspection<br><a href='http://arxiv.org/pdf/2606.18601'>论文</a></td><td>◆提出一种面向人机协同机器人视觉检测的实时闭环姿态控制流程，解决感知噪声、表面不规则和人工遥操作共同作用下的表面对齐问题。
◆将操作员输入与视觉感知得到的表面法向对齐目标统一到导纳控制框架中，实现共享自治下的柔顺响应。
◆创新性地把末端执行器建模为在黏性介质中运动的虚拟球体，用可解释的质量-阻尼系统生成同步、平滑的姿态调整。
◆相比纯离线规划，该方法能够根据实时表面几何误差和人工指令动态修正运动，更适合工业在线检测场景。
◆在6自由度机械臂上验证了系统的稳定法向跟踪能力，最终平均姿态误差达到0.4°，体现出较高精度。</td></tr>
<tr><td>2026-06-16</td><td>Task Allocation and Motion Planning in Dynamic, Cluttered Environments via CBBA and Graphs of Convex Sets<br><a href='http://arxiv.org/pdf/2606.18516'>论文</a></td><td>◆论文提出一种面向动态、杂乱环境的多智能体任务分配与运动规划联合框架，将CBBA分布式任务分配与GCS轨迹优化相结合。

◆利用时间扩展的3D+time配置空间，GCS能够在存在静态和动态障碍的场景中生成安全且时间高效的最优轨迹。

◆方法将任务分配与轨迹规划紧密耦合，使CBBA在决策时不仅考虑任务归属，还考虑智能体到达动态任务的时间和位置可行性。

◆该框架支持动态任务如会合目标的分配，能够提供更准确的任务完成时间估计，从而提升分配质量。

◆通过在3D+time空间中协调路径，系统可降低多智能体间碰撞风险，并在仿真杂乱环境中验证了有效性。</td></tr>
<tr><td>2026-06-16</td><td>LAGO Policy: Latency-Aware Asynchronous Diffusion Policies with Goal-Directed Collision-Free Planning for Smooth Manipulation<br><a href='http://arxiv.org/pdf/2606.17982'>论文</a> | <a href='https://lago-policy.github.io/'>代码</a></td><td>LAGO Policy针对异步扩散视觉运动策略在真实机器人中易出现动作块间不连续、运动抖动和碰撞的问题，提出了一个兼顾平滑性、安全性与实时执行的统一框架。
◆ 通过延迟感知的classifier-free guidance，将未来动作作为条件引入扩散策略，显著提升异步推理下的动作块间一致性。
◆ 从示范数据中预测任务相关交互目标，使策略具备面向目标的避障与无碰撞轨迹规划能力。
◆ 引入时空轨迹优化，对即将执行的动作进行低加加速度、可行性和安全性约束下的细化。
◆ 将扩散策略生成、目标推断与轨迹优化整合到同一异步动作生成流程中，提升真实场景部署可靠性。
实验表明，LAGO Policy在多种复杂操作任务中实现了更平滑、更安全的执行，并保持较高任务成功率。</td></tr>
<tr><td>2026-06-16</td><td>FLAP: FOV-Constrained Active Perception Planning for Prior-Map-Free 3D Navigation<br><a href='http://arxiv.org/pdf/2606.17630'>论文</a></td><td>◆本文提出FLAP框架，将主动感知直接融入未知复杂3D环境中的无人机轨迹优化，以兼顾安全性与飞行效率。
◆其感知约束由无人机动力学推导，并在传感器坐标系中建模，从而更精确处理有限视场和探测距离。
◆论文设计了速度触发的感知约束激活机制，使规划器能根据运动状态动态权衡避障感知与轨迹效率。
◆方法引入带参数化起始时间优化的主动感知子轨迹段，降低因障碍物发现过晚导致的碰撞风险。
◆该框架支持任意3D机动中的主动感知，无需依赖昂贵的感知感知前端路径生成器，并在仿真和真实实验中验证了对不同环境与传感器配置的鲁棒性。</td></tr>
<tr><td>2026-06-18</td><td>DIFF-IPPO: Diffusion-Based Informative Path Planning with Open-Vocabulary Belief Maps<br><a href='http://arxiv.org/pdf/2606.16780'>论文</a></td><td>本文提出了DIFF-IPPO框架，将开放词汇信念图生成器与基于扩散的规划器相结合用于信息性路径规划。
◆提出将基于扩散模型的规划器引入信息性路径规划，突破了现有方法难以直接基于非高斯多模态信念图生成全局轨迹的局限。
◆构建了结合开放词汇感知与扩散规划的流水线，使生成的轨迹能将传感器覆盖集中于高信念区域。
该方法在多场景中取得了81.49%至86.55%的归一化检测得分。
在模拟搜救任务中，五架无人机利用批处理条件轨迹生成，仅3.5分钟即可首次定位目标。</td></tr>
<tr><td>2026-06-15</td><td>WaveSync: Constrained Wavefront Optimization for Synchronized Co-Speech Gestures in Humanoid Robots<br><a href='http://arxiv.org/pdf/2606.16600'>论文</a> | <a href='https://github.com/pairs-lab/WaveSync}{WaveSync}'>代码</a></td><td>本文提出了WaveSync混合框架，解决了人形机器人生成共语手势时难以兼顾语音同步与硬件运动约束的耦合难题。
◆利用大语言模型将对话分解为结构化语义模式并分配逐词重要性权重，创新性地构建出连续的语义重要性波形。
◆采用动态运动基元塑造手势轨迹，在增强手势表现力的同时严格保证了运动的运动学可行性。
◆引入波前优化阶段，通过手势时长压缩与前向传播机制，实现手势与语音的峰值对齐并解决残余的运动学违规问题。
实验表明该方法实现了高同步精度，在客观与主观评估中均超越基线，且各组件对生成富有表现力且符合运动学规范的手势均不可或缺。</td></tr>
<tr><td>2026-06-15</td><td>Steering Emotional Dynamics for Art Therapy: Controllable Narrative Script Generation through Hierarchically Guided LLM Agents<br><a href='http://arxiv.org/pdf/2606.16481'>论文</a></td><td>本文提出了EC-Script框架，一种基于大语言模型智能体的分层控制框架，解决了现有文本生成方法无法遵循指定情感轨迹以满足艺术治疗需求的问题。
◆通过情感轨迹规划建立整体叙事方向，确保叙事的宏观情感走向受控。
◆采用角色驱动的场景生成推进场景级情节发展，使情节逻辑与角色状态契合。
◆利用情感控制的剧本编写调节角色局部情感变化，精细管理微观情感波动。
实验表明，该框架生成的逐场景剧本与预设轨迹高度一致，在情感轨迹遵循度上显著优于基线方法。
该研究实现了叙事生成中情感动态的有效导向，为AI辅助情感疗愈提供了可靠技术支持。</td></tr>
<tr><td>2026-06-15</td><td>HOLO-MPPI: Multi-Scenario Motion Planning via Hierarchical Policy Optimization<br><a href='http://arxiv.org/pdf/2606.16480'>论文</a></td><td>◆ 提出HOLO-MPPI框架，将离线高层策略学习与在线低层MPPI随机最优控制结合，用于无需逐场景调参的多场景运动规划。

◆ 离线阶段学习一个在抽象动作空间中生成鲁棒计划的高层策略，并配合学习到的世界模型支持在线预测与评估。

◆ 在线阶段让高层策略作为数据驱动的先验生成器，根据当前观测和目标动态参数化MPPI的采样分布，避免手工设计先验难以扩展的问题。

◆ 通过MPPI在高层先验附近实时优化低层控制序列，使系统既具备跨场景泛化能力，又能适应局部扰动和随机交互。

◆ 在自动驾驶任务中，论文设计了有效的高层动作空间和针对性的模型结构，并在多种驾驶场景中验证其优于传统MPPI和端到端RL基线，同时保持实时控制性能。</td></tr>
<tr><td>2026-06-15</td><td>Game-Theoretic Multi-Agent Reinforcement Learning for Swarm Trajectory Planning in Low-Altitude Wireless Networks<br><a href='http://arxiv.org/pdf/2606.16386'>论文</a></td><td>本文针对低空无线网络中多小区场景下无人机群轨迹规划存在资源块分配引发强战略耦合的问题进行研究。为了在通信吞吐量和任务完成效率之间取得平衡并解决多小区资源拥塞问题，作者提出了一种基于博弈论的多智能体强化学习框架。
◆将多小区拥塞感知的无人机轨迹规划问题构建为具有通信与任务感知效用函数的合作随机拥塞博弈。
◆提出一种集中训练分布式执行的多智能体近端策略优化算法，以在多小区资源拥塞下最大化社会效益。
仿真结果表明，该方法在总体效用和任务成功率上优于多种基线算法，且能在实际训练预算内实现稳定收敛。</td></tr>
<tr><td>2026-06-15</td><td>GraphWorld: Long-Horizon Planning with World Models for End-to-End Autonomous Driving<br><a href='http://arxiv.org/pdf/2606.16274'>论文</a></td><td>针对现有端到端自动驾驶方法局限于短期规划且缺乏长期时序依赖建模的问题，本文提出了GraphWorld框架，通过隐式世界模型显式增强长视距规划能力。
◆提出以自车为中心的交互图，基于空间距离自适应建模关键相邻智能体，并通过跨节点交叉注意力将关系上下文传播至规划查询。
◆提出世界状态条件规划，通过建模自车与周围智能体的交互来学习以自车为中心的隐式世界表征。
该表征捕捉了关键的交互动态与安全语义，并作为条件信号引导具有安全意识的长视距轨迹规划。
实验表明，GraphWorld显著降低了碰撞率并提升了长视距规划性能，验证了其在复杂驾驶环境中的有效性。</td></tr>
</tbody>
</table>
</div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
</tbody>
</table>
</div>

<h2 id='sensor-undistortion'>Sensor Undistortion</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-06-17</td><td>Optimal transport of signed fractal measures with dimensional distortion: a variational characterization<br><a href='http://arxiv.org/pdf/2606.19631'>论文</a></td><td>◆本文将带符号测度的最优传输理论扩展到Ahlfors正则分形支撑集之间，并允许源与目标存在可控的局部维数扭曲。

◆通过在跨符号传输成本中加入εΦ(ds(x)-dt(y))惩罚项，论文刻画了维数不匹配对最优传输结构的影响。

◆在H1--H7条件下，证明了任意ε&gt;0时最优传输映射Tε的存在性与唯一性。

◆论文推导出带维数扭曲修正项的耦合Monge--Ampère方程，推广了经典Brenier--Caffarelli框架。

◆核心创新是提出双Legendre--Fenchel表征，证明四种符号传输情形下最优势函数是共轭方程系统的唯一不动点。

◆该变分刻画为后续数值算法设计和ε渐近分析提供了统一理论基础。</td></tr>
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
<tr><td>2026-06-12</td><td>HumP-KD: A Hybrid Uncertainty-Aware Multi-Stage Progressive Knowledge Distillation Framework for Efficient Fire Classification<br><a href='http://arxiv.org/pdf/2606.14684'>论文</a></td><td>本文提出了HumP-KD框架，用于在资源受限硬件上实现高效且可部署的实时火灾分类。
◆提出混合异构教师知识蒸馏，将冻结的Swin-Tiny和ViT-Base及其Meta-MLP集成的知识蒸馏到轻量级MobileViT-S中。
◆设计层次渐进式知识蒸馏，通过层次特征构建器生成融合空间注意力掩码，选择性引导蒸馏关注判别性区域。
◆引入多阶段知识蒸馏机制，在训练中逐步激活三个蒸馏阶段。
实验表明该方法F1分数达0.9876，显著优于无蒸馏基线，且具备强鲁棒性与泛化能力。
学生模型仅4.94M参数，参数缩减最高达17.5倍，CPU帧率达37.72FPS，完全满足实时部署需求。</td></tr>
<tr><td>2026-06-12</td><td>FEMOT: Multi-Object Tracking using Frame and Event Cameras<br><a href='http://arxiv.org/pdf/2606.14094'>论文</a> | <a href='https://github.com/Event-AHU/FEMOT'>代码</a></td><td>针对RGB相机在复杂场景下性能受限且RGB-事件多目标跟踪缺乏数据的问题，本文提出了FEMOT数据集及FEMOTR框架。
◆构建了大规模RGB-事件多目标跟踪数据集FEMOT，涵盖多样真实场景与14个挑战属性，填补了该领域缺乏高质量标注数据的空白。
◆基于该数据集评估了十余种先进跟踪器，建立了全面的综合基准，为未来研究提供可靠平台。
◆提出多模态跟踪框架FEMOTR，在频域中对RGB和事件特征进行解耦与融合。
该机制有效利用了两者的互补特性，实现了更鲁棒的目标定位与身份关联。
在FEMOT和DSEC-MOT数据集上的广泛实验充分验证了所提方法的有效性。</td></tr>
<tr><td>2026-06-11</td><td>Observation of intertwined charge density wave order and superconductivity in Janus monolayer<br><a href='http://arxiv.org/pdf/2606.13828'>论文</a></td><td>◆本文首次基于第一性原理系统研究了Janus单层1T-ZrSeTe中电荷密度波与超导不稳定性的共存和相互关联。
◆发现其声子谱在M点存在显著软化，源于增强的电子-声子耦合以及带间、带内散射共同导致的电子不稳定性。
◆揭示2×2×1晶格畸变会重构能带并打开小的间接带隙，使体系由半金属性转变为半导体。
◆与ZrTe2单层相比，Se替代一层Te显著降低畸变能量收益，说明Janus结构削弱了CDW不稳定性。
◆论文进一步证明电子关联和双轴应变可有效调控CDW与超导不稳定性。
◆在高温未畸变相中，ZrSeTe表现出声子介导的双能隙超导，主要来自M点软模与Zr d、Te p轨道费米面能带的强耦合，而SOC会降低超导转变温度。</td></tr>
<tr><td>2026-06-11</td><td>Revisiting Vehicle Color Recognition in Long-Tailed Surveillance Scenarios<br><a href='http://arxiv.org/pdf/2606.13625'>论文</a> | <a href='https://github.com/viniciusorru/vcr-synthetic'>代码</a></td><td>该论文针对监控场景下车辆颜色识别中存在的严重类别不平衡问题,基于真实世界数据集 UFPR-VeSV 开展了系统性研究。作者结合生成式数据增强、现代视觉表征、损失重加权、学习率调度、颜色安全增强、前景感知预处理与集成融合等多种策略,显著提升了对稀有颜色类别的识别性能。最终方法在微观准确率上达到 94.6%,宏观准确率达 79.7%,相比最新文献宏观准确率提升 8.2 个百分点。此外,作者通过人工错误分析指出,部分剩余错误即使对人类标注者也存在视觉模糊性,从而揭示了基于颜色的车辆识别在非受限监控图像中的实际局限。

核心创新点如下:

◆ 首次系统性地将文本条件生成(RunDiffusion/JuggernautXL)与图像条件颜色编辑(Gemini 2.0 Flash)两种现成生成式策略应用于车辆颜色少数类的合成增强。

◆ 提出综合性训练流程,将合成数据与损失重加权、颜色安全数据增强、前景感知预处理及集成融合相结合,有效缓解长尾分布问题。

◆ 在 UFPR-VeSV 数据集上取得 SOTA 性能,宏观准确率较已有文献提升 8.2 个百分点,显著改善稀有颜色类别的识别效果。

◆ 通过人工错误分析揭示了颜色识别任务的固有视觉模糊性,为该领域的性能上限提供了实证依据。

◆ 开源了所生成的合成图像与完整源码,促进后续在长尾监控场景下的可复现研究。</td></tr>
<tr><td>2026-06-10</td><td>TESS detection of periodic brightness variations during the rise of classical nova PGIR22akgylf<br><a href='http://arxiv.org/pdf/2606.12532'>论文</a></td><td>这篇论文利用TESS空间望远镜对缓慢上升型经典新星PGIR22akgylf进行了高精度光度监测,覆盖了新星发现后3到16天的关键阶段,并辅以地面观测追踪了其长达约133天的完整上升过程。研究团队探测到周期为0.1802±0.0012天、峰峰振幅约0.02星等的周期性亮度变化,该信号在TESS观测的两周内保持稳定,暗示其源于双星轨道运动。作者据此推断伴星为矮星,并提出周期性信号是由于双星轨道运动使新星包层(此时尺度与双星轨道间距相当)发生形变所致,从而揭示了公共包层相互作用在该新星壳层抛射中的重要作用。

◆ 首次在经典新星上升阶段利用TESS高精度光度数据探测到稳定的周期性亮度调制信号,为研究新星包层结构提供了新观测窗口。

◆ 提出周期性光变源自双星轨道运动对膨胀新星包层的形变作用这一新颖物理解释,将光变特征与包层几何结构直接关联。

◆ 首次为经典新星缓慢上升阶段提供了公共包层相互作用参与壳层抛射的直接观测证据。

◆ 打破了缓慢上升现象仅存在于共生双星热核爆发中的传统认知,证明该现象同样可发生于含矮星伴星的紧致双星系统中。

◆ 通过周期稳定性和轨道动力学分析,首次利用上升阶段光变对新星伴星性质(矮星)做出限定,为新星双星系统参数测定提供了新方法。</td></tr>
<tr><td>2026-06-10</td><td>Spatially Coupled Phase-to-Depth Calibration for Fringe Projection Profilometry<br><a href='http://arxiv.org/pdf/2606.11601'>论文</a></td><td>针对条纹投影轮廓术中逐像素独立拟合导致的空间不一致和结构化伪影问题，本文提出了一种空间耦合的相位深度标定方法。
◆提出空间耦合的相位深度变换模型，所有像素共享由全局相位标量与仿射空间项构成的单个低维映射，替代独立的逐像素拟合，并可选附加有界平滑修正场。
◆引入原生网格配对方案，直接在参考相机网格上构建相位深度标定对，将立体三维平面沿原生光线采样回相机网格，从而避免对相位图进行纠正。
在具备高分辨率真值的牙科目标上，该方法取得了与主动立体参考相当的点对面均方根误差（约12微米）。
相比传统逐像素标定法，它不仅大幅提升了空间一致性，还将运行时映射简化为少量的逐像素元素级操作，参数存储几乎可忽略。</td></tr>
<tr><td>2026-06-09</td><td>A Multimodal RGB and Events Dataset for Hand Detection in First-Person View<br><a href='http://arxiv.org/pdf/2606.10790'>论文</a></td><td>该论文针对事件相机在手部检测中训练数据匮乏的瓶颈，提出了一种合成第一人称视角事件数据集的方法。
◆提出利用现有RGB Egohands数据集结合v2e工具箱，合成第一人称视角事件相机手部数据集的方法。
◆通过变化v2e工具箱参数，生成了涵盖不同光照条件和尺度的多版本数据集，增强了数据多样性。
◆设计了结合微调YOLOv8模型与时间插值的标注策略，实现了高时间分辨率事件数据的真值生成。
研究最终构建了多模态RGB与事件数据集，并利用现有多模态算法验证了其有效性，达到了与前沿方法媲美的检测性能。</td></tr>
<tr><td>2026-06-08</td><td>Dense Force Estimation with an Event-based Optical Tactile Sensor<br><a href='http://arxiv.org/pdf/2606.09451'>论文</a></td><td>本文提出了首个基于事件光学触觉传感器的密集三维力场重建框架，解决了现有事件传感器仅能预测整体净力的问题。
◆提出基于事件的标记跟踪算法以恢复触觉表面的剪切位移。
◆利用卷积神经网络预测法向位移，并收集了同步的力-位移-事件数据集用于训练。
◆创新性地通过逆有限元法将三维表面位移映射为物理受力。
实验表明该框架在最高20N受力范围内实现了低误差精准重建，平均运行频率达100Hz。
此工作为机器人抓取与灵巧操作的高频控制迈出了密集力反馈的第一步。</td></tr>
<tr><td>2026-06-08</td><td>Beyond Humans: Multispecies Animal Face Recognition Using Transfer Learning<br><a href='http://arxiv.org/pdf/2606.09353'>论文</a></td><td>该论文针对传统动物识别物理设备不实用且现有动物面部数据集规模小难以训练深度学习模型的问题，提出利用迁移学习实现多物种动物面部识别的方法。
◆创新性地探索了利用在大规模人类面部或通用物体数据集上预训练的模型作为骨干网络，解决动物面部数据不足的迁移学习方案。
◆首次系统比较了专门针对人类面部训练的FaceNet与在通用物体类别上预训练的Vision Transformer在跨物种动物面部识别上的性能差异。
研究在狗、灵长类和牛这三个图像质量与捕获条件差异极大的数据集上进行了验证。
结果表明，Vision Transformer在狗和牛的数据集上表现优异且超越了现有最优方法，而在图像质量较差的灵长类数据集上虽具鼓励性但表现波动。</td></tr>
<tr><td>2026-06-07</td><td>Magnetic Brunn-Minkowski inequalities<br><a href='http://arxiv.org/pdf/2606.08626'>论文</a></td><td>本文研究了黎曼流形上的闵可夫斯基平均，其中插值由给定磁势下作用量最小化的磁测地线实现。
◆建立了该操作的布鲁恩-闵可夫斯基不等式与磁里奇曲率下界之间的等价关系。
◆探讨了Kähler流形和Sasakian流形上的自然磁场等多种实例。
◆为海森堡群上的接触磁测地线证明了一个尖锐且无畸变的布鲁恩-闵可夫斯基不等式。
◆发现来自不同上同调类的闭磁势可能会产生不同的测地线闵可夫斯基平均。</td></tr>
<tr><td>2026-06-12</td><td>An ultra-wide-bandgap semiconductor photodetector for linear measurement of bright sub-bandgap light<br><a href='http://arxiv.org/pdf/2606.07807'>论文</a></td><td>本文提出了一种亚带隙氮化铝光电探测器，解决了传统探测器在中低强度光下易饱和的问题。
◆实现了对超过40瓦每平方厘米的超强蓝光的非饱和线性响应。
◆在高达300摄氏度的高温下依然保持无失真的线性响应。
◆揭示了金属-氮化铝肖特基结处深能级点缺陷介导光响应的物理机制。
◆通过掺杂和接触工程证明，窄空间电荷区是实现超强光探测与精确测量的关键。
该研究为超宽禁带半导体器件在航空航天及核电等极端条件下的可靠运行提供了工程策略。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>4829</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4231</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2411</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1611</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1606</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1427</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1263</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1249</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>944</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>941</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>917</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>795</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>780</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>742</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>723</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>708</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>638</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>636</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>622</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>591</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>565</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>554</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>537</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>501</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>486</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>438</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>410</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>342</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>340</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>264</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>252</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>243</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>235</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>222</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>199</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>199</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>167</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2844</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1641</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1351</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1095</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1036</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>871</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>697</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>656</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>649</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>621</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>583</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>573</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>567</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>562</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>551</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>515</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>483</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>461</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>445</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>442</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>335</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>312</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>298</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>281</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>279</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>257</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>221</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>206</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>202</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>187</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>176</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>169</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>166</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>159</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>153</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>137</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>136</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>131</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
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
> 更新于: 2026.06.23
