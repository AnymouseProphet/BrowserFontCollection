Browser Font Collection
=======================

I'm Autistic and ADHD which means sometimes things gnaw in my head until I start
them and I have to do something even if it never actually comes to fruition or I
literally can not concentrate on anything else.

This may be one of those cases where nothing gets completed but hopefully it
will result in something, even if not the end result I currently an visualizing.

Browser Fingerprinting is a method trackers use to track the user covertly. What
they do is use JavaScript to detect things about your system and from that they
can make a fingerprint of your system and track you without using tracking
cookies.

One of the methods they use is detection of what system fonts are available to
your web browser.

One way to combat that is if a browser vendor had a set of fonts that could be
used as local fonts for the web browser and *only* that set of fonts could be
used as local fonts for the wen browser.

So if, say, Lucida Grande is installed on your system and they try to detect it
by using JavaScript to specify Lucida Grande and see if the size of the
string matches up for what it should be with the actual font---then even though
you do have Lucida Grande installed, the test will fail to detect it because it
isn't actually available to the web browser. Only the specified set of fonts,
the same fonts that are available to everyone using that web browser, can be
detected and the information is not unique enough to aid in browser
fingerprinting.

Web designers can still use whatever fonts they want to use---they just have to
serve it as a web font if they want it guaranteed that the browser will use it.
When the specified font is critical that really is what they should be doing
anyway.


Free Libre Open Source Software
-------------------------------

