<template>
    <div class="date-picker-container">
      <input
        type="text"
        v-model="selectedDate"
        @focus="showDatePicker"
        placeholder="Select a date"
      />
      <div v-if="isDatePickerVisible" class="date-picker">
        <div class="calendar">
          <div class="month">
            <button @click="previousMonth">&lt;</button>
            <span>{{ currentMonth }}</span>
            <button @click="nextMonth">&gt;</button>
          </div>
          <div class="days">
            <div v-for="day in days" :key="day" class="day">{{ day }}</div>
            <div v-for="blank in firstDayOffset" :key="blank" class="blank"></div>
            <div
              v-for="date in daysInMonth"
              :key="date"
              class="date"
              @click="selectDate(date)"
            >
              {{ date }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        selectedDate: '',
        isDatePickerVisible: false,
        currentDate: new Date(),
      };
    },
    computed: {
      currentMonth() {
        return this.currentDate.toLocaleString('default', { month: 'long' });
      },
      daysInMonth() {
        const year = this.currentDate.getFullYear();
        const month = this.currentDate.getMonth() + 1;
        const lastDay = new Date(year, month, 0).getDate();
        return Array.from({ length: lastDay }, (_, i) => i + 1);
      },
      firstDayOffset() {
        const firstDay = new Date(this.currentDate.getFullYear(), this.currentDate.getMonth(), 1).getDay();
        return Array.from({ length: firstDay }, (_, i) => i);
      },
      days() {
        return ['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat'];
      },
    },
    methods: {
      showDatePicker() {
        this.isDatePickerVisible = true;
      },
      hideDatePicker() {
        this.isDatePickerVisible = false;
      },
      previousMonth() {
        this.currentDate.setMonth(this.currentDate.getMonth() - 1);
      },
      nextMonth() {
        this.currentDate.setMonth(this.currentDate.getMonth() + 1);
      },
      selectDate(date) {
        this.selectedDate = `${date}-${this.currentMonth}-${this.currentDate.getFullYear()}`;
        this.hideDatePicker();
      },
    },
  };
  </script>
  
  <style scoped>
  .date-picker-container {
    position: relative;
  }
  
  input {
    padding: 10px;
  }
  
  .date-picker {
    position: absolute;
    top: 100%;
    left: 0;
    border: 1px solid #ccc;
    background-color: #fff;
    padding: 10px;
    z-index: 1;
  }
  
  .calendar {
    display: flex;
    flex-direction: column;
  }
  
  .month {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 10px;
  }
  
  .days {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
  }
  
  .day {
    text-align: center;
    padding: 5px;
    font-weight: bold;
  }
  
  .blank {
    visibility: hidden;
  }
  
  .date {
    text-align: center;
    padding: 5px;
    cursor: pointer;
  }
  
  </style>
  