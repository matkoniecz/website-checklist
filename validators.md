Useful HTML validators

What counts here: how many useful errors are reported, how many false positives are reported, how much time is needed to use this tools.

# Mobile-Friendly Test by Google

[Test made by Google](https://search.google.com/test/mobile-friendly). Especially important as hopefully what is reported here is similar to factors considered by Google for [ranking mobile-friendly websites higher](https://webmasters.googleblog.com/2016/03/continuing-to-make-web-more-mobile.html).

Following suggestions (like using viewport) from it may save time on what would be otherwise wasted on unneded debugging.

# Grammarly

Checker of grammar and language. Not very smart and has plenty of false positives but sometimes catches real problems. I consider it worth using to avoid wasting time and attention of a human proofreader on obvious things. Accepts markdown and raw html as input. Requires registration to work properly, strongly pushes a paid version.

Not a HTML-focused tool (it checks any text), with plenty of problems and still turned out to be the more useful than most automatic validators.

I use [simple script](https://github.com/matkoniecz/mapsaregreat.com/blob/master/code%20and%20content%20not%20served%20directly/html_to_text.py) to check all text at once.

# PageSpeed Insights

[Next useful Google tool](https://developers.google.com/speed/pagespeed/insights/).


# manually check version of dependencies

For example remember to update your leaflet .js and .css files. (is there a way to automate that?)

# html-proofer

[html-proofer by gjtorikian](https://github.com/gjtorikian/html-proofer)

`htmlproofer folder_to_validate --check-html --check-favicon` is the only automatic validator that I found so far that reminds about favicons.


# webpagetest.org

[Page speed test](http://www.webpagetest.org).

# html5validator by svenkreiss

[Scriptability-friendly validator](https://github.com/svenkreiss/html5validator). So far it reported no user-visible problems, but installation (`pip install html5validator`) and running (`html5validator --show-warnings --root folder_to_validate`) is easy so it may be worth using.

# Nu Html Checker
https://github.com/validator/validator via java .jar file - relatively easy to install (`npm install --save vnu-jar`, move .jar file to known location) and use, reported some minor but user-visible problems (pages with text and without any &lt;h1&gt; tags) that helped to improve the site.

I use it as follows (command executed in main folder of .html and .css files):

find . -name "*.html" -exec java -jar /path_to_vnu_jar/vnu.jar --also-check-css --also-check-svg --verbose {} \;
find . -name "*.css" -exec java -jar /path_to_vnu_jar/vnu.jar --also-check-css --also-check-svg --verbose {} \;

# HTMLProofer

https://github.com/gjtorikian/html-proofer

I use it like this `/usr/local/bin/htmlproofer . --check-html --check-favicon --log-level warn`, from root folder of a project.

# Rawler
https://github.com/oscardelben/rawler

Appears to be able to check only live websites.

`/usr/local/bin/rawler https://mapsaregreat.com | /bin/grep -v "]  INFO -- : 200 - "`

# Stylelint

https://github.com/stylelint/stylelint/blob/master/docs/user-guide/cli.md

Looks potentially useful, not worth configuring effort for me at this moment.

# W3C CSS Validation

https://github.com/w3c/css-validator + http://jigsaw.w3.org/css-validator/

Not investigated for now, but looks like something useful.