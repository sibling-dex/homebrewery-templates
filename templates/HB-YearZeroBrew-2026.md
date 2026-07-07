```metadata
title: YearZeroBrew
description: ''
tags:
  - meta:Theme
renderer: V3
theme: Blank

```

```css
/*=======---  Example CSS styling  ---=======*/
/* Any CSS here will apply to your document! */
@import url('https://fonts.googleapis.com/css2?family=EB+Garamond:ital,wght@0,400..800;1,400..800&family=Reddit+Sans+Condensed:wght@200..900&family=Reddit+Sans:ital,wght@0,200..900;1,200..900&display=swap');
@import url('https://fonts.cdnfonts.com/css/futura-pt');
@import url('https://fonts.cdnfonts.com/css/futura-condensed-pt');
@import url('https://fonts.cdnfonts.com/css/futura-condensed-extra');

*, *::before, *::after {
  box-sizing: border-box;
}

body {
  font-family: "EB Garamond";
  font-size: 9pt;
  line-height: 1.4;
  
  counter-reset: chapter-number footnote-number;
}

@media print {
  .page {
    height: 100vh;
    width: 100vw;
  }
}

.pages {
  &:has(.a4) .page {
    width: 210mm;
    height: 297mm;
  }
  &:has(.a5) .page {
    width: 148.5mm;
    height: 210mm;
  }
  &:has(.letter) .page {
    width: 8.5in;
    height: 11in;
  }
}
.pages:has(span[columns=1]) {
  .columnWrapper {
    column-count: 1 !important;
  }
}

.page {
  position: relative;
  padding: 2cm 0 0 0;
  column-gap: 1cm;
  
  contain: none;
  content-visibility: unset;

  .columnWrapper {
  display: block;
    width: 17cm;
    height: 23cm;
    margin: auto;
  }

  h1 {
    font-family: "Futura Condensed Extra";
    font-size: 37pt;
    font-weight: black;
    text-align: center;
    text-transform: uppercase;
    column-span: all;
    margin-bottom: 5mm;
    
    counter-increment: chapter-number;
        
    &::before {
      content: counter(chapter-number);
      display: flex;
      place-items: center;
      justify-content: center;
      color: white;
      background-color: black;
      width: 13mm;
      height: 17mm;
      margin: auto;
    }
  }

  h2, h3 {
    font-family: "Futura Condensed PT";
    text-transform: uppercase;
    margin-top: 1em;
  }

  h2 { font-size: 18pt; }
  h3 { font-size: 13pt; }
  h4 {
    display: inline-block;
    font-weight: 500;
    font-size: 1em;
    text-transform: uppercase;
    margin: 1em .5ex 0 0;
    
    & + p {
      display: inline;
      
      &::after {
        content: " ";
        display: block;
      }
    }
  }
  
  p,ul,ol,dl {
    hyphens: auto;
  }
  
  p {
    & + p {
      text-indent: 1.5em;
    }
    & + :not(p) {
      margin-top: 1em;
    }
  }
  
  blockquote {
    font-family: "Futura PT";
  
    p {
      font-size: 11pt;
      font-style: italic;
    }
  }
  
  ul,ol,dl {
    margin: 0 0 1em 0;
  }
  
  ul {
    list-style: "✦  ";
  }
  
  dl {
    padding-left: 0;
    
    dt {
      margin-left: 0;
    }
  }
  
  table {
    font-family: "Futura PT";
    margin: 0 0 1em 0;
    
    thead {
      color:white;
      background: black;
    }
    
    tbody{
      tr:nth-of-type(odd) {
        background: lightgrey;
      }
    }
    tr {
      border-top: .5pt solid black;
    }
    td, th {
      font-size: 8pt;
      font-weight: 600;
      padding: 2pt 1em 0 1em;
    }
    th {
      font-weight: bold;
      text-transform: uppercase;
    }
  }
 
  .columnSplit + * {
    margin-top: 0 !important;
  }
  .columnWrapper > *:first-child {
    margin-top: 0;
  }
  
  .caption,
  .box {
    display: block;
    font-family: "Futura PT";
      font-size: 8pt;
    padding: 2.5mm;
    
    h3 {
      font-family: "Futura PT";
      font-size: 8pt;
      text-transform: uppercase;
      margin-top: 0;
    }
    h4 {
      font-weight: 600;
    }
    p,ol,ul,dl {
      font-weight: 600;
      margin: 0;
    }
  }
  .toc {
    display: block;
    width: 5cm;
    margin: auto;
    
    h2 {
      font-family: "Futura Condensed Extra";
    }
    p, ul, ol {
      font-family: "Futura Condensed PT";
      font-size: 17pt;
      padding: 0;
      margin: 0;
      list-style-position: inside;;
      counter-reset: list-item;
      
      li {
        display: flex;
        align-items: baseline;
        justify-content: space-between;
        border-top: 1pt solid black;
        counter-increment: list-item;
          height: 1.2em;
        
        &::before {
          content: counter(list-item) ".";
          margin-right: 2pt;
        }
      }
      
      .inline-block {
        display: inline;
        flex-grow: 1;
      }
    }
  }
  .caption {
    margin: 2mm 0;
    border-top: 3pt double black;
  }
  .box {
    margin: 5mm 0;
    border: 1pt solid black;
  }
  .center {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-justify: center;
    text-indent: 0;
    margin: auto;
  }
  
  &::after,
  .chapterNumber,
  .pageNumber {
    position: absolute;
    display: block;
    left: 0 !important;
    right: 0 !important;
    font-family: "Futura PT";
    margin: 0 auto;
  }
  &::after {
    content: "";
    font-size: 11pt;
    bottom: 1cm;
    width: 17cm;
    height: 1.3cm;
    border-top: 1px solid black;
    background-image: url('https://freeleaguepublishing.com/wp-content/uploads/2023/11/Year-Zero-Engine-license-logo-black.png');
    background-size: 1.32cm 1cm;
    background-repeat: no-repeat;
    background-position: center bottom;
  }
  .chapterNumber {
    text-align: center;
    text-transform: uppercase;
    font-weight: bold;
    padding: 0 2mm;
    width: 17cm;
    height: 1cm;
    top: 1cm;
    
    &.auto::before {
      content: counter(chapter-number) " – ";
    }
  }
  .pageNumber {
    text-align: center;
    text-transform: uppercase;
    font-weight: bold;
    padding: 0 3mm;
    width: 17cm;
    height: 1cm;
    bottom: 1cm;
  }
  &:nth-of-type(even) {
    .pageNumber {
      text-align: left;
    }
  }
  &:nth-of-type(odd) {
    .pageNumber {
      text-align: right;
    }
  }
  
  a[href^="#fn"] {
    text-decoration: none;
    counter-increment: footnote-number;
    
    &::after {
      display: inline;
      content: counter(footnote-number) " ";
      vertical-align: super;
      font-size: smaller;
    }
  }
  
  .footnote {
    position: absolute;
    font-size: 9pt;
    bottom: 2.5cm;
      
    &::before {
      display: inline;
      content: counter(footnote-number) " ";
      vertical-align: super;
      font-size: smaller;
    }
  }
}









```

