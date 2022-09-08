# AI and Python

## [Libraries](https://towardsdatascience.com/5-less-known-python-libraries-that-can-help-in-your-next-data-science-project-5970a81b32de)
 

- *[Mito](https://docs.trymito.io)* - Like Excel 
```shell
python -m pip install mitoinstaller
python -m mitoinstaller install
```

- *SweetViz* - Plot per column etc

`pip install sweetviz`

```python
import sweetviz as sv
import pandas as pd
# read dataset
df = pd.read_csv('StudentsPerformance.csv')
# generate report
my_report = sv.analyze(df)
my_report.show_html()
```

- Faker - Fake Data

`pip install faker`

```python
from faker import Faker
fake = Faker()
>>> fake.name()
Corey Edwards
>>> fake.job()
Nurse, mental health
>>> fake.company()
Patel-Porter
>>> fake.ssn()
656-80-3536
>>> fake.email()
stacey69@example.org
>>> fake.address()
057 Bailey Club Suite 230 Jamieshire, WA 93828
```

- OpenDataSets - Downloading kaggle

`pip install opendatasets`

- Emoji

`pip install emoji`

```python
import emoji
>>> emoji.demojize("Happy birthday! ️️❤️🎁")
Happy birthday! :red_heart::wrapped_gift:
```


## Paddle Paddle

- [Github](https://github.com/PaddlePaddle)
