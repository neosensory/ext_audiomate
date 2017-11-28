# PINGU

Pingu is a library for easy access to audio datasets. It provides the datastructures for accessing/loading different datasets in a generic way. This should ease the use of audio datasets for example for machine learning tasks.

Documentation: https://ynop.github.io/pingu/

## Installation

Install the latest development version:

```sh
pip install git+https://github.com/ynop/pingu.git
```


## Example
Example for loading a corpus and using the FramedSignalGrabber to retrieve the audio signal in frames.

```python
>>> ds = Corpus.load('/path/to/the/dataset', loader='default')
>>> grabber = FramedSignalGrabber(ds, label_list_idx='music', frame_length=400, hop_size=160)
>>>
>>> # Every frame contains the actual signal and a vector defining the active labels
>>> for frame in grabber:
>>>     print(frame)
(array([-0.00317392,  0.00866726,  0.01651051, ..., -0.01336711,
   -0.01263466, -0.01232948], dtype=float32), array([ 0.,  0.,  1.,  0.], dtype=float32))
...
```
