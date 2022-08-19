# Chapter 39

<pre>1. HTMLCollection과 NodeList는 DOM API가 여러 개의 결과값을 반환하기 위한
DOM 컬렉션 객체입니다. 둘다 유사 배열 객체이면서 이터러블입니다. 둘의 차이가 뭘까요?</pre>

<details>
  <summary>Solution</summary>
  <pre>HTMLCollection 객체는 노드 객체의 상태 변화를 실시간으로 반영하는 살아 있는(live)<br/>DOM 컬렉션 객체입니다. 반대로 NodeList는 노드 객체의 상태 변경을 실시간으로 반영하지 않고 결과값을<br/>반환할때 그 상태를 정적으로 유지하는 죽은 (non-live) 객체로 동작합니다.하지만 안전하게 사용하려면<br/>둘다 Spread syntax 혹은 Array.from을 통해서 배열로 만들어 사용하라 하네요. (page 699)</pre>
</details>

<br>

<pre>2. HTML에서 Node와 Element 인터페이스를 상속받은 한 요소의 자식 요소를 탐색하려고 한다. 해당 노드를 반환하는건 같으나 차이점이 무엇일까요?</pre>

```js
Node.prototype.childNodes
Node.prototype.firstChild
Node.prototype.lastChild
------------------------------
Element.prototype.children
Element.prototype.firstElementChild
Element.prototype.lastElementChild
```

<details>
  <summary>Solution</summary>
  <pre>1. Node 인터페이스를 통한 탐색은 해당 자식 노드를 탐색하여 NodeList에 담아 반환을 합니다.<br/>   Element 인터페이스는 HTMLCollection에 담아 반환하죠.<br/><br/>2. Node 인터페이스는 요소노드뿐만 아니라 텍스트 노드도 포함되어 있을 수 있습니다.<br/>   하지만 Element 인터페이스는 텍스트 노드까지 반환하지 않아요.  </pre>
</details>

<br>

<pre>3. 프로토타입 체인 관점에서, 파싱하여 객체화한 ul 요소 노드 객체에 바인딩된<br/>prototype을 모두 작성하세요.</pre>

<details>
  <summary>Solution</summary>
  <pre>HTMLUListElement, HTMLElement, Element, Node, EventTarget, Object의<br/>prototype에 바인딩되며 프로토타입 객체를 상속받는다.</pre>
</details>

<br>

<pre>4. Node.prototype.hasChildNodes 메서드는 자식 노드의 존재 유무에 따라 boolean을 반환하는데,<br>이때 텍스트 노드를 포함하여 자식 노드의 존재를 확인한다.<br>자식 노드 중에 텍스트 노드가 아닌 요소 노드가 존재하는지 확인할때 사용하는 프러퍼티를 작성하세요.</pre>

<details>
  <summary>Solution</summary>
  <pre>children.length 또는 Elemnent 인터페이스의<br> childElementCount 프러퍼티를 사용한다.</pre>
</details>

<br>