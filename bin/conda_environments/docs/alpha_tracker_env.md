# Commands Used
conda deactivate
conda create -p ./bin/conda_environments/env/alphatracker_env python=3.8
conda activate ./bin/conda_environments/env/alphatracker_env

# Configure the channels
conda config --add channels defaults
conda config --add channels pytorch
conda config --add channels conda-forge

# Install pytorch
conda install -c pytorch -c conda-forge pytorch==1.9.0 
conda install -c pytorch -c conda-forge torchvision==0.10.0
conda install -c pytorch -c conda-forge torchaudio==0.9.0 
conda install -c pytorch -c conda-forge cudatoolkit=11.1 

### RIGHT HERE

# Exporting path for easier installation
export PATH=/usr/local/cuda/bin/:$PATH
export LD_LIBRARY_PATH=/usr/local/cuda/lib64/:$LD_LIBRARY_PATH

# Setting up the environment
python setup.py build develop

##### Please first modify Makefile according to cuda version #####
cd ./Tracking/AlphaTracker/train_yolo/darknet/
## Add libcuda.so symlink to libcuda.so.1
## https://github.com/apache/incubator-mxnet/issues/8436
sudo ln -s /usr/lib/x86_64-linux-gnu/libcuda.so.1 /usr/lib/x86_64-linux-gnu/libcuda.so
make

# Downloading
cd ../../
python3 download.py

## Make sure to get correct copy of AlphaTracker/Tracking/AlphaTracker/models/sppe/duc_se.pth

