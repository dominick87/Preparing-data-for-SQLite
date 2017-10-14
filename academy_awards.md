
### Introduction to the data

Exploring the data and looking for data quality issues


```python
import pandas as pd
df = pd.read_csv("academy_awards.csv", encoding="ISO-8859-1")

df
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
      <th>Year</th>
      <th>Category</th>
      <th>Nominee</th>
      <th>Additional Info</th>
      <th>Won?</th>
      <th>Unnamed: 5</th>
      <th>Unnamed: 6</th>
      <th>Unnamed: 7</th>
      <th>Unnamed: 8</th>
      <th>Unnamed: 9</th>
      <th>Unnamed: 10</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2010 (83rd)</td>
      <td>Actor -- Leading Role</td>
      <td>Javier Bardem</td>
      <td>Biutiful {'Uxbal'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2010 (83rd)</td>
      <td>Actor -- Leading Role</td>
      <td>Jeff Bridges</td>
      <td>True Grit {'Rooster Cogburn'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2010 (83rd)</td>
      <td>Actor -- Leading Role</td>
      <td>Jesse Eisenberg</td>
      <td>The Social Network {'Mark Zuckerberg'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2010 (83rd)</td>
      <td>Actor -- Leading Role</td>
      <td>Colin Firth</td>
      <td>The King's Speech {'King George VI'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2010 (83rd)</td>
      <td>Actor -- Leading Role</td>
      <td>James Franco</td>
      <td>127 Hours {'Aron Ralston'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5</th>
      <td>2010 (83rd)</td>
      <td>Actor -- Supporting Role</td>
      <td>Christian Bale</td>
      <td>The Fighter {'Dicky Eklund'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2010 (83rd)</td>
      <td>Actor -- Supporting Role</td>
      <td>John Hawkes</td>
      <td>Winter's Bone {'Teardrop'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7</th>
      <td>2010 (83rd)</td>
      <td>Actor -- Supporting Role</td>
      <td>Jeremy Renner</td>
      <td>The Town {'James Coughlin'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>8</th>
      <td>2010 (83rd)</td>
      <td>Actor -- Supporting Role</td>
      <td>Mark Ruffalo</td>
      <td>The Kids Are All Right {'Paul'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>9</th>
      <td>2010 (83rd)</td>
      <td>Actor -- Supporting Role</td>
      <td>Geoffrey Rush</td>
      <td>The King's Speech {'Lionel Logue'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10</th>
      <td>2010 (83rd)</td>
      <td>Actress -- Leading Role</td>
      <td>Annette Bening</td>
      <td>The Kids Are All Right {'Nic'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>11</th>
      <td>2010 (83rd)</td>
      <td>Actress -- Leading Role</td>
      <td>Nicole Kidman</td>
      <td>Rabbit Hole {'Becca'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>12</th>
      <td>2010 (83rd)</td>
      <td>Actress -- Leading Role</td>
      <td>Jennifer Lawrence</td>
      <td>Winter's Bone {'Ree'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>13</th>
      <td>2010 (83rd)</td>
      <td>Actress -- Leading Role</td>
      <td>Natalie Portman</td>
      <td>Black Swan {'Nina Sayers/The Swan Queen'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>14</th>
      <td>2010 (83rd)</td>
      <td>Actress -- Leading Role</td>
      <td>Michelle Williams</td>
      <td>Blue Valentine {'Cindy'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>15</th>
      <td>2010 (83rd)</td>
      <td>Actress -- Supporting Role</td>
      <td>Amy Adams</td>
      <td>The Fighter {'Charlene Fleming'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>16</th>
      <td>2010 (83rd)</td>
      <td>Actress -- Supporting Role</td>
      <td>Helena Bonham Carter</td>
      <td>The King's Speech {'Queen Elizabeth'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>17</th>
      <td>2010 (83rd)</td>
      <td>Actress -- Supporting Role</td>
      <td>Melissa Leo</td>
      <td>The Fighter {'Alice Ward'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>18</th>
      <td>2010 (83rd)</td>
      <td>Actress -- Supporting Role</td>
      <td>Hailee Steinfeld</td>
      <td>True Grit {'Mattie Ross'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>19</th>
      <td>2010 (83rd)</td>
      <td>Actress -- Supporting Role</td>
      <td>Jacki Weaver</td>
      <td>Animal Kingdom {'Janine 'Smurf' Cody'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>20</th>
      <td>2010 (83rd)</td>
      <td>Animated Feature Film</td>
      <td>How to Train Your Dragon</td>
      <td>Chris Sanders and Dean DeBlois</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>21</th>
      <td>2010 (83rd)</td>
      <td>Animated Feature Film</td>
      <td>The Illusionist</td>
      <td>Sylvain Chomet</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>22</th>
      <td>2010 (83rd)</td>
      <td>Animated Feature Film</td>
      <td>Toy Story 3</td>
      <td>Lee Unkrich</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>23</th>
      <td>2010 (83rd)</td>
      <td>Art Direction</td>
      <td>Alice in Wonderland</td>
      <td>Production Design: Robert Stromberg; Set Decor...</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>24</th>
      <td>2010 (83rd)</td>
      <td>Art Direction</td>
      <td>Harry Potter and the Deathly Hallows Part 1</td>
      <td>Production Design: Stuart Craig; Set Decoratio...</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>25</th>
      <td>2010 (83rd)</td>
      <td>Art Direction</td>
      <td>Inception</td>
      <td>Production Design: Guy Hendrix Dyas; Set Decor...</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>26</th>
      <td>2010 (83rd)</td>
      <td>Art Direction</td>
      <td>The King's Speech</td>
      <td>Production Design: Eve Stewart; Set Decoration...</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>27</th>
      <td>2010 (83rd)</td>
      <td>Art Direction</td>
      <td>True Grit</td>
      <td>Production Design: Jess Gonchor; Set Decoratio...</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>28</th>
      <td>2010 (83rd)</td>
      <td>Cinematography</td>
      <td>Black Swan</td>
      <td>Matthew Libatique</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>29</th>
      <td>2010 (83rd)</td>
      <td>Cinematography</td>
      <td>Inception</td>
      <td>Wally Pfister</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
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
    </tr>
    <tr>
      <th>10107</th>
      <td>1927/28 (1st)</td>
      <td>Art Direction</td>
      <td>Harry Oliver</td>
      <td>7th Heaven</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10108</th>
      <td>1927/28 (1st)</td>
      <td>Cinematography</td>
      <td>George Barnes</td>
      <td>The Devil Dancer; The Magic Flame; and Sadie T...</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10109</th>
      <td>1927/28 (1st)</td>
      <td>Cinematography</td>
      <td>Charles Rosher</td>
      <td>Sunrise</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10110</th>
      <td>1927/28 (1st)</td>
      <td>Cinematography</td>
      <td>Karl Struss</td>
      <td>Sunrise</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10111</th>
      <td>1927/28 (1st)</td>
      <td>Directing</td>
      <td>Lewis Milestone</td>
      <td>Two Arabian Knights</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10112</th>
      <td>1927/28 (1st)</td>
      <td>Directing</td>
      <td>Ted Wilde</td>
      <td>Speedy</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10113</th>
      <td>1927/28 (1st)</td>
      <td>Directing</td>
      <td>Frank Borzage</td>
      <td>7th Heaven</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10114</th>
      <td>1927/28 (1st)</td>
      <td>Directing</td>
      <td>Herbert Brenon</td>
      <td>Sorrell and Son</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10115</th>
      <td>1927/28 (1st)</td>
      <td>Directing</td>
      <td>King Vidor</td>
      <td>The Crowd</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10116</th>
      <td>1927/28 (1st)</td>
      <td>Directing</td>
      <td>To Charles Chaplin, for acting, writing, direc...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10117</th>
      <td>1927/28 (1st)</td>
      <td>Best Picture</td>
      <td>The Caddo Company</td>
      <td>The Racket</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10118</th>
      <td>1927/28 (1st)</td>
      <td>Best Picture</td>
      <td>Fox</td>
      <td>7th Heaven</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10119</th>
      <td>1927/28 (1st)</td>
      <td>Best Picture</td>
      <td>Paramount Famous Lasky</td>
      <td>Wings</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10120</th>
      <td>1927/28 (1st)</td>
      <td>Writing</td>
      <td>Alfred Cohn</td>
      <td>The Jazz Singer</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10121</th>
      <td>1927/28 (1st)</td>
      <td>Writing</td>
      <td>Anthony Coldeway</td>
      <td>Glorious Betsy</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10122</th>
      <td>1927/28 (1st)</td>
      <td>Writing</td>
      <td>Benjamin Glazer</td>
      <td>7th Heaven</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10123</th>
      <td>1927/28 (1st)</td>
      <td>Writing</td>
      <td>Lajos Biro</td>
      <td>The Last Command</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10124</th>
      <td>1927/28 (1st)</td>
      <td>Writing</td>
      <td>Ben Hecht</td>
      <td>Underworld</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10125</th>
      <td>1927/28 (1st)</td>
      <td>Writing</td>
      <td>Gerald Duffy</td>
      <td>The Private Life of Helen of Troy</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10126</th>
      <td>1927/28 (1st)</td>
      <td>Writing</td>
      <td>Joseph Farnham[NOTE: This award was not associ...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10127</th>
      <td>1927/28 (1st)</td>
      <td>Writing</td>
      <td>George Marion, Jr.[NOTE: This nomination was n...</td>
      <td>NaN</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10128</th>
      <td>1927/28 (1st)</td>
      <td>Writing</td>
      <td>To Charles Chaplin, for acting, writing, direc...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10129</th>
      <td>1927/28 (1st)</td>
      <td>Honorary Award</td>
      <td>To Warner Bros., for producing The Jazz Singer...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10130</th>
      <td>1927/28 (1st)</td>
      <td>Honorary Award</td>
      <td>To Charles Chaplin, for acting, writing, direc...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10131</th>
      <td>1927/28 (1st)</td>
      <td>Engineering Effects (archaic category)</td>
      <td>Ralph Hammeras [NOTE: This nomination was not ...</td>
      <td>NaN</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10132</th>
      <td>1927/28 (1st)</td>
      <td>Engineering Effects (archaic category)</td>
      <td>Roy Pomeroy</td>
      <td>Wings</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10133</th>
      <td>1927/28 (1st)</td>
      <td>Engineering Effects (archaic category)</td>
      <td>Nugent Slaughter [NOTE: Though no specific tit...</td>
      <td>NaN</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10134</th>
      <td>1927/28 (1st)</td>
      <td>Unique and Artistic Picture (archaic category)</td>
      <td>Fox</td>
      <td>Sunrise</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10135</th>
      <td>1927/28 (1st)</td>
      <td>Unique and Artistic Picture (archaic category)</td>
      <td>Metro-Goldwyn-Mayer</td>
      <td>The Crowd</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10136</th>
      <td>1927/28 (1st)</td>
      <td>Unique and Artistic Picture (archaic category)</td>
      <td>Paramount Famous Lasky</td>
      <td>Chang</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>10137 rows × 11 columns</p>
</div>



There are 6 unnamed columns. Let's explore if any of them have valid values that we need


```python
for i in range(5,11):
    print(df["Unnamed: " + str(i)].value_counts())
