### 1. Promise의 기능과 필요한 이유에 대해서 설명해주세요.

- Promise는 자바스크립트에서 비동기 작업을 처리하기 위한 객체입니다. Promise는 비동기 작업이 완료될 때까지 기다리지 않고 다른 작업을 처리할 수 있도록 해주며, 비동기 작업이 완료되면 그 결과를 반환합니다.promise가 필요한 이유 중 첫번 째는 콜백 지옥을 방지하기 위함입니다. 콜백 지옥은 콜백 함수가 중첩되어 복잡한 코드가 되는 현상을 말합니다. Promise를 사용하면 비동기 작업을 간결하게 처리할 수 있어 콜백 지옥을 방지할 수 있습니다. 두번 째는 에러 핸들링을 쉽게 하기 위함입니다. Promise는 then() 메서드와 catch() 메서드를 제공하여 에러 핸들링을 쉽게 할 수 있습니다. 마지막으로 코드 가독성을 높이기 위함입니다. Promise를 사용하면 비동기 작업을 연속적으로 처리할 수 있어 코드 가독성을 높일 수 있습니다.

### 2. 얕은 복사와 깊은 복사에 대해서 설명해주세요.

- 얕은 복사와 깊은 복사는 객체나 배열을 복사할 때, 사용되는 방식으로, 복사된 객체나 배열이 원본 객체나 배열과 어떻게 연관되어 있는가에 따라 구분됩니다. 얕은 복사는 원본 객체, 배열과 복사된 객체, 배열이 같은 메모리 주소를 참조하는 방식입니다. 즉, 복사된 객체나 배열에서 원본 객체, 배열의 값을 수정하면, 원본 객체, 배열도 영향을 받게 됩니다. 이는 객체, 배열의 크기가 큰 경우, 복사 시간을 절약할 수 있어서 유용합니다. 깊은 복사는 원본 객체, 배열과 복사된 객체, 배열이 서로 다른 메모리 주소를 참조하는 방식입니다. 즉, 복사된 객체, 배열에서 원본 객체, 배열의 값을 수정해도, 원본 객체, 배열은 영향을 받지 않습니다. 이는 객체, 배열 내부에 또 다른 객체, 배열이 있는 경우, 원본 객체나 배열의 값을 유지하면서 복사본을 생성할 때 사용합니다.

### 3. 클로저에 대해 설명해주세요.

- 클로저는 내부함수가 외부함수의 변수에 접근할 수 있는 것을 의미합니다. 즉, 클로저는 해당 함수가 선언된 시점의 유효범위 내에 있는 변수들에 접근할 수 있습니다. 이는 함수가 호출될 때마다 새로운 스코프가 생성되는 JavaScript의 동작 중 하나입니다. 클로저를 이용하면, 함수 내부의 변수를 외부에서 직접 접근할 수 없게 되므로, 정보 은닉 및 보안에 유용하게 사용될 수 있습니다.

### 4. 브라우저 렌더링 방식에 대해 설명하세요.

- 사용자가 특정 페이지에 접속하여 HTML을 서버로부터 내려받으면, 브라우저의 렌더링 엔진에서는 이를 파싱합니다. HTML 파싱을 진행하면서, DOM 트리를 만들게 되는데, 이 때 Link 태그를 만나 StyleSheet를 내려받게 될 경우 CSS 파싱을 통해 CSSOM 트리를 만들게 됩니다. 이 일련된 과정을 통해 둘을 결합하여 렌더 트리를 만들고, 레이아웃 작업을 통해 사용자에게 그려줄 영역을 계산한 뒤, 화면에 보여줍니다. 위 과정을 진행하면서 자바스크립트를 만나면, 자바스크립트 런타임 환경에 수행권한을 넘겨 결과 값을 받습니다. 이 과정 중, DOM파싱은 중단되고, 생성된 DOM 노드의 레이아웃의 수치를 변경할 시 영향 받은 모든 노드의 수치를 재계산하여, 렌더 트리를 재생성하는 과정을 Reflow 과정이라고하며, 이 과정이 끝난 후 재생성된 렌더 트리를 다시 그리게 되는데 이 과정을 Repaint라고 합니다. reflow가 이루어졌다고 항상 repaint가 되는 것은 아니며, background-color, visibillty, outline 등 레이아웃 수치에 영향을 끼치지 않는 것은 repaint 과정만 진행됩니다.

