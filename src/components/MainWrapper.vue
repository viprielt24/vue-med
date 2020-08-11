<template>
  <div>
    <Read> </Read>
    <BestDoctors> </BestDoctors>
  </div>
</template>

<script>
import Read from '@/components/Read';
import BestDoctors from '@/components/BestDoctors';

export default {
  name: 'MainWrapper',
  components: {
    Read,
    BestDoctors
  }
}
</script>

<style scoped>

</style>
