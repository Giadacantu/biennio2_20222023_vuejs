<script setup>

</script>

<template>
    <div class="video-div">
     <video width="800" height="500" controls>
            <source src="@/assets/Men.mp4" type="video/mp4">
            <source src="@/assets/Men.mp4" type="video/ogg">
        Il browser non supporta il tag video
        </video>
    </div>
</template>


<style scoped>
.video-div{
    display: flex;
    margin-bottom: 100px;
    justify-content: center;
    align-items: center;
}
</style>