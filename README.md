# 1. 프로젝트 개요
----------------------------------------------------------------
### 1.1 개발배경 및 프로젝트 목적 <br>
학교 공강 시간에 학우들과 PC방에 갈 때 마다 자리가 없는 것을 보고 굉장한 불편함을 느껴 저희는 안드로이드 앱과 주변 PC방들의 DB를 연동하여 실시간으로 좌석현황을 확인하고 위치 또한 알 수 있고, 스마트폰으로 결제까지 할 수 있는 앱인 POCKET_PC라는 앱을 개발하게 되었습니다.

### 1.2 부분별 수행 업무 및 담당자 <br>
|소속|성명|업무내용|
|------|---|---|
|      |진승오|프로젝트 총괄, 산출물 제작 및 검토|
| 3-C  |송창범|UI 구성 및 기능 구현, APP코딩|
|      |이성재|데이터 베이스 구축 및 서버연동, 기능 구현| <br>

### 1.3 프로젝트 개발 범위 <br>
본 어플리케이션 개발 프로젝트는 안드로이드 OS 기반 스마트폰에서 구현이 되어 있으며 초기 의도에서 거듭된 회의를 통해 몇 가지 기능을 추가로 구현하였습니다. 

# 2. 요구사항 정의
----------------------------------------------------------------
### 2.1 목적
본 항목은 기능적 요구사항, 비기능적 요구사항 등을 담고 있으며, 사용자 요구사항을 정의하기 위해 작성되었습니다. <br>
기능적 요구사항은 사용자의 요구사항을 구현하는데 필요한 주요기능을 정의하며, 비기능적 요구사항은 사용자가 직접 사용하지는 않지만 시스템의 
안정적인 개발과 운영을 내부적으로 구현되어야 하는 기능을 정의합니다.

### 2.2 기능적 요구사항
#### 2.2.1 Intro
해당 어플리케이션이 구동되면 로딩시간동안 나타나는 화면으로 어플리케이션 이름과 로고가 출력되게 합니다.

#### 2.2.2 Login-인트로가 끝나면 로그인 창이 나타납니다.
계정이 없을 시 회원가입 후 로그인을 할 수 있습니다. <br>
만약 비밀번호나 아이디를 잃어버렸다면 아이디/비밀번호 찾기를 통해 찾을 수 있습니다. <br>

#### 2.2.3 MainActivity
로딩이 지나간 후 메인메뉴 버튼과 앱 로고 및 공지사항과 PC방 목록 바로기가 나옵니다. <br>
메인메뉴 버튼은 4가지의 메뉴(공지사항, 버전정보, 계정정보, PC앱 설명서)를 보여줍니다. <br>
공지사항은 메인메뉴안에 있는 공지사항을 조그맣게 가져와 로고밑에 배치되어 있습니다. <br>
PC방 목록 바로가기는 누르면 PC방 목록으로 넘어갑니다. <br>

#### 2.2.4 PC방 List
피시방 DB와 연동하여 PC방 목록을 보여줍니다. <br>
피시방 클릭시 연동한 PC방에 대한 자리현황과 정보를 알 수 있는 창으로 넘어갑니다. <br>
지역별로 피시방 목록을 분류할 수 있습니다. <br>

##### 2.2.4-1 PC방
피시방에 대한 간단한 정보와 위치, 요금제, 실시간 자리현황을 알 수 있습니다. <br>
결재하기 버튼을 누르면 결재하기로 넘어갑니다. <br>

##### 2.2.4-2 결제
피시방별 요금제를 파악하여 해당 피시방의 요금제에 맞게 결제를 할 수 있습니다. <br>
결재시에는 카카오페이를 이용합니다. <br>

#### 2.2.5 버전정보
현재 앱의 버전 정보를 나타냅니다. <br>

#### 2.2.6 공지사항
앱 업데이트시 수정 사항과 알려야할 공지에 대한 게시판 <br>

#### 2.2.7 Pocket PC앱 설명
앱 사용에 대한 간단한 가이드 <br>

#### 2.2.8 계정정보
해당 계정에 대한 계정 정보(아이디, 비번, 가입시 입력했던 정보)를 보여줍니다.
계정정보에서 아이디 및 비밀번호, 개인정보를 변경할 수 있습니다.

### 2.3 비기능적 요구사항
#### 2.3.1 시스템 제약조건
스마트폰에서 GPS기능을 활용할 수 있는 상태여야 합니다.
DB연동을 위한 서버가 가동중이어야 합니다.

#### 2.3.2 유지보수성
각 기능은 모듈화 되어 향후 업데이트가 유용해야 합니다.
코드 오류가 발생할 때 쉽게 찾아서 고치기가 가능해야 합니다.

#### 2.3.3 신뢰성
GPS 기능 활용 시, 사용자의 현 위치가 제대로 반영되어야 합니다.
해당 PC방에 대한 정보(요금, 좌석현황 등)가 정확하고 오류가 없어야 합니다.

#### 2.3.4 안정성
어플리케이션의 오류가 스마트폰이나 안드로이드 OS에 영향을 끼쳐선 안된다.

#### 2.3.5 보안성
개인정보 보호를 위하여 최소한의 정보만 사용자에게 요구한다.

## 3. 시스템 구조
----------------------------------------------------------------
### 3.1 목적
본 항목은 Pocket Pc를 구성하는 각 구성요소들을 분류하고 각 요소들 사이의 상호 관계에 대해 설명합니다.

