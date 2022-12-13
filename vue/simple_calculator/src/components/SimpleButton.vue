 <template>
    <div class="buttons">
        <button @click="addNumbers" type="text" class="singleButton">+</button>
        <button @click="subNumbers" type="text" class="singleButton">-</button>
        <button @click="mulNumbers" type="text" class="singleButton">*</button>
        <button @click="divNumbers" type="text" class="singleButton">/</button>
        <button @click="calculate" type="text" class="specialButton">=</button>
    </div>
</template>

<script>
export default {
    emits: ['addNumbers', 'subNumbers', 'mulNumbers', 'divNumbers', 'calculate'],

    methods: {
        addNumbers() {
            this.$emit("addNumbers")
        },

        subNumbers() {
            this.$emit("subNumbers")
        },

        mulNumbers() {
            this.$emit("mulNumbers")
        },

        divNumbers() {
            this.$emit("divNumbers")
        },

        calculate() {
            this.$emit("calculate")
        },
    }
}


</script>

<style>
.buttons {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
}

.singleButton {
    padding: 35px 80px 35px 80px;
    margin-top: 1.5rem;
    font-size: 1rem;
    color: blue;
    font-weight: 600;
}

.specialButton {
    padding: 50px 425px 50px 425px;
    margin-top: 2rem;
    color: black;
    font-size: 2rem;
    font-weight: 600;
}

</style>