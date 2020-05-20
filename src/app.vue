<template>
<div>
    <div>  
        <h1>Unit Converter</h1>
    </div>
    <div>
        <unitList :unitsList="units"></unitList>
    </div>
    <div>
        <h4>Base Unit : {{baseUnit}}</h4>
        <input type="text" name="baseUnitInput" placeholder="Unit"> 
        <button @click="setBaseUnit()">Set Unit</button>
        <h4>New Unit</h4>
        <unitAdd @added="addNewUnit($event)"></unitAdd>
        <input type="number" v-model.number="baseAmount">
        <ol>
            <li v-for="Units in this.units" :key="Units">
                <convertionMath :unit="Units.type" :rate="Units.rate" :value="convertionVal" :amount="baseAmount"></convertionMath>
            </li>
        </ol>

        
    </div>
</div>
</template>

<script>
    import unitAdd from "./unitAdd.vue";
    import unitList from "./unitList.vue";
    import convertionMath from "./convertionMath.vue";
    export default {
        components: {unitAdd, unitList, convertionMath},
        data() {
        return {
            baseAmount:1000,
            baseUnit: 'Please set a base unit to convert from.',
            units: []
        };
        },
        methods: {
        addNewUnit(Unit) {
            this.units.push(Unit);
        },
        setBaseUnit(){
            this.baseUnit=document.querySelector("input[name=baseUnitInput]").value;
        }
        }
    };
</script>