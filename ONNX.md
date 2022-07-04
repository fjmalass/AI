# ONNX

[`onnxruntime`](http://onnxruntime.ai/docs)

# Supported operators, aka `opset_version` (e.g., BatchNormalization)

Typical exporter can determine the `opset` (typical default to 9)

- [onnx operators schemas] (https://github.com/onnx/onnx/blob/main/docs/Operators.md)

## `PyTorch` -> `onnx`

- Integral part of repo
- Check the [`Symbolic_helper`](https:://pytorch.org/onnx/symbolic_helper.py) and

## `Tensorflow` or `keras` -> `onnx`

- Install `tf2onnx` `pip install tf2onnx`
- Run directly from program or use `the` `cli`
- or Use onnx.transformers to convert checkpoints

## `sklearn` -> `onnx`
- Install `sk2onnx` `pip install sk2onnx`


# Executing `onnx` file with  `onnxruntime`
* Install `onnxruntime` `pip install onnxruntime`
```
import onnxruntime as rt

sess = rt.InferenceSession(<File.onnx>)
input_name = sess.get_inputs()[0].name
label_name = sess.get_outputs()[0].name
pred_onx = sess.run([label_name], {input_name: X.astype(numpy.float32)})[0]
```



# Pretrained Models Examples:
* [Onnx-examples](https://github.com/onnx/models)
