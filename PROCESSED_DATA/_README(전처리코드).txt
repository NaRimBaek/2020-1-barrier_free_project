① 전처리코드 파일에 대한 세부설명
1) _README(전처리코드).txt: 전처리코드 설명 파일
2) [K-DATA] 동국대_BF(BarrierFree)_데이터전처리.ipynb: 전처리코드 실행 파일 (Jupyter Notebook)
3) DATA_LSMD_ADM_SECT_UMD_서울_동별_prc.csv : shp(서울시 동별) 데이터
   DATA_장애인콜택시 이용고객 목적지(동단위) Best100_raw.csv : <장애인콜택시 이용고객 목적지(동단위) Best100> raw 데이터
   DATA_장애인콜택시 이용고객 목적지(동단위) Best100_Seoul_dong_prc.csv : <장애인콜택시 이용고객 목적지(동단위) Best100> raw데이터를 동별로 그룹핑하여 택시 건수 구한 데이터
   DATA_장애인콜택시 이용고객 목적지(동단위) Best100_Seoul_dong_(법정동수정)_prc.csv : <DATA_장애인콜택시 이용고객 목적지(동단위) Best100_Seoul_dong_prc.csv> 데이터를 엑셀에서 법정동 기준으로 전처리한 데이터
   DATA_장애인콜택시 이용고객 목적지(동단위) Best100_prc.csv : <장애인콜택시 이용고객 목적지(동단위) Best100> 전처리 완료 데이터
   DATA_장애인 구인 현황_EMD_NM_prc.csv : <DATA_장애인 구인 현황_raw.csv> 데이터를 엑셀에서 지역구/법정동/위,경도 추가한 데이터
   DATA_장애인 구인 현황_EMD_NM_(shp)1stJOIN_(법정동수정)_prc.csv : 엑셀에서 법정동 기준으로 전처리한 데이터
   DATA_장애인 구인 현황_prc.csv : <장애인 구인 현황> 전처리 완료 데이터
   DATA_서울시 장애인 현황(장애유형별, 동별) 통계_prc.csv : <DATA_서울시 장애인 현황(장애유형별, 동별) 통계_raw.txt> 데이터를 '지체/뇌병변/심장장애/호흡기장애'만 추출하여 동 이름 추가하고 장애인 수 카운트한 데이터로, 전처리 완료 데이터
   DATA_서울시 장애인시설 현황_prc.csv : <DATA_서울시 장애인시설 현황_raw.csv> 데이터를 QGIS에서 시각화 후 법정동별 개수 카운트한 데이터로, 전처리 완료 데이터
   DATA_서울시 신한카드 장애인 복지카드 이용현황_prc.csv :  '서울시 빅데이터 캠퍼스'가 보유한 Raw Data의 법정동별 이용횟수를 QGIS에서 시각화하여 반출. 이후 시각화한 자료를 카운트한 데이터로, 전처리 완료 데이터
   DATA_대규모점포 인허가 정보_prc.csv : <DATA_대규모점포 인허가 정보_raw.csv> 데이터를 QGIS에서 시각화 후 법정동별로 카운트한 데이터로, 전처리 완료 데이터
   DATA_TOTAL DATASET.csv : 출력 데이터셋

② 각 파일의 실행 순서
1) [K-DATA] 동국대_BF(BarrierFree)_데이터전처리.ipynb 실행 
2) 'DATA_TOTAL DATASET.csv' 출력 확인
2) 'BARRIER_FREE_FINAL.ipynb' 실행 
3) 'BARRIER_FREE.xlsx' 출력 확인

③ 프로그래밍 언어 버전
본 분석은 'Jupyter Notebook (anaconda3) 6.0.3' 에서 진행되었음.

