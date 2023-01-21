```python
import requests
import pandas as pd
```


```python
link_to_explore = "https://snhupenmen.com/sports/baseball/stats/"
years = list(range(2012,2022))
links = []
for year in years : 
    string = link_to_explore + str(year)
    links.append(string)

length = len(links) - 1
i = 0
gbg = []
ptch = []
fldr = []
while i < length:
    i+= 1
    gbg.append(pd.read_html(links[i])[6])
    ptch.append(pd.read_html(links[i])[1])
    fldr.append(pd.read_html(links[i])[0])
game_by_game = pd.concat(gbg)
pitchers = pd.concat(ptch)
hitters = pd.concat(fldr)
```


```python
pitchers = pitchers[pitchers["Player"] != "Totals" ]
pitchers = pitchers[pitchers["Player"] != "Opponents"]
game_by_game = game_by_game[game_by_game["Date"] != "Total"]
hitters = hitters[hitters["Player"] != "Opponents"]
```


```python
pitchers['Last_Name'] = pitchers.Player.str.split(',',expand = True)[0]
pitchers['First_name'] = pitchers.Player.str.split(',',expand = True)[2]
hitters['Last_Name'] = hitters.Player.str.split(',',expand = True)[0]
hitters['First_name'] = hitters.Player.str.split(',',expand = True)[2]
```


```python
def wins_losses(w_l):
    if w_l == 'W':
        return 1
    else:
        return 0
#Creating a function to look at home,away and neutral
def home_away(h_a):   
    if h_a == 'vs':
        return 'home'
    elif h_a == 'at':
        return 'away'
    else:
        return 'neutral'
gbg['site'] = gbg['Loc'].apply(home_away)

#Storing the binary variables in result 
gbg['result'] = gbg['W/L'].apply(wins_losses)
gbg[['snhu_runs','snhu_runs']] = gbg.Score.str.split("-", expand = True)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Input In [45], in <cell line: 14>()
         12     else:
         13         return 'neutral'
    ---> 14 gbg['site'] = gbg['Loc'].apply(home_away)
         16 #Storing the binary variables in result 
         17 gbg['result'] = gbg['W/L'].apply(wins_losses)


    TypeError: list indices must be integers or slices, not str



```python
top_pitchers = pitchers.groupby(['First_name', 'Last_Name'])[['AB','H','SO', '2B', '3B','HBP','HR','IP','ER']].sum()
top_pitchers['average'] = top_pitchers.H/top_pitchers.AB
top_pitchers['ERA'] = top_pitchers['ER']/(top_pitchers['IP']/9)
```


```python
top_pitchers.sort_values("IP", ascending=False).head()
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
      <th></th>
      <th>AB</th>
      <th>H</th>
      <th>SO</th>
      <th>2B</th>
      <th>3B</th>
      <th>HBP</th>
      <th>HR</th>
      <th>IP</th>
      <th>ER</th>
      <th>average</th>
      <th>ERA</th>
    </tr>
    <tr>
      <th>First_name</th>
      <th>Last_Name</th>
      <th></th>
      <th></th>
      <th></th>
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
      <th>Jake</th>
      <th>Walkinshaw</th>
      <td>839</td>
      <td>168</td>
      <td>234</td>
      <td>20</td>
      <td>3</td>
      <td>13</td>
      <td>12</td>
      <td>232.3</td>
      <td>50</td>
      <td>0.200238</td>
      <td>1.937150</td>
    </tr>
    <tr>
      <th>Alex</th>
      <th>Person</th>
      <td>822</td>
      <td>189</td>
      <td>173</td>
      <td>31</td>
      <td>4</td>
      <td>9</td>
      <td>16</td>
      <td>219.4</td>
      <td>75</td>
      <td>0.229927</td>
      <td>3.076572</td>
    </tr>
    <tr>
      <th>Mitchell</th>
      <th>Powers</th>
      <td>719</td>
      <td>153</td>
      <td>221</td>
      <td>29</td>
      <td>5</td>
      <td>8</td>
      <td>14</td>
      <td>197.2</td>
      <td>54</td>
      <td>0.212796</td>
      <td>2.464503</td>
    </tr>
    <tr>
      <th>Wesley</th>
      <th>Tobin</th>
      <td>723</td>
      <td>156</td>
      <td>225</td>
      <td>20</td>
      <td>2</td>
      <td>7</td>
      <td>18</td>
      <td>196.6</td>
      <td>62</td>
      <td>0.215768</td>
      <td>2.838250</td>
    </tr>
    <tr>
      <th>Derrick</th>
      <th>Sylvester</th>
      <td>620</td>
      <td>145</td>
      <td>171</td>
      <td>18</td>
      <td>1</td>
      <td>17</td>
      <td>1</td>
      <td>166.4</td>
      <td>38</td>
      <td>0.233871</td>
      <td>2.055288</td>
    </tr>
  </tbody>
</table>
</div>




```python
top_pitchers["ERA"].dropna()
top_5 = top_pitchers.sort_values("IP", ascending=False).head(10)
length = len(top_5) 
row = 0 
while row < length:
    print(top_5.index[row][0] + " " + top_5.index[row][1]+ " pitched a total of " + str(int(top_5.iloc[row]['IP'])) + 
            " innings pitching at SNHU. He retired with a total of "+ str(int(top_5.iloc[row]['SO']))+ " strikesouts he was able to complish this with a "+
         str(top_5.iloc[row]['ERA'])+ " era. ")
    row += 1
```

     Jake Walkinshaw pitched a total of 232 innings pitching at SNHU. He retired with a total of 234 strikesouts he was able to complish this with a 1.9371502367628066 era. 
     Alex Person pitched a total of 219 innings pitching at SNHU. He retired with a total of 173 strikesouts he was able to complish this with a 3.0765724703737467 era. 
     Mitchell Powers pitched a total of 197 innings pitching at SNHU. He retired with a total of 221 strikesouts he was able to complish this with a 2.464503042596349 era. 
     Wesley Tobin pitched a total of 196 innings pitching at SNHU. He retired with a total of 225 strikesouts he was able to complish this with a 2.8382502543234995 era. 
     Derrick Sylvester pitched a total of 166 innings pitching at SNHU. He retired with a total of 171 strikesouts he was able to complish this with a 2.0552884615384612 era. 
     Andrew Lalonde pitched a total of 141 innings pitching at SNHU. He retired with a total of 141 strikesouts he was able to complish this with a 2.8045325779036827 era. 
     Jeffrey Praml pitched a total of 136 innings pitching at SNHU. He retired with a total of 160 strikesouts he was able to complish this with a 2.4395604395604398 era. 
     Endy Morales pitched a total of 132 innings pitching at SNHU. He retired with a total of 111 strikesouts he was able to complish this with a 2.9251700680272106 era. 
     Alex Gomes pitched a total of 127 innings pitching at SNHU. He retired with a total of 112 strikesouts he was able to complish this with a 2.4725274725274726 era. 
     Tim Viehoff pitched a total of 122 innings pitching at SNHU. He retired with a total of 156 strikesouts he was able to complish this with a 2.7250409165302782 era. 



```python

```
