Book Recommendation System
-------------------------------
This is a Content-based book recommendation system which recommends the top 5 similar books for each book.

Installation
-------------------------------

### Data Information

* Clone this repo to your computer.
* Get into the folder using `cd Recommendation_System`.
* Get the raw data information:
    *  Switch into the `Original_dataset` directory using `cd Original_dataset`.
    *  You should see two raw dataset in csv file called `items.csv` and `transactions.csv`.
    *  You can get more information on [Data Mining Cup 2021](https://www.data-mining-cup.com/dmc-2021/) website.

### Install the requirements
* Install the requirements using `pip install -r requirements.txt`
    * Make sure you use Python3.
    * Recommendation: use a virtual environment for this project.

Data Preprocessing
-------------------------------
* Run `mkdir Annotated_dataset` on home directory to create a directory for processed data.
* Switch into the directory that contains multiple jupyter notebooks for data processing using `cd Data_preprocessing`.
* 1. Use `Data_Understanding.ipynb` to overview the raw data.
* 2. Extract features from `items.csv`
    * 1. Language: This `Language_Detection.ipynb` notebook generates the language of each book based on each item's title
       * This will create `items_lang.csv` in the `Annotated_dataset` folder.    
