# asr_demo
## Clone the above repo and create a virtual env and install habitat-lab
```
conda create -n habitat python=3.8 cmake=3.14.0
conda activate habitat
cd habitat-lab
pip install -e .
cd ..
```
## Installing habitat-sim using conda
```
conda install habitat-sim withbullet -c conda-forge -c aihabitat
```
## Testing
Run the following commands to download some of the Replica scenes (~140mb) and (optionally) 105 scene variations with pre-baked lighting from Replica (~480mb)
```
cd habitat-sim
python src_python/habitat_sim/utils/datasets_download.py --uids replica_cad_dataset
python src_python/habitat_sim/utils/datasets_download.py --uids replica_cad_baked_lighting
```
Then 
either load a ReplicaCAD scene in the viewer application with physics enabled
```
habitat-viewer --enable-physics --dataset data/replica_cad/replicaCAD.scene_dataset_config.json -- apt_1
```
or Replica Baked lighting scene in the viewer with physics enabled
```
habitat-viewer --enable-physics --dataset data/replica_cad_baked_lighting/replicaCAD_baked.scene_dataset_config.json --scene Baked_sc1_staging_00
```

*The viewer application outputs the full list of keyboard and mouse interface options to the console at runtime.*
