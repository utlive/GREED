# ST-GREED: Space-Time Generalized EntropicDifferences for Frame Rate Dependent VideoQuality

**Pavan C. Madhusudana**, Neil Birkbeck, Yilin Wang, Balu Adsumilli and Alan C. Bovik

## Usage
The code has been tested with python 3.6. Please refer to [requirements.txt](requirements.txt) for details.
Additionally [FFmpeg](https://ffmpeg.org/) needs to be installed.

### Demo data download
For Linux and Mac users, the following commands to can be used to download sample videos for demo code. Videos with two different resolutions 1080p and 4K will be downloaded.
```
mkdir data
bash demo_data_download_1080p.sh
bash demo_data_download_4K.sh
```
Windows users can run the following commands
```
mkdir data
demo_data_download_1080p.bat
demo_data_download_4K.bat
```
Alternatively, the videos can be manually download from [HERE](https://utexas.box.com/s/13swqajkyhdui9kty2vwyithp8zcobmb)

### Running GREED
We provide two ways to run GREED. 
First method calculates GREED score based on the pretrained model. The model is trained on the entire [LIVE-YT-HFR database](https://live.ece.utexas.edu/research/LIVE_YT_HFR/LIVE_YT_HFR/index.html). We provide models trained on three temporal filters - Haar, Daubechies-2 and Biorthogonal-2.2. The choice of temporal filter can be provided as an argument while running the command. The following commands can be used to compute GREED features for 1080p and 4K resolution videos respectively.
```
python3 demo_score.py --ref_path data/books_crf_0_120fps.yuv --dist_path data/books_crf_28_30fps.yuv --ref_fps 120 --dist_fps 30 --height 1080 --width 1920 --bit_depth 8 --temp_filt bior22
python3 demo_score.py --ref_path data/Flips_crf_0_120fps.yuv --dist_path data/Flips_crf_48_30fps.yuv --ref_fps 120 --dist_fps 30 --height 2160 --width 3840 --bit_depth 10 --temp_filt bior22
```

Second way is to simply calculate GREED features. The following commands can be used to compute GREED features for 1080p and 4K resolution videos respectively.
```
python3 demo_feat.py --ref_path data/books_crf_0_120fps.yuv --dist_path data/books_crf_28_30fps.yuv --ref_fps 120 --dist_fps 30 --height 1080 --width 1920 --bit_depth 8 --temp_filt bior22
python3 demo_feat.py --ref_path data/Flips_crf_0_120fps.yuv --dist_path data/Flips_crf_48_30fps.yuv --ref_fps 120 --dist_fps 30 --height 2160 --width 3840 --bit_depth 10 --temp_filt bior22
```

## Contact
Please contact Pavan (pavan.madhusudana@gmail.com) if you have any questions, suggestions or corrections to the above implementation.
