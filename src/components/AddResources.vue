<template>
    <base-dialog v-if="inputIsInValid" title="Invalid Input" @close="confirmError()">
        <template #default>
            <p>At least one input value is invalid,Please check all your input values.</p>

        </template>
        <template #actions>
            <base-button @click="confirmError">Okay </base-button>
        </template>
    </base-dialog> <base-card>
        <form @submit.prevent="submitForm">
            <div class="form-control">
                <label for="title">Title</label>
                <input type="text" id="title" name="title" ref="titleInput">
            </div>
            <div class="form-control">
                <label for="description">Description</label>
                <textarea rows="3" id="description" name="description" ref="descriptionInput">
                                                                                                                                                                                                                                                                                                                                                                                        </textarea>
            </div>
            <div class="form-control">
                <label for="link">Link</label>
                <input type="url" id="link" name="link" ref="linkInput">
            </div>
            <div>

                <base-button type="submit">Add Resource</base-button>
            </div>
        </form>
    </base-card>
</template>

<script>
export default {
    data() {
        return {
            inputIsInValid: false,
        }
    },
    inject: ['addResource'],
    methods: {
        submitForm() {
            const enteredTitle = this.$refs.titleInput.value;
            const enteredDescription = this.$refs.descriptionInput.value;
            const enteredLink = this.$refs.linkInput.value;
            if (enteredTitle === '' || enteredDescription === '' || enteredLink === '') {
                this.inputIsInValid = true;
                return;
            }
            this.addResource(enteredTitle, enteredDescription, enteredLink);
        },
        confirmError() {
            this.inputIsInValid = false;
        }
    }
}
</script>

<style scoped>
label {
    font-weight: bold;
    display: block;
    margin-bottom: 0.5rem;
}

input,
textarea {
    display: block;
    width: 100%;
    font: inherit;
    padding: 0.15rem;
    border: 1px solid #ccc;
}

input:focus,
textarea:focus {
    outline: none;
    border-color: #3a0061;
    background-color: #f7ebff;
}

.form-control {
    margin: 1rem 0;
}
</style>