# Machine Learning 5 特徵提取器

利用分類器，讓人們能自行訓練自己專屬的機器學習模型。

## Loading the extension for Machine Learning 5
    
    The Video Sensing extension is also used in this tutorial.

Open up the extension page.

![](../images/add.png)

Select Video Sensing, Machine Learning 5 and the Pen extension.

![](../images/add2.png)

![](../images/ml28.png)

New programming blocks will be added.

![](../images/ml6.png)

If your computer has a low specification(e.g. lacks a discrete GPU), its performance maybe enhanced by using CPU mode.

![](../images/ml14.png)

## Feature Extraction

### Example 1: Rock Paper Scissors

Turn on the camera and initialize the feature extractor

![](../images/ml15.png)

Teach the program to recognize the background.

![](../images/ml16.png)

Teach the program to recognize rock.

![](../images/ml17.png)

Then teach the program to recognize paper and scissors.

The program is now able to recognize these gestures.

![](../images/ml18.png)

![](../images/ml19.png)

The trained model can be saved as a json file for use in other programs.

![](../images/ml20.png)

We can load a model from before.

![](../images/ml21.png)