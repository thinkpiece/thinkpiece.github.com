JY Tech Blog
============

HOWTO
-----


1. Create a new file in the _post and name it as [yyyy-mm-dd-title.md]
2. All post files must begin with YAML Front Matter
3. Commit and push to the remote repository


STRUCTURE
---------

    _includes/ (parts of html files)
    ├── analytics.html
    ├── comments.html
    ├── footer.html
    ├── head.html
    ├── header.html
    └── summary.html
    _layouts/ (default static html template)
    ├── default.html
    ├── page.html
    └── post.html
    _posts/
    └── (posts named as (date)-(title).md)
    _sass/
    ├── _base.scss
    ├── _layout.scss
    └── _syntax-highlighting.scss
    css/
    └── main.scss
    _config.yml
    about.md
    archive.html (a page that shows all archieves in chronological order)
    CNAME
    feed.xml
    Gemfile
    Gemfile.lock
    index.html
    tag.md (a page that show article list according to tags)




Useful Links
------------

- [Jekyll]
- [Markdown]

[Jekyll]: http://jekyllrb.com
[Markdown]: http://daringfireball.net/projects/markdown/
