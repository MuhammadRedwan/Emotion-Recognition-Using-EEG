# Emotion-Recognition-Using-EEG

## Disclousre

This code uses [DEAP dataset](https://www.eecs.qmul.ac.uk/mmv/datasets/deap/) [1], specifically data_preprocessed_python.zip file. 

the zip file contains 32 .dat (python) files, one per participant.

Each participant file contains two arrays:

| Array name | Array shape | Array contents |
|------------|--------------|----------------|
| data       | 40 x 40 x 8064 | video/trial x channel x data |
| labels      | 40 x 4        | video/trial x label (valence, arousal, dominance, liking) |


- The data was downsampled to 128Hz.
- A bandpass frequency filter from 4.0-45.0Hz was applied.
- The data was averaged to the common reference.
- The EEG channels were reordered so that they all follow [the Geneva order](https://www.eecs.qmul.ac.uk/mmv/datasets/deap/readme.html).
- The data was segmented into 60 second trials and a 3 second pre-trial baseline removed.
- The trials were reordered from presentation order to video (Experiment_id) order.

**Due to Github's policies, which do not allow file uploads of more than 100MB, a copy of the data used can be downloaded via [this link](https://drive.google.com/file/d/1cBV6at_F2mPWIXKnRT1AQKSySZX7bnT3/view?usp=drive_link).**

## Literature Review

[2] and [3] are the main sources the literature review is based upon. Both disscussed the state-of-art methods for Emotion Recongiiton usign EEG signals, as well as, associated challanges ,and pontetial applications.

The presented methods on those papers suggested a strong correlation between the approaches which combine the spatial and temporal components of EEG signals and the metrices of accuracy, precision, etc. Only the methods which utilized DEAP dataset were collected and analyzed. As presented on the following table:

| Method                                       | Accuracy          |
|---------------------------------------------|-------------------|
| **CNN-5 with PLV matrices**             | 99.73% (4-class), 99.11% (2-class), 99.74% (2-class arousal)  |
| **CNN-LSTM** | 97.41% (valence), 97.39% (arousal), 97.68% (dominance)  |
| **ECNN-C**               | 98.35% (valence), 98.51% (arousal), 98.55% (dominance) |
| **Multi-column CNN**         | 90.01% (valence), 90.65% (arousal)   |
| **LSTM + Attention + CNN** | 90.1% (2-class valence), 88.3% (2-class arousal), 86.95% (3-class valence), 84.1% (3-class arousal)|
| **2D-CNN with soft attention + ConvLSTM**   | 87.84% (valence), 87.69% (arousal)   |
| **Hierarchical LSTM**   | 85.9%   |
| **LSTM**      | 81.1% (valence), 74.38% (arousal)  |

Exisiting challanges comprises of associated computational cost, and the nature of EEG which are not identical accross individuals for a specific reaction (e.g. arousal, valence, etc), thus introducing the over-fitting.

## Suggested Methods

Currently, three approaches are considered which aim to reduce the computational cost while mainting a reliable model in terms of accuracy to fit within a specific applications such as embedded real-time emotion recognition which utilize low-energy low-specs components. The suggested approaches are as follow:

-
-
-

## References

[1] "[DEAP: A Database for Emotion Analysis using Physiological Signals (PDF)](https://www.eecs.qmul.ac.uk/mmv/datasets/deap/doc/tac_special_issue_2011.pdf)", S. Koelstra, C. M\ uehl, M. Soleymani, J.-S. Lee, A. Yazdani, T. Ebrahimi, T. Pun, A. Nijholt, I. Patras, EEE Transactions on Affective Computing, vol. 3, no. 1, pp. 18-31, 2012

[2] Jafari, M., Shoeibi, A., Khodatars, M., Bagherzadeh, S., Shalbaf, A., García, D. L., Gorriz, J. M., & Acharya, U. R. (2023). Emotion recognition in EEG signals using deep learning methods: A review. Computers in Biology and Medicine, 165, 107450.

[3] Roy, Y., Banville, H., Albuquerque, I., Gramfort, A., Falk, T. H., & Faubert, J. (2019, January 16). Deep learning-based electroencephalography analysis: a systematic review. arXiv.org.
