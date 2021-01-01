<template>
    <h1 id="tableLabel">Weather forecast</h1>

    <p>This component demonstrates fetching data from the server.</p>

    <p v-if="!forecasts"><em>Loading...</em></p>

    <table class='table table-striped' aria-labelledby="tableLabel" v-if="forecasts">
        <thead>
            <tr>
                <th>Date</th>
                <th>Temp. (C)</th>
                <th>Temp. (F)</th>
                <th>Summary</th>
            </tr>
        </thead>
        <tbody>
            <a href="FetchData.vue">FetchData.vue</a>
            <tr v-for="forecast of forecasts" v-bind:key="forecast">
                <td>{{ forecast.date }}</td>
                <td>{{ forecast.temperatureC }}</td>
                <td>{{ forecast.temperatureF }}</td>
                <td>{{ forecast.summary }}</td>
            </tr>
        </tbody>
    </table>
</template>


<script>
    import axios from 'axios'
    export default {
        name: "FetchData",
        data() {
            return {
                forecasts: []
            }
        },
        methods: {
            getWeatherForecasts() {
                const baseUrl = "https://localhost:44324";

                const data = new URLSearchParams();
                data.append("grant_type", "client_credentials");
                data.append("client_id", "secret_client_id");
                data.append("client_secret", "secret");
                data.append("scope", "apiscope");

                axios.post(`${baseUrl}/api/token`, data, {
                    headers: {
                        'Content-Type': 'application/x-www-form-urlencoded'
                    }
                }).then(auth => {
                    axios.get(`${baseUrl}/api/weather`, {
                        headers: {
                            "Authorization": `Bearer ${auth.data.access_token}`
                        }
                    })
                        .then((response) => {
                            this.forecasts = response.data;
                        })
                        .catch(function (error) {
                            alert(error);

                        });

                });
            }
        },
        mounted() {
            this.getWeatherForecasts();
        }
    }
</script>