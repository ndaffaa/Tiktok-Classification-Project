# TikTok Claims and Opinions Classification Project

## Project Overview

This project involves developing a machine learning model to classify TikTok videos as either claims or opinions. The primary goal is to assist human moderators by identifying videos that are more likely to violate TikTok's terms of service.

## Data Dictionary
|        Column name       |  Type |                                                                                                                             Description                                                                                                                             |
|:------------------------:|:-----:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| #                        | int   | TikTok assigned number for video with claim/opinion.                                                                                                                                                                                                                |
| claim_status             | obj   | Whether the published video has been identified as an “opinion” or a “claim.” In this dataset, an “opinion” refers to an individual’s or group’s personal belief or thought. A “claim” refers to information that is either unsourced or from an unverified source. |
| video_id                 | int   | Random identifying number assigned to video upon publication on TikTok.                                                                                                                                                                                             |
| video_duration_sec       | int   | How long the published video is measured in seconds.                                                                                                                                                                                                                |
| video_transcription_text | obj   | Transcribed text of the words spoken in the published video.                                                                                                                                                                                                        |
| verified_status          | obj   | Indicates the status of the TikTok user who published the video in terms of their verification, either “verified” or “not verified.”                                                                                                                                |
| author_ban_status        | obj   | Indicates the status of the TikTok user who published the video in terms of their permissions: “active,” “under scrutiny,” or “banned.”                                                                                                                             |
| video_view_count         | float | The total number of times the published video has been viewed.                                                                                                                                                                                                      |
| video_like_count         | float | The total number of times the published video has been liked by other users.                                                                                                                                                                                        |
| video_share_count        | float | The total number of times the published video has been shared by other users.                                                                                                                                                                                       |
| video_download_count     | float | The total number of times the published video has been downloaded by other users.                                                                                                                                                                                   |
| video_comment_count      | float | The total number of comments on the published video.                                                                                                                                                                                                                |

## PACE Framework
Throughout this project, we follow the PACE framework: Plan, Analyze, Construct, and Execute.

### Plan
**Business Need and Modeling Objective:** TikTok requires a machine learning model to differentiate between videos presenting claims and those presenting opinions. This assists human moderators in prioritizing videos that need review.

## Analyze
**Data Exploration:** We examine data, summary information, and descriptive statistics to understand the dataset.
**Class Balance:** The dataset is balanced, with 50.3% claims and 49.7% opinions.

## Construct
**Feature Engineering:** We extracted text length as a new feature and encoded categorical variables.

**Text Tokenization:** We used CountVectorizer to tokenize the video_transcription_text column by breaking each video's transcription into both 2-grams and 3-grams, and selected the 15 most frequently occurring tokens as features.

**Model Building:** We built and evaluated Random Forest and XGBoost models.

## Execute
**Model Evaluation:** Random Forest was selected as the champion model due to its better recall score.

**Final Model:** We used the champion model to predict on test data and visualized feature importances.

## Installation

To replicate this analysis, you'll need to install the following packages:

```
pip install pandas numpy matplotlib seaborn scikit-learn xgboost

```


## Usage

Load the dataset and run the Jupyter notebooks provided in the repository to follow the analysis and modeling steps.

# Conclusion

**Recommendation:** The model performed well and is recommended for use.

**Model Insights:** The model's predictions are primarily based on user engagement metrics.

**Future Improvements:** The current model performs nearly perfectly. However, additional features like the number of reports per video and total reports by each author could be beneficial.
