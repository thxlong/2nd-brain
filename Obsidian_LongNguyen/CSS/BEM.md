`Block Element Modifier`

### Scenario:
- Laptop: --> Block
- Keyboard, mouse, touchpad, screen: --> Element
- Laptop big, Laptop small: --> Modifier for **Block**
- Small keyboard, small screen: --> Modifier for **Element**

###### The BEM rule for CLASS
```txt
1. Block having both Element & Modifier
`Block__Element--Modifier`
laptop__touchpad--smooth, laptop__screen--scale

2. Block only have Modifier
`Block--Modifier`
=> laptop--small, laptop--big, laptop-expensive

3. Block only have Element
`Block__Element`
=> laptop__keyboard, laptop__touchpad, laptop__screen
```
