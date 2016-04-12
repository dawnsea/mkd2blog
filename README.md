# mkd2blog
마크다운을 블로그로


# 뭐하는 놈인가?
깃헙에 마크다운으로 블로그 글을 쓴 다음, 이 툴을 사용하면 완전한 정적 페이지로 전환해줌.
ftp 업로드까지 자동으로 처리해주긴 함..



# 서문
만들기 귀찮아서 데지는 줄 알았... 꼭 필요해서 만들었음.
파이썬 잘 못 함.. 


# 사용법
python ./tblog_static.py clone | pull


# 설정
소스 앞부분을 다음과 같이 수정

```python 
my_config = { 'REPODIR'   : 'tblog',   # 레파짓의 로컬 디렉토리 이름
              'GITHUB'    : 'https://github.com/dawnsea/tblog.git',  # 블로그 마크다운 문서들 보관장소 
              'DOCROOT'   : '/blog/',   # 웹서버 홈
              'NAME'      : '[t:/]',   # rss 표시 이름
              'DESC'      : '[t:/] is not technology-root', # rss 표시 설명
              'URL'       : 'http://www.troot.co.kr', # rss 에서 사용할 블로그 URL
              'FTP'       : 'troot.co.kr',   # ftp 업로드 주소
              'FTPUSER'   : 'keeptalk', # ftp 계정
              'FTPPATH'   : 'www',  # 웹서버의 경로
              'FTPREMOTE' : '/home/hosting_users/keeptalk/www'  }  # 웹서버의 절대 경로
```

# 글쓰기
레파짓에 다음 경로를 생성함

- images : 블로그 안에 이미지를 삽입할 경우 여기에 넣어둠, 이미지는 마크다운 태그로 삽입하되 /로 시작함.
- 년-월 폴더 : 이 안에 글을 씀
- 년-월 폴더/url : 파일명이 url이 됨.
- 예) 2016-04/첫글이당  : 첫글이당이라는 마크다운 파일이 내가 쓴 글임
- 규칙 : 최초 3줄을 다음과 같이 씀 (형식 지켜야됨)
- - 제목 : 나는 제목이당
- - 태그 : 음악, 잡담, 영화
- - 날짜 : 2016/04/04  
- 제목에 [비공개] 를 포함하면 나만 보는 글이 됨


# 꾸미기 
- template/css/style.css, style2.css 수정
- template/*.html 수정


# 퍼블리시
- python tblog_static.py 실행하면 정적 페이지가 deploy에 생성됨. 
- 이어서 ftp 업로드가 수행됨. (귀찮으면 걍 빼삼..)
- 귀찮으면 서버에 python 모듈 깔고 크론탭에 걸기 바람.. 더 이상 지원 몬함 귀찮음.
- 매번 암호 넣기 귀찮으면 코드에 넣으삼.. 털리면 니 책임.

# 관리자 (나만 보는 페이지)
- 툴을 실행하면 콘솔에 어드민용 주소가 표시됨. 그 페이지로 들어가면 비공개 글가지 다 보임.
- 예) http://www.troot.co.kr/blog/admin240bf9e4-42d5-413a-93be-1085c88bbddb
- 이 주소는 퍼블리시 할 때마다 바뀜. 귀찮으면 고정으로 코드 수정 gogo 

# 부족한 기능들
- 고쳐 쓰세요

# 라이선스
- 그땅거 음따. 

# 후기
- 플라스크 학습용으로 github 연동을 블로그 툴을 만들었는데,
- 만들다 보니 CRUD를 다 구현할 필요가 있을까 github에서 글 쓰기가 좋은데,
- 그러다 보니 머더러 CRUD를 다 구현할 껑가 이래서야 정적 페이지가 아니자너
- 에라 모르겠다 걍 올 html로 찍어버리자 이게 영속성이 이따.
- ... 하고 만들었습니다.

단 두 명만!! 제발!! 두 명만이라도 써주신다면..

