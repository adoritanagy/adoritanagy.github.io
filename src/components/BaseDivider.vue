<template>
    <div class="base-divider" :style="{'background-color': color}"></div>
</template>
<script>
export default {
    name: "BaseDivider",
    props: {
        color: {
            type: String,
            default: "#f7c21a"
        }
    }
}
</script>

<style lang="scss">
.base-divider {
    height: 10px;
    width: 100%;
    border-radius: 5px;
}
</style>