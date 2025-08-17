Horus Heresy - BlackJack Edition.
============
## Overview ##

__What's this?__

This is NOT the data repo for the Horus Heresy 3rd edition. It is NOT maintained by the wonderful folks at BSData. Please go look at their fine work. 

This is a repo set up for a gaming group that wants to stick with the 2nd edition rules, and will include the new units backported for 2nd edition. It will additionally include units/rules from 1st edition, 40k, whatever else we like. It was imported from (https://github.com/BSData/horus-heresy-2nd-edition) , and all the hard work the BSData team put in is greatly appreciated.


__I found a bug!__ / *I have another request*

We're not accepting bug reports/suggestions at this time

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
