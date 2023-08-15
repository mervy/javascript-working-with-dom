# Javascript - Introdução ao DOM

Introdução ao DOM

**Principais Técnicas de Manipulação do DOM:**

1. Seleção de Elementos:
   - `document.querySelector(selector)` – Seleciona o primeiro elemento que corresponde ao seletor CSS.
   - `document.querySelectorAll(selector)` – Seleciona todos os elementos que correspondem ao seletor CSS.
   - `document.getElementById(id)` – Seleciona o elemento com o ID especificado.
   - `document.getElementsByClassName(className)` – Seleciona todos os elementos com a classe especificada.
   - `document.getElementsByTagName(tagName)` – Seleciona todos os elementos com a tag especificada.

2. Criação e Modificação de Elementos:
   - `document.createElement(tagName)` – Cria um novo elemento com a tag especificada.
   - `element.appendChild(child)` – Adiciona um elemento filho ao final do elemento pai.
   - `element.insertBefore(newElement, referenceElement)` – Insere um novo elemento antes do elemento de referência.
   - `element.setAttribute(name, value)` – Define o valor do atributo especificado para um elemento.
   - `element.removeAttribute(name)` – Remove o atributo especificado de um elemento.
   - `element.innerHTML` – Define ou obtém o conteúdo HTML de um elemento.
   - `element.textContent` – Define ou obtém o conteúdo de texto de um elemento.
   - `element.insertAdjacentHTML(position, htmlString)` – Insere HTML na posição especificada em relação ao elemento.
   - `element.insertAdjacentText(position, text)` – Insere texto na posição especificada em relação ao elemento.

3. Manipulação de Estilos e Classes:
   - `element.style.property = value` – Define uma propriedade CSS para um elemento.
   - `element.classList.add(className)` – Adiciona uma classe a um elemento.
   - `element.classList.remove(className)` – Remove uma classe de um elemento.
   - `element.classList.toggle(className)` – Alterna uma classe em um elemento.
   - `element.classList.contains(className)` – Verifica se um elemento possui uma classe.
   - `window.getComputedStyle(element)` – Obtém o estilo computado de um elemento.

4. Event Handling:
   - `element.addEventListener(event, function)` – Adiciona um ouvinte de evento a um elemento.
   - `element.removeEventListener(event, function)` – Remove um ouvinte de evento de um elemento.
   - `event.preventDefault()` – Previne a ação padrão de um evento.
   - `event.stopPropagation()` – Interrompe a propagação de um evento aos elementos pai.
   - `event.target` – Retorna o elemento que acionou o evento.
   - `event.currentTarget` – Retorna o elemento ao qual o ouvinte de evento está anexado.
   - `event.type` – Retorna o tipo do evento.
   - `event.key` – Retorna a tecla pressionada (para eventos de teclado).
   - `event.keyCode` – Retorna o valor Unicode da tecla pressionada (para eventos de teclado).

5. Traversal:
   - `element.parentNode` – Retorna o nó pai de um elemento.
   - `element.childNodes` – Retorna uma coleção de todos os nós filhos de um elemento.
   - `element.firstChild` – Retorna o primeiro nó filho de um elemento.
   - `element.lastChild` – Retorna o último nó filho de um elemento.
   - `element.previousSibling` – Retorna o nó irmão anterior de um elemento.
   - `element.nextSibling` – Retorna o próximo nó irmão de um elemento.
   - `element.parentElement` – Retorna o elemento pai de um elemento (excluindo nós de texto e comentários).
   - `element.children` – Retorna uma coleção de todos os elementos filhos de um elemento (excluindo nós de texto e comentários).

6. Atributos e Propriedades:
   - `element.getAttribute(name)` – Retorna o valor do atributo especificado de um elemento.
   - `element.setAttribute(name, value)` – Define o valor do atributo especificado para um elemento.
   - `element.removeAttribute(name)` – Remove o atributo especificado de um elemento.
   - `element.propertyName` – Define ou obtém o valor de uma propriedade para um elemento.
   - `element.dataset` – Retorna um DOMStringMap contendo todos os atributos de dados personalizados de um elemento.
   - `element.hasAttribute(name)` – Retorna um valor Boolean indicando se um elemento possui o atributo especificado.
   - `element.propertyName = value` – Define o valor de uma propriedade para um elemento.

7. Performance Optimization:
   - `requestAnimationFrame(callback)` – Agenda uma função para ser executada na próxima renderização do navegador.
   - `window.performance.mark(name)` – Cria uma marca de desempenho com o nome especificado.
   - `window.performance.measure(name, startMark, endMark)` – Cria uma medida de desempenho com o nome especificado, usando as marcas de início e fim.
   - `element.getBoundingClientRect()` – Retorna um objeto DOMRect contendo o tamanho e a posição de um elemento.
   - `element.offsetWidth` – Retorna a largura de um elemento, incluindo padding e borda, mas não a margem.
   - `element.offsetHeight` – Retorna a altura de um elemento, incluindo padding e borda, mas não a margem.
   - `element.offsetLeft` – Retorna a distância entre a borda esquerda de um elemento e a borda esquerda do seu elemento pai de deslocamento.
   - `element.offsetTop` – Retorna a distância entre a borda superior de um elemento e a borda superior do seu elemento pai de deslocamento.

**Motivação para o Estudo:**

Dominar a manipulação do DOM é uma habilidade fundamental para qualquer desenvolvedor web. Com essas técnicas, você pode criar sites interativos, dinâmicos e responsivos, tornando a experiência do usuário mais envolvente. O estudo da manipulação do DOM é uma jornada empolgante e recompensadora que oferece uma ampla gama de possibilidades criativas.

Imagine a satisfação de criar interfaces incríveis, animações suaves, formulários inteligentes e interações envolventes, tudo isso através do seu próprio código. Cada linha de código que você escreve tem o poder de transformar ideias em realidade na web.

Lembre-se de que a prática constante é fundamental. À medida que você enfrenta desafios e cria projetos, você solidifica seu conhecimento e aprimora suas habilidades. Não tenha medo de experimentar, errar e aprender com seus erros. A comunidade de desenvolvimento web é vasta e acolhedora, oferecendo recursos e suporte para ajudá-lo em sua jornada.

Então, mantenha-se motivado, continue explorando, pratique e crie coisas incríveis. Seja curioso, ousado e persistente. Com dedicação, você poderá desbloquear oportunidades emocionantes e contribuir para a construção de um mundo digital cada vez mais interativo e cativante.

Aproveite a jornada e nunca subestime o poder das suas mãos para moldar a web! 🚀🌟
