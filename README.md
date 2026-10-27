# Meu Caderno de Receitas

Aplicação web para cadastrar, organizar, pesquisar, editar, imprimir e fazer backup de receitas diretamente no navegador.

## Sobre o projeto

O **Meu Caderno de Receitas** é uma aplicação desenvolvida com HTML, CSS e JavaScript puro. Cada receita registra o nome do usuário, o nome da receita, os ingredientes e o modo de preparo.

As informações são armazenadas localmente no navegador. O projeto não utiliza servidor, conta online ou banco de dados remoto.

## Funcionalidades

- Cadastro de receitas.
- Edição de receitas salvas.
- Exclusão individual com confirmação.
- Pesquisa por nome da receita, usuário, ingrediente ou conteúdo do preparo.
- Impressão de todas as receitas.
- Impressão individual de uma receita.
- Exportação dos dados para backup em JSON.
- Importação de backup em JSON.
- Armazenamento local com `localStorage`.
- Modal com informações sobre armazenamento e responsabilidade pelos dados.
- Layout responsivo para computadores e dispositivos móveis.
- Estilos específicos para impressão.
- Mensagens de status acessíveis com `aria-live`.

## Tecnologias utilizadas

- HTML5
- CSS3
- JavaScript Vanilla
- Web Storage API (`localStorage`)
- FileReader API
- Blob API
- CSS Grid
- Media Queries

## Estrutura do projeto

```text
meu-caderno-de-receitas/
├── index.html
└── README.md
```

A estrutura, os estilos e toda a lógica da aplicação estão concentrados no arquivo `index.html`.

## Como executar

1. Baixe os arquivos do projeto.
2. Mantenha o `index.html` e o `README.md` na mesma pasta.
3. Abra o arquivo `index.html` em um navegador moderno.
4. Preencha os campos do formulário.
5. Clique em **Salvar receita**.

Não é necessário instalar dependências, configurar banco de dados ou executar um processo de compilação.

## Cadastro de receitas

Cada receita possui os seguintes campos:

| Campo | Descrição |
|---|---|
| Nome do usuário | Identifica quem cadastrou a receita |
| Nome da receita | Título da receita |
| Ingredientes | Lista de ingredientes, preferencialmente um por linha |
| Modo de preparo | Instruções para preparar a receita |

Todos os campos são obrigatórios.

## Pesquisa

O campo de pesquisa filtra as receitas enquanto o usuário digita. A busca considera:

- nome do usuário;
- nome da receita;
- ingredientes;
- modo de preparo.

A comparação não diferencia letras maiúsculas de minúsculas.

## Edição e exclusão

O botão **Editar** preenche o formulário com os dados da receita selecionada. Depois da alteração, basta salvar novamente.

O botão **Excluir** solicita confirmação antes de remover definitivamente o registro do armazenamento local.

## Impressão

A aplicação permite:

- imprimir a lista completa pelo botão **Imprimir**;
- imprimir somente uma receita pelo botão **Imprimir receita**.

Durante a impressão, formulários, controles, avisos e botões de ação são ocultados para melhorar a apresentação do documento.

## Armazenamento local

As receitas são armazenadas no `localStorage` com a chave:

```text
caderno_receitas_v2
```

Os dados ficam vinculados ao navegador e ao dispositivo utilizados. Eles não são enviados para um servidor ou para uma conta online.

As receitas podem ser perdidas se os dados do navegador forem apagados, se o navegador for reinstalado, se o dispositivo apresentar defeito ou se o arquivo for aberto em outro navegador ou aparelho.

## Backup e restauração

### Exportar backup

O botão **Exportar backup** gera um arquivo JSON contendo a identificação da aplicação e todas as receitas cadastradas. O nome do arquivo inclui a data e o horário da exportação.

### Importar backup

O botão **Importar backup** permite selecionar um arquivo JSON. A aplicação aceita:

- um objeto com a propriedade `receitas`;
- uma lista JSON direta de receitas.

> Atenção: a importação substitui todas as receitas armazenadas atualmente. A aplicação solicita confirmação antes de concluir a operação.

## Privacidade e responsabilidade pelos dados

A interface apresenta um aviso explicando que as receitas existem somente no armazenamento local do navegador. Para reduzir o risco de perda, recomenda-se exportar backups regularmente e guardar os arquivos JSON em um local seguro.

## Personalização

As cores principais podem ser alteradas nas variáveis CSS:

```css
:root {
  --p: #b84a2b;
  --g: #496b4a;
  --bg: #fff8f1;
  --bd: #e5d5c8;
  --tx: #2d2724;
}
```

Também é possível modificar os limites dos campos diretamente nos atributos `maxlength` do formulário.

## Compatibilidade

Use um navegador moderno com suporte a:

- JavaScript;
- `localStorage`;
- FileReader API;
- Blob e Object URLs;
- impressão pelo navegador;
- CSS Grid e Media Queries.

## Limitações

- Não existe sincronização entre dispositivos.
- Não há autenticação de usuários.
- Não há banco de dados remoto.
- A importação substitui os dados atuais.
- O arquivo de backup precisa possuir uma estrutura JSON válida e compatível.
- A limpeza dos dados do navegador pode apagar todas as receitas.

## Autor

**Alberto de Campos Neto**

## Aviso

> Este projeto é uma demonstração educacional desenvolvida para estudos de HTML, CSS e JavaScript. A empresa mencionada é fictícia e qualquer semelhança com empresas reais é mera coincidência.
