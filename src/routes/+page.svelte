<script>
    import "../app.css";

    let result = '';

    function handleClick(event) {
        const buttonValue = event.target.innerText;

        if (buttonValue === 'AC') {
            result = '';
        } else if (buttonValue === 'DEL') {
            result = result.slice(0, -1);
        } else if (buttonValue === '=') {
            result = eval(result);
        } else if (buttonValue === '.') {
            if (result === '') {
                result = '0.';
            } else if (!result.includes('.')) {
                result += '.';
            }
        } else {
            result += buttonValue;
        }
    }
</script>


<div class="container">
    <div class="resultsContainer">
        <div class="resultTextContainer">
            <div class="resultText">{result}</div>
        </div>

        <div class="resultContainer">
            <div class="result">{result}</div>
        </div>
    </div>

    <div class="buttonContainer">
        <div class="buttonGroupContainer">
            <button class="button buttonAc" on:click={handleClick}>AC</button>
            <button class="button buttonDel" on:click={handleClick}>DEL</button>
            <button class="button buttonOperand" on:click={handleClick}>/</button>
        </div>

        <div class="buttonGroupContainer">
            <button class="button" on:click={handleClick}>7</button>
            <button class="button" on:click={handleClick}>8</button>
            <button class="button" on:click={handleClick}>9</button>
            <button class="button buttonOperand" on:click={handleClick}>*</button>
        </div>
    
        <div class="buttonGroupContainer">
            <button class="button" on:click={handleClick}>4</button>
            <button class="button" on:click={handleClick}>5</button>
            <button class="button" on:click={handleClick}>6</button>
            <button class="button buttonOperand" on:click={handleClick}>-</button>
        </div>
    
        <div class="buttonGroupContainer">
            <button class="button" on:click={handleClick}>1</button>
            <button class="button" on:click={handleClick}>2</button>
            <button class="button" on:click={handleClick}>3</button>
            <button class="button buttonOperand" on:click={handleClick}>+</button>
        </div>
    
        <div class="buttonGroupContainer">
            <button class="button" on:click={handleClick}>0</button>
            <button class="button" on:click={handleClick}>.</button>
            <button class="button buttonEq" on:click={handleClick}>=</button>
        </div>
    </div>
</div>