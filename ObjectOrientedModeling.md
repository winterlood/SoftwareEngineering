Modeling 
===

Model?
---

현재나, 미래의 (즉 앞으로 개발할) 시스템의 원하는 모습을 가시화 한것,

시스템의 구조와 행위를 명세한것

시스템을 구축하는 청사진

**추상화**에 바탕을 둔다.
> 특정 관점에서 관련이 있는것 <br>(즉 수강신청 소프트웨어 내의 학생의 경우 수강과목, 지도교수 )  <br>
> 관련없는 자질구레한것은 무시 (학생의 키 등등..)

UML
---

대표적인 System Modeling Language 

시스템을 설계하기 위한 공용 언어


Class Diagram
---

시간에 관계 없음

시스템의 **정적**인 구조를 표현한다.

> Ex> 건물의 구조 등등 (1층에는 4개의 강의실이 있다.) <br>

> 시간에 흐름에 제약받거나 의존적이지 않은 항상 그러한 행동

동적인 구조는 다루지 않는다.

> Ex> 6시가 지나면 가로등이 켜진다.

Class
---

### 1. Class란 ?

동일한 속성을 지니고,

동일한 행위를 수행하는 **객체의 집합**

**객체를 생성하는 설계도/틀** 이다.

> Ex> Unity의 Prefabs도 객체이다.

### 2. Class Expressed in UML

세 부분으로 나누어진 박스

가장 윗부분은 Class의 이름, 중간부분은 Attribute, 마지막 부분은 Operator

그림 추후 첨부

접근 제어자의 표현은 

 - **+** : Public
 - **-** : Private
 - **#** : Protected
 - **~** : Package
 
다음과 같다.

----------------
| Coures       |
|--------------|
|-id           |
|-name         |
|-nameOfStudent|
|--------------|
|+addStudent   |
|+deleteStudent|
|--------------|

다음 UML로 표현된 Class를 C#으로 구현한 코드는 다음과 같다.

~~~
class Coures
        {
            private string id;
            private string name;
            private int numOfStudent;
            public Coures()
            {
                numOfStudent = 0;
            }

            public void addStudent()
            {
                numOfStudent += 1;
            }

            public void deleteStudent()
            {
                if (numOfStudent > 0) numOfStudent -= 1;
                else numOfStudent = 0;
            }
        }
~~~

이렇게 UML로 표현된 Class는 객체지향 언어이면 무슨 언어이든 구현해 낼 수 있다.


관계
---

### 1. 연관관계

하나의 클래스의 기능을 다른클래스들에서 사용하게 되는것

연관 관계는 연관되어있는 클래스들 사이에 실선을 그어 표시한다.

> 두 클래스 사이의 관계가 명확하지 않으면 이름을 쓰지 않아도 된다.



~~~
        public class Phone
        {
        }
        
        public class Preson
        {
            Phone homePhones = new Phone();
            Phone officePhones = new Phone();
        }
~~~
