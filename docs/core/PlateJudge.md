## PlateJudge

Classifies candidate regions as plate/non-plate using an SVM.

Package: `org.easypr.core`

### Public API

- `PlateJudge()`
- `void loadModel()` / `void loadModel(String path)`
- `int plateJudge(Mat inMat)`
- `int plateJudge(Vector<Mat> inVec, Vector<Mat> resultVec)`
- `void setModelPath(String path)` / `String getModelPath()`

### Usage

```java
PlateJudge judge = new PlateJudge();
int y = judge.plateJudge(candidateMat); // 1 for plate, 0 for non-plate
```
