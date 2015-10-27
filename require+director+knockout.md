

1. require.js 
```javascript
require.config({
	paths: {
		text: 'lib/requirejs/text',
		css: 'lib/requirejs/css',
		jquery: 'lib/jquery/jquery-1.11.2',
		knockout: "lib/knockout/knockout-3.2.0.debug",
		director: 'lib/director/director',
		bootstrap: 'lib/bootstrap/js/bootstrap',
		dataapi: 'scripts/dataapi',
		util: 'scripts/util',
		nav: 'scripts/util',
		channel: 'scripts/channel',
		report: 'scripts/report'
	},
	shim: {
		"dataapi": {
			deps: ["jquery"]
		},
		"bootstrap": {
			deps: ["jquery"]
		}
	}
});

require(['text!html/channel.html', 'scripts/channel.js', 'css!styles/channel.css'], function(template, jsModel) {
	$("#content").html(template);
	jsModel.init(index);
});
```
    
2. director.js
```javascript
var routes = {
	'/channel/:channelIndex': channel,
	'/report': report
};
window.router = Router(routes);
// 初始化路由
window.router.init();
```

3. knockout.js
示例和机制


