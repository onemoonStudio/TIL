# DesignPattern

헷갈리는 두가지 패턴에 대해서 공부를 해보자.

- Factory Method Pattern
- Abstract Factory Pattern

## Factory Method Pattern

객체를 생성하기 위해 인터페이스를 정의하지만, 어떤 클래스의 인스턴스를 생성할지에 대한 결정은 서브클래스가 내리도록 한다. 즉 객체의 생성을 캡슐화 한다.



이때 객체의 생성을 담당하는 모든 객체가 Factory Method를 따르는 것은 아니며, 구현상으로의 차이가 있을 수 있다. 또한 팩토리 메서드 내부에서 분기가 처리되는 것이 어색해 보일 수 있으나, 핵심은 그런 분기처리를 외부에서 하는 것이 아닌 Factory 에서 한다는 것이고 활용에 따라서 Factory Method로 생성할 수 있는 여러 객체타입을 하나로 묶는다면 용이한 관리가 가능해진다.



예를 들어서 음악 재생 앱을 만든다고 하자 그리고 추후에 동영상을 플레이 해야한다. 이때 음악 및 동영상을 팩토리 메서드로 생성 한다면 동영상 또한 용이하게 생성하고 관리할 수 있다는 말이다. 음악이 만들어지거나 플레이 함수 등은 공통적으로 관리하면 되기 때문이다.



## Abstract Factory Pattern

상세화된 서브클래스를 정의하지 않고도 서로 관련성이 있거나 독립적인 여러 객체의 군을 생성하기 위한 인터페이스를 제공한다. 이는 객체가 생성되거나 구성, 표현되는 방식과 시스템을 독립적으로 만들고자 할 때 가장 좋다. 혹은 여러 제품군을 사용하는데 제품군의 변경이 잦아질 수 있는 경우도 마찬가지이다. 또한 관련된 객체들의 생성을 일괄적으로 처리하고 싶은 경우 사용하기 좋다.

생각보다 개념이 복잡해서 글보다는 그림을 보거나, 코드를 직접 작성하는 것이 나을 듯 하다. 이 부분은 한번 직접 해봐야겠다.



### Reference

https://johngrib.github.io/wiki/factory-method-pattern/

https://ko.wikipedia.org/wiki/팩토리_메서드_패턴

https://johngrib.github.io/wiki/abstract-factory-pattern/

https://ko.wikipedia.org/wiki/추상_팩토리_패턴