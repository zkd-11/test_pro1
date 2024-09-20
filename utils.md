## Classes

<dl>
<dt><a href="#Timer">Timer</a></dt>
<dd><p>记时小工具</p></dd>
</dl>

## Members

<dl>
<dt><a href="#anchorCurrent">anchorCurrent</a></dt>
<dd><p>当前的临时锚点数据</p>
<ul>
<li>只有在有流程栈叠加时才会存在, 存储最上层锚点数据, 否则为 null</li>
</ul></dd>
<dt><a href="#_default">_default</a></dt>
<dd><p>传送锚点: 传送到预定义好的目标流程</p>
<ol>
<li>在 anchors.ts 里预先定义锚点类型, 含 锚点名称, query参数, payload参数 3部分</li>
<li>流程落地页固定为 <code>pages/share/index</code>, 固定携带入参 scene=[ANCHOR_NAME]&amp;anchored=1</li>
<li>share入口页根据 scene 参数确定初始化场景并跳转, 根据 anchored=1 参数确定已经叠加了流程栈, 支持回到前一个流程</li>
<li>如果 share 入口页只接收到了 scene 值, 而没有 anchored=1, 则作为常规业务链接处理, 无叠加流程栈</li>
</ol></dd>
<dt><a href="#EScene">EScene</a></dt>
<dd><p><strong>外部入口</strong>暂定场景值区间</p>
<ul>
<li>场景值必须可枚举, <strong>不建议开放区间给外部自定义, 应该另起字段</strong></li>
<li>0~999: <strong>暂不使用</strong></li>
<li>1000~1999: 早期场景值, <strong>不再增加</strong>, 与微信小程序场景值有重叠</li>
<li>10000~10999: 前端常规场景, 其他端不应该隐式覆盖这个区间</li>
<li>FIXME: 确定海报场景的区间, 后续场景避开这个区间</li>
<li>TODO: 增加脚本检查场景值是否合规且不重复</li>
</ul></dd>
<dt><a href="#formatSpecItemText">formatSpecItemText</a></dt>
<dd><p>获取商品标签类型</p></dd>
<dt><a href="#getWeek">getWeek</a></dt>
<dd><p>获取截止日期</p></dd>
<dt><a href="#isSameMonth">isSameMonth</a></dt>
<dd><p>判断两天是否是同一天</p></dd>
<dt><a href="#isSameDate">isSameDate</a></dt>
<dd><p>补0</p></dd>
<dt><a href="#repairTime">repairTime</a> ⇒</dt>
<dd><p>昨天、今天、明天</p></dd>
<dt><a href="#judgeTime">judgeTime</a></dt>
<dd></dd>
<dt><a href="#getTime">getTime</a> ⇒</dt>
<dd><p>日期时间显示格式</p></dd>
<dt><a href="#formatDate">formatDate</a></dt>
<dd><p>时间戳转换为年月日时分秒</p></dd>
<dt><a href="#getTimeRange">getTimeRange</a> ⇒</dt>
<dd><p>计算两个时间戳(毫秒级)之间的时间差</p></dd>
<dt><a href="#getTimeDiff">getTimeDiff</a> ⇒ <code>Object</code></dt>
<dd><p>计算视频时间</p></dd>
<dt><a href="#vibrateShort">vibrateShort</a></dt>
<dd><p>拨打电话号码</p></dd>
<dt><a href="#makePhoneCall">makePhoneCall</a></dt>
<dd><p>打开地图定位</p></dd>
<dt><a href="#openLocationMap">openLocationMap</a></dt>
<dd><p>toast 提示</p></dd>
<dt><a href="#showToast">showToast</a></dt>
<dd><p>字符串省略号格式化（ps：临时暴力版）</p></dd>
<dt><a href="#hexToRgba">hexToRgba</a></dt>
<dd><p>判断是否是JSON格式</p></dd>
<dt><a href="#telEncryption">telEncryption</a></dt>
<dd><p>价格分开为整数、小数</p></dd>
<dt><a href="#useInteger">useInteger</a></dt>
<dd><p>判断是否全为0</p></dd>
<dt><a href="#binarySearch">binarySearch</a></dt>
<dd><p>保留分隔符拆分字符串</p></dd>
<dt><a href="#splitWithDelimiter">splitWithDelimiter</a> ⇒</dt>
<dd><p>颜色值转换</p></dd>
<dt><a href="#fetchDataList">fetchDataList</a></dt>
<dd><p>节流</p></dd>
<dt><a href="#checkPhone">checkPhone</a></dt>
<dd><p>校验身份证号码</p></dd>
<dt><a href="#checkIDCard">checkIDCard</a></dt>
<dd><p>校验邮箱</p></dd>
<dt><a href="#checkEmail">checkEmail</a></dt>
<dd><p>校验生日</p></dd>
<dt><a href="#handleVideoMenuGoods">handleVideoMenuGoods</a></dt>
<dd><p>扫码</p></dd>
<dt><a href="#handleScanCode">handleScanCode</a></dt>
<dd><p>跳转第三方链接</p></dd>
<dt><a href="#handleThirdPartyLinks">handleThirdPartyLinks</a></dt>
<dd><p>设置页面下一次 pageShow 的事件, 默认设置当前页面, 可以指定 delta 为其他历史页面</p></dd>
<dt><a href="#routeToCart">routeToCart</a></dt>
<dd><p>跳转到订单中心</p></dd>
<dt><a href="#subscribeMessage">subscribeMessage</a></dt>
<dd><p>获取订阅消息模版ID：一店一购小程序</p></dd>
<dt><a href="#subscribeMessage2DVisual">subscribeMessage2DVisual</a></dt>
<dd><p>获取订阅消息模版ID：商家小程序</p></dd>
</dl>

## Constants

<dl>
<dt><a href="#CNMobileReg">CNMobileReg</a></dt>
<dd><p>中国手机号匹配正则</p></dd>
<dt><a href="#areaCodesList">areaCodesList</a></dt>
<dd><p>区号列表</p></dd>
<dt><a href="#anchorHistory">anchorHistory</a></dt>
<dd><p>流程栈: 目前单生命周期内有效, reLaunch时会保留, 小程序销毁后重置</p>
<ul>
<li>保存的是历史流程栈, 当前流程保存在 anchorCurrent</li>
<li>比如常规进入时: anchorHistory=[], anchorCurrent=0
<ul>
<li>scan或share页如果当前无锚点则手动初始化一个 anchor0: anchorHistory=[anchor0], anchorCurrent=0</li>
<li>调用了一次 go(anchor1) 后: anchorHistory=[anchor0, anchor1], anchorCurrent=1</li>
<li>再调用一次 go(anchor2) 后: anchorHistory=[anchor0, anchor1, anchor2], anchorCurrent=2</li>
<li>再调用一次 back() 后: anchorHistory=[anchor0, anchor1], 而 anchorCurrent=1</li>
<li>再调用一次 back() 后, anchorHistory=[anchor0], 而 anchorCurrent=0</li>
<li>此后不支持再调 back()</li>
</ul>
</li>
</ul></dd>
<dt><a href="#formatMoney">formatMoney</a></dt>
<dd><p>格式化金额
通过对 formatNumber 的封装实现</p></dd>
<dt><a href="#DAY_NOW">DAY_NOW</a></dt>
<dd><p>一天时间戳</p></dd>
<dt><a href="#DEFAULT_SHARE_IMG">DEFAULT_SHARE_IMG</a></dt>
<dd><p>默认分享图片</p></dd>
<dt><a href="#DEFAULT_SHARE_IMG_2DVISUAL">DEFAULT_SHARE_IMG_2DVISUAL</a></dt>
<dd><p>默认分享图片</p></dd>
<dt><a href="#componentNameMap">componentNameMap</a></dt>
<dd><p>组件名称映射</p></dd>
<dt><a href="#cachedAuthData">cachedAuthData</a></dt>
<dd><p>生命周期内缓存的授权信息</p>
<ul>
<li>仅供不方便访问 store 的底层能力使用</li>
<li>常规业务用户信息应该从 store.User 里获取</li>
</ul></dd>
<dt><a href="#LOG_API_MAP">LOG_API_MAP</a></dt>
<dd><p>需要上报请求耗时的API</p></dd>
<dt><a href="#mpPerformanceEvents">mpPerformanceEvents</a></dt>
<dd><p>小程序性能监控事件</p>
<ul>
<li>仅 开发版/体验版 开启</li>
</ul></dd>
<dt><a href="#service">service</a></dt>
<dd><p>WebSocket</p></dd>
<dt><a href="#SceneType2DVisual">SceneType2DVisual</a></dt>
<dd><p>商家小程序消息订阅对应场景</p></dd>
<dt><a href="#userOperateMap">userOperateMap</a></dt>
<dd><p>用户操作</p></dd>
</dl>

## Functions

