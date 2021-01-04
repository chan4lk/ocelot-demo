<template>
  <div class="container">
    <h1 id="tableLabel">Weather forecast</h1>

    <p>This component demonstrates fetching data from the server.</p>

    <p v-if="!forecasts">Loading...</p>

    <table
      v-if="forecasts"
      class="table table-striped"
      aria-labelledby="tableLabel"
    >
      <thead>
        <tr>
          <th>Date</th>
          <th>Temp. (C)</th>
          <th>Temp. (F)</th>
          <th>Summary</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="forecast of forecasts" :key="forecast.date">
          <td>{{ forecast.date }}</td>
          <td>{{ forecast.temperatureC }}</td>
          <td>{{ forecast.temperatureF }}</td>
          <td>{{ forecast.summary }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "FetchData",
  data() {
    return {
      forecasts: [],
    };
  },
  mounted() {
    this.getWeatherForecasts();
  },
  methods: {
    getWeatherForecasts() {
      const baseUrl = "";

      const data = new URLSearchParams();
      data.append("grant_type", "client_credentials");
      data.append("client_id", "secret_client_id");
      data.append("client_secret", "secret");
      data.append("scope", "apiscope");

      axios
        .post(`${baseUrl}/api/token`, data, {
          headers: {
            "Content-Type": "application/x-www-form-urlencoded",
          },
        })
        .then((auth) => {
          axios
            .get(`${baseUrl}/api/weather`, {
              headers: {
                Authorization: `Bearer ${auth.data.access_token}`,
              },
            })
            .then((response) => {
              this.forecasts = response.data;
            })
            .catch(function (error) {
              alert(error);
            });
        });
    },
  },
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
