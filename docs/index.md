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

<script>

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

# 🏠 Game Engine Winter 2026

Broad 4230<br/>
Tuesdays and Thursdays, 9 a.m. - 11:50 a.m.

**INSTRUCTOR**<br/>
Office hours: Thursdays 12 p.m. - 1 p.m., by appointment only.<br/>
Email: huazzers@g.ucla.edu

**TEACHING ASSISTANT**<br/>
Office hours: Tuesdays 12 p.m. - 1 p.m., by appointment only.<br/>
Email: elliotbyu@g.ucla.edu

---