Such a collection of standardized fonts *must* be under a suitable FLOSS license
for fonts, such as
[SIL OFL](https://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=OFL) or
similar licenses.

The obvious reason for this is so that the font licenses do not interfere with
web browsers and operating systems that are distributed using a FLOSS license.

A less obvious reason is that many fonts now have funky licenses that allow them
to be used on a PC but do not allow them to be embedded without paying more
money. So if you print a web page to PDF for distribution within your office,
you may actually be violating the font license. The collection of fonts that are
standard to the browser should not ever be the cause of that accidental license
violation.

A violation can still occur in the case of web fonts, but browser vendors can
compensate for that by allowing the user to specify only the bundled local fonts
be used when printing a web page to PDF. Well, the bundled local fonts and the
Ghostscript fonts would probably be okay as the Ghostscript fonts are also under
a libre license that allows embedding.


Stylistic Coverage
------------------

The font collection should contain suitable metric similar and glyph similar
fonts for the fonts many existing web pages currently specify but do not serve
from a font server.

The term "Web Safe Fonts" is often used by web designers to describe fonts that
are safe to specify without using a web font served from a web server. However
no such specification of what exactly is a "Web Safe Font" actually exists.

It is my opinion that some fonts *beyond* just what is currently considered to
be "Web Safe Fonts" should exist. As these fonts will have a libre license, web
designers can specify the fonts in the collection such that the local font is
used for web browsers that have them available and if not, it is served from as
a web font. This means less bandwidth and faster page loads for users with the
fonts available but the page will still render as intended if the user does not
have the font available.


OpenType Features
-----------------

When appropriate the fonts should make use of OpenType features. Things like
small-caps, spacing of digits, etc. should be available for CSS control. And
things like automatic ligatures, etc.

Just an example---some fonts like Arial that were often used for headlines had
variable-width spacing for the numerical digits as they should when used in a
headline. But that then causes digits not to line up when used in a column.
With OpenType fonts, you can have both variable width and fixed width digits in
the same font and use CSS to specify which is used when.

It is possible that current versions of Arial allow this, but historically they
were not OpenType fonts so variable width digits was the way things were.


Font Names
----------

In most cases when creating a font as a replacement for another font, the name
of the font should be a novel font name. This gives freedom to use different
font metrics and even different glyph shapes as needed. One really should not
alter the metrics or the glyphs when using a variant of the existing name.


Web-Safe Fonts
--------------

This listing is based largely upon the "Core Fonts for the Web" project that
Microsoft started in 1996 and ended in 2002 but are still quite heavily
specified on web pages, both archaic and modern. Some font substitutions are
added because they appear to be common despite not being part of the "Core Fonts
for the Web" (such as a substitute for Tahoma).

Note that metric compatibility was NOT a goal but metric *similarity* at least
for the codepoints covered by the the Fonts being substituted was a goal.

The current list:

* AMP Desert Sans (substitute for Arial)
* AMP Desert Sans Black (substitute for Arial Black)
* AMP Mortal Emulation (substitute for Andalé Mono)
* AMP New Deliverance (substitute for Courier New)
* AMP Scrapyard Sans (substitute for Comic Sans MS)
* AMP Blue Ridge (substitute for Georgia)
* AMP Air Horn (substitute for Impact)
* Linux Libertine (substitute for Times New Roman)
* AMP Mangonel (substitute for Trebuchet MS)
* AMP Green Envy (substitute for Verdana)
* AMP Tahoe (substitute for Tahoma)
* AMP American Hipster (substitute for American Typewriter)
* AMP Redmond Petroglyph (substitute for Webdings, Wingdings, Wingdings 2,
Wingdings 3)
* AMP Harlett (substitute for Marlett, a Windows UI interface font)

The above fonts (except for "AMP Tahoe" and "AMP American Hipster" and "AMP
Harlett") are intended as substitutes for the Microsoft "Core Web Fonts" when a
web pages specifies fonts in the Microsoft "Core Web Fonts".

I decided not to use an existing Helvetica clone as an Arial substitute even
though they are plentiful because even though it has metric compatibility with
Helvetica, Arial is a significantly different design. Also, given how common
"Arial Unicode MS" is installed on both Windows and macOS systems---a long term
goal of the substitute should be font with the same kind of extensive Unicode
coverage as "Arial Unicode MS".

I am not making a narrow version of the "AMP Desert Sans" at this time. Websites
that specify a narrow version of Arial but do not serve it from a font server
will end up with the narrow "TeX Gyre Heros" substituted instead. That is not
ideal.

I decided not to use an existing Courier clone as a "Courier New" substitute
because there are many serif differences between Courier and Courier New.

A lot of people like to hate "Comic Sans MS" however that font is very helpful
to many dyslexic users. The name "Scrapyard Sans" was chosen because Scrapyards
often have handwritten signs that can resemble comic strip lettering *and*
because I think that name would tickle those who love to hate "Comic Sans MS".

Linux Libertine was chosen as a substitute for Times New Roman because it is an
existing high quality OpenType font with many modern OpenType features already
present. I did not feel a need to try to recreate a "Times New Roman" clone.

Tahoma is not part of the "Core Fonts for the Web" but it is a very standard
font on Windows systems and is specified on a lot of web pages. "American
Typewriter" is also not part of the "Core Fonts for the Web" but it is used with
some high frequency---often as a web font, granted, but I still thought it was
worth having a substitute available.

The "AMP Redmond Petroglyph" font will have all the Unicode codepoints from both
Webdings and the three Wingdings versions but the 8-bit slots 2F--FF should
correspond with Webdings for compatibility with existing web pages that specify
Webdings. Wingdings comparable glyphs would only accessible through their
Unicode codepoints. Web browsers that implement this font collection could map
8-bit encoding requests from within the various Wingdings fonts to the proper
Unicode codepoint within the "AMP Redmond Petroglyph" substitute font.


'Base 35' Substitutes
---------------------

Many web pages specify fonts from the Adobe Postscript Level 2 "Base 35" fonts.
The TeX Gyre fonts, while not fully metric compatible, are the best clones of
these fonts that I have seen and they are available as OpenType fonts. The TeX
Gyre Fonts are forks of the URW versions of the "Base 35" fonts that ship with
Ghostscript.

* TeX Gyre Adventor (substitute for ITC Avant Garde Gothic)
* TeX Gyre Bonum (substitute for ITC Bookman)
* TeX Gyre Chorus (substitute for ITC Zapf Chancery)
* TeX Gyre Cursor (substitute for Courier)
* TeX Gyre Heros (substitute for Helvetica)
* TeX Gyre Pagella (substitute for Palatino)
* TeX Gyre Schola (substitute for New Century Schoolbook)
* TeX Gyre Termes (substitute for Times)
* AMP Standard Symbol L (substitute for Symbol)
* AMP Dingbats (substitute for Dingbats)

The "AMP Standard Symbols L" and "AMP Dingbats" will be based heavily on the URW
Type 1 "Base 35 Ghostscript" fonts and may use identical outlines but packaged
as OpenType fonts. These will carry a GPL license as the upstream URW fonts do.

There is a possibility that the "Linux Libertine" font already mentioned is a
better substitute for Times than "TeX Gyre Termes" is but honestly I do not have
a problem with including both and using the former when "Times New Roman" is
called for and the latter when "Times" is called for.


Fruity Nostalgia Fonts
----------------------

A lot of the currently specified fonts are substitutions for the fonts that were
shipped by Microsoft for the web.

There were twelve bitmap fonts that were readily available on Apple Macintosh
systems through System 6.0.8. I call them the "Classic Mac Fonts". Most of them
were designed by [Susan Kare](https://en.wikipedia.org/wiki/Susan_Kare).

Eleven of them I would like to reproduce as modern libre OpenType fonts that are
available as local fonts for browsers to use.

* AMP Spyridon (inspired by "Classic Mac" Athens)
* AMP Weegham Park (inspired by "Classic Mac" Chicago)
* AMP Cairoglyphs (inspired by "Classic Mac" Cairo)
* AMP Wankdorf (inspired by "Classic Mac" Geneva)
* AMP Ashburton Grove (inspired by "Classic Mac" London)
* AMP Gilmore Field (inspired by "Classic Mac" Los Angeles)
* AMP Stade Louis II (inspired by "Classic Mac" Monaco)
* AMP Polo Grounds (inspired by "Classic Mac" New York)
* AMP Candlestick Park (inspired by "Classic Mac" San Francisco)
* AMP Hanlan's Point (inspired by "Classic Mac" Toronto)
* AMP Ermelinda (inspired by "Classic Mac" Venice)

The metrics would not be exact and the glyph reproduction would not be exact and
the codepoints covered would be much more extensive.

"AMP Cairoglyphs" will use visually distinctive art so that it does not infringe
upon any of the glyphs that are trademarked, such as Claris the Dogcow.


Default CSS Generic Font Families
---------------------------------

There are many "Generic" font families that can be specified at the end of a CSS
`font-family` declaration so the web browser knows what font to use if none of
the specified fonts are available:

* `serif`  
&#160;&#160;&#160;&#160; The default serif family. I recommend "Linux Libertine"
for this purpose. The default serif family *should* be paired with the STIX math
fonts used for MathML.
* `sans-serif`  
&#160;&#160;&#160;&#160; The default sans-serif family. I recommend the font
[Intel Clear Sans](https://01.org/clear-SANS) for this purpose. That font is the
easiest on my eyes, giving me the longest period of time before reading
comprehension drops due to eye/brain fatigue.
* `monospace`  
&#160;&#160;&#160;&#160; I recommend
"[Space Mono](https://fonts.google.com/specimen/Space+Mono)" for this. It is a
really nice monospace font with a dotted zero.
* `cursive`  
&#160;&#160;&#160;&#160; A font used for cursive-like rendering of text. I kind
of like "[Rampage Monoline](https://creatypestudio.co/rampage/)" but that is not
a free libre font. I found it to be easy to read. "TeX Gyre Chorus" is also an
option that is already planned in the collection but I have always seen the Zapf
Chancery and clones as best for nostalgia excerpts rather than generic cursive
needs.
* `fantasy`  
&#160;&#160;&#160;&#160; A font used for fantasy style typesetting. For this I
I hope to develop a new font called "AMP Bloomin' Fairy" inspired by the fantasy
font [Luminary](https://www.myfonts.com/fonts/canadatype/luminari/). I have seen
that font specified more than once in CSS files and it is a rather legible
fantasy font.
* `emoji`  
&#160;&#160;&#160;&#160; Font used for Emoji glyphs. This is something many
browsers currently develop themselves and that is probably okay but "Noto Color
Emoji" is what I would suggest browsers choose rather than developing their own.
Let other Emoji fonts exist but let the Noto team develop the default---they do
a damn good job and it is libre.
* `math`  
&#160;&#160;&#160;&#160; The default font for MathML. STIX fonts are the the
defacto standard and should be.
* `fangsong`  
&#160;&#160;&#160;&#160; The default font for Fang Song typefaces in Chinese. It
has been described to be as an intermediary between Serif and Sans-serif. I am
not qualified to have a valued opinion on the font for this.

The following generic CSS font families I do not like:

* `system-ui`
* `ui-serif`
* `ui-sans-serif`
* `ui-monospace`
* `ui-rounded`

Personally I do not like those generic families and do not think they should
exist. See (https://www.w3.org/TR/css-fonts-4/#generic-font-families) for the
descriptions of what they are for, system UI fonts are often user configurable
so those CSS generic families help with browser finger-printing.

Personally I recommend `system-ui`, `ui-rounded`, and `ui-sans-serif` map to
`sans-serif`, `ui-serif` should map to `serif`, and `ui-monospace` should map to
`monospace`.

It was a mistake for W3C to add those generic families to the CSS specification
but W3C is largely controlled by corporate interests now and does not always do
the right thing.


Internationalization
--------------------

Many reading this README will see that I clearly am biased towards Latin script.
That is not an intentional bias, it is an ignorance bias.

In many cases, especially for the "AMP" fonts, additional linguistic support can
be added to some of the fonts if the project takes off. For example, the planned
"AMP Desert Sans" should probably have a goal of the same coverage that the font
"Arial Unicode MS" has.

In the case of the TeX Gyre fonts, coordination should be done with
[GUST](http://www.gust.org.pl/projects/e-foundry/tex-gyre/index_html) for any
additional codepoints.

The font "Intel Clear Sans" also should probably have the same Unicode coverage
that "Arial Unicode MS" has. I am *almost* inclined to find out if crowd-funding
could help inspire Monotype to fork it and make a libre "Clear Sans MT" based on
"Intel Clear Sans" that includes small-caps and additional Unicode coverage on
par with "Arial Unicode MS".

Adding codepoints to the fonts chosen with a Latin script bias does will not
completely solve the problem. In some cases fonts designed specifically for the
non-Latin script market are probably appropriate. The "generic" family defaults
may also need to be fluid, changing if the web server sends a language header
where a different default for a "generic" family is better.

For example, "Linux Libertine" quite likely is not the best default serif font
if `ko` (Korean) is specified as the language for the web page.


