# 이전 커밋 가져오기

### reset

-   git에서 이전 커밋으로 돌아가려면 reset을 사용한다
-   reset은 3가지 옵션이 있다
    -   default
        -   돌아온 커밋 이후의 변경사항은 모두 unstaged 영역에 남는다
    -   soft
        -   돌아온 커밋 이후의 변경사항은 모두 staged 영역에 남는다
    -   hard
        -   변경사항을 모두 제거한다. 코드들은 끝이다

```
git reset --{opction} {돌아갈 위치}
```

돌아간 이후에는 강제 푸쉬를 할 수 있다

```
git push -f origin main
```

브랜치 룰을 조정하여 강제 푸쉬를 할 수 있다
