# Baby's World

A virtual version of her real doll. Dress her, feed her, play with her, give her a bath, and rock her to sleep.

## What's in this folder

| Path | What it is |
|---|---|
| `index.html` | **The whole game.** Every picture is built into this one file, so this is the only file the game needs to run. |
| `images/built-in/` | Copies of every picture inside the game, for reference or editing. The game doesn't read these files. |
| `images/built-in/outfits/` | The photos of her doll in each outfit (`look_*.webp`). |
| `images/built-in/arms/` | Her cut-out forearms, used when she hugs the lovey (`arm_*.webp`). |
| `images/built-in/things/` | Bottles, food, pacifiers, teethers, rattles and toys (`acc_*.webp`). |
| `images/built-in/other/` | Her original photo, the flat-lay clothes and the first food set. |
| `sounds/` | A `.wav` copy of every built-in sound. The game makes these sounds itself, so the files are only needed if you want to swap one out (see below). |

## Put it on GitHub Pages

1. Create a **public** repository, for example `babys-world`.
2. Upload **everything in this folder**, keeping the folders (**Add file → Upload files**, drag the files and folders in, then **Commit changes**).
3. Go to **Settings → Pages**, choose **Deploy from a branch**, then **main** and **/ (root)**, and click **Save**.
4. After a minute or two, open `https://YOUR-USERNAME.github.io/babys-world/`.
5. On her phone, open the link and choose **Add to Home screen**.

Her progress (stars, clothes, what she likes to eat) is saved in that phone's browser.

## Add new things

1. Save a picture with a see-through background (PNG or WEBP) in `images/`, for example `images/teddy-teether.png`.
2. Edit `index.html` and find `const MY_THINGS = [` near the top of the script.
3. Add one line:

   ```js
   {name:"Teddy Teether", img:"images/teddy-teether.png", kind:"teether"},
   ```

`kind` decides how she uses it:

| kind | what happens |
|---|---|
| `drink` | bottle or sippy cup: hold it to her lips and she drinks |
| `pouch` | food pouch: she sucks and squeezes |
| `spoonfeed` | jar, bowl or plate: you bring her bites on a spoon |
| `spoon` | a spoon: feeds her from the last jar she had |
| `puffs` | snack canister: puffs go into her mouth one at a time |
| `bite` | food she bites (a cracker, a banana…) |
| `paci` | pacifier: let go at her mouth and it stays in |
| `teether` | she chews on it |
| `rattle` / `hold` | toys you shake or show her |
| `stack` | stacking toy |
| `cuddle` | lovey or plush: she hugs it |

The comment above `MY_THINGS` explains the optional extras: `size`, `mouth`, `grip`, `turn`, `tuck` (for side-view pacifiers), `food` (food color) and `about`.

You can also use any built-in picture by name, for example `img:"acc_bottle"`.

## Use your own sounds

1. Put the sound file in `sounds/`, for example a recording of you saying "Mama! Mama!" in a little voice, saved as `sounds/mama.mp3`.
2. In `index.html`, find `const MY_SOUNDS = {` and add a line:

   ```js
   const MY_SOUNDS = {
     mama:"sounds/mama.mp3",
   };
   ```

The sound names are chime, munch, slurp, giggle, coo, swish, mama, rattle, lullaby, splash, pop, tada, coin and nope. `mama` replaces the phone's voice when she calls for you.

## Grown-up area

Press and hold the lock button at the top. There you can rename her, delete things, give stars, change the PIN, reset the game and run the self-check.
