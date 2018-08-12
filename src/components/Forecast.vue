<template>
    <div>
      
      <div class="hero">
            <div class="container">
                <form action="#" class="find-location">
                    <input type="text" placeholder="Find your location..." v-model="query">
                    <input type="submit" value="Find" @click.prevent="getData(query)">
                </form>
            </div>
      </div>

      <div class="container">
        
            <div class="forecast-section" v-if="!error">
                    
                    <div class="current-weather">
                        <div class="current-weather-header">
                            <span>{{currentWeather().day}}</span>
                            <span>{{currentWeather().date}}</span>
                        </div>

                        <div class="current-weather-body">

                            <div class="current-weather-city">{{ city.name }}</div>
                            <div class="current-weather-temp-wrapper">
                                <span class="current-weather-temp">{{current.main.temp | round(current.main.temp)}}<sup>o</sup>C</span>
                                <img :src="currentWeather().icon" :title="currentWeather().description" class="current-weather-icon">
                            </div>

                            <div class="current-weather-footer">
                                <div title="Humidity">
                                    <img src="@/assets/images/ic_umbrella.png" alt="">
                                    <span>{{current.main.humidity}}%</span>
                                </div>
                                <div title="Wind speed">
                                    <img src="@/assets/images/ic_wind.png" alt="">
                                    <span>{{current.wind.speed | kmh(current.wind.speed)}}km/h</span>
                                </div>
                                <div title="Wind direction">
                                    <img src="@/assets/images/ic_compass.png" alt="">
                                    <span>{{current.wind.deg | direction(current.wind.deg)}}</span>
                                </div>
                            </div>
                        </div>

                    </div>

                    <div class="forecast-weather-wrapper">
                        
                        <div class="forecast-weather" v-for="(fc, index) in forecastList" :key="index">

                            <div class="forecast-weather-header">
                                <span>{{fc.dt | toDate(fc.dt)}}</span>
                            </div>

                            <div class="forecast-weather-body">
                                <img :src="getForecastData(index).icon" :title="getForecastData(index).description">
                                <div class="forecast-weather-temp">
                                    {{fc.main.temp | round(fc.main.temp)}}<sup>o</sup>C
                                </div>
                            </div>
                        </div>

                    </div>
            </div>

            <div class="forecast-no-result" v-else>
                <h1>No result, city not found</h1>
            </div>

        </div>
    </div>
</template>

<script>
import axios from 'axios';
import moment from 'moment';

const APP_ID = '9fe214c1058ab59efce91424411b8d39';
const API_URL_FORECAST = 'https://api.openweathermap.org/data/2.5/forecast';
const API_URL_CURRENT = 'https://api.openweathermap.org/data/2.5/weather';
const CNT = 6;
const ICON_URL = 'https://openweathermap.org/img/w/';

export default {

    data(){

      return {

        error : false,

        query : '',

        city : {},

        current : {},

        forecastList : []
      }

    },

    methods : {

      getForecast(city){

          axios.get(`${API_URL_FORECAST}?q=${city}&cnt=${CNT}&units=metric&appid=${APP_ID}`)
          .then(res => {
            // console.log(res.data);
            this.city = res.data.city;
            this.forecastList = res.data.list;
            this.error = false;
          })
          .catch(err => {
            console.log(err);
            this.error = true;
          });

      },

      getCurentWeather(city){
          axios.get(`${API_URL_CURRENT}?q=${city}&units=metric&appid=${APP_ID}`)
            .then(res => {
              // console.log(res.data);
              this.current = res.data;
              this.error = false;
            })
            .catch(err => {
              console.log(err);
              this.error = true;
            });
      },

      getData(city){

        this.getCurentWeather(city);
        this.getForecast(city);
        

      },

      getForecastData(index){

        return {
          icon : `${ICON_URL}${this.forecastList[index].weather[0].icon}.png`,

          description : this.forecastList[index].weather[0].description
        }

      },

       currentWeather(){

            return {

                day : moment.unix(this.current.dt).utc().local().format('dddd'),

                date : moment.unix(this.current.dt).utc().local().format('DD MMMM YYYY'),

                icon : `${ICON_URL}${this.current.weather[0].icon}.png`,

                description : this.current.weather[0].description

            }

      }


    },

    filters : {
      
        toDate(timestamp){
          return moment.unix(timestamp).utc().local().format('dddd HH:mm');
        },

        round(number){
          return Math.round(number);
        },

        direction(degree){
          
          if(degree>337.5) return 'North';
          if(degree>292.5) return 'North West';
          if(degree>247.5) return 'West';
          if(degree>202.5) return 'South West';
          if(degree>157.5) return 'South';
          if(degree>122.5) return 'South East';
          if(degree>67.5)  return 'East';
          if(degree>22.5)  return 'North East';
          return 'North';

        },

        kmh(ms){
          return Math.round(ms * 3.6);
        }

    },

    created(){
      this.getData('Yogyakarta');
    }

}

