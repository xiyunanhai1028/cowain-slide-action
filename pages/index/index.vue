<template>
	<view class="container">
		<scroll-view class="scroll-view" scroll-y>
			<cowain-slide-action :slide-width="90" v-for="(item, index) in list" :key="index">
				<template v-slot:card>
					<view class="card" @click="_markRead(item)">
						<view class="header-wrap">
							<view class="title-wrap">
								<view class="dot"></view>
								<text class="title">{{ item.title }}</text>
							</view>
							<text class="time">{{ item.createdTime }}</text>
						</view>
						<view class="remark">
							<text class="msg">{{ item.remark  }}</text>
						</view>
					</view>
				</template>
				<template v-slot:delete>
					<view class="delete-wrap">
						<image src="../../static/icon-delete-card.png" class="icon-delete"
							@click.stop="onDeleteItemClick(index)" />
					</view>
				</template>
			</cowain-slide-action>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				list: [{
						"id": "116",
						"maintenanceCode": "BY220810000002",
						"title": "工单消息",
						"type": "care",
						"createdTime": "2022-08-10 10:09:56",
						"remark": "收到一个新的【保养工单】，点击查看详情。",
						"isRead": "0"
					},
					{
						"id": "120",
						"maintenanceCode": "WX220820000011",
						"title": "工单消息",
						"type": "maintain",
						"createdTime": "2022-08-10 10:09:56",
						"remark": "收到一个新的【维修工单】，点击查看详情。",
						"isRead": "0"
					},
					{
						"id": "123",
						"maintenanceCode": "BY220820000002",
						"title": "工单消息",
						"type": "care",
						"createdTime": "2022-08-10 10:09:56",
						"remark": "收到一个新的【保养工单】，点击查看详情。",
						"isRead": "0"
					},
					{
						"id": "124",
						"maintenanceCode": "WX220820000002",
						"title": "工单消息",
						"type": "maintain",
						"createdTime": "2022-08-10 10:09:56",
						"remark": "收到一个新的【维修工单】，点击查看详情。",
						"isRead": "0"
					},
					{
						"id": "112",
						"maintenanceCode": "BY220810000001",
						"title": "工单消息",
						"type": "care",
						"createdTime": "2022-08-10 10:08:05",
						"remark": "收到一个新的【保养工单】，点击查看详情。",
						"isRead": "0"
					},
					{
						"id": "115",
						"maintenanceCode": "WX220810000002",
						"title": "工单消息",
						"type": "maintain",
						"createdTime": "2022-08-10 10:08:05",
						"remark": "收到一个新的【维修工单】，点击查看详情。",
						"isRead": "0"
					},
					{
						"id": "122",
						"maintenanceCode": "WX220820000022",
						"title": "工单消息",
						"type": "maintain",
						"createdTime": "2022-08-10 10:08:05",
						"remark": "收到一个新的【维修工单】，点击查看详情。",
						"isRead": "0"
					},
					{
						"id": "118",
						"maintenanceCode": "WX220820000001",
						"title": "工单消息",
						"type": "maintain",
						"createdTime": "2022-08-03 09:52:21",
						"remark": "收到一个新的【维修工单】，点击查看详情。",
						"isRead": "0"
					},
					{
						"id": "121",
						"maintenanceCode": "BY220804000002",
						"title": "工单消息",
						"type": "care",
						"createdTime": "2022-08-03 09:52:21",
						"remark": "收到一个新的【保养工单】，点击查看详情。",
						"isRead": "0"
					}
				]
			}
		},
		onLoad() {

		},
		methods: {
			onDeleteItemClick(index) {
				uni.showToast({
					title: `点击了${index}位置`,
					icon: 'none'
				})
			},
		}
	}
</script>

<style>
	.container {
		width: 100%;
		height: 100vh;
		background-color: rgba(245, 246, 248, 1);
	}

	.scroll-view {
		width: 100%;
		height: 100%;
	}

	.card {
		margin-left: 24rpx;
		width: 702rpx;
		height: 171rpx;
		padding: 28rpx 24rpx;
		box-sizing: border-box;
		border-radius: 24rpx;
		background-color: white;

	}

	.header-wrap {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.title-wrap {
		display: flex;
		align-items: center;
	}

	.dot {
		margin-right: 11rpx;
		width: 16rpx;
		height: 16rpx;
		background-color: rgba(222, 11, 11, 1);
		border-radius: 8rpx;
	}

	.title {
		font-size: 32rpx;
		font-family: PingFangSC-Medium, PingFang SC;
		font-weight: 500;
		color: #323233;
		line-height: 45rpx;
	}

	.remark {
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin-top: 26rpx;
	}

	.time {
		font-size: 26rpx;
		font-family: PingFangSC-Regular, PingFang SC;
		font-weight: 400;
		color: $txt-black-204;
		line-height: 36rpx;
	}

	.msg {
		width: 540rpx;
		font-size: 26rpx;
		font-family: PingFangSC-Regular, PingFang SC;
		font-weight: 400;
		color: #666666;
		line-height: 36rpx;

		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
	}

	.delete-wrap {
		position: absolute;
		right: 0px;
		top: 0;
		width: 180rpx;
		height: 171rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		z-index: 999;
	}

	.icon-delete {
		width: 80rpx;
		height: 80rpx;
		object-fit: cover;
	}
</style>
