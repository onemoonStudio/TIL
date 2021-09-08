# CleanCode 

## ch 11 시스템

복잡성은 죽음이다. 제품을 기획하고 제작하고 테스트 하기 어렵게 만든다. - MS CTO 



도시에는 큰 그림을 그리는 사람들이 있으며, 작은 사항에 집중하는 사람들도 있다. 이때 작은 사항에 집중하는 사람들은 큰 그림을 보지 못하더라도 도시는 효율적으로 돌아간다. 적절한 추상화와 모듈화 덕분이다. 



준비 과정과 런타임 과정을 분리해야한다. 객체를 생성하는 것과 사용하는 것이 분리되어야 한다는 소리이다. 첫번째로 Lazy 는 과연 좋은 코드일까? 물론 사용전에 객체를 생성하지 않는 부분과, nil을 리턴하지 않는다는 점은 좋은 점이라고 할 수 있다. 하지만 사용되지 않는 객체에 의존성을 부여함에 따라서 변경이 조금씩 어려워질 수도 있다는 사실을 기억하자. 체계적이고 탄탄한 시스템을 만들고 싶다면 손쉬운 기법으로 모듈성을 깨서는 안된다.



사용과 제작을 분리하는 가장 강력한 메커니즘 하나가 바로 의존성 주입이다. 의존성 주입은 제어역전과 의존성 관리를 사용하는 개념인데, 제어 역전에서는 한 객체가 맡은 보조 책임을 새로운 객체에게 전적으로 떠넘긴다. 이때 새로운객체는 넘겨받은 책임만 다하면 되기 때문에 SRP를 지키게 된다. 의존성 관리는 어떨까? 객체는 의조성 자체를 인스턴스로 만드는 책임을 지지 않으며, 이를 다른 "전담" 메커니즘으로 넘긴다. 이러한 메커니즘이 우리가 흔히 부르는 컨테이너라고 할 수 있다.



확장에 대해서 생각해보자. 마을이 발전하면서 계속해서 도로를 넓힌다고 했을 때, 처음부터 크게 만들었으면 좋겠다는 생각을 할 수도 있다. 하지만 다시 생각해보면 작은 마을에 큰 도로가 생기는 것을 반길 사람이 있을까? 시스템은 적절하게 성장을 해야한다. 하지만 생각해야 할 부분은 단순한 아키텍쳐를 복잡한 아키텍쳐로 조금씩 키울 수 없다. 모듈을 나누고 관심사를 최대한 분리하도록 하자 그렇게 되면 지엽적인 관리와 결정이 가능해진다. 그리고 이러한 결정은 최대한 많은 고민과 함께 하는 것이 가장 좋다.