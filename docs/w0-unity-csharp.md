# Intro to Game Engine, Unity, and C&#35;

---

## What is a Game Engine?

Let's break this question down. First of all...

### What is a Game?

![Definition of a "game," from Rise of the Videogame Zinesters by Anna Anthropy](./img/zinesters_game_definition.png)
<figure>
<blockquote>
<p>A game is an experience, and that experience has a certain character. [...] And if we’re discussing an experience, then that implies someone is there to have that experience, someone we refer to as a player. We can’t talk about a game without talking about the experience of the player playing that game, even if the playing experience we’re talking about is often our own.</p>
<p>
<mark>The experience we call a game is created by the interaction between different rules</mark>, but the rules themselves aren’t the game, the interaction is! <mark>A game can’t exist without a player or players</mark>: someone needs to be engaging with the rules for the experience to happen.</p>
</blockquote>
<figcaption>-- Chapter Three, Rise of the Videogame Zinesters. Anna Anthropy.</figcaption>
</figure>

For example, in a game of tag, YOU HAVE TO DESIGN RULES FOR...

1. **THE SETUP** -- how do you decide who's "it"? when can they start tagging people?
2. **THE LEVEL / PLAYING FIELD** -- how far can players go before they're "out-of-bounds"? are there safe zones where people can't be tagged? 
3. **PLAYER BEHAVIOUR** -- are players only allowed to travel in a certain manner (e.g. speedwalking, but no running), and how can that be enforced (e.g. speedwalking means both feet cannot be lifted off the ground at the same time at any moment.) If someone gets tagged, what happens to them? Do they freeze in position, become "it", or are they out of the game? 
4. **CONCLUDING THE EXPERIENCE** -- how do you know when the game has ended, and who the winner/loser is (if any)?

</br>

#### "Is xxx a game?"

<figure>
<iframe class="itch-html-embed" frameborder="0" src="https://html-classic.itch.zone/html/5171563/index.html" width="100%" height="400" ></iframe>
<figcaption>-- <a href="https://sweetfish.itch.io/game">is this a game?</a> by sweetfish on itch.io.</figcaption>
</figure>

Technically, this question is irrelevant to this class.

Regardless of what you end up making for your assignments, you'll eventually have to make decisions about the **parameters and conditions** of your project (which you could think of as being "the rules of your game") and consider how one's interaction / encounter of these "rules" will affect their overall experience of it.

In this class, we will focus on **how to implement these rules using game engines**, so that you can explore its creative affordances for designing particular experiences.

### What is an Engine?

<figure>
<img src ="https://media1.tenor.com/m/9Gvf9FdRqUYAAAAd/marine-diesel-engine-engine.gif" alt="Marine Diesel Engine Animation GIF">
<figcaption>-- Marine Diesel Engine Animation GIF (<a href="https://tenor.com/en-GB/view/marine-diesel-engine-engine-gif-8550503">Source</a>)</figcaption>
</figure>

<figure>
<img src="../img/horse-3-small-1.webp">
<figcaption>-- Animation of Eadweard Muybridge’s Jockey riding a race horse from his ‘Animal Locomotion’ series, 1878/87 / J. Paul Getty Museum, Los Angeles, USA / Bridgeman Images</figcaption>
</figure>

</br>
Consider the following definitions from the Wikitionary page for <a href ="https://en.wiktionary.org/wiki/engine#English">"Engine"</a>:

</br>

> "A complex mechanical device which converts energy into useful motion or physical effects."

In a mechanical sense, <mark>an engine is an energy converter</mark> that can transform certain type(s) of input into other type(s) of "productive" output.

</br>

<blockquote><p>"A person or group of people which influence a larger group; a driving force." </p></blockquote>
<blockquote><p>"Anything used to effect a purpose; any device or contrivance; an agent."</p></blockquote>

In an abstract sense, <mark>an engine is an information carrier</mark> that can contain, transfer, and transform ideas, beliefs, and principles. 

</br>

<blockquote><p>"A large construction used in warfare, such as a battering ram, catapult etc. [from 14th c.]"</p></blockquote>
<blockquote><p>"The part of a car or other vehicle which provides the force for motion, now especially one powered by internal combustion. [from 19th c.]"</p></blockquote>

From a historical and infrastructural standpoint, <mark>an engine is a catalyst of both the production and destruction of worlds, societies, and cultures.</mark>

</br>

> "A software or hardware system responsible for a specific technical task (usually with qualifying word)."
>>   a graphics engine; </br> a physics engine.

In computing, <mark>an engine is a specialised machine</mark> for performing a specific task.

</br>

