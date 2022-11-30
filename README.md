# CuboidBlocks

## Description
This is a **dataset** of volumetric mapping problems. It consists of 60 instances, each consisting of a tetrahedral mesh of a genus 0 object together with a prescribed mapping of its boundary onto a cuboid. A standard 3D Tutte embedding fails (i.e. yields inverted/flipped elements and thus a non-bijective map) on every single instance. Also state-of-the-art 3D untangling methods struggle with it, despite the relatively simple convex boundary setting. For instance, the [Code](https://github.com/duxingyi-charles/lifting_simplices_to_find_injectivity) of the method ["Lifting Simplices to Find Injectivity"](https://dl.acm.org/doi/abs/10.1145/3386569.3392484) succeeds on 35/60, the [Code](https://github.com/ssloy/invertible-maps/tree/main/cpp) of the method ["Foldover-free maps in 50 lines of code"](https://dl.acm.org/doi/abs/10.1145/3450626.3459847) succeeds on 28/60. We therefore hope it can inspire and be of use in further research on this problem.

## Origin
The instances were encountered during research in the context of the [3D Motorcycle Complex](https://github.com/HendrikBrueckler/MC3D).

## Structure
Each instance is represented by two tetrahedral meshes in `.vtk` format, `object.vtk` and `parameter.vtk`. Both contain the same mesh structure, `object.vtk` equipped with the XYZ-coordinates (object space) per vertex, `parameter.vtk` equipped with UVW-coordinates (parameter space) per vertex (where the boundary vertices' UVW-coordinates represent the prescribed boundary map; the interior vertices' UVW-coordinates represent the (non-flip-free) Tutte embedding solution). The `handles.txt` file of each instance additionally contains the list of indices of boundary vertices (as required as additional input by one of the above codes).
