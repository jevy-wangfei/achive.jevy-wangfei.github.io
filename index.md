---
layout: default
title: Jevy's Blog
---
<div id="menu">
<li><a href="#" id="personal">Personal</a></li>
<li><a href="#" id="project">Works</a></li>
<li><a href="#" id="article">Article</a></li>
<li><a href="#" id="picture">Picture</a></li>
<!-- <li><a href="#" id="portfolio">Learn Portfolio</a></li>
<li><a href="#" id="pc">PC Blog</a></li> -->
<li><a href="#" id="all" class="live">All</a></li>
</div>
<div id="aboutme">
<div class="me_img"><img src="img/me.jpg"/></div>
<div class="me">
<h1>Wang Fei</h1>
<p>A graduate master of computer science student.
Four years java programming experience, and familiar with python, shell, PL/SQL, JS, Linux/Unix, Oracle, MySQL, Cassandra and computer network.<br>

Resume: <a href="./pdf/personal.pdf">Wang's CV in pdf</a>  &nbsp;
Github Addr: <a href="https://github.com/jevy-wangfei">Github</a> &nbsp;
Recent <a href="#projectList"> Works </a>
  </p>
</div>
</div>
<div class="content">
<div class="leftNav">
    {% for post in site.posts %}
        <li class="post-teaser {{ post.tags | join:' ' }}" onclick="showArticle('{{post.dd}}')">
            <a href="#">
                <span class="post-teaser__title">{{ post.title }}</span>
                <!-- <span class="post-teaser__date">{{ post.date | date: "%d %B %Y" }}</span> -->
            </a>
        </li>
    {% endfor %}
</div>
<div id="timeline" >



				{% for post in site.posts %}
					{% if post.category == 'timeline' %}
					    <div class="post__timeline {{ post.tags | join:' ' }}" id="{{post.dd}}">
					    	<div class="timeline__meta">
								<time datetime="{{ post.date }}">
									{{ post.date | date: "%B" }}<br/><small>{{ post.date | date: "%Y" }}</small>
								</time>
							</div>
							<div class="timeline__body">
								{% if post.quote %}

									<blockquote>
										<span class="quote">&#8220;<br>&#8221;</span>
										<p>{{ post.quote }}</p>
									</blockquote>
									{{ post.content }}
								{% else %}
									{{ post.content }}
								{% endif %}

							</div>
					    </div>
					{% endif %}
				{% endfor %}

      </div>
</div>

<div id="footer">
{% include footer.html %}
</div>
