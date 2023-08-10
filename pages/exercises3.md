[<img src="https://cdn-icons-png.flaticon.com/512/25/25694.png" alt="" width="50" align="center">](https://mervy.github.io/js-dom/)   [<img  src="https://icons.veryicon.com/png/o/business/monochrome-financial-and-business-icons/to-work-in-an-office-2.png"  alt=""  width="50" align="center">](https://mervy.github.io/js-dom/pages/exercises1) [<img  src="https://static.thenounproject.com/png/94973-200.png"  alt=""  width="50" align="center">](https://mervy.github.io/js-dom/pages/exercises2) [<img  src="https://icons.veryicon.com/png/o/business/monochrome-financial-and-business-icons/to-work-in-an-office-2.png"  alt=""  width="50" align="center">](https://mervy.github.io/js-dom/pages/exercises3)

## Exercícios

1. Tendo o calendário abaixo (só começo do código), faça os exercicios a seguir:
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
    <td>1</td>
    <td>2</td>
    <td>3</td>
    <td>4</td>
    <td>5</td>
  </tr>
a) colete do usuário duas datas (usando inputs de data) e altere a cor do “quadrado” dessa data no calendário dinamicamente. Por exemplo, se o usuário escolher a data 01/10/2022 – o quadrado da com o dia 1 (quarta-feira) deve mudar de cor.

b) colete do usuário duas datas (usando inputs de data), a seguir faça: 1) calcule quantos dias existem entre elas e exiba na tela (por exemplo, entre 05/04/2022 – 10/04/2022 → 5 dias); 2) mude a cor dos dias entre as datas selecionadas para a cor azul e as datas selecionadas para a cor laranja.

Solução [clique aqui](https://mervy.github.io/js-dom/pages/solutions3)

  
2. Crie um componente que possua uma caixa de texto (que só aceita números e tenha um rótulo (label)) e um botão “calcular”.
Use o número para calcular o fatorial dele e mostrá-lo na tela. Além disso, quando o botão é acionado o componente deve também mostrar tempo necessário para a execução. 

Solução [clique aqui](https://mervy.github.io/js-dom/pages/solutions3)

3. Crie um componente que possua um botão “criar relatório” e quando acionado o seu programa deverá imprimir um relatório de resultados da disciplina javascript para 20 alunos, no formato de tabela. Mas tem algumas regras adicionais:

As notas deverão ser números inteiros entre 0 e 100, criadas aleatoriamente; (dica: use a função math.radom(), dá um google!)
Cada aluno deve ser representado por um registro composto por numero e nota
Use uma função construtora chamada Aluno. Se você for bem ousado, implemente usando classes;
Armazene a nota do aluno como uma variável privada do tipo symbol, use getters e setters para recuperar a informação.
Os registros devem ser armazenados em um array;
A impressão do relatório deve ter:
Um título;
Os resultados mostrados linha a linha no formato “Aluno Nº ?? – Nota ?? [(A/RE)PROVADO]”; e
Um rodapé com estatística final no formato “APROVADOS: ??(??%)  |  REPROVADOS: YY (??%)”

Solução [clique aqui](https://mervy.github.io/js-dom/pages/solutions3)

4. Crie um componente que possui 3 caixas de texto (só aceitam números e possuem rótulos (label) com a quantidade de números, valor mínimo e valor máximo), 1 botão calcular, e ao clicar no botão de “calcular”:
- Um array deve ser criado com a quantidade de números aleatórios (informados pelo usuário) no intervalo informado.
- Os números devem estar entre valor mínimo e valor máximo (inclusives).
- Calcular quantidade de números deve ser menor que a soma de valor mínimo e valor máximo.

Solução [clique aqui](https://mervy.github.io/js-dom/pages/solutions3)

5. Exercício 05 – Crie um componente que possui 3 caixas de texto que só aceitam números e tenha os rótulos (label): lado A, lado B e lado C e 1 botão “calcular”. Quando acionado o botão deve dizer se um triângulo é formado por esses 3 lados. Caso afirmativo, informe se o triângulo equilátero, isósceles ou escaleno. (esse é bem simples né =D ) 

Solução [clique aqui](https://mervy.github.io/js-dom/pages/solutions3)

6. Agora vamos criar um último componente mais avançado. Nesse, você precisa criar campos para usuário e login em aplicação(sign up/ sign in).
No 1º cenário, antes de estar logado, o visitante se depara com o formulário de login ou de criação de usuário. Se for feito o login com sucesso, o componente deve levar ao cenário 2, se falhar ele deve alertar o usuário e voltar ao início do cenário 1. Se o usuário optar por criar um usuário, o componente deve criar o registro de um novo usuário e voltar para início do cenário 1.
No cenário 2, após logado, mostrar apenas um texto de logado no componente e um botão (ou link) para deslogar, retornando ao início do cenário 1. Deve ser possível criar múltiplos usuários e, se fechada, a página não pode perder os registros de usuários  armazenados.

Solução [clique aqui](https://mervy.github.io/js-dom/pages/solutions3)

