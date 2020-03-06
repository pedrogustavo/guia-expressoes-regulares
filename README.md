# guia-expressoes-regulares
Guia de uso para expressões regulares com Javascript

```js
// Construtor
var meuRegex = new RegExp('padraoDeBusca')

// RegExp literal (disponível apenas em browsers atualizados)
const meuRegex = /padraoDeBusca/

// match em uma string
meuRegex.test('minhaString')
```

## Metacharacters
`.`: representa TODOS caracteres possíveis, exceto quebras de linha `\n, \r, \u2028, \u2029`

`\d`: representa qualquer dígito de 0 a 9 | igual a: `/[0-9]/` 

`\w`: representa caracteres de palavra, ou seja, alfa - numéricos(letras não acentuadas e números) e underlines(_)  
igual a: `/[A-z0-9_]/` 

`\b`: representa limite de palavra 

`\s`: representa espaçamentos(espaços(\s), tabulações(\t) e quebras de linha(\n, \r, \u2028, \u2029)) 


*Para usar a barra invertida, o ponto ou qualquer metacaractere com seus valores literais, preceda com uma barra invertida, por exemplo:\\ e \.*


## Quantifiers
`?`: captura de 0 a 1 vez;
`*`: captura de 0 a n vezes;
`+`: captura de 1 a n vezes;
`{x}`: captura x vezes;
`{x,}`: captura de x a n vezes;
`{x,y}`: captura de x a y vezes;



`/(.+?)/` *Para capturamos somente o mínimo necessário.*

## Extras e exemplos

**Sets negados:** `^` como primeiro caractere, nega o set, senão é lido literalmente
**Ranged sets:** `-` entre caracteres monta um range set
**Caracteres acentuados (alfabeto brasileiro):** `/\u00C0-\u00FF/`

*Por exemplo, para extrair palavras que contenham car, escrevemos `/[A-z]*car[A-z]*/` e capturamos cara, trocar, trocarmos, etc.*
