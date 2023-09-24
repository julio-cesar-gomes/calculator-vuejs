      <script>
      export default {
        data() {
          return {
            num1: 0,
            num2: 0,
            operator: "+",
            result: 0,
          };
        },
        methods: {
          calculateResult() {
            const n1 = parseFloat(this.num1);
            const n2 = parseFloat(this.num2);
            
            switch (this.operator) {
              case "+":
                this.result = n1 + n2;
                break;
              case "-":
                this.result = n1 - n2;
                break;
              case "*":
                this.result = n1 * n2;
                break;
              case "/":
                if (n2 !== 0) {
                  this.result = n1 / n2;
                } else {
                  this.result = "Error";
                }
                break;
            }
          },
        },
      };
      </script>

    <template>
      <div class="calculator">
        <h2>Calculadora Aritmética</h2>
        <div class="input-fields">
          <input v-model="num1" type="number" placeholder="Número 1" @input="calculateResult" />
          <select v-model="operator" @input="calculateResult">
            <option value="+">Somar</option>
            <option value="-">Subtrair</option>
            <option value="*">Multiplicar</option>
            <option value="/">Dividir</option>
          </select>
          <input v-model="num2" type="number" placeholder="Número 2" @input="calculateResult" />
        </div>
        <div class="result">
          <p>Resultado: {{ result }}</p>
        </div>
      </div>
    </template>


<style scoped>
.calculator {
  text-align: center;
  margin: 20px;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.input-fields {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 20px 0;
}

input[type="number"] {
  width: 100px;
  margin: 0 10px;
  padding: 5px;
}

select {
  padding: 5px;
}

.result {
  font-weight: bold;
}
</style>
