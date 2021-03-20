# MapD Docker GPU cuda
Building MapD from source in a cuda docker image.

1. Install docker and nvidia docker toolkit from below link  
   ```https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker```

2. Pull cuda runtime docker image from docker hub and run  
   ```docker pull nvidia/cuda:11.2.2-cudnn8-devel-ubuntu20.04  
   docker run -it --name container_name --gpus device=0 docker-image-id bash```

3. Clone latest omnisci(Previously known as MapD) repository from github.  
   ```git clone git@github.com:omnisci/omniscidb.git```

4. Replace llvm patch file under script directory with above patch file.  

# Build
```
mkdir build  
cd build  
cmake -DCMAKE_BUILD_TYPE=debug ..  
make -j 4  
```
