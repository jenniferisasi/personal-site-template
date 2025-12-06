# personal-site-template
A template to create simple personal sites with bio, projects and CV. It turns simple markdown files into web pages. No coding required for updates.

The site has four pages:
- About page (homepage)
- Projects page in one language
- Projects page in another language
- CV/Resume page

# Using This Template
If you want to use this template for your own site:

1. Click the green "Use this template" button at the top of this page
2. Choose "Create a new repository"
3. Name your repository anything you want (like my-portfolio or personal-site)
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


## What's in Each Folder

**content/** - This is what you will edit regularly
- `about.md` - Info about you (this becomes the homepage)
- `projects-en.md` - Your project in English
- `projects-es.md` - Your projects but in another language (Spanish as template)
- `cv.md` - Your resume/CV

**images/** - All pictures and screenshots
- `photo.jpg` - Your profile photo
- Any project screenshots you want to show

**Other files** - You rarely need to touch these
- `template.html` - The page layout
- `styles.css` - Colors and fonts
- `.github/workflows/deploy.yml` - Instructions for GitHub on how to build the site

## Adding a New Project

1. Open `content/projects-en.md`
2. Find an existing project section
3. Copy everything from one `---` line to the next `---` line
4. Paste it where I want the new project
5. Change the title, date, description, etc.
6. Save by clicking "Commit changes"

Do the same thing in `content/projects-es.md` for the Spanish version.


## Adding Images

To add a screenshot or photo:

1. Click "Add file" at the top, then "Upload files"
2. Upload my image to the `images` folder
3. In my Markdown file, add this line where I want the image:
   ```
   ![Description of image](./images/my-image.jpg)
   ```
4. Replace `my-image.jpg` with whatever I named the file

## Basic Markdown Formatting

Markdown is just text with some symbols for formatting. Here's what I can use:

```
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


### How It Actually Works

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

You can search for these and replace them with any other color codes you want.
