# Paper Review on the nowadays studies about Covid-19

## P1. Mobility network models of COVID-19 explain inequities and inform reopening

- Authors: Serina Chang, Emma Pierson, Pang Wei Koh, Jaline Gerardin, Beth Redbird, David Grusky & Jure Leskovec
  -  컴공 베이스 + 예방의학, Policy Research? + 사회학

- [10 November 2020, Nature](https://www.nature.com/articles/s41586-020-2923-3?fbclid=IwAR0iyWJwtGTAf19Uj4ikHG1VZPG221gFkt16zbH4-CbxjJOksp5MLS94EdU#article-info)
- [Project pages](https://covid-mobility.stanford.edu//)
  - 프로젝트 페이지에 정리를 아주 잘 해놓았음
  - FAQ를 참고하면 거의 논문에 대한 요약을 살펴볼 수 있음
  - 사실 초록도 매우 잘 써놔서, 초록만으로 거의 모든 내용을 살펴 볼 수 있음
  - [리뷰어와의 리뷰내용 공개](https://static-content.springer.com/esm/art%3A10.1038%2Fs41586-020-2923-3/MediaObjects/41586_2020_2923_MOESM3_ESM.pdf)
  - [높은 퀄리티의 영상 초록](https://www.youtube.com/watch?v=FZG85TN1nhE)

###  Highlight

- 인구조사 기반 최하위 단위(CBGs)의 Compartment모델 사용
- 모바일 데이터 기반 모빌리티 네트워크 구축(Bipartite; CBGs-POIs) 
- 54억개의 시간당 연결선 고려
- 상대적으로 단순한 SEIR 모델이 인구행동의 상당한 변화에도 불구하고 비교적 정확한 예측 정확도를 보여줌
- POI에서 소수의 `Super Spreader`가 감염의 대부분을 일으키는 것으로 (시뮬레이션에의해) 확인되었고, POI에서 최대 이용률 제한(restricting the maximum occupancy)이 일괄적 이동량 감소(uniformly reducing mobility)보다 더 효과적이라는 것을 확인
- (인종, 사회 경제적) 취약 계층에서 감염률이 더 높은 것을 정확히 예측; **다른 이유가 아닌 순전한 이동량의 차이**
- 취약계층에서는 다른 계층과 다르게, 사람이 붐비는 POI에 대한 이용률이 감소하지 않은 것을 확인

### Mobility network model

- Bipartite Network를 사용
  - POIs(points interest)와 CBGs(census block groups) 기반
    - 인구수 기반 10개 상위 대도시 지역 데이터 사용
    - POIs: 헤르토랑과 같은 비 거주기반 장소 (~552,758)
    - CBGs: 대량 600-3,000명의 사람을 포함한 인구조사 블록그룹 (~56,945)
  - Hours movements from SafeGraph
    - 모바일 어플리케이션을 통해 위치데이터를 집계하는 회사
    - 2020-3-1 ~ 2020-5-2까지의 이동 패턴 연구
    - Google 이동데이터와 비교

| ![](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fs41586-020-2923-3/MediaObjects/41586_2020_2923_Fig1_HTML.png?as=webp) |
| :----------------------------------------------------------: |
| **a**, The mobility network captures hourly visits from each CBG to each POI. The vertical lines indicate that most visits are between nearby POIs and CBGs. Visits dropped markedly from March to April, as indicated by the lower density of grey lines. Mobility networks in the Chicago metro area are shown for 13:00 on two Mondays, 2 March 2020 (top) and 6 April 2020 (bottom). **b**, We overlaid a disease-spread model on the mobility network, with each CBG having its own set of SEIR compartments. New infections occur at both POIs and CBGs, with the mobility network governing how subpopulations from different CBGs interact as they visit POIs. **c**, Left, to test the out-of-sample prediction, we calibrated the model on data before 15 April 2020 (vertical black line). Even though its parameters remain fixed over time, the model accurately predicts the case trajectory in the Chicago metro area after 15 April using the mobility data (r.m.s.e. on daily cases = 406 for dates ranging from 15 April to 9 May). Right, model fit was further improved when we calibrated the model on the full range of data (r.m.s.e. on daily cases = 387 for the dates ranging from 15 April to 9 May). **d**, We fitted separate models to 10 of the largest US metro areas, modelling a total population of 98 million people; here, we show full model fits, as in **c** (right). In **c** and **d**, the blue line represents the model predictions and the grey crosses represent the number of daily reported cases; as the numbers of reported cases tend to have great variability, we also show the smoothed weekly average (orange line). Shaded regions denote the 2.5th and 97.5th percentiles across parameter sets and stochastic realizations. Across metro areas, we sample 97 parameter sets, with 30 stochastic realizations each (*n* = 2,910); see Supplementary Table [6](https://www.nature.com/articles/s41586-020-2923-3#MOESM1) for the number of sets per metro area. |



### Mobility reduction and reopening plans

#### The magnitude of mobility reduction is at least as important as its timing

- 미국의 경우, 3월에 이동량이 급격히 감소했음 이 기간을 중심으로 이동량 감소에 대한 코로나 영향력을 테스트
- 단순한 scaling을 통해 이동량의 크기를 감소 이전과 동일하게 유지했을 때의 가상의 시나리오로 시뮬레이션 수행
- 이동성 감소는 감염을 현저하게 줄일 수 있음
- Fig 2 (a)를 보면 timing에 대한 시뮬레이션은 그저 shift의 효과로밖에 안보임..

| ![](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fs41586-020-2923-3/MediaObjects/41586_2020_2923_Fig2_HTML.png?as=webp) |
| :----------------------------------------------------------: |
| The Chicago metro area is used as an example; results for all metro areas are included in Extended Data Figs. [3](https://www.nature.com/articles/s41586-020-2923-3#Fig6), [4](https://www.nature.com/articles/s41586-020-2923-3#Fig7), Supplementary Figs. [10](https://www.nature.com/articles/s41586-020-2923-3#MOESM1), [15](https://www.nature.com/articles/s41586-020-2923-3#MOESM1)–[24](https://www.nature.com/articles/s41586-020-2923-3#MOESM1) and Supplementary Tables [4](https://www.nature.com/articles/s41586-020-2923-3#MOESM1), [5](https://www.nature.com/articles/s41586-020-2923-3#MOESM1), as indicated. **a**, Counterfactual simulations (left) of past reductions in mobility illustrate that the magnitude of the reduction (middle) was at least as important as its timing (right) (Supplementary Tables [4](https://www.nature.com/articles/s41586-020-2923-3#MOESM1), [5](https://www.nature.com/articles/s41586-020-2923-3#MOESM1)). **b**, The model predicts that most infections at POIs occur at a small fraction of superspreader POIs (Supplementary Fig. [10](https://www.nature.com/articles/s41586-020-2923-3#MOESM1)). **c**, Left, the cumulative number of predicted infections after one month of reopening is plotted against the fraction of visits lost by partial instead of full reopening (Extended Data Fig. [3](https://www.nature.com/articles/s41586-020-2923-3#Fig6)); the annotations within the plot show the fraction of maximum occupancy that is used as the cap and the horizontal red line indicates the cumulative number of predicted infections at the point of reopening (on 1 May 2020). Compared to full reopening, capping at 20% of the maximum occupancy in Chicago reduces the number of new infections by more than 80%, while only losing 42% of overall visits. Right, compared to uniformly reducing visits, the reduced maximum occupancy strategy always results in a smaller predicted increase in infections for the same number of visits (Extended Data Fig. [4](https://www.nature.com/articles/s41586-020-2923-3#Fig7)). The horizontal grey line at 0% indicates when the two strategies result in an equal number of infections, and we observe that the curve falls well below this baseline. The *y* axis plots the relative difference between the predicted number of new infections under the reduced occupancy strategy compared to a uniform reduction. **d**, Reopening full-service restaurants has the largest predicted impact on infections, due to the large number of restaurants as well as their high visit densities and long dwell times (Supplementary Figs. [15](https://www.nature.com/articles/s41586-020-2923-3#MOESM1)–[24](https://www.nature.com/articles/s41586-020-2923-3#MOESM1)). Colours are used to distinguish the different POI categories, but do not have any additional meaning. All results in this figure are aggregated across 4 parameter sets and 30 stochastic realizations (*n* = 120). Shaded regions in **a**–**c** denote the 2.5th to 97.5th percentiles; boxes in **d** denote the interquartile range and data points outside this range are shown as individual dots. |

#### A minority of POIs account for the majority of the predicted infections

- 10%의 POI에서 POI전체 감염의 85%가 일어남
- 음식점같은 POI에 비해 식료품점 같은 곳은 이동량 감소 후에도 어쩔 수 없이 꾸준한 감염이 일어남(이동량이 감소하지 않음)

#### Reopening with a reduced maximum occupancy

- 5월1일 이후에 대해 reopening 시나리오를 테스트함

- 시간당 방문회수를 이전 수치로 되돌리며(최대 인원수를 초과하는 경우에는 제한함), 최대 수용인원을 줄이는 효과를 모델링해봄

- 오타? 그래프상으론 40%

> Full reopening without reducing the maximum occupancy produced a spike in the predicted number of infections: in the Chicago metro area, our models projected that an additional 32% (95% confidence interval, 25–35%) of the population would be infected by the end of May (Fig. [2c](https://www.nature.com/articles/s41586-020-2923-3#Fig2)).

- 이는 최대 점유 수를 줄이면 각 POI 내에서 시간에 따라 달라지는 방문 밀도를 이용하여 위험도가 가장 높은 고밀도 기간 동안 POI에 대한 방문을 불균형 적으로 줄이지만 위험이 낮은 기간에는 방문 수가 변경되지 않기 때문

#### Relative risk of reopening different categories of POIs

- 제목 그대로 특정 카테고리에서 그 위험이 더 높은 것으로 보여짐(풀 서비스 레스토랑, 체육관, 호텔, 카페, 종교 단체 및 제한된 서비스 레스토랑)

### Demographic disparities in infections

- 각 CBG마다 인종 구성 및 소득 중간값에 대한 예측 감염율을 살펴봄: 상/하위 십분위에 대해 비교

#### Predicting disparities from mobility data

- 이동 데이터만 사용하고도 취약 계층의 감염위험이 더 높은 것을 정확히 예측함
- 이러한 감염 위험율은 앞서도 언급됬던 주요 POI에 의해 주도됨(상위계층보다 하위계층에서 더욱 도드러짐)
- Supplementary에서 인종에 차이에서도 확인됨


| ![](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fs41586-020-2923-3/MediaObjects/41586_2020_2923_Fig3_HTML.png?as=webp) |
| :----------------------------------------------------------: |
| **a**, In every metro area, our model predicts that people in lower-income CBGs are likelier to be infected. **b**, People in non-white CBGs area are also likelier to be infected, although results are more variable across metro areas. For **c**–**f**, the Chicago metro area is used as an example, but references to results for all metro areas are provided for each panel. **c**, The overall predicted disparity is driven by a few POI categories such as full-service restaurants (Supplementary Fig. [2](https://www.nature.com/articles/s41586-020-2923-3#MOESM1)). **d**, One reason for the predicted disparities is that higher-income CBGs were able to reduce their mobility levels below those of lower-income CBGs (Extended Data Fig. [6](https://www.nature.com/articles/s41586-020-2923-3#Fig9)). **e**, Within each POI category, people from lower-income CBGs tend to visit POIs that have higher predicted transmission rates (Extended Data Table [3](https://www.nature.com/articles/s41586-020-2923-3#Tab3)). The size of each dot represents the average number of visits per capita made to the category. The top 10 out of 20 categories with the most visits are labelled, covering 0.48–2.88 visits per capita (hardware stores–full-service restaurants). **f**, Reopening (at different levels of reduced maximum occupancy) leads to more predicted infections in lower-income CBGs than in the overall population (Extended Data Fig. [3](https://www.nature.com/articles/s41586-020-2923-3#Fig6)). In **c**–**f**, purple denotes lower-income CBGs, yellow denotes higher-income CBGs and blue represents the overall population. Aside from **d** and **e**, which were directly extracted from mobility data, all results in this figure represent predictions aggregated over model realizations. Across metro areas, we sample 97 parameter sets, with 30 stochastic realizations each (*n* = 2,910); see Supplementary Table [6](https://www.nature.com/articles/s41586-020-2923-3#MOESM1) for the number of sets per metro area. Shaded regions in **c** and **f** denote the 2.5th–97.5th percentiles; boxes in (**a**, **b**) denote the interquartile range; data points outside the range are shown as individual dots. |

#### Lower-income CBGs saw smaller reductions in mobility

- 불균형의 원인 1: 이동량 감소가 훨씬 적음

#### POIs visited by lower-income CBGs have higher transmission rates

- 불균형의 원인 2: 취약계층이 이용하는 POI의 감염률이 더욱 높음

#### Reopening plans must account for disparate effects

- 제목 그대로...



### Model dynamics

- 디테일한 수학적 접근은 다음과 같

$$
{N}_{{S}_{{c}_{i}}\to {E}_{{c}_{i}}}^{(t)} \sim {\rm{Pois}}\left(\frac{{S}_{{c}_{i}}^{(t)}}{{N}_{{c}_{i}}}\mathop{\sum }\limits_{j=1}^{n}{\lambda }_{{p}_{j}}^{(t)}{w}_{ij}^{(t)}\right)+{\rm{Binom}}({S}_{{c}_{i}}^{(t)},{\lambda }_{{c}_{i}}^{(t)})
$$

$$
{N}_{{E}_{{c}_{i}}\to {I}_{{c}_{i}}}^{(t)} \sim {\rm{Binom}}({E}_{{c}_{i}}^{(t)},1/{\delta }_{E})
$$

$$
{N}_{{I}_{{c}_{i}}\to {R}_{{c}_{i}}}^{(t)} \sim {\rm{Binom}}({I}_{{c}_{i}}^{(t)},1/{\delta }_{I}),
$$

- Cases from visiting POIs: ${\rm{Pois}}(({S}_{{c}_{i}}^{(t)}/{N}_{{c}_{i}}){\sum }_{j=1}^{n}{\lambda }_{{p}_{j}}^{(t)}{w}_{ij}^{(t)})$
- cases not coptured by visiting POIs: ${\rm{B}}{\rm{i}}{\rm{n}}{\rm{o}}{\rm{m}}({S}_{{c}_{i}}^{(t)},{\lambda }_{{c}_{i}}^{(t)})$
- Infection rate at POI $p_j$: ${\lambda }_{{p}_{j}}^{(t)}={\beta }_{{p}_{j}}^{(t)}({I}_{{p}_{j}}^{(t)}/{V}_{{p}_{j}}^{(t)})$ where ${V}_{{p}_{j}}^{(t)}={\sum }_{i=1}^{m}{w}_{ij}^{(t)}$

$$
\begin{array}{c}{N}_{{S}_{{c}_{i}}\to {E}_{{c}_{i}}}^{(t)} \sim {\rm{Pois}}\left(\frac{{S}_{{c}_{i}}^{(t)}}{{N}_{{c}_{i}}}\mathop{\sum }\limits_{j=1}^{n}{\lambda }_{{p}_{j}}^{(t)}{w}_{ij}^{(t)}\right)+{\rm{Binom}}({S}_{{c}_{i}}^{(t)},{\lambda }_{{c}_{i}}^{(t)})\\ =\mathop{\underbrace{{\rm{Pois}}\left(\psi \frac{{S}_{{c}_{i}}^{(t)}}{{N}_{{c}_{i}}}\mathop{\sum }\limits_{j=1}^{n}\frac{{d}_{{p}_{j}}^{2}}{{a}_{{p}_{j}}}\left(\mathop{\sum }\limits_{k=1}^{m}\frac{{I}_{{c}_{k}}^{(t)}}{{N}_{{c}_{k}}}{w}_{kj}^{(t)}\right){w}_{ij}^{(t)}\right)}}\limits_{{\rm{New}}\,{\rm{infections}}\,{\rm{from}}\,{\rm{visiting}}\,{\rm{POIs}}}+\mathop{\underbrace{{\rm{Binom}}\left({S}_{{c}_{i}}^{(t)},{\beta }_{{\rm{base}}}\frac{{I}_{{c}_{i}}^{(t)}}{{N}_{{c}_{i}}}\right)}}\limits_{{\rm{Base}}\,{\rm{rate}}\,{\rm{of}}\,{\rm{new}}\,{\rm{CBG}}\,{\rm{infections}}}.\end{array}
$$

...

더이상은 너무 디테일해서 생략

...

###  Code availabilty

- [At GitHub](https://github.com/snap-stanford/covid-mobility): Python으로 짜여진 코드
  - 환경세팅부터 데이터 수집, 그래프 시각화까지 코드를 나름 잘 정리해주셨음 



## P2. Dynamics of COVID-19 under social distancing measures are driven by transmission network structure

- Authors: Anjalika Nande, Ben Adlam, Justin Sheen, Michael Z. Levy, Alison L. Hill
  -  진화동역학 + 생물통계
- [3 February, 2021, PLOS COMPUTATIONAL BIOLOGY](https://doi.org/10.1371/journal.pcbi.1008684)
- [Code-GitHub](https://github.com/alsnhll/COVID19NetworkSimulations)

### Highlight

- 사회적 거리두기를 네트워크 구조에 따라 시뮬레이션 함
- 사회적 거리두기 정책에 따라 관찰된 효과들은 역학적 분석에 따르면 일관성이 없어 예측 불가능함
- 강력한 사회적 거리두기를 두어도 여전히 발병률은 증가하는데, 사회적 거리두기를 시행하는 시기, 진짜 효과가 있는지, 언제 시행해야 제일 좋은지에 대한 연구
- 한줄 요약: **강력한 사회적 거리두기 조치를 시행 한 후에도 몇 주에서 몇 달 후에 전염병이 최고조에 달할 수 있으며 감소 추세가 매우 느릴 수 있음**

| ![](https://journals.plos.org/ploscompbiol/article/figure/image?size=large&id=info:doi/10.1371/journal.pcbi.1008684.g001) |
| :----------------------------------------------------------: |
| **Fig 1. COVID-19 dynamics before and after lockdown interventions in five example regions.**<br />A) The city of Wuhan, China (8.5K $km^2$, 11.1M ppl), B) The Lombardy region of Italy (23.8K km2, 10.1M ppl) C) The autonomous Community of Madrid in Spain (8.0K km2, 6.6M ppl) D) New York City in the state of New York, USA (1.2K km2, 8.2M ppl). E) The county of Los Angeles, California, USA (4.7K km2, 9.8M ppl). “New cases” and “New deaths” are daily numbers of new reports, averaged over a 7 day window centered on the current day. For Lombardy, New York, and Los Angeles, “Hospitalized” and “ICU” are the total number of patients currently in regular hospital care or critical care, respectively. In Wuhan, the same time series are the number of patients currently categorized as having “severe” or “critical” infection (using the same definitions as in our model). In Madrid, due to data availability, these series are instead the daily number of new admissions (with 7-day smoothing). |

###  Model

#### Modeling the spread and clinical progression of COVID-19

- modified the classic SEIR compartmental epidemiological model
- simulate infection spreading stochastically through a fixed, weighted contact network with one million nodes
- Fig2는 mean-field case

| ![](https://journals.plos.org/ploscompbiol/article/figure/image?size=large&id=info:doi/10.1371/journal.pcbi.1008684.g002) |
| :----------------------------------------------------------: |
| **Fig 2. Dynamics pre and post social distancing intervention in well-mixed populations.**<br />A) Model of COVID-19 clinical progression and transmission. The model is described in the text and detailed in the Methods. Social distancing interventions (red X) reduce the rate of transmission and the generation of new infections. B-E) Simulated time course of the population level prevalence of each clinical stage of infection under different intervention efficacies. The intervention was implemented on day 40. Solid line is mean and shaded areas are 5th and 95th percentile. Black dotted line shows the time the intervention began. F) Time to peak of different infection stages, measured as days post-intervention. The first three quantities are peak prevalence levels (I1, I2, I3), while the latter two are peak daily incidence values. We assume that cases are diagnosed only at the time of hospitalization. Daily incidence values were first smoothed using moving averages over a 7 day window centered on the date of interest. Bars represent 5th and 95th percentile. |

- Fig3은 multi-layer networks describing connections within households and external connections
- average household size $n_{HH}$~2.5, full distribution shown in **[Fig 3B](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1008684#pcbi-1008684-g003)**
- recorded daily interactions amenable to transmission of respiratory infections (average $n_{EX}$~7.5, standard deviation 2.5
- 매우 강력한 개입은 그 효과가 확실한 반면, 불완전한 개입(80%)에서는 그 효과가 매우 점진적인 감소로 이어짐

| ![](https://journals.plos.org/ploscompbiol/article/figure/image?size=large&id=info:doi/10.1371/journal.pcbi.1008684.g003) |
| :----------------------------------------------------------: |
| **Fig 3. Dynamics pre and post social distancing interventions in network-structured populations with household and external transmission.**<br />A) Multi-layer network of transmission. Individuals have contacts within their households and with others outside the household. Household and external contacts may have different weights (e.g. different likelihood of transmission), due to for example different levels of physical contact or time spent together per day. Social distancing interventions (red X) remove or decrease the weight of external contacts. B) Distribution of household sizes. C) Distribution of the # of contacts (degree) within the household and outside the household. D) The contribution of household and external spread to the total R0 value as a function of the relative weight of external contacts. E)-F) Simulated time course of different clinical stages of infection under an intervention with efficacy of 100% (E) or 80% (F) at reducing external contacts, when household and external contacts have equal weight. Black dotted line shows the time the intervention began. G) The role of the relative importance of household vs external contacts in determining the outcome of the intervention, measured by the size of the epidemic. Epidemic final size is defined as the percent of the population who have recovered by day 300. H-J) Same as above but under the scenario where the weight of household contacts doubles post-intervention ($w_{HH}$ → $2w_{HH}$, due to increased time spent in house). K) The household secondary attack rate, defined as the probability of transmission per susceptible household member when there is a single infected individual in the house, as a function of the relative weight of external contacts. L) The percent of households which are “seeded” with infection at the time the intervention was implemented (i.e. have at least one infected individual). In all scenarios the overall infection prevalence at the time intervention was started was identical. |





| ![](https://journals.plos.org/ploscompbiol/article/figure/image?size=large&id=info:doi/10.1371/journal.pcbi.1008684.g004) |
| :----------------------------------------------------------: |
| **Fig 4. Time to epidemic peak after social distancing interventions depends on the relative roles of household and external transmission.**<br />A-C) Time to peak of different infection stages, measured as days post-intervention. A) Social distancing intervention with 100% efficacy at reducing external contacts (or all contacts in the case of a well-mixed network). B) Social distancing intervention with 80% efficacy. C) Social distancing intervention with 80% efficacy, and assuming that household weights double post-intervention (*w**HH* → 2*w**HH*, due to increased time spent in the home). The first three quantities are peak prevalence levels (I1, I2, I3), while the latter two are daily incidence values. We assume that cases are diagnosed only at the time of hospitalization. Daily incidence values were first smoothed using moving averages over a 7 day window centered on the date of interest. Bars represent 5th and 95th percentile. For each clinical stage included (each different color), the lighter-colored data point is the comparison to the well-mixed population, then the other points are for decreasing contributions of external connections and increasing role of household transmission. |

- 인구 집단을 세분화: 취학 연령, 취학 연령, 노동 연령 및 노인의 네 가지
- 외부 접촉을 세분화: 학교, 직장, 사회 및 커뮤니티의 네 가지 계층

| ![](https://journals.plos.org/ploscompbiol/article/figure/image?size=large&id=info:doi/10.1371/journal.pcbi.1008684.g005) |
| :----------------------------------------------------------: |
| **Fig 5. Clustered vs uniform adoption of social distancing measures.**<br />A) Schematic of the multi-layer network created to more realistically capture non-household contacts and how they are altered by social distancing measures. In each layer, the degree distribution and level of clustering were chosen to match data. The “community” layer represents any other contact not fitting in the other four categories. Colors of nodes represent four broad age groups that determine network membership and structure: preschool-aged (pink), school-aged (purple), working-aged (blue) and elderly (green). B)—C) Simulated time courses of infection in the presence of social distancing intervention with random (B) vs clustered (C) adherence to measures. In both cases, all school connections were deleted post-intervention and 85% of connections were uniformly deleted at random in the social and community layers. In B) 85% of work connections were uniformly deleted whereas, in C) 85% of workplaces were dissolved, leading to clusters of disconnected vs connected individuals in the work layer of the network. The effective intervention efficacy for all layers combined was ~ 88% in both scenarios. Black dotted line shows the time the intervention began. |

