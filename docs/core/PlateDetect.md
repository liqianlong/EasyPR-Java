## PlateDetect

Detects candidate license plate regions in an input image.

Package: `org.easypr.core`

### Public API

- `int plateDetect(Mat src, Vector<Mat> resultVec)`
  - On success, fills `resultVec` with cropped plate images.
  - Return codes: 0 success; -1 `src` empty; -2 no plate found.

- `void setPDLifemode(boolean pdLifemode)`
- `void setPDDebug(boolean pdDebug)` / `boolean getPDDebug()`

- Parameter passthrough to `PlateLocate`:
  - `setGaussianBlurSize(int)`, `getGaussianBlurSize()`
  - `setMorphSizeWidth(int)`, `getMorphSizeWidth()`
  - `setMorphSizeHeight(int)`, `getMorphSizeHeight()`
  - `setVerifyError(float)`, `getVerifyError()`
  - `setVerifyAspect(float)`, `getVerifyAspect()`
  - `setVerifyMin(int)`, `setVerifyMax(int)`
  - `setJudgeAngle(int)`

### Usage

```java
PlateDetect detector = new PlateDetect();
detector.setPDLifemode(true);
Vector<Mat> plates = new Vector<>();
int code = detector.plateDetect(src, plates);
```

### Notes

- If debug is enabled, intermediate images are written into `tmp/`.
- Uses `PlateLocate` then `PlateJudge` (SVM) to filter candidates.
