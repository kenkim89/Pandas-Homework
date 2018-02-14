

```python
import pandas as pd
import numpy as np
import os
```


```python
#Save file path to variable
csv_path = os.path.join("Resource", "schools_complete.csv")
csv_path2 = os.path.join("Resource", "students_complete.csv")
```


```python
#Read with Pandas School head
schools_df = pd.read_csv(csv_path)
schools_df = schools_df.rename(columns={
    "name":"school"})
schools_df
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School ID</th>
      <th>school</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
    </tr>
    <tr>
      <th>5</th>
      <td>5</td>
      <td>Wilson High School</td>
      <td>Charter</td>
      <td>2283</td>
      <td>1319574</td>
    </tr>
    <tr>
      <th>6</th>
      <td>6</td>
      <td>Cabrera High School</td>
      <td>Charter</td>
      <td>1858</td>
      <td>1081356</td>
    </tr>
    <tr>
      <th>7</th>
      <td>7</td>
      <td>Bailey High School</td>
      <td>District</td>
      <td>4976</td>
      <td>3124928</td>
    </tr>
    <tr>
      <th>8</th>
      <td>8</td>
      <td>Holden High School</td>
      <td>Charter</td>
      <td>427</td>
      <td>248087</td>
    </tr>
    <tr>
      <th>9</th>
      <td>9</td>
      <td>Pena High School</td>
      <td>Charter</td>
      <td>962</td>
      <td>585858</td>
    </tr>
    <tr>
      <th>10</th>
      <td>10</td>
      <td>Wright High School</td>
      <td>Charter</td>
      <td>1800</td>
      <td>1049400</td>
    </tr>
    <tr>
      <th>11</th>
      <td>11</td>
      <td>Rodriguez High School</td>
      <td>District</td>
      <td>3999</td>
      <td>2547363</td>
    </tr>
    <tr>
      <th>12</th>
      <td>12</td>
      <td>Johnson High School</td>
      <td>District</td>
      <td>4761</td>
      <td>3094650</td>
    </tr>
    <tr>
      <th>13</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
    </tr>
    <tr>
      <th>14</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Students head
students_df = pd.read_csv(csv_path2)
students_df.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Student ID</th>
      <th>name</th>
      <th>gender</th>
      <th>grade</th>
      <th>school</th>
      <th>reading_score</th>
      <th>math_score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Paul Bradley</td>
      <td>M</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>66</td>
      <td>79</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Victor Smith</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>94</td>
      <td>61</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Kevin Rodriguez</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>90</td>
      <td>60</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Dr. Richard Scott</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>67</td>
      <td>58</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Bonnie Ray</td>
      <td>F</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>97</td>
      <td>84</td>
    </tr>
  </tbody>
</table>
</div>




```python
#District head
district_df = pd.merge(schools_df, students_df, on="school")
district_df.head()

```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School ID</th>
      <th>school</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
      <th>Student ID</th>
      <th>name</th>
      <th>gender</th>
      <th>grade</th>
      <th>reading_score</th>
      <th>math_score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>0</td>
      <td>Paul Bradley</td>
      <td>M</td>
      <td>9th</td>
      <td>66</td>
      <td>79</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>1</td>
      <td>Victor Smith</td>
      <td>M</td>
      <td>12th</td>
      <td>94</td>
      <td>61</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>2</td>
      <td>Kevin Rodriguez</td>
      <td>M</td>
      <td>12th</td>
      <td>90</td>
      <td>60</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>3</td>
      <td>Dr. Richard Scott</td>
      <td>M</td>
      <td>12th</td>
      <td>67</td>
      <td>58</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>4</td>
      <td>Bonnie Ray</td>
      <td>F</td>
      <td>9th</td>
      <td>97</td>
      <td>84</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Pass bins
bins = [0,69,100]
bin_names = ['Fail','Pass']
```


