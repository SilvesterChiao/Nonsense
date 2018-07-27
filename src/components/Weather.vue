<template>
  <div>
    <div class="weather-box">
      <div class="weather-info">
        <div class="weather-city">
          {{ weather.city }}
        </div>
        <div class="weather-temperature">
          {{ weather.temperature }}
        </div>
        <div class="weather-text">
          {{ weather.text }} | 空气{{ weather.quality }}  {{ weather.aqi }}
        </div>
      </div>
      <div class="weather-other">
        <div>
          <span>{{ weather.wind_direction }}</span>
          <span>{{ weather.wind_scale }}</span>
        </div>
        <div>
          <span>相对湿度</span>
          <span>{{ weather.humidity }}</span>
        </div>
        <div>
          <span>体感温度</span>
          <span>{{ weather.feels_like }}</span>
        </div>
      </div>
    </div>
    <div class="weather-future-box">
      <div class="weather-future" v-for="(item, index) in weather.future" :key="index">
        <span>{{ item.date }}</span>
        <span>{{ item.text }} | {{ item.quality }}</span>
        <span>{{ item.high }}/{{ item.low }} ℃</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'weather',
  data() {
    return {
      weather: {
        city: '杭州',
        text: '阴',
        temperature: '18℃',
        feels_like: '19.8℃',
        wind_direction: '北风',
        wind_scale: '1级',
        humidity: '72%',
        quality: '良',
        aqi: '59',
        future: [
          {
            date: '03-26',
            day: '星期二',
            text: '阵雨转多云',
            high: '20',
            low: '12',
            quality: '良',
          },
          {
            date: '03-27',
            day: '星期三',
            text: '多云转晴',
            high: '24',
            low: '12',
            quality: '良',
          },
          {
            date: '03-28',
            day: '星期四',
            text: '晴转多云',
            high: '27',
            low: '14',
            quality: '良',
          },
        ],
      },
    };
  },
};
</script>

<style lang="scss">

</style>

<style lang="scss" scoped>
.weather-box {
  position: relative;
  width: 100%;
  height: 500px;
  background-color: #3f51b5;
}

.weather-info {
  padding: 16px 20px;
}

.weather-city {
  font-size: 14px;
  color: #fff;
}

.weather-temperature {
  margin-top: 8px;
  font-size: 24px;
  color: #fff;
}

.weather-text {
  margin-top: 8px;
  font-size: 12px;
  color: #fff;
}

.weather-other {
  display: flex;
  justify-content: space-around;
  position: absolute;
  bottom: 16px;
  width: 100%;
}

.weather-other div {
  display: flex;
  flex-direction: column;
  width: 33.33%;
  border-right: 1px solid #fff;
  text-align: center;
}

.weather-other div:last-child {
  border-right: none;
}

.weather-other div span {
  font-size: 14px;
  color: #fff;
}

.weather-other div span:last-child {
  height: 30px;
  line-height: 30px;
  font-size: 20px;
}

.weather-future-box {
  padding: 0 14px;
  box-sizing: border-box;
  width: 100%;
  border-bottom: 1px solid #e1e1e1;
}

.weather-future {
  display: flex;
  justify-content: space-around;
  width: 100%;
  height: 40px;
  border-bottom: 1px solid #e1e1e1;
  line-height: 40px;
}

.weather-future:last-child {
  border-bottom: none;
}

.weather-future span {
  display: inline-block;
  width: 33.33%;
  font-size: 14px;
  text-align: center;
}

</style>
