# 📅 Schedule

<!--removes sidebar outline-->
<style>
    @media (min-width: 768px) {
        .col-md-9 {
            width: 100% !important;
        }
        
        .d-md-block {
        display: none !important;
        }
        
        #component-content{
            margin-left:0 !important;
        }
    }
</style>

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

|  | Tuesday       | Thursday      |
| ------- | ------------- | ------------- |
| W1  | **04/01**</br><p><mark class="due">📌 DUE: <a href="https://forms.gle/3LVDUEox97UH1xwY6">Preliminary Survey</a></mark></p><p>Course Overview & Introductions</p><p>[Tech Setup](./tech-setup.md) </p><p>Lecture: [Intro to Game Engine, Unity, and C#](./0-unity-csharp.md)</p><p><mark class="assign">▶️ ASSIGN: [Reading Response 1](./readings-and-homeplays.md/#reading-response-1), [Project 1](./project-1.md)</mark></p> | **04/03**</br><p>Tutorial: [Transforms, Vectors](./1-transforms-vectors.md)</p><p><mark class="assign">▶️ ASSIGN: [Homeplay 1](./readings-and-homeplays.md#homeplay-1)</mark></p> |
| W2  | **04/08**</br><p><mark class="due">📌 DUE: Reading Response 1</mark></p><p>Tutorial: [Prefabs, Loops, Arrays](./2-prefabs-loops-arrays-import.md)</p> | **04/10**</br><p><mark class="due">📌 DUE: Homeplay 1, Project 1 Sketch </mark></p><p>Tutorial: [Randomness, Noise, Custom Classes for Storing Data](./3-randomness-noise-customclasses.md)</p>|
| W3  | **04/15**</br><p>Tutorial: [Basic Input, UI, Lights and Camera Settings](./4-basicinput-ui-lights-camera.md)</p><p>Demo: [How to Submit](./how-to-submit.md)</p><p>Studio Time</p> | **04/17**</br><p><mark class="due">📌 DUE: Project 1</mark></p><p>Project 1 Crit</p><p><mark class="assign">▶️ ASSIGN: [Reading Response 2](./readings-and-homeplays.md/#reading-response-2), [Project 2](./project-2.md)</mark></p>|
| W4  | **04/22**</br><p>Lecture: [Game + Play + Level Design!](./5-game-play-level-design.md)</p><p><mark class="assign">▶️ ASSIGN: Homeplay 2</mark></p> | **04/24**</br><p><mark class="due">📌 DUE: Reading Response 2</mark></p><p>Tutorial: [Physics Engine: Rigidbody, Collider, Collisions, Triggers](./6-physics-engine.md)</p>|
| W5  | **04/29**</br><p><mark class="due">📌 DUE: Homeplay 2</mark></p><p>Tutorial: [Input Systems, State Machines, Events](./7-inputsystem-statemachine-event.md)</p> | **05/01**</br><p>Tutorial: [Statics, Scenes, Sounds, VFX](./8-statics-scenes-sounds-vfx.md)</p>|
| W6  | **05/06**</br><p><mark class="due">📌 DUE: Project 2 Prototype Playtest</mark></p><p>Tutorial: [Animation, Coroutines, Persistent Data](./9-animation-coroutines-persistentdata.md)</p> | **05/08**</br><p>Tutorial: [Sprites and Video Players](./10-sprites-videoplayers.md)</p><p>Studio Time</p>|
| W7  | **05/13**</br><p><mark class="due">📌 DUE: Project 2</mark></p><p>Project 2 Crit</p><p><mark class="assign">▶️ ASSIGN: [Project 3](./project-3.md), [Homeplay 3](./readings-and-homeplays.md/#homeplay-3)</mark></p> | **05/15**</br><p>ALT-Engine Micro Game Jam</p>|
| W8  | **05/20**</br><p><mark class="due">📌 DUE: Homeplay 3</mark></p><p>Tutorial: Interactive Text</p> | **05/22**</br><p><mark class="due">📌 DUE: Project 3 Sketch</mark></p><p>Tutorial: Inventory and Collections</p>|
| W9  | **05/27**</br><p>Tutorial: More Cameras, Cinemachine</p> | **05/29**</br><p>Studio Time</p>|
| W10  | **06/03**</br><p>Studio Time</p> | **06/05**</br><p><mark class="due">📌 DUE: Project 3</mark></p><p>Project 3 Crit</p> |