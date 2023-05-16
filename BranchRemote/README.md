### git Branch Remote
추적 브랜치가 현재 어떻게 설정되어 있는지 확인하려면 `git branch -vv`라고 하면된다.
위 명령어를 실행하면 로컬 브랜치 목록과 로컬 브랜치가 추적중인 원격 브랜치도 함께 보여준다.
또한 로컬 브랜치가 앞서가는지 뒤쳐지는지에 대한 내용도 보여준다.

```bash
    $ git branch -vv
    iss53     7e424c3 [origin/iss53: ahead 2] forgot the brackets
    master    1ae2a45 [origin/master] deploying index fix
    * serverfix f8674d9 [teamone/server-fix-good: ahead 3, behind 1] this should do it
    testing   5ea463a trying something new
```
