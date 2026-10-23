## AULA 3 — Variáveis (`let`/`const`), tipos numéricos e atribuição
**Habilidade da ementa:** variáveis e constantes.

### Card de conceito 

**Variável** = caixa nomeada que guarda um valor. **Constante** = caixa que não muda.
```js
let idade = 16;          // pode ser reatribuída
idade = idade + 1;       // 17 — a variável "envelheceu"
const CURSO = "DS";      // NÃO pode ser reatribuída
```
- Regras de nome (identificador): começar com letra/`_`/`$`; sem espaços; sem palavras reservadas (`let`, `if`, `for`...); padrão da turma: `camelCase`.
- Atribuição `=` **não é igualdade**: "guarda o da direita na caixa da esquerda".
- Atualização com atalhos: `idade += 1` ou `idade++`.
- `%` resto da divisão: `7 % 2` → `1`; `500 % 60` → `20` (o que "sobra").
- `Math.floor(8.33)` → `8` (arredonda para baixo, joga os centavos fora).
- `numero.toFixed(2)` → 2 casas decimais: `(6.8333).toFixed(2)` → `"6.83"`.

### Teoria formal 

**Pergunta de resgate:** *"Se todo algoritmo precisa de precisão, como a máquina 'lembra' de um valor entre dois passos?"* → memória.

- **Memória:** a variável é um **endereçamento nomeado**: o nome é etiqueta, o valor mora em uma célula de memória. `let a = 5` = criar célula + rotular + guardar; `a = 10` = **sobrescrever** (não existe "mudança", existe substituição).

- **Constante** (`const`) = célula lacrada na criação: reatribuição é erro de execução (`TypeError`) — não é enfeite, é proteção de dados que não podem mudar (taxa, nome da escola).

- **Identificador** (nome): regras de formação + palavras **reservadas** (léxico oficial da linguagem — `let`, `if`, `for`... não podem virar nomes; analogia: são "conectivos", não "proposições").

- **Tipagem dinâmica** do JS: o tipo gruda no **valor**, não na caixa — `let x = 5` e depois `x = "oi"` é aceito. (Outras linguagens amarram o tipo na caixa; Isso volta na Unidade 4.)

- **Teste de mesa** = método formal de verificação inspirado na argumentação dedutiva da Unidade 1: tabela linha a linha (variável | valor | saída), provando que o algoritmo termina e produz a saída certa.

### Desafio  — "A conta de chegada"
```js
let saldo = 100;
saldo += 45;     // depósito
saldo -= 30;     // pix
console.log(`Saldo final: R$ ${saldo}`);
```
Pergunta de checagem: *por que `saldo += 45` e não `saldo = saldo + 45`? as duas funcionam?* → sim, são equivalentes.

### Desafios autônomos 

**3.1** Crie uma constante para o nome da escola e uma variável para o número de alunos; imprima `"Colégio X tem 40 alunos."`




**3.2** O que imprime? Racionalize a ordem.
```js
let a = 5;
let b = a;
a = 10;
console.log(b);
```



**3.3** Converta minutos: variável `duracaoMin = 500` → imprima `X h e Y min` usando `%` e divisão.




**3.4** Média de 3 notas: variáveis `n1 = 7; n2 = 5.5; n3 = 8;` → imprima `Média: 6.83` (duas casas com `toFixed(2)`).

**3.5** Ache os 3 bugs: `cont numero = "16 anos"; let 2nota = 5; const media`


---

## AULA 4 — Tipos de dados, `typeof` e conversões + entrada de dados
**Habilidade da ementa:** tipos de dados nativos; conversão (implícita e explícita); comandos de entrada.

### Card de conceito

Três tipos que usamos agora: **number**, **string**, **boolean** (`true/false` — ponte com a tabela-verdade da Unidade 2).
```js
typeof 16          // "number"
typeof "16"        // "string"
typeof true        // "boolean"
```
- Conversão **implícita** (o JS faz sozinho): `"2" + 2` → `"22"`.
- Conversão **explícita** (nós mandamos): `Number("2") + 2` → `4` ; `String(2)` → `"2"`.
- `Number("abc")` → `NaN` (Not a Number — "não vira número").
- **Entrada** de dados no navegador: `prompt("Digite seu nome")` → sempre devolve **string** (por isso convertemos!).

```js
let nome = prompt("Qual é o seu nome?");
console.log(`Olá, ${nome}!`);
```

### Teoria formal

**Pergunta de resgate:** *"Na Unidade 2, quantas linhas tinha a tabela-verdade de 2 proposições?"* → 2² = 4; portas lógicas avaliavam V/F — hoje o JS avalia `true/false` exatamente igual.

- **Tipos primitivos da aula:** `number` (números — base decimal na escrita, binário por dentro, retomada de sistemas de numeração), `string` (texto), `boolean` (valor lógico: `true`≡V, `false`≡F 

- **Conversão:** implícita (coerção: a máquina decide sozinha — `"2" + 2` → `"22"`) vs explícita (nós decidimos: `Number("2")` → `2`). Regra prática da turma: **toda entrada de `prompt` é string e toda conta precisa de conversão explícita.**
- **`NaN`** = "avaliação impossível": `Number` só aceita string que seja número puro; qualquer operação com `NaN` contamina o resto (analogia: proposição sem valor lógico invalida o argumento).
- **Comando de ENTRADA** (`prompt`) fecha o ciclo E-P-S iniciado na aula 1: agora o algoritmo lê dados do usuário, processa e devolve saída.

### Desafio - "Idade que soma"
```js
let idade = Number(prompt("Digite sua idade:"));
console.log(`No ano que vem você terá ${idade + 1} anos.`);
```
Demonstrar o bug ao vivo **sem** `Number`: idade `16` → `"161"` (string `+` número). Explicar o porquê.

### Desafios autônomos (20 min) — Núcleo: 4.1–4.3, 4.5 · 🏖️ Praia: 4.4
**4.1** Classe (prever `typeof`): `"42"` · `42` · `4 + 2` · `"4" + "2"` · `true` · `"true"`

**4.2** Converta e calcule: `let preco = "19.90";` → imprima o preço de 3 unidades com 2 casas decimais.

**4.3** Verifique a senha com booleano (ferramenta nova só deste desafio: `===` compara valor **e** tipo — `"5" === 5` é `false`; aprofundaremos na aula de operadores):
```js
let senhaDigitada = prompt("Senha?");
const SENHA_CERTA = "abcd";
console.log(senhaDigitada === SENHA_CERTA);
```
O que aparece se eu digitar `abcd`? E se eu apagar o `const` e reatribuí-lo?

**4.4** Explique o resultado: `console.log(Number("R$ 10") + 5)`

**4.5** Boletim: um `prompt` para nome, dois para notas (com `Number`) → imprima média com template literal.

### 

Gerar um "cartão de estudante" completo: nome, sobrenome, idade, cidade e matrícula com o padrão `DS-<2 primeiras letras do nome>-<idade>`.

