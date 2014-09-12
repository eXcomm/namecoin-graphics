Namecoin Graphics
=================
This is the official repo for visual collateral (logos, badges, etc) for Namecoin.  Only material found in this repository should be used in official Namecoin software and websites.

| ![Basic](https://raw.githubusercontent.com/indolering/namecoin-graphics/master/png/200/200-namecoin-logo-basic.png) | ![Shaded](https://raw.githubusercontent.com/indolering/namecoin-graphics/master/png/200/200-namecoin-logo-shaded.png) |      ![3D](https://raw.githubusercontent.com/indolering/namecoin-graphics/master/png/200/200-namecoin-logo-3d.png) |
| :--------: | :----: | :------: |
| Basic Logo | Shaded | Fancy 3D |

| ![Banner](https://raw.githubusercontent.com/indolering/namecoin-graphics/master/png/500/500-namecoin-logo+wordmark.png) | 
| :--------: |
| Full Banner |

Usage
=====

NOTE: this section is incomplete, [see Firefox branding guidelines](https://www.mozilla.org/en-US/styleguide/identity/firefox/branding/).

We strongly encourage outsider art and wish to promote liberal expression of the Namecoin brand.  However, this should be restricted to artistic expressions which are part of a larger composition: one-off pieces for fundraisers, images accompanying articles about Namecoin, etc.

Competing logos being used as currency identifiers weaken the overall brand-recognition of Namecoin.

## Good

Examples

## Bad

Examples

## License
We have recently suffered from fraudulent software and misinformation spread by cranks and trolls. We intend to release the files under a permissive copy-left license after we have worked out the trademark and copyright issues with some lawyers.  This should not be a problem in the interim as the vast majority of use-cases are covered by fair-use.

Graphics Structure
==================

##ai
The "source" files created using Illustrator, linked copies are used whenever possible.

* `namecoin-logo-outlined.ai` is a single vector outline generated from `namecoin-logo.ai`.  The shape builder tool is used create pool the constituent shapes together.

* `namecoin-icon.ai` uses both placed shapes AND custom N's.  The N's for 16x16, 24x24, and 32x32 have cross-ties that are 1/4 thinner than normal.  This increases contrast/clarity of the shape at small sizes. 

* `namecoin-wordmark-outlined.ai` Static outlines, no font required. 

##SVG & PNG Conversion

`ai2SvgPng.js` is used to convert the graphics from `./ai` to SVG and PNG.  Any .ai files with the word "icon" or "circle" in their names are exempted. It does not attempt to perform additional compression, which should be handled at the server level.

`ai2SvgPng.js` requires illustrator and can be run by selecting:

	File -> Scripts -> Other Scripts -> ai2SvgPng.js

You will be prompted for the project directory, which is the root directory for the Git repo (`/namecoin-graphics/`). The script requires the following directories to be present:

	/ai/name.ai
	/svg/
	/png/1000/
	/png/500/
	/png/200/
	/png/100/

##icons
`namecoin.ico` and `namecoin.icns` are created manually using the images from namecoin.iconset.  Each OS has a different icon creation app.

###namecoin.iconset
Created by **exporting** `namecoin-icon.ai` with the "Use Artboards" option enabled. For some reason, one must rename some files to remove trailing `-`.

###favicons

Generated by uploading `1000-namecoin-coin-basic.png` to [RealFaviconGenerator.net](http://realfavicongenerator.net). 

`/icons/favicons/favicon.ico` is overwritten by copying and renaming `/icons/namecoin.ico`.

`favicon-16x16.png`,`favicon-24x24.png`, and `favicon-32x32.png` are overwritten with equivalent files from `/icons/namecoin.iconset/`.


Troubleshooting
===============
## Misc
* Try simplifying shapes by combining multiple shapes into a single shape. This may require maintaining editable source and simplified version used for linking.  The `*-outlined` logo is an example of this.

## Clipping Mask Errors
These frequently occur with SVG exports of images with complex shapes that have been placed/linked.

* Ensure that points and paths do no extend past the canvas.
* Copy and paste instead of placing (hack: not advised as changes to source file do not propagate).
* Avoid effects which require rasterization.

## Hairlines
* Averaging points converges lines.
* Extend shapes that touch each until they overlap slightly.
* Try layering additional solid shapes with either the same color a neutral color /behind/ edges.


