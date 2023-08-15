<img src="javascript-logo.png" alt="JS logo" style="width:100px;"/> 
| [Home](https://mervy.github.io/javascript-working-with-dom) 
| [Exercises 01](https://mervy.github.io/javascript-working-with-dom/pages/exercises1) 
| [Exercises 02](https://mervy.github.io/javascript-working-with-dom/pages/exercises2) 
| [Exercises 03](https://mervy.github.io/javascript-working-with-dom/pages/exercises3) 

Claro, aqui estão as respostas para os exercícios mais desafiadores:

**Manipulação de Elementos e Seletores:**

1. ```javascript
   const paragrafosDentroDiv = document.querySelectorAll('.container p');
   paragrafosDentroDiv.forEach(paragrafo => {
     paragrafo.classList.add('destaque');
   });
   ```
2. ```javascript
   const tabela = document.createElement('table');
   for (let i = 0; i < 3; i++) {
     const linha = tabela.insertRow();
     for (let j = 0; j < 4; j++) {
       const celula = linha.insertCell();
       celula.textContent = `Linha ${i + 1}, Coluna ${j + 1}`;
     }
   }
   const containerTabela = document.querySelector('#tabela-container');
   containerTabela.appendChild(tabela);
   ```
3. ```javascript
   const inputsTexto = document.querySelectorAll('input[type="text"]');
   inputsTexto.forEach(input => {
     input.classList.add('campo-texto');
   });
   ```
4. ```javascript
   const botoes = document.querySelectorAll('.botoes button');
   botoes.forEach(botao => {
     botao.textContent = 'Clique Aqui';
   });
   ```
5. ```javascript
   const botaoDinamico = document.createElement('button');
   botaoDinamico.textContent = 'Botão Dinâmico';
   const containerBotoes = document.querySelector('.botoes');
   containerBotoes.appendChild(botaoDinamico);
   ```

**Manipulação de Conteúdo:**

6. ```javascript
   const listaUl = document.createElement('ul');
   for (let i = 1; i <= 5; i++) {
     const item = document.createElement('li');
     item.textContent = `Item ${i}`;
     listaUl.appendChild(item);
   }
   const containerLista = document.querySelector('.lista-container');
   containerLista.appendChild(listaUl);
   ```
7. ```javascript
   const paragrafos = document.querySelectorAll('.conteudo p');
   paragrafos.forEach(paragrafo => {
     paragrafo.textContent = 'Novo Parágrafo';
   });
   ```
8. ```javascript
   const tabelaClonada = document.querySelector('#tabela').cloneNode(true);
   const outraTabela = document.querySelector('#outra-tabela');
   outraTabela.parentElement.insertBefore(tabelaClonada, outraTabela);
   ```
9. ```javascript
   const selectOpcoes = document.querySelector('#opcoes');
   while (selectOpcoes.firstChild) {
     selectOpcoes.removeChild(selectOpcoes.firstChild);
   }
   ```
10. ```javascript
    const btnRemoverLi = document.createElement('button');
    btnRemoverLi.textContent = 'Remover Último';
    const listaNaoOrdenada = document.querySelector('ul');
    btnRemoverLi.addEventListener('click', () => {
      const ultimoLi = listaNaoOrdenada.lastElementChild;
      if (ultimoLi) {
        listaNaoOrdenada.removeChild(ultimoLi);
      }
    });
    const containerBotao = document.querySelector('.botoes');
    containerBotao.appendChild(btnRemoverLi);
    ```

**Manipulação de Atributos e Propriedades:**

11. ```javascript
    const novaImagem = document.createElement('img');
    novaImagem.setAttribute('src', 'imagem.jpg');
    novaImagem.setAttribute('alt', 'Imagem');
    const containerImagem = document.querySelector('.imagem-container');
    containerImagem.appendChild(novaImagem);
    ```
12. ```javascript
    const divConteudo = document.querySelector('#conteudo');
    divConteudo.innerHTML = '<p>Novo Conteúdo</p>';
    ```
13. ```javascript
    const inputEmail = document.querySelector('#email');
    const tipoEmail = inputEmail.getAttribute('type');
    ```
14. ```javascript
    const listaNumerada = document.createElement('ol');
    for (let i = 1; i <= 5; i++) {
      const item = document.createElement('li');
      item.textContent = `Item ${i}`;
      listaNumerada.appendChild(item);
    }
    const containerLista = document.querySelector('.lista-container');
    containerLista.appendChild(listaNumerada);
    ```
15. ```javascript
    const spanContador = document.querySelector('#contador');
    let contador = 0;
    setInterval(() => {
      contador++;
      spanContador.innerText = contador.toString();
    }, 1000);
    ```

**Manipulação de Estilos e Classes:**

16. Crie uma animação CSS que faça um elemento `div` com a classe "animado" girar 360 graus continuamente.
```css
.animado {
  animation: girar 4s linear infinite;
}

@keyframes girar {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
```

17. Adicione uma classe "ativo" a um elemento `tab` ao clicar nele e remova essa classe dos outros elementos `tab` no mesmo container.
```javascript
const tabs = document.querySelectorAll('.tab');
tabs.forEach(tab => {
  tab.addEventListener('click', () => {
    tabs.forEach(t => t.classList.remove('ativo'));
    tab.classList.add('ativo');
  });
});
```

18. Altere o estilo de um elemento `button` com o ID "botao" para ter uma cor de fundo gradiente.
```javascript
const botao = document.querySelector('#botao');
botao.style.background = 'linear-gradient(to bottom, #ff9900, #ffcc00)';
```

19. Crie uma função que aceite um elemento e uma cor como argumentos e aplique essa cor como cor de fundo no elemento.
```javascript
function aplicarCorDeFundo(elemento, cor) {
  elemento.style.backgroundColor = cor;
}

const divElemento = document.querySelector('.elemento');
aplicarCorDeFundo(divElemento, 'blue');
```

20. Altere o tamanho da fonte de todos os elementos `h3` dentro de um elemento `div` com a classe "conteudo" para o dobro do tamanho atual.
```javascript
const divConteudo = document.querySelector('.conteudo');
const elementosH3 = divConteudo.querySelectorAll('h3');
elementosH3.forEach(h3 => {
  const tamanhoFonteAtual = parseFloat(getComputedStyle(h3).fontSize);
  h3.style.fontSize = `${tamanhoFonteAtual * 2}px`;
});
```

Continuarei com as respostas para os próximos exercícios em uma nova resposta devido a limitações de espaço.
User
continue
ChatGPT
**Event Handling:**

21. Crie um elemento `div` e adicione um ouvinte de evento que mude sua cor de fundo ao passar o mouse sobre ele.
```javascript
const divColorida = document.createElement('div');
divColorida.style.width = '100px';
divColorida.style.height = '100px';
divColorida.style.backgroundColor = 'red';

divColorida.addEventListener('mouseover', () => {
  divColorida.style.backgroundColor = 'blue';
});

divColorida.addEventListener('mouseout', () => {
  divColorida.style.backgroundColor = 'red';
});

const container = document.querySelector('.container');
container.appendChild(divColorida);
```

22. Crie um botão que, ao ser clicado, adicione um ouvinte de evento de teclado que exiba no console a tecla pressionada.
```javascript
const botaoTeclado = document.createElement('button');
botaoTeclado.textContent = 'Clique para Ouvir Teclado';

botaoTeclado.addEventListener('click', () => {
  window.addEventListener('keydown', event => {
    console.log('Tecla Pressionada:', event.key);
  });
});

const containerBotoes = document.querySelector('.botoes');
containerBotoes.appendChild(botaoTeclado);
```

23. Crie um formulário com campos de entrada e um botão de envio. Ao pressionar Enter em um campo de entrada, o formulário deve ser enviado.
```html
<form id="meu-form">
  <input type="text" name="nome" placeholder="Nome">
  <input type="email" name="email" placeholder="E-mail">
  <input type="submit" value="Enviar">
</form>
```
```javascript
const meuForm = document.querySelector('#meu-form');
meuForm.addEventListener('submit', event => {
  event.preventDefault();
  console.log('Formulário Enviado!');
});
```

24. Crie uma função que detecte um duplo clique em um elemento `div` e altere seu conteúdo para "Duplo Clique Detectado".
```javascript
const divDuploClique = document.createElement('div');
divDuploClique.textContent = 'Clique Duas Vezes';

divDuploClique.addEventListener('dblclick', () => {
  divDuploClique.textContent = 'Duplo Clique Detectado';
});

const container = document.querySelector('.container');
container.appendChild(divDuploClique);
```

25. Crie um elemento `div` e adicione um ouvinte de evento que alterne a cor de fundo entre vermelho e verde a cada clique.
```javascript
const divColorToggle = document.createElement('div');
divColorToggle.style.width = '100px';
divColorToggle.style.height = '100px';
divColorToggle.style.backgroundColor = 'red';

divColorToggle.addEventListener('click', () => {
  if (divColorToggle.style.backgroundColor === 'red') {
    divColorToggle.style.backgroundColor = 'green';
  } else {
    divColorToggle.style.backgroundColor = 'red';
  }
});

const container = document.querySelector('.container');
container.appendChild(divColorToggle);
```

Essas são as respostas para os exercícios mais desafiadores. Lembre-se de experimentar e adaptar esses códigos para aprimorar suas habilidades de desenvolvimento web. Se você tiver alguma dúvida ou precisar de mais orientações, estou aqui para ajudar!
