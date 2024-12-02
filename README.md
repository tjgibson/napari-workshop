# 2024 bioinformatics workshop: Napari image viewer for exploring spatial transcriptomics

As more labs perform spatial transcriptomics experiments, there is a necessity for researchers to be able to visualize and explore the results. For 10X genomics experiments, the Loupe Browser application is one option for exploring spatial data that does not require any coding. While Loupe Browser offers an intuitive, polished, interactive interface, the functionality is limited. I recently started using the [Napari image viewer](https://napari.org/stable/) for visualizing spatial datsets. Napari is powerful, flexible, and customizable, and can be used to visualize tissue images, gene expression, and virtually any type of data or analysis resulting from spatial transcriptomics experiments. Napari can also be used more generally for any type of imaging/microscopy data, but this workshop will focus on spatial transcriptomics. The following instructions can be used to install and run Napari with minimal coding required.

***Note for Windows users: while the following instructions should work on Windows, Mac, or Linux computers, I don't have a way of testing this on Windows and can't guarantee everything will work***

## Download this repository to your computer

**Option 1: Using git from the command line** If you are familiar with using the command line program git, open a terminal session and use the following code to clone this repository in a location of your choosing:

```         
git clone https://github.com/tjgibson/2024-napari-workshop.git
```

**Option 2: Download through github** To download this repository through the web, do the following:

1.  navigate to the github page: <https://github.com/tjgibson/2024-napari-workshop>.

2.  Click on the green code icon to open a dropdown menu.

3.  Click download zip and save in a location of your choice.

4.  Unzip the file and open the folder.

## Download the example dataset

To try out Napari on a real spatial transcriptomic dataset, follow the instructions below to download an example dataset and place it in the data folder.

### Mouse intestines dataset

10X genomics provides an example dataset generated using the Visium HD platform on mouse intestines.

1.  Use [this link](https://s3.embl.de/spatialdata/spatialdata-sandbox/visium_hd_3.0.0_io.zip) to download the dataset and save it to the data folder.

2.  Rename the dataset `visium_hd.zarr`.

## Software Setup

Using Napari will require you to have the following software installed on your computer:

1.  Python and conda/mamba.

2.  The spatialdata Python package.

3.  The Visual Studio Code editor for opening and launching the Python notebook.

### *Installing Python*

I recommend using the Miniforge Python distribution.

#### Mac/Linux installation:

1.  Open a terminal session.

2.  In the terminal, navigate to your downloads folder so that the Miniforge install script will be downloaded there:

```         
cd ~/Downloads
```

3.  Run the following code to install Miniforge:

```         
curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"
bash Miniforge3-$(uname)-$(uname -m).sh
```

#### Windows installation:

Visit [this link](https://github.com/conda-forge/miniforge) to download and run the Windows installer.

Full installation instructions and additional information about Miniforge can be found [here](https://github.com/conda-forge/miniforge)

### *Installing the spatialdata package*

1.  Open a fresh terminal session.
2.  You can verify that you have installed conda/mamba by running `which conda` or `which mamba`, which should output something similar to `/Users/myusername/miniforge3/condabin/mamba`.
3.  Navigate to the directory for this workshop:

```         
cd /path/to/2024-napari-workshop
```

4.  Generate a software environment for the spatialdata package by entering the following command:

```         
conda env create -n spatialdata -f spatialdata.yaml
```

## Opening the example notebook in VS code

Although Napari is an interactive, graphical application, it is launched from a Python script/notebook rather than by opening an app on your computer. As an easy way to launch Napari, I have provided a template ipython notebook to load a spatial transcriptomics dataset and launch the Napari viewer. To do so, follow the steps below.

1.  Download and install the Visual Studio Code program: <https://code.visualstudio.com/Download>

2.  Open VS Code. Click on file, open folder and select the folder for this workshop.

3.  Open the file `napari_viewer.ipynb` in VS Code.
