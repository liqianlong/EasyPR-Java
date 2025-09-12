## PlateLocate

Finds candidate plate regions via gradients, morphology, and contour filtering.

Package: `org.easypr.core`

### Public API

- `void setLifemode(boolean islifemode)`
  - Adjusts internal parameters for natural photos. Call before `plateLocate`.

- `Vector<Mat> plateLocate(Mat src)`
  - Returns cropped plate candidates.

- Parameter tuning
  - `setGaussianBlurSize(int)`, `getGaussianBlurSize()`
  - `setMorphSizeWidth(int)`, `getMorphSizeWidth()`
  - `setMorphSizeHeight(int)`, `getMorphSizeHeight()`
  - `setVerifyError(float)`, `getVerifyError()`
  - `setVerifyAspect(float)`, `getVerifyAspect()`
  - `setVerifyMin(int)`, `setVerifyMax(int)`
  - `setJudgeAngle(int)`
  - `setDebug(boolean)`, `getDebug()`

### Usage

```java
PlateLocate locator = new PlateLocate();
locator.setLifemode(true);
locator.setDebug(false);
Vector<Mat> candidates = locator.plateLocate(src);
```
