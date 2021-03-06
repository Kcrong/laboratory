# League-of-Fortuneteller
기계학습을 이용해 게임(리그 오브 레전드) 결과를 예측해보자

## Feature list
* blue_team_level
* blue_team_kill
* blue_team_death
* blue_team_assist
* blue_team_ckrate (킬 기여 수)
* blue_team_damage
* blue_team_bought_pink_ward
* blue_team_installed_ward
* blue_team_removed_ward
* blue_team_cs
* blue_team_cs_per_minute
* blue_team_gold
* blue_team_tier (Bronze, Silver 등 단계에 따라 숫자로 환산한 데이터)
* red_team_level
* red_team_kill
* red_team_death
* red_team_assist
* red_team_ckrate
* red_team_damage
* red_team_bought_pink_ward
* red_team_installed_ward
* red_team_removed_ward
* red_team_cs
* red_team_cs_per_minute
* red_team_gold
* red_team_tier

## Model
* Dense(same size with input) with Activation ReLu
* Dense_1 with Activation Sigmoid

## Result
**Accuracy: 95.37%**
```text
   5/2289 [..............................] - ETA: 0s - loss: 0.0028 - acc: 1.0000
 150/2289 [>.............................] - ETA: 0s - loss: 0.0845 - acc: 0.9667
 305/2289 [==>...........................] - ETA: 0s - loss: 0.1004 - acc: 0.9639
 425/2289 [====>.........................] - ETA: 0s - loss: 0.0920 - acc: 0.9671
 570/2289 [======>.......................] - ETA: 0s - loss: 0.0971 - acc: 0.9614
 710/2289 [========>.....................] - ETA: 0s - loss: 0.1036 - acc: 0.9577
 845/2289 [==========>...................] - ETA: 0s - loss: 0.1042 - acc: 0.9598
1005/2289 [============>.................] - ETA: 0s - loss: 0.1038 - acc: 0.9612
1150/2289 [==============>...............] - ETA: 0s - loss: 0.1063 - acc: 0.9617
1285/2289 [===============>..............] - ETA: 0s - loss: 0.1059 - acc: 0.9603
1435/2289 [=================>............] - ETA: 0s - loss: 0.1044 - acc: 0.9610
1595/2289 [===================>..........] - ETA: 0s - loss: 0.1106 - acc: 0.9574
1755/2289 [======================>.......] - ETA: 0s - loss: 0.1127 - acc: 0.9561
1910/2289 [========================>.....] - ETA: 0s - loss: 0.1221 - acc: 0.9534
2075/2289 [==========================>...] - ETA: 0s - loss: 0.1193 - acc: 0.9533
2230/2289 [============================>.] - ETA: 0s - loss: 0.1192 - acc: 0.9534
2289/2289 [==============================] - 0s - loss: 0.1178 - acc: 0.9537   
```


# Usage

## Make training dataset
`make_data.py` is only for make training data.  
> *FYI, our repo has already good [train_data](https://github.com/Kcrong/League-of-Fortuneteller/blob/master/train_data/data.csv), so you can use it.*

after make `nickname_list.txt` file with nickname list, run `make_data.py`.
```bash
(env3) $ python make_data.py
```
Then, if you see `train_data` folder, there will be two csv files. `computer_trainable.csv` and `human_readable.csv`.  
you need `computer_trainable.csv`. so rename the `computer_trainable.csv` to `data.csv`.
    
 
## Train model
`model.py` is our predict model.
Just run `model.py`

```bash
(env3) $ python model.py
W tensorflow/core/platform/cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE4.1 instructions, but these are available on your machine and could speed up CPU computations.
Epoch 1/20
W tensorflow/core/platform/cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE4.2 instructions, but these are available on your machine and could speed up CPU computations.
W tensorflow/core/platform/cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use AVX instructions, but these are available on your machine and could speed up CPU computations.
W tensorflow/core/platform/cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use AVX2 instructions, but these are available on your machine and could speed up CPU computations.
W tensorflow/core/platform/cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use FMA instructions, but these are available on your machine and could speed up CPU computations.
...
...
...
```

### Thanks
