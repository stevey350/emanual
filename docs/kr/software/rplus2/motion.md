---
layout: archive
lang: kr
ref: rplus2_motion
read_time: true
share: true
author_profile: false
permalink: /docs/kr/software/rplus2/motion/
sidebar:
  title: R+ Motion 2.0
  nav: "rplusmotion2"
---

# [개요](#개요)

![](/assets/images/sw/rplus2/motion/r+motion_main.jpg)

1. 로보플러스 모션(R+ Motion)  
  모션이란 로봇이 의미있는 행동을 하기 위해 필요한 관절 별 모터의 위치와 속도 데이터 집합을 의미합니다. 로봇이 움직이기 위해서는 조립된 로봇에 맞는 모션 프로젝트 파일을 편집하여 다운로드 해야 합니다.

    ![](/assets/images/sw/rplus2/motion/motion_34.gif)

2. 모션 파일과 태스크 파일은 어떤 관계인가요?  
  태스크 파일은 로봇이 어떻게 생각하고 움직일지 논리, 사고를 정의한 프로그램 코드이며, 모션 파일은 태스크에서 내린 판단에 따라 움직일 행동이 정의된 데이터입니다.  
  만약, 내가 만든 로봇이 단순한 동작만을 사용하는 로봇이라면 태스크 파일을 작성할 때 모션을 사용하지 않아도 되지만 정밀한 움직임이나 댄스와 같이 많은 움직임이 필요하다면 모션 파일을 사용하는 것이 효율적입니다.  
  **(태스크 코드에서 모션을 사용한다면, 반드시 모션 파일을 다운로드해야 합니다.)**

## [메뉴설명](#메뉴설명)

![](/assets/images/sw/rplus2/motion/motion_1.gif)

1. 단계별 편집탭  
  모션의 편집과정은 아래와 같이 4단계로 분리되어있으며 순서대로 편집을 진행합니다. 각 탭메뉴는 키보드의 단축키 F1~F4로 빠른 이동이 가능합니다.

    ![](/assets/images/sw/rplus2/motion/motion_2.gif)

2. 빠른 실행 메뉴  
  홈 탭으로 이동하지 않고 다른 프로젝트를 열거나 현재 열려있는 프로젝트를 저장할 수 있습니다.

3. 로봇 연결 메뉴  
  “연결하기”버튼을 클릭하여 로봇 연결하기 창이 활성화되면 아래와 같이 로봇이 연결된 포트를 선택한 후 연결을 시도할 수 있습니다.

    ![](/assets/images/sw/rplus2/motion/motion_3.gif)

4. 로그창  
  모션 편집과정에서 발생한 알림 메시지와 오류 메시지가 표기됩니다. 아래 그림에서 순서대로 로그의 레벨, 발생시간, 메시지가 표기됩니다.

    ![](/assets/images/sw/rplus2/motion/motion_4.gif)

## [3D 로봇과 실제 로봇](#3d-로봇과-실제-로봇)

3D 로봇은 실제 로봇의 아바타 역할을 합니다. 실제 로봇이 없는 상황에서는 로봇을 대신하여 모션을 편집하거나 재생합니다.  
실제 로봇이 연결된 상황에서는 자동 동기화 기능을 통해 실제 로봇을 조작하는 인터페이스로 사용됩니다.  
제품별로 제공하는 예제를 3D 로봇으로 제공하며 모션 프로젝트를 처음 생성할 때 선택할 수 있습니다.  
최초 선택된 3D 로봇은 모션프로젝트를 생성한 후에는 변경할 수 없으며 추후 변경할 수 있도록 지원할 예정입니다.

![](/assets/images/sw/rplus2/motion/r+motion41.jpg)

제공하는 3D 로봇 외에 사용자가 임의로 제작한 로봇을 사용할 경우 다이나믹셀 정보를 읽어와 자유 형태 로봇을 구성할 수 있습니다.

![](/assets/images/sw/rplus2/motion/r+motion42.jpg)

## [모션 데이터](#모션-데이터)

모션 파일에는 로봇을 움직이고 다운로드하기 위한 여러 정보가 포함되며 데이터 구조는 아래 그림과 같습니다.

![](/assets/images/sw/rplus2/motion/motion_5.gif)

