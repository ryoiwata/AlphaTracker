# Steps Taken

## Installation

- Add libcuda.so symlink to libcuda.so.1
    - https://github.com/apache/incubator-mxnet/issues/8436
    - `sudo ln -s /usr/lib/x86_64-linux-gnu/libcuda.so.1 /usr/lib/x86_64-linux-gnu/libcuda.so`
    - `make`

- Removed unzip line for: /home/riwata/Projects/Tracking_Alphas/AlphaTracker/Tracking/AlphaTracker/download.py

- Replaced the model at: /home/riwata/Projects/Tracking_Alphas/Iwata_temp/AlphaTracker/Tracking/AlphaTracker/models/sppe
    - Original was just an HTML file

- Need to rerun Alphatracker
    - /home/riwata/Projects/Tracking_Alphas/AlphaTracker/Tracking/AlphaTracker/track_result/alphapose-results.json
        - Boxes are all NaN