④ 사용한 라이브러리 목록 및 버전
Package                            Version
---------------------------------- -------------------
alabaster                          0.7.12
anaconda-client                    1.7.2
anaconda-navigator                 1.9.12
anaconda-project                   0.8.3
argh                               0.26.2
asn1crypto                         1.3.0
astroid                            2.4.2
astropy                            4.0.1.post1
atomicwrites                       1.4.0
attrs                              19.3.0
autopep8                           1.5.3
Babel                              2.8.0
backcall                           0.2.0
backports.functools-lru-cache      1.6.1
backports.shutil-get-terminal-size 1.0.0
backports.tempfile                 1.0
backports.weakref                  1.0.post1
bcrypt                             3.1.7
beautifulsoup4                     4.9.1
bitarray                           1.4.0
bkcharts                           0.2
bleach                             3.1.5
bokeh                              2.1.1
boto                               2.49.0
Bottleneck                         1.3.2
brotlipy                           0.7.0
certifi                            2020.6.20
cffi                               1.14.0
chardet                            3.0.4
click                              7.1.2
cloudpickle                        1.5.0Note: you may need to restart the kernel to use updated packages.
clyent                             1.2.2
colorama                           0.4.3

comtypes                           1.1.7
conda                              4.8.3
conda-build                        3.18.11
conda-package-handling             1.7.0
conda-verify                       3.4.2
contextlib2                        0.6.0.post1
cryptography                       2.9.2
cycler                             0.10.0
Cython                             0.29.21
cytoolz                            0.10.1
dask                               2.20.0
decorator                          4.4.2
defusedxml                         0.6.0
diff-match-patch                   20200713
distributed                        2.20.0
docutils                           0.16
entrypoints                        0.3
et-xmlfile                         1.0.1
fastcache                          1.1.0
filelock                           3.0.12
flake8                             3.8.3
Flask                              1.1.2
fsspec                             0.7.4
future                             0.18.2
gevent                             20.6.2
glob2                              0.7
gmpy2                              2.0.8
graphviz                           0.14.1
greenlet                           0.4.16
h5py                               2.10.0
HeapDict                           1.0.1
html5lib                           1.1
idna                               2.10
imageio                            2.9.0
imagesize                          1.2.0
importlib-metadata                 1.7.0
intervaltree                       3.0.2
ipykernel                          5.3.2
ipython                            7.16.1
ipython-genutils                   0.2.0
ipywidgets                         7.5.1
isort                              4.3.21
itsdangerous                       1.1.0
jdcal                              1.4.1
jedi                               0.17.1
Jinja2                             2.11.2
joblib                             0.16.0
json5                              0.9.5
jsonschema                         3.2.0
jupyter                            1.0.0
jupyter-client                     6.1.6
jupyter-console                    6.1.0
jupyter-core                       4.6.3
jupyterlab                         2.1.5
jupyterlab-server                  1.2.0
keyring                            21.2.1
kiwisolver                         1.2.0
lazy-object-proxy                  1.4.3
libarchive-c                       2.9
llvmlite                           0.33.0+1.g022ab0f
locket                             0.2.0
lxml                               4.5.2
MarkupSafe                         1.1.1
matplotlib                         3.2.2
mccabe                             0.6.1
menuinst                           1.4.16
mglearn                            0.1.9
mistune                            0.8.4
mkl-fft                            1.1.0
mkl-random                         1.1.1
mkl-service                        2.3.0
mock                               4.0.2
more-itertools                     8.4.0
mpmath                             1.1.0
msgpack                            1.0.0
multipledispatch                   0.6.0
navigator-updater                  0.2.1
nbconvert                          5.6.1
nbformat                           5.0.7
networkx                           2.4
nltk                               3.5
nose                               1.3.7
notebook                           6.0.3
numba                              0.50.1
numexpr                            2.7.1
numpy                              1.18.5
numpydoc                           1.1.0
olefile                            0.46
openpyxl                           3.0.4
packaging                          20.4
pandas                             1.0.5
pandocfilters                      1.4.2
paramiko                           2.7.1
parso                              0.7.0
partd                              1.1.0
path                               13.1.0
pathlib2                           2.3.5
pathtools                          0.1.2
patsy                              0.5.1
pep8                               1.7.1
pexpect                            4.8.0
pickleshare                        0.7.5
Pillow                             7.2.0
pip                                20.1.1
pkginfo                            1.5.0.1
pluggy                             0.13.1
ply                                3.11
prometheus-client                  0.8.0
prompt-toolkit                     3.0.5
psutil                             5.7.0
py                                 1.9.0
pycodestyle                        2.6.0
pycosat                            0.6.3
pycparser                          2.20
pycurl                             7.43.0.5
pydocstyle                         5.0.2
pyflakes                           2.2.0
Pygments                           2.6.1
pylint                             2.5.3
PyNaCl                             1.4.0
pyodbc                             4.0.0-unsupported
pyOpenSSL                          19.1.0
pyparsing                          2.4.7
pyreadline                         2.1
pyrsistent                         0.16.0
PySocks                            1.7.1
pytest                             5.4.3
python-dateutil                    2.8.1
python-jsonrpc-server              0.3.4
python-language-server             0.34.1
pytz                               2020.1
PyWavelets                         1.1.1
pywin32                            227
pywin32-ctypes                     0.2.0
pywinpty                           0.5.7
PyYAML                             5.3.1
pyzmq                              19.0.1
QDarkStyle                         2.8.1
QtAwesome                          0.7.2
qtconsole                          4.7.5
QtPy                               1.9.0
regex                              2020.6.8
requests                           2.24.0
rope                               0.17.0
Rtree                              0.9.4
ruamel-yaml                        0.15.87
scikit-image                       0.16.2
scikit-learn                       0.23.1
scipy                              1.5.2
seaborn                            0.10.1
Send2Trash                         1.5.0
setuptools                         49.2.0.post20200714
simplegeneric                      0.8.1
singledispatch                     3.4.0.3
sip                                4.19.13
six                                1.15.0
sklearn                            0.0
snowballstemmer                    2.0.0
sortedcollections                  1.2.1
sortedcontainers                   2.2.2
soupsieve                          2.0.1
Sphinx                             3.1.2
sphinxcontrib-applehelp            1.0.2
sphinxcontrib-devhelp              1.0.2
sphinxcontrib-htmlhelp             1.0.3
sphinxcontrib-jsmath               1.0.1
sphinxcontrib-qthelp               1.0.3
sphinxcontrib-serializinghtml      1.1.4
sphinxcontrib-websupport           1.2.3
spyder                             4.1.4
spyder-kernels                     1.9.2
SQLAlchemy                         1.3.18
statsmodels                        0.11.1
sympy                              1.6.1
tables                             3.6.1
tblib                              1.6.0
terminado                          0.8.3
testpath                           0.4.4
threadpoolctl                      2.1.0
toml                               0.10.1
toolz                              0.10.0
tornado                            6.0.4
tqdm                               4.47.0
traitlets                          4.3.3
typing-extensions                  3.7.4.2
ujson                              1.35
unicodecsv                         0.14.1
urllib3                            1.25.9
watchdog                           0.10.3
wcwidth                            0.2.5
webencodings                       0.5.1
Werkzeug                           1.0.1
wheel                              0.34.2
widgetsnbextension                 3.5.1
win-inet-pton                      1.1.0
win-unicode-console                0.5
wincertstore                       0.2
wrapt                              1.11.2
xlrd                               1.2.0
XlsxWriter                         1.2.9
xlwings                            0.19.5
xlwt                               1.3.0
xmltodict                          0.12.0
yapf                               0.30.0
zict                               2.0.0
zipp                               3.1.0
zope.event                         4.4
zope.interface                     4.7.1



