
<p align="center">
  <img width="300" src="https://tembah.net/uploads/news/1632208614.jpeg" alt="logo">
</p>

<h1 align="center">Modelling Football Scores in the Italian Serie A :soccer: </h1>

<h2 align="center">Projects in Math Modelling - ACM40960</h2>

### :scroll: Basic Overview
The research aims to forecast the likelihood of a football match outcome, then assess the model's accuracy by contrasting its forecasts with those of the bookmaker, in this case Bet365. The best of the three Machine Learning models deployed is then utilised to construct a betting simulation in order to determine the profit made over a few weeks.

This project has been completed within Jupyter Notebooks using the Python programming language. You can run these notebooks using an appropriate IDE/UI, such as  _Jupyter Notebook_  or _JupyterLab_.

The different model notebooks included in this repository has already been executed in full, with all relevant plots, figures and results already visible. Therefore, the fully executed file can be viewed by clicking on the file name directly on GitHub. Alternatively, if you would like to access a copy of the notebook and execute it yourself, then proceed to the  **Quick Start**  section below.

---
### :zap: Quick Start
<p align="center">
<img src="https://c.tenor.com/qUoZaWUg4UsAAAAC/football-player-juggling.gif" height="200">
</p>

**:page_facing_up: Document Information :**
- **Code :** 
1. Linear Poisson Regression Model : **Code_Reg_Poiss.py**
2. Linear Negative Binomial Regression Model : **Code_Reg_NB.py** 
3. Non-Linear Poisson Regression Model : **Code_DNN.py**
- **Data Set :** 
1. Clean Dataset for Model : **model_data.csv**
2. Data for Betting Model Simulation : **betting_data.csv**
3. Variables explanation : **variables.docx** 

**:wrench: Installation Guide**

The code is written in Python and stored as *.ipynb* file. Easiest way to run a python file is through <font color ="green">**Anaconda**</font>. Download and Install it [here](https://www.anaconda.com/products/distribution).

After completing the installation, open _Anaconda-Navigator_ and select _Launch_ on the _JupyterLab_ pane or the _Notebook_ pane(highlighted in the image below). If not installed, please _Install_ and _Launch_.
<img src="https://miro.medium.com/max/1400/1*CrzFvh-ha0mkhUrA3q786A.png">

We use the package ***Keras*** which needs to be additionally installed using the code below in terminal.
TensorFlow and Keras require _Python 3.6+ (Python 3.8 requires TensorFlow 2.2+)_ , and the _latest version of pip_. You can determine the version of Python installed on your computer by running the following command:
```
python3 --version
```
Run the following command to ensure that the latest version of pip is installed:
```
pip install --upgrade pip
```
To install TensorFlow for CPU and GPU processors, run the following command:
```
pip install tensorflow
```
Output should be similar to:
```
Name: tensorflow
Version: 2.2.0
Summary: TensorFlow is an open source machine learning framework for everyone.
Home-page: https://www.tensorflow.org/
Author: Google Inc.
Author-email: packages@tensorflow.org
License: Apache 2.0
Location: c:\python38\lib\site-packages
Requires: google-pasta, gast, six, protobuf, tensorboard, h5py, termcolor, absl-py, opt-einsum, wrapt, grpcio, keras-preprocessing, tensorflow-estimator, numpy, astunparse, wheel, scipy
Required-by:
```
This will install keras and many other libraries, including numpy, tensorflow, etc. The command will take some time to download and install all the relevant packages.
> Make sure you press y–(Yes) when asked to continue.

Next, you can clone this GitHub repository onto your local machine. On GitHub, navigate to the repository, select the green _Code_ button, and then select the clipboard button beside the link to copy the repo link (highligthed in the image below)
<img src="https://www.w3schools.com/git/img_github_clone_url.png">
Then open a terminal window on your local machine and navigate to the location where you want to save the repository. Then type  _git clone_  and paste the URL copied earlier, and enter the command.
```
git clone <repository_URL>
```
Return to the  Jupyter Notebook  window launched previously, click on the _Upload_ in the top right corner of the window, and navigate to the newly created project folder. Open the folder and then select the _.ipynb_ file located in this folder to open the codes. 

or alternatively,

Return to the _JupyterLab_ window launched previously, click on the folder icon in the top left corner of the window, and navigate to the newly created project folder. Then double-click on the _.ipynb_ file located in this folder to open the Jupyter Notebook.

----
<font size=5>**:warning: Note :clock5:**</font> 
Each code takes different times to run as follows
| Code	 |  ~ Run Time |
|:-------| :---:|
| Code_Reg_Poiss.py | 1 min
| Code_Reg_NB.py | 3 min 20 sec |
| Code_DNN.py |10 min 40 sec |
---
### :black_nib: Preparation 
**Reading the Data Set**
Every code notebook has a path variable as shown below to set the directory of the data set. Prefix the location of the data set on your PC to /.
```python
# Importing Dataset
path = '/'
df = pd.read_csv(path + 'model_data.csv')
```
**Load the packages**
Most of the packages are pre installed during Anaconda installation. If any package is not  installed on your PC, please follow the steps by replacing the package name with the required package.
```
conda install -c conda-forge <package_name>
pip install <package_name>
```
You can run the whole file by pressing _F5_ button or run selected block of cells, using _F9_.

---
### :mag_right: Exploratory Data Analysis
Relationship between variables using a pairs plot
<img src="https://github.com/MeghashreeRao/UCD_Final_Project/blob/main/Images/pairs_plot.png?raw=true">
Variables were selected mainly based on correlation values.
<img src="https://github.com/MeghashreeRao/UCD_Final_Project/blob/main/Images/correlation_plot.png?raw=true">

---
### :mortar_board: Model Results
Table below shows the Ranked Probability Score(RPS) Score used to measure the football match outcome with different Machine Learning model.
Method | RPS of Our Model | RPS Bookies Model| RPS Difference
:---:|:---:|:---:|:---:
Poisson Regression|0.2016| 0.1992|0.0025
Negative Binomial| 0.2158| 0.1992|0.016
Poisson Neural Network|0.2161|0.1992|0.017

Simplest Model, the Poisson Regression Linear Model performed well with lowest RPS Difference. This model was used to simulate Betting results.

---
### :money_with_wings: Betting Results
Our Betting Simulation Model is built taking into consideration 3 things mainly, that no bet can be placed twice on the same match, Risk and Ratio values.

Optimal Ratio (ratio of estimated probability to bookmakers probability) and Risk (risk of betting) values are in the range [1.17, 1.23] and [0.4, 0.45], respectively. For a €5 wager per bet, the overall profit from this strategy is in the range of €43 - €67.  Similarly, by doubling the wager to €10 per bet, we obtain a profit in the range of €83 - €235.
<img src="https://github.com/MeghashreeRao/UCD_Final_Project/blob/main/Images/Result2.png?raw=true">

Over the weeks of 6 to 38, with the Ratio = 1.17 and Risk=0.4 we make a profit of approximately €67 as shown in the betting simulation below.
<img src="https://github.com/MeghashreeRao/UCD_Final_Project/blob/main/Images/Result1.png?raw=true">

----
### :computer: Code Contributors

<a href="https://github.com/KurtDarmanin"><img src="https://avatars.githubusercontent.com/u/93616246?v=4" width="150"></a>
<a href="https://github.com/MeghashreeRao"><img src="https://avatars.githubusercontent.com/u/63202493?s=400&u=5f83edcdd5d15656ad42759ca39ef3f4d964c200&v=4" width="150"></a>