<dl>
<dt><a href="#getAreaItem">getAreaItem(areaCode)</a> ⇒</dt>
<dd><p>获取手机区号信息</p></dd>
<dt><a href="#initAsyncLib">initAsyncLib()</a></dt>
<dd><p>全局注册异步包的加载方法</p>
<ul>
<li>然后可以使用 globalLib.getV2() 方法异步加载模块</li>
<li>目前在 app 的 constructor 里全局注册, <strong>确保在这之后再访问异步模块</strong></li>
<li>TODO: 构建时根据区块包的 manifest.json 动态替换这里的引用路径, 减少维护成本</li>
</ul></dd>
<dt><a href="#loadH5Lib">loadH5Lib(src, target)</a></dt>
<dd><p>异步加载 h5 包</p></dd>
<dt><a href="#useDebugConfig">useDebugConfig()</a></dt>
<dd><p>跨组件共享 debugConfig, 并同步至 storage</p></dd>
<dt><a href="#initAnchor">initAnchor()</a></dt>
<dd><p>初始化当前锚点</p>
<ul>
<li>默认会清空锚点历史记录, 比如扫码/分享进入场景 一定作为首个锚点</li>
<li>从连锁门店列表等场景进入的, 可以只初始化当前锚点为目标 而不清空锚点历史记录</li>
</ul></dd>
<dt><a href="#back">back()</a></dt>
<dd><p>至少要留一项历史anchor</p></dd>
<dt><a href="#distanceFormat">distanceFormat(distance)</a> ⇒</dt>
<dd><p>格式化距离</p></dd>
<dt><a href="#formatWatcherCount">formatWatcherCount(watcherCount)</a> ⇒</dt>
<dd><p>格式化观看人数</p></dd>
<dt><a href="#getBounds">getBounds(menuModule, payload, isFirst)</a></dt>
<dd><p>计算不同尺寸的菜的具体尺寸</p></dd>
<dt><a href="#formatReserveTime">formatReserveTime(formPage, reserveType, setTimeInterval, chargingRuleType)</a></dt>
<dd><p>格式化预定时间</p></dd>
<dt><a href="#cssObjectToStyle">cssObjectToStyle(style, options)</a> ⇒</dt>
<dd><p>原生语法使用，将react styleObject转换为style-string</p></dd>
<dt><a href="#updateTopKuaishouItemShow">updateTopKuaishouItemShow(topKuaishouItems, showTopItemData)</a></dt>
<dd><p>更新展示的数据</p></dd>
<dt><a href="#formatMemo">formatMemo(data)</a></dt>
<dd><p>格式化备注</p></dd>
<dt><a href="#formatNumber">formatNumber(values)</a></dt>
<dd><p>格式化数字</p></dd>
<dt><a href="#formatSpecItemText">formatSpecItemText(item)</a></dt>
<dd><p>格式化规格信息</p></dd>
<dt><a href="#getWeek">getWeek(value)</a></dt>
<dd><p>获取星期</p></dd>
<dt><a href="#getCurrentTime">getCurrentTime(now)</a></dt>
<dd><p>获取当前日期 年 月 日 星期 小时 分钟 秒</p></dd>
<dt><a href="#getTimestampRange">getTimestampRange(startTimestamp, endTimestamp)</a> ⇒</dt>
<dd><p>获取 开始日期-结束日期 之前每天时间戳</p></dd>
<dt><a href="#isSameMonth">isSameMonth(dateA, dateB)</a></dt>
<dd><p>判断是否是同一个月</p></dd>
<dt><a href="#useCountDown">useCountDown(timer)</a></dt>
<dd><p>倒计时 hook</p></dd>
<dt><a href="#usePageViewTime">usePageViewTime(interval)</a> ⇒</dt>
<dd><p>页面浏览时间统计</p></dd>
<dt><a href="#getTimeRange 获取时间范围">getTimeRange 获取时间范围(code, timeType)</a> ⇒ <code>object</code></dt>
<dd><p>方法说明</p></dd>
<dt><a href="#formatUserInfo">formatUserInfo(data)</a> ⇒</dt>
<dd><p>我的信息数据处理</p></dd>
<dt><del><a href="#divide100">divide100()</a></del></dt>
<dd><p>除以 100 并保留两位小数</p></dd>
<dt><a href="#divide100V2">divide100V2(src)</a></dt>
<dd><p>除以 100 并保留两位小数</p></dd>
<dt><a href="#removeTrailingZeros">removeTrailingZeros(src)</a></dt>
<dd><p>去除数字后面的0</p></dd>
<dt><a href="#safeDecodeURIComponent">safeDecodeURIComponent(str)</a></dt>
<dd><p>code comes form angular
解码 URI 编码</p></dd>
<dt><a href="#arrRemoveEmpty">arrRemoveEmpty(arr)</a></dt>
<dd><p>数组去空item方法</p></dd>
<dt><a href="#modifyVideoPageMutedCache">modifyVideoPageMutedCache()</a></dt>
<dd><p>修改视频页面是否静音的缓存</p></dd>
<dt><a href="#setTitle">setTitle(name)</a></dt>
<dd><p>设置微信 webview 页面标题</p></dd>
<dt><a href="#getVideoPageMutedCache">getVideoPageMutedCache(entityId)</a></dt>
<dd><p>获取视频页面是否静音的缓存
h5环境一定默认静音 不支持跟随店铺保存配置</p></dd>
<dt><a href="#cutImage">cutImage(src, menuModule, isShowDefaultSrc, otherParams)</a></dt>
<dd><p>图片裁剪</p></dd>
<dt><a href="#asyncDelay">asyncDelay(timeout)</a></dt>
<dd><p>异步延时调用</p></dd>
<dt><a href="#vibrateShort">vibrateShort(type)</a></dt>
<dd><p>设备短震动</p>
<ul>
<li>部分设备不支持 非关键反馈 不处理错误</li>
<li>需要手机系统开启触感反馈 否则也会无效</li>
<li>不支持 h5</li>
</ul></dd>
<dt><a href="#parseQuery">parseQuery()</a></dt>
<dd><p>解析 from [url query] to [object]</p>
<ul>
<li>此方法仅供入口流程解析一次url参数</li>
<li>此方法不应该被到处调用 而应该从store获取状态</li>
<li>外部都应该先统一跳转到应用的一个落地页 再重定向到具体业务路径下, 这样只需要在落地页解析一次url参数</li>
</ul></dd>
<dt><a href="#isPageShow">isPageShow(page)</a></dt>
<dd><p>判断页面是否显示</p></dd>
<dt><a href="#generateId">generateId()</a></dt>
<dd><p>生成唯一ID</p></dd>
<dt><a href="#getMultiMenuId">getMultiMenuId()</a></dt>
<dd><p>获取当前multiMenuId</p>
<ul>
<li>优先从 store.Shop 获取，其次从 store.Menu 获取</li>
</ul></dd>
<dt><a href="#customerPopup">customerPopup(func)</a></dt>
<dd><p>客服统一拦截入口</p></dd>
<dt><del><a href="#compareVersion">compareVersion()</a></del></dt>
<dd><p>用来比较 currentVersion 当前环境小程序调试基础库 和 appointVersion 指定小程序调试基础库</p>
<ul>
<li>1 代表 currentVersion 大于 appointVersion</li>
<li>0 代表 currentVersion 等于 appointVersion</li>
<li>-1 代表 currentVersion 小于 appointVersion</li>
</ul></dd>
<dt><a href="#useDidUpdateEffect">useDidUpdateEffect(fn, inputs)</a></dt>
<dd><p>自定义hooks useEffect 初次渲染不执行</p></dd>
<dt><a href="#requestPaymentAlipay">requestPaymentAlipay(prePayId, payUrl)</a></dt>
<dd><p>支付宝支付</p></dd>
<dt><a href="#generateError">generateError(msg, code)</a></dt>
<dd><p>生成包含 code 的错误</p></dd>
<dt><a href="#hexToRgba">hexToRgba(hexColor, alpha, options)</a> ⇒</dt>
<dd><p>客户端背景色16进制(前2位为透明度)转换为rgba</p></dd>
<dt><a href="#useDebounceFn">useDebounceFn(func, wait, immediate)</a></dt>
<dd><p>防抖</p></dd>
<dt><del><a href="#formatPageParams">formatPageParams(params)</a></del></dt>
<dd><p>格式化页面参数</p></dd>
<dt><a href="#accMultiply">accMultiply(num1, num2)</a></dt>
<dd><p>精确乘法</p></dd>
<dt><a href="#fen2yuan">fen2yuan(num)</a></dt>
<dd><p>分转元</p></dd>
<dt><a href="#getHourMS">getHourMS()</a> ⇒</dt>
<dd><p>获取当天的开始时间</p></dd>
<dt><a href="#telEncryption">telEncryption(phone)</a> ⇒</dt>
<dd><p>格式化手机号 保留后四位和前三位</p></dd>
<dt><a href="#isFloat">isFloat(value)</a></dt>
<dd><p>判断是否是浮点数</p></dd>
<dt><del><a href="#getUnit">getUnit(unit)</a> ⇒</del></dt>
<dd><p>统一获取商家价格单位</p></dd>
<dt><a href="#activityShareInfo">activityShareInfo()</a> ⇒</dt>
<dd><p>邀请有礼活动 入会任务 检查支付接口需要添加 itemId + inviteCustomerId + activityEntityId</p></dd>
<dt><a href="#findComponentId">findComponentId(list, name, preFix)</a> ⇒</dt>
<dd><p>兼容老版本活动｜商品快速定位组件</p></dd>
<dt><a href="#isEqual">isEqual(target1, target2)</a></dt>
<dd><p>判断两个变量是否相等</p></dd>
<dt><a href="#init">init()</a></dt>
<dd><ul>
<li>注入jssdk cdn</li>
<li>请求jssdk配置</li>
<li>执行初始化</li>
<li>在ready回调中resolve</li>
<li>如果期间调用了api 自动等待完成然后执行</li>
</ul></dd>
<dt><a href="#parseEnv">parseEnv()</a></dt>
<dd><p>获取jssdk环境</p></dd>
<dt><a href="#initScript">initScript()</a></dt>
<dd><p>注入jssdk cdn</p></dd>
<dt><a href="#initTicket">initTicket()</a></dt>
<dd><p>请求jssdk ticket (仅微信环境需要)</p></dd>
<dt><a href="#initConfig">initConfig()</a></dt>
<dd><p>初始化 jssdk</p></dd>
<dt><a href="#call">call()</a></dt>
<dd><p>调用jssdk</p></dd>
<dt><a href="#requestPaymentAlipay">requestPaymentAlipay(params)</a></dt>
<dd><p>支付宝支付</p></dd>
<dt><a href="#scanCodeAlipay">scanCodeAlipay()</a></dt>
<dd><p>扫码支付宝</p></dd>
<dt><a href="#getCurrentLocationAlipay">getCurrentLocationAlipay()</a></dt>
<dd><p>支付宝获取当前位置</p></dd>
<dt><a href="#callAppMethod">callAppMethod()</a></dt>
<dd><p>app调用方法</p></dd>
<dt><a href="#getToken">getToken()</a></dt>
<dd><p>优先从内存缓存取token</p>
<ul>
<li>取不到则尝试从 storage 获取</li>
</ul></dd>
<dt><a href="#keepLogin">keepLogin(forceLogin, skipCache)</a></dt>
<dd><p>保持登录</p>
<ul>
<li>检查顺序: 本地token存储 -&gt; Taro.checkSession -&gt; 接口is_valid_token</li>
</ul></dd>
<dt><a href="#notifyDebugEvent">notifyDebugEvent()</a></dt>
<dd><p><strong>事件调试</strong> - 标记事件各个步骤合并上报</p>
<ul>
<li>step=start 作为固定开始标记, 将触发重新计时</li>
<li>step=end 作为固定完成标记, 将触发埋点上报, 后续必须再次调用 start 事件来启用</li>
<li>step=cancel 作为固定取消标记, 将直接清空当前事件数据</li>
<li>必须先上报 start 来开启步骤, 否则其他步骤都无效</li>
<li>上报 end 步骤会上报埋点, 并清空当前事件数据, 不再接收后续步骤</li>
</ul></dd>
<dt><a href="#getMemberCardCss">getMemberCardCss(themeMode, cardLevel, name)</a></dt>
<dd><p>获取会员卡样式</p></dd>
<dt><a href="#getLevelEndTimeDesc">getLevelEndTimeDesc(cardItem, level, periodType, levelEndTime)</a></dt>
<dd><p>卡有效期文案展示</p></dd>
<dt><a href="#navigateToMenu">navigateToMenu()</a></dt>
<dd><p>跳转到菜单</p></dd>
<dt><a href="#savePhoneContact">savePhoneContact(payload)</a></dt>
<dd><p>保存到通讯录</p></dd>
<dt><a href="#fetchDataList">fetchDataList(index, promises)</a></dt>
<dd><p>递归请求</p></dd>
<dt><a href="#checkPhone">checkPhone()</a></dt>
<dd><p>校验手机号码</p></dd>
<dt><a href="#combineUrl">combineUrl(url, params, isGateway)</a></dt>
<dd><p>合并请求参数 - 本地地址</p></dd>
<dt><a href="#combineOriginUrl">combineOriginUrl(url, params, skipEncode)</a></dt>
<dd><p>合并请求参数 - 任意地址</p></dd>
<dt><a href="#getToken">getToken()</a></dt>
<dd><p>优先从内存缓存取token</p>
<ul>
<li>取不到则尝试从 storage 获取</li>
</ul></dd>
<dt><a href="#getEntryPagePath">getEntryPagePath()</a></dt>
<dd><p>获取入口页面</p></dd>
<dt><a href="#routeTo">routeTo(path, options)</a></dt>
<dd><p>跳转页面</p></dd>
<dt><a href="#hanldePageRoute">hanldePageRoute()</a></dt>
<dd><p>防止小程序页面栈出现多个视频菜单
页面栈中包含多个视频菜单会导致小程序闪退</p></dd>
<dt><a href="#getAppointPaths">getAppointPaths(sourceType)</a></dt>
<dd><p>获取指定路径的页面</p></dd>
<dt><a href="#isExistPagePath">isExistPagePath(path)</a></dt>
<dd><p>判断页面是否存在</p></dd>
<dt><a href="#routeToPagePath">routeToPagePath()</a></dt>
<dd><p>动态判断 navigateBack/navigateTo/redirectTo 到目标路由</p>
<ul>
<li>如果页面栈中有目标路由 则 navigateBack</li>
<li>如果没有目标路由 默认 navigateTo 否则 redirectTo</li>
<li>如果是后退 <strong>不支持</strong>拼接 options.params 参数</li>
</ul></dd>
<dt><a href="#getMemberSystemId">getMemberSystemId(type, entityId)</a></dt>
<dd><p>获取会员系统 ID</p></dd>
<dt><a href="#getOrderCount">getOrderCount()</a></dt>
<dd><p>获取订单数量</p></dd>
<dt><a href="#addToActivityDetailSource">addToActivityDetailSource(code, source)</a></dt>
<dd><p>添加活动详情来源</p></dd>
<dt><a href="#getCurrentShopEnvEntityId">getCurrentShopEnvEntityId()</a></dt>
<dd><p>获取当前店铺环境实体ID</p></dd>
<dt><a href="#hotspotJump">hotspotJump(type, options)</a></dt>
<dd><p>热点跳转</p></dd>
<dt><a href="#handleVideoMenuGoods">handleVideoMenuGoods(entityId, goodId, multiMenuId, isJumpDetail)</a></dt>
<dd><p>跳转到商品</p></dd>
<dt><a href="#usePageShow">usePageShow()</a></dt>
<dd><p>支持 showAction 的 Taro.useDidShow</p></dd>
<dt><a href="#navigateBack">navigateBack()</a></dt>
<dd><p>快捷方法: 设置上一页的 showAction 并后退</p>
<ul>
<li>可以在上一个页面的 usePageShow 里获取到页面后退事件</li>
</ul></dd>
<dt><del><a href="#handleNavigatedBack">handleNavigatedBack()</a></del></dt>
<dd><p>在页面 useDidShow 里调用, 获取返回事件</p></dd>
<dt><a href="#getTargetMenuPath">getTargetMenuPath()</a></dt>
<dd><p>当前不在三本菜单中，寻找页面栈中存在的菜单路径(就远原则)，都不存在默认跳视频菜单</p></dd>
<dt><a href="#getCurrentPageName">getCurrentPageName()</a></dt>
<dd><p>获取当前页面栈</p></dd>
<dt><a href="#routeToMenu">routeToMenu()</a></dt>
<dd><p>跳转到另一本菜单,默认会自动寻找</p></dd>
<dt><a href="#routeToOrdered">routeToOrdered()</a></dt>
<dd><p>跳转到已下单的商品</p></dd>
<dt><a href="#routeToCart">routeToCart(action)</a></dt>
<dd><p>跳转到购物车</p></dd>
<dt><a href="#init">init()</a></dt>
<dd><p>全局路由监听</p></dd>
<dt><a href="#routerToWebview">routerToWebview(name, query, noSplit)</a></dt>
<dd><p>跳转 Webview 页面</p></dd>
<dt><a href="#saveImageToPhotosAlbum">saveImageToPhotosAlbum(options)</a></dt>
<dd><p>保存图片到相册</p></dd>
<dt><a href="#scanCode">scanCode()</a></dt>
<dd><p>唤起 扫一扫</p></dd>
<dt><a href="#setAnchorMenuId">setAnchorMenuId(id, kindId)</a></dt>
<dd><p>设置锚点</p></dd>
<dt><a href="#getAnchorMenuId">getAnchorMenuId()</a></dt>
<dd><p>获取锚点</p></dd>
<dt><a href="#clearAnchorMenuId">clearAnchorMenuId()</a></dt>
<dd><p>清除锚点</p></dd>
<dt><a href="#getCache">getCache(originKey, bucket)</a></dt>
<dd><p>获取缓存</p></dd>
<dt><a href="#setCache">setCache(originKey, data, options)</a></dt>
<dd><p>设置缓存</p></dd>
<dt><a href="#removeCache">removeCache(originKey, bucket)</a></dt>
<dd><p>删除缓存</p></dd>
<dt><a href="#flushCache">flushCache(bucket)</a></dt>
<dd><p>清理指定 bucket 下过期的缓存</p></dd>
<dt><a href="#flushAllCache">flushAllCache()</a></dt>
<dd><p>清理所有缓存中过期的缓存</p></dd>
<dt><a href="#removeBucket">removeBucket(bucket)</a></dt>
<dd><p>移除指定 bucket</p></dd>
<dt><a href="#clearGreetingCardData">clearGreetingCardData()</a></dt>
<dd><p>清理礼品卡数据</p></dd>
<dt><a href="#cacheTempFile">cacheTempFile()</a></dt>
<dd><p>缓存临时文件(路径)到 localStorage</p>
<ul>
<li>小程序临时文件: 空间可以有 2GB, 运行时最多到 4GB, 由微信控制何时清理</li>
</ul></dd>
<dt><a href="#tryTempFile">tryTempFile()</a></dt>
<dd><p>尝试获取缓存的临时文件(路径), 满足以下条件时才能成功获取</p>
<ol>
<li>临时文件路径缓存在 temp_file bucket 里</li>
<li>临时文件实际存在(未被微信清理)</li>
</ol></dd>
<dt><a href="#subscribeMessage">subscribeMessage(entityId, sceneType)</a></dt>
<dd><p>订阅消息：一店一购</p></dd>
<dt><a href="#subscribeMessage2DVisual">subscribeMessage2DVisual(entityId, sceneType)</a></dt>
<dd><p>订阅消息：商家小程序</p></dd>
<dt><a href="#getCacheUserOperate">getCacheUserOperate(key)</a></dt>
<dd><p>获取缓存的用户操作</p></dd>
<dt><a href="#setCacheUserOperate">setCacheUserOperate(key, data, options)</a></dt>
<dd><p>设置用户操作缓存</p></dd>
</dl>