### 5. 자바스크립트 엔진의 콜 스택이 무엇인지 설명할 수 있나요?

- 콜 스택은 자바스크립트 엔진에서 함수가 호출되는 순서를 추적하는 데 사용되는 데이터 구조입니다. 스택은 후입선출 구조를 가지고 있어 가장 최근에 호출된 함수가 맨 위에 있고 가장 오래된 함수가 맨 아래에 있습니다. 함수를 호출하면 콜 스택에 푸시되고 함수가 반환되면 콜 스택에서 팝(제거)됩니다. 콜 스택은 자바스크립트 엔진이 함수 호출의 순서를 추적하고 함수 내부에서 변수와 객체에 대한 액세스를 관리하는 데 사용됩니다.

### 6. JavaScript는 싱글 스레드입니다. 어떻게 싱글 스레드 방식으로 비동기 호출을 할 수 있는 지에 대해 설명할 수 있나요?

- JavaScript는 싱글 스레드 언어이지만 비동기 호출을 할 수 있습니다. 이는 이벤트 루프를 사용하여 수행됩니다. 이벤트 루프는 자바스크립트 엔진에서 비동기 이벤트를 처리하는 데 사용되는 스레드입니다. 이벤트 루프는 항상 실행 중이며 키보드 입력, 마우스 클릭 및 네트워크 요청과 같은 이벤트를 기다리고 있습니다. 이벤트가 발생하면 이벤트 루프는 해당 이벤트를 처리하기 위해 호출할 함수를 대기열에 추가합니다. 함수가 이벤트 루프에 의해 호출되면 콜 스택에 푸시됩니다. 함수가 완료되면 콜 스택에서 팝(제거)되고 이벤트 루프는 다음 이벤트를 기다립니다. 이벤트 루프를 사용하여 비동기 호출을 하면 메인 스레드가 차단되지 않습니다. 즉, 메인 스레드는 사용자 인터페이스를 업데이트하고 사용자 입력을 처리하는 등의 다른 작업을 계속 수행할 수 있습니다.

### 7. Event Loop에 대해 설명할 수 있나요?

- 이벤트 루프는 자바스크립트 엔진에서 비동기 이벤트를 처리하는 데 사용되는 루프입니다. 이벤트 루프는 항상 실행 중이며 키보드 입력, 마우스 클릭 및 네트워크 요청과 같은 이벤트를 기다리고 있습니다. 이벤트가 발생하면 이벤트 루프는 해당 이벤트를 처리하기 위해 호출할 함수를 대기열에 추가합니다. 함수가 이벤트 루프에 의해 호출되면 콜 스택에 푸시됩니다. 함수가 완료되면 콜 스택에서 팝(제거)되고 이벤트 루프는 다음 이벤트를 기다립니다. 이벤트 루프를 사용하여 비동기 호출을 하면 메인 스레드가 차단되지 않습니다. 즉, 메인 스레드는 사용자 인터페이스를 업데이트하고 사용자 입력을 처리하는 등의 다른 작업을 계속 수행할 수 있습니다.

### 8. 가비지 컬렉션이란 무엇이며 가비지 컬렉션을 가진 언어에는 무엇이 있나요?

- 가비지 컬렉션(GC)은 프로그램이 동적으로 할당했던 메모리 영역 중에서 더 이상 사용하지 않는 영역을 자동으로 해제하는 메모리 관리 기법입니다. GC는 프로그램이 메모리 관리에 신경쓰지 않고도 더 효율적으로 메모리를 사용할 수 있도록 하기 때문에 프로그래머에게 유용한 도구입니다. 그러나 GC는 프로그램에 지연 시간이 발생할 수 있고 GC 자체가 메모리 관리에 많은 오버헤드를 추가할 수 있다는 단점도 있습니다. 가비지 컬렉션을 지원하는 언어로는 Java, C#, Python, JavaScript, PHP 등이 있습니다.

### 9. AJAX는 무엇인가요?

