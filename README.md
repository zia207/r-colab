## Run R-Code in Google Colab


[Google Colab](https://colab.research.google.com/) is a cloud-based platform provided by Google for running and executing Python code. It is built on Jupyter Notebook and offers a free, convenient, and collaborative environment for data analysis, machine learning, and general-purpose Python programming. Colab allows you to create and share Jupyter notebooks that include code, text, images, and visualizations.

Key features of Google Colab include:

1.  **Free GPU and TPU Support:** Colab provides free access to a limited amount of GPU (Graphics Processing Unit) and TPU (Tensor Processing Unit) resources, which can significantly accelerate deep learning computations.

2.  **Collaborative Editing:** Multiple users can collaborate in real-time on the same Colab notebook, making it useful for team projects or sharing knowledge.

3.  **Google Drive Integration:** You can easily save and load files to and from your Google Drive, enabling seamless data storage and retrieval.

4.  **Rich Text and Media Support:** Colab notebooks support rich media integration, allowing you to include images, videos, and other multimedia elements in your notebooks.

5.  **Pre-installed Libraries:** Many popular Python libraries for data analysis, machine learning, and deep learning (e.g., NumPy, Pandas, TensorFlow, PyTorch) come pre-installed on Colab, reducing setup time.

6.  **Easy Sharing:** Colab notebooks can be easily shared with others by generating a shareable link. It's a convenient way to showcase your work or collaborate with others.

To get started with Google Colab, visit the official website at [**https://colab.research.google.com/**](https://colab.research.google.com/). You can create a new notebook or open an existing one from your Google Drive. The notebooks run on virtual machines hosted by Google, and once you close the browser, the virtual machine and its contents are discarded. Still, your notebook will be automatically saved to your Google Drive.

Remember that the available resources, such as GPU and TPU quotas, may be limited to free users. Also, the specific features and limitations of Google Colab may evolve, so it's always a good idea to check the official website or documentation for the latest information.

## R Runtime

Although Google Colab is primarily designed for Python, it also supports R. You can run R code in a Colab notebook by creating an R runtime environment. Here's how you can set it up:

1.  Open Google Colab in your web browser at https://colab.research.google.com/.

2.  Click on the `File` menu and select `New notebook` to create a new notebook.

3.  In the toolbar, click on the `Runtime` menu and select `Change runtime type.`

4.  In the dialog box that appears, select `R` from the `Runtime type` dropdown.

5.  Click on the `Save` button to apply the changes.

Once you have set up the R runtime environment, you can start writing and executing R code in the notebook cells. To run a code cell, press Shift+Enter or click the "Play" button next to the cell.

You can install R packages in Colab by using the **install.packages()** function.

## Python Runtime

1.  Open Google Colab in your web browser at https://colab.research.google.com/.

2.  Click on the `File` menu and select `New notebook` to create a new notebook.

3.  In the toolbar, click on the `Runtime` menu and select `Change runtime type.`

4.  In the dialog box that appears, select `Python 3` from the `Runtime type` dropdown.

5.  Click on the `Save` button to apply the changes.

6.  Easy way to run R in Colab with Python runtime using **rpy2** python package which helps in using R in Python environments. We have to install this package using the `pip` command in code chunk::

> !pip uninstall rpy2 -y

> !pip install rpy2==3.5.1

> load_ext rpy2.ipython`

7.  Since R in Google Lab run in Ubuntu OS, we have to install several `Ubuntu` packages to install several R packages

> !sudo apt-get install\
> libssl-dev\
> libcurl4-openssl-dev\
> unixodbc-dev
> libxml2-dev
> libmariadb-dev
> libfontconfig1-dev\
> libharfbuzz-dev\
> libfribidi-dev\
> libfreetype6-dev\
> libpng-dev\
> libtiff5-dev\
> libjpeg-dev\
> libcairo2-dev\
> libgmp-dev\
> libmpfr-dev\
> liblapack-dev\
> libcairo2-dev\
> libzmq3-dev\
> libharfbuzz-dev\
> libpng-dev\
> build-essential\
> libcairo2-dev\
> libmpfr-dev\
> cmake\
> gfortran

> !sudo apt-get install ghostscript\
> !sudo add-apt-repository ppa:dns/gnu\
> !sudo apt-get update\
> !sudo apt install libgsl-dev

8.  Mount Google: Use following command and follow on-screen instruction 

> from google.colab import drive
>
> drive.mount('/content/drive')

9.  Install R Packages in Google Drive

Before installation of R packages, we have create a folder (name R) in your Google Drive, from you load all packages. During installation you to define this location (`lib='drive/My Drive/R/'`) locally for R-packages. For example:

> install.packages(c('tidyverse', 'data.table'), lib='drive/My Drive/R/', repos='http://cran.rstudio.com/')

10. Load R Package from Google Drive. Use following command to load R-packages

> %%R
>
> .libPaths('drive/My Drive/R')
>
> library (tidyverse)

> library (data.table)

11. Use following commands, if to check and Installed Required R packages

> pkg \<- c( 'tidyverse','data.table')
>
> new.packages \<- pkg\[!(pkg %in% installed.packages(lib='drive/My Drive/R/')\[,"Package"\])\]

> if(length(new.packages)) install.packages(new.packages, lib='drive/My Drive/R/')








