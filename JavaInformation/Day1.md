### 더 알아가기 - ☀️Map과 HashMap의 차이☀️
- `Map`이란❓
  - Map 인터페이스는 키(Key)와 값(Value)으로 이루어진 데이터의 집합이다. 
  - 순서가 유지되지 않으며, 중복을 허용하지 않는다. 즉, 한개의 Key에 한개의 Value 값이 매칭된다.
  - 이 인터페이스를 구현한 대표적인 클래스들로는 HashMap, TreeMap, LinkedHashMap 등이 있다.
- `HashMap`이란❓
  - HashMap 은 Map Interface 를 Implements 한 클래스로서 중복을 허용하지 않는다.
  - Map의 특징인 Key 와 Value 의 쌍으로 이루어지며, key 또는 value 값으로써 `null` 을 허용한다.
  - 즉, HashMap은 Map이라는 interface의 구현체(implemetents)인 것이다.
- 여기서 드는 의문점🧐
  - Map과 HashMap을 선언 및 생성할 때 `Map<String, Integer> photo =  new Map<>();` 또는 `HashMap<String, Integer> photo = new HashMap<>();` 이렇게 구현될 것이라고 생각했었다.
  - 하지만 다른 사람들의 코드를 보고 이유를 제대로 알지 못한 채 `Map<Long,Member> store = new HashMap<>();` 이렇게 생성하여 종종 사용했었는데 이렇게 사용하는 이유를 한번 살펴보자.
  - 이유💁🏼
    - Map 인터페이스의 제약을 따르겠다는 의도를 명확하게 드러낸다.
    - 사용하는 코드가 Map 인터페이스 제약을 따르기 때문에 향후 변경시에 사용코드를 변경하지 않아도 된다. -> HashMap을 다른 클래스로 변경이 필요하면 선언하는 코드만 변경하면 된다. 이미 사용되고 있는 코드는 수정 할 필요가 없다.
    - 나중에 더 성능이 좋거나 동시성 처리가 가능한 구체적인 Map으로 변경해야 할 떄 `HashMap<String, Integer> photo = new HashMap<>();`으로 되어있다면 상당히 많은 고민을 해야하지만 `Map<Long,Member> store = new HashMap<>();`로 되어있다면 선언부만 변경해주면 된다.
    - 만약 HashMap에 구체적인 기능을 사용해야 한다면 `HashMap<String, Integer> photo = new HashMap<>();`으로 선언하는 것이 맞다.

