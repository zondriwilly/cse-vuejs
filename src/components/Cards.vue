<template>
    <div class="card">
        <h2 v-html="title"></h2>
        <a :href="url">{{ url }}</a>
        <p> {{ desc }} </p>
    </div>
</template>

<script>
export default {
    name: 'Cards',
    props : ['title', 'url', 'desc']
}
</script>

<style scooped>
.card  {
    border: 0;
    padding: 20px;
    width: 700px;
    border-radius: 9px;
    background: #252526;
    color: #fff;
    display: block;
    margin: 0 auto;
    margin-bottom: 20px;
}
a {
    color: rgb(7, 201, 23);
    margin: 5px 0;
    margin-top: 2px;
    display: block;
    text-decoration: none;
}
p {
    color: #b7b7b7;
}
</style>