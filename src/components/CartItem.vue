<template>
<div class="book-item" v-bind:class="{'is-complete':book.completed}">

    <b>{{book.title}}</b><br />
    <b>Price:</b> {{book.price}}<br />
    <b>Qty:</b> {{book.qty}}<br />
    <div align="center">
        <button class="btn btn-success" >&nbsp;+&nbsp;</button>&nbsp;
        <button class="btn btn-info">&nbsp;-&nbsp;</button>&nbsp;
        <button class="btn btn-danger" v-on:click="Remove(book.bookid)">&nbsp;x&nbsp;</button>
    </div>

</div>
</template>

<script>
export default {
    name: "CartItem",
    props: ["book"],
    methods:{
        Remove(bookId){
            this.$emit('removeCartitem',bookId)
        }
    }

}
</script>

<style scoped>
.book-item {
    background: #dcf83e;
    padding: 10px;
    border-bottom: 1px rgb(0, 0, 0) dotted;
}
</style>