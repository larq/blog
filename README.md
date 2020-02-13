# Larq Blog

The Larq Blog is built using [Hugo](https://gohugo.io/), a Go-based static site builder. It gets built and deployed automatically on pushes to the `master` branch. To build the blog locally:

1. [Install Hugo](https://gohugo.io/getting-started/installing)
1. `hugo server` (use `hugo server -D` to show draft posts too)
1. Visit `http://localhost:1313/`

To add a new post:

1. `hugo new blog/post-name.md`
1. `hugo server -D` (shows posts that are in draft mode)
