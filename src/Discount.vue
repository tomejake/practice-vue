<template>
<div class="discount">
    <h4>지금 결제하면 {{salePer}}% 할인</h4>
</div>
</template>

<script>
export default {
    name : 'Discount',
    props : {
        salePer : Number,
    }
}
</script>

<style>

</style>