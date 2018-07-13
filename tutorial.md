# Making your first Binder
*A collaborative document*

## Contents 
- [Motivation](https://github.com/dmgt/binder_tutorial/blob/master/tutorial.md#motivation)
  - Why might I want to use it?
  - What is Binder? 
- [Making some Binders](https://github.com/dmgt/binder_tutorial/blob/master/tutorial.md#making-a-binder-based-on-a-fork-of-an-existing-binder-template)
  - Example 1: Making a Binder based on a fork of an existing Binder template
  - TODO Example 2: Adding some data to the example Binder
  - TODO Example 3 -  Making a Binder based on an existing repo of your own, from scratch
   
## Motivation

 - Run publically-avalible code in your browser without having to download the software or data it depends on to your own laptop! 
     - [**Try it here**](http://jupyter.org/try)
 - Allow others to temporarily run and modify a python or R script you have written, regardless of the version(s) of Python or R (if any) they have installed
 - Preserve and share a rendered version of a research compendium so that reviewers, readers, and possible reusers may quickly evaluate and share your work


### What *is* Binder?
As [summarized](https://hackmd.io/s/S1fWYzBfQ#) by Binder developer Carol Willing:

---
 - It's a service ([mybinder.org](https://mybinder.org/))
 - A way to display your work (eg with Jupyter notebooks or R Shiny)
 - A clickable badge you can get for a GitHub repo
 -  A project you can deploy ([BinderHub](https://binderhub.readthedocs.io/en/latest/))
 
---
       
  - [Official diagram](http://binderhub.readthedocs.io/en/latest/overview.html) from documentation

 - A [diagram](https://github.com/dmgt/binder_brainstorming/blob/master/binder_diagram_draft.pdf) targeting novices 


### Some more cool examples of Binders
- Launch code from an interactive textbook with Binder: https://github.com/willingc/ThinkDSP
- Launch a tutorial with all the code and data from CERN for a gravity wave tutorial! ([click 'LIGO Binder' here](https://notebooks.gesis.org/))
- Launch an academic paper with all the code and data in RStudio in Binder: https://github.com/cboettig/noise-phenomena

## How to make Binders
#### Example 1 - A Binder based on a fork of an existing Binder template 

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
- TODO

### Example 3 -  Making a Binder based on an existing repo of your own, from scratch
- R example from Hao: https://github.com/ha0ye/Power_of_Irma
- Python example from Carol: https://github.com/willingc/ThinkDSP
- R package from Hao: https://github.com/ha0ye/rEDM

1. Check the information on repo2docker [configuration files](https://repo2docker.readthedocs.io/en/latest/config_files.html) to identify how to specify the package dependencies for your repo.

*Note that you need a `runtime.txt` file to specify the version of Python or R.*

*For an R package repo, you will want to add `R CMD INSTALL .` to the `postBuild` file so that the package will be installed from the contents of the repo (as the latest version of the package may not be available from MRAN yet).*

2. Add these files to your existing repo, either in the root directory, or in a `/binder` folder.

3. Follow the directions in step 4. of [Example 1](#example-1---a-binder-based-on-a-fork-of-an-existing-binder-template) above to create a new binder for the repo.

4. If you modify files in the `master` branch of your repo, launching Binder will go through the steps of building a new image. Thus, if you want Binder links in your README, it's recommended to add those before launching Binder, so that you don't have to wait through another build of the image.

Here are the sample links:
```
Jupyter+R: [![Binder](http://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/yourusername/r/master?filepath=index.ipynb)

RStudio: [![Binder](https://mybinder.org/v2/gh/yourusername/r/master?urlpath=rstudio)

RShiny: [![Binder](http://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/yourusername/r/master?urlpath=shiny/bus-dashboard/)
```

### Can be added in future: 
- FAQ (lots of questions summarized from breakout session [here](https://hackmd.io/SGRP3O3CSoOORDDQfpMlow?both#)

- Making a binder of a research compendium that exists as a GitHub repo, for review and evaluation purposes (there are examples of such in the published literature that we can point to. This example might also include how to reposit and get the DOI for the object.)