```python
#Add bins to summary
district_df["reading_pass"] = pd.cut(district_df["reading_score"],
                                           bins, labels=bin_names)
district_df["math_pass"] = pd.cut(district_df["math_score"],
                                            bins, labels=bin_names)
district_df.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School ID</th>
      <th>school</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
      <th>Student ID</th>
      <th>name</th>
      <th>gender</th>
      <th>grade</th>
      <th>reading_score</th>
      <th>math_score</th>
      <th>reading_pass</th>
      <th>math_pass</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>0</td>
      <td>Paul Bradley</td>
      <td>M</td>
      <td>9th</td>
      <td>66</td>
      <td>79</td>
      <td>Fail</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>1</td>
      <td>Victor Smith</td>
      <td>M</td>
      <td>12th</td>
      <td>94</td>
      <td>61</td>
      <td>Pass</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>2</td>
      <td>Kevin Rodriguez</td>
      <td>M</td>
      <td>12th</td>
      <td>90</td>
      <td>60</td>
      <td>Pass</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>3</td>
      <td>Dr. Richard Scott</td>
      <td>M</td>
      <td>12th</td>
      <td>67</td>
      <td>58</td>
      <td>Fail</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>4</td>
      <td>Bonnie Ray</td>
      <td>F</td>
      <td>9th</td>
      <td>97</td>
      <td>84</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
  </tbody>
</table>
</div>




```python
#District Pass
district_df_passr = district_df.loc[district_df["reading_pass"] == "Pass"]
district_df_passm = district_df.loc[district_df["math_pass"] == "Pass"]
district_df_passm.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School ID</th>
      <th>school</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
      <th>Student ID</th>
      <th>name</th>
      <th>gender</th>
      <th>grade</th>
      <th>reading_score</th>
      <th>math_score</th>
      <th>reading_pass</th>
      <th>math_pass</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>0</td>
      <td>Paul Bradley</td>
      <td>M</td>
      <td>9th</td>
      <td>66</td>
      <td>79</td>
      <td>Fail</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>4</td>
      <td>Bonnie Ray</td>
      <td>F</td>
      <td>9th</td>
      <td>97</td>
      <td>84</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>5</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>5</td>
      <td>Bryan Miranda</td>
      <td>M</td>
      <td>9th</td>
      <td>94</td>
      <td>94</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>6</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>6</td>
      <td>Sheena Carter</td>
      <td>F</td>
      <td>11th</td>
      <td>82</td>
      <td>80</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>8</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>8</td>
      <td>Michael Roth</td>
      <td>M</td>
      <td>10th</td>
      <td>95</td>
      <td>87</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Round 2 digits
def round2(number):
    # Rounds the number
    rounded_number = round(number, 2)
    # Creates a string
    string = str(rounded_number)
    # Returns the string
    return string
```


```python
#District stats
total_students = district_df["name"].count()
total_schools = schools_df["school"].count()
total_budget = schools_df["budget"].sum()
mean_math = district_df["math_score"].mean()
mean_read = district_df["reading_score"].mean()
percent_math = (district_df_passm["math_pass"].count()/district_df["math_pass"].count())*100
percent_reading = (district_df_passr["reading_pass"].count()/district_df["reading_pass"].count())*100
average_pass = (percent_math+percent_reading)/2
```


```python
district_summary=pd.DataFrame({"Total Students": [total_students],
                               "Total Schools": [total_schools],
                               "Total Budget": [total_budget],
                               "Average Math Score":[mean_math],
                               "Average Reading Score":[mean_read],
                               "% Passing Math":[percent_math],
                               "% Passing Reading":[percent_reading],
                               "% Passing Overall":[average_pass]})
district_summary["Average Math Score"] = district_summary["Average Math Score"].map(round2)
district_summary["Average Reading Score"] = district_summary["Average Reading Score"].map(round2)
district_summary["% Passing Math"] = district_summary["% Passing Math"].map(round2)
district_summary["% Passing Reading"] = district_summary["% Passing Reading"].map(round2)
district_summary["% Passing Overall"] = district_summary["% Passing Overall"].map(round2)
district_summary[["Total Students","Total Schools","Total Budget","Average Math Score","Average Reading Score",
                "% Passing Math", "% Passing Reading","% Passing Overall"]]

