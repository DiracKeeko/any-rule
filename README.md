# 正则大全  ![已收录77条](https://img.shields.io/badge/已收录-77条-673ab7.svg) [![版本](https://badgen.net/vs-marketplace/v/russell.any-rule)](https://marketplace.visualstudio.com/items?itemName=russell.any-rule) [![安装量](https://badgen.net/vs-marketplace/i/russell.any-rule)](https://marketplace.visualstudio.com/items?itemName=russell.any-rule) [![下载量](https://badgen.net/vs-marketplace/d/russell.any-rule)](https://marketplace.visualstudio.com/items?itemName=russell.any-rule) ![MIT](https://img.shields.io/badge/license-MIT-F44336.svg) [![CircleCI](https://badgen.net/github/status/any86/any-rule/master/ci/circleci)](https://circleci.com/gh/any86/any-rule)

🦕支持**web** / **vscode** / **idea** / **Alfred Workflow**多平台

## :rocket:web版本
https://any86.github.io/any-rule/

## 🍭vscode插件

### 安装
vscode应用商店中搜索"**any-rule**".

### 使用
**方式1:**

1. 按**F1**(mac下fn+F1)打开正则列表.
2. **输入关键词搜索**, 比如"手机".

![GIF](https://user-images.githubusercontent.com/8264787/146724787-888a8666-5d2a-4e5e-b383-aec7c53bd312.gif)

**方式2:**

右键选择"🦕正则大全".

![GIF](https://user-images.githubusercontent.com/8264787/146725447-4d92caed-2dd0-4f11-91d1-8da9cd8ff08b.gif)

**方式3:**

在代码任意位置输入"**@zz**".

![GIF](https://user-images.githubusercontent.com/8264787/146725402-30b34119-b709-4d49-adb2-af8dbb786d3b.gif)

## 👩‍🏫图解正则
<details>
<summary>查看详情</summary>
每次在any-rule中选择正则后会弹出提示, 可点击"🤖图解正则".

![image](https://user-images.githubusercontent.com/8264787/146726200-d97e48c3-df76-4531-8210-b6935fffb997.png)

点击后可以看到正则解析, 方便大家学习.

![image](https://user-images.githubusercontent.com/8264787/146726350-58166bf9-7f7f-4685-86aa-f055d0c0b914.png)

**注意**: 图解直接使用了https://regexper.com, 在此对作者表示敬意和感谢.
</details>

## 社区版本
[idea版](https://github.com/zhoriya/idea-rule)

[Alfred Workflow版](https://github.com/cccyb/workflows)

[hyjs: 函数封装版](https://github.com/heiyehk/hyjs/tree/main/packages/utils)

## :fire:关于PR
欢迎大家PR, 步骤如下:
1. **正则**请在**packages/www/src/RULES.js**中添加.
2. 运行`npm run test:rules`进行测试.
3. 运行`npm run build:md`更新**README.md**.
4. 请务必提交到**develop**分支.

在此感谢大家对**any-rule**做出的贡献! 

## 🍔正则

### 火车车次
```javascript
/^[GCDZTSPKXLY1-9]\d{1,4}$/
```

### 手机机身码(IMEI)
```javascript
/^\d{15,17}$/
```

### 必须带端口号的网址(或ip)
```javascript
/^((ht|f)tps?:\/\/)?[\w-]+(\.[\w-]+)+:\d{1,5}\/?$/
```

### 网址(URL)
```javascript
/^(((ht|f)tps?):\/\/)?([^!@#$%^&*?.\s-]([^!@#$%^&*?.\s]{0,63}[^!@#$%^&*?.\s])?\.)+[a-z]{2,6}\/?/
```

### 统一社会信用代码
```javascript
/^[0-9A-HJ-NPQRTUWXY]{2}\d{6}[0-9A-HJ-NPQRTUWXY]{10}$/
```

### 统一社会信用代码(宽松匹配)(15位/18位/20位数字/字母)
```javascript
/^(([0-9A-Za-z]{15})|([0-9A-Za-z]{18})|([0-9A-Za-z]{20}))$/
```

### 迅雷链接
```javascript
/^thunderx?:\/\/[a-zA-Z\d]+=$/
```

### ed2k链接(宽松匹配)
```javascript
/^ed2k:\/\/\|file\|.+\|\/$/
```

### 磁力链接(宽松匹配)
```javascript
/^magnet:\?xt=urn:btih:[0-9a-fA-F]{40,}.*$/
```

### 子网掩码(不包含 0.0.0.0)
```javascript
/^(254|252|248|240|224|192|128)\.0\.0\.0|255\.(254|252|248|240|224|192|128|0)\.0\.0|255\.255\.(254|252|248|240|224|192|128|0)\.0|255\.255\.255\.(255|254|252|248|240|224|192|128|0)$/
```

### linux"隐藏文件"路径
```javascript
/^\/(?:[^\/]+\/)*\.[^\/]*/
```

### linux文件夹路径
```javascript
/^\/(?:[^\/]+\/)*$/
```

### linux文件路径
```javascript
/^\/(?:[^\/]+\/)*[^\/]+$/
```

### window"文件夹"路径
```javascript
/^[a-zA-Z]:\\(?:\w+\\?)*$/
```

### window下"文件"路径
```javascript
/^[a-zA-Z]:\\(?:\w+\\)*\w+\.\w+$/
```

### 股票代码(A股)
```javascript
/^(s[hz]|S[HZ])(000[\d]{3}|002[\d]{3}|300[\d]{3}|600[\d]{3}|60[\d]{4})$/
```

### 大于等于0, 小于等于150, 支持小数位出现5, 如145.5, 用于判断考卷分数
```javascript
/^150$|^(?:\d|[1-9]\d|1[0-4]\d)(?:\.5)?$/
```

### html注释
```javascript
/<!--[\s\S]*?-->/g
```

### md5格式(32位)
```javascript
/^([a-f\d]{32}|[A-F\d]{32})$/
```

### GUID/UUID
```javascript
/^[a-f\d]{4}(?:[a-f\d]{4}-){4}[a-f\d]{12}$/i
```

### 版本号(version)格式必须为X.Y.Z
```javascript
/^\d+(?:\.\d+){2}$/
```

### 视频(video)链接地址（视频格式可按需增删）
```javascript
/^https?:\/\/(.+\/)+.+(\.(swf|avi|flv|mpg|rm|mov|wav|asf|3gp|mkv|rmvb|mp4))$/i
```

### 图片(image)链接地址（图片格式可按需增删）
```javascript
/^https?:\/\/(.+\/)+.+(\.(gif|png|jpg|jpeg|webp|svg|psd|bmp|tif))$/i
```

### 24小时制时间（HH:mm:ss）
```javascript
/^(?:[01]\d|2[0-3]):[0-5]\d:[0-5]\d$/
```

### 12小时制时间（hh:mm:ss）
```javascript
/^(?:1[0-2]|0?[1-9]):[0-5]\d:[0-5]\d$/
```

### base64格式
```javascript
/^\s*data:(?:[a-z]+\/[a-z0-9-+.]+(?:;[a-z-]+=[a-z0-9-]+)?)?(?:;base64)?,([a-z0-9!$&',()*+;=\-._~:@\/?%\s]*?)\s*$/i
```

### 数字/货币金额（支持负数、千分位分隔符）
```javascript
/^-?\d+(,\d{3})*(\.\d{1,2})?$/
```

### 数字/货币金额 (只支持正数、不支持校验千分位分隔符)
```javascript
/(?:^[1-9]([0-9]+)?(?:\.[0-9]{1,2})?$)|(?:^(?:0)$)|(?:^[0-9]\.[0-9](?:[0-9])?$)/
```

### 银行卡号（10到30位, 覆盖对公/私账户, 参考[微信支付](https://pay.weixin.qq.com/wiki/doc/api/xiaowei.php?chapter=22_1)）
```javascript
/^[1-9]\d{9,29}$/
```

### 中文姓名
```javascript
/^(?:[\u4e00-\u9fa5·]{2,16})$/
```

### 英文姓名
```javascript
/(^[a-zA-Z][a-zA-Z\s]{0,20}[a-zA-Z]$)/
```

### 车牌号(新能源)
```javascript
/^[京津沪渝冀豫云辽黑湘皖鲁新苏浙赣鄂桂甘晋蒙陕吉闽贵粤青藏川宁琼使领][A-HJ-NP-Z](?:((\d{5}[A-HJK])|([A-HJK][A-HJ-NP-Z0-9][0-9]{4}))|[A-HJ-NP-Z0-9]{4}[A-HJ-NP-Z0-9挂学警港澳])$/
```

### 车牌号(非新能源)
```javascript
/^[京津沪渝冀豫云辽黑湘皖鲁新苏浙赣鄂桂甘晋蒙陕吉闽贵粤青藏川宁琼使领][A-HJ-NP-Z][A-HJ-NP-Z0-9]{4}[A-HJ-NP-Z0-9挂学警港澳]$/
```

### 车牌号(新能源+非新能源)
```javascript
/^[京津沪渝冀豫云辽黑湘皖鲁新苏浙赣鄂桂甘晋蒙陕吉闽贵粤青藏川宁琼使领][A-HJ-NP-Z][A-HJ-NP-Z0-9]{4,5}[A-HJ-NP-Z0-9挂学警港澳]$/
```

### 手机号(mobile phone)中国(严谨), 根据工信部2019年最新公布的手机号段
```javascript
/^(?:(?:\+|00)86)?1(?:(?:3[\d])|(?:4[5-79])|(?:5[0-35-9])|(?:6[5-7])|(?:7[0-8])|(?:8[\d])|(?:9[189]))\d{8}$/
```

### 手机号(mobile phone)中国(宽松), 只要是13,14,15,16,17,18,19开头即可
```javascript
/^(?:(?:\+|00)86)?1[3-9]\d{9}$/
```

### 手机号(mobile phone)中国(最宽松), 只要是1开头即可, 如果你的手机号是用来接收短信, 优先建议选择这一条
```javascript
/^(?:(?:\+|00)86)?1\d{10}$/
```

### date(日期)
```javascript
/^\d{1,4}(-)(1[0-2]|0?[1-9])\1(0?[1-9]|[1-2]\d|30|31)$/
```

### 可以被moment转化成功的时间 YYYYMMDD HH:mm:ss
```javascript
/^\d{4}([\/:-\S])(1[0-2]|0?[1-9])\1(0?[1-9]|[1-2]\d|30|31) (?:[01]\d|2[0-3]):[0-5]\d:[0-5]\d$/
```

### email(邮箱)
```javascript
/^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
```

### 座机(tel phone)电话(国内),如: 0341-86091234
```javascript
/^(?:(?:\d{3}-)?\d{8}|^(?:\d{4}-)?\d{7,8})(?:-\d+)?$/
```

### 身份证号(1代,15位数字)
```javascript
/^[1-9]\d{7}(?:0\d|10|11|12)(?:0[1-9]|[1-2][\d]|30|31)\d{3}$/
```

### 身份证号(2代,18位数字),最后一位是校验位,可能为数字或字符X
```javascript
/^[1-9]\d{5}(?:18|19|20)\d{2}(?:0[1-9]|10|11|12)(?:0[1-9]|[1-2]\d|30|31)\d{3}[\dXx]$/
```

### 身份证号, 支持1/2代(15位/18位数字)
```javascript
/^\d{6}((((((19|20)\d{2})(0[13-9]|1[012])(0[1-9]|[12]\d|30))|(((19|20)\d{2})(0[13578]|1[02])31)|((19|20)\d{2})02(0[1-9]|1\d|2[0-8])|((((19|20)([13579][26]|[2468][048]|0[48]))|(2000))0229))\d{3})|((((\d{2})(0[13-9]|1[012])(0[1-9]|[12]\d|30))|((\d{2})(0[13578]|1[02])31)|((\d{2})02(0[1-9]|1\d|2[0-8]))|(([13579][26]|[2468][048]|0[048])0229))\d{2}))(\d|X|x)$/
```

### 护照（包含香港、澳门）
```javascript
/(^[EeKkGgDdSsPpHh]\d{8}$)|(^(([Ee][a-fA-F])|([DdSsPp][Ee])|([Kk][Jj])|([Mm][Aa])|(1[45]))\d{7}$)/
```

### 帐号是否合法(字母开头，允许5-16字节，允许字母数字下划线组合
```javascript
/^[a-zA-Z]\w{4,15}$/
```

### 中文/汉字
```javascript
/^(?:[\u3400-\u4DB5\u4E00-\u9FEA\uFA0E\uFA0F\uFA11\uFA13\uFA14\uFA1F\uFA21\uFA23\uFA24\uFA27-\uFA29]|[\uD840-\uD868\uD86A-\uD86C\uD86F-\uD872\uD874-\uD879][\uDC00-\uDFFF]|\uD869[\uDC00-\uDED6\uDF00-\uDFFF]|\uD86D[\uDC00-\uDF34\uDF40-\uDFFF]|\uD86E[\uDC00-\uDC1D\uDC20-\uDFFF]|\uD873[\uDC00-\uDEA1\uDEB0-\uDFFF]|\uD87A[\uDC00-\uDFE0])+$/
```

### 小数
```javascript
/^\d+\.\d+$/
```

### 数字
```javascript
/^\d{1,}$/
```

### html标签(宽松匹配)
```javascript
/<(\w+)[^>]*>(.*?<\/\1>)?/
```

### qq号格式正确
```javascript
/^[1-9][0-9]{4,10}$/
```

### 数字和字母组成
```javascript
/^[A-Za-z0-9]+$/
```

### 英文字母
```javascript
/^[a-zA-Z]+$/
```

### 小写英文字母组成
```javascript
/^[a-z]+$/
```

### 大写英文字母
```javascript
/^[A-Z]+$/
```

### 密码强度校验，最少6位，包括至少1个大写字母，1个小写字母，1个数字，1个特殊字符
```javascript
/^\S*(?=\S{6,})(?=\S*\d)(?=\S*[A-Z])(?=\S*[a-z])(?=\S*[!@#$%^&*? ])\S*$/
```

### 用户名校验，4到16位（字母，数字，下划线，减号）
```javascript
/^[a-zA-Z0-9_-]{4,16}$/
```

### ip-v4[:端口]
```javascript
/^((\d|[1-9]\d|1\d\d|2[0-4]\d|25[0-5])\.){3}(\d|[1-9]\d|1\d\d|2[0-4]\d|25[0-5])(?::(?:[0-9]|[1-9][0-9]{1,3}|[1-5][0-9]{4}|6[0-4][0-9]{3}|65[0-4][0-9]{2}|655[0-2][0-9]|6553[0-5]))?$/
```

### ip-v6[:端口]
```javascript
/(^(?:(?:(?:[0-9A-Fa-f]{1,4}:){7}[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){6}:[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){5}:([0-9A-Fa-f]{1,4}:)?[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){4}:([0-9A-Fa-f]{1,4}:){0,2}[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){3}:([0-9A-Fa-f]{1,4}:){0,3}[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){2}:([0-9A-Fa-f]{1,4}:){0,4}[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){6}((\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b)\.){3}(\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b))|(([0-9A-Fa-f]{1,4}:){0,5}:((\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b)\.){3}(\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b))|(::([0-9A-Fa-f]{1,4}:){0,5}((\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b)\.){3}(\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b))|([0-9A-Fa-f]{1,4}::([0-9A-Fa-f]{1,4}:){0,5}[0-9A-Fa-f]{1,4})|(::([0-9A-Fa-f]{1,4}:){0,6}[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){1,7}:))$)|(^\[(?:(?:(?:[0-9A-Fa-f]{1,4}:){7}[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){6}:[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){5}:([0-9A-Fa-f]{1,4}:)?[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){4}:([0-9A-Fa-f]{1,4}:){0,2}[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){3}:([0-9A-Fa-f]{1,4}:){0,3}[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){2}:([0-9A-Fa-f]{1,4}:){0,4}[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){6}((\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b)\.){3}(\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b))|(([0-9A-Fa-f]{1,4}:){0,5}:((\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b)\.){3}(\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b))|(::([0-9A-Fa-f]{1,4}:){0,5}((\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b)\.){3}(\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b))|([0-9A-Fa-f]{1,4}::([0-9A-Fa-f]{1,4}:){0,5}[0-9A-Fa-f]{1,4})|(::([0-9A-Fa-f]{1,4}:){0,6}[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){1,7}:))\](?::(?:[0-9]|[1-9][0-9]{1,3}|[1-5][0-9]{4}|6[0-4][0-9]{3}|65[0-4][0-9]{2}|655[0-2][0-9]|6553[0-5]))?$)/i
```

### 16进制颜色
```javascript
/^#?([a-fA-F0-9]{6}|[a-fA-F0-9]{3})$/
```

### 微信号(wx)，6至20位，以字母开头，字母，数字，减号，下划线
```javascript
/^[a-zA-Z][-_a-zA-Z0-9]{5,19}$/
```

### 邮政编码(中国)
```javascript
/^(0[1-7]|1[0-356]|2[0-7]|3[0-6]|4[0-7]|5[1-7]|6[1-7]|7[0-5]|8[013-6])\d{4}$/
```

### 中文和数字
```javascript
/^((?:[\u3400-\u4DB5\u4E00-\u9FEA\uFA0E\uFA0F\uFA11\uFA13\uFA14\uFA1F\uFA21\uFA23\uFA24\uFA27-\uFA29]|[\uD840-\uD868\uD86A-\uD86C\uD86F-\uD872\uD874-\uD879][\uDC00-\uDFFF]|\uD869[\uDC00-\uDED6\uDF00-\uDFFF]|\uD86D[\uDC00-\uDF34\uDF40-\uDFFF]|\uD86E[\uDC00-\uDC1D\uDC20-\uDFFF]|\uD873[\uDC00-\uDEA1\uDEB0-\uDFFF]|\uD87A[\uDC00-\uDFE0])|(\d))+$/
```

### 不能包含字母
```javascript
/^[^A-Za-z]*$/
```

### java包名
```javascript
/^([a-zA-Z_]\w*)+([.][a-zA-Z_]\w*)+$/
```

### mac地址
```javascript
/^((([a-f0-9]{2}:){5})|(([a-f0-9]{2}-){5}))[a-f0-9]{2}$/i
```

### 匹配连续重复的字符
```javascript
/(.)\1+/
```

### 数字和英文字母组成，并且同时含有数字和英文字母
```javascript
/^(?=.*[a-zA-Z])(?=.*\d).+$/
```

### 香港身份证 
```javascript
/^[a-zA-Z]\d{6}\([\dA]\)$/
```

### 澳门身份证 
```javascript
/^[1|5|7]\d{6}\(\d\)$/
```

### 台湾身份证 
```javascript
/^[a-zA-Z][0-9]{9}$/
```

### 大写字母，小写字母，数字，特殊符号 `@#$%^&*`~()-+=` 中任意3项密码
```javascript
/^(?![a-zA-Z]+$)(?![A-Z0-9]+$)(?![A-Z\W_!@#$%^&*`~()-+=]+$)(?![a-z0-9]+$)(?![a-z\W_!@#$%^&*`~()-+=]+$)(?![0-9\W_!@#$%^&*`~()-+=]+$)[a-zA-Z0-9\W_!@#$%^&*`~()-+=]/
```

### 正整数，不包含0
```javascript
/^\+?[1-9]\d*$/
```

### 负整数，不包含0
```javascript
/^-[1-9]\d*$/
```

### 整数
```javascript
/^-?[1-9]\d*$/
```

### 浮点数
```javascript
/^(-?\d+)(\.\d+)?$/
```

### email(支持中文邮箱)
```javascript
/^[A-Za-z0-9\u4e00-\u9fa5]+@[a-zA-Z0-9_-]+(\.[a-zA-Z0-9_-]+)+$/
```
