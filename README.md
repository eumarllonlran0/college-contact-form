# Fale Conosco — Faculdade Horizonte

Página de contato de uma faculdade fictícia, feita com **HTML, CSS e JavaScript puros** (sem frameworks). O projeto começou como um exercício de frontend para praticar marcação semântica, estilização responsiva e interatividade básica.

🔗 **Ver online:** https://eumarllonlran0.github.io/formulario-contato-faculdade/

## Funcionalidades

- Formulário dividido em duas seções: **Sobre você** e **Sua mensagem**
- Validação nativa do navegador (campos obrigatórios, formato de e-mail, tamanho mínimo)
- Mensagens de erro exibidas só depois que a pessoa interage com o campo, ligadas a ele por `aria-describedby` para leitores de tela
- Seletor de perfil estilizado como "chips" (Futuro aluno, Aluno atual etc.)
- Contador de caracteres em tempo real no campo de mensagem
- Máscara automática de telefone no formato brasileiro: `(00) 00000-0000`
- Botão de envio muda para "Enviando…" para evitar envios duplicados
- Página de agradecimento que cumprimenta a pessoa pelo nome
- Layout responsivo (funciona bem no celular)
- Modo escuro automático, que segue o tema do sistema
- Respeita a configuração de acessibilidade "reduzir movimento"

## Tecnologias

| Tecnologia | Uso |
| --- | --- |
| HTML5 | Estrutura semântica e validação do formulário |
| CSS3 | Variáveis CSS, Grid, Flexbox, `clamp()`, media queries e pseudo-classes |
| JavaScript | Tratamento de eventos, manipulação do DOM e `sessionStorage` |
| Google Fonts | Fraunces (títulos) e Inter (textos) |

## Estrutura do projeto

```
.
├── index.html         # Página do formulário de contato
├── obrigado.html      # Página exibida após o envio
├── css/
│   └── estilos.css    # Todos os estilos
└── js/
    └── principal.js   # Contador de caracteres, máscara de telefone e envio do formulário
```

## Como executar

Não precisa instalar nada:

1. Baixe ou clone o repositório
   ```bash
   git clone https://github.com/eumarllonlran0/formulario-contato-faculdade.git
   ```
2. Abra o `index.html` no navegador

> Dica: no VS Code, a extensão **Live Server** recarrega a página automaticamente a cada alteração.

## O que aprendi

### HTML

- Estruturei o formulário com tags **semânticas**: `<main>`, `<form>`, `<fieldset>` e `<legend>` para agrupar campos relacionados.
- Liguei cada `<label>` ao seu campo com `for` e `id`, o que melhora a acessibilidade e permite clicar no rótulo para focar o campo.
- Agrupei os chips de perfil em um `<fieldset>` próprio com `<legend>`, a forma nativa de dar nome a um grupo de botões de opção.
- Liguei cada mensagem de erro ao seu campo com `aria-describedby`, para que os leitores de tela a anunciem.
- Usei os tipos de campo certos (`email`, `tel`, `radio`, `checkbox`) e atributos como `required`, `minlength`, `maxlength` e `autocomplete`, para o próprio navegador validar os dados e ajudar a pessoa.
- Entendi a diferença entre usar `<br>` para espaçamento e deixar o espaçamento com o CSS.

### CSS

- Organizei cores e tamanhos em **variáveis CSS** (`:root`), para mudar o tema editando poucos valores.
- Criei o **modo escuro** com `prefers-color-scheme`, redefinindo só essas variáveis, e desativei as transições com `prefers-reduced-motion`.
- Usei `:is()` para aplicar uma regra a vários seletores e `clamp()` para um título que se ajusta ao tamanho da tela.
- Usei **Grid** para colocar campos lado a lado e **Flexbox** para alinhar rótulos, chips e a caixa de seleção.
- Deixei o layout **responsivo** com `@media`: no celular, os campos ficam em uma única coluna e o botão ocupa toda a largura.
- Estilizei os estados de interação: `:hover`, `:focus-visible`, `:checked` e `:user-invalid`.
- Transformei os botões de opção em chips, escondendo o input visualmente e estilizando o `<span>` ao lado com o combinador `+`.
- **Um bug que me ensinou muito:** esqueci um `;` e uma `}` em uma regra, e todo o CSS abaixo dela parou de funcionar. Aprendi a conferir se as chaves estão fechadas e a prestar atenção nos avisos do editor.

### JavaScript

- Dividi o script em funções pequenas e com nomes claros (`formatarTelefone`, `salvarNome`, `recuperarNome`, `configurarFormulario`, `configurarPaginaObrigado`), cada uma com uma única responsabilidade.
- Selecionei elementos com `getElementById` e `form.elements` e tratei as ações da pessoa com `addEventListener`.
- Criei um **contador de caracteres** atualizado no evento `input`.
- Criei uma **máscara de telefone** com uma expressão regular (`/\D/g`) para manter só os dígitos antes de formatar.
- No envio, chamei `event.preventDefault()`, desativei o botão, salvei o nome no `sessionStorage` e redirecionei para a página definida no `action` do formulário.
- Usei `try/catch` para a página continuar funcionando mesmo se o navegador bloquear o armazenamento.
- Aprendi a usar **um único arquivo JS em duas páginas**, verificando se cada elemento existe antes de usá-lo.

## Próximos passos

- [ ] Enviar os dados para um backend real ou um serviço de formulários (ex.: Formspree)
- [x] Adicionar modo escuro com `prefers-color-scheme`
- [x] Ligar as mensagens de erro aos campos com `aria-describedby`
- [x] Colocar o grupo de chips em um `<fieldset>` próprio
- [ ] Adicionar um botão para alternar manualmente entre tema claro e escuro

## Autor

Feito por **Marllon Lorran** — [LinkedIn](https://www.linkedin.com/in/eumarllonlran0/) · [GitHub](https://github.com/eumarllonlran0)
