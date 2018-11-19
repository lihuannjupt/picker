<template>
  <div id="app">
    <button class="button" @click="showDialog "  >点我</button>
     <awesome-picker 
     
      ref="picker"
      :subTitle="picker.subTitle"
      :textTitle="picker.textTitle"
      :data="picker.data"
      :anchor="picker.anchor"
      @confirm="handlePickerConfirm"
      @cancel="handlePickerCancel">
    </awesome-picker>
  </div>
</template>

<script>
import AwesomePicker from '../Index.vue'
const data1 = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']
const data2 = ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z']
export default {
  name: "App",
  data() {
    return {
      picker: {
        // subTitle: '多列选择器',
        anchor: [
              { 
                index: 0,
                value: 'A'
              },
              {
                index: 0,
                value: 'A-a'
              } 
        ],
        textTitle: '多列选择器',
        data: [
          {
            value: 'A',
            children: [
              { value: 'A-a' },
              { value: 'A-b' },
              { value: 'A-c' },
              { value: 'A-d' },
              { value: 'A-e' },
              { value: 'A-f' }
            ]
          },
          {
            value: 'b',
            children: [
              { value: 'B-a' },
              { value: 'B-b' },
              { value: 'B-c' },
              { value: 'B-d' },
              { value: 'B-e' },
              { value: 'B-f' }
            ]
          }
          ]
      }
    }
  },   
  methods: { 
    function1(obj) {
      console.log(obj)
    },
    showDialog() {
      this.$refs.picker.show()
    },
    handlePickerConfirm(v) {
      this.picker.anchor = v;
      this.value = v ? JSON.stringify(v) : null;
      console.log(v);
    },
    handlePickerCancel() {
      console.log("this.value");
    },
  },
  components: {
    AwesomePicker
  }
}

</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #fff;
}
* {
  margin: 0px;
  padding: 0px;
  /* background-color: #f1f2f6 */
}
.button {
  background-color: #ff4433;
  width: 80px;
  height: 40px;
  margin: 50px;
}

</style>