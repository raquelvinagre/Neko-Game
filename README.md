# Neko

An interactive fiction game about surviving as a stray cat, built with [Twine](https://twinery.org/) and the [SugarCube 2](https://www.motoslave.net/sugarcube/2/) story format.

## 📖 Story

Explore the streets, parks, suburbs, train station, restaurant, cat colony, and shelter while managing health, hunger, and trust.

**Features:**
- Multiple branching paths and endings
- Branching locations and survival outcomes
- Persistent state tracking across your journey
- Atmospheric CSS styling

## 🛠️ Local Development

### Prerequisites

1. Download [Tweego](https://github.com/tmedwards/tweego/releases) for your platform
2. Download [SugarCube 2](https://github.com/tmedwards/sugarcube-2/releases) story format for Tweego
3. Extract SugarCube into Tweego's `storyformats/` directory (or set `TWEEGO_PATH`)

### Build

```bash
# Set the path to your story formats
export TWEEGO_PATH="/path/to/tweego/storyformats"

# Compile the story
tweego -o dist/index.html src/story.twee

# Or use the watch mode for development
tweego -o dist/index.html -w src/
```

Then open `dist/index.html` in your browser.

### Media

The interface reserves a dark image area above every passage. The included
`assets/giphy.gif` is used as the animated scene, and the optional looping
soundtrack can be added as `assets/background-music.mp3`. Music is off by
default and can be enabled with the `MUSIC` button. The story supports both
the deployed `dist/index.html` layout and opening `build/Neko.html` directly
from the local filesystem.

Scene files can be GIF, WebP, or MP4. MP4 scenes play muted, looping, and
inline above the passage content.


## 📝 Writing Your Own Story

Edit `src/story.twee` using [Twee notation](https://github.com/iftechfoundation/twine-specs/blob/master/twee-3-specification.md):

```twee
:: Passage Name
This is the text of the passage.

* [[Link text|Target Passage]]

:: Target Passage
You arrived at the target passage!

<<if $someVariable>>
  Conditional text here.
<</if>>
```

Refer to the [SugarCube 2 documentation](https://www.motoslave.net/sugarcube/2/docs/) for macros, styling, and advanced features.

## License

MIT
