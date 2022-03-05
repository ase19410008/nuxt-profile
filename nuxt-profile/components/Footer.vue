<template>
    <footer id="footer">
        {{ date }}
    </footer>
</template>

<script setup>
const today = new Date();
const year = today.getFullYear();
const month = today.getMonth() + 1;
const day = today.getDate();
const date = `${year}年${month}月${day}日`;
</script>

<style lang="scss" scoped>
/*-------------------------------------------
footer
-------------------------------------------*/
#footer {
    font-size: 0.5rem;
    padding: 10px 0;
    text-align: center;
}
</style>