# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    The router holds the different routes & their respective paths, and the
    route determines behavior & generates viewstates for that particular path.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to 'campus.boston'}}{{/link-to}}
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    1. The first route is actually nested under 'products', while the second one
    is not.
    2. The first one will allow us to add an {{outlet}} to the products template
    so each individual product renders in that view, but it won't allow us to
    use the back button to get back to just the products view because it thinks
    we are already there (due to nesting.) The second way is the correct 'Ember
    way' to create these routes, and it allows us to specify the url path we
    want without actually nesting.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    params.movie_id
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    model (using either each model as |something| or directly using model.name,
    etc.)
    ```
