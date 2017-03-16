<template>
  <div id="app" class="uk-container uk-container-center uk-text-center uk-margin-large-top">
    <img src="./assets/logo.png">
    <h1>{{ msg }}</h1>
    <ul class="uk-subnav uk-flex-center">
      <li><a href="https://vuikit.js.org" target="_blank">Docs</a></li>
      <li><a href="https://gitter.im/vuikit/vuikit" target="_blank">Gitter Chat</a></li>
      <li><a href="https://twitter.com/vuikit" target="_blank">Twitter</a></li>
    </ul>
    
    <vk-button>Hello from Vuikit button!</vk-button>
  
  <input id="target"
  type="text"
  placeholder="Pick a date"
  v-model="date"
  @focus="showDate = true">
<vk-datepicker-drop :show="showDate"
  target="#target"
  :year="year"
  :month="month"
  :dates="date
    ? [date]
    : []"
  @pick="
    date = arguments[0].format('YYYY-MM-DD'),
    show = false
  "
  @change="
    year = arguments[0].year(),
    month = arguments[0].month()
  "
  @clickOut="showDate = false">
</vk-datepicker-drop>
<vk-button id="blly"
  @click.native="showToggle = !showToggle">
  Toggle
</vk-button>
<vk-dropdown target="#blly"
  :show="showToggle">
 <ul>
  <li>one</li>
  <li>two</li>
  <li>three</li>
 </ul>
  
</vk-dropdown>
  </div>
  
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue Vuikit App',
      showDate: false,
      showToggle: false,
    }
  }
}
</script>
