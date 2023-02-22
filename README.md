# barrier_free_project

 <장애인 이동권 증진을 위한 전동보장구 충전소 입지 선정>



**규칙: 파일명은 ppt에 있는대로 통일하되, 원본데이터는 뒤에 _raw, 전처리된 데이터는 뒤에 _prc를 붙임. (단, 충전소 데이터의 경우 ppt에 있는대로 통일하지 않았음)**

**프로그래밍 언어 버전: Python 3.8/Jupyter Notebook(anaconda3) 6.0.3/QGIS 3.10.8
		     세부 라이브러리 버전은 각 폴더 README.txt에 기재되어 있음.
ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ


# 0. RAW DATA

1) 서울시 동별 / 구별 shp 파일 (국가공간정보포털(오픈마켓))
2) 서울시 장애인 현황 (서울 열린데이터 광장)
3) 장애인 구인 현황 (한국장애인고용공단)
4) 전동휠체어급속충전기 표준 데이터 (공공데이터포털)
5) 전동휠체어 급속충전기 (스마트서울맵)
6) 전동휠체어 급속충전기 운영현황 (서울교통공사)
7) 대규모 점포 인허가 정보 (서울 열린데이터 광장)
8) 서울시 장애인 시설 현황 (서울 열린데이터 광장)
9) 장애인콜택시 이용고객 목적지용(동단위) Best 100 (서울시설공단)
10) 서울시 신한카드 장애인 복지카드 이용현황 (서울시 빅데이터 캠퍼스)



# 1. PROCESSED DATA 전처리과정

* 코드 관련 설명 파일 : _README(전처리코드).txt 참조
* 본 분석은 Jupyter Notebook(anaconda3)에서 진행되었음
* 주소에서 위경도로 변환 시, 구글 스프레드시트 내의 부가기능인 GEOCODE 변환프로그램을 사용함
* QGIS에서 법정동별 좌표의 개수 카운트 시, [벡터 > 분석도구 > 폴리곤 내부에 있는 포인트 개수 구하기] 기능을 사용함

1) shp(서울시 동별/구별) 데이터 
   : 신사, 신정동 (QGIS, 엑셀 처리)

2) 서울시 장애인 현황
   : raw데이터 -> '지체/뇌병변/심장장애/호흡기장애'만 추출 -> “DATA_서울시 장애인 현황(장애유형별, 동별) 통계_prc”로 파일명 설정 -> 법정동 코드(EMD_CD)추가 

3) 장애인 구인 현황
   : raw데이터 -> 시군구+동+위경도 변환 -> 법정동별 인원 카운트 -> shp(서울시 동별)      데이터 기준으로 장애인 구인 현황 데이터 법정동으로 변경 (엑셀 처리)

4) 전동휠체어급속충전기 표준 데이터
   : raw데이터 -> 시설명, 시도명, 시군구명, 위경도 좌표만 남기고 필요없는 데이터 제거 ->  법정동코드(EMD_CD) 열 추가해서 다른 데이터와 조인 가능하게 처리 -> ”DATA_서울시 충전소_공공데이터포털_raw”로 파일명 설정 ->  이후 4,5번 데이터와 합쳐서 하나의 “DATA_서울시 충전소 ALL_prc” 파일로 합쳐 전처리 함

5-6) 전동휠체어 급속충전기 (스마트서울맵) + 전동휠체어 급속충전기 운영현황 (서울교통공사): 3에서 누락되어 있는 지하철 역내 충전소 위치를 수집

7) 대규모 점포 인허가 정보
   : raw데이터-> 필요없는 열 삭제 -> 주소가 누락된 data는 상호명으로 추가 -> 위경도 좌표 변환 -> QGIS에서 시각화 -> 법정동 별 개수 카운트

8) 서울시 장애인 시설 현황
   : raw데이터의 주소 -> 위경도 변환 -> QGIS 시각화 -> 법정동별 개수 카운트

9) 장애인콜택시 이용고객 목적지(동단위) Best 100
   : openAPI 크롤링 -> ‘서울특별시’만 추출 -> 동별 택시 건수 sum  -> shp(서울시 동별) 데이터 기준으로 장애인콜택시 이용고객 목적지(동단위) Best100 법정동으로 변경 (엑셀 처리) -> 동별 택시 건수 sum ( = 법정동 처리하면서 중복 법정동 있는 것 처리)

10) 서울시 신한카드 장애인 복지카드 이용현황
   : 서울시빅데이터캠퍼스가 보유한 RAW DATA의 이용횟수를 법정동별로 합계 구해서 시각화 -> 시각화해서 반출한 자료를 다시 카운트해서 csv로 작성




## 1_1. 데이터 파일명 설명

