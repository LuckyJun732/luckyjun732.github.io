## K-Modes & K-Prototype

---

### K-Modes Clustering
Tipe Data Kategorical<br>
Sumber : https://archive.ics.uci.edu/ml/datasets/bank+marketing<r>
<pre># supress warnings
import warnings
warnings.filterwarnings('ignore')

# Importing all required packages
import numpy as np
import pandas as pd

# Data viz lib
import matplotlib.pyplot as plt
import seaborn as sns
%matplotlib inline
from matplotlib.pyplot import xticks</pre>

Menjalankan scrit :<br>
<pre>bank = pd.read_csv('../input/bankmarketing.csv')</pre>
<pre>bank.head()</pre>

Import Kolom Kategorikal :<br>
<pre>bank_cust = bank[['age','job', 'marital', 'education', 'default', 'housing', 'loan','contact','month','day_of_week','poutcome']]</pre>
<pre>bank_cust.head()</pre>

Output :<br>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>job</th>
      <th>marital</th>
      <th>education</th>
      <th>default</th>
      <th>housing</th>
      <th>loan</th>
      <th>contact</th>
      <th>month</th>
      <th>day_of_week</th>
      <th>poutcome</th>
      <th>age_bin</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>housemaid</td>
      <td>married</td>
      <td>basic.4y</td>
      <td>no</td>
      <td>no</td>
      <td>no</td>
      <td>telephone</td>
      <td>may</td>
      <td>mon</td>
      <td>nonexistent</td>
      <td>50-60</td>
    </tr>
    <tr>
      <th>1</th>
      <td>services</td>
      <td>married</td>
      <td>high.school</td>
      <td>unknown</td>
      <td>no</td>
      <td>no</td>
      <td>telephone</td>
      <td>may</td>
      <td>mon</td>
      <td>nonexistent</td>
      <td>50-60</td>
    </tr>
    <tr>
      <th>2</th>
      <td>services</td>
      <td>married</td>
      <td>high.school</td>
      <td>no</td>
      <td>yes</td>
      <td>no</td>
      <td>telephone</td>
      <td>may</td>
      <td>mon</td>
      <td>nonexistent</td>
      <td>30-40</td>
    </tr>
    <tr>
      <th>3</th>
      <td>admin.</td>
      <td>married</td>
      <td>basic.6y</td>
      <td>no</td>
      <td>no</td>
      <td>no</td>
      <td>telephone</td>
      <td>may</td>
      <td>mon</td>
      <td>nonexistent</td>
      <td>30-40</td>
    </tr>
    <tr>
      <th>4</th>
      <td>services</td>
      <td>married</td>
      <td>high.school</td>
      <td>no</td>
      <td>no</td>
      <td>yes</td>
      <td>telephone</td>
      <td>may</td>
      <td>mon</td>
      <td>nonexistent</td>
      <td>50-60</td>
    </tr>
  </tbody>
</table>



<img src="images/JumlahUserFB.png?raw=true"/>
Data ranking merupakan data Ordinal.
<img src="images/JumlahUserFB2.png?raw=true"/>
Data pengguna dalam satuan jutaan. Rata-rata yang diperoleh sebesar 262,35 yang tersebar di 10 negara.<br>Sedangkan untuk standar Deviasi-nya sebesar 69,05
<r><img src="images/JumlahUserFB3.png?raw=true"/>

---
<img src="images/JumlahUserFB4.png?raw=true"/>

---
<p style="font-size:11px">Data ini saya dapatkan dari <a href="https://sproutsocial.com/insights/new-social-media-demographics/">sproutsocial</a></p>
<!-- Remove above link if you don't want to attibute -->
