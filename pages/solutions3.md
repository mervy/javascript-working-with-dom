[<img src="https://cdn-icons-png.flaticon.com/512/25/25694.png" alt="" width="50" align="center">](https://mervy.github.io/js-dom/)   [<img  src="https://icons.veryicon.com/png/o/business/monochrome-financial-and-business-icons/to-work-in-an-office-2.png"  alt=""  width="50" align="center">](https://mervy.github.io/pages/exercises1) [<img  src="https://static.thenounproject.com/png/94973-200.png"  alt=""  width="50" align="center">](https://mervy.github.io/pages/exercises2) [<img  src="https://icons.veryicon.com/png/o/business/monochrome-financial-and-business-icons/to-work-in-an-office-2.png"  alt=""  width="50" align="center">](https://mervy.github.io/pages/exercises3)

1. 
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .calendar {
      border-collapse: collapse;
    }

    .calendar th, .calendar td {
      border: 1px solid black;
      width: 30px;
      height: 30px;
      text-align: center;
    }

    .calendar td.selected {
      background-color: blue;
      color: white;
    }

    .calendar td.highlighted {
      background-color: orange;
      color: white;
    }

    .hidden {
      display: none;
    }
  </style>
</head>
<body>

<table class="calendar">
<thead>
  <tr>
    <th>Dom</th>
    <th>Seg</th>
    <th>Ter</th>
    <th>Qua</th>
    <th>Qui</th>
    <th>Sex</th>
    <th>Sab</th>
    <th>Dom</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td id="day1">1</td>
    <td>2</td>
    <td>3</td>
    <td>4</td>
    <td>5</td>
  </tr>
  <!-- Continue the rest of the table here -->
</tbody>
</table>

<p>a) colete do usuário duas datas (usando inputs de data) e altere a cor do "quadrado" dessa data no calendário dinamicamente. Por exemplo, se o usuário escolher a data 01/10/2022 – o quadrado da com o dia 1 (quarta-feira) deve mudar de cor.</p>
<button id="exercise1">Mostrar Resposta</button>
<p id="answer1" class="hidden">
<script>
  document.getElementById("exercise1").addEventListener("click", function() {
    // Código JavaScript Puro para o exercício a)
    var date1 = new Date("2022-10-01");
    var day1 = document.getElementById("day1");

    day1.style.backgroundColor = "green"; // Altere a cor conforme necessário
    day1.style.color = "white";

    // Fim do código
    document.getElementById("answer1").classList.remove("hidden");
  });
</script>
</p>

<p>b) colete do usuário duas datas (usando inputs de data), a seguir faça: 
1) calcule quantos dias existem entre elas e exiba na tela (por exemplo, entre 05/04/2022 – 10/04/2022 → 5 dias); 
2) mude a cor dos dias entre as datas selecionadas para a cor azul e as datas selecionadas para a cor laranja.</p>
<button id="exercise2">Mostrar Resposta</button>
<p id="answer2" class="hidden">
<script>
  document.getElementById("exercise2").addEventListener("click", function() {
    // Código JavaScript Puro para o exercício b)
    var startDate = new Date("2022-04-05");
    var endDate = new Date("2022-04-10");

    var daysDiff = Math.floor((endDate - startDate) / (1000 * 60 * 60 * 24));
    alert("Dias entre as datas: " + daysDiff);

    var calendarCells = document.getElementsByTagName("td");

    for (var i = 0; i < calendarCells.length; i++) {
      var cellDate = new Date("2022-04-" + calendarCells[i].textContent);
      
      if (cellDate > startDate && cellDate < endDate) {
        calendarCells[i].classList.add("highlighted");
      }
    }

    // Fim do código
    document.getElementById("answer2").classList.remove("hidden");
  });
</script>
</p>

