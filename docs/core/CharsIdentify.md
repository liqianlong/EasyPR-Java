## CharsIdentify

Identifies a single character image using a trained ANN model.

Package: `org.easypr.core`

### Public API

- `CharsIdentify()`
- `String charsIdentify(Mat input, Boolean isChinese, Boolean isSpeci)`
- `void loadModel(String path)` / `void setModelPath(String path)` / `String getModelPath()`

### Usage

```java
CharsIdentify ci = new CharsIdentify();
ci.setModelPath("res/model/ann.xml");
String ch = ci.charsIdentify(charMat, false, false);
```

### Notes

- `isChinese` should be true for the first character position on Chinese plates.
- `isSpeci` should be true for the city code letter slot (second position).
