### Attention results
**Water levels & Precipitations**

The first possible improvement is to give more data to the model. This is done by providing the precipitation height of every water station.
Doing so doubles the amount of data while still predicting only the water level of the last station. All models were used using a fused loss. Not that the Concat attention was trained longer whereas the other attention layers overfit when trained longer
<table>
  <thead>
    <tr>
      <th>Training length</th>
      <th>Attention</th>
      <th>Phase</th>
      <th>MAE</th>
      <th>MSE</th>
      <th>NSE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="6">200</td>
      <td rowspan="2">Dot</td>
      <td> Training</td>
      <td>0.22</td>
      <td>0.26</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.18</td>
      <td>0.20</td>
    </tr>
    <tr>
      <td rowspan="2">Luong</td>
      <td> Training</td>
      <td>0.12</td>
      <td>0.19</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.12</td>
      <td>0.15</td>
    </tr>
    <tr>
      <td rowspan="2">Concat</td>
      <td> Training</td>
      <td>0.40</td>
      <td>0.43</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.38</td>
      <td>0.39</td>
    </tr>
    <tr>
      <td rowspan="6">300</td>
      <td rowspan="2">Dot</td>
      <td> Training</td>
      <td>0.10</td>
      <td>0.16</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.05</td>
      <td>0.08</td>
    </tr>
    <tr>
      <td rowspan="2">Luong</td>
      <td> Training</td>
      <td>0.38/td>
      <td>0.42</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.37</td>
      <td>0.38</td>
    </tr>
    <tr>
      <td rowspan="2">Concat</td>
      <td> Training</td>
      <td>0.14</td>
      <td>0.19</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.13</td>
      <td>0.16</td>
    </tr>
    <tr>
      <td rowspan="6">400</td>
      <td rowspan="2">Dot</td>
      <td> Training</td>
      <td>--</td>
      <td>--</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>--</td>
      <td>--</td>
    </tr>
    <tr>
      <td rowspan="2">Luong</td>
      <td> Training</td>
      <td>--</td>
      <td>--</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>-</td>
      <td>--</td>
      <td>--</td>
    </tr>
    <tr>
      <td rowspan="2">Concat</td>
      <td> Training</td>
      <td>0.12</td>
      <td>0.17</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.09</td>
      <td>0.11</td>
    </tr>
  </tbody>
</table>




 **Water levels, precipitations and weather record**
<table>
  <thead>
    <tr>
      <th>Training length</th>
      <th>Attention</th>
      <th>Phase</th>
      <th>MAE</th>
      <th>MSE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="6">100</td>
      <td rowspan="2">Dot</td>
      <td> Training</td>
      <td>0.10</td>
      <td>0.16</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.06</td>
      <td>0.09</td>
    </tr>
    <tr>
      <td rowspan="2">Luong</td>
      <td> Training</td>
      <td>0.11</td>
      <td>0.19</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.08</td>
      <td>0.14</td>
    </tr>
    <tr>
      <td rowspan="2">Concat</td>
      <td> Training</td>
      <td>0.11</td>
      <td>0.19</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.08</td>
      <td>0.14</td>
    </tr>
    <tr>
      <td rowspan="6">200</td>
      <td rowspan="2">Dot</td>
      <td> Training</td>
      <td>0.15</td>
      <td>0.20</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.10</td>
      <td>0.12</td>
    </tr>
    <tr>
      <td rowspan="2">Luong</td>
      <td> Training</td>
      <td>--</td>
      <td>--</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>--</td>
      <td>--</td>
    </tr>
    <tr>
      <td rowspan="2">Concat</td>
      <td> Training</td>
      <td>0.10</td>
      <td>0.16</td>
    </tr>
    <tr>
      <td> Validation</td>
      <td>0.02</td>
      <td>0.06</td>
    </tr>
  </tbody>
</table>
