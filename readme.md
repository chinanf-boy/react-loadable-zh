![React Loadable](http://thejameskyle.com/img/react-loadable-header.png)

[![translate-svg]][translate-list]

组件的动态导入与加载 的 高级组件

> 如果你听过 路由控制 动态导入组件(基于路由的分割),那么这个库就是高级组件控制的(基于组件的分割)

[translate-svg]: http://llever.com/translate.svg
[translate-list]: https://github.com/chinanf-boy/chinese-translate-list


---

## 校对✔

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

## 例子

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

-   ["我现在对此很着迷: CRA使用React Router v4 和 react-loadable. 免费代码分割,太方便了."](https://twitter.com/matzatorski/status/872059865350406144)
-   ["Webpack 2升级 和 react-loadable; 在2小时内 初始负载从 1.1mb到529kb. 提升很大. "](https://twitter.com/jwbradley87/status/847191118269833216)
-   ["哦,嘿 - 使用react-loadable,我在初始负载下降了13K. 轻松获胜!"](https://twitter.com/AdamRackis/status/846593080992153600)
-   ["看了一眼就看起来很棒了. 在我们的主捆绑包上刮去了50kb. "](https://github.com/quran/quran.com-frontend/pull/701#issuecomment-287908551)
-   ["我已经完成了 服务器端渲染+代码分割+ PWA ServiceWorker缓存设置 😎 (感谢react-loadable) . 现在我们的前端非常快. "](https://twitter.com/mxstbr/status/922375575217627136)
-   ["使用react-loadable, 从 221.28 KB→115.76 KB @ main bundle. TMD非常棒且非常简单. "](https://twitter.com/evgenyrodionov/status/958821614644269057)

## 用户

- [Analog.Cafe](https://www.analog.cafe)
- [Appbase.io](https://github.com/appbaseio/reactivesearch)
- [Atlassian](https://www.atlassian.com/)
- [Cloudflare](https://www.cloudflare.com)
- [Curio](https://www.curio.org)
- [Dresez](https://dresez.pk/)
- [Flyhomes](https://flyhomes.com)
- [Gogo](https://gogoair.com)
- [MediaTek MCS-Lite](https://github.com/MCS-Lite)
- [Render](https://render.com)
- [Snipit](https://snipit.io)
- [Spectrum.chat](https://spectrum.chat)
- [Talentpair](https://talentpair.com)
- [Tinder](https://tinder.com/)
- [Unsplash](https://unsplash.com/)
- [Wave](https://waveapps.com/)

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

是时候开始拆分您应用的代码了!

![A single giant bundle vs multiple smaller bundles](http://thejameskyle.com/img/react-loadable-split-bundles.png)

代码分割是一个 包含整个应用程序的大型捆绑包,并将它们拆分为多个较小的捆绑包,其中包含应用程序的不同部分. 

这似乎很难做到,但像Webpack这样的工具内置了这个工具,而React Loadable旨在使其变得非常简单. 

### 基于路由的分割 vs 基于组件的分割

你会遇到的一个常规建议是把你的应用分成多个路由，然后一个个异步加载。这种方式似乎对大多数应用有作用，点击一个链接然后加载一页新的页面并不是一个太差的体验。

但是我们可以做得比这个更好。

React 的大多数路由工具都是一个简单的组件。没有什么特别的. (对不起莱恩和迈克尔 - 你有什么特别之处) . 那么如果我们针对组件而不是路由进行优化来进行优化呢?那会让我们得到什么?
（指在组件层动态优化而不是传统的动态加载路由）

![Route vs. component centric code splitting](http://thejameskyle.com/img/react-loadable-component-splitting.png)

（上图可以看到，路由分割的粒度还是比较大，一个路由就是一条系列组件，而组件的分割更细，在路由里还可以细分

事实证明: 相当多. 
除了路由之外,还有很多地方可以轻松拆分您的应用. 模式,选项卡和更多UI组件隐藏内容,直到用户完成某些操作才能显示它.

> **例:** 也许你的应用程序有一个埋在 选项卡组件 内的地图. 每当用户可能又或者永远不会访问该选项卡时,为什么要为父路由加载大量地图库? 

更别提其他所有在更高优先级内容加载完成后才会延迟加载的部分。例如在你的页面最底部有的组件需要加载一堆包（虽然组件本身可能不大，但是这些底部组件可能引入一些很大的第三方包）：为什么这些需要和顶部的组件一起加载呢？

你也可以继续轻松地分割路由，因为路由也仅仅是组件而已。怎么对你的应用最好怎么做。

但是我们需要使在组件层面分割和路由层面分割一样容易。分割一块新位置应该简单到改变应用的几行代码一样容易，其他剩余的工作应该是自动化的。

### 介绍React Loadable

React Loadable是一个小型库,它使得 以组件为中心 的代码在React中非常容易分割. 

`Loadable`是一个高阶组件 (一个创建组件的函数) ,它允许您在将 任何模块渲染到应用程序之前 动态加载它. 

让我们设想两个组件,导入一个组件和渲染另一个组件. 

```js
import Bar from './components/Bar';

class Foo extends React.Component {
  render() {
    return <Bar/>;
  }
}
```

现在我们依赖于`Bar`意味着通过`import`导入同步,但是在我们去渲染它之前我们不需要它. 那么我们为什么不推迟呢?

用一个**动态导入** ([目前处于第3阶段的tc39提案](https://github.com/tc39/proposal-dynamic-import)) 我们可以修改我们的组件来异步加载`Bar`. 

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

然而，这种方式有很多手动工作，而且它并不能处理很多不同的场景。例如如果 import() 失败怎么办？服务器端渲染怎么处理？

你可以使用 Loadable 来抽象地解决这个问题. 使用 Loadable 很简单。所有你需要做的就是**传入一个加载组件的函数**，和一个当你的组件在加载时提示用户来**占位显示 “Loading” 状态的组件**。

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

### `import()`的自动代码分割

关于 `import()` 最好的事情就是 Webpack 2 能够在你引入了一个新的模块之后为你[自动进行代码分割](https://webpack.js.org/guides/code-splitting/)，而不需要任何额外的工作。

这意味只需要通过切换到 `import()` 并使用 React Loadable，你可以很容易实验新的代码分割点，来弄清楚在你的应用上怎么处理表现最好。

### 创建一个伟大的"Loading..."组件

渲染静态"正在加载..."并不能说明什么. 您还需要考虑错误状态,超时 并使其成为一种不错的体验. 

```js
function Loading() {
  return <div>Loading...</div>;
}

Loadable({
  loader: () => import('./WillFailToLoad'), // oh no!
  loading: Loading,
});
```

为了让这一切变得美好,你的[加载组件](#loadingcomponent)会收到几个不同的`props`. 

#### 加载错误状态

当你的[`loader`](optsloader)失败,你的[加载组件](#loadingcomponent)会收到一个[`error`](propserror)来自`props`,将是一个`Error`对象 (否则它将是`null`) . 

```js
function Loading(props) {
  if (props.error) {
    return <div>Error! <button onClick={ props.retry }>Retry</button></div>;
  } else {
    return <div>Loading...</div>;
  }
}
```

#### 避免加载组件时的闪烁

有时组件加载非常快，小于 200ms，提示加载的组件会在界面上一闪而过.

一些用户调研表明这会导致用户感知事情发生（组件加载）的时间比真实的更长。如果你什么都不显示，那么用户对加载的感知反而觉得更快.

所以你的 loading 组件（就是在真正要用的组件加载完成之前显示的提示组件）有一个[`pastDelay`props](#propspastdelay)，只有在真正用到的组件花了比设定的 delay更长的时间加载的时候，[delay延迟](#optsdelay)才会是 true （才会显示提示的 loading 组件）.


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

delay 的默认值是 `200ms`，但你也可以使用第三个参数来设置[延迟](#optsdelay)时长. 

```js
Loadable({
  loader: () => import('./components/Bar'),
  loading: Loading,
  delay: 300, // 0.3 seconds
});
```

#### 超时`loader`花了太长时间

有时网络连接很糟糕,永远不会解决或失败,它们只是永远挂在那里. 这对用户来说很糟糕,因为他们不知道是不总是花这么长时间,或者他们应该尝试刷新. 

该[加载组件](#loadingcomponent)会收到一个[`timedOut`prop](#propstimedout)将被设置为`true`, 当[`loader`](#optsloader)已经超时了的时候. 

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

但是,默认情况下禁用此功能. 要打开它,你可以传递一个[`timeout`选项](#optstimeout)给`Loadable`. 

```js
Loadable({
  loader: () => import('./components/Bar'),
  loading: Loading,
  timeout: 10000, // 10 seconds
});
```

### 自定义渲染

默认`Loadable`将渲染`default`导出模块. 如果要自定义此行为,可以使用[`render`选项](#optsrender). 

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

从技术上讲,你可以使用`loader()`做任何你想做的事,只要它返回一个Promise和[你能够渲染一些东西](#customizing-rendering). 但写出来可能有点烦人. 

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

使用`Loadable.Map`时,[`render()`方法](#optsrender)是必须的. 它将通过一个`loaded`参数传入`loader`形状的对象. 

### 预加载

作为一种优化手段，你也可以在一个组件被渲染之前预加载它。

例如，如果你需要一个按钮被点击时加载一个新的组件，你可以在这个用户把鼠标 hover 到这个按钮之上时就开始预加载这个组件。

被 Loadable 构建的组件会开放一个[ preload 静态方法](#loadablecomponentpreload)刚好做到这点（指预加载）。


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
  <small>服务端渲染</small>
</h2>

当你去渲染所有这些动态加载的组件时,你会得到的是屏幕上一大堆加载. 

这真的很糟糕,但好消息是 React Loadable 旨在使服务器端渲染好好工作,就好像没有动态加载任何内容. 

这是使用[Express](https://expressjs.com/)的启动服务器. 

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

### 在服务器上预加载所有loadable组件

第一步是:从服务器渲染正确内容,确保在您渲染它们时已经加载了所有可加载组件. 

为此,您可以使用[`Loadable.preloadAll`](#loadablepreloadall)方法. 它返回一个Promise,该Promise将在所有可加载组件准备就绪后`resolve`. 

```js
Loadable.preloadAll().then(() => {
  app.listen(3000, () => {
    console.log('Running on http://localhost:3000/');
  });
});
```

### 在客户端上准备服务器端渲染的应用程序

这是事情变得有点棘手的地方. 所以让我们做好准备吧. 

为了让我们获取从服务器渲染的内容,我们需要拥有于服务器上相同的渲染代码. 

为此,我们首先需要可加载的组件来告诉我们它们正在渲染哪些模块. 

#### 声明正在加载哪些模块

有两种选择:[`Loadable`](#loadable)和[`Loadable.Map`](#loadablemap)用于告诉我们组件尝试加载哪些模块: [`opts.modules`](#optsmodules)和[`opts.webpack`](#optswebpack). 

```js
Loadable({
  loader: () => import('./Bar'),
  modules: ['./Bar'],
  webpack: () => [require.resolveWeak('./Bar')],
});
```

但是不要过分担心这些选项. React Loadable含有一个[Babel插件](#babel-plugin), 会为你添加它们. 

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

接下来,我们需要找出请求时,实际渲染的模块. 

为此,有[`Loadable.Capture`](#loadablecapture)可用于收集所有已渲染模块的组件. 

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

#### 将加载的模块映射到捆绑器

为了确保客户端加载,所有在服务器端渲染的模块,我们需要将它们映射到Webpack创建的包. 

这分为两部分. 

首先,我们需要Webpack告诉我们每个模块所包含的捆绑包. 为此,有[React可加载Webpack插件](#webpack-plugin). 

从`react-loadable/webpack`导入`ReactLoadablePlugin`,并将其包含在您的webpack配置中. 它通过`filename`存储有关包位置的JSON数据. 

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

然后我们将回到我们的服务器,并使用这些数据将我们的模块并入捆绑. 

要将模块并入捆绑,请导入[`getBundles`](#getbundles)方法,它来自`react-loadable/webpack`和Webpack的数据. 

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

然后我们可以将这些包渲染成`<script>`标签. 

很重要的是: 捆绑包包括*之前*的主要捆绑文件,以便在应用程序渲染之前通过浏览器加载它们. 

但是,由于Webpack清单 (具有解析bundle的逻辑) 存在于主bundle中,因此需要将其提取到自己的块中. 

这很容易做到,就是通过使用[CommonsChunkPlugin](https://webpack.js.org/plugins/commons-chunk-plugin/)

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

*注意: 从Webpack 4开始,`CommonsChunkPlugin`已被删除,并且不再需要提取清单. *

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
        // 或者 如果你使用了 publicPath 在 webpack 配置中
        // 你可以使用 捆绑中的 publicPath 值, 例如:
        // 返回 `<script src="${bundle.publicPath}"></script>`
      }).join('\n')}
      <script src="/dist/main.js"></script>
    </body>
  </html>
`);
```

#### 在客户端上预加载准备好的可加载组件

我们可以使用[`Loadable.preloadReady()`](#loadablepreloadready)- 客户端上的方法,用于预加载页面上包含的可加载组件. 

类似[`Loadable.preloadAll()`](#loadablepreloadall),它会返回一个Promise,在`then`上我们可以`hydrate`我们的应用程序. 

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
  现在 服务端渲染完美工作!
</h4>

<h2>
  <hr>
  <hr>
  <img src="http://thejameskyle.com/img/react-loadable-api-docs.png" alt="API DOCS">
  <hr>
  <hr>
  <small>API 文档</small>
</h2>

### `Loadable`

[渲染](#optsrender)模块之前动态[加载](#optsloader)模块的高阶组件,一个[loading](#opts.loading)组件在模块不可用时会被渲染. 

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

Loadable.Map的[`opts.loader`](#optsloader)接受一个函数组成的对象,和需要一个[`opts.render`](#optsrender)方法. 

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

使用`Loadable.Map`的`render()`方法`,它的`loaded`参数与你的`loader`对象形状相同.

### `Loadable`和`Loadable.Map`选项

#### `opts.loader`

一个函数返回一个加载模块的promise. 

```js
Loadable({
  loader: () => import('./Bar'),
});
```

使用[`Loadable.Map`](#loadablemap)时,这接受了这种类型函数组成的对象. 

```js
Loadable.Map({
  loader: {
    Bar: () => import('./Bar'),
    i18n: () => fetch('./i18n/bar.json').then(res => res.json()),
  },
});
```

使用`Loadable.Map`时,你还需要给予一个[`opts.render`](#optsrender)函数. 

#### `opts.loading`

一个[`LoadingComponent`](#loadingcomponent)会在模块加载或错误时 渲染. 

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

在传递[`props.pastDelay`](#propspastdelay)到你的[`loading`](#optsloading)组件(上面的),用来运行之前等待的时间 (以毫秒为单位). 默认为`200`. 

```js
Loadable({
  delay: 200
});
```

[详细了解延迟](#avoiding-flash-of-loading-component). 

#### `opts.timeout`

在传递[`props.timedOut`](#propstimedout)到你的[`loading`](#optsloading)组件,用来启动之前等待的时间 (以毫秒为单位) . 默认情况下超时是关闭的. 

```js
Loadable({
  timeout: 10000
});
```

[阅读有关超时的更多信息](#timing-out-when-the-loader-is-taking-too-long). 

#### `opts.render`

用于自定义*loading*模块的渲染函数. 

参数`loaded`是来自[`opts.loader`](#optsloader)和`props`,是传递给了[`LoadableComponent`](#loadablecomponent). 

```js
Loadable({
  render(loaded, props) {
    let Component = loaded.default;
    return <Component {...props}/>;
  }
});
```

#### `opts.webpack`

一个可选函数,它返回一个Webpack模块ID的数组,通过使用`require.resolveWeak`. 

```js
Loadable({
  loader: () => import('./Foo'),
  webpack: () => [require.resolveWeak('./Foo')],
});
```

使用[Babel插件](#babel-plugin),这个选项能自动化了. 

#### `opts.modules`

包含导入模块路径的可选数组. 

```js
Loadable({
  loader: () => import('./my-component'),
  modules: ['./my-component'],
});
```

使用[Babel插件](#babel-plugin),这个选项能自动化了. 

### `LoadableComponent`

这是`Loadable`和`Loadable.Map`返回的组件. 

```js
const LoadableComponent = Loadable({
  // ...
});
```

传递给此`LoadableComponent`组件的`props`,将直接传递到动态加载的渲染函数[`opts.render`](#optsrender). 

#### `LoadableComponent.preload()`

这是一个[`LoadableComponent`](#loadablecomponent)的静态方法,可用于提前加载组件. 

```js
const LoadableComponent = Loadable({...});

LoadableComponent.preload();
```

这会返回一个Promise,但您应该避免等待该Promise`then`,以更新您的UI. 在大多数情况下,它会产生糟糕的用户体验. 

[阅读有关预加载的更多信息](#preloading). 

### `LoadingComponent`

这是您传递给[`opts.loading`](#optsloading)的函数. 

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

一个`Error`对象传递给[`LoadingComponent`](#loadingcomponent)当[`loader`](#optsloader)失败了的时候. 没有错误时`null`通过. 

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

[`LoadingComponent`](#loadingcomponent)函数参数`props`的`retry`字段,当[`loader`](#optsloader)失败的时候,用于重试加载组件. 

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

props 的一个布尔值,在超时[`timeout`](#optstimeout)之后,传递给[`LoadingComponent`](#loadingcomponent)函数. 

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

props 的一个布尔值, 在延迟[`delay`](#optsdelay)之后,传递给[`LoadingComponent`](#loadingcomponent)函数. 

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

这将递归运行所有的[`LoadableComponent.preload`](#loadablecomponentpreload)方法,直到它们都被解决. 允许您 在服务器等 环境中预加载所有动态模块. 

```js
Loadable.preloadAll().then(() => {
  app.listen(3000, () => {
    console.log('Running on http://localhost:3000/');
  });
});
```

需要着重注意的是, 应该 在初始化模块时 就声明所有可加载组件,而不是在渲染应用程序时. 

**好:**

```js
// 模块初始化期间...
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
    // 应用渲染期间...
    const LoadableComponent = Loadable({...});
  }
}
```

> **注意:** 在你的应用程序使用`react-loadable`的情况下,如果您有多个`Loadable.preloadAll()`副本,这函数将不会工作

[阅读有关服务器上预加载的更多信息](#preloading-all-your-loadable-components-on-the-server). 

### `Loadable.preloadReady()`

检查已在浏览器中加载的模块 和 调用对应的[`LoadableComponent.preload`](#loadablecomponentpreload)方法. 

```js
Loadable.preloadReady().then(() => {
  ReactDOM.hydrate(<App/>, document.getElementById('app'));
});
```

[阅读有关客户端预加载的更多信息](#waiting-to-render-on-the-client-until-all-the-bundles-are-loaded). 

### `Loadable.Capture`

用于报告渲染哪些模块的组件. 

它接受 props 的一个`report`函数,其中渲染的`moduleName`由 React Loadable 提供的. 

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

算然提供[`opts.webpack`](#optswebpack)和[`opts.modules`](#optsmodules),来配置对于每个可加载的组件,但这需要记住许多手动工作. 

而Babel插件不同,您可以将Babel插件添加到您的配置中,它将为您自动执行: 

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

**输出**

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

[阅读有关声明加载模块的更多信息](#declaring-which-modules-are-being-loaded). 

## Webpack插件

为了在渲染服务器端时[发送正确的捆绑包](#mapping-loaded-modules-to-bundles),您需要React Loadable 的 Webpack插件来为您提供 模块到捆绑包 的映射. 

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

这将创建一个文件 (`opts.filename`) ,您可以将模块映射到捆绑包. 

[阅读有关将 模块 映射到捆绑包 的更多信息](#mapping-loaded-modules-to-bundles). 

### `getBundles`

`react-loadable/webpack`导出的方法,用于将模块转换为捆绑包. 

```js
import { getBundles } from 'react-loadable/webpack';

let bundles = getBundles(stats, modules);
```

[阅读有关将 模块 映射到捆绑包 的更多信息](#mapping-loaded-modules-to-bundles). 

<h2>
  <hr>
  <hr>
  <img src="http://thejameskyle.com/img/react-loadable-faq.png" alt="FAQ">
  <hr>
  <hr>
  <small>FAQ</small>
</h2>

### 我该如何避免重复?

指定相同`loading`组件或`Loadable()`设定相同的`delay`快速重复. 那么其实,你可以包装`Loadable`使用您自己的高阶组件 (HOC) 来设置默认选项. 

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

然后当你去使用它，你可以指定一个`loader`. 

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

不幸的是,目前使用(上述的)可加载的高级组件, 会破坏[react-loadable/babel](#babel-plugin)工作, 所以在这种情况下,你必须手动添加所需的属性 (`modules`,`webpack`) . 

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

### 我该如何处理其他`.css`文件或服务器端渲染中的`.map`文件?

当你使用[`getBundles`](#getbundles),它可能会返回 除JavaScript以外 的文件类型,具体取决于您的Webpack配置. 

要处理此问题,您应手动过滤,您关心的文件扩展名: 

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
