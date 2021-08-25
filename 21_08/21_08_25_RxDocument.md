# Rx Document 3

### Scheduler

만약 Rx 환경에서 multithreading 을 고려한다면 Scheduler를 고려해야한다. 특히 폭포처럼 연쇄되는 Operator 사이에서 특정한 Scheduler로 해당 작업을 위임시킬 수 있다.

기본적으로 일련의 Observable이 일하는 작업이 실행되는 thread는 Subscribe가 호출된 thread와 동일하다. 이때 이를 다르게 할 수 있는 방법은 두가지가 있다.

1. SubscribeOn

이는 Observable이 어느 Scheduler에서 일을 하는지 결정하는 Operator이다.

2. ObserveOn

이 또한 마찬가지로 다른 Scheduler로 지정을 한다. 이는 observable이 observer로 noti를 전달 할때 schduler를 변경한다.

### Reference

http://reactivex.io/documentation/scheduler.html

