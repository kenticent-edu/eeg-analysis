# EEG Analysis

The signals that come from our brain are nosy, nonstationary, very complex, and with high dimensionality. Therefore, identifying the mental state requires specific signal processing techniques and machine learning tools once we acquire the signal.

## Workflow

To begin with, I didn’t have the complete information about the recording. Thus, I had to fill the gaps in the data as much as I could. For example, the device which was used during the recording was unknown - MNE, a Python library used in this work for analysis, complained the data was missing the information about the channels. Luckily, from the names of the last ones, I could deduce that a biosemi16 device was used and assigned each channel its location.

<img src="https://user-images.githubusercontent.com/56925230/147356509-03b59ffe-5993-4456-bc8f-619c013321b9.jpg" alt="Biosemi-16-Channel-Head-Cap-Layout" width="500"/>

![Screenshot 2021-12-24 154717](https://user-images.githubusercontent.com/56925230/147356965-01c08d0a-16e7-4191-9eb8-20249569a59a.png)

As you see on the plot, fixing the channels allowed MNE to beatifully create a color legend.

### The waves to analyse

![Screenshot 2021-12-24 154506](https://user-images.githubusercontent.com/56925230/147356854-37ed310e-7d0a-48d8-8ed8-709029b42cd5.png)

## ECG Artifacts

Speaking of the noise, as we know from our course, the ECG signal may have a bad impact on the performance of the EEG. Heart potentials over the scalp of the head can generate noise that must be removed from the signal after. According to this article [1], people with short and wide necks are the ones that suffer the most from this interference.

![Screenshot 2021-12-24 154344](https://user-images.githubusercontent.com/56925230/147356777-f1b94a28-6c09-48bd-b795-9c54c750a896.png)

We see on the last row of the plot, that there is almost no ECG noise, except for a small anomaly at the beginning when the recording just started, - the repairing must have been done already.

## Conclusions

![download](https://user-images.githubusercontent.com/56925230/147357088-88b47db7-0fd2-4dba-9923-1ea088d3b212.png)

During the EEG recording, an unstable alpha rhythm which had a frequency of 10.5-11 Hz and was amplified to 110 µV was dominating. Activation reaction was fuzzy: from the beginning of the EEG, the continuing functional loads provoked synchronized sharp discharges. After functional loads we can see discharges in form of sharp waves - both in the D hemisphere and later in the S hemisphere. They're also common in the fronto-precentral, temporal, and parieto occipital regions.

## Materials

[1] https://www.medscape.com/answers/1140247-177025/what-are-ecg-artifacts-on-eeg

[2] https://www.youtube.com/watch?v=B9ti7boa9jc

[3] https://arxiv.org/ftp/arxiv/papers/2010/2010.11667.pdf

[4] https://reader.elsevier.com/reader/sd/pii/S2352711021000753?token=4F6251103DBB953194A50E6909779313DC8A6296D68B775AAF6BC034D40E48BF0B1C9B45669583BD55A2C29A0C9E518D&originRegion=eu-west-1&originCreation=20211224130918

The EEG results used in this project were mine. A separate thanks to the cotributors of the libraries used for the analysis.

## Usage

```bash
git clone https://github.com/kenticent-edu/eeg-analysis
pip install -r requirements.txt
```
