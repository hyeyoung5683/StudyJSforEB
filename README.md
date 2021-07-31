# StudyJSforEB
This project is for improving my work skills.


Day1 : 31 July 2021

<< 자바스크립트 문자열 다루기 >>
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
  
. 두개 이상의 문자열 합치기

. 연산자 오버로드: 연산자가 입력값에 따라 여러가지동작을 하도록하는 것

. var nwString = "".concat("this ", "is ", "a ", "string");
  form필드로부터 문자열을 생성하는 경우처럼 여러값을 하나의 문자열로 더 쉽게가능

. var boolValue= true; var stringValue = "값: " + boolValue;

. 작업 중인 문자열이 객체인지 ㄹ터럴인지분간어려운상태
  var strObject = new String("Value is ");
  var stringLiteral = "String";
  var stringValue = strObject + stringLiteral; //Value is String = 만환결과는 객체가아닌 문자열임

. 숫자 10.00문자열은 10으로 변환되어 비교 연산에 사용됨, 문자열 리터럴값과 string객체면 두 변수의 자료형이 다르므로 변수 내부 값과 상관없이 비교 결과가나올수있음 그럴땐 "===" 사용
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

. indexOf 문자열 위치의 숫자 반환: 첫번째인덱스 = 0부분 문자열이 대상 문자열 안에 없는지 확인하려면 반환되는 값이 -1인지 살펴보면됨
lastIndexOf: 마지막에 나타난 부분 문자열의 인덱스 위치 반환






