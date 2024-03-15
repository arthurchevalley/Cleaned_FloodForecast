### Encoder Decoder handoff LSTM
**Water levels**

The first step is trying to predict the water level of one bridge given the water levels of three upstream stations.

<table>
  <thead>
    <tr>
      <th>Training length</th>
      <th>Losses</th>
      <th>Cell</th>
      <th>Phase</th>
      <th>MAE</th>
      <th>MSE</th>
      <th>NSE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="8">100</td>
      <td rowspan="4">Separated</td>
      <td rowspan="2">LSTM</td>
      <td> Training</td>
      <td>0.10</td>
      <td>0.17</td>
      <td>0.96</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.03</td>
      <td>0.06</td>
      <td>0.75</td>
    </tr>
    <tr>
      <td rowspan="2">GRU</td>
      <td> Training</td>
      <td>0.10</td>
      <td>0.17</td>
      <td>1.00</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.03</td>
      <td>0.06</td>
      <td>0.81</td>
    </tr>
    <tr>
      <td rowspan="4">Fused</td>
      <td rowspan="2">LSTM</td>
      <td> Training</td>
      <td>0.10</td>
      <td>0.17</td>
      <td>0.93</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.03</td>
      <td>0.06</td>
      <td>0.83</td>
    </tr>
    <tr>
      <td rowspan="2">GRU</td>
      <td> Training</td>
      <td>0.10</td>
      <td>0.17</td>
      <td>0.91</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.02</td>
      <td>0.06</td>
      <td>0.82</td>
    </tr>
  </tbody>
</table>


Looking at the previous table, the results are rather good as the errors are small and the NSE score is close to the maximum. 
However, when training length increases, some overfitting can be seen as the training performances are increased but the validation decreases.

**Water levels & Precipitations**

The first possible improvement is to give more data to the model. This is done by providing the precipitation height of every water station.
Doing so doubles the amount of data while still predicting only the water level of the last station. For this, only the LSTM Cells are shown as better results are achieved. All models were trained for 100 epochs. The handoff layer model is also shown in comparison.
<table>
  <thead>
    <tr>
      <th>Model</th>
      <th>Phase</th>
      <th>MAE</th>
      <th>MSE</th>
      <th>NSE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="2">LSTM Fuse Losses</td>
      <td> Training</td>
      <td>0.10</td>
      <td>0.16</td>
      <td>0.87</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.02</td>
      <td>0.05</td>
      <td>0.84</td>
    </tr>
    <tr>
      <td rowspan="2">LSTM Fuse Losses Handoff</td>
      <td> Training</td>
      <td>0.10</td>
      <td>0.16</td>
      <td>0.88</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.02</td>
      <td>0.05</td>
      <td>0.85</td>
    </tr>
  </tbody>
</table>




 **Water levels, precipitations and weather record**
The second obvious improvement is to give even more data to the model. This is done by providing the weather record of the surrounding area.
Doing so the amount of data is even increased but predicts only the water level of the last station. As for the previous experiment, only the LSTM Cells are shown as better results are achieved and the handoff layer model is compared. However, as more data were used, the models were trained for 180 epochs.
<table>
  <thead>
    <tr>
      <th>Model</th>
      <th>Phase</th>
      <th>MAE</th>
      <th>MSE</th>
      <th>NSE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="2">LSTM Fuse Losses</td>
      <td> Training</td>
      <td>0.10</td>
      <td>0.16</td>
      <td>0.87</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.02</td>
      <td>0.06</td>
      <td>0.83</td>
    </tr>
    <tr>
      <td rowspan="2">LSTM Fuse Losses Handoff</td>
      <td> Training</td>
      <td>0.10</td>
      <td>0.16</td>
      <td>0.84</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.03</td>
      <td>0.06</td>
      <td>0.83</td>
    </tr>
  </tbody>
</table>
