<template>
	<view class="content">
		<div class="item filter_input">
			<div class="lable">日期期间：</div>
			<view class="date_item">
				<dyDatePicker placeholder="起始日期" :childValue="from" :minSelect="from_minSelect" :maxSelect="from_maxSelect"
				 :iconshow="false" @getData="getFromData"></dyDatePicker>
			</view>
			<view class="filter_inputline"></view>
			<view class="date_item">

				<dyDatePicker placeholder="结束日期" :minSelect="to_minSelect" :childValue="to" :maxSelect="to_maxSelect" :iconshow="false"
				 @getData="getToData"></dyDatePicker>
			</view>
		</div>
		<div class="item">
			<div class="lable">禁止选择：</div>
			<dyDatePicker childValue="2019/08/08" :disabled="true" @getData="getData" placeholder="请选择日期"></dyDatePicker>
		</div>
		<div class="item">
			<div class="lable">指定开始、结束时间：</div>
			<dyDatePicker @getData="getData" placeholder="请选择日期" minSelect="2000/01/01" maxSelect="2025/12/31"></dyDatePicker>
		</div>
		<div class="item">
			<div class="lable">指定值：</div>
			<dyDatePicker @getData="getData" childValue="2019/08/08" placeholder="请选择日期" minSelect="2000/01/01" maxSelect="2025/12/31"></dyDatePicker>
		</div>
		
		<div class="item">
			<div class="lable">选择月份：</div>
			<dyDatePicker timeType="month" @getData="getData" placeholder="请选择日期" minSelect="2000/01/01" maxSelect="2025/12/31"></dyDatePicker>
		</div>
		<div class="item">
			<div class="lable">选择年份：</div>
			<dyDatePicker timeType="year" @getData="getData" placeholder="请选择日期" minSelect="2000/01/01" maxSelect="2025/12/31"></dyDatePicker>
		</div>
	</view>
</template>

<script>
	import dyDatePicker from '../../components/lanxiujuan-dyDate/lanxiujuan-dyDate.vue'
	export default {
		components: {
			dyDatePicker
		},
		data() {
			return {
				from_minSelect: '1900/01/01',
				from_maxSelect: '2050/12/31',
				to_minSelect: '1900/01/01',
				to_maxSelect: '2050/12/31',
				from: '',
				to: '',
			}
		},
		onLoad() {

		},
		methods: {
			/**
			 * @param {to_minSelect|from}  to_minSelect结束时间的最小选择范围 from=>开始日期
			 */
			getFromData(time) {
				this.to_minSelect = time
				this.from = time
			},
			/**
			 * @param {from_maxSelect|to} from_maxSelect=>开始日期可选最大可选值 to=> 结束日期
			 */
			getToData(time) {
				this.from_maxSelect = time
				this.to = time
			},
			getData() {
				// 
			}
		}
	}
</script>

<style lang="less">
	* {
		padding: 0px;
		margin: 0 auto;
		box-sizing: border-box;
	}


	.content {
		text-align: center;

		margin-top: 20px;
		font-size: 24rpx;

	}

	.item {
		box-sizing: border-box;
		width: 100%;
		height: 40px;
		line-height: 40px;
		background-color: #ffffff;
		position: relative;
		padding: 0px 10px 0px 100px;
		margin-bottom: 10px;
		text-align: right;
	}

	.item .lable {
		position: absolute;
		left: 10px;
		top: 0px;
		color: #333333;
	}

	uni-picker-view-column {
		font-size: 24rpx;
	}

	.filter_input {
		height: 92rpx;
		padding-top: 10rpx;
	}

	.date_item {
		float: left;
		width: 240upx;
		overflow: hidden;
		display: inline-block;
		text-align: center;
		border: 1px solid #ececec;
		height: 72rpx;
		line-height: 72rpx;

		// font-size: 28rpx;
		&:last-child {
			// float: right;
		}

		input {
			height: 72rpx;

			.uni-input-placeholder {
				color: #b5b8c2;
			}
		}
	}

	.filter_inputline {
		float: left;
		margin: 0 4rpx;
		line-height: 72rpx;

		&:after {
			content: '—';
			font-size: 28rpx;
			color: #848b9a;
		}
	}
</style>
