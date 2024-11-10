export PATH=$PATH:/usr/local/cuda/bin
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda/lib64

export PATH=$PATH:/usr/include/mpich-3.2-x86_64
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/lib64/mpich-3.2/lib
export LD_LIBRARY_PATH=/usr/lib64/mpich-3.2/lib:$LD_LIBRARY_PATH

nvcc nccl-reduce.cu -o nccl-reduce -lnccl

nvcc nccl-reducempi.cu -o nccl-reducempi -lnccl -lmpi -L /usr/lib64/mpich-3.2/lib/ -I /usr/include/mpich-3.2-x86_64

nvcc nccl-stream.cu -o nccl-stream -lnccl -lmpi  -L /usr/lib64/mpich-3.2/lib/ -I /usr/include/mpich-3.2-x86_64

nvcc nccl-softmax.cu -o nccl-softmax -lnccl -lmpi  -L /usr/lib64/mpich-3.2/lib/ -I /usr/include/mpich-3.2-x86_64

nvcc nccl-jacobi.cu -o nccl-jacobi -lnccl -lmpi  -L /usr/lib64/mpich-3.2/lib/ -I /usr/include/mpich-3.2-x86_64

nvcc nccl-overlay.cu -o nccl-overlay -lnccl -lmpi  -L /usr/lib64/mpich-3.2/lib/ -I /usr/include/mpich-3.2-x86_64
