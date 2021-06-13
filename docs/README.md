## Manyland.js
The **manyland.js** file contains all of the source code for Manyland. It is where you will be spending most of your time when trying to understand how the game works.

The name of the **manyland.js** file has its version number appended to the file (e.g ```manyland.js?v=5798```).

## Accessing Manyland.js

To access **manyland.js**, open the developer tools in your browser (typically done with **F12** or **CTRL+SHIFT+J**). 

Head over to the sources tab and then click the manyland.com drop down.

<div align=center>
<img src="https://i.gyazo.com/84d7ad21fa59c4c2dda2c6be123fef51.png"/>
</div>

Click the **manyland.js** file to see the code behind Manyland. To make things easier to read, click the two curly brackets in the bottom left to beautify the code.

<div align=center>
<img src="https://i.gyazo.com/72e3d08a47bd0ed848a4732f9f0bed71.png"/>
</div>


The code should now look similar to this:

<div align=center>
<img src="https://i.gyazo.com/f81f88d83bc3415c71b525d03475adf7.png"/>
</div>

## Your First Mod

A good way to get started with **modding** is to find a variable and try to manipulate it to see what happens.

As an example, try modifying the **gravity variable**. Go to the console tab and type ```ig.game.gravity = 400``` and then press enter. You will now notice that when you jump you go significantly higher.

As a challenge, try to find the variable that holds your Y coordinate and modify it.

## Notes
<ul>
    <li>There are a few things to note when you start modding: 
        <ul>
            <li>Log out of your account</li>
            <li>Use a VPN if possible</li>
            <li>Never attempt to modify account rank or editor status</li>
            <li>Utilize breakpoints and stepping into functions in developer tools</li>
            <li>Words that are bolded repeatedly throughout the documentation are important concepts</li>
            <li>It is highly recommended that you learn JavaScript</li>
        </ul>
    </li>