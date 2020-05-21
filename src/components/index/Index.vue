<template>
	<div class='content'>
		<div class="swiper">
			<Swiper v-if="list.length > 0" showIndicator="true" direction="horizontal" grabCursor="true" interval="5000" autoPlay="true" simulateTouch="true" class="swiper" freeMode="true" effect="coverflow" ref="swiper">
				<Slide v-for="(item,index) in list" :key="index">
					<img :src="item.pic_path" />
				</Slide>

			</Swiper>
			<div class="prev" @click="prev">
				<img src="../../assets/img/left.png"/>
			</div>
			<div class="next" @click="next">
				<img src="../../assets/img/left.png"/>
			</div>
		</div>
		<div class="service  wrap" id="zhuanye">
			<h1>专业服务</h1>
			<p class="p1">我们以技术服务为核心业务，并在此基础上提供行业应用软件等一系列信息服务</p>
			<div class="service-list">
				<div v-for="(item,index) in service" :key="index" :class="['single',index == nowService ? 'active' : '']"  @click="changeService(index)">
					<img :src="item.pic_path"/>
					<p>{{item.name}}</p>
				</div>

			</div>
			<div class="service-detail">

				<h2>{{service[nowService].name}}</h2>
				<p v-html="service[nowService].content">{{service[nowService].content}}</p>

			</div>
		</div>

		<div class="service hangye"  id="hangye">
			<h1>行业</h1>
			<p class="p1">我们与多个行业内知名企业合作，熟悉洞察行业现状及发展是我们一直在做的事</p>
			<div class="hangye-list wrap">
				<div class="single" v-for="(item,index) in hangye" :key="index" :title="item.content">
					<img :src="item.pic_path" class="img"/>
					<h3>{{item.name}}</h3>
					<p>{{item.content}}</p>
				</div>

			</div>
		</div>


		<div class="service about"  id="about">
			<h1>关于我们</h1>
			<p class="p1">博亚君杰注重创新和可持续发展，不断探索前沿技术与商业应用的无限可能</p>
			<div class="about-fenlei wrap">
				<div  v-for="(item,index) in about" :key="index" :class="['single',index == nowAbout ? 'active' : '']" @click="changeAbout(index)">
					{{item.name}}
				</div>

			</div>
			<div class="about-content wrap">
				<div class="img">
					<img :src="about[nowAbout].pic_path">
				</div>
				<div class="content" v-html="about[nowAbout].content">
					about[nowAbout].content
				</div>
			</div>
		</div>

		<div class="service hangye"  id="zhaopin">
			<h1>加入我们</h1>
			<p class="p1">人才即未来，博亚君杰的发展需要广纳贤才，凝聚人才</p>
			<div class="hangye-list wrap">
				<div class="single" v-for="(item,index) in zhaopin" :key="index" :title="item.content">
					<img src="../../../static/img/zhaopin.png" class="img"/>
					<h3>{{item.name}}</h3>
					<p>{{item.content}}</p>
				</div>

			</div>

			<div class="zhaopin-more wrap">
				请访问博亚君杰的招聘合作网站，了解我们最新的职位需求
				<div class="imgs">

					<img src="../../../static/img/zhilian.png"/>
					<img src="../../../static/img/qiancheng.png"/>
					<img src="../../../static/img/boos.png" />
					<img src="../../../static/img/lagou.png" />
				</div>
			</div>
		</div>

		<div class="service about"  id="lianxi">
			<h1>联系我们</h1>
			<div class="lianxi wrap">
				<div class='left'>
					<p>公司地址：北京市海淀区上地信息产业基地三街1号楼  </p>
					<p>服务热线：010-56207170</p>
					<p>邮箱：service@boya-isoft.com</p>
				</div>
				<div class="right">
					<div class="top">
						<input placeholder="您的名字"/>
						<input placeholder="您的电话"/>
					</div>
					<textarea placeholder="您的需求"></textarea>
					<div><button >确认提交</button></div>
				</div>
			</div>
		</div>

		<div class='footer'>
			<p>版权所有：北京博亚君杰科技有限公司 Copyright © 2019 All Rights Reserved 京ICP备19016084号-1</p>
			<p>公司地址：北京市海淀区上地信息产业基地三街1号楼</p>
			<p>联系电话：010-56207170 &nbsp;  邮箱：service@boya-isoft.com</p>
		</div>
	</div>
