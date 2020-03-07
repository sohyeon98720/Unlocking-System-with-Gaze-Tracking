# Unlocking System with Gaze Tracking
# 시선 추적을 이용한 잠금 해제 시스템
[요약](#요약)  
[개발 기간](#개발-기간)  
[개발자](#개발자)  
[하드웨어 제작](#하드웨어-제작)  
[사용 프로그램](#사용-프로그램)  
[사용 기술](#사용-기술)  
[결과](#결과)

---
### 요약
- 카메라를 이용하여 실시간 동공 영상 촬영
- 모니터와 사용자 눈의 움직임간 동기화를 위한 캘리브레이션 과정 수행

- 사용자의 눈의 움직임에 따라 유니티에서 캐릭터의 눈이 움직임

- 아바타의 눈 움직임에 따라 비밀번호가 입력됨
---
### 개발 기간

- 2019/08/19 ~ 2019/09/11
---
### 개발자

- [김소현 (sohyeon98720)](https://github.com/sohyeon98720), 박현지, [이혜인(hyeinlee725)](https://github.com/hyeinlee725), [정민지(minji-o-j)](https://github.com/minji-o-j) 


--- 
### 하드웨어 제작
#### - 준비물
![image](https://user-images.githubusercontent.com/45448731/75803052-1aec8180-5dc1-11ea-9005-3a1a7a7de31d.png)


- 웹캠의 __적외선 차단 필름 제거__  
- __자외선 차단 필름을 넣음__  　    `<<선명한 동공 영상을 얻기 위해 적외선 영상을 만듦!`  
- 카메라 주위에 적외선 램프 고정
<br>

#### -완성품
![image](https://user-images.githubusercontent.com/45448731/75803296-92baac00-5dc1-11ea-95c0-182f2be12af5.png)
- 3D 프린팅을 이용하여 카메라 케이스를 제작하였다.
---

### 사용 프로그램

-  __CL-Eye Test__: 안경에 부착된 카메라를 통해 눈 영상 촬영

-  __OpenCV__: 동공 추출, 시선 추적, Calibration

-  __Unity__: 프로그램 제작, 아바타의 눈 움직이게끔 함

-  __Visual Studio__: 프로그래밍, 시선 관련 데이터 처리

---
### 사용 기술
#### -동공 추출
- HoughCircles 함수를 이용하여 원을 찾음  
- 찾을 수 있는 원의 최소 반지름, 최대 반지름, 원 사이의 거리를 조절하여 동공 하나만 추출하도록 함

    ![image](https://user-images.githubusercontent.com/45448731/75806335-cb10b900-5dc6-11ea-8a4e-0ba68616577a.png)
- __Circle 함수를 이용해 동공에 원을 그리고, 그 중심좌표를 찾음__
<br>

#### -캘리브레이션
![image](https://user-images.githubusercontent.com/45448731/75952876-55563b80-5ef3-11ea-9194-05cfbc111283.png)
- '눈이 화면을 보고 있다'라고 인식하게끔 하기 위해 필요한 과정.
- __화면과 사용자 간의 거리가 항상 일정하지 않기 때문에__ 이 과정이 필요하다.  
<br>

![image](https://user-images.githubusercontent.com/45448731/75953050-c4339480-5ef3-11ea-95eb-984fdabf579e.png)  
→캘리브레이션 과정
1. 왼쪽 위, 오른쪽 아래를 볼 때의 동공의 중심 좌표를 찾는다.
2. 두 점을 기준으로 9개 점의 좌표를 계산한다.
3. 패턴 입력 화면에서 전체 화면을 9개의 영역으로 나누어 점의 좌표와 연관시킨다.

---
### 결과

- 메인 화면  
![image](https://user-images.githubusercontent.com/45448731/76137002-5d40e780-607b-11ea-9bfe-c3b7c7bd50fc.png)
<br>

- 개발자 보기  
![image](https://user-images.githubusercontent.com/45448731/76137003-603bd800-607b-11ea-8662-4368fe8b5f24.png)
<br>

#### 잠금 설정시  
- 캘리브레이션  
![image](https://user-images.githubusercontent.com/45448731/76137035-aee97200-607b-11ea-9d4a-828f16d0a0b3.png)
    - 왼쪽 위, 오른쪽 아래를 일정 프레임씩 보게 함으로써 화면을 보는 눈의 위치를 파악한다.  
<br>

- 비밀번호 등록하기  
![image](https://user-images.githubusercontent.com/45448731/76137062-11db0900-607c-11ea-895f-6731286e769d.png)  
![image](https://user-images.githubusercontent.com/45448731/76137081-3fc04d80-607c-11ea-9e83-8625c66f02d8.png)  
    -`등록`단계에서 비밀번호를 입력하면 
<br>
- 입력한 비밀번호 확인하기  
![image](https://user-images.githubusercontent.com/45448731/76137039-bb6dca80-607b-11ea-89c1-f4065723c220.png)

