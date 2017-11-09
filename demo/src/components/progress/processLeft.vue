<template>
  <div class="Progress_left" style="text-align: left;" @mousemove="change_item">
    <span v-for="(item, index) in small_col" v-bind:key="item.name" class="small_item" :index="index" v-bind:class="[
          map[item.type],  
          curHoverClass.indexOf(map[item.type]) > 0  ? 'active': ''
        ]">
        &nbsp;  
      </span>
    <div style="clear:both">
      {{content}}
    </div>
  </div>
</template>

<script>
  import _ from "lodash"
  export default {
    data() {
      return {
        map: {
          'error': 'small_error',
          'success': 'small_success',
          'warn': 'small_warn'
        },
        small_col: [],
        content: '',
        curHoverClass: ''
      };
    },
    created() {
      let data = _.groupBy([{
          name: 'success18',
          type: 'success'
        },
        {
          name: 'success19',
          type: 'success'
        },
        {
          name: 'success20',
          type: 'success'
        },
        {
          name: 'error1',
          type: 'error'
        },
        {
          name: 'success1',
          type: 'success'
        },
        {
          name: 'warn1',
          type: 'warn'
        },
        {
          name: 'error2',
          type: 'error'
        },
        {
          name: 'error3',
          type: 'error'
        },
        {
          name: 'success2',
          type: 'success'
        },
        {
          name: 'warn2',
          type: 'warn'
        },
        {
          name: 'error5',
          type: 'error'
        },
        {
          name: 'error6',
          type: 'error'
        },
        {
          name: 'success3',
          type: 'success'
        },
        {
          name: 'warn3',
          type: 'warn'
        },
        {
          name: 'error7',
          type: 'error'
        },
        {
          name: 'error8',
          type: 'error'
        },
        {
          name: 'success4',
          type: 'success'
        },
        {
          name: 'error9',
          type: 'error'
        },
        {
          name: 'error10',
          type: 'error'
        },
        {
          name: 'success5',
          type: 'success'
        },
        {
          name: 'warn4',
          type: 'warn'
        },
        {
          name: 'success9',
          type: 'success'
        },
        {
          name: 'success10',
          type: 'success'
        },
        {
          name: 'error4',
          type: 'error'
        },
        {
          name: 'success11',
          type: 'success'
        },
        {
          name: 'error11',
          type: 'error'
        },
        {
          name: 'success16',
          type: 'success'
        },
        {
          name: 'success17',
          type: 'success'
        },
        {
          name: 'error12',
          type: 'error'
        },
        {
          name: 'success6',
          type: 'success'
        },
        {
          name: 'warn5',
          type: 'warn'
        },
        {
          name: 'error13',
          type: 'error'
        },
        {
          name: 'success7',
          type: 'success'
        },
        {
          name: 'success8',
          type: 'success'
        },
        {
          name: 'success12',
          type: 'success'
        },
        {
          name: 'success13',
          type: 'success'
        },
        {
          name: 'success14',
          type: 'success'
        },
        {
          name: 'success15',
          type: 'success'
        },
      ],item=>item.type)
      var arr = []
      for (let key in data) {
        arr = arr.concat(data[key])
      }
      this.small_col = arr
    },
    methods: {
      change_item(e) {
        const target = e.target
        const className = target.className
        const index = target.getAttribute('index')
        const item = this.small_col[index]
        this.curHoverClass = className
        this.content = item && item.name
      }
    }
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .Progress_left {
    height: 100%;
    width: 100%;
    border-left: 1px solid #000;
    margin-left: -1px;
  }
  .small_error {
    background: #ed1941;
  }
  .small_warn {
    background: #ffd400;
  }
  .small_success {
    background: #bed742;
  }
  .small_item {
    width: 25px;
    height: 25px;
    display: inline-block;
    border-right: 1px solid #000;
    border-top: 1px solid #000;
  }
  .small_item:first-child {
    border-left: 0px solid #000;
    border-bottom: 0px solid #000;
  }
  .small_item:hover {
    opacity: 0.3;
  }
  .active {
    opacity: 0.6;
  }
</style>
