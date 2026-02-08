---
title: People
permalink: /people/
---

<style>
  /* --- 网格布局控制器 --- */
  .people-grid {
    display: grid;
    /* 强制一行3列，每列宽度相等 */
    grid-template-columns: repeat(3, 1fr); 
    /* 行间距40px，列间距20px */
    gap: 40px 20px; 
    width: 100%;
    box-sizing: border-box;
  }

  /* --- 关键修复：强制覆盖主题默认样式 --- */
  .people-grid .list-item-people {
    width: auto !important;  /* 禁止占满一行 */
    margin: 0 !important;    /* 去掉默认外边距 */
    padding: 0 !important;
    text-align: center;      /* 文字居中 */
    display: flex;           /* 使用flex布局 */
    flex-direction: column;  /* 垂直排列（图在上，字在下） */
    align-items: center;     /* 内容水平居中 */
  }

  /* --- 214x214 标准方框 --- */
  .img-box {
    width: 214px;
    height: 214px;
    /* 这一行可选：如果你想看到方框的边界，可以加个浅灰色背景，不需要就删掉 */
    /* background-color: #f5f5f5; */ 
    
    /* 让图片在盒子里上下左右绝对居中 */
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    margin-bottom: 10px; /* 图片和名字之间的距离 */
  }

  /* --- 图片自适应逻辑 --- */
  .img-box img {
    /* 保证图片不超过盒子 */
    max-width: 100%;
    max-height: 100%;
    width: auto;
    height: auto;
    
    /* contain: 完整显示图片（会有留白）
       cover: 填满盒子（会裁切掉一部分） 
       你之前的描述想要“resize到214贴进方块”，用 contain 最安全 */
    object-fit: contain; 
    
    /* 去掉图片自带的边框或阴影 */
    margin: 0;
    padding: 0;
    box-shadow: none;
  }

  /* --- 手机端适配：变成单列 --- */
  @media (max-width: 768px) {
    .people-grid {
      grid-template-columns: 1fr;
    }
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
        {% if profile.avatar %}
            {% if profile.position == "pi" %}
                                <a href="{{ site.baseurl }}{{ profile.url }}"><img width="285" height="214" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
            {% else %}
                <div class="img-box">
                    <a href="{{ site.baseurl }}{{ profile.url }}" style="display:flex; width:100%; height:100%; justify-content:center; align-items:center;">
                        <img src="{{site.baseurl}}/images/people/{{profile.avatar}}">
                    </a>
                </div>
            {% endif %}
        {% else %}
             <div class="img-box">
                <a href="{{ site.baseurl }}{{ profile.url }}"><img src="http://evansheline.com/wp-content/uploads/2011/02/facebook-Storm-Trooper.jpg"></a>
             </div>
        {% endif %}
        
        <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
    </div>    
    {% endif %}
  {% endfor %}
</div>
{% endfor %}