1. 키-프레임  
  기존의 모션 스텝(Motion Step)과 유사한 개념으로 로봇의 연속적인 움직임을 표현하기 위해 특징적인 자세를 재생하고 싶은 시점에 저장한 단위를 말합니다.  
  예를 들어 1.5초 시점에서 “만세”자세를 키-프레임으로 저장해놓으면, 해당 시점이 다가올수록 로봇이 “만세”자세를 취하게 됩니다.

    ![](/assets/images/sw/rplus2/motion/motion_6.gif)

2. 모션 유닛  
  기존의 모션 페이지(Motion Page)와 유사한 개념으로 로봇의 연속적인 움직임을 표현하기 위해 시간 순으로 배치한 키-프레임의 묶음 단위를 말합니다.  
  아래 그림을 예로 들면 “박수치기”라는 모션 유닛은 0.5초에 “양손 펼치기” 키-프레임을 저장하고, 1초에 “양손 모으기” 키-프레임을 저장한 형태로 이루어질 수 있습니다.

    ![](/assets/images/sw/rplus2/motion/motion_7.gif)

3. 모션  
  기존의 페이지 연결(Page Link)과 유사한 개념으로 로봇의 댄스와 같이 복잡하고 긴 동작을 표현하기 위해 여러 개의 모션 유닛을 연결한 묶음 단위를 말합니다.  
  아래 그림을 예로 들면 “태권무”라는 모션은 “왼손 잽”, “좌향좌”, “오른쪽공격1”, “오른손 어퍼라”는 모션 유닛을 순서대로 연결한 형태로 이루어질 수 있습니다.

    ![](/assets/images/sw/rplus2/motion/motion_8.gif)

4. 모션 그룹  
  모션 2.0에서는 파일내의 용량 제한이 없어지게 되어, 로봇에 다운로드시 일부의 모션을 선택하여 모션 목록을 작성하여야 합니다.  
  이렇게 작성된 모션 목록을 “모션 그룹”이라 부르며 제어기의 메모리 용량에 따라 저장할 용량이 백분율로 표시됩니다.  
  아래 그림을 예로 들면 “댄스 전용”이라는 모션 그룹은 9개의 모션을 담고 있으며 제어기 용량의 15.7%를 사용합니다.  

    ![](/assets/images/sw/rplus2/motion/motion_9.gif)

5. 3D 로봇  
  모션 데이터를 해석할 때 기준이 되는 로봇으로 로봇이 연결되지 않은 상황에서도 모션 데이터를 재생할 수 있도록 도와줍니다.  
  모션 파일을 생성할 때 반드시 선택해야 하며, 편집기 내에서 “3D 로봇 변경”메뉴를 제공합니다.  
  아래 그림은 동일한 모션 데이터를 서로 다른 3D 로봇에 적용한 예시 입니다.  

    ![](/assets/images/sw/rplus2/motion/motion_10.gif)

## [타임라인 편집 방식의 장점](#타임라인-편집-방식의-장점)

기존에는 로봇의 동작을 표현하는 단위로 모션 페이지를 사용했으나 모션 2.0에서는 “모션 유닛”을 사용합니다.  
모션 유닛은 하나의 타임라인을 가지며 타임라인 상에 포즈를 배치할 수 있습니다.  

기존에는 페이지 내의 스텝 개수가 7개로 제한되어 있어서 8개 이상의 스텝이 필요한 경우 추가 페이지를 만들어 연결해주는 불편함이 있었지만 새로운 모션 2.0에서는 스텝 개수가 제한되지 않습니다.  
또한 영화 및 애니메이션 분야에서 많이 활용되는 타임라인기반의 키-프레임 편집 방식을 도입하여 로봇의 스텝을 시간의 흐름 순으로 나열하고 스텝간의 간격을 시각적으로 조절하기 때문에 연속 동작을 기존 모션 1.0보다 효과적으로 편집할 수 있습니다.

  ![](/assets/images/sw/rplus2/motion/motion_11.gif)

  > 키프레임 편집 - 연속 동작을 이루는 키-포즈를 시간 순으로 나열하는 편집 방식

타임 라인에서 삽입된 스텝이 막대의 형태로 1차원 그래프로 표시되어 스텝간격을 직관적으로 확인할 수 있을 뿐만 아니라 사이 시간의 보간 포즈(interpolation pose)도 확인할 수 있게 되었습니다.

## [흐름제어 편집 방식의 장점](#흐름제어-편집-방식의-장점)

