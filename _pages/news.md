---
layout: wide
permalink: /news/
redirect_from:
  - /updates/
pagination:
  enabled: true
---

<div id="blog" class="usa-graphic-list usa-section usa-section--dark sign-up-intro">
  <div class="grid-container maxw-desktop">
    <h1 class="margin-0">Form Service News</h1>
  </div>
</div>
<div class="grid-container padding-bottom-2 maxw-desktop">
  <div class="grid-row">
    <div class="desktop:grid-col-8 usa-prose padding-right-4">
      <!-- This loops through the paginated posts -->
      {% for post in paginator.posts %}
      <div
        class="padding-bottom-5 margin-top-4 usa-prose border-bottom-05 border-base-lightest usa-content"
      >
        <h3 class="title">
          <a
            class="usa-link text-no-underline"
            href="{{ site.baseurl }}{{ post.url }}"
            >{{post.title}}</a
          >
        </h3>
        <div class="margin-bottom-2">
          <div class="margin-top-neg-105 font-family-ui">
            {{ post.date | date: '%B %d, %Y' }}
          </div>
        </div>
        <div >
          {% if post.image %} {% asset "{{ post.image }}"
          class="tablet:float-left tablet:width-1/3 padding-right-3
          padding-top-1" alt="{{ post.image_alt_text }}" %} {% endif %} {{
          post.excerpt | markdownify }}
        </div>
      </div>
      {% endfor %}
      <!-- Pagination links -->
      <div class="grid-row padding-top-2">
        <div
          class="tablet:grid-col-4 text-center tablet:order-2 font-body-xs text-base"
        >
          Page {{ paginator.page }} of {{ paginator.total_pages }}
        </div>
        <div class="tablet:grid-col-4 text-right tablet:order-3">
          {% if paginator.next_page %}
          <a
            href="{{ paginator.next_page_path | prepend: site.baseurl }}"
            class="paginate-link usa-link font-family-ui text-no-underline text-bold tablet:margin-top-0"
            >Next {{ paginator.per_page }} Posts &rsaquo;</a
          >
          <a
            href="{{ paginator.next_page_path | prepend: site.baseurl }}"
            class="paginate-button usa-button margin-top-3 font-family-ui"
            >Next {{ paginator.per_page }} Posts &rsaquo;</a
          >
          {% endif %}
        </div>
        <div class="tablet:grid-col-4 text-left tablet:order-1">
          {% if paginator.previous_page %}
          <a
            href="{{ paginator.previous_page_path | prepend: site.baseurl }}"
            class="paginate-link usa-link font-family-ui text-no-underline tablet:margin-top-0"
            >&lsaquo; Previous {{ paginator.per_page }} Posts</a
          >
          <a
            href="{{ paginator.previous_page_path | prepend: site.baseurl }}"
            class="paginate-button font-family-ui usa-button margin-top-2"
            >&lsaquo; Previous {{ paginator.per_page }} Posts</a
          >
          {% endif %}
        </div>
      </div>
    </div>

  </div>
  <div class="grid-row padding-top-4 tablet:padding-x-4 margin-bottom-4">
    <a class="usa-link" href="#blog">Return to top</a>
  </div>
</div>
