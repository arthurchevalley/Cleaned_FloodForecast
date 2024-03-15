# FloodForecast
Flood Forecasting using multiple water levels along a river in Korea. In addition, weather information, such as temperature, precipitation, RH, pressure and wind speed.
It addresses using multiple recurrent neural networks such as LSTM, GRU and encoder-decoder architecture. In addition, multiple attention mechanisms are compared in the encoder-decoder architecture.


## Introduction

This project aims at getting familiar with recurrent neural networks for a given real-life scenario. As this is just developed as a toy example, no hyper-parameters tuning nor   in-depth analysis have been conducted. In addition, the use of [lightning library]([https://www.google.com](https://lightning.ai/)) is investigated. This library allows to boost [PyTorch](https://pytorch.org/) learning and provides a framework similar to [Keras framework](https://keras.io/).

## Dataset

The dataset is made from official data of Korean government. The measuring station are four bridges located around the town of [Yeoju](https://www.google.com/maps/place//@37.2635254,127.478696,11.11z/data=!4m4!1m3!11m2!2s4ysh5WVoRwG3AOzuPy9Jgw!3e3?authuser=0&entry=ttu) as shown in the following picture. The precipitations are recorded at the same place.

<img width="188" alt="bridges" src="https://github.com/arthurchevalley/FloodForecast/assets/62807485/bf754832-69f3-41a9-b326-3c3d17684bc9">

The data used are sampled on an hourly basis from 22.02.2012 to 01.06.2023. Then the first 75% of those data are used for training while the remaining 25% are used for testing.
Before any usage, the data are normalised using a min-max normalisation for each type of data. 
Indeed, those data are the following:

<table>
  <thead>
    <tr>
      <th colspan="2">Bridge 1 (furthest downstream) </th>
      <th colspan="2">Bridge 2 </th>
      <th colspan="2">Bridge 3 </th>
      <th colspan="2">Bridge 4 (furthest upstream)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Water Level</td>
      <td>Precipitation</td>
      <td>Water Level</td>
      <td>Precipitation</td>
      <td>Water Level</td>
      <td>Precipitation</td>
      <td>Water Level</td>
      <td>Precipitation</td>
    </tr>
  </tbody>
</table>

All wheater data are recorded at <a href="https://www.google.com/maps/place/Icheon,+Gyeonggi,+Cor%C3%A9e+du+Sud/@37.6172742,126.1642664,8z/data=!3m1!4b1!4m6!3m5!1s0x3564a61400916683:0x598fcda12914e460!8m2!3d37.2097769!4d127.4810494!16zL20vMDN2NnAx?entry=ttu">Icheon</a>. Even though it is not in the same city as the other measure, it will not be perfect. However, the city being relatively close by, it should be usable data.
<table>
  <thead>
    <tr>
      <th>Relative Humidity</th>
      <th>Pressure</th>
      <th>Temperature</th>
      <th>Wind Speed</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>RH (%) </td>
      <td>Sea Level Pressure [hPa]</td>
      <td>Temperature in Celsius Degrees</td>
      <td>Wind speed in [m/s]</td>
    </tr>
  </tbody>
</table>

## Models

### LSTM and GRU layers
The two first models are simple LSTM and GRU layers as depicted in the following images from WikiPedia. For all models, the number of hidden layers is set to 256 and two units are used. 
<table>
  <thead>
    <tr>
      <td>LSTM Cell</td>
      <td>GRU Cell</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <img src="https://github.com/arthurchevalley/FloodForecast/assets/62807485/15f4de1c-fb48-4b37-961f-668c5fcb97a8" alt="LSTM Cell" title="LSTM Cell" style="width:66%">
      </td>
      <td>
        <img src="https://github.com/arthurchevalley/FloodForecast/assets/62807485/84f1e5da-68ca-4008-8090-f614d51aa086" alt="GRU Cell" title="GRU Cell" style="width:33%">
      </td>
    </tr>
  </tbody>
</table>

When looking at the extended results of the [LSTM Model](flood/LSTM_results.md) and the [GRU Model](flood/GRU_results.md) one can see that both models are achieving similar performances. First, adding the weather data points is detrimental as the models are not generalised and lead to a large overfitting. 


### Encoder-Decoder architecture
Then, models with an encoder and decoder are investigated. Four models are tested by varying the cells and architecture. First only having LSTM and GRU cells in a classic encoder-decoder model. Then, both models are tested by adding a hand-off layer between the encoder and decoder. The extended results of the [Encoder-Decoder models](flood/ED_HO_results.md) are available.

Finally, models with attention are tested, respectively Luong, Bahdanau or concat attention layers approaches. The extended results of the [Attention models](flood/Attention.md) are available.

