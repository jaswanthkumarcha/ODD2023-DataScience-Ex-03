# EX-03 UNIVARIATE ANALYSIS
### Aim:
To read the given data and perform the univariate analysis with different types of plots.

### Explanation:
Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.

### Algorithm:
Step1: Read the given data.

Step2: Get the information about the data.

Step3: Remove the null values from the data.

Step4: Mention the datatypes from the data.

Step5: Count the values from the data.

Step6: Do plots like boxplots,countplot,distribution plot,histogram plot.

- Diabetes.csv
```
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
from google.colab import files
uploaded=files.upload()
df=pd.read_csv('diabetes.csv')
df.head()
df.describe()
df.isnull().sum()
df.info()
sns.boxplot(x="Glucose",data=df)
Glucose_q1 = df['Glucose'].quantile(0.25)
Glucose_q3 = df['Glucose'].quantile(0.75)
Glucose_IQR = Glucose_q3 - Glucose_q1
Glucose_low = Glucose_q1 - 1.5 * Glucose_IQR
Glucose_high = Glucose_q3 + 1.5 * Glucose_IQR
df=df[((df['Glucose']>=Glucose_low)&(df['Glucose']<=Glucose_high))]
sns.countplot(x="Glucose",data=df)
sns.distplot(df['Glucose'])
sns.histplot(x="Glucose",data=df)
```
  - Output(diabetes.csv) :
    
   ![272159225-1d3b12f6-7b20-4d55-bc5b-aa87020d5b89](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/bf6b91bc-e3af-4be4-844d-f078b1d6eb6d)
 
![272159241-fa9b48c9-50b2-4c7d-a41b-7dd97ccbeffa](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/2c9cee35-7f5e-4c3b-848b-e896659cf48e)

![272159261-df172427-658f-4dab-a2e1-4a8ff56c8639](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/ff7b2aed-b371-4696-ab42-84ced29eedd9)

![272159283-a079d5b0-5e56-4a79-8b82-b23e79c26f2d](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/a813ec6b-f2a5-46a8-b497-5fbbd8727d24)

![272159316-5ec1bd77-8ae4-46d5-ba61-15279960d57d](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/50da3be5-6fac-412b-9ec7-5f606e423174)

![272159332-40ca042e-5c75-42e0-8786-c26c54039280](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/72d5534f-e5ed-4997-9fc5-b4819d926ca0)

![272159352-c275a6cf-0d5e-4783-b4cc-5bd5999d1a07](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/4d903aab-99e4-44e7-9379-42b581bef3ce)

- SuperStore.csv:
```
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
from google.colab import files
uploaded=files.upload()
df=pd.read_csv('SuperStore.csv')
df.head()
df.describe()
df.isnull().sum()
df.info()
df['Postal Code']=df['Postal Code'].fillna(method='ffill')
sns.boxplot(x='Postal Code', data=df)
sns.countplot(x='Postal Code',data=df)
sns.distplot(df["Postal Code"])
sns.histplot(x="Postal Code",data=df)
```
  - Output(SuperStore.csv) :

![272160258-c01fd877-a11f-4f76-942e-f8b61469d0bd](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/aabcd0c8-cb45-4815-99aa-7ab8ea35167c)
    
![272160278-027f846a-c889-4446-b217-5c9e041be521](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/dd758d2e-4b3e-4478-955d-a1873af5e9cf)

![272160328-e03e85ee-9873-4f11-9182-6435206a0570](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/7f8fc139-0f1e-48be-b38e-30be9df8c624)

![272160338-d6554d40-d4ce-4ee9-8679-21e2fbf49ebf](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/26dc4f00-1bf3-4cfc-9c48-e534fddca566)

![272160341-50394024-0d2b-4141-95bb-0792351caf8d](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/7c0459e8-42d5-4e50-b8a3-ff89ee8c70dc)

![272160355-4dc2f8ef-9d9e-4408-a4f5-28f2c7091bf0](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/04e20793-257f-4c0f-8cff-d53e522db1bf)

![272160370-8c10f57f-7bea-4eb2-8b3d-cb91624fb331](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/007448fb-5213-43f6-98bc-ad9824ddc640)


   - employeesal.csv:
```
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
from google.colab import files
uploaded=files.upload()
df=pd.read_csv('employeesal.csv')
df.head()
df.describe()
df.isnull().sum()
df.info()
sns.boxplot(x='Experience_Years',data=df)
sns.countplot(x="Experience_Years",data=df)
sns.distplot(df['Experience_Years'])
sns.histplot(x="Experience_Years",data=df)
```
- Output(employeesal.csv) :

![272162113-3c6aa2b1-a2c9-4e5c-b244-c1fd7b95de74](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/719718d7-afa1-4df2-8a00-a2d1b94a391e)

![272162136-50535ce5-798d-4689-a510-8b64542272e2](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/2145ca19-9b44-4cfd-b981-e140d5de46c9)

![272162126-7d5f1c67-e2ec-403f-908b-bba9fc6a1923](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/f768dc65-dc9e-4ee9-9675-d66da6a7a72f)

![272162150-d33eeccd-9096-470d-852f-1d7d5e76b979](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/812c6a0a-45ea-4356-8344-3a7b6a924c33)

![272162162-73f32d4e-4fbc-46c7-bd18-18cc201e5998](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/15b1781c-3fe0-4a62-a2e2-c01f860a31a9)

![272162171-bbdeff51-b108-4786-9223-8f6e825262a7](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/06da741f-19c1-4e1e-9c17-94301154e2eb)

![272162189-9506c400-a405-424e-bbd8-5fc0417c3572](https://github.com/22002102/ODD2023-DataScience-Ex-03/assets/119091638/05c4e9fb-4036-4e13-bab4-5e754583e4bb)


# Result:
Thus we have read the given data and performed the univariate analysis with different types of plots.
