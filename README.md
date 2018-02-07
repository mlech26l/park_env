# park_env
Deterministic simulation environment for the parking of a rover. The parking is defined via reference check points that should be passed. 

Partially compatible with OpenAI Gym environments.
There exists no visualization (env.render is not implemented).

# How to get it working:
```bash
cd park_gym
make 
mv bin/park_gym.so ..

```

Then you can work in this directory or add it to your PYTHONPATH shell variable.
Usage of the environment is pretty straight forward:

```python
import park_env

env = ParkEnv()
env.reset()
obs, r, done, info = env.action([0,0])

```

Observation space consists of the 3 variables x,y and theta. Additional information like a start signal must be added explicitly.
Action space consists of the 2 variables: linear velocity and angular velocity.
The check points are loaded from the file learn_tw.dat

