# IKEMEN GO Universal Armor 1.1 By Kamekaze 
**Mail** - ilive@kamekaze.world

**Twitter** - @OldEra_Kamekaze

**Bsky** - kamekaze.world

**Fgc network** - Kamekaze@fgc.network

###### FOR IKEMEN GO .99 OR LATER ONLY. 5/30/24 NIGHTLY OR LATER

**To download, go to the code button and download the zip.**

## Instructions
Add the armor.zss file to your save/config.json under **CommonFiles**

This plug and play armor works by the player 
turning the map "ikarmor_assertarmor" on, once it is on
it will activate and handle all attacks
it is important to note that all attacks with any invul can be hit
while it is active due to how the code works. the user MUST turn
the armor flag on and off on their own!
If you want your character to never have armor you can
add a const to them called **"ikarmor_no_armor"** It will negate any 
armor activation as the helper will not be called for them.

### Player Values:
**ikarmor_throw_protect** - set this map to one to disable the ability to be thrown 
this works for characters with "hyper armor"
**ikarmor_assertarmor** - set to 1 to toggle armor. Hyper armor by default
The player must handle their own management to make it act as super armor
The recommended code for that can be found commented here below		     


## Super Armor example
##### Assume this is in the [statedef +1]

```
map(ikarmor_assertarmor):=!map(armormod);

if numhelper(map(armor_helper_st))  && helper(map(armor_helper_st)),map(hittime)=0 &&  !map(armormod)
{
map(armormod):=1;
}

if map(armormod) && movetype!=H && helper(map(armor_helper_st)),map(hittime)=0
{
map(armormod):=map(armormod)+1;

if map(armormod)>=25 # Can be any number, doesnt matter
{
map(armormod):=0;
}
}
```
