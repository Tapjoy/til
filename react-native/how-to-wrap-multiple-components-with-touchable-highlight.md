# How to wrap multiple components with TouchableHighlight

`<TouchableHighlight/>` is extreamly useful and important component of `React-Native`.<br>
Basically, it has quite similar usage of `<button>` tag in HTML.
By using it, a developer can easily render 'touchable' component with native touch feedback on react-native app.<br>
But when you use this component, you should cautiously read the [documentation](http://facebook.github.io/react-native/docs/touchablehighlight.html). Otherwise you will fall into the trap of common mistake.
<br><br>
The mistake is
- Wrapping multiple child components with `TouchableHighlight` like what people usually have done with `<button>` tag in HTML
```jsx
  <TouchableHighlight onPress={this._handleOfferPress}>
    <Image source={this.props.data.img} style={styles.offerImage} />
    <Text style={styles.offerText}>
      {this.props.data.payout}
    </Text>
  </TouchableHighlight>
```
<br>
The thing is that `TouchableHighlight` is able to have only one child component. And with the mistake, you will get an aggressive error screen.
Solution is quite simple.<br>
- Just wrap the multiple child components with `<View />` react-native component.
```jsx
  <TouchableHighlight onPress={this._handleOfferPress}>
    <View style={styles.container} >
      <Image source={this.props.data.img} style={styles.offerImage} />
      <Text style={styles.offerText}>
        {this.props.data.payout}
      </Text>
    </View>
  </TouchableHighlight>
```

February 12 2017, by echo304
