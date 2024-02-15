# Jargon / lyhärit

Aloin kirjoittaa teatterielokuvista lyhytarvosteluja tai muuten vain tajunnanvirtaisia kommentaareja pienelle piirille noin 2012 lähtien. Tämä sivusto kokoaa nämä elokuvakommentit kronologisesti.

{% for post in site.categories["movie"] %}

  {% capture year_of_current_post %}
  {{ post.date | date: "%Y" }}
  {% endcapture %}

  {% capture year_of_previous_post_in_set %}
  {{ site.categories["movie"][forloop.index].date | date: "%Y" }}
  {% endcapture %}

  {% if forloop.first %}
  <h2>{{ year_of_current_post }}</h2>
  <ol reversed="true">
  {% endif %}

          <li><a href="{{ post.url }}">{{ post.title }}</a></li>

  {% if forloop.last %}
  </ol>
  {% else %}
  {% if year_of_current_post != year_of_previous_post_in_set %}
  </ol>

  <h2>{{ year_of_previous_post_in_set }}</h2>
  <ol reversed="true">
  {% endif %}
  {% endif %}

{% endfor %}
