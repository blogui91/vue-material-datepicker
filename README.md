# vue-material-datepicker
Datepicker component with material design for Vue.js

# Demo
SOON

![Screenshot](screenshot.png)

# Requirements

- [Vue.js](https://github.com/yyx990803/vue) `^1.0.0`
- [moment](https://github.com/moment/moment) `^2.11.1`
- [lodash](https://github.com/lodash/lodash) `^4.5.0`
- [vue-touch](https://github.com/vuejs/vue-touch) `^1.0.2`

# Installation

## npm

```shell
$ npm install vue-datepicker
```

# Usage

```html
<!-- your component -->
<script>
import mdDatepicker from 'vue-material-datepicker'
export default {
  data() {
      return {
        options: {
          lang : 'en',
          startsOnSunday: false,
          format:'YYYY-MM-DD'
          btnStrOk : 'Ok',
          btnStrCancel : 'Cancel',
          overlayOpacity : 0.5, //0.5 as default
          dismissible : true //as true as default
          //format:"YYYY-MM-DD HH:mm:ss"
        },
        limit:[{
            type: 'weekday',
            available: [1,2,3,4,5]
          },
          {
           type:'fromto',
           from:'2016-02-01',
           to:'2016-02-20'
          }]
      }
    },
    components: {
      'md-datepicker': mdDatepicker
    }
}
</script>
<template>
  <div class="card">
    <div class="row">
      <span>Event datetime：</span>
      <md-datepicker type="datetime" :model.sync="starttime" :options="option" :limit="limit"></md-datepicker>
    </div>
    <div class="row">
      <span>Event  all day：</span>
      <md-datepicker type="date" :model.sync="endtime" :options="option"></md-datepicker>
    </div>
    <div class="row">
      <span>time：</span>
      <md-datepicker type="date" :model.sync="testTime" :options="timeoption"></md-datepicker>
    </div>
  </div>
  <div class="test">
    Departure Date:{{starttime}}
    <br> Return Date：{{endtime}}
    <br> test Date：{{testTime}}
  </div>
</template>


```

# API


 - limit

 * from sometime to sometime

```javascript

limit: {
  type:'fromto',
  from:'2016-01-10',
  to:'2016-01-30'
}

```
 * weekdays

```javascript

limit:{
  type: 'weekday',
  available: [1, 2, 3, 4, 5] 
}

```

prop

```html

<md-datepicker :model.sync="starttime" :range="limit"></md-datepicker>

```

# License

[The MIT License](http://opensource.org/licenses/MIT)

