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

**Due to Github's policies, which not allow file uploads of more than 100MB, a copy of the data used can be downloaded via [this link]().**

## Literature Review



## Suggested Methods


## References

[1] "[DEAP: A Database for Emotion Analysis using Physiological Signals (PDF)](https://www.eecs.qmul.ac.uk/mmv/datasets/deap/doc/tac_special_issue_2011.pdf)", S. Koelstra, C. M\ uehl, M. Soleymani, J.-S. Lee, A. Yazdani, T. Ebrahimi, T. Pun, A. Nijholt, I. Patras, EEE Transactions on Affective Computing, vol. 3, no. 1, pp. 18-31, 2012

[2] Jafari, M., Shoeibi, A., Khodatars, M., Bagherzadeh, S., Shalbaf, A., García, D. L., Gorriz, J. M., & Acharya, U. R. (2023). Emotion recognition in EEG signals using deep learning methods: A review. Computers in Biology and Medicine, 165, 107450.

[3] Roy, Y., Banville, H., Albuquerque, I., Gramfort, A., Falk, T. H., & Faubert, J. (2019, January 16). Deep learning-based electroencephalography analysis: a systematic review. arXiv.org.
