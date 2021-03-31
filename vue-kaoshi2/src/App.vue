<template>
    <div class=''>
      <com @sss="sss" :show="show"></com>
      <div>
        <span v-show="show == 1 ">商品</span>
        <span v-show="show == 2 ">价格</span>
        <span v-show="show == 3 ">数量</span>
        <span v-show="show == 4 ">图片</span>
        <input type="text" v-show="show == 1" v-model="value">
        <input type="text" v-show="show == 2" v-model="value1">
        <input type="text" v-show="show == 3" v-model="value2">
        <input type="text" v-show="show == 4" v-model="value3">
      </div>
      <span @click="shang">上一步</span>
      <span @click="xia" v-if="this.show != 4">下一步</span>
      <span @click="ok" v-else>完成</span>
      <div v-show="showok">商品：{{this.obj.name}}</div>
      <div v-show="showok">价格：{{this.obj.price}}</div>
      <div v-show="showok">数量：{{this.obj.num}}</div>
      <div v-show="showok">图片：{{this.obj.url}}</div>
      <button @click="del" v-show="showok">清空</button>
    </div>
</template>

<script>
import com from './components/com'
export default {
    data() {
        return {
          value:'',
          value1:'',
          value2:'',
          value3:'',
          show:1,
          xia1:'下一步',
          obj:{
            name:'',
            url:'',
            price:'',
            num:''
          },
          showok:false
        };
    },
    components:{
      com,
    },
    mounted() {},
    methods: {
      xia() {
        if(this.value == ''&&this.show==1) {
          alert('内容不能为空')
          return 
        }
        if(this.value1 == ''&&this.show==2) {
          alert('内容不能为空')
          return 
        }
        if(this.value2 == ''&&this.show==3) {
          alert('内容不能为空')
          return 
        }
        if(this.value3 == ''&&this.show==4) {
          alert('内容不能为空')
          return 
        }
        
        if(this.show == 4) {
          this.show = 4
        } else {
          this.show += 1
        }
      },
      ok() {
        this.showok = true
        console.log(this.value);
          this.obj.name = this.value
          this.obj.price = this.value1
          this.obj.url = this.value2
          this.obj.num = this.value3
          
      },
      shang() {
        if(this.value == ''&&this.show==1) {
          alert('内容不能为空')
          return 
        }
        if(this.value1 == ''&&this.show==2) {
          alert('内容不能为空')
          return 
        }
        if(this.value2 == ''&&this.show==3) {
          alert('内容不能为空')
          return 
        }
        if(this.value3 == ''&&this.show==4) {
          alert('内容不能为空')
          return 
        }
        
        if(this.show == 1) {
          this.show = 1
          this.xia1 = ''
        } else {
          this.xia1 = '下一步'
          this.show -= 1
        }
      },
      del() {
        this.showok = false
          this.obj.name = ''
          this.value = ''
          this.obj.price = ''
          this.value1 = ''
          this.obj.url = ''
          this.value2 = ''
          this.obj.num = ''
          this.value3 = ''
          this.show = 1
      },
      sss(id) {
        if(this.value == ''&&this.show==1) {
          alert('内容不能为空')
          return 
        }
        if(this.value1 == ''&&this.show==2) {
          alert('内容不能为空')
          return 
        }
        if(this.value2 == ''&&this.show==3) {
          alert('内容不能为空')
          return 
        }
        if(this.value3 == ''&&this.show==4) {
          alert('内容不能为空')
          return 
        }
        this.show = id
        console.log(id);
      }
    },
};
</script>

<style>
 .red {
  color: green;
 }
</style>
