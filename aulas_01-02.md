## AULA 0/setup — Iniciação ao VS Code + primeiro HTML (encaixar no início da Aula 1)


1. Criar no desktop/Documentos a pasta `logica-js/` (arquivo → abrir pasta no VS Code)
2. Novo arquivo `index.html` → digitar `!` + Tab (Emmet gera o esqueleto)
3. Trocar o `<title>` e o `<h1>` para o próprio nome
4. Copiar o bloco `<script>` do `molde.html` 

5. Salvar (Ctrl+S) → abrir no navegador → **F12 → aba Console** → recarregar (Ctrl+R)
6. Primeiro código: `console.log("Olá, mundo!");` dentro do `<script>` 

7. Provocar um erro de propósito (tirar uma aspas) → ler a mensagem vermelha → corrigir

Extensões do VS Code 
 Prettier. 
 
A partir daqui, todo exercício das aulas 1–4 roda dentro do `<script>` do HTML de cada aula (`aula1.html`, `aula2.html`...).

## AULA 1 — Seu primeiro programa: `console.log` e saída de dados
**Habilidade da ementa:** comandos de entrada, processamento e saída · comunicar-se com clareza.

### Card de conceito (8 min) — projetar/ler
Um **algoritmo** é uma sequência finitа de passos que resolve um problema. Escrever algoritmo em JavaScript é dar ordens a uma máquina que **não entende contexto** — só sintaxe.

Hoje aprendemos o primeiro comando: **saída**.

```js
console.log("Olá, mundo!");
```
- `console.log()` → imprime uma linha no console do navegador (F12 → aba Console).
- O que vai **dentro das aspas** é texto literal.
- Ponto e vírgula `;` marca o fim da instrução (opcional no JS, mas vamos padronizar com `;`).

| Termo JS | Analogia do cotidiano |
|---|---|
| instrução | uma linha da receita de bolo |
| console | o prato onde a receita "chega pronta" |
| sintaxe | pontuação: errar vírgula muda tudo |

### Teoria formal (10 min — quadro/slide, registro no caderno)
**Pergunta de resgate:** *"O que separava um argumento válido de uma falácia na Unidade 1?"* → um algoritmo é a "prova" do mundo da computação: cada passo precisa garantir o próximo.

**Definição (Knuth):** algoritmo é um procedimento que executa, em um número finito de passos, uma sequência de instruções precisas e bem definidas para resolver um problema. Propriedades obrigatórias:
1. **Finitude** — termina após um número finito de passos (um algoritmo que nunca acaba não resolve nada);
2. **Precisão** — cada instrução é clara, sem ambiguidade (a máquina não "entende contexto");
3. **Entrada** — zero ou mais dados iniciais;
4. **Saída** — um ou mais resultados;
5. **Efetividade** — todo passo é executável na prática.

**Ciclo E-P-S:** `ENTRADA → PROCESSAMENTO → SAÍDA`. Hoje dominamos a **saída** (`console.log`); entrada chega na aula 4 (`prompt`); processamento nas aulas 2–3.

**Representações do MESMO algoritmo** (da mais humana à mais rígida) — ementa: "representações visuais, português estruturado ou linguagem algorítmica":
```
Linguagem natural → Fluxograma (aula 5) → Portugol (pseudocódigo) → Código (JS)
```
Comparação portugol ↔ JavaScript (nosso padrão de tradução até o fim da UC):
| Português estruturado | JavaScript |
|---|---|
| `algoritmo "apresentacao"` | `<script> ... </script>` |
| `inicio` / `fim` | início / fim do bloco de código |
| `escreva "Olá"` | `console.log("Olá");` |

### Desafio 

Escrever o "cartão de apresentação" do aluno:
```js
console.log("Nome: Maria");
console.log("Turma: 2º DS");
console.log("Lema: lógica antes da linguagem");

```
Pergunta *o que acontece se eu esquecer uma aspa?* → rodar o erro de propósito e ler a mensagem do console (cultura de erro desde a aula 1).

### Desafios autônomos (20 min) — Núcleo: 1.1–1.4 · 🏖️ Praia (quem terminar antes): 1.5, 1.6
**1.1** Imprima exatamente: `Estou aprendendo lógica com JavaScript`
<details><summary>Gabarito</summary>

