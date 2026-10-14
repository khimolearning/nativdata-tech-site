# Putting the NativData Tech site online

Menu names on GitHub and Netlify change now and then. If a button is not exactly where I say, look for the closest match.

## Part 1: Set up the folder

1. Create a folder on your computer called `nativdata-site`.
2. Put all of these inside it, in the same folder (no sub-folders):

| File | What it is |
|---|---|
| `index.html` | The page |
| `styles.css` | Colours, font, glow effects |
| `script.js` | Mobile menu |
| `profile.png` | Your headshot |
| `logo.png` | Logo icon only, shown in the header |
| `favicon-32.png` | Tiny icon in the browser tab |
| `apple-touch-icon.png` | Icon when someone saves the site to a phone home screen |

The three icon files that come in the zip are temporary placeholders so the site works today.

## Swapping in the real logo later

When the final logo is ready, replace the three icon files with new ones that have **exactly the same names**:

- `logo.png`: icon only (no text), transparent background, square, 512 x 512 px
- `favicon-32.png`: the icon, 32 x 32 px
- `apple-touch-icon.png`: the icon on a solid dark background (#0a0a0a), 180 x 180 px

Do not rename them and do not change any code. Then run `git add .`, `git commit -m "New logo"`, `git push`. Browsers keep old tab icons for a while, so press Ctrl + F5 (or clear the cache) to see the new one.

The header shows the name "NativData Tech" as live text next to `logo.png`, so you do not need a logo with text in it on the site. Keep the full horizontal logo for your CV, LinkedIn banner and documents.

## Part 2: Preview it on your laptop

1. Open the folder in VS Code (File > Open Folder).
2. Install the **Live Server** extension (Extensions icon on the left, search "Live Server", Install).
3. Right-click `index.html` and choose **Open with Live Server**. The site opens in your browser and refreshes whenever you save.
4. Check it on your phone too. Shrink the browser window to see the mobile layout.

No Live Server? Double-click `index.html` and it opens in your browser. Fonts need internet to load.

## Part 3: Put it on GitHub

1. Go to github.com and sign in as khimolearning.
2. Click **New repository**.
3. Name it `nativdata-tech-site`. Set it to **Public**. Do not tick "Add a README". Click **Create repository**.
4. In VS Code, open the terminal (Terminal > New Terminal). Make sure it is inside the `nativdata-site` folder, then run these one at a time:

```
git init
git add .
git commit -m "First version of NativData Tech site"
git branch -M main
git remote add origin https://github.com/khimolearning/nativdata-tech-site.git
git push -u origin main
```

5. Refresh the GitHub page. You should see your files.

## Part 4: Connect Netlify so it updates by itself

1. Go to netlify.com and sign up with **Continue with GitHub**.
2. Click **Add new site**, then **Import an existing project**.
3. Choose **GitHub**, allow access, and pick `nativdata-tech-site`.
4. Leave **Build command** empty. For **Publish directory**, leave it empty or type `.`
5. Click **Deploy**. After about a minute you get a live link ending in `.netlify.app`.

## Part 5: Change the web address

1. In your site on Netlify, open **Site configuration** (or **Site settings**).
2. Find **Change site name** (sometimes under Domain management).
3. Type something like `nativdatatech`. Your address becomes `nativdatatech.netlify.app` if it is free.

## Part 6: Making changes later

Every time you edit a file:

1. Save the file in VS Code.
2. In the terminal, run:

```
git add .
git commit -m "Describe what you changed"
git push
```

3. Netlify sees the push and updates the live site in about a minute.

## Changing a DOI or link later

1. Open `index.html` and search for the DOI number, for example `23335775`.
2. Replace it with the new number. Each project link looks like `https://doi.org/10.5281/zenodo.NUMBER`.
3. Save, then run `git add .`, `git commit -m "Update DOI"`, `git push`.

## Things to check before you share the link

- Project 4 GitHub link: confirm the repo name matches `NativData-Project4-Blood-Sugar-Measurement`.
- Open every link once to make sure none leads to a 404.
- Check the chart numbers in the hero against your Project 3 women's table.