</body>
</html>
```

Este é um exemplo de código HTML com JavaScript puro para resolver os exercícios propostos. Você pode copiar e colar esse código em um arquivo HTML e abri-lo em um navegador para ver o calendário e testar as funcionalidades. Certifique-se de que o JavaScript esteja habilitado no seu navegador para que os scripts funcionem corretamente.

2. Aqui está um exemplo de como você pode criar um componente usando HTML, CSS e JavaScript puro para calcular o fatorial de um número e exibir o tempo necessário para a execução:
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      font-family: Arial, sans-serif;
    }

    .container {
      text-align: center;
      margin-top: 50px;
    }

    label {
      font-weight: bold;
    }
  </style>
</head>
<body>

<div class="container">
  <label for="numberInput">Digite um número:</label>
  <input type="text" id="numberInput" pattern="[0-9]*">
  <button id="calculateButton">Calcular</button>
  <p id="result"></p>
  <p id="executionTime"></p>
</div>

<script>
  document.getElementById("calculateButton").addEventListener("click", function() {
    var numberInput = document.getElementById("numberInput");
    var resultDisplay = document.getElementById("result");
    var executionTimeDisplay = document.getElementById("executionTime");

    var inputNumber = parseInt(numberInput.value);

    if (isNaN(inputNumber)) {
      resultDisplay.textContent = "Por favor, insira um número válido.";
      executionTimeDisplay.textContent = "";
      return;
    }

    var startTime = performance.now();
    var factorial = calculateFactorial(inputNumber);
    var endTime = performance.now();
    var executionTime = endTime - startTime;

    resultDisplay.textContent = "Fatorial de " + inputNumber + ": " + factorial;
    executionTimeDisplay.textContent = "Tempo de execução: " + executionTime.toFixed(2) + " milissegundos";
  });

  function calculateFactorial(number) {
    if (number === 0 || number === 1) {
      return 1;
    } else {
      return number * calculateFactorial(number - 1);
    }
  }
</script>

</body>
</html>
```
Este exemplo cria um componente com uma caixa de texto para entrada do número, um botão "Calcular", um espaço para exibir o resultado do cálculo do fatorial e outro espaço para exibir o tempo de execução. Certifique-se de copiar o código acima para um arquivo HTML e abri-lo em um navegador para ver e interagir com o componente.

3. Aqui está um exemplo de um componente que atende às regras adicionais especificadas para criar um relatório de resultados da disciplina JavaScript para 20 alunos:

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      font-family: Arial, sans-serif;
    }

    .container {
      text-align: center;
      margin-top: 50px;
    }

    table {
      border-collapse: collapse;
      margin-top: 20px;
      margin-left: auto;
      margin-right: auto;
    }

    table, th, td {
      border: 1px solid black;
    }

    th, td {
      padding: 8px;
    }

    th {
      background-color: #f2f2f2;
    }
  </style>
</head>
<body>

<div class="container">
  <button id="createReportButton">Criar Relatório</button>
  <div id="reportTableContainer"></div>
</div>

<script>
  function Aluno(numero, nota) {
    let _nota = Symbol('nota');
    this.numero = numero;

    this.setNota = function(nota) {
      if (nota >= 0 && nota <= 100) {
        this[_nota] = nota;
      } else {
        throw new Error('A nota deve estar entre 0 e 100.');
      }
    };

    this.getNota = function() {
      return this[_nota];
    };

    this.setNota(nota);
  }

  document.getElementById("createReportButton").addEventListener("click", function() {
    var reportTableContainer = document.getElementById("reportTableContainer");

    var alunos = [];
    for (var i = 1; i <= 20; i++) {
      var randomGrade = Math.floor(Math.random() * 101); // Random grade between 0 and 100
      var aluno = new Aluno(i, randomGrade);
      alunos.push(aluno);
    }

    var reportTable = document.createElement("table");
    var headerRow = reportTable.insertRow(0);

    var headers = ["Aluno", "Nota", "Situação"];
    for (var i = 0; i < headers.length; i++) {
      var headerCell = document.createElement("th");
      headerCell.textContent = headers[i];
      headerRow.appendChild(headerCell);
    }

    var aprovados = 0;
    var reprovados = 0;

    for (var i = 0; i < alunos.length; i++) {
      var row = reportTable.insertRow(i + 1);
      var studentCell = row.insertCell(0);
      var gradeCell = row.insertCell(1);
      var situationCell = row.insertCell(2);

      studentCell.textContent = "Aluno " + alunos[i].numero;
      gradeCell.textContent = alunos[i].getNota();

      if (alunos[i].getNota() >= 60) {
        situationCell.textContent = "APROVADO";
        aprovados++;
      } else {
        situationCell.textContent = "REPROVADO";
        reprovados++;
      }
    }

    reportTableContainer.innerHTML = "";
    reportTableContainer.appendChild(reportTable);

    var totalAlunos = alunos.length;
    var percentAprovados = ((aprovados / totalAlunos) * 100).toFixed(2);
    var percentReprovados = ((reprovados / totalAlunos) * 100).toFixed(2);

    var statistics = document.createElement("p");
    statistics.textContent = "APROVADOS: " + aprovados + " (" + percentAprovados + "%)  |  REPROVADOS: " + reprovados + " (" + percentReprovados + "%)";
    reportTableContainer.appendChild(statistics);
  });
