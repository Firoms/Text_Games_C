C 언어를 기반으로 한 텍스트 게임입니다.   
2017년에 제가 처음으로 했던 프로젝트이기 때문에,   
조금 미흡한 부분이 많고 그래픽적인 요소 역시 거의 들어가지 않았습니다.   
gotoxy 함수를 바탕으로 프로그램의 화면이 전환되도록 만들었습니다.   
또한, 랜덤 함수 rand를 이용하여 게임적인 요소를 추가하였습니다.   
   
   ***
   
   
## 서바이벌 블랙잭 게임 (Black Jack Game)
기본적인 블랙잭 게임의 룰을 기반으로 한 카드 게임입니다.   
원래는 AI나 두 명의 플레이어가 함께 할 수 있는 블랙잭 게임을 제작하고 싶었으나,   
제작 당시 능력이 부족하여 혼자서 할 수 있는 디펜스 형식의 블랙잭 게임으로 구성하였습니다.
### 룰
라운드마다 정해진 목표점수가 있습니다.   
블랙잭 게임을 통해 플레이어의 점수를 획득합니다.   
(점수는 라운드마다 초기화되지 않고 누적됩니다.)   
플레이어의 점수가 현재 라운드의 목표점수보다 높거나 같으면,   
다음 라운드가 진행되고, 그렇지 않으면 게임에서 패배하게 됩니다.   
### 점수 획득 방법(블랙잭 게임)
한 라운드 당 블랙잭 게임이 한번 진행되어 점수를 획득할 수 있습니다.   
라운드가 시작되면, 기본적으로 1에서 11까지의 숫자중 하나가 랜덤으로 뽑히게 됩니다.  
이때 1을 입력하고 엔터를 누르면 카드를 하나 뽑을 수 있으며,   
2를 입력하고 엔터를 누르면 카드를 그만 뽑을 수 있습니다.   
한 라운드에 뽑은 카드의 합만큼 점수를 획득할 수 있지만,   
카드의 합이 21을 초과할 경우 Bust로 0점을 획득하게 되니 적당하게 카드를 뽑아야 합니다.
반면 카드의 합이 딱 21이 될 경우 블랙잭을 달성하게 되며,   
보너스로 25에서 50사이의 랜덤 점수를 추가로 획득하게 됩니다.   
### 추가사항
라운드 별 목표점수는 2x(라운드)x(라운드)의 값으로 설정하였습니다.   
서바이벌 형태의 게임이기 때문에, 플레이어가 패배할 때까지 게임이 진행됩니다.   
숫자가 잘못입력되면, 카드 그만 뽑기가 선택됩니다.   
   
   
   ***
   
   
## 프로그램 강화 게임 (Program Reinforce Game)
대부분의 강화게임과 비슷한 형태로 진행되는 게임입니다.   
서바이벌 블랙잭 게임 제작 이후, 욕심이 생겨서   
유사한 시스템으로 프로그램 강화 게임을 제작하였습니다.
### 룰
기본금 1000원을 바탕으로 프로그램을 구입/판매/강화를 통하여 수익을 얻고   
이러한 수익을 바탕으로 계속한 강화를 통해 높은 등급의 프로그램을 만드는 것이 목적입니다.   
크게 패배 조건은 없지만, 프로그램을 구입 할 자금이 없을 경우 게임에 참여할 수 없습니다.
### 기능
프로그램 강화 게임에는 크게 4가지 기능이 있습니다.
#### 1. 프로그램 강화
프로그램 강화를 선택하면, 일정 확률로 강화에 성공하게 됩니다.   
강화에 성공하게 되면 일정 금액을 획득하며, 프로그램 강화 등급이 기본적으로 1만큼 상승합니다.   
반면 강화에 실패할 경우, 프로그램 강화 등급이 5등급 하락합니다.
강화 확률은 (100-(현재 프로그램 강화 등급))%로 강화에 성공할 수록 확률이 희박해집니다.   
#### 2. 프로그램 사기
프로그램 사기를 선택하면, 플레이어가 소유한 금액으로 강화할 프로그램을 구매할 수 있습니다.   
기본적으로 강화등급이 1인 프로그램은 100원, 10인 프로그램은 300원, 20인 프로그램은 1000원,   
30인 프로그램은 3000원, 30에서 60사이의 랜덤 등급의 프로그램은 10000원을 지불하여 구입할 수 있습니다.   
#### 3. 아이템 상점
아이템 상점을 선택하면, 프로그램 강화와 관련 된 아이템을 구매할 수 있습니다.   
강화 확률을 2%, 5%, 10% 올려주는 아이템을 각각 1000원, 2000원, 3500원에 구입할 수 있습니다.   
또한 강화 성공했을 때, 등급을 추가적으로 3만큼 올려주는 아이템이 5000원,   
5만큼 올려주는 아이템을 10000원으로 구입 가능합니다.   
구매한 아이템들은 즉시 사용되며, 확률 증가 아이템은 중복사용이 가능합니다.
#### 4. 로또
로또를 선택하면, 플레이어가 소유한 금액으로 로또를 도전할 수 있습니다.   
원하는 금액을 로또에 지불하면, 10%로의 확률로 지불한 금액의 2,3,5,10배에 당첨되며,   
50%의 확률로 지불한 금액을 다 잃게 됩니다.
### 추가사항
승리목표는 크게 없으며, 프로그램의 강화 등급을 자신의 한계까지 높여보는 것이 목적인 게임입니다.   
프로그램의 강화 등급이 100 이상이 될 경우에는 무조건 아이템을 사용해야 강화에 성공할 수 있습니다.   
1,2,3,4 이외의 다른 문자나 번호를 입력하게 되면, 다시 선택해 주세요라는 문구가 뜨지만,   
숨겨진 코드로 제작 연도인 2017를 입력할 경우, 돈 30000원을 획득할 수 있습니다.   
