<!DOCTYPE html>
<html>
<head>
<title>Sleap Note.md</title>
<meta http-equiv="Content-type" content="text/html;charset=UTF-8">

<style>
/* https://github.com/microsoft/vscode/blob/master/extensions/markdown-language-features/media/markdown.css */
/*---------------------------------------------------------------------------------------------
 *  Copyright (c) Microsoft Corporation. All rights reserved.
 *  Licensed under the MIT License. See License.txt in the project root for license information.
 *--------------------------------------------------------------------------------------------*/

body {
	font-family: var(--vscode-markdown-font-family, -apple-system, BlinkMacSystemFont, "Segoe WPC", "Segoe UI", "Ubuntu", "Droid Sans", sans-serif);
	font-size: var(--vscode-markdown-font-size, 14px);
	padding: 0 26px;
	line-height: var(--vscode-markdown-line-height, 22px);
	word-wrap: break-word;
}

#code-csp-warning {
	position: fixed;
	top: 0;
	right: 0;
	color: white;
	margin: 16px;
	text-align: center;
	font-size: 12px;
	font-family: sans-serif;
	background-color:#444444;
	cursor: pointer;
	padding: 6px;
	box-shadow: 1px 1px 1px rgba(0,0,0,.25);
}

#code-csp-warning:hover {
	text-decoration: none;
	background-color:#007acc;
	box-shadow: 2px 2px 2px rgba(0,0,0,.25);
}

body.scrollBeyondLastLine {
	margin-bottom: calc(100vh - 22px);
}

body.showEditorSelection .code-line {
	position: relative;
}

body.showEditorSelection .code-active-line:before,
body.showEditorSelection .code-line:hover:before {
	content: "";
	display: block;
	position: absolute;
	top: 0;
	left: -12px;
	height: 100%;
}

body.showEditorSelection li.code-active-line:before,
body.showEditorSelection li.code-line:hover:before {
	left: -30px;
}

.vscode-light.showEditorSelection .code-active-line:before {
	border-left: 3px solid rgba(0, 0, 0, 0.15);
}

.vscode-light.showEditorSelection .code-line:hover:before {
	border-left: 3px solid rgba(0, 0, 0, 0.40);
}

.vscode-light.showEditorSelection .code-line .code-line:hover:before {
	border-left: none;
}

.vscode-dark.showEditorSelection .code-active-line:before {
	border-left: 3px solid rgba(255, 255, 255, 0.4);
}

.vscode-dark.showEditorSelection .code-line:hover:before {
	border-left: 3px solid rgba(255, 255, 255, 0.60);
}

.vscode-dark.showEditorSelection .code-line .code-line:hover:before {
	border-left: none;
}

.vscode-high-contrast.showEditorSelection .code-active-line:before {
	border-left: 3px solid rgba(255, 160, 0, 0.7);
}

.vscode-high-contrast.showEditorSelection .code-line:hover:before {
	border-left: 3px solid rgba(255, 160, 0, 1);
}

.vscode-high-contrast.showEditorSelection .code-line .code-line:hover:before {
	border-left: none;
}

img {
	max-width: 100%;
	max-height: 100%;
}

a {
	text-decoration: none;
}

a:hover {
	text-decoration: underline;
}

a:focus,
input:focus,
select:focus,
textarea:focus {
	outline: 1px solid -webkit-focus-ring-color;
	outline-offset: -1px;
}

hr {
	border: 0;
	height: 2px;
	border-bottom: 2px solid;
}

h1 {
	padding-bottom: 0.3em;
	line-height: 1.2;
	border-bottom-width: 1px;
	border-bottom-style: solid;
}

h1, h2, h3 {
	font-weight: normal;
}

table {
	border-collapse: collapse;
}

table > thead > tr > th {
	text-align: left;
	border-bottom: 1px solid;
}

table > thead > tr > th,
table > thead > tr > td,
table > tbody > tr > th,
table > tbody > tr > td {
	padding: 5px 10px;
}

