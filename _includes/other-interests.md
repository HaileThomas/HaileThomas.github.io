## Other Interests

Outside of research, I'm a big movie fan. Here's my current top twenty:

{% assign top = site.data.movies | first %}
<div class="callout movie-pick">
  <div class="movie-row">
    <span>🎬 <strong>{% if top.link %}<a href="{{ top.link }}" target="_blank" rel="noopener">{{ top.title }}</a>{% else %}{{ top.title }}{% endif %}</strong>{% if top.year %} ({{ top.year }}){% endif %}</span>
    <a href="#" id="movie-toggle" class="movie-next" aria-expanded="false" aria-controls="movie-list">See full top 20 ↓</a>
  </div>
  <ol id="movie-list" class="movie-list" hidden>
    {% for m in site.data.movies %}
    <li title="{{ m.title }}{% if m.year %} ({{ m.year }}){% endif %}"><strong>{% if m.link %}<a href="{{ m.link }}" target="_blank" rel="noopener">{{ m.title }}</a>{% else %}{{ m.title }}{% endif %}</strong>{% if m.year %} ({{ m.year }}){% endif %}</li>
    {% endfor %}
  </ol>
</div>

<script>
(function () {
  var toggle = document.getElementById("movie-toggle");
  var list = document.getElementById("movie-list");
  toggle.addEventListener("click", function (e) {
    e.preventDefault();
    var open = list.hidden;
    list.hidden = !open;
    toggle.setAttribute("aria-expanded", open);
    toggle.textContent = open ? "Hide top 20 ↑" : "See full top 20 ↓";
  });
})();
</script>
