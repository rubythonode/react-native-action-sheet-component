## React Native Action Sheet Component
React Native Action Sheet Component for iOS & Android.

Pull request are welcomed. Please follow the Airbnb style guide [Airbnb JavaScript](https://github.com/airbnb/javascript)

[Try it with Exponent](https://exp.host/@jacklam718/action-sheet-example)

#### Preview
<img src="https://raw.githubusercontent.com/jacklam718/react-native-action-sheet-component/master/.github/action-sheet.gif" width="300">
<img src="https://raw.githubusercontent.com/jacklam718/react-native-action-sheet-component/master/.github/action-sheet.png" width="300">


## Installation
##### yarn
`yarn add react-native-action-sheet-component`
##### npm
`npm install --save react-native-action-sheet-component`


## Usage with `ActionSheet`
```javascript
import { EvilIcons, Ionicons } from '@exponent/vector-icons';
import ActionSheet, { ActionSheetItem } from 'react-native-action-sheet-component';
```

```javascript
class Example extends Component {
  constructor(props) {
    super(props) {

      this.state = {
        defaultSelectedValues: ['github'],
      }
    }
  }

  render() {
    return (
      <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
        <ActionSheet
          ref={(actionSheet) => { this.topActionSheet = actionSheet; }}
          position="top"
          onChange={this.onChange}
          defaultValue={this.state.defaultSelectedValues}
          multiple
        >
          <ActionSheetItem
            text="Github"
            value="github"
            selectedIcon={checkedIcon}
            icon={
              <EvilIcons name="sc-github" size={42} />
            }
            onPress={this.onItemPress}
          />
          <ActionSheetItem
            text="Facebook"
            value="facebook"
            selectedIcon={checkedIcon}
            icon={
              <EvilIcons name="sc-facebook" color="#4363A2" size={42} />
            }
            onPress={this.onItemPress}
          />
        </ActionSheet>
      </View>
    )
  }
}
```


##### Show
```javascript
actionSheet.show(() => {
  console.log('callback - show');
})
```

##### Hide
```javascript
actionSheet.hide(() => {
  console.log('callback - hide');
})
```

## Props
### ActionSheet
| Prop | Type | Default | Note |
|---|---|---|---|
| `value?` | `any` | `null` | | |
| `defaultValue?` | `any` | `null` | | |
| `onShow` | `Function` | () => {} | |
| `onHide` | `Function` | () => {} | |
| `onChange` | `Function` | () => {} | |
| `show` | `boolean` | `false` | |
| `multiple` | `boolean` | `false` | |
| `hideOnSelceted` | `boolean` | `true` | |
| `showSparator` | `boolean` | `true` | |
| `animationDuration` | `number` | `250` | |
| `overlayOpacity` | `number` | `0.3` | |
| `position` | `string` | `top` | |
| `children` | `any` | `null` | |

### ActionSheetItem
| Prop | Type | Default | Note |
|---|---|---|---|
| `text?` | `any` | `null` | | |
| `icon?` | `any` | `null` | | |
| `index?` | `number` | `null` | | |
| `selectedIcon?` | `number` | ` require('./img/checkmark.png')` | | |
| `selected?` | `boolean` | `false` | | |
| `onPress?` | `Function` | `() => {}` | | |
| `style?` | `any` | `null` | | |
