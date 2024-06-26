# Locamotiv: An interactive tool for evaluating multi-camera localization systems

## Introduction
**Locamotiv** is an interactive web app that simplifies the evaluation of multi-camera localization systems. Traditionally, evaluating these systems requires access to ground truth data, which can be expensive and time-consuming to acquire. Rather than relying on quantitative metrics, Locamotiv allowing users to assess the system's performance visually while providing system hyperparameters that can be adjusted in real time. Locamotiv is currently only configured to run on a single prepackaged dataset, but plans to allow users to upload their own data. 
## Setup Instructions

### Environment

### Sample Data
1. **Download** resources from one of the [StreetAware](https://www.mdpi.com/1424-8220/23/7/3710) [dataset](https://drive.google.com/drive/u/0/folders/1BPtiIF8gBOoZANAGkwDjJUYakpCUYHM1) camera setups [**here**](https://drive.google.com/file/d/15lB4lmCu5InYMu0mcgPaR6JsgY6NPFy3/view?usp=drive_link)

2. **Unzip** `data.zip` into the `flask_app/static/` folder. Resulting path should resemble `flask_app/static/data/chase_1/...`

## Using the tool

Start the application by running the command `flask run` within the `flask_app` folder

```(locamotiv) ../Locamotiv/flask_app> flask run```


![app_controls](https://github.com/jeckseveg/Locamotiv/blob/main/tool_layout.png)

### Control Description
In the app's main screen there are two sections: one dedicated for the video footage and one dedicated to the localization process. 

On the right, users can control playback for all 8 videos using the scrubber and play/pause button. Controls for playback speed are also included. Using the camera buttons, you can activate/disable individual cameras and toggle whether their detections should be included for localization.  

On the left, users can view translated ground points, their assigned communities, and their computed centroids. Individual points and centroids can be toggled on/off. Additionally users can change the minimum number of points required in a community before a centroid is registered. Higher values means detections from additional cameras is required while setting this value to 1 means that even individual points will register. 

### Tips


## Roadmap
- ~~Minimum viable product for submission~~
- Fix bugs, improve javascript video and python clustering performance, refactor
- Embed [homography tool](https://github.com/dbloisi/homography-computation/tree/master)
- Package stable version with tools for downloading and processing StreetAware videos
- Configure object detection network and allow for user upload data 

## Additional Notes

The bounding boxes used in the StreetAware dataset come from a pretrained HRNET model and should NOT be treated as ground truth.