```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Total Students</th>
      <th>Total Schools</th>
      <th>Total Budget</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>% Passing Overall</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>39170</td>
      <td>15</td>
      <td>24649428</td>
      <td>78.99</td>
      <td>81.88</td>
      <td>74.98</td>
      <td>85.81</td>
      <td>80.39</td>
    </tr>
  </tbody>
</table>
</div>




```python
#District GroupBy
district_group = district_df.groupby(["school", "type"])
district_group.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School ID</th>
      <th>school</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
      <th>Student ID</th>
      <th>name</th>
      <th>gender</th>
      <th>grade</th>
      <th>reading_score</th>
      <th>math_score</th>
      <th>reading_pass</th>
      <th>math_pass</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>0</td>
      <td>Paul Bradley</td>
      <td>M</td>
      <td>9th</td>
      <td>66</td>
      <td>79</td>
      <td>Fail</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>1</td>
      <td>Victor Smith</td>
      <td>M</td>
      <td>12th</td>
      <td>94</td>
      <td>61</td>
      <td>Pass</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>2</td>
      <td>Kevin Rodriguez</td>
      <td>M</td>
      <td>12th</td>
      <td>90</td>
      <td>60</td>
      <td>Pass</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>3</td>
      <td>Dr. Richard Scott</td>
      <td>M</td>
      <td>12th</td>
      <td>67</td>
      <td>58</td>
      <td>Fail</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>4</td>
      <td>Bonnie Ray</td>
      <td>F</td>
      <td>9th</td>
      <td>97</td>
      <td>84</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>2917</th>
      <td>1</td>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
      <td>2917</td>
      <td>Amy Jacobs</td>
      <td>F</td>
      <td>10th</td>
      <td>85</td>
      <td>87</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>2918</th>
      <td>1</td>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
      <td>2918</td>
      <td>Nathan Campbell</td>
      <td>M</td>
      <td>12th</td>
      <td>97</td>
      <td>84</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>2919</th>
      <td>1</td>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
      <td>2919</td>
      <td>Randall Stewart</td>
      <td>M</td>
      <td>12th</td>
      <td>67</td>
      <td>77</td>
      <td>Fail</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>2920</th>
      <td>1</td>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
      <td>2920</td>
      <td>Jennifer Brown</td>
      <td>F</td>
      <td>9th</td>
      <td>97</td>
      <td>64</td>
      <td>Pass</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>2921</th>
      <td>1</td>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
      <td>2921</td>
      <td>Denise Lopez</td>
      <td>F</td>
      <td>10th</td>
      <td>79</td>
      <td>64</td>
      <td>Pass</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>5866</th>
      <td>2</td>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
      <td>5866</td>
      <td>Jamie Montgomery</td>
      <td>F</td>
      <td>12th</td>
      <td>70</td>
      <td>91</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>5867</th>
      <td>2</td>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
      <td>5867</td>
      <td>Shannon Phillips</td>
      <td>F</td>
      <td>10th</td>
      <td>84</td>
      <td>71</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>5868</th>
      <td>2</td>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
      <td>5868</td>
      <td>Todd Barber</td>
      <td>M</td>
      <td>11th</td>
      <td>95</td>
      <td>99</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>5869</th>
      <td>2</td>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
      <td>5869</td>
      <td>Desiree King</td>
      <td>F</td>
      <td>12th</td>
      <td>76</td>
      <td>95</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>5870</th>
      <td>2</td>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
      <td>5870</td>
      <td>Melissa Roberts</td>
      <td>F</td>
      <td>10th</td>
      <td>71</td>
      <td>82</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>7627</th>
      <td>3</td>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
      <td>7627</td>
      <td>Russell Davis</td>
      <td>M</td>
      <td>10th</td>
      <td>70</td>
      <td>88</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>7628</th>
      <td>3</td>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
      <td>7628</td>
      <td>Timothy Walker</td>
      <td>M</td>
      <td>12th</td>
      <td>97</td>
      <td>93</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>7629</th>
      <td>3</td>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
      <td>7629</td>
      <td>Katie Johnston</td>
      <td>F</td>
      <td>12th</td>
      <td>83</td>
      <td>81</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>7630</th>
      <td>3</td>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
      <td>7630</td>
      <td>Joann Oconnell</td>
      <td>F</td>
      <td>12th</td>
      <td>77</td>
      <td>91</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>7631</th>
      <td>3</td>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
      <td>7631</td>
      <td>Sarah Alexander</td>
      <td>F</td>
      <td>10th</td>
      <td>84</td>
      <td>93</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>12262</th>
      <td>4</td>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
      <td>12262</td>
      <td>Heather Wright</td>
      <td>F</td>
      <td>11th</td>
      <td>79</td>
      <td>68</td>
      <td>Pass</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>12263</th>
      <td>4</td>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
      <td>12263</td>
      <td>Elizabeth Goodwin</td>
      <td>F</td>
      <td>10th</td>
      <td>91</td>
      <td>81</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>12264</th>
      <td>4</td>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
      <td>12264</td>
      <td>Michelle Wong</td>
      <td>F</td>
      <td>9th</td>
      <td>78</td>
      <td>89</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>12265</th>
      <td>4</td>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
      <td>12265</td>
      <td>Scott Roth MD</td>
      <td>M</td>
      <td>11th</td>
      <td>91</td>
      <td>85</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>12266</th>
      <td>4</td>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
      <td>12266</td>
      <td>Billy Wilson</td>
      <td>M</td>
      <td>12th</td>
      <td>76</td>
      <td>83</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>13730</th>
      <td>5</td>
      <td>Wilson High School</td>
      <td>Charter</td>
      <td>2283</td>
      <td>1319574</td>
      <td>13730</td>
      <td>Kelli Anderson</td>
      <td>F</td>
      <td>10th</td>
      <td>84</td>
      <td>71</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>13731</th>
      <td>5</td>
      <td>Wilson High School</td>
      <td>Charter</td>
      <td>2283</td>
      <td>1319574</td>
      <td>13731</td>
      <td>Russell Ramirez</td>
      <td>M</td>
      <td>10th</td>
      <td>72</td>
      <td>87</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>13732</th>
      <td>5</td>
      <td>Wilson High School</td>
      <td>Charter</td>
      <td>2283</td>
      <td>1319574</td>
      <td>13732</td>
      <td>Eric Butler</td>
      <td>M</td>
      <td>10th</td>
      <td>97</td>
      <td>82</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>13733</th>
      <td>5</td>
      <td>Wilson High School</td>
      <td>Charter</td>
      <td>2283</td>
      <td>1319574</td>
      <td>13733</td>
      <td>Warren Kerr</td>
      <td>M</td>
      <td>11th</td>
      <td>93</td>
      <td>68</td>
      <td>Pass</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>13734</th>
      <td>5</td>
      <td>Wilson High School</td>
      <td>Charter</td>
      <td>2283</td>
      <td>1319574</td>
      <td>13734</td>
      <td>Gail Hall</td>
      <td>F</td>
      <td>9th</td>
      <td>79</td>
      <td>72</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>23274</th>
      <td>9</td>
      <td>Pena High School</td>
      <td>Charter</td>
      <td>962</td>
      <td>585858</td>
      <td>23274</td>
      <td>Alec Davis</td>
      <td>M</td>
      <td>9th</td>
      <td>91</td>
      <td>75</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>23275</th>
      <td>9</td>
      <td>Pena High School</td>
      <td>Charter</td>
      <td>962</td>
      <td>585858</td>
      <td>23275</td>
      <td>Michael Meyer</td>
      <td>M</td>
      <td>10th</td>
      <td>94</td>
      <td>76</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>23276</th>
      <td>9</td>
      <td>Pena High School</td>
      <td>Charter</td>
      <td>962</td>
      <td>585858</td>
      <td>23276</td>
      <td>Donald Gutierrez</td>
      <td>M</td>
      <td>11th</td>
      <td>98</td>
      <td>91</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>23277</th>
      <td>9</td>
      <td>Pena High School</td>
      <td>Charter</td>
      <td>962</td>
      <td>585858</td>
      <td>23277</td>
      <td>Travis Chavez</td>
      <td>M</td>
      <td>11th</td>
      <td>78</td>
      <td>71</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>23278</th>
      <td>9</td>
      <td>Pena High School</td>
      <td>Charter</td>
      <td>962</td>
      <td>585858</td>
      <td>23278</td>
      <td>Sheena Ball</td>
      <td>F</td>
      <td>12th</td>
      <td>87</td>
      <td>92</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>24236</th>
      <td>10</td>
      <td>Wright High School</td>
      <td>Charter</td>
      <td>1800</td>
      <td>1049400</td>
      <td>24236</td>
      <td>Aaron Johnson</td>
      <td>M</td>
      <td>10th</td>
      <td>89</td>
      <td>72</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>24237</th>
      <td>10</td>
      <td>Wright High School</td>
      <td>Charter</td>
      <td>1800</td>
      <td>1049400</td>
      <td>24237</td>
      <td>Kimberly Hamilton</td>
      <td>F</td>
      <td>10th</td>
      <td>84</td>
      <td>93</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>24238</th>
      <td>10</td>
      <td>Wright High School</td>
      <td>Charter</td>
      <td>1800</td>
      <td>1049400</td>
      <td>24238</td>
      <td>Ashley Johns</td>
      <td>F</td>
      <td>10th</td>
      <td>88</td>
      <td>88</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>24239</th>
      <td>10</td>
      <td>Wright High School</td>
      <td>Charter</td>
      <td>1800</td>
      <td>1049400</td>
      <td>24239</td>
      <td>Stephanie Donovan</td>
      <td>F</td>
      <td>10th</td>
      <td>75</td>
      <td>84</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>24240</th>
      <td>10</td>
      <td>Wright High School</td>
      <td>Charter</td>
      <td>1800</td>
      <td>1049400</td>
      <td>24240</td>
      <td>Cynthia Guzman</td>
      <td>F</td>
      <td>11th</td>
      <td>93</td>
      <td>82</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>26036</th>
      <td>11</td>
      <td>Rodriguez High School</td>
      <td>District</td>
      <td>3999</td>
      <td>2547363</td>
      <td>26036</td>
      <td>Sherry Jenkins</td>
      <td>F</td>
      <td>11th</td>
      <td>74</td>
      <td>81</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>26037</th>
      <td>11</td>
      <td>Rodriguez High School</td>
      <td>District</td>
      <td>3999</td>
      <td>2547363</td>
      <td>26037</td>
      <td>Kimberly Calderon</td>
      <td>F</td>
      <td>10th</td>
      <td>80</td>
      <td>86</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>26038</th>
      <td>11</td>
      <td>Rodriguez High School</td>
      <td>District</td>
      <td>3999</td>
      <td>2547363</td>
      <td>26038</td>
      <td>William Brady</td>
      <td>M</td>
      <td>11th</td>
      <td>97</td>
      <td>62</td>
      <td>Pass</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>26039</th>
      <td>11</td>
      <td>Rodriguez High School</td>
      <td>District</td>
      <td>3999</td>
      <td>2547363</td>
      <td>26039</td>
      <td>Jacob Padilla</td>
      <td>M</td>
      <td>11th</td>
      <td>79</td>
      <td>73</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>26040</th>
      <td>11</td>
      <td>Rodriguez High School</td>
      <td>District</td>
      <td>3999</td>
      <td>2547363</td>
      <td>26040</td>
      <td>Paula Maldonado</td>
      <td>F</td>
      <td>10th</td>
      <td>96</td>
      <td>92</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>30035</th>
      <td>12</td>
      <td>Johnson High School</td>
      <td>District</td>
      <td>4761</td>
      <td>3094650</td>
      <td>30035</td>
      <td>Lisa Casey</td>
      <td>F</td>
      <td>12th</td>
      <td>87</td>
      <td>87</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>30036</th>
      <td>12</td>
      <td>Johnson High School</td>
      <td>District</td>
      <td>4761</td>
      <td>3094650</td>
      <td>30036</td>
      <td>Jessica Lopez</td>
      <td>F</td>
      <td>9th</td>
      <td>98</td>
      <td>62</td>
      <td>Pass</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>30037</th>
      <td>12</td>
      <td>Johnson High School</td>
      <td>District</td>
      <td>4761</td>
      <td>3094650</td>
      <td>30037</td>
      <td>Anna Wilkins</td>
      <td>F</td>
      <td>11th</td>
      <td>89</td>
      <td>77</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>30038</th>
      <td>12</td>
      <td>Johnson High School</td>
      <td>District</td>
      <td>4761</td>
      <td>3094650</td>
      <td>30038</td>
      <td>Andrew Smith</td>
      <td>M</td>
      <td>9th</td>
      <td>66</td>
      <td>85</td>
      <td>Fail</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>30039</th>
      <td>12</td>
      <td>Johnson High School</td>
      <td>District</td>
      <td>4761</td>
      <td>3094650</td>
      <td>30039</td>
      <td>Robert Allison</td>
      <td>M</td>
      <td>11th</td>
      <td>63</td>
      <td>85</td>
      <td>Fail</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>34796</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>34796</td>
      <td>Michael Mercado</td>
      <td>M</td>
      <td>9th</td>
      <td>66</td>
      <td>94</td>
      <td>Fail</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>34797</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>34797</td>
      <td>Stephen Wolf</td>
      <td>M</td>
      <td>11th</td>
      <td>68</td>
      <td>63</td>
      <td>Fail</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>34798</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>34798</td>
      <td>Bonnie Hughes</td>
      <td>F</td>
      <td>12th</td>
      <td>73</td>
      <td>59</td>
      <td>Pass</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>34799</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>34799</td>
      <td>Melissa Smith</td>
      <td>F</td>
      <td>11th</td>
      <td>88</td>
      <td>58</td>
      <td>Pass</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>34800</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>34800</td>
      <td>Brian Mitchell</td>
      <td>M</td>
      <td>10th</td>
      <td>96</td>
      <td>55</td>
      <td>Pass</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>37535</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>37535</td>
      <td>Norma Mata</td>
      <td>F</td>
      <td>10th</td>
      <td>76</td>
      <td>76</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>37536</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>37536</td>
      <td>Cody Miller</td>
      <td>M</td>
      <td>11th</td>
      <td>84</td>
      <td>82</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>37537</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>37537</td>
      <td>Erik Snyder</td>
      <td>M</td>
      <td>9th</td>
      <td>80</td>
      <td>90</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>37538</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>37538</td>
      <td>Tanya Martinez</td>
      <td>F</td>
      <td>9th</td>
      <td>71</td>
      <td>69</td>
      <td>Pass</td>
      <td>Fail</td>
    </tr>
    <tr>
      <th>37539</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>37539</td>
      <td>Noah Erickson</td>
      <td>M</td>
      <td>9th</td>
      <td>86</td>
      <td>76</td>
      <td>Pass</td>
      <td>Pass</td>
    </tr>
  </tbody>
