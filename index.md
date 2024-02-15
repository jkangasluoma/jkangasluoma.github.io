# Jargon lyhärit

Aloin kirjoittaa näkemistäni teatterielokuvista lyhytarvosteluja tai muuten vain tajunnanvirtaisia kommentaareja ystäville ja tutuille noin 2012 lähtien. Tämä sivusto kokoaa nämä elokuvakommentit kronologisesti.

{% for post in site.posts %}

  {% capture year_of_current_post %}
  {{ post.date | date: "%Y" }}
  {% endcapture %}

  {% capture year_of_previous_post_in_set %}
  {{ site.posts[forloop.index].date | date: "%Y" }}
  {% endcapture %}

  {% if forloop.first %}
  <h2>{{ year_of_current_post }}</h2>
  <ul>
  {% endif %}

          <li><a href="{{ post.url }}">{{ post.title }}</a></li>

  {% if forloop.last %}
  </ul>
  {% else %}
  {% if year_of_current_post != year_of_previous_post_in_set %}
  </ul>

  <h2>{{ year_of_previous_post_in_set }}</h2>
  <ul>
  {% endif %}
  {% endif %}

{% endfor %}
