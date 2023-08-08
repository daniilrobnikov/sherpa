# sherpa

## Usage with [kaldi-gstreamer-server](https://github.com/alumae/kaldi-gstreamer-server/tree/py3) and [Estonian model](https://huggingface.co/TalTechNLP/icefall_pruned_transducer_stateless7_streaming_et)

```bash
# go to the sherpa root directory
python ./sherpa/bin/streaming_server.py \
  --port=6006 \
  --encoder-model="path/to/icefall_pruned_transducer_stateless7_streaming_et/encoder_jit_trace.pt" \
  --decoder-model="path/to/icefall_pruned_transducer_stateless7_streaming_et/decoder_jit_trace.pt" \
  --joiner-model="path/to/icefall_pruned_transducer_stateless7_streaming_et/joiner_jit_trace.pt" \
  --tokens="path/to/icefall_pruned_transducer_stateless7_streaming_et/data/lang_bpe_1000/tokens.txt"
```

```bash
# go to the kaldi-gstreamer-server root directory
python kaldigstserver/client.py -r=32000 test/data/lause2.raw
```

# sherpa

`sherpa` is an open-source speech-text-text inference framework using
PyTorch, focusing **exclusively** on end-to-end (E2E) models,
namely transducer- and CTC-based models. It provides both C++ and Python APIs.

This project focuses on deployment, i.e., using pre-trained models to
transcribe speech. If you are interested in how to train or fine-tune your own
models, please refer to [icefall][icefall].

We also have other **similar** projects that don't depend on PyTorch:

- [sherpa-onnx][sherpa-onnx]
- [sherpa-ncnn][sherpa-ncnn]

> `sherpa-onnx` and `sherpa-ncnn` also support iOS, Android and embedded systems.

## Installation and Usage

Please refer to the **documentation** at <https://k2-fsa.github.io/sherpa/>

## Try it in your browser

Try `sherpa` from within your browser without installing anything:
<https://huggingface.co/spaces/k2-fsa/automatic-speech-recognition>

[icefall]: https://github.com/k2-fsa/icefall
[sherpa-onnx]: https://github.com/k2-fsa/sherpa-onnx
[sherpa-ncnn]: https://github.com/k2-fsa/sherpa-ncnn
