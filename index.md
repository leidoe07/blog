# **My Blog**


Hi! I'm [*Leilani Dore*](https://leidoe07.github.io/), a senior in the Brooklyn STEAM Center learning Backend Development.

I'm using this blog to document everything I learn, build, and improve on.


<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