</table>
<p>75 rows × 13 columns</p>
</div>




```python
pass_math = district_df[district_df['math_score'] >=70].groupby('school')['Student ID'].count()/district_group['name'].count()*100
pass_reading = district_df[district_df['reading_score'] >=70].groupby('school')['Student ID'].count()/district_group['name'].count()*100
pass_overall = ((pass_math + pass_reading)/2)
```

School Summary

Create an overview table that summarizes key metrics about each school, including:
School Name
School Type
Total Students
Total School Budget
Per Student Budget
Average Math Score
Average Reading Score
% Passing Math
% Passing Reading
Overall Passing Rate (Average of the above two)


```python
school_summary=pd.DataFrame({"Total Students": district_group["name"].count(),
                             "School Budget": district_group["budget"].mean(),
                             "Per Student Budget": district_group["budget"].mean()/district_group["name"].count(),
                             "Average Math Score": district_group["math_score"].mean(),
                             "Average Reading Score": district_group["reading_score"].mean(), 
                             "% Passing Overall": pass_overall,
                             "% Passing Math": pass_math,
                             "% Passing Reading": pass_reading
                            })
school_summary["Average Math Score"] = school_summary["Average Math Score"].map(round2)
school_summary["Average Reading Score"] = school_summary["Average Reading Score"].map(round2)
school_summary["% Passing Math"] = school_summary["% Passing Math"].map(round2)
school_summary["% Passing Reading"] = school_summary["% Passing Reading"].map(round2)
school_summary["% Passing Overall"] = school_summary["% Passing Overall"].map(round2)
school_summary = school_summary[["Total Students","School Budget","Per Student Budget","Average Math Score","Average Reading Score",
                "% Passing Math", "% Passing Reading","% Passing Overall"]]
school_summary.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>Total Students</th>
      <th>School Budget</th>
      <th>Per Student Budget</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>% Passing Overall</th>
    </tr>
    <tr>
      <th>school</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <th>District</th>
      <td>4976</td>
      <td>3124928</td>
      <td>628.0</td>
      <td>77.05</td>
      <td>81.03</td>
      <td>66.68</td>
      <td>81.93</td>
      <td>74.31</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <th>Charter</th>
      <td>1858</td>
      <td>1081356</td>
      <td>582.0</td>
      <td>83.06</td>
      <td>83.98</td>
      <td>94.13</td>
      <td>97.04</td>
      <td>95.59</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>2949</td>
      <td>1884411</td>
      <td>639.0</td>
      <td>76.71</td>
      <td>81.16</td>
      <td>65.99</td>
      <td>80.74</td>
      <td>73.36</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>2739</td>
      <td>1763916</td>
      <td>644.0</td>
      <td>77.1</td>
      <td>80.75</td>
      <td>68.31</td>
      <td>79.3</td>
      <td>73.8</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <th>Charter</th>
      <td>1468</td>
      <td>917500</td>
      <td>625.0</td>
      <td>83.35</td>
      <td>83.82</td>
      <td>93.39</td>
      <td>97.14</td>
      <td>95.27</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Top Performing Schools (By Passing Rating)
top_schools = school_summary.sort_values(by="% Passing Overall", ascending=False)
top_schools
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>Total Students</th>
      <th>School Budget</th>
      <th>Per Student Budget</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>% Passing Overall</th>
    </tr>
    <tr>
      <th>school</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Cabrera High School</th>
      <th>Charter</th>
      <td>1858</td>
      <td>1081356</td>
      <td>582.0</td>
      <td>83.06</td>
      <td>83.98</td>
      <td>94.13</td>
      <td>97.04</td>
      <td>95.59</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <th>Charter</th>
      <td>1635</td>
      <td>1043130</td>
      <td>638.0</td>
      <td>83.42</td>
      <td>83.85</td>
      <td>93.27</td>
      <td>97.31</td>
      <td>95.29</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <th>Charter</th>
      <td>1468</td>
      <td>917500</td>
      <td>625.0</td>
      <td>83.35</td>
      <td>83.82</td>
      <td>93.39</td>
      <td>97.14</td>
      <td>95.27</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <th>Charter</th>
      <td>962</td>
      <td>585858</td>
      <td>609.0</td>
      <td>83.84</td>
      <td>84.04</td>
      <td>94.59</td>
      <td>95.95</td>
      <td>95.27</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <th>Charter</th>
      <td>2283</td>
      <td>1319574</td>
      <td>578.0</td>
      <td>83.27</td>
      <td>83.99</td>
      <td>93.87</td>
      <td>96.54</td>
      <td>95.2</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <th>Charter</th>
      <td>1800</td>
      <td>1049400</td>
      <td>583.0</td>
      <td>83.68</td>
      <td>83.95</td>
      <td>93.33</td>
      <td>96.61</td>
      <td>94.97</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <th>Charter</th>
      <td>1761</td>
      <td>1056600</td>
      <td>600.0</td>
      <td>83.36</td>
      <td>83.73</td>
      <td>93.87</td>
      <td>95.85</td>
      <td>94.86</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <th>Charter</th>
      <td>427</td>
      <td>248087</td>
      <td>581.0</td>
      <td>83.8</td>
      <td>83.81</td>
      <td>92.51</td>
      <td>96.25</td>
      <td>94.38</td>
    </tr>
    <tr>
      <th>Bailey High School</th>
      <th>District</th>
      <td>4976</td>
      <td>3124928</td>
      <td>628.0</td>
      <td>77.05</td>
      <td>81.03</td>
      <td>66.68</td>
      <td>81.93</td>
      <td>74.31</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <th>District</th>
      <td>4635</td>
      <td>3022020</td>
      <td>652.0</td>
      <td>77.29</td>
      <td>80.93</td>
      <td>66.75</td>
      <td>80.86</td>
      <td>73.81</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>2739</td>
      <td>1763916</td>
      <td>644.0</td>
      <td>77.1</td>
      <td>80.75</td>
      <td>68.31</td>
      <td>79.3</td>
      <td>73.8</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <th>District</th>
      <td>4761</td>
      <td>3094650</td>
      <td>650.0</td>
      <td>77.07</td>
      <td>80.97</td>
      <td>66.06</td>
      <td>81.22</td>
      <td>73.64</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <th>District</th>
      <td>2917</td>
      <td>1910635</td>
      <td>655.0</td>
      <td>76.63</td>
      <td>81.18</td>
      <td>65.68</td>
      <td>81.32</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>2949</td>
      <td>1884411</td>
      <td>639.0</td>
      <td>76.71</td>
      <td>81.16</td>
      <td>65.99</td>
      <td>80.74</td>
      <td>73.36</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <th>District</th>
      <td>3999</td>
      <td>2547363</td>
      <td>637.0</td>
      <td>76.84</td>
      <td>80.74</td>
      <td>66.37</td>
      <td>80.22</td>
      <td>73.29</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Bottom Performing Schools (By Passing Rating)
top_schools.tail()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>Total Students</th>
      <th>School Budget</th>
      <th>Per Student Budget</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>% Passing Overall</th>
    </tr>
    <tr>
      <th>school</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>2739</td>
      <td>1763916</td>
      <td>644.0</td>
      <td>77.1</td>
      <td>80.75</td>
      <td>68.31</td>
      <td>79.3</td>
      <td>73.8</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <th>District</th>
      <td>4761</td>
      <td>3094650</td>
      <td>650.0</td>
      <td>77.07</td>
      <td>80.97</td>
      <td>66.06</td>
      <td>81.22</td>
      <td>73.64</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <th>District</th>
      <td>2917</td>
      <td>1910635</td>
      <td>655.0</td>
      <td>76.63</td>
      <td>81.18</td>
      <td>65.68</td>
      <td>81.32</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>2949</td>
      <td>1884411</td>
      <td>639.0</td>
      <td>76.71</td>
      <td>81.16</td>
      <td>65.99</td>
      <td>80.74</td>
      <td>73.36</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <th>District</th>
      <td>3999</td>
      <td>2547363</td>
      <td>637.0</td>
      <td>76.84</td>
      <td>80.74</td>
      <td>66.37</td>
      <td>80.22</td>
      <td>73.29</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Math scores by grade
gradelvl_df = district_df.groupby(["school", "grade"])
mathgrade_summary=pd.DataFrame({"Avg Math Score by Grade": gradelvl_df["math_score"].mean()})
mathgrade_summary.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>Avg Math Score by Grade</th>
    </tr>
    <tr>
      <th>school</th>
      <th>grade</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="4" valign="top">Bailey High School</th>
      <th>10th</th>
      <td>76.996772</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>77.515588</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>76.492218</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>77.083676</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <th>10th</th>
      <td>83.154506</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Reading scores by grade
readinggrade_summary=pd.DataFrame({"Avg Reading Score by Grade": gradelvl_df["reading_score"].mean()})
readinggrade_summary.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>Avg Reading Score by Grade</th>
    </tr>
    <tr>
      <th>school</th>
      <th>grade</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="4" valign="top">Bailey High School</th>
      <th>10th</th>
      <td>80.907183</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>80.945643</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>80.912451</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>81.303155</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <th>10th</th>
      <td>84.253219</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Scores by School Spending Bins
bins = [0,600,620,640,660]
school_bins = ['Poor','Average','Good','Excellent']
school_summary["School Spend Grade"] = pd.cut(school_summary["Per Student Budget"],
                                           bins, labels=school_bins)
bins = [0,2000,3500,5000]
size_bins = ['Small','Medium','Large']
school_summary["School Size"] = pd.cut(school_summary["Total Students"],
                                           bins, labels=size_bins)
```


