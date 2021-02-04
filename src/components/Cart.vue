<template>
<div>
    <h2>Books in Cart</h2>
    <div v-bind:key="book.bookid" v-for="book in cart">
        <CartItem v-bind:book="book" v-on:removeCartitem="Remove(book.bookid)" />
    </div>
</div>
</template>

<script>
import CartItem from './CartItem.vue';
export default {
    name: "Cart",
    props: ["cart"],
    components: {
        CartItem
    },
    methods:{
        Remove(bookId){
            this.$emit('removeCartitem',bookId);
        }
    }

}
</script>

<style scoped>
.book-item {
    background: #ff7300;
    padding: 10px;
    border-bottom: 1px rgb(0, 0, 0) dotted;
}
</style>