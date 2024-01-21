<template>
    <div class="container">
        <div class="row">
            <div class="col">
                <h1 class="mt-5">Login</h1>
                <hr />
                <FormTag @myevent="submitHandler" name="MyForm" event="myevent">
                    <TextInput 
                        v-model="email" 
                        label="Email" 
                        type="email" 
                        name="email" 
                        required="true" />
                    <TextInput 
                        v-model="password" 
                        label="Password" 
                        type="password" 
                        name="password" 
                        required="true" />
                    <hr />
                    <input class="btn btn-primary" type="submit" value="Login">
                </FormTag>
            </div>
        </div>
    </div>
</template>

<script>
import TextInput from './../components/forms/TextInput.vue'
import FormTag from './forms/FormTag.vue'

export default {
    name: 'AppLogin',
    data() {
        return {
            email: "",
            password: ""
        }
    },
    components: {
        TextInput,
        FormTag
    },
    methods: {
        submitHandler() {
            console.log("submitHanlder called: success");
        }
    }
}
</script>