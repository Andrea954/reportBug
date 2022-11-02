<template>
	<div class="container">
		<van-pull-refresh class="test" v-model="isLoading" @refresh="onRefresh">
			<p>刷新次数: {{ count }}</p>
		</van-pull-refresh>
	</div>
</template>
<script>
import { Vue, Component } from 'vue-property-decorator'
import { Toast } from 'vant'
@Component()
export default class extends Vue {
	count = 0
	isLoading = false

	onRefresh() {
		alert('ok')
		setTimeout(() => {
			Toast('刷新成功')
			this.isLoading = false
			this.count++
		}, 1000)
	}
}
</script>
<style>
.container {
	width: 100vw;
	height: 100vh;
	background: skyblue;
}
.test {
	width: 100%;
	height: 100%;
}
</style>
