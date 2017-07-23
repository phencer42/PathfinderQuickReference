# Pathfinder Quick Reference
A better quick reference app for Pathfinder
Developed and maintained by Sterling Huber, phencer42@gmail.com

----------------------------------------------------
# Overview

Pathfinder Quick Reference (PQR) is an app designed for quickly looking up relevant information to your Pathfinder tabletop sessions as quickly as possible. It is planned from the bottom up to provide the most relevant information to the user as quickly as possible: saving throw types for spells, the damage that a necklace of Fireballs type III does with its largest gem, whatever the hell shaken actually does.

This app will be using d20pfsrd.com as its main source of information. If other sources are included this will be detailed in the this documented as well as in the app.

This document and code is still very very early in its design and is very subject to change. It's made by one developer in his spare time but if things start having any cohesion and you see problems let me know at phencer42@gmail.com.
----------------------------------------------------
# Structure

PQR runs with a fairly simple Android Java front end with a search library interfacing with the backend SQL database. I have yet to decide on a search library, recommendations are welcome.

----------------------------------------------------
# Content Types

Below are the content types that this app will search through as well as the fields that will be detailed in the database for each. Fields with a $ next to them will be displayed in the main search results without having to click the field for more details. Fields with a ~ next to them will not be present for all elements of that type.

Spells
-Name$
-Class Level$
-Elemental School~$
-Quick Description$
-Casting Time$
-Range$
-Target~$
-Effect~$
-Duration$
-Components$
-Costs Money
-School
-Spell Resistance
-Full Description

Wondrous Items
-Name$
-Slot$
-Cost$
-CL
-Aura
-Weight
-Construction Requirements
-Quick Description$
-Full Description

Conditions
-Name$
-Quick Description$
-Full Description

Weapons
-Name$
-Category$
-Cost$
-Dmg (S)$
-Dmg (M)$
-Critical$
-Range$
-Weight
-Damage Type
-Special
-Has Detailed Description$
-Detailed Description

Armor & Shields
-Name$
-Cost$
-Armor/Shield Bonus$
-Maximum Dex Bonus
-Armor Check Penalty$
-Arcane Spell Failure Chance
-Speed 30 ft.$
-Speed 20 ft.$
-Weight
-Complete Description

Class
-Name$
-Role
-Alignment
-Hit Die$
-Starting Wealth
-Class Skills
-Skill Ranks Per Level$
-Class Table$
-Weapon Proficiency$
-Armor Proficiency$

Class Special Abilities
-Name$
-Quick Description$
-Full Description

Feats
-Name$
-Prerequisites$
-Quick Description$
-Category
-Full Description

Possibly more

----------------------------------------------------
# Front End

The front end will display a search bar at the top of the screen and the past several searches listed below. Upon swiping right from the left side, a browse menu will appear. This browse menu will contain categories of information to browse as well as a help and information section.

The search bar once typed in will visually clear out the previous searches listed and immediately provide Google-instant-style the most relevant results from all categories across the database. This will be presented in the same format that the results in the "previous searches" section are displayed. When one target is clicked it will change the screen to one providing the details on the target selected accurate and complete as possible to d20pfsrd.com standards.

----------------------------------------------------
# Search Results

Search results will display mostly incomplete information on each target to provide the most relevant information for standard play for as many elements as possible in a search. The idea is that the element will need to be clicked on for only very specific instances and in most cases you'll get all the info you need from the main search page.

----------------------------------------------------
# The Database

The database on the back end is a SQLite database. SQLite is chosen for both how nicely it plays with Java but also because it will allow us to store the entire database in the app locally so it won't require an internet connection for use.

Each table of the database will represent a different content type (i.e. spells, conditions, etc). This will allow the many different fields required for each content type to be handled in the nice organized way that SQL allows.

----------------------------------------------------
# Design Notes

None at this time.
