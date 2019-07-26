<template>
    <div class="pageNum">
        <span class="pageNumL">{{ pgLeft }}</span>
        <span class="pageNumR">{{ pgRight }}</span>
    </div>
</template>

<script>
export default {
    props: {
        pgLeft: {type: String, default: ""},
        pgRight: {type: String, default: ""}
    },
    data() {
        return {
            
        }
    }
}
</script>

<style lang="scss" scoped>
.pageNum {
    position: absolute;
    bottom: 17px;
    width: 100%;
    padding: 0 55px;
    font-size: 18px;
    font-weight: bold;
    font-family: 'Copse', serif;
    
}
@media screen and (max-width: 575px) {
    .pageNum {
        bottom: 25px;
        font-size: 15px;
    }
}

.pageNumL {
    float: left;
    border-bottom: 2px solid transparent;
    transition: all 0.5s;
}
.pageNumR {
    float: right;
    border-bottom: 2px solid transparent;
    transition: all 0.5s;
}
</style>

