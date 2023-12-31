# Stock Price Prediction using NLP and Time Series Analysis

## Table of Contents
1. [Introduction](#introduction)
   1.1 [Problem Statement](#problem-statement)
   1.2 [Data Exploration](#data-exploration)
2. [Data Pre-processing](#data-pre-processing)
   2.1 [Model Selection](#model-selection)
   2.2 [Approach 1](#approach-1)
   2.3 [Approach 2](#approach-2)
   2.4 [Approach 3](#approach-3)
   2.5 [Approach 4](#approach-4)
3. [Optimization](#optimization)
   3.1 [Manual Fine Tuning](#manual-fine-tuning)
   3.2 [Keras Random Search Tuning](#keras-random-search-tuning)
4. [Evaluation](#evaluation)
   4.1 [Single Input Approach](#single-input-approach)
   4.2 [Multiple Input Approach](#multiple-input-approach)
5. [Application](#application)

---

## Introduction

### Problem Statement

The stock market is one of the most important ways for companies to raise money, along with debt markets, which are generally more imposing but do not trade publicly. This project aims to predict stock price movements by analyzing historical news headlines using Natural Language Processing (NLP). News headlines can provide valuable information about a company or industry and can give insight into the overall economic and political climate, which can affect stock prices.

![Figure 1](https://drive.google.com/uc?export=view&id=1dhGlW81o-HLKFw3_VG9LyouAqKEG5Azw)
*Figure 1: Example of data*

### Data Exploration

The data sources for this project include daily stock price indices obtained from the Dow Jones Industrial Average (DJIA) and historical news headlines from Reddit WorldNews. DJIA is a stock market index of 30 prominent companies listed on stock exchanges in the United States. The data covers the period from 2008-08-08 to 2016-07-01, enabling analysis of stock performance during the 2008-2009 financial crisis.

![Figure 2](https://drive.google.com/uc?export=view&id=1neh8C7aM2m4l-jJk2TaBRS90TwPRQ_TZ)
*Figure 2: DJIA Historical Line Chart*

---

## Data Pre-processing

### Model Selection

To address the problem, Recurrent Neural Network (RNN) models, specifically Long Short-Term Memory (LSTM), were selected due to their ability to capture sequential data patterns. Different approaches were explored for handling text and numerical features.

#### Approach 1

Approach 1 utilizes text features. Glove Dictionary is used for word embedding, followed by an LSTM layer for handling long-term dependencies between words.

![Figure 3](https://drive.google.com/uc?export=view&id=1qV-aAPEyf4f0327rUGF5tMlHPdCqo1HS)
*Figure 3: Approach 1 Architecture*

#### Approach 2

Approach 2 focuses solely on numerical features. It employs LSTM layers to process sequential information in time series data.

![Figure 4](https://drive.google.com/uc?export=view&id=1bwZwQpUwLvOOplePpD7CLbWsA8C444u_)
*Figure 4: Approach 2 Architecture*

#### Approach 3

Approach 3 combines text features with sentiment scores generated by a Pre-trained Sentiment Intensity Analyzer (SIA). These features are then merged with numerical data.

![Figure 5](https://drive.google.com/uc?export=view&id=1DEMWyHSXk1LvKI709T5ljRSy0sL6_qn6)
*Figure 5: Approach 3 Architecture*

#### Approach 4

Approach 4 combines the strengths of Approach 1 and Approach 2 through parallel branches and a concatenate layer.

![Figure 6](https://drive.google.com/uc?export=view&id=1fPRvDMRVs4mYyHDBxd22Qa9bQimT_CYW)
*Figure 6: Approach 4 Architecture*

---

## Optimization

Optimization was performed using manual fine-tuning and Keras Random Search Tuning.

### Manual Fine Tuning

Manual fine-tuning involved adjusting hyperparameters, including learning rate, hidden layers, dropout layers, activation functions, and the number of nodes.

![Figure 7](https://drive.google.com/uc?export=view&id=1dJezpGOVLUQPmz09cdghXT4TBTRDwke5)
*Figure 7: Train & Validation Loss of Best Model from Random Search*

### Keras Random Search Tuning

Random search tuning utilized the Keras Random Search Tuner to explore various hyperparameters within specified ranges.

---

## Evaluation

Evaluation metrics include test loss and the comparison between real and predicted stock price movements.

### Single Input Approach

#### Approach 1

![Figure 8a](https://drive.google.com/uc?export=view&id=156EuYmaBPvVG-HIJnivNiuKw8OtXwHfA)
![Figure 8b](https://drive.google.com/uc?export=view&id=1zfvUMC7IKYuBv8vX6aGR-1ePRbQ_LZvM)

#### Approach 2

![Figure 9a](https://drive.google.com/uc?export=view&id=110D_fDnmk-LHEI5B5-gIOnrZQhjQtUV4)
![Figure 9b](https://drive.google.com/uc?export=view&id=1pzadiVTT474fjHSIIPxDAugXc67cWISX)

### Multiple Input Approach

#### Approach 3

![Figure 10a](https://drive.google.com/uc?export=view&id=1Cy-10ijG2pvR4eMggq8SSRbNyebsi6cG)
![Figure 10b](https://drive.google.com/uc?export=view&id=1rQXUtmI__vf-2jtjPyQw_fUwoGfnUMFk)

#### Approach 4

![Figure 11a](https://drive.google.com/uc?export=view&id=1s8dO4uYqO-vo2jitcpc7sFQnsfG9uHBq)
![Figure 11b](https://drive.google.com/uc?export=view&id=1VhihNU4DlSFYSIohxrfU_AVLI2htFLyk)

---

## Application

This model can be applied by investors and companies to make informed decisions in the stock market. It provides insights into stock price movements based on news analysis. Additionally, it has applications in other fields, such as healthcare, where it can analyze news related to health and medical threats.
