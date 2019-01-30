<template>
    <span>
        <a :href="link" v-if="type=='link'"  v-bind="$attrs">{{ slot }}</a>
        <input type="submit" v-if="type=='submit'" :value="slot"  v-bind="$attrs"/>
    </span>
</template>

<script>
export default {
    inheritAttrs: false,
    props: [
        'type',
        'link'
    ],
    data() {
        return {
            slot: ''
        }
    },
    mounted() {
        if (this.$slots.default) {
            this.slot = this.$slots.default[0].text;
        }
    }
}
</script>

<style scoped>
input, a {
    display: inline-block;
    box-sizing: border-box;
    border: none;
    padding: 0;
    margin: 0;
    cursor: pointer;
    background: #ed1c24;
    width: 190px;
    height: 45px;
    line-height: 45px;
    text-align: center;
    border-radius: 5px;
    color: white;
    text-decoration: none;
}
</style>

