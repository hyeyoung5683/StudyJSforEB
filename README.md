# StudyJSforEB
This project is for improving my work skills.


Day1 : 31 July 2021

<< 자바스크립트 문자열 다루기 1. JS문자열다루기>>

0.
- 문자열은(String) JS의 가장중요한 구성 요소 
  이유: 사용빈도가 어떤 자료형보다 높을 것임, 웹 페이지의 폼에서 가져오면 숫자값도        문자열로 값을 구한후 숫자로 변환
  
- 문자열은 Ajax를 통해 서버측 애플리케이션 호출할때 인수로도 사용되고 JS객체 기복   적인 직렬화 형식 구성때도 쓰임
- toString: 모든 JS객체가 가지고 있는 메서드 중 하나, 직렬화된형식을 문자열로   반환하는 역할


- 문자열 원시 자료형 
  문자열은 원시primitive자료형이자 객체,
  이외4종류: 숫자,불리언,null,unddfined
  리터럴literal: 숫자,불리언,배열,객체,정규표현식의 리터러형식 
  
- 문자열 객체: String 
  var city = new String("St. Louis");
  
- 인스턴스화되면 여러속성접근가능
  var lcCity = city.toLowerCase(); //st. louis  
  
1.  
. 두개 이상의 문자열 합치기

. 연산자 오버로드: 연산자가 입력값에 따라 여러가지동작을 하도록하는 것

. var nwString = "".concat("this ", "is ", "a ", "string");
  form필드로부터 문자열을 생성하는 경우처럼 여러값을 하나의 문자열로 더 쉽게가능

. var boolValue= true; var stringValue = "값: " + boolValue;

. 작업 중인 문자열이 객체인지 리터럴인지분간어려운상태
  var strObject = new String("Value is ");
  var stringLiteral = "String";
  var stringValue = strObject + stringLiteral; //Value is String = 만환결과는 객체가아닌 문자열임

2.
. 숫자 10.00문자열은 10으로 변환되어 비교 연산에 사용됨, 

3.
문자열 리터럴값과 string객체면 두 변수의 자료형이 다르므로 변수 내부 값과 상관없이 비교 결과가나올수있음 그럴땐 "===" 사용
  var strObject = new String("Tommy");
  var strLiteral = "Tommy";
  if(strObject == strObject) true
  if(strObject === strObject) false

. 문자열이 같지 않은지 확인하고싶을때 부등연산자 (!=) 엄격한 부등연산자(!==)사용, 문자열이 서로 같지 않을때 참을 반환
  var strnOne = "One";
  var strTwo = "two";
  it(strnOne != strnTwo)// 두 문자열은 같지 않으므로 결과는 참

  var strObject = new String("Tommy");
  var strLiteral = "Tommy";
  it(strObject !== strObject)// 피연산자의 자료형이 서로 다르므로 성공

. localCompare 숫자값반환(비교연산자를 더 많이 사용하지만 또다른방법임)
0: 같음 
-1: 원래문자보다 문자적으로큼 
1: 원래문자열이 더 큼

4.
. indexOf 문자열 위치의 숫자 반환: 첫번째인덱스 = 0부분 문자열이 대상 문자열 안에 없는지 확인하려면 반환되는 값이 -1인지 살펴보면됨
lastIndexOf: 마지막에 나타난 부분 문자열의 인덱스 위치 반환


5.
. 문자열 부분 추출 substring
목록은 콜론:시작 마침표.로 끝남

