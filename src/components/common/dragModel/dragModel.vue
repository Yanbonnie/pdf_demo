<template>
    <section class="dragBox">
        <div class="dragTop " id="dragTop" >
            <slot name="dragTop">

            </slot>            
            <div class="line" id="line" ></div>
        </div>
        <div class="dragBottom">
            <slot name="dragBottom">

            </slot>
        </div>
    </section>
</template>
<script>
export default {
    data(){
        return{

        }
    },
    methods:{
        drag(obj,oDragTop) {		
            obj.onmousedown = function(ev) {
                var ev = ev || event;
                
                // var disX = ev.clientX - this.offsetLeft;
                var disY = ev.clientY - this.offsetTop;
                var disD = ev.clientY;
                var Height = oDragTop.offsetHeight-1;
                console.log(Height)
                
                if ( obj.setCapture ) {
                    obj.setCapture();
                }
                
                document.onmousemove = function(ev) {
                    var ev = ev || event;
                    
                    // obj.style.left = ev.clientX - disX + 'px';
                    // obj.style.top = ev.clientY - disY + 'px';
                    console.log(ev.clientY)
                    oDragTop.style.height = Height + (ev.clientY - disD) +'px';
                }
                
                document.onmouseup = function() {
                    document.onmousemove = document.onmouseup = null;
                    //释放全局捕获 releaseCapture();
                    if ( obj.releaseCapture ) {
                        obj.releaseCapture();
                    }
                }
                
                return false;
                
            }
            
        }
    },
    mounted(){
        var oDiv = document.getElementById('line');
        var oDragTop = document.getElementById('dragTop');
        this.drag(oDiv,oDragTop)
    }
}
</script>
<style lang="scss" scoped>
.dragBox{
    width: 500px;
    height: 500px;
    border: 1px #ccc solid;
    display: flex;
    flex-direction:column;
    margin: 0 auto;
    .dragTop{
        // display: block;
        width: 98%;
        padding: 0 1%;
        height: 300px;
        border-bottom: 1px #ccc solid;
        position: relative;
        background:pink;
        overflow: hidden;
        .line{
            position: absolute;
            width: 100%;
            height: 5px;
            left: 0;
            bottom: 0;
            // background: red;
            z-index: 100;
            &:hover{
                cursor: s-resize;
            }
        }
        ul{
            height:100%;
            overflow: auto;
        }
    }
    .dragBottom{
        // display:flex;
		flex-grow:1;
        width: 100%;
        background: #ccc;
        h3{
            line-height: 50px;
            text-align: center;
            display: block;
        }
    }
}
.sign_page_scroll::-webkit-scrollbar-track {
	-webkit-box-shadow: inset 0 0 0 pink;
	border-radius: 0;
	background-color: pink;
}

.sign_page_scroll::-webkit-scrollbar {
	width: 5px;
	background-color: #fff;
}

.sign_page_scroll::-webkit-scrollbar-thumb {
	border-radius: 100px;
	-webkit-box-shadow: inset 0 0 5px #fff;
	background-color: #fff;
}
</style>


