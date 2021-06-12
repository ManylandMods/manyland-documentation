## What is Obfuscation?

**Obfuscation** is the obscuring of code by making it difficult to **read**, **understand**, and **use**. 

Manyland uses **obfuscation** and **minification** to prevent users from making **mods** (short for **modifications**) and to decrease file sizes for faster loading.

## Manyland's Obfuscation

Manyland uses **obfuscation** by renaming important object, variable, and function names to random numbers preceded by a capital O. 

The randomly generated names will change every update, which results in making mods useless if **deobfuscation** was not utilized.

An example of what obfuscation looks like in Manyland is ```ig.game.O65``` (this example is the **local player object** in version 5798 of manyland.js).

## Deobfuscation

**Deobfuscation** is the process of bypassing Manyland's obfuscation so that mods continue to work every update.

You can make your own **deobfuscator**; however, the **modding** community mostly uses Parse's for simplicity sake (https://github.com/parseml/many-deobf)

## Parse's Deobfuscator

Parse's **deobfuscator** is able to find obfuscated objects, variables, and functions by abusing the fact that Manyland does not obfuscate all variable names.

You can include Parse's deobfuscator in your mod with the following code snippet:

```js
/**
 * An asynchronous function to load the newest version of many-deobf
 */
async function main() {
    await $.getScript("https://cdn.jsdelivr.net/gh/parseml/many-deobf@latest/deobf.js")
    
    // . . .
}

main()
```
Parse's deobfuscator allows you to input values into a list of functions to return the obfuscation you need. There are five functions included in Parse's deobfuscator to accomplish this:

```js
/**
* Searches for a unique string 
* Returns the function that includes the string
* @param    object    the object that the function is a part of
* @param    string    the unique string to search for
* @param    returnKey    a boolean if you want to return the key or not
* @return  the function that includes the unique string
*/

Deobfuscator.function(object, string, returnKey);

/**
* Searches for a unique property of an object
* Returns the object that has the unique property
* @param    object    the object that the property is a part of
* @param    string    the name of the unique property
* @param    returnKey    a boolean if you want to return the key or not
* @return  the object that includes the unique property
*/

Deobfuscator.object(object, string, returnKey);

/**
* Finds a variable that's length matches the supplied length argument 
* @param    object    the object that the variable is a part of
* @param    length    the length of the variable's value
* @param    returnKey    a boolean if you want to return the key or not
* @return  the variable with content length that matches the supplied length
*/

Deobfuscator.variableByLength(object, length, returnKey);

/**
* Finds the value of whatever is betwee two strings
* @param    func     a suplied function
* @param    start    the start of what is between the two strings
* @param    end    the end of what is between the two strings
* @return  what was found between the two strings
*/

Deobfuscator.keyBetween(func, start, end);

/** 
* Finds an object property by type
* @param    object    the object that the property is a part of
* @param    type    the type of the property
* @param    returnKey   a boolean if you want to return the key or not
* @return  a property that matches the supplied data type
*/

Deobfuscator.keyBetween(object, type, returnKey);
```

For example, if you wanted to find out the current obfuscation for the **local player object** you can look for a property of the object that is not obfuscated (e.g ```.screenName```). You can then plug this information into Parse's deobfuscator to return the **local player object**:



```js
/**
 * A function to find the local player object.
 * @return Object with your player information.
 */
function getPlayerObject() {
    return Deobfuscator.object(ig.game, "screenName", false);
}
```

Thankfully, you do not have to write code every time to find the most used obfuscation due to the fact that Parse's **deobfuscator** comes with a set of useful predefined objects and functions: 

```js
ig.game.player // Self Object
ig.game.player.changeName(name) // Change name function
ig.game.players // Player Array
ig.game.equip.item(id) // Function to equip bodies / items
ig.game.blocks // Object that holds block ids and such
ig.game.websocket // WebSocket object
ig.game.player.id // Your player ID

function idFromScreenName(string screenName) {} // Screenname to player id
function updatePlayers() {} // Updates the ig.game.players array for new players
```

## Notes
From this point forward, all documentation will use Parse's deobfuscator so that information can be useful and more readable regardless of updates.