---
order: 0
title: Ant Design of React
---

antd is a set of React components which follow Ant Design specification. It is designed to develop RIA sucn as dashboard to serve enterprise.

<div class="pic-plus">
  <img width="150" src="https://t.alipayobjects.com/images/rmsweb/T11aVgXc4eXXXXXXXX.svg">
  <span>+</span>
  <img width="160" src="https://t.alipayobjects.com/images/rmsweb/T16xRhXkxbXXXXXXXX.svg">
</div>

<style>
.pic-plus > * {
  display: inline-block!important;
  vertical-align: middle;
}
.pic-plus span {
  font-size: 30px;
  color: #aaa;
  margin: 0 20px;
}
</style>

---

## Features

- Designed as Ant Design, a design language to create user friendly and beautiful websites.
- It is a set of high quality UI components and based on [React Component](http://react-component.github.io/badgeboard/).
- Provide a work flow which is based on npm and webpack and babel, it supports ES2015 and TypeScript.

## Installation

```bash
$ npm install antd
```

## Example

```jsx
import { DatePicker } from 'antd';
ReactDOM.render(<DatePicker />, mountNode);
```

Import style:

```jsx
import 'antd/dist/antd.css';  // or 'antd/dist/antd.less'
```

You can use `import DatePicker from 'antd/lib/date-picker'` or [babel-plugin-antd](https://github.com/ant-design/babel-plugin-antd)(This plugin supports import component and styles on demand) to import components on demand.

## Version

- Stable: [![npm package](http://img.shields.io/npm/v/antd.svg?style=flat-square)](https://www.npmjs.org/package/antd)
- Beta: [![](https://cnpmjs.org/badge/v/antd.svg?&tag=beta&subject=npm)](https://www.npmjs.org/package/antd)

## Compatibility

Modern browsers and IE8+.

> [IE8 issues](https://github.com/xcatliu/react-ie8)

## Useful Links

- [Home Page](http://ant.design/)
- [Changelog](/changelog)
- [Scaffold](https://github.com/ant-design/antd-init/)
- [Develop Tools](http://ant-tool.github.io/)
- [React Component](http://react-component.github.io/)
- [Ant Design Mobile](http://mobile.ant.design)
- [React Code Style](https://github.com/react-component/react-component.github.io/blob/master/docs/zh-cn/component-code-style.md)
- [Design Principle of Component](https://github.com/react-component/react-component.github.io/blob/master/docs/zh-cn/component-design.md)
- [Design Handbook](https://os.alipayobjects.com/rmsportal/HTXUgPGkyyxEivE.png)
- [Scaffold and Demo Supported by Community](https://github.com/ant-design/ant-design/issues/129)

## Who are using antd

- Ant Financial
- Alibaba
- Koubei
- China Internet Plus
- Didi

> If your company or product has use Ant Design, it's welcomed to comment in [this issue]((https://github.com/ant-design/ant-design/issues/477)).

## Contributing

Please read our [CONTRIBUTING.md](https://github.com/ant-design/ant-design/blob/master/.github/CONTRIBUTING.md) first.

If you have any idea to improve antd, just create a [Pull Request](https://github.com/ant-design/ant-design/pulls). Also, you can report bug by [issue](https://github.com/ant-design/ant-design/issues/new) or [ask questions](https://github.com/ant-design/ant-design/issues)。

> Recommend to read [*How To Ask Questions The Smart Way*](http://www.catb.org/~esr/faqs/smart-questions.html) and [How to Ask a Question in Open Source Community](https://github.com/seajs/seajs/issues/545) and [How to Report Bugs Effectively](http://www.chiark.greenend.org.uk/~sgtatham/bugs.html), a smart question will get right answer quickly.
