# Flutter 실행 가이드
## 개발 환경 세팅

1. flutter 설치: flutter 홈페이지에서 직접 다운받아도 되지만, 니꼬가 추천해준대로 homebrew를 이용해 설치했다. ⇒  `brew install —cask flutter`
2. xcode, android studio 등 모바일 앱 개발에 필요한 시뮬레이터 설치
    
    xcode는 설치 후 `sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer` 커맨드를 터미널에 입력해 run시켜준다.
    
3. `flutter doctor` 커맨드를 이용하면 개발에 필요한 설정이 완료되었는지를 알 수 있다.
    ![flutter_doctor](https://github.com/Dumibell/flutter-basic-tutorial/assets/100185602/aa3dbec3-f23b-4535-be79-3ac6c0ddd15f)



## 실행

1. `flutter create [프로젝트명]` : 원하는 경로에 flutter 프로젝트를 생성한다.
2. vscode를 사용한다면 유용한 extenstion들이 있다. debugging에 엄청 도움됨.
    ![vscode_extension_dart](https://github.com/Dumibell/flutter-basic-tutorial/assets/100185602/c995cb7e-328a-4aa9-b6d6-39d8144c5004)
![vscode_extenstion_flutter](https://github.com/Dumibell/flutter-basic-tutorial/assets/100185602/ef99f292-08bc-44ef-a251-5919193fd88f)


    
    두 확장자를 설치해준다. 
    
3. vscode에서 원하는 시뮬레이터를 선택하고 debugger 아이콘을 클릭하면 해당 시뮬레이터에서 flutter가 실행된다. (이 때 에러가 난다면 `flutter clean` 후 `flutter run`으로 다시 실행시켜보자.)
4. 맨 왼쪽에 있는 돋보기 아이콘 누르면 widget inspector가 실행됨. 그럼 웹개발 할 때 크롬 개발자도구처럼 활용 가능~
![debugger](https://github.com/Dumibell/flutter-basic-tutorial/assets/100185602/5e63a369-28c1-4e87-8970-a638901f34a8)



1. dart에는 constant가 존재하는데, constant는 수정할 수 없고 compile 전에 그 value를 알 수 있는 변수이다. 따라서 complier가 최적화하는 데 도움이 됨. 여기서 몇몇 위젯은 constant이기 때문에 앞에 const를 붙여줘야함.
    
    vscode의 settings.json 파일을 열어서 아래의 코드를 추가해준다.
   ```json
   "editor.codeActionsOnSave": {
    "source.fixAll": true // 저장할 때마다 자동으로 고쳐줌(ex. const가 자동으로 붙음)
    },
    "dart.previewFlutterUiGuides": true, // 부모 자식 관계를 쉽게 확인할 수 있는 가이드라인 표시
   ```
