<template>
    <div class="flex items-center justify-center w-full header">
        <h2>{{ title }}</h2>
        <span>{{ timestamp }}</span>
    </div>
</template>
<script>
import moment from 'moment';
export default {
    name: 'DataTitle',
    props: ['text', 'date'],
    computed: {
        timestamp: function(){
            return moment(this.date).format('MMMM Do YYYY  - h:mm:ss a')
        }
    }
}
</script>