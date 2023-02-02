## plot_model

------------------
#### ryuuzaki42 info - start

### Tested in Google Collab
#### Mount the /content/drive
```sh
from google.colab import drive
drive.mount('/content/drive')
```

### Install tensorflow 2.6.4
```sh
!pip install tensorflow==2.6.4
import tensorflow as tf
print(tf.__version__)
```

### Install pydotplus
```sh
pip install pydotplus
```

### Install graphviz
```sh
pip install graphviz
```

### Clone plot_model
```sh
!git clone https://github.com/ryuuzaki42/plot_model
```

### Load/Exec file
```sh
execfile("/content/plot_model/plot_model/plot_model.py")
```

### Make the plot
```sh
plot_model(model)

# Default
#plot_model(model, to_file='model.png', show_shapes=True, show_layer_names=False, rankdir='TB', expand_nested=False, style=0, color=True, dpi=96)

# My use
#num_file = "01"
#file_name_s = "model_" + num_file + "_s.png"

#plot_model(model, to_file=file_name_s, show_shapes=False, show_layer_names=False, rankdir='TB', expand_nested=False, style=0, color=True, dpi=96)
```

### Args:
    model: A Keras model instance
    to_file: File name of the plot image.
    show_shapes: whether to display shape information.
    show_dtype: whether to display layer dtypes.
    show_layer_names: whether to display layer names.
    rankdir: `rankdir` argument passed to PyDot,
        a string specifying the format of the plot:
        'TB' creates a vertical plot;
        'LR' creates a horizontal plot.
    expand_nested: Whether to expand nested models into clusters.
    dpi: Dots per inch.

## Original plot
```sh
import tensorflow as tf
from keras.utils.vis_utils import plot_model

num_file = "01"
file_name_f = "model_" + num_file + "_f.png"

tf.keras.utils.plot_model(model, to_file=file_name_f, show_shapes=True, show_dtype=False, show_layer_names=False, rankdir='TB', expand_nested=False, dpi=96)
```

## Print conv
```sh
#print("f\n\n", f, "\n")
#print(DECODER, "\n")

for i, layer in enumerate(model.layers):
  #if 'conv' in layer.name:
  if layer.weights:
    print("  ", layer.name, end=" ")
    print(layer.weights[0].shape)
    #print(layer.weights[1].shape)
  else:
    print("       ",layer.name)

  print(i,'-' * 30)
```

#### ryuuzaki42 info - end
------------------

After some changing of code, now should be able to run with tensorflow 2.6.4, for other using package information, you can see in My environments.txt
, my project can using the following package and success to run the plot_mode.

GitHub:[https://github.com/Qinbf/plot_model.git](https://github.com/Qinbf/plot_model.git)

plot_model is a API for model visualization reference to [tensorflow.keras.utils.plot_model](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/keras/utils/vis_utils.py).

 <p align="center"><img  src="https://raw.githubusercontent.com/Qinbf/plot_model/master/img/1.png" width="50%" height="50%"></p>
 
 ------------------
 
 ## Installation

Before installing plot_model, please install one of its engines: **TensorFlow**, **Keras**. 


You may also consider installing the following :

```sh
pip install pydotplus
pip install graphviz
```
- !!!!! Finally,download and install [graphviz](https://graphviz.gitlab.io/download/) to plot model graphs. !!!!!

Then, you can install plot_model itself. There are two ways to install plot_model:

- **Install plot_model from PyPI (recommended):**

Note: These installation steps assume that you are on a Linux or Mac environment.
If you are on Windows, you will need to remove `sudo` to run the commands below.

```sh
sudo pip install plot_model
```

If you are using a virtualenv, you may want to avoid using sudo:

```sh
pip install plot_model
```

- **Alternatively: install plot_model from the GitHub source:**

First, clone plot_model using `git`:

```sh
git clone https://github.com/Qinbf/plot_model.git
```

 Then, `cd` to the plot_model folder and run the install command:
```sh
cd plot_model
sudo python setup.py install
```

------------------

## Getting started

API is similar to tensorflow.keras.utils.plot_model

```python
from plot_model import plot_model
plot_model(model)
```

default parameters:
```python
plot_model(model, to_file='./model.png', show_shapes=True, show_layer_names=False, rankdir='TB', expand_nested=False, style=0, color=True, dpi=96)
```

**color**: whether to display color. Default True.
 
**style**: 0 new style. 1 original style. Default 0. 

------------------

## Examples
<h5 align="center">ResNet</h5>
<p align="center"><img  src="https://raw.githubusercontent.com/Qinbf/plot_model/master/img/2.png" width="25%" height="25%"></p>

 
<h5 align="center">Inception</h5>
<p align="center"><img  src="https://raw.githubusercontent.com/Qinbf/plot_model/master/img/3.png" width="50%" height="50%"></p>
 
 
<h5 align="center">ResNeXt</h5>
<p align="center"><img  src="https://raw.githubusercontent.com/Qinbf/plot_model/master/img/4.png" width="65%" height="65%"></p>


