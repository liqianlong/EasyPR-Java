## CoreFunc

Static helpers for color classification, histogram features, and visualization.

Package: `org.easypr.core`

### Enums

- `Color { UNKNOWN, BLUE, YELLOW }`
- `Direction { UNKNOWN, VERTICAL, HORIZONTAL }`

### Public API

- `static Mat colorMatch(Mat src, Color color, boolean adaptive_minsv)`
- `static boolean plateColorJudge(Mat src, Color color, boolean adaptive_minsv)`
- `static Color getPlateType(Mat src, boolean adaptive_minsv)`
- `static float[] projectedHistogram(Mat img, Direction direction)`
- `static Mat features(Mat in, int sizeData)`
- `static void showImage(String title, Mat src)`

### Usage

```java
CoreFunc.Color type = CoreFunc.getPlateType(plateMat, true);
float[] horiz = CoreFunc.projectedHistogram(binary, CoreFunc.Direction.HORIZONTAL);
```
