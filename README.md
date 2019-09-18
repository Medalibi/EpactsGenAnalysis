# EPACTS - Efficient and Parallelizable Association Container Toolbox for Genetic Analysis of Population-based Association Studies (23rd to 27th September)

### What is EPACTS?

EPACTS is a versatile software pipeline to perform various statistical tests for identifying genome-wide association from sequence data through a user-friendly interface, both to scientific analysts and to method developer.s

### Docker container usage of this package 

```Shell
mkdir $HOME/DATA

docker run -it --rm -v /tmp/.X11-unix:/tmp/.X11-unix:rw --privileged -e DISPLAY=unix$DISPLAY -v $HOME/DATA:/home/training/DATA --device /dev/dri --privileged --name epactsgeneanalysis ebitraining/epactsgeneanalysis
```

#### To resume using an container:

```Shell
docker exec -it epactsgeneanalysis /bin/bash
```

#### To build the container:

```Shell
docker build -f ./Dockerfile -t epactsgeneanalysis .
docker tag epactsgeneanalysis ebitraining/epactsgeneanalysis:latest
docker push ebitraining/epactsgeneanalysis:latest
```

### Downloading and Installing EPACTS

You can clone the current snapshot of this repository to install as well

```Shell
git clone https://github.com/statgen/EPACTS.git
cd EPACTS
cget install -DCMAKE_C_FLAGS="-fPIC" -DCMAKE_CXX_FLAGS="-fPIC" -f requirements.txt
mkdir build; cd build
cmake -DCMAKE_INSTALL_PREFIX=</path/to/install> -DCMAKE_TOOLCHAIN_FILE=../cget/cget/cget.cmake -DCMAKE_BUILD_TYPE=Release ..
make
make install
```

### EPACTS Documentation

The latest version of documentation of EPACTS can be found at
http://genome.sph.umich.edu/wiki/EPACTS

### Feedbacks

Feel free to contact Hyun Min Kang (hmkang@umich.edu) or joint EPACTS Google group (http://groups.google.com/group/epacts) to ask questions about EPACTS
