

<template>
  <div class="text-white container mt-5">
    <div id="test">
      <h1 class="text-center">Deret Fibonacci Generator</h1>
    <div class="d-flex">
      <input type="number" class="form-control" v-model="number" :max="99999" @keyup.enter="fibonacciSequence" />
    </div>
    <h4 class="mt-3">Hasil</h4>
  <div>{{ fibonacci }}</div>
</div>

  </div>
</template>

<script>

export default {
  data() {
    return {
      number: null,
      fibonacci: []
    }
  },
  mounted() {

  },
  methods: {
    getTimestamp: function () {
      return Date.now();
    },
    fibonacciSequence: function(e) {
      var i;
      var fib = [];
      var result = [];

      fib[0] = 0;
      fib[1] = 1;
      for (i = 2; i < this.number; i++) {
        // Next fibonacci number = previous + one before previous
        fib[i] = fib[i - 2] + fib[i - 1];
        result.push(fib[i]);
      }
      result.unshift(1);
      result.unshift(0);
      
      this.fibonacci = result;
      // alert("Success, server responded with: " + this.getTimestamp() );
    }
    
   }
}

</script>