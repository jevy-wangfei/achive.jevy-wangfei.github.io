---
layout: default
title: Jevy's Blog
---
<div id="header">
{% include header.html %}
</div>
<div id="timeline">
				{% for post in site.posts %}
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
							    <hr>
							</div>
					    </div>
					{% endif %}
				{% endfor %}
	<div class="post_timeline personal">
		<div class="timeline_meta"><time>JANUARY<br /><small>2014</small></time>
		</div>
		<div class="timeline_body">{% include personal.htm %}<hr>
		</div>
	</div>
		
	
</div>

<div id="footer">
{% include footer.html %}
</div>