. 목록값 분리 String.split (var fruits = list.split(",");

. substr 문자열 추출 메서드

6.
. 문자열 존재 || 빈 문자열 확인
typeof연산자
ValueOf메서드
String 객체의 length속성으로 조건문작성 가능
if (((typof unknownVariable != "underfined") && 
(typeof unknownVariable.valueOf() == "string")) &&
(unknownVariable.length > 0)) { ... }

. typeof연산자는 변수 타입반환
number : 숫자
string : 문자열
boolean : 불리언
fcunction : 함수
object : null,배열 || 다른JS객체
undefined : 정의되지않았을때

if((typeof unknownVariable !== "undefined") && (unknownVariable.length > 0)) { ... } //정의되지않은 테스트에서 실패하면 두번째 조건은 처리하지않으며 실패함(이런방식으로오류예방가능)

7.
키워드 문자열을 여러개 키워드로 나누기
var strList = "keyword1,keyword2,keyword3,keyword4";
var arrayList = strList.split(",",2) //요소가2개인배열 
- 2번째인수를 정하지않으면 발견된 모든 구분자 기준 분리
- 빈문자열('' || "") 전달하면 모든 문자 나눔

8.
줄바꿈 문자와 같은 특수 문자 문자열 삽입
이스케이프문자열사용

카피라이트 기호 : \u00A9
\'  작은따옴표
\"  큰따옴표
\\  백슬래시
\b  백스페이스
\f  폼피드(연속용지사용프른터다음장넘기기위한문자)
\n  줄바꿈
\r  캐리지 리턴 (커서줄젤앞옮기라는의미)
\t  가로탭
\ddd  8진수문자열
\xdd  16진수문자열
\udddd  유니코드문자열

9.
textarea줄별로 처리

. 이스케이프 문자열로 인코딩된 텍스트를 적절한 HTML코드로 변활할때 사용할수있음(textarea입력된내용그대로HTML출력)

//줄바꿈문자기준textarea문자열분리
var txtBox = document.getElementByID("test");
var lines = txtBox.value.split("\n");

//내용을 HTML버전변경
var resultString ="<p>";
for(var i = 0; i < lines.length; i++) {
  resultString += lines[i] + "<br />";
}
resultString += "</p>";
                                
//페이지에출력
var blk = document.getElementById("result");
blk.innerHTML =resultString;

모든줄바꿈은 br요소로 변환
                                
10.
문자열 끝 공백 제거

. ECMAScript5에서 새롭게 정의된 String객체의 trim메서드

Screen Shot 2021-07-31 at 2.49.01 PM![Screen Shot 2021-07-31 at 2 49 01 PM](https://user-images.githubusercontent.com/84766081/127730219-c9b2d496-cb13-4f6b-9bf4-28f540ade2c8.png)

. IE8제외한 모든 브라우저지원하지만 사용할수없는 브라우저에서도문제발생안토록만든 우회법

Screen Shot 2021-07-31 at 2.51.05 PM![Screen Shot 2021-07-31 at 2 51 05 PM](https://user-images.githubusercontent.com/84766081/127730244-2f2b4c5d-a6de-4852-a2b4-e0205944a2a8.png)

. 왼쪽공백제거 trimLeft 오른쪽공백제거 trimRight도 있음
                                
11.
문자열 왼쪽 또는 오른쪽에 문자열 채워 넣기

. 잘림방지공백문자(&nbsp;)
Screen Shot 2021-07-31 at 2.54.59 PM![Screen Shot 2021-07-31 at 2 54 59 PM](https://user-images.githubusercontent.com/84766081/127730327-6a88a290-4276-4e51-8e09-5dc3d97d33f2.png)

데이터베이스저장시는 공백저장하고싶지않음 .. 웹페이지출력할때는 넣고싶은경우있음 
css사용해서 하는방법 
innerHTML을통해서 넣는방법
DOM 레벨2의기능사용방법도있음 

Screen Shot 2021-07-31 at 2.56.32 PM![Screen Shot 2021-07-31 at 2 56 32 PM](https://user-images.githubusercontent.com/84766081/127730364-099f3889-b0be-4a46-8982-821db8207f82.png)
                                
                               
                               
Day2 : 1 August 2021

<< 자바스크립트 문자열 다루기 3. 날짜,시간 타이머>>
  
Screen Shot 2021-08-01 at 1.16.16 PM![Screen Shot 2021-08-01 at 1 16 16 PM](https://user-images.githubusercontent.com/84766081/127759374-953a3035-a596-4889-973a-b51754aaf751.png)
Screen Shot 2021-08-01 at 1.16.26 PM![Screen Shot 2021-08-01 at 1 16 26 PM](https://user-images.githubusercontent.com/84766081/127759375-49dbb8c9-f0e7-4734-bb3c-b095d4cc03a4.png)

0.
자바스크립트 타이머
window객체 메서드: 
- setInterval 취소할 때까지 계속 반복 실행하는 타이머만듬
- setTimeout 한번만 실행하는 타이머를 만듬

1.
오늘 날짜 출력
- 시간값은 기본적으로 0설정됨 / 월은 0부터 시작
- 다른형식을 원하면 getMonth, getFullYear, getTime, getDate와 같은 메서드 사용

2.
UTC 날짜 및 시간 출력

협정셰계시 날짜와 시간에 접근하기위해 UTC JS메서드사용
- toUTCString:협정세계시를 기준한 날짜/시간문자열반환
  
3. 
ISO 8601형식으로 날짜 출력
- ISO 8601 날짜와 시간표기법을 정의한 국제 표준, API제공 애플리케이션에서 필요할때있음
Screen Shot 2021-08-01 at 1.34.59 PM![Screen Shot 2021-08-01 at 1 34 59 PM](https://user-images.githubusercontent.com/84766081/127759386-88f549a4-bd39-406c-879e-a80920040499.png)

- 형식: 시간을뜻하는 T
Screen Shot 2021-08-01 at 1.36.09 PM![Screen Shot 2021-08-01 at 1 36 09 PM](https://user-images.githubusercontent.com/84766081/127759402-905e817f-1827-487d-a219-727665b6deed.png)
Screen Shot 2021-08-01 at 1.36.13 PM![Screen Shot 2021-08-01 at 1 36 13 PM](https://user-images.githubusercontent.com/84766081/127759403-5b7bf5a8-cdc6-4eec-bfed-5001044e7cfa.png)

- UTC기준이면 Z
Screen Shot 2021-08-01 at 1.37.27 PM![Screen Shot 2021-08-01 at 1 37 27 PM](https://user-images.githubusercontent.com/84766081/127759422-0b46b3a1-cdf5-4364-94a4-868f31d3bd67.png)

날짜출력기능필요없게될것이며 ECMAScript5에서 Date에 TtoISOString메서드 새로 추가됨

4.
ISO 8061형식의 날짜 Date객체변환

- Date 객체만들려고하면 에러발생 String.split메서드 사용
- 월은1부터시작12 > JS객체에서사용하려면 -1빼야함
- UTC유지하려면 Date객체의 UTC매서드사용하여 날짜 협정세계시리로 작성

Screen Shot 2021-08-01 at 1.58.42 PM![Screen Shot 2021-08-01 at 1 58 42 PM](https://user-images.githubusercontent.com/84766081/127759783-79884478-f110-43eb-8e30-f93fd1c1bf48.png)
Screen Shot 2021-08-01 at 1.58.50 PM![Screen Shot 2021-08-01 at 1 58 50 PM](https://user-images.githubusercontent.com/84766081/127759788-3227a80d-469c-4a9c-af51-37bad27aa094.png)

5.
특정 날짜로 객체 생성

- 년,월,일 Data생성자에 전달되는정수값, 시간값주어지지않으면 시간은 기본적으로0으로생성
  
6.
미래 날짜 만들기
- Data객체의 get,set매서드사용 
Screen Shot 2021-08-01 at 2.04.15 PM![Screen Shot 2021-08-01 at 2 04 15 PM](https://user-images.githubusercontent.com/84766081/127759843-75dd1fb7-ebe3-4767-bd44-eebaeb294bcd.png)

Screen Shot 2021-08-01 at 2.04.52 PM![Screen Shot 2021-08-01 at 2 04 52 PM](https://user-images.githubusercontent.com/84766081/127759850-6302ce1a-608b-4318-aff2-66e27d7ecc75.png)

- UTC버전도 사용가능, 과거는 원하는날짜만큼 빼면됨
  
7.
경과 시간 구하기

두이벤트사이에 경과한 시간 구하고싶을때 첫번째 이벤트 발생시 Date 객체생성 > 두번째이벤트발생시 또다른 Date객체생성
뺀값은 밀리초 단위로 초단위 값바꾸려면 1,000나눔

Screen Shot 2021-08-01 at 2.06.57 PM![Screen Shot 2021-08-01 at 2 06 57 PM](https://user-images.githubusercontent.com/84766081/127759875-a4f490bb-dedd-491c-b6ac-4eae1d742e63.png)


8.
타임아웃 만들기

이벤트기반에 타임아웃: window.setTimeout(실행할표현식,[밀리초단위의시간])

9.
반복 타이머 만들기

똑같은 함수를 일정한 각격을 두고 반복해서 실행
- window.setInterval
  
10.
함수 클로저를 타이머와 함께 사용

타이머가 붙은 함수제공하되 타이머 메서드 호출때 함수바로추가하고자할때
- setInterval, setTimeout메서드 호출시 익명 함수를 첫번째 인수사용

Screen Shot 2021-08-01 at 2.12.50 PM![Screen Shot 2021-08-01 at 2 12 50 PM](https://user-images.githubusercontent.com/84766081/127759950-d310b6ab-da93-4562-8059-ebc46ff526e8.png)

Screen Shot 2021-08-01 at 2.13.27 PM![Screen Shot 2021-08-01 at 2 13 27 PM](https://user-images.githubusercontent.com/84766081/127759962-969bcd68-560c-4371-bda8-b4fae425c758.png)
Screen Shot 2021-08-01 at 2.13.35 PM![Screen Shot 2021-08-01 at 2 13 35 PM](https://user-images.githubusercontent.com/84766081/127759964-5c06eff8-0edf-44a8-a809-79a8e490d151.png)

  
<< 자바스크립트 문자열 다루기 5. 배열과 반복문  >>

0.
배열은 순서가 매겨진 원소의 집합
Screen Shot 2021-08-01 at 11.11.05 PM![Screen Shot 2021-08-01 at 11 11 05 PM](https://user-images.githubusercontent.com/84766081/127773984-30c562c1-df89-4a2f-a34b-7e5b18ec2805.png)

- JS엔진에 있어 배열 리터럴은 접근할때마다 특히 함수호출마다매번재해석해야하는대상
- 배열 리터럴은 함수에 값을 전달하려고 만들었던 임시 변수대체할수있다는 장점이있음

1.
반복문에서 배열 사용하기

- for / while
Screen Shot 2021-08-01 at 11.21.45 PM![Screen Shot 2021-08-01 at 11 21 45 PM](https://user-images.githubusercontent.com/84766081/127774354-538d1c7b-b3bc-4a3e-bef7-5ab45d0c056b.png)
Screen Shot 2021-08-01 at 11.21.49 PM![Screen Shot 2021-08-01 at 11 21 49 PM](https://user-images.githubusercontent.com/84766081/127774357-770f6971-80f1-4568-ab08-eb2f1b9bb52d.png)

3.
배열에서 문자열 만들기
  
- array객체 내장매서드 join: 배열원소를묶어 문자열로 만들수있다.
Screen Shot 2021-08-01 at 11.27.37 PM![Screen Shot 2021-08-01 at 11 27 37 PM](https://user-images.githubusercontent.com/84766081/127774532-e561038f-27e8-4d30-bb26-c49170eb7570.png)

- 인자로 구분자를 전달할수있는데 생략시 쉼표삽입됨

4.
배열 정렬하기

- array객체 내장매서드 sort: 배열정렬(기본 오름차순 정렬순서바꾸고싶으면 reverse)
Screen Shot 2021-08-01 at 11.30.13 PM![Screen Shot 2021-08-01 at 11 30 13 PM](https://user-images.githubusercontent.com/84766081/127774620-f9a05613-c5bc-48f0-9a99-c661b28fce46.png)

5.
값에 순차적으로저장접근

- FIFO 큐작성: Array객체의 push메서드사용/shift매서드 사용으로 큐에서 원소 추출
Screen Shot 2021-08-01 at 11.36.02 PM![Screen Shot 2021-08-01 at 11 36 02 PM](https://user-images.githubusercontent.com/84766081/127774812-ae849ba9-6b94-418b-9f7a-65849adb84e7.png)

6.
값을 저장하고 역순접근

- LIFO 스택작성: Array객체의 push메서드 사용 스택 원소 추가, pop메서드사용 스택 원소 추출

Screen Shot 2021-08-01 at 11.38.25 PM![Screen Shot 2021-08-01 at 11 38 25 PM](https://user-images.githubusercontent.com/84766081/127774890-b53582d0-82d1-44d7-a792-7841b9812833.png)
Screen Shot 2021-08-01 at 11.38.29 PM![Screen Shot 2021-08-01 at 11 38 29 PM](https://user-images.githubusercontent.com/84766081/127774892-b76d5ad6-4bda-4302-8473-27b831209dab.png)

7.
기존 배열 부분 집합 새 배열 작성

- Array객체의 slice메서드: 주어진범위의 원소를 기반으로 새 배열을 만들수있다.

8.
배열 탐색

- indexOf : 가장처음에 찾은 값 반환
- lastIndexOf : 가장 마지막에 찾은 값 반환
- 모든브라우저가 지원하는하지않음


9.
다차원 배열 평평하게 만들기

- Array객체의 concat메서드 사용 다차원 배열 1차원배열로만들수있다.
Screen Shot 2021-08-01 at 11.52.58 PM![Screen Shot 2021-08-01 at 11 52 58 PM](https://user-images.githubusercontent.com/84766081/127775371-3db3da10-e195-48e9-bf23-7bc2875114aa.png)

10. 
배열 원소 검색 없애거나 바꾸기

- Array의 indexOf와 splice메서드 사용하면 배열 원소 찾아 제거하거나 치환가능

11.
각 배열 원소에 함수 적용

- Array객체의 forEach사용 각 배열 원소에 콜백함수추가가능

12.
배열의 모든 원소에 함수 적용하고 새로운 배열 반환

- Array의 map메서드 사용
Screen Shot 2021-08-02 at 12.04.05 AM![Screen Shot 2021-08-02 at 12 04 05 AM](https://user-images.githubusercontent.com/84766081/127775724-d08da461-9148-41d0-a53c-33acd5b844ac.png)

- 세개인수전달: 각각 현재의 배열원소, 배열 원소의 인덱스, 배열

13. 
값을 걸러낸 배열 작성

- Array객체의 filter메서드사용

14.
배열 콘텐츠 유효성 검사

- Array객체의 every메서드 사용: 모든 원소 주어진 조건 통화하는지 확인가능
- Array객체의 some메서드 사용: 주어진 조건 만족시키는 요소가 최소 1개 이상있는지 확인가능
  

