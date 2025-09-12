## ANNTrain

Builds and trains an ANN for character recognition.

Package: `org.easypr.train`

### Public API

- `Mat features(Mat in, int sizeData)`
- `void annTrain(Mat TrainData, Mat classes, int nNeruns)`
- `int saveTrainData()`
- `void saveModel(int predictSize, int neurons)`
- `int annMain()`

### Dataset

- Character images under `res/train/data/chars_recognise_ann/`
  - Latin digits/letters: `chars2`
  - Chinese province codes: `charsChinese`

### Workflow

1. Generate training feature matrices and labels (`saveTrainData`).
2. Train the ANN and write `res/train/ann.xml` (`saveModel`).
