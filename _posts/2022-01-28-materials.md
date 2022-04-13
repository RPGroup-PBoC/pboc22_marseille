---
layout: post
title: Materials
cover: readings.jpg
categories: posts
permalink: materials
tag: mar
year: 2022
---
Here you will find papers, vignettes, and other resources mentioned in the class. They will be added as the course progresses.

## Vignettes

<a href="https://www.youtube.com/channel/UCnYEe45w6F4G3AEYCyNHMWg/videos" target="_blank">{{"PBoC Vignette Library"}}</a> - This series of vignettes expands on topics we will cover in the course.  Specific suggestions for vignettes to watch will be given during the course.

<table>
<tr>
    <th style="width:130px"><b>Date</b></th>
    <th><b>Topic</b></th>
</tr>
{% for day in site.data.vignettes %}
{% if day.exurl %}
{% else %}
<tr>
    <td>{{day.date}}  </td>
    <td>{{day.topic1}}
    {% if day.videos1 %}
    {% for v in day.videos1 %}
    {% if v.name %}
    <a href="http://rpdata.caltech.edu/courses/aph161/2021/videos/{{v.name}}" target="_blank">{{v.title}}</a><br/>
    {% else %} 
    <a href="{{v.url}}" target="_blank">{{v.title}}</a><br/>
    {{v.description}}<br/>
    {%endif %}
    {%endfor%}
    {%endif %}
    {{day.topic2}}
    {% if day.videos2 %}
    {% for v in day.videos2 %}
    {% if v.name %}
    <a href="http://rpdata.caltech.edu/courses/aph161/2021/videos/{{v.name}}" target="_blank">{{v.titlea}}</a><br/>
    {% else %}
    <a href="{{v.urla}}" target="_blank">{{v.titlea}}</a><br/>
    {{v.descriptiona}}<br/>
    {%endif %}
    {%endfor%}
    {%endif %}
    </td>
    <!--<td>--->
    <!--{% if day.slide %}--->
    <!--<a href="http://rpdata.caltech.edu/courses/aph161/protected/2022/slides/{{day.slide}}">Slides</a>--->
    <!--{%endif%}---> 
    <!--</td>---> 

  <!-- {% if day.slide %} 
  <td>
  {% for s in day.slide %}
  <a href="http://rpdata.caltech.edu/courses/aph161/protected/2020/videos/{{s}}"><b class="post-title">{{s}}</b></a> 
  {%endfor%}
  </td>
  {% else %}
  <td> {{'-'}} </td>
  {% endif %} -->
</tr>
{% endif %}
{% endfor %}
</table>

## In-Class Readings

{% assign readings = site.data.papers %}

{% for week in readings %}
<span style="display: block; font-weight: 500"> <b>{{ week[0] }}</b></span>

{% for p in week[1] %}
{% assign dir = "http://rpdata.caltech.edu/courses/course_papers/protected/" %}
{% if p.link != None %}
{% assign dir = p.link %}
[{{ p.title }}]({{ p.link }}) by {{ p.author }} *{{ p.journal }}* {{ p.volume }}{{ p.number }} {{ p.year }}. {{ p.description }}
{% elsif p.PDF != None %}
[{{ p.title }}]({{ dir }}{{ p.PDF }}) by {{ p.author }} *{{ p.journal }}* {{ p.volume }}{{ p.number }} {{ p.year }}. {{ p.description }}
{% else %}
{{p.title}} by {{ p.author }} *{{ p.journal }}* {{ p.volume }}{{ p.number }} {{ p.year }}. {{ p.description }}
{% endif %}
{% endfor %}
{% endfor %}
