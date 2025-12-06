# personal-site-template

A template to create simple personal sites with bio, projects and CV. It turns simple markdown files into web pages. No coding required for updates.

The site has four pages:
- About page (homepage)
- Projects page in your main language
- Projects page in an alternative language
- CV/Resume page

## Using This Template

If you want to use this template for your own site:

1. Click the green "Use this template" button at the top of this page
2. Choose "Create a new repository"
3. Name your repository anything you want (like `my-portfolio` or `personal-site`)
4. Make sure it's set to "Public"
5. Click "Create repository"

GitHub will copy all these files to your new repository. Then you can edit them with your own information.

**After copying, you'll need to enable GitHub Pages:**

1. Go to Settings in your new repository
2. Click "Pages" on the left side
3. Under "Source", select "GitHub Actions"
4. Your site will be live at `https://your-username.github.io/repository-name`

## How to Make Changes

Everything you need to edit is in the `content` folder. To update anything:

1. Navigate to the file (example: `content/about.md`)
2. Click the pencil icon in the top right corner
3. Edit the text
4. Scroll to the bottom and click "Commit changes"
5. Wait 2-3 minutes for the site to update

That's it. The website rebuilds itself automatically.

### To Edit the Footer

1. Navigate to `template.html`
2. Find the footer section and change the content:
```html
    <footer>
        <p>&copy; 2024 [Your Name]. All rights reserved.</p>
    </footer>
```

### To Change the Language Labels in Navigation

1. Navigate to `template.html`
2. Find the navigation section
3. Change "Projects" and "Proyectos" to your preferred language labels
4. Example: Change "Proyectos" to "Projets" for French, "Projekte" for German, etc.

## What's in Each Folder

**content/** - This is what you will edit regularly
- `about.md` - Info about you (this becomes the homepage)
- `projects-main.md` - Your projects in your primary language
- `projects-alt.md` - Your projects in an alternative language
- `cv.md` - Your resume/CV

**images/** - All pictures and screenshots
- `photo.jpg` - Your profile photo
- Any project screenshots you want to show

**Other files** - You rarely need to touch these
- `template.html` - The page layout (edit here to change language labels)
- `styles.css` - Colors and fonts
- `.github/workflows/deploy.yml` - Instructions for GitHub on how to build the site

## Adding a New Project

1. Open `content/projects-main.md`
2. Find an existing project section
3. Copy everything from one `---` line to the next `---` line
4. Paste it where you want the new project
5. Change the title, date, description, etc.
6. Save by clicking "Commit changes"

Do the same thing in `content/projects-alt.md` for the alternative language version.

## Adding Images

To add a screenshot or photo:

1. Click "Add file" at the top, then "Upload files"
2. Upload your image to the `images` folder
3. In your Markdown file, add this line where you want the image:
```markdown
   ![Description of image](./images/my-image.jpg)
```
4. Replace `my-image.jpg` with whatever you named the file

## Basic Markdown Formatting

Markdown is just text with some symbols for formatting. Here's what you can use:
```markdown
# Big heading
## Smaller heading
### Even smaller heading

**bold text**
*italic text*

- Bullet point
- Another bullet point

[Link text](https://website.com)

![Image description](./images/photo.jpg)
```

If you want to learn markdown better, I recommend you read: [Getting Started with Markdown](https://programminghistorian.org/en/lessons/getting-started-with-markdown) by Sarah Simpkin

## How It Actually Works

When you save changes to a Markdown file, GitHub runs a process in the background:

1. Takes the Markdown files
2. Converts them to HTML web pages using a tool called Pandoc
3. Wraps them in the template (adds the navigation menu, styling, etc.)
4. Publishes everything to the web

This all happens automatically. You never see it or interact with it. You just edit Markdown files and the website updates.

## Troubleshooting

**My changes aren't showing up**
- Wait 3-5 minutes after saving. The site needs time to rebuild.
- Check the "Actions" tab at the top. If there's a red X, something went wrong. Click it to see what.

**My image isn't appearing**
- Make sure the image is in the `images` folder
- Check that the filename matches exactly (including .jpg or .png)
- Image paths should look like: `./images/filename.jpg`

**I broke something**
- Don't worry! GitHub keeps history of all changes
- Click on the file, then "History" at the top right
- Find the last working version and click the three dots to revert

## Want to Change the Design?

If you want different colors or fonts, you can edit `styles.css`. The main colors in the file are:
- `#3498db` - The blue accent color
- `#2c3e50` - The dark blue/gray navigation bar

To change these and other colors:
1. Visit [color-hex.com/color-palettes](https://www.color-hex.com/color-palettes/) to browse color palette ideas
2. Pick colors you like and copy their hex codes
3. Open `styles.css` in your repository
4. Search for `#3498db` and replace it with your new primary color
5. Search for `#2c3e50` and replace it with your new dark color
6. Commit the changes

Your site will update automatically in 2-3 minutes!

## Want to Add More Project Pages?

If you need a third (or fourth) project page in another language, here's how:

### Step 1: Create the New Markdown File
1. Go to the `content/` folder
2. Click "Add file" → "Create new file"
3. Name it `projects-lang3.md` (or any name you want)
4. Copy content from `projects-main.md` and translate it
5. Commit the file

### Step 2: Update the Workflow
1. Open `.github/workflows/deploy.yml`
2. Find the "Convert Markdown to HTML" section
3. Add these lines before the "Convert CV" part:
```yaml
          # Convert projects (third language)
          pandoc content/projects-lang3.md -o _site/projects-lang3.html \
            --template=./template.html \
            --metadata title="Projects" \
            --metadata page="projects-lang3"
```
4. Commit changes

### Step 3: Update the Navigation Menu
1. Open `template.html`
2. Find the `<nav>` section
3. Add a new line in the menu:
```html
            <li><a href="./projects-lang3.html">项目</a></li>
```
   (Replace "项目" with your language label)

4. Commit changes

Your new project page will appear in the navigation menu and be accessible on your site!
