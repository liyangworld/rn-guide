# 封装日志打印 - log.js

封装自己的日志打印功能，以实现以下需求：

* 开发环境输出打印到控制台，生产环境禁用打印
* 打印时高亮显示，并自动添加当前时间
* 将日志存储在本地，或者批量发送到日志服务器

代码实现如下：

```javascript
'use strict';
//日志存放处
let logs = [];

//如果日志超过200条就去掉最早的那条日志
//或批量写入服务器 然后清空
function add(log){
    logs.push(log);
    if(logs.length>200)logs.shift();
}

exports.getLogs = function () {
    return logs;
}
exports.getLog = function (index) {
    return logs[index];
}

function getNowStr(){
	const now = new Date();
	return now.toLocaleDateString()+ ' ' + now.toTimeString().substr(0, 8);
}

//输出信息 仅用于开发时调试
exports.log = function (...args) {
    if (__DEV__) {
        args[0] = "%c" + getNowStr() + ' ' +  args[0];
        args.splice(1, 0, 'color: #2d8cf0');
        console.log(...args);
    }
}

//输出成功
exports.logSuccess = function (...args) {
	args.unshift(getNowStr());
    add(args);
    if (__DEV__) {
		let info = args.concat();
        info[0] = "%c" + info.shift() + ' ' +  info[0];
        info.splice(1, 0, 'color: #3EC408');
        console.log(...info);
    }
}

//输出错误
exports.logError = function (...args) {
	args.unshift(getNowStr());
    add(args);
    if (__DEV__) {
		let info = args.concat();
        info[0] = "%c" + info.shift() + ' ' +  info[0];
        info.splice(1, 0, 'color: #ed3f14');
        console.log(...info);
    }
}

//输出警告
exports.logWarn = function (...args) {
	args.unshift(getNowStr());
    add(args);
    if (__DEV__) {
        let info = args.concat();
        info[0] = "%c" + info.shift() + ' ' +  info[0];
        info.splice(1, 0, 'color: #ff9900');
        console.log(...info);
    }
}
```

主要对外暴露了4个方法：log、logSuccess、logError、logWarn。