1) shp(서울시 동별)

   (1) Raw Data
   	: DATA_LSMD_ADM_SECT_UMD_서울_동별_raw
	
   (2) 동일 이름 동 수정 (QGIS + 엑셀에서 처리)
       	: DATA_LSMD_ADM_SECT_UMD_서울_동별_prc

2) 서울시 장애인 현황(장애유형별,동별) 통계

   (1) Raw Data
       	: DATA_서울시 장애인 현황(장애유형별,동별) 통계_raw (확장자 txt)
	
   (2) 최종 전처리 완료 Data
       	: DATA_서울시 장애인 현황(장애유형별, 동별) 통계_prc

3) 장애인 구인 현황

   (1) Raw Data
       	: DATA_장애인 구인 현황_raw
	
   (2) Raw Data에서 지역구 / 법정동 / 위도+경도 추가 (엑셀에서 처리)
       	: DATA_장애인 구인 현황_EMD_NM_prc
	
   (3) shp(서울시 동별) 데이터 + 장애인 구인 현황
       	: DATA_장애인 구인 현황_EMD_NM_(shp)1stJOIN_prc
          	=> 동 수정 필요한 데이터 탐색 위한 파일
		
   (4) 법정동 기준으로 동 변경 (엑셀 처리)
        	: DATA_장애인 구인 현황_EMD_NM_(shp)1stJOIN_(법정동수정)_prc
		
   (5) 최종 전처리 완료 Data
        	: DATA_장애인 구인 현황_prc

4) 서울시 충전소 ALL

   (1) Raw Data
       	: DATA_서울시 충전소_공공데이터포털_raw
         	+ DATA_서울시 충전소_서울교통공사+스마트서울맵
		
   (2) 최종 전처리 완료 데이터셋
       	: DATA_서울시 충전소 ALL_prc

5) 대규모점포 인허가 정보

   (1) Raw Data
       	: DATA_대규모점포 인허가 정보_raw
	
   (2) 최종 전처리 완료 Data
       	: DATA_대규모점포 인허가 정보_prc

6) 서울시 장애인시설 현황

   (1) Raw Data
       	: DATA_서울시 장애인시설 현황_raw
	
   (2) 최종 전처리 완료 Data
       	: DATA_서울시 장애인시설 현황_prc

7) 장애인콜택시 이용고객 목적지(동단위) Best100

   (1) Raw Data
       	: DATA_장애인콜택시 이용고객 목적지(동단위) Best100_raw
	
   (2) Raw Data에서 ‘서울특별시’ 데이터만 추출한 Data
       	: DATA_장애인콜택시 이용고객 목적지(동단위) Best100_Seoul_prc
	
   (3) 2번 데이터에서 동별 택시 건수 sum
       	: DATA_장애인콜택시 이용고객 목적지(동단위) Best100_Seoul_dong_prc
	
   (4) 법정동 기준으로 동 변경 (엑셀 처리)
       	: DATA_장애인콜택시 이용고객 목적지(동단위) Best100_Seoul_dong_(법정동수정)_prc
	
   (5) 최종 전처리 완료 Data
       	: DATA_장애인콜택시 이용고객 목적지(동단위) Best100_prc
	
  
8) 서울시 신한카드 장애인 복지카드 이용현황

   (1) Raw Data
       	: QGIS 좌표 이미지 반출 (0. RAW DATA > 서울시 신한카드 장애인 복지카드 이용현황_raw 내에 위치)
	
   (2) 최종 전처리 완료 Data
       	: DATA_서울시 신한카드 장애인 복지카드 이용현황_prc
	

9) 최종 전처리 완료 데이터셋

   (1) 최종 전처리 완료 데이터셋
       	: DATA_TOTAL DATASET (1. PROCESSED DATA > JOIN DATA 내에 위치)
	
   (2) QGIS 시각화를 위해 1을 전처리한 데이터셋
       	: DATA_K-Means_Clustering (3. QGIS > QGIS_DATA 내에 위치)





# 2. CLUSTERING

1) 클러스터링 분석 실행 파일
    : 본 분석은 Jupyter Notebook(anaconda3)에서 진행되었으며, 실행 환경(Jupyter Notebook, Python)에 맞춰 선택할 수 있도록, 'ipynb', 'py' 2가지의 형태로 제공하고 있음. 

2) 코드 관련 설명 파일
    : _README(K-Means).txt 참조

3) 입출력 데이터셋 
    : 입력은 DATASET.csv 파일이며, 출력된 결과는 BARRIER_FREE.xlsx 파일임.






# 3. QGIS (버전 3.10.8)

1) 구성
   : 경로를 C드라이브에 두고 [동국대_BF_QGIS_FINAL.zip]을 풀면, QGIS_DATA 폴더와 QGIS_PROJECT 폴더로 구성되어 있음