### STEP1) Import Libraries

import pandas as pd
from pandas import DataFrame
import numpy as np
import requests
from bs4 import BeautifulSoup
import os
from datetime import datetime



### STEP2) shp(서울시 동별) csv 데이터
데이터 파일명 : <DATA_LSMD_ADM_SECT_UMD_서울_동별_prc>
shp(서울시 동별) 데이터는 pca/clustering 분석에 필요한 데이터 셋의 기준점이 됨 (동 명, 동 코드 등)

dong_shp = pd.read_csv('DATA_LSMD_ADM_SECT_UMD_서울_동별_prc.csv', encoding = 'cp949')
dong_shp_df = dong_shp.iloc[:, :2]
dong_shp_df.columns = ['EMD_CD', 'EMD_NM']
dong_shp_df



### STEP3) 장애인콜택시 이용고객 목적지(동단위) Best100 데이터
#### STEP3 - 1) 장애인콜택시 이용고객 목적지(동단위) Best100 - 크롤링
해당 데이터는 OpenAPI 형태로 데이터포맷은 JSON+XML 형식
2019/01/01 ~ 2019/12/31 데이터 수집 위해 크롤링 진행

#수집 기간 정의
import datetime

days_range = []

start = datetime.datetime.strptime("20190101", "%Y%m%d") #시작점 : 2019.01.01
end = datetime.datetime.strptime("20200101", "%Y%m%d") #끝점 : 2019.12.31
date_generated = [start + datetime.timedelta(days = x) for x in range(0, (end-start).days)]

