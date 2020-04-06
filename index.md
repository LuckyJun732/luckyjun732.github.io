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

<br>
Sumber : https://github.com/nicodv/kmodes bagian csv<br>

<pre>import numpy as np
from kmodes.kmodes import KModes

# random categorical data
data = np.random.choice(20, (100, 10))

km = KModes(n_clusters=4, init='Huang', n_init=5, verbose=1)

clusters = km.fit_predict(data)

# Print the cluster centroids
print(km.cluster_centroids_)</pre>

<pre>import numpy as np
from kmodes.kprototypes import KPrototypes

syms = np.genfromtxt('soybeans.csv', dtype=str, delimiter=',')[:, 0]
X = np.genfromtxt('soybeans.csv', dtype=object, delimiter=',')[:, 1:]
X[:, 0] = X[:, 0].astype(float)

kproto = KPrototypes(n_clusters=2, init='Cao', verbose=2)
clusters = kproto.fit_predict(X, categorical=[9, 2])

print(kproto.cluster_centroids_)
print(kproto.cost_)
print(kproto.n_iter_)

for s, c in zip(syms, clusters):
    print("Symbol: {}, cluster:{}".format(s, c))</pre>


<p style="font-size:11px">Berasal dari<a href="https://www.google.co.uk/">Google UK</a></p>
<!-- Remove above link if you don't want to attibute -->
