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

# Project 1: Auto-Generator

<div class="duedate">
<p>📌 <b>SKETCH/PROPOSAL DUE:</b> Week 2 Thursday, April 10</p>
<p>📌 <b>FINAL PROJECT BUILD + DOCUMENTATION DUE:</b> Week 3 Thursday, April 17</p>
<p><a href="https://forms.gle/DdU363hqEDBTenadA">Submit Final Submission Here</a></p>
<blockquote>Please read the <a href="../how-to-submit">How To Submit</a> page for more detailed instructions.</blockquote>
</div>

## Prompt

Create a generator in Unity that only requires 1 ~ 2 button controls to run. 

</br>
**Consider the following options:**

* a landscape / level / terrain generator;
* a random character generator, eg. exquisite corpse;
* an evolution simulator, e.g. cellular automaton.

</br>
**Possible techniques:**

* modular architecture using prefabs, arrays/lists, instantiate/destroy functions, empty transforms as connection points;
* procedural / algorithmic generation using random functions, perlin noise, custom parameters, L-systems, cellular automata, etc.

</br>
**Tips:**

* Consider what constraints or rules you can impose to create unique forms and color palettes.
* You may work in 2D or 3D. Lean into your strengths as a visual designer / artist as much as possible with this project! (And also remember you don't have much time!)
* Consider how a viewer will see / experience your generative designs. Can they orbit the camera around? Can they press a button to generate new objects?

<br>

## Requirements

Project 1 contains **TWO COMPONENTS**: 
> - **PART 1 (2.5%): SKETCH OF PROJECT PROPOSAL** </br>📌 *Due: Week 2 Thursday, April 10* </br>A sketch and/or in-progress prototype of your project. Bring this to class for discussion! </br><ul><li>*What are you generating? How are you generating it?*</li></ul>
> - **PART 2 (12.5%): FINAL PROJECT BUILD WITH DOCUMENTATION** </br>📌 *Due: Week 3 Thursday, April 17* </br>Refer to [submission guidelines](./how-to-submit.md), and submit your final project.
> 
> **Total contribution to final course grade: 15%**

</br>
**Your final project is not required to:** 

- be a traditional video game;
- have sound / audio.

<br>

## Evaluation

Your final project will be evaluated according to the guidelines listed in the [course syllabus](./syllabus.md/#evaluation-criteria).

---