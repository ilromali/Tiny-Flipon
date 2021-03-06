# Tiny Flipon π

![Banner](banner.png)

An open-source minimalist but playable version of [Flipon](https://www.flipon.net), my juicy fast-paced match-3 game.

Get the original game on:

- [PC](https://store.steampowered.com/app/1285020/Flipon/)
- [Nintendo Switch](https://www.nintendo.com/games/detail/flipon-switch/)
- [Android](https://play.google.com/store/apps/details?id=com.pid.flipon) 
- [iOS](https://apps.apple.com/us/app/flipon/id1535461342)

The game was made by me (dev, project manager, release), AurΓ©lien Regard (2D art), Yoann Bazoge (UI/UX), Swann MΓ©nage (sound design) and Zander Noriega (music).

## What is Tiny Flipon

Tiny Flipon is a playable Unity project containing the core gameplay of Flipon. Most of the source code is a direct copy of what is in the complete game.

![Tiny Flipon GIF](tiny-flipon.gif)

What is included?

- β Core logic: Grid of blocks, move horizontally, combo, chain
- β Unity project
- β Objectives 
- β Local multiplayer logic
- β "AI" 
- β Touch controls
- β Dynamic UI and screen split
- β Unit tests for gameplay

What is not included?

- β Assets (no sprites, no backgrounds, no sounds, no FXs) - no copyrighted files!
- β Third-party premium plugins (Odin Inspector, InControl, etc)
- β Audio
- β Gamepad support 
- β Menus, UI
- β Dialog system
- β i18n and texts
- β Custom editor tools
- β Console and mobile ports

## Code Architecture & quality 

**THIS IS A FAR FROM PERFECT CODEBASE** and it doesn't matter. I'm not releasing it because I want to show my C# skill, instead I want to show what a released game looks like inside: complex, some dead code (but some dead code is link to the "tiny" part), lots of code that could be refactored, scrap from previous projects... 

Now, with Flipon I wanted to avoid using Unity's scene as much as possible except for the UI. That's why the `Game` scene doesn't display anything when not running: everything is created on Play.

I also wanted to have a testable independant C# project for the `Core`. That's why you have `Block` (core) and `BlockScript` (Unity MonoBehaviour).
Turns out it wasn't a great idea, but I did manage to have Unit tests for most of that part. Also it could be reused in ahything else (ML, Flipon 99 players online, whatever).

BUT in the end a lot of game logic also happen in `PonGameScript` and `GridScript` (like chain detection), so it is far from perfect.

## How to run

Open the project in [Unity](unity3d.com/) (2019.4.0f18).

Open the `Game` scene.

Play. It should run.

Now you can tweak the `GAME SETTINGS` GameObject to change players, objectives, grid size, speed, etc.

![Game Settinngs GameObject](settings.png)


## Contributing

The gameplay code is this repository is the same than in the game.
If you want to make a significant modification or addition, I may or may not add it in the final game. If so, I'll indeed properly credits your work.

There's a `.DotSettings` file for Rider/Omnisharp if you want to follow the coding style of the prokject.

Note: I use as much Gitmoji as possible my commit messages.



