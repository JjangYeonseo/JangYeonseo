자기소개 웹사이트 만들기
-

아주 간단한 자기소개 사이트를 만들어 보았습니다. <br>
짧은 글과 함께 동영상, 사진, 링크를 첨부하는 기본적인 구조로 작성하였습니다. <br>
기능 및 디자인은 차차 보완하는 걸로,,,

[자기소개 사이트 바로가기 ->] <br>
https://jjangyeonseo.github.io/JangYeonseo/ <br>


고충
-

index.html은 내 로컬 파일에 저장되어 있어서 링크 바로가기 첨부 불가능 <br>
-> 문제 해결을 위해 깃허브 내에서 url 생성하여 첨부하는 방식 선택 <br>
-> 이렇게 했더니, 로컬 파일의 index.html에서는 잘 열리던 사진과 동영상이 깃허브 내 url에서는 제대로 나오지 않음 <br>

해결방안
-

로컬 파일과 GitHub Pages에서 이미지 경로가 다르게 동작하는 것을 이해해야 함 <br>

상대 경로 vs 절대 경로
-

1. 상대 경로는 현재 파일의 위치를 기준으로 다른 파일의 위치를 지정하는 방식 <br>
./images/Jjanggu.jpg는 현재 파일이 위치한 디렉토리에서 images 폴더 안의 Jjanggu.jpg 파일 가리킴 <br>

2. 절대 경로는 사이트의 루트(최상위 디렉토리)를 기준으로 파일의 위치를 지정 <br>
/images/Jjanggu.jpg는 사이트의 루트에서 시작하는 경로를 의미함 <br>

로컬 파일 vs GitHub Pages
-

1. 로컬 환경에서 ./images/Jjanggu.jpg와 같은 상대 경로는, 파일이 있는 위치를 기준으로 이미지 찾음 <br>
이 경우, index.html 파일과 images 폴더가 같은 디렉토리 내에 있다면 제대로 작동함

2. GitHub Pages는 프로젝트의 최상위 디렉토리(즉, 리포지토리의 루트)를 기준으로 상대 경로를 해석하는 경향이 있음 <br>
따라서 ./images/Jjanggu.jpg 경로를 사용할 때, images 폴더가 index.html 파일과 동일한 디렉토리 안에 있어야만 이미지가 제대로 로드됨 <br>

결론
-

1. 내 로컬 환경에서 ./images/Jjanggu.jpg가 잘 작동한 이유는, 로컬 환경에서는 파일 구조에 따라 정확하게 상대 경로가 해석됐기 때문 <br>
2. 그러나 GitHub Pages에서는 URL이 상대 경로를 다르게 해석하기 때문에, /images/Jjanggu.jpg 또는 Jjanggu.jpg로 지정할 때만 올바르게 동작함 <br>
3. 최상위 디렉토리에서 접근하는 경우, GitHub Pages에서 상대 경로가 제대로 해석되지 않으면, 파일의 위치를 기준으로 단순화된 경로를 사용하는 게 좋음 <br>
4. Jjanggu.jpg로 이미지를 불러오는 경우, index.html 파일과 이미지 파일이 동일한 디렉토리에 있을 때는 이미지가 제대로 표시됨 <br>
-> index.html 파일과 리소스 파일들(이미지, 비디오 등)을 동일한 디렉토리에 두거나, 리소스 폴더의 위치에 맞춰 절대 경로를 사용하면 더 안정적인 결과 얻을 수 있음!