기존에는 모션 페이지 간의 연결과 반복, 재생속도가 각 페이지에 종속되어 있어 같은 페이지 데이터를 여러 곳에서 재사용하기 어려웠지만 모션 2.0에서는 이러한 흐름 제어(연결, 반복, 재생속도 조절)를 모션 유닛에서 분리하여 하나의 모션 유닛을 여러 곳에서 재사용할 수 있고 반복 및 재생 속도를 자유롭게 지정할 수 있도록 하였습니다.   
또한 2D 블록과 화살표 기반의 흐름도를 도입하여 나열된 블록과 화살표를 읽는 것 만으로 로봇이 어떻게 움직일지 예측할 수 있습니다.

아래의 그림은 모션 흐름도의 예시입니다. 그림과 같이 작성된 모션은 다음과 같이 동작합니다.

1. 모션 유닛 “인사2”를 1.3배 속도로 2번 반복 재생한 후,
2. 모션 유닛 “앉아”를 1배 속도로 1번 재생한 후,
3. 모션 유닛 “일어서”를 1배 속도로 1번 재생합니다.

  ![](/assets/images/sw/rplus2/motion/motion_12.gif)

## [모션 다운로드 주의사항](#모션-다운로드-주의사항)

기존에는 모션 파일의 크기가 로봇 제어기의 저장 용량을 초과할 수 없어 용량이 큰 모션의 경우 모션 파일을 별도로 나누어 저장해야 했던 반면, 모션 2.0에서는 모션 프로젝트 내에 용량 제한이 없어 한 가지 로봇의 모션을 하나의 파일에 모두 저장한 후 필요시 선택적으로 다운로드할 수 있습니다.  
모션 프로젝트 내에 저장된 로봇 모션 중 목적에 따라 원하는 모션을 모션 그룹으로 묶을 수 있으며, 작성한 모션 그룹 중 하나를 로봇에 다운로드할 수 있습니다.

![](/assets/images/sw/rplus2/motion/motion_13.gif)

모션 그룹을 편집하는 과정에서 모션을 담을 때마다 우측에 제어기 예상 메모리 용량이 세로 막대 그래프로 표시됩니다.
모션 그룹에 담긴 모션에는 순서대로 호출 번호가 부여되며 이를 활용해서 R+Task에서 호출할 수 있습니다.

`다운로드시 주의사항` 기존과 달리 모션 유닛과 모션을 편집하는 과정에서 실제 로봇으로 모션을 재생한 경우 로봇 제어기내에 저장된 모션이 삭제되므로 모션 편집을 완료한 후에 반드시 로봇 제어기에 모션을 새로 다운로드해야 합니다
{: .notice--warning}

# [따라해보기](#따라해보기)

## [예제 프로젝트 열기](#예제-프로젝트-열기)

1. 홈 탭의 “프로젝트 열기”버튼을 클릭합니다.
2. 예제 프로젝트 파일을 선택합니다.
3. “열기”버튼을 클릭합니다.

![](/assets/images/sw/rplus2/motion/r+motion5.jpg)

## [로봇 연결하기](#로봇-연결하기)

1. 화면 하단의 “연결하기”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion6.jpg)

2. 로봇이 연결된 포트를 선택한 후 “연결하기”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/motion_14.gif)

3. 로봇이 연결되면 아래 그림과 같이 포트 번호와 전송속도가 표시됩니다.

    ![](/assets/images/sw/rplus2/motion/r+motion8.jpg)

## [새 모션 유닛 만들기](#새-모션-유닛-만들기)

로봇의 어떠한 동작을 표현하기 위해 동작의 특징된 자세를 시간 순으로 나열하여 저장한 데이터를 모션 유닛이라 합니다. 저장된 자세들은 시간 간격에 따라 보간되어 이어진 움직임으로 재생됩니다.

1. 모션 유닛 탭으로 이동한 후, 상단 툴바의 모션 유닛 목록을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion9.jpg)

2. 모션 유닛 목록에서 "새 모션 유닛 만들기" 버튼을 클릭 합니다.
3. 새로운 모션 유닛의 이름을 입력한 후 “확인”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion10.jpg)

4. 새로 생성된 모션 유닛을 선택한 후 “확인”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion11.jpg)

## [모션 유닛 편집하기(3D 로봇 활용)](#모션-유닛-편집하기-3D-로봇-활용)

지금부터 실제 로봇이 없는 상황에서 3D 로봇만으로 모션 유닛을 편집합니다. 3D 로봇의 포즈를 편집하고 타임라인 상에 저장하여 연결된 동작을 만듭니다.

