<template>
    <div class="composer">
        <textarea v-model="message" class="messenger-composer" @keydown.enter="send" placeholder="Message..."></textarea>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                message: ''
            };
        },
        methods: {
            send(e) {
                e.preventDefault();
                
                if (this.message === '') {
                    return
                }

                this.$emit('send', this.message);
                this.message = '';
            }
        }
    }
</script>

<style lang="scss" scoped>
.composer {
    position: absolute;
    padding-top: 70px;
}
</style>