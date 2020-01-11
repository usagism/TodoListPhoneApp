<template>
    <view class="header">
        <text class="title"> {{ title }}</text>
    </view>
</template>

<script>
export default {
    props: ['title']
}
</script>

<style >
.header {
    height: 60px;
    background-color: white;
    justify-content: center;
    align-items: center;
}

.title{
    color: blue;
    font-size: 28px;
    font-weight: 900;
    text-transform: uppercase;
}
</style>