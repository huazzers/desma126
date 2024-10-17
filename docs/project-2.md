# Project 2: Ball Game Remix

## Final Submission Due: Week 6 Thursday, November 7

<div class="duedate">
<p>Submit Here (Link TBD)</p>
<blockquote>Please read the <a href="../how-to-submit">How To Submit</a> page for more detailed instructions.</blockquote>
</div>

<figure>
    <img src="../img/wiiplay.png" width=100%>
    <figcaption>-- Wii Play, Nintendo</figcaption>
</figure>

### Prompt

Adapt **one of the following** ball-based games into a digital game. 

- Ball-and-net sports (tennis, volleyball)
- Ball-and-wall sports (squash, racketball, handball)
- Throwing sports (Bocce Ball, dodgeball, bowling, skee ball)
- Tabletop sports (Billiards, Pool, Foosball, Air hockey)
- [Beigoma](https://www.youtube.com/watch?v=6Ez9QR7Lq3o) / Beyblade
- Golf
- Pinball / [Bagatelle](https://www.youtube.com/watch?v=agamnUk5Y84)
- Pachinko

<br>

... AND add **an interesting twist** to your game. 

<br>

### Requirements

Project 2 contains THREE COMPONENTS: 
> - **PART 1 (5%): BALL GAME RESEARCH** </br><mark>*Due: Week 4 Tuesday, October 22*</mark> </br>Do some research about the game you have chosen, and bring your notes to class for discussion. (Refer [below](#ball-game-research) for research topics to cover.)
> - **PART 2 (5%): PROTOTYPE PLAYTEST** </br><mark>*Due: Week 5 Thursday, October 31*</mark> </br>Bring a prototype of your project to class -- we will be playtesting each others' projects. Prioritise core mechanics for player interaction and level design, placeholder visuals and playing from the Unity Editor are ok at this stage. 
> - **PART 3 (15%): FINAL PROJECT BUILD WITH DOCUMENTATION** </br><mark>*Due: Week 6 Thursday, November 7*</mark> </br>Refer to [final submission requirements](#final-submission) and [submission guidelines](./how-to-submit.md), then submit your final project. 
> 
> **Total contribution to final course grade: 25%**

<br>

#### Ball Game Research

After picking a ball game to adapt for Project 2, do some research about the game you have chosen, considering the following questions: 

##### Environment

<div class="div-container">
    <div style="width:47.5%;">
        <img src="../img/tennis%20court.png">
    </div>
    <div style="width:47.5%;">
        <ul>
            <li style="margin-top:0;">What are the physical properties of the game environment (e.g. the ball, the play surface)?
            </li>
            <li>What are the affordances (opportunities for interaction or game mechanics) of the game environment?
            </li>
            <li>Are there any properties or affordances that are unusual or that you didn't expect?
            </li>
        </ul>
    </div>
</div>

<br>

##### Body

For the *actual physical* game:

<div class="div-container">
    <div style="width:47.5%;">
        <img src="../img/baseball%20swing.jpeg">
    </div>
    <div style="width:47.5%;">
        <ul>
            <li style="margin-top:0;">What tools or appendages are used to play the actual physical game?
            </li>
            <li>What are the properties and affordances of those tools? 
            </li>
            <li>Are there any properties or affordances that are unusual or unexpected?
            </li>
        </ul>
    </div>
</div>
<!--
<div class="div-container">
    <div style="width:47.5%;">
        <figure>
        <img src="https://img.itch.zone/aW1hZ2UvMjI5MTgvMTA2MjA4LmdpZg==/794x1000/6m2Fy8.gif">
        <figcaption>-- sparking vinegar - Super Cricket Fighter Turbo
        </figcaption>
        </figure>
    </div>
    <div style="width:47.5%;">
        <ul>
            <li style="margin-top:0;">What tools or appendages does the player use to play your <i>digital</i> game?
            </li>
            <li>What are the properties and affordances of those tools?
            </li>
            <li>What ways can you think of adapting the physical affordances and properties to the digital?
            </li>
        </ul>
    </div>
</div>
-->
For your *digital* game:
<ul>
            <li style="margin-top:0;">What tools or appendages does the player use to play your <i>digital</i> game?
            </li>
            <li>What are the properties and affordances of those tools?
            </li>
            <li>What ways can you think of adapting the physical affordances and properties to the digital?
            </li>
            <li>What are some affordances that only the digital game can have?
            </li>
        </ul>

<br>

##### Mind

<div class="div-container">
    <div style="width:47.5%;">
        <img src="../img/tennisshots.png">
    </div>
    <div style="width:47.5%;">
        <ul>
            <li style="margin-top:0;">What are the rules of your game? How does play proceed? Consider drawing a flow chart.
            </li>
            <li>How is your game scored? Does it have an unusual or idiosyncratic scoring system, like Golf or Tennis?
            </li>
            <li>Research the strategy of your game. Are there certain rules of thumb that players follow to succeed in the game?
            </li>
            <li>What decisions is a skilled player making on a moment to moment basis, and why?
            </li>
            <li>What resources does a skilled player manage during the game? stamina? number of shots left?
            </li>
        </ul>
    </div>
</div>


<br>

#### Final Submission

Your final project should have the following elements:

##### Physics

Your game must use the **Rigidbody** component to simulate **physics-based** motion and collision. 

- Experiment with the **mass, drag, and angular drag** of the ball to obtain results appropriate for your sport. A bowling ball has very different properties than a ping pong ball!
- Use [Rigidbody.AddForce](https://docs.unity3d.com/ScriptReference/Rigidbody.AddForce.html) or [Rigidbody.AddForceAtPosition](https://docs.unity3d.com/ScriptReference/Rigidbody.AddForceAtPosition.html) to **adjust velocity**. Consider when to use the different [force modes](https://docs.unity3d.com/ScriptReference/ForceMode.html): Force, Acceleration, Impulse, VelocityChange
- Use [OnCollisionEnter](https://docs.unity3d.com/ScriptReference/MonoBehaviour.OnCollisionEnter.html) to **detect when objects collide**, and play appropriate sounds
- Use [OnTriggerEnter](https://docs.unity3d.com/ScriptReference/MonoBehaviour.OnTriggerEnter.html) to **detect when objects enter an area**, such as a scoring zone or an out-of-bounds zone.

<br>

##### Gameplay

Your game should keep track of one or more player's **score**. Scores should be determined more or less according to the rules of the game you are adapting.

Consider how your **game mechanics** and **level design** can offer different strategic options and play experiences.

For example, you could research how factors like [spin](https://en.wikipedia.org/wiki/Glossary_of_cue_sports_terms#spin) or tilt affect the game you are adapting, and consider whether your game should include a way for players to spin the ball or tilt the playing area.

<figure>
    <img src="../img/ballspindiagram.png" width=100%>
    <figcaption>-- For instance, this diagram shows how topspin affects the trajectory of the ball in table tennis. The ball would have fallen off the table if it's trajectory had not bent downwards due to spin!</figcaption>
</figure>

<br>

You could also explore how **different terrains** for your playing field can affect the gameplay.

See examples of ping pong variations by Laurent Perbos, Gabriel Orozco, and Lee Wen. How would these tables change the experience of playing table tennis?

<div class="div-container">
    <div style="width:47.5%;margin-right:2.5%;">
        <figure>
            <img src="../img/pingpong-pipe.png" width=100%>
            <figcaption>-- Laurent Perbos - Ping Pong Pipe</figcaption>
        </figure>
    </div>
    <div style="width:47.5%;">
        <figure>
            <img src="../img/pingpong-console.png" width=100%>
            <figcaption>-- Laurent Perbos - Console</figcaption>
        </figure>
    </div>
</div>

<br>

<figure>
    <img src="../img/pingpong-pond.png" width=100%>
    <figcaption>-- Gabriel Orozco - Ping Pond Table</figcaption>
</figure>

<br>

<figure>
    <img src="../img/pingpong-goaround.png" width=100%>
    <figcaption>-- Lee Wen - Ping Pong Go Around</figcaption>
</figure>

<br>

What other affordances can digital games offer beyond changing the shape of the playing field? Animated obstacles? AIs? Alternative control schemes? Genre mashups?

<figure>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/UXw6TY_6YVA" title="Pin Pon, 2015 - Gameplay Trailer" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<figcaption>-- Theo Triantafyllidis - <a href="https://theotrian.itch.io/pinpon">Pin Pon</a>. <br>"Pin Pon is a game about online dating. Using a leap motion controller, players try to bounce stuff off their part of the table and into the opponents. Its always a match!" 
</figcaption>
</figure>

<br>

<figure>
<div class="div-container">
    <div style="width:47.5%;">
        <img src="../img/soccer 1.gif">
    </div>
    <div style="width:47.5%;">
        <img src="../img/soccer 2.gif">
    </div>
</div>
<figcaption>-- Peter Sheehan - <a href="https://perebite.itch.io/soccer-on-an-expanding-field">Soccer on an Expanding Field</a>. <br>"Play soccer on a field that doubles every time a goal is scored. For two players. [...] Every time a goal is scored, the field doubles in size." 
</figcaption>
</figure>

<br>

<figure>
<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/24498490?badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" style="position:absolute;top:0;left:0;width:100%;height:100%;" title="Untitled (idk)"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
<figcaption>-- Peter Lu, Steven Amrhein and Alex Rickett - Animal Golf. <br>"Balls are round, socially acceptable things to hit with clubs. But they roll! That’s not helping anybody. Animal Golf is what happens when you replace boring, rollable golf balls with animals that bounce, flip, and wobble. If you’ve ever wanted to hit a whale into a whale shaped hole, now’s your chance!" 
</figcaption>
</figure>

<br>

If you're making a multiplayer game, you could consider what type of social mechanics you'd like your players to have.

<figure>
<iframe src="https://editor.p5js.org/nkrkt/full/T9DxpX_kR" width=800 height=800></iframe>
<figcaption> -- Nick Crockett - Multiplayer Game Prompt Generator
</figure>

<br>

##### Interaction Design

Translating the nuances of a sport to a digital game is a complex challenge.

Players of real-life games like tennis are able to control the velocity and spin of their of the ball with subtle changes to how they strike the ball with the racquet. Traditional game controls, whether it's a gamepad or mouse and keyboard, don't usually offer this level of control!

<iframe width="100%" height="315" src="https://www.youtube.com/embed/EuWPjXJPOFU?si=cbszDkLHRCXNQPJi" title="Serena Williams & Conan Play Wii Tennis | Late Night with Conan O’Brien" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

**Consider how you allow the player to interact with the ball in 3D space.**

How would you design an interface for your game that feels expressive and true to the original sport? How do existing games manage this complexity?

For instance, there are many different examples of how tennis can be adapted to the screen:

<br>

<div class="div-container">
    <div style="width:60%;margin-right:2.5%;">
        <p style="margin-top:0 !important">
        <b>Pong</b> presents a top-down view of the court. The ball moves in straight lines, and bounces off the sides of the screen.
        <br>
        <br>
        The player controls one of two paddles, which can only move on the vertical axis. Pong is all about positioning, the ball bounces off the paddle without extra input from the player.
        </p>
    </div>
    <div style="width:35%;">
        <img src="../img/pong.gif">
    </div>
</div>

<br>

<div class="div-container">
    <div style="width:60%;margin-right:2.5%;">
        <p style="margin-top:0 !important">
        <b>Tennis for Two</b> presents a side-on view of the court, which emphasizes the arcing trajectory of the ball over the net.
        <br>
        <br>
        In Tennis for two, players control their horizontal position with a dial, and must press a button to strike the ball.
        </p>
    </div>
    <div style="width:35%;">
        <iframe width="100%" height="315" src="https://www.youtube.com/embed/6PG2mdU_i8k" title="Tennis for Two - The Original Video Game" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
    </div>
</div>

<br>

<div class="div-container">
    <div style="width:60%;margin-right:2.5%;">
        <p style="margin-top:0 !important">
        3D tennis games like <b>Virtua Tennis</b> present a tennis court rendered in 3D, with the camera positioned up high behind one of the two players.
        <br><br>
        Players are able to move their avatar using a 2D directional interface (such as a d-pad or analogue stick), and usually must press a button to strike the ball.
        <br><br>
        Different games will approach aim, spin, and power in a variety of ways. How would you give the player nuanced control of the ball in a game like this?
        </p>
    </div>
    <div style="width:35%;">
        <iframe width="100%" height="315" src="https://www.youtube.com/embed/Vs0XUKHeYpc" title="Virtua Tennis - Gameplay Dreamcast HD 720P" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
    </div>
</div>

<br>

##### Visual Communication

Consider the **look** and **feel** of your game, including lighting, materials, and more. If you wish, you may use 2D or 3D assets to compose your scene.

Use visual elements to **communicate the state of the game** to the player. 

Lines, meters, and arrows, can be useful for indicating aim, force, spin, and more.

Particle effects or a trail renderer can help draw attention to a fast moving object.

<br>

##### Sound

Don't forget that sound can be a powerful communication tool, and can help make a game feel more expressive. 

Consider increasing the **volume** and **pitch** of a sound effect based on how hard the ball collides with another object, or consider giving moving objects a "whoosh" sound that changes pitch and volume according to the object's speed.

<br>

### Evaluation

Your final project will be evaluated according to the guidelines listed in the [course syllabus](./syllabus.md/#evaluation-criteria).

<!--
?? ball game remix
?? physics game in general -- just has to use physics mechanics? 

# Prompt

Remix the Unity roll-a-ball tutorial! 

# Requirements

Project 1 has a THREE-PART SUBMISSION PROCESS: 
[] **PART 1 (2.5%): COMPLETE UNITY ROLL-A-BALL TUTORIAL** -- Submit tutorial build here (link tbd)</br>*(Due: October 3 (Week 1 Thursday))*
[] **PART 2 (2.5%): SKETCH OF PROJECT PRPOSAL** -- Bring this to class for discussion! </br>*(Due: October 8 (Week 2 Tuesday))*
[] **PART 3 (10%): FINAL PROJECT BUILD WITH DOCUMENTATION** -- Refer to [submission guidelines](./how-to-submit.md), and submit your final project here (link tbd) *(Due: October 17 (Week 3, Thursday))*

**Total contribution to final course grade: 15%**

---

**Your final project must follow the following rules:** 
[] NO MOUSE INTERACTIONS. NONE! 
[] PLAYER MECHANIC MUST INCLUDE A ROLLING BALL.
[] AT LEAST 2 OF THE FOLLOWING ASPECTS OF CHOICE MUST BE DIFFERENT FROM THE TUTORIAL </br> 
    * Level map - how does game* environment guide / challenge / support your player throughout the experience?
    * Player controls - how the ball is rolled, player camera, etc. other player interactions
    * Rules and mechanics - how game* responds to player's actions, how game* is won / lost / concluded. 

**Your final project is not required to:** 
* be a classic video game.
* have sound / audio. 

# Evaluation

Your final project will be evaluated according to the guidelines listed in the [course syllabus](./index.md/#evaluation-criteria).

-->