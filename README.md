# nir-ded-dataset

This is a dataset consisting of images of a DED operation, at different standoff distances.

The `focus_dataset.pkl` file is available in the "Releases" section.

## Usage

The file is a Python Pickle file, and the most straightforward way of using it is to directly import into the python script, although it can be easily exported to other formats.

The Python object is a dictionary, that contains the standoff distances as keys, and arrays of images as values. The images have been taken sequentially.

For example:

```python
with open('focus_dataset.pkl', 'rb') as f:
  dataset = pickle.load(f)
del dataset['bounds'] # This is an extra key that was kept for simplicity

for i, (dist, images) in enumerate(dataset.items()):
  print('{} entry, taken at distance {} with {} images'.format(i, dist, images.shape[0]))
```
