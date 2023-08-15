<img src="../javascript-logo.png" alt="JS logo" style="height:70px;"/> 
| [Home](https://mervy.github.io/javascript-working-with-dom) 
| [Exercises 01](https://mervy.github.io/javascript-working-with-dom/pages/exercises1) 
| [Exercises 02](https://mervy.github.io/javascript-working-with-dom/pages/exercises2) 
| [Exercises 03](https://mervy.github.io/javascript-working-with-dom/pages/exercises3) 


## 1
Aqui está o código JavaScript puro para resolver o exercício proposto, usando manipulação do DOM:

```javascript
document.addEventListener('DOMContentLoaded', function () {
    const calendar = document.querySelector('.calendar tbody');
    
    // Função para calcular a diferença em dias entre duas datas
    function calculateDateDifference(date1, date2) {
        const oneDay = 24 * 60 * 60 * 1000; // Milissegundos em um dia
        const diffDays = Math.round(Math.abs((date1 - date2) / oneDay));
        return diffDays;
    }
    
    // Função para alterar a cor de um elemento do calendário
    function changeColor(element, color) {
        element.style.backgroundColor = color;
    }
    
    // Manipular os inputs de data e realizar as ações
    const dateInputs = document.querySelectorAll('input[type="date"]');
    const submitButton = document.querySelector('button');
    
    submitButton.addEventListener('click', function () {
        const startDate = new Date(dateInputs[0].value);
        const endDate = new Date(dateInputs[1].value);
        
        // Exibir a diferença em dias
        const dateDifference = calculateDateDifference(startDate, endDate);
        const diffDisplay = document.createElement('p');
        diffDisplay.textContent = `Diferença em dias: ${dateDifference}`;
        document.body.appendChild(diffDisplay);
        
        // Mudar a cor dos dias entre as datas selecionadas
        const days = calendar.querySelectorAll('td');
        days.forEach(function (day) {
            const dayNumber = parseInt(day.textContent);
            const currentDate = new Date();
            currentDate.setFullYear(startDate.getFullYear(), startDate.getMonth(), dayNumber);
            
            if (currentDate >= startDate && currentDate <= endDate) {
                changeColor(day, 'blue'); // Mudar a cor para azul
            } else {
                changeColor(day, ''); // Resetar a cor
            }
        });
    });
});
```

Este código faz o seguinte:

1. Aguarda o carregamento do DOM antes de executar qualquer código.
2. Obtém a referência à tabela do calendário, aos inputs de data e ao botão de envio.
3. Define uma função para calcular a diferença em dias entre duas datas.
4. Define uma função para alterar a cor de um elemento do calendário.
5. Adiciona um ouvinte de evento ao botão de envio para realizar as ações quando o botão for clicado.
6. Converte as datas dos inputs para objetos de data.
7. Calcula a diferença em dias entre as datas e exibe o resultado.
8. Itera sobre os elementos de dia na tabela do calendário, compara as datas e altera a cor conforme necessário.

Lembre-se de adicionar o HTML correspondente à tabela, aos inputs de data e ao botão de envio para que o código funcione corretamente.

## 2. 
Aqui está o código corrigido para coletar duas datas usando inputs de data, calcular a diferença em dias e alterar a cor dos dias entre as datas selecionadas:

```javascript
document.addEventListener('DOMContentLoaded', function () {
    const calendar = document.querySelector('.calendar tbody');

    // Função para calcular a diferença em dias entre duas datas
    function calculateDateDifference(date1, date2) {
        const oneDay = 24 * 60 * 60 * 1000; // Milissegundos em um dia
        const diffDays = Math.round(Math.abs((date1 - date2) / oneDay));
        return diffDays;
    }

    // Função para alterar a cor de um elemento do calendário
    function changeColor(element, color) {
        element.style.backgroundColor = color;
    }

    // Manipular o botão de envio
    const submitButton = document.querySelector('button');

    submitButton.addEventListener('click', function () {
        const dateInputs = document.querySelectorAll('input[type="date"]');
        const startDate = new Date(dateInputs[0].value);
        const endDate = new Date(dateInputs[1].value);

        // Exibir a diferença em dias
        const dateDifference = calculateDateDifference(startDate, endDate);
        const diffDisplay = document.createElement('p');
        diffDisplay.textContent = `Diferença em dias: ${dateDifference}`;
        document.body.appendChild(diffDisplay);

        // Mudar a cor dos dias entre as datas selecionadas
        const days = calendar.querySelectorAll('td');
        days.forEach(function (day) {
            const dayNumber = parseInt(day.textContent);
            const currentDate = new Date();
            currentDate.setFullYear(startDate.getFullYear(), startDate.getMonth(), dayNumber);

            if (currentDate >= startDate && currentDate <= endDate) {
                changeColor(day, 'blue'); // Mudar a cor para azul
            } else {
                changeColor(day, ''); // Resetar a cor
            }

            if (currentDate.getTime() === startDate.getTime() || currentDate.getTime() === endDate.getTime()) {
                changeColor(day, 'orange'); // Mudar a cor para laranja
            }
        });
    });
});
```

Certifique-se de que o HTML também contenha os elementos corretos para os inputs de data, a tabela do calendário e o botão de envio. O código acima coletará duas datas, calculará a diferença em dias e alterará a cor dos dias no calendário conforme as datas selecionadas.

### 3.
Aqui está um exemplo de como você pode criar um componente HTML com uma caixa de texto, um rótulo (label) e um botão "calcular" para calcular o fatorial de um número e mostrar o tempo necessário para a execução:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fatorial Calculator</title>
</head>
<body>
    <div id="fatorial-calculator">
        <label for="number-input">Digite um número:</label>
        <input type="number" id="number-input" />
        <button id="calculate-button">Calcular Fatorial</button>
        <p id="result"></p>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function () {
            const numberInput = document.getElementById('number-input');
            const calculateButton = document.getElementById('calculate-button');
            const resultElement = document.getElementById('result');

            calculateButton.addEventListener('click', function () {
                const inputValue = parseInt(numberInput.value);

                if (!isNaN(inputValue)) {
                    const startTime = performance.now();
                    const factorial = calculateFactorial(inputValue);
                    const endTime = performance.now();
                    const executionTime = endTime - startTime;

                    resultElement.innerHTML = `Fatorial de ${inputValue}: ${factorial}<br>Tempo de execução: ${executionTime.toFixed(2)} ms`;
                } else {
                    resultElement.textContent = 'Digite um número válido.';
                }
            });

            function calculateFactorial(number) {
                if (number === 0 || number === 1) {
                    return 1;
                } else {
                    return number * calculateFactorial(number - 1);
                }
            }
        });
    </script>
</body>
</html>
```

Neste exemplo, criamos um componente que consiste em uma caixa de texto para inserir um número, um botão "Calcular" para executar o cálculo do fatorial e um elemento de parágrafo para exibir o resultado do cálculo e o tempo de execução. Quando o botão "Calcular" é clicado, o código verifica se o valor inserido é um número válido, calcula o fatorial e exibe o resultado junto com o tempo de execução.

### 4.
Aqui está um exemplo de como criar um componente que atenda às suas especificações:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Relatório de Notas</title>
</head>
<body>
    <div id="report-generator">
        <button id="create-report-button">Criar Relatório</button>
        <div id="report"></div>
    </div>

    <script>
        class Aluno {
            constructor(numero) {
                this._numero = numero;
                this._nota = Symbol('nota');
            }

            get numero() {
                return this._numero;
            }

            get nota() {
                return this._nota;
            }

            set nota(value) {
                if (value >= 0 && value <= 100) {
                    this._nota = value;
                } else {
                    console.error('Nota inválida');
                }
            }
        }

        document.addEventListener('DOMContentLoaded', function () {
            const createReportButton = document.getElementById('create-report-button');
            const reportElement = document.getElementById('report');

            createReportButton.addEventListener('click', function () {
                const alunos = [];
                const totalAlunos = 20;

                for (let i = 1; i <= totalAlunos; i++) {
                    const notaAleatoria = Math.floor(Math.random() * 101); // Gera um número aleatório entre 0 e 100
                    const aluno = new Aluno(i);
                    aluno.nota = notaAleatoria;
                    alunos.push(aluno);
                }

                const aprovados = alunos.filter(aluno => aluno.nota >= 60);
                const reprovados = alunos.filter(aluno => aluno.nota < 60);

                const reportContent = `
                    <h2>Relatório de Notas da Disciplina JavaScript</h2>
                    <table>
                        <tr>
                            <th>Aluno</th>
                            <th>Nota</th>
                            <th>Situação</th>
                        </tr>
                        ${alunos.map(aluno => `
                            <tr>
                                <td>Aluno Nº ${aluno.numero}</td>
                                <td>${aluno.nota}</td>
                                <td>${aluno.nota >= 60 ? 'APROVADO' : 'REPROVADO'}</td>
                            </tr>
                        `).join('')}
                    </table>
                    <p>APROVADOS: ${aprovados.length} (${(aprovados.length / totalAlunos * 100).toFixed(2)}%) | REPROVADOS: ${reprovados.length} (${(reprovados.length / totalAlunos * 100).toFixed(2)}%)</p>
                `;

                reportElement.innerHTML = reportContent;
            });
        });
    </script>
</body>
</html>
```

Neste exemplo, criamos uma classe `Aluno` para representar cada aluno com um número e uma nota, utilizando símbolos para armazenar a nota como variável privada. Quando o botão "Criar Relatório" é clicado, o código gera 20 registros de alunos com notas aleatórias entre 0 e 100. Em seguida, cria uma tabela de relatório mostrando os resultados de cada aluno e exibe as estatísticas de aprovação/reprovação no rodapé do relatório.

### 5. 
Aqui está um exemplo de como criar o componente HTML com as funcionalidades que você descreveu:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gerador de Números Aleatórios</title>
</head>
<body>
    <div id="number-generator">
        <label for="quantity-input">Quantidade de Números:</label>
        <input type="number" id="quantity-input" />
        <label for="min-value-input">Valor Mínimo:</label>
        <input type="number" id="min-value-input" />
        <label for="max-value-input">Valor Máximo:</label>
        <input type="number" id="max-value-input" />
        <button id="generate-button">Calcular</button>
        <div id="result"></div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function () {
            const quantityInput = document.getElementById('quantity-input');
            const minValueInput = document.getElementById('min-value-input');
            const maxValueInput = document.getElementById('max-value-input');
            const generateButton = document.getElementById('generate-button');
            const resultElement = document.getElementById('result');

            generateButton.addEventListener('click', function () {
                const quantity = parseInt(quantityInput.value);
                const minValue = parseInt(minValueInput.value);
                const maxValue = parseInt(maxValueInput.value);

                if (isNaN(quantity) || isNaN(minValue) || isNaN(maxValue)) {
                    resultElement.textContent = 'Preencha todos os campos com valores numéricos.';
                    return;
                }

                if (quantity >= minValue + maxValue) {
                    resultElement.textContent = 'A quantidade de números deve ser menor que a soma de valor mínimo e valor máximo.';
                    return;
                }

                const numbersArray = generateRandomNumbers(quantity, minValue, maxValue);
                resultElement.innerHTML = `Números gerados: ${numbersArray.join(', ')}`;
            });

            function generateRandomNumbers(quantity, minValue, maxValue) {
                const numbersArray = [];
                for (let i = 0; i < quantity; i++) {
                    const randomNumber = Math.floor(Math.random() * (maxValue - minValue + 1)) + minValue;
                    numbersArray.push(randomNumber);
                }
                return numbersArray;
            }
        });
    </script>
</body>
</html>
```

Neste exemplo, criamos um componente que contém três caixas de texto para a quantidade de números, valor mínimo e valor máximo, um botão de calcular e um elemento de resultado. Quando o botão "Calcular" é clicado, o código verifica se os campos foram preenchidos com valores numéricos, se a quantidade de números é menor que a soma de valor mínimo e valor máximo e, se as condições forem atendidas, gera um array de números aleatórios dentro do intervalo especificado e exibe os números gerados no elemento de resultado.

### 6.
Aqui está um exemplo de como criar o componente HTML com as funcionalidades que você descreveu:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Verificador de Triângulos</title>
</head>
<body>
    <div id="triangle-checker">
        <label for="side-a-input">Lado A:</label>
        <input type="number" id="side-a-input" />
        <label for="side-b-input">Lado B:</label>
        <input type="number" id="side-b-input" />
        <label for="side-c-input">Lado C:</label>
        <input type="number" id="side-c-input" />
        <button id="check-button">Verificar</button>
        <p id="result"></p>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function () {
            const sideAInput = document.getElementById('side-a-input');
            const sideBInput = document.getElementById('side-b-input');
            const sideCInput = document.getElementById('side-c-input');
            const checkButton = document.getElementById('check-button');
            const resultElement = document.getElementById('result');

            checkButton.addEventListener('click', function () {
                const sideA = parseFloat(sideAInput.value);
                const sideB = parseFloat(sideBInput.value);
                const sideC = parseFloat(sideCInput.value);

                if (isNaN(sideA) || isNaN(sideB) || isNaN(sideC)) {
                    resultElement.textContent = 'Preencha todos os campos com valores numéricos.';
                    return;
                }

                if (sideA + sideB > sideC && sideB + sideC > sideA && sideA + sideC > sideB) {
                    if (sideA === sideB && sideB === sideC) {
                        resultElement.textContent = 'Triângulo Equilátero';
                    } else if (sideA === sideB || sideB === sideC || sideA === sideC) {
                        resultElement.textContent = 'Triângulo Isósceles';
                    } else {
                        resultElement.textContent = 'Triângulo Escaleno';
                    }
                } else {
                    resultElement.textContent = 'Não é um triângulo.';
                }
            });
        });
    </script>
</body>
</html>
```

Neste exemplo, criamos um componente que possui três caixas de texto para os lados A, B e C de um triângulo, um botão de verificar e um elemento de resultado. Quando o botão "Verificar" é clicado, o código verifica se os campos foram preenchidos com valores numéricos e, se forem, realiza as verificações para determinar se os lados formam um triângulo e, em caso afirmativo, qual tipo de triângulo (equilátero, isósceles ou escaleno). O resultado é exibido no elemento de resultado.

### 7. 
Aqui está um exemplo simples de como criar um cenário de autenticação com HTML, CSS e JavaScript. Este exemplo utiliza o `localStorage` para armazenar os registros de usuários, mas em um ambiente de produção real, seria mais apropriado usar um backend para armazenamento seguro.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Autenticação</title>
</head>
<body>
    <div id="auth-container">
        <div id="login-form" class="form">
            <h2>Login</h2>
            <input type="text" id="login-username" placeholder="Usuário" />
            <input type="password" id="login-password" placeholder="Senha" />
            <button id="login-button">Login</button>
            <p id="login-error" class="error"></p>
        </div>
        <div id="signup-form" class="form">
            <h2>Criar Usuário</h2>
            <input type="text" id="signup-username" placeholder="Usuário" />
            <input type="password" id="signup-password" placeholder="Senha" />
            <button id="signup-button">Criar Usuário</button>
            <p id="signup-success" class="success"></p>
        </div>
        <div id="loggedin-content">
            <p>Logado</p>
            <button id="logout-button">Deslogar</button>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function () {
            const loginForm = document.getElementById('login-form');
            const loginUsername = document.getElementById('login-username');
            const loginPassword = document.getElementById('login-password');
            const loginButton = document.getElementById('login-button');
            const loginError = document.getElementById('login-error');

            const signupForm = document.getElementById('signup-form');
            const signupUsername = document.getElementById('signup-username');
            const signupPassword = document.getElementById('signup-password');
            const signupButton = document.getElementById('signup-button');
            const signupSuccess = document.getElementById('signup-success');

            const loggedinContent = document.getElementById('loggedin-content');
            const logoutButton = document.getElementById('logout-button');

            loginButton.addEventListener('click', function () {
                const storedUsers = JSON.parse(localStorage.getItem('users')) || [];
                const user = storedUsers.find(u => u.username === loginUsername.value && u.password === loginPassword.value);

                if (user) {
                    loginError.textContent = '';
                    loggedinContent.style.display = 'block';
                    loginForm.style.display = 'none';
                    signupForm.style.display = 'none';
                } else {
                    loginError.textContent = 'Usuário ou senha inválidos.';
                }
            });

            signupButton.addEventListener('click', function () {
                const storedUsers = JSON.parse(localStorage.getItem('users')) || [];
                const newUser = {
                    username: signupUsername.value,
                    password: signupPassword.value
                };

                storedUsers.push(newUser);
                localStorage.setItem('users', JSON.stringify(storedUsers));

                signupSuccess.textContent = 'Usuário criado com sucesso. Faça o login.';
                signupUsername.value = '';
                signupPassword.value = '';
            });

            logoutButton.addEventListener('click', function () {
                loggedinContent.style.display = 'none';
                loginForm.style.display = 'block';
                signupForm.style.display = 'block';
            });
        });
    </script>
</body>
</html>
```

Neste exemplo, criamos um cenário de autenticação com dois formulários: um para login e outro para criação de usuário. Os registros de usuários são armazenados no `localStorage` como um array de objetos contendo nome de usuário e senha. Quando o usuário faz login com sucesso, é exibido um conteúdo logado com a opção de deslogar. Quando o usuário cria um novo usuário, a mensagem de sucesso é exibida. Se você fechar a página e reabrir, os registros de usuários serão mantidos no `localStorage`. 

Note que este é apenas um exemplo básico e a segurança não foi tratada adequadamente. Em um ambiente real, é importante usar um backend seguro para autenticação e armazenamento de senhas.