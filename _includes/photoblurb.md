
Images captured on a mix of film, mobile and digital with a bias toward 35mm film. My favorite film stocks are Kodak's offerings of Ektar 100, Gold 200 and Portra 800. As for digital, I like Fujifilm's X series of cameras, so that is what I use.

<style>
/* Style the buttons */
.btn {
  outline: 1px;
  border: 0px;
  outline-style: dotted;
  outline-color: #010101;
  padding: 12px 16px;
  background-color: white;
  cursor: pointer;
}

.btn:hover {
  background-color: #ddd;
}

.btn.active {
  background-color: #666;
  color: white;
}

.post-title {
  font-family: 'Space Grotesk', sans-serif;
}
</style>

<div id="myBtnContainer">
  {%- assign pagelist = site.pages | where: "filter", "photos" -%}
  {% if page.category != "Show All" %}<button class="btn" onclick="window.location.href= '/photos/' "> Show All</button> {% endif %}
  <button class="btn active" onclick="window.location.href= '{{ page.url }} '"> {{ page.category }} </button>
  <button class="btn" onclick="showMore()">Filter...</button>
  <span id="more">
  {% for others in pagelist %}
  {% if page.url != others.url %}
  <button class="btn" onclick="window.location.href= '{{ others.url }}' "> {{ others.category }} </button>
  {% endif %}
  {% endfor %}

  </span>
</div>

<script>

window.location.replace(page.url); 

</script>
