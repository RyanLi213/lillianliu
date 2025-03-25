<template>
    <div class="landing">
        <transition name="slide-fade">
            <h1 class="landing_text" v-if="show">{{message}}</h1>
        </transition>
    </div>
</template>

<script>
    export default {
        name: 'Landing',
        data() {
            // TODO : Change these messages to your own words ...
            let landingMessages = [
                "Hey Princess <3",
                "It's Your Birthday Today :)",
                "I hope the day shines as bright as you <3",
                "I was scheming a little...",
                "And made this for you <3"
            ];
            return {
                message: "",
                messages: landingMessages,
                show: true,
                showButton: false,
                count: 0,
                maxCount: landingMessages.length - 1
            }
        },
        mounted: function () {
            this.message = this.messages[this.count];
            setTimeout(this.fadeText, 2000);
        },
        methods: {
            fadeText() {
                this.show = false;
                this.count++;
                this.message = this.messages[this.count];
                setTimeout(this.showText, 1250);
            },
            showText() {
                this.show = true;
                if (this.count !== this.maxCount) {
                    setTimeout(this.fadeText, 2250);
                } else {
                    this.showButton = true;
                    setTimeout(() =>this.$router.push('/home'), 3000);
                }
            }
        }
    }

</script>

<style scoped>
    .landing {
        line-height: 80vh;
        font-size: 3vw;
        text-align: center;
        background-color: #7fe5ff; /* dark navy blue background */
        color: #fffbe6;            /* soft yellow-white font */
        height: 100vh;             /* make it fill the screen */
        display: flex;
        align-items: center;
        justify-content: center;
}


    .landing_text {
        vertical-align: baseline;
    }
</style>
