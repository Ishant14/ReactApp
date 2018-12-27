# ReactApp

# How React Component Should maintain the state . 

To collect data from multiple children, or to have two child components communicate with each other, you need to declare the shared state in their parent component instead. The parent component can pass the state back down to the children by using props; this keeps the child components in sync with each other and with the parent component.

# Use setState correctly 

setState() method work asynchronously.  So the  below is not sure to give you the right result 

```js
this.setState({
showPerson : !showPerson,
toggleClicked: this.setState.toggleClicked+1;
});

```

In the above code it is not guraanted that toggleClicked value will be correct always. To make it correct use the below way :

```js
this.setState((prevState,props)=>{
return {
showPerson : !showPerson,
toggleClicked: this.setState.toggleClicked+1;
}
});

```
It will take the prevState and increment the toggled value in that only.










