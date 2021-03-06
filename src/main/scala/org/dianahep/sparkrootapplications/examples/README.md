# Various Examples. 

## ReductionExample App
- Reads in a dataset in ROOT format
- Selects a Collection of Muons - quite standard collection that we use to test against
- Performs some trivial filter/flatMap operations: Selects DiMuon pairs
- Aggreages with Histogrammar and prints... and saves bundles: file:/tmp/testBundles.json
- Saves in parquet format all of the flattened Dimuon pairs: file:/tmp/testReduced.parquet

__To Run:__
```
from the root of this repo:
sbt package

__this cmd below is just an example!!! You must provide the input properly... The jar which contains the class... etc... all the paths should be specified acording to your needs__
spark-submit --master local --class "org.dianahep.sparkrootapplications.examples.ReductionExampleApp" --packages org.diana-hep:spark-root_2.11:0.1.11,org.diana-hep:histogrammar-sparksql_2.11:1.0.3 /Users/vk/software/diana-hep/spark-root-applications/target/scala-2.11/spark-root-applications_2.11-0.0.2.jar file:/Users/vk/software/diana-hep/test_data/0029E804-C77C-E011-BA94-00215E22239A.root
```

__Some of the things it will print:__
```
On dsDiMuons.show:

+---------+-------------+------------+----------+
|        e|           px|          py|        pz|
+---------+-------------+------------+----------+
| 9.027341|    2.8114102|   2.0337317| -8.331155|
|20.616512|    4.2575407|    5.383979|-19.399937|
|20.616512|    4.2575407|    5.383979|-19.399937|
|32.205685|    5.7036715|    8.734226| -30.46872|
|14.988299|   -1.2429894|   -3.692814|-14.471439|
|10.421754|-0.0064013065|   -3.198005| -9.756542|
|10.421754|-0.0064013065|   -3.198005| -9.756542|
| 5.855208|    1.2301868|  -2.7031958| -5.041644|
|16.901054|   -2.2639802|  -5.7359023| -15.73451|
|12.972484|    -2.917809|  -2.4680312|-12.000999|
|12.972484|    -2.917809|  -2.4680312|-12.000999|
| 9.043912|   -3.5716379|     0.79984| -8.267488|
|28.126917|   -1.6677399|    5.838281|  27.46292|
|19.399242|   -1.5881548|   4.0297585|   18.8945|
|19.399242|   -1.5881548|   4.0297585|   18.8945|
|10.671566|   -1.5085697|    2.221235| 10.326083|
|109.69228|     6.773477|    48.19971| -98.30189|
|58.403553|    2.2265315|   24.095825|-52.512177|
|58.403553|    2.2265315|   24.095825|-52.512177|
|7.1148167|   -2.3204138|-0.008062047| -6.722468|
+---------+-------------+------------+----------+

                        +---------------------------------------------------------+
underflow      0        |                                                         |
[  0  ,  1  )  4423     |*********                                                |
[  1  ,  2  )  1.569E+4 |******************************                           |
[  2  ,  3  )  2.687E+4 |****************************************************     |
[  3  ,  4  )  2.609E+4 |**************************************************       |
[  4  ,  5  )  2.099E+4 |****************************************                 |
[  5  ,  6  )  1.441E+4 |****************************                             |
[  6  ,  7  )  9870     |*******************                                      |
[  7  ,  8  )  7484     |**************                                           |
[  8  ,  9  )  5448     |***********                                              |
[  9  ,  10 )  3779     |*******                                                  |
[  10 ,  11 )  2919     |******                                                   |
[  11 ,  12 )  2081     |****                                                     |
[  12 ,  13 )  1500     |***                                                      |
[  13 ,  14 )  1146     |**                                                       |
[  14 ,  15 )  833      |**                                                       |
[  15 ,  16 )  667      |*                                                        |
[  16 ,  17 )  522      |*                                                        |
[  17 ,  18 )  369      |*                                                        |
[  18 ,  19 )  301      |*                                                        |
[  19 ,  20 )  215      |                                                         |
[  20 ,  21 )  204      |                                                         |
[  21 ,  22 )  141      |                                                         |
[  22 ,  23 )  128      |                                                         |
```
