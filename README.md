# Tap-Titans-2-Progress-Bot
A HiroMacro script for Tap Titans game
-by Tune389
-edited by djo5296 (me)

## Features
 - Auto leveling sword master (only at the start of each code run)
 - Autoprestige after randomized X minutes, given a range
 - Random Hits
 - Autostart any skill on full mana
 - Autostart boss fights with any skill
   - changed old behavior to auto start WC instead of specifying in the settings
   - later in a run after X minutes, will also activate DS and Midas
     - be sure to edit this setting if you don't like it
 - Boss detection (no actions while fighting vs a boss)
 - Autofight ClanQuest
 - Autobuy skills
   - always max HS
   - other skills level up using 2-3 taps (skill cancellation FIXED in pull request Dec 26 update)
   - if you want other skills only at level one, use #justUnlockSkills = 1
     - only reports of it not working but it should work... idk, i dont use it lol
 - Autolevel heroes with scroll detection & spam
   - max top most hero first, then bottom most hero
   - level everyone else accdg to #heroIntensity
 - Stop leveling older heroes after X minutes
   - check under :levelHeroesScrollDown and check specified minutes
 - Autostart skills every X minutes
   - make sure you edit both Action-Skills settings at the top and ":afterPrestige" sections
 - #lateTournament in case you need to stop then re-start mid-run (remember/estimate your current run time!)
   - will always start at #minz minutes so be sure to turn this off once you prestige #bug ish, just lazy to fix
 - dynamic changing of intervalSkill based on time elapsed (change according to preference)
   - look for resultUpdateTime
   
## Changes from last code
 UPDATED
 - stop leveling up non-main heroes after X minutes
   - Heroes now have a lvl 6k cap, it doesn't matter if you keep leveling old heroes because you need to get all passive skills, also for future ascension
   - should now stop visiting your older heroes after 51 minutes (look for this section under :levelHeroesScrollDown)

 CHANGED
 - startBossSkill: 0|1|2|3|4|5|6 (If the boss fight fails, the bot will wait for this skill before the next boss start)
 - startBossSecondarySkill: 0|1|2|3|4|5|6 (The bot press this skill on boss fight start, but without checking availability)
   - reworked into clicking "FIGHT BOSS" whenever it appears during :randomTouch; uses #checkBossDuringRandomTouch setting
     - also clicks on WC, and later on, Midas and DS as well
     - CODE TIME RATE SLOWS DOWN IF ON!!!!!!!!!
     - if #checkBossDuringRandomTouch == 0, will follow old system for boss fight checks and time properly syncs; UNTESTED
       - off setting reported to not work lol. you can just delete the getColor part in :randomTouch
 
## FREQUENTLY ASKED QUESTIONS
To everyone with problems when leveling heroes or skills:
- I can't keep answering problems for leveling up heroes/skills since they dont happen to me
  - i.e. i can't replicate how the codes eff up when you run them on yours so I can't get a good grasp of how to fix them.

Common fixes below:
Copy paste the scrolling sections in the places that need the extra scrolling. Maybe it's not reaching where it's supposed to
- just read the names of each ":" section and where each brings you so you know where to place them. they shouldnt be hard to follow as each :section seems properly labeled

For your convenience:
> //scroll up
  touchDown 0 280 650
		sleep 200
		touchMove 0 280 600
		sleep 50
		touchMove 0 280 700
		sleep 50
		touchMove 0 280 750
		sleep 50
		touchMove 0 280 780
		touchUp 0
		sleep 200
		#time = #time + 550
  
> //scroll down
	touchDown 1 280 740
	sleep 200
	touchMove 1 280 710
	sleep 50
	touchMove 1 280 500
	sleep 50
	touchMove 1 280 410
	sleep 50
	touchMove 1 280 400
	touchUp 1
	sleep 300
 #time = #time + 550

Adjust coordinates by 1 or 2 numbers
- as i have been repeating, since the code follows color checks, I have reported in an earlier response that some coordinates may just not "exist" (e.g. one of my values is "459 755" when my OC self wants it "460 755", but i cant use that value because hiro can't detect "460 755" for some reason)
- if still none, find your own coordinates (and even color) that works for you by turning off hiro, going to settings, turn on location (and color) debug, then turn hiro back on. This adds lag as codes run so once you find what you need, turn off the debug settings and edit the coordinates and color values as what you have found

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
 - fullManaSkill: 1|2|3|4|5|6
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
 
## In case I missed anything about features/available settings
 - check top section of code and read descriptions there and all "//" comments present elsewhere
 - again, I am a pet user, prestiging at around 5500, current settings need editing to suit different playstle, especially earlier MS
   - all current settings apply to *MY* liking
   - edit/add your own codes accdg to your own preference, I do not take requests to suit your playstyle
   - I may do feature requests, depends.
   - Do report bugs though (ASIDE FROM ERRORS WHEN LEVELING, SEE ABOVE FOR HOW TO FIX)
