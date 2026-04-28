# Listings

Introduction to a very useful quarto feature

![](mondrian.jpg)

Mondrian: Tableau I

Listings are a powerful and flexible way to generate collections of content automatically from your Markdown files. As the name suggests, a *listing* pulls together multiple documents and renders them as a structured list—useful for feature grids, blog indexes, documentation overviews, and more.

For example, the feature cards on the main page of this theme are not written manually. Instead, they are generated from all Markdown documents inside the `features/` directory. This keeps your content modular and maintainable: you simply add or edit files in that folder, and the listing updates itself automatically.

### Defining a Listing

Listings are configured in your document’s YAML frontmatter. Here’s a basic example:

``` yaml
listing:
  - id: listing-features
    contents: 
      - ./features/
      - "!/features/index.qmd"
    type: grid
    sort: "date desc"
    fields: [image, title, description] 
```

Each option controls a different aspect of how the listing behaves and appears:

- `id`: A unique identifier for the listing. You’ll use this to place it in your document.
- `contents`: Specifies which files to include. You can point to directories, individual files, or exclude files using the `!` prefix.
- `type`: Determines the layout (e.g., `grid`, `list`, etc.).
- `sort`: Controls ordering, such as sorting by date in descending order.
- `fields`: Defines which metadata from each document should be displayed (e.g., author, date, title, etc).

Listings can be rendered in different layouts depending on your needs. You can see an example of a \*gridÜ layout on the [main page](https://mdwm.org/quarto-pressmark/#features), where features are displayed as cards with images and descriptions. In contrast, the [features page](https://mdwm.org/quarto-pressmark/features/) itself uses a list-style layout, presenting the same content in a more compact, linear format.

### Placing a Listing in Your Page

Once defined, you can render the listing anywhere in your document by referencing its `id`. For example:

``` html
::: {#listing-features}
<!-- The listing will be injected here -->
:::
```

At build time, this placeholder is replaced with the generated listing based on your configuration.

### Going Further

Listings in Quarto support a wide range of customization options, including filtering, categorization, pagination, and custom templates. You can also combine listings with frontmatter metadata (like tags or categories) to create more dynamic and interactive content structures.

For a deeper dive into all available options—such as advanced filtering, custom layouts, and display controls—refer to the [official documentation](https://quarto.org/docs/websites/website-listings.html)