</script>

</body>
</html>
```

Neste exemplo, implementei a classe `Aluno` usando uma função construtora e o conceito de variáveis privadas usando símbolos. O código cria um relatório de resultados da disciplina JavaScript para 20 alunos, seguindo as regras adicionais especificadas. Certifique-se de copiar o código acima para um arquivo HTML e abri-lo em um navegador para ver e interagir com o componente.

4. Aqui está um exemplo de um componente que atende às suas especificações, com 3 caixas de texto para entrada de informações e um botão para calcular e gerar um array de números aleatórios dentro do intervalo especificado:

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      font-family: Arial, sans-serif;
    }

    .container {
      text-align: center;
      margin-top: 50px;
    }

    label {
      font-weight: bold;
    }
  </style>
</head>
<body>

<div class="container">
  <label for="quantityInput">Quantidade de Números:</label>
  <input type="text" id="quantityInput" pattern="[0-9]*">
  <br>
  <label for="minValueInput">Valor Mínimo:</label>
  <input type="text" id="minValueInput" pattern="[0-9]*">
  <br>
  <label for="maxValueInput">Valor Máximo:</label>
  <input type="text" id="maxValueInput" pattern="[0-9]*">
  <br>
  <button id="calculateButton">Calcular</button>
  <p id="result"></p>
</div>

<script>
  document.getElementById("calculateButton").addEventListener("click", function() {
    var quantityInput = document.getElementById("quantityInput");
    var minValueInput = document.getElementById("minValueInput");
    var maxValueInput = document.getElementById("maxValueInput");
    var resultDisplay = document.getElementById("result");

    var quantity = parseInt(quantityInput.value);
    var minValue = parseInt(minValueInput.value);
    var maxValue = parseInt(maxValueInput.value);

    if (isNaN(quantity) || isNaN(minValue) || isNaN(maxValue)) {
      resultDisplay.textContent = "Por favor, preencha todos os campos corretamente.";
      return;
    }

    if (quantity >= (minValue + maxValue)) {
      resultDisplay.textContent = "A quantidade de números deve ser menor que a soma do valor mínimo e valor máximo.";
      return;
    }

    var randomNumbers = generateRandomNumbers(quantity, minValue, maxValue);
    resultDisplay.textContent = "Números Aleatórios: " + randomNumbers.join(", ");
  });

  function generateRandomNumbers(quantity, minValue, maxValue) {
    var randomNumbers = [];
    for (var i = 0; i < quantity; i++) {
      var randomNumber = Math.floor(Math.random() * (maxValue - minValue + 1)) + minValue;
      randomNumbers.push(randomNumber);
    }
    return randomNumbers;
  }
</script>

</body>
</html>
```

Este exemplo cria um componente com caixas de texto para entrada da quantidade de números desejados, valor mínimo e valor máximo, e um botão "Calcular". Quando o botão é clicado, o programa gera um array de números aleatórios dentro do intervalo especificado, desde que a quantidade seja menor que a soma do valor mínimo e valor máximo. Certifique-se de copiar o código acima para um arquivo HTML e abri-lo em um navegador para ver e interagir com o componente.

5. Claro, aqui está um exemplo de um componente que verifica se um triângulo é formado pelos três lados fornecidos pelos usuários e, em caso afirmativo, determina se o triângulo é equilátero, isósceles ou escaleno:

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      font-family: Arial, sans-serif;
    }

    .container {
      text-align: center;
      margin-top: 50px;
    }

    label {
      font-weight: bold;
    }
  </style>
</head>
<body>

<div class="container">
  <label for="sideAInput">Lado A:</label>
  <input type="text" id="sideAInput" pattern="[0-9]*">
  <br>
  <label for="sideBInput">Lado B:</label>
  <input type="text" id="sideBInput" pattern="[0-9]*">
  <br>
  <label for="sideCInput">Lado C:</label>
  <input type="text" id="sideCInput" pattern="[0-9]*">
  <br>
  <button id="calculateButton">Calcular</button>
  <p id="result"></p>
</div>

