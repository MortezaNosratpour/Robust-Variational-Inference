# Robust-Variational-Inference
Aim to propose a variational inference method to overcome cold posterioe effect and be robust against any corruption. (Work is in progress)

We assume a distribution p(a, β) of augmentations aβ(x) : X → X from a predefined set of label-
preserving augmentations a ∈ A = {id, blur, noise,rot, . . . , }. Each augmentation can come with optional

intensity parameters β, which often ranges from 1 to 5. For instance, CIFAR-C has 19 corruptions with 5
intensities, leading to a total of K = |A| = 95 augmentations (excluding the clean image). The augmentation
distribution factorises into

$p(a, β) = p(β|a)p(a)$
where p(β|a) is the intensity distribution and p(a) is the augmentation distribution. We assume β ∈ R is
continuous, while a is from a countable set.

We define an augmented likelihood: 

![1](https://github.com/MortezaNosratpour/Robust-Variational-Inference/assets/45389014/7325fc57-4bed-4e96-8007-b6fc656fb5ca)


That is, we require the predictive posterior

![2](https://github.com/MortezaNosratpour/Robust-Variational-Inference/assets/45389014/de2fd038-e30e-4686-8b28-f5aadb38155e)



to be simultaneously good for any kind of label-preserving input transformation a(x).


Also we aim to solve cold posterio effect (CPE) in Bayesian neural networks:

CPE : The surprising observation that performance in neural networks is not optimal when we use the usual Bayesian posterior. Instead, we get better performance when the posterior taken to the power of 1/T where T < 1. (Nabarro et al.2021)
Tempering can reduce this misspecification by approximating the correct posterior.(Nabarro et al. 2021):

![image](https://github.com/MortezaNosratpour/Robust-Variational-Inference/assets/45389014/f9e25c5d-b24f-4716-a3f5-9da30622e703)

The proposed posterior tries to get rid of tempering factor (T, which is a hyperparameter of the network and need to be tuned) also solves the CPE problem.
