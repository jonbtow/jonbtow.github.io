---
layout: project
permalink: "/Books/CleanCode/"
title: Clean Code
---
[version](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)

### Chapters
<!-- Row Content -->
<div class="w3-col w3-container" style="width:70%">
     <ol class="entry-previews">
     {% for project in site.projects %}
        {% if project.level == 1 %}
	   <li>
	    <p class="post-preview">
	      <a href="{{ project.url }}">
	      	   {{ project.title }}
		    <br>
		    {{project.introduction}}
	     </a>
	    </p>
	   </li>
	{% endif %}
    {% endfor %}
     </ol>
</div>