| ![](https://journals.plos.org/ploscompbiol/article/figure/image?size=large&id=info:doi/10.1371/journal.pcbi.1008684.g006) |
| :----------------------------------------------------------: |
| **Fig 6. Individual risk of infection depends on household size and worker status.**<br />A) Risk of infection versus household size in simulations. Risk of infection was calculated after 300 days, with 100% intervention efficacy. Bar colors represent different relative weights of external contacts (compared to household contacts). Dotted lines are the population level average infection levels for the same scenarios. B) Risk of infection versus worker status. A “worker” is defined as someone with an occupation in which they continue to work outside the home despite social distancing measures. Categories include being a worker yourself (red), living in a household with at least one other individual who is working (orange), or having no workers in the house (yellow). As a comparison the population average risk is shown (dotted line). Interventions that reduce the overall number of people working outside the home by 70% and 85% are shown (in all cases all schools are assumed to be closed and the same percent of social and community contacts are removed). |

| ![](https://journals.plos.org/ploscompbiol/article/figure/image?size=large&id=info:doi/10.1371/journal.pcbi.1008684.g007) |
| :----------------------------------------------------------: |
| **Fig 7. Effect of partially relaxing intervention by forming household bubbles.**<br />Some time after a social distancing intervention was implemented, each household merges with another random household. In each resulting two-household “bubble”, all individuals are connected to all other individuals. A)-D) Simulated time courses of infection before and after social distancing interventions (with 80% vs 90% intervention efficacy) and after partial-relaxation by household merging. Top row: External contacts of individuals were unchanged after two households were merged, such that overall number of contacts increased. Bottom row: External contacts for individuals were reduced after two households were merged, such that overall number of contacts remained unchanged. In all cases, intervention was started 43 days after the onset of the epidemic (first black dotted line) and was relaxed after two months (60 days, second black dotted line). |

