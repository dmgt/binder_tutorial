# Making your first Binder
*A collaborative document*

### Contents 
- [Motivation](https://github.com/dmgt/binder_tutorial/blob/master/tutorial.md#motivation)
  - Why might I want to use it?
  - What is Binder? 
- [Making some Binders](https://github.com/dmgt/binder_tutorial/blob/master/tutorial.md#making-a-binder-based-on-a-fork-of-an-existing-binder-template)
  - Example 1: Making a Binder based on a fork of an existing Binder template
  - TODO Example 2: Adding some data to the example Binder
  - TODO Example 3 -  Making a Binder based on an existing repo of your own, from scratch
   
## Motivation

### Why might I want to use it? 

 - When do you use a binder? Running code from Github without having to download Python or R to create the Jupyter or RStudio environment (eg teaching a large class using RStudio without having to have all students download various versions of R)
    - If you know how to use git, clone the repo and make edits on git. If you don't know how to use git, you can use binder to manipulate data 
    - Why do we use containers? Creating a setting in which all computer architecture is equalized, variable hardware from person to person will not affect the memory allocated for calculations, which could effect data analysis 
- "Freezing" and sharing a rendered version of a research compendium being entered into the scholarly record so that reviewers, readers, and possible reusers may evaluate the findings 


### What *is* Binder?
   - [Quoting](https://hackmd.io/s/S1fWYzBfQ#) Binder developer Carol Willing: It's a service, a way to display your work (eg with Jupyter notebooks or R Shiny), a clickable badge you can get for a GitHub repo, and a project you can deploy 
   - A [diagram](https://github.com/dmgt/binder_brainstorming/blob/master/binder_diagram_draft.pdf) targeting novices 
        - novice gave feedback this still assumed things they hadn't seen before eg what is a container anyway?
   - [Official diagram](http://binderhub.readthedocs.io/en/latest/overview.html) from documentation


Try it out: 
- https://try.jupyter.org
- Launch a book with Binder: https://github.com/willingc/ThinkDSP
- Launch an academic paper with all the code and data and RStudio in Binder

## Making a Binder based on a fork of an existing Binder template 
#### Example 1 - exactly replicating the example Binder 

1. Register for a [GitHub](https://github.com/) account if you do not have one.
2. Go to the [binder-examples](https://github.com/binder-examples/r) GitHub repo and click on one of the examples eg `r` or `jupyterlab`

    <img src="screenshots/binder_example_repo_smaller.PNG" alt="Screenshot of Binder Examples GitHub repository" width="700px"/> 
    
3. Click the grey "Fork" button on the top-right corner of the page, which will create your own copy of the repo under your own GitHub account.  

     <img src="screenshots/fork_button.PNG" alt="Screenshot showing fork button on upper right corner" width="700px"/> 

4. Go to the [mybinder](https://mybinder.org/) website, copy the url of your forked repository `https://github.com/yourusername/r` and paste it under the `GitHub repo or URL` section.

     <img src="screenshots/binder_webpage_smaller.PNG" alt="Screenshot of Binder project homepage at mybinder.org" width="700px"/> 
    
    You can leave the `Git branch, tag, or commit`  and `Path to a notebook file` options blank

5. When you click `launch`, Binder will start building what's called an *image* that contains all of the code and data and required software specified in the example repository you forked. This will probably take a while - eg 10 minutes. If too many people (eg a large entire classroom) try to do this at once, it may be more than mybinder.org can handle at once right now :)

    <img src="screenshots/building_progress_bar.PNG" alt="Screenshot of Binder loading progress bar" width="700px"/> 
    
    If you want to see what is happening in more detail, click 'show build logs'

     <img src="screenshots/build_log_example.PNG" alt="Screenshot of build log showing the progress of installing different packages" width="700px"/>

  
7. When the Binder opens, by default you will see a Jupyter file browser.
The image below shows a Binder from the `r` example page shown above.
  
     <img src="screenshots/jupyter_file_browser.PNG" alt="Jupyter file browser - a file directory" width="700px"/>
    
8. Click on the file ending in `.ipynb`to open it - now you can interact with the code in your Browser, while it runs on a remote computer, thanks to Binder! Note that this session is temporary and will time out after about an hour (or less) if it is not used. The url generated will only work for this temporary session, in the future you will have to open the Binder again. 

    <img src="screenshots/notebook_example.PNG" alt="Screenshot of a Jupyter notebook running R with some code and a plot" width="700px"/>

9. If you want to open an RStudio session or R shiny app instead of opening the R code in a Jupyter notebook, then go back to your own github page where you forked the example, eg  `https://github.com/yourusername/r`, and edit the `README.md`. 
 
change 
```
Jupyter+R: [![Binder](http://mybinder.org/badge.svg)](http://beta.mybinder.org/v2/gh/binder-examples/r/master?filepath=index.ipynb)

RStudio: [![Binder](http://mybinder.org/badge.svg)](http://beta.mybinder.org/v2/gh/binder-examples/r/master?urlpath=rstudio)

RShiny: [![Binder](http://mybinder.org/badge.svg)](http://beta.mybinder.org/v2/gh/binder-examples/r/master?urlpath=shiny/bus-dashboard/)
```

   to
   
```
Jupyter+R: [![Binder](http://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/yourusername/r/master?filepath=index.ipynb)

RStudio: [![Binder](https://mybinder.org/v2/gh/yourusername/r/master?urlpath=rstudio)

RShiny: [![Binder](http://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/yourusername/r/master?urlpath=shiny/bus-dashboard/)
```
and click `commit changes` at the bottom of the page. 

Now you can click the badges to open your own binder in a Jupyter notebook, *or* an Rstudio session or R shiny app :) 

You can also directly try opening a url by adding `urlpath=rstudio` at the end , eg <https://mybinder.org/v2/gh/yourusername/r/master?urlpath=rstudio>

 

### Example 2 - adding some data to the example Binder 


### Example 3 -  Making a Binder based on an existing repo of your own, from scratch
- TODO: R example
    - Example from Hao: https://github.com/ha0ye/Power_of_Irma
- TODO: Python example



### Can be added in future: 
- Making a binder of a research compendium that exists as a GitHub repo, for review and evaluation purposes (there are examples of such in the published literature that we can point to. This example might also include how to reposit and get the DOI for the object.)
- FAQ