1. 아래 그림과 같이 화면 상단에 검게 표시된 타임라인(timeline)에서 임의의 위치를 클릭합니다.
2. 키보드의 Ctrl키를 누른 상태에서 4, 6번 관절을 선택합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion12.jpg)

3. 우측 하단의 “각도 조정”메뉴를 활용하면 관절을 움직일 수 있습니다. 로봇의 양팔에 해당하는 관절을 움직여 로봇의 포즈를 만들어 봅니다.

    ![](/assets/images/sw/rplus2/motion/r+motion13.jpg)

4. 화면 우측 상단에 “키 프레임 삽입”버튼을 클릭하여 앞서 만든 3D 로봇의 포즈를 삽입합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion14.jpg)

5. 다시, 타임라인 상에서 임의로 다음 위치를 지정한 후 “키 프레임 삽입”버튼을 클릭하여 동일한 포즈를 삽입합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion15.jpg)

6. 3D 로봇의 포즈를 변경한 후 “키 프레임 저장”버튼을 클릭하여 변경된 포즈를 덮어씌웁니다.

    ![](/assets/images/sw/rplus2/motion/r+motion16.jpg)

7. 상단 툴바의 “재생”버튼을 클릭하여 지금까지 만든 모션 유닛을 재생해봅니다. 앞서 타임라인 상에 삽입한 로봇의 포즈가 시간 순으로 재생됩니다.

    ![](/assets/images/sw/rplus2/motion/r+motion17.jpg)

## [모션 유닛 편집하기2(실제 로봇 활용)](#모션-유닛-편집하기2-실제-로봇-활용)

지금부터 실제 로봇을 연결하여 모션 유닛을 편집합니다. 실제 로봇의 자세를 손으로 조작하면서 타임라인 상에 저장할 동작을 만듭니다.

1. 좌측 하단의 “연결하기”버튼을 클릭하여 로봇을 연결합니다. (로봇 연결하기 참조)
2. 새로운 모션 유닛을 생성합니다. (새 모션 유닛 만들기 참조)
3. 전체 관절을 선택한 후 ”토크 끄기”버튼을 클릭하여 실제 로봇의 토크를 풀어줍니다. (임의로 관절을 클릭한 후 Ctrl+A를 누르면 전체 관절이 선택됩니다.)

    ![](/assets/images/sw/rplus2/motion/r+motion18.jpg)

4. 실제 로봇을 손으로 움직여 원하는 포즈를 만든 후 “토크 켜기”버튼을 클릭, 이어서 “로봇 포즈 읽기“버튼을 클릭합니다. (3D 로봇이 실제 로봇의 포즈를 따라 합니다.)

    ![](/assets/images/sw/rplus2/motion/r+motion19.jpg)

    ![](/assets/images/sw/rplus2/motion/r+motion20.jpg)

5. 화면 상단에 검게 표시된 타임라인에서 임의의 위치를 클릭한 후 “키 프레임 삽입”버튼을 클릭하여 로봇으로부터 읽어온 포즈를 해당 위치에 삽입합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion21.jpg)

6. 다시, 타임라인 상에서 임의로 다음 위치를 지정한 후 “키 프레임 삽입”버튼을 클릭하여 동일한 포즈를 삽입합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion22.jpg)

7. 토크 끄기 버튼을 클릭하여 실제 로봇의 토크를 풀어줍니다.
8. 실제 로봇을 손으로 움직여 원하는 자세를 만든 후 “토크 켜기”버튼을 클릭, 이어서 “로봇 포즈 읽기“버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion23.jpg)

9. “키 프레임 저장”버튼을 클릭하여 두 번째로 삽입된 포즈를 덮어 씌웁니다.
10. 좌측 하단의 “동기화 모드”버튼을 클릭하여 활성화합니다. (동기화 모드가 활성화되면 3D로봇의 포즈가 자동으로 실제 로봇에 입력됩니다.)

    ![](/assets/images/sw/rplus2/motion/r+motion23-1.jpg)

11. 타임라인 상에서 임의로 다음위치를 선택한 후 3D 로봇을 조작하여 세번째 포즈를 잡아줍니다. 이때 3D 로봇을 따라 움직이는 실제 로봇이 무게중심을 잃지 않도록 확인하며 진행합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion24.jpg)

12. 상단 툴바의 “재생”버튼을 클릭하여 지금까지 만든 모션 유닛을 재생해봅니다. 앞서 타임라인 상에 삽입한 로봇의 포즈가 시간 순으로 재생됩니다

