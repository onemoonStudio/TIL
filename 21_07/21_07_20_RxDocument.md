# Rx Document 1

### Observable

Observer 는 Observable을 subscribe 한다. 용어가 헷갈리니 이 관계를 잘 알아두자. Observer는 이후 Observable이 방출하는 이벤트 혹은 시퀀스(이벤트들)에 대해서 반응을 한다.

- 따라서 Rx는 어떻게 동작하는가에 대해서 물어본다면 Observer가 이벤트를 방출하는 Observable을 구독함으로써 방출하는 이벤트에 대해서 처리하는 것이 Rx의 동작 방식이다 라고 할 수 있겠다.

이러한 패턴을 사용하는 가장 큰 이유는 동시적인 프로그래밍에서 유용하기 때문이다. 이유는 방출하는 이벤트를 blocking을 통해서 기다리지 않고, observer라는 대리자를 통해서 방출되는 이벤트를 받아 적절하게 처리하는 로직을 작성하기 때문이다.



### Hot Observable vs Cold Observable

Observable은 언제 이벤트를 방출하는가? 이는 Observable에 달려있다.

Hot Observable은 생성과 동시에 이벤트를 방출하는 Observable을 말한다. 따라서 나중에 hot Observable을 구독한다는 것은 Observable의 중간부터 참여한다는 것을 의미한다.

반면에 Cold Observable은 구독이 되기 전까지 이벤트를 방출하지 않는다. 이후 Observer가 구독을 하게 되면 비로소 이벤트를 방출하는 Observable을 말한다. 따라서 이를 구독한다는 것은 Observable의 event sequence 전체를 확인할 수 있음을 보장한다.



### Single

Single은 Observable과 비슷하지만 단 하나의 이벤트를 방출하는 Observable 이다. 즉 하나의 값을 보내거나 하나의 에러를 보낸다.

따라서 Observable 과 다르게 2개의 메서드 onSuccess, onError 만 처리하면 된다.

Single은 위의 메서드를 단 한번만 호출한다, 다시말해서 하나의 이벤트만 방출한다. 따라서 이벤트가 방출이 된다면 구독을 끊는 특성을 가지고 있다.



### Reference

http://reactivex.io/documentation/observable.html

http://reactivex.io/documentation/single.html

