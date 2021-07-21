# Rx Document 2

### Subject

Subject 는 Observable 이면서 Observer 역할을 할 수 있는 일종의 bridge 라고 할 수 있다.

따라서 Observer이기 때문에 다른 Observable을 구독할 수 있으며, Observable이기 때문에 이벤트를 방출하는 것이 가능해진다.

Subject는 Observable을 구독하고 있기 때문에, Observable이 item을 방출할 수 있도록 트리거가 된다고 할 수 있다. Cold 에서 Hot으로 바뀐다는 말이 이런 이유에서 이다.



### naljin님 블로그

여기에서 Subject 가 왜 Observer인가에 대해서 의문을 가졌는데 naljin님께서 블로그에 잘 정리를 해주셨다. Subject를 보면 ObservableType 그리고 ObserverType 프로토콜을 둘 다 채택하고 있다. 따라서 Observer이기 때문에 on 메서드를 통해 이벤트를 넘기는 것이 가능했고, ObservableType이기 때문에 구독을 통해서 방출된 아이템에 대응하는 것이 가능해진 것이다. 

이 부분은 조금 더 살펴봐야 겠다.



### Reference

http://reactivex.io/documentation/subject.html

https://sujinnaljin.medium.com/rxswift-subject-99b401e5d2e5