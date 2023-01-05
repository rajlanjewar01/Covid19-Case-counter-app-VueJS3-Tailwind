<template>
    <select 
    class="px-4 py-3 rounded-full form-select block border rounded" 
    v-model="selected"
    >
        <option value="0">select country</option>
        <option v-for="country in countries" :value="country.ID">
            {{ country.Country }}
        </option>
    </select>
</template>
<script>
    export default{
        name: 'CountrySelect',
        props: ['countries'],
        data(){
            return {
                selected : 0
            };
        }
    }
</script>