## [새 모션 만들기](#새-모션-만들기)

모션이란 여러 개의 모션 유닛을 이어 붙이거나 반복횟수, 재생속도 등을 지정하여 댄스와 같이 긴 동작을 효율적으로 표현하기 위한 데이터 단위 입니다.  
태스크 코드에서 모션을 사용하기 위해서는 반드시 모션 유닛을 조합하여 모션을 만들어야 합니다.

1. 모션 탭으로 이동한 후, 상단 툴바의 모션 목록을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion25.jpg)

2. 모션 목록에서 “새 모션 만들기”버튼을 클릭합니다.
3. 새로운 모션의 이름을 입력한 후 “확인”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion27.jpg)

4. 새로 생성된 모션을 선택한 후 “확인”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion28.jpg)

## [모션 편집하기](#모션-편집하기)

지금부터 빈 모션 내에 모션 유닛을 삽입한 후 재생 파라미터를 편집하는 방법을 설명합니다.

1. 우측 상단에 “모션 유닛 삽입”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion29.jpg)   
    
2. 삽입할 모션 유닛을 선택한 후 “재생 파라미터”탭을 선택합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion30.jpg)

3. 재생 파라미터 탭에서 삽입할 모션 유닛의 재생속도, 반복횟수, 호출번호 삽입 유무를 편집할 수 있습니다. 우선 값을 변경하지 않고 “확인”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion31.jpg)

4. 삽입된 모션 유닛을 확인한 후 “재생”버튼을 클릭하여 모션을 확인 합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion32_.jpg)

5. 삽입된 모션 유닛을 다른 모션 유닛으로 변경하거나 재생 파라미터를 수정하려면 삽입된 모션 유닛을 더블 클릭합니다.
6. “초록색 화살표”를 더블 클릭하면 모션 유닛이 실행된 후 이어서 실행할 모션 유닛을  추가로 삽입할 수 있습니다.
7. “분홍색 화살표”를 더블 클릭하면 모션 유닛이 종료될 때 이어서 실행할 모션 유닛을 추가로 삽입할 수 있습니다.

    ![](/assets/images/sw/rplus2/motion/r+motion33.jpg)

8. “초록색 화살표”를 더블클릭하여 다음 위치에 “초기 자세” 모션 유닛을 추가합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion34.jpg)

9. 완성된 모션을 재생해봅니다.

    ![](/assets/images/sw/rplus2/motion/r+motion35.png)

## [모션 그룹 만들기](#모션-그룹-만들기)

로봇에 모션을 다운로드하기 위해서는 모션 그룹을 만들어야 합니다. 모션 그룹은 전체 모션 중 다운로드할 모션을 선택하여 묶어놓은 데이터 단위 입니다.

1. 모션 다운로드 탭으로 이동한 후, 중앙 좌측의 “새 모션 그룹 만들기”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion36.jpg)

2. 새 모션 그룹의 이름을 입력한 후 “확인”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion37.jpg)

3. 후보 모션 목록에서 그룹에 포함시킬 모션을 선택한 후 “모션 추가”버튼을 클릭합니다. 우측에 막대 그래프를 통해 실제 로봇의 저장공간을 얼마나 사용했는지 알 수 있습니다. “확인”버튼을 클릭하여 모션 그룹을 생성합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion38.jpg)

## [로봇에 다운로드하기](#로봇에-다운로드하기)

1. 모션 그룹 목록에서 로봇에 다운로드할 모션 그룹을 선택합니다. 우측의 저장 용량 그래프가 초과하지 않았는지 확인합니다.

    ![](/assets/images/sw/rplus2/motion/r+motion39.jpg)

2. “모션 그룹 다운로드”버튼을 클릭하여 로봇에 다운로드합니다. 화면 중앙에 다운로드 과정이 표기됩니다.

    ![](/assets/images/sw/rplus2/motion/r+motion40.jpg)

# [유용한 정보](#유용한-정보)

## [자유 형태 로봇 생성(사용자 로봇)](#자유-형태-로봇-생성-사용자-로봇)

1. 홈 탭을 클릭한 후 “새 프로젝트 만들기”버튼을 클릭합니다.
2. “자유 형태 로봇”탭에서 사용할 제어기를 선택한 후 “관절 추가”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/motion_15.gif)

