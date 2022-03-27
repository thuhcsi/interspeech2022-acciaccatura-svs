---
layout: default
---

<!-- Text can be **bold**, _italic_, or ~~strikethrough~~. -->

_Weiya You, Shaohuan Zhou, Yuren You, Jiankun Hu, Zhiyong Wu, Shiyin Kang_





# ABSTRACT

The acciaccatura is a kind of ornaments which is very commonly used in playing or singing. The flexible use of the acciaccatura can make the singing more expressive. However, as far as we observe, there is no research on the analysis of the acciaccatura and its prediction. In this paper, we analyze a Chinese music score dataset with acciaccatura annotations. Base on the analysis results, we obtain the factors affecting the acciaccatura: duration and pitch, and use them as features, after being encoded by embedding, they are feed into BiLSTM-CRF models which have good performance in named entity recognition (NER) to predict the acciaccatura position and pitch. Finally, the ABX tests is used to verify that the music score containing the model's predicted acciaccatura allowed the singing voice synthesis model to synthesize a more beautiful song.

# ACCIACCATURA PREDICTION

Our goal is to predict the acciaccatura position and acciaccatura pitch from the original score. Finally, the acciaccatura score is used to synthesize a more beautiful song.

## PREDICTION IS THE SAME AS LABELING

The percentage of sentences predicted and labeled exactly the same is 69.61%.

| No        | Labeled music score        | Audio | Without acciaccatura        | Audio |
|:----------|:---------------------------|:------|:----------------------------|:------|
| 1         | ![059004_label](assets/images/059004_label.jpg) | <audio controls><source src="assets/audios/059004_label.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![059004_no](assets/images/059004_no.jpg) | <audio controls><source src="assets/audios/059004_no.wav" type="audio/wav">Your browser does not support the audio element.</audio>  |
| 2         | ![059008_label](assets/images/059008_label.jpg) | <audio controls><source src="assets/audios/059008_label.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![059008_no](assets/images/059008_no.jpg) | <audio controls><source src="assets/audios/059008_no.wav" type="audio/wav">Your browser does not support the audio element.</audio>  |
| 3         | ![066002_label](assets/images/066002_label.jpg) | <audio controls><source src="assets/audios/066002_label.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![066002_no](assets/images/066002_no.jpg) | <audio controls><source src="assets/audios/066002_no.wav" type="audio/wav">Your browser does not support the audio element.</audio>  |

## LESS PREDICTION THAN LABELING

The percentage of sentences with only partial acciaccatura labels missing was 16.99%.

| No        | Labeled music score        | Audio | Without acciaccatura        | Audio | Predicted music score        | Audio |
|:----------|:---------------------------|:------|:----------------------------|:------|:-----------------------------|:------|
| 1         | ![018007_label](assets/images/018007_label.jpg) | <audio controls><source src="assets/audios/018007_label.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![018007_no](assets/images/018007_no.jpg) | <audio controls><source src="assets/audios/018007_no.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![018007_pred](assets/images/018007_pred.jpg) | <audio controls><source src="assets/audios/018007_pred.wav" type="audio/wav">Your browser does not support the audio element.</audio>  |
| 2         | ![103011_label](assets/images/103011_label.jpg) | <audio controls><source src="assets/audios/103011_label.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![103011_no](assets/images/103011_no.jpg) | <audio controls><source src="assets/audios/103011_no.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![103011_pred](assets/images/103011_pred.jpg) | <audio controls><source src="assets/audios/103011_pred.wav" type="audio/wav">Your browser does not support the audio element.</audio>  |
| 3         | ![241037_label](assets/images/241037_label.jpg) | <audio controls><source src="assets/audios/241037_label.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![241037_no](assets/images/241037_no.jpg) | <audio controls><source src="assets/audios/241037_no.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![241037_pred](assets/images/241037_pred.jpg) | <audio controls><source src="assets/audios/241037_pred.wav" type="audio/wav">Your browser does not support the audio element.</audio>  |