</template>

<script>
	import { Swiper, Slide } from 'vue-swiper-component'
	export default {
		data() {
			return {
				list: [{
					pic_path: '../static/img/banner1.png'
				}, {
					pic_path: '../static/img/banner2.png'
				},{
					pic_path: '../static/img/banner3.png'
				}],
				nowService:0,
				service:[
					{
						name:'应用软件开发与维护',
						content:'博亚君杰拥有专业化的应用开发服务团队，长期为客户提供端到端的应用软件开发和维护服务。凭借丰富项目实践经验，博亚君杰能够为客户提供包括：系统开发、平台开发、APP开发、项目定制等全栈服务，为客户提供更高的IT投资回报。<br><br>博亚君杰基于优异的项目管理、流程、工作方法和工具，保证每一个项目关键点的完成，为客户提供完善的开发与运维服务。<br><br>博亚君杰的应用开发与维护服务将IT与业务需求统一起来，能够帮助用户降低总拥有成本、降低运作风险、减少系统故障、维护系统稳定性，并对设施规划、设计和建造进行有效管理，为客户提供低成本、高质量的服务。<br><br>博亚君杰凭借在IT领域的行业经验和技术专长，能够帮助客户在短时间内组建专门的开发、测试、以及技术支持团队，提供专业现场技术服务。',
						pic_path:'../../static/img/kaifa.jpg'
					},
					{
						name:'测试服务',
						content:'在移动互联网等数字化革命浪潮不断的推动下，企业应用程序在激烈的市场竞争中面临着诸多的挑战，如何在竞争中不断的提高产品的质量，赢得更多的市场份额成为企业关注的重点，因此，企业应用测试也走向越来越重要的位置。<br><br>博亚君杰擅长专业的测试咨询和管理服务，以及高效的测试执行，权威的自动化测试和工具的开发等，并且拥有领先的测试技术和卓越测试中心的最佳实践，能够为客户提供灵活的、定制化的测试服务，确保客户产品高质量的交付<img src="../static/img/ceshi1.png" class="ceshi_img"/><img src="../static/img/ceshi2.png" class="ceshi_img"/>',
						pic_path:'../../static/img/pic2.jpg'
					},
					{
						name:'移动互联网服务',
						content:'专业、规范、先进的全方位技术服务体系<br><br>融合时尚设计元素，通过与移动互联网的实际应用紧密结合，博亚君杰能为客户提供专业、完善、创新的移动互联网服务，以及从服务端到移动终端的一体化解决方案。<br><br>博亚君杰在移动互联网应用开发的基础上，已经为众多客户提供专业化的终端应用适应性测试服务，帮助实现主流智能终端的自动化测试和适应性测试覆盖，有效降低基础测试平台投入。<div class="hangye-list yidong" style="justify-content: center;"><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>咨询服务</h3><p>从移动互联网的独特角度结合各行业特点，提供实用、高效、有价值的专业产品及技术咨询服务。</p></div><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>设计服务 </h3><p>提供从产品（Product）、交互（User Experience）、视觉（User Interface）等多维度的设计服务。同时，博亚君杰将客户需求和运营目标紧密结合，为企业运营管理提供完整的服务包和服务传递系统的规划与设计。 </p></div><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>开发服务 </h3><p>拥有多样化的专业移动设备和新媒体平台开发团队，提供基于iOS（iPhone、iPad）、Android、Windows Phon等设备的应用程序开发服务。  </p></div><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>测试服务</h3><p>范围包括：应用流程性测试、稳定性测试、适配性测试以及耗电量、流量测试。   </p></div></div><h3 style="margin-top:20px">我们的优势</h3><br> o 创新的产品及UE/UI设计理念<br> o 强大的技术开发和研发实力 <br> o 专业测试服务能力 <br> o 丰富的项目实施和管理经验 <br> o 完整高效的移动应用项目实施及管理体系 ',
						pic_path:'../../static/img/pic3.jpg'
					},
					{
						name:'IT基础设施管理服务',
						content:' IT基础设施的保障是企业组织内信息化运行的基础，随着企业信息化复杂程度不断加剧，基础设施的良好运行有助于提高组织内部管理效率，减少基于基础设施终端带来的业务风险。博亚君杰凭借多年的行业积累、深厚的行业专长和成熟的行业实践，为客户需求提供全方面的维护服务方案。<br><br>维护服务包括硬件系统维护支持服务、 基本级维护服务、标准级维护服务、增强级维护服务、顶级维护服务、软件系统维护支持服务 故障排除服务、预防性维护服务、软件产品的升级、技术交流与技术支持、软件配置优化服务、软件和数据的备份及恢复等 <div class="hangye-list yidong" style="justify-content: center;"><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>维护服务</h3><p>从硬件系统维护支持服务 基本级维护服务、标准级维护服务、增强级维护服务</p></div><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>顶级维护服务 </h3><p>软件系统维护支持服务 故障排除服务、预防性维护服务、软件产品的升级、技术交流与技术支持、软件配置优化服务、软件和数据的备份及恢复</p></div></div><h3 style="margin-top:20px">客户价值</h3><br>o 	端到端的服务方案，为客户节约成本、提高效率。<br>o 专业的资源管理，打造高质量服务团队。<br>o 全面的质量保障，专注、全面的质量管理体系保证高质量服务。<br>o 高效的管理系统，实现高效管理。',
						pic_path:'../../static/img/pic4.jpg'
					},
					{
						name:'业务流程服务外包',
						content:'如今，外包对于企业日益增长的需求是一种解决之道。随着商业能力的不断提升，外包已经不再仅是低成本劳动力，而是为实现更高效率的业务能力所采取的一项战略举措。其最终是要促进客户实际业务革新的成功。借助业务流程外包(BPO)，您的企业能够从劳动力密集型业务中解放出来并控制成本，同时您还能够专注于自身核心业务。<br> <br>博亚君杰通过充分利用质量标准和流程、深厚的知识以及工具和专家资源管理，为客户提供综合的BPO 解决方案。作为我们客户资源和能力的战略延伸，我们专注于建立深入持久的客户关系，以此为客户带来可观的价值。<br> <br> 博亚君杰可提供为您量身定做的BPO 解决方案，并可提供包含离岸开发中心(ODC) 最佳实践的BPO 解决方案。我们的目标是建立长期稳固的合作伙伴关系，由此降低成本并提升绩效，使企业能够更好地服务于他们的客户和股东。<BR><BR>博亚君杰基于多年的IT咨询与服务实践、以及对BPO业务的积极探索，博亚君杰造就了一支专业的BPO业务咨询和服务实施团队，积累了丰富的经验，拥有独特的服务优势，主要服务范围包括以下几个方面：<div class="hangye-list yidong" style="justify-content: center;"><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>技术支持</h3><p>台式机，笔记本，网络，软件支持、系统监控和远程管理、服务器和网络管理。</p></div><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>人事服务 </h3><p>主要提供绩效管理、工资核算、福利管理及核算、工资发放、报销发放、员工档案管理等。</p></div><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>数据管理及文档服务 </h3><p>主要包括元数据管理、记录管理、文档扫描和录入等。</p></div><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>客户支持服务</h3><p>主要包括客户桌面支持、电话呼入和呼出、客户信息核对、客户关怀、电话增值服务等。</p></div><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>数据管理和分析 </h3><p>数据管理和分析包含后勤支持服务（人力资源管理和文档管理），特殊领域的服务（法律和审计文档影像化服务），运营数据实时录入服务，股票固定收益和调研。</p></div><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>客户服务中心</h3><p>呼出处理：电话营销、电话照会、客户资料核对、市场调研、客户通知等；呼入处理：产品咨询、产品售后服务、产品相关使用服务、邮件处理等。</p></div></div>',
						pic_path:'../../static/img/pic6.jpg'
					},
					{
						name:'安全服务',
						content:'企业资产和数据的安全是一个企业的立命之本。随着信息化的快速发展，网络犯罪不断增加，各企业都在寻求高性价比、安全的系统平台以及可靠的合作伙伴。博亚君杰的信息安全服务为客户提供了全面实时的安全保护，通过端到端的全面覆盖避免突发事件的发生以及提前做好应对防护措施。<div class="hangye-list yidong" style="justify-content: center;"><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>端点安全管理</h3><p>提供的服务包括防病毒管理，文件的完整性，主机入侵防护和网络访问控制</p></div><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>安全事故和事件管理</h3><p>SIEM包括全天候的安全监控、日志收集和管理、事件关联和安全事件响应</p></div><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>网络安全</h3><p>包括网络入侵防护、防火墙管理和电子邮件安全</p></div><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>漏洞管理</h3><p>EVM服务包括IT基础设施漏洞扫描、网络应用程序扫描，修复报告及其策略合规</p></div><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>身份和访问管理（IAM）</h3><p>IAM服务包括用户配置、访问控制、授权评审、治理合规和报告</p></div><div class="single" ><img src="../static/img/yiding.png" class="img"/><h3>数据安全</h3><p>数据安全服务包括网页内容过滤、数据泄露防护和加密</p></div></div>',
						pic_path:'../../static/img/anquan.jpg'
					},
					{
						name:'人力资源服务',
						content:'博亚君杰的IT人力资源配置服务充分免除您在人员招聘和培训上的顾虑和时间，使您可以专注于核心业务的运营，人力资源配置服务可以帮您打开进入行业技术知识的窗口，减少您对内部培训和专业技能发展的投入和资金，从而达到节约成本的目的，我们高质量的人力资源配置会全面协助和加速您的产品上市。<img src="../static/img/renli.jpg" style="width:calc(100% + 60px);display:block;margin-top:30px;margin-left:-30px"/>',
						pic_path:'../../static/img/pic5.jpg'
					}
				],
				hangye:[
					{
						name:'高科技',
						content:'数字化革命不仅席卷了传统的行业，也为高科技行业带来了新的机遇与挑战。如何提高产品的用户体验，缩短产品的上市时间，优化成本结构以及强化客户管理等都成为高科技企业关注的重点。而博亚君杰正在利用自身特有的资源与优势，结合服务知名高科技企业的最佳实践，帮助企业加速创新、助力增长、升级体验并优化企业运营。',
						pic_path:'../../static/img/gaokeji.png'
					},
					{
						name:'银行',
						content:'迈入数字银行时代，银行该如何实现持续稳定发展？博亚君杰洞悉银行市场和客户需求的变化，以工匠精神，锐意创新，帮助银行重构现代数字化的业务模式，革新业务流程，助力银行在新经济时代下实现业务转型。',
						pic_path:'../../static/img/yinhang.png'
					},
					{
						name:'保险',
						content:'保险公司如何在数字化时代中保持利润增长？博亚君杰通过为保险企业打造全流程一体化的解决方案，帮助您不断突破能力瓶颈，提升客户体验，升级服务模式，倍增服务效率，提升企业竞争力。',
						pic_path:'../../static/img/baoxian.png'
					},{
						name:'证券',
						content:'随着证券企业的业务量增长、业务模式创新与行业转型的不断推进，风险控制与数据管理将是您企业成功的关键。博亚君杰以当今先进技术驱动行业创新，助力证券企业赢在数字经济时代。',
						pic_path:'../../static/img/zhengquan.png'
					},{
						name:'金融其他',
						content:'在金融企业全面数字化转型过程中，博亚君杰凭借深厚的行业专业知识积累，高质量的交付体系和一流的服务能力，正帮助全球金融组织更好地适应不断变化的数字金融市场，服务新时代的需求，推动整个金融行业的长足进步。',
						pic_path:'../../static/img/jinrong.png'
					},{
						name:'电信',
						content:'电信行业正面临新的业务模式和客户期望，博亚君杰通过对技术、解决方案和服务的平衡组合，帮助电信企业应对数字化挑战并时刻保持在技术的最前沿，以便企业更深入的挖掘业务价值，超越客户期望。',
						pic_path:'../../static/img/dianxin.png'
					},{
						name:'互联网',
						content:'互联网经济在中国GDP中占比持续攀升，面对日益庞大和复杂的业务需求，博亚君杰多年来不断探索互联网行业的需求及最前沿技术，专注于运用最新的数字化技术手段，为众多知名互联网企业提供综合技术服务与极致的合作体验，驱动互联网行业加速创新，推动中国互联网的发展与进步。',
						pic_path:'../../static/img/hulianwang.png'
					},{
						name:'汽车',
						content:'汽车行业市场机遇与挑战并存，客户需求的快速变化、日新月异的技术变革和汽车行业的节能减排绿色革命，促使汽车制造商努力创新，提供个性化和差异化的服务来满足市场新需求。博亚君杰凭借领先的研发能力、卓越的开发经验及深厚的行业累积，服务知名车企，助力汽车企业数字化转型，实现更完美的交互体验。',
						pic_path:'../../static/img/qiche.png'
					},{
						name:'医疗和健康',
						content:'“互联网+医疗”时代正在到来，医疗行业面临着增速放缓、产业数字化转型及整合等时代趋势的挑战和机遇。如何化繁为简，赋能医疗创新，实现智能医疗的新格局？博亚君杰通过搭建共享、协同、智慧的信息化平台，助力医疗健康机构、药企以及患者实现协作人性化、安全常态化的智慧医疗体系。',
						pic_path:'../../static/img/jiankang.png'
					},{
						name:'旅游交通',
						content:'全球旅游和交通个性化需求日益增长，旅游及交通业也更加大众化、产业化，在全球范围内持续扩张，并维持了较高的增长态势。博亚君杰基于云计算、大数据、移动通信等技术，助力旅游、交通行业实现数字化转型，从而为人们创造更智能的出行体验。',
						pic_path:'../../static/img/lvyou.png'
					},
					{
						name:'政府和教育',
						content:'博亚君杰致力于为智慧城市及相关行业解决方案，服务于政府园区、大中院校、教育机构和普通市民，建构以人为本、智能协同的智慧生态系统。',
						pic_path:'../../static/img/jiaoyu.png'
					},{
						name:'媒体娱乐',
						content:'移动互联网的发展要求媒体和娱乐行业必须紧跟技术的变革，越来越多的用户通过移动终端就能获得海量的信息。博亚君杰凭借丰富的实践经验和定制化的解决方案，帮助媒体和娱乐公司提高效率、优化技术和革新工艺，从而为用户带来更为卓越的体验。',
						pic_path:'../../static/img/yule.png'
					}
				],
				nowAbout:0,
				about:[
					{
						name:'公司介绍',
						content:'北京博亚君杰科技有限公司是一家专业的IT咨询、服务及行业解决方案提供商，公司凭借多年的行业积累、深厚的行业专长和成熟的行业实践、国际化的精英团队和完善的人才管理、完备的交付体系与服务网络、以及无处不在的创新精神与实践，助力客户尽享科技革新所带来的卓越运营，致力于为互联网、高科技、电信、政府企业、能源等多个行业提供数字化解决方案与服务，包括数字化咨询、数字化解决方案设计与实施、IT基础设施建设与运维、软件开发与测试服务和数字化运营服务、IT外包及业务流程外包等高品质服务，为各领域客户持续创造关键价值。<br><br>作为国内领先的信息技术与行业软件服务供应商，博亚君杰坚持以客户为中心，全力以赴为客户交付提供尽善尽美的解决方案，同时紧密把握行业发展脉搏，充分利用良好的行业实践，为客户提供创新、适用、完整的信息化解决方案以及端到端（End to End）的信息技术服务。<br><br>博亚君杰注重创新和可持续发展，不断探索前沿技术与商业应用的无限可能。<br><br>未来，博亚君杰秉承“融合创新，成就卓越，超越期待，尽善尽美”的服务理念，一如既往的为客户提供优质、专业、高效的服务，力争成为中国综合实力最强的信息技术服务提供商，并将持续履行我们的社会责任，为优秀的人才提供一个开放、平等、机会丰富的工作平台，帮助他们实现自身的价值。',
						pic_path:'../../../static/img/gongsi.jpg'
					},
					{
						name:'商业价值',
						content:'博亚君杰是亚洲领先的IT服务提供商，具备专业、高效、全方位的交付能力。 <br><br>拥有成熟先进的IT基础设施管理服务经验，有战略顾问和技术专家组成专业团队，7x24小时协助客户解决方案和资产管理过程中遇到的各种挑战。 <br><br>博亚君杰是企业值得信赖的战略型合作伙伴，让企业专注于核心业务，加速企业数字化建设，赢得更多核心竞争力。',
						pic_path:'../../../static/img/jiazhi.jpg'
					},
					{
						name:'愿景、使命和价值观',
						content:'我们的使命<br>博亚君杰矢志成为领先的创新型技术服务提供商<br><br>我们的愿景<br>企业最值得信赖优质合作伙伴<br><br>核心价值观<br>客户至上，服务先行<br>持续创新，团队意志<br>注重信誉，互利互惠 <br>行业领先，民族品牌',
						pic_path:'../../../static/img/shiming.jpg'
					}
				],
				zhaopin:[
					{
						name:'研发项目经理',
						content:'技能要求：项目管理，解决方案，需求分析。岗位职责： 1、负责基金、保险、证券、信托等行业系统等应用软件的驻场开发项目管理工作； 2、组织并确认所承担的产品、项目的需求分析、技术评审和多个过程工作产品的确认；3、负责整个项目小组的任务分解和分派，组织、协调工作；4、负责策划和组织产品（项目）的测试工作。负责最终产品发布的确认审核工作，保障好项目交付；5、制定项目开发工作的整体计划，规划及协调项目开发的人力资源，组建开发团队；6、做好开发过程中的风险控制、变更管理；7、跟踪产品、项目开发的进程，按计划推进开发进程； 8、做好开发过程中问题的管理，关注好客户反馈，保障好开发进度和质量； 9、负责项目组与外部的沟通，保持好与客户之间信息的畅通。 '
					},
					{
						name:'产品经理',
						content:'岗位职责：根据公司战略规划，研究分析市场需求，规范管理产品生产，指导产品经理工作，使产品更加符合用户的需求。产品管理工作：       按照公司战略指导方向，制定产品竞争策略及方案，贯彻及实施；     制订产品需求文档，以供设计、开发、测试人员明确产品需求；     跟进UI设计，确保产品效果图符合产品需求文档的要求；     跟进开发人员的开发，确保产品功能特性和交互符合产品需求；     收集分析用户意见反馈，以便于挖掘用户的真正需求。     市场分析工作：收集市场需求，指导及规划产品迭代改进或设计；      收集市场信息，用户信息，竞争对手信息，研究，分析，以供决策使用；     配合市场制定产品价格及市场策略；    评估跟踪产品数据，分析上线数据，持续产品改进；     配合市场活动，进行产品设计。     产品规划工作：按照公司战略指导方向，配合市场，制定产品策略，编写规划方案；      编写产品规划方案；     组织产品规划方案讨论；     组织产品规划方案评审；     产品迭代版本及路线图规划。'
					},
					{
						name:'架构设计师',
						content:'岗位职责：1、把握总体设计和参与重要技术决策，指导初中级开发人员在整体架构下开展详细设计和开发工作； 2、解决项目中的关键问题和技术难题，核心代码与组件编写，重用库代码架构与开发； 3、根据产品需求，负责需求分析，业务流程优化，方案设计、单元测试和上线使用；4、作为核心团队的技术骨干或带头人，负责和参与系统架构以及功能的逻辑设计、实现、验证、集成和文档工作；  5、负责技术部技术人员的技术辅导，提高团队初、中级技术人员的技术水平。'
					},{
						name:'UI设计经理',
						content:'岗位职责：1、负责UI设计团队日常工作、设计产出的质量审核；2、带领UI设计团队与公司内部其它部门合作，参与产品的规划，提供专业意见，与产品线共同策划业务方向，进行新产品设计、页面制作、产品原型评测等工作；3、 对相关产品模块UI界面质量负责；4、完善产品UI设计流程, UI设计规范, UI设计风格；5、基于对用户需求的研究，规划用户体验策略，组织用户研究，可用性评估与测试等相关工作的开展。'
					},{
						name:'UI设计师',
						content:'岗位职责：1、收集和分析用户对于GUI的需求，根据产品需求，对产品的整体美术风格、交互设计、界面结构、操作流程等做出设计；2、负责项目中各种交互界面、图标、LOGO、按钮等相关元素的设计与制作；3、能积极与开发沟通，推进界面及交互设计的最终实现；4、负责软件界面的美术设计、创意工作和制作工作；5、根据各种相关软件的用户群，提出构思新颖、有高度吸引力的创意设计；6、对页面进行优化，使用户操作更趋于人性化。'
					},{
						name:'Android高级开发工程师',
						content:'岗位职责：1、负责安卓移动客户端应用产品的开发；2、独立完成编码和单元测试工作，确保开发质量；3、与团队其他成员协作/沟通，解决技术问题；4、参与产品需求的沟通、讨论和评审；'
					},{
						name:'IOS高级开发工程师',
						content:'职位要求：1、两年及以上客户端开发工作经验；2、熟练掌握java语言，熟悉面向对象的程序设计方法；3、熟悉android手机平台开发，有两年以上的android应用程序开发经验；4、具有独立分析问题，解决问题的能力，能独立完成开发工作；5、思路清晰，思维敏捷，快速的学习能力，能够承受工作的压力；6、善于沟通，乐于分享；'
					},{
						name:'.NET工程师',
						content:'职位要求：1、两年及以上客户端开发工作经验；2、熟练掌握java语言，熟悉面向对象的程序设计方法；3、熟悉android手机平台开发，有两年以上的android应用程序开发经验；4、具有独立分析问题，解决问题的能力，能独立完成开发工作；5、思路清晰，思维敏捷，快速的学习能力，能够承受工作的压力；6、善于沟通，乐于分享；'
					},{
						name:'C/C++工程师',
						content:'岗位职责：1、负责大型金融平台系统的开发和维护工作；2、根据需求独立完成相关设计和文档撰写；3、参与大型金融产品的需求沟通、功能设计及测试工作；'
					},
					{
						name:'JAVA开发工程师',
						content:'岗位职责：1、负责产品部核心软件系统的后台研发工作； 2、负责相关业务模块的设计、编码和文档等工作。'
					},
					{
						name:'软件测试工程师',
						content:'职位描述：1、完整参与系统的需求分析、测试案例、测试执行、问题提交等整个项目测试流程；2、对测试实施过程中发现的系统问题进行跟踪分析和报告，推动测试中发现问题及时合理解决；3、善于学习及较好的细心和耐心从而推动整个项目的测试效率及质量；4、善于从用户角度评审需求及最终设计，提高产品的易用性；'
					},{
						name:'实施工程师',
						content:'岗位职责：负责基金、保险、证券、信托等行业投资系统、估值系统、登记过户系统等应用软件的驻场运维服务工作。'
					}

				],
			}
		},
		components: {
			Swiper,
			Slide
		},

		methods: {
			prev:function(){
				 this.$refs.swiper.prevSlide();
			},
			next:function(){
				 this.$refs.swiper.nextSlide();
			},
			changeService:function(e){
				this.nowService = e;
			},
			changeAbout:function(e){
				this.nowAbout = e;
			}
		}
	}
</script>

<style lang="less">
	@import "../../assets/css/index.less";
</style>
