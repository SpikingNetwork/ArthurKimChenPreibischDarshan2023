This repository contains Jupyter notebooks describing a workflow that could be
used to re-create the figures in [Arthur, Kim, Chen, Preibisch, and Darshan
(2023)](https://www.biorxiv.org/content/10.1101/2022.09.26.509578v3.full).  The
actual figures were made using the Linux command line interface to
TrainSpikingNet.jl to facilitate batching parallel jobs out to an on-premise
cluster.


If you want to follow along, you'll need to install and run Jupyter:

```
julia> ]add IJulia
julia> using IJulia
julia> notebook()
```

The default kernel uses just one thread.  To create a kernel that fully
utilizes your CPU cores:

```
installkernel("Julia auto threads", env=Dict("JULIA_NUM_THREADS" => "auto"))
```

To use Jupyter remotely, on a headless machine for example:

```
julia> using IJulia
julia> IJulia.find_jupyter_subcommand("")[1]   # copy the output for later
```

Then, on the Unix command line:

```
ssh <your-machine> -L 8888:localhost:8888
<path-to-jupyter-from-above> notebook
```

See https://github.com/JuliaLang/IJulia.jl/issues/586 for more details.