### 3.2 시스템 구조
#### 시나리오 흐름도
![noname01](https://user-images.githubusercontent.com/33046341/65528342-247adf00-df2f-11e9-8b5c-f5c1c330956e.png)
### 3.3 플로우 차트
#### 순서도
![순서도](https://user-images.githubusercontent.com/33046341/65528324-1d53d100-df2f-11e9-8555-8375b70a04a0.png)

## 4. 요구사항 명세
------------------------------------------------------------------
### 4.1 목적
이 문서는 기능적 요구사항, 비기능적 요구사항 등을 담고 있으며 시스템 요구사항을 정의하기 위해 작성 되었습니다. 기능적 요구사항은 시스템의 요구사항을 구현하는데 필요한 주요기능을  정의하며, 비기능적 요구사항은 시스템의 안정적인 
개발과 운영을 위하여 내부적으로 구현되어야 하는 기능을 정의합니다.

### 4.2 기능적 요구사항 명세

#### 4.2.1 Loding
![image](https://user-images.githubusercontent.com/33046341/65529023-5e98b080-df30-11e9-98e4-355a3df5d74e.png)

#### 4.4.2 Login
![image](https://user-images.githubusercontent.com/33046341/65529061-6ce6cc80-df30-11e9-8416-831a9fc8b6c5.png)

#### 4.2.3 MainActivity
![image](https://user-images.githubusercontent.com/33046341/65529102-7a03bb80-df30-11e9-97bc-49b29c04a3ab.png)

#### 4.2.4 PC방 List
![image](https://user-images.githubusercontent.com/33046341/65529127-8851d780-df30-11e9-9b7f-a84c371171d8.png)

#### 4.2.5 PC방
![image](https://user-images.githubusercontent.com/33046341/65529148-93a50300-df30-11e9-8ba9-a25dfbfa14f4.png)

#### 4.2.6 결재
![image](https://user-images.githubusercontent.com/33046341/65529183-a15a8880-df30-11e9-9e35-317d71313b5d.png)

#### 4.2.7 버전정보
![image](https://user-images.githubusercontent.com/33046341/65529200-a9b2c380-df30-11e9-8a58-048987dee627.png)

#### 4.2.8 공지사항
![image](https://user-images.githubusercontent.com/33046341/65529222-b46d5880-df30-11e9-8da5-6f2733b5483e.png)

#### 4.2.9 Pocket PC 앱 설명
![image](https://user-images.githubusercontent.com/33046341/65529249-c2bb7480-df30-11e9-9c5c-4c2e81273ded.png)

#### 4.2.10 계정정보
![image](https://user-images.githubusercontent.com/33046341/65529278-cd760980-df30-11e9-8374-be88ae9a8602.png)

## 4.3 비기능적 요구사항 명세
#### 4.3.1 시스템 제약조건
![image](https://user-images.githubusercontent.com/33046341/65529315-debf1600-df30-11e9-8e98-4c35a6d06d93.png)

#### 4.3.2 유지보수성
![image](https://user-images.githubusercontent.com/33046341/65529332-e8e11480-df30-11e9-816f-3157653717f7.png)

#### 4.3.3 신뢰성
![image](https://user-images.githubusercontent.com/33046341/65529368-f72f3080-df30-11e9-832e-be1c405b0fde.png)

#### 4.3.4 오작동 방지
![image](https://user-images.githubusercontent.com/33046341/65529408-fe563e80-df30-11e9-994b-f4840d76095a.png)

#### 4.3.5 안정성
![image](https://user-images.githubusercontent.com/33046341/65529433-0b732d80-df31-11e9-87b9-25467708a1c8.png)

#### 4.3.6 보안성
![image](https://user-images.githubusercontent.com/33046341/65529518-38274500-df31-11e9-9bfd-c122758f433f.png)

# 5. 시스템 모델
--------------------------------------------------------------------------------
## 5.1 목적
본 항목은 시스템 컴포넌트간의 관계, 시스템과 시스템 환경과의 관계를 보여주는 시스템 모델을 보여줍니다. 이 부분에서 어떤 모델을 사용하여 시스템의 디자인을 할 것인지를 보여줍니다. UML을 사용하여 개략적인 모델 형태를 나타냅니다. <br>

## 5.2 Use-case Diagram 
사용자의 입장에서 본 시스템의 행동 <br>
![image](https://user-images.githubusercontent.com/33046341/65529587-5e4ce500-df31-11e9-89b6-96488094249e.png)

## 5.3 Process modeling 
시스템과 시스템 환경과의 프로세스 행동 <br>
![image](https://user-images.githubusercontent.com/33046341/65529616-6b69d400-df31-11e9-94a1-5e9ef01c053b.png)

## 5.4 Database Logical modeling
데이터베이스의 논리적 설계 <br>
![image](https://user-images.githubusercontent.com/33046341/65529634-745aa580-df31-11e9-841b-11a819197c43.png)

# 6. 부록
---------------------------------------------------------------------
## 7.1 사용자 인터페이스 UI
![image](https://user-images.githubusercontent.com/33046341/65529694-96542800-df31-11e9-9f1d-7e2b2e75a7e5.png)
![image](https://user-images.githubusercontent.com/33046341/65529699-981deb80-df31-11e9-85d6-18b93c307bc9.png)

## 7.2 일정
![image](https://user-images.githubusercontent.com/33046341/65529731-a53ada80-df31-11e9-8ced-4ae1d9243c0d.png)

# 8. 소스코드 Structure
-----------------------------------------------------------------------
![image](https://user-images.githubusercontent.com/33046341/65529768-b2f06000-df31-11e9-9b70-fa0182bda1af.png)
![image](https://user-images.githubusercontent.com/33046341/65529772-b4ba2380-df31-11e9-8fc0-0d33d5ea5f95.png)
![image](https://user-images.githubusercontent.com/33046341/65529775-b5eb5080-df31-11e9-9280-d86837277f1c.png)
![image](https://user-images.githubusercontent.com/33046341/65529782-b84daa80-df31-11e9-94f3-ecbda50a6ac0.png)
