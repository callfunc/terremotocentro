---
layout: page
title: News
permalink: /news/
---


{% assign filteredissues = site.data.issuesjson | where: "state","open" %}
{% for member in filteredissues %}
{% if member.issue.labels contains "Notizie Utili" %}
* <a href="/issues/{{ member.number | datapage_url: '.' }}">{{member.title}}</a>
{% endif %}
{% endfor %}

<section class="sieve">
        <div class="panel-group" id="feed_display"></div>
          <div style="clear:both;"></div>
</section>


<!-- Include all compiled plugins (below), or include individual files as needed -->
<script src="//code.jquery.com/jquery-1.12.3.js"></script>
<script type="text/javascript" src="../js/moment.js"></script>
<script type="text/javascript" src="../js/FeedEk.js"></script>
<script type="text/javascript" src="../js/masonry.js"></script>
<script type="text/javascript" src="../js/FeedEk_news.js"></script>
<!-- form di ricerca delle news -->
<script src="../js/jquery.sieve.min.js" type="text/javascript"></script>
<script>
  var searchTemplate="<div class='form-group'><div class='input-group'><div class='input-group-addon'>Cerca:</div><input type='text' class='form-control' placeholder='(cerca qui...)'></div></div>"
  $("section.sieve").sieve({ itemSelector: "li" });
</script>
<style> div.form-inline.text-center {padding-bottom: 8rem;} .itemTitle a {font-weight: bold; color: #337ab7 !important; text-decoration: none;} </style>
