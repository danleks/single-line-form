<template>
    <div class="formWrapper">
        <form action="#" @submit.prevent class="formWrapper__container">
            <input v-model="form.city" type="text" placeholder="Where do you want to go?">

            <label for="from">From</label>
            <input v-model="form.from" type="date" id="from">

            <label for="to">To</label>
            <input v-model="form.to" type="date" id="to">

            <select name="guest" id="guest" v-model="form.selected">
                <option disabled value="">Select number of guests</option>
                <option v-for="option in form.options" :key="option.value" :value="option.value">{{ option.text }}</option>
            </select>

            <button @click="$emit('show-summary')" type="submit">Submit</button>
        </form>
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
    .formWrapper {
        position: relative;
        z-index: 3;
        height: 100%;

        display: flex;
        justify-content: center;
        align-items: center;

        &__container {
            display: flex;
            justify-content: center;
            border: 20px solid rgba(0,0,0,.6);

            & > * {
                padding: 15px;
                background-color: #fff;
                border: none;
                border-right: 1px solid rgba(0,0,0,.6);
            }

            input[type="date"] {
                flex-basis: 190px;
            }

            button {
                border: none;
                color: #fff;
                background-color: rgba(red, 0.8);

                &:hover {
                    cursor: pointer;
                    background-color: rgba(red, 1);
                }
            }
        }
    }

</style>
