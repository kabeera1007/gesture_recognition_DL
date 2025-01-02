# Gesture Recognition Project

## Problem Statement
As a data scientist, At a home electronics company that manufactures state-of-the-art smart televisions, we want to develop a cool feature in the smart TV that can recognize five different gestures performed by the user. This feature will help users control the TV without using a remote.

---
# Dataset

[Link to dataset](https://drive.google.com/uc?id=1ehyrYBQ5rbQQe6yL4XbLWe3FMvuVUGiL)

## Observations

| Experiment Number | Model                          | Epochs | Train Accuracy | Validation Accuracy | Decision + Explanation                                                                                                                                               |
|--------------------|-------------------------------|--------|-----------------|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1                  | Conv3D                        | 20     | 0.2             | 0.41                | Adding more layers, as it’s clear that the model cannot learn.                                                                                                      |
| 2                  | Conv3D                        | 20     | 0.61            | 0.75                | While the accuracies have increased compared to the prior model, the number of parameters has gone up significantly. Reducing the number of parameters.             |
| 3                  | Conv3D                        | 20     | 0.97            | 0.83                | The model seems to be overfitting; reducing the number of parameters even further.                                                                                  |
| 4                  | Conv3D                        | 20     | 0.17            | 0.5                 | Reducing the number of parameters has had an adverse effect, and now the model is underfitting. Increasing the number of epochs to 40 and removing Dropout layers.  |
| 5                  | Conv3D                        | 40     | 1               | 0.91                | The model is clearly overfitting. Reducing the number of parameters and re-introducing Dropout layers.                                                              |
| 6                  | Conv3D                        | 40     | 0.99            | 1                   | The model is definitely overfitting. Increasing the number of Dropout layers and replacing the Flatten layer with GlobalAveragePooling3D.                           |
| 7                  | Conv3D                        | 40     | 0.99            | 0.91                | The model still seems to be overfitting. Trying a different architecture.                                                                                           |
| 8                  | TimeDistributed Conv2D + LSTM | 20     | 0.5             | 0.66                | The accuracy is sub-par, most likely due to the limited number of epochs. However, due to time restraints, switching to a different architecture and increasing epochs to 40. |
| 9                  | TimeDistributed Conv2D + GRU  | 40     | 0.96            | 0.81                | The model works well; however, the difference between the train and validation accuracy is significant. Adding some Dropout layers.                                 |
| 10                 | TimeDistributed Conv2D + GRU  | 40     | 0.86            | 0.58                | Adding Dropout layers has negatively impacted the model. Trying a different model architecture and increasing the number of epochs to 50.                           |
| 11                 | TimeDistributed Conv2D        | 50     | 0.99            | 0.91                | The model seems to be overfitting. Introducing Dropout layers to deal with overfitting.                                                                             |
| 12                 | TimeDistributed Conv2D        | 50     | 0.93            | 0.91                | The accuracy scores for the model are great. Selecting Model 12 as the final model.                                                                                 |

---

## Conclusion
We selected **Model 12 (TimeDistributed Conv2D)** as our final model because it achieved a training accuracy of **0.93** and a validation accuracy of **0.91**, which met our requirements.
