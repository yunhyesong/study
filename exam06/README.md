# exam06 정리

## formcheck.html

* checkbox, radio처리시 .change() 되었을 때 이벤트 제어하는 것이 좋다.
* label이 아닌 input에 이벤트를 주는 것이 맞다. 

 ```javascript
 // .change() 사용 예시
 // input이 change되었을 때 이벤트가 일어나도록 한다.
  this._checkInput.on('change', $.proxy(this._onClickForm, this));
 ```

* .is() vs .prop() vs .attr()

	* `.is()` : 셀렉터의 대상을 다시 셀렉터로 비교하여 맞으면 true 아니면 false 를 반환
	* `.prop()` : Javascript 와 관련된 것을 탐색 시 이용 (prop는 dom객체 속성(Property)으로 접근)
	* `.attr()` : html에 관련된 것을 탐색 시 이용 (attr는 html 마크업 특성(Attribute)으로 접근)

* target을 label로 잡아 이벤트를 발생시킬 때, e.preventDefault(); 처리를 하면 input의 checked를 막아 실제로 입력 값이 체크되지 않는다.

[번외] 	JQuery UI 의 Dialog 에서 checkbox 에 대한 버그가 존재한다. 
		checkbox 의 체크를 없을 때에는 상관이 없으나, 체크를 다시 할 때 체크가 되지 않는 문제가 (특정조건에서) 발생한다. 이는 Dialog 의 버그이며 $(개체).prop("checked", true); 로 checkbox 을 처리하면 문제없이 잘 작동한다. 
		($(개체).attr("checked", true); 로 체크를 해줄 때는 발생)

## sort.html

* .detach()와 .append() 메소드를 사용하여 develop하기
   (.remove() 메소드 사용 시 이벤트가 삭제되어 동작하지 않기 때문에 다시 걸어줘야한다.)
* 배열에 담아 처리해보도록 한다.