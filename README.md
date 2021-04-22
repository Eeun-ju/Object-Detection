# Object-Detection  
여러 물체에 대해 어떤 물체인지 분류하는 **Classification** 문제와 그 물체의 위치를 박스를 통해 나타내는 **Localization** 문제를 해내는 분야이다.  
자율주행자동차, CCTV, 스포츠 경기 등에 쓰이며 위 코드는 2019년 하계 현장실습 CCTV 사람 탐지 프로젝트에서 구현한 코드이다.  

### R-CNN(Regions with CNN features)의 등장
CNN은 바로 object Detection 분야에 적용되지 못하고 있다가 R-CNN의 등장으로 적용되었다. R-CNN을 수정, 보완하여 관련 계열의 논문들(Fast, Mask etc)이 등장하였다.  
*사진첨부*  
데이터와 레이블 투입 -> 영역 제안 -> 제안된 영역(CNNs) -> 분류 및 Bounding Box 조정 순으로 이루어진다.  
영역 제안은 선택적 탐색 방법으로 이루어진다. 특정 기준에 따라 탐색을 실시하는 방법으로, 작은 크기의 초기 영역을 설정한 후 작은 영역을 큰 영역으로 병합하여 이를 바탕으로 영역을 제안하게 된다. SVM을 통한 분류와 Box 제안은 동시에 이루어진다. 
모든 제안된 Box마다 CNN을 돌려야 하고 분류를 위한 SVM, Regression까지 모두 이루어져야 하기 때문에 어렵고 시간이 오래 걸린다는 문제가 있다.

### Faster R-CNN  
새로운 방식인 Region Proposal Network(RPN)을 통해 속도를 올리고 실시간으로 인식이 가능할 수 있게 만든 모델이다. 



### Mask R-CNN

농촌진흥청 - 꽃 개수 카운팅 프로젝트에서 사용한 코드이다. Mask R-CNN은 물체 분류와 위치를 모두 나타내는데, Box형식이 아닌 mask 한다. Instance Segmentation까지 다루는 특징이 있다.   
Classification, BBox Regression, Mask를 동시에 얻으며 Fast R-CNN에 mask를 추가한 모델이다. 
github 링크 : https://github.com/matterport/Mask_RCNN
