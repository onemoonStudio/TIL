# Rx Document 3

### Scheduler

만약 Rx 환경에서 multithreading 을 고려한다면 Scheduler를 고려해야한다. 특히 폭포처럼 연쇄되는 Operator 사이에서 특정한 Scheduler로 해당 작업을 위임시킬 수 있다.

기본적으로 일련의 Observable이 일하는 작업이 실행되는 thread는 Subscribe가 호출된 thread와 동일하다. 이때 이를 다르게 할 수 있는 방법은 두가지가 있다.

1. SubscribeOn

이는 Observable이 어느 Scheduler에서 일을 하는지 결정하는 Operator이다. 쉽게 말해서 어떤 Scheduler 에서 작업을 시작할지 결정한다. 추가적으로 SubscribeOn 은 일련의 Operator 사이에 있더라도 상관없이 어떤 Scheduler에서 작업을 시작할지 결정할 수 있다.

2. ObserveOn

이 또한 마찬가지로 다른 Scheduler로 지정을 한다. 이는 observable이 observer로 noti를 전달 할때 schduler를 변경한다. ObserveOn의 경우 해당 Operator 이후에 작업이 실행되는 Scheduler를 변경하기 때문에 어떤 Operator 사이에서 실행되는지 그리고 그 이후에 어떤 Operator가 실행되는지 민감하다.



위와 같은 이유로 ObserveOn 의 경우 여러 포인트에서 여러번 실행시킬 수 있음을 확인할 수 있다.

![schedulers](http://reactivex.io/documentation/operators/images/schedulers.png)



### Reference

http://reactivex.io/documentation/scheduler.html

