---
layout: xtUML
title: xtUML Portfolio
---
<div id="timeline" >
<div id="menu">
<li><a href="#" id="personal">Description</a></li>
<li><a href="#" id="article">Class</a></li>
<li><a href="#" id="picture">State</a></li>
<li><a href="#" id="design">Process</a></li>
<li><a href="#" id="all" class="live">All</a></li>
</div>
<div id="aboutme">
<h1>Wang Fei</h1>
<p>I am interested in large-scale data process and artificial intelligent. After working in ZTESoft for three years,
I decided to go to ANU for further study. </p>
</div>

				{% for post in site.post.xtuml %}
					{% if post.category == 'timeline' %}
					    <div class="post__timeline {{ post.tags | join:' ' }}">
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
<div id="footer">
{% include footer.html %}
</div>