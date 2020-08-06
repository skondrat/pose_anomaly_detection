# PoseAnomalyDetection

## install requirements:

```shell script
    pip install -r requirements.txt
```

## Install AlphaPose

### CPU usage installation:

https://github.com/nickgrealy/AlphaPose/tree/pytorch-cpu

### Change some AlphaPose code:
https://github.com/MVIG-SJTU/AlphaPose/issues/335#issuecomment-508972808

## preprocess 
run preprocessing/convert_to_frames.py 
Has two options (ffmpeg / cv2)

## pose tracking 
run AlphaPose/demo.py
```shell script
python3 demo.py --indir ${img_directory} --outdir examples/res 
```
## Anomaly detection

run anomaly_detection/find_outliers.py

params:
1) features df
2) drop_scores: bool. Drop each coordinate confidence scores.
3) param flatten_rows: bool. Create additional columns with data for multiple frames
4) param log_cols: bool. Logarithm features.
5) param drop_corr: bool. Drop high correlated features.
6) param plotting: bool. Plot results .

## Future improvements

1) Normalize human pose joints position making invatiant to position on frame
2) Analyze joins which can't introduce outliers and remove them (e.g. head)

