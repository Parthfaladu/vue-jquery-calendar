# vue-jquery-calendar
[![npm version](https://badge.fury.io/js/vue-jquery-calendar.svg)](https://badge.fury.io/js/vue-jquery-calendar)

`vue-jquery-calendar` is wrapper vue package of `jquery ui datepicker`

## Installation
```
npm install --save vue-jquery-calendar
```
Or using yarn
```
yarn add vue-jquery-calendar -dev
```

For Installing plugin import `vue-jquery-calendar` in your component page.

```js
//foo.vue
import VueJqueryCalendar from 'vue-jquery-calendar';
export default {
  components: {
    VueJqueryCalendar,
  },
}
```

### Note

Please note that this package depends on `jQuery` and `jquery-ui`, but you won't need to add it to your project manually, `vue-jquery-calendar` will handle this for you automatically if this dependencies are not detected.


### CSS
For `vue-jquery-calendar` appearance import jquery-ui css in `App.vue` main file
```js
<style>
@import '~jquery-ui-dist/jquery-ui.css';
</style>
```

## Example App
 try out this [Code Sandbox]()


## Basic Usage

You can pass an array of fullclendar objects through the props

```html
<VueJqueryCalendar v-model="date" :class-name="'form-control'" date-format="dd-mm-yy" :readonly="true" />
...
<script>
import moment from 'moment';
import VueJqueryCalendar from 'vue-jquery-calendar';
...
  components: {
	VueJqueryCalendar,
  },
  data() {
    return {
        date: moment().subtract(30, "days").format("DD-MM-YYYY"),
    }
  }
...
</script>
```
### Props

| Name                  | Type       | Default        | Description                                                                                                                 |
| --------------------- | ---------- | -------------- | --------------------------------------------------------------------------------------------------------------------------- |
| value                 | `String`   | null           | Value of the input DOM                                                                                                      |
| showButtonPanel       | `Boolean`  | false          | To display a button pane underneath the calendar 
| changeMonth           | `Boolean`  | false          | The month should be rendered as a dropdown instead of text
| changeYear            | `Boolean`  | false          | The year should be rendered as a dropdown instead of text
| numberOfMonths        | `Number`   | 1              | The number of months to display in a single row 
| dateFormat            | `String`   | 'dd/mm/yy'     | The format for parsed and displayed dates
| readonly              | `Boolean`  | false          | Calendar input field set as read-only mode
| className             | `String`   | null           | Calendar input class name set


### Events

| Name     | Description               |
| -------- | ------------------------- |
| change   |  get value on change date |
