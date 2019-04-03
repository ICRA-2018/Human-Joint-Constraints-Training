# Human-Joint-Constraints-Training
[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/icra2018/human-joint-constraints-training.svg)](https://hub.docker.com/r/icra2018/human-joint-constraints-training)
<a href="#how-to-run-with-docker"><img src="https://img.shields.io/badge/Docker-instructions-brightgreen.svg"></a>

Training procedure for ICRA 2018 paper https://arxiv.org/abs/1709.08685. For usage during physics simulations, see https://github.com/dartsim/dart/pull/1016.

The Matlab procedure here depends on the database and code developed by Akhter and Black: http://poseprior.is.tue.mpg.de/.
You will need to sign up an account there to access their database. After you do that, unzip their prior.zip file, and move all the files in the unzipped folder into the Human-Joint-Constraints-Training folder.

Run toa_generate_random_pairs.m to generate samples for training the range(validity) of left arm poses; Run tol_generate_random_pairs.m to generate samples for training the range(validity) of left leg & foot poses;

Neural-net training follows the standard process of feed-forward nets. There is an example python script keras_leftarm_train.py using the Keras library for your reference.

# How to Run with Docker

## Linux
#### Prerequisites
* MATLAB installed on local host.

Tested on Ubuntu 16.04.6 with Docker 18.06.1-ce, MATLAB R2017a.

1. Open a terminal and run the command (replacing the MATLAB folder and MAC address with your own):
```
docker run --rm -p 8888:8888 -v /usr/local/MATLAB/R2017a:/usr/local/MATLAB/R2017a \
    -v /usr/local/lib/python3.5/dist-packages/matlab:/usr/local/lib/python3.5/dist-packages/matlab \
    --mac-address=2c:60:0c:d6:50:36 icra2018/human-joint-constraints-training:latest
```
2. Run a web browser and open the link: [http://localhost:8888/lab/tree/README.ipynb](http://localhost:8888/lab/tree/README.ipynb)
