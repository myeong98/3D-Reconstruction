# 3D Reconstruction

*****

3D Reconstruction을 구현하기 위해 camera sensor를 통해 Droid SLAM을 진행

## Driod SLAM Getting Start

*****

1. 터미널에서 아래의 repo를 복사. (--recursive는 하위 서브모듈까지 모두 복사하는 기능) 

```
git clone --recursive https://github.com/princeton-vl/DROID-SLAM.git
```

2. 새로운 anaconda를 제공된 yaml 파일로 생성.

```
conda env create -f environment.yaml
pip install evo --upgrade --no-binary evo
pip install gdown
```

3. setup.py install 진행.

```
python setup.py install
```

## Demos

*****

1. [droid.pth](https://drive.google.com/file/d/1PpqVt1H4maBa_GbPJp4NwxRsd9jk-elh/view?pli=1)를 다운받은 후
```
cd ~/droid/src/DROID-SLAM/
```
폴더에 넣기.

2. 주어진 script를 이용하여 sample video를 다운.

```
./tools/download_sample_data.sh
```

다운받은 sample 중에 하나레 대해 데모를 실행. 실헹 중에는 s키를 눌러 increase the filtering threshold를 하고, a키를 눌러 decrease the filtering threshold를 할 수 있음. 그리고 full resolution depth maps으로 3D-Reconstruction을 하려면 ```--reconstruction_path flag```를 사용

```
python demo.py --imagedir=data/abandonedfactory --calib=calib/tartan.txt --stride=2
```

```
python demo.py --imagedir=data/sfm_bench/rgb --calib=calib/eth.txt
```

```
python demo.py --imagedir=data/Barn --calib=calib/barn.txt --stride=1 --backend_nms=4
```

```
python demo.py --imagedir=data/mav0/cam0/data --calib=calib/euroc.txt --t0=150
```

```
python demo.py --imagedir=data/rgbd_dataset_freiburg3_cabinet/rgb --calib=calib/tum3.txt
```

## Training (학습은 안해봤어요...)

*****

## Execution Results in LAB

```python camera_topic.py```를 실행하고 rosbag을 통해 저장 후 .png 파일로 변환 후 실행.

아래의 사진은 demo를 실행하여 나온 결과.
