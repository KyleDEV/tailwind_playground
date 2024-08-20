# Tailwind CSS Basic Playground
본 레포지토리는 [Tailwind CSS](https://tailwindcss.com) 환경 셋업에 아직 익숙하지 않은 개발자와 비개발자들이 손쉽고 빠르게 웹페이지 UI 디자인을 시작 할 수 있도록 공유되었습니다.

아래의 안내에 따라 `public` 폴더의 `index.html`을 수정하여 곧바로 Tailwind CSS를 사용해 볼 수 있으며, 자신이 디자인한대로 빌드된 아웃풋 파일(`style.css`)을 실시간으로 획득할 수 있습니다.





## ● 사전 필요사항
### 1) Node.js & npm 
> npm : Node.js 패키지 매니저. Node.js 를 설치하면 함께 설치되는 터미널 명령어 프로그램.

 [Tailwind CSS(위키)](https://en.wikipedia.org/wiki/Tailwind_CSS) 는 Node.js 패키지로 빌드되는 Post-processed CSS이므로 빌드하기위해 컴퓨터에 `npm`이 설치되어 있어야 합니다. npm은 Node.js를 설치하면 함께 설치됩니다. [Node.js 웹사이트](https://nodejs.org/en/)의 안내에 따라 자신의 컴퓨터에 Node.js를 **전역적으로** 설치해주세요.

 ### 2) Visual Studio Code & 확장
 로컬 HTML 파일을 실행하기엔 웹브라우저만으로도 충분하지만, html파일을 저장 할 때마다 웹브라우저를 새로고침해야하는 불편함이 따를 것입니다. 반면, 로컬웹서버에서 해당파일을 실행시키면 실시간으로 웹페이지가 리로드 할 수 있어 미리보기가 편리하며, 같은 로컬네트워크의 모바일 기기에서도 웹페이지에 접속해 볼 수 있습니다.

 어떤 코드에디터와 로컬서버로도 사용가능하지만, `VS Code`에서 `Live Server` 확장을 이용하면 로컬웹서버를 실행해 곧바로 작업중인 `html`파일에 맞는 페이지를 실행시킬 수 있습니다.

먼저 VS Code가 없다면 [Visual Studio Code](https://code.visualstudio.com)를 자신의 컴퓨터에 다운로드하여 설치해주세요.

#### ♠ Live Server 확장 설치
다음으로는 VS Code에서 곧바로 로컬웹서버를 실행시킬 수 있는 `Live Server` 확장을 설치합니다.

또한 다음과정을 통해 설정을 미리하면 좋습니다.

![](./README_IMG/Live-Server-Setting.png)

* Full Reload 설정:
  * ![](./README_IMG/Live-Server-Setting-full-reload.png)

* Local IP 사용 설정
  * ![](./README_IMG/Live-Server-Setting-use-local-ip.png)
  * > 로컬 IP 사용으로하면 Live Server로 웹브라우저가 열릴 때 현재 네트워크의 로컬IP가 표시된 URL이 나옵니다. 이 주소로 모바일에서도 접속해 볼 수 있습니다.


#### ♠ Tailwind CSS Intellisense 
추가로, `Tailwind Labs`사의 `Tailwind CSS Intellisense` 확장을 설치하면 Tailwind CSS의 `class` 이름 자동완성 기능을 사용할 수 있습니다.

![](./README_IMG/Tailwind-CSS-IntelliSense.png)






## ● 레포지토리 다운로드 및 Tailwind CSS 설치
이 Github 레포지토리를 로컬에 다운로드 받아 압축을 풀고 나오는 폴더를 VS Code에서 엽니다.

### Tailwind CSS 모듈 설치
Tailwind CSS 모듈설치에 필요한 모든 것들은 이미 `package.json`에 명시되어있습니다. 

`VS Code`의 `Terminal` 창을 열고 (`Control`+`Shift`+`~` ) 아래 명령어를 입력해서 필요한 모듈을 설치합니다.

~~~
npm install
~~~
> 명령어 실행위치는 `package.json`파일이 위치한 레포지토리 폴더여야합니다. VS Code에서 레포지토리를 정상적으로 열었다면 해당 위치일 것입니다.







## ● 페이지 디자인 시작 및 실시간 미리보기

### 1) html 파일 열기
`public/index.html`을 열고 여기에서 웹페이지를 디자인할 수 있습니다. Tailwind CSS 아웃풋 파일은 아래와 같이 링크되어있습니다만 아직 최초 빌드 전에는 아직 파일이 존재하지 않습니다.

![](./README_IMG/stylesheet-output-file-link.png)

또한 다른 페이지가 추가로 필요하다면 `public` 폴더 하위에 `html`파일을 만들고 위와같이 `<head>`태그안에 아웃풋 파일을 링크해 사용해주세요.

### 2) 아웃풋 파일 실시간 자동 빌드 실행
Tailwind CSS는 html,js 파일에서 사용된 Tailwind CSS `class=""` 이름들에대해서만 출력파일을 만드는 Post-processed CSS 입니다. 현재 레포지토리는 `public`폴더에 있는 `.html`, `.js` 파일을 인식하도록 설정되어있습니다.

`VS Code`의 `Terminal` 창을 열고 (`Control`+`Shift`+`~` ) 다음명령어를 입력하세요. 
~~~
npm run tailwind
~~~
> 참고: 이 명령어는 Tailwind CSS 인풋파일에서 아웃풋파일을 만드는 긴 명령어를 편의를 위해 축약한 것이며, `package.json`의 `scripts`에 정의해둔 커스텀 `npm run` 명령어입니다.

이 명령어를 실행하면 아래처럼 실시간 프로세스가 실행되며 html 파일을 저장 할 때마다 자동으로 `public/style.css` 파일이 생성, 변경됩니다.

![](./README_IMG/tailwind-watch-in-terminal.png)

> 자동 빌드 실행을 중지하려면 터미널에서 `Control`+`C`키를 누르십시오.

### 3) Live Server로 로컬서버 실행해서 미리보기
현재 작업중이 `.html`파일에서 우클릭 메뉴로  `Live Server`를 열거나, VS Code 오른쪽 하단에 나오는 `Go Live` 버튼을 클릭하면 현재 작업폴더에 해당하는 로컬서버 주소로 실행됩니다.

![](./README_IMG/open-live-server-menu.png)
> 참고: VS Code에서 현재 작업중인 문서가 `.html`파일이 아니면 폴더 구조가 출력될 뿐입니다.

이제 `index.html` 파일을 수정하고 저장 할 때마다 열려있는 웹브라우저가 리로드됩니다.
