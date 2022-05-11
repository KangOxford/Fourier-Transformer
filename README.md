# FokkerPlanck-Transformer

Transformer for solving the problem in `Stochastic Local Volatility`
* Basic Component
  * All the files can be found [here](https://drive.google.com/drive/folders/1tUCTlFCo_-FoiCj-LkJdOsZrlSSq4mTe?usp=sharing)
  * [Online SDE optimization simulation](https://drive.google.com/file/d/1QRuUF7aWUdJ25q0jIrGUu63Mn1ohrIMp/view)
* Stages of the lab
  * Lab_0, sampling of the FokkerPlanck PDE, with the help of Quantlib.
  * Lab_1, FNO in solving the FokkerPlanck PDE.
  * Lab_2, FNO Transformer in solving the FokkerPlanck PDE.

* Basic Introduction
  * Mid-May UBS Tour
  * Normally, it would be a high dimensional problem if the pde dimension is over 4 and almost can not be solved if the dimension is over 7.
  * There are also some RL based methods to solve it
    * In solving `HJB PDE`, [Actor-Critic Method for High Dimensional Static Hamilton-Jacobi-Bellman Partial Differential Equations based on Neural Networks](https://drive.google.com/file/d/1HaaCSM7JVOiG9VpH0m72fsYW_urPEwsb/view?usp=sharing)   
    * In solving `Elliptic PDE`, [Neural Q-learning for solving elliptic PDEs](https://drive.google.com/file/d/1rh6Syg8r4UgnDKIBX7bOw2zkC_4DDMF6/view?usp=sharing)

## Week3
* Try with FNO for basic set up of the experiment.
* The FNO model for solving a family of PDEs.
  * [FNO project](https://github.com/zongyi-li/fourier_neural_operator)
  * [FNO    data](https://drive.google.com/drive/folders/1LfmrsIw6Wo_vbYhy3Azr4KVK8FeZDLT8?usp=sharing) 
  * [FNO models](https://drive.google.com/drive/folders/1pxQeQhE-M9OGbVIHr35fid4CDquXFWa-?usp=sharing)Here are the pre-trained models. It can be evaluated using eval.py or super_resolution.py
* By now there is no need to focus on the Galerkin Transformer, as it only provides a better precision on results.
* We will focus more on the FNO in the next stages.
* The FNO is more focused on solving a family of PDEs without try to train the neural network from the scratch, such as when the initial condition or the boundary condition change.
