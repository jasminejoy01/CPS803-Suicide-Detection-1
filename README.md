# Suicide Detection (CPS803)
### Abstract 
Project uses ML techniques in detecting a probable suicide message based on social media posts. 
For this purpose, we will train and test classifiers such as Naïve Bayes, Support Vector Model, Logistic Regression and MLP to distinguish Reddit posts that indicate suicide and non-suicide. 
The word associations derived from each method is used to identify posts with suicidal tendencies.

### Datasets <br>
 <table>
    <thead>
      <tr>
        <th>Datasets</th>
        <th>Intended Use</th>
        <th>Rows</th>
        <th>Description</th>
      </tr>
    </thead>
    <tbody>
        <tr>
            <td><i>Suicide Detection</i></td>
            <td>Training</td>
            <td>232,074</td>
            <td>Data from Kaggle. Data contains reddit posts that have been labelled as suicide and non-suicide.</td>
        </tr>
        <tr>
            <td><i>Suicide Notes</i></td>
            <td>Test</td>
            <td>464</td>
            <td>Data from Kaggle. Notes written by users who were confirmed with suicidal tendencies.</td>
        </tr>
            <tr>
            <td><i>r/depression r/SuicideWatch</i></td>
            <td>Test</td>
            <td>20,364</td>
            <td>Data from Kaggle. Data contains reddit posts from r/depression and r/suicidewatch.</td>
        </tr>
    </tbody>
  </table>
  
### Procedure
![Untitled Diagram drawio](https://user-images.githubusercontent.com/55416635/142925329-23ffc099-be9a-44a6-9583-97bd35442513.png)
### Preliminary Results

#### Suicide Detection Train-Test Split <br>
<table>
    <thead>
      <tr>
        <th>Model</th>
        <th>BERT Accuracy</th>
        <th>Count Vectorize Accuracy</th>
      </tr>
    </thead>
    <tbody>
        <tr>
            <td><i>Logistic Regression</i></td>
            <td>81.08</td>
            <td>93.19</td>
        </tr>
        <tr>
            <td><i>Bernoulli Naive Bayes</i></td>
            <td>82.33</td>
            <td>77.75</td>
        </tr>
            <tr>
            <td><i>Multinomial Naive Bayes</i></td>
            <td>82.33</td>
            <td>90.25</td>
        </tr>
        </tr>
            <tr>
            <td><i>SVM</i></td>
            <td>82.33</td>
            <td>92.55</td>
        </tr>
        </tr>
            <tr>
            <td><i>Random Forest</i></td>
            <td>82.35</td>
            <td>75.71</td>
        </tr>
    </tbody>
  </table>


#### suicide_notes <br>
<table>
    <thead>
      <tr>
        <th>Model</th>
        <th>BERT Accuracy</th>
        <th>Count Vectorize Accuracy</th>
      </tr>
    </thead>
    <tbody>
        <tr>
            <td><i>Logistic Regression</i></td>
            <td>59.50</td>
            <td>83.41</td>
        </tr>
        <tr>
            <td><i>Bernoulli Naive Bayes</i></td>
            <td>52.86</td>
            <td>59.05</td>
        </tr>
            <tr>
            <td><i>Multinomial Naive Bayes</i></td>
            <td>36.16</td>
            <td>94.83</td>
        </tr>
        </tr>
            <tr>
            <td><i>SVM</i></td>
            <td>59.04</td>
            <td>78.66</td>
        </tr>
        </tr>
            <tr>
            <td><i>Random Forest</i></td>
            <td>63.39</td>
            <td>55.17</td>
        </tr>
    </tbody>
  </table>

#### reddit_depression_suicidewatch <br>
<table>
    <thead>
      <tr>
        <th>Model</th>
        <th>BERT Accuracy</th>
        <th>Count Vectorize Accuracy</th>
      </tr>
    </thead>
    <tbody>
        <tr>
            <td><i>Logistic Regression</i></td>
            <td>44.98</td>
            <td>54.61</td>
        </tr>
        <tr>
            <td><i>Bernoulli Naive Bayes</i></td>
            <td>45.02</td>
            <td>45.30</td>
        </tr>
            <tr>
            <td><i>Multinomial Naive Bayes</i></td>
            <td>45.45</td>
            <td>49.43</td>
        </tr>
        </tr>
            <tr>
            <td><i>SVM</i></td>
            <td>44.86</td>
            <td>54.58</td>
        </tr>
        </tr>
            <tr>
            <td><i>Random Forest</i></td>
            <td>44.69</td>
            <td>45.65</td>
        </tr>
    </tbody>
  </table>


### Key Concepts <br>
 <table>
    <thead>
      <tr>
        <th>Datasets</th>
        <th>True Positives</th>
        <th>False Positives</th>
        <th>False Negatives</th>
      </tr>
    </thead>
    <tbody>
        <tr>
            <td><i>Sample 100</i></td>
            <td>probably a coward, way of life, bad things, better go, don’t want to feel sorry anymore, want to take their life, felling hurt, lost things, can’t find meaning in their life</td>
            <td>really like to go on a date, struggling to ask someone out, asking a friend out, way of life, things were simpler back in school, mentions words like "girlfriend" & "past"</td>
            <td>anyone want to talk, loneliness, depression, thoughts of suicide, therapists</td>
        </tr>
        <tr>
            <td><i>Suicide Notes</i></td>
            <td>mentions caring for family and friends (people around them), thoughts to kill oneself</td>
            <td></td>
            <td>hurt, afraid and wondering about pain and death, sorry, want to cry, wondering if someone hears them, sad hours</td>
        </tr>
            <tr>
            <td><i>r/depression r/SuicideWatch</i></td>
            <td>believe they will never be happy, would like to see their family happy, better if they are dead, wishing life ended, feel useless, wishing things could change or were different</td>
            <td>depressed, hating life, recent, way of life, references to the past</td>
            <td>anxiety, panicking, use of medications, call for help</td>
        </tr>
    </tbody>
  </table>

### Themes <br>
| Datasets                     | True Positives        | False Positives | False Negatives         |
| -----------------------------|:---------------------:| ---------------:| -----------------------:|
| *Sample 100*                 | regret                | social anxiety  | loneliness & depression |
| *Suicide Notes*              | goodbye notes         |                 | loneliness & anxiety    |
| *r/depression r/SuicideWatch*| regret & goodbye notes| social anxiety  | loneliness & anxiety    |

