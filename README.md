# TIL
배움의 기록

# 2022-05-19
- 자바형변환
- https://soobarkbar.tistory.com/57

# 2022-05-20
- 오라클 WITH 테이블 
<pre>
<code>
WITH A AS
(
  SELECT SQL QUERY....
)
SELECT * FROM A;
</code>
</pre>
원하는 데이터를 조회하여 가상테이블로 만든후 사용하는 것
WITH 테이블은 여러번 사용할 때 효과가 더 크며, 가상테이블은 메모리에 생성되므로 액세스 속도가 빠르며 조회후에는 자동으로 소멸된다.

# 2022-05-23
- 자바스크립트 this
###### 함수 실행에 new 키워드를 사용하면, 그 함수 안에서 this 키워드는 새로운 객체를 가리킨다.
###### apply, call, bind를 사용해 함수를 호출/생성 했다면, 함수 안에서 this 키워드는 apply, call, bind 호출시 전달된 객체를 가리킨다.
###### 함수가 객체의 메소드로서 호출되었다면, this는 그 함수를 속성(property)으로 추가한 객체를 가리킨다.
- - -
+ 함수가 단순히 실행되었다면, 다시말해 위의 3가지 사례를 제외한 방식으로 호출되었다면, this는 전역 객체를 가리킨다. 브라우저에서는 window, node에서는 global이 된다. 만약 strict 모드(‘use strict’)에서는 this는 전역 객체 대신 undefined가 된다.
+ 만약 위의 4가지 조건이 중첩된다면, 먼저 제시한 규칙이 적용된다. (1번 규칙부터 우선함)
+ 함수가 ES2015의 화살표 함수라면, 위의 규칙을 모두 무시하고, 함수가 만들어진 시점에서 그 함수를 둘러싼 scope의 this를 가리킨다.
- 참고) https://blog.rhostem.com/posts/2020-04-12-fe-interview-handbook-js-1

# 2022-05-25
# JAVA) Matcher 클래스와 Pattern 클래스
- Mathcer 클래스 : 패턴을 해석하여 문자열에 맞춰주는 작업
   pattern 클래스를 기준으로 수행
   
<code>
  Pattern regex = Pattern.compile("정규식 String 값")
  Mather matcher = regex.matcher("찾을 글");
</code>
</pre>

- ex) 예를 들어, 기사에서 이미지 태그만을 가져오고 싶으면 

<pre>
<code>
  Pattern regex = Pattern.compile("<*src=[\"']?([^>\"']+)[\"']?[^>]*>")
  Mather matcher = regex.matcher(기사);
</code>
</pre>

- Mather 클래스의 메소드

### find()
Pattern에 일치하는 문자열이 발견되면 true, 아니면 false

### start()
Pattern에 일치하는 문자열 시작 index 반환

### end()
Pattern에 일치하는 문자열 끝 index 반환

### group()
Pattern에 일치하는 문자열을 반환

### match()
문자열 전체가 Pattern에 일차하면 true, 아니면 false

<pre>
<code>
  while (matcher.find()){
    find_val = matcher.group(1); //찾은 값
}
</code>
</pre>