<a name="Timer"></a>

## Timer
<p>记时小工具</p>

**Kind**: global class  
<a name="new_Timer_new"></a>

### new Timer(autoStart)
<p>构造函数</p>


| Param | Default | Description |
| --- | --- | --- |
| autoStart | <code>true</code> | <p>是否自动开始计时，默认自动开始</p> |

<a name="anchorCurrent"></a>

## anchorCurrent
<p>当前的临时锚点数据</p>
<ul>
<li>只有在有流程栈叠加时才会存在, 存储最上层锚点数据, 否则为 null</li>
</ul>

**Kind**: global variable  
<a name="_default"></a>

## \_default
<p>传送锚点: 传送到预定义好的目标流程</p>
<ol>
<li>在 anchors.ts 里预先定义锚点类型, 含 锚点名称, query参数, payload参数 3部分</li>
<li>流程落地页固定为 <code>pages/share/index</code>, 固定携带入参 scene=[ANCHOR_NAME]&amp;anchored=1</li>
<li>share入口页根据 scene 参数确定初始化场景并跳转, 根据 anchored=1 参数确定已经叠加了流程栈, 支持回到前一个流程</li>
<li>如果 share 入口页只接收到了 scene 值, 而没有 anchored=1, 则作为常规业务链接处理, 无叠加流程栈</li>
</ol>