for date in date_generated:
    days_range.append(date.strftime("%Y%m%d"))

#크롤러 작성
from tqdm.notebook import tqdm

temp = []

#데이터 불러오기
def get_data(url):
    response = requests.get(url).text
    df = pd.read_html(response)
    return df

#(날짜별) 포맷에 맞춰 url 크롤링
for date in tqdm(days_range):
    base_url = f'http://m.calltaxi.sisul.or.kr/api/open/newEXCEL0002.asp?key=29c3729265fa3b49c7d3e75147dc19a3&sDate={date}'
    df1 = get_data(base_url)
    
    for row in df1:
        row
    
    temp.append(row)

# 날짜별 데이터 하나의 데이터셋으로 저장
taxi_raw = pd.concat(temp, ignore_index = True)
taxi_raw

taxi_raw.to_csv('DATA_장애인콜택시 이용고객 목적지(동단위) Best100_raw.csv', encoding = 'cp949')

# 데이터 파일명 : <DATA_장애인콜택시 이용고객 목적지(동단위) Best100_raw>
# =>20190101 ~ 20191231 raw데이터 저장 완료


#### STEP3 - 2) 장애인콜택시 이용고객 목적지(동단위) Best100 전처리 (1st)
STEP3 - 1)에서 수집한 Raw Data 전처리 진행
Raw Data는 전국 데이터 포함 -> '서울특별시'만 추출하여 동별 택시 건수 탐색

# taxi 데이터 칼럼명 변경
taxi = taxi_raw.iloc[:]
taxi.columns = ['DATE', 'SI_NM', 'GU_NM', 'EMD_NM', 'TAXI_CNT']

# raw데이터에서 '서울특별시' 데이터만 출력해서 새로운 csv파일 저장
taxi_seoul = taxi[taxi['SI_NM'] == '서울특별시']
taxi_seoul.set_index("DATE", inplace = True)
taxi_seoul.to_csv('DATA_장애인콜택시 이용고객 목적지(동단위) Best100_Seoul_prc.csv', encoding = 'cp949')

# 동별 택시 건수 더해서 새로운 csv 파일 저장
taxi_seoul_df = pd.read_csv('DATA_장애인콜택시 이용고객 목적지(동단위) Best100_Seoul_prc.csv', encoding = 'cp949')
taxi_seoul_df2 = taxi_seoul_df.iloc[:, 3:]
taxi_dong = taxi_seoul_df2.groupby('EMD_NM').sum()
taxi_dong
taxi_dong.to_csv('DATA_장애인콜택시 이용고객 목적지(동단위) Best100_Seoul_dong_prc.csv', encoding = 'cp949')


