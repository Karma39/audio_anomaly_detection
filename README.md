# audio_anomaly_detection
## Digital forensics and biometrics project
The assigned task was an anomalies detection over some audio sample from the dataset: https://www.kaggle.com/datasets/pythonafroz/electrical-motor-anomaly-detection-from-sound-data

In particulare the sample used are the fan one, section 0

## First idea

The first approach was to build an autoencoder from scratch, encoding the full mel-spectrum for each file, but the result where poor.
Furthermore the number of parameter need was problematic

## Second idea

I have tried to see the mel-spectrum as an image and encoded it using a convolutional autoencoder and the result was worse then before.

## Third idea

I've tried to look for some feature rappresentation idea and the majority of project working on similar dataset using the autoencoder approach
were separating the mel-spectrum in different frame, where each frame contains a fixed number of contiuguos time frames.

This method coupled with a simple evaluation usign a threshold on the mse betwen original and reconstructed image, brought the recall to ~70%
but the precision droped to ~63% and the model was basically detecting ~50% of nominality as anomalies.

## Final modification

Under the suggestion of the proffessor i tried to reduce the frequency range from 0-8 KHZ to 1-5 KHz seeing the same recall rate but a much better
precision, in this case the anomalies where assigned as anomalies ~30% of the times, keeping a ~70% recall rate.
