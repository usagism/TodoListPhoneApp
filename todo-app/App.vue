<template>
  <view class="container">
    <Statusbar bar-style="dark-conent"/>
    <NewHeader title="Enjoy Life Todo App" />
    <Inputs />
  </view>
</template>
<script>
import Statusbar from './components/Statusbar';
import NewHeader from './components/NewHeader';
import Inputs from './components/Inputs';

export default {
    components: {
        Statusbar,
        NewHeader,
        Inputs
    }
}
</script>

<style>
.container {
  background-color: white;
  /* align-items: center; */
  /* justify-content: center; */
  flex: 1;
}
.text-color-primary {
  color: blue;
}

</style>
