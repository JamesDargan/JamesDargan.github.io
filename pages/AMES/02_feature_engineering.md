## AMES Housing Regression ([Repo](https://github.com/JamesDargan/AMES))

**Project Component:**
After cleaning the dataset and imputing missing values, I perform extensive EDA of various features. I proceed to derive many dummy variables from these features to either 1) isolate relevant distinction from within non-ordinal values, 2) bin ordinal features to capture meaningful layers, and 3) sum discrete counts to produce a linear relationship, 4) separate continuous variable by category identify to isolate divergent linear relationships with the target.
<br><br>

**My Project Medium Blogs:**<br>
[AMES Data Cleaning]()<br>
<br>


**Feature Transformations:**<br>
 - Apply log transform to saleprice to create a more normally distributed target
 - Apply log transform to area and length features to preserve linear relationship to target
 - Add square of age since remodel to capture nonlinear relationship

**Binning of Features**
- Dummy over/under condition rating of 5 to capture level jump
- Group irregular lot shapes to capture homogenous difference from regular lots
- Round half-story structures down to whole due to low observation counts
- Group all lesser electrical systems due to low observation counts
- Group unpaved drives together due to low observation counts
- Group functional components due to low observation counts

**Derived Dummy Features**
- Create fence dummy from misc feature
- Create adjacent major road dummy from conditions
- Create adjacent railroad dummy from conditions
- Create adjacent positive feature from conditions

**Derived Continuous Features**
- Sum all bathroom features to create smooth linear relationship
- Separate attached and detached garage square footage
- Square footage per room
- Non-basement square footage per bedroom
- Bathrooms per bedroom
- Age since remodel at time of sale


**Why It Matters:**
Inputting high-quality features improves model performance. Some raw features collected on a scale may not be linearly related to the target, but instead have discrete jumps in average at certain points along the scale. Binning these values or creating a dummy can enable a linear model to capture that true relationship. Similarly, raw data can break down components too small to reflect the overall relationship, for example total baths better reflects consumer preference than a breakdown of every type and location of bathroom. Furthermore, raw data can provide features which in isolation explain less than the ratio of one to the other.
