# FAQ and common user hurdles

1) The system cannot find the path specified
   - check your path and if you're running the terminal as administrator. As a good practice avoid using white spaces and dots in your folder and file names. Use `_` or `-` instead
2) Blury images
   - If there is a lot of motion blur and you absolutely need to label blurry bodyparts, you should do it but try to be as consistent as possible
3) 'OOM when allocating tensor with shape'
   - You're trying to use more memory than is available on your GPU. Consider cropping unnecessary parts of the image, changing the `batch_size` or the `global_scale`
     in pose_cfg.yaml
4) How do I restart the training from snapshot?
   - To restart training from a snapshot you have to change the `init_weights` in your pose_cfg.yaml file to a path of your snapshot (without the extension!) e.g.:
   `init_weights: "C:\lizards\nesocijalna-gojak-2022-10-03\dlc-models\iteration-0\nesocijalnaOct3-trainset95shuffle1\train\snapshot-100000"
5) Can I add new bodyparts to existing project?
   - Yes! You'll then have to label those new bodyparts onto all your images stored in labeled-data and create a new training dataset - remember to change iteration
     number in your config.yaml file
6) 'Error: Tracklets are empty'
   - This error usually means that your model hasn't been trained well enough. You can run `deeplabcut.create_video_with_all_detections(config_path, video_path)` to
     see how it performs
7) No suitable videos found in "yourpath" error
   - Check if your path isn't pointing to a "_labeled" video. You should always point to the regular video that was used for analysis
8) Video analysis stuck at a specific point/cannot start analysis
   - Most likely this frame of the video was corrupted/the whole video has been corrupted. Re-encode the video following the amazing guide (:grin:) written by @KonradDanielewski
     [Video reencoding](https://deeplabcut.github.io/DeepLabCut/docs/recipes/io.html#tips-on-video-re-encoding-and-preprocessing)
9) Missing data/jumping labels/occlusions
   - low likelihood detections that result in missing data at visualization step are completely normal and to be expected. Essential step of pose estimation data processing
     is filtering it and interpolating what you consider bad detections. For general purposes, DLC offer `deeplabcut.filterpredictions(config_path, filtertype="arima"/"median"/"spline"`

## If your issue isn't listed here you should checkout the [community forum](https://forum.image.sc/tag/deeplabcut) and feel free to post your question there
