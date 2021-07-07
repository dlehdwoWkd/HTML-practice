# Transition

어떤 상태에서 다른 상태로의 변화를 보내주는 애니메이션  
(1) transition은 state가 없는 요소에 붙어야 한다.  
(2) transition에 변화를 준 것들은 state에 들어있는 것들이 기준이 되어 바뀌는 것이다.

# Transformation

css로 3D까지 할 수 있게 하는 기능  
(1) transformation은 box element를 변형시키지 않는다. 그러므로 옆에 sibling들에게 영향을 끼치지 않는다.  
(2) 일종의 3D transformation이기 때문에 margin, padding이 적용되지 않는다.  
(3) transfomation은 페이지의 픽셀의 다른 부분에서 일어난다.  
(4) box차원에서 일어나지 않는다.  
(5) transition 등과 결합 가능하다.

# 애니메이션 만들기

@keyframes 애니메이션 이름{
from{

}  
to {

}  
}  
사용하기 {  
animation: 애니메이션 이름 재생시간 옵션  
}

여러 단계로 나누어 할경우 from to 가 아닌 0% 25% 50% 75% 100% 로 나눠서 할 수도 있다.

# Media query

웹사이트를 보고 있는 이용자의 스크린 사이즈를 감지해서 화면을 변하게 해주는 방법  
@media screen and (max-width: 00px) {} 을 이용하여 몇 픽셀부터 화면이 다르게 보이는지 설정할 수 있다.  
orientation: landscape를 이용하면 세로모드인지 가로모드인지도 구별 할 수 있다.
