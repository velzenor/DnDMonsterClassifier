# Intro
Dungeons and Dragons (D&D) is a tabletop role-playing game that often involves fighting monsters. While setting up the game, a game master (GM) has access to a compilation of monsters that their players may encounter. Every possible monster in the game has a *stat-block*, a summary of that creature's game statistics and abilities (e.g. it'll say the amount of damage dealt by a dragon's fire breath). Within these, monsters are given a challenge rating (CR), usually from zero to thirty, that attempts to quantifiy their difficulty if fought. The GM uses this measure to build *encounters* for their players, and thus control the sense of challenge throughout the narrative.

Moreover, a GM may want to create custom monsters to exactly fit their story. In such cases, assessing an accurate CR for such monsters isn't always simple.

# Project Goal
Train a machine learning model that assesses the CR of creatures in D&D.

# Interactive Demo
A web-based interactive demo, that lets you estimate the CR of a custom monster, is available [here](https://colab.research.google.com/drive/1IehnwiZQxBs_XjkPQP7x-Vqaua7uhcm1?usp=sharing).

# Dataset
Attribution: *This work includes material from the System Reference Document 5.2.1 (“SRD 5.2.1”) by Wizards of the Coast LLC, available at https://www.dndbeyond.com/srd. The SRD 5.2.1 is licensed under the Creative Commons Attribution 4.0 International License, available at https://creativecommons.org/licenses/by/4.0/legalcode.*

Data was collected directly from the SRD, a document published by the makers of D&D which contains over 300 monsters from the game. It was compiled into tabular form, which is available within this project as [`monsters.csv`](https://github.com/velzenor/DnDMonsterAssessor/blob/24c0b7d035bac84f0a6a3ac0a9e0fb9579ac161b/data/monsters.csv). 

The feature descriptions are as follows:

| Feature | Desciption |
| --- | --- |
| Name | The monster's name |
| SizeType | Size and type (e.g. Medium Beast) |
| Align | Alignment |
| AC | Armor class |
| Init | Initiative with default result in parenthesis |
| HP | Hit points with hit dice formula in parenthesis |
| Multiattack | A boolean that's True if it has multiattack |
| LegAct | A boolean that's True if it has legendary actions |
| LegRes | A boolean that's True if it has legendary resistances |
| Speed | The monster's speeds delimited by commas |
| CR | Challenge rating |
| PB | Proficiency bonus |
| *Ability Scores* | The score, modifier and saving throw bonus delimited by slashes |



# Model and Training
The project uses a Random Forest regressor as implemented in the sci-kit learn package.