<script>
  document.getElementById("calculateButton").addEventListener("click", function() {
    var sideAInput = document.getElementById("sideAInput");
    var sideBInput = document.getElementById("sideBInput");
    var sideCInput = document.getElementById("sideCInput");
    var resultDisplay = document.getElementById("result");

    var sideA = parseFloat(sideAInput.value);
    var sideB = parseFloat(sideBInput.value);
    var sideC = parseFloat(sideCInput.value);

    if (isNaN(sideA) || isNaN(sideB) || isNaN(sideC)) {
      resultDisplay.textContent = "Por favor, preencha todos os campos corretamente.";
      return;
    }

    if (sideA + sideB > sideC && sideB + sideC > sideA && sideA + sideC > sideB) {
      if (sideA === sideB && sideB === sideC) {
        resultDisplay.textContent = "Triângulo Equilátero";
      } else if (sideA === sideB || sideA === sideC || sideB === sideC) {
        resultDisplay.textContent = "Triângulo Isósceles";
      } else {
        resultDisplay.textContent = "Triângulo Escaleno";
      }
    } else {
      resultDisplay.textContent = "Não é um triângulo válido.";
    }
  });
</script>

</body>
</html>
```

Este exemplo cria um componente com caixas de texto para entrada dos lados A, B e C de um triângulo e um botão "Calcular". Quando o botão é clicado, o programa verifica se os lados formam um triângulo e determina se é equilátero, isósceles ou escaleno. Certifique-se de copiar o código acima para um arquivo HTML e abri-lo em um navegador para ver e interagir com o componente.

6. Criar um sistema de autenticação e gerenciamento de usuários é um pouco mais complexo, pois envolve o uso de armazenamento local (por exemplo, cookies ou armazenamento local) para manter o estado de login. Aqui está um exemplo simplificado usando JavaScript puro para o componente que você descreveu:

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      font-family: Arial, sans-serif;
    }

    .container {
      text-align: center;
      margin-top: 50px;
    }

    label {
      font-weight: bold;
    }
  </style>
</head>
<body>

<div class="container" id="loginContainer">
  <h2>Login / Sign Up</h2>
  <label for="usernameInput">Usuário:</label>
  <input type="text" id="usernameInput">
  <br>
  <label for="passwordInput">Senha:</label>
  <input type="password" id="passwordInput">
  <br>
  <button id="loginButton">Login</button>
  <button id="signupButton">Sign Up</button>
</div>

<div class="container" id="loggedinContainer" style="display: none;">
  <h2>Logado</h2>
  <p>Você está logado no sistema.</p>
  <button id="logoutButton">Logout</button>
</div>

<script>
  var users = [];

  function User(username, password) {
    this.username = username;
    this.password = password;
  }

  document.getElementById("loginButton").addEventListener("click", function() {
    var usernameInput = document.getElementById("usernameInput").value;
    var passwordInput = document.getElementById("passwordInput").value;

    var user = users.find(function(user) {
      return user.username === usernameInput && user.password === passwordInput;
    });

    if (user) {
      document.getElementById("loginContainer").style.display = "none";
      document.getElementById("loggedinContainer").style.display = "block";
    } else {
      alert("Usuário ou senha inválidos.");
    }
  });

  document.getElementById("signupButton").addEventListener("click", function() {
    var usernameInput = document.getElementById("usernameInput").value;
    var passwordInput = document.getElementById("passwordInput").value;

    var existingUser = users.find(function(user) {
      return user.username === usernameInput;
    });

    if (existingUser) {
      alert("Usuário já existe.");
    } else {
      var newUser = new User(usernameInput, passwordInput);
      users.push(newUser);
      alert("Usuário registrado com sucesso.");
    }
  });

  document.getElementById("logoutButton").addEventListener("click", function() {
    document.getElementById("loggedinContainer").style.display = "none";
    document.getElementById("loginContainer").style.display = "block";
  });
</script>

</body>
</html>
```

Este exemplo cria um componente de autenticação simples com dois cenários. O primeiro cenário exibe o formulário de login ou registro. Se o login for bem-sucedido, o componente muda para o segundo cenário, onde mostra que o usuário está logado. Quando o usuário faz logout, ele é redirecionado de volta ao primeiro cenário.

Lembrando que este é um exemplo simplificado e não deve ser usado em produção. Em um ambiente real, a autenticação deve ser implementada de maneira mais segura, com técnicas como hashing de senhas e autenticação do lado do servidor. Além disso, o armazenamento local pode ser substituído por um banco de dados ou outra forma de armazenamento persistente.