#### STEP3 - 3) 동별 택시 건수 데이터는 행정동+법정동 구성 -> 법정동 기준으로 변경
데이터 파일명 : <DATA_장애인콜택시 이용고객 목적지(동단위) Best100_Seoul_dong_(법정동수정)_prc>
* [법정동 변경 기준]
sol1) 행정동을 법정동으로 변경
sol2) 하나의 행정동이 여러 개의 법정동으로 나눠질 경우 '주민센터' 기준 법정동으로 변경


#### STEP3 - 4) 장애인콜택시 이용고객 목적지(동단위) Best100 전처리 (2nd)

# 행정동 -> 법정동 변경 완료된 데이터 다시 전처리 진행
taxi_prc = pd.read_csv('DATA_장애인콜택시 이용고객 목적지(동단위) Best100_Seoul_dong_(법정동수정)_prc.csv', encoding = 'cp949')
taxi_prc_df = taxi_prc.iloc[:, :2]

taxi_prc_df2 = taxi_prc_df.groupby('EMD_NM').sum()
taxi_prc_df2

# shp(서울시 동별) 데이터 + 장애인콜택시 목적지 Best100 데이터 JOIN
법정동 기준으로 데이터 구성된 shp(서울시 동별) 데이터와 전처리 완료된 장애인콜택시 목적지 Best100 데이터 조인하여 최종 전처리 완료 데이터 csv파일 저장 (EMD_CD, EMD_NM, TAXI_CNT로 구성)
taxi_df = pd.merge(left = dong_shp_df, right = taxi_prc_df2, how = 'left', on = 'EMD_NM')
taxi_df = taxi_df.fillna(0)
taxi_df.set_index('EMD_CD', inplace = True)
taxi_df
taxi_df.to_csv('DATA_장애인콜택시 이용고객 목적지(동단위) Best100_prc.csv', encoding = 'cp949')

# 데이터 파일명 : <DATA_장애인콜택시 이용고객 목적지(동단위) Best100_prc> => '장애인콜택시 목적지 Best100' 최종 전처리 완료 데이터



### STEP4) 장애인 구인 현황
#### STEP4 - 1) 장애인 구인 현황 전처리 (1st)
데이터 파일명 : <DATA_장애인 구인 현황_EMD_NM_prc>
-> 위의 데이터는 <DATA_장애인 구인 현황_raw.csv> 데이터에 동 이름과 위/경도 추가한 데이터

# 장애인 동별 구인현황 데이터 불러오기
job = pd.read_csv("DATA_장애인 구인 현황_EMD_NM_prc.csv", encoding = 'cp949')

# raw 데이터에서 동별 구인현황 추출
job_dong = job.groupby('EMD_NM')
job_dong_sum = job_dong['구인인원'].sum()
job_dong_df = pd.DataFrame(job_dong_sum)

# shp(서울시 동별) 데이터와 조인 후 저장
job_join = pd.merge(left = dong_shp_df, right = job_dong_df, how = 'right', on = 'EMD_NM')
job_join.to_csv("DATA_장애인 구인 현황_EMD_NM_(shp)1stJOIN_prc.csv", encoding = 'cp949')


#### STEP4 - 2) 장애인 구인 현황 데이터는 행정동+법정동 구성 -> 법정동 기준으로 변경
데이터 파일명 : <DATA_장애인 구인 현황_EMD_NM_(shp)1stJOIN_(법정동수정)_prc>
* [법정동 변경 기준]
sol1) 행정동을 법정동으로 변경
sol2) 하나의 행정동이 여러 개의 법정동으로 나눠질 경우 '주민센터' 기준 법정동으로 변경


#### STEP4 - 3) 장애인 구인 현황 전처리 (2nd)

# 행정동 -> 법정동 변경 완료된 데이터 다시 전처리 진행
job_prc = pd.read_csv('DATA_장애인 구인 현황_EMD_NM_(shp)1stJOIN_(법정동수정)_prc.csv', encoding = 'cp949')
job_prc_df = job_prc.iloc[:, 1:3]

