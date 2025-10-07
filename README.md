## 1. Executar container

docker run -it --name sarimax_container -v .:/sarimax -p 8080:8080 python:3.6 bash

## 2. Instalar dependencias e inicar jupyter
```
pip install --upgrade pip wheel
pip install statsmodels seaborn faker sklearn pyflux jupyter
jupyter notebook --ip=0.0.0.0 --port=8080  --allow-root
```
## 3. Ajustar pyflux
ARQUIVO:
/usr/local/lib/python3.6/site-packages/pyflux/tsm.py

TROCAR (na linha 435):
if isinstance(date_index, pd.tseries.index.DatetimeIndex):

POR:
if isinstance(date_index, pd.DatetimeIndex):
