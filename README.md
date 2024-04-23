# jupyter_milton
Repo for notebooks and documents for jupyter to Milton job submission

# Running napari_lattice workflows on HPC

## Setup
1. Login to slurm_login node via rap
   1. If this is your first time (test by typing ```conda``` and seeing if the command is found or not) type:
   
      ```module load anaconda3```

      ```conda init```
2. Clone this repo:

    ```git clone https://github.com/BioimageAnalysisCoreWEHI/jupyter_milton```
 
    ```cd jupyter_milton```

------
# THIS IS NO LONGER REQUIRED*
##### *HOPEFULLY...
##### Required environment is now on /Microscopy/BAC_Conda_envs/napari_milton 

3. Create environment 
    ```conda env create -f napari_milton.yml```
4. Currently the pip release of napari_lattice has some bugs, reinstall from git:
   
   ```conda activate napari_milton```

   ```pip install --upgrade --force-reinstall git+https://github.com/bioimageanalysiscoreWEHI/napari_lattice.git```
------------


5. Optional convenience, create a small conda env for the jupyter notebooks (allows extra functionality)

   ```conda deactivate```

   ```conda create -n on_demand python=3.9```

   ```conda activate on_demand```

   ```conda install ipykernel```

   ```python -m ipykernel install --user --on_demand --display-name "Python (on_demand)```

   ```pip install read_roi```
#### Done! You can quit out of slurm_login now

---

# On Demand
Go to ondemand.hpc.wehi.edu.au 

1. Select Jupyter Notebook
2. Under “Additional Modules” type Xvfb
3. Change Runtime hours to as long as you think you’ll need (not to run the whole pipeline, just to get the job(s) submitted. 
4. Click Launch and wait until it’s spun up, then click Connect to Jupyter 
5. Launch “Submit to Milton.ipyb”  
6. Change to on_demand Kernel if you defined one – this is only necessary for some of the new/upcoming features like detecting the number of rois automagically

---

#Jupyter Notebook - useful comands
- ctrl+enter -> run selected cell
- shift+enter -> run selected cell and advance to next cell
- arrow keys -> navigate
- enter -> edit cell

# Example data
Can be found in 

/stornext/General/scratch/GP_Transfer/Lachie/TEST/

- There's a czi and an roi file in there, as well as a psf folder
- The process we want is to crop and deconlolve with cuda_gpu for 20 iterations




