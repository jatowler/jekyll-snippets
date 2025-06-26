# jekyll-snippets
Convenience functions, includes, and plugins for Jekyll blogs

## Includes
These snippets go in your `_includes` folder and can be dropped into any layout, post, page, or other include.

### `breadcrumb-schema.html`
For providing [Schema.org breadcrumb](https://schema.org/BreadcrumbList) structured data ([Google documentation](https://developers.google.com/search/docs/appearance/structured-data/breadcrumb)).

Does not create visual content.

Example YAML frontmatter to implement [the Google example](https://developers.google.com/search/docs/appearance/structured-data/breadcrumb#year-genre%20example):

```yaml
breadcrumb:
  - name: "Books"
    url: /books
  - name: "Science Fiction"
    url: /books/sciencefiction
```

Note that the current page is always included as the final breadcrumb using its `title` attribute.

### `faq-schema.html`
For providing [Schema.org FAQ](https://schema.org/FAQPage) structured data ([Google documentation](https://developers.google.com/search/docs/appearance/structured-data/faqpage)). Note that Google only provides FAQ "rich results" for "well-known, authoritative websites that are government-focused or health-focused." But the structured data can help search engines and LLMs understand your page better anyway.

Does not create visual content.

Example YAML frontmatter to implement [the Google example](https://developers.google.com/search/docs/appearance/structured-data/faqpage#examples):

```yaml
faq:
  - q: How to find an apprenticeship?
    a: We provide an official service to search through available apprenticeships. To get started, create an account here, specify the desired region, and your preferences. You will be able to search through all officially registered open apprenticeships.
  - q: Whom to contact?
    a: You can contact the apprenticeship office through our official phone hotline above, or with the web-form below. We generally respond to written requests within 7-10 days.
```

Note that the snippet strips paragraph (`<p>`/`</p>`) tags, so if you need to include them you need to edit the snippet (just delete `| remove: '<p>' | remove: '</p>'` from line 12).
