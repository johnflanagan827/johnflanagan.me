---
permalink: /
title: "About Me"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am an undergraduate student at the [University of Notre Dame](https://www.nd.edu), majoring in **Computer Science** and **Mathematics**. I am currently a software engineering intern at Garmin for summer 2024.

I am passionate about machine learning and natural language processing. You can view my resume [here](/resume/).

Research
-----
Currently, I work with [Dr. Meng Jiang](http://www.meng-jiang.com/) and PhD student [Noah Ziems](https://noahziems.com/), focusing on various **Large Language Model (LLM)** applications.

_**Publications:**_

- {% for pub in site.publications reversed %}
      <div>
        <a style="font-size: medium; display: block;" href="{{ pub.arxivurl }}"><strong>{{ pub.title }}</strong></a>
        <p style="font-size: medium; margin-top: 6px; margin-bottom: 1px;">
          {% assign authors = pub.authors | split: "," %}
          {% assign authors_list = '' %}
    
          {% for author in authors %}
          {% assign trimmed_author = author | strip %}
          {% if trimmed_author == site.author.name %}
          {% assign formatted_author = '<strong>' | append: trimmed_author | append: '</strong>' %}
          {% else %}
          {% assign formatted_author = trimmed_author %}
          {% endif %}
          
          {% if forloop.last == false %}
          {% assign authors_list = authors_list | append: formatted_author | append: ', ' %}
          {% else %}
          {% assign authors_list = authors_list | append: formatted_author %}
          {% endif %}
          {% endfor %}
          
          {{ authors_list }}
    
        </p>
    
        <p style="font-size: medium; margin-top: 0;">
          <i>{{ pub.venue }}</i> 
          {% if pub.link %}
            <a href="{{ pub.link }}" title="Publication Link"><i class="fas fa-fw fa-link zoom" aria-hidden="true"></i></a>
          {% endif %}
          {% if pub.paperurl %}
            <a href="{{ pub.paperurl }}" title="Download PDF"><i class="fas fa-fw fa-file-pdf zoom" aria-hidden="true"></i></a>
          {% endif %}
          {% if pub.codeurl %}
          <a href="{{ pub.codeurl }}" title="GitHub Code"><i class="fab fa-fw fa-github zoom" aria-hidden="true"></i></a>
          {% endif %}
        </p>
      </div>
    {% endfor %}

Contact Info
------
You can email me at **contact [AT] johnflanagan [DOT] me**, or connect with me on [LinkedIn](https://www.linkedin.com/in/johnflanag/).
