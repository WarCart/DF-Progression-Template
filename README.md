# DF-Progression-Template
This is Template of config datapack of mod Ability Progression (DF progression).

## Ability Setup
To config Ability you need to create file with name of ability in abilities package.

To get the ability name you need to enable advanced tooltips (f3 + h) in your minecraft world and target the ability in the ability equipping gui. It should be something like "mod_id:ability_name" usually mod_id being the mineminenomi and as ability file name you should use ability_name.

If mod_id is not mineminenomi you would need to create another package inside of data foulder that would match mod_id, inside create abilities foulder and file with name of ability.

To sum things up to config ability you need to create file at: .../data/"mod_id"/abilities/"ability_name".json

## Fruit Awakening Setup
This stuff allows to set requirement to awaken fruit that if player has achived them his fruit will be awakened. If player hasn't achived requiremets but his fruit is awakened his fruit will be unawakened, so consider putting awakening as an alternative set of requirements

It is almost same system but insted of ability name you need to use item id.

So with advanced tooltips you need to look at fruit in your inventory, you will get something formated as "mod_id:fruit_id", where mod_id is again usually mineminenomi.

File you need to create would be at: .../data/"mod_id"/awakenings/"fruit_id".json

## Requirements
In all of the files you created should be an "requirements" parameter, an array of arrays.

If requirements parameter (later reffered as reqs) is fufulled the ability or awakening will be given to player.

Reqs counts as fufulled if at least one of arrays (later reffered as set) in it is fulfilled.

Set is fulfilled if all requiremets in it is counted completed (To learn how requirement are counted completed go to [All Requirements](https://github.com/WarCart/DF-Progression-Template/blob/main/README.md#all-requirements))

## Finishing your datapack
To load your datapack all you need is to compress your data directory **with the pack.mcmeta** to .zip file and put it to the datapacks foulder in your minecraft world.

Alternative is to use something like [Open Loader](https://www.curseforge.com/minecraft/mc-mods/open-loader) to compile your files on the go, that will help with testing

## All Requirements
### Doriki
_ability_progression:doriki_

Needs a number parameter, with name doriki, optionaly boolean named percentage

If percentage is true doriki should be in range from 0 to 1 otherwise from 0 to your doriki limit

If percentage is false this requirement counts as completed if player have equal or bigger doriki then number

If percentage is true this requirement counts as completed if player's doriki/limit is equal or bigger then number
### Haki XP
_ability_progression:haki_

Needs a number, called hakiXP, one of three haki types(BUSOSHOKU, KENBUNSHOKU or HAOSHOKU), named hakiType, optionaly a boolean called percentage

If percentage is true number should be in range from 0 to 1 otherwise from 0 to your haki xp limit

If percentage is false this requirement counts as completed if player have equal or bigger haki xp of given type then number

If percentage is true this requirement counts as completed if player's haki xp of given type/haki xp limit is equal or bigger then number
### Race
_ability_progression:race_

Needs a string, named race

Counts as completed if player have same race as given race
### Sub race
_ability_progression:sub_race_

Needs a string, named subRace

Useful if you need to have ability only be avalilable for some minks not for all

Counts as completed if player have same sub race as given string
### Style
_ability_progression:fighting_style_

Needs a string, named style

Counts as completed if player have same fighting style(swordsman, sniper, ect.) as given string
### Faction
_ability_progression:faction_

Needs a string, named faction

Counts as completed if player have same faction as given string
### Fruit
_ability_progression:devil_fruit_

Needs item id, named fruitID

Counts as completed if player have devil fruit given as item id
### Awakening
_ability_progression:awakening_

Counts as completed if player have awakened devil fruit (any)
### Haoshoku Haki
_ability_progression:haoshoku_born_

Counts as completed if player can unlock haoshoku haki in this world in any scenario
### Quest
_ability_progression:quest_

Needs Quest id, named questID

Counts as completed if player completed given quest
### Ability
_ability_progression:unlocked_ability_

Needs Ability id, named ability

Counts as completed if player have unlocked given ability
### Ability Used
ability_progression:ability_used

Needs Ability id, named ability, and Number called timesUsed

Counts as completed if player have used Ability Number times
### Loyalty
ability_progression:loyalty

Needs Number named loyalty

Counts as completed if player have Number or more Loyalty
### Default
ability_progression:default

Counts as completed if player would have unlocked the ability without the mod

If referenced from awakening would newer be completed
