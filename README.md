# How to set up your IJulia kernels for the Intro to Julia Sciware session

## Step one: get the git repository

The first thing to do is clone the repository containing the notebooks, data, and some ancillary files. I usually keep repos like this in a folder called projects or demos, so for me this would look like:

    cd ~/projects
    git clone https://github.com/flatironinstitute/sciware-julia.git

If you already have the sciware-julia repo cloned, then make sure to pull from master:

    git pull origin master

That should put all the notebooks and such in the sciware-julia folder. Now we are ready to set up jupyter.

## Step two: install Jupyter kernels

What you will need to do depends if you have access to the [Flatiron Institute JupyterHub](https://docs.simonsfoundation.org/index.php/Public:JupyterHub) at jupyter.flatironinstitute.org.

### If you do have access to jupyter.flatironinstitute.org:

In this case all you should need to do is copy the two kernel files included in the Sciware github repository to:

    .local/share/jupyter/kernels

Like so:

    cp -r julia* ~/.local/share/jupyter/kernels/

Then, if you reload your Launcher page on Jupyter, you should see two new kernels available.

### If you do not have access:

In this case you''ll need to download your own Julia executable. Go to https://julialang.org/downloads/#current_stable_release and download Julia-1.4. This is an executable so you can simply install it without building Julia from source. Make sure you keep track of where Julia is installed. For example, I usually install Julia in `$HOME/julia`.

Launch Julia (using $HOME/julia/usr/bin/julia, for example) and run:

    ] *(yes, type close square bracket)*
    add IJulia
    build IJulia

That should install and build everything you need to run Julia jupyter notebooks, and install the kernel for you. In that case you don't need the JSON files discussed above.

## Step 3: launch the main Jupyter notebook

### If you're using jupyter.flatironinstitute.org

Open jupyter.flatironinstitute.org in your browser and use the same username and password you use to log in to the clusters. You should see a launcher screen. Navigate to the folder where you cloned sciware-julia. Click on the Sciware Introduction to Julia notebook. Jupyter will ask which kernel you want to use. Select `Julia-1.4`. (Make sure it says Julia-1.4 in the upper-right corner with an open circle, and click to change it if not.)

### If you're using your own computer

Navigate to the sciware-julia folder in your terminal. Once there, run jupyter notebook. You should see the folder open up in your browser. Click on the Sciware Introduction to Julia notebook. Jupyter will ask which kernel you want to use. Select Julia-1.4.


