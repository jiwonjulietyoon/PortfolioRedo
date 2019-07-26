<template>
    <nav>
        <span id="bb-nav-prev" class="nav-btn">
            <div class="navArrowRec"></div>
            <div class="navArrowTri"></div>
        </span>
        <span id="bb-nav-next" class="nav-btn">
            <div class="navArrowRec"></div>
            <div class="navArrowTri"></div>
        </span>
    </nav>
</template>


<script>
export default {
    data() {
        return {

        }
    }
}
</script>


<style lang="scss" scoped>
nav {
    width: calc(100% - 30px);
	height: 50px;
	bottom: 30px;
	left: 15px;
	position: absolute;
	z-index: 1000;
}
.nav-btn {
	position: absolute;
	width: 32px;
	height: 32px;
	bottom: 0;
	background-color: rgb(238, 68, 62);
	border-radius: 50%;
    cursor: pointer;
    &:hover {
        background-color: #d50027;
    }
    &:active {
        background-color: #000;
    }
    .no-js & {
        display: none;
    }
    &#bb-nav-prev {
        left: 12px;
    }
    &#bb-nav-next {
        right: 12px;
    }
}
.navArrowRec {
	position: absolute;
	width: 10px;
	height: 8px;
	top: 50%;
	left: 40%;
	transform: translate(-50%, -50%);
    background-color: white;
    #bb-nav-prev > & {
        left: 60%;
    }
}
.navArrowTri {
	position: absolute;
	width: 0;
	height: 0;
	top: 24%;
    left: 52%;
    border-top: 9px solid transparent;
    border-left: 10px solid white;
    border-bottom: 9px solid transparent;
    #bb-nav-prev > & {
        border-left: none;
	    border-right: 10px solid white;
	    left: 17%;
    }
}

</style>
