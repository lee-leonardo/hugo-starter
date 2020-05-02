# leo-hugo-starter
A hugo starter project with the scripts in place for adoption on github pages. Also a helpful synopsis included here of the starter guide to serve as a reference and get up to speed with a glance.
Learn more at the site: https://gohugo.io/getting-started/external-learning-resources/

## Prereqs

- [install hugo](https://gohugo.io/getting-started/installing/)
- generate template: `hugo new site <name>`

## Layout

```
.
├── archetypes      # templates to generate front matter based on the path used (example below)
├── config.toml     # config can be json, toml, yaml. https://gohugo.io/getting-started/configuration/#all-variables-yaml
├── content         # output folder
├── assets          # things to process with hugo pipes such as Sass/Less, etc. https://gohugo.io/hugo-pipes/
├── data            # data to be processed into pages can be json, toml, yaml. https://gohugo.io/templates/data-templates/
├── layouts         # html templates. https://gohugo.io/templates/introduction/
├── static          # copied to the site as is.
└── themes          # published or created themes used by the site as a base.
*── resources       # folders created to serve as caches for operations such as Sass.

```

### Examples

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