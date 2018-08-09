![React Loadable](http://thejameskyle.com/img/react-loadable-header.png)

[![translate-svg]][translate-list]

组件的动态导入与加载 的 高级组件

> 如果你听过 路由控制 动态导入组件(基于路由的分割),那么这个库就是高级组件控制的(基于组件的分割)

[translate-svg]: http://llever.com/translate.svg
[translate-list]: https://github.com/chinanf-boy/chinese-translate-list


---

## 校对🀄

欢迎 \`Issue\` 和 \`Pull\` ❤️, 最好 \`Pull\` 👏

|翻译的原文|与日期|原文更新|更多
---|---|---|---
[commit]|2018 7.20|![last commit][last]|[中文翻译][more]

[commit]:  https://github.com/jamiebuilds/react-loadable/tree/8992fd510dea6d2d26afe04e8f6e2a23297798ab
[last]: https://img.shields.io/github/last-commit/jamiebuilds/react-loadable.svg
[more]: https://github.com/chinanf-boy/chinese-translate-list

## 生活

[help me live , live need money 💰](https://github.com/chinanf-boy/live-need-money)

---


## 安装

```sh
yarn add react-loadable
```

## 例

```js
import Loadable from 'react-loadable';
import Loading from './my-loading-component';

const LoadableComponent = Loadable({
  loader: () => import('./my-component'),
  loading: Loading,
});

export default class App extends React.Component {
  render() {
    return <LoadableComponent/>;
  }
}
```

## 快乐的客户: 

-   ["我现在对此很着迷: CRA使用React Router v4并且可以反应加载. 免费代码拆分,这很容易. "](https://twitter.com/matzatorski/status/872059865350406144)
-   ["Webpack 2升级和反应可装载;在2小时内初始负载从1.1mb到529kb. 很大. "](https://twitter.com/jwbradley87/status/847191118269833216)
-   ["哦,嘿 - 使用可加载的组件,我在初始负载下撞了13K. 轻松获胜!"](https://twitter.com/AdamRackis/status/846593080992153600)
-   ["看了一眼就看起来很棒了. 在我们的主捆上刮了50kb. "](https://github.com/quran/quran.com-frontend/pull/701#issuecomment-287908551)
-   ["我已经完成了服务器端渲染+代码拆分+ PWA ServiceWorker缓存设置😎 (感谢react-loadable) . 现在我们的前端非常快. "](https://twitter.com/mxstbr/status/922375575217627136)
-   ["使用react-loadable来自221.28 KB→115.76 KB @ main bundle. 他妈的非常棒且非常简单. "](https://twitter.com/evgenyrodionov/status/958821614644269057)

## 用户

-   [Analog.Cafe](https://www.analog.cafe)
-   [Appbase.io](https://github.com/appbaseio/reactivesearch)
-   [Atlassian的](https://www.atlassian.com/)
-   [CloudFlare的](https://www.cloudflare.com)
-   [古玩](https://www.curio.org)
-   [Dresez](https://dresez.pk/)
-   [Flyhomes](https://flyhomes.com)
-   [勾勾](https://gogoair.com)
-   [联发科技MCS-Lite](https://github.com/MCS-Lite)
-   [给予](https://render.com)
-   [Snipit](https://snipit.io)
-   [Spectrum.chat](https://spectrum.chat)
-   [Talentpair](https://talentpair.com)
-   [火种](https://tinder.com/)
-   [Unsplash](https://unsplash.com/)
-   [波](https://waveapps.com/)

> *如果您的公司或项目正在使用React Loadable,请打开PR并将自己添加到此列表中 (请按字母顺序排列) *

## 另见: 

-   [`react-loadable-visibility`](https://github.com/stratiformltd/react-loadable-visibility)- 建立在和保持相同的API之上`react-loadable`,此库使您可以加载屏幕上可见的内容. 

<h2>
  <hr>
  <hr>
  <img src="http://thejameskyle.com/img/react-loadable-guide.png" alt="GUIDE">
  <hr>
  <hr>
  <small>Guide</small>
</h2>

所以你有你的React应用程序,你将它与Webpack捆绑在一起,事情进展顺利. 但是有一天你会注意到你的应用程序的捆绑包变得越来越大,以至于减慢了速度. 

是时候开始代码拆分您的应用了!

![A single giant bundle vs multiple smaller bundles](http://thejameskyle.com/img/react-loadable-split-bundles.png)

代码拆分是一个包含整个应用程序的大型捆绑包,并将它们拆分为多个较小的捆绑包,其中包含应用程序的不同部分. 

这似乎很难做到,但像Webpack这样的工具内置了这个工具,而React Loadable旨在使其变得非常简单. 

### 基于路由的拆分与基于组件的拆分您将看到的一条常见建议是将应用程序分成不同的路径,并异步加载每个路径. 

对于许多应用程序而言,这似乎运行良好 - 作为用户,单击链接并等待页面加载是Web上熟悉的体验. 但我们可以做得更好. 

使用React的大多数路由工具,路由只是一个组件. 

对他们来说没什么特别的 (对不起莱恩和迈克尔 - 你有什么特别之处) . 那么如果我们针对组件而不是路由进行优化来进行优化呢?那会让我们得到什么?事实证明: 相当多. 

![Route vs. component centric code splitting](http://thejameskyle.com/img/react-loadable-component-splitting.png)

除了路线之外,还有很多地方可以轻松拆分您的应用. 模式,选项卡和更多UI组件隐藏内容,直到用户完成某些操作才能显示它. 例: 

> **也许你的应用程序有一个埋在选项卡组件内的地图. **每当用户可能永远不会访问该选项卡时,为什么要为父路由加载大量映射库?更不用说所有可以推迟加载内容的地方,直到更高优先级的内容加载完毕. 

页面底部的那个组件加载了一堆库: 为什么要与顶部的内容同时加载?而且由于路由只是组件,我们仍然可以在路由级别轻松进行代码分割. 

在您的应用中引入新的代码分割点应该非常简单,您不必再三考虑它. 

这应该是改变几行代码的问题,其他一切都应该是自动化的. 介绍React Loadable

### React Loadable是一个小型库,它使得以组件为中心的代码在React中非常容易分割. 

是一个高阶组件 (一个创建组件的函数) ,它允许您在将任何模块呈现到应用程序之前动态加载它. 

`Loadable`让我们设想两个组件,一个导入并渲染另一个组件. 

现在我们依赖

```js
import Bar from './components/Bar';

class Foo extends React.Component {
  render() {
    return <Bar/>;
  }
}
```

通过同步导入`Bar`,但是在我们去渲染它之前我们不需要它. `import`那么我们为什么不推迟呢?

用一个**动态导入** ([目前处于第3阶段的tc39提案](https://github.com/tc39/proposal-dynamic-import)) 我们可以修改我们的组件加载`Bar`异步. 

```js
class MyComponent extends React.Component {
  state = {
    Bar: null
  };

  componentWillMount() {
    import('./components/Bar').then(Bar => {
      this.setState({ Bar });
    });
  }

  render() {
    let {Bar} = this.state;
    if (!Bar) {
      return <div>Loading...</div>;
    } else {
      return <Bar/>;
    };
  }
}
```

但这是一大堆工作,它甚至没有处理一堆案例. 什么时候`import()`失败?那么服务器端渲染呢?

相反,你可以使用`Loadable`去除问题. 

```js
import Loadable from 'react-loadable';

const LoadableBar = Loadable({
  loader: () => import('./components/Bar'),
  loading() {
    return <div>Loading...</div>
  }
});

class MyComponent extends React.Component {
  render() {
    return <LoadableBar/>;
  }
}
```

### 自动代码分割`import()`

当你使用`import()`使用Webpack 2+,它会[自动进行代码分割](https://webpack.js.org/guides/code-splitting/)为您而无需额外配置. 

这意味着只需切换到即可轻松尝试新的代码分割点`import()`并使用React Loadable. 找出最适合您的应用的内容. 

### 创建一个伟大的"加载..."组件

渲染静态"正在加载..."与用户的通信不够. 您还需要考虑错误状态,超时并使其成为一种不错的体验. 

```js
function Loading() {
  return <div>Loading...</div>;
}

Loadable({
  loader: () => import('./WillFailToLoad'), // oh no!
  loading: Loading,
});
```

为了让这一切变得美好,你的[加载组件](#loadingcomponent)收到几个不同的道具. 

#### 加载错误状态

当你的[`loader`](optsloader)失败,你的[加载组件](#loadingcomponent)会收到一个[`error`](propserror)道具将是一个`Error`对象 (否则它将是`null`) . 

```js
function Loading(props) {
  if (props.error) {
    return <div>Error! <button onClick={ props.retry }>Retry</button></div>;
  } else {
    return <div>Loading...</div>;
  }
}
```

#### 避免*闪存的加载组件*

有时组件加载速度非常快 (\<200ms) ,加载屏幕只会在屏幕上快速闪烁. 

许多用户研究已经证明,这会导致用户感知事情的时间比实际时间长. 如果您没有显示任何内容,用户会认为它更快. 

所以你的加载组件也会得到一个[`pastDelay`支柱](#propspastdelay)只有当组件加载时间超过一组时才会成立[延迟](#optsdelay). 

```js
function Loading(props) {
  if (props.error) {
    return <div>Error! <button onClick={ props.retry }>Retry</button></div>;
  } else if (props.pastDelay) {
    return <div>Loading...</div>;
  } else {
    return null;
  }
}
```

此延迟默认为`200ms`但你也可以自定义[延迟](#optsdelay)在`Loadable`. 

```js
Loadable({
  loader: () => import('./components/Bar'),
  loading: Loading,
  delay: 300, // 0.3 seconds
});
```

#### 定时出来的时候`loader`花了太长时间

有时网络连接很糟糕,永远不会解决或失败,它们只是永远挂在那里. 这对用户来说很糟糕,因为他们不知道是否应该总是花这么长时间,或者他们应该尝试刷新. 

该[加载组件](#loadingcomponent)会收到一个[`timedOut`支柱](#propstimedout)将被设置为`true`当. . . 的时候[`loader`](#optsloader)已经超时了. 

```js
function Loading(props) {
  if (props.error) {
    return <div>Error! <button onClick={ props.retry }>Retry</button></div>;
  } else if (props.timedOut) {
    return <div>Taking a long time... <button onClick={ props.retry }>Retry</button></div>;
  } else if (props.pastDelay) {
    return <div>Loading...</div>;
  } else {
    return null;
  }
}
```

但是,默认情况下禁用此功能. 要打开它,你可以传递一个[`timeout`选项](#optstimeout)至`Loadable`. 

```js
Loadable({
  loader: () => import('./components/Bar'),
  loading: Loading,
  timeout: 10000, // 10 seconds
});
```

### 自定义渲染

默认`Loadable`将呈现`default`导出返回的模块. 如果要自定义此行为,可以使用[`render`选项](#optsrender). 

```js
Loadable({
  loader: () => import('./my-component'),
  render(loaded, props) {
    let Component = loaded.namedExport;
    return <Component {...props}/>;
  }
});
```

### 加载多个资源

从技术上讲,你可以做任何你想做的事`loader()`只要它返回一个承诺和[你能够渲染一些东西](#customizing-rendering). 但写出来可能有点烦人. 

为了便于并行加载多个资源,您可以使用[`Loadable.Map`](#loadablemap). 

```js
Loadable.Map({
  loader: {
    Bar: () => import('./Bar'),
    i18n: () => fetch('./i18n/bar.json').then(res => res.json()),
  },
  render(loaded, props) {
    let Bar = loaded.Bar.default;
    let i18n = loaded.i18n;
    return <Bar {...props} i18n={i18n}/>;
  },
});
```

使用时`Loadable.Map`该[`render()`方法](#optsrender)是必须的. 它将通过一个`loaded`param是一个与你的形状相匹配的物体`loader`. 

### 预加载

作为优化,您还可以决定在呈现之前预加载组件. 

例如,如果您需要在按下按钮时加载新组件,则可以在用户将鼠标悬停在按钮上时开始预加载组件. 

创建的组件`Loadable`露出一个[静态的`preload`方法](#loadablecomponentpreload)这正是这个. 

```js
const LoadableBar = Loadable({
  loader: () => import('./Bar'),
  loading: Loading,
});

class MyComponent extends React.Component {
  state = { showBar: false };

  onClick = () => {
    this.setState({ showBar: true });
  };

  onMouseOver = () => {
    LoadableBar.preload();
  };

  render() {
    return (
      <div>
        <button
          onClick={this.onClick}
          onMouseOver={this.onMouseOver}>
          Show Bar
        </button>
        {this.state.showBar && <LoadableBar/>}
      </div>
    )
  }
}
```

<h2>
  <hr>
  <hr>
  <img src="http://thejameskyle.com/img/react-loadable-ssr.png" alt="SERVER SIDE RENDERING">
  <hr>
  <hr>
  <small>Server-Side Rendering</small>
</h2>

当你去渲染所有这些动态加载的组件时,你会得到的是一大堆加载屏幕. 

这真的很糟糕,但好消息是React Loadable旨在使服务器端渲染工作,好像没有动态加载任何内容. 

这是我们的启动服务器使用[表现](https://expressjs.com/). 

```js
import express from 'express';
import React from 'react';
import ReactDOMServer from 'react-dom/server';
import App from './components/App';

const app = express();

app.get('/', (req, res) => {
  res.send(`
    <!doctype html>
    <html lang="en">
      <head>...</head>
      <body>
        <div id="app">${ReactDOMServer.renderToString(<App/>)}</div>
        <script src="/dist/main.js"></script>
      </body>
    </html>
  `);
});

app.listen(3000, () => {
  console.log('Running on http://localhost:3000/');
});
```

### 在服务器上预加载所有可加载组件

从服务器呈现正确内容的第一步是确保在您渲染它们时已经加载了所有可加载组件. 

为此,您可以使用[`Loadable.preloadAll`](#loadablepreloadall)方法. 它返回一个承诺,该承诺将在所有可加载组件准备就绪时解决. 

```js
Loadable.preloadAll().then(() => {
  app.listen(3000, () => {
    console.log('Running on http://localhost:3000/');
  });
});
```

### 在客户端上拾取服务器端呈现的应用程序

这是事情变得有点棘手的地方. 所以让我们为自己做好准备吧. 

为了让我们获取从服务器呈现的内容,我们需要拥有用于在服务器上呈现的所有相同代码. 

为此,我们首先需要可加载的组件来告诉我们它们正在渲染哪些模块. 

#### 声明正在加载哪些模块

有两种选择[`Loadable`](#loadable)和[`Loadable.Map`](#loadablemap)用于告诉我们组件尝试加载哪些模块: [`opts.modules`](#optsmodules)和[`opts.webpack`](#optswebpack). 

```js
Loadable({
  loader: () => import('./Bar'),
  modules: ['./Bar'],
  webpack: () => [require.resolveWeak('./Bar')],
});
```

但是不要过分担心这些选择. React Loadable包括一个[Babel插件](#babel-plugin)为你添加它们. 

只需添加`react-loadable/babel`插件到您的Babel配置: 

```json
{
  "plugins": [
    "react-loadable/babel"
  ]
}
```

现在将自动提供这些选项. 

#### 找出渲染的动态模块

接下来,我们需要找出请求进入时实际呈现的模块. 

为此,有[`Loadable.Capture`](#loadablecapture)可用于收集所有已呈现模块的组件. 

```js
import Loadable from 'react-loadable';

app.get('/', (req, res) => {
  let modules = [];

  let html = ReactDOMServer.renderToString(
    <Loadable.Capture report={moduleName => modules.push(moduleName)}>
      <App/>
    </Loadable.Capture>
  );

  console.log(modules);

  res.send(`...${html}...`);
});
```

#### 将加载的模块映射到bundle

为了确保客户端加载所有在服务器端呈现的模块,我们需要将它们映射到Webpack创建的包. 

这分为两部分. 

首先,我们需要Webpack告诉我们每个模块所包含的捆绑包. 为此,有[React可加载Webpack插件](#webpack-plugin). 

导入`ReactLoadablePlugin`从`react-loadable/webpack`并将其包含在您的webpack配置中. 通过它`filename`用于存储有关我们的包的JSON数据的位置. 

```js
// webpack.config.js
import { ReactLoadablePlugin } from 'react-loadable/webpack';

export default {
  plugins: [
    new ReactLoadablePlugin({
      filename: './dist/react-loadable.json',
    }),
  ],
};
```

然后我们将回到我们的服务器并使用这些数据将我们的模块转换为bundle. 

要从模块转换为包,请导入[`getBundles`](#getbundles)方法来自`react-loadable/webpack`和来自Webpack的数据. 

```js
import Loadable from 'react-loadable';
import { getBundles } from 'react-loadable/webpack'
import stats from './dist/react-loadable.json';

app.get('/', (req, res) => {
  let modules = [];

  let html = ReactDOMServer.renderToString(
    <Loadable.Capture report={moduleName => modules.push(moduleName)}>
      <App/>
    </Loadable.Capture>
  );

  let bundles = getBundles(stats, modules);

  // ...
});
```

然后我们可以将这些包渲染成`<script>`我们的HTML中的标签. 

包括捆绑包很重要*之前*主要包,以便在应用程序呈现之前可以通过浏览器加载它们. 

但是,由于Webpack清单 (包括解析bundle的逻辑) 存在于主bundle中,因此需要将其提取到自己的块中. 

这很容易做到[CommonsChunkPlugin](https://webpack.js.org/plugins/commons-chunk-plugin/)

```js
// webpack.config.js
export default {
  plugins: [
    new webpack.optimize.CommonsChunkPlugin({
      name: 'manifest',
      minChunks: Infinity
    })
  ]
}
```

*注意: 从Webpack 4开始,CommonsChunkPlugin已被删除,并且不再需要提取清单. *

```js
let bundles = getBundles(stats, modules);

res.send(`
  <!doctype html>
  <html lang="en">
    <head>...</head>
    <body>
      <div id="app">${html}</div>
      <script src="/dist/manifest.js"></script>
      ${bundles.map(bundle => {
        return `<script src="/dist/${bundle.file}"></script>`
        // alternatively if you are using publicPath option in webpack config
        // you can use the publicPath value from bundle, e.g:
        // return `<script src="${bundle.publicPath}"></script>`
      }).join('\n')}
      <script src="/dist/main.js"></script>
    </body>
  </html>
`);
```

#### 在客户端上预加载准备好的可加载组件

我们可以使用[`Loadable.preloadReady()`](#loadablepreloadready)客户端上的方法,用于预加载页面上包含的可加载组件. 

喜欢[`Loadable.preloadAll()`](#loadablepreloadall),它会返回一个承诺,在解决方案上意味着我们可以保护我们的应用程序. 

```js
// src/entry.js
import React from 'react';
import ReactDOM from 'react-dom';
import Loadable from 'react-loadable';
import App from './components/App';

Loadable.preloadReady().then(() => {
  ReactDOM.hydrate(<App/>, document.getElementById('app'));
});
```

<h4 align="center">
  Now server-side rendering should work perfectly!
</h4>

<h2>
  <hr>
  <hr>
  <img src="http://thejameskyle.com/img/react-loadable-api-docs.png" alt="API DOCS">
  <hr>
  <hr>
  <small>API Docs</small>
</h2>

### `Loadable`

动态的高阶组件[装载](#optsloader)以前的模块[翻译](#optsrender)它,a[装载](#opts.loading)模块不可用时呈现组件. 

```js
const LoadableComponent = Loadable({
  loader: () => import('./Bar'),
  loading: Loading,
  delay: 200,
  timeout: 10000,
});
```

这会返回一个[LoadableComponent](#loadablecomponent). 

### `Loadable.Map`

允许您并行加载多个资源的高阶组件. 

Loadable.Map的[`opts.loader`](#optsloader)接受一个功能对象,需要一个[`opts.render`](#optsrender)方法. 

```js
Loadable.Map({
  loader: {
    Bar: () => import('./Bar'),
    i18n: () => fetch('./i18n/bar.json').then(res => res.json()),
  },
  render(loaded, props) {
    let Bar = loaded.Bar.default;
    let i18n = loaded.i18n;
    return <Bar {...props} i18n={i18n}/>;
  }
});
```

使用时`Loadable.Map`该`render()`方法`loaded`param将是一个与你的形状相同的对象`loader`. 

### `Loadable`和`Loadable.Map`选项

#### `opts.loader`

一个函数返回一个加载模块的promise. 

```js
Loadable({
  loader: () => import('./Bar'),
});
```

使用时[`Loadable.Map`](#loadablemap)这接受了这些类型的函数的对象. 

```js
Loadable.Map({
  loader: {
    Bar: () => import('./Bar'),
    i18n: () => fetch('./i18n/bar.json').then(res => res.json()),
  },
});
```

使用时`Loadable.Map`你还需要通过一个[`opts.render`](#optsrender)功能. 

#### `opts.loading`

一个[`LoadingComponent`](#loadingcomponent)在模块加载或错误时呈现. 

```js
Loadable({
  loading: LoadingComponent,
});
```

此选项是必需的,如果您不想渲染任何内容,请返回`null`. 

```js
Loadable({
  loading: () => null,
});
```

#### `opts.delay`

在通过之前等待的时间 (以毫秒为单位) [`props.pastDelay`](#propspastdelay)到你的[`loading`](#optsloading)零件. 默认为`200`. 

```js
Loadable({
  delay: 200
});
```

[详细了解延迟](#avoiding-flash-of-loading-component). 

#### `opts.timeout`

在通过之前等待的时间 (以毫秒为单位) [`props.timedOut`](#propstimedout)到你的[`loading`](#optsloading)零件. 默认情况下这是关闭的. 

```js
Loadable({
  timeout: 10000
});
```

[阅读有关超时的更多信息](#timing-out-when-the-loader-is-taking-too-long). 

#### `opts.render`

用于自定义已加载模块的呈现的函数. 

收到`loaded`这是解决的价值[`opts.loader`](#optsloader)和`props`哪些道具传递给了[`LoadableComponent`](#loadablecomponent). 

```js
Loadable({
  render(loaded, props) {
    let Component = loaded.default;
    return <Component {...props}/>;
  }
});
```

#### `opts.webpack`

一个可选函数,它返回一个Webpack模块ID数组,您可以使用它`require.resolveWeak`. 

```js
Loadable({
  loader: () => import('./Foo'),
  webpack: () => [require.resolveWeak('./Foo')],
});
```

这个选项可以自动化[Babel插件](#babel-plugin). 

#### `opts.modules`

包含导入模块路径的可选数组. 

```js
Loadable({
  loader: () => import('./my-component'),
  modules: ['./my-component'],
});
```

这个选项可以自动化[Babel插件](#babel-plugin). 

### `LoadableComponent`

这是返回的组件`Loadable`和`Loadable.Map`. 

```js
const LoadableComponent = Loadable({
  // ...
});
```

传递给此组件的道具将直接传递到动态加载的组件[`opts.render`](#optsrender). 

#### `LoadableComponent.preload()`

这是一个静态的方法[`LoadableComponent`](#loadablecomponent)可用于提前加载组件. 

```js
const LoadableComponent = Loadable({...});

LoadableComponent.preload();
```

这会返回一个承诺,但您应该避免等待该承诺解析以更新您的UI. 在大多数情况下,它会产生糟糕的用户体验. 

[阅读有关预加载的更多信息](#preloading). 

### `LoadingComponent`

这是您传递给的组件[`opts.loading`](#optsloading). 

```js
function LoadingComponent(props) {
  if (props.error) {
    // When the loader has errored
    return <div>Error! <button onClick={ props.retry }>Retry</button></div>;
  } else if (props.timedOut) {
    // When the loader has taken longer than the timeout
    return <div>Taking a long time... <button onClick={ props.retry }>Retry</button></div>;
  } else if (props.pastDelay) {
    // When the loader has taken longer than the delay
    return <div>Loading...</div>;
  } else {
    // When the loader has just started
    return null;
  }
}

Loading({
  loading: LoadingComponent,
});
```

[阅读有关加载组件的更多信](#creating-a-great-loading-component)

#### `props.error`

一个`Error`对象传递给[`LoadingComponent`](#loadingcomponent)当. . . 的时候[`loader`](#optsloader)失败了. 没有错误时`null`通过. 

```js
function LoadingComponent(props) {
  if (props.error) {
    return <div>Error!</div>;
  } else {
    return <div>Loading...</div>;
  }
}
```

[详细了解错误](#loading-error-states). 

#### `props.retry`

函数道具传递给[`LoadingComponent`](#loadingcomponent)当. . . 的时候[`loader`](#optsloader)失败,用于重试加载组件. 

```js
function LoadingComponent(props) {
  if (props.error) {
    return <div>Error! <button onClick={ props.retry }>Retry</button></div>;
  } else {
    return <div>Loading...</div>;
  }
}
```

[详细了解错误](#loading-error-states). 

#### `props.timedOut`

一个布尔道具传递给[`LoadingComponent`](#loadingcomponent)一套之后[`timeout`](#optstimeout). 

```js
function LoadingComponent(props) {
  if (props.timedOut) {
    return <div>Taking a long time...</div>;
  } else {
    return <div>Loading...</div>;
  }
}
```

[阅读有关超时的更多信息](#timing-out-when-the-loader-is-taking-too-long). 

#### `props.pastDelay`

一个布尔道具传递给[`LoadingComponent`](#loadingcomponent)一套之后[`delay`](#optsdelay). 

```js
function LoadingComponent(props) {
  if (props.pastDelay) {
    return <div>Loading...</div>;
  } else {
    return null;
  }
}
```

[详细了解延迟](#avoiding-flash-of-loading-component). 

### `Loadable.preloadAll()`

这将打电话给所有人[`LoadableComponent.preload`](#loadablecomponentpreload)递归方法,直到它们都被解决. 允许您在服务器等环境中预加载所有动态模块. 

```js
Loadable.preloadAll().then(() => {
  app.listen(3000, () => {
    console.log('Running on http://localhost:3000/');
  });
});
```

重要的是要注意,这需要在初始化模块时声明所有可加载组件,而不是在呈现应用程序时. 

**好: **

```js
// During module initialization...
const LoadableComponent = Loadable({...});

class MyComponent extends React.Component {
  componentDidMount() {
    // ...
  }
}
```

**坏: **

```js
// ...

class MyComponent extends React.Component {
  componentDidMount() {
    // During app render...
    const LoadableComponent = Loadable({...});
  }
}
```

> **注意: ** `Loadable.preloadAll()`如果您有多个副本,则无效`react-loadable`在你的应用程序中

[阅读有关服务器上预加载的更多信息](#preloading-all-your-loadable-components-on-the-server). 

### `Loadable.preloadReady()`

检查已在浏览器中加载的模块并调用匹配项[`LoadableComponent.preload`](#loadablecomponentpreload)方法. 

```js
Loadable.preloadReady().then(() => {
  ReactDOM.hydrate(<App/>, document.getElementById('app'));
});
```

[阅读有关客户端预加载的更多信息](#waiting-to-render-on-the-client-until-all-the-bundles-are-loaded). 

### `Loadable.Capture`

用于报告呈现哪些模块的组件. 

接受一个`report`每个人都需要的道具`moduleName`通过React Loadable呈现的. 

```js
let modules = [];

let html = ReactDOMServer.renderToString(
  <Loadable.Capture report={moduleName => modules.push(moduleName)}>
    <App/>
  </Loadable.Capture>
);

console.log(modules);
```

[阅读有关捕获渲染模块的更多信](#finding-out-which-dynamic-modules-were-rendered). 

## Babel插件

提供[`opts.webpack`](#optswebpack)和[`opts.modules`](#optsmodules)对于每个可加载的组件,需要记住许多手动工作. 

相反,您可以将Babel插件添加到您的配置中,它将为您自动执行: 

```json
{
  "plugins": ["react-loadable/babel"]
}
```

**输入**

```js
import Loadable from 'react-loadable';

const LoadableMyComponent = Loadable({
  loader: () => import('./MyComponent'),
});

const LoadableComponents = Loadable.Map({
  loader: {
    One: () => import('./One'),
    Two: () => import('./Two'),
  },
});
```

**产量**

```js
import Loadable from 'react-loadable';
import path from 'path';

const LoadableMyComponent = Loadable({
  loader: () => import('./MyComponent'),
  webpack: () => [require.resolveWeak('./MyComponent')],
  modules: [path.join(__dirname, './MyComponent')],
});

const LoadableComponents = Loadable.Map({
  loader: {
    One: () => import('./One'),
    Two: () => import('./Two'),
  },
  webpack: () => [require.resolveWeak('./One'), require.resolveWeak('./Two')],
  modules: [path.join(__dirname, './One'), path.join(__dirname, './Two')],
});
```

[阅读有关声明模块的更多信息](#declaring-which-modules-are-being-loaded). 

## Webpack插件

为了[发送正确的捆绑包](#mapping-loaded-modules-to-bundles)在渲染服务器端时,您需要React Loadable Webpack插件来为您提供模块到bundle的映射. 

```js
// webpack.config.js
import { ReactLoadablePlugin } from 'react-loadable/webpack';

export default {
  plugins: [
    new ReactLoadablePlugin({
      filename: './dist/react-loadable.json',
    }),
  ],
};
```

这将创建一个文件 (`opts.filename`) 您可以导入以将模块映射到捆绑包. 

[阅读有关将模块映射到bundle的更多信息](#mapping-loaded-modules-to-bundles). 

### `getBundles`

导出的方法`react-loadable/webpack`用于将模块转换为捆绑包. 

```js
import { getBundles } from 'react-loadable/webpack';

let bundles = getBundles(stats, modules);
```

[阅读有关将模块映射到bundle的更多信息](#mapping-loaded-modules-to-bundles). 

<h2>
  <hr>
  <hr>
  <img src="http://thejameskyle.com/img/react-loadable-faq.png" alt="FAQ">
  <hr>
  <hr>
  <small>FAQ</small>
</h2>

### 我该如何避免重复?

指定相同`loading`组件或`delay`每次使用`Loadable()`快速重复. 相反,你可以包装`Loadable`使用您自己的高阶组件 (HOC) 来设置默认选项. 

```js
import Loadable from 'react-loadable';
import Loading from './my-loading-component';

export default function MyLoadable(opts) {
  return Loadable(Object.assign({
    loading: Loading,
    delay: 200,
    timeout: 10,
  }, opts));
};
```

然后你可以指定一个`loader`当你去使用它. 

```js
import MyLoadable from './MyLoadable';

const LoadableMyComponent = MyLoadable({
  loader: () => import('./MyComponent'),
});

export default class App extends React.Component {
  render() {
    return <LoadableMyComponent/>;
  }
}
```

不幸的是,目前使用包裹的可装载休息时间[反应可装载/巴别](#babel-plugin)所以在这种情况下你必须添加所需的属性 (`modules`,`webpack`) 手动. 

```js
import MyLoadable from './MyLoadable';

const LoadableMyComponent = MyLoadable({
  loader: () => import('./MyComponent'),
  modules: ['./MyComponent'],
  webpack: () => [require.resolveWeak('./MyComponent')],
});

export default class App extends React.Component {
  render() {
    return <LoadableMyComponent/>;
  }
}
```

### 我该如何处理其他款式`.css`或源图`.map`服务器端渲染?

你打电话时[`getBundles`](#getbundles),它可能会返回除JavaScript以外的文件类型,具体取决于您的Webpack配置. 

要处理此问题,您应手动过滤到您关心的文件扩展名: 

```js
let bundles = getBundles(stats, modules);

let styles = bundles.filter(bundle => bundle.file.endsWith('.css'));
let scripts = bundles.filter(bundle => bundle.file.endsWith('.js'));

res.send(`
  <!doctype html>
  <html lang="en">
    <head>
      ...
      ${styles.map(style => {
        return `<link href="/dist/${style.file}" rel="stylesheet"/>`
      }).join('\n')}
    </head>
    <body>
      <div id="app">${html}</div>
      <script src="/dist/main.js"></script>
      ${scripts.map(script => {
        return `<script src="/dist/${script.file}"></script>`
      }).join('\n')}
    </body>
  </html>
`);
```
