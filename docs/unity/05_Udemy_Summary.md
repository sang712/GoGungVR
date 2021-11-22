# Udemy 특강

## Introduction

- 강사 소개 및 배울 내용 소개
- Section 별 내용 소개

Through this section, we will learn how to develop VR experiences with Unity's XR Interaction Toolkit with fun thanks to Quidditch VR game assets. This section will also help you set up your VR project with the latest Unity version and latest VR tech such as OpenXR, a standard that will let us develop cross-platform VR apps/games.

In this section, we will cover the topics below =>

- Setting up a Unity project for the latest VR development SDKs.
- Importing Game Assets
- Configuring/Optimizing your VR project for Oculus Quest 2.
- Unity's new input system and setting up Device-based XR Rig.
- Installing external apps to Quest 2.
- Oculus Link setup

## 3-18. Introduction to Section

- Oculus Integration 을 이용해 VR 실습을 할 수 있다.
- 해리포터에 나오는 퀴티치 경기를 게임으로 만드는 Quidditch VR
- 게임을 진행하는 UI를 만들 수 있다.

## 3-19. Installing Unity and Creating The First Oculus Quest Project

- Unity Hub 설치 및 프로젝트 버전 설치
- 프로젝트 생성 - MyFirstOculusQUESTProject

## 3-20. Importing Oculus Integration and Game Assets

- Oculus integration 임포트
- Game Assets 다운로드 & 임포트
- Scene 에 놓여 있는 Broomstick 살펴보기

## 3-21. OVRCameraRig: Basic Unity Scene Setup For Oculus Quest

- GameScene 을 OVRCameraRigScene 의 이름으로 따로 저장
- OVRCameraRig import and Delete Camera
- OVRCameraRig is the first component to be added to view the scene in VR.

## 3-22. Building Your First Oculus Quest Unity Project

- Build Settings → Android 플랫폼으로 Switch platform
- Player Settings → Install XR Plug-in Management → check the Oculus
- XR Plug-in Management 하위의 Oculus 에 settings file 생성을 위해 Create 클릭 → Quest 2 check 확인
- Player 메뉴에서 Other Settings 의 Graphics APIS 를 OpenGLES3 로 변경, Color Space 는 Linear 로 변경
- PackageName 을 com.ssafy.firstoculusquestproject 로 변경
- Minimum API Level is 23
- Building Settings → Texture Compression : ASTC 로 변경
- Build 후 apk 파일 다운로드

## 3-24. Installing apk Files To The Quest With ADB

- apk 빌드 성공 후 두 가지 방법으로 Quest 에 apk 파일을 업로드 할 수 있다.
- Side-Quest 활용은 다음 강의, 이번엔 조금 더 어려운 방법 - Unity Dashboard 사용
- 생략 후 다음 강의 go

## 3-25. Installing apk Files To The Quest With Side-Quest

- 쉽게 apk 파일을 Quest 에 업로드 하는 방법
- Side Quest Download
- PC 에 Oculus Quest 연결
- Side Quest 에서 무료 게임 다운로드 및 내 apk 파일 업로드

## 3-26. Adding Local VR Player And Movement With Joystick

- Scene 을 다른이름으로 저장 - OVRPlayerControllerScene
- OVRCameraRig 삭제 후 OVRPlayerController Drag & Drop
- Broomstick scale 1,1,1 로 설정
- STADIUM PLAY AREA 에 Box Collider component 추가 및 scale 설정 (100, 0.01, 250)
- Player 를 Broomstick 앞에 위치 시키고 땅에 설 수 있도록 위치 시킨다.
- Scene 저장 및 Build Settings 에서 Add Open Scene, Run Device 는 Oculus Quest 2
- Player Settings 에서 Product Name은 OVRPlayerControllerDemo 로 변경
- Build and Run 클릭 → ovrplayercontrollerdemo.apk 로 이름 설정, Oculus Quest 2 기기 내에서 app 실행됨 → 왼쪽 조이스틱으로 이동, 오른쪽 조이스틱으로 방향 변경 가능
- Unity로 돌아와 OVRPlayerController → OVRCameraRig 에서 Tracking Origin Type 을 Floor Level 로 변경 후 다시 Build and Run

## 3-27. Oculus Local Avatar

