# Priority-based reward shaping for fast-settling and low-deviation trajectory planning of a wing-in-ground craft’s altitude change


* **Description on directories:**  Directories named with "multiobj_k_" are cases of conventional multi-objective functions, whose magnitude of weight are labeled at the end of the name. For example, 'multiobj_k_10e-3' means that the weight $k$ in the reward function is 0.001. Directories named with "proposed_base_" represent cases of the proposed objective function, whose magnitude of base is written at the end of the name. For instance, "proposed_base_3" means that the base $\lambda$ in the reward function is 3.
* Each directory is an individual case. Each case are examined with eight different seeds, so there are eight sub directories named with "s_", where main code files locate.

* **Main code file:** At the each sub-sub directory, there are six files for the training, which are as following:
1. *Main.py*. It's main function and the training environment and reward function are defined. 

2. *replay.py*. It's classes of replay buffer during training.

3. *net.py*. It's classes of neural network for the algorithm of Proximal Policy Optimization (PPO).

4. *agent.py*. It's classes of agents for PPO.

5. *aeropy_fix.py*. It's functions for aerodynamics and kinectics of the wing-in-ground craft (WIG) during training.

* **Prerequisites for running codes:**  Pytorch is needed to be installed in advance. In order to run the code at each sub-sub directory, the file 'datacollection.npy', 'guiyi_0.3to0.6_case1_0bu.pth', "actor_0.3to0.6_case1_0bu.pth", "critic_0.3to0.6_case1_0bu.pth" and "critic_target_0.3to0.6_case1_0bu.pth" should be downloaded and then placed in the root directory. Since the website of Github limits the size of files, the necessary file and main results are placed in the same directory and they are upload in onedrive. The link is https://aluhiteducn-my.sharepoint.com/:f:/g/personal/huhuan2016_alu_hit_edu_cn/Ep8QRnHSo9hNm3PEpckQcWEBjVqPFWObGAQFST0qGj39fg?e=WlgHZT. The file 'datacollection.npy' is used for the calculation of aerodynamics for the WIG, and other files is needed for the code to implement deep reinforcement learning.

* For your convenience, the above link shows all files and their right location in the root directory.

* **Main results after running codes:**  For each case, after the eight subcase of different seeds ran, please run the file "watch_and_pick_find.py" to find out the case that gets the maximum reward. After the python file ran, there will be eight picture which are the outputs of the eight subcases after the training. The optimal trajectory is labled with "maximum.png", and the corresponding subcase can be found according to the same '.png' file.

* all results are placed in the the directory "result_trajectory", and each file is named after the corresponding cases.

* **There are also other files for your reference.

1. *actor.pth*. It's neural network of the Actor in deep reinforcement learning.

2. *critic.pth*. It's neural network of the Critic in deep reinforcement learning.

3. *critic_target.pth*. It's neural network of the Target of Actor in deep reinforcement learning.

4. *guiyi.pth.npy*. It's memory buffer which is used for normalization during training.

6. *reward_curve.png*. It's reward curve during training.

7. *thebest.npy*. It's the data of trajectory which is rewarded mostly after training.

8. *theone.png*. It shows the trajectory which is rewarded mostly after training.

9. *bestlog.npy*. It records every breakthrough of the reward during training.
