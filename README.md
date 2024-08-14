# Enhancing EEG-based BCI Classification with Multi-Scale CNNs: A Comparative Analysis

## Overview
This project explores the impact of Multi-Scale Convolutional Neural Networks (CNNs) on the classification of EEG signals in Brain-Computer Interface (BCI) systems. By comparing the performance of two models, EEGNet and MSTANN, the study demonstrates how richer temporal feature extractions can enhance CNN models' accuracy in classifying EEG signals.

## Models
### EEGNet
EEGNet is a specialized CNN model designed for EEG signal classification. It consists of a temporal convolutional layer followed by depthwise and separable convolutions that handle spatial filtering. The final fully connected layer integrates the features for classification. The architecture is optimized for efficiency, making it suitable for real-time BCI applications.

![EEGNet Architecture](https://drive.google.com/uc?export=view&id=1mWfOeVIOi5nSba6tOWRaVlQioJ6cmGvC)

### MSTANN
The Multi-Scale Temporal Attention Neural Network (MSTANN) is an advanced model that enhances EEGNet by incorporating multi-scale temporal feature extraction. The model uses three 1D convolutional layers with kernel sizes of 3, 11, and 19 to capture different temporal patterns in the EEG data. These feature maps are then concatenated and further processed for classification, making MSTANN adept at capturing nuanced temporal features.

![MSTANN Architecture](https://drive.google.com/uc?export=view&id=15vBuAUMYisOPryKNCydT_-pqWAziJXhR)

## Dataset
The EEG data utilized in this project is sourced from the [BCI Competition IV 2a](http://www.bbci.de/competition/iv/#dataset2a) dataset. Key characteristics of the dataset include:

- **Participants**: 9
- **Electrodes**: 22 Ag/AgCl
- **Sampling Frequency**: 250 Hz
- **Epoched Data**: [2, 6] seconds
- **Frequency Range**: 0.5 - 100 Hz
- **Band-Pass Filtered**: 4 - 40 Hz (Using IIR Filter)
- **Classes**: Left Hand, Right Hand, Foot, Tongue

### List of Events
The following events are annotated in the dataset:

- **'1023'**: Rejected trial
- **'1072'**: Eye movements
- **'276'**: Idling EEG (eyes open)
- **'277'**: Idling EEG (eyes closed)
- **'32766'**: Start of a new run
- **'768'**: Start of a trial
- **'769'**: Cue onset **Left** (class 1)
- **'770'**: Cue onset **Right** (class 2)
- **'771'**: Cue onset **Foot** (class 3)
- **'772'**: Cue onset **Tongue** (class 4)

Events 769, 770, 771, and 772 were selected for classification.

## Training Setup
The models were trained using the following parameters:

- **Optimizer**: Adam
- **Batch Size**: 64
- **Epochs**: 500
- **Learning Rate**: 0.001
- **Loss Function**: Cross Entropy

## Conclusion
This project highlights the potential of multi-scale CNNs in enhancing EEG-based BCI classification. By comparing EEGNet and MSTANN, it demonstrates how richer temporal feature extraction can improve model performance in EEG signal classification.

## References
If you use this code or the models in your work, please cite the original papers of the orignal models:

- [Lawhern, V. J., Solon, A. J., Waytowich, N. R., Gordon, S. M., Hung, C. P., & Lance, B. J. (2018). EEGNet: a compact convolutional neural network for EEG-based brain–computer interfaces. Journal of neural engineering, 15(5), 056013.](https://iopscience.iop.org/article/10.1088/1741-2552/aace8c)

- [Wu, R., Jin, J., Daly, I., Wang, X., & Cichocki, A. (2023). Classification of motor imagery based on multi-scale feature extraction and the channeltemporal attention module. IEEE Transactions on Neural Systems and Rehabilitation Engineering.](https://ieeexplore.ieee.org/iel7/7333/4359219/10180110.pdf)

If you used the dataset in your work, please cite the original paper of it:

[Brunner, C., Leeb, R., Müller-Putz, G., Schlögl, A., & Pfurtscheller, G. (2008). BCI Competition 2008–Graz data set A. Institute for knowledge discovery (laboratory of brain-computer interfaces), Graz University of Technology, 16, 1-6.](https://lampz.tugraz.at/~bci/database/001-2014/description.pdf)
