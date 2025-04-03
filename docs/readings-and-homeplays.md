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

# Readings and Homeplays

---

## Reading Responses
<!--Brief description on what reading responses are.-->

Read the assigned material, and submit your response to the given questions **in your own words.**

### Reading Response 1

<div class="duedate">
<p>📌 <b>DUE: Week 2 Tuesday, April 8</b>
</br><a href="https://forms.gle/guG2HcU52nntLakn8">Submit Your Response Here</a></p>
</div>

Read Kate Compton's "So you want to build a generator" 
[https://galaxykate0.tumblr.com/post/139774965871/so-you-want-to-build-a-generator](https://galaxykate0.tumblr.com/post/139774965871/so-you-want-to-build-a-generator)

</br>

***Optional***

If you're hungry for more, below are some recommended talks on more methods and applications of procedural generation:

- Kate Compton PROCJAM 2015 Talk (15:58 - 49:53) "Let It Grow: Practical Procedural Generation From The Ground Up" (34 min) [https://www.youtube.com/live/s_eyo_m_hnc?feature=shared&t=958](https://www.youtube.com/live/s_eyo_m_hnc?feature=shared&t=958)
- Herbert Wolverson 2020 Roguelike Celebration Talk "Procedural Map Generation Techniques" (27 min) [https://www.youtube.com/live/TlLIOgWYVpI](https://www.youtube.com/live/TlLIOgWYVpI) 

<br>

### Reading Response 2

<div class="duedate">
<p>📌 <b>DUE: Week 4 Thursday, April 24</b></p>
</div>

TBD

<!--
Read these two writings by Steve Swink:

- [***Game Feel: The Secret Ingredient***](https://www.gamedeveloper.com/design/game-feel-the-secret-ingredient)
- Then read **Chapter 17** of [***Game Feel: A Game Designer's Guide to Virtual Sensation***](https://gamifique.wordpress.com/wp-content/uploads/2011/11/2-game-feel.pdf) (pg. 316 of the PDF).

Respond to the questions in the form **in your own words**. 

For this reading response, it helps to have some idea(s) for what you'd like to do for Project 2 beforehand -- some questions will ask you to apply concepts that introduced in the writing to your plans for Project 2. 

</br>

***Optional***: 

Watch [***Juice it or lose it - a talk by Martin Jonasson & Petri Purho***](https://youtu.be/Fy0aCDmgnxg) for a live demonstration of how to get juiciness with tweening, particles, and other visual design decisions.

<br>

-->

---


## Homeplays

- Sign up for game(s) to play in groups of 2~3;
- 30 ~ 60 minutes of total game play;
- Take notes, ask questions, consider the prompt;
- Take screenshots / recordings if needed.

PC / HTML games will also be available in the PC work stations next to the 4th floor Undergrad Lounge (Exit the elevator, turn right into the lounge, and the PC work stations will be on your right.)

<img src ="../img/20240927_153604.jpg" alt="Log into your DMA account user, or dma, password: dma1. Open File Explorer, then go to This PC, C drive, ProgramFiles, GameEngine Homeplays folder.">

<br>

### Homeplay 1

<div class="duedate">
<p>📌 <b>DUE: Week 2 Thursday, April 10</b>
</br><a href="https://docs.google.com/spreadsheets/d/1AiUgLQjXvfYdugF8H9iqIldoyj6m6JJZAEK97xzko9s/edit?usp=sharing">Sign Up + Submit Presentations Here</a></p>
</div>

Plan to spend about 30 ~ 60 minutes playing the game(s) with your group members, then **prepare a short 5 ~ 7 minute presentation** in response to the following:

1. Tell us about the project
    - What is being generated?
    - What generation method, properties, and constraints (do you think) are being used?
    - How do you interact with it?
2. Consider the effectiveness of this generator and your experience of it -- what works, what doesn't, and why? 
    - Do the generated results feel meaningful, memorable, merely distinguishable, or pretty much the same?
    - Was there something else about the project that was notable in your experience of it -- the camera, gameplay, interface, etc. ?

**Please share a link to any presentation materials** in the sign up sheet next to your group names. You will share your responses with the rest of the class during lesson time on the due date.

<br>

### Homeplay 2

<div class="duedate">
<p>📌 <b>DUE: Week 5 Tuesday, April 29</b></p>
</div>

TBD 
<!--
<div class="duedate">
<p>Due: Week 8 Tuesday, November 19
</br><a href="https://docs.google.com/spreadsheets/d/1x4n8uIGx_rXHAzmBcC_ezYw_YON5d0jG7F7Ui2UBXsk/edit?usp=sharing">Sign Up Here + Submit Presentations Here</a></p>
</div>
-->

<!--
Plan to spend about 30 ~ 60 minutes playing the game(s) with your group members, then **prepare a short 5 ~ 7 minute presentation** in response to the following:

1. Tell us about the project
    - What is the project about? What aspects of the project offer you context - the writing? the objects in space? the player interaction? the game rules? the sound? the visual language? the camera perspective?
    - Any notable features of this project that affected your experience
2. Consider your experience of the project -- what works, what doesn't, and why?
    - overall feelings, reactions, thoughts about the game's subject matter, before/during/after playing.
    - anything you're interested in applying to your own projects? 


**Please share a link to any presentation materials** in the sign up sheet next to your group names. You will share your responses with the rest of the class during lesson time on the due date.

-->

### Homeplay 3

<div class="duedate">
<p>📌 <b>DUE: Week 8 Thursday, May 22</b></p>
</div>

TBD