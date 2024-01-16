# Hannah's UNIX Cafe

Author: Hannah Houts, @hehouts, UC Davis.

## Getting started

Use this to get familiar with the RStudio interface and the unix shell.

Start by opening RStudio.

### Log into farm

Use your datalab-XX account to log into farm.

### Allocate a compute node

Run:
```
srun -p high2 --time=3:00:00 --nodes=1 --cpus-per-task 1 --mem 5GB --pty /bin/bash
```

### Install the necessary software

The first time you run this, create a conda environment with the necessary software:
```
module load mamba

mamba create -y -n cafe r-rmarkdown r-knitr
mamba activate cafe
```
this will take ~5 minutes.

Every time thereafter, you will need to run the following after srun:
```
module load mamba
mamba activate cafe
```

### Start up RStudio Server

```
module load rstudio-server
rstudio-launch 
```

and follow the process to connect to RStudio Server from your laptop.

### R Studio

When you first open RStudio, you'll notice it's divided into several panels, each serving a distinct purpose.

1. **Console Panel**: This is where R code is executed. You can type commands directly here or run code from a script. It's like a direct line of communication with R.

2. **Source Panel**: Here, you write and edit files (R scripts, R markdowns, shell scripts). This panel supports features like syntax highlighting and tab-completion to make writing R code easier.

3. **Environment/History Panel**: The Environment tab displays variables created during your R session, along with their values and types. The History tab keeps a log of all commands you've run, allowing you to revisit and reuse them.

4. **Files/Plots/Packages/Help/Viewer Panel**: This multifunctional panel has tabs for:
   - **Files**: Browse, view, and manage files in your working directory.
   - **Plots**: View graphs and charts you generate with your code.
   - **Packages**: Install, load, and manage R packages.
   - **Help**: Access R documentation and help files.
   - **Viewer**: Display web content or visualizations.

### Open the tutorial

Go to the Console panel on the left, and then click on the Terminal.
At the terminal prompt, type:

```
cd ~/
git clone https://github.com/ctb/hannahs-unix-cafe
```

In the Files panel, you'll see a new folder, `hannahs-unix-cafe`. Go to that
folder and open tutorial.Rmd in RStudio by clicking on it.

