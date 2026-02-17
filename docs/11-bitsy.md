---
title: ALT-Engine Micro Game Jam - Bitsy
---


<script>hljs.highlightAll();</script>
<!--jump to anchor tag adjusted to header height offset-->
<script>
// Get the header element
let header = document.querySelector('header');

// Get the height of the header
document.querySelectorAll('a[href^="#"]')
.forEach(function (anchor) {
    anchor.addEventListener('click', 
    function (event) {
        event.preventDefault();

        // Get the target element that 
        // the anchor link points to
        let target = document.querySelector(
            this.getAttribute('href')
        );
        
        let headerHeight = header.offsetHeight*2;
        
        let targetPosition = target
            .getBoundingClientRect().top - headerHeight;

        window.scrollTo({
            top: targetPosition + window.scrollY,
            behavior: 'smooth'
        });
    });
});
</script>

# ALT-Engine Micro game jam

---

<embed type="text/html" src="../bitsyjam/on_a_tuesday_afternoon___.html" width="100%" height="500">

## What is Bitsy? 

This "tiny" engine was made by Adam Le Doux who writes:

> hi! bitsy is a little editor for little games or worlds. the goal is to make it easy to make games where you can walk around and talk to people and be somewhere.

<br>

## What are we doing today?

By the end of class, we'd have made a Bitsy game in groups of 2-3 and (hopefully) also do a class presentation of our projects! The time limit is part of the game jam challenge ✨  

<br>

### Schedule

| Time | Activity |
|---|---|
| 0900 | 🍎 Intro to Game Jam activity and Bitsy game engine |
| 0920 | 💡 Brainstorm Ideas |
| 0930 | 🗳️ Voting for Ideas |
| 0940 | 🤝 Form Groups |
| 0950 | ⚒️ WORK WORK WORK |
| 1120 | ⏱️ TIMES UP -- Submit and Present ! |
| 1150 | 🏁 Game Jam end ! |

### Prompt

Generate your bitsy game ideas with the following sentence:

> a **(noun)** is wandering in **(a place)**. upon **(arriving at / encountering)** **(a specific location / object / person in the place)**, a story about **(a topic)** unfolds.

<br>

We’ll return to this in a moment. But first how do you do things in bitsy?

## Intro to Bitsy

> Here's our Tutorial Notes: [**Bitsy Workshop**](https://docs.google.com/document/d/1R9Om07CeanjrNTW1GPOvXREeEI92x3VFQSNvYGQSTds/edit?usp=sharing)

![](./img/bitsy.jpg)

<br>

## Let's brainstorm some ideas! 

You’ve gotten a quick taste of the engine, so let’s come up with some ideas!

1. Grab a paper.
2. Write a version of this sentence with the parenthesis filled in with your own ideas:
    
    > a **(noun)** is wandering in **(a place)**. upon **(arriving at / encountering)** **(a specific location / object / person in the place)**, a story about **(a topic)** unfolds.

3. When you’re done. Put your paper on the designated idea table.

<br>

## Let's put it to a vote!

Each person gets ***Three votes***

![](./img/start-line.gif)

Read through the ideas. Place a sticker on your favorite ones.

![](./img/start-line.gif)

We’ll take the top 4-5 ideas and write them on the board!

<figure>
    <img src="../img/antifieldguide.gif">
    <figcaption>-- <a href="https://hellodri.itch.io/anti-field-guide">Anti-Guide to Field Guides</a>. Dri Chiu Tattersfield (hellodri).</figcaption>
</figure>

<br>

## Let's get into groups! 

- Three people max.
- Workshop the idea, make a sketch, storyboard, plan what you’ll make (remember that your game can be small)
- Divide up the work if needed. (writing, drawing, sounds, bitsy assembly)
    * **Have a "developer" work on the core interactions of your game using placeholder interactable objects and rooms.** <br>This person would implement the dialogs, variable actions, and exit/endings of the game; and eventually compile the finalised assets made by other team members. <br><br>There could be multiple developers working on different parts of the game -- remember to plan ahead for how certain variable data should be labelled to avoid conflicts when merging. 
    * **Have only ONE (1) person working on room and tile designs.** <br>Merging room and tile data can get especially tedious, because you'll find yourself needing to re-index a bunch of tile assets... <br><br>Other game asset data like sprites, avatars, items, and audio are comparatively easier to compile from multiple sources. 
- Make sure to add an **ending** somewhere in your project!

<br>

### Notes on collaborating across multiple devices

Behind the scenes, bitsy is just storing everything as text.

Take a look at the **“Game Data”** tool. If you scroll around (or search for names), you’ll be able to find the data connected with your sprite / room / color palette

**You can copy and paste things from one game data file to another.**

If you’ve decided to use any hacks or plugins this might be a bit more tricky.

<figure>
    <img src="../img/endlessscroll.gif">
    <figcaption>-- <a href="https://haraiva.itch.io/endless-scroll">Endless Scroll</a>. Cecile Richard (haraiva).</figcaption>
</figure>

<br>


## ... THE MOMENT YOU'VE ALL BEEN WAITING FOR!

<embed type="text/html" src="../bitsyjam/museum/index.html" width="100%" height="500">

<br>


---

## Some course reminders

- **Homeplay Response 2** is due next Tuesday.
- **Project 3 Proposal** is due next Thursday.
