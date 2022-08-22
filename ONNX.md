# ONNX

[`onnxruntime`](http://onnxruntime.ai/docs)

## Pre-trained Models Examples

- [`ONNX-Zoo`](https://github.com/onnx/models)

## Supported operators, _aka_ `opset_version` e.g., `BatchNormalization`

Typical exporter can determine the `opset` (typical default to 13) [now 17 2022-08-21]

- [`ONNX` operators schemas](https://github.com/onnx/onnx/blob/main/docs/Operators.md)

### `PyTorch` -> `onnx`

- Integral part of repo
- Check the [`Symbolic_helper`](https:://pytorch.org/onnx/symbolic_helper.py) and

### `Tensorflow` or `keras` -> `onnx`

- Install `tf2onnx` `pip install tf2onnx`
- Run directly from program or use `the` `cli`
  - `python -m tf2onnx.convert --saved-model <tensorflow-model-path> --output <model.onnx>`
- or Use `onnx.transformers` to convert checkpoints

### `sklearn` -> `onnx`

- Install `sk2onnx` `pip install sk2onnx`

## Executing `ONNX` file with  `onnxruntime`

- Install `onnxruntime`

`pip install onnxruntime`

```python
import onnxruntime as rt

sess = rt.InferenceSession(<File.onnx>)
input_name = sess.get_inputs()[0].name
label_name = sess.get_outputs()[0].name
pred_onnx = sess.run([label_name], {input_name: X.astype(numpy.float32)})[0]
```

### Visualization

- [`Netron`](https://github.com/lutzroeder/Netron)
- [`Visual DL`](https://github.com/PaddlePaddle/VisualDL)
- [`Zetan`]
