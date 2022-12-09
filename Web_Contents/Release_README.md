# Mutiny!
"God" management game where you handle the resource management of a police ship, made by two UPC students in the Game Development Bachelor's Degree


## The Team
Carles Homs:
Role: Code & Design
Github Account: https://github.com/ch0m5

Dídac Romero: 
Role : Code & Complementary art (UI, audio)
Github Account: https://github.com/DidacRomero

Webpage: https://ch0m5.github.io/Mutiny/
Github Repository: https://github.com/ch0m5/Mutiny (Link should only work if you are a contributor)
Link to Wiki: https://github.com/ch0m5/Mutiny/wiki  (Link should only work if you are a contributor)
MIT License: https://github.com/ch0m5/Mutiny/blob/master/LICENSE (Link should only work if you are a contributor) You can also see the license at the end of the README.


## Gameplay

### Core Loop & Goals
Your goal is to complete your voyage of 3 rounds, 3 days each, delivering your captive prisoners at the end of each round.
You have a minimal amount of prisoners you have to deliver, if you lose more than that you'll be fired!
You'll get paid by every prisoner delivered. The money can be used to buy ship upgrades, hire employees, and buy resources during the next round, so plan ahead!

All this information can be seen on the UI at the top left of the screen and on the round end menus.

### Controls
In this assignment you have 4 buttons to give orders to some agents.
1. The alarm button alarms police guards for 15 seconds, with a cooldown of 15 seconds. They will run around the ship beating prisoners protesting or escaping.
	Note: While guards can intervene without the alarm, if they are outnumbered by the protesters they will flee in fear! The alarm ensures the rebelion is put down.
2. The button with the shape of a pot will order the assistants to go and cook 20 units of food, it has a 5 seconds cooldown.
3. The checklist with life icons in it will send the assistants to heal people who are hurt and waiting at the Infarmary.
4. The guard with "Zzz" icon will send a guard to either rest or fulfill another more prioritary need.
	Useful to force guards to attend their needs when things are calm, even if they're not in critical state, so that they don't pile up too much.

Pressing on top of a character will show their current needs values and information about what they're doing at the moment.

At the bottom of the screen, you can see the resources that the ship holds, as well as the ammount of money you have left. There's a button at the right
called Shop, which you can use to buy resources with your remaining money. Inside the shop, hitting the + or - buttons next to the icons, will determine 
how many resoures you want to buy, whenever you want to confirm your purchase, click the green button Buy!, located at the bottom of the shop menu.

At the end of every round you'll be able to buy ship upgrades and hire more employees using a similar shop system.

### Resources
Resources are used to do actions which satisfy needs (see AI).
The resources available are:
 - Alcohol: To take care of boredom, more expensive but can be acquired at the easily accessible Canteen.
 - Tobacco: To take care of boredom, cheaper but requires to be outside which is far away from the rest of areas.
 - Medicine: To heal characters.
 - Ingredients: To make food.
 - Food (Made, not bought!): To eat.
 - Shampoo: To take a shower.
 - Toilet paper: To take a dump.
 
### Ship Upgrades
Upgrades allow for more actions to be done at the same time by more agents and can be bought at the end of a round.
The upgrades available are:
 - Beds (max 4 + 3): For agents to rest in. 3 spots at game start (on the ground, no beds).
 - Showers (max 3): For agents to shower. 1 at game start.
 - Toilets (max 3): For agents to take a dump. 1 at game start.
 - Stoves (max 3): For assistants to cook. 1 at game start.
 - Gourneys (max 4): For patients to be treated by assistants.  1 at game start.


## AI

### Characters & General Behaviors
- Policeman / Guard: They can be distinguished for their police riot gear. They are the force that keeps protesters from escaping.
	- Default Behavior: They patrol around the ship and attack protesters or prisoners attempting to escape the ship.
	- Angry: Excess of boredom. Beats up the first non-guard he spots.

- Asistant: they can be distinguished by their appearance of an airport assistant wearing green gloves. They cook food and heal injured crew.
	- Default Behavior: They wander around the ship until an order from the player is given.
	- Angry: Excess of boredom or getting hit by a guard. Quits the job.
	
- CDR / Prisoner: They can be distinguished because of their white grandma hair. They want to protest and escape the ship when they see the chance.
	- Default Behavior: They wander around the ship, getting angry at random times. They will join other nearby protesters if they see one.
	- Angry: Happends randomly based on their discontent (see Needs). Sparks a protest somewhere, which can lead to an escape attempt after 15 seconds.

All "Afraid" agents run away of whatever scared them and wait somewhere. If the source of fear doesn't appear for a while, they stop being scared.

### Needs
All agents have their own goals, which can be their own defaults or given by the player.
However, they also have needs that must be fullfilled, which are the following:
- Hunger: Too much and the character will die!
- Health: If it reaches 0, the character dies!
- Fatigue: Too much and the character will faint.
- Filth: Too much and the character's health will decrease.
- Boredom: Too much and the character will get angry.
- Bladder: Too much and the character will mess itself on the spot, which gets him filthy and scares other agents.
 
The more unfullfilled the needs are, the higher the discontent is, which will prompt prisoners to protest and attempt escape.

### Day/Night
Except for the guards, agents are more prompt to sleep when it's nighttime.
Prisoners are more prompt to getting angry and protest when it's nighttime.


## Innovation
- Use of "Smart Objects". The ship is filled with spots which can be occupied or free, preventing the overlapping of agents in the same exact location.
- Agents use detection to react to events happening around the ship. Prisoners and assistants flee from violence, for example.
- All agents present some sort of basic teamwork behavior:
	- Prisoners will join ongoing protests, adding on their numbers.
	- Guards detect other nearby guards when stopping a protest. If they're outnumbered, they flee in fear. Triggering the alarm prevents this.
	- Assistants ordered to heal will go to patients waiting at the infarmary
- The behavior system is shared between agents.
	- All agents have agent-type bound goals and needs to attend, but each has diferent thresholds in which they feel the necessity to fulfill them.
	- These needs are also ordered in priority and create an overall discontent value. These value lowers the "necessity threshold" to overcome.
	  In other words, the worse the needs are the higher the discontent, and the lower the values have to be for the agent to tend to needs.
- Interruption system: Agents are ready for their current processes to be interrupted at ANY time by either surrounding events or player orders.


## CREDITS
Game Icons creditation.

Commons 3.0: https://creativecommons.org/licenses/by/3.0/

- Cooking Pot by Delapouite. 		Placed icon over a sketch. Licensed under commons 3.0.
- Turd by Lorc. 					Placed icon over a sketch. Licensed under commons 3.0.
- Night Sleep by Delapouite.		Placed icon over a sketch. Licensed under commons 3.0.
- Meal by Delapouite.				Placed icon over a sketch. Licensed under commons 3.0.
- Health increase by sbed.			Placed icon over a sketch. Licensed under commons 3.0.
- Punch Blast by Lorc.				Placed icon over a sketch. Licensed under commons 3.0.
- Evasion by Delapouite.			Placed icon over a sketch. Licensed under commons 3.0.


## LICENSE
MIT License

Copyright (c) 2019 Carles Homs, Dídac Romero

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