```js
console.log("Estou aprendendo lógica com JavaScript");
```
</details>

**1.2** Imprima seu nome em uma linha e sua idade na outra.
<details><summary>Gabarito</summary>

```js
console.log("Nome: João");
console.log("Idade: 16");
```
</details>

**1.3** Imprima as etapas do algoritmo "trocar lâmpada queimada" (mín. 4 linhas).
<details><summary>Gabarito (um possível)</summary>

```js
console.log("1. Desligue o disjuntor");
console.log("2. Retire a lâmpada queimada");
console.log("3. Enrosque a lâmpada nova");
console.log("4. Religue o disjuntor e teste");
```
</details>

**1.4** Corrija o código quebrado:
```js
console.log("Hoje é aula de lógica;
console.log();
```



**1.5** Imprima a tabuada do 7 como saída fixa (7, 14, 21... 70) — 1 linha por resultado.



**1.6** O que imprime `22` e não `202`? Corrija: `console.log(20 + "2")`.



### Boss level — "Recibo de lanchonete"
Imprimir um recibo com pelo menos 4 linhas de `console.log`, incluindo itens com preço e uma linha final "TOTAL: R$ ...". Validar: 7 linhas de código, zero erros no console.




---

## AULA 2 — Strings, concatenação e template literals
**Habilidade da ementa:** expressões e operadores · entrada-processamento-saída.

### Card de conceito (8 min)
**String** = texto entre aspas. Dúvidas frequentes: aspa simples `' '` e crase `` ` ` `` também funcionam; aspas dentro de aspas quebram o código.

**Concatenação** com `+` cola textos:
```js
console.log("Olá, " + "Maria");        // "Olá, Maria"
console.log("2" + "2");                // "22"  (texto + texto)
console.log(2 + 2);                    // 4     (número + número)
```

**Template literal** com crase e `${ }` — nosso padrão para saídas bonitas:
```js
console.log(`Total: R$ ${23} às ${17}h`);
```
- `\n` quebra linha dentro da string.



### Teoria formal 




- **Dado** = matéria-prima do algoritmo; **string** = sequência de caracteres (texto). 


- **Expressão** = combinação de operandos e operadores que o interpretador **avalia** resultando num valor. É a parente computacional da **proposição** que avaliamos na tabela-verdade — com uma diferença: expressão pode avaliar para número, texto ou lógico.

- **Concatenação** (`+` entre strings) ≠ **adição** (`+` entre números): o operador é o mesmo, a avaliação depende dos **tipos** dos operandos — a máquina decide "por regra", nunca por contexto 



### Desafio 
```js
let nome = "Ravi";   // caixinhas só viram "ofício" na aula 3; aqui é só para ver ${nome} funcionando
console.log(`Bom dia, ${nome}! Você está na turma de Desenvolvimento de Sistemas.`);
```
Testar trocando o nome. Provocar: *e se eu escrever `Bom dia, nome!` sem o cifão?* → sai a palavra "nome".

### Desafios

**2.1** Usando `"Sistema"` e `"Prisional"` (duas strings coladas com `+`), imprima `Sistema Prisional` com um espaço entre as palavras.



**2.2** O que cada linha imprime? Escreva a resposta ANTES de rodar.
```js
console.log("3" + 4);
console.log(3 + 4 + "");
console.log(`soma: ${3 + 4}`);
```


**2.3** Imprima em UMA linha, com template literal: `Meu nome é <nome>, tenho <idade> anos.`



**2.4** Gere a "ficha de matrícula" em 3 linhas usando um único `console.log` com `\n`:
```
Aluno: ...
Turma: ...
Curso: Técnico em Desenvolvimento de Sistemas
```



**2.5** Corrija os 2 bugs: `console.log('Aula de "lógica" e `strings`');`





### — "Convite de aniversário"
Programa de 3 linhas que monta e imprime um convite: `"Venha ${nome}! Festa dia ${data} às ${hora}."` + uma linha de contagem: faltam `${(30 - 12)} dias`. Critério: usar `+` pelo menos 1 vez e template literal pelo menos 2.




