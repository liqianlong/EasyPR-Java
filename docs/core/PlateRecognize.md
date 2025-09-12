## PlateRecognize

High-level API that detects plates in an image and recognizes their color and text.

Package: `org.easypr.core`

### Public API

- `int plateRecognize(Mat src, Vector<String> licenseVec)`
  - Detects plates in `src`. For each plate, appends `"蓝牌:苏EUK722"`-style strings to `licenseVec`.
  - Returns 0 on success; negative values come from underlying detection failures.

- `void setLifemode(boolean lifemode)`
  - Tunes underlying `PlateDetect` parameters for natural scene photos when true.

- `void setDebug(boolean debug)`
  - Enables debug output in both detection and character recognition.

### Usage

```java
PlateRecognize pr = new PlateRecognize();
pr.setLifemode(true);
pr.setDebug(false);

Vector<String> out = new Vector<>();
int code = pr.plateRecognize(src, out);
```

### Notes

- Internally composes `PlateDetect` and `CharsRecognise`.
- Make sure model files exist under `res/model/`.
