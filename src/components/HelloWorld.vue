<template>
	<div class="hello">
		<button @click="add">遮罩</button>
		<div class="mask" id="mask" @click="mask" @touchmove="someFunction" v-show="displaceNode"></div>
			<div class="mtai" v-show="displaceNode">
				<button @click="clone">关闭</button>
				<ul>
					<li>状态选择</li>
					<li>待审批</li>
					<li>完成</li>
					<li>全部</li>
				</ul>
			</div>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				displaceNode:false,
			}
		},
		created() {
			
		},
		methods: {
			add(){
//				$("#mask").css("height", $(document).height());
//				$("#mask").css("width", $(document).width());
				this.displaceNode=true;
			},
				mask(){
					this.displaceNode=false;
				},
				someFunction(e){
					console.log("no  dome....")
				if(e && e.stopPropagation) { //非IE
					e.stopPropagation();　　
				}　　
				else { //IE
					window.event.cancelBubble = true;　　
				}　
				},
				clone(){
					this.displaceNode=false;
				}
		},
	
		
				mounted() {
		   }

	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
		.mask {
		position: absolute;
		top: 0px;
		z-index: 50;
		left: 0px;
		background: rgba(0, 0, 0, 0.5);
		width: 100%;
		height: 100%;
		}
		.mtai{
			position: absolute;
			z-index: 100;
			margin: 150px;
			background: pink;
		}
</style>