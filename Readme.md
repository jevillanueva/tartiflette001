## Levantar desde gitpod
A travez desde una ventana de un navegador
```
gitpod.io/#https://github.com/jevillanueva/tartiflette001
```
Levantar el server
```
$ python -m recipes_manager
```
Ingresar a la url "/graphiql" para probar los recursos
```
{
  recipes {
    id
    name
    cookingTime
  }
}
```
```
recipes {
    id
    name
    cookingTime
    ingredients {
      name
      quantity
      unitMeasurement
    }
  }
```
```
{
  recipe(id: 1) {
    id
    name
    cookingTime
    ingredients {
      name
      quantity
      unitMeasurement
    }
  }
}
```
### Mutation
Para realizar acciones de actualizado
```
mutation {
  updateRecipe(input: {
    id: 1
    name:"Tartiflette update"
    cookingTime: 12
  }){
    id
    name
    cookingTime
  }
}
```

### Subscription
Para realizar una subscription a travez de un socket
```
subscription {
  launchAndWaitCookingTimer(id: 1) {
    remainingTime
    status
  }
}
```