table > tbody > tr + tr > td {
	border-top: 1px solid;
}

blockquote {
	margin: 0 7px 0 5px;
	padding: 0 16px 0 10px;
	border-left-width: 5px;
	border-left-style: solid;
}

code {
	font-family: Menlo, Monaco, Consolas, "Droid Sans Mono", "Courier New", monospace, "Droid Sans Fallback";
	font-size: 1em;
	line-height: 1.357em;
}

body.wordWrap pre {
	white-space: pre-wrap;
}

pre:not(.hljs),
pre.hljs code > div {
	padding: 16px;
	border-radius: 3px;
	overflow: auto;
}

pre code {
	color: var(--vscode-editor-foreground);
	tab-size: 4;
}

/** Theming */

.vscode-light pre {
	background-color: rgba(220, 220, 220, 0.4);
}

.vscode-dark pre {
	background-color: rgba(10, 10, 10, 0.4);
}

.vscode-high-contrast pre {
	background-color: rgb(0, 0, 0);
}

.vscode-high-contrast h1 {
	border-color: rgb(0, 0, 0);
}

.vscode-light table > thead > tr > th {
	border-color: rgba(0, 0, 0, 0.69);
}

.vscode-dark table > thead > tr > th {
	border-color: rgba(255, 255, 255, 0.69);
}

.vscode-light h1,
.vscode-light hr,
.vscode-light table > tbody > tr + tr > td {
	border-color: rgba(0, 0, 0, 0.18);
}

.vscode-dark h1,
.vscode-dark hr,
.vscode-dark table > tbody > tr + tr > td {
	border-color: rgba(255, 255, 255, 0.18);
}

</style>

<style>
/* Tomorrow Theme */
/* http://jmblog.github.com/color-themes-for-google-code-highlightjs */
/* Original theme - https://github.com/chriskempson/tomorrow-theme */

/* Tomorrow Comment */
.hljs-comment,
.hljs-quote {
	color: #8e908c;
}

/* Tomorrow Red */
.hljs-variable,
.hljs-template-variable,
.hljs-tag,
.hljs-name,
.hljs-selector-id,
.hljs-selector-class,
.hljs-regexp,
.hljs-deletion {
	color: #c82829;
}

/* Tomorrow Orange */
.hljs-number,
.hljs-built_in,
.hljs-builtin-name,
.hljs-literal,
.hljs-type,
.hljs-params,
.hljs-meta,
.hljs-link {
	color: #f5871f;
}

/* Tomorrow Yellow */
.hljs-attribute {
	color: #eab700;
}

/* Tomorrow Green */
.hljs-string,
.hljs-symbol,
.hljs-bullet,
.hljs-addition {
	color: #718c00;
}

/* Tomorrow Blue */
.hljs-title,
.hljs-section {
	color: #4271ae;
}

/* Tomorrow Purple */
.hljs-keyword,
.hljs-selector-tag {
	color: #8959a8;
}

.hljs {
	display: block;
	overflow-x: auto;
	color: #4d4d4c;
	padding: 0.5em;
}

.hljs-emphasis {
	font-style: italic;
}

.hljs-strong {
	font-weight: bold;
}
</style>

<style>
/*
 * Markdown PDF CSS
 */

 body {
	font-family: -apple-system, BlinkMacSystemFont, "Segoe WPC", "Segoe UI", "Ubuntu", "Droid Sans", sans-serif, "Meiryo";
	padding: 0 12px;
}

pre {
	background-color: #f8f8f8;
	border: 1px solid #cccccc;
	border-radius: 3px;
	overflow-x: auto;
	white-space: pre-wrap;
	overflow-wrap: break-word;
}

pre:not(.hljs) {
	padding: 23px;
	line-height: 19px;
}

blockquote {
	background: rgba(127, 127, 127, 0.1);
	border-color: rgba(0, 122, 204, 0.5);
}

.emoji {
	height: 1.4em;
}

