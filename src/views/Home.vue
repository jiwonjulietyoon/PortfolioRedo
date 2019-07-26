<template>
  <div id="wrap">
    <div id="bookOutline">
      <div id="bookContainer">
        <div class="bb-custom-wrapper">
          <div class="bb-bookblock" id="bb-bookblock">
            <div class="bb-item" id="item1">
                <div class="content">
                    <!-- <pg1-scroller class="scroller" /> -->
                </div>
                <page-num :pgLeft="''" :pgRight="'About Me'" />
            </div>
            <div class="bb-item" id="item2">
                <div class="content">
                    <!-- <pg2-scroller class="scroller" /> -->
                </div>
                <page-num :pgLeft="'Welcome'" :pgRight="'Skills'" />
            </div>
          </div>
          <nav-arrows />
        </div>
      </div>
    </div>
  </div>
</template>



<script src="../js/bk_jquery.bookblock"></script>
<script src="../js/bk_jquery.mousewheel"></script>
<script src="../js/bk_jquerypp.custom"></script>
<script src="../js/bk_modernizr.custom.79639"></script>
<script src="../js/bk_page"></script>

<script>
import NavArrows from '../components/NavArrows';
import PageNum from '../components/PageNum';

export default {
  components: {
    'nav-arrows': NavArrows,
    'page-num': PageNum
  },
};
</script>


<style lang="scss" scoped>
@import "@/css/style.scss";

#wrap {
  width: 100%;
  height: 100vh;
  min-height: 500px;
  overflow-y: auto;
  background-color: $bgBlack;
}

@keyframes bookRise {
  0% {top: 10%;}
  95% {top: 2.5%;}
  100% {top: 3%;}
}
#bookOutline {
  width: 95%;
  height: 94%;
  margin: 0 auto;
  position: relative;
  // animation: bookRise 1s;
  animation-fill-mode: forwards;
}

#bookContainer {
  position: absolute;
  top: 0; left: 0; bottom: 0; right: 0;
  background-color: $bookCoverBrown;
  border-radius: 7px;
  padding: 15px;
  @include xsDown {
    padding: 10px;
  }
}

.bb-custom-wrapper,
.bb-bookblock {
	width: 100%;
	height: 100%;
}
.bb-bookblock {
	position: relative;
	background: #fff;
	z-index: 100;
}
.bb-item {
  position: relative;
  .js & {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    display: none;
    background: #fff;
  }
}

.js .content {
	position: absolute;
	top: 60px;
	left: 0;
	width: 100%;
	bottom: 50px;
	overflow: hidden;
  -webkit-font-smoothing: subpixel-antialiased;
  &:before, &:after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 20px;
    z-index: 100;
    pointer-events: none;
    background: -webkit-linear-gradient(top, rgba(255,255,255,1) 0%, rgba(255,255,255,0) 100%);
    background: -moz-linear-gradient(top, rgba(255,255,255,1) 0%, rgba(255,255,255,0) 100%);
    background: -o-linear-gradient(top, rgba(255,255,255,1) 0%, rgba(255,255,255,0) 100%);
    background: linear-gradient(to bottom, rgba(255,255,255,1) 0%, rgba(255,255,255,0) 100%);
  }
  &:after {
    top: auto;
    bottom: 0;
    background: -webkit-linear-gradient(bottom, rgba(255,255,255,1) 0%, rgba(255,255,255,0) 100%);
    background: -moz-linear-gradient(bottom, rgba(255,255,255,1) 0%, rgba(255,255,255,0) 100%);
    background: -o-linear-gradient(bottom, rgba(255,255,255,1) 0%, rgba(255,255,255,0) 100%);
    background: linear-gradient(to top, rgba(255,255,255,1) 0%, rgba(255,255,255,0) 100%);
  }
  @include xsDown {
    top: 30px;
    font-size: 60%;
  }
}

@include smDown {
	.no-js .container {
		padding: 0;
	}
	.content {
		font-size: 80%;
	}
}
.scroller {
	padding: 10px 5%;
}


</style>
