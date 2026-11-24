# Fale Conosco — Faculdade Horizonte

Página de contato de uma faculdade fictícia, desenvolvida com **HTML, CSS e JavaScript puros** (sem frameworks). O projeto começou como um exercício de front-end para praticar marcação semântica, estilização responsiva e interatividade básica.

🔗 **Demonstração:** https://eumarllonlran0.github.io/formulario-contato-faculdade/

## Funcionalidades

- Formulário dividido em duas seções: **Sobre você** e **Sua mensagem**
- Validação nativa do navegador (campos obrigatórios, formato de e-mail e tamanho mínimo)
- Mensagens de erro exibidas somente depois que o usuário interage com o campo, vinculadas a ele por `aria-describedby` para leitores de tela
- Seletor de perfil estilizado como "chips" (Futuro aluno, Aluno matriculado etc.)
- Contador de caracteres em tempo real no campo de mensagem
- Máscara automática de telefone no formato brasileiro: `(00) 00000-0000`
- Botão de envio muda para "Enviando…" para evitar envios duplicados
- Página de agradecimento que cumprimenta o usuário pelo nome
- Layout responsivo (funciona bem em dispositivos móveis)
- Modo escuro automático, que acompanha o tema do sistema
- Respeita a configuração de acessibilidade "reduzir movimento"

## Tecnologias

| Tecnologia | Uso |
| --- | --- |
| HTML5 | Estrutura semântica e validação do formulário |
| CSS3 | Propriedades personalizadas, Grid, Flexbox, `clamp()`, media queries e pseudo-classes |
| JavaScript | Tratamento de eventos, manipulação do DOM e `sessionStorage` |
| Google Fonts | Fraunces (títulos) e Inter (texto) |

## Estrutura do projeto

```
.
├── index.html        # Página do formulário de contato
├── thank-you.html    # Página exibida após o envio
├── css/
│   └── styles.css    # Todos os estilos
└── js/
    └── main.js       # Contador de caracteres, máscara de telefone e envio do formulário
```

## Como executar

Não é preciso instalar nada:

1. Baixe ou clone o repositório
   ```bash
   git clone https://github.com/eumarllonlran0/formulario-contato-faculdade.git
   ```
2. Abra o `index.html` no navegador

> Dica: no VS Code, a extensão **Live Server** recarrega a página automaticamente a cada alteração.

## O que aprendi

### HTML

- Estruturei o formulário com tags **semânticas**: `<main>`, `<form>`, `<fieldset>` e `<legend>` para agrupar campos relacionados.
- Vinculei cada `<label>` ao seu campo com `for` e `id`, o que melhora a acessibilidade e permite clicar no rótulo para focar o campo.
- Agrupei os chips de perfil em um `<fieldset>` próprio com `<legend>`, a forma nativa de rotular um grupo de botões de opção.
- Vinculei cada mensagem de erro ao seu campo com `aria-describedby`, para que os leitores de tela a anunciem.
- Usei os tipos de input corretos (`email`, `tel`, `radio`, `checkbox`) e atributos como `required`, `minlength`, `maxlength` e `autocomplete`, para que o próprio navegador valide os dados e ajude o usuário.
- Entendi a diferença entre usar `<br>` para espaçamento e deixar o espaçamento a cargo do CSS.

### CSS

- Organizei cores e tamanhos em **propriedades personalizadas** (`:root`), de modo que o tema pode ser alterado editando poucos valores.
- Implementei o **modo escuro** com `prefers-color-scheme`, redefinindo apenas essas variáveis, e desativei as transições com `prefers-reduced-motion`.
- Usei `:is()` para aplicar uma regra a vários seletores e `clamp()` para um título que se ajusta ao tamanho da tela.
- Usei **Grid** para posicionar campos lado a lado e **Flexbox** para alinhar rótulos, chips e a caixa de seleção.
- Deixei o layout **responsivo** com `@media`: no celular, os campos ficam em uma única coluna e o botão ocupa toda a largura.
- Estilizei os estados de interação: `:hover`, `:focus-visible`, `:checked` e `:user-invalid`.
- Transformei os botões de opção em chips ocultando visualmente o input e estilizando o `<span>` adjacente com o combinador `+`.
- **Um bug que me ensinou muito:** esqueci um `;` e uma `}` em uma regra, e todo o CSS abaixo dela parou de funcionar. Aprendi a conferir se as chaves estão fechadas corretamente e a prestar atenção aos avisos do editor.

### JavaScript

- Dividi o script em funções pequenas e com nomes claros (`formatPhone`, `saveName`, `retrieveName`, `setUpForm`, `setUpThankYouPage`), cada uma com uma única responsabilidade.
- Selecionei elementos com `getElementById` e `form.elements` e tratei as ações do usuário com `addEventListener`.
- Criei um **contador de caracteres** atualizado no evento `input`.
- Criei uma **máscara de telefone** usando uma expressão regular (`/\D/g`) para manter apenas os dígitos antes de formatá-los.
- No envio, chamei `event.preventDefault()`, desativei o botão, salvei o nome no `sessionStorage` e redirecionei para a página definida no `action` do formulário.
- Usei `try/catch` para que a página continue funcionando mesmo se o navegador bloquear o armazenamento.
- Aprendi a usar **um único arquivo JS em duas páginas**, verificando se cada elemento existe antes de usá-lo.

## Próximos passos

- [ ] Enviar os dados para um backend real ou um serviço de formulários (ex.: Formspree)
- [x] Adicionar modo escuro com `prefers-color-scheme`
- [x] Vincular as mensagens de erro aos campos com `aria-describedby`
- [x] Colocar o grupo de chips em um `<fieldset>` próprio
- [ ] Adicionar um botão para alternar manualmente entre os temas claro e escuro

## Autor

Desenvolvido por **Marllon Lorran** — [LinkedIn](https://www.linkedin.com/in/eumarllonlran0/) · [GitHub](https://github.com/eumarllonlran0)
