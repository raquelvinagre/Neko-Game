# The Forgotten Tower 🏰

An interactive fiction game built with [Twine](https://twinery.org/) (SugarCube 2 format), compiled with [Tweego](https://www.motoslave.net/tweego/), and automatically deployed to GitHub Pages via GitHub Actions.

## 🎮 Play

Once deployed, the game is available at:

```
https://<your-username>.github.io/<repo-name>/
```

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

## 🚀 Deployment

This project uses **GitHub Actions** to automatically build and deploy to **GitHub Pages** on every push to `main`.

### Setup

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Under **Source**, select **GitHub Actions**
4. Push a commit to `main` (or manually trigger the workflow from the Actions tab)

The workflow will:
1. Install Tweego and SugarCube 2
2. Compile `src/story.twee` → `dist/index.html`
3. Deploy `dist/` to GitHub Pages

## 📁 Project Structure

```
.
├── .github/
│   └── workflows/
│       └── deploy.yml      # GitHub Actions workflow
├── src/
│   └── story.twee          # Twine story source (Twee format)
├── package.json
└── README.md
```

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

