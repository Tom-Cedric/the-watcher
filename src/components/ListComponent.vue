<template>
    <div class="list">
        <h3>Deine Liste:</h3>
        <div class="container">
            <table class="table">
                <thead>
                    <th>#</th>
                    <th>Name</th>
                    <th>Typ</th>
                    <th>Bewertung</th>
                    <th>Abgeschlossen?</th>
                </thead>
                <tbody>
                    <tr v-for="item in dataJson" :key="item.id">
                        <td scope="row">{{ item.id }}</td>
                        <td>{{ item.name }}</td>
                        <td>{{ item.typ }}</td>
                        <td>{{ item.score }} / 5</td>
                        <td>
                            <button v-if="item.done === 1" type="button" class="btn btn-secondary btn-sm">
                                <span class="material-icons" style="vertical-align: middle;">
                                    radio_button_unchecked
                                </span>
                            </button>
                            <button v-else type="button" class="btn btn-success btn-sm" disabled>
                                <span class="material-icons" style="vertical-align: middle;">
                                    check_circle_outline
                                </span>
                            </button>
                        </td>
                    </tr>
                </tbody>
            </table>
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
    .card {
        align-content: center;
    }
</style>