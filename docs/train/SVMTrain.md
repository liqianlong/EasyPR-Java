## SVMTrain

Prepares datasets and trains an SVM classifier for plate detection.

Package: `org.easypr.train`

### Public API

- Constructors: `SVMTrain()`, `SVMTrain(SVMCallback callback)`
- `void learn2HasPlate()` / `void learn2HasPlate(float bound)`
- `void learn2NoPlate()` / `void learn2NoPlate(float bound)`
- `void getHasPlateTrain(Mat trainingImages, Vector<Integer> trainingLabels)`
- `void getNoPlateTrain(Mat trainingImages, Vector<Integer> trainingLabels)`
- `void getHasPlateTest(MatVector testingImages, Vector<Integer> testingLabels)`
- `void getNoPlateTest(MatVector testingImages, Vector<Integer> testingLabels)`
- `void getAccuracy(Mat testingclasses_predict, Mat testingclasses_real)`
- `int svmTrain(boolean dividePrepared, boolean trainPrepared)`

### Workflow

1. Split raw images in `res/train/data/plate_detect_svm/learn/` into `train/` and `test/`.
2. Extract features with `SVMCallback` (default `Features`).
3. Train or load an SVM model and evaluate.
