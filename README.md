# Robust-Variational-Inference
Aim to propose a variational inference method to overcome cold posterioe effect and be robust against any corruption. (Work is in progress)

We assume a distribution p(a, β) of augmentations aβ(x) : X 7→ X from a predefined set of label-
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
