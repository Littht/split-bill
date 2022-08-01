<script setup>
import { store, getGrandTotal } from '../store/store';
import Label from './Label.vue';
import Person from './Person.vue';

</script>


<template>
    <div class="no_items" v-if="store.people.length === 0">No Items</div>
    <div class="people_view" v-if="store.people.length > 0">
        <div class="header">
            <div>
                <Label title="Total + Tip: " :value="getGrandTotal()" />
            </div>
            <div>
                <Label title="Remaining " :value="store.params.remaining" />
            </div>
        </div>
        <div class="people_container">
            <Person v-for="person in store.people" 
            :key="person.id" 
            :id="person.id" 
            :number-of-person="person.numberOfPerson" 
            :total-per-person="person.totalPerPerson"
            :paid="person.paid"/>
        </div>
    </div>
</template>

<script scoped></script>