- OculusLocalAvatarScene 으로 Scene Name 변경 후 LocalAvatar 검색하여 Drag & Drop into TrackingSpace
- LocalAvatar 의 Ovr Avatar Component 의 Show Third Person 체크 확인!!
- Rotation 0, 180, 0 확인!! Position 0, 0, 1.5
- Scene 저장 후 Build & Run 으로 확인, oculuslocalavatardemo.apk
- 내 앞에 3D Avatar 가 보이면 다시 Unity 로 돌아와 Ovr Avatar Component 의 Visibility 속성에서 Start With Controllers 체크 확인!! → Show Third Person 체크 해제!! → Position 과 Rotation 을 0, 0, 0 으로 설정 → Save Scene → Build and Run → 내 손이 컨트롤러와 함께 보인다.

## 3-28. Oculus Controllers And Custom Hands

- Scene Name 을 OculusControllersAndCustomHands 로 변경 후 LocalAvatar Object 체크 해제
- LeftHandAnchor 하위 오브젝트로 3D Cube 생성
- Cube 의 Scale 을 Player 와 맞추기 위해 0.1 로 설정 후 RightHandAnchor 에 복사 붙여넣기!!
- Cube 의 Position 이 0, 0, 0 임을 확인하고 Save Scene, Build and Run !!
- Cube 들이 Controller 를 잘 Tracking 해 따라온다면 이제 Cube 들은 제거하고 OculusTouch 를 검색하여 Drag & Drop (OculusTouchForQuest2_Right or Left)
- 각각을 Left 또는 RightControllerAnchor 의 하위 오브젝트로 위치시킨다. 그리고 Posiotion 을 0, 0, 0 으로 설정해준다. Build and Run 으로 Test!!
- 작 동작 한다면 CustomHand 를 입혀보자. Assets 에서 검색 후 import, 이때 RightControllerAnchor 와 동일한 위치에 import 한다. (CustomHandRight or Left)
- OculusTouchForQuest2 는 체크 해제 후 보이지 않게 설정
- CustomHandRight and Left 는 Position 초기화 0,0,0 설정 Build and Run 으로 Test!!
- Unity 로 돌아와 CustomHand 를 클릭해보면 Inspector 에서 Rigidbody 와 OVR Grabber Script Component 를 확인할 수 있다. → 나중에 다룬다.
- CustomHandRight → Offset → r_hand_skeletal_lowres → hands:hands_geom → hands:Rhand 의 Inspector 에서 Skinned Mesh Renderer Component 살펴보기
  - Materials 의 Element 0 가 Hands_solid 로 되어있는데 클릭해보면 손의 색깔을 바꿀 수 있고, Hands_solid 의 Metallic 조절을 통해 손의 느낌을 armor 로 변경할 수 있다.

## 3-29. Basic Teleportation

- Scene Name 을 BasicTeleportationScene 로 변경
- OVRPlayerController 삭제 후 GameObject 생성을 위해 Create Empty 후 VRPlayerController 로 이름 변경
- VRPlayerController 에 Rigidbody, Capsule Collider component 추가
- Capsule Collider Component 에서 Radius 를 0.35, Height 을 2로 설정
- Rigidbody 의 Constraints 의 Freeze Rotaton X,Y,Z 모두 체크
- 그 후 VRPlayerController 하위에 OVRCameraRig 추가 및 Floor Level 로 변경, Position 0,0,0
- VRPlayerController에 Sile Capsule With Stick Movement (Script) 추가 - teleportation 사용을 위해 추가 → CameraRig 자리에 OVRCameraRig Drag & Drop 으로 추가, Speed 4로 설정
- VRPlayerController 에 Character Camera Constraint (Script) 추가 → Camera Rig 에 OVRCameraRig Drag & Drop 으로 추가, Preferred Height 2로 설정
- Save and Build and Run (Scene 선택 잘 하기, Product Name 잘 쓰기, apk 파일 이름 잘 쓰기)

------

