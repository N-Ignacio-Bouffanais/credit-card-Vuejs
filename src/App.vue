<script>
let input = document.getElementById("name")
let nombre =input ?input.value : ''

export default {
  data() {
    return {
      valor: 123,
      date: "09/26",
      name: nombre,
      number: "9591 6489 6389 1011",
    };
  },
  methods: {
    Confirm() {
      let y = document.getElementById("form");
      y.style.display = "none";
      let x = document.getElementById("success");
      x.style.display = "flex";
    },
  }
};
</script>

<template>
  <section class="container-left">
    <figure class="image-card-front">
      <img src="/bg-card-front.png" alt="credit card front" />
    </figure>
    <figure class="image-card-back">
      <img src="/bg-card-back.png" alt="credit card back" />
    </figure>
    <span class="circle_one"></span>
    <span class="circle_two"></span>
    <p class="number">{{ number }}</p>
    <p class="name">{{ name }}</p>
    <p class="date">{{ date }}</p>
    <p class="number-back">{{ valor }}</p>
  </section>
  <section class="container-right">
    <form v-on:submit.prevent="onSubmit" class="form" id="form">
      <p class="name">
        <label for="Jane Appleseed">CARDHOLDER NAME</label>
        <input
          type="text"
          name="Jane Appleseed"
          placeholder="e.g. Jane Appleseed"
          id="name"
          required
        />
      </p>
      <p class="number">
        <label for="CARD NUMBER">CARD NUMBER</label>
        <input
          type="tel"
          name="CARD NUMBER"
          id="number"
          placeholder="e.g. 1234 5678 9123 0000"
          required
        />
      </p>
      <div class="date-container">
        <div class="date">
          <label for="Jane Appleseed">EXP. DATE (MM/YY)</label>
          <input type="month" value="2010-02" name="date" id="date" required />
        </div>
        <div class="cvc">
          <label for="CVC">CVC</label>
          <input
            type="number"
            name="CVC"
            required
            placeholder="e.g. 123"
            id="cvc"
          />
        </div>
      </div>
      <button v-on:click="Confirm" id="button">Confirm</button>
    </form>
    <div class="success" id="success">
      <span class="circle">
        <i class="fa-solid fa-check"></i>
      </span>
      <h1 class="title">THANK YOU!</h1>
      <p>We've added your card details</p>
      <button>Continue</button>
    </div>
  </section>
</template>

<style></style>
