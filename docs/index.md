## EasyPR-Java Documentation

This documentation covers all public APIs, classes, and utilities in EasyPR-Java. It includes method signatures, behavioral notes, and runnable examples using JavaCV.

- Project: `org.easypr`
- Image/Model assets: under `res/`

## Quickstart

Recognize license plates from an image in one step using `PlateRecognize`:

```java
import static org.bytedeco.javacpp.opencv_highgui.imread;
import java.util.Vector;
import org.bytedeco.javacpp.opencv_core.Mat;
import org.easypr.core.PlateRecognize;

Mat src = imread("res/image/test_image/plate_recognize.jpg");
Vector<String> results = new Vector<>();

PlateRecognize pr = new PlateRecognize();
pr.setLifemode(true);      // tune for natural scene photos
pr.setDebug(false);        // disable debug image dumps

int code = pr.plateRecognize(src, results);
// code == 0 on success; results items look like "蓝牌:苏EUK722"
```

Or use detection and OCR separately:

```java
import static org.bytedeco.javacpp.opencv_highgui.imread;
import java.util.Vector;
import org.bytedeco.javacpp.opencv_core.Mat;
import org.easypr.core.PlateDetect;
import org.easypr.core.CharsRecognise;

Mat src = imread("res/image/test_image/plate_recognize.jpg");

PlateDetect detector = new PlateDetect();
detector.setPDLifemode(true);
Vector<Mat> plates = new Vector<>();
if (detector.plateDetect(src, plates) == 0) {
  CharsRecognise cr = new CharsRecognise();
  for (Mat plate : plates) {
    String text = cr.charsRecognise(plate);
  }
}
```

## Modules

- Core
  - [`PlateRecognize`](core/PlateRecognize.md)
  - [`PlateDetect`](core/PlateDetect.md)
  - [`PlateLocate`](core/PlateLocate.md)
  - [`CharsRecognise`](core/CharsRecognise.md)
  - [`CharsIdentify`](core/CharsIdentify.md)
  - [`CharsSegment`](core/CharsSegment.md)
  - [`PlateJudge`](core/PlateJudge.md)
  - [`CoreFunc`](core/CoreFunc.md)
  - [`SVMCallback`](core/SVMCallback.md)
  - [`Features`](core/Features.md)

- Training
  - [`SVMTrain`](../train/SVMTrain.md)
  - [`ANNTrain`](../train/ANNTrain.md)

- Utilities
  - [`Util`](../util/Util.md)
  - [`Convert`](../util/Convert.md)

## Conventions

- All examples assume Java 8+, JavaCV 0.11+, and assets in `res/`.
- Most APIs accept/return `org.bytedeco.javacpp.opencv_core.Mat` and Java `Vector`.
