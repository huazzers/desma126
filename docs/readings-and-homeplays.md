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

# Readings and Homeplays

---

## Reading + Homeplay Response 1

<div class="duedate">
<p>📌 <b>DUE: Week 2 Tuesday, January 13</b></p>
</div>

Read Kate Compton's "[So you want to build a generator](https://galaxykate0.tumblr.com/post/139774965871/so-you-want-to-build-a-generator)"

***AND***

Play **at least ONE (1)** of the following projects in this [spreadsheet](https://docs.google.com/spreadsheets/d/1P4iHbmpMGBqSL9H3Pr3enju12mVvFvBCRHUqka5SaTs/edit?usp=sharing).

<br>

... and then [**submit your response here**](https://forms.gle/NkumCEpzL81FbB2UA).

<br>

**Optional readings:**

- Kate Compton PROCJAM 2015 Talk (15:58 - 49:53) "[Let It Grow: Practical Procedural Generation From The Ground Up](https://www.youtube.com/live/s_eyo_m_hnc?feature=shared&t=958)" 
- Herbert Wolverson 2020 Roguelike Celebration Talk "[Procedural Map Generation Techniques](https://www.youtube.com/live/TlLIOgWYVpI)" 

<br>

---

## Reading Response 2

<div class="duedate">
<p>📌 <b>DUE: Week 4 Tuesday, January 27</b>
</div>

Read Steve Swink’s “[Game Feel: The Secret Ingredient](https://www.gamedeveloper.com/design/game-feel-the-secret-ingredient)”

<br>

***AND***

<br>

**any ONE (1)** of the following:

- Henry Jenkins, “[Game Design As Narrative Architecture](https://drive.google.com/file/d/1FmHFVyv-vv19LSccrY80BWfGVFQJ1Qh3/view?usp=sharing)"
- Alenda Cheng, “[Rambunctious Games: A Manifesto for Environmental Game Design](https://drive.google.com/file/d/1nxV71PJjhWbC6NariZf_mNYbCeAkZ5xI/view?usp=sharing)”

<br>

... and then [**submit your responses here**](https://forms.gle/zvkidpDeg3h9wBu66). 

> 💡 Tip: You can add placeholder text inside the first question to see questions in the next section... just make sure your final submission is properly updated with your intended response!

</br>

***Optional***: 

- Read **Chapter 17** of [***Game Feel: A Game Designer's Guide to Virtual Sensation***](https://gamifique.wordpress.com/wp-content/uploads/2011/11/2-game-feel.pdf) (pg. 316 of the PDF).
- Watch [***Juice it or lose it - a talk by Martin Jonasson & Petri Purho***](https://youtu.be/Fy0aCDmgnxg) for a live demonstration of how to get juiciness with tweening, particles, and other visual design decisions.

<br>

---

## Homeplay Response 2

<div class="duedate">
<p>📌 <b>DUE: Week 8 Tuesday, February 24</b>
</div>

Pick **ONE** of the following homeplay options in this [**spreadsheet**](https://docs.google.com/spreadsheets/d/1owkWE0WNRbM_UKVOhzJANH2vcCUerjyE44VX3-Jmo_M/edit?usp=sharing).

> ⚠️ **Note:**<br>Some have multiple projects listed in the same row -- you should play **all projects listed in the same row** as one homeplay response.

<br>

... then [**submit your responses here**](https://forms.gle/44Vg5327ZU83HS2X8). 

> 💡 **Tip:**<br>You can add a placeholder response to first question to see questions in the next section... just make sure your final submission is properly updated with your intended response!