- Unity 로 돌아와 VRPlayerController 하위에 Create Empty and 이름을 LocomotionController 로 변경 후, Locomotion Controller Component, Locomotion Teleport Component 추가
- Locomotion Controller 의 CameraRig 에 OVRCameraRig 드래그, Character Controller 에 VRPlayerController 드래그, Player Controller 에 VRPlayerController 드래그
- Locomotion Teleport 의 Teleport Destination Prefab 에 TeleportDestination 검색 후 드래그 앤 드랍
- Teleport Input Handler Touch Component 추가 후 Input Mode 를 Thumbstick Teleport 로 변경 → Aim Button 과 Teleport Button 을 L Thumbstick 으로 설정 → Aiming Controller 는 L Touch 로 설정
- Teleport Aim Visual Laser Component 추가 → Teleport Laser 검색 후 Laser Prefab 에 드래그 앤 드랍
- Layer 만들기 : TeleportLayer
- Teleport Target Handler Physical Component 추가 → Layer 설정 : Aim Collision Layer Mask 속성에 TeleportLayer 설정
- *STADIUM PLAY AREA 의  Layer 를 TeleportLayer 로 변경*
- Locomotion Teleport 의 Teleport Destination Layer 에 8번 Layer 등록
- Teleport Aim Handler Laser Component 추가
- Teleport Orientation Handler Thumbstick Component 추가 → Thumbstick 을 R Touch 로 변경
- Teleport Transition Instant Component 추가
- Oculus Touch For QuestAndRiftS_Left 를 LeftControllerAnchor 하위에 넣자
- Locomotion Teleport Component 의 Enable Movement During Pre Teleport & Aim 을 체크 해제, Enable Rotation During Aim, Pre Teleport 의 체크 해재
- Save Scene, Build and Run

## 3-30. Grabbing Objects

- Scene Name 을 BasicGrabbingScene 으로 변경

- VRPlayerController 삭제

- OVRPlayerController import and 위치 조정, OVRCameraRig 의 Floor Level 설정

- OVRPlayerController 의 Character Controller 의 Radius 0.25 로 설정

- CustomHand(왼,오) import - Left,RightHandAnchor 하위에 import, reset position

- Customhand 에 있는 Capsule Collider 확인 가능, 이는 오브젝트와의 상호작용을 위해 존재한다.

- Customhand 의 OVRGrabber Script open (그냥 살펴보기)

- BroomStick 에 

  Rigidbody

   추가, 

  OVR Grabbable

   추가, grab point 지정 가능

  - BroomStick 하위에 작은 sphere 추가 = 손잡이가 된다.
  - BroomStick Grab Points 의 Size 는 1, Element 0 는 생성한 Sphere 드래그 앤 드롭
  - Rigidbody 의 Use Gravity 체크 해제, Is Kinematic 체크

- Save the Scene 후 Scene 체크, Product Name = BasicGrabbingDemo, Build And Run, basicgrabbing.apk 빌드

- 이때 오브젝트를 잡으면 뒤로 밀리는 현상이 발생하는데,

  - The reason for this is that when we grab the object, we try to update its transform with the grabber hand transform in every physics update.
  - Also, since it is a Rigidbody, it collides with the OVRPlayerController's collider and pushes it back.
  - The fix is very simple. Just check Parent Held Object toggle.
  - CustomHandLeft and Right 의 OVR Grabber Component 의 Parent Held Object 체크!!
  - This will make the grabbed object a child of the grabber hand.

- Save and Build and Run

- 다른 Grab Point 를 설정하기 위해 Sphere 복제, BroomStick 에 알맞게 위치 조정

  - BroomStick 의 OVR Grabbable 의 Grab Points Size 는 2, Element 1 에 Sphere 드래그 앤 드롭
  - Allow Offhand Grab 이 체크되어 있으면 I will be able to grab the broomstick while already holding it with my other hand.

- Save and Build and Run

- 다른 오브젝트도 import 후 잡아보자

- Assets > Prefabs 의 BeaterBat and Bludger import

  - Bludger 에 Rigidbody 추가, Mass 를 0.25 로 설정
  - Sphere Collider 추가, OVR Grabbable 추가 및 Grab Points Size 는 1, Element 0 에는 Bludger 드래그 앤 드롭
  - BeaterBat 에 Rigidbody 추가, Box Collider 추가, OVR Grabbable 추가
  - Grab Points 에 Size 1, Element 0 에 BeaterBat 드래그 앤 드롭

- Save and Build and Run