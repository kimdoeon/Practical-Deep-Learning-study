# 3_Neural_net_foudations

## Keywords
> ___SGD___  

> ___ReLU___

> ___non-linear activation functions___
## About Lecture

* __course TIPS!__
   * watch lecture -> reun notebook & experiment 
reoroduce results
repeat with different datset

   * fastbook rep -> clean folder -> same code but without text and ouput logs -> use it when you practice 

* __IDEAS of this week__
    * rock,sissor, paper with image
    - predict the avr temp of an area based on an aerial photograph
    - music genre classification
    - art movement classifire

* __Introducing new flatform__
    * paperspace : similiar to kaggle/google
    * using note book named Gradient
    * best platform for our course
    * real computer. not virtual environment
    * provide permanet storage so that we can maintain our files next time.

* __whole process__
    * import timm library
    * model training and predict
    * launch model using Gradio

* __module description__
    * learner 
        1. list of pre processing stpes that turn our imges into things of the model 
        2. train model   
        => you can actually grab the trained model by grabbing the .model attribute  
        `m = learn.model`
    * pytorch > get_submodule
        * ex) 0.model.stem.1 == return parameters of LayerNorm2d (mouse point)
![2_3](./img/2_3.png)
![2_4](./img/2_4.png)
=> what are these numbers?
    * torch.clip() == torch.clamp()  
    Changing the value into the category of min or max
ex) tensor([-2.5, 3, -1,10])
=> if you set min = 0.5 with torach.clamp, data under 0.5 turn into 0.5 so that the min value of tensor can be 0.5

* __gradient descent__

    calculate the gradient and do a descent to decrease the loss  
    loss function  
    loss.backward()  
    abc.grad=> ouput gradient

* __ReLU__  
Rectified Linear Function. 
    ```python
    def rectified_linear(m,b,x):
        y = m*x +b
        return torch.clip(y,0.)
    plot_function(partial(rectified_linear,1,1))
    ```
    In ReLU, value under 0 is 0, over 1 is linear function.
    but you overlap ReLU several times, It became waveform, and you overlap ReLU enough times, you can make model tha fit our data. Then we can get precise model. 
    Parameters are derived from gradient descent.
## Questions
* How di I know I have enough data?
* what are some signs that indicate my problem needs more data?

---
[code](https://www.kaggle.com/code/jhoward/how-does-a-neural-net-really-work)

