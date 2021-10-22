<template>
    <div class="list">
        <h3>Deine Liste:</h3>
        <div v-for="item in dataJson" :key="item.id" class="list-element">
            <h3>{{ item.name }}</h3>
            <p>
                <span>Typ:</span> {{ item.typ }}
            </p>
            <p>
                <span>Bewertung:</span> {{ item.score }}
            </p>
            <p>
                <span>Abgeschlossen?</span> {{ (item.done === 1) ? 'Ja' : 'Nein' }}
            </p>
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
    .list-element {
        border: 1px solid #212121;
        margin-bottom: 1em;
    }
</style>