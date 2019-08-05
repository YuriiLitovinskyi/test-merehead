<template>
  <div class="about">
    <h2>This is a test task for Merehead</h2>
    <img :src="image" />
  </div>
</template>


<script>

import image from '../assets/logo.png'

export default {
	data: function () {
	    return {
	        image: image
	    }
	}
}
</script>
