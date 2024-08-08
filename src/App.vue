<!--
	这个项目是一个网页版的智能对话机器人。
	整个项目采用 TailwindCSS 作为样式库。
	我们会在这个文件中一步一步地构建整个页面。
-->

<script setup>
import { ref } from 'vue'
import MessageItem from '@/components/MessageItem.vue'
// 导入 utils/mock.js 中的 mockDataMessages
import { mockDataMessages } from '@/utils/mock.js'

const $messages = ref(mockDataMessages)
</script>

<template>
	<!--
		首先这里需要一个容器，用来包裹主体区域。
		它的高度撑满整个页面，最大宽度为 640px，并且居中显示。
		我们一步一步来，暂时不需要考虑它的内容。
	-->
	<div class="mx-auto max-w-[640px] h-full overflow-hidden bg-white flex flex-col">
		<!--
			这里需要仿手机 App 的聊天界面布局形式：
			* 顶部是标题栏，高度固定。
			* 底部是操作栏，高度固定。
			* 中间区域是对话区，高度占据剩余空间，当内容超长时可以出现垂直滚动条。
		-->
		<header class="h-11 bg-gray-100 border-b flex-none flex items-center justify-center">
			<h1 class="font-bold text-lg">Simple Chat</h1>
		</header>
		<div class="p-5 pb-10 flex-auto overflow-y-auto">
			<MessageItem v-for="message of $messages" :messageItem="message"></MessageItem>
		</div>
		<footer class="h-12 border-t flex-none flex items-stretch justify-between">
			<div class="flex-auto">
				<input
					class="px-4 w-full h-full outline-0 border-transparent border-2 focus:border-blue-300"
					placeholder="请输入消息内容"
				/>
			</div>
			<div class="flex-none">
				<button class="px-4 size-full bg-blue-500 text-white hover:bg-blue-600">
					发送
				</button>
			</div>
		</footer>
	</div>
</template>

<style scoped>

</style>
