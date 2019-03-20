# Human-Joint-Constraints-Training
<a href="#roslab-run"><img src="https://img.shields.io/badge/ROSLab-run-brightgreen.svg"></a>

Training procedure for ICRA 2018 paper https://arxiv.org/abs/1709.08685. For usage during physics simulations, see https://github.com/dartsim/dart/pull/1016.

The Matlab procedure here depends on the database and code developed by Akhter and Black: http://poseprior.is.tue.mpg.de/.
You will need to sign up an account there to access their database. After you do that, unzip their prior.zip file, and move all the files in the unzipped folder into the Human-Joint-Constraints-Training folder.

Run toa_generate_random_pairs.m to generate samples for training the range(validity) of left arm poses; Run tol_generate_random_pairs.m to generate samples for training the range(validity) of left leg & foot poses;

Neural-net training follows the standard process of feed-forward nets. There is an example python script keras_leftarm_train.py using the Keras library for your reference.

# ROSLab Run

## Prerequisites:
* [Docker](https://www.docker.com/)
* [nvidia-docker](https://github.com/nvidia/nvidia-docker/wiki/Installation-(version-2.0))
* Tested on Ubuntu Linux 16.04, Docker version 18.06.1-ce, NVIDIA Driver version 410.48.

## 1. Clone the repository and build ROSLab image:
```
git clone https://github.com/ICRA-2018/Human-Joint-Constraints-Training.git
cd Human-Joint-Constraints-Training
./roslab_build
```
## 2. Launch ROSLab image:
```
./roslab_run
```
## 3. Open JupyterLab in your browser:
[http://localhost:8888/lab/tree/README.ipynb](http://localhost:8888/lab/tree/README.ipynb)

## 4. Run in JupyterLab:

Open the notebook [demo.ipynb](demo.ipynb) and run all the cells.
