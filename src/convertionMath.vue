<template>
    <div>
        {{UnitV}}/{{RateV}}->{{this.amount*RateV}}
    </div>
</template>

<script>
export default {
    props: ['unit','rate','value','amount'],
    data() {
      return {
          UnitV:this.unit,
          RateV:this.rate,
          amountV:this.amount
      };
    }
}
</script>