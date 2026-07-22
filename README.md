Horus Heresy - BlackJack Edition.
============
## Overview ##

__What's this?__

This is NOT the data repo for the Horus Heresy 3rd edition. It is NOT maintained by the wonderful folks at BSData. Please go look at their fine work. 

This is a repo set up for a gaming group that wants to stick with the 2nd edition rules, and will include the new units backported for 2nd edition. It will additionally include units/rules from 1st edition, 40k, whatever else we like. It was imported from (https://github.com/BSData/horus-heresy-2nd-edition) , and all the hard work the BSData team put in is greatly appreciated.


__I found a bug!__ / *I have another request*

We're not accepting bug reports/suggestions at this time

## Changelog

Changes from Second Edition:

### Legiones Astartes
- Added Saturnine Praetor, allowing Concussion Hammer, War Axe, Disruption fist, plasma blaster and regular ranged Saturnine Weapons
- Added Saturnine Terminators, allowing both Saturnine Melee and ranged weapons, also allowed standard terminator ranged and melee    weapons to be taken
- Added Saturnine Command Squad
- Added Disintegrator weapons for Vets
- Added Araknae Weapon platform into Fortifications
- Added Saturnine Dreadnought
- Added Veteran Heavy Support squad with Disintegrator blaster and Heavy Disintegrator into Elites
- Modified Caestus Assault Ram Misercorde back to HHv1 rules, changed transport capacity to 12. puts it back in line with intended use
- Added Centurion in Saturnine Armour
- Added Veteran Breacher Squad to elites
- Added Bayonets and Chain Bayonets to breachers, veteran breachers and Phalanx Warders, addendum to boarding shileds to allow their use
- Contemptor Dread now ws4/bs4, Deredo ws4/bs5, Leviathan ws5/bs4
- Updated Dreadnought weapon profiles to match Liber Melias
- Updated expanded options to toggle 40k units, 3rd ed units, expanded RoW and FoC and Liber Melias options on/off (Note, the units in there havent all been included in the toggle, just the toggle itself and a few units for testing)
- Added Destroyer Company RoW, Destroyer units added to troops choice for this etc 
- Changed Rad-Phage to apply to the Unit, not the model
- Gave Cavalry Battlehardened
- Added Rad missiles to all missile launchers and gravis missile maunchers when using Destroyer RoW, including Aiolos Missile Launcher and Whirlwind missile launcher
- Added Rad grenade option for all sgts when using Destroyer RoW 
- Scouts given Line
- Tactical Support Squads given Line
- Disintegrator rifle and blaster dropped 5 points, vet sgts given to all standard squads
- Added Chainaxes for 5pts to Assault squads (due mk2 kit having just that option, WE chainaxes still free)

### Mechanicum/Titan Legions
- Added Galvanic rifle from 40k to Secutarii Peltasts so Regular rangers can be proxied in, Radium Jazzail also added
- Added new Cyberthuergic Arcana discipline, Artificia Gladatoris - Adds Melee Focus, ability to add +1WS to automata
- Added Dunecrawler from Codex Skitarii 7th Edition, with all the weapon options that entails. added as an Armiger type to HS for Titan legions
- Changed void shields so they no longer suck
- Added Sydonian Dragoons to FA slot for Titan legions
- Added Ironstrider Ballistarius to HS for Titan Legions
- Added Sicaran Infiltrators to Elites for Titan Legions
- Added Transuranic Arquebus and added new unit - Secutarii Pellentesque 1-3 skitarii with Arquebus'
- Added Herax pattern automata maniple from Panoptica Liber Ingenium
- Added Accipiter Pattern-Automata Squadron based on the Herax, to represent pre corrupted Foetid Blight drone
- Made Both Secutarii units Line
- Added Galvantic Blaster/Plasma Blaster to Secutarii Peltasts
- Added VenomCrawler to Dark Mechanicum elites choice, similar to a Blood Slaughterer


## Standards

### Creating units
#### Names
In general, we remove the "Legion" prefix from units, unless that unit has a non-legion equivalent such as Legion Baneblade

We create a unit entry for each unit, and a model entry within that unit (even if it's a single model unit).
This allows us to get an accurate model count and keeps everything consistent.

On UNITS we default them to hidden and add a modifier with constraint to set "Hidden to False" if "Equal to 1 selection in force of <> on". Ensure "And all child selections is checked".
On UPGRADES, we default the option to not hidden, and set "Hidden to True" if the "off" condition is selected.

#### Important reminders:
These are requirements on a unit to maintain rites of war:
- Solar Auxilia and Imperialis Militia units need "SA or IM Unit" for rites of war that count that number of units.
- - Lords of war should be excluded from this as they won't be in the "allied detachment"

### .cattemplate? and what are all the template_id_ comments?
A .cattemplate file is a .cat file, renamed to .cattemplate, used by [BSCOPY](https://github.com/nstephenh/BSCopy)

We used bscopy to copy all 18 legions after implementing the first one. 
We didn't maintain the template so it's not recommended to re-run bscopy

## Tests
GitHub actions will load configured lists in [tests](tests) and ensure they produce the expected outcome. 
To add a new test:
1. Export a roster from NewRecruit or BattleScribe
2. Rename that roster from .ros to .test and place it in [tests](tests)
3. Add a new case to [tests.py](tests/tests.py): 
    ```python
    def test_NameOfTest(self):
        self.load_list('Name of Roster file with no extension')
        errors = self.get_error_list()
        self.assertEqual(0, len(errors), "This list has validation errors")
    ```
   * There are other tests, such as checking for points on a specific unit. Look through the code for examples.
4. Run the unit tests with python, or create a pull request to have GitHub run them automatically. 
   * To run them locally, install python and the packages `selenium` and `webdriver-manager`, and Google Chrome.

[BSData.net]: https://www.bsdata.net/
[bug report]: https://github.com/BSData/horus-heresy/issues/new/choose
