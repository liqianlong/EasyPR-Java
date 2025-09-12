## Features

Default `SVMCallback` implementation used by SVM training and `PlateJudge`.

Package: `org.easypr.core`

### Public API

- `Mat getHisteqFeatures(Mat image)`
- `Mat getHistogramFeatures(Mat image)`
- `Mat getSIFTFeatures(Mat image)`
- `Mat getHOGFeatures(Mat image)`

### Notes

- `getSIFTFeatures` and `getHOGFeatures` return null in this version.
