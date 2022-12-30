
# Analysis of Student Exam Performance
## Stephanie Fissel and Katlyn Walter


```python
import pandas as pd
```

## Read in dataset


```python
df = pd.read_csv('/Users/stephaniefissel/Downloads/StudentsPerformance.csv')
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>gender</th>
      <th>race/ethnicity</th>
      <th>parental level of education</th>
      <th>lunch</th>
      <th>test preparation course</th>
      <th>math score</th>
      <th>reading score</th>
      <th>writing score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>female</td>
      <td>group B</td>
      <td>bachelor's degree</td>
      <td>standard</td>
      <td>none</td>
      <td>72</td>
      <td>72</td>
      <td>74</td>
    </tr>
    <tr>
      <th>1</th>
      <td>female</td>
      <td>group C</td>
      <td>some college</td>
      <td>standard</td>
      <td>completed</td>
      <td>69</td>
      <td>90</td>
      <td>88</td>
    </tr>
    <tr>
      <th>2</th>
      <td>female</td>
      <td>group B</td>
      <td>master's degree</td>
      <td>standard</td>
      <td>none</td>
      <td>90</td>
      <td>95</td>
      <td>93</td>
    </tr>
    <tr>
      <th>3</th>
      <td>male</td>
      <td>group A</td>
      <td>associate's degree</td>
      <td>free/reduced</td>
      <td>none</td>
      <td>47</td>
      <td>57</td>
      <td>44</td>
    </tr>
    <tr>
      <th>4</th>
      <td>male</td>
      <td>group C</td>
      <td>some college</td>
      <td>standard</td>
      <td>none</td>
      <td>76</td>
      <td>78</td>
      <td>75</td>
    </tr>
  </tbody>
</table>
</div>



## Group average scores by gender


```python
gender = df.groupby(by=['gender']).mean()
gender
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>math score</th>
      <th>reading score</th>
      <th>writing score</th>
    </tr>
    <tr>
      <th>gender</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>female</th>
      <td>63.633205</td>
      <td>72.608108</td>
      <td>72.467181</td>
    </tr>
    <tr>
      <th>male</th>
      <td>68.728216</td>
      <td>65.473029</td>
      <td>63.311203</td>
    </tr>
  </tbody>
</table>
</div>



## Group average scores by race/ethnicity


```python
race = df.groupby(by=['race/ethnicity']).mean()
race
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>math score</th>
      <th>reading score</th>
      <th>writing score</th>
    </tr>
    <tr>
      <th>race/ethnicity</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>group A</th>
      <td>61.629213</td>
      <td>64.674157</td>
      <td>62.674157</td>
    </tr>
    <tr>
      <th>group B</th>
      <td>63.452632</td>
      <td>67.352632</td>
      <td>65.600000</td>
    </tr>
    <tr>
      <th>group C</th>
      <td>64.463950</td>
      <td>69.103448</td>
      <td>67.827586</td>
    </tr>
    <tr>
      <th>group D</th>
      <td>67.362595</td>
      <td>70.030534</td>
      <td>70.145038</td>
    </tr>
    <tr>
      <th>group E</th>
      <td>73.821429</td>
      <td>73.028571</td>
      <td>71.407143</td>
    </tr>
  </tbody>
</table>
</div>



## Group average scores by parental level of education


```python
edu = df.groupby(by=['parental level of education']).mean()
edu
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>math score</th>
      <th>reading score</th>
      <th>writing score</th>
    </tr>
    <tr>
      <th>parental level of education</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>associate's degree</th>
      <td>67.882883</td>
      <td>70.927928</td>
      <td>69.896396</td>
    </tr>
    <tr>
      <th>bachelor's degree</th>
      <td>69.389831</td>
      <td>73.000000</td>
      <td>73.381356</td>
    </tr>
    <tr>
      <th>high school</th>
      <td>62.137755</td>
      <td>64.704082</td>
      <td>62.448980</td>
    </tr>
    <tr>
      <th>master's degree</th>
      <td>69.745763</td>
      <td>75.372881</td>
      <td>75.677966</td>
    </tr>
    <tr>
      <th>some college</th>
      <td>67.128319</td>
      <td>69.460177</td>
      <td>68.840708</td>
    </tr>
    <tr>
      <th>some high school</th>
      <td>63.497207</td>
      <td>66.938547</td>
      <td>64.888268</td>
    </tr>
  </tbody>
</table>
</div>



## Group average scores by lunch status


```python
lunch = df.groupby(by=['lunch']).mean()
lunch
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>math score</th>
      <th>reading score</th>
      <th>writing score</th>
    </tr>
    <tr>
      <th>lunch</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>free/reduced</th>
      <td>58.921127</td>
      <td>64.653521</td>
      <td>63.022535</td>
    </tr>
    <tr>
      <th>standard</th>
      <td>70.034109</td>
      <td>71.654264</td>
      <td>70.823256</td>
    </tr>
  </tbody>
</table>
</div>



## Group average scores by test preparation course status


```python
prep = df.groupby(by=['test preparation course']).mean()
prep
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>math score</th>
      <th>reading score</th>
      <th>writing score</th>
    </tr>
    <tr>
      <th>test preparation course</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>completed</th>
      <td>69.695531</td>
      <td>73.893855</td>
      <td>74.418994</td>
    </tr>
    <tr>
      <th>none</th>
      <td>64.077882</td>
      <td>66.534268</td>
      <td>64.504673</td>
    </tr>
  </tbody>
</table>
</div>




```python
import plotly.express as px
```

## Combine all factors of scores into one dataframe


```python
df['total score'] = df['math score']+df['reading score']+df['writing score']
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>gender</th>
      <th>race/ethnicity</th>
      <th>parental level of education</th>
      <th>lunch</th>
      <th>test preparation course</th>
      <th>math score</th>
      <th>reading score</th>
      <th>writing score</th>
      <th>total score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>female</td>
      <td>group B</td>
      <td>bachelor's degree</td>
      <td>standard</td>
      <td>none</td>
      <td>72</td>
      <td>72</td>
      <td>74</td>
      <td>218</td>
    </tr>
    <tr>
      <th>1</th>
      <td>female</td>
      <td>group C</td>
      <td>some college</td>
      <td>standard</td>
      <td>completed</td>
      <td>69</td>
      <td>90</td>
      <td>88</td>
      <td>247</td>
    </tr>
    <tr>
      <th>2</th>
      <td>female</td>
      <td>group B</td>
      <td>master's degree</td>
      <td>standard</td>
      <td>none</td>
      <td>90</td>
      <td>95</td>
      <td>93</td>
      <td>278</td>
    </tr>
    <tr>
      <th>3</th>
      <td>male</td>
      <td>group A</td>
      <td>associate's degree</td>
      <td>free/reduced</td>
      <td>none</td>
      <td>47</td>
      <td>57</td>
      <td>44</td>
      <td>148</td>
    </tr>
    <tr>
      <th>4</th>
      <td>male</td>
      <td>group C</td>
      <td>some college</td>
      <td>standard</td>
      <td>none</td>
      <td>76</td>
      <td>78</td>
      <td>75</td>
      <td>229</td>
    </tr>
  </tbody>
</table>
</div>


