# 2021 revzim - azadventure-demo - firebase

### server - Node/TypeScript
### client - Unreal Engine 4.26/C++

## GAME FEATURES
Server
- authoritative state of truth
  - any and all modifications/decisions to the game state are strictly handled by the game server
- procedural generation of any heroes & enemies
- turn-based battle against server ai
- battle data & actions are dictated by server
- any & all updates that modifiy the server state of truth are validated by the server before any modification is finalized
- battle structure: heap priority queue

Heroes & Enemies
- derived from one base 'brain' class to dictate metatype
- psuedo-random procedural generation (each hero & enemy is different)
- each metatype is generated from the following:
  - 20 hero models & 5 enemy models 
    - 3 different metatype animation blueprints
    - each blueprint has 5-7 'actions' (variance due to asset limitations)
  - 100 different weapons
  - 20 particle systems generated per each attack
  - metadata - definitions & attributes per generated hero
  - all assets transform (weapon, model, particlesystem xf)
- all notable actions are recorded & stored in firestore
  - ex. defeating an enemy & successfully fishing will yield experience

## GAME FLOW
- login/signup and connect to the game server
  - use any email/password combo to sign up
    - `firebase authentication system`
    - `just like everything else, don't use a password you've used before`
    - `my server uses firebase token validation for authentication`
  - on successful signup, server will procedurally generate your character & all attributes as well as asset information
  - hero assets (weapons/models) can be altered in game and every change is recorded and will be reflected immediately in game as well as in your hero ui

``` FIRST DEMO OF TESTING NEW WEB UI PLUGIN w/ UE4. VUETIFY WAS TOO INTENSIVE AND ENDED UP LAGGING UI SO DROPPED IN NEWER DEMOS ```
# [VIDEO DEMO](https://revzim.github.io/azadventure-demo/)

```
- PC ISNT GREAT SO RECORDING STUTTERS A LITTLE DURING CERTAIN SWAPPING DUE TO RUNNING SEVERAL APPLICATIONS & PROGRAMS WHILE RECORDING
```

## PLAY
- CLIENT > DOUBLE CLICK `AZAdventure.exe`
- YOU CAN EITHER RUN YOUR OWN SERVER AND PLAY OR CONNECT TO ANOTHER SERVER
- GO TO `CLIENT` SECTION TO LEARN HOW TO CONNECT TO OTHER SERVERS

CLIENT
```
- TO PLAY YOU WILL HAVE TO POINT THE CLIENT TO A SERVER
- TO DO THIS, ENTER CLIENT>AZADVENTURE>CONTENT>SETTINGS
- OPEN SETTINGS.JSON
```

SERVER
```
- PROVIDED IS A BUILT VERSION OF THE GAME SERVER
- TO EDIT THE SERVER PORT GO TO: SERVER & OPEN CFG.JSON
- EDIT PORT TO WHATEVER PORT YOU DESIRE
- MAKE SURE IF JOINING YOUR SERVER, CHANGE SERVER ADDRESS WITHIN CLIENT SETTINGS * SEE ABOVE CLIENT SECTION *
- DOUBLE CLICK THE GAME SERVER TO AUTOMATICALLY START IT UP
```

### AUTHOR: [revzim](https://github.com/revzim)

```
PACKAGED ON: 2021-08-25
```
