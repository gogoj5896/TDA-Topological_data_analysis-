# TDA-Topological_data_analysis-exercise

<br />
<br />

# * Topological Data Analysis
- 3_teamproject(nba clustering) 중 TDA를 알게 되어서 관련 논문 등을 찾아보고 연습
- 관련블로그 : http://skyeong.net/154
- 관련 논문 : 

http://www.ayasdi.com/wpcontent/uploads/2015/02/Topological_Methods_for_the_Analysis_of_High_Dimensional_Data_Sets_and_3D_Object_Recognition.pdf  

http://www.nature.com/articles/srep01236

- TDA 간단한 개념(관련블로그에서 참조한 내용)

: 비지도 기계학습 (unsupervised machine learning)에 해당되고, 보다 구체적으로는 "Partial Clustering"에 속함

: 필터함수 구성 -> 거리함수 구성 -> 클러스터링 -> 시각화


아직은 개념을 명확하게 습득하지 못했지만, data 분석에 도입해보면서 부족한 공부를 메꿔가려고 함
(위상수학을 듣긴 했었지만 기억이 안나서 안타까운..)

<br />
<br />

# * library 적용 순서
- (https://github.com/MLWave/kepler-mapper)
## 1. Initialize
mapper = km.KeplerMapper(verbose=1)

## 2. Fitting and transforming
projected_data = mapper.fit_transform(data, projection="sum", scaler=km.preprocessing.MinMaxScaler(), distance_matrix = "cosine" )

## 3. Mapping
topological_network = mapper.map(projected_X, inverse_X=None, 
                                 clusterer=cluster.DBSCAN(eps=0.5,min_samples=3), 
                                 nr_cubes=10, overlap_perc=0.1)
                                 
## 4 .Visualizing
mapper.visualize(topological_network, path_html="mapper_visualization_output.html")

<br />
<br />

# Example(nba_clustering)
![image](https://github.com/gogoj5896/TDA-Topological_data_analysis-/blob/master/image%26html/aa.png)
