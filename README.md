# vuejs-starting

## 준비 과정
* nodejs 설치
	- <https://nodejs.org/>
* Atom editor 설치
	- <https://atom.io/>
* yarn 설치
	```
	npm -g install yarn
	```

## Vue-cli 사용
* Vue-cli 설치
```
npm install -g @vue/cli
or
yarn global add @vue/cli
```
* 프로젝트 생성
```
vue create new-project-name
```
* Vuetify 적용 (Optional)
```
cd new-project-name
vue add vuetify
```
## VueLogger 설치
<https://www.npmjs.com/package/vuejs-logger>
```
cd new-project-name
npm install vuejs-logger
```
* Code example
	- **/src/main.js**
	```
	import VueLogger from 'vuejs-logger';
	const isProduction = process.env.NODE_ENV === 'production';

	const loggerOptions = {
		isEnabeld: true,
		logLevel : isProduction ? 'error' : 'debug',
		stringifyArguments : false,
		showLogLevel : true,
		showMethodName : true,
		separator: '|',
		showConsoleColors: true
	};

	Vue.use(VueLogger, loggerOptions);
	```
	- Write logs (**/views/someVueFile.vue**)
	```
	... (중략)
	export default {
		mothods: {
			someMethod () {
				this.$log.debug('SomeLog.data.debug')
				this.$log.info('SomeLog.data.info')
				this.$log.warn('SomeLog.data.warn')
				this.$log.error('SomeLog.data.error')
				this.$log.fatal('SomeLog.data.fatal')
			}
		}
	}
	... (이하 생략)
	```
