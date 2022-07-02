<template>
  <div class="app-container">
    <div style="margin:0 0 5px 20px">
      根据原顺序排列
    </div>
    <fixed-thead />

    <div style="margin:30px 0 5px 20px">
      根据点选顺序排列
    </div>
    <unfixed-thead />
  </div>
</template>

<script>
import FixedThead from './components/FixedThead'
import UnfixedThead from './components/UnfixedThead'

export default {
  name: 'DynamicTable',
  components: { FixedThead, UnfixedThead }
}
</script>

