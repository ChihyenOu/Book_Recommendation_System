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
    * Language: This `Language_Detection.ipynb` notebook generates the language of each book based on each item's title
       * This will create `items_inc_lang.csv` in the `Annotated_dataset` folder.
    * Age Identifier: Use `Data_preprocessing_Interest_Age.ipynb` to assign each item an age value
       * This will create `item_inc_lang_age.csv` file which is the final item dataset in the `Annotated_dataset` folder. 
* 3. Process duplicate items for `transaction.csv`
    * Use `Item_Preprocessing.ipynb` to generate the processed dataset `preprocessed_transactions.csv` to the `Annotated_dataset` folder.

Modeling
-------------------------------
This recommendation problem is without user rating, called a content-based recommendation problem.
After finishing data processing, the transaction dataset `preprocessed_transactions.csv` is used to build the relationship between items.
   - This idea is referenced with this conference paper ([Feature weighting in content based recommendation system using social network analysis](https://www.researchgate.net/publication/221022528_Feature_weighting_in_content_based_recommendation_system_using_social_network_analysis)).

* 1. Use `Build_transaction_social_network_data.ipynb` to build a social network.
   * create two dataset that are `transaction_network.csv` and `transaction_network_data_all.csv` to the `Annotated_dataset` folder.
* 2. Train a Logistic Regression model on all features
   * Based on `transaction_network_data_all.csv` dataset, this `Weights_for_features.ipynb` notebook saves the trained model called `finalized_LR_model.sav` to the `Annotated_dataset` folder.
* 3. Recommendation system
