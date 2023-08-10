User
Agora mostre a resposta, o código de cada um
ChatGPT
Claro! Aqui estão as respostas para cada exercício:

**Manipulação de Elementos e Seletores:**

1. `const primeiroParagrafo = document.querySelector('.conteudo p');`
2. `const listaItens = document.querySelectorAll('ul li');`
3. `const tituloElemento = document.getElementById('titulo'); tituloElemento.textContent = 'Novo Título';`
4. ```
   const links = document.querySelectorAll('a');
   links.forEach(link => link.classList.add('link-destaque'));
   ```
5. ```
   const elementosDestaque = document.querySelectorAll('.destaque');
   elementosDestaque.forEach(elemento => elemento.classList.remove('destaque'));
   ```

**Manipulação de Conteúdo:**

6. ```
   const novoParagrafo = document.createElement('p');
   novoParagrafo.textContent = 'Novo parágrafo criado.';
   const conteudoElemento = document.querySelector('#conteudo');
   conteudoElemento.appendChild(novoParagrafo);
   ```
7. `const mensagemSpan = document.getElementById('mensagem'); mensagemSpan.textContent = 'Texto Atualizado';`
8. ```
   const divModelo = document.querySelector('.modelo');
   const novaDiv = divModelo.cloneNode(true);
   divModelo.parentElement.insertBefore(novaDiv, divModelo);
   ```
9. `const listaOrdenada = document.querySelector('ol'); listaOrdenada.removeChild(listaOrdenada.lastElementChild);`
10. ```
    const novoH2 = document.createElement('h2');
    novoH2.textContent = 'Novo Título';
    const paragrafo = document.querySelector('p');
    paragrafo.parentElement.insertBefore(novoH2, paragrafo);
    ```

**Manipulação de Atributos e Propriedades:**

11. `const imagem = document.querySelector('#foto'); const src = imagem.getAttribute('src');`
12. `const linkBotao = document.querySelector('.botao'); linkBotao.setAttribute('href', 'pagina.html');`
13. `const inputSenha = document.querySelector('#senha'); const possuiRequired = inputSenha.hasAttribute('required');`
14. `const spanDescricao = document.querySelector('#descricao'); spanDescricao.textContent = 'Novo Texto';`
15. `const checkboxAceito = document.querySelector('#aceito'); const estaMarcado = checkboxAceito.checked;`

**Manipulação de Estilos e Classes:**

16. `const divBloco = document.querySelector('.bloco'); divBloco.classList.add('destaque');`
17. `const botao = document.querySelector('#botao'); botao.classList.remove('ativo');`
18. ```
    const lis = document.querySelectorAll('li');
    lis.forEach(li => {
      li.addEventListener('click', () => {
        li.classList.toggle('selecionado');
      });
    });
    ```
19. ```
    const paragrafo = document.querySelector('p');
    paragrafo.style.backgroundColor = 'lightgray';
    ```
20. `const divElemento = document.querySelector('#elemento'); const temClasseVisivel = divElemento.classList.contains('visivel');`

**Event Handling:**

21. `const botaoEnviar = document.querySelector('#btnEnviar'); botaoEnviar.addEventListener('click', () => { /* código aqui */ });`
22. `const inputEntrada = document.querySelector('#entrada'); inputEntrada.removeEventListener('evento', () => { /* código aqui */ });`
23. ```
    const link = document.querySelector('a');
    link.addEventListener('click', (event) => {
      event.preventDefault();
    });
    ```
24. ```
    const spanElemento = document.querySelector('span');
    spanElemento.addEventListener('click', (event) => {
      event.stopPropagation();
    });
    ```
25. ```
    document.addEventListener('keydown', (event) => {
      console.log('Tipo de Evento:', event.type);
      console.log('Tecla Pressionada:', event.key);
    });
    ```

**Traversal:**

26. `const elementoFilho = document.querySelector('#filho'); const elementoPai = elementoFilho.parentNode;`
27. `const ulElemento = document.querySelector('ul'); const filhosUl = ulElemento.childNodes;`
28. `const divContainer = document.querySelector('.container'); const primeiroFilhoDiv = divContainer.firstChild;`
29. `const liElemento = document.querySelector('.item'); const proximoIrmaoLi = liElemento.nextSibling;`
30. `const h3Elemento = document.querySelector('#titulo'); const elementoPaiH3 = h3Elemento.parentElement;`

Continuarei com as respostas para os próximos exercícios em uma nova resposta devido a limitações de espaço.
User
continue
ChatGPT
**Manipulação de Cookies e Documentos:**

31. `document.cookie = 'usuario=joao';`
32. `const preferenciasCookie = document.cookie;`
33. `document.cookie = 'carrinho=; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/;';`
34. `document.title = 'Nova Página';`
35. `window.alert('Bem-vindo!');`

**Performance Optimization:**

36. ```
    function animar() {
      const elemento = document.querySelector('.elemento');
      let posicao = 0;

      function mover() {
        posicao += 5;
        elemento.style.transform = `translateX(${posicao}px)`;
        if (posicao < 200) {
          requestAnimationFrame(mover);
        }
      }

      requestAnimationFrame(mover);
    }
    animar();
    ```
37. `window.performance.mark('inicio'); /* Código a ser medido */ window.performance.mark('fim'); window.performance.measure('minhaMedida', 'inicio', 'fim');`
38. ```
    const elementoImg = document.querySelector('img');
    const rect = elementoImg.getBoundingClientRect();
    console.log('Dimensões da Imagem:', rect.width, 'x', rect.height);
    ```
39. `const larguraCorpo = document.body.offsetWidth; console.log('Largura do Corpo:', larguraCorpo);`
40. ```
    const elementoH1 = document.querySelector('h1');
    const posicaoTopo = elementoH1.offsetTop;
    console.log('Posição do Elemento:', posicaoTopo);
    ```

Esses são os códigos para cada exercício. Lembre-se de que você pode experimentar esses códigos em um ambiente de desenvolvimento para entender melhor como eles funcionam e como as diferentes manipulações do DOM acontecem. Se você tiver mais perguntas ou precisar de mais exemplos, não hesite em perguntar!