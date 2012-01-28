---
layout : layout
title : code52
---

{% include latest_project.html %}

<ul class="ideas">
    {% for post in site.posts %}
		<li>
			<div class="idea">
				{% if forloop.first and post.layout == "post" %}
					<h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
					
					<div class="postdate">{{ post.date | date: "%e %B, %Y"  }}
						<ul>
						{% for tag in post.tags %}
							<li><a href="/tag/{{ tag }}">{{ tag }}</a></li>
						{% endfor %}
						</ul>
					</div>
					
					{{ post.content }}
					<br />
					<a href="{{ post.url}}#disqus_thread">Comments</a>
				{% else %}
					<h2><a class="postlink" href="{{ post.url }}">{{ post.title }}</a></h2>
					<div class="postdate">{{ post.date | date: "%e %B, %Y"  }}
						<ul>
						{% for tag in post.tags %}
							<li><a href="/tag/{{ tag }}">{{ tag }}</a></li>
						{% endfor %}
						</ul>
					</div>
					{{ post.content }}
					
					<a href="{{ post.url }}#disqus_thread">Comments</a>
				{% endif %}
			</div>
		</li>
    {% endfor %}
</ul>
	
<script type="text/javascript">
//<![CDATA[
(function() {
    var links = document.getElementsByTagName('a');
    var query = '?';
    for(var i = 0; i < links.length; i++) {
    if(links[i].href.indexOf('#disqus_thread') >= 0) {
        query += 'url' + i + '=' + encodeURIComponent(links[i].href) + '&';
    }
    }
    document.write('<script charset="utf-8" type="text/javascript" src="http://disqus.com/forums/code52/get_num_replies.js' + query + '"></' + 'script>');
})();
//]]>
</script>