<script setup>
import { defineProps,ref } from 'vue';
import { pay } from '../store/store';

const props= defineProps(["id", "numberOfPerson", "totalPerPerson", "paid"])
const paid= ref(false)

handleChange=(e)=>{
    paid= e.target.value

    pay(props.id, paid)
}
</script>

<template>
    <div>
        <div class="person_number">
            Person {{ props.numberOfPerson}}
        </div>
        <div class="person_to_pay">{{new Intl.NumberFormat('en-US',{
            style: "currency",
            currency:"USD",
        }).format(props.totalPerPerson)}}</div>
        <div class="paid">
            <input type="checkbox" name="" id="" @change="handleChange"> paid
        </div>
    </div>
</template>

<style scoped>

</style>