## P3. Modelling COVID-19 transmission in supermarkets using an agent-based model

- Authors: Fabian Ying, Neave O’Clery
  -  정량연구, 공간역학 
- [April 9, 2021, PLOS ONE](https://doi.org/10.1371/journal.pone.0249821)
- [Code-GitHub](https://github.com/fabianying/covid19-supermarket-abm)

### Highlight

- 가상의 슈퍼마켓 구조에 대한 ABM 시뮬레이션 논문
- 시뮬레이션을 통해 최대 고객수 제한, 배치 변경 등을 테스트
- 쇼핑 데이터에 적용하여 노출 시간을 추정
- 강력한 사회적 거리두기를 두어도 여전히 발병률은 증가하는데, 사회적 거리두기를 시행하는 시기, 진짜 효과가 있는지, 언제 시행해야 제일 좋은지에 대한 연구
- 한줄 요약: **강력한 사회적 거리두기 조치를 시행 한 후에도 몇 주에서 몇 달 후에 전염병이 최고조에 달할 수 있으며 감소 추세가 매우 느릴 수 있음**

| ![](https://journals.plos.org/plosone/article/figure/image?size=large&id=10.1371/journal.pone.0249821.g001) |
| :----------------------------------------------------------: |
| **Fig 1. Overview of agent-based model.**<br />**(A)** A network representation of a small supermarket/convenience store with an example shopping path (in green). We generate each shopping path from a sequence of shelf locations (in blue), which correspond to the shelves from a customer picks up their items during a visit and the entrance and the tills. In this example, the customer picks up *K* = 4 items at the shelves marked in blue with 2, 3, 4, and 5. **(B)** Virus transmission model. A susceptible customer (in black) becomes infected at rate *β* whenever they are in the same zone as an infectious customer (in red). |

| ![](https://journals.plos.org/plosone/article/figure/image?size=large&id=info:doi/10.1371/journal.pone.0249821.t001) |
| :----------------------------------------------------------: |
| **Table 1. Parameter values in our agent-based model.**<br />We list uncertainty bounds, when available. |

| ![](https://journals.plos.org/plosone/article/figure/image?size=large&id=info:doi/10.1371/journal.pone.0249821.g002) |
| :----------------------------------------------------------: |
| **Fig 2. Exposure times and chance of infection from 1000 simulations.**<br />**(A)** Histogram of total customer exposure time for all exposed customers (i.e., susceptible customers with positive exposure time) across 1000 simulations. The distribution can be approximated by an exponential distribution. **(B)** Histogram of chance of infection per susceptible customer across 1000 simulations. **(C)** Total exposure time per node. Nodes in the centre and near the tills of the store show significantly higher amount of exposure time than others. |

| ![](https://journals.plos.org/plosone/article/figure/image?size=large&id=info:doi/10.1371/journal.pone.0249821.t002) |
| :----------------------------------------------------------: |
| **Table 2. Simulation results.**<br />We show the mean and standard deviation of each metric across 1000 simulations. |

| ![](https://journals.plos.org/plosone/article/figure/image?size=large&id=info:doi/10.1371/journal.pone.0249821.g003) |
| :----------------------------------------------------------: |
| **Fig 3. Change in number of infections and chance of infection by reducing maximum number of customers in store or arrival rate.**<br />**(A + B)** Mean number of infections (with the shaded area showing the standard deviation) as a function of maximum number *C*max of customers and customer arrival rate λ (respectively). As the number of infections is a linear function of the total exposure time, we also show the total exposure time on the right vertical axis. **(C + D)** Mean chance of infection for each susceptible customer (with the shaded area showing the standard deviation) as a function of maximum number *C*max of customers and customer arrival rate λ (respectively). As the chance of infection is a linear function of the mean exposure time (per susceptible customer), we also show the mean exposure time on the right vertical axis. In subfigures (A) and (C), the mean number of infections and mean chance of infection plateaus, as the number of customers typically does not exceed 20 in our simulations. |

| ![](https://journals.plos.org/plosone/article/figure/image?size=large&id=info:doi/10.1371/journal.pone.0249821.g004) |
| :----------------------------------------------------------: |
| **Fig 4. Effect of one-way aisle layout on infections.**<br />**(A)** Store layout with one-way aisles. **(B + C)** Number of infections in a store as a function of the customer arrival time and mean number of customers (respectively). We show on the right vertical axis the total exposure time, as the number of infections is proportional to the total exposure time in our model. The one-way layout increases the number of infections with the same arrival rate (see subfigure D). It appears that the number of infections mainly depends on how many customers are in the store on average (see subfigure C). **(D)** Mean customer shopping time. The one-way layout increases the time that customers spend in the store, so more customers are in the store and thereby increase the number of infections. |

|      |
| :--: |
|      |

|      |
| :--: |
|      |

|      |
| :--: |
|      |

