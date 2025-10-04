# RealEstate10K_downloader
These scripts are used to download RealEstate10K dataset. 

## Install 
Install `yt_dlp` in your environment.

```bash
pip install yt_dlp
```

## Download Videos
Download [RealEstate10K](https://google.github.io/realestate10k/download.html) txt files and extract here manually. Arrange it as follows:

```bash
├── RealEstate10K
│      └── pose_files
│             ├── train
│             └── test
```

Then, execute the following commands
```shell
python3 generate_dataset.py test
python3 generate_dataset.py train
```
This downloads YouTube movies and extract frames which are needed.  

```bash
├── RealEstate10K
│      ├── pose_files
│      │      ├── train
│      │      └── test
│      └── videos_youtube
│             ├── train
│             └── test
```

RealEstate10K(including images) is very large. Please be careful.    
__Please use this at your own risk.__

Because of unkown reasons, `yt_dlp` fails to download and save movies. 
In this case, sequence name is added to `failed_videos_{test, train}.txt`.

## Visualizer

Also, `vizualizer.py` is placed here. This shows us camera poses using Open3d.
```shell
python3 vizualizer.py [/path/to/pose_data.txt]
e.g. (python3 vizualizer.py ./RealEstate10K/test/0c4c5d5f751aabf5.txt)
```

