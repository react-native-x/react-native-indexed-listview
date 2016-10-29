# React Native IndexedListView (remobile)
A indexed listview in chat app like contacts list

## Installation
```sh
npm install @remobile/react-native-indexed-listview --save
```

## Usage

### Example
```js
'use strict';

var React = require('react');
var ReactNative = require('react-native');
var {
    View,
    Text,
    Image,
    StyleSheet,
} = ReactNative;
var IndexedListView =  require('@remobile/react-native-indexed-listview');

module.exports = React.createClass({
    componentWillMount() {
        SplashScreen.hide();
    },
    getInitialState() {
        return {
            list: {
                'A': [
                    {name: '阿三', img:app.img.login_alipay_button},
                    {name: '阿哥', img:app.img.login_qq_button},
                    {name: '阿拉斯加', img:app.img.login_weixin_button},
                    {name: '阿星', img:app.img.login_qq_button},
                    {name: '阿杜', img:app.img.login_alipay_button},
                ],
                'B': [
                    {name: '白素贞', img:app.img.login_alipay_button},
                    {name: '白元芳', img:app.img.login_qq_button},
                    {name: '白小姐', img:app.img.login_weixin_button},
                    {name: '白达', img:app.img.login_qq_button},
                    {name: '白城', img:app.img.login_alipay_button},
                ],
                'C': [
                    {name: '陈毅', img:app.img.login_alipay_button},
                    {name: '陈东', img:app.img.login_weixin_button},
                    {name: '陈晓东', img:app.img.login_qq_button},
                    {name: '陈明', img:app.img.login_weixin_button},
                    {name: '陈都', img:app.img.login_alipay_button},
                ],
                'D': [
                    {name: '大姐', img:app.img.login_alipay_button},
                    {name: '大伯', img:app.img.login_weixin_button},
                    {name: '大家', img:app.img.login_alipay_button},
                    {name: '大哥', img:app.img.login_qq_button},
                    {name: '大大', img:app.img.login_alipay_button},
                ],
                'E': [
                    {name: '阿三', img:app.img.login_alipay_button},
                    {name: '阿哥', img:app.img.login_qq_button},
                    {name: '阿拉斯加', img:app.img.login_weixin_button},
                    {name: '阿星', img:app.img.login_qq_button},
                    {name: '阿杜', img:app.img.login_alipay_button},
                ],
                'F': [
                    {name: '白素贞', img:app.img.login_alipay_button},
                    {name: '白元芳', img:app.img.login_qq_button},
                    {name: '白小姐', img:app.img.login_weixin_button},
                    {name: '白达', img:app.img.login_qq_button},
                    {name: '白城', img:app.img.login_alipay_button},
                ],
                'G': [
                    {name: '陈毅', img:app.img.login_alipay_button},
                    {name: '陈东', img:app.img.login_weixin_button},
                    {name: '陈晓东', img:app.img.login_qq_button},
                    {name: '陈明', img:app.img.login_weixin_button},
                    {name: '陈都', img:app.img.login_alipay_button},
                ],
                'H': [
                    {name: '大姐', img:app.img.login_alipay_button},
                    {name: '大伯', img:app.img.login_weixin_button},
                    {name: '大家', img:app.img.login_alipay_button},
                    {name: '大哥', img:app.img.login_qq_button},
                    {name: '大大', img:app.img.login_alipay_button},
                ],
            },
        }
    },
    renderRow(obj, sectionID, rowID) {
        return (
            <View style={styles.row}>
                <Image
                    resizeMode='stretch'
                    source={obj.img}
                    style={styles.avatar}
                    />
                <Text sytle={styles.name}>{obj.name}</Text>
            </View>
        )
    },
    render() {
        return (
            <View style={styles.container}>
                <IndexedListView
                    list={this.state.list}
                    renderRow={this.renderRow}
                    />
            </View>
        )
    },
});

var styles = StyleSheet.create({
    container: {
        flex: 1,
        paddingTop: 24,
    },
    row: {
        paddingVertical:10,
        flexDirection: 'row',
        alignItems: 'center',
    },
    avatar: {
        height: 50,
        width: 50,
        borderRadius: 25,
        marginHorizontal: 20,
    },
    name: {
        fontSize: 16,
    }
});

```

## Screencasts

![refresh](https://github.com/remobile/react-native-indexed-listview/blob/master/screencasts/demo.gif)

#### Props
- `letters:Array [optional]` <br>
    use show AlphabetaList <br>
    default: ``` [0, 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z', 1] ```
    <br>
- `list:Object [required]` <br>
    format: {A:[...], B:[...]} <br>
- `renderRow:React.PropTypes.func.isRequired`

- `renderSectionHeader:React.PropTypes.func`
```js
    renderSectionHeader(obj, sectionID) {
        return (
            <View style={styles.section} onLayout={this.onLayout.bind(null, sectionID)}>
                <Text >{sectionID}</Text>
            </View>
        );
    },
```
- `renderSeparator:func`
```js
    renderSeparator(sectionID, rowID) {
        return (
            <View style={styles.separator} key={sectionID+'_'+rowID}/>
        );
    },
```
- `alphabetaListStyle:React.PropTypes.style`

- `letterStyle:React.PropTypes.style`
