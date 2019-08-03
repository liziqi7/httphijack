# httphijack

使用 `Javascript` 实现前端防御 `http劫持` 及防御 `XSS攻击`，并且对可疑攻击进行上报。

## Usage

引入 `httphijack.js` 。

```HTML
<script type="text/javascript" src='./src/httphijack.js'></script>

<script>
	window.httphijack.init({
			reportUrl: '',//上报地址
			whiteList: ['ac.de.com', 'csdn.net'],//白名单域名，对白名单域名放行
			rules: { //配置规则
				"iframeSrc": true,//页面被嵌套在iframe中
				"inlineEvent": true, //对内联事件拦截
				"staticScript": true,//对静态插入脚本和iframe 拦截
				"dynamicScript": true //对动态脚本 监测
			}
		});
</script>
```

## Features：

- 所有内联 on\* 事件执行的代码
- a 标签 href 属性 `javascript:` 内嵌的代码
- 静态脚本、`iframe` 等恶意内容
- 动态添加的脚本文件、`iframe` 等恶意内容
- `document-write`添加的内容
- 页面被 `iframe` 嵌套劫持

## Tips:

建立自己的域名白名单、关键字黑名单、上报系统及接收后端。

防御 `XSS` 及 `http劫持`，更多的还是得依靠升级 `https` 和 `CSP/CSP2(内容安全策略)` 等非 `JavaScript` 技术，高明的攻击者可以绕过任何 `JavaScript` 防护。

> 组件未在生产环境使用，使用了很多 HTML5 才支持的 API，仅供学习交流。

## License

MIT
