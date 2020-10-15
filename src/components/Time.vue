<template>
  <div>{{ nowTime }}</div>
  <div>
    <button @click="getNowTime">显示时间</button>
  </div>
  <hr>
</template>

<script>
import {ref} from 'vue'

export default {
  name: 'Time',
  setup() {
    const nowTime = ref("00:00:00");
    const getNowTime = () => {
      const now = new Date();
      const hour = now.getHours() < 10 ? "0" + now.getHours() : now.getHours();
      const minute = now.getMinutes() < 10 ? "0" + now.getMinutes() : now.getMinutes();
      const sec = now.getSeconds() < 10 ? "0" + now.getSeconds() : now.getSeconds();
      nowTime.value = hour + ":" + minute + ":" + sec;
      setTimeout(getNowTime, 1000);   //每一秒执行一次这个方法
    };
    return {
      nowTime,
      getNowTime,
    };
  },
}
</script>
