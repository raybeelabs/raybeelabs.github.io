# AdMob app-ads.txt 설정 작업 정리

## 작업 배경

Google AdMob에서 **Fruit Spinner** 앱의 `app-ads.txt` 파일을 찾을 수 없다는 경고가 표시됨.
AdMob이 광고 인벤토리의 정당한 판매자임을 인증하려면 개발자 웹사이트에 `app-ads.txt` 파일이 있어야 함.

---

## app-ads.txt란?

- 광고 인벤토리를 판매하도록 **승인된 광고 소스**를 광고주가 식별할 수 있게 해주는 텍스트 파일
- - 개발자 웹사이트의 루트 경로에 위치해야 함 (예: `https://example.com/app-ads.txt`)
  - - Google Play 콘솔에 등록된 **개발자 웹사이트 URL**과 반드시 일치해야 함
   
    - ---

    ## 문제 상황

    - 기존에 운영 중인 개발자 웹사이트 없음
    - - app-ads.txt 파일을 올릴 곳이 없는 상태
     
      - ---

      ## 해결 방법: GitHub Pages 활용

      웹사이트가 없어도 **GitHub Pages**를 이용해 무료로 정적 웹사이트를 만들고 app-ads.txt를 호스팅할 수 있음.

      ---

      ## 진행한 작업 순서

      ### 1단계: GitHub 계정 생성
      - GitHub 계정 생성: `raybeelabs`
      - - GitHub 계정 이메일은 AdMob/Play 콘솔과 무관하게 아무 이메일로 생성 가능
       
        - ### 2단계: GitHub Pages 저장소 생성
        - - 저장소 이름을 반드시 `[사용자명].github.io` 형식으로 생성해야 GitHub Pages가 자동 활성화됨
          - - 생성한 저장소: `raybeelabs/raybeelabs.github.io`
            - - README 포함하여 생성 (저장소 즉시 활성화를 위해)
              - - 생성 후 자동으로 `https://raybeelabs.github.io` 주소로 웹사이트 호스팅 시작
               
                - ### 3단계: app-ads.txt 파일 생성
                - - 저장소에 `app-ads.txt` 파일 생성
                  - - 파일 내용: AdMob에서 제공한 퍼블리셔 코드 입력
                   
                    - ```
                      google.com, pub-9927407488925716, DIRECT, f08c47fec0942fa0
                      ```

                      - 접근 URL: `https://raybeelabs.github.io/app-ads.txt`
                     
                      - ### 4단계: Google Play 콘솔에 개발자 웹사이트 등록
                      - - Google Play 콘솔 → 개발자 계정 → 계정 세부정보 → 내 정보
                        - - **웹사이트** 항목에 `https://raybeelabs.github.io` 입력 후 저장
                         
                          - ---

                          ## 최종 결과

                          | 항목 | 내용 |
                          |------|------|
                          | GitHub 저장소 | https://github.com/raybeelabs/raybeelabs.github.io |
                          | 개발자 웹사이트 | https://raybeelabs.github.io |
                          | app-ads.txt URL | https://raybeelabs.github.io/app-ads.txt |
                          | AdMob 퍼블리셔 ID | pub-9927407488925716 |

                          ---

                          ## 이후 확인 사항

                          - AdMob이 app-ads.txt를 크롤링하는 데 **최대 24시간** 소요
                          - - 24시간 후 AdMob → 앱 → app-ads.txt 탭에서 상태가 정상으로 변경되었는지 확인
