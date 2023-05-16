### Rebase - 다른 토픽 브랜치에서 갈라져 나온 토픽 브랜치 제어
1. `git rebase --onto master server client` master 브랜치부터 server 브랜치와 client 브랜치의 공통 조상까지의 커밋을 client 브랜치에서 없애고 싶을 때 사용한다.
   client 브랜치에서만 변경된 패치를 만들어 master 브랜치에서 client 브랜치를 기반으로 새로 만들어 적용한다.

2. master 브랜치로 돌아가 fast-forward 시킬 수 있다.
```bash
    git checkout master
    git merge client
```
3. server 브랜치의 일이 다 끝나면 `git rebase <basebranch> <topicbranch>`라는 명령으로 Checkout하지 않고 바로 server 브랜치를 master브랜치로 Rebase 할 수 있다. 이 명령은 토픽(server) 브랜치를 Checkout하고 베이스(master) 브랜치에 Rebase 한다.
```bash
    git rebase master server
```

4. server 브랜치의 수정사항을 master 브랜치에 적용

5. master 브랜치에 server 브랜치의 수정 사항을 적용
```bash
    git checkout master
    git merge server
```

6. merge된 branch는 제거
```bash
    git branch -d client
    git branch -d server
```

------------------------------------------------------------------------------------
### Reabse의 위험성
- Rebase가 장점이 많은 기능이지만 단점이 없는것은 아니다.
    - 이미 공개 저장소에 Push 한 커밋을 Rebase 하지 마라(이 지침만 지키면 Rebase 하는데 문제 될 게 없다.)