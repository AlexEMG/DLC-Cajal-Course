# FAQ and Common User Hurdles

<b>1) The system cannot find the path specified</b>
   - check your path and if you're running the terminal as administrator. As a good practice avoid using white spaces and dots in your folder and file names. Use `_`        or `-` instead

<b>2) Blury images</b>
   - If there is a lot of motion blur and you absolutely need to label blurry bodyparts, you should do it but try to be as consistent as possible

<b>3) 'OOM when allocating tensor with shape'</b>
   - You're trying to use more memory than is available on your GPU. Consider cropping unnecessary parts of the image, changing the `batch_size` or the `global_scale`
     in pose_cfg.yaml

<b>4) How do I restart the training from snapshot?</b>
   - To restart training from a snapshot you have to change the `init_weights` in your pose_cfg.yaml file to a path of your snapshot (without the extension!) e.g.: <br>
     `init_weights: "C:\path\project_path-2022-10-03\dlc-models\iteration-0\project_pathOct3-trainset95shuffle1\train\snapshot-100000"`

<b>5) Can I add new bodyparts to an existing project?</b>
   - Yes! You'll then have to label those new bodyparts onto all your images stored in labeled-data and create a new training dataset - remember to change iteration
     number in your config.yaml file

     Additional info on restarting training after adding new bodyparts: https://forum.image.sc/t/adding-new-labels/73675

<b>6) 'Error: Tracklets are empty'</b>
   - This error usually means that your model hasn't been trained well enough. You can run `deeplabcut.create_video_with_all_detections(config_path, video_path)` to
     see how it performs

<b>7) No suitable videos found in "yourpath" error</b>
   - Check if your path isn't pointing to a "_labeled" video. You should always point to the regular video that was used for analysis

<b>8) Video analysis stuck at a specific point/cannot start analysis</b>
   - Most likely this frame of the video was corrupted/the whole video has been corrupted. Re-encode the video following the amazing guide (:grin:) written by @KonradDanielewski
     [Video reencoding](https://deeplabcut.github.io/DeepLabCut/docs/recipes/io.html#tips-on-video-re-encoding-and-preprocessing)

<b>9) Missing data/jumping labels/occlusions</b>
   - low likelihood detections that result in missing data at visualization step are completely normal and to be expected. Essential step of pose estimation data            processing is filtering it and interpolating what you consider bad detections. For general purposes, DLC offer `deeplabcut.filterpredictions(config_path,              filtertype="arima"/"median"/"spline"`

<b>10) How to report issues and share snippets of code?</b>
   -  To report any issues, especially when sharing code or error tracebacks we use Markdown, a markup language used for formatting text. This allows us to easily           create code blocks, quote others, bold/italicize/underscore etc. You can follow this [short guide for Markdown](https://support.discord.com/hc/en-us/articles/210298617-Markdown-Text-101-Chat-Formatting-Bold-Italic-Underline-) from Discord or this [more elaborate](https://www.markdownguide.org/basic-syntax/) one to become a Markdown expert!


## If you can't find what you are looking 👀 for here, you should checkout the [community forum](https://forum.image.sc/tag/deeplabcut)!

## 🚨 Feel free to post your question there (on the User forum or Discord)!
