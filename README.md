# SPICEMIX-GASTRULOID

This README.md file documents how I (Tee) installed and analyzed data using `spicemix` package. I hope that this GitHub repo will foster collaboration and keep us on the same page with the analyses. 

## Clone This Repository on to Local Device 
1. Add introduction to Git 

## Install `spicemix` on Server 2
1. Access Anaconda Powershell Prompt by pressing Start and search for Anaconda Powershell Prompt. The name in parenthesis is the name of conda environment i.e., `Anaconda Powershell Prompt (openmm2)` will launch Anaconda Prompt in `openmm2` conda environment. In this case, it does not matter which one you choose. 
2. In Anaconda Powershell Prompt, create a new conda environment by typing `conda create -n spicemix python=3.10`.

     * Option `-n` specifies the name of the environment. Here we create a new environment named `spicemix`. 
     * Argument `python=3.10` specifies the version of Python that will be installed in this environment. This ensures the compatibility between Python; `torch`, a neural net package used by `spicemix`; and `CUDA` accelerated hardwares available on Server 2. 
  
3. Activate the newly created environment by entering `conda activate spicemix`. 

4. Install GPU-supported `torch` by entering the following command: `pip install torch==1.11.0+cu113 torchvision==0.12.0+cu113 torchaudio==0.11.0 --extra-index-url https://download.pytorch.org/whl/cu113` 

5. Check if `torch` can find `CUDA` by accessing `IPython` from Anaconda Powershell Prompt. 

    5.1. Type `python` on the Powershell Prompt.

    5.2. Import `torch` by entering `import torch`.

    5.3. Check if `torch` can see `CUDA` by adding this command `torch.cuda.is_available()`. It should return `True`. 

    For example, 
    ```{ipython}
    >>> import torch
    >>> torch.cuda.is_available()
    True 
    ```


6. Install the remaining dependencies for this package by typing in `conda install pytorch pandas scikit-learn h5py tqdm scanpy louvain python-igraph seaborn jupyterlab -c conda-forge`.

   * Option `-c conda-forge` ensures that conda finds these packages in the right channel. Without this option, Anaconda takes a long time to find packages and most of the time fail. 

## Analyze Tutorial Data Available Online 
1. Access Anaconda Powershell Prompt by pressing Start and search for Anaconda Powershell Prompt. The name in parenthesis is the name of conda environment i.e., `Anaconda Powershell Prompt (openmm2)` will launch Anaconda Prompt in `openmm2` conda environment. In this case, it does not matter which one you choose.

2. Activate the spicemix environment by entering `conda activate spicemix`.

3. Go to the directory that contains the jupyter notebook file by entering `cd F:/Tee/spicemix/spicemix-gastruloid/scripts/`

4. Run the command `juyter lab`. This should launch a new browser tab that allows you to interact with Jupyter (interactive python) session.

5. To the left, open the file `20240523_Tutorial.ipynb`
