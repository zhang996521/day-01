<template>
    <div class=''>
        <div>
            <span :class="show == 1 ?'red':''" @click="sss(1)">第一步</span>
            <span :class="show == 2 ?'red':''" @click="sss(2)">第二步</span>
            <span :class="show == 3 ?'red':''" @click="sss(3)">第三步</span>
            <span :class="show == 4 ?'red':''" @click="sss(4)">第四步</span>
        </div>
    </div>
</template>

<script>
export default {
    props:{
        show:Number
    },
    data() {
        return {};
    },
    mounted() {},
    methods: {
        sss(id) {
            this.$emit('sss',id)
        }
    },
};
</script>

<style lang='scss'>

</style>
