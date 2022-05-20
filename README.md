# Fourier-Transformer for solving Fokker-Planck PDE

Transformer for solving the problem in `Stochastic Local Volatility`
* Basic Component
  * All the files can be found [here](https://drive.google.com/drive/folders/1tUCTlFCo_-FoiCj-LkJdOsZrlSSq4mTe?usp=sharing)
  * The problem is denfined in [Stochastic Local Volatility](https://drive.google.com/file/d/184I0tqs4zpfCbq3lyIeRzp175HkjXA0J/view?usp=sharing), with SDE of 2 dimensions in space and 1 dimension in time.
* Stages of the lab
  * Experiment_0, sampling of the FokkerPlanck PDE, with the help of Quantlib.
  * Experiment_1, FNO in solving the FokkerPlanck PDE.
  * Experiment_2, FNO Transformer in solving the FokkerPlanck PDE.
* Basic Introduction
  * July UBS Tour
  * There are also some RL based methods to solve it
    * In solving `HJB PDE`, [Actor-Critic Method for High Dimensional Static Hamilton-Jacobi-Bellman Partial Differential Equations based on Neural Networks](https://drive.google.com/file/d/1HaaCSM7JVOiG9VpH0m72fsYW_urPEwsb/view?usp=sharing)   
    * In solving `Elliptic PDE`, [Neural Q-learning for solving elliptic PDEs](https://drive.google.com/file/d/1rh6Syg8r4UgnDKIBX7bOw2zkC_4DDMF6/view?usp=sharing)

## Week4
`2022.May.09, 11:00AM~12:15Noon`, with `Dr. Shuhao Cao`, `Ziheng Wang`, and `Deqing Jiang` at `Mathematical Institute`.
* The interface bwtween Quantlib and Transform
  * Sampling point format
  * Pre-process data format on our own
* The result of the PDE is in a stochastic way, which is totally different from the 
* ![static](static/Snipaste_2022-05-20_21-31-32.png)
</br> In order to get `v`, the `p` is what we want to solve, the transition density. It can be discribed by The Fokker-Planck Equation, which is 2 dimensions in space and 1 dimension in time.
</br> ![static](static/Snipaste_2022-05-20_21-35-03.png)
* `#TODO` Problems still remains
  * How to define the input data format
  * How to define the final result of our model
  * Is there any advantage compared with the tradition method `Monte Carlo`?
* Reference paper
  * `Fourier Neural Operator` [Fourier Neural Operator for Parametric Partial Differential Equations](https://drive.google.com/file/d/1izZPb4bfFm7nvD7k_cwRz_9v5moqR2oq/view?usp=sharing)
  * `Galerkin Transformer` [Choose a Transformer Fourier or Galerkin](https://drive.google.com/file/d/1PzW236pBHC71Ad-vTKiKo6NjVzeslYhp/view?usp=sharing)
  * `Fourier Transformer` [Adaptive Fourier Neural Operators: Efficient Token Mixers for Transformers](https://drive.google.com/file/d/1_YIJilTPHvddl8m2hHGU7sdhnH9eV_jZ/view?usp=sharing)
  * `DeepXDE` [A deep learning library for solving differential equations](https://arxiv.org/abs/1907.04502) [`Documentation`](https://deepxde.readthedocs.io/en/latest/)

## Week3

![Process](static/Process.svg)

* Problems remian in this week
  * Only a set of PDEs are suitable for Fourier Transform.
  * Why sample is `256*256` and downsample is `64*64`, what has downsampling done here?
  * How MCMC using FNO？
  * To solve different PDEs, do we need to change the code in the FNO?
    * Or the info has been included in the dataset by sampling.
  * We need to solve a two dimensional difussion equation.
    * https://github.com/KangOxford/Fourier-Transformer/blob/6fd306e6a6856a46b3db78fa57db8ced3c307060/fourier_neural_operator/fourier_3d.py#L1-L7
    * In the `class SpectralConv3d(nn.Module):`
    </br>https://github.com/KangOxford/Fourier-Transformer/blob/90686ea11466e55739068a4ca5b56fa74063d6f5/fourier_neural_operator/fourier_3d.py#L61-L76
  * How does the advantage of operator learning functions in this lab?
    * Does it not need to train again with different intial condition or boundrary condition.
    * Perhaps. As the Operator is learnt. So one of the three condtion has been solved, with the other two to be the intial condition and boundrary condition.
* Try with FNO for basic set up of the experiment.
* The FNO model for solving entire family of PDEs.
  * [FNO project](https://zongyi-li.github.io/neural-operator/)
  * [FNO GitHub](https://github.com/zongyi-li/fourier_neural_operator)
  * [FNO introduction](https://zongyi-li.github.io/blog/2020/fourier-pde/)
  * [FNO data](https://drive.google.com/drive/folders/1LfmrsIw6Wo_vbYhy3Azr4KVK8FeZDLT8?usp=sharing) 
  * [FNO models](https://drive.google.com/drive/folders/1pxQeQhE-M9OGbVIHr35fid4CDquXFWa-?usp=sharing)
    * Here are the pre-trained models. It can be evaluated using eval.py or super_resolution.py
* By now there is no need to focus on the Galerkin Transformer, as it only provides a better precision on results.
* We will focus more on the FNO in the next stages.
* The FNO is more focused on solving a family of PDEs without try to train the neural network from the scratch, such as when the initial condition or the boundary condition change.
