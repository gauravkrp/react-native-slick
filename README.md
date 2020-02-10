<p align="center">
  <img alt="react-native-slick" src="http://i.imgur.com/P4cRUgD.png" width="208">
</p>

<p align="center">
  The best Slick component for React Native.
</p>

<p align="center">
  <a href="http://standardjs.com/"><img alt="JavaScript Style Guide" src="https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat-square"></a>
  <a href="https://npmjs.org/package/react-native-slick"><img alt="npm version" src="http://img.shields.io/npm/v/react-native-slick.svg?style=flat-square"></a>
  <a href="https://npmjs.org/package/react-native-slick"><img alt="npm version" src="http://img.shields.io/npm/dm/react-native-slick.svg?style=flat-square"></a>
  <a href="https://github.com/ahmed3mar/react-native-slick/pulls?q=is%3Apr+is%3Aclosed"><img alt="PR Stats" src="https://img.shields.io/issuestats/i/github/ahmed3mar/react-native-slick.svg?style=flat-square"></a>
  <a href="https://github.com/ahmed3mar/react-native-slick/issues?q=is%3Aissue+is%3Aclosed"><img alt="Issue Stats" src="https://img.shields.io/issuestats/p/github/ahmed3mar/react-native-slick.svg?style=flat-square"></a>
  <a href="https://gitter.im/ahmed3mar/react-native-slick?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge"><img alt="Join the chat" src="https://badges.gitter.im/ahmed3mar/react-native-slick.svg"></a>
</p>

# react-native-slick

## Roadmap

> see: [ROADMAP.md](ROADMAP.md)

## Changelogs

