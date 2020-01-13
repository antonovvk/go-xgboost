WORK IN PROGRESS... USE AT OWN RISK :-)

# go-xgboost

Go bindings for [XGBoost](https://github.com/dmlc/xgboost)

```go
import "github.com/antonovvk/go-xgboost"
```

## Usage

This library is meant for running predictions against a pre-trained XGBoost model.

```go

// Create predictor for a model and define the number of workers (and other settings)
predictor, _ := xgboost.NewPredictor(modelPath, runtime.NumCPU(), 0, 0, -1)

// Make prediction for one row
res, _ := predictor.Predict(xgboost.FloatSliceVector([]float32{1, 2, 3}))
fmt.Printf("Results: %+v\n", res)
// output: Results: [1.08002]

```

## License

[MIT](https://github.com/antonovvk/go-xgboost/blob/master/LICENSE)
