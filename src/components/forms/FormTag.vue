<template>
    <form @submit.prevent="submit" :ref="name" :event="event" :action="action" :method="method" autocomplete="off"
        class="needs-validation" novalidate>
        <slot></slot>
    </form>
</template>

<script>
export default {
    name: 'FormTag',
    props: ["action", "method", "name", "event"],
    methods: {
        submit() {
            let myForm = this.$refs[this.$props.name]
            console.log("myForm is", myForm)

            if (myForm.checkValidity()) {
                console.log("My event name: ", this.$props["event"]);
                console.log("Name: ", this.$props.name)
                this.$emit(this.$props.event)
            } else
                console.log('CheckValidity failed');
            myForm.classList.add('was-validated')
        }
    },
    /*  mounted() {
         console.log("Mounted");
         (function () {
             'use strict'
 
             // Fetch all the forms we want to apply custom Bootstrap validation styles to
             var forms = document.querySelectorAll('.needs-validation')
 
             // Loop over them and prevent submission
             Array.prototype.slice.call(forms)
                 .forEach(function (form) {
                     form.addEventListener('submit', function (event) {
                         if (!form.checkValidity()) {
                             event.preventDefault()
                             event.stopPropagation()
                         }
 
                         form.classList.add('was-validated')
                     }, false)
                 })
         })()
     } */
}
</script>