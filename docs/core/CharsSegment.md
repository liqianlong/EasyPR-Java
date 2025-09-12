## CharsSegment

Segments individual characters from a plate image.

Package: `org.easypr.core`

### Public API

- `int charsSegment(Mat input, Vector<Mat> resultVec)`
  - Returns number of characters on success (> 0), or -3 on failure.

- Debug and tuning
  - `void setLiuDingSize(int)`
  - `void setColorThreshold(int)`
  - `void setBluePercent(float)` / `float getBluePercent()`
  - `void setWhitePercent(float)` / `float getWhitePercent()`
  - `boolean getDebug()` / `void setDebug(boolean)`

### Usage

```java
CharsSegment seg = new CharsSegment();
seg.setDebug(false);
Vector<Mat> chars = new Vector<>();
int n = seg.charsSegment(plateMat, chars);
```
