# Carla Start
## 0. Install Carla
```bash

```
https://github.com/Kin-Zhang/mmfn/blob/main/scripts/setup_carla.sh  
https://carla.readthedocs.io/en/0.9.10/start_quickstart/  
https://www.zhihu.com/column/c_1324712096148516864
https://github.com/ucla-mobility/OpenCDA

## 1. Environment Config
```bash
# << Leaderboard setting
# ===> pls remeber to change this one
export CODE_FOLDER=/home/rubin/rubinFiles/3_papers/code/mmfn
export CARLA_ROOT=/home/rubin/CARLA_0.9.12
# ===> pls remeber to change this one
export SCENARIO_RUNNER_ROOT=${CODE_FOLDER}/scenario_runner
export LEADERBOARD_ROOT=${CODE_FOLDER}/leaderboard
export PYTHONPATH="${CARLA_ROOT}/PythonAPI/carla/":"${SCENARIO_RUNNER_ROOT}":"${LEADERBOARD_ROOT}":"${CARLA_ROOT}/PythonAPI/carla/dist/carla-0.9.12-py3.7-linux-x86_64.egg":"${CODE_FOLDER}/team_code":${PYTHONPATH}

```


## 2. Example
Test for Install.
```
cd /home/rubin/CARLA_0.9.12
./CarlaUE4.sh

<!-- And then, on the other terminal, run the python script -->
cd PythonAPI/example 
python3 automatic_control.py
```


# 1. User Manual
[how to use fisheye camera in Carla](https://github.com/Dtananaev/CarlaFSD)

