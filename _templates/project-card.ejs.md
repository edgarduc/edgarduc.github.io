```{=html}
<div class="project-grid list">
<% for (const item of items) { %>
  <article class="project-card" <%= metadataAttrs(item) %>>

    <% if (item.image) { %>
      <img
        class="project-image"
        src="<%- item.image %>"
        alt="<%- item['image-alt'] || item.title %>"
        loading="lazy"
      >
    <% } %>

    <div class="project-body">
      <div class="project-header">
        <h3 class="listing-title project-title"><%- item.title %></h3>
        <% if (item.year) { %>
          <span class="listing-year project-year"><%- item.year %></span>
        <% } %>
      </div>

      <p class="listing-description project-description">
        <%- item.description %>
      </p>

      <% if (item.concepts && item.concepts.length) { %>
        <div class="listing-concepts project-tags">
          <% for (const concept of item.concepts) { %>
            <span class="project-tag"><%- concept %></span>
          <% } %>
        </div>
      <% } %>

      <div class="project-links">
        <% if (item.github) { %>
          <a href="<%- item.github %>">GitHub</a>
        <% } %>

        <% if (item.pdf) { %>
          <a href="<%- item.pdf %>">PDF</a>
        <% } %>

        <% if (item.paper) { %>
          <a href="<%- item.paper %>">Paper</a>
        <% } %>

        <% if (item.demo) { %>
          <a href="<%- item.demo %>">Demo</a>
        <% } %>
      </div>
    </div>
  </article>
<% } %>
</div>
```