2) QGIS_DATA 폴더
   (1) shp 파일
       	: DATA_shp(서울시 구별),
         	 DATA_shp(서울시 동별),
         	 DATA_shp(서울시 동별)_충전소입지선정
		 
   (2) 전처리 완료된 파일
       	: DATA_서울시 충전소 ALL_prc
	
   (3) K-means clustering 결과파일
       	: DATA_K-Means_Clustering
	
   (4) 입지분석결과 파일
       	: DATA_최종 충전소 입지 선정_전체, 
        	 DATA_최종 충전소 입지 선정_목동,
        	 DATA_최종 충전소 입지 선정_장안동

3) QGIS_PROJECT 폴더
   : [K-DATA]동국대_BF_QGIS.qgz 파일 실행


4) 레이어: 체크박스를 누르면 레이어 활성/비활성 가능

   (1) grid_500 
       	: 500m*500m 셀 분석시 사용
	
   (2) grid_100 
       	: 100m*100m 셀 분석시 사용
	
   (3) DATA_최종 충전소 입지 선정_전체 
       	: 목동, 장안동의 입지 좌표를 보여줌
	
   (4) DATA_최종 충전소 입지 선정_장안동_layer 
       	: 장안동의 충전소 입지 및 반경을 보여줌
	
   (5) DATA_최종 충전소 입지 선정_목동_layer 
       	: 목동의 충전소 입지 및 반경을 보여줌
	
   (6) DATA_서울시 충전소 ALL_prc 
       	: 서울시에 있는 모든 충전소의 좌표를 보여줌
	
   (7) K-Means_서울시 충전소 ALL_layer 
       	: 서울시에 있는 모든 충전소의 반경을 보여줌
	
   (8) DATA_K-Means_Clustering 
       	: K-means clustering 결과를 나타내는 데이터로, (9)의 shp 파일과 조인되어 group을 나타낼 때 사용됨
	
   (9) K-Means_shp_layer
       	: 서울시 동별 전체 shp파일로, K-means clustering 결과와 조인되어 형성된 group을 보여줌
	
   (10) LSMD_ADM_SECT_UMD_서울_동별_충전소입지선정 
       	: 입지선정 과정에서 500m*500m 셀 분석을 통해 탐색된 목동, 자양동, 장안동의 동 명을 보여줌
	
   (11) LSMD_ADM_SECT_UMD_서울_동별
       	: 서울시 동별 전체 shp파일로, 경계선을 뚜렷하게 보이게 하기 위해 추가됨
	
   (12) LARD_ADM_SECT_SGG_11
       	: 서울시 구별 전체 shp파일로, 구 명을 나타냄
	
   (13) NAVER Maps v5
       	: QGIS 플러그인 중 하나인 [TMS for Korea]를 설치해야 사용 가능. [5. 기타] 폴더에 프로그램 넣어두었음. 
         	Naver Street Label: 네이버 지도의 지역명을 보여줌
         	Naver Street: 네이버 지도의 길을 보여줌




# 4. opnion

## 내 역할

- 차원 축소, clustering 등 소외지역을 도출하기 위한 모형 설계를 중점적으로 담당하였다.
Kmeans, DBSCAN 등 다양한 clustering을 구현 후 실루엣 계수, 3d plot을 통해 군집이 잘 나누어졌는지, 군집 분석 결과 해석이 가능한지를 기준으로 최종 모델을 Kmeans로 결정하였다.

- 여러 사전 연구들을 기반으로, 세부입지 선정을 위한 점수 산출 기준을 선정하여 최종적으로 입지를 선정하였다.  


## 배운점

- 주제선정부터 분석, 문제 해결까지 한 첫 번째 데이터분석 팀 프로젝트로, 데이터 분석에 있어서 팀원들과 의사소통하고 협력하는 방법을 배울 수 있었다. 
- 프로젝트 진행에서 데이터 권한 등의 문제로 초반에 설정한 계획에서 바꿔야 할 때가 존재하며, 이를 해결하기 위해 팀원과 많은 협력을 거쳐야 함을 배울 수 있었다. 
- QGIS를 이용하여 coverage map을 그리는 방법에 대해 배울 수 있었다. 


## 어려웠던 점과 해결방법

분석 초반 계획은 충전소 입지 선정을 위해, 각 지역의 충전소 이용량을 예측하는 것이였지만, 중간에 데이터 이용 권한의 문제로 충전소 이용량(target) 데이터를 구할 수가 없었다. 
이를 해결하기 위해 충전소 이용과 관련된 다양한 설명변수들을 기반으로 서울 지역의 군집 분석 진행한 후 각 군집마다 차등을 두어 coverage map을 그리는 방향으로 수정하게 되었다. 