```

    *                                                                                                               7
     discoverer of stars                                                                                            1
     resilience                                                                                                     1
     error-prone measurements on sets. [Digital Imaging Technology]"                                                1
     D.B. "Don" Keele and Mark E. Engebretson has resulted in the over 20-year dominance of constant-directivity    1
    Name: Unnamed: 5, dtype: int64
    *                                                                   9
     direct radiator bass style cinema loudspeaker systems. [Sound]"    1
     flexibility and water resistance                                   1
     sympathetic                                                        1
    Name: Unnamed: 6, dtype: int64
     kindly                                               1
    *                                                     1
     while requiring no dangerous solvents. [Systems]"    1
    Name: Unnamed: 7, dtype: int64
     understanding comedy genius - Mack Sennett.""    1
    *                                                 1
    Name: Unnamed: 8, dtype: int64
    *    1
    Name: Unnamed: 9, dtype: int64
    *    1
    Name: Unnamed: 10, dtype: int64
    

It seems they are few values compared to the number of rows(10137) and those values seem to be notes with no much relation.
Also, the column `Additional Info` contains a few different formatting styles. 
We'll get rid of them later on (at cleaning up steps).

### Filtering the data

The dataset is incredibly messy you can notice many inconsistencies that make it hard to work with. Let's filter our Dataframe to a subset, so it's more manageable:
* Use the first 4 digit of Year and convert to `int64` value
* Update the DataFrame with Years > `2000`
* Use conditional filtering to select only the rows where Category matches one of the 4 awards we're interested in
  * Actor -- Leading Role
  * Actor -- Supporting Role
  * Actress -- Leading Role
  * Actress -- Supporting Role



```python
df["Year"] = df["Year"].str[0:4].astype("int64")
```


```python
df["Year"].head()
```




    0    2010
    1    2010
    2    2010
    3    2010
    4    2010
    Name: Year, dtype: int64




```python
later_than_2000 = df[df["Year"] > 2000]
later_than_2000
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
      <th>Year</th>
      <th>Category</th>
      <th>Nominee</th>
      <th>Additional Info</th>
      <th>Won?</th>
      <th>Unnamed: 5</th>
      <th>Unnamed: 6</th>
      <th>Unnamed: 7</th>
      <th>Unnamed: 8</th>
      <th>Unnamed: 9</th>
      <th>Unnamed: 10</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Javier Bardem</td>
      <td>Biutiful {'Uxbal'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Jeff Bridges</td>
      <td>True Grit {'Rooster Cogburn'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Jesse Eisenberg</td>
      <td>The Social Network {'Mark Zuckerberg'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Colin Firth</td>
      <td>The King's Speech {'King George VI'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>James Franco</td>
      <td>127 Hours {'Aron Ralston'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5</th>
      <td>2010</td>
      <td>Actor -- Supporting Role</td>
      <td>Christian Bale</td>
      <td>The Fighter {'Dicky Eklund'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2010</td>
      <td>Actor -- Supporting Role</td>
      <td>John Hawkes</td>
      <td>Winter's Bone {'Teardrop'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7</th>
      <td>2010</td>
      <td>Actor -- Supporting Role</td>
      <td>Jeremy Renner</td>
      <td>The Town {'James Coughlin'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>8</th>
      <td>2010</td>
      <td>Actor -- Supporting Role</td>
      <td>Mark Ruffalo</td>
      <td>The Kids Are All Right {'Paul'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>9</th>
      <td>2010</td>
      <td>Actor -- Supporting Role</td>
      <td>Geoffrey Rush</td>
      <td>The King's Speech {'Lionel Logue'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10</th>
      <td>2010</td>
      <td>Actress -- Leading Role</td>
      <td>Annette Bening</td>
      <td>The Kids Are All Right {'Nic'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>11</th>
      <td>2010</td>
      <td>Actress -- Leading Role</td>
      <td>Nicole Kidman</td>
      <td>Rabbit Hole {'Becca'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>12</th>
      <td>2010</td>
      <td>Actress -- Leading Role</td>
      <td>Jennifer Lawrence</td>
      <td>Winter's Bone {'Ree'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>13</th>
      <td>2010</td>
      <td>Actress -- Leading Role</td>
      <td>Natalie Portman</td>
      <td>Black Swan {'Nina Sayers/The Swan Queen'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>14</th>
      <td>2010</td>
      <td>Actress -- Leading Role</td>
      <td>Michelle Williams</td>
      <td>Blue Valentine {'Cindy'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>15</th>
      <td>2010</td>
      <td>Actress -- Supporting Role</td>
      <td>Amy Adams</td>
      <td>The Fighter {'Charlene Fleming'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>16</th>
      <td>2010</td>
      <td>Actress -- Supporting Role</td>
      <td>Helena Bonham Carter</td>
      <td>The King's Speech {'Queen Elizabeth'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>17</th>
      <td>2010</td>
      <td>Actress -- Supporting Role</td>
      <td>Melissa Leo</td>
      <td>The Fighter {'Alice Ward'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>18</th>
      <td>2010</td>
      <td>Actress -- Supporting Role</td>
      <td>Hailee Steinfeld</td>
      <td>True Grit {'Mattie Ross'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>19</th>
      <td>2010</td>
      <td>Actress -- Supporting Role</td>
      <td>Jacki Weaver</td>
      <td>Animal Kingdom {'Janine 'Smurf' Cody'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>20</th>
      <td>2010</td>
      <td>Animated Feature Film</td>
      <td>How to Train Your Dragon</td>
      <td>Chris Sanders and Dean DeBlois</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>21</th>
      <td>2010</td>
      <td>Animated Feature Film</td>
      <td>The Illusionist</td>
      <td>Sylvain Chomet</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>22</th>
      <td>2010</td>
      <td>Animated Feature Film</td>
      <td>Toy Story 3</td>
      <td>Lee Unkrich</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>23</th>
      <td>2010</td>
      <td>Art Direction</td>
      <td>Alice in Wonderland</td>
      <td>Production Design: Robert Stromberg; Set Decor...</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>24</th>
      <td>2010</td>
      <td>Art Direction</td>
      <td>Harry Potter and the Deathly Hallows Part 1</td>
      <td>Production Design: Stuart Craig; Set Decoratio...</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>25</th>
      <td>2010</td>
      <td>Art Direction</td>
      <td>Inception</td>
      <td>Production Design: Guy Hendrix Dyas; Set Decor...</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>26</th>
      <td>2010</td>
      <td>Art Direction</td>
      <td>The King's Speech</td>
      <td>Production Design: Eve Stewart; Set Decoration...</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>27</th>
      <td>2010</td>
      <td>Art Direction</td>
      <td>True Grit</td>
      <td>Production Design: Jess Gonchor; Set Decoratio...</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>28</th>
      <td>2010</td>
      <td>Cinematography</td>
      <td>Black Swan</td>
      <td>Matthew Libatique</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>29</th>
      <td>2010</td>
      <td>Cinematography</td>
      <td>Inception</td>
      <td>Wally Pfister</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
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
    </tr>
    <tr>
      <th>1264</th>
      <td>2001</td>
      <td>Writing</td>
      <td>Monster's Ball</td>
      <td>Written by Milo Addica &amp; Will Rokos</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1265</th>
      <td>2001</td>
      <td>Writing</td>
      <td>The Royal Tenenbaums</td>
      <td>Written by Wes Anderson &amp; Owen Wilson</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1266</th>
      <td>2001</td>
      <td>Honorary Award</td>
      <td>To Sidney Poitier in recognition of his remark...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1267</th>
      <td>2001</td>
      <td>Honorary Award</td>
      <td>To Robert Redford: Actor, director, producer, ...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1268</th>
      <td>2001</td>
      <td>Jean Hersholt Humanitarian Award</td>
      <td>Arthur Hiller</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1269</th>
      <td>2001</td>
      <td>Scientific and Technical (Scientific and Engin...</td>
      <td>To JOHN M. EARGLE, D.B. DON" KEELE and MARK E....</td>
      <td>design and engineering of the modern constant...</td>
      <td>direct radiator style motion picture loudspea...</td>
      <td>D.B. "Don" Keele and Mark E. Engebretson has ...</td>
      <td>direct radiator bass style cinema loudspeaker...</td>
      <td>NaN</td>
      <td>*</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1270</th>
      <td>2001</td>
      <td>Scientific and Technical (Scientific and Engin...</td>
      <td>To IAIN NEIL for the concept and optical desig...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1271</th>
      <td>2001</td>
      <td>Scientific and Technical (Scientific and Engin...</td>
      <td>To FRANZ KRAUS, JOHANNES STEURER and WOLFGANG ...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1272</th>
      <td>2001</td>
      <td>Scientific and Technical (Scientific and Engin...</td>
      <td>To PETER KURAN for the invention, and SEAN COU...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1273</th>
      <td>2001</td>
      <td>Scientific and Technical (Scientific and Engin...</td>
      <td>To MAKOTO TSUKADA, SHOJI KANEKO and the TECHNI...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1274</th>
      <td>2001</td>
      <td>Scientific and Technical (Scientific and Engin...</td>
      <td>To STEVEN GERLACH, GREGORY FARRELL and CHRISTI...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1275</th>
      <td>2001</td>
      <td>Scientific and Technical (Scientific and Engin...</td>
      <td>To PAUL J. CONSTANTINE and PETER M. CONSTANTIN...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1276</th>
      <td>2001</td>
      <td>Scientific and Technical (Technical Achievemen...</td>
      <td>To PETE ROMANO for the design and development ...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1277</th>
      <td>2001</td>
      <td>Scientific and Technical (Technical Achievemen...</td>
      <td>To JORDAN KLEIN for his pioneering efforts in ...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1278</th>
      <td>2001</td>
      <td>Scientific and Technical (Technical Achievemen...</td>
      <td>To BERNARD M. WERNER and WILLIAM GELOW for the...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1279</th>
      <td>2001</td>
      <td>Scientific and Technical (Technical Achievemen...</td>
      <td>To TOMLINSON HOLMAN for the research and syste...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1280</th>
      <td>2001</td>
      <td>Scientific and Technical (Technical Achievemen...</td>
      <td>To GEOFF JACKSON and ROGER WOODBURN for their ...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1281</th>
      <td>2001</td>
      <td>Scientific and Technical (Technical Achievemen...</td>
      <td>To THOMAS MAJOR BARRON for the overall concept...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1282</th>
      <td>2001</td>
      <td>Scientific and Technical (Technical Achievemen...</td>
      <td>To JOHN R. ANDERSON, JIM HOURIHAN, CARY PHILLI...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1283</th>
      <td>2001</td>
      <td>Scientific and Technical (Technical Achievemen...</td>
      <td>To STEVE SULLIVAN and ERIC R.L. SCHAFER for th...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1284</th>
      <td>2001</td>
      <td>Scientific and Technical (Technical Achievemen...</td>
      <td>To CARL LUDWIG and JOHN M. CONSTANTINE, JR. fo...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1285</th>
      <td>2001</td>
      <td>Scientific and Technical (Technical Achievemen...</td>
      <td>To BILL SPITZAK, PAUL VAN CAMP, JONATHAN EGSTA...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1286</th>
      <td>2001</td>
      <td>Scientific and Technical (Technical Achievemen...</td>
      <td>To DR. LANCE J. WILLIAMS for his pioneering in...</td>
      <td>Pyramidal Parametrics" and "View Interpolatio...</td>
      <td>NO</td>
      <td>*</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1287</th>
      <td>2001</td>
      <td>Scientific and Technical (Technical Achievemen...</td>
      <td>To DR. UWE SASSENBERG and ROLF SCHNEIDER for t...</td>
      <td>an advanced and robust camera and object matc...</td>
      <td>which significantly reduces the need for pain...</td>
      <td>error-prone measurements on sets. [Digital Im...</td>
      <td>NaN</td>
      <td>*</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1288</th>
      <td>2001</td>
      <td>Scientific and Technical (Technical Achievemen...</td>
      <td>To DR. GARLAND STERN for the concept and imple...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1289</th>
      <td>2001</td>
      <td>Scientific and Technical (Technical Achievemen...</td>
      <td>To MIC RODGERS and MATT SWEENEY for the concep...</td>
      <td>low bed picture car carrier and camera platfo...</td>
      <td>economic and realistic filming of action sequ...</td>
      <td>NaN</td>
      <td>*</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1290</th>
      <td>2001</td>
      <td>Scientific and Technical (Gordon E. Sawyer Award)</td>
      <td>Edmund M. Di Giulio</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1291</th>
      <td>2001</td>
      <td>Scientific and Technical (Bonner Medal)</td>
      <td>To Ray Feeney in appreciation for outstanding ...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1292</th>
      <td>2001</td>
      <td>Scientific and Technical (Special Awards)</td>
      <td>To Rune Ericson for his pioneering development...</td>
      <td>NaN</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1293</th>
      <td>2001</td>
      <td>Scientific and Technical (Special Awards)</td>
      <td>To the American Society of Cinematographers (A...</td>
      <td>first published by the ASC in 1930, the Ameri...</td>
      <td>this premier reference manual has had a signi...</td>
      <td>NaN</td>
      <td>*</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>1294 rows × 11 columns</p>
</div>




```python
award_categories = ["Actor -- Leading Role", "Actor -- Supporting Role", "Actress -- Leading Role", "Actress -- Supporting Role"]
nominations = later_than_2000[later_than_2000["Category"].isin(award_categories)].copy()
nominations
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
      <th>Year</th>
      <th>Category</th>
      <th>Nominee</th>
      <th>Additional Info</th>
      <th>Won?</th>
      <th>Unnamed: 5</th>
      <th>Unnamed: 6</th>
      <th>Unnamed: 7</th>
      <th>Unnamed: 8</th>
      <th>Unnamed: 9</th>
      <th>Unnamed: 10</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Javier Bardem</td>
      <td>Biutiful {'Uxbal'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Jeff Bridges</td>
      <td>True Grit {'Rooster Cogburn'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Jesse Eisenberg</td>
      <td>The Social Network {'Mark Zuckerberg'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Colin Firth</td>
      <td>The King's Speech {'King George VI'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>James Franco</td>
      <td>127 Hours {'Aron Ralston'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5</th>
      <td>2010</td>
      <td>Actor -- Supporting Role</td>
      <td>Christian Bale</td>
      <td>The Fighter {'Dicky Eklund'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2010</td>
      <td>Actor -- Supporting Role</td>
      <td>John Hawkes</td>
      <td>Winter's Bone {'Teardrop'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7</th>
      <td>2010</td>
      <td>Actor -- Supporting Role</td>
      <td>Jeremy Renner</td>
      <td>The Town {'James Coughlin'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>8</th>
      <td>2010</td>
      <td>Actor -- Supporting Role</td>
      <td>Mark Ruffalo</td>
      <td>The Kids Are All Right {'Paul'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>9</th>
      <td>2010</td>
      <td>Actor -- Supporting Role</td>
      <td>Geoffrey Rush</td>
      <td>The King's Speech {'Lionel Logue'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>10</th>
      <td>2010</td>
      <td>Actress -- Leading Role</td>
      <td>Annette Bening</td>
      <td>The Kids Are All Right {'Nic'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>11</th>
      <td>2010</td>
      <td>Actress -- Leading Role</td>
      <td>Nicole Kidman</td>
      <td>Rabbit Hole {'Becca'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>12</th>
      <td>2010</td>
      <td>Actress -- Leading Role</td>
      <td>Jennifer Lawrence</td>
      <td>Winter's Bone {'Ree'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>13</th>
      <td>2010</td>
      <td>Actress -- Leading Role</td>
      <td>Natalie Portman</td>
      <td>Black Swan {'Nina Sayers/The Swan Queen'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>14</th>
      <td>2010</td>
      <td>Actress -- Leading Role</td>
      <td>Michelle Williams</td>
      <td>Blue Valentine {'Cindy'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>15</th>
      <td>2010</td>
      <td>Actress -- Supporting Role</td>
      <td>Amy Adams</td>
      <td>The Fighter {'Charlene Fleming'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>16</th>
      <td>2010</td>
      <td>Actress -- Supporting Role</td>
      <td>Helena Bonham Carter</td>
      <td>The King's Speech {'Queen Elizabeth'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>17</th>
      <td>2010</td>
      <td>Actress -- Supporting Role</td>
      <td>Melissa Leo</td>
      <td>The Fighter {'Alice Ward'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>18</th>
      <td>2010</td>
      <td>Actress -- Supporting Role</td>
      <td>Hailee Steinfeld</td>
      <td>True Grit {'Mattie Ross'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>19</th>
      <td>2010</td>
      <td>Actress -- Supporting Role</td>
      <td>Jacki Weaver</td>
      <td>Animal Kingdom {'Janine 'Smurf' Cody'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>135</th>
      <td>2009</td>
      <td>Actor -- Leading Role</td>
      <td>Jeff Bridges</td>
      <td>Crazy Heart {'Bad Blake'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>136</th>
      <td>2009</td>
      <td>Actor -- Leading Role</td>
      <td>George Clooney</td>
      <td>Up in the Air {'Ryan Bingham'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>137</th>
      <td>2009</td>
      <td>Actor -- Leading Role</td>
      <td>Colin Firth</td>
      <td>A Single Man {'George'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>138</th>
      <td>2009</td>
      <td>Actor -- Leading Role</td>
      <td>Morgan Freeman</td>
      <td>Invictus {'Nelson Mandela'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>139</th>
      <td>2009</td>
      <td>Actor -- Leading Role</td>
      <td>Jeremy Renner</td>
      <td>The Hurt Locker {'Staff Sergeant William James'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>140</th>
      <td>2009</td>
      <td>Actor -- Supporting Role</td>
      <td>Matt Damon</td>
      <td>Invictus {'Francois Pienaar'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>141</th>
      <td>2009</td>
      <td>Actor -- Supporting Role</td>
      <td>Woody Harrelson</td>
      <td>The Messenger {'Captain Tony Stone'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>142</th>
      <td>2009</td>
      <td>Actor -- Supporting Role</td>
      <td>Christopher Plummer</td>
      <td>The Last Station {'Tolstoy'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>143</th>
      <td>2009</td>
      <td>Actor -- Supporting Role</td>
      <td>Stanley Tucci</td>
      <td>The Lovely Bones {'George Harvey'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>144</th>
      <td>2009</td>
      <td>Actor -- Supporting Role</td>
      <td>Christoph Waltz</td>
      <td>Inglourious Basterds {'Col. Hans Landa'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
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
    </tr>
    <tr>
      <th>1040</th>
      <td>2002</td>
      <td>Actress -- Leading Role</td>
      <td>Salma Hayek</td>
      <td>Frida {'Frida Kahlo'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1041</th>
      <td>2002</td>
      <td>Actress -- Leading Role</td>
      <td>Nicole Kidman</td>
      <td>The Hours {'Virginia Woolf'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1042</th>
      <td>2002</td>
      <td>Actress -- Leading Role</td>
      <td>Diane Lane</td>
      <td>Unfaithful {'Connie Sumner'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1043</th>
      <td>2002</td>
      <td>Actress -- Leading Role</td>
      <td>Julianne Moore</td>
      <td>Far from Heaven {'Cathy Whitaker'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1044</th>
      <td>2002</td>
      <td>Actress -- Leading Role</td>
      <td>Renée Zellweger</td>
      <td>Chicago {'Roxie Hart'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1045</th>
      <td>2002</td>
      <td>Actress -- Supporting Role</td>
      <td>Kathy Bates</td>
      <td>About Schmidt {'Roberta Hertzel'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1046</th>
      <td>2002</td>
      <td>Actress -- Supporting Role</td>
      <td>Julianne Moore</td>
      <td>The Hours {'Laura Brown'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1047</th>
      <td>2002</td>
      <td>Actress -- Supporting Role</td>
      <td>Queen Latifah</td>
      <td>Chicago {'Matron Mama Morton'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1048</th>
      <td>2002</td>
      <td>Actress -- Supporting Role</td>
      <td>Meryl Streep</td>
      <td>Adaptation {'Susan Orlean'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1049</th>
      <td>2002</td>
      <td>Actress -- Supporting Role</td>
      <td>Catherine Zeta-Jones</td>
      <td>Chicago {'Velma Kelly'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1157</th>
      <td>2001</td>
      <td>Actor -- Leading Role</td>
      <td>Russell Crowe</td>
      <td>A Beautiful Mind {'John Nash'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1158</th>
      <td>2001</td>
      <td>Actor -- Leading Role</td>
      <td>Sean Penn</td>
      <td>I Am Sam {'Sam Dawson'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1159</th>
      <td>2001</td>
      <td>Actor -- Leading Role</td>
      <td>Will Smith</td>
      <td>Ali {'Muhammad Ali'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1160</th>
      <td>2001</td>
      <td>Actor -- Leading Role</td>
      <td>Denzel Washington</td>
      <td>Training Day {'Alonzo'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1161</th>
      <td>2001</td>
      <td>Actor -- Leading Role</td>
      <td>Tom Wilkinson</td>
      <td>In the Bedroom {'Matt Fowler'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1162</th>
      <td>2001</td>
      <td>Actor -- Supporting Role</td>
      <td>Jim Broadbent</td>
      <td>Iris {'John Bayley'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1163</th>
      <td>2001</td>
      <td>Actor -- Supporting Role</td>
      <td>Ethan Hawke</td>
      <td>Training Day {'Jake'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1164</th>
      <td>2001</td>
      <td>Actor -- Supporting Role</td>
      <td>Ben Kingsley</td>
      <td>Sexy Beast {'Don Logan'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1165</th>
      <td>2001</td>
      <td>Actor -- Supporting Role</td>
      <td>Ian McKellen</td>
      <td>The Lord of the Rings: The Fellowship of the R...</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1166</th>
      <td>2001</td>
      <td>Actor -- Supporting Role</td>
      <td>Jon Voight</td>
      <td>Ali {'Howard Cosell'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1167</th>
      <td>2001</td>
      <td>Actress -- Leading Role</td>
      <td>Halle Berry</td>
      <td>Monster's Ball {'Leticia Musgrove'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1168</th>
      <td>2001</td>
      <td>Actress -- Leading Role</td>
      <td>Judi Dench</td>
      <td>Iris {'Iris Murdoch'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1169</th>
      <td>2001</td>
      <td>Actress -- Leading Role</td>
      <td>Nicole Kidman</td>
      <td>Moulin Rouge {'Satine'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1170</th>
      <td>2001</td>
      <td>Actress -- Leading Role</td>
      <td>Sissy Spacek</td>
      <td>In the Bedroom {'Ruth Fowler'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1171</th>
      <td>2001</td>
      <td>Actress -- Leading Role</td>
      <td>Renée Zellweger</td>
      <td>Bridget Jones's Diary {'Bridget Jones'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1172</th>
      <td>2001</td>
      <td>Actress -- Supporting Role</td>
      <td>Jennifer Connelly</td>
      <td>A Beautiful Mind {'Alicia Nash'}</td>
      <td>YES</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1173</th>
      <td>2001</td>
      <td>Actress -- Supporting Role</td>
      <td>Helen Mirren</td>
      <td>Gosford Park {'Mrs. Wilson'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1174</th>
      <td>2001</td>
      <td>Actress -- Supporting Role</td>
      <td>Maggie Smith</td>
      <td>Gosford Park {'Constance, Countess of Trentham'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1175</th>
      <td>2001</td>
      <td>Actress -- Supporting Role</td>
      <td>Marisa Tomei</td>
      <td>In the Bedroom {'Natalie Strout'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1176</th>
      <td>2001</td>
      <td>Actress -- Supporting Role</td>
      <td>Kate Winslet</td>
      <td>Iris {'Young Iris Murdoch'}</td>
      <td>NO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>200 rows × 11 columns</p>
</div>



### Cleaning Up the Won and Unnamed columns


```python
# mapping yes/no to 1/0 and renaming Won? to Won
yes_no_switch = {"YES": 1, "NO": 0}
nominations["Won?"] = nominations["Won?"].map(yes_no_switch)
nominations["Won"] = nominations["Won?"]

# removing all the unnamed columns
col_drop = ["Won?","Unnamed: 5","Unnamed: 6","Unnamed: 7","Unnamed: 8","Unnamed: 9","Unnamed: 10"]
final_nominations = nominations.drop(col_drop,axis=1)

final_nominations.head()
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
      <th>Year</th>
      <th>Category</th>
      <th>Nominee</th>
      <th>Additional Info</th>
      <th>Won</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Javier Bardem</td>
      <td>Biutiful {'Uxbal'}</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Jeff Bridges</td>
      <td>True Grit {'Rooster Cogburn'}</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Jesse Eisenberg</td>
      <td>The Social Network {'Mark Zuckerberg'}</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Colin Firth</td>
      <td>The King's Speech {'King George VI'}</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>James Franco</td>
      <td>127 Hours {'Aron Ralston'}</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>



### Cleaning up the Additional Info column


```python
additional_info_one = final_nominations["Additional Info"].str.rstrip("'}")
additional_info_two = additional_info_one.str.split(" {'")

movie_names = additional_info_two.str[0]
characters = additional_info_two.str[1]

final_nominations["Movie"] = movie_names
final_nominations["Character"] = characters

final_nominations = final_nominations.drop("Additional Info", axis=1)

final_nominations.head()
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
      <th>Year</th>
      <th>Category</th>
      <th>Nominee</th>
      <th>Won</th>
      <th>Movie</th>
      <th>Character</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Javier Bardem</td>
      <td>0</td>
      <td>Biutiful</td>
      <td>Uxbal</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Jeff Bridges</td>
      <td>0</td>
      <td>True Grit</td>
      <td>Rooster Cogburn</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Jesse Eisenberg</td>
      <td>0</td>
      <td>The Social Network</td>
      <td>Mark Zuckerberg</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Colin Firth</td>
      <td>1</td>
      <td>The King's Speech</td>
      <td>King George VI</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>James Franco</td>
      <td>0</td>
      <td>127 Hours</td>
      <td>Aron Ralston</td>
    </tr>
  </tbody>
</table>
</div>



### Exporting to SQLite


```python
import sqlite3 as sql

conn = sql.connect("nominations.db")
final_nominations.to_sql("nominations", conn,  if_exists='replace', index=False)
```

### Veryfing in SQL

Let's now query the database to make sure everything worked as expected.


```python
q1 = '''pragma table_info("nominations")'''
pd.read_sql_query(q1, conn)
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
      <th>cid</th>
      <th>name</th>
      <th>type</th>
      <th>notnull</th>
      <th>dflt_value</th>
      <th>pk</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Year</td>
      <td>INTEGER</td>
      <td>0</td>
      <td>None</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Category</td>
      <td>TEXT</td>
      <td>0</td>
      <td>None</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Nominee</td>
      <td>TEXT</td>
      <td>0</td>
      <td>None</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Won</td>
      <td>INTEGER</td>
      <td>0</td>
      <td>None</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Movie</td>
      <td>TEXT</td>
      <td>0</td>
      <td>None</td>
      <td>0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>5</td>
      <td>Character</td>
      <td>TEXT</td>
      <td>0</td>
      <td>None</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```python
q2 = '''
select * from nominations limit 10
'''
pd.read_sql_query(q2, conn)
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
      <th>Year</th>
      <th>Category</th>
      <th>Nominee</th>
      <th>Won</th>
      <th>Movie</th>
      <th>Character</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Javier Bardem</td>
      <td>0</td>
      <td>Biutiful</td>
      <td>Uxbal</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Jeff Bridges</td>
      <td>0</td>
      <td>True Grit</td>
      <td>Rooster Cogburn</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Jesse Eisenberg</td>
      <td>0</td>
      <td>The Social Network</td>
      <td>Mark Zuckerberg</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>Colin Firth</td>
      <td>1</td>
      <td>The King's Speech</td>
      <td>King George VI</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2010</td>
      <td>Actor -- Leading Role</td>
      <td>James Franco</td>
      <td>0</td>
      <td>127 Hours</td>
      <td>Aron Ralston</td>
    </tr>
    <tr>
      <th>5</th>
      <td>2010</td>
      <td>Actor -- Supporting Role</td>
      <td>Christian Bale</td>
      <td>1</td>
      <td>The Fighter</td>
      <td>Dicky Eklund</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2010</td>
      <td>Actor -- Supporting Role</td>
      <td>John Hawkes</td>
      <td>0</td>
      <td>Winter's Bone</td>
      <td>Teardrop</td>
    </tr>
    <tr>
      <th>7</th>
      <td>2010</td>
      <td>Actor -- Supporting Role</td>
      <td>Jeremy Renner</td>
      <td>0</td>
      <td>The Town</td>
      <td>James Coughlin</td>
    </tr>
    <tr>
      <th>8</th>
      <td>2010</td>
      <td>Actor -- Supporting Role</td>
      <td>Mark Ruffalo</td>
      <td>0</td>
      <td>The Kids Are All Right</td>
      <td>Paul</td>
    </tr>
    <tr>
      <th>9</th>
      <td>2010</td>
      <td>Actor -- Supporting Role</td>
      <td>Geoffrey Rush</td>
      <td>0</td>
      <td>The King's Speech</td>
      <td>Lionel Logue</td>
    </tr>
  </tbody>
</table>
</div>




```python
conn.close()
```


```python

```
