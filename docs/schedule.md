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

    blockquote{
        margin: 0 0.5em;
    }

    table th:first-of-type {
        width: 10%;
    }
    table th:nth-of-type(2) {
        width: 45%;
    }
    table th:nth-of-type(3) {
        width: 45%;
    }

/*
    table tr:nth-child(1)>td:nth-child(2), table tr:nth-child(8)>td:nth-child(2), table tr:nth-child(10)>td:nth-child(3){
        background-color:gray;
    }*/

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
    
    window.onload = function(e){
        var cell = document.getElementById('component-site-name');
        var caseId = cell.innerHTML;
        cell.innerHTML = '';
        var link = document.createElement('a');
        link.href = '../';
        link.appendChild(document.createTextNode(caseId));
        cell.appendChild(link);
    }
</script>

|  | Tuesday       | Thursday      |
| ------- | ------------- | ------------- |
| W1  | **01/06**</br><p>Introductions</p><p>[🛠️ Tech Setup](https://docs.google.com/document/d/1CGhRzQgaY6i87bgxVyaFQmYGLqq-W-n90z05SzFD9ns/edit?usp=sharing)</p><p>Course Overview</p><p>Lecture: [Intro to Game Engine](https://docs.google.com/document/d/1TIGMrA3fb6Y-wtA_GyIpzArXjy3CI6-zwYXy-Z0GWqg/edit?usp=sharing)</p><p>Tutorial: [Intro to Unity Interface](https://docs.google.com/document/d/1saqPp3NiYvGjYzLdyJoKv6TKah0BzYOgiSI8ko_prwY/edit?usp=sharing)</p><blockquote><p>Making a New Unity Project, Basic Unity Navigation, GameObjects and Components, Importing 2D and 3D Assets</p></blockquote><div class="assign"><p>▶️ ASSIGN:</p><ul><li>[Survey](survey.md) (Due: W1 Thu, 01/08)</li><li>[Reading + Homeplay Response 1](readings-and-homeplays.md/#reading-homeplay-response-1) (W2 Tue, 01/13)</li><li>[Project 1](project-1.md) (Due: W3 Tue, 01/20)</li></ul></div> | **01/08**</br><div class="due"><p>📌 DUE: </p><ul><li>Survey</li></ul></div><p>Tutorial: [C# Fundamentals](https://docs.google.com/document/d/1ID8zn8cNe1CO3E5EEV51eXiI3rpcS5eg9F8dvjSTKlw/edit?usp=sharing)</p><blockquote><p>Anatomy of a Unity C# Script, Vector Math for Transforming GameObjects</p></blockquote> |
| W2  | **01/13**</br><div class="due"><p>📌 DUE: </p><ul><li>Reading + Homeplay Response 1</li></ul></div><p>Tutorial: [Modular Generation, Procedural Generation](https://docs.google.com/document/d/1J2Q9Ff66kFWJMFiAE8Oq8elD7hGJN-nZS_PfeaDWAkc/edit?usp=sharing)</p><blockquote><p>Randomness, Loops, Instantiation with Prefabs and Arrays, Noise, Custom Serializable Classes</p></blockquote><p>Studio Time: One-on-one checkins</p><blockquote><p>Bring your ideas, works in progress, and questions to class!</p></blockquote> | **01/15**</br><p>Tutorial: [Basic Input, UI, Light, Camera, Post Processing](https://docs.google.com/document/d/15AI31HotvrMih-oxO8WAF5-mU_ymGCxN6NSLg0vecc0/edit?usp=sharing)</p><p>[How To Submit](how-to-submit.md)</p>|
| W3  | **01/20**</br><div class="due"><p>📌 DUE: </p><ul><li>Project 1</li></ul></div><p>Lecture: Game + Play + Level Design</p><p>Tutorial: Prototyping Game Environments with Roll-a-ball</p><blockquote><p>Grayboxing, Unity Terrain</p></blockquote><div class="assign"><p>▶️ ASSIGN:</p><ul><li>Project 2 (Due: W6 Thu, 02/12)</li><li>Reading Response 2 (W4 Tue, 01/27)</li></ul></div> | **01/22**</br><p>Tutorial: Physics Engine<p><blockquote><p>Rigidbodies, Colliders, Collisions, Triggers</p></blockquote>|
| W4  | **01/27**</br><div class="due"><p>📌 DUE: </p><ul><li>Project 2 Proposal</li><li>Reading Response 2</li></ul></div><p>Tutorial: Input System, State Machines</p> | **01/29**</br><p>Tutorial: Game Data and Scene Management</p><blockquote><p>Score-keeping, Singletons, Loading Scenes, Coroutines, UI</p></blockquote>|
| W5  | **02/03**</br><div class="due"><p>📌 DUE: </p><ul><li>Project 2 Prototype Playtest</li></ul></div><p>Tutorial: Sounds, Video Players, Visual Effects</p> | **02/05**</br><p>Studio Time: One-on-one meetings</p>|
| W6  | **02/10**</br><p>Tutorial: Post-processing, How To Submit</p><p>Studio Time: One-on-one meetings</p> | **02/12**</br><div class="due"><p>📌 DUE: </p><ul><li>Project 2</li></ul></div><div class="assign"><p>▶️ ASSIGN:</p><ul><li>Project 3 (W10 Tue, 03/10)</li><li>Homeplay Response 2 (W8 Tue, 02/24)</li><li>Extra Topics Survey (Due: W8 Tue, 02/24)</li></ul></div>|
| W7  | **02/17**</br><p>Alt-Game Engine Jam</p> | **02/19**</br><p>Tutorial: Interactive Text Workshop with Ink</p>|
| W8  | **02/24**</br><div class="due"><p>📌 DUE: </p><ul><li>Homeplay Response 2</li><li>Extra Topics Survey</li></ul></div><p>Tutorial: Cinematic Tools in Unity, Inventory System</p><blockquote><p>More Unity Camera Tricks, Cinemachine, Timeline, Scriptable Objects</p></blockquote> | **02/26**</br><div class="due"><p>📌 DUE: </p><ul><li>Project 3 Proposal</li></ul></div><p>Studio Time: One-on-one meetings</p>|
| W9  | **03/03**</br><p>Tutorial: Extra Topics <!--Persistent Data, NavMesh / NPC Behaviour, More Animation Tips--></p> | **03/05**</br><p>Studio Time: One-on-one meetings</p>|
| W10  | **03/10**</br><div class="due"><p>📌 DUE: </p><ul><li>Project 3</li></ul></div><p>Project 3 Crit Day 1</p> | **03/12**</br><p>Project 3 Crit Day 2</p> |