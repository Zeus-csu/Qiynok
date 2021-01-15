<template>
    <div class="twoot-item">
        <div class="user-profile-twoot">
            <div class="twoot-item-user">
                @{{username}}
             </div>
            <div class="twoot-item-content">
                {{twoot.content}}
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "TwootItem",
        props: {
          username:{
            type: String,
            required: true
                 },
          twoot: {
            type: Object,
            required: true
               }
        }
    }
</script>

<style  scoped>

.twoot-item {
    border:1px solid #777;
    background-color: ivory;
}



</style>