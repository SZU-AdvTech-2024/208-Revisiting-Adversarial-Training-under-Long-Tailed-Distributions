## Revisiting Adversarial Training under Long-Tailed Distributions

Code for CVPR 2024 "Revisiting Adversarial Training under Long-Tailed Distributions".

## Environment

- Python (3.9.12)
- Pytorch (2.1.0)torch==2.1.0  torchvision==0.16.0
- torchvision (0.16.0)
- CUDA
- AutoAttack
- advertorch

## Content

- ```./datasets```: Generate long-tailed datasets.
- ```./models```: Models used for training.
- ```train_at_bsl_cifar10.py```: AT-BSL on CIFAR-10-LT.
- ```train_at_bsl_cifar100.py```: AT-BSL on CIFAR-100-LT.
- ```at_bsl_loss.py```: Loss function for AT-BSL.
- ```pgd_attack.py```: Use PGD to select the best epoch during training.
- ```eval.py```:  Evaluate the robustness under various attacks.

## Run

- AT-BSL using ResNet18 on CIFAR-10-LT
```bash
CUDA_VISIBLE_DEVICES='0' python train_at_bsl_cifar10.py --arch res --aug none
```
# 训练
Files already downloaded and verified
Files already downloaded and verified
Natual: (70.00%)
Robust: (32.40%)
best_acc:0.6822 best_rob:0.3703 best_epoch:77
# 预测
None
Robust: (68.17%)
None: 1.4 seconds
FGSM
Robust: (41.42%)
FGSM: 4.5 seconds
PGD
Robust: (36.93%)
PGD: 64.8 seconds
CW
Robust: (34.91%)
CW: 67.9 seconds
lsa PGD
Robust: (34.58%)
PGD: 66.4 seconds
autoattack
Robust: (33.04%)
autoattack: 2643.6 seconds
model-res-cifar10-none/epoch77.pt
0.6817	0.4142	0.3693	0.3491	0.3458	0.3304	

Process finished with exit code 0


- AT-BSL-RA using ResNet18 on CIFAR-10-LT
```bash
CUDA_VISIBLE_DEVICES='0' python train_at_bsl_cifar10.py --arch res --aug ra
```
# 训练
Natual: (70.73%)
Robust: (37.69%)
best_acc:0.6981 best_rob:0.3818 best_epoch:92
================================================================
# 预测
None
Robust: (69.76%)
None: 1.1 seconds
FGSM
Robust: (42.47%)
FGSM: 4.4 seconds
PGD
Robust: (38.09%)
PGD: 64.1 seconds
CW
Robust: (35.86%)
CW: 66.4 seconds
lsa PGD
Robust: (35.48%)
PGD: 66.7 seconds
autoattack
Robust: (33.76%)
autoattack: 2775.2 seconds
model-res-cifar10-ra/epoch92.pt
0.6976	0.4247	0.3809	0.3586	0.3548	0.3376	

Process finished with exit code 0


- AT-BSL using WideResNet-34-10 on CIFAR-100-LT
- 
# hhhh train
```bash
CUDA_VISIBLE_DEVICES='0' python train_at_bsl_cifar100.py --arch wrn --aug none
```
# 训练
Natual: (48.09%)
Robust: (16.87%)
best_acc:0.4988 best_rob:0.2017 best_epoch:75

# 预测
None
Robust: (49.83%)
None: 7.6 seconds
FGSM
Robust: (23.40%)
FGSM: 31.6 seconds
PGD
Robust: (19.99%)
PGD: 511.5 seconds
CW
Robust: (19.58%)
CW: 519.5 seconds
lsa PGD
Robust: (21.37%)
PGD: 512.9 seconds
autoattack
Robust: (18.14%)
autoattack: 22777.0 seconds
model-wrn-cifar100-none/epoch75.pt
0.4983	0.2340	0.1999	0.1958	0.2137	0.1814	


- AT-BSL-AuA using WideResNet-34-10 on CIFAR-100-LT

```bash
CUDA_VISIBLE_DEVICES='0' python train_at_bsl_cifar100.py --arch wrn --aug aua
```
# 训练
Files already downloaded and verified
Files already downloaded and verified
Natual: (55.06%)
Robust: (22.18%)
best_acc:0.5320 best_rob:0.2533 best_epoch:76

# 预测的结果
Files already downloaded and verified
None
Robust: (53.15%)
None: 7.7 seconds
FGSM
Robust: (28.08%)
FGSM: 32.5 seconds
PGD
Robust: (25.12%)
PGD: 520.6 seconds
CW
Robust: (23.45%)
CW: 526.1 seconds
lsa PGD
Robust: (24.56%)
PGD: 524.4 seconds
autoattack
Robust: (21.40%)
autoattack: 27227.6 seconds
G:\task\10-AT-BSL-main\model-wrn-cifar100-aua\epoch76.pt
0.5315	0.2808	0.2512	0.2345	0.2456	0.2140	

Process finished with exit code 0


- Evaluation

```bash
CUDA_VISIBLE_DEVICES='0' python eval.py --model_path INSERT-YOUR-MODEL-PATH
```


## Pre-trained Models

- The pre-trained models can be downloaded from the [Google Drive](https://drive.google.com/drive/folders/1o-ZGm43jfrg_tALUNy_dGJpUBx1yHfp-?usp=drive_link).

## Reference Code

[1] RoBal: https://github.com/wutong16/Adversarial_Long-Tail

[2] REAT: https://github.com/GuanlinLee/REAT

[3] AT: https://github.com/MadryLab/cifar10_challenge

[4] TRADES: https://github.com/yaodongyu/TRADES