<script>
    let fibonacciNumbers = [0, 1];
    let month = 0;

    function calculateFibonacci() {
        while (fibonacciNumbers.length <= month) {
            let last = fibonacciNumbers[fibonacciNumbers.length - 1];
            let secondLast = fibonacciNumbers[fibonacciNumbers.length - 2];
            fibonacciNumbers.push(last + secondLast);
        }
    }

    function nextMonth() {
        month += 1;
        calculateFibonacci();
    }

    function previousMonth() {
        if (month > 0) {
            month -= 1;
            calculateFibonacci();
        }
    }

    function updateMonth(event) {
        month = parseInt(event.target.value);
        calculateFibonacci();
    }
</script>

<h1>Os coelhos de Fibonacci 🐇</h1>

<p>
    Mês:
    <input type="number" bind:value={month} min="0" on:input={updateMonth} />
    <br>
    <br>
    <button on:click={previousMonth}>Mês anterior</button>
    <br>
    <br>
    <br>
    <button on:click={nextMonth}>Próximo mês</button>
    <br>
    <br>
</p>

<p>Após {month} meses, haverá {fibonacciNumbers[month]} ninhadas de coelhos!</p>