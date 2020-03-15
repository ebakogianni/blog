---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
# πριν περιείχε απλώς τη γραμμή:
# layout: home

layout: carte
---
<p class="bloc-gris">Pour visualiser les calques et la liste des lieux faites apparaître les outils de la carte (<img src="https://ebakogianni.github.io/paris-au-cinema/assets/bouton_outils.png" alt="Bouton Outils">) et cliquez sur <img src="https://ebakogianni.github.io/paris-au-cinema/assets/bouton_calques.png" alt="Bouton Calques"> puis sur <img src="https://ebakogianni.github.io/paris-au-cinema/assets/bouton_visualiser_les_donnees.png" alt="Bouton Visualiser les données">. Les lieux sont classés par décennie et triés selon l'ordre alphabétique du titre de film puis selon leur ordre d'apparition dans le film. Il est possible de filtrer les contenus en saisissant un mot-clé (mot du titre, année, réalisateur, adresse) dans la barre de recherche. Les points rouges marquent les principaux lieux des films traités dans les <a href="https://ebakogianni.github.io/paris-au-cinema/articles/">articles</a> du site.
</p>

&nbsp;

# Dernier article

<ul class="post-list">
  {% for post in site.posts limit: 1 %}
    <li>
      <div>
      {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
       <span class="post-meta">{{ post.date | date: date_format }}</span> <!---|
       {% for tag in post.tags %}
      <a class="post" href="/tag/{{ tag | downcase | url_encode }}"><small>{{ tag }}</small></a>{% unless forloop.last %}, {% endunless %}
      {% endfor %} --->
       <h3>
          <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
          </a>
        </h3>
      <figure class="post-cover" style="float: left">
        <a href="{{ post.url | relative_url }}"><img src="{{ post.image | prepend: site.baseurl }}" alt="{{ post.title }}" title="{{ post.title }}"></a>
      </figure>
       {{ post.excerpt | strip_html | truncatewords: 100 }}
       <a href="{{ post.url | relative_url }}">Lire la suite</a>
      </div>   
    </li>
  {% endfor %}
</ul>