**Kind**: global variable  
<a name="EScene"></a>

## EScene
<p><strong>外部入口</strong>暂定场景值区间</p>
<ul>
<li>场景值必须可枚举, <strong>不建议开放区间给外部自定义, 应该另起字段</strong></li>
<li>0~999: <strong>暂不使用</strong></li>
<li>1000~1999: 早期场景值, <strong>不再增加</strong>, 与微信小程序场景值有重叠</li>
<li>10000~10999: 前端常规场景, 其他端不应该隐式覆盖这个区间</li>
<li>FIXME: 确定海报场景的区间, 后续场景避开这个区间</li>
<li>TODO: 增加脚本检查场景值是否合规且不重复</li>
</ul>

**Kind**: global variable  
<a name="formatSpecItemText"></a>

## formatSpecItemText
<p>获取商品标签类型</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| type | <p>商品类型</p> |
| subType | <p>卡券子类型</p> |
| isCombo | <p>是否是套餐</p> |

<a name="getWeek"></a>

## getWeek
<p>获取截止日期</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| time | <p>时间戳</p> |
| line | <p>截止时间</p> |

<a name="isSameMonth"></a>

## isSameMonth
<p>判断两天是否是同一天</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| dateA | <p>第一个日期</p> |
| dateB | <p>第二个日期</p> |

<a name="isSameDate"></a>

## isSameDate
<p>补0</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| v | <p>需要补0的数字</p> |

<a name="repairTime"></a>

## repairTime ⇒
<p>昨天、今天、明天</p>

**Kind**: global variable  
**Returns**: <p>-2 后天
-1 明天
0 今天
1 昨天
2 前天</p>  

| Param | Description |
| --- | --- |
| timestamp | <p>时间戳</p> |

<a name="judgeTime"></a>

## judgeTime
**Kind**: global variable  

| Param | Description |
| --- | --- |
| timestamp | <p>时间戳</p> |

<a name="getTime"></a>

## getTime ⇒
<p>日期时间显示格式</p>

**Kind**: global variable  
**Returns**: <p>2022-01-01 12:00:00 周六</p>  

| Param | Description |
| --- | --- |
| format | <p>Y-M-D h:m:s W</p> |
| timestamp | <p>时间戳</p> |

<a name="formatDate"></a>

## formatDate
<p>时间戳转换为年月日时分秒</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| val | <p>时间戳</p> |

<a name="getTimeRange"></a>

## getTimeRange ⇒
<p>计算两个时间戳(毫秒级)之间的时间差</p>

**Kind**: global variable  
**Returns**: <ul>
<li>hours - 小时</li>
<li>seconds - 秒</li>
<li>minutes - 分钟</li>
<li>days - 天</li>
</ul>  

| Param | Type |
| --- | --- |
| temp1 | <code>number</code> | 
| temp2 | <code>number</code> | 

<a name="getTimeDiff"></a>

## getTimeDiff ⇒ <code>Object</code>
<p>计算视频时间</p>

**Kind**: global variable  

| Param | Type |
| --- | --- |
| temp1 | <code>number</code> | 

<a name="vibrateShort"></a>

## vibrateShort
<p>拨打电话号码</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| phoneNumber | <p>电话号码</p> |

<a name="makePhoneCall"></a>

## makePhoneCall
<p>打开地图定位</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| options.latitude | <p>纬度</p> |
| options.longitude | <p>经度</p> |
| options.name | <p>位置名</p> |
| options.address | <p>地址</p> |
| options.scale | <p>缩放比例</p> |

<a name="openLocationMap"></a>

## openLocationMap
<p>toast 提示</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| msg | <p>提示内容</p> |
| isSuccess | <p>是否成功</p> |

<a name="showToast"></a>

## showToast
<p>字符串省略号格式化（ps：临时暴力版）</p>

**Kind**: global variable  
<a name="hexToRgba"></a>

## hexToRgba
<p>判断是否是JSON格式</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| str | <p>需要判断的内容</p> |

<a name="telEncryption"></a>

## telEncryption
<p>价格分开为整数、小数</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| price | <p>价格</p> |
| several | <p>保留到小数点后几位</p> |

<a name="useInteger"></a>

## useInteger
<p>判断是否全为0</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| str | <p>需要判断的字符串</p> |

<a name="binarySearch"></a>

## binarySearch
<p>保留分隔符拆分字符串</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| str | <p>需要拆分的字符串</p> |
| delimiter | <p>分隔符</p> |

<a name="splitWithDelimiter"></a>

## splitWithDelimiter ⇒
<p>颜色值转换</p>

**Kind**: global variable  
**Returns**: <p>00FF11 -&gt; #FF0011</p>  

| Param | Description |
| --- | --- |
| src | <p>颜色值不带#</p> |

<a name="fetchDataList"></a>

## fetchDataList
<p>节流</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| fn | <p>需要执行的函数</p> |
| interval | <p>间隔</p> |

<a name="checkPhone"></a>

## checkPhone
<p>校验身份证号码</p>

**Kind**: global variable  
<a name="checkIDCard"></a>

## checkIDCard
<p>校验邮箱</p>

**Kind**: global variable  
<a name="checkEmail"></a>

## checkEmail
<p>校验生日</p>

**Kind**: global variable  
<a name="handleVideoMenuGoods"></a>

## handleVideoMenuGoods
<p>扫码</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| code | <p>扫码内容</p> |

<a name="handleScanCode"></a>

## handleScanCode
<p>跳转第三方链接</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| params |  |
| params.thirdUrlType | <p>0: 跳转小程序 1: 跳转网页 2: 跳转外链</p> |
| params.thirdUrlAppId | <p>小程序appid</p> |
| params.thirdUrl | <p>网页链接</p> |

<a name="handleThirdPartyLinks"></a>

## handleThirdPartyLinks
<p>设置页面下一次 pageShow 的事件, 默认设置当前页面, 可以指定 delta 为其他历史页面</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| action | <p>动作名称, 需要保证唯一, 避免冲突</p> |
| delta | <p>默认为 0, 给当前页设置, 后退时传 1, 给上一页设置</p> |

<a name="routeToCart"></a>

## routeToCart
<p>跳转到订单中心</p>

**Kind**: global variable  
<a name="subscribeMessage"></a>

