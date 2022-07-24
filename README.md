# SLEAP Note

SLEAP is an open source deep-learning based framework for multi-animal pose tracking. It can be used to track any type or number of animals and includes an advanced labeling/training GUI for active learning and proofreading. This note will show you how to get SLEAP running on the laptop and train all models using GUI.

![enter image description here](https://sleap.ai/docs/_static/sleap_movie.gif)

 - Written by Yi (Daniel) Lu 
 - Yi_Lu@hms.harvard.edu

# Instructions for getting started
## Installation
In brief:
  `conda create -y -n sleap -c sleap -c nvidia -c conda-forge sleap=1.2.5`
-  This is the recommended installation method. Works on Windows and Linux.

For more information, see [the installation guide](https://sleap.ai/installation.html).

## Workflow
 -  Create a SLEAP project and add videos
 -  Label frames using the GUI
 -  Convert videos (optional)
 -  Train the model
 -  Run inference
 -  Review and fix predictions
 -  Track instances across frames
 -  Export data for analysis
## Creating a new project and adding videos
 -  Open your terminal
 -  Activate your `conda` environment by typing `conda activate sleap`.
 -  Enter `sleap-label` in the command line to launch the GUI
  
![enter image description here](https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/start.png)

![enter image description here](https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/2.png)

Add a video by clicking the <B>“Add Video”</B> button in the <B>“Videos”</B> panel on the right side of the main window, or by dragging-and-dropping your video file from its folder into the SLEAP GUI.

![enter image description here](https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/3.png)

SLEAP currently supports mp4, avi, and h5 files. For mp4 and avi files, you’ll be asked whether to import the video as grayscale.

![enter image description here](https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/4.png)

Click <B>"import"</B>
A directory will be created in the location you specified, with the name  `projectname.slp`. It will initialize the file structure needed to run sleap.

## Creating a Skeleton

Create a new skeleton using the <B>“Skeleton”</B> panel on the right side of the main window.

Use the <B>“New Node”</B> button to add a node (e.g.,snout,tail tip). Double-click the node name to rename it. Repeat until you have created all your nodes. You then need to connect the nodes with edges. Directly to the left of the “Add edge” button you’ll see two drop-down menus. Use these to select a pair of nodes, and then click <B>“Add Edge”</B>. Repeat until you’ve entered all the edges.

Click <B>“Save skeleton”</B> button to save the skeleton you just created for later use.

![enter image description here](https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/5.png)

For more information, see [Creating a project](https://sleap.ai/tutorials/new-project.html).

## Selecting frames to label

You can either pick your own frames or let the system suggest a set of frames using the <B>“Labeling Suggestions”</B> panel. SLEAP can give you random or evenly-spaced samples, or it can try to give you distinctive groups of frames by taking the image features into account.

Choose the <B>"method"</B> and <B>"sampling method"</B> you would like to use, then click <B>“Generate Suggestions”</B>.

See [Labeling Suggestions](https://sleap.ai/guides/gui.html#suggestion-methods) for more information about the suggestion methods.

## Labeling frames

Start by adding an <B>instance</B> of the skeleton to the current image by clicking the <B>“New Instance”</B> button in the Instances panel. 

Move the points to their appropriate positions by dragging with the mouse. Use the mouse scroll-wheel to zoom.You can <B>move the entire instance</B> by holding down the <B>Alt</B> key which you then click on a node and drag the instance. You can <B>rotate the instance</B> by holding down the <B>Alt</B> key while you then click on a node and use the scroll-wheel.

For body parts that are not visible in the frame, <B>right-click</B> the node (or its name) to <B>toggle visibility</B>. 

![enter image description here](https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/6.png)

Save the project after labeling the selected frames.

## Training  
select “Run Training…” from the “Predict” menu, you will have three choices for models: <B>single animal</B>, <B>multi-animal top-down</B>, or <B>multi-animal bottom-up</B>. We find that bottom-up mode works better for our datasets. You can configure the hyperparameters for training your model in the <B>“Model Configuration”</B> tabs of the Training Dialog:

![enter image description here](https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/8.png)
![enter image description here](https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/9.png)

For more information about the types of models you can train, see [Configuring models](https://sleap.ai/guides/choosing-models.html#choosing-models).

Once you hit the Run button, you should see a window which shows you a graph of training and validation loss for each model as it trains.

![enter image description here](https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/10.png)

## Initial inference
After each model is trained, inference will run and if everything is successful, you should get a dialog telling you how many frames got predictions. Suggested frames with predicted instances will be marked in the seekbar. So try clicking on the newly marked frames or use the <B>“Next Labeled Frame”</B> command in the “Go” menu to step through frames with labels.

![enter image description here](https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/14.png)

## Correcting the labeling
Predicted instances in the frame are displayed in grey with yellow nodes. To edit a prediction, you’ll need to replace it with an editable instance. Double-click the predicted instance and it will be converted into a regular instance.

<i><B>Note: Predicted instances will not be used for future model training unless you correct the predictions in the GUI.</i></B>

Once you’ve added and/or corrected more instances, you enter into a human-in-the-loop training cycle: train a new model, predict on more frames, correct those predictions. You will continue to iterate this process until you have achieved the desired pose labeling accuracy for your dataset. 

## Running inference and tracking
When you’re satisfied with the predictions you’re getting, you can use your models to predict on more frames and track animal identities by selecting <B>“Run Inference…”</B> from the <B>“Predict”</B> menu. 

![enter image description here](https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/17.png)

The inference dialog allows you to choose a method to use for tracking instance identities but also has a place to select the tracker. By default the inference dialog will use the most recently train model, but if you want to choose another trained model, you can do this by using the dropdown menu on the tab for the relevant model type.

![enter image description here](https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/18.png)

See [Tracking methods](https://sleap.ai/guides/proofreading.html#tracking-method-details) for more information about the tracker methods and options.

## Track proofreading

Once you have predicted tracks, you’ll need to proofread these to ensure that the identities of instances across frames are correct. By default, predicted instances all appear in grey and yellow. Select “Color Predicted Instances” to show the tracks in color.

There are two main types of mistakes made by the tracking code: mistaken identities and lost identities. Here are some strategies that works for fixing lost and mistaken identities:

(1) select <B>“Transpose Instance Tracks”</B> in the <B>“Labels”</B> menu to swap the identities assigned to a pair of instances
(2) click <B>“Set Instance Track” submenu</B> in the <B>“Labels”</B> menu to assign an instance to a different (or new) track
(3) double-click the track name in the <B>“Instances”</B> panel to edit the track names in the instance you selected
(4) click <B>“Next Track Spawn Frame”</B> command in the <B>“Labels”</B> menu to find the next frame in which a new track is spawned and change back to the track from previous frames

![enter image description here](https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/16.png)

## Export Data For Analysis
The easiest way to work with the data from SLEAP is to export an HDF5 file by choosing “Export Analysis HDF5…” in the “File” menu.

You can read this file in MATLAB like this:
    
    occupancy_matrix = h5read('path/to/analysis.h5','/track_occupancy')
    tracks_matrix = h5read('path/to/analysis.h5','/tracks')

You can read this file in Python like this:
    
    import h5py
    with h5py.File('path/to/analysis.h5', 'r') as f:
      occupancy_matrix = f['track_occupancy'][:]
      tracks_matrix = f['tracks'][:]

    print(occupancy_matrix.shape)
    print(tracks_matrix.shape)


## Export predictions to .csv files
 
    from sleap import configuration, postprocessing, projects
    import os
    import pandas as pd
    import random  
   
    project_path = "/path/to/project.slp"
    cfg = configuration.make_postprocessing_cfg(project_path=project_path) 
    postprocessing.postprocess_and_save(cfg)
    records = projects.get_records_from_datadir(os.path.join(project_path, 'DATA'))
    animal = random.choice(list(records.keys()))
    record = records[animal]
    
    # figure out the filename
    predictions_filename = os.path.join(os.path.dirname(record['rgb']), record['key'] + '_predictions.csv')
    assert  os.path.isfile(predictions_filename)
    # read csv  
    df = pd.read_csv(predictions_filename, index_col=0)
    # display outputs 
    print(df.head())


## Acknowledgements
I would like to extend a special thanks to [Orefice lab](https://www.oreficelab.org/) members Yuki Dai and Kelsey Clausing for animal behavior data acquisition and productive discussion. I also want to thank Talmo Pereira for helpful guidance and suggestions. If you have any issues, or can't get SLEAP running, or just have questions, please raise an issue on <a href="https://github.com/talmolab/sleap/issues">Github</a>.

## References

<p dir="auto">SLEAP is the successor to the single-animal pose estimation software <a href="https://github.com/talmo/leap">LEAP</a> (<a href="https://www.nature.com/articles/s41592-018-0234-5" rel="nofollow">Pereira et al., Nature Methods, 2019</a>).</p>

<blockquote>
T.D. Pereira, N. Tabris, A. Matsliah, D. M. Turner, J. Li, S. Ravindranath, E. S. Papadoyannis, E. Normand, D. S. Deutsch, Z. Y. Wang, G. C. McKenzie-Smith, C. C. Mitelut, M. D. Castro, J. D’Uva, M. Kislin, D. H. Sanes, S. D. Kocher, S. S-H, A. L. Falkner, J. W. Shaevitz, and M. Murthy. <a href="https://www.nature.com/articles/s41592-022-01426-1" rel="nofollow">Sleap: A deep learning system for multi-animal pose tracking</a>. <em>Nature Methods</em>, 19(4), 2022</blockquote>
