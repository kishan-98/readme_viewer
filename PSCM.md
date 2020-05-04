# <center>Physics of Soft Condensed Matter</center>
## <center>Final Project</center>
## <center>Steered Molecular Dynamics</center>
## <center>Deca-Alanine</center>
### <center>Kishan Sangani</center>
### <center>201501053</center>


## Introduction
This README is to guide you step by step in order to generate all the necessary graphs.

## Directory Hierarchy
```
201501053
|- 201501053_PSCM_Final_Project.pdf => project report
|- *.tcl => required tcl libraries to plot graph
|- get_graphs.sh => gets all the graph from data using tcl scripts
|- compile_graphs.sh => generates the combined graph of distribution of work
|- plots => will contain all the plots with appropriate file name
|- molecules => contains the screenshots of the molecules from VMD GUI
|- ExpCond_* => contains the data related to various experimental conditions
    |- unfold => contains experimental data about unfolding
        |- plot_graphs.tcl => tcl script to plot all the graphs in xmgrace format for unfolding
        |- get_graphs.sh => converts the above graphs from xmgrace format to png format
    |- refold => contains experimental data about refolding
        |- plot_graphs.tcl => tcl script to plot all the graphs in xmgrace format for refolding
        |- get_graphs.sh => converts the above graphs from xmgrace format to png format
    |- plot_work.py => plots the work distribution for the given experiment
|- gen_expr.sh => file that generates the experimental condition above **Kindly refrain from using the above as it is configured for MacOS; that is the reason why I have attached experimental condition data**
```

## Usage
* Run `./get_graphs.sh all` to generate all the graphs.
* Conversely, if you want graphs for only particular condition, run `./get_graphs.sh <condition ID(2-5)>`
* Run `./get_graphs.sh clear all` to clear all the graphs.
* Conversely, if you want to clear graphs for only particular condition, run `./get_graphs.sh clear <condition ID(2-5)>`
* Run `./compile_graphs.sh` to compile all the graphs.
    * Make sure to run `./get_graphs.sh all`, otherwise it might throw errors for some of the graph as they might not be created. However, `./get_graphs.sh all` automatically compiles all the graphs.
* Conversely, if you want to compile graphs for only some condition, run `./compile_graphs.sh <beginning condition ID> <end condition ID>`

## Procedure
* `get_graphs.sh` script goes into the experimental directory and executes the Tcl/Tk `plot_graphs.tcl` scripts (as mentioned in the hierarchy) which generates graphs in xmgrace format, which are then converted to png and stored in ExpCond_X/[un|re]fold/plots.
* Then those plots are converted to PNG using the other `get_graphs.sh` script in the respective experimental condition folders.

## TL;DR

* First run `./get_graphs.sh clear all` to clear all the graphs.
* Then run  `./get_graphs.sh all` to generate and compile all the graphs in the plots directory as mentioned above in the hierarchy.