3. 사용할 ID와 모터 종류를 선택한 후 “확인”버튼을 클릭하면 관절목록에 추가됩니다.

    ![](/assets/images/sw/rplus2/motion/motion_16.gif)

4. 이와 같이 사용할 모터 목록을 작성한 후 프로젝트를 생성하면 아래 그림과 같이 자유 형태 로봇이 생성됩니다.  
  자유 형태 로봇은 3D 로봇만으로 실제 로봇의 움직임을 유추하기 어려우나 연결된 실제 로봇의 움직임을 확인하며 모션 편집이 가능해집니다.

    ![](/assets/images/sw/rplus2/motion/motion_17.gif)

## [3D 로봇 변경](#3D-로봇-변경)

모션 파일은 최초 선택한 3D 로봇을 기준으로 작성됩니다. 모션 파일내의 데이터를 유지한 채로 3D 로봇을 변경해야 하는 경우 3D 로봇 변경 기능을 사용합니다.  
아래 설명은 “휴머노이드 A타입”을 “휴머노이드 C타입”으로 변경하는 예시로 진행됩니다.

1. 홈 탭으로 이동한 후, 좌측 메뉴 중 “3D 로봇”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/motion_18.gif)

2. 중앙 하단의 “3D 로봇 변경하기”버튼을 클릭하여 변경을 원하는 로봇을 선택한 후 확인버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/motion_19.gif)

3. 3D 로봇이 변경되면 아래와 같이 탭이 이동합니다.
4. 불필요한 관절이 있을 경우 해당 관절을 제거하는 것이 좋습니다. 다시 홈 탭의 “3D 로봇”메뉴로 이동합니다. (제거할 관절이 없다면 ⑤는 생략합니다.)

    ![](/assets/images/sw/rplus2/motion/motion_20.gif)

5. 선택한 후 좌측의 “관절 제거”버튼을 사용하여 제거합니다. 제거가 완료되면 우측 하단의 “적용하기”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/motion_21.gif)

6. 불필요한 관절이 모두 제거되었습니다.

    ![](/assets/images/sw/rplus2/motion/motion_22.gif)

## [포즈 미러링](#포즈-미러링)

3D 로봇의 각 관절은 아래 그림과 같이 중앙선을 기준으로 좌우 관절이 대칭으로 이루어져 미러링 기능을 사용할 수 있습니다. R+ Motion에서 제공하는 미러링 기능은 포즈 대칭과 포즈 교환이 있습니다.

  ![](/assets/images/sw/rplus2/motion/motion_23.gif)

**포즈 대칭(Pose Symmetry)**

1. 포즈 대칭을 실행하기 위해 기준 값이 대입되어있는 관절을 선택합니다.
2. “미러링”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/motion_24.gif)

3. 선택한 관절의 값이 대칭되는 관절에 대입되었음을 확인합니다.

    ![](/assets/images/sw/rplus2/motion/motion_25.gif)

**포즈 교환(Pose Exchange)**

1. 포즈 교환을 실행하기 위해 기준 값이 대입되어있는 관절과 대응되는 관절을 모두 선택합니다.
2. “미러링”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/motion_26.gif)

3. 선택한 관절의 값이 서로 교환되었음을 확인합니다.

    ![](/assets/images/sw/rplus2/motion/motion_27.gif)

## [모션 호출 번호 수정](#모션-호출-번호-수정)

모션 호출 번호는 로보플러스 태스크(Task)로 작성한 프로그램 코드에서 모션 데이터를 호출할 때 사용됩니다.
제어기에 다운로드한 모션 데이터의 호출번호와 태스크에서 사용한 호출번호가 일치하도록 입력해야 합니다.

1. “모션 다운로드”탭으로 이동한 후, 모션 호출 번호를 수정할 모션그룹을 선택하고 편집 버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/motion_28.gif)

2. 모션 그룹 내에 담긴 모션 중 수정하고 싶은 호출 번호나 종료 번호를 클릭합니다. 변경할 번호를 입력한 후 “Enter”키를 누릅니다.

    ![](/assets/images/sw/rplus2/motion/motion_29.gif)

3. 만약 입력한 번호가 중복되면 다음과 같은 확인 창이 활성화됩니다. 종료 번호의 경우 값을 넣지 않으면 임의로 할당됩니다.

    ![](/assets/images/sw/rplus2/motion/motion_30.gif)

## [모션 파일간 데이터 복사](#모션-파일간-데이터-복사)

