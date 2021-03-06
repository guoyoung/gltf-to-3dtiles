# GLTF-Optimizer
A command line tool to convert gltf(glb) file to 3d tiles format.

# Usage example
GLTF_OPTIMIZER.exe -i "../data/test.gltf" -o "../data/output"

# Demo
Here is the source gltf model and the generated result.
https://pan.baidu.com/s/10VI1h9dORIFFDF8CVSRdnQ 
code: pw6l 

# Build
git clone -b devel https://github.com/cnr-isti-vclab/vcglib.git

Set environment VCG_LIB to root of vcglib.

git clone https://github.com/nxddsnc/GLTF-Optimizer.git

Build it with vs2015 community.

# Overview
There are serveral step for the conversion.

Step1. Import gltf file use [tinygltf](https://github.com/syoyo/tinygltf).

Step2. Create hierachical binary tree and insert nodes to boxes according to it's bounding box center.

Step3. Generate tileset structure according to the result of step2.

Step4. Do decimation on each level of the tree with the powerful mesh processing library [vcglib](http://vcg.isti.cnr.it/vcglib/).

Step5. Output the tileset.json file and corresponding gltf/glb(contains batchId) files.

After conversion, we can use 3dtiles-tools to convert glb to b3dm so that it can be viewed in cesium.js. Or use the command called "glbsToB3dms" in my fork (https://github.com/nxddsnc/3d-tiles-tools).

# Note
##### It is just a test project yet and with no textures supported yet. And currently I am working on issue#8.
##### If you have any questions, please contact me(fanqileiOGL@163.com).


