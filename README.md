# Cryptocurrency Trading!
#### *Claudia Lobato Jimenez*
This project was completed  as part of the final project upon completing the Le Wagon data science bootcamp (batch #699)
## Description
We created a Deep learning model to predict the direction of next day's bitcoin price, using sentiment analysis of social media posts and technical price and economic features.
In addition to the model, we created a user interfase that can be found here: https://crypto-demo-i66qec4k3a-nw.a.run.app/
Note that __the 'predict' page may not be updated__ as I am doing some maintainance on the scrapping modules and it is currently not life. We will update the page once it is life to recomend!

## The DATA
 - We pulled data from "Finantial Model API"
 - Scrapped data from Reddit
 - Pulled posts from the Twitter API

### Sentiment Analysis 
We first did __data preprocesing__ for NLP where we removed numbers and stopwords as they don't carry predictive power, adapted capital letters and tokenized the words to be used in a model. 
As the posts did not have any classification it was hard to train the model, so we used a transfer learning model from Hugging Face trained on twitter posts to obtain a sentiment score.

### Price Feature 
We used moving averages and other features you can find in the code to analyse the previous performance of bitcoin. 
We also had to ensure stationarity in order to use the data to predict.

## The model
WE used an LSTM model, with the inputs mentioned above obtaining as an output the price of bitcoin for tomorrow. When evaluating the model we realized it was overestimating the change of price, however the direction was correct, and so we changed it to a classification problem, where the output is whether the price was going up or down. 

## Going forward
Due to the time constraint we had when initially creating the project, I am currently working on cleaning the code. 
In addition I am working on making the code work life with Google cloud

# Startup the project
Note that if you clone the repo you will not be able to run the website directly, you will first need to scrape the data, with the available code. 

The initial setup.

Create virtualenv and install the project:
```bash
sudo apt-get install virtualenv python-pip python-dev
deactivate; virtualenv ~/venv ; source ~/venv/bin/activate ;\
    pip install pip -U; pip install -r requirements.txt
```

Unittest test:
```bash
make clean install test
```

Check for cryptocurrency_trading in gitlab.com/{group}.
If your project is not set please add it:

- Create a new project on `gitlab.com/{group}/cryptocurrency_trading`
- Then populate it:

```bash
##   e.g. if group is "{group}" and project_name is "cryptocurrency_trading"
git remote add origin git@github.com:{group}/cryptocurrency_trading.git
git push -u origin master
git push -u origin --tags
```

Functionnal test with a script:

```bash
cd
mkdir tmp
cd tmp
cryptocurrency_trading-run
```

# Install

Go to `https://github.com/{group}/cryptocurrency_trading` to see the project, manage issues,
setup you ssh public key, ...

Create a python3 virtualenv and activate it:

```bash
sudo apt-get install virtualenv python-pip python-dev
deactivate; virtualenv -ppython3 ~/venv ; source ~/venv/bin/activate
```

Clone the project and install it:

```bash
git clone git@github.com:{group}/cryptocurrency_trading.git
cd cryptocurrency_trading
pip install -r requirements.txt
make clean install test                # install and test
```
Functionnal test with a script:

```bash
cd
mkdir tmp
cd tmp
cryptocurrency_trading-run
```



