# Homework 3 Report

## 2 Deep Q-learning

1. `CartPole-v1` environmental steps VS eval return

   ![image-20241014095439017](https://raw.githubusercontent.com/OctopussGarden/ImageRepo/main/imgs/image-20241014095439017.png)

2. `LunarLander-v2` environmental steps VS eval return with seed 1~3

   ![image-20241014095647356](https://raw.githubusercontent.com/OctopussGarden/ImageRepo/main/imgs/image-20241014095647356.png)

   Seeds 1~3 order

   <img src="https://raw.githubusercontent.com/OctopussGarden/ImageRepo/main/imgs/image-20241014095926540.png" alt="image-20241014095926540" style="zoom: 33%;" />

3. `CartPole-v1`  learning rate comparison

   curve with higher eval_return is with learning rate `0.001`, while the lower one with `0.05`

   - Eval return

     ![image-20241014100034341](https://raw.githubusercontent.com/OctopussGarden/ImageRepo/main/imgs/image-20241014100034341.png)

     > Eval with lower learning rate has higher eval return

   - Critic loss

     ![image-20241014100210730](https://raw.githubusercontent.com/OctopussGarden/ImageRepo/main/imgs/image-20241014100210730.png)
     
     > Larger learning rate tends to have increasing critic loss, has poorer performance.

4. `LunarLander-v2` Double Q learning *(in magenta)* VS "Vanilla" DQN *(in navy blue)*

   ![image-20241014101535398](https://raw.githubusercontent.com/OctopussGarden/ImageRepo/main/imgs/image-20241014101535398.png)

5. `MsPacmanNoFrameskip-v0` EvalReturn VS TrainReturn

   ![image-20241014105130678](https://raw.githubusercontent.com/OctopussGarden/ImageRepo/main/imgs/image-20241014105130678.png)

   ![image-20241014110536352](https://raw.githubusercontent.com/OctopussGarden/ImageRepo/main/imgs/image-20241014110536352.png)