1. 복사할 데이터가 담긴 모션 파일을 실행합니다.
2. “홈”탭의 “3D 로봇”탭으로 이동하여, “3D 로봇 변경” 버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/motion_31.gif)

3. 모션 파일의 3D 로봇을 확인한 후 “3D 로봇 변경하기”창을 닫습니다.

    ![](/assets/images/sw/rplus2/motion/motion_32.gif)

4. 모션 편집기를 하나 더 실행하여 방금 확인한 3D 로봇으로 빈 프로젝트를 생성합니다.

    ![](/assets/images/sw/rplus2/motion/motion_33.gif)

5. 모션 유닛 목록을 열어 복사할 대상을 선택한 후, 단축키 “Ctrl+C”를 실행합니다.

    ![](/assets/images/sw/rplus2/motion/motion_35.gif)

6. 빈 프로젝트가 실행된 모션 편집기에서 모션 유닛 목록을 열어 단축키 “Ctrl+V”를 실행합니다.

    ![](/assets/images/sw/rplus2/motion/motion_36.gif)

{% capture motion_01 %}
`모션 파일간 데이터 복사 시 주의사항`
- 복사가 가능한 데이터는 관절 값, 키-프레임, 모션 유닛, 모션입니다.
- 빈 프로젝트에 이미 같은 이름의 데이터가 존재한다면 복사되지 않습니다.
- 복사는 모션 유닛 -> 모션 순으로 진행해야 하며, 모션 유닛을 복사하지 않고 모션을 복사한다면 빈 모션으로 복사됩니다.
{% endcapture %}

<div class="notice-warning">{{ motion_01 | markdownify }}</div>

## [오프셋 편집](#오프셋-편집)

1. 홈 탭을 클릭한 후 오프셋 편집을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/motion_37.gif)  

2. 로봇을 연결합니다. (로봇 연결하기 참조)
3. 동기화 모드를 활성화 합니다.
4. 초기 포즈를 잡아준 후 로봇을 확인하며 오프셋 포즈를 편집합니다.

    ![](/assets/images/sw/rplus2/motion/motion_38.gif)

5. 실제 로봇이 초기 포즈와 같은 포즈를 잡을 때가 가장 이상적인 오프셋입니다.
6. 실제 로봇이 초기 포즈를 취한 3D 로봇과 같은 자세를 잡도록 오프셋을 천천히 조정합니다.
7. “오프셋 다운로드“버튼을 클릭하여 오프셋을 로봇 제어기에 저장합니다.

    ![](/assets/images/sw/rplus2/motion/motion_39.gif)

8. 초기 포즈와 오프셋 포즈간의 차이가 오프셋으로 적용됩니다. (오프셋 포즈 – 초기 포즈 = 오프셋)

## [구 버전 파일(*.mtn) 변환하기](#구-버전-파일-mtn-변환하기)

  ![](/assets/images/sw/rplus2/motion/motion_40.gif)

새로운 “로보플러스 모션2.0 (R+ Motion 2.0)”에서는 기존의 “로보플러스 모션1.0 (Roboplus Motion 1.0)” 에서 사용해오던 구 모션 파일(*.mtn)을 그대로 사용할 수 없습니다.   
구 모션 파일(*.mtn)을 새로운 모션 편집기에서 사용하려면 *.mtnx로 변환하는 과정을 거쳐야 합니다.*

`주의사항` mtn파일을 mtnx파일로 변환한 후에는 저장 용량 및 모션 호출번호가 변경될 수 있습니다. 변환이 완료된 후 모션 호출번호를 확인하여 다시 지정해주시기 바랍니다.
{: .notice--warning}

1. 로보플러스 모션을 실행합니다.

    ![](/assets/images/sw/rplus2/motion/motion_41.gif)

2. 로봇을 연결한 후 로봇 모션을 mtn파일로 저장하기 위해 “다른 이름으로 저장” 메뉴를 실행합니다.

    ![](/assets/images/sw/rplus2/motion/motion_42.gif)

3. 저장할 파일명을 입력한 후 “저장”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/motion_43.gif)

4. R+ Motion 2.0을 실행합니다. “프로젝트 열기”버튼을 클릭한 후 파일 확장자를 “mtn Files” 로 변경합니다.

    ![](/assets/images/sw/rplus2/motion/motion_44.gif)

5. 변환을 진행할 대상 mtn 파일을 선택한 후 “열기"버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/motion_45.gif)

6. 아래 그림과 같이 컨버팅 실행 메시지 창이 활성화되면 “확인”버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/motion_46.gif)