{{wide,center,width:10cm
![](https://freeleaguepublishing.com/wp-content/uploads/2023/11/Year-Zero-Engine-license-logo-black.png){width:8cm}

::::

> Year Zero Engine Standard Reference Document v1.0 

> Authored by Tomas Härenstam

> © 2023 Fria Ligan AB

::

{{font-size:12pt,margin-bottom:1em
Permission to copy, modify and distribute this text is granted solely through the Year Zero Engine Free Tabletop License, [available here](https://freeleaguepublishing.com/wp-content/uploads/2023/03/Year-Zero-Engine-License-Agreement.pdf).
}}
{{font-size:12pt
You should read the FTL and understand its terms before using this material.
}}

::

{{toc
## Contents

1. INTRODUCTION         {{...}}  2
2. PLAYER CHARACTERS    {{...}}  4
3. SKILLS & SPECIALTIES {{...}}  8
4. COMBAT & DAMAGE      {{...}} 15
5. MAGIC                {{...}} 30
6. TRAVEL               {{...}} 41
}}

}}

\page

# Introduction

Welcome to Year Zero. This document contains the core Year Zero Engine mechanics for tabletop roleplaying, used in several Free League games.

## THE BASICS

This section introduces some key concepts in roleplaying, and how they are used in games using the Year Zero Engine.

### THE PLAYERS

Each player except one controls a player character (PC). You decide what your PC thinks and feels, what they say and do -- but not what happens to them. It is your job as a player to immerse yourself in your PC. They may be an adventurer in a faraway fantasy world -- but they are still, at heart, a person with feelings and dreams, just like you. Try to imagine -- how would you react if you were in their shoes? What would you do? The player characters are always the protagonists of the story. The game is about you. Your decisions, your adventures.

### THE GAMEMASTER

The final player is the Gamemaster, the GM. They describe the game world to you, they portray the people you meet, and they control the enemies you fight. The game is a conversation between the players and the GM, back and forth, until a critical situation arises where the outcome is uncertain. Then it’s time to break out the dice -- read more about this in Chapter 3.

It is the GM’s job to put obstacles in your path and challenge your PCs, forcing them to show what they’re really made of. But it is not up to the GM to decide everything that happens in the game -- and above all, not how your story is supposed to end. That is decided in the game. That is why you are playing the game -- to find out how your story ends.

{{box
### ABBREVIATIONS

PC = Player Character <br>
NPC = Non-Player Character <br>
GM = Gamemaster <br>
YZE = Year Zero Engine <br>
SRD = Standard Reference Document
}}


{{box
### YOU AND OTHERS

Most of the rules in this document are written in the second person -- i.e., speaking to “you.” Rules that apply to you also apply to others in the game, both PCs and NPCs, unless explicitly stated otherwise.
}}

## KEY FEATURES
The Year Zero Engine was originally developed as the ruleset for Mutant: Year Zero, but has been further modified and adapted to a wide range of games with different themes and settings. Yet, six core features of the game remain the same in all iterations. These are listed and explained below.

### ACCESSIBLE
The basics of the Year Zero Engine are very easy to learn. It is easy to teach to new players, making the barrier to play very low. Complexity and depth are added piece by piece, offering more choices to the player as they gain more insight into the system.

### FAST AND DECISIVE
The Year Zero Engine is fast, quickly producing meaningful results by removing any dice rolling, bookkeeping and calculations that don’t move the action forward. Year Zero Engine combat systems are often deadly, pushing conflicts to decisive moments. The risks are high, and PCs are rarely safe from danger no matter how experienced they are.

### RISKS & REWARDS
In the Year Zero Engine, you can increase your chances significantly by pushing your roll -- i.e. re-rolling the dice -- but pushing always comes with a cost. This dynamic constantly pushes you to weigh risks and rewards, and makes the Year Zero Engine particularly suited for harsh, survival-focused games.

{{box
### THESE SIDEBARS
Sidebars such as this one are interspersed throughout this rules text. They typically contain rules variants, comments and advice on how to play.
}}

{{pageNumber,auto}}
\page

### PLAYER-CENTRIC
In Year Zero Engine games, the players and their characters are at the heart of the story. The PCs are the protagonists of the story, never the NPCs. The rules focus on the PCs and their actions, while NPCs are handled quickly and effectively by the Gamemaster. The system is designed to always present the players with meaningful choices.

### STORY DRIVEN
Roleplaying is about creating stories, memorable moments at the gaming table that you’ll remember for years to come. The Year Zero Engine is designed to produce dramatic effects that will push your story forward and make it take unexpected turns.

### ADAPTABLE
The Year Zero Engine is designed to be very adaptable for different play styles, themes, and game settings. By using skills and talents in a modular fashion, the system creates building blocks that are very easily added, removed, and re-engineered.

## DICE POOLS vs STEP DICE
Every Year Zero Game is different, but two main forks can be identified – the original dice pool variety (using pools of D6s) and the more recent step dice version (using a variety of polyhedral dice). Both versions are included in this SRD. When designing your game, you can choose whichever version you
prefer.

## TOOLS OF THE GAME
Year Zero Engine games typically give you plenty of room for improvisation and creativity. Yet they also provide a number of tools to help you create your own story.

### CHARACTER SHEETS
To document your character, you use a character sheet. This document does not include a character sheet, as any YZE game will need a sheet adapted to the specific rules version and game setting. How you create your character will be described in the next chapter.

### DICE
As a character in a Year Zero Engine game, you will have to take risks. Sooner or later, you will end up in situations where the outcome is uncertain, no matter how skilled you are. It’s time to break out the dice. Regular six-sided dice (also called D6) are required to play the dice pool version YZE, preferably 10–15 of them, while the step dice version of YZE uses polyhedral dice, including D8, D10 and D12. Some rules variations require dice in different colors.

\column

{{box
### ROLLING DICE 
The rules will sometimes ask you to roll D3, 2D6, D66, and D100. D3 means you roll a D6 and divide the result by two, rounding up. 2D6 means you roll two six-sided dice and add the results. D66 means you roll two D6. The first die represents the tens digit and the second die represents the ones digit. That generates a result between 11 and 66. D100 means you roll two D10. The first represents the tens digit and the second the ones digit. A double zero counts as 100. You can even roll D666, by rolling three six-sided dice. The first die then counts as the hundreds digit, the second as the tens digit and the third as the ones digit.
}}

### CUSTOM CARDS
Another useful accessory for YZE games is a custom card deck. The cards can be used as reference sheets for gear or NPCs, but also to randomize initiative in combat – read more about this in Chapter 4.

{{caption
### MEASURING TIME

Three units are used to measure time in YZE games, depending on the situation at hand. See the adjacent table. The exact duration of a round, stretch and shift can vary depending on the situation. It’s the GM’s job to track time and determine when another round, stretch or shift has passed. There are typically four shifts in a day: morning, day, evening, and night.
}}

| UNIT OF TIME | DURATION     | USED IN     |
|:-------------|:-------------|:------------|
| Round        | 5–10 seconds | Combat      |
| Stretch      | 5–10 minutes | Exploration |
| Shift        | 5–10 hours   | Travel      |


## PLAYING SAFELY
In YZE games, you are largely in control of the story, and with this comes responsibility. The player characters will face great danger and difficult challenges, but no player should find the situations they experience unpleasant or offensive. It is important that everyone around the gaming table is having fun and feeling safe.

Before starting the game, talk things through and see if someone wants certain subjects to be kept out of the game. Always respect a player who wants to pause and discuss what is happening in the game, or even leave the table if the player so chooses. And you may also want to talk about what happened after the game session.

{{chapterNumber,auto Introduction}}
{{pageNumber,auto}}
\page

# PLAYER CHARACTERS

Your player character (PC) is your most important asset in any
Year Zero Engine game. They are your avatar, your eyes and
ears in the world. But they, in return, depend on you making
the right decisions for them. Take your PC seriously and play
them as if they were a real person. It’s more fun that way. At
the same time, don’t try to protect your PC from every conceivable danger. The goal of the game is to create a good story.
For that to happen you need to take risks.

During the course of the game, your PC will change and
develop. Their skills and specialties can be developed through
experience, but you can also discover how their personality
changes and is formed in a way that cannot be measured by
numbers on a page. This is when your player character truly
comes alive.

### CHARACTER SHEET
To create your player character, you need a character sheet.
This SRD does not include a character sheet, as any YZE
game will need a sheet adapted to the specific rules version
and game setting.

{{box
### SEVEN STEPS OF CREATION
How you create your player character is explained in detail in
this chapter. The summary below is a helpful overview. Grab a
character sheet, a pencil, and follow these steps:

1. Choose your archetype.
2. Determine your attributes.
3. Determine your skills.
4. Choose your starting specialty.
5. Determine your personality traits.
6. Pick your gear.
7. Choose a name.
}}

## ARCHETYPE
Most Year Zero Engine games have some type of character
archetypes to choose from. The archetypes – which can also be
called “roles,” “professions,” or “careers” – are based on the
game world, and help the players grasp the setting.
The archetype determines what type of person you are,
your background and role in the group. Your archetype will
influence your attributes, skills, specialties, and starting gear.
Archetypes can feel stereotypical, and they are meant to
be. Picking an archetype is a quick way for yourself and the
other players to get an immediate feel for your character. But
remember that your character is more than just their archetype. The archetype is just a starting point toward creating a
unique player character.

## ATTRIBUTES
Your character has four attributes that indicate your basic
physical and mental capabilities. Your attributes are used
when you roll dice to perform actions in the game, and also
determine how much damage and stress can withstand before
you become broken. Read more about this in Chapter 4.

- STRENGTH: Raw muscle power and brawn
- AGILITY: Body control, speed, and motor skills
- WITS: Sensory perception, intelligence, and sanity
- EMPATHY: Personal charisma and ability to manipulate others

### :fas_dice_d6: :fas_dice_d6: :fas_dice_d6: DICE POOL ATTRIBUTES
In the dice pool version of YZE, human attribute scores range
from 1 to 5. See the table below.


#### STARTING SCORES:
Typically, you can distribute 14 points across your attributes. You can assign no less than 2 and no more than 5 points to any attribute.


#### KEY ATTRIBUTE:
In many Year Zero Engine games, each archetype has a “key attribute.” You can have a maximum score of 5 in your key attribute – other attributes are limited to a maximum of 4.


| ATTRIBUTE | DESCRIPTION   |
|:----------|:--------------|
| 5         | Extraordinary |
| 4         | Capable       |
| 3         | Average       |
| 2         | Below Average |
| 1         | Feeble        |


### :df_d8: :df_d12: STEP DICE ATTRIBUTES
In the step dice version of YZE, attributes are rated on a scale
from A to D. Each attribute rating is connected to a specific
die type. See the table below.

{{pageNumber,auto}}
\page

#### STARTING SCORES:
You start with a baseline of C in all four attributes. You may then make three increases, of one step each, up to A. You can increase any attributes you want. You can gain one extra increase by decreasing one attribute from C to D.

#### DIE SIZE:
A term sometimes used in the step dice rules text is “die size.” This simply means the highest possible result on a particular die type. The die size of a D6 is 6, the die size of a D8 is 8, etc.

| ATTRIBUTE | DIE TYPE | DIE SIZE | DESCRIPTION   |
|:----------|:---------|:---------|:--------------|
| A         | D12      | 12       | Extraordinary |
| B         | D10      | 10       | Capable       |
| C         | D8       |  8       | Average       |
| D         | D6       |  6       | Feeble        |

## HEALTH & RESOLVE
Your attributes determine how much damage and stress you
can take before being broken and thus taken out of action. In
some YZE games, this is measured by your Health and Resolve scores. Read more about how those work in Chapter 4.

### :fas_dice_d6: :fas_dice_d6: :fas_dice_d6: DICE POOL RATINGS

- HEALTH: Your starting Health equals the average of your
Strength and Agility scores, rounding fractions up, plus
one.

- RESOLVE: Your starting Resolve equals the average of your
Wits and Empathy scores, rounding up, plus one.

### :df_d8: :df_d12: STEP DICE RATINGS

- HEALTH: Your starting Health equals the sum of the die
size for your Strength and Agility scores divided by 4,
rounding fractions up.

- RESOLVE: Your starting Resolve equals the sum of the
die size for your Wits and Empathy scores divided by 4,
rounding up.

### VARIATIONS
There are other ways to manage damage and trauma within
the Year Zero Engine, which don’t require Health or Resolve
scores at all. Two variants are described below:

- JUST HEALTH: Some YZE games have only a Health rating, not Resolve.
- ATTRIBUTE DAMAGE: You suffer damage directly on your
attributes, reducing your effectiveness. You are broken if
any attribute is reduced to zero.
- CONDITIONS: Each point of damage gives you a condition
(page 21) and you are broken when you have suffered a
set number of conditions.


## SKILLS
Your skills are the knowledge and abilities you have acquired
during your life. They are important, as they determine, along
with your attributes, how effectively you can perform certain
actions in the game. There are twelve basic skills in the YZE
SRD, and they are all described in detail in Chapter 3. Some
Year Zero Engine games have different or additional skills.

### DICE POOL SKILLS
In the dice pool version of YZE, skills are measured by skill
level on a scale from 0 to 5. The higher the number, the better.

#### NO SKILL LEVEL?
You can always roll for a skill even if you have no level in that skill – in that case you only use the associated attribute for the skill in question, and gear. Read more about how skills work in the next chapter.

#### STARTING SKILLS:
Typically, you can distribute 10 points across your starting skills. In many Year Zero Engine games, each archetype lists a number of associated skills. You can only start the game with a skill level 3 in your archetype skills – all other skills are limited to a starting level of 1.

| SKILL LEVEL | DESCRIPTION |
|:------------|:------------|
| 5           | Elite       |
| 4           | Veteran     |
| 3           | Experienced |
| 2           | Trained     |
| 1           | Novice      |

### STEP DICE SKILLS
In the step dice version of YZE, skill levels are measured on a
scale from A to D just like attributes. Just like for attributes, each
skill level is connected to a specific die type. See the table below.

#### NO SKILL LEVEL?
You can generally roll for a skill even if you have no level at all in that skill – in that case, only use the associated attribute for the skill in question.

#### STARTING SKILLS:
Choose one B level skill, two C level skills, and three D level skills. Your B level skill must typically be one listed by your archetype. You can choose your C and D level skills freely.

| SKILL LEVEL | DIE TYPE | DIE SIZE | DESCRIPTION |
|:------------|:---------|:---------|:------------|
| A           | D12      | 12       | Elite       |
| B           | D10      | 10       | Veteran     |
| C           |  D8      |  8       | Experienced |
| D           |  D6      |  6       | Novice      |


{{chapterNumber,auto PLAYER CHARACTERS}}
{{pageNumber,auto}}
\page

## SPECIALTIES
Specialties are tricks, moves and minor abilities that give you a small edge. In some Year Zero Engine games, they are instead called talents. Specialties are more narrow than skills and give you a way to fine-tune your character.

You can typically pick one specialty when creating your character, but your archetype determines which specialties you can choose from. You can learn more specialties during the
course of the game.

You can find a few examples of specialties in Chapter 3
(page 8 and forward), but most specialties are tuned to the
specific game and its setting.

## PERSONALITY TRAITS
Year Zero Engine games use a variety of methods to give your PC unique personality traits beyond the numerical stats. Some examples follow below.

#### PRIDE:
Something specific that defines your character and makes them stand out. It can be an ability, an event in your past, or something else. Once per game session, you may check your Pride to get one automatic success in a dice roll. You must justify how your Pride helps you.

#### WEAKNESS:
An Achilles heel that can get you into trouble somehow. Your weakness adds depth and personality to your character and can also be used by the GM to create challenges for you. Roleplaying according to your weakness gives you extra XP at the end of the session.

#### DARK SECRET:
Something that you have experienced before the game begins that has left its mark on you or still threatens you in some way. Your Dark Secrets is primarily a tool for the GM to create stories with, but can also earn you extra XP you get after a game session.

#### BIG DREAM:
This is your PC’s main long-term goal in the game. During play, you will gain extra XP if you risk or sacrifice something significant to move closer to seeing your big dream realized.

#### RELATIONSHIPS:
Your relationship with each of the other PCs, described with a short sentence for each. Your relationships are mainly used by the GM to create interesting challenges for you in the game.

#### BUDDY:
The PC in the group that you feel closest to. Making a sacrifice or taking a big risk for your Buddy will earn you extra XP.

\column

## GEAR
Many (but not all) Year Zero Engine games are focused on survival, and having the right gear will help you do that. You must write down all the items you are carrying. Write down one item per row in the Gear section on your character sheet.
If it’s not listed on your sheet, you don’t have it with you.

#### STARTING GEAR:
Your archetype typically determines what gear you can choose from at the start of the game. Clothes and gear used to carry other gear does not count toward your encumbrance and does not need to be noted down.

### ENCUMBRANCE
You can unhindered carry a number of regular items up to your carry limit, which is equal to double your Strength rating (dice pool system) or equal to your Strength die size (step dice system). Heavier items count as two, three or more regular items. Light items count as ½ or even ¼ regular items. 

#### BACKPACK:
If you have a backpack, you can use it to carry an additional number of regular items equal to your carry limit. However, carrying a backpack gives you a −2 modifier on all Mobility skill rolls (page 12). The backpack itself does not affect your encumbrance.

#### TINY ITEMS:
Items with negligible weight, that can be hidden in a closed fist, are called tiny. They are so small they don’t affect your encumbrance at all. Tiny items still need to be listed on your character sheet.

#### MOUNTS & VEHICLES:
If you have a horse or other mount, you can let it carry some of your gear. The animal can carry a number of regular items up to its own carry limit, and twice that number if you dismount and lead it. Vehicles can store even more gear.

{{box
### ENCUMBRANCE VARIANTS
The YZE encumbrance rules can be modified according to the type of game. Two options follow below.

Weapons at Hand: In this variant, you can have up to three hand-held weapons at hand, which means that they are kept in a sheath or holster or otherwise readily available for use in combat. Weapons kept at hand do not count toward your encumbrance. Any helmet or armor worn on your body also does not count toward your encumbrance. This variant reduces record-keeping.

#### NO ENCUMBRANCE:
If your YZE game is not focused on gear, you can do away with encumbrance rules
}}

\page

### CONSUMABLES

A special category of items in the game are called consumables. It can be food, water, ammunition, arrows, torches, air
supply, electric power or others – depending on the setting of
the game. There are two main ways to manage consumables.

#### TRACKING:
The obvious way to manage consumables is to simply track them on your character sheet. Write down every ration of food, arrow or bullet, and reduce the amount as they are used up. A ration of food, ten arrows, or 25 bullets typically count as ¼ of a regular item.

#### SUPPLY ROLLS:
To emulate the scarcity of consumables without tracking each and every unit, you can use supply rolls. For each consumable in the game, you have a Supply rating. A higher rating is better. For encumbrance, each consumable counts as one regular item no matter the Supply rating.

At regular intervals (depending on the consumable in question), you need to make a supply roll. This means rolling a number of D6 equal to the current Supply rating – but never more than six dice. For each 1 rolled, the Supply rating is reduced by one. When the Supply rating reaches zero, you’re out of the consumable.

If you want to give a consumable to another person, simply increase the recipient’s Supply rating as many steps as you decrease your own.

## EXPERIENCE
The things you learn during the game are measured in Experience Points (XP). You receive XP after the end of each game session. Talk it through and let the whole group discuss what has happened. For each of the below questions that you can reply “yes” to, you get one XP:

- Did you participate in the game session?
- Did you explore a new location?
- Did you defeat one or more dangerous adversaries?
- Did you overcome an obstacle without using force?
- Did you act according to your weakness/dark secret/big dream/relationships (page 6)?
- Did you perform another extraordinary action of some kind?
- Specific games can award XP for other actions as well.

The GM has the final word when it comes to how much XP each character should get.

### SPENDING XP
You can use your XP to improve your skills and specialties, or to learn new ones. You can only spend XP when your PC gets a chance to rest, or between game sessions.

\column

#### SKILLS:
To increase a skill level by one step costs a number of XP indicated in the tables on page 7. You can only increase a skill level one step at a time. Learning a new skill (at skill level 1/D) costs 5 XP.

In addition, to raise a skill level or gain a new skill, you must have used the skill and succeeded at least once since your last increase. Make a mark by the skill on the character sheet to indicate this. Only meaningful skill rolls where something is truly at stake count for this purpose. The GM has final say. As an alternative to making a skill roll, you can be instructed for one shift by a teacher with a higher skill level than you.

#### SPECIALTIES:
Learning a specialty always costs 10 XP, but also requires a teacher – a PC or NPC who already knows the specialty – instructing you for at least one shift. After the shift, the teacher makes a Persuasion roll. If they fail, you learn nothing this shift. You keep your XP and the teacher can try again in another shift.

### :fas_dice_d6: :fas_dice_d6: :fas_dice_d6: SKILL LEVEL INCREASE
| TARGET LEVEL | XP COST |
|:----30%-------|:--------|
| 1 |  5 |
| 2 | 10 |
| 3 | 15 |
| 4 | 20 |
| 5 | 25 |

### :df_d8: :df_d12: SKILL LEVEL INCREASE
| TARGET LEVEL | XP COST |
|:----30%------|:--------|
| D |  5 |
| C | 10 |
| B | 15 |
| A | 20 |

### PERSONALITY TRAITS
After any session, you may change personality traits such as your pride, weakness, dark secret, big dream, and relationships. Try to connect the change to something that has happened during the course of the game.