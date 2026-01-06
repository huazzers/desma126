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

# Project 1: Auto-Generator

<div class="duedate">
<p>📌 <b>FINAL PROJECT BUILD + DOCUMENTATION DUE:</b> Week 3 Tuesday, January 20</p>
<p>Submit Final Submission Here (TBD)</p>
<blockquote>Please read the <a href="../how-to-submit">How To Submit</a> page for more detailed instructions.</blockquote>
</div>

## Prompt

In order to keep play interesting and unique for each iteration, video games often use custom algorithmic systems that dynamically generate different environments, characters, and other game data using the same set of assets.

To get familiar with building custom dynamic systems using Unity and C#, your first project prompt is as follows:

***Create a generator in Unity that only requires 1 ~ 2 button controls to run.***

---

**Consider the following options:**

* a landscape / level / terrain generator;
* a random character generator, eg. exquisite corpse;
* an evolution simulator, e.g. cellular automaton.

</br>
**Possible techniques:**

* modular architecture using prefabs, arrays/lists, instantiate/destroy functions, empty transforms as connection points;<br>![](./img/exquisite-corpse_cropped.gif)
* procedural / algorithmic generation using random functions, perlin noise, custom parameters, L-systems, cellular automata, etc.<br>![](./img/0505.gif)<br><br><figure>[![](./img/bibites.png)](https://thebibites.itch.io/the-bibites)<figcaption>-- [The Bibites](https://thebibites.itch.io/the-bibites) on itch.io</figcaption></figure><figure>[![](./img/L-system.png)](https://www.youtube.com/watch?v=E1B4UoSQMFw)<figcaption>-- (Youtube video) "[Coding Traing #16: L-systems](https://www.youtube.com/watch?v=E1B4UoSQMFw)"</figcaption><figure><figure>[![](./img/conwaysgameoflife.gif)](https://conwaylife.com/)<br>![](./img/conwaysgameoflife_summary.jpg)<figcaption>-- [Conway's Game of Life](https://conwaylife.com/)</figcaption></figure>

</br>
**Tips:**

* Consider what **constraints** or **rules** you can impose to create unique forms and color palettes.
* **You may work in 2D or 3D.** Lean into your strengths as a visual designer / artist as much as possible with this project! (And also remember you don't have much time!)
* **Consider how a viewer will see / experience your generative designs.** Can they orbit the camera around? Can they press a button to generate new objects?

</br>

**Inspirations**

<figure><a href="https://jamschutz.itch.io/quick-character-creator"><img src="../img/quickcharactercreator.jpg"></a><figcaption>-- Hao Liao and Joey Schutz, "<a href="https://jamschutz.itch.io/quick-character-creator">Quick Charcater Genreator</a>"</figcaption></figure>

<figure><a href="https://grey2scale.itch.io/pet-the-pup"><img src="../img/petthepup.gif"></a><figcaption>-- Will Herring, "<a href="https://grey2scale.itch.io/pet-the-pup">Pet the Pup at the Party</a>"</figcaption></figure>

<figure><a href="https://lingdonh.itch.io/better-horses"><img src="../img/betterhorses.png"></a><figcaption>-- Lingdong Huang, "<a href="https://lingdonh.itch.io/better-horses">Better Horses</a>"</figcaption></figure>

<figure><a href="http://www.galaxykate.com/apps/Prototypes/LTrees/"><img src="../img/flowers.png"></a><figcaption>-- Kate Compton"<a href="http://www.galaxykate.com/apps/Prototypes/LTrees/">Flowers</a>"... who also wrote this Tumblr post about making generators "<a href="https://www.tumblr.com/galaxykate0/139774965871/so-you-want-to-build-a-generator">So you want to build a generator...</a>"</figcaption></figure>

<figure><a href="https://titouanm.com/mucartographer/"><img src="../img/mucartographer.png"></a><figcaption>-- Titouan Millet, "<a href="https://titouanm.com/mucartographer/">Mu Cartographer</a>"</figcaption></figure>

<figure><a href="https://ncase.me/emoji-prototype/"><img src="../img/ncaseemojisim.png"></a><figcaption>-- Nicky Case, "<a href="https://ncase.me/emoji-prototype/">Emoji Simulator</a>"</figcaption></figure>

<br>

## Requirements

**Your final project requires:**

- the use of **modular OR procedural generation techniques**, or even a mix of both!
- **at least 1~2 button controls** to run.

</br>
**Your final project is not required to:** 

- be a traditional video game;
- have sound / audio.

<br>

## Evaluation

Your final project will be evaluated according to the guidelines listed in the [course syllabus](./syllabus.md/#evaluation-criteria).

---

-->