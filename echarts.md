# [echarts usage](http://echarts.baidu.com)
## Tutorial
```html
<script type="text/javascript">
    data () {
        return {
            mychart: null, //the needle which directs echart.
            defaultOption: {
                //This is the initial option of the echart.
            }
        }
    }
    mounted: function () {
        //please don't forget `this`!!! 
      this.mychart = echarts.init(document.getElementById('chart_all'))
      this.mychart.setOption(this.defaultOption)
      console.log('mounted called!!')        
    }
</script>
```
More details of Echarts in [example](http://echarts.baidu.com/examples.html)
More parameters of Echarts in [Gitbook](https://princess310.gitbooks.io/the-echarts-learn-book/content/series.html)
