<template>
    <div class="list">
        <h3>Deine Liste:</h3>
        <div class="container">
            <div v-for="item in dataJson" :key="item.id" class="list-element">
                <div class="row">
                    <div class="col"></div>
                    <div class="col">
                        <div class="card" style="width: 100%; margin-bottom: 1em;">
                            <div class="card-body">
                                <h5 class="card-title">{{ item.name }}</h5>
                                <p>
                                    <span>Typ:</span> {{ item.typ }}
                                </p>
                                <p>
                                    <span>Bewertung:</span> {{ item.score }}
                                </p>
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
                            </div>
                        </div>
                    </div>
                    <div class="col"></div>
                </div>
            </div>  
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