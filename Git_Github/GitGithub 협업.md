# Git/Github 협업

## Branch

### Branch의 중요성

- 1차 제출 후 다음 버전 개발 중에 이전 버전 오류

  다음버전이 반영 되지않게 1차 제출 버전만 수정해서 올리는 방법

- 최종 제출을 master라는 branch에 저장
- 다음 버전 개발은 tgd라는 branch에 저장
- git checkout master를 입력하면 branch master로 이동(tgd에 저장된 파일은 사라짐)
- master에 있는 파일을 변경하고 git add하면 master branch 변경사항만 업로드됨
- 차후 git merge tgd를 하면 1차제출 수정사항+tgd 된다

### Master Branch

- Master=배포 가능한 코드

  (외부로 유출 가능한 코드)

  당연히 정상 작동할 것으로 기대

- 개발용 브랜치는 따로 설정되어있을 거기 때문에



### Branch 명령어

1. branch 생성

```bash
$ git branch 브랜치이름
```

2. branch 이동

```bash
$ git checkout 브랜치이름
```

3. branch 생성 및 이동

```bash
$ git checkout -b 브랜치 이름
```

4. branch 조회

```bash
$ git branch
```

5. branch merge(발생가능 시나리오 3개)

```bash
(master) $ git merge 브랜치이름
```

- master로 병합하는 경우 master 브랜치에서 명령어 작성해야함!
- '브랜치이름'을 해당 브랜치로 병합하는 명령어이기 때문

6. branch 삭제

```bash
$ git branch -d 브랜치이름
```

### Branch Merge Scenario

1) 'branch' 폴더 만들기

2) git init
3) README.md 파일 만들고 커밋

최초의 루트커밋 없이 아래의 실습을 진행할 수 X

----------------------------------------------------------------

*로컬에서만 진행

1. 독박쓰기

2. merge commit(자동)

   각 브랜치 작업이 다른 파일 수정하고 있기 때문에

3. merge commit(자동X)

   conflict=>같은파일이 다르게 수정된 커밋이 있어서

   conflict 확인 후 commit 직접 해야함

*작업을 한다=빈 파일 아무거나 만든다로 대체