- **[v1.0.0]**
  + Fix bugs and copy updates from original repo
  + [52b7023](https://github.com/leecade/react-native-swiper/pull/483/commits/52b702346b4f43df25e669880c819c4a0c41c13e), [	61a189d](https://github.com/leecade/react-native-swiper/pull/483/commits/61a189dcd7200a7567e79a990d0729f32398785b) Update: using PropTypes from prop-types and Change View.propTypes to ViewPropTypes (@thanks [@ahmed3mar](https://github.com/ahmed3mar)).
  + [84840b3](https://github.com/leecade/react-native-swiper/pull/485/commits/84840b353d8f98b493a4640bf83e02e3727f6f85) Update README.md - fix links image readme (@thanks [@Eric013](https://github.com/Eric013)).
  + [react-natie-swiper](https://github.com/leecade/react-native-swiper) Fork original repository and change name to react-native-slick.


> see more: [CHANGELOG.md](CHANGELOG.md)

## Show Cases

> Try these cases by yourself very easy, Just open `examples/ios/slick.xcodeproj` in Xcode, then press `Cmd + R`; you may edit `examples/index.ios.js` for switch cases.

### [examples/components/Basic](https://github.com/ahmed3mar/react-native-slick/blob/master/examples/components/Basic)

![](http://i.imgur.com/zrsazAG.gif=300x)

### [examples/components/Slick](https://github.com/ahmed3mar/react-native-slick/blob/master/examples/components/Slick)

![](http://i.imgur.com/hP3f3oO.gif=300x)

### [examples/components/SlickNumber](https://github.com/ahmed3mar/react-native-slick/blob/master/examples/components/SlickNumber)

![](http://i.imgur.com/0rqESVb.gif=300x)

### [examples/components/Phone](https://github.com/ahmed3mar/react-native-slick/blob/master/examples/components/Phone)

![](http://i.imgur.com/c1BhjZm.gif=300x)

### [examples/components/LoadMinimal](https://github.com/ahmed3mar/react-native-slick/blob/master/examples/components/LoadMinimal)

![](http://i.imgur.com/LAOHbJA.gif=300x)

### [examples/components/PhotoView](https://github.com/ahmed3mar/react-native-slick/blob/master/examples/components/PhotoView)

![](http://i.imgur.com/GkIRzjO.gif=300x)

> with [react-native-photo-view](https://github.com/alwx/react-native-photo-view)

## Getting Started

- [Installation](#installation)
- [Basic Usage](#basic-usage)
- [Properties](#properties)
  + [Basic](#basic)
  + [Custom basic style & content](#custom-basic-style--content)
  + [Pagination](#pagination)
  + [Autoplay](#autoplay)
  + [Control buttons](#control-buttons)
  + [Props of Children](#props-of-children)
  + [Basic props of `<ScrollView />`](#basic-props-of-scrollview-)
  + [Supported ScrollResponder](#supported-scrollresponder)
- [Examples](#examples)
- [Development](#development)

### Installation

```bash
$ npm i react-native-slick --save
```

### Basic Usage

- Install `react-native` first

```bash
$ npm i react-native -g
```

- Initialization of a react-native project

```bash
$ react-native init AwsomeProject
```

- Then, edit `AwsomeProject/index.ios.js`, like this:

```jsx
import React, { Component } from 'react';
import {
  AppRegistry,
  StyleSheet,
  Text,
  View
} from 'react-native';

import Slick from 'react-native-slick';

var styles = StyleSheet.create({
  wrapper: {
  },
  slide1: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#9DD6EB',
  },
  slide2: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#97CAE5',
  },
  slide3: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#92BBD9',
  },
  text: {
    color: '#fff',
    fontSize: 30,
    fontWeight: 'bold',
  }
})

var slick = React.createClass({
  render: function() {
    return (
      <Slick style={styles.wrapper} showsButtons={true}>
        <View style={styles.slide1}>
          <Text style={styles.text}>Hello Slick</Text>
        </View>
        <View style={styles.slide2}>
          <Text style={styles.text}>Beautiful</Text>
        </View>
        <View style={styles.slide3}>
          <Text style={styles.text}>And simple</Text>
        </View>
      </Slick>
    )
  }
})

AppRegistry.registerComponent('AwsomeProject', () => slick);
```

### Properties

#### Basic

| Prop  | Default  | Type | Description |
| :------------ |:---------------:| :---------------:| :-----|
| horizontal | true | `bool` | If `true`, the scroll view's children are arranged horizontally in a row instead of vertically in a column. |
| loop | true | `bool` | Set to `false` to disable continuous loop mode. |
| index | 0 | `number` | Index number of initial slide. |
| showsButtons | false | `bool` | Set to `true` make control buttons visible. |
| autoplay | false | `bool` | Set to `true` enable auto play mode. |

#### Custom basic style & content

| Prop  | Default  | Type | Description |
| :------------ |:---------------:| :---------------:| :-----|
| width | - | `number` | If no specify default enable fullscreen mode by `flex: 1`. |
| height | - | `number` | If no specify default fullscreen mode by `flex: 1`. |
| style | {...} | `style` | See default style in source. |
| loadMinimal | false | `bool` | Only load current index slide , `loadMinimalSize` slides before and after. |
| loadMinimalSize | 1 | `number` | see `loadMinimal`   |
| loadMinimalLoader | `<ActivityIndicator />` | `element` | Custom loader to display when slides aren't loaded

#### Pagination

| Prop  | Default  | Type | Description |
| :------------ |:---------------:| :---------------:| :-----|
| showsPagination | true | `bool` | Set to `true` make pagination visible. |
| paginationStyle | {...} | `style` | Custom styles will merge with the default styles. |
| renderPagination | - | `function` | Complete control how to render pagination with three params (`index`, `total`, `context`) ref to `this.state.index` / `this.state.total` / `this`, For example: show numbers instead of dots. |
| dot | `<View style={{backgroundColor:'rgba(0,0,0,.2)', width: 8, height: 8,borderRadius: 4, marginLeft: 3, marginRight: 3, marginTop: 3, marginBottom: 3,}} />` | `element` | Allow custom the dot element. |
| activeDot | `<View style={{backgroundColor: '#007aff', width: 8, height: 8, borderRadius: 4, marginLeft: 3, marginRight: 3, marginTop: 3, marginBottom: 3,}} />` | `element` | Allow custom the active-dot element. |
| dotStyle | - | `object` | Allow custom the active-dot element. |
| dotColor | - | `string` | Allow custom the active-dot element. |
| activeDotColor | - | `string` | Allow custom the active-dot element. |
| activeDotStyle | - | `object` | Allow custom the active-dot element. |

#### Autoplay

| Prop  | Default  | Type | Description |
| :------------ |:---------------:| :---------------:| :-----|
| autoplay | true | `bool` | Set to `true` enable auto play mode. |
| autoplayTimeout | 2.5 | `number` | Delay between auto play transitions (in second). |
| autoplayDirection | true | `bool` | Cycle direction control. |

#### Control buttons

| Prop  | Default  | Type | Description |
| :------------ |:---------------:| :---------------:| :-----|
| showsButtons | true | `bool` | Set to `true` make control buttons visible. |
| buttonWrapperStyle | `{backgroundColor: 'transparent', flexDirection: 'row', position: 'absolute', top: 0, left: 0, flex: 1, paddingHorizontal: 10, paddingVertical: 10, justifyContent: 'space-between', alignItems: 'center'}` | `style` | Custom styles. |
| nextButton | `<Text style={styles.buttonText}>›</Text>` | `element` | Allow custom the next button. |
| prevButton | `<Text style={styles.buttonText}>‹</Text>` | `element` | Allow custom the prev button. |

#### Props of Children

| Prop  | Default  | Type | Description |
| :------------ |:---------------:| :---------------:| :-----|
| style | {...} | `style` | Custom styles will merge with the default styles. |
| title | {<Text numberOfLines={1}>...</Text>} | `element` | If this parameter is not specified, will not render the title. |

#### Basic props of `<ScrollView />`

| Prop  | Default  | Type | Description |
| :------------ |:---------------:| :---------------:| :-----|
| horizontal | true | `bool` | If `true`, the scroll view's children are arranged horizontally in a row instead of vertically in a column. |
| pagingEnabled | true | `bool` | If true, the scroll view stops on multiples of the scroll view's size when scrolling. This can be used for horizontal pagination.  |
| showsHorizontalScrollIndicator | false | `bool` | Set to `true` if you want to show horizontal scroll bar. |
| showsVerticalScrollIndicator | false | `bool` |  Set to `true` if you want to show vertical scroll bar. |
| bounces | false | `bool` | If `true`, the scroll view bounces when it reaches the end of the content if the content is larger then the scroll view along the axis of the scroll direction. If `false`, it disables all bouncing even if the alwaysBounce* props are true.  |
| scrollsToTop | false | `bool` | If true, the scroll view scrolls to top when the status bar is tapped.  |
| removeClippedSubviews | true | `bool` | If true, offscreen child views (whose overflow value is hidden) are removed from their native backing superview when offscreen. This canimprove scrolling performance on long lists.  |
| automaticallyAdjustContentInsets | false | `bool` | Set to `true` if you need adjust content insets automation. |
| scrollEnabled | true | `bool` | Enables/Disables swiping |

> @see: http://facebook.github.io/react-native/docs/scrollview.html

#### Supported ScrollResponder

| Prop  | Params  | Type | Description |
| :------------ |:---------------:| :---------------:| :-----|
| onScrollBeginDrag | `e` / `state` / `context` | `function` | When animation begins after letting up |
| onMomentumScrollEnd | `e` / `state` / `context` | `function` | Makes no sense why this occurs first during bounce |
| onTouchStartCapture | `e` / `state` / `context` | `function` | Immediately after `onMomentumScrollEnd` |
| onTouchStart | `e` / `state` / `context` | `function` | Same, but bubble phase |
| onTouchEnd | `e` / `state` / `context` | `function` | You could hold the touch start for a long time |
| onResponderRelease | `e` / `state` / `context` | `function` | When lifting up - you could pause forever before * lifting |

> Note: each ScrollResponder be injected with two params: `state` and `context`, you can get `state` and `context`(ref to slick's `this`) from params, for example:

```jsx
var slick = React.createClass({
  _onMomentumScrollEnd: function (e, state, context) {
    console.log(state, context.state)
  },
  render: function() {
    return (
      <Slick style={styles.wrapper}
      onMomentumScrollEnd ={this._onMomentumScrollEnd}
     ...
      </Slick>
    )
  }
})
```

> More ScrollResponder info, see: https://github.com/facebook/react-native/blob/master/Libraries/Components/ScrollResponder.js

### Methods

#### scrollBy(index, animated)

Scroll by relative index.

Parameters:

| Name  | Type     | default | Description |
| :---- | :------: | :------: | :--- |
| index | `number`   | `undefined` | offset index |
| animated | `bool`   | `true` | offset index |

### Examples

```bash
$ cd examples
$ npm i
$ react-native run-ios
```

> Quick start with [examples](https://github.com/ahmed3mar/react-native-slick/tree/master/examples/).

### Development

```bash
$ cd examples
$ npm i
$ npm run dev
$ react-native run-ios
```

Then launch simulator to preview. Note that you just need to edit the source file `src/index.js`, the change will auto sync to examples.

And now that this project follows the [standard](https://github.com/feross/standard) code style, you'd better prepare it for IDE.

## Contribution

- [@leecade](mailto:leecade@163.com) The main author.
- [@rajkissu](mailto:rajkissu@gmail.com) The secondary contributor.
- [@ahmed3mar](mailto:ahmed3mar@outlook.com).
- [@gauravkrp](mailto:gaurav.golu1@gmail.com).

## Questions

Feel free to [contact me](mailto:gaurav.golu1@gmail.com) or [create an issue](https://github.com/gauravkrp/react-native-slick/issues/new)

> Inspired by [nolimits4web/Slick](https://github.com/nolimits4web/swiper/) & Design material from [Dribbble](https://dribbble.com/) & made with ♥.