job_prc_df2 = job_prc_df.groupby('EMD_NM').sum()
job_prc_df2

# shp(서울시 동별) 데이터 + 장애인 구인 현황 데이터 JOIN

# #shp(동별) 데이터 기준 장애인 구인 현황 데이터 조인 및 저장
job_df = pd.merge(left = dong_shp_df, right = job_prc_df2, how = 'left', on = 'EMD_NM')
job_df = job_df.fillna(0)
job_df.set_index('EMD_CD', inplace = True)
job_df.to_csv("DATA_장애인 구인 현황_prc.csv", encoding = 'cp949')

# 데이터 파일명 : <DATA_장애인 구인 현황_prc> => '장애인 구인 현황' 최종 전처리 완료 데이터



### STEP5) 서울시 장애인 현황(장애유형별, 동별) 통계
데이터 파일명 : <DATA_서울시 장애인 현황(장애유형별, 동별) 통계_prc>
위의 데이터는 <DATA_서울시 장애인 현황(장애유형별,동별) 통계_raw.txt> 데이터를 '지체/뇌병변/심장장애/호흡기장애'만 추출하여 동 이름 추가하고 장애인 수 카운트한 데이터

disabled_df = pd.read_csv('DATA_서울시 장애인 현황(장애유형별, 동별) 통계_prc.csv', encoding = 'cp949')
disabled_df



### STEP6) 서울시 장애인시설 현황
데이터 파일명 : <DATA_서울시 장애인시설 현황_prc>
위의 데이터는 <DATA_서울시 장애인시설 현황_raw.csv> 데이터를 QGIS에서 시각화 후 법정동별 개수 카운트한 데이터

welfare_df = pd.read_csv('DATA_서울시 장애인시설 현황_prc.csv', encoding = 'cp949')
welfare_df



### STEP7) 서울시 신한카드 장애인 복지카드 이용현황
데이터 파일명 : <DATA_서울시 신한카드 장애인 복지카드 이용현황_prc>
위의 데이터는 '서울시 빅데이터 캠퍼스'가 보유한 Raw Data의 법정동별 이용횟수를 QGIS에서 시각화하여 반출. 이후 시각화한 자료를 카운트한 데이터

card_df = pd.read_csv('DATA_서울시 신한카드 장애인 복지카드 이용현황_prc.csv', encoding = 'cp949')
card_df



### STEP8) 대규모점포 인허가 정보
데이터 파일명 : <DATA_대규모점포 인허가 정보_prc>
위의 데이터는 <DATA_대규모점포 인허가 정보_raw.csv> 데이터를 QGIS에서 시각화 후 법정동별로 카운트한 데이터

shop_df =  pd.read_csv('DATA_대규모점포 인허가 정보_prc.csv', encoding = 'cp949')
shop_df



### STEP9) 활용데이터 전체 JOIN
pca/clustering 분석을 위한 하나의 데이터 셋으로 csv파일 저장

join1 = pd.merge(left = dong_shp_df, right = disabled_df.iloc[:, 1:], how = 'left', on = 'EMD_CD')
join2 = pd.merge(left = join1, right = shop_df.iloc[:, 1:], how = 'left', on = 'EMD_CD')
join3 = pd.merge(left = join2, right = taxi_df.iloc[:, 1:], how = 'left', on = "EMD_CD")
join4 = pd.merge(left = join3, right = job_df.iloc[:, 1:], how = 'left', on = 'EMD_CD')
join5 = pd.merge(left = join4, right = welfare_df.iloc[:, 1:], how = 'left', on = 'EMD_CD')
join6 = pd.merge(left = join5, right = card_df.iloc[:, 1:], how = 'left', on = 'EMD_CD')

# 결측치 처리 및 저장
total = join6.fillna(0)
total.set_index('EMD_CD', inplace = True)
total
total.to_csv('DATA_TOTAL DATASET.csv', encoding = 'cp949')