## subscribeMessage
<p>获取订阅消息模版ID：一店一购小程序</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| entityId | <p>商家ID</p> |
| sceneType | <p>场景</p> |

<a name="subscribeMessage2DVisual"></a>

## subscribeMessage2DVisual
<p>获取订阅消息模版ID：商家小程序</p>

**Kind**: global variable  

| Param | Description |
| --- | --- |
| entityId | <p>商家ID</p> |
| sceneType | <p>场景</p> |

<a name="CNMobileReg"></a>

## CNMobileReg
<p>中国手机号匹配正则</p>

**Kind**: global constant  
<a name="areaCodesList"></a>

## areaCodesList
<p>区号列表</p>

**Kind**: global constant  
<a name="anchorHistory"></a>

## anchorHistory
<p>流程栈: 目前单生命周期内有效, reLaunch时会保留, 小程序销毁后重置</p>
<ul>
<li>保存的是历史流程栈, 当前流程保存在 anchorCurrent</li>
<li>比如常规进入时: anchorHistory=[], anchorCurrent=0
<ul>
<li>scan或share页如果当前无锚点则手动初始化一个 anchor0: anchorHistory=[anchor0], anchorCurrent=0</li>
<li>调用了一次 go(anchor1) 后: anchorHistory=[anchor0, anchor1], anchorCurrent=1</li>
<li>再调用一次 go(anchor2) 后: anchorHistory=[anchor0, anchor1, anchor2], anchorCurrent=2</li>
<li>再调用一次 back() 后: anchorHistory=[anchor0, anchor1], 而 anchorCurrent=1</li>
<li>再调用一次 back() 后, anchorHistory=[anchor0], 而 anchorCurrent=0</li>
<li>此后不支持再调 back()</li>
</ul>
</li>
</ul>

**Kind**: global constant  
<a name="formatMoney"></a>

## formatMoney
<p>格式化金额
通过对 formatNumber 的封装实现</p>

**Kind**: global constant  

| Param | Description |
| --- | --- |
| number | <p>要格式化的数字</p> |

<a name="DAY_NOW"></a>

## DAY\_NOW
<p>一天时间戳</p>

**Kind**: global constant  
<a name="DEFAULT_SHARE_IMG"></a>

## DEFAULT\_SHARE\_IMG
<p>默认分享图片</p>

**Kind**: global constant  
<a name="DEFAULT_SHARE_IMG_2DVISUAL"></a>

## DEFAULT\_SHARE\_IMG\_2DVISUAL
<p>默认分享图片</p>

**Kind**: global constant  
<a name="componentNameMap"></a>

## componentNameMap
<p>组件名称映射</p>

**Kind**: global constant  
<a name="cachedAuthData"></a>

## cachedAuthData
<p>生命周期内缓存的授权信息</p>
<ul>
<li>仅供不方便访问 store 的底层能力使用</li>
<li>常规业务用户信息应该从 store.User 里获取</li>
</ul>

**Kind**: global constant  
<a name="LOG_API_MAP"></a>

## LOG\_API\_MAP
<p>需要上报请求耗时的API</p>

**Kind**: global constant  
<a name="mpPerformanceEvents"></a>

## mpPerformanceEvents
<p>小程序性能监控事件</p>
<ul>
<li>仅 开发版/体验版 开启</li>
</ul>

**Kind**: global constant  
<a name="service"></a>

## service
<p>WebSocket</p>

**Kind**: global constant  
<a name="SceneType2DVisual"></a>

## SceneType2DVisual
<p>商家小程序消息订阅对应场景</p>

**Kind**: global constant  

