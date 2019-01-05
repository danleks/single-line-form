<template>
    <div class="summaryWrapper">
        <div class="summaryWrapper__items">
            <div @click="$emit('close-booking')" class="close">
                <span class="close__item"></span>
            </div>
            <h1>Your booking:</h1>
            <p>City: {{form.city}}</p>
            <p>From: {{form.from}}</p>
            <p>To: {{form.to}}</p>
            <p>Guests: {{form.selected}}</p>
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
            position: relative;
            padding: 30px;
            background-color: rgba(0, 0, 0, 0.5);
            box-shadow: 0 5px 10px rgba(0,0,0,.7);

            h1 {
                padding-top: 30px;
                font-size: 44px;
                text-align: center;
                color: #fff;

            }


            & > p {
                padding: 10px 70px;
                font-size: 40px;
                color: #fff;
            }
        }

        .close {
            position: absolute;
            top: 12px;
            right: 16px;
            width: 24px;
            height: 25px;
            cursor: pointer;


            &__item {
                position: absolute;
                top: 10px;
                right: 21px;

                &::before,
                &::after {
                    position: absolute;

                    content: '';
                    width: 18px;
                    height: 3px;
                    background-color: #fff;
                }

                &::before {
                   transform: rotate(45deg);
                }

                &::after {
                   transform: rotate(-45deg);
                }
            }
        }
    }
</style>