```python
#Scores by School Spending
school_summary1 = school_summary[["School Spend Grade","Average Math Score","Average Reading Score",
                "% Passing Math", "% Passing Reading","% Passing Overall"]]
school_summary1.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>School Spend Grade</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>% Passing Overall</th>
    </tr>
    <tr>
      <th>school</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <th>District</th>
      <td>Good</td>
      <td>77.05</td>
      <td>81.03</td>
      <td>66.68</td>
      <td>81.93</td>
      <td>74.31</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <th>Charter</th>
      <td>Poor</td>
      <td>83.06</td>
      <td>83.98</td>
      <td>94.13</td>
      <td>97.04</td>
      <td>95.59</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>Good</td>
      <td>76.71</td>
      <td>81.16</td>
      <td>65.99</td>
      <td>80.74</td>
      <td>73.36</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>Excellent</td>
      <td>77.1</td>
      <td>80.75</td>
      <td>68.31</td>
      <td>79.3</td>
      <td>73.8</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <th>Charter</th>
      <td>Good</td>
      <td>83.35</td>
      <td>83.82</td>
      <td>93.39</td>
      <td>97.14</td>
      <td>95.27</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Scores by School Size Bins

```


```python
#Score by School Spend Grade
school_summary3 = school_summary[["School Spend Grade","Average Math Score","Average Reading Score",
                "% Passing Math", "% Passing Reading","% Passing Overall"]]
scorebyspend = school_summary3.sort_values(by=["School Spend Grade"],
                                                 ascending=False)
scorebyspend
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>School Spend Grade</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>% Passing Overall</th>
    </tr>
    <tr>
      <th>school</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Johnson High School</th>
      <th>District</th>
      <td>Excellent</td>
      <td>77.07</td>
      <td>80.97</td>
      <td>66.06</td>
      <td>81.22</td>
      <td>73.64</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <th>District</th>
      <td>Excellent</td>
      <td>76.63</td>
      <td>81.18</td>
      <td>65.68</td>
      <td>81.32</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <th>District</th>
      <td>Excellent</td>
      <td>77.29</td>
      <td>80.93</td>
      <td>66.75</td>
      <td>80.86</td>
      <td>73.81</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>Excellent</td>
      <td>77.1</td>
      <td>80.75</td>
      <td>68.31</td>
      <td>79.3</td>
      <td>73.8</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <th>Charter</th>
      <td>Good</td>
      <td>83.42</td>
      <td>83.85</td>
      <td>93.27</td>
      <td>97.31</td>
      <td>95.29</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <th>District</th>
      <td>Good</td>
      <td>76.84</td>
      <td>80.74</td>
      <td>66.37</td>
      <td>80.22</td>
      <td>73.29</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <th>Charter</th>
      <td>Good</td>
      <td>83.35</td>
      <td>83.82</td>
      <td>93.39</td>
      <td>97.14</td>
      <td>95.27</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>Good</td>
      <td>76.71</td>
      <td>81.16</td>
      <td>65.99</td>
      <td>80.74</td>
      <td>73.36</td>
    </tr>
    <tr>
      <th>Bailey High School</th>
      <th>District</th>
      <td>Good</td>
      <td>77.05</td>
      <td>81.03</td>
      <td>66.68</td>
      <td>81.93</td>
      <td>74.31</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <th>Charter</th>
      <td>Average</td>
      <td>83.84</td>
      <td>84.04</td>
      <td>94.59</td>
      <td>95.95</td>
      <td>95.27</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <th>Charter</th>
      <td>Poor</td>
      <td>83.68</td>
      <td>83.95</td>
      <td>93.33</td>
      <td>96.61</td>
      <td>94.97</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <th>Charter</th>
      <td>Poor</td>
      <td>83.27</td>
      <td>83.99</td>
      <td>93.87</td>
      <td>96.54</td>
      <td>95.2</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <th>Charter</th>
      <td>Poor</td>
      <td>83.36</td>
      <td>83.73</td>
      <td>93.87</td>
      <td>95.85</td>
      <td>94.86</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <th>Charter</th>
      <td>Poor</td>
      <td>83.8</td>
      <td>83.81</td>
      <td>92.51</td>
      <td>96.25</td>
      <td>94.38</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <th>Charter</th>
      <td>Poor</td>
      <td>83.06</td>
      <td>83.98</td>
      <td>94.13</td>
      <td>97.04</td>
      <td>95.59</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Score by School size
school_summary4 = school_summary[["School Size","Average Math Score","Average Reading Score",
                "% Passing Math", "% Passing Reading","% Passing Overall"]]
scorebysize = school_summary4.sort_values(by=["School Size"],
                                                 ascending=False)
scorebysize
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>School Size</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>% Passing Overall</th>
    </tr>
    <tr>
      <th>school</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Rodriguez High School</th>
      <th>District</th>
      <td>Large</td>
      <td>76.84</td>
      <td>80.74</td>
      <td>66.37</td>
      <td>80.22</td>
      <td>73.29</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <th>District</th>
      <td>Large</td>
      <td>77.07</td>
      <td>80.97</td>
      <td>66.06</td>
      <td>81.22</td>
      <td>73.64</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <th>District</th>
      <td>Large</td>
      <td>77.29</td>
      <td>80.93</td>
      <td>66.75</td>
      <td>80.86</td>
      <td>73.81</td>
    </tr>
    <tr>
      <th>Bailey High School</th>
      <th>District</th>
      <td>Large</td>
      <td>77.05</td>
      <td>81.03</td>
      <td>66.68</td>
      <td>81.93</td>
      <td>74.31</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <th>Charter</th>
      <td>Medium</td>
      <td>83.27</td>
      <td>83.99</td>
      <td>93.87</td>
      <td>96.54</td>
      <td>95.2</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <th>District</th>
      <td>Medium</td>
      <td>76.63</td>
      <td>81.18</td>
      <td>65.68</td>
      <td>81.32</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>Medium</td>
      <td>77.1</td>
      <td>80.75</td>
      <td>68.31</td>
      <td>79.3</td>
      <td>73.8</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>Medium</td>
      <td>76.71</td>
      <td>81.16</td>
      <td>65.99</td>
      <td>80.74</td>
      <td>73.36</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <th>Charter</th>
      <td>Small</td>
      <td>83.68</td>
      <td>83.95</td>
      <td>93.33</td>
      <td>96.61</td>
      <td>94.97</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <th>Charter</th>
      <td>Small</td>
      <td>83.42</td>
      <td>83.85</td>
      <td>93.27</td>
      <td>97.31</td>
      <td>95.29</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <th>Charter</th>
      <td>Small</td>
      <td>83.36</td>
      <td>83.73</td>
      <td>93.87</td>
      <td>95.85</td>
      <td>94.86</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <th>Charter</th>
      <td>Small</td>
      <td>83.84</td>
      <td>84.04</td>
      <td>94.59</td>
      <td>95.95</td>
      <td>95.27</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <th>Charter</th>
      <td>Small</td>
      <td>83.8</td>
      <td>83.81</td>
      <td>92.51</td>
      <td>96.25</td>
      <td>94.38</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <th>Charter</th>
      <td>Small</td>
      <td>83.35</td>
      <td>83.82</td>
      <td>93.39</td>
      <td>97.14</td>
      <td>95.27</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <th>Charter</th>
      <td>Small</td>
      <td>83.06</td>
      <td>83.98</td>
      <td>94.13</td>
      <td>97.04</td>
      <td>95.59</td>
    </tr>
  </tbody>
</table>
</div>




```python

```




    <pandas.core.groupby.DataFrameGroupBy object at 0x113ea7780>



#Observable Trends
-There is an inverse relationship between 'Budget per Student' and student test scores in both math and reading. 
-There is a direct correlation between school size and student test scores
-Charter schools are shown to have higher test scores vs district schools of similar size or similar spend per student. Charter schools also tend to spend less per student and have smaller student populations
