# Expresiones After Effects

Created: December 25, 2021 7:59 AM
Tag: animación

### Conteo Aleatorio

```jsx
posterizeTime(5)
Math.round(random(0,144))
```

### Elección aleatoria entre un array

```jsx
posterizeTime(1)
var a = [0,100]
var r = Math.floor(random(0,2))
a[r]
```

```jsx
posterizeTime(1)
var b = ["música", "reggaeton", "dancehall", "rap", "soca", "zouk", "afrobeat", "salsa choke", "boombap", "guaracha", "edm", "lo fi", "trap", "hip hop", "champeta", "mode up", "kizomba", "drill", "pop", "retrowave"]
var r = Math.floor(random(0,19))
var a = "'estás escuchando los beats del futuro para los futuros hits. \n crea " +"["+ b[r] +"]" + " increíble con estos 144 ml de flow'"
a
```

### Asociar capa a checkbox

```jsx
effect("Galaxy Visibility")("Checkbox").value*100
```

### Elegir color de un dropdown

```jsx
temp = thisComp.layer("Control").effect("Color")("Menu").value;
selectedColor = [ 0, [184, 223, 56, 0]/255 , [1, 44, 55, 0]/255 , [1, 1, 1, 0] ]
selectedColor[temp]
```