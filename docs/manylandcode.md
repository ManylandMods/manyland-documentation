## Impact.js

**Impact.js** is a JavaScript game engine that Manyland was developed with. 

It is highly recommended that you go through the documentation of **impact.js**, as becoming familiar with it will greatly improve your ability to create **mods** (https://impactjs.com/documentation). It will also save you a significant amount of time when it comes to reading **manyland.js**.

## Console

As a **mod** developer, one of your most useful assets will be logging to the console. **manyland.js** overrides the default console object with **consoleref**. 

To log to the console, type ```consoleref.log("example")``` instead of ```console.log("example")```

## Local Player Object

The **local player object** relates to everything that has to do with your character. 

With Parse's **deobfuscator**, you can access the local player object by typing ```ig.game.player``` into the console. This will list all properties related to your player.

An important property to note is **id**. All items and players in Manyland have a 24 character id (often referenced as **rid** in manyland.js for players). A significant amount of Manyland's id checks are **client-side**, which means it is possible to do things such as edit creations that are not yours via messing around with ids (even without the cloneable attribute).

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

Block array ID and block ID placement checks are also **client-side**.

With Parse's **deobfuscator**, you can access the block array by typing ```ig.game.blocks``` into the console.

## Dialog

**Dialog** boxes in Manyland are popups such as player profiles, alerts, writables, and so forth. Understanding dialog in Manyland is extremely important for developing **mods**. 

I will be covering two of the most important dialogs in Manyland for mod development: **alertDialog** and **playerDialog**.

Call ```ig.game.alertDialog.open();``` to create an alert dialog. The function open() takes 13 arguments, but only the first argument is required:

```js
/**
 * @param   a   the HTML or plain text to display
 * @param   b   a boolean determing if param a is parsed as HTML or not
 * @param   c   callback function for the close button
 * @param   d   text to display inside of the close button  
 * @param   e   boolean that enlarges the dialog size
 * @param   f   boolean that moves the close button to the top right
 * @param   g   boolean that determines if the dialog is opaque
 * @param   h   boolean that determines if the dialog is long/on left side of the screen
 * @param   k   boolean that determines if the dialog is at the top of the screen
 * @param   l   boolean that determines if Y overflow is hidden or not
 * @param   m   boolean that determines if the dialog is completely transparent
 * @param   n   boolean that determines if the dialog has a small rectangle shape
 */

ig.game.alertDialog.open(a, b, c, d, e, f, g, h, k, l, m, n);
```



