# Appliances-Energy-Prediction
This project deals with predicting appliances energy consumption of a particular household in Belgium based on the temperature and humidity levels of different rooms in the building and the weather reports in the area over a period of 4.5 months.

The data set is at 10 min for about 4.5 months. The house temperature and humidity conditions were monitored with a ZigBee wireless sensor network. Each wireless node transmitted the temperature and humidity conditions around 3.3 min. Then, the wireless data was averaged for 10 minutes periods. The energy data was logged every 10 minutes with m-bus energy meters. Weather from the nearest airport weather station (Chievres Airport, Belgium) was downloaded from a public data set from Reliable Prognosis (rp5.ru) and merged together with the experimental data sets using the date and time column. Two random variables have been included in the data set for testing the regression models and to filter out non-predictive attributes (parameters).

## Dataset Link
- http://archive.ics.uci.edu/ml/datasets/Appliances+energy+prediction
## Dataset Information
- Number of instances: 19,735
- Number of attributes: 29