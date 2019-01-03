<template>
    <div class="summaryWrapper">
        <div class="summaryWrapper__items">
            <h1>Your booking:</h1>
            <p>City: {{form.city}}</p>
            <p>From: {{form.from}}</p>
            <p>To: {{form.to}}</p>
            <p>Number of guests: {{form.selected}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        form: {
            type: Object,
            required: true,
        }
    }
}
</script>

<style lang="scss" scoped>
    .summaryWrapper {
        position: relative;
        z-index: 3;
        height: 100%;

        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;



        &__items {
            padding: 20px;
            background-color: rgba(0,0,0,.5);

            h1 {
                font-size: 44px;
                text-align: center;
                color: #fff;

            }


            & > p {
                font-size: 40px;
                color: #fff;
            }
        }
    }
</style>
