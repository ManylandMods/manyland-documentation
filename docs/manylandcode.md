## Impact.js

**Impact.js** is a JavaScript game engine that Manyland was developed with. 

It is highly recommended that you go through the documentation of **impact.js**, as becoming familiar with it will greatly improve your ability to create **mods** (https://impactjs.com/documentation). It will also save you a significant amount of time when it comes to reading **manyland.js**.

## Console

As a **mod** developer, one of your most useful assets will be logging to the console. **manyland.js** overrides the default console object with **consoleref**. 

To log to the console, type ```consoleref.log("example")``` instead of ```console.log("example")```

## Local Player Object

The **local player object** relates to everything that has to do with your character. 

With Parse's **deobfuscator**, you can access the local player object by typing ```ig.game.player``` into the console. This will list all properties related to your player.

An important property to note is **id**. All items and players in Manyland have a 24 character id (often referenced as **rid** in manyland.js for players). A significant amount of Manyland's id checks are **client-sided**, which means it is possible to do things such as edit creations that are not yours via messing around with ids (even without the cloneable attribute).

## Player Array

The **player array** is an array of all player objects currently connected to the world. Each **player object** is structured similarly to the **local player object**. You can access information about other players using the player array (e.g coordinates, name, and id).

With Parse's **deobfuscator**, you can access the player array using ```ig.game.players```.

An example code snippet that prints all player names and their respective coordinates:

```js
ig.game.players.forEach(player => {
    consoleref.log(`${player.screenName} | ${player.pos.x}, ${player.pos.y}`);
});
```

## Block Array

The **block array** is an array of all item objects that you have loaded in. Some important attributes of an item object are **base** (item type), **creatorId**, **id**, and **name**.

Block array ID and block placement checks are also **client-sided**.


## Dialogue

