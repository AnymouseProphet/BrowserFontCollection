AMP Standard Symbols L
======================

The "Symbol" font primarily contains Greek letters and mathematical symbols. It
was primarily intended to allow the typesetting of basic mathematics.

The "AMP Symbol" font exists for legacy rendering of documents that were typeset
using the Symbol font for mathematics, especially on the web. New documents
should use MathML with the STIX fonts.

Symbol is an 8-byte font that uses a custom encoding. Some browsers will
implement that encoding when the Symbol font is specified but not all of them do
nor does the HTML5 specification require them to, and I suspect none of them
will implement that encoding for "AMP Symbol".

To that end, in addition to the Unicode codepoints, every glyph except for the
`x80--x8F` range that are neither mathematical nor part of the *original* font
have also been assigned a Unicode codepoint that corresponds with the 8-bit slot
in the font the glyph uses.

If you have a historical document that uses Symbol mathematics the preferred
course of action:

1. Port the document to use MathML with the STIX Fonts. When that can not be
done:
2. Port the uses of Symbol in the document to reference the proper Unicode
codepoints. When that can not be done:
3. Make sure the document uses ISO-8859-1 or UTF-8 as the character encoding so
that "AMP Symbol" has the best chance of working. When that can not be done:
4. Require the actual "Symbol" font be available when rendering the font and
understand that some clients still may render gibberish.

With *Option 1* this font will not be needed. With *Option 2* this font can be
use used to provide the needed glyphs. With *Option 3* this font can be used to
provide the needed glyphs and I *suspect* it will work even in browsers that do
not implement the special Symbol font encoding. With *Option 4* this font will
*probably* not work, you probably have to have the genuine Symbol font available
when rendering the document and even then it will not work in some browsers.

For a large number of documents I recommend trying *Option 3* initially as a
temporary patch until you can take the time or pay someone to implement *Option
1* which is the technically proper fix for mathematics on the web.


Font Slots `x80--x9F`
---------------------

These font slots are traditionally not used in the Symbol font. I have put some
glyphs related to operating system technical support within that range, and may
add additional glyphs as needed.

These glyphs are only available by their Unicode codepoint. HTML/XML entities
are shown below.

* `&#xF810;` --- Flying flag icon intended to be reminiscent of the Windows Key.
See https://www.kreativekorp.com/charset/pua/Linux/char/F810/
* `&#xF811` --- Hamburger icon intended to represent a pull-down menu. See
https://www.kreativekorp.com/charset/pua/Linux/char/F811/
* `&#xF812;` --- Pear intended to be reminiscent of the Apple key, but not that
for trademark reasons, AMP Symbol uses a pear and not an Apple and also note
that the AMP Symbol font does not have a bite taken out. Also available through
the entity `&#xF8FF` in slot `xFA` as Mac versions of the Symbol font often had
that glyph in that slot and referencing `U+F8FF`. See
https://www.kreativekorp.com/charset/pua/Linux/char/F812/
* `&#xF813;` --- Open Pear version of above. See
https://www.kreativekorp.com/charset/pua/Linux/char/F813/
* `&#xF3200;` --- The BSD Daemon.
* `&#xF3201;` --- The GNU Head.
* `&#xE000;` --- Tux the Linux Penguin.

Planned but may be some time before implements: A glyph that combines Tux the
Linux Penguin with the GNU Head into a ligature to represent GNU/Linux.

Distribution specific glyphs will not be added. Some distributions already do
that in other fonts.


Font Origin
-----------

This OpenType font is based upon the Postscript font `usyr.pfb` as shipped by
TeXLive in TeXLive 2021.

    Original Font Name : Standard Symbols L
    Original Style     : Regular
    Original Type      : Postscript type-1 font
    Original Version   : 001.005
    Original Copyright : URW Software, Copyright 1997 by URW. See the file
                         COPYING (GNU General Public License) for license
                         conditions. As a special exception, permission is
                         granted to include this font program in a Postscript
                         or PDF file that consists of a document that contains
                         text to be displayed or printed using this font,
                         regardless of the conditions or license applying to the
                         document itself.
    Original Glyph Cnt : 190
    Ognl Color Glyhs   : no

Most of the vector math in the font from URW was re-used in this OpenType
version. A few changes were made.


Font Encoding Slot `x60`
------------------------

Adobe versions of this font often have a a glyph Adobe calls a "Radical
Extender". That glyph is not assigned a Unicode codepoint, is not in all
versions of the Adobe font, and is not in the URW clone that I used to make this
OpenType font.

I added that glyph to this font.


Font Encoding Slots `x80--x8F`
-----------------------------

The `x80--x8F` slots are traditionally not used by the Symbol font.

I am using four of them for the `U+F810--U+F813` range described at:

    https://www.kreativekorp.com/charset/pua/Linux/block/F810/

* `U+F810` in slot `x80` has a flying flag icon. It can be used in place of the Windows Key.
* `U+F811` in slot `x81` has a hamburger menu icon. It can be used to indicate a menu.
* `U+F812` in slot `x82` has the same Pear icon I am using in slot `F0`. It can be used to indicate the Apple key.
* `U+F813` in slot `x83` has an open version of that icon.

Additionally I am adding these four which have standard Unicode codepoints:

* `U+229E` in slot `x84` which is often used to simulate the Windows Key.
* `U+2325` in slot `x85` which corresponds with the Options Key symbol.
* `U+2318` in slot `x86` which corresponds with the Apple Flower key.
* `U+1F441` in slot `x87` which I use for a 1984 eye.

Tux the Linux Penguin is sometimes put at codepoint `U+E000` by some fonts.

This font has that in slot `x8E`.

Finally, because the Symbol font I started with is licensed under the GPL, I am
adding the GNU Head in slot `x8F`. Unicode codepoint `U+F3201`.


Font Encoding Slots `x90--x92`
------------------------------

The `x90--x9F` slots are traditionally not used by the Symbol font. This font
also does not use them for anything.


Font Encoding Slot `xF0`
------------------------

At least some if not all Adobe versions of this font for the Apple Macintosh
platform have the Apple logo at the font encoding slot `xF0`.

The Adobe version of this font for other systems and the URW clone that I used
to make this OpenType font do not have that glyph.

I could not add an Apple glyph but I did add a glyph of a pear in that encoding
slot. Unicode codepoint `U+F8FF` was used for this, which is the codepoint that
is used by Apple for this glyph.

The glyph is identical to what is in slot `x82` (`U+F812`).


Copyright and Trademark Symbols
-------------------------------

The Symbol font has two versions of the Registered Trademark symbol and two
version of the Copyright symbol. One version of each uses a sans-serif version
of the letter inside the circle and the other version uses a serif-version.


Test Pages
----------

These have not yet been created.
