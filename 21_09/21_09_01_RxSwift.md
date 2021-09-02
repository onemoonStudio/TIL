# RxSwift



## Observable 실행 및 lazy 생성

Observable은 subscribe, 즉 구독을 하기 전까지는 아무런 일을 하지 않는다. 따라서 어떤 Observable을 리턴하는 함수를 만들어서 해당 함수를 사용하더라도 실제로 구독 전에는 해당 함수의 작업이 실행되지 않는 것이다.

만약 구독 이후에 어떤 Observable에 대해서 생성을 하고 싶다면 ( Swift Lazy 처럼 ) Observable.deferred 를 한번 살펴보도록 하자.

## RxSwift의 구독과 해지

Subscribe 는 구독을 하는데 disposebag이라는 특별한 반환객체가 있다. 이는 disposable로써 구독의 해지에 대해서 깊은 연관이 있다. 이를 제대로 신경쓰지 않으면 실제로 필요가 없더라도 구독이 계속해서 진행될 수 있기 때문이다.

각각의 disposable에 대해서 dispose를 할 수 있다. 하지만 여러개의 구독을 한번에 끊기에는 아무래도 많은 수고가 들어가게 되기 때문에 다른 방식을 사용해야 한다. 이때 사용하는 것이 disposed라는 메서드와 DisposeBag이다. disposed(bag:) 메서드에서 파라미터에 들어간 bag에 자기자신 (disposable)을 Insert한다. 이렇게 되면 disposable들이 disposebag에 등록이 되고 해당 bag이 dispose된다면 연결된 disposable들은 모두 구독이 해지된다.

이때 disposebag을 let으로 선언할 수도 있으나 var로 선언하는 것이 조금 더 활용도가 높다. 이유는 해당 객체가 사라지면 구독이 사라지기 때문에 만약 구독을 초기화 하고 싶은 경우 새로운 disposebag을 넣기만 하면 되기 때문이다.

## Ref

https://rhammer.tistory.com/286?category=649741

https://magi82.github.io/ios-rxswift-03/