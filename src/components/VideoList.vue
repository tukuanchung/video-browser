<template>
	<ul class="list-group col-md-4">
		<VideoListItem 
			v-for="mySingleVideo in videos"
			:video="mySingleVideo"
			:key="mySingleVideo.etag"
			@videoSelect="onVideoSelect"
		>
		</VideoListItem>
	</ul>
</template>

<script>
import VideoListItem from './VideoListItem';

export default {
	name : 'VideoList',
	components:{
		VideoListItem
	},
    // What is data received from parent
	props: ['videos'],
	methods: {
		onVideoSelect(video){
			this.$emit('videoSelect', video)
		}
	}
};
</script>

<style>

</style>