</script>

<style scoped>

/* HERO-SECTION-STYLE 
----------------------------------------------
*/

.hero {
    background: url('../assets/images/hero.jpg');
    background-size: cover;
    padding: 75px 0;
    min-height: 350px;
}

input {
    outline: none;
    border: none;
    border-radius: 50px;
}

.find-location {
    position: relative;
    margin-bottom: 70px;
}

input[type="text"] {
    width: 100%;
    padding: 20px 130px 20px 20px;
    background: #1E212A;
    color: white;
}

input[type="submit"] {
    position: absolute;
    top: 5px;
    right: 5px;
    bottom: 5px;
    padding: 0 38px;
    background: #228FB9;
    color: #fff;
}

/* FORECAST-SECTION-STYLE
-----------------------------------------------------
*/
.forecast-section {
    display: flex;
    flex-wrap:  nowrap;
    background: #323544;
    color: #fff;
    border-radius: 10px;
    overflow: hidden;
    min-height: 285px;
    margin-top: -150px;
    margin-bottom: 50px;
}

.forecast-no-result {
    background: #323544;
    min-height: 285px;
    margin-top: -150px;
    margin-bottom: 50px;
    padding: 30px;
    border-radius: 10px;
}

.forecast-weather-wrapper {
    display: flex;
    flex-basis: 0;
    flex-grow: 1;
}

.forecast-section .current-weather {
    flex-basis: 1;
}

.forecast-section .forecast-weather {
    flex-basis: 0;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.forecast-section .forecast-weather:nth-child(odd){
    background: #262A35;
}


.current-weather-header,
.forecast-weather-header {

    background: #2D2F3C;  
    min-height: 40px;
    display: flex;
    justify-content: center;
    align-items: center;

}

.current-weather-header {
    display: flex;
    justify-content: space-between;
    padding: 0px 10px;
}

.forecast-weather-header {
    width: 100%;
    text-align: center;
}

.forecast-section .forecast-weather:nth-child(odd) > .forecast-weather-header{
    background: #222631;
}

.current-weather-temp-wrapper {
    display: flex;
    align-items: center;
}

.current-weather-temp {
    font-size: 90px;
}

.current-weather-icon {
    height: 60px;
    margin-left: 40px;
    
}

.current-weather-body {
    padding: 30px;
}

.current-weather-footer {
    display: flex;
}

.current-weather-footer > *:not(:first-child) {
    margin-left: 20px;
}

.current-weather-footer span {
    margin-left: 10px;
}

.current-weather-city {
    font-size: 18px;
}

.forecast-weather-body {

    margin-top: 40px;
}

.forecast-weather-temp {
    font-size: 24px; 
    margin-top: 40px;
}

@media screen and (max-width: 990px) {
    
    .forecast-section {
        flex-wrap: wrap;
        min-height: 500px;
    }

    .current-weather {
        flex-basis: 100%;
    }

    .forecast-weather-body {

        margin-top: 20px;

    }

    .forecast-weather-temp {
     
        margin-top: 20px;

    }


}

@media screen and (max-width: 400px) {
    .current-weather-temp {
        font-size: 65px;
    }

    .current-weather-footer img{
        display: block;
    }
    
    .current-weather-footer span {
        margin-left: 0px;
    }

    .current-weather-header {
        padding-right: 20px;
    }
    
    .forecast-weather-temp {
        font-size: 16px;
        text-align: center;
    }
}





</style>
