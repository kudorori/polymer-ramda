# polymer-ramda

# Description

單純想將Ramda綁定到Polymer中方便使用而已，相關的Method直接參考[Ramda Documents](http://ramdajs.com/)

# Example

> 怕會與原有Method衝突，故有關於Ramda的Method皆有加上`R_`前綴詞

```
<dom-module id="hello-test">
  <template>
    <style>
    </style>
    [[R_prop("hi", obj)]]
    [[R_propOr("我是預設值","bar", obj)]]
    <div>
      <div>
        obj2array
      </div>
      <template is="dom-repeat" items="[[R_toPairs(obj)]]">
        <div>
          [[item.0]] / [[item.1]]
        </div>
      </template>
    </div>
  </template>
  <script>
    customElements.define("hello-test", class extends polymerRamda(Polymer.Element){
      static get is() { return "hello-test"; }
      static get properties() {
        return {
          obj: {
            type: Object,
            value: {
              hi: "你好",
              a1: 0,
              a2: 1,
              a3: 2
            }
          }
        }
      }
      static get observers() {
        return []
      }
      constructor() {
        super();
      }
      connectedCallback() {
        super.connectedCallback();
      }
      disconnectedCallback(){
        super.disconnectedCallback();
      }
      ready() {
        super.ready();
      }
    })
  </script>
</dom-module>

```
