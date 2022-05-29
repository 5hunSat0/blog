## 5hunSat0 blog (記録用)

github pages で構成した記録用 blog。 用法はその時の気分で変わります。


### 投稿一覧
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

