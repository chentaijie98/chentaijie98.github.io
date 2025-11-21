---
layout: archive
permalink: /teaching/
title: "Teaching"
author_profile: true
---

<div class="ai-background" style="padding:20px 0;">

<div class="card-container">
<p style="font-size:16px;line-height:1.8;">
As a dedicated educator, I have been involved in teaching activities at both <strong>The University of Hong Kong</strong> and <strong>Nankai University</strong>. Below are the courses I have contributed to as a teaching assistant and instructor.
</p>
</div>

<i class="fas fa-chalkboard-teacher" style="color:#667eea;"></i> Teaching Experience

<div class="teaching-list">

{% for post in site.teaching reversed %}
<div class="card-container" style="border-left-color:#667eea;margin-bottom:25px;">
<h3 style="margin:0 0 10px 0;color:#667eea;font-size:20px;">
<i class="fas fa-graduation-cap"></i> {{ post.title }}
</h3>
<p style="margin:5px 0;color:#666;font-size:15px;">
<i class="fas fa-university"></i> <strong>{{ post.venue }}</strong>
</p>
<p style="margin:5px 0;color:#666;font-size:15px;">
<i class="fas fa-calendar-alt"></i> {{ post.date | date: "%B %Y" }} | <i class="fas fa-tag"></i> {{ post.type }}
</p>
<p style="margin:5px 0;color:#666;font-size:15px;">
<i class="fas fa-map-marker-alt"></i> {{ post.location }}
</p>

{% if post.excerpt %}
<div style="margin-top:15px;padding-top:15px;border-top:1px solid #e0e0e0;">
{{ post.excerpt | markdownify }}
</div>
{% endif %}

<p style="margin:15px 0 0 0;">
<a href="{{ post.url }}" class="styled-link" style="font-size:15px;">
<i class="fas fa-arrow-right"></i> View Details
</a>
</p>
</div>
{% endfor %}

</div>

</div>

<style>
.teaching-list {
  margin-top: 20px;
}

.teaching-list h3 i {
  margin-right: 8px;
}

.teaching-list .card-container:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 24px rgba(102, 126, 234, 0.2);
}
</style>
