# SyntheticArticulatedData
Procedurally generated articulated objects specified in Universal Robot Description Format (URDF), and rendered using Mujoco.

# Environment
  Miniconda 24.7.1
  Python 3.9.18
  Ubuntu 22.04.4

# Mujoco
Setup installtion
1. Download the Mujoco library from 
https://mujoco.org/download/mujoco210-linux-x86_64.tar.gz
2. create a hidden folder :
mkdir /home/username/.mujoco
3. extract the library to the .mujoco folder
4. include these lines in  .bashrc file:

``` 
export LD_LIBRARY_PATH=/home/user_name/.mujoco/mujoco210/bin 
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/lib/nvidia 
 export PATH="$LD_LIBRARY_PATH:$PATH" 
export LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libGLEW.so 
```

5. source .bashrc

6. Test that the library is installed by going into:
cd ~/.mujoco/mujoco210/bin
./simulate ../model/humanoid.xml

# FOr Mujoco-py
Step 4 Install mujoco-py:
conda create --name mujoco_py python=3.8
conda activate mujoco_py
sudo apt update
sudo apt-get install patchelf
sudo apt-get install python3-dev build-essential libssl-dev libffi-dev libxml2-dev  
sudo apt-get install libxslt1-dev zlib1g-dev libglew1.5 libglew-dev python3-pip
git clone https://github.com/openai/mujoco-py
cd mujoco-py
pip install -r requirements.txt
pip install -r requirements.dev.txt
sudo apt-get install libglew-dev
pip install -e . --no-cache

Step 6 run these commands
conda activate mujoco_py
sudo apt install libosmesa6-dev libgl1-mesa-glx libglfw3
sudo ln -s /usr/lib/x86_64-linux-gnu/libGL.so.1 /usr/lib/x86_64-linux-gnu/libGL.so
cd
cd examples
python3 setting_state.py

Dependencies needed:
pip install "Cython<3"
pip install torchvision
pip3 install opencv-python
pip install matplotlib
pip3 install pyro-ppl
pip install transforms3d

# Open GL initalization failed
unset LD_PRELOAD

# FileExistsError: [Errno 17] File exists:
os.makedirs(test_dir, exist_ok=True)

#  anim.save(os.path.join(dir,'animation.mp4'), fps=30, extra_args=['-vcodec', 'libx264']),
# writer = writer_cls(fps, **writer_kwargs)
#  animation issue
conda install -c conda-forge av

Setup:
```pip install -r requirements.txt```

Example generation:
```python generate_data.py --n 10 --dir ./test --obj microwave --masked --debug```

# PyBullet

Setup:
```pip install -r requirements-bullet.txt```

Example generation:
```python generate_data.py --n 10 --dir ./test --obj microwave --masked --debug --py-bullet```
