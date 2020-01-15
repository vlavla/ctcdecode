

Fixing the bug when your target vocab lisr containing word or chinese char.

In the original code, the word list can only have numbers, letters, or single-byte characters, because this is done when passing from Python to C ++ code.

```python
self._labels = ''.join(labels).encode()
```

I modified here, and passed the python list directly, and then when binding, the accepted  parameters were changed from char to vector.

======================================================================================================

## ctcdecode

ctcdecode is an implementation of CTC (Connectionist Temporal Classification) beam search decoding for PyTorch.
C++ code borrowed liberally from Paddle Paddles' [DeepSpeech](https://github.com/PaddlePaddle/DeepSpeech).
It includes swappable scorer support enabling standard beam search, and KenLM-based decoding.

### Installation
The library is largely self-contained and requires only PyTorch 1.0. Building the C++ library requires gcc or clang. KenLM language modeling support is also optionally included, and enabled by default.

```bash
# get the code
git clone --recursive https://github.com/parlance/ctcdecode.git
cd ctcdecode
pip install .
```