* [SceneType2DVisual](#SceneType2DVisual)
    * [.BALANCE_STATUS_REFUND](#SceneType2DVisual.BALANCE_STATUS_REFUND)
    * [.STATUS](#SceneType2DVisual.STATUS)
    * [.REFUND_BALANCE](#SceneType2DVisual.REFUND_BALANCE)
    * [.RESERVE](#SceneType2DVisual.RESERVE)
    * [.RESERVE_REFUND_BALANCE](#SceneType2DVisual.RESERVE_REFUND_BALANCE)
    * [.COUPON](#SceneType2DVisual.COUPON)
    * [.BALANCE_STATUS](#SceneType2DVisual.BALANCE_STATUS)
    * [.PICK_UP](#SceneType2DVisual.PICK_UP)
    * [.AUDIT](#SceneType2DVisual.AUDIT)
    * [.SIGN_ACTIVITY_SCENE](#SceneType2DVisual.SIGN_ACTIVITY_SCENE)

<a name="SceneType2DVisual.BALANCE_STATUS_REFUND"></a>

### SceneType2DVisual.BALANCE\_STATUS\_REFUND
<p>账户余额提醒、订单状态通知、退款状态通知</p>

**Kind**: static property of [<code>SceneType2DVisual</code>](#SceneType2DVisual)  
<a name="SceneType2DVisual.STATUS"></a>

### SceneType2DVisual.STATUS
<p>订单状态通知</p>

**Kind**: static property of [<code>SceneType2DVisual</code>](#SceneType2DVisual)  
<a name="SceneType2DVisual.REFUND_BALANCE"></a>

### SceneType2DVisual.REFUND\_BALANCE
<p>退款状态通知、账户余额提醒</p>

**Kind**: static property of [<code>SceneType2DVisual</code>](#SceneType2DVisual)  
<a name="SceneType2DVisual.RESERVE"></a>

### SceneType2DVisual.RESERVE
<p>预定状态通知</p>

**Kind**: static property of [<code>SceneType2DVisual</code>](#SceneType2DVisual)  
<a name="SceneType2DVisual.RESERVE_REFUND_BALANCE"></a>

### SceneType2DVisual.RESERVE\_REFUND\_BALANCE
<p>预定状态通知、退款状态通知、账户余额提醒</p>

**Kind**: static property of [<code>SceneType2DVisual</code>](#SceneType2DVisual)  
<a name="SceneType2DVisual.COUPON"></a>

### SceneType2DVisual.COUPON
<p>优惠券到账提醒、优惠券使用成功通知、优惠券过期提醒</p>

**Kind**: static property of [<code>SceneType2DVisual</code>](#SceneType2DVisual)  
<a name="SceneType2DVisual.BALANCE_STATUS"></a>

### SceneType2DVisual.BALANCE\_STATUS
<p>账户余额提醒、订单状态通知，</p>

**Kind**: static property of [<code>SceneType2DVisual</code>](#SceneType2DVisual)  
<a name="SceneType2DVisual.PICK_UP"></a>

### SceneType2DVisual.PICK\_UP
<p>自提场景，消息订阅通知</p>

**Kind**: static property of [<code>SceneType2DVisual</code>](#SceneType2DVisual)  
<a name="SceneType2DVisual.AUDIT"></a>

### SceneType2DVisual.AUDIT
<p>佣金账户开通状态</p>

**Kind**: static property of [<code>SceneType2DVisual</code>](#SceneType2DVisual)  
<a name="SceneType2DVisual.SIGN_ACTIVITY_SCENE"></a>

### SceneType2DVisual.SIGN\_ACTIVITY\_SCENE
<p>签到活动场景，消息订阅通知</p>

**Kind**: static property of [<code>SceneType2DVisual</code>](#SceneType2DVisual)  
<a name="userOperateMap"></a>

## userOperateMap
<p>用户操作</p>

**Kind**: global constant  
<a name="getAreaItem"></a>

## getAreaItem(areaCode) ⇒
<p>获取手机区号信息</p>

**Kind**: global function  
**Returns**: <p>undefined || areaItem</p>  

| Param | Type |
| --- | --- |
| areaCode | <code>SupportedAreaCode</code> | 

<a name="initAsyncLib"></a>

## initAsyncLib()
<p>全局注册异步包的加载方法</p>
<ul>
<li>然后可以使用 globalLib.getV2() 方法异步加载模块</li>
<li>目前在 app 的 constructor 里全局注册, <strong>确保在这之后再访问异步模块</strong></li>
<li>TODO: 构建时根据区块包的 manifest.json 动态替换这里的引用路径, 减少维护成本</li>
</ul>

**Kind**: global function  
<a name="loadH5Lib"></a>

## loadH5Lib(src, target)
<p>异步加载 h5 包</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| src | <p>加载路径</p> |
| target | <p>挂载到 window 上的全局变量名称</p> |

<a name="useDebugConfig"></a>

## useDebugConfig()
<p>跨组件共享 debugConfig, 并同步至 storage</p>

**Kind**: global function  
<a name="initAnchor"></a>

## initAnchor()
<p>初始化当前锚点</p>
<ul>
<li>默认会清空锚点历史记录, 比如扫码/分享进入场景 一定作为首个锚点</li>
<li>从连锁门店列表等场景进入的, 可以只初始化当前锚点为目标 而不清空锚点历史记录</li>
</ul>

**Kind**: global function  
<a name="back"></a>

## back()
<p>至少要留一项历史anchor</p>

**Kind**: global function  
<a name="distanceFormat"></a>

## distanceFormat(distance) ⇒
<p>格式化距离</p>

**Kind**: global function  
**Returns**: <p>&lt;100m
100-999m
1000-9999km</p>  

| Param | Default | Description |
| --- | --- | --- |
| distance | <code>0</code> | <p>距离</p> |

<a name="formatWatcherCount"></a>

## formatWatcherCount(watcherCount) ⇒
<p>格式化观看人数</p>

**Kind**: global function  
**Returns**: <p>&lt;10000 x</p>
<blockquote>
<p>=10000 x万</p>
</blockquote>  

| Param | Description |
| --- | --- |
| watcherCount | <p>观看人数</p> |

<a name="getBounds"></a>

## getBounds(menuModule, payload, isFirst)
<p>计算不同尺寸的菜的具体尺寸</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| menuModule | <p>菜的展示模式</p> |
| payload | <p>附加内容</p> |
| isFirst | <p>是否是第一个</p> |

<a name="formatReserveTime"></a>

## formatReserveTime(formPage, reserveType, setTimeInterval, chargingRuleType)
<p>格式化预定时间</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| formPage | <p>产品一个页面的日期要加上年，一个不要年</p> |
| reserveType | <p>7-普通预定，8-计时商品</p> |
| setTimeInterval | <p>0-时间段，1-月日</p> |
| chargingRuleType | <p>1-按天，2-按小时，3-按分钟，4-按场次</p> |

<a name="cssObjectToStyle"></a>

## cssObjectToStyle(style, options) ⇒
<p>原生语法使用，将react styleObject转换为style-string</p>

**Kind**: global function  
**Returns**: <p>style</p>  

| Param | Description |
| --- | --- |
| style | <p>CSSProperties</p> |
| options | <p>转换单位</p> |

<a name="updateTopKuaishouItemShow"></a>

## updateTopKuaishouItemShow(topKuaishouItems, showTopItemData)
<p>更新展示的数据</p>

**Kind**: global function  
**Author**: 糖霜  

| Param | Description |
| --- | --- |
| topKuaishouItems | <p>已展示的数据</p> |
| showTopItemData | <p>是否展示的数据</p> |

<a name="formatMemo"></a>

## formatMemo(data)
<p>格式化备注</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| data | <p>备注信息</p> |

<a name="formatNumber"></a>

## formatNumber(values)
<p>格式化数字</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| values | <p>配置</p> |
| values.number | <p>要格式化的数字</p> |
| values.decimals | <p>保留几位小数, 默认 0</p> |
| values.util | <p>多少位开启换单位, 默认 万</p> |
| values.roundtag | <p>舍入参数, [ceil: 向上取整, floor: 向下取整, round: 四舍五入], 默认 round</p> |
| values.decPoint | <p>小数点符号, 默认 '.'</p> |
| values.thousandsSep | <p>千分位符号, 默认 无</p> |

<a name="formatSpecItemText"></a>

## formatSpecItemText(item)
<p>格式化规格信息</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| item | <p>规格项</p> |
| item.name | <p>规格项名称</p> |
| item.price | <p>规格项价格，默认为 0</p> |
| item.num | <p>规格项数量，默认为 1</p> |
| item.mark | <p>规格项标记，默认为 x</p> <p>e.g.: 做法/加料 ¥加价金额 x份数 ex: 红烧¥1 x2</p> |

<a name="getWeek"></a>

## getWeek(value)
<p>获取星期</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| value | <p>星期日到星期六排序对应下标 0-6</p> |

<a name="getCurrentTime"></a>

## getCurrentTime(now)
<p>获取当前日期 年 月 日 星期 小时 分钟 秒</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| now | <p>当前时间戳</p> |

<a name="getTimestampRange"></a>

## getTimestampRange(startTimestamp, endTimestamp) ⇒
<p>获取 开始日期-结束日期 之前每天时间戳</p>

**Kind**: global function  
**Returns**: <p>开始到结束之间每天的时间戳</p>  

| Param | Description |
| --- | --- |
| startTimestamp | <p>开始日期</p> |
| endTimestamp | <p>结束日期</p> |

<a name="isSameMonth"></a>

## isSameMonth(dateA, dateB)
<p>判断是否是同一个月</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| dateA | <p>第一个日期</p> |
| dateB | <p>第二个日期</p> |

<a name="useCountDown"></a>

## useCountDown(timer)
<p>倒计时 hook</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| timer | <p>倒计时时间</p> |

<a name="usePageViewTime"></a>

## usePageViewTime(interval) ⇒
<p>页面浏览时间统计</p>

**Kind**: global function  
**Returns**: <ul>
<li>viewTime 页面浏览时间</li>
<li>handle() 开始记录</li>
</ul>  

| Param | Default | Description |
| --- | --- | --- |
| interval | <code>1000</code> | <p>时间间隔</p> |

<a name="getTimeRange 获取时间范围"></a>

## getTimeRange 获取时间范围(code, timeType) ⇒ <code>object</code>
<p>方法说明</p>

**Kind**: global function  
**Returns**: <code>object</code> - <p>startTime - 开始时间  endTime - 结束时间</p>  

| Param | Type | Description |
| --- | --- | --- |
| code | <code>string</code> | <p>昨日  00：00：00 - 23：59：59; this_week 本周 本周周一* 的 00：00：00- 当前的时间; last_week 上周 上周一 00:00:00 - 周日的 23：59:59;</p> |
| timeType | <code>string</code> | <p>时间格式 非必填 默认为时间戳 其他格式见 type ITimeType</p> |

<a name="formatUserInfo"></a>

## formatUserInfo(data) ⇒
<p>我的信息数据处理</p>

**Kind**: global function  
**Returns**: <ul>
<li>name 用户名</li>
<li>avatar 用户头像</li>
<li>userPhone 用户手机号</li>
<li>videoCount 视频数</li>
<li>addressCount 收获地址数量</li>
<li>balance 佣金余额</li>
</ul>  

| Param | Description |
| --- | --- |
| data | <p>客户端返回的数据</p> |

<a name="divide100"></a>

## ~~divide100()~~
***Deprecated***

<p>除以 100 并保留两位小数</p>

**Kind**: global function  
<a name="divide100V2"></a>

## divide100V2(src)
<p>除以 100 并保留两位小数</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| src | <p>被除数</p> |

<a name="removeTrailingZeros"></a>

## removeTrailingZeros(src)
<p>去除数字后面的0</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| src | <p>数字</p> <p>e.g. 12.10 -&gt; 12.1</p> |

<a name="safeDecodeURIComponent"></a>

## safeDecodeURIComponent(str)
<p>code comes form angular
解码 URI 编码</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| str | <p>需要解码的字符串</p> |

<a name="arrRemoveEmpty"></a>

## arrRemoveEmpty(arr)
<p>数组去空item方法</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| arr | <p>数组</p> |

<a name="modifyVideoPageMutedCache"></a>

## modifyVideoPageMutedCache()
<p>修改视频页面是否静音的缓存</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| params.entityId | <p>实体ID</p> |
| params.muted | <p>是否静音</p> |

<a name="setTitle"></a>

## setTitle(name)
<p>设置微信 webview 页面标题</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| name | <p>标题</p> |

<a name="getVideoPageMutedCache"></a>

## getVideoPageMutedCache(entityId)
<p>获取视频页面是否静音的缓存
h5环境一定默认静音 不支持跟随店铺保存配置</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| entityId | <p>实体ID</p> |

<a name="cutImage"></a>

## cutImage(src, menuModule, isShowDefaultSrc, otherParams)
<p>图片裁剪</p>

**Kind**: global function  

| Param | Default | Description |
| --- | --- | --- |
| src |  | <p>图片地址</p> |
| menuModule |  | <p>裁剪模式</p> |
| isShowDefaultSrc | <code>true</code> | <p>是否显示默认图片</p> |
| otherParams |  | <p>其他参数</p> <ul> <li>FIXME: 目前有很多直接用菜单模板类型作为 ECutMode 了, 可以精简为只留几档裁剪尺寸, 菜单再垫一层根据菜单模板类型选择 ECutMode 的方法</li> </ul> |

<a name="asyncDelay"></a>

## asyncDelay(timeout)
<p>异步延时调用</p>

**Kind**: global function  

| Param | Default | Description |
| --- | --- | --- |
| timeout | <code>1000</code> | <p>延迟时间</p> |

<a name="vibrateShort"></a>

## vibrateShort(type)
<p>设备短震动</p>
<ul>
<li>部分设备不支持 非关键反馈 不处理错误</li>
<li>需要手机系统开启触感反馈 否则也会无效</li>
<li>不支持 h5</li>
</ul>

**Kind**: global function  

| Param | Description |
| --- | --- |
| type | <p>震动类型</p> |

<a name="parseQuery"></a>

## parseQuery()
<p>解析 from [url query] to [object]</p>
<ul>
<li>此方法仅供入口流程解析一次url参数</li>
<li>此方法不应该被到处调用 而应该从store获取状态</li>
<li>外部都应该先统一跳转到应用的一个落地页 再重定向到具体业务路径下, 这样只需要在落地页解析一次url参数</li>
</ul>

**Kind**: global function  
<a name="isPageShow"></a>

## isPageShow(page)
<p>判断页面是否显示</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| page | <p>要判断的页面地址</p> |

<a name="generateId"></a>

## generateId()
<p>生成唯一ID</p>

**Kind**: global function  
<a name="getMultiMenuId"></a>

## getMultiMenuId()
<p>获取当前multiMenuId</p>
<ul>
<li>优先从 store.Shop 获取，其次从 store.Menu 获取</li>
</ul>

**Kind**: global function  
<a name="customerPopup"></a>

## customerPopup(func)
<p>客服统一拦截入口</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| func | <p>回调函数</p> |

<a name="compareVersion"></a>

## ~~compareVersion()~~
***Deprecated***

<p>用来比较 currentVersion 当前环境小程序调试基础库 和 appointVersion 指定小程序调试基础库</p>
<ul>
<li>1 代表 currentVersion 大于 appointVersion</li>
<li>0 代表 currentVersion 等于 appointVersion</li>
<li>-1 代表 currentVersion 小于 appointVersion</li>
</ul>

**Kind**: global function  
<a name="useDidUpdateEffect"></a>

## useDidUpdateEffect(fn, inputs)
<p>自定义hooks useEffect 初次渲染不执行</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| fn | <p>需要执行的函数</p> |
| inputs | <p>依赖项</p> |

<a name="requestPaymentAlipay"></a>

## requestPaymentAlipay(prePayId, payUrl)
<p>支付宝支付</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| prePayId | <p>支付id</p> |
| payUrl | <p>支付地址</p> |

<a name="generateError"></a>

## generateError(msg, code)
<p>生成包含 code 的错误</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| msg | <p>错误信息</p> |
| code | <p>错误码</p> |

<a name="hexToRgba"></a>

## hexToRgba(hexColor, alpha, options) ⇒
<p>客户端背景色16进制(前2位为透明度)转换为rgba</p>

**Kind**: global function  
**Returns**: <p>rgba(255, 255, 255, 0.6)</p>  

| Param | Description |
| --- | --- |
| hexColor | <p>#99FFFFFF</p> |
| alpha | <p>自定义透明度0-1</p> |
| options | <p>特殊数据返回配置</p> |

<a name="useDebounceFn"></a>

## useDebounceFn(func, wait, immediate)
<p>防抖</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| func | <p>需要执行的函数</p> |
| wait | <p>防抖时间</p> |
| immediate | <p>是否立即执行</p> |

<a name="formatPageParams"></a>

## ~~formatPageParams(params)~~
***Deprecated***

<p>格式化页面参数</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| params | <p>页面参数</p> |

<a name="accMultiply"></a>

## accMultiply(num1, num2)
<p>精确乘法</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| num1 | <p>被乘数</p> |
| num2 | <p>乘数</p> |

<a name="fen2yuan"></a>

## fen2yuan(num)
<p>分转元</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| num | <p>需要转换的分</p> |

<a name="getHourMS"></a>

## getHourMS() ⇒
<p>获取当天的开始时间</p>

**Kind**: global function  
**Returns**: <p>2022-01-01 00:00:00</p>  
<a name="telEncryption"></a>

## telEncryption(phone) ⇒
<p>格式化手机号 保留后四位和前三位</p>

**Kind**: global function  
**Returns**: <p>123****4567</p>  

| Param | Description |
| --- | --- |
| phone | <p>手机号</p> |

<a name="isFloat"></a>

## isFloat(value)
<p>判断是否是浮点数</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| value | <p>需要判断的值</p> |

<a name="getUnit"></a>

## ~~getUnit(unit) ⇒~~
***Deprecated***

<p>统一获取商家价格单位</p>

**Kind**: global function  
**Returns**: <p>价格单位</p>  

| Param | Description |
| --- | --- |
| unit | <p>单位如份</p> |

<a name="activityShareInfo"></a>

## activityShareInfo() ⇒
<p>邀请有礼活动 入会任务 检查支付接口需要添加 itemId + inviteCustomerId + activityEntityId</p>

**Kind**: global function  
**Returns**: <ul>
<li>itemId 商品id</li>
<li>inviteCustomerId 邀请人id</li>
<li>activityEntityId 活动id</li>
</ul>  
<a name="findComponentId"></a>

## findComponentId(list, name, preFix) ⇒
<p>兼容老版本活动｜商品快速定位组件</p>

**Kind**: global function  
**Returns**: <p>对应快速定位组件 items</p>  

| Param | Description |
| --- | --- |
| list | <p>组件装修数据</p> |
| name | <p>组件名称</p> |
| preFix | <p>组件id前缀</p> |

<a name="isEqual"></a>

## isEqual(target1, target2)
<p>判断两个变量是否相等</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| target1 | <p>变量1</p> |
| target2 | <p>变量2</p> |

<a name="init"></a>

## init()
<ul>
<li>注入jssdk cdn</li>
<li>请求jssdk配置</li>
<li>执行初始化</li>
<li>在ready回调中resolve</li>
<li>如果期间调用了api 自动等待完成然后执行</li>
</ul>

**Kind**: global function  
<a name="parseEnv"></a>

## parseEnv()
<p>获取jssdk环境</p>

**Kind**: global function  
<a name="initScript"></a>

## initScript()
<p>注入jssdk cdn</p>

**Kind**: global function  
<a name="initTicket"></a>

## initTicket()
<p>请求jssdk ticket (仅微信环境需要)</p>

**Kind**: global function  
<a name="initConfig"></a>

## initConfig()
<p>初始化 jssdk</p>

**Kind**: global function  
<a name="call"></a>

## call()
<p>调用jssdk</p>

**Kind**: global function  
<a name="requestPaymentAlipay"></a>

## requestPaymentAlipay(params)
<p>支付宝支付</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| params | <p>支付参数</p> |
| params.prePayId | <p>支付id</p> |
| params.payUrl | <p>支付地址</p> |

<a name="scanCodeAlipay"></a>

## scanCodeAlipay()
<p>扫码支付宝</p>

**Kind**: global function  
<a name="getCurrentLocationAlipay"></a>

## getCurrentLocationAlipay()
<p>支付宝获取当前位置</p>

**Kind**: global function  
<a name="callAppMethod"></a>

## callAppMethod()
<p>app调用方法</p>

**Kind**: global function  
<a name="getToken"></a>

## getToken()
<p>优先从内存缓存取token</p>
<ul>
<li>取不到则尝试从 storage 获取</li>
</ul>

**Kind**: global function  
<a name="keepLogin"></a>

## keepLogin(forceLogin, skipCache)
<p>保持登录</p>
<ul>
<li>检查顺序: 本地token存储 -&gt; Taro.checkSession -&gt; 接口is_valid_token</li>
</ul>

**Kind**: global function  

| Param | Default | Description |
| --- | --- | --- |
| forceLogin | <code>false</code> | <p>是否强制重新登录</p> |
| skipCache | <code>false</code> | <p>默认生命周期内 3分钟 直接通过而不再触发接口 is_valid_token, 传 true 时一定触发</p> |

<a name="notifyDebugEvent"></a>

## notifyDebugEvent()
<p><strong>事件调试</strong> - 标记事件各个步骤合并上报</p>
<ul>
<li>step=start 作为固定开始标记, 将触发重新计时</li>
<li>step=end 作为固定完成标记, 将触发埋点上报, 后续必须再次调用 start 事件来启用</li>
<li>step=cancel 作为固定取消标记, 将直接清空当前事件数据</li>
<li>必须先上报 start 来开启步骤, 否则其他步骤都无效</li>
<li>上报 end 步骤会上报埋点, 并清空当前事件数据, 不再接收后续步骤</li>
</ul>

**Kind**: global function  
<a name="getMemberCardCss"></a>

## getMemberCardCss(themeMode, cardLevel, name)
<p>获取会员卡样式</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| themeMode | <p>主题颜色 light | dark</p> |
| cardLevel | <p>会员等级</p> |
| name | <p>配置项</p> |

<a name="getLevelEndTimeDesc"></a>

## getLevelEndTimeDesc(cardItem, level, periodType, levelEndTime)
<p>卡有效期文案展示</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| cardItem |  |
| level | <p>会员等级</p> |
| periodType | <p>1-指定有效期 2-永久</p> |
| levelEndTime | <p>有效期时间戳</p> |

<a name="navigateToMenu"></a>

## navigateToMenu()
<p>跳转到菜单</p>

**Kind**: global function  
<a name="savePhoneContact"></a>

## savePhoneContact(payload)
<p>保存到通讯录</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| payload | <p>需要保存到通讯录的数据</p> |

<a name="fetchDataList"></a>

## fetchDataList(index, promises)
<p>递归请求</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| index | <p>下标</p> |
| promises | <p>需要执行的函数</p> |

<a name="checkPhone"></a>

## checkPhone()
<p>校验手机号码</p>

**Kind**: global function  
<a name="combineUrl"></a>

## combineUrl(url, params, isGateway)
<p>合并请求参数 - 本地地址</p>

**Kind**: global function  

| Param | Default | Description |
| --- | --- | --- |
| url |  | <p>请求地址</p> |
| params |  | <p>请求参数</p> |
| isGateway | <code>false</code> | <p>是否为网关, 默认为 false</p> |

<a name="combineOriginUrl"></a>

## combineOriginUrl(url, params, skipEncode)
<p>合并请求参数 - 任意地址</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| url | <p>请求地址</p> |
| params | <p>请求参数</p> |
| skipEncode | <p>是否跳过编码</p> |

<a name="getToken"></a>

## getToken()
<p>优先从内存缓存取token</p>
<ul>
<li>取不到则尝试从 storage 获取</li>
</ul>

**Kind**: global function  
<a name="getEntryPagePath"></a>

## getEntryPagePath()
<p>获取入口页面</p>

**Kind**: global function  
<a name="routeTo"></a>

## routeTo(path, options)
<p>跳转页面</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| path | <p>跳转页面</p> |
| options | <p>跳转参数</p> |
| options.params | <p>参数</p> |
| options.action | <p>跳转动作 NAVIGATE - 跳转页面，REDIRECT - 重定向页面，RELAUNCH - 关闭所以页面打开新页面</p> |

<a name="hanldePageRoute"></a>

## hanldePageRoute()
<p>防止小程序页面栈出现多个视频菜单
页面栈中包含多个视频菜单会导致小程序闪退</p>

**Kind**: global function  
<a name="getAppointPaths"></a>

## getAppointPaths(sourceType)
<p>获取指定路径的页面</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| sourceType | <p>页面路径</p> |

<a name="isExistPagePath"></a>

## isExistPagePath(path)
<p>判断页面是否存在</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| path | <p>页面路径</p> |

<a name="routeToPagePath"></a>

## routeToPagePath()
<p>动态判断 navigateBack/navigateTo/redirectTo 到目标路由</p>
<ul>
<li>如果页面栈中有目标路由 则 navigateBack</li>
<li>如果没有目标路由 默认 navigateTo 否则 redirectTo</li>
<li>如果是后退 <strong>不支持</strong>拼接 options.params 参数</li>
</ul>

**Kind**: global function  
<a name="getMemberSystemId"></a>

## getMemberSystemId(type, entityId)
<p>获取会员系统 ID</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| type | <p>跳转类型</p> |
| entityId | <p>实体ID</p> |

<a name="getOrderCount"></a>

## getOrderCount()
<p>获取订单数量</p>

**Kind**: global function  
<a name="addToActivityDetailSource"></a>

## addToActivityDetailSource(code, source)
<p>添加活动详情来源</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| code | <p>跳转类型</p> |
| source | <p>来源</p> |

<a name="getCurrentShopEnvEntityId"></a>

## getCurrentShopEnvEntityId()
<p>获取当前店铺环境实体ID</p>

**Kind**: global function  
<a name="hotspotJump"></a>

## hotspotJump(type, options)
<p>热点跳转</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| type | <p>跳转类型</p> |
| options | <p>跳转参数</p> |

<a name="handleVideoMenuGoods"></a>

## handleVideoMenuGoods(entityId, goodId, multiMenuId, isJumpDetail)
<p>跳转到商品</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| entityId | <p>实体id</p> |
| goodId | <p>商品id</p> |
| multiMenuId | <p>多菜单id</p> |
| isJumpDetail | <p>是否跳转到商品详情</p> |

<a name="usePageShow"></a>

## usePageShow()
<p>支持 showAction 的 Taro.useDidShow</p>

**Kind**: global function  
<a name="navigateBack"></a>

## navigateBack()
<p>快捷方法: 设置上一页的 showAction 并后退</p>
<ul>
<li>可以在上一个页面的 usePageShow 里获取到页面后退事件</li>
</ul>

**Kind**: global function  
<a name="handleNavigatedBack"></a>

## ~~handleNavigatedBack()~~
***Deprecated***

<p>在页面 useDidShow 里调用, 获取返回事件</p>

**Kind**: global function  
<a name="getTargetMenuPath"></a>

## getTargetMenuPath()
<p>当前不在三本菜单中，寻找页面栈中存在的菜单路径(就远原则)，都不存在默认跳视频菜单</p>

**Kind**: global function  
<a name="getCurrentPageName"></a>

## getCurrentPageName()
<p>获取当前页面栈</p>

**Kind**: global function  
<a name="routeToMenu"></a>

## routeToMenu()
<p>跳转到另一本菜单,默认会自动寻找</p>

**Kind**: global function  

| Param | Type | Description |
| --- | --- | --- |
| params.id | <code>string</code> | <p>需要定位到的菜ID</p> |
| params.kindId | <code>string</code> | <p>菜KindId 预留，暂未支持</p> |
| params.target | <code>string</code> | <p>指定一定要跳转的菜单名</p> |

<a name="routeToOrdered"></a>

## routeToOrdered()
<p>跳转到已下单的商品</p>

**Kind**: global function  
<a name="routeToCart"></a>

## routeToCart(action)
<p>跳转到购物车</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| action | <p>跳转方式，NAVIGATE - 跳转页面，REDIRECT - 重定向页面</p> |

<a name="init"></a>

## init()
<p>全局路由监听</p>

**Kind**: global function  
<a name="routerToWebview"></a>

## routerToWebview(name, query, noSplit)
<p>跳转 Webview 页面</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| name | <p>页面名称</p> |
| query | <p>参数</p> |
| noSplit | <p>是否需要拆分 - 默认为需要拆分链接 不需要的话传split</p> |

<a name="saveImageToPhotosAlbum"></a>

## saveImageToPhotosAlbum(options)
<p>保存图片到相册</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| options | <p>保存图片到相册的参数</p> |

<a name="scanCode"></a>

## scanCode()
<p>唤起 扫一扫</p>

**Kind**: global function  
<a name="setAnchorMenuId"></a>

## setAnchorMenuId(id, kindId)
<p>设置锚点</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| id | <p>菜单id</p> |
| kindId | <p>分类id</p> |

<a name="getAnchorMenuId"></a>

## getAnchorMenuId()
<p>获取锚点</p>

**Kind**: global function  
<a name="clearAnchorMenuId"></a>

## clearAnchorMenuId()
<p>清除锚点</p>

**Kind**: global function  
<a name="getCache"></a>

## getCache(originKey, bucket)
<p>获取缓存</p>

**Kind**: global function  

| Param | Default | Description |
| --- | --- | --- |
| originKey |  | <p>原始key</p> |
| bucket | <code>default</code> | <p>存储桶字段 默认为'default'</p> |

<a name="setCache"></a>

## setCache(originKey, data, options)
<p>设置缓存</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| originKey | <p>原始key</p> |
| data | <p>数据</p> |
| options | <p>配置</p> |
| options.bucket | <p>存储桶字段</p> |
| options.expired | <p>过期时间</p> |

<a name="removeCache"></a>

## removeCache(originKey, bucket)
<p>删除缓存</p>

**Kind**: global function  

| Param | Default | Description |
| --- | --- | --- |
| originKey |  | <p>原始key</p> |
| bucket | <code>default</code> | <p>存储桶字段</p> |

<a name="flushCache"></a>

## flushCache(bucket)
<p>清理指定 bucket 下过期的缓存</p>

**Kind**: global function  

| Param | Default | Description |
| --- | --- | --- |
| bucket | <code>default</code> | <p>存储桶字段</p> |

<a name="flushAllCache"></a>

## flushAllCache()
<p>清理所有缓存中过期的缓存</p>

**Kind**: global function  
<a name="removeBucket"></a>

## removeBucket(bucket)
<p>移除指定 bucket</p>

**Kind**: global function  

| Param | Default | Description |
| --- | --- | --- |
| bucket | <code>default</code> | <p>存储桶字段</p> |

<a name="clearGreetingCardData"></a>

## clearGreetingCardData()
<p>清理礼品卡数据</p>

**Kind**: global function  
<a name="cacheTempFile"></a>

## cacheTempFile()
<p>缓存临时文件(路径)到 localStorage</p>
<ul>
<li>小程序临时文件: 空间可以有 2GB, 运行时最多到 4GB, 由微信控制何时清理</li>
</ul>

**Kind**: global function  
<a name="tryTempFile"></a>

## tryTempFile()
<p>尝试获取缓存的临时文件(路径), 满足以下条件时才能成功获取</p>
<ol>
<li>临时文件路径缓存在 temp_file bucket 里</li>
<li>临时文件实际存在(未被微信清理)</li>
</ol>

**Kind**: global function  
<a name="subscribeMessage"></a>

## subscribeMessage(entityId, sceneType)
<p>订阅消息：一店一购</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| entityId | <p>商家ID</p> |
| sceneType | <p>场景</p> |

<a name="subscribeMessage2DVisual"></a>

## subscribeMessage2DVisual(entityId, sceneType)
<p>订阅消息：商家小程序</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| entityId | <p>商家ID</p> |
| sceneType | <p>场景</p> |

<a name="getCacheUserOperate"></a>

## getCacheUserOperate(key)
<p>获取缓存的用户操作</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| key | <p>操作类型</p> |

<a name="setCacheUserOperate"></a>

## setCacheUserOperate(key, data, options)
<p>设置用户操作缓存</p>

**Kind**: global function  

| Param | Description |
| --- | --- |
| key | <p>操作类型</p> |
| data | <p>操作数据</p> |
| options | <p>配置</p> |
| options.expired | <p>过期时间</p> |

