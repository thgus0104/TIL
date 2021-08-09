# GLI 환경 명령어

## 기본

(cmd보다는 git bash 사용 권장)

- ls = list

  (있는 거 보여줘라)

- pwd = print working directory

  (지금 파일을 보여줘라)

- mkdir = make directory

  (파일을 만들어라)

- cd = change directory

- mv a.txt b.txt

  (파일명 변경 좌)

- .. = 상위 디렉토리

- . = 현재 디렉토리

  git add . ->현재 디렉을 스테이징 공간에 저장하는 것

- touch a.png = 0byte짜리 png파일 생성

## git

1. git init

   원하는 디렉토리에 깃파일 생성

   (그 저장소에 모든 버전들이 저장이됨)

2. git add <file>

   원하는 파일을 스테이징 공간에 저장

   **스테이징 공간**

   중요한 이유는 여러 커밋으로 분류하는 것이 버전 관리가 수월할 수 가 있다.

   파일A, 파일B, 파일C가 있을 때

   파일C를 따로 add하여 커밋하면 

   B,C와 따로 관리된다. 

   1. 만약 B,C 커밋을 날리더라도 A는 살아있다.

   2. B는 수정하고, C는 삭제하고 버전을 업뎃한 후,

      그 버전을 되돌리면

      본인은 C만을 되돌리고 싶언던 것일지라도 같은 커밋에 저장된

      B도 이전버전으로 돌아간다.

      (즉, B수정전-C삭제전이 한개의 버전으로 관리되기 때문)

   즉, 한 개의 커밋에 담으면 하나만 수정해도 전체 파일에 변화가 일어날 수 있기 때문에 커밋을 잘 분류하는 게 좋다.

   ```git bash
   $ git add a.txt b.txt #복수의 디렉토리 한 커밋에 add
   $ git add test_folder/ #특정폴더 
   $ git add c.txt #특정 파일
   $ git add "*.txt" #특정확장자
   ```

   

3. git commit -m 'commit message'

커밋 시키는 것

이 때, 커밋할 파일들을 잘 나타내는 것을 메세지로 삼아야 한다.

4. git status

```git bash
$git status

On branch master

#커밋되기 전 변경 사항(=커밋 될 변경 사항들)(즉, 스테이징공간에 있는 애들)
Changes to be committed:
    (use "git restore --staged <file>..." to unstage)
        deleted:    b.txt
   
#staged(commit을 위한) 아닌 변경사항들
Changes not staged for committed:
    (use "git add <file>..." to update what will be committed)
    (use "get restore <file>..." to discard changes in working directory)
        modified:    a.txt
        
# 트래킹 X 파일들
#커밋된 적 없는 파일들...()
Untracked files
(use "git add <file>..." to include in what will be committed) 


```



4. git log 버전을 보고싶을 때

   (git log-2--oneline : 최근 두개만 보여달라 )



5. git config -l(알파벳 L)로 이메일/이름 확인해보기

## github

1. 원격 저장소 추가

```bash
$ git remote add origin <주소>
$ git remote add origin https:// github.com/<username>/<저장소이름>.git
```

- 깃아, 원격 저장소(remote)를 추가해줘, origin이라는 이름으로, 주소를

- 다른 이름을 붙일수도 있지만 origin을 주로 쓰기 때문에 바꾸지 않는것을 권장

- 이미 오리진이 존재할 때

  (remote origin already exists)

  추가등록은 안됨(덮어쓰기 안됨)

2. git remote rm origin

- 오리진이라는 이름의 주소를 지워줘

3. 원격저장소 push

```bash
$ git push <원격저장소이름> <브랜치이름>
$ git push origin master

-u 옵션: upstream 옵션
git push라고 명령을 하더라도 설정된 원격저장소에 브랜치를 push
$ git push -u origin master
```

4. 원격저장소 조회

```bash
$ git remote -v #verbose
origin  https://github.com/thgus0104/test.git (fetch)
origin  https://github.com/thgus0104/test.git (push)

```

5. 파일 내려받기

clone과 download.zip의 차이

clone은 .git이 존재

즉, 버전관리 가능(이전버전 조회 가능)

6. 프로필 설정

   - 원격 저장소 이름을  자신의 아이디로 설정

     (프로필로 설정되는 저장소명으로 설정되어있음)