# Hugo starter project
A hugo starter project with the scripts in place for adoption on github pages. Also a helpful synopsis included here of the starter guide to serve as a reference and get up to speed with a glance.
Learn more at the site: https://gohugo.io/getting-started/external-learning-resources/
The hugo docs are really good and most of stuff here is just derived from there, I just wanted to add it in a single place so people can get up and running within an hour.

## Prereqs

- [install hugo](https://gohugo.io/getting-started/installing/)
- generate template: `hugo new site <name>`

## Directory structure

```
.
├── config.toml     # config can be json, toml, yaml. https://gohugo.io/getting-started/configuration/#all-variables-yaml
├── public          # the output of hugo, this is to be published by github pages.
├── content         # parent folder of content (example below)
├── archetypes      # templates to generate front matter based on the path used (example below)
├── assets          # things to process with hugo pipes such as Sass/Less, etc. https://gohugo.io/hugo-pipes/
├── data            # data to be processed into pages can be json, toml, yaml. https://gohugo.io/templates/data-templates/
├── layouts         # html templates. https://gohugo.io/templates/introduction/
├── static          # copied to the site as is.
└── themes          # published or created themes used by the site as a base.
*── resources       # folders created to serve as caches for operations such as Sass.

```

### Examples

- content: content divides the website into sections of content e.g. `content/posts`, `content/blog`, `content/about`, `content/tutorials`
- archetypes: `hugo new posts/newPost.md` will use the default front matter from `archetypes/posts.md`, `archetypes/default.md`, then theme related ones.

## Running Locally

- **Building**: `hugo`
- **Running Locally**: `hugo server`
- **Create new post**: `hugo new <name>.md`
- Defaut local address: [http://localhost:1313](http://localhost:1313/)

### Common Flags

- `-D` build with drafts
- `-F` build with future content
- `-v` to look at logging
- `-w` watch local changes to rebuild content

## Changing themes

1. download the theme, use the directory path: `themes/<theme name>`
2. if you are using git for version control and the theme is a gitmodule gitmodules: `git submodule add <url to git> themes/<theme name>`
3. Add the theme key to the config.toml file: `theme = "<theme name>"`

## Github Pages

### Simple github managed publishing

1. Add the configuration to point the toml file to publish at docs
**config.toml**
```toml
publishDir = "docs"
```

2. Navigate to github.com/<username>/<project-name>/settings.
3. Go to the github pages section, in the drop down select the option to deploy from the `/docs` folder.

Here's some links to help out.
- [Hugo Site](https://gohugo.io/hosting-and-deployment/hosting-on-github/)
- [Github Pages Site](https://help.github.com/en/github/working-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)

### To keep the hugo repo private

1. Create a submodule for your public folder: `git submodule add -b master https://github.com/<USERNAME>/<USERNAME>.github.io.git public`.
2. Subsequent deployments can be done with `bash ./deploy.sh`.

- [deploy.sh source](https://gohugo.io/hosting-and-deployment/hosting-on-github/#put-it-into-a-script).

### Github Actions






## Advanced Archetypes

Archetypes can be used to create folders.
```
.
├── archetypes
│   ├── posts.md
│   ├── default.md
│   └── post-bundle
│       ├── index.md
│       ├── about.md
│       └── images
│           └── image.jpeg
...
```

- `hugo new post-bundle posts/newPost`