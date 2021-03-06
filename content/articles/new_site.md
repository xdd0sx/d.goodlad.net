The technical bits of this new site are rather interesting. It is generated by
[nanoc](http://nanoc.stoneship.org/). The [susy
plugin](http://susy.oddbird.net/) for [compass](http://www.compass-style.org/)
is the basis for the styling: the grid layout and the vertical rhythm of the
pages.


## nanoc

nanoc is a static site generator; one of many, in fact. I chose it mainly
because of its flexibility. That flexibility, though, can be a bit of a
hurdle when you first start using it.

Since there is no pre-defined structure for your nanoc site, it can be
daunting to figure out where to start on a new project. If you're interested,
my site's source is available on
[Github](https://github.com/dgoodlad/d.goodlad.net). The interesting files
are:

* _Rules_: note the inclusion of compass and the susy plugin here, as well as
  the handling of asset files that don't need to be processed in any way.
* _content/index.html_: nanoc provides some pre-built helper modules, one of
  which, *Blogging*, gives access to a *sorted_articles* method. It's used
  here to list exerpts from the three most recent articles.
* _content/articles/*_ there are a pair of files here for each article. In the
  yaml metadata file, note the *kind* and *created_at* fields which are treated
  specially by the *Blogging* helpers.


## susy

The susy plugin provides a number of sass mixins to lay out content in a grid
and to maintain vertical rhythm even when changing fonts and sizes.

I wrote a small mixin that changes the default behavior for font resizing.
Instead of accepting CSS's normal vertical centering of text within its
*line-height* property, I add an offset using margin-top to ensure that the
text's baseline matches that of all the other text. This helps, for example,
line up headings with regular text beside them.

I've sent a [pull
request](https://github.com/ericam/compass-susy-plugin/pull/11) to the author
of susy to include this mixin in the plugin itself. There are a couple of
issues that may prevent its inclusion, but if you're interested feel free to
grab it from the site's sources and use it yourself.
