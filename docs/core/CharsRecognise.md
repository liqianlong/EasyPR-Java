## CharsRecognise

Segments characters from a plate image and recognizes them. Also infers plate color.

Package: `org.easypr.core`

### Public API

- `void loadANN(String path)`
  - Loads an ANN model file (default is `res/model/ann.xml`).

- `String charsRecognise(Mat plate)`
  - Segments and recognizes plate characters. Returns plate text like `"苏EUK722"`.

- `void setCRDebug(boolean isDebug)` / `boolean getCRDebug()`
- `String getPlateType(Mat input)`
  - Returns Chinese label for color: `"蓝牌"`, `"黄牌"`, or `"未知"`.

- Character segmentation tuning:
  - `setLiuDingSize(int)`, `setColorThreshold(int)`
  - `setBluePercent(float)`, `getBluePercent()`
  - `setWhitePercent(float)`, `getWhitePercent()`

### Usage

```java
CharsRecognise cr = new CharsRecognise();
cr.setCRDebug(false);
String text = cr.charsRecognise(plateMat);
String color = cr.getPlateType(plateMat);
```

### Notes

- Internally uses `CharsSegment` and `CharsIdentify`.
