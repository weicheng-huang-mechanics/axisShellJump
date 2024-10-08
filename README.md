# Overview
This project involves a dynamic simulation of an axisymmetric shell jumper.

<br/><img src='demo.gif' width="600">

# Prerequisites

0. Update

```bash
   sudo apt-get update
   ```

1. Install lapack

```bash
sudo apt-get install libblas-dev liblapack-dev
```

2. Install gfortran

```bash
sudo apt-get install gfortran
```

3. Install OpenGL


```bash
sudo apt-get install freeglut3-dev
```

4. Download eigen3

```bash
https://gitlab.com/libeigen/eigen/-/releases/3.4.0
```

5. Move eigen3 to /usr/local/include


```bash
sudo mv 'your eigen' /usr/local/include
```

6. Install mkl

```bash
sudo apt-get install -y gpg-agent wget

wget -qO - https://repositories.intel.com/graphics/intel-graphics.key | sudo apt-key add -

sudo apt-add-repository 'deb [arch=amd64] https://repositories.intel.com/graphics/ubuntu focal main'

sudo apt-get update

sudo apt-get install intel-opencl-icd intel-level-zero-gpu level-zero intel-media-va-driver-non-free libmfx1

cd /tmp

wget https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB

sudo apt-key add GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB

rm GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB

echo "deb https://apt.repos.intel.com/oneapi all main" | sudo tee /etc/apt/sources.list.d/oneAPI.list

sudo apt update

sudo apt install intel-basekit

sudo apt install intel-hpckit(not required)
```

# Installation

```bash
source /opt/intel/oneapi/setvars.sh

g++ -I /usr/local/include/eigen-3.4.0/ main.cpp world.cpp setInput.cpp timeStepper.cpp inertialForce.cpp externalGravityForce.cpp dampingForce.cpp elasticStretchingForce.cpp elasticBendingForce.cpp elasticPlate.cpp externalPressureForce.cpp elasticBoundaryForce.cpp externalContactForce.cpp -lGL -lglut -lGLU -L${MKLROOT}/lib/intel64 -Wl,--no-as-needed -lmkl_intel_lp64 -lmkl_intel_thread -lmkl_core -liomp5 -llapack -lgfortran -fopenmp -lpthread -lm -Ofast -o simDER

```

# Run 

```bash
./simDER option.txt

```

