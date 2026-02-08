---
title: Vast Intelligence Lab
---


**Vast Intelligence Lab (VIL)** is an independent research laboratory founded by Wenhao Wang in Sydney, Australia. The lab is dedicated to addressing real-world research challenges and disseminating its findings through top-tier conferences and journals. VIL currently comprises a team of around 10 members, with research interests spanning (multimodal) large language models, agentic AI, visual generation, AI safety, and reinforcement learning.


### **Lab News**
<div class="content list">
  {% for post in site.posts %}
    {% if post.categories contains 'blog' %}
    <div class="list-item">
    <p class="list-post-title">
        <a href="{{ site.baseurl }}{{ post.url }}"><span style="color:#268bd2;">- {{ post.title }}</span></a> (<small>{{post.date | date: "%m/%d/%y" }}</small>)
        </p>
    </div>
    {% endif %}
  {% endfor %}
</div>

<br>

### Contact Us
We welcome collaborations and partnerships. Please feel free to reach out to **Wenhao Wang** at **wangwenhao@vastilab.com**.

### Welcome to Sydney

![Sydney](https://raw.githubusercontent.com/vastilab/vastilab.github.io/main/images/sydney_2.jpeg)
