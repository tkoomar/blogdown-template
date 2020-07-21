# blogdown-template

# Part 1

## Set Up

There are a few steps and packages to install before you get your blog all set up:
```{r}
install.packages("blogdown")
library(blogdown)
install_hugo()
## If you want to start a site from scratch, with examples of all available widgets:
## blogdown::new_site(theme = "gcushen/hugo-academic")
```

## Resources
 
* The Academic theme docs:
    * https://sourcethemes.com/academic/
* The Blogdown book:
    * https://bookdown.org/yihui/blogdown/
    
## The Homepage

When someone arrives at your website, they will usually land on your *homepage*, so this is where we will start. All of the content for your site is, conveniently located in the `content/` directory, and the content for the homepage is in the `content/home/` sub-directory. 

Each section of the Academic homepage is a "widget". Each widget has a corresponding `*.md` file in `content/home/`. The order of the widgets is determined by their **weight**, which is set near the top of each `*.md` file. Widgets with *lower* weight appear first. For a full breakdown of all of the possible widgets, see the documentation for Hugo Academic: https://sourcethemes.com/academic/docs/page-builder. We will only go over the few section types found on this simple site. 

### Render the site

To preview your site locally, run: 
```{r}
blogdown::serve_site()
```
Now, let's go down each section of the page home page and do a little investigating of each section. We will skip the top menu bar for now and go on to the 

### Slider (`/content/home/slider.md`)

This displays a carousel of some images, potentially with text and link overlays. Pretty cool, but maybe not the style you're going for. If you want to disable it, you can either set `active = false` on line 5, or just delete `content/home/slider.md`. You'll need to run `blogdown::hugo_build()` to rebuild the site to see the change reflected. 


If you want to keep this section, open the `content/home/slider.md` file. As you can see, each template is fairly well documented with comments, so follow those to add your own images to the `static/img/` directory.  I am a big fan of www.pexels.com for high quality and CC-0 stock images, like the ones I included here. www.flaticon.com is also a good option for vector based pictures -- it's licence just requires attribution. 

### About Me (`content/home/about.md`)

This is the section where you can talk about yourself. If you notice, there isn't a lot in this file. That is because, as it mentions in the header, most of that is living in `content/authors/yourname`. 

The content for this widget is actually being pulled from a different page (the authors page, specifically). If you go to `content/authors/yourname/_index.md`, you can customize this biography. Keep it short and to the point, there are more sections later to highlight specific aspects of your work. 

I would recommend renaming 'yourname' to, you know, your actual name. This is in three places:
1) The `content/authors/yourname` directory
2) Line 3 of `content/authors/yourname/_index.md`
3) Line 13 of `content/home/about.md`

Now, just go through `content/authors/yourname/_index.md`, customizing the content as desired, including the links to your various social and scientific profiles. Finally, replace `content/authors/yourname/avatar.jpg` with a nice photo of yourself cropped square. The image needs to be called `avatar.jpg`. 

### Skills(`content/home/skills.md`)

This section is a nice way to highlight a few of your key skills for potential employers. You may not want it so prominent, or at all. Feel free to change the weight to lower it, or remove it entirely. I my case, I moved it (along with the  next few sections) to their own page. We won't cover that now, but it is also an option. 

If you do want to keep this section and add your own icons, go here: https://fontawesome.com/icons?d=gallery&m=free to see what is available. You'll notice that these we used in the About section for social links as well. 


### Education and Experience (`content/home/experience.md`)

This is more accurately thought of as a timeline section. Feel free to add in as many sections as you want for degrees, jobs, or research positions you've had. They should reorder automatically based on the start and end dates you provide. 

### Accomplishements (`content/home/accomplishments.md`)

Basically a non-linear version of the above widget. You could put awards and past conference attendance here. Or, use the previous section just for education, and this one for jobs and research experience. 

Keep in mind: you can have as many versions of any widget you want -- they just each need a unique file name. Maybe you want two experience widgets, and none of these. 


### Projects (`content/home/projects.md`)

Like how the `about.md` section  draws its content from `content/authors/`, this section gets most of its content from the `content/project/`, where each sub-directory (a **page bundle** in Hugo terminology) is a separate entry. 

Unlike the About/Biography section, there is still a lot going on in `content/home/projects.md`, however. This all has to do with formatting and ordering. Refer to the commends and do some experimentation to get it looking how you like, then move on to adding your own projects to `content/project/`. 

The two example projects in `content/project/` do a good job illustrating the full functionality of those pages. Each project just needs to be a folder with a `index.md` and a `featured.jpg`. Customize/create your own using those `index.md` as templates (the headers are what is mostly important).  

### Featured (`content/home/featured.md`)

This widget just grabs a piece of content and makes it featured. In this case it is a publication (maybe a key paper you want to highlight before you get to the full publication list) -- but you could put a project, talk, or random blog post here. To do so, you just need to add `featured: true` to the header of the `index.md` for the page(s) that you want to appear in the featured section (see line 8 of `content/publication/conference-paper/index.md`)

### Publications (`content/home/publications.md`)

As you might be able to guess at this point, each publication gets its own page, and thus has its own corresponding directory in `content/publication`. 

Like with projects, `content/home/publications.md` just describes how this particular section of the homepage should be formatted. Customize it to your heart's desire, then work on adding your papers to `content/publication`. 

Like each project, each publication directory has an `index.md` and a `featured.jpg`. Fill these out as you desire. Not that while the template provides a few standard link types (like `url_pdf` or `url_code`), you can add your own custom links too. See lines 16-20 of `content/publicatino/journal-article/index.md` for examples. 

Also note that, for me, the automatic citation often gave strange errors, so I removed the `cite.bib` from my publication folders. You might have better luck, and can put the BibTeX format for your articles here for ease of retrieval for yourself and collaborators. 

If your publication doesn't have an eye-catching figure you would like to use as the featured image, I suggest using www.pexels.com or similar to find something pretty and thematically appropriate. 

### Contact

A widget that provides your contact info. Feel free to move or disable entirely.  These parameters are actually set in `config/_default/params.toml`, so look there to set them if you want to keep this enabled. 

## Other Customization

### Random Params (`config/_default/params.toml`)

Color theme can be set on line 16. See https://sourcethemes.com/academic/themes/ for details. 

###  Navbar (`config/_default/menus.toml`)

A detailed description of building menus can be found here: https://gohugo.io/content-management/menus/

The main thing to remember is how URL linking works. If you provide `url = "#somesection"`, the menu will link to the named section on the current page (`www.baseurl.com#somesection`). If you provide `url = "somesection"`, it will instead take you to an entirely new page (`www.baseurl.com/somesection`) See **Project Hash** vs **Project Slash** to get a better sense of what this means. 