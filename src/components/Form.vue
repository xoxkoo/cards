<script>
export default {
    data() {
        return {
            show: false,
            category: '',
            mission: ''
        }
    },
    methods: {
        add() {
            if (this.category != '' && this.mission != '')
            this.$emit('add', [this.category, this.mission])
            this.category = ''
            this.mission = ''
        },
        show() {
            if (this.show == true) {
                document.querySelector('form').style.display = 'none'
                document.querySelector('#showBtn').style.display = 'block'   
            }
            else {
                document.querySelector('form').style.display = 'block'
                document.querySelector('#showBtn').style.display = 'none'   
            }
        }
    },
}
</script>

<template>
<div></div>
    <!-- <div>
        <button id="showBtn" v-on:click="show()">Zobraziť</button>
        <form @submit.prevent="add()" style="">
            <input type="text" class="category-input" placeholder="Kategória" v-model="category">
            <textarea class="mission-input" placeholder="Úloha" v-model="mission" rows="3"></textarea>
            <button type="submit">Pridať</button>
        </form>
    </div> -->
</template>

<style>
form {
    margin: auto;
    width: 22rem;
}

button {
    display: block;
    padding: 1em 2rem;
    border-radius: 1rem;
    border: none;
    cursor: pointer;
    background: #8EB8E5;
    margin: 1em auto;
}

input, textarea {
    display: block;
    background: rgba(161, 196, 236, 0.5);
    border: 1px solid #474747;
    border-radius: .75rem;
    padding: 1rem 1.5rem;
    margin: .5em 0;
    width: 100%;
    font-family: inherit;
    font-size: .95rem;
    transition: .35s;
}

input:focus,
textarea:focus {
    background: rgba(161, 196, 236, 1);
}
</style>