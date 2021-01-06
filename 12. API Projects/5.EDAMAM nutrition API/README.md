# EDAMAM nutrition API 🍔🥤

### This [nutrition API](https://developer.edamam.com/edamam-docs-nutrition-api) can be used for:  
- Full analysis of food recipes in real-time
    - Entity extraction, measure, and quantity extraction with computation of the applicable nutrition for the recipe and applicable health and diet labels. 
    - Finally, it adjusts quantity for certain ingredients to account for the cooking process. 
    - For example, it calculates oil absorption for fried recipes, excludes solids from stock and broth recipes, calculates marinate absorption for marinates, and much more.
- Extraction of food entities with measures and quantities from unstructured text.
- Usage in chatbots transcribing natural speech to text.

### This API is paid and requires registration but it offers a free demo with some limitations.

- Learned to interact with the [EDAMAM API](https://developer.edamam.com/) using python and the requests library.
- Explored different types of endpoints, parameters, and responses of the API.
- A POST request has to be made to the API endpoint with the name and ingredients of the recipe.

##### We define the recipe as a dictionary:  
- the key 'title' contains the name of the recipe
- the key 'ingr' is a list of ingredients
```python
recipe = {
    'title': 'Mango milkshake',
    'ingr': ['2 mangoes', '1.5 cups milk', '2 tablespoons sugar']
}
```
- Details like calories, total weight, diet labels, health labels, cautions, total nutrients, ingredients, and total nutrients KCal is provided to us.
- The API uses Natural Language Processing to understand and process the recipe ingredients.
- Exported the entire response of the API as a [JSON file](https://raw.githubusercontent.com/Prajwalsrinvas/web-scraping-projects/main/12.%20API%20Projects/5.EDAMAM%20nutrition%20API/mango_milkshake_data.json) for any further use.
- Created dataframes for different nutritional analysis datapoints.


# Total Nutrients

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>label</th>
      <th>quantity</th>
      <th>unit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>ENERC_KCAL</th>
      <td>Energy</td>
      <td>723.21</td>
      <td>kcal</td>
    </tr>
    <tr>
      <th>FAT</th>
      <td>Fat</td>
      <td>14.4486</td>
      <td>g</td>
    </tr>
    <tr>
      <th>FASAT</th>
      <td>Saturated</td>
      <td>7.44414</td>
      <td>g</td>
    </tr>
    <tr>
      <th>FAMS</th>
      <td>Monounsaturated</td>
      <td>3.91272</td>
      <td>g</td>
    </tr>
    <tr>
      <th>FAPU</th>
      <td>Polyunsaturated</td>
      <td>1.19082</td>
      <td>g</td>
    </tr>
    <tr>
      <th>CHOCDF</th>
      <td>Carbs</td>
      <td>143.229</td>
      <td>g</td>
    </tr>
    <tr>
      <th>FIBTG</th>
      <td>Fiber</td>
      <td>10.752</td>
      <td>g</td>
    </tr>
    <tr>
      <th>SUGAR</th>
      <td>Sugars</td>
      <td>135.228</td>
      <td>g</td>
    </tr>
    <tr>
      <th>SUGAR.added</th>
      <td>Sugars, added</td>
      <td>24.95</td>
      <td>g</td>
    </tr>
    <tr>
      <th>PROCNT</th>
      <td>Protein</td>
      <td>17.0394</td>
      <td>g</td>
    </tr>
  </tbody>
</table>
</div>





# % daily value
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>label</th>
      <th>quantity</th>
      <th>unit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>ENERC_KCAL</th>
      <td>Energy</td>
      <td>36.1605</td>
      <td>%</td>
    </tr>
    <tr>
      <th>FAT</th>
      <td>Fat</td>
      <td>22.2286</td>
      <td>%</td>
    </tr>
    <tr>
      <th>FASAT</th>
      <td>Saturated</td>
      <td>37.2207</td>
      <td>%</td>
    </tr>
    <tr>
      <th>CHOCDF</th>
      <td>Carbs</td>
      <td>47.7429</td>
      <td>%</td>
    </tr>
    <tr>
      <th>FIBTG</th>
      <td>Fiber</td>
      <td>43.008</td>
      <td>%</td>
    </tr>
    <tr>
      <th>PROCNT</th>
      <td>Protein</td>
      <td>34.0788</td>
      <td>%</td>
    </tr>
    <tr>
      <th>CHOLE</th>
      <td>Cholesterol</td>
      <td>12.2</td>
      <td>%</td>
    </tr>
    <tr>
      <th>NA</th>
      <td>Sodium</td>
      <td>6.84792</td>
      <td>%</td>
    </tr>
    <tr>
      <th>CA</th>
      <td>Calcium</td>
      <td>48.775</td>
      <td>%</td>
    </tr>
    <tr>
      <th>MG</th>
      <td>Magnesium</td>
      <td>24.7143</td>
      <td>%</td>
    </tr>
  </tbody>
</table>
</div>




# Details of Mangoes 🥭
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>quantity</th>
      <td>2</td>
    </tr>
    <tr>
      <th>measure</th>
      <td>whole</td>
    </tr>
    <tr>
      <th>foodMatch</th>
      <td>mangoes</td>
    </tr>
    <tr>
      <th>food</th>
      <td>mangos</td>
    </tr>
    <tr>
      <th>foodId</th>
      <td>food_an1dqoib8xj3tyb3pr7c0abi4rbw</td>
    </tr>
    <tr>
      <th>weight</th>
      <td>672</td>
    </tr>
    <tr>
      <th>retainedWeight</th>
      <td>672</td>
    </tr>
    <tr>
      <th>nutrients</th>
      <td>{'VITD': {'label': 'Vitamin D', 'quantity': 0....</td>
    </tr>
    <tr>
      <th>measureURI</th>
      <td>http://www.edamam.com/ontologies/edamam.owl#Me...</td>
    </tr>
    <tr>
      <th>status</th>
      <td>OK</td>
    </tr>
  </tbody>
</table>
</div>





# Details of Milk 🥛




<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>quantity</th>
      <td>1.5</td>
    </tr>
    <tr>
      <th>measure</th>
      <td>cup</td>
    </tr>
    <tr>
      <th>foodMatch</th>
      <td>milk</td>
    </tr>
    <tr>
      <th>food</th>
      <td>whole milk</td>
    </tr>
    <tr>
      <th>foodId</th>
      <td>food_b49rs1kaw0jktabzkg2vvanvvsis</td>
    </tr>
    <tr>
      <th>weight</th>
      <td>366</td>
    </tr>
    <tr>
      <th>retainedWeight</th>
      <td>366</td>
    </tr>
    <tr>
      <th>nutrients</th>
      <td>{'VITD': {'label': 'Vitamin D', 'quantity': 18...</td>
    </tr>
    <tr>
      <th>measureURI</th>
      <td>http://www.edamam.com/ontologies/edamam.owl#Me...</td>
    </tr>
    <tr>
      <th>status</th>
      <td>OK</td>
    </tr>
  </tbody>
</table>
</div>





# Details of Sugar 🍬
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>quantity</th>
      <td>2</td>
    </tr>
    <tr>
      <th>measure</th>
      <td>tablespoon</td>
    </tr>
    <tr>
      <th>foodMatch</th>
      <td>sugar</td>
    </tr>
    <tr>
      <th>food</th>
      <td>granulated sugar</td>
    </tr>
    <tr>
      <th>foodId</th>
      <td>food_axi2ijobrk819yb0adceobnhm1c2</td>
    </tr>
    <tr>
      <th>weight</th>
      <td>25</td>
    </tr>
    <tr>
      <th>retainedWeight</th>
      <td>25</td>
    </tr>
    <tr>
      <th>nutrients</th>
      <td>{'RIBF': {'label': 'Riboflavin', 'quantity': 0...</td>
    </tr>
    <tr>
      <th>measureURI</th>
      <td>http://www.edamam.com/ontologies/edamam.owl#Me...</td>
    </tr>
    <tr>
      <th>status</th>
      <td>OK</td>
    </tr>
  </tbody>
</table>
</div>





# Total Nutrients KCal
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>label</th>
      <th>quantity</th>
      <th>unit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>ENERC_KCAL</th>
      <td>Energy</td>
      <td>723</td>
      <td>kcal</td>
    </tr>
    <tr>
      <th>PROCNT_KCAL</th>
      <td>Calories from protein</td>
      <td>64</td>
      <td>kcal</td>
    </tr>
    <tr>
      <th>FAT_KCAL</th>
      <td>Calories from fat</td>
      <td>122</td>
      <td>kcal</td>
    </tr>
    <tr>
      <th>CHOCDF_KCAL</th>
      <td>Calories from carbohydrates</td>
      <td>537</td>
      <td>kcal</td>
    </tr>
  </tbody>
</table>
</div>
