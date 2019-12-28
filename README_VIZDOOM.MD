For running world models data generation for VizDoom example on Leonhard cluster:

Run this </br>
<code>module load StdEnv openmpi/4.0.1 openblas/0.2.19 libpng/1.6.27 gtkplus/3.20.10 sdl2/2.0.5 gcc/4.8.5 cmake/3.4.3 jpeg/9b python_cpu/3.6.1 libgme/0.6.2 boost/1.62.0 eth_proxy mesa/12.0.6 mesa-glu/9.0.0 opencv/3.4.6 ffmpeg/3.2.14</code>

</br>

Then run this in order to get needed files in gym </br>
<code>python -m pip install --no-cache-dir --user mpi4py </code> </br>
<code>python -m pip install --no-cache-dir --user gym </code> </br>
<code>python -m pip install --no-cache-dir --user gym[box2d] </code> </br>
<code>python -m pip install --no-cache-dir --user gym[all] </code> </br>

</br>

When you do this you need to git clone both VizDoom dependent libraries: </br>
<code>git clone https://github.com/dsvilarkovic/ViZDoom </code></br>
<code>git clone https://github.com/dsvilarkovic/vizdoomgym </code></br>

First you need to follow instructions for installing ViZDoom library by: </br>
<code>cd VizDoom </code> </br>
<code>python -m pip install --user . </code></br>

Then install vizdoomgym wrapper: </br>
<code>cd vizdoomgym </code> </br>
<code>python -m pip install --user -e . </code></br>


After that run the simple example to see if everything works: </br>
<code>import gym  </br>
import vizdoomgym </br>
env = gym.make('VizdoomBasic-v0')</code> </br>


For running the data generation from this folder run this example file: </br>
<code>xvfb-run -s "-screen 0 1400x900x24" python data/generation_script.py --rollouts 10 --rootdir datasets/vizdoom --threads 1
</code>
</br>
