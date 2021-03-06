scratch
=======

It's a markdown scratchpad. Your local `pandoc` installation gets exported over
the web so you can do useful (or in my case, stupid) things with it.

__Warning.__
If you do run this software, you are exposing your `pandoc` installation to
whoever who can access your web server, making any local vulnerabilities remote!


API
---

Usage example:

```sh
curl --compressed https://scratch.b0ss.net/api.pl -H 'Content-Type: text/plain' --data-binary @file.md
```

`api.pl` accepts the following parameters via query string,

<dl>
<dt><code>numbersections</code></dt>
<dd>number sections if specified
</dd>
<dt><code>standalone</code></dt>
<dd>generates a standalone HTML if specified, snippet otherwise.
</dd>
<dt><code>webmath</code></dt>
<dd>either <code>mathjax</code>(default) or <code>webtex</code>.
</dd>
</dl>


Markdown Scratchpad
-------------------

Basic markdown editor that uses API to auto-update, [try it](https://scratch.b0ss.net).
There's also a less functional [no JS version](https://scratch.b0ss.net/nojs.pl) which defaults to `webtex`.


Setup
-----

* The `.pl` files require Apache 2 with `mod_perl` 2.0, I think no extra modules are needed.
* The rest are static files which you may serve any way you wish.
* The user that `httpd` runs as must have execute permissions on your `pandoc` binary.
