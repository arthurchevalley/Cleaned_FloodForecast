### LSTM
**Water levels**

The first step is trying to predict the water level of one bridge given the water levels of three upstream stations.
<table>
  <thead>
    <tr>
      <th>Training length (Epochs)</th>
      <th>Phase</th>
      <th>Mean Absolute Error</th>
      <th>Mean Squared Error</th>
      <th>NSE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="2">100</td>
      <td> Training</td>
      <td>0.02</td>
      <td>0.03</td>
      <td>0.95</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.03</td>
      <td>0.06</td>
      <td>0.81</td>
    </tr>
    <tr>
      <td rowspan="2">175</td>
      <td> Training</td>
      <td>0.01</td>
      <td>0.02</td>
      <td>0.96</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.03</td>
      <td>0.06</td>
      <td>0.79</td>
    </tr>
  </tbody>
</table>

Looking at the previous table, the results are rather good as the errors are small and the NSE score is close to the maximum. 
However, when training length increases, some overfitting can be seen as the training performances are increased but the validation decreases.

**Water levels & Precipitations**

The first possible improvement is to give more data to the model. This is done by providing the precipitation height of every water station.
Doing so doubles the amount of data while still predicting only the water level of the last station.
<table>
  <thead>
    <tr>
      <th>Training length (Epochs)</th>
      <th>Phase</th>
      <th>Mean Absolute Error</th>
      <th>Mean Squared Error</th>
      <th>NSE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="2">100</td>
      <td> Training</td>
      <td>0.02</td>
      <td>0.03</td>
      <td>0.95</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.03</td>
      <td>0.06</td>
      <td>0.76</td>
    </tr>
    <tr>
      <td rowspan="2">175</td>
      <td> Training</td>
      <td>0.01</td>
      <td>0.02</td>
      <td>0.97</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.03</td>
      <td>0.06</td>
      <td>0.82</td>
    </tr>
    <tr>
      <td rowspan="2">250</td>
      <td> Training</td>
      <td>0.01</td>
      <td>0.02</td>
      <td>0.98</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.03</td>
      <td>0.06</td>
      <td>0.81</td>
    </tr>
  </tbody>
</table>




 **Water levels, precipitations and weather record**

<table>
  <thead>
    <tr>
      <th>Training length (Epochs)</th>
      <th>Phase</th>
      <th>Mean Absolute Error</th>
      <th>Mean Squared Error</th>
      <th>NSE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="2">100</td>
      <td> Training</td>
      <td>0.02</td>
      <td>0.02</td>
      <td>0.96</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.04</td>
      <td>0.08</td>
      <td>0.66</td>
    </tr>
    <tr>
      <td rowspan="2">250</td>
      <td> Training</td>
      <td>0.01</td>
      <td>0.01</td>
      <td>0.99</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.03</td>
      <td>0.07</td>
      <td>0.75</td>
    </tr>
    <tr>
      <td rowspan="2">350</td>
      <td> Training</td>
      <td>0.01</td>
      <td>0.01</td>
      <td>1.0</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.03</td>
      <td>0.06</td>
      <td>0.78</td>
    </tr>
  </tbody>
</table>
