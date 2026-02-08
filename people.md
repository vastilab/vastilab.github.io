---
title: People
permalink: /people/
---

<style>
  /* 针对学生和校友的网格布局：一行3个，间距20px */
  .people-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* 强制3列 */
    gap: 30px 20px; /* 行间距30px，列间距20px */
    align-items: start; /* 顶部对齐 */
  }
  
  /* 移动端适配：手机上变回单列，防止太挤 */
  @media (max-width: 768px) {
    .people-grid {
      grid-template-columns: 1fr;
    }
  }

  /* 214x214 的标准相框容器 */
  .img-box {
    width: 214px;
    height: 214px;
    background-color: #f9f9f9; /* 可选：给留白部分一个淡淡的背景色，不要可以删掉 */
    margin: 0 auto 10px auto;  /* 居中并保持下方间距 */
    
    /* 让图片在方块里上下左右居中 */
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
  }

  /* 图片在相框里的样式 */
  .img-box img {
    max-width: 100%;
    max-height: 100%;
    width: auto;
    height: auto;
    object-fit: contain; /* 关键：保证长边缩放至214，完整显示 */
  }
  
  /* 名字居中对齐 */
  .list-item-people {
    text-align: center;
  }
</style>

{% assign people_sorted = (site.people | sort: 'joined' %}
{% assign people_array = "pi|gradstudent|alumni" | split: "|" %}

{% for item in people_array %}

<div class="pos_header">
{% if item == 'pi' %}
<h3>Founder</h3>
 {% elsif item == 'gradstudent' %}
<h3>Team Member</h3>
 {% elsif item == 'alumni' %}
<h3>Alumni</h3>
{% endif %}
</div>

<div class="content list people {% if item != 'pi' %}people-grid{% endif %}">
  {% for profile in people_sorted %}
    {% if profile.position contains item %}
    <div class="list-item-people">
      <div class="list-post-title">         {% if profile.avatar %}
                        {% if profile.position == "pi" %}
                <a href="{{ site.baseurl }}{{ profile.url }}"><img width="285" height="214" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
            {% else %}
                <div class="img-box">
                    <a href="{{ site.baseurl }}{{ profile.url }}">
                        <img src="{{site.baseurl}}/images/people/{{profile.avatar}}">
                    </a>
                </div>
            {% endif %}
        {% else %}
             <div class="img-box">
                <a href="{{ site.baseurl }}{{ profile.url }}"><img src="http://evansheline.com/wp-content/uploads/2011/02/facebook-Storm-Trooper.jpg"></a>
             </div>
        {% endif %}
        
        <div>
            <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
        </div>
      </div>
    </div>    
    {% endif %}
  {% endfor %}
</div>
{% endfor %}
