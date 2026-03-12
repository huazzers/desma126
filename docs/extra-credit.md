---
title: Extra Credit
---

<style>
    @media (min-width: 768px) {
        
        .d-md-block {
        display: none !important;
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

# Extra Credit

<div class="duedate">
<p>📌 <b>DUE:</b> Week 10 Sunday, March 15</p>
</div>

*Attend a Game Lab event, or any other guest talk, art exhibition, or performance related to games and interactive media, and tell me about your experience!*

Please submit your response before the deadline: [https://forms.gle/opuZtoqX1JY9uUri9](https://forms.gle/opuZtoqX1JY9uUri9)