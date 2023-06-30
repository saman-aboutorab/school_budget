## Introduction

In this project, we will be looking at data from US School Improvement
Grants in 2010. This program gave nearly \$4B to schools to help them
renovate or improve their programs.
:::

::: {.cell .code execution_count="1" id="MPjlrEH_-f3U"}
``` python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```
:::

::: {.cell .markdown}
![school](vertopal_3cfe4f90602f4c2e9fb0fa8f50dddac6/c35c6dd7b9a4663ce36c113dafc0b97bb196a023.png)
:::

::: {.cell .markdown id="V_Ts9d8yAUNc"}
## Dataset
:::

::: {.cell .code execution_count="3" colab="{\"base_uri\":\"https://localhost:8080/\"}" id="9eJTBHPBATQi" outputId="0b46d7b7-63d5-4033-971c-5caf66f32f3a"}
``` python
df = pd.read_csv('schoolimprovement2010grants.csv')
print(df.head())
```

::: {.output .stream .stdout}
       Unnamed: 0                        School Name      City State  \
    0           0  HOGARTH KINGEEKUK MEMORIAL SCHOOL  SAVOONGA    AK   
    1           1                    AKIACHAK SCHOOL  AKIACHAK    AK   
    2           2                     GAMBELL SCHOOL   GAMBELL    AK   
    3           3               BURCHELL HIGH SCHOOL   WASILLA    AK   
    4           4                       AKIAK SCHOOL     AKIAK    AK   

                                   District Name  Model Selected  Award_Amount  \
    0              BERING STRAIT SCHOOL DISTRICT  Transformation        471014   
    1                     YUPIIT SCHOOL DISTRICT  Transformation        520579   
    2              BERING STRAIT SCHOOL DISTRICT  Transformation        449592   
    3  MATANUSKA-SUSITNA BOROUGH SCHOOL DISTRICT  Transformation        641184   
    4                     YUPIIT SCHOOL DISTRICT  Transformation        399686   

      Region  
    0   West  
    1   West  
    2   West  
    3   West  
    4   West  
:::
:::

::: {.cell .code execution_count="11" id="EihcOneoA978"}
``` python
sns.set_palette("rocket")
```
:::

::: {.cell .code execution_count="12" colab="{\"base_uri\":\"https://localhost:8080/\",\"height\":506}" id="qwKA6E6GA1vB" outputId="eff81f6d-2418-4c77-fdd8-4db0f4c9b861"}
``` python
# Create a displot of the Award Amount
sns.displot(df['Award_Amount'],
             kind='kde',
             rug=True,
             fill=True)

# Plot the results
plt.show()
```

::: {.output .display_data}
![](vertopal_3cfe4f90602f4c2e9fb0fa8f50dddac6/d0385e89ef7fb5277bafef2542dd31db13bcead3.png)
:::
:::

::: {.cell .code execution_count="15" colab="{\"base_uri\":\"https://localhost:8080/\",\"height\":467}" id="Rnw9ohc1-jNa" outputId="63de0c29-b5e2-49c7-d43a-4d35f9e13daa"}
``` python
# Create a barplot with each Region shown as a different color
sns.barplot(data=df,
         y='Award_Amount',
         x='Model Selected',
         hue='Region')

plt.show()
plt.clf()
```

::: {.output .display_data}
![](vertopal_3cfe4f90602f4c2e9fb0fa8f50dddac6/98588a0e24734c4197cb0cf8f99c3836588b5856.png)
:::

::: {.output .display_data}
    <Figure size 640x480 with 0 Axes>
:::
:::

::: {.cell .code id="Ytewhu0eAaWa"}
``` python
```
:::
