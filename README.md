# hugo 0.50 bug minimal reproduction repo

Attempt to build this site with the following flags using hugo 0.50:

```
hugo  --verbose --templateMetrics --templateMetricsHints --minify --theme=casper
```

Expect error output like the following:

```
$ hugo  --verbose --templateMetrics --templateMetricsHints --minify --theme=casper
WARN 2018/11/06 12:04:13 No translation bundle found for default language "en"
WARN 2018/11/06 12:04:13 Translation func for language en not found, use default.
WARN 2018/11/06 12:04:13 i18n not initialized, check that you have language file (in i18n) that matches the site language or the default language.
INFO 2018/11/06 12:04:13 Using config file: config.toml
Building sites … INFO 2018/11/06 12:04:13 syncing static files to public/
INFO 2018/11/06 12:04:13 found taxonomies: map[string]string{"tag":"tags", "category":"categories"}
INFO 2018/11/06 12:04:13 Alias "/post/page/1/index.html" translated to "post/page/1/index.html"
INFO 2018/11/06 12:04:13 Alias "/tags/page/1/index.html" translated to "tags/page/1/index.html"
INFO 2018/11/06 12:04:13 Alias "/categories/page/1/index.html" translated to "categories/page/1/index.html"
INFO 2018/11/06 12:04:13 Alias "/page/1/index.html" translated to "page/1/index.html"
ERROR 2018/11/06 12:04:13 parse error:7:17: unexpected comma character outside an array or object
    7:         "name": ,
                       ^
ERROR 2018/11/06 12:04:13 parse error:8:7: unexpected comma character outside an array or object
    8:              
             ^
ERROR 2018/11/06 12:04:13 parse error:7:17: unexpected comma character outside an array or object
    7:         "name": ,
                       ^
ERROR 2018/11/06 12:04:13 parse error:8:5: unexpected right brace character
    8:     },
           ^

Template Metrics:

      cache     cumulative       average       maximum         
  potential       duration      duration      duration  count  template
      -----     ----------      --------      --------  -----  --------
         67   26.642961ms    5.328592ms     8.52362ms      5  partials/header.html
          0   20.195278ms    6.731759ms    8.288447ms      3  _default/list.html
          0   12.056996ms   12.056996ms   12.056996ms      1  _default/single.html
         82     8.61653ms    1.723306ms      3.1538ms      5  partials/twitter_card.html
          0     3.63252ms     3.63252ms     3.63252ms      1  page/index.html
         84      1.7414ms      348.28µs     771.525µs      5  partials/semantic.html
        100    1.031992ms     206.398µs     432.909µs      5  partials/footer.html
        100     864.688µs     432.344µs     775.994µs      2  partials/li.html
        100     661.999µs     661.999µs     661.999µs      1  partials/home-content.html
         95     649.847µs     129.969µs     278.867µs      5  partials/navigation.html
        100     386.243µs     386.243µs     386.243µs      1  partials/social.html
         94     334.646µs       41.83µs     172.551µs      8  partials/pagination.html
        100     251.914µs     251.914µs     251.914µs      1  partials/author.html
        100     218.369µs     218.369µs     218.369µs      1  partials/share.html
        100     171.272µs     171.272µs     171.272µs      1  partials/disqus.html
        100     109.851µs     109.851µs     109.851µs      1  partials/suggestions.html

Total in 49 ms
Error: Error building site: failed to render pages: parse error:9:13: unexpected comma character outside an array or object
    9:              
                   ^
```

Also see https://discourse.gohugo.io/t/hugo-0-50-fails-when-minify-is-enabled-on-content-that-worked-fine-in-hugo-0-48
