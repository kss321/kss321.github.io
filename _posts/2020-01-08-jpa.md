https://jobc.tistory.com/120

queryDsl

1. fetchJoin

queryDsl로 select할 때, 그냥 join(), leftJoin(), rightJoin()만 사용하면 from의 entity에 있는 값만 가져옴
select의 조건으로만 사용하고 싶을때는 위와 같이 사용해도 되지만, join한 entity의 값도 같이 가져오고 싶은 경우에는 
fetchJoin()을 사용하여 한번에 같이 가져올 수 있음

출처 : https://blog.leocat.kr/notes/2019/06/01/querydsl-avoid-n-plus-one-issue-with-fetch-join

