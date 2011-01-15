This is a simple addon that tests some assumptions about [bug 616472], "Unify sizes of toolbarbutton images to make life easier for extensions".

The big-picture goal here is to make it much easier for Firefox add-on authors to create toolbar icons for multiple platforms. It's currently [rather painful][].

The platforms in question are OS X, Linux, and Windows. The toolbar can also be in one of two modes, small and large. Thus there are 6 mode/platform combinations.

## TODOs

1. Get the addon into a state where it actually tests what we're trying to do.

  * Generate a 16x16 image with a 1-pixel wide border at the edges.
  * Do the same for a 24x24 image.
  * Update the `chrome.manifest` and CSS files so that all six toolbar-mode/platform combinations will display correctly. That is, each combination should display one of the icons at its native resolution, with no cropping or distortion.
  * Upload the addon to [bug 616472][] for feedback.

2. Research automated testing requirements for this by looking at the [Firefox Review Requirements][] and talking to necessary people.

3. If we need to write automated tests, consider whether to write them now, or after we've written one or all of the fixes.

4. Hack Firefox to make the tests pass.

  * We're hoping that OS X already works. In [comment 7][] Jorge mentions that 16x16 icons are actually stretched to 20x20, but later comments in the bug suggest that this was fixed. Also, we think that large and small toolbar icons on OS X look the exact same, but we should test this.
  * The other platforms/modes to try, in order, are **Windows small** (16x16), **Linux small** (16x16), **Linux large** (24x24), **Windows large** (which depends on incoming changes to be made by  [Stephen Horlander][]).

5. Make screenshots and upload them to the bug.

6. Request UI review (likely from [Alexander Limi][] or [Alex Faaborg][]).

7. Request review (likely from [Dão Gottwald][]).

  [rather painful]: http://blog.mozilla.com/addons/2010/12/02/toolbar-buttons-in-firefox-4/
  [comment 7]: https://bugzilla.mozilla.org/show_bug.cgi?id=616472#c7
  [bug 616472]: https://bugzilla.mozilla.org/show_bug.cgi?id=616472
  [Stephen Horlander]: http://stephenhorlander.com/
  [Firefox Review Requirements]: http://www.mozilla.org/projects/firefox/review.html
  [Alexander Limi]: http://limi.net/
  [Alex Faaborg]: http://blog.mozilla.com/faaborg/
  [Dão Gottwald]: http://en.design-noir.de/