In this class, we will be mostly using software programs designed specifically for game development... but really, <a href="#what-is-a-game-engine_1">anything can be a "game engine."</a>

It is also worth considering the various contexts in which the engine emerges, so that we can better grasp the possibilities and implications of this technology, and then decide how and where we would like to proceed with this tool.

### Put them together... GAME ENGINE! 

Returning to our first question: 

#### What is a game engine?

<figure>
<img src="../img/guess-we-making-games-now_cropped.gif">
<figcaption>-- <a href="https://wttdotm.com/guess_we_doin_games_now/desktop.html">guess we doin games now</a> by morry kolman (@WTTDOTM)</figcaption>
</figure>

- Tools designed specifically for developing games (e.g. Unity, [Bitsy](https://www.bitsy.org/), [PICO-8](https://www.lexaloffle.com/pico-8.php), [in-game](https://create.roblox.com/) [level](https://supermariomaker.nintendo.com/) [builders](https://www.minecraft.net/en-us/about-minecraft))
- Platforms which primarily serve some other non-game-making function (if any at all), but are nonetheless used for making games. (e.g. [Spread](https://eieio.games/nonsense/game-10-realtime-gsheet/)[sheets](https://www.youtube.com/watch?v=N2QC6VQXo8U), [Checkboxes](https://eieio.games/nonsense/game-14-one-million-checkboxes/), [Post-war junkyards and bombsites](https://www.ludozofi.com/home/library/adventure-playgrounds-and-postwar-reconstruction/))

<figure>
<img src="../img/occupation-vs-free-play.jpg">
<figcaption>-- <a href="https://truthout.org/articles/when-play-is-criminalized-racial-disparities-in-childhood/">When Play Is Criminalized: Racial Disparities in Childhood</a>. Eisa Nefertari Ulen, TRUTHOUT.
</figure>

If a game is ["an experience that is made from the interaction between different rules"](#what-is-a-game), then broadly speaking, <mark>a game engine could be anything that converts rules and interaction into playable experiences. </mark>

And, in the same way that tools which aren't even intended for game-making *can* be used to make games...

#### Game engines aren't *only* used for making games.

<ul>
<li>Films and performance</br></br>
<figure>
<div style="padding:56.25% 0 0 0;position:relative;">
<iframe src="https://www.youtube.com/embed/gK3JRl3nRUc?si=XRMg0IfV8VOJXE3f" title="YouTube video player" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></div>
<figcaption>-- <a href="https://cathoderadiator.itch.io/juvenoia">Juvenoia</a> by Michael Luo</figcaption>
</figure>
<figure>
<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/328440768?badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" style="position:absolute;top:0;left:0;width:100%;height:100%;" title="FIRE UNDERGROUND (Trailer)"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
<figcaption>-- <a href="https://ncrockett.com/Overview">Fire Underground (Trailer)</a> by Nick Crockett</figcaption>
</figure>
<figure>
<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/242495062?badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" style="position:absolute;top:0;left:0;width:100%;height:100%;" title="FIRE UNDERGROUND (Trailer)"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
<figcaption>-- <a href="https://sutopat.itch.io/cubeism">Cubeism</a> by Patrick Stefaniak</figcaption>
</figure>
</li>
<li>
Simulation models</br></br>
<!--
life engine: https://thelifeengine.net/
the bibites: https://thebibites.itch.io/the-bibites 
evolution: https://keiwan.itch.io/evolution
evopedal: https://evolgames.itch.io/evolpedal
adapt: https://store.steampowered.com/app/888780/Adapt/ 
better horses: https://lingdonh.itch.io/better-horses
thrive: https://revolutionarygamesstudio.com/releases/ 
emoji simulator: https://ncase.me/sim/
* https://boids.cubedhuang.com/ -- boids simulator, with parameter sliders
reading: https://www.redblobgames.com/ 
-->
<figure>
<figcaption></figcaption>
</figure>
<figure>
<figcaption></figcaption>
</figure>
</li>
</ul>

... and more! 

---

## Unity is a Game Engine

We'll spend most of this course working in the Unity game engine. 

<img src ="https://lh4.googleusercontent.com/R_CoauogJuPBNek5Csg6ybU4aLeME4HwgK5q6A5g79nroxoxjUqlD-08cd0Cn3tDeShpQQo3lyNb7zTA2wXxYG2D79dIysKDKonxehoBJmRu98qq061HLFKe9EUQHdaV-tDebqi4q-f4m1zvVzZru_s" alt="Unity game engine preview">
<!--HOST THIS IMAGE LOCALLY!-->

Unity, initially released in 2005, is a closed-source game engine, and Unity Technologies, the developer of the engine, has been a publicly traded company since 2020. 

The engine gained popularity through being free for small, independent developers, with a relatively easy learning curve. 

Compared to most other game engines, Unity also tries to avoid being aesthetically identifiable and not be tied to a particular genre of game. 

Other industries use Unity for things like [Architectural](https://unity.com/solutions/architecture-engineering-construction) and [Auto](https://unity.com/solutions/automotive-and-transportation) rendering, [Film and TV production](https://unity.com/solutions/real-time-filmmaking-explained), [AI training](https://unity.com/products/machine-learning-agents) and [computer vision](https://unity.com/products/computer-vision).

Unity also contracts with the US Department of Defense for [military training and simulation.](https://www.vice.com/en/article/y3d4jy/unity-workers-question-company-ethics-as-it-expands-from-video-games-to-war)

<figure><div style ="padding:56.25% 0 0 0;position:relative;">
<iframe width="100%" height="100%" src="https://www.youtube-nocookie.com/embed/0lLBnGe6Ecc?si=DGJKtpGZ18pKe-Dr" title="YouTube video player" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></div>
<figcaption>-- R.I.D.E. by USC Institute for Creative Technologies.</figcaption>
</figure>

<figure>
<img src="../img/only-for-defensive-purposes-of-course.jpg" alt="only for defensive purposes, of course, says Otacon from Metal Gear Solid 1.">
<figcaption>-- <!--moments before Otacon's mecha fantasies shatters.-->Metal Gear Solid (1988)</figcaption>
</figure>

### Anatomy of the Unity Editor

<figure>
<img src ="https://docs.unity3d.com/uploads/Main/using-editor-window.png" alt="Unity Editor in default layout with each panel labelled with an Alphabet.">
<figcaption>-- Unity Editor window in default workspace layout</figcaption>
</figure>

Read the following articles from the Unity User Manual:

- [Unity's interface](https://docs.unity3d.com/Manual/UsingTheEditor.html)
- [GameObjects](https://docs.unity3d.com/Manual/GameObjects.html)
- [Transforms](https://docs.unity3d.com/Manual/class-Transform.html)
- [Using Components](https://docs.unity3d.com/Manual/UsingComponents.html)

### Unity C&#35;

Unity uses <mark>C#, a type of object-oriented language</mark>, as one of its primary scripting languages.

We typically write Unity C# scripts to make customised blueprints for accessing, organising, and implementing data inside our game project. This is helpful for:

1. storing information such as **variables** and **functions** inside an **object** or **class**;
2. programming interactive / dynamic behaviour in objects;

Most of the time, we're working with a class called <a href="https://docs.unity3d.com/ScriptReference/MonoBehaviour.html">MonoBehaviour</a> which behaves like a component that can be attached to any gameobject in our scene.

### Let's create a Unity C&#35; script!

Here's the general thought process when figuring out what to put in our script:

1. **OUTPUT** -- *"I need my script to do *THIS*..."*
2. **INPUT** -- *"... so I need to access *THESE VARIABLES*..."*
3. **METHOD** -- *"... and call *THESE FUNCTIONS* in order of *THIS SEQUENCE*."* 

### Anatomy of a C&#35; Script

Watch this video for a brief introduction to [C# Variables and Functions](https://www.youtube.com/watch?v=-c1RsydH2nA) in Unity.

### Naming conventions 

#### Unity C# script names

- use pascal case, *e.g. MyScript.cs*
- the file name of the script and the name of the MonoBehaviour must be exactly the same (case-sensitive).
- the name must be unique, ie. no two MonoBehaviours should have the same name.

#### Variable names

- no spaces allowed.
- use camel case. </br><pre><code>int numberOfCamels</code></pre>
- use clear and descriptive nouns, the intent of this variable should be immediately apparent from its name
    - if it is a bool, prefix with a verb (typically phrase as a question.) </br><pre><code>bool isWalking, hasSpecialAbility;</code></pre>
- use prefixes with an underscore to differentiate private member variables from public ones.</br><pre><code>private bool _currentHealth; 
private static int s_winScore;</code></pre>


#### Function Names

- use pascal case. </br><pre><code>float MultiplyByTwo(){...}</code></pre>

### Key principles of Programming in Unity C&#35;

- **Single Responsibility** -- Every module of code (class, function, etc.) should have a one and only purpose in the software functionality. This will be very helpful when you need to debug your scripts.
- **Keep everything private unless it *absolutely* needs to be public.**
    - if a variable just needs to be visible in the Inspector but does not need to be publicly accessible, you should keep it private then add [SerializeField] before it. </br><pre><code>[SerializeField] bool _currentIndex;</code></pre>