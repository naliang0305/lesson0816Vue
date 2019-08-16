<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>網頁</h1>
    <test></test>
    <ve-histogram v-bind:data="chartData"></ve-histogram>
    <ve-line :data="chartData"></ve-line>
    <div class="btn" v-on:click="changeData">改變資料</div>
  </div>
</template>

<script>
import test from './components/test'
import VeHistogram from 'v-charts/lib/histogram.common'
import VeLine from 'v-charts/lib/line.common'
export default {
  name: 'app',
  data(){
    return{
        chartData: {
          columns: ['日期', '访问用户', '下单用户', '下单率'],
          rows: [
            { '日期': '1/1', '访问用户': 1393, '下单用户': 1093, '下单率': 0.32 },
            { '日期': '1/2', '访问用户': 3530, '下单用户': 3230, '下单率': 0.26 },
            { '日期': '1/3', '访问用户': 2923, '下单用户': 2623, '下单率': 0.76 },
            { '日期': '1/4', '访问用户': 1723, '下单用户': 1423, '下单率': 0.49 },
            { '日期': '1/5', '访问用户': 3792, '下单用户': 3492, '下单率': 0.323 },
            { '日期': '1/6', '访问用户': 4593, '下单用户': 4293, '下单率': 0.78 }
          ]
          
        }
        
    }     
  },
  components:{
    test,
    VeHistogram,
    VeLine
  },
  methods:{
    changeData: function(){
      this.chartData.rows[0].访问用户 += 100
    }
  }

}
</script>

<style>
.btn{
  width: 70px;
  margin: 0 auto;/*傳統置中*/
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 5px 10px;
  cursor:pointer;
  background-color: yellow;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
