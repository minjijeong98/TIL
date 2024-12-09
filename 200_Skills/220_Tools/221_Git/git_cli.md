# 주요 Git CLI 명령어

## 기본 설정
```bash
# 초기 설정
git init  # 초기화
git config user.name minjijeong98
git config user.email minji.jeong.ds@gmail.com
git config --list  # 설정 내용 조회

# 프로젝트 가져오기 1
git clone {repositiory_address}

# 프로젝트 가져오기 2
git remote add origin {repository_address}
git fetch origin  # 원격 저장소의 내용 로컬로 가져오기
git pull origin main  # 원격 저장소의 내용을 로컬 저장소로 병합

# 브랜치 가져오기
git branch -r  # 원격 브랙치 조회
git branch {branch_name} # local branch 생성
git checkout {branch_name} # 사용할 branch로 체크아웃
git checkout -b {branch_name}  # branch 생성하면서 해당 branch로 checkout
git push origin {branch_name}  # 원격 브랜치에 local 브랜치 붙여넣기

# 브랜치 내용 가져오기
git pull origin develop
```

## 로컬 폴더를 github에 레포지토리로 업로드
```bash
git init

```