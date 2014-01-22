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
									{{ post.date | date: "%B" }}<small>{{ post.date | date: "%Y" }}</small>
								</time>	
							</div>
							<div class="timeline__body">
								{% if post.quote %}
									{{ post.content }}
									<blockquote>
										<span class="quote">&#8220;<br>&#8221;</span>
										<p>{{ post.quote }}</p>
									</blockquote>
								{% else %}
									{{ post.content }}
								{% endif %}
							    <hr>
							</div>
					    </div>
					{% endif %}
				{% endfor %}

</div>

<div id="footer">
{% include footer.html %}
</div>
