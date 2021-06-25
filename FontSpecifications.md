AMP Font Specifications
=======================

There are basically two broad classes of fonts---Regular fonts and Specialty
fonts.

Specialty fonts serve a specific purpose and the specifications presented here
may not always apply to them.


AMP Prefix
----------

All fonts designed for this project will use "AMP" followed by a space as a sort
of namespace to indicate the font is AnyMouse Prophet foundry. Fonts provided by
other foundries will not have their name changed, this is just for fonts that
are created or modified by AMP.


Font Family Names
-----------------

When the font contains primarily novel outline math but is based upon the shapes
of another font, a novel font name will be used that is somewhat related to the
name of the font it is based upon yet is a distinctively different name.

When the font contains outline math take from the font it is based upon, the
name of the font it is based upon will be preserved as well as the copyright and
related informational metadata in the font. The "AMP" prefix will still be used.


Font License
------------

All fonts designed by AMP will be released under the
[SIL OFL](https://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=OFL)
license.

Existing fonts modified by AMP will obviously retain the license that they were
originally released under.


Glyph Outlines
--------------

All glyphs will be drawn as Type 1 outlines, using cubic Bézier curves (rather
than the quadratic used for TrueType outlines) and will be packaged as `.otf`
OpenType fonts.


Font Variants
-------------

With the exception of specialty fonts where it is not practical, AMP font
families at a minimum will have both 400 and 700 weights and both upright and
slanted (either Italic or Oblique) variants at both those weights.

When additional weights exist (such as 800 for Arial Black) both an upright and
slanted will exist for the additional font weights.

This is to avoid problems with fake embolding and fake italics.


Font Design Phases
------------------

Fonts will generally be designed in a seven-phase process. It is fine to create
glyphs that are part of a future phase at any time before that phase.

### Phase 1: Code Page 1252 (also known as Windows-1252)

CP-1252 is a superset of glyphs within ISO-8859-15 (and ISO-8859-1). For
variable-width fonts, the OpenType feature of allowing numerals to be either
variable-width or monospace should be implemented.

For variable-width fonts, the `f-f`, `f-l`, `f-i`, `f-f-i`, and `f-f-l`
ligatures will be implemented.

The ellipsis codepoints `U+2026` and `U+22EF` will be implemented. For
variable-width fonts, an alternate `U+2026` consisting of three asterisks will
be implemented (sometimes used in legal documents to make an omission visually
obvious). Honestly I do not know if web browsers can access an alternate
ellipsis but these fonts can be used in other applications.

All codepoints in U+201x

* U+229E (Often used to simulate Windows key)
* U+2325 (Option key symbol)
* U+2318 (Place of Interest Sign - used for Apple Flower key)
* U+F8FF (Used for Apple logo but will use below pear instead)
* U+1F350 (Pear Emoji)
* U+1F441 (Used for 1984 Eye, easter egg alternate glyph for U+F8FF)


### Phase 2: First Major Step towards WGL-4

* All missing codepoints in Latin Extended A
* All missing codepoints in Latin Extended B
* WGL-4 Latin Extended Additional
* WGL-4 Spacing Modifiers
* All missing General Punctuation codepoints
* Superscripts and Subscripts codeblock (U+207x, U+208x, U+209x)
* All vulgar fractions (U+2150--U+215F, U+2189)

That includes many glyphs that are not part of WGL-4 but makes sense to add at
the same time as glyphs from those ranges that are part of WGL-4.

Note that WGL-4 compliance is nowhere near yet achieved.

### Phase 3: Greek and Cyrillic and TeX T1.

* Greek Codepoints (U+0384--U+03CE)
* Cyrillic Codepoints (U+0400--U+0491)
* WGL-4 Arrows
* All Mathematical Operators (U+2200--U+22FF)
* Any codepoints still needed for the LaTeX
[Cork Encoding](https://en.wikipedia.org/wiki/Cork_encoding) (also called T1)

At this point the fonts *should* be fully usable in LaTeX with a T1 encoding
both using the modern LaTeX compilers that can use OpenType fonts and by
exporting the OpenType font to an 8-bit Type 1 font.

The fonts should be tested in LaTeX to help reveal potential issues.

### Phase 4: Vietnamese, Thai, Number Forms, and more WGL-4 Codepoints

* Any codepoints still missing from
[CP-1258](https://en.wikipedia.org/wiki/Windows-1258)
* Thai ISO-8859-11 codepoints
* Full Roman Numeral Support (Misc. Number Forms)
* U+2184, U+218A, U+218B (remaining Misc. Number Forms)
* WGL-4 Letterlike Symbols
* WGL-4 Miscellaneous Technical
* Some non-WGL-4 Miscellaneous Technical (to be determined)
* WGL-4 Miscellaneous Symbols
* Some non-WGL-4 Miscellaneous Symbols (to be determined)

This will bring the font *almost* to full WGL-4 compliance.

I have not yet determined which "Miscellaneous Technical" and "Miscellaneous
Symbol" glyphs that are not part of WGL-4 I want to require for AMP "Regular"
fonts.

### Phase 5: Full WGL-4 Compliance

* Box-drawing characters
* Block elements
* Geometric Shapes
* Any remaining ligatures that make typographical sense for the font

At this point the font will have full WGL-4 compliance and should have extensive
testing both in the context of WGL-4 and additional codepoints (such as Thai).

### Phase 6: Additional Desirable OpenType Features

* Small-caps
* Other desirable OpenType features often found in a "Pro" font

### Phase 7: Professional Cleanup

Crowd-source the funds necessary to have a professional fontographer clean-up
the font so it has a professional polish.

### Beyond Phase 7

With most fonts I will consider them "finished" when Phase 7 has been completed.

Some fonts, like the planned "AMP Desert Sans", will need codepoints added that
go well-beyond WGL-4 and the additional codepoints already being specified (this
is because Arial Unicode has huge codepoint coverage).

For other fonts that I consider finished after Phase 7, as need dictates they
may have updates to address those needs.