- AJAX는 비동기 자바스크립트와 XML의 약자입니다. Ajax는 빠르게 동작하는 동적인 웹 페이지를 만들기 위한 개발 기법의 하나입니다. Ajax는 웹 페이지 전체를 다시 로딩하지 않고도, 웹 페이지의 일부분만을 갱신할 수 있습니다. 즉 Ajax를 이용하면 백그라운드 영역에서 서버와 통신하여, 그 결과를 웹 페이지의 일부분에만 표시할 수 있습니다.

### 10. 실행컨텍스트에 대해서 설명해주세요

- 컨텍스트는 자바스크립트 코드가 실행되는 환경입니다. 모든 JavaScript 코드는 실행 컨텍스트 내부에서 실행된다고 생각하면 됩니다. 즉 함수가 실행되면 함수 실행에 해당하는 실행 컨텍스트가 생성되고, 자바스크립트 엔진에 있는 콜 스택에 차곡차곡 쌓입니다. 그리고 가장 위에 쌓여있는 컨텍스트와 관련 있는 코드를 실행하면서, 전체 코드의 환경과 순서를 보장하게 됩니다. 실행 컨텍스트는 식별자(변수, 함수, 클래스 등의 이름)를 등록하고 관리하는 스코프와 코드 실행 순서 관리를 구현한 내부 매커니즘입니다. 실행 컨텍스트는 함수가 호출될 때 생성되고 함수가 종료될 때 파괴됩니다. 함수가 호출되면 실행 컨텍스트가 콜 스택에 푸시되고 함수가 종료되면 실행 컨텍스트가 콜 스택에서 팝됩니다.

### 11. var vs let vs const 차이를 설명해주세요

- var, let, const는 자바스크립트에서 변수를 선언하는 데 사용할 수 있는 세 가지 키워드입니다. var는 변수 선언에 사용되는 가장 오래된 키워드입니다. var로 선언된 변수는 함수 범위가 있으며 선언된 모든 블록에 액세스할 수 있습니다. let는 변수 선언에 사용되는 최신 키워드입니다. let로 선언된 변수는 블록 범위가 있으며 선언된 블록 내에서만 액세스할 수 있습니다. const는 상수 선언에 사용되는 키워드입니다. const로 선언된 변수는 값을 변경할 수 없습니다.

### 12. 호이스팅이란 무엇인가요?

- JavaScript에서 호이스팅은 변수와 함수의 선언이 코드의 최상단으로 이동되는 것입니다. 즉, 변수나 함수를 선언하기 전에 사용할 수 있습니다. 또한 호이스팅은 JavaScript의 강력한 도구입니다. 호이스팅을 사용하면 코드를 더 간결하고 이해하기 쉽게 만들 수 있습니다.

### 13. object 관련 메서드

- Object.create()

  주어진 프로토타입(prototype)의 객체와 속성들을 갖고 있는 새 객체를 생성합니다.

- Object.assign()

  하나 이상의 원본 객체들로부터 모든 열거가능한 속성들을 대상 객체로 복사합니다.

- Object.keys()

  객체의 키만 담은 배열을 반환합니다.

- Object.values()

  객체의 값만 담은 배열을 반환합니다.

- Object.entries()

  [키, 값] 쌍을 담은 배열을 반환합니다.

  보통 객체를 이차원 배열로 변환하고 Map자료형으로 만들때 사용

- Object.fromEntries()

  [키, 값] 형태의 배열을 객체로 반환합니다.

- Object.is()

  두 값이 같은지를 비교합니다.

  모든 NaN 값은 같다고 처리됩니다

- Object.freeze() / Object.isFrozen()

  객체를 프리징(freeze)합니다. 즉, 다른 곳의 코드에서 객체의 속성을 지우거나 바꿀 수 없습니다.

  객체가 프리징 되었는지 확인합니다.

​- Object.seal() / Object.isSealed()

다른 코드가 객체의 속성을 삭제하지 못하도록 합니다.

객체가 실링(seal) 되었는지 확인합니다.

​- Object.getPrototypeOf()

명시된 객체의 프로토타입을 반환.

​- Object.setPrototypeOf()

프로토타입(즉, 내부의 [[Prototype]] 속성)을 설정합니다.

​- Instanceof

해당 변수가 객체인지 비교하거나, 객체가 특정 생성자의 자식인지 조회할 수 있습니다.