code {
	font-size: 14px;
	line-height: 19px;
}

/* for inline code */
:not(pre):not(.hljs) > code {
	color: #C9AE75; /* Change the old color so it seems less like an error */
	font-size: inherit;
}

/* Page Break : use <div class="page"/> to insert page break
-------------------------------------------------------- */
.page {
	page-break-after: always;
}

</style>

<script src="https://unpkg.com/mermaid/dist/mermaid.min.js"></script>
</head>
<body>
  <script>
    mermaid.initialize({
      startOnLoad: true,
      theme: document.body.classList.contains('vscode-dark') || document.body.classList.contains('vscode-high-contrast')
          ? 'dark'
          : 'default'
    });
  </script>
<h1 id="sleap-note">SLEAP Note</h1>
<p>SLEAP is an open source deep-learning based framework for multi-animal pose tracking. It can be used to track any type or number of animals and includes an advanced labeling/training GUI for active learning and proofreading. This note will show you how to get SLEAP running on the laptop and train all models using GUI.</p>
<p><img src="https://sleap.ai/docs/_static/sleap_movie.gif" alt="enter image description here"></p>
<ul>
<li>Written by Yi (Daniel) Lu</li>
<li>Yi_Lu@hms.harvard.edu</li>
</ul>
<h1 id="instructions-for-getting-started">Instructions for getting started</h1>
<h2 id="installation">Installation</h2>
<p>In brief:
<code>conda create -y -n sleap -c sleap -c nvidia -c conda-forge sleap=1.2.5</code></p>
<ul>
<li>This is the recommended installation method. Works on Windows and Linux.</li>
</ul>
<p>For more information, see <a href="https://sleap.ai/installation.html">the installation guide</a>.</p>
<h2 id="workflow">Workflow</h2>
<ul>
<li>Create a SLEAP project and add videos</li>
<li>Label frames using the GUI</li>
<li>Convert videos (optional)</li>
<li>Train the model</li>
<li>Run inference</li>
<li>Review and fix predictions</li>
<li>Track instances across frames</li>
<li>Export data for analysis</li>
</ul>
<h2 id="creating-a-new-project-and-adding-videos">Creating a new project and adding videos</h2>
<ul>
<li>Open your terminal</li>
<li>Activate your <code>conda</code> environment by typing <code>conda activate sleap</code>.</li>
<li>Enter <code>sleap-label</code> in the command line to launch the GUI</li>
</ul>
<p><img src="https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/start.png" alt="enter image description here"></p>
<p><img src="https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/2.png" alt="enter image description here"></p>
<p>Add a video by clicking the <B>“Add Video”</B> button in the <B>“Videos”</B> panel on the right side of the main window, or by dragging-and-dropping your video file from its folder into the SLEAP GUI.</p>
<p><img src="https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/3.png" alt="enter image description here"></p>
<p>SLEAP currently supports mp4, avi, and h5 files. For mp4 and avi files, you’ll be asked whether to import the video as grayscale.</p>
<p><img src="https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/4.png" alt="enter image description here"></p>
<p>Click <B>&quot;import&quot;</B>
A directory will be created in the location you specified, with the name  <code>projectname.slp</code>. It will initialize the file structure needed to run sleap.</p>
<h2 id="creating-a-skeleton">Creating a Skeleton</h2>
<p>Create a new skeleton using the <B>“Skeleton”</B> panel on the right side of the main window.</p>
<p>Use the <B>“New Node”</B> button to add a node (e.g.,snout,tail tip). Double-click the node name to rename it. Repeat until you have created all your nodes. You then need to connect the nodes with edges. Directly to the left of the “Add edge” button you’ll see two drop-down menus. Use these to select a pair of nodes, and then click <B>“Add Edge”</B>. Repeat until you’ve entered all the edges.</p>
<p>Click <B>“Save skeleton”</B> button to save the skeleton you just created for later use.</p>
<p><img src="https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/5.png" alt="enter image description here"></p>
<p>For more information, see <a href="https://sleap.ai/tutorials/new-project.html">Creating a project</a>.</p>
<h2 id="selecting-frames-to-label">Selecting frames to label</h2>
<p>You can either pick your own frames or let the system suggest a set of frames using the <B>“Labeling Suggestions”</B> panel. SLEAP can give you random or evenly-spaced samples, or it can try to give you distinctive groups of frames by taking the image features into account.</p>
<p>Choose the <B>&quot;method&quot;</B> and <B>&quot;sampling method&quot;</B> you would like to use, then click <B>“Generate Suggestions”</B>.</p>
<p>See <a href="https://sleap.ai/guides/gui.html#suggestion-methods">Labeling Suggestions</a> for more information about the suggestion methods.</p>
<h2 id="labeling-frames">Labeling frames</h2>
<p>Start by adding an <B>instance</B> of the skeleton to the current image by clicking the <B>“New Instance”</B> button in the Instances panel.</p>
<p>Move the points to their appropriate positions by dragging with the mouse. Use the mouse scroll-wheel to zoom.You can <B>move the entire instance</B> by holding down the <B>Alt</B> key which you then click on a node and drag the instance. You can <B>rotate the instance</B> by holding down the <B>Alt</B> key while you then click on a node and use the scroll-wheel.</p>
<p>For body parts that are not visible in the frame, <B>right-click</B> the node (or its name) to <B>toggle visibility</B>.</p>
<p><img src="https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/6.png" alt="enter image description here"></p>
<p>Save the project after labeling the selected frames.</p>
<h2 id="training">Training</h2>
<p>select “Run Training…” from the “Predict” menu, you will have three choices for models: <B>single animal</B>, <B>multi-animal top-down</B>, or <B>multi-animal bottom-up</B>. We find that bottom-up mode works better for our datasets. You can configure the hyperparameters for training your model in the <B>“Model Configuration”</B> tabs of the Training Dialog:</p>
<p><img src="https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/8.png" alt="enter image description here">
<img src="https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/9.png" alt="enter image description here"></p>
<p>For more information about the types of models you can train, see <a href="https://sleap.ai/guides/choosing-models.html#choosing-models">Configuring models</a>.</p>
<p>Once you hit the Run button, you should see a window which shows you a graph of training and validation loss for each model as it trains.</p>
<p><img src="https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/10.png" alt="enter image description here"></p>
<h2 id="initial-inference">Initial inference</h2>
<p>After each model is trained, inference will run and if everything is successful, you should get a dialog telling you how many frames got predictions. Suggested frames with predicted instances will be marked in the seekbar. So try clicking on the newly marked frames or use the <B>“Next Labeled Frame”</B> command in the “Go” menu to step through frames with labels.</p>
<p><img src="https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/14.png" alt="enter image description here"></p>
<h2 id="correcting-the-labeling">Correcting the labeling</h2>
<p>Predicted instances in the frame are displayed in grey with yellow nodes. To edit a prediction, you’ll need to replace it with an editable instance. Double-click the predicted instance and it will be converted into a regular instance.</p>
<p><i><B>Note: Predicted instances will not be used for future model training unless you correct the predictions in the GUI.</i></B></p>
<p>Once you’ve added and/or corrected more instances, you enter into a human-in-the-loop training cycle: train a new model, predict on more frames, correct those predictions. You will continue to iterate this process until you have achieved the desired pose labeling accuracy for your dataset.</p>
<h2 id="running-inference-and-tracking">Running inference and tracking</h2>
<p>When you’re satisfied with the predictions you’re getting, you can use your models to predict on more frames and track animal identities by selecting <B>“Run Inference…”</B> from the <B>“Predict”</B> menu.</p>
<p><img src="https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/17.png" alt="enter image description here"></p>
<p>The inference dialog allows you to choose a method to use for tracking instance identities but also has a place to select the tracker. By default the inference dialog will use the most recently train model, but if you want to choose another trained model, you can do this by using the dropdown menu on the tab for the relevant model type.</p>
<p><img src="https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/18.png" alt="enter image description here"></p>
<p>See <a href="https://sleap.ai/guides/proofreading.html#tracking-method-details">Tracking methods</a> for more information about the tracker methods and options.</p>
<h2 id="track-proofreading">Track proofreading</h2>
<p>Once you have predicted tracks, you’ll need to proofread these to ensure that the identities of instances across frames are correct. By default, predicted instances all appear in grey and yellow. Select “Color Predicted Instances” to show the tracks in color.</p>
<p>There are two main types of mistakes made by the tracking code: mistaken identities and lost identities. Here are some strategies that works for fixing lost and mistaken identities:</p>
<p>(1) select <B>“Transpose Instance Tracks”</B> in the <B>“Labels”</B> menu to swap the identities assigned to a pair of instances
(2) click <B>“Set Instance Track” submenu</B> in the <B>“Labels”</B> menu to assign an instance to a different (or new) track
(3) double-click the track name in the <B>“Instances”</B> panel to edit the track names in the instance you selected
(4) click <B>“Next Track Spawn Frame”</B> command in the <B>“Labels”</B> menu to find the next frame in which a new track is spawned and change back to the track from previous frames</p>
<p><img src="https://github.com/YiDanielLu/SLEAP-Note/raw/main/Image/16.png" alt="enter image description here"></p>
<h2 id="export-data-for-analysis">Export Data For Analysis</h2>
<p>The easiest way to work with the data from SLEAP is to export an HDF5 file by choosing “Export Analysis HDF5…” in the “File” menu.</p>
<p>You can read this file in MATLAB like this:</p>
<pre><code>occupancy_matrix = h5read('path/to/analysis.h5','/track_occupancy')
tracks_matrix = h5read('path/to/analysis.h5','/tracks')
</code></pre>
<p>You can read this file in Python like this:</p>
<pre><code>import h5py
with h5py.File('path/to/analysis.h5', 'r') as f:
  occupancy_matrix = f['track_occupancy'][:]
  tracks_matrix = f['tracks'][:]

