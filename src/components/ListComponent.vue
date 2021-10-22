<template>
    <div class="list">
        <h3>Ich bin eine Liste!</h3>
        <div v-for="item in dataJson" :key="item.id">
            {{ item.name }}
        </div>
    </div>
</template>

<script>
//TODO: Later we switch to a nosql database. Like MongoDB or CouchDB.
import jsonFile from "./data.json"

export default {
    data() {
        return {
            dataJson: jsonFile
        };
    },
}
</script>

<style>
    .list {
        padding-top: 5em;
        padding-bottom: 5em;
    }
</style>