## MORE PREDICTION THAN LABELING

The percentage of sentences with more partial acciaccatura labels was 10.01%.

| No        | Labeled music score        | Audio | Without acciaccatura        | Audio | Predicted music score        | Audio |
|:----------|:---------------------------|:------|:----------------------------|:------|:-----------------------------|:------|
| 1         | ![029006_label](assets/images/029006_label.jpg) | <audio controls><source src="assets/audios/029006_label.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![029006_no](assets/images/029006_no.jpg) | <audio controls><source src="assets/audios/029006_no.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![029006_pred](assets/images/029006_pred.jpg) | <audio controls><source src="assets/audios/029006_pred.wav" type="audio/wav">Your browser does not support the audio element.</audio>  |
| 2         | ![052019_label](assets/images/052019_label.jpg) | <audio controls><source src="assets/audios/052019_label.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![052019_no](assets/images/052019_no.jpg) | <audio controls><source src="assets/audios/052019_no.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![052019_pred](assets/images/052019_pred.jpg) | <audio controls><source src="assets/audios/052019_pred.wav" type="audio/wav">Your browser does not support the audio element.</audio>  |
| 3         | ![439000_label](assets/images/439000_label.jpg) | <audio controls><source src="assets/audios/439000_label.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![439000_no](assets/images/439000_no.jpg) | <audio controls><source src="assets/audios/439000_no.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![439000_pred](assets/images/439000_pred.jpg) | <audio controls><source src="assets/audios/439000_pred.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | 

## SAME NUMBER, PREDICTION OFFSET

The percentage of predicted sentences with the same number of acciaccatura but with acciaccatura position shifts was 2.42%.

| No        | Labeled music score        | Audio | Without acciaccatura        | Audio | Predicted music score        | Audio |
|:----------|:---------------------------|:------|:----------------------------|:------|:-----------------------------|:------|
| 1         | ![076024_label](assets/images/076024_label.jpg) | <audio controls><source src="assets/audios/076024_label.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![076024_no](assets/images/076024_no.jpg) | <audio controls><source src="assets/audios/076024_no.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![076024_pred](assets/images/076024_pred.jpg) | <audio controls><source src="assets/audios/076024_pred.wav" type="audio/wav">Your browser does not support the audio element.</audio>  |
| 2         | ![130040_label](assets/images/130040_label.jpg) | <audio controls><source src="assets/audios/130040_label.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![130040_no](assets/images/130040_no.jpg) | <audio controls><source src="assets/audios/130040_no.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![130040_pred](assets/images/130040_pred.jpg) | <audio controls><source src="assets/audios/130040_pred.wav" type="audio/wav">Your browser does not support the audio element.</audio>  |
| 3         | ![244042_label](assets/images/244042_label.jpg) | <audio controls><source src="assets/audios/244042_label.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![244042_no](assets/images/244042_no.jpg) | <audio controls><source src="assets/audios/244042_no.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![244042_pred](assets/images/244042_pred.jpg) | <audio controls><source src="assets/audios/244042_pred.wav" type="audio/wav">Your browser does not support the audio element.</audio>  |

## OTHER SITUATIONS

The percentage of sentences with other cases was 0.957%.

| No        | Labeled music score        | Audio | Without acciaccatura        | Audio | Predicted music score        | Audio |
|:----------|:---------------------------|:------|:----------------------------|:------|:-----------------------------|:------|
| 1         | ![003000_label](assets/images/003000_label.jpg) | <audio controls><source src="assets/audios/003000_label.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![003000_no](assets/images/003000_no.jpg) | <audio controls><source src="assets/audios/003000_no.wav" type="audio/wav">Your browser does not support the audio element.</audio>  | ![003000_pred](assets/images/003000_pred.jpg) | <audio controls><source src="assets/audios/003000_pred.wav" type="audio/wav">Your browser does not support the audio element.</audio>  |