print(occupancy_matrix.shape)
print(tracks_matrix.shape)
</code></pre>
<h2 id="export-predictions-to-csv-files">Export predictions to .csv files</h2>
<pre><code>from sleap import configuration, postprocessing, projects
import os
import pandas as pd
import random  

project_path = &quot;/path/to/project.slp&quot;
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
</code></pre>
<h2 id="acknowledgements">Acknowledgements</h2>
<p>I would like to extend a special thanks to <a href="https://www.oreficelab.org/">Orefice lab</a> members Yuki Dai and Kelsey Clausing for animal behavior data acquisition and productive discussion. I also want to thank Talmo Pereira for helpful guidance and suggestions. If you have any issues, or can't get SLEAP running, or just have questions, please raise an issue on <a href="https://github.com/talmolab/sleap/issues">Github</a>.</p>
<h2 id="references">References</h2>
<p dir="auto">SLEAP is the successor to the single-animal pose estimation software <a href="https://github.com/talmo/leap">LEAP</a> (<a href="https://www.nature.com/articles/s41592-018-0234-5" rel="nofollow">Pereira et al., Nature Methods, 2019</a>).</p>
<blockquote>
T.D. Pereira, N. Tabris, A. Matsliah, D. M. Turner, J. Li, S. Ravindranath, E. S. Papadoyannis, E. Normand, D. S. Deutsch, Z. Y. Wang, G. C. McKenzie-Smith, C. C. Mitelut, M. D. Castro, J. D’Uva, M. Kislin, D. H. Sanes, S. D. Kocher, S. S-H, A. L. Falkner, J. W. Shaevitz, and M. Murthy. <a href="https://www.nature.com/articles/s41592-022-01426-1" rel="nofollow">Sleap: A deep learning system for multi-animal pose tracking</a>. <em>Nature Methods</em>, 19(4), 2022</blockquote>

</body>
</html>
