## Repository clone & commit 하기

```bash
1. git clone {git repository 주소}
2. git checkout -b "branch 명"
3. 작업한 문서 올리기
4. git add .
5. (git status : 상태 확인, 필수는 아니지만 해보는게 좋음)
6. git commit -m "commit message"
7. git push origin "브랜치명"
```

## Branch 생성하기

```bash
git checkout -b "branchName"
```

## 원격 Branch 가져오기

1. 원격 브랜치 업데이트
    
    ```docker
    git remote update
    ```
    
    - 원격 저장소의 브랜치에 접근하기 위해 원격 저장소 갱신
    - 원격 레포지토리의 브랜치들이 로컬 레포지토리에도 반영
2. 원격 저장소 브랜치 확인하기
    
    ```docker
    git branch -r
    ```
    
    - 원격 저장소의 브랜치 리스트들을 확인할 수 있음
    - 로컬 브랜치 목록을 보고싶다면 다음과 같은 명령어 입력
        
        ```docker
        git branch -a
        ```
        
3. 원격 브랜치 코드 로컬 브랜치에 적용하기
    
    ```docker
    git checkout -t [origin/원격 브랜치명]
    ```
    
    - 원격 레포지토리의 브랜치를 로컬 브랜치에 적용하고 싶을 때 사용
    - 즉 영구적으로 tracking 하고 싶을 때 -t 옵션을 주어 checkout 하면 됨
    - 이 방법을 쓰면 원격 브랜치명과 로컬 브랜치명이 같게 checkout 된다.
    
    ```docker
    git checkout -b [생성할 브랜치명] [원격 브랜치명]
    ```
    
    - -b 명령어를 넣어주어 원격 브랜치의 내용을 가져올 로컬 브랜치의 이름을 원하는대로 바꿔줄 수도 있음
- 참고 자료 [https://velog.io/@juno7803/git-원격-브랜치-가져오기remote-branch](https://velog.io/@juno7803/git-%EC%9B%90%EA%B2%A9-%EB%B8%8C%EB%9E%9C%EC%B9%98-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0remote-branch)

## 원격 브랜치 삭제하기

1. 원격 브랜치 업데이트
    
    ```docker
    git remote update
    ```
    
    - 원격 저장소의 브랜치에 접근하기 위해 원격 저장소 갱신
    - 원격 레포지토리의 브랜치들이 로컬 레포지토리에도 반영
2. 원격 저장소 브랜치 확인하기
    
    ```docker
    git branch -r
    ```
    
    - 원격 저장소의 브랜치 리스트들을 확인할 수 있음
3. 삭제하기
    
    ```yaml
    git push origin --delete {branch_name}
    ```
    
- 참고 자료 [https://www.lesstif.com/gitbook/git-delete-remote-branch-20776547.html](https://www.lesstif.com/gitbook/git-delete-remote-branch-20776547.html)

## 이미 commit한 메시지 수정하기

### 마지막 커밋 메시지 수정하기

- —amend 옵션 사용
    
    ```bash
    git commit --amend -m "message"
    ```
    
- vi 편집기를 이용해 수정하기
    
    ```bash
    git commit --amend
    ```
    
    - 명령어를 입력하면 vi가 실행되고 수정이 가능하다.

### 마지막 이전 커밋 메시지 수정하기

- rebase 명령 사용
    
    ```bash
    git rebase -i HEAD~3
    ```
    
    - 최근 커밋 로그 중 3개를 불러온다.
    - i를 눌러 편집모드로 들어간 후 pick을 reword로 수정한 후 :wq → 커밋 메시지를 수정할 수 있게 된다.

### 참고 자료

- [https://xtring-dev.tistory.com/entry/Git-이미-commit한-메세지-수정하기-바로-이전그-전리모트-commit](https://xtring-dev.tistory.com/entry/Git-%EC%9D%B4%EB%AF%B8-commit%ED%95%9C-%EB%A9%94%EC%84%B8%EC%A7%80-%EC%88%98%EC%A0%95%ED%95%98%EA%B8%B0-%EB%B0%94%EB%A1%9C-%EC%9D%B4%EC%A0%84%EA%B7%B8-%EC%A0%84%EB%A6%AC%EB%AA%A8%ED%8A%B8-commit)
- [https://holika.tistory.com/entry/Git-삽질기록-Git-push-이후에-커밋-메시지를-수정하고-싶을-때](https://holika.tistory.com/entry/Git-%EC%82%BD%EC%A7%88%EA%B8%B0%EB%A1%9D-Git-push-%EC%9D%B4%ED%9B%84%EC%97%90-%EC%BB%A4%EB%B0%8B-%EB%A9%94%EC%8B%9C%EC%A7%80%EB%A5%BC-%EC%88%98%EC%A0%95%ED%95%98%EA%B3%A0-%EC%8B%B6%EC%9D%84-%EB%95%8C)
