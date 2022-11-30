<template>
  <ejs-bulletchart :dataSource="sprintData"
    valueField="completedStories"
    targetField="requiredStories"
    :minimum="5"
    :maximum="45"
    :interval="5"
    width="80%"
    height="400"
    categoryField="name"
    title="Sprint Planning"
    subtitle="Estimated in story points"
    :minorTickLines="minorTickLine"
    :majorTickLines="majorTickLine"
    :legendSettings="legend"
    :tooltip="tooltipSettings"
    orientation="Vertical">
      <ejs-ranges>
        <ejs-range end="25" color="#DBE7F3"></ejs-range>
        <ejs-range end="37" color="#BBCEE7"></ejs-range>
        <ejs-range end="45" color="#96B2D7"></ejs-range>
      </ejs-ranges>
    </ejs-bulletchart>
</template>

<script>
import {BulletChartComponent, BulletRangeCollectionDirective, BulletRangeDirective,
  BulletChartLegend, BulletTooltip} from '@syncfusion/ej2-vue-charts';

export default {
  name: 'App',
  components: {
    'ejs-bulletchart': BulletChartComponent,
    'ejs-ranges': BulletRangeCollectionDirective,
    'ejs-range': BulletRangeDirective
  },
  provide:{
    bulletChart: [BulletChartLegend, BulletTooltip]
  },
  data(){
    return{
      minorTickLine:{ width:0 },
      majorTickLine:{ color:'blue'},
      legend:{ visible:true },
      tooltipSettings:{ enable:true },
      sprintData:[
        { 
          requiredStories: 20,
          completedStories: 25,
          name: 'David',
        },
        {
          requiredStories: 25,
          completedStories: 20,
          name: "Asif"
        },
        {
          requiredStories: 15,
          completedStories: 10,
          name: "Thomas"
        },
        {
          requiredStories: 40,
          completedStories: 39,
          name: "Rohit"
        },
        {
          requiredStories: 35,
          completedStories: 40,
          name: "Virat"
        },
      ]
    }
  }
}
</script>

<style>
@import url("https://cdn.syncfusion.com/ej2/bootstrap5.css");
#app{
  margin: 5%;
}
</style>
