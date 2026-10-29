# The Forgotten Tower 🏰

An interactive fiction game about exploring a mysterious tower, built with [Twine](https://twinery.org/) and the [SugarCube 2](https://www.motoslave.net/sugarcube/2/) story format.

## 📖 Story

You discover an ancient tower in a dark forest. What secrets does it hold? Explore multiple paths, discover hidden passages, and uncover the wizard's life work — a living map of the entire universe.

**Features:**
- Multiple branching paths and endings
- Hidden passage discoverable with a secret item
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

