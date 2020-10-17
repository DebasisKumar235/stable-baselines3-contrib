.. _examples:

Examples
========

WIP

.. PyBullet: Normalizing input features
.. ------------------------------------
..
.. Normalizing input features may be essential to successful training of an RL agent
.. (by default, images are scaled but not other types of input),
.. for instance when training on `PyBullet <https://github.com/bulletphysics/bullet3/>`__ environments. For that, a wrapper exists and
.. will compute a running average and standard deviation of input features (it can do the same for rewards).
..

.. .. note::
..
.. 	you need to install pybullet with ``pip install pybullet``
..
..
.. .. image:: ../_static/img/colab-badge.svg
..    :target: https://colab.research.google.com/github/Stable-Baselines-Team/rl-colab-notebooks/blob/sb3/pybullet.ipynb
..
..
.. .. code-block:: python
..
..   import gym
..   import pybullet_envs
..
..   from stable_baselines3.common.vec_env import DummyVecEnv, VecNormalize
..   from stable_baselines3 import PPO
..
..   env = DummyVecEnv([lambda: gym.make("HalfCheetahBulletEnv-v0")])
..   # Automatically normalize the input features and reward
..   env = VecNormalize(env, norm_obs=True, norm_reward=True,
..                      clip_obs=10.)
..
..   model = PPO('MlpPolicy', env)
..   model.learn(total_timesteps=2000)