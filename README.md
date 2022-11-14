# Font Organiser

A Python script to rename TrueType and OpenType font files, and file them by creator.

## How To Use It

Be aware that this is a work-in-progress, tailored to my own requirements, written with zero concern for user-friendliness, and liberally sprinkled with `# TODO:` comments.

Edit the script `fontorg.py`, and change these lines to point to the directories of your choice:

```
source      = r'D:/Fonts/To Sort/'
destination = r'D:/Fonts/Sorted/'
```

When run, the script will process all `.ttf` and `.otf` files in the source directory, and copy them to the destination directory with more helpful filenames. Filenames will consist of the font name and style, followed by a bracketed version number or date. Where possible, fonts are placed in subdirectories named after their author or manufacturer. Failing that, known font creators will be identified by their copyright or trademark messages; these are defined in the list `creators`, which currently takes up half the script.

Everything else will be filed under `(unknown)`. For these fonts, the copyright and trademark messages are written to the file `unknowns.txt`, which one can trawl for repeat offenders to add to the creators list.

Duplicate files are detected by size and content hash, and will not be re-copied.

If you want the fonts deleted from the source directory, uncomment this line:
```
#   os.remove(file)
```

Oh, and be prepared to learn that many of the `1001 FREE FONTS!!!!11.zip` that you downloaded weren't actually meant to be free 🙄 .

## License

Code is copyright by Tyrone C. and made available under the MIT license, the text of which can be found in the LICENSE.md file in this repository.
