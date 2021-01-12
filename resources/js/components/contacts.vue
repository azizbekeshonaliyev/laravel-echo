<template>
    <div class="inbox_chat scroll">
        <contact-person v-for="person in contacts" :person="person" :key="'persons-' + person.id"></contact-person>
    </div>
</template>
<script>
    import ContactPerson from './include/contact-person';
    export default {
        components:{ContactPerson},
        props:['contacts']
    }
</script>
