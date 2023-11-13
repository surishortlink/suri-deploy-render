# Suri × Deploy to Render

You're viewing a template repository tailored for deploying Suri to
[Render](https://render.com/).

What's Suri? Suri is your own link shortener that's easily deployed as a static
site. No server-side hosting, serverless cloud functions, or database necessary.
Head over to the main [`jstayton/suri`](https://github.com/jstayton/suri)
repository to learn more, including additional deployment methods.

## Setup

1. Click the "Use this template" button above and then "Create a new
   repository". Fill in the required details to create a new repository based on
   this one.
2. On the [Render Dashboard](https://dashboard.render.com/), create a new
   Blueprint.
3. Connect or re-configure your GitHub account to grant access to your new
   repository. Select that repository and hit "Connect".
4. Give the Blueprint a name, such as "Suri". The `main` branch should already
   be selected. Hit "Apply" to begin the build and deploy process.
5. Any commits to the `main` branch of your new repository will trigger a new
   deploy. You can change this by going to the "Settings" of your `suri` service
   and editing the "Branch" and "Auto-Deploy" options.
6. If you want to use a custom domain, follow Render's guide:
   [Custom Domains](https://render.com/docs/custom-domains).

## Manage Links

Links are managed through [`./src/links.json`](./src/links.json), which is
seeded with a few examples to start:

```json
{
  "/": "https://github.com/jstayton/suri",
  "1": "https://fee.org/articles/the-use-of-knowledge-in-society/",
  "tw": "https://twitter.com"
}
```

It couldn't be simpler: the key is the "shortlink" path that gets redirected,
and the value is the target URL. Keys can be as short or as long as you want,
using whatever mixture of characters you want. `/` is a special entry for
redirecting the root path.

Go ahead and make an edit, then commit and push to your repository. Render
should automatically build and deploy your change. That's it!

## Config

Config options are set in [`suri.config.json`](suri.config.json). There is only
one at this point:

| Option | Description                                                        | Type    | Default |
| ------ | ------------------------------------------------------------------ | ------- | ------- |
| `js`   | Whether to redirect with JavaScript instead of a `<meta>` refresh. | Boolean | `false` |
