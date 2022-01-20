![fmLaunchPad logo][fmLaunchPad logo]
# fmLaunchPad
[3-2-1 FileMaker is GO!]

A cheeky little rocket to help you start the FileMaker file you want.

## The Problem

😎 FileMaker got a cool new feature in FM18/FM19 - a predefined file to open at startup. However, FileMaker's 'open file at startup' setting applies equally to all instances of FileMaker. *It is not possible to specify different start files for different versions/instances of FileMaker client.*

🤨 On customers computers this is mostly not a problem as there is often only one target database, but sometimes (and maybe very often in developer environments) **we want different databases to be started in different situations!**

❗️ It's a case of *'one size ***does not*** fit all'*!

## The Solution

🚀 MrWatson's fmLaunchPad - a cheeky little rocket with multiple module segments -  allows you to define which file should start in which context:

![fmLaunchPadRocket][fmLaunchPadRocket]

Just launch fmLaunchPad - or manually set light to the rocket's flame - and your off! 🚀

## Getting started

1. Download the [latest release][fmLaunchPad releases] of fmLaunchPad.

2. Move the folder into the Applications folder (recommended, but anywhere will do)
   - If you also have [fmWorkMate][fmWorkMate home] place the fmLaunchPad folder alongside the fmWorkMate folder if you wish to open/edit fmLaunchPad from fmWorkMate.

3. Open fmLaunchPad in FileMaker => The welcome screen should appear
4. Read through the instructions to get an idea how fmLaunchPad works
5. Prepare your rocket and modules as necessary for your requirements, as documented below
6. Prime your rocket to launch at startup

    1. Open the FileMaker Settings
    2. Select 'At startup, open file'
    3. Choose the fmLaunchPad file.

7. Launch your rocket

  - Click the flame at the bottom
  - Or simply restart FileMaker 


## Preparing your Rocket

fmLaunchPad comes with a basic rocket that you need to customize to your specific needs.

1. Press the list-icon in the top right to switch to list view.

   For each module you can see from left to right

   - the start condition for the rocket module (or a little tick if the module is always to be performed)
   - the action to take and target file reference
   - the name of the module on the side of the rocket
   - a little rocket icon, if the start condition is currently met
   - a module options button
   - a move button

   The module options button next to the rocket nose cone at the top is for the Preflight Check settings - more about those below.

   Between the wings the module navigation controls are to be found.

   The rocket flame at the bottom starts the rocket launch when clicked!

2. Add, remove or change modules as necessary

   - You can duplicate or delete a module from the Module Options button
   - Change the start condition as necessary
     - Use the fmAppName or fmFoldername functions to identify the FileMaker instance
     - See the help pages for more functions you can use
     - See the example setup for fmWorkMate below

3. Define the Module's launch conditions

   You can decide what datbase to open based on...

   - the FileMaker Version,
   - the name or location of the application (*),
   - modifier keys,
   - the presence in a particular network,
   - the availavbility of a file at a particular path,
   - or even based on the time of day/month/year, if you want!

   There is a little + button to the right of the Else If, you can use to insert various conditions.
   
   You want to always open the same file?
   
   - click the tiny hidden checkbox to the left of the If
   - or just enter always (or a 1) into the launch conditions field

4. Setup Module options

   - In the module options you can
     - turn a module on or off
     - set a module to launch in capsule mode (see below)
     - or duplicate/delete a module

5. Setup Module order

   - Modules are triggered from top to bottom
   - To reorder a module
     1. Click the moduler's move button on the far right
     2. Click the move button at the place where the module should appear

6. Setup Preflight Check, if necessary

    In the Preflight Check you can define $$variables which can be used in the module start conditions, for example:

    ```
    $$OfficeNetwork = Contains( IPs ; "192.168.1." )
    ```

    In a module start condition you can then simply reference the $$variables:

    ```
    Else If
        $$OfficeNetwork
    ```

## What's a Capsule module?

A normal local starter file suffers the problem that it can only be opened one instance at a time, meaning that you can't open a 2nd file until the first file has opened and 'let go' of the starter file.

fmLaunchPad has a cool solution to this problem: **Capsules!**

=> Define a module as a capsule (in the module options)!

When the module is launched fmWorkmate launches a separate 'capsule' - that is, it saves and opens a separate starter file - allowing the rocket to immediately 'fall back to earth' (close), allowing a second FileMaker app to start immediately and without conflict!

=> One fmLaunchPad, multiple Capsules, no conflicts!

## Creating multiple FileMaker apps (on Mac)

If you have several FileMaker solutions that you want to run alongside each other, you might want to consider creating multiple apps - one for each solution.

(*) On Mac it is possible to simply duplicate the FileMaker.app to make a separate instance of FileMaker to use with your target database.

1. Duplicate the FileMaker app
2. Rename it or place it in a named Folder
3. Change the file icon to suit your app
4. Define a module in fmLaunchPad to launch your target database when this app starts (based on the folder or app name).

On Windows you can only distinguish FileMaker versions (as far as I know).

This is a good way to create a separate app for fmWorkMate.

## Example Setup for fmWorkMate

Here you can find [a step by step description of how you set up fmLaunchPad to start a custom fmWorkMate app](https://github.com/mrwatson-de/fmWorkMate/Setting_up_fmWorkMate_with_fmLaunchPad.md).

## Known Issues

There is one downside to fmLaunchPad and that is 

- It **always** launches when FileMaker opens, *even if you have dragged a specific file to the FileMaker icon in your dock*.

This means you have to abort the mission when FileMaker first opens, and then drag the file again.

Yes, it is annoying, and there is no workaround that I know, ... but all in all **life with fmLaunchPad is better than life without**!

## 3-2-1 FileMaker is GO!

So you are ready to launch and the stars are your limit! ✨

Have a great trip! 🚀

MrWatson

[![mrwatson.de logo][mrwatson.de logo]][mrwatson.de]

## Links

- fmLaunchPad
  - [fmLaunchPad home][fmLaunchPad home]
  - [fmLaunchPad repo][fmLaunchPad repo]
- Related Tools
  - [fmWorkMate][fmWorkMate home]



[fmLaunchPad home]:https://www.fmworkmate.com/fmlaunchpad
[fmLaunchPad repo]:https://github.com/mrwatson-de/fmLaunchPad
[fmLaunchPad logo]:fmLaunchPadLogo_256_sm.png
[fmLaunchPad releases]:https://github.com/mrwatson-de/fmLaunchPad/releases
[fmLaunchPadRocket]:fmLaunchPadRocket50_sm.png
[fmWorkMate home]:https://www.fmworkmate.com/fmWorkMate
[MBS-Plugin]:https://www.monkeybreadsoftware.com/filemaker/
[mrwatson.de logo]:www.mrwatson.de_neon_128.png
[mrwatson.de]:http://www.mrwatson.de


