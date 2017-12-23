# Tap-Titans-2-Progress-Bot
A HiroMacro script for Tap Titans game
-by Tune389
-edited by djo5296 (me)

## Features
 - Auto leveling
 - Autoprestige after randomized X minutes, given a range
 - Random Hits
 - Autostart any skill on full mana
 - Autostart boss fights with midas
   >changed old behavior to auto start midas instead of specifying in the settings
   >later in a run after X minutes, will also activate DS and Midas
     >>be sure to edit (out) this setting if you don't like it
 - Boss detection (no actions while fighting vs a boss)
 - Autofight ClanQuest
 - Autobuy skills
   >always max HS
   >other skills level up using 2-3 taps (WILL cancel active skills #bug)
 - Autolevel heroes with scroll detection & spam
   >max top most hero first, then bottom most hero
   >level everyone else accdg to #heroIntensity
 - Autostart skills every X minutes
 - #lateTournament in case you need to stop then re-start mid-run (remember/estimate your current run time!)
   >will always start at #minz minutes so be sure to turn this off once you prestige #bug
 - dynamic changing of intervalSkill based on time elapsed (change according to preference)
   
## Changes from last code
 REMOVED -stop leveling up non-main heroes after X minutes
  >because heroes now have a lvl 6k cap, it doesn't matter if you keep leveling old heroes because you need to get all passive skills, also for future ascension
 CHANGED - startBossSkill: 0|2|3|4|5|6 (If the boss fight fails, the bot will wait for this skill before the next boss start)
 - startBossSecondarySkill: 0|2|3|4|5|6 (The bot press this skill on boss fight start, but without an readyup check)
  >reworked into always click "FIGHT BOSS" whenever it appears
  >also clicks on skill Heroes, and later on Midas and DS as well
 
## Coming Soon
  - properly detect if skill is running or not to prevent cancellation
  - stop leveling already maxed heroes especially the really early heroes

## Basic Requirements:
 - Android Device or Emulator
 - Resolution 480x800 (you can change it maybe if your device is different)
 - Root for HiroMacro

## Install
 - Download NoxPlayer, MEmu, ...
 - Enable root
 - Set screen size to: 480x800
 - Settings -> SuperUser -> disable notifications
 - Install HiroMacro + Tap Titans 2
 - Insert downloaded script by C+P
 - HiroMacro Settings -> Color Access Method -> ScreenCapture
 - Start HiroMacro Service
 - Start Tap Titans 2
 - Click on volume down to start the script
 - again to stop
 
## Optional for better performance:
 - Set ScreenCapture delay in HiroMakro settings to 0
 - Increase ram to 1500 or more.
 - Increase used cores to 2 or more.

## Settings available:
 - enableFairies: 1|0 (enable if you bought Premium and disable Ads, otherwise, play check settings for #agree and #decline
 - hatchEggs: 1|0
 - enableClanShip: 1|0
 - enableSkills: 1|0
 - enableClanQuest 1|0
 - enableHeroes: 1|0
 - enableAutoprestige: 1|0
 - fullManaSkill: 2|3|4|5|6
 - prestigeAfterXMinutes: 1-300
 - intervalHS: 0-n (set an interval to 1 if you want to use this skill every minute)
 - intervalCrit: 0-n
 - intervalFireBlade: 0-n
 - intervalMidas: 0-n
 - intervalShadowClone: 0-n
 - intervalHeroes: 0-n
 - runActionsOnStart: 1|0
 - heroIntensity: 1-n (increase this value if you want more taps on the level up buttons of hero per scroll)
 - enableTapping 0|1
 
## In case I missed anything
 - check top section of code and read descriptions there
 - again, I am a pet user, prestiging at around 5500
   >all current settings apply to *MY* liking
   >edit/add your own codes accdg to your own preference, I do not take requests to suit your playstyle. Maybe feature requests though not sure