7. 모션 데이터를 사용할 3D 로봇을 선택한 후 확인 버튼을 클릭합니다.

    ![](/assets/images/sw/rplus2/motion/motion_47.gif)

8. 컨버팅이 완료되면 좌측 상단의 “모션 유닛 목록”을 클릭하여 제대로 변환되었는지 확인합니다.

    ![](/assets/images/sw/rplus2/motion/motion_48.gif)

9. 변환이 완료된 mtnx 파일을 저장합니다

    ![](/assets/images/sw/rplus2/motion/motion_49.gif)

## [3D 카메라 조작](#3D-카메라-조작)

1. 마우스 오른쪽 버튼을 클릭한 채 드래그하면 시점이 회전됩니다.

    ![](/assets/images/sw/rplus2/motion/motion_50.gif)

2. Home 키를 누르거나 마우스 휠 버튼을 앞으로 굴리면 시점이 확대됩니다.

    ![](/assets/images/sw/rplus2/motion/motion_52.gif)

3. End 키를 누르거나 마우스 휠 버튼을 뒤로 굴리면 시점이 축소됩니다.

    ![](/assets/images/sw/rplus2/motion/motion_51.gif)

4. Page Down 키를 누르면 시점이 내려갑니다. (시점이 내려감에 따라 로봇이 위로 올려져 보입니다.)

    ![](/assets/images/sw/rplus2/motion/motion_53.gif)

5. Page Up 키를 누르면 시점이 올라갑니다. (시점이 올라감에 따라 로봇이 아래로 내려져 보입니다.)

    ![](/assets/images/sw/rplus2/motion/motion_54.gif)

## [단축키](#단축키)

![](/assets/images/sw/rplus2/motion/motion_55.gif)

![](/assets/images/sw/rplus2/motion/motion_57.gif)

![](/assets/images/sw/rplus2/motion/motion_58.gif)

## [자주 묻는 질문](#자주-묻는-질문)

1. 지원 가능한 제품 군은?
  - 프리미엄, 스템, 스마트, 다윈미니
  - CM-200, CM-510, CM-530, CM-700, OpenCM9.04C, AX시리즈, MX시리즈, XL-320 로 구성된 로봇
  - TTL / RS485 통신 제품군 모두 사용 가능

2. 지원 가능한 3D 모델은?
  - 지원 제품 군 중에서 모션을 사용하는 예제 전체

3. 지원 가능한 관절의 개수는?
  - 다이나믹셀을 사용할 경우 최대 26개의 관절을 사용할 수 있으며, ID는 0~25번까지 사용가능
  - CM-200을 사용할 경우 최대 8개의 관절을 사용할 수 있으며 ID는 3~10번까지 사용가능

4. 예제 3D 모델 외의 로봇을 추가할 수 있나요?
  - 현재는 모터가 나열된 형태로만 제공하며, 추후 PC버전에서 R+ Design으로 조립한 로봇을 활용할 수 있도록 지원할 예정

5. MTN파일을 MTNX로 변환할 수 있나요?
  - E-Manual의 “구 버전 파일(.mtn) 변환하기” 페이지 참조

6. MTNX파일을 MTN으로 변환할 수 있나요?
  - 현재는 지원하지 않으며, 앞으로도 지원계획 없음

7. 모션 파일을 수정한 후 제대로 동작하지 않습니다. 어떻게 해야 하나요?
  - 모션 파일을 수정한 후 반드시 모션그룹을 다시 다운로드 해야 합니다.

8. 제어기가 잘 연결되지 않습니다. 어떻게 해야 하나요?
  - 제어기를 껐다 켠 후 다시 시도해보세요. (만약 사용하는 제어기가 CM-200이라면 제어기를 끈 후, 전원버튼을 2~3초 눌러서 태스크를 멈춘 후 시도해 보세요.)

9. 관절 그룹에서 가중치가 뭔가요?
  - 여러 관절의 각도 값을 각각 다른 배수로 조절할 때 사용하는 기능입니다.
  - 관절 그룹을 선택한 후 “차이 조정” 기능을 사용하면 가중치 만큼씩 값이 더해지게 됩니다.
  - 계산식 : 현재각도 = 이전각도 + (회전방향 x 가중치 x 클릭횟수)
  - 관절 그룹을 이용한 예시 영상
  - [http://youtu.be/a7vkf95Q1is?list=UUuHS2rd-R6LjKyw3yTKXObA]
