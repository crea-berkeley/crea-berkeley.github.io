Blog for CREA
=============

How to Publish a Blog Post
--------------------------

This blog is maintained using the Jekyll static site generator. Check out the [Jekyll](http://jekyllrb.com/) website on installation and usage instructions. The instructions below assume you have Jekyll already installed.

1. Create an empty Markdown file with filename in the format `YYYY-MM-DD-title-of-blog-post.md` in the `_posts` directory. For example, the filename `2015-01-03-relation-extraction-by-example.md` refers to a blog post authored on January 3, 2015 titled "Relation Extraction by Example".
2. Add the following information to the top of the Markdown file, replacing the content in angular brackets (`<>`) with the relevant information.

    ```
    ---
    layout: post
    title: <Title of Blog Post>
    author: <Full Name>
    ---
    ```

3. Compose your blog in Markdown format, below the header inserted above. Jekyll will transform the Markdown file into HTML that can be displayed in the browser. The [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) and [Daring Fireball: Markdown Syntax Documentation](http://daringfireball.net/projects/markdown/syntax) are useful resources for Markdown reference. As you are working on the page you can have `jekyll serve` running, which will generate the HTML files as you save your changes. This makes it easier to preview how the blog post will look since all you need to do is to refresh the blog page in the browser.
4. After you are done with the page, just commit, push, and submit a pull request.
