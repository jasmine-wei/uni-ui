<template>
	<view>
		<view class="example-title">默认样式</view>
		<uni-pagination title="标题文字" total="20"></uni-pagination>
        <view class="example-title">修改按钮文字</view>
        <uni-pagination title="标题文字" total="20" prev-text="前一页" next-text="后一页"></uni-pagination>
        <view class="example-title">图标样式</view>
        <uni-pagination title="标题文字" show-icon="true" total="20"></uni-pagination>
        <view class="example-title">修改数据长度</view>
        <uni-pagination title="标题文字" show-icon="true" :current="current" :total="total" @change="change"></uni-pagination>
        <view class="btn-view">
            <view>
                当前页：{{current}}，数据总量：{{total}}条，每页数据：{{pageSize}}
            </view>
            <button type="primary" @click="add">增加10条数据</button>
            <button type="default" @click="reset">重置数据</button>
        </view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				current:1,
                total:0,
                pageSize:10
			}
		},
        methods:{
            add(){
                this.total += 10
            },
            reset(){
                this.total = 0
                this.current = 1
            },
            change(e){
                console.log(e);
                this.current = e.current
            }
        }
	}
</script>

<style>
    .btn-view{
        margin: 30upx 30upx 0;
        text-align: center;
    }
    button{
        margin-top: 30upx;
    }
</style>
