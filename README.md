# guia-expressoes-regulares
Guia de uso para expressões regulares com Javascript.

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

### Remover emojis
```js
function removeEmojis (string) {
  var regex = /(?:[\u2700-\u27bf]|(?:\ud83c[\udde6-\uddff]){2}|[\ud800-\udbff][\udc00-\udfff]|[\u0023-\u0039]\ufe0f?\u20e3|\u3299|\u3297|\u303d|\u3030|\u24c2|\ud83c[\udd70-\udd71]|\ud83c[\udd7e-\udd7f]|\ud83c\udd8e|\ud83c[\udd91-\udd9a]|\ud83c[\udde6-\uddff]|\ud83c[\ude01-\ude02]|\ud83c\ude1a|\ud83c\ude2f|\ud83c[\ude32-\ude3a]|\ud83c[\ude50-\ude51]|\u203c|\u2049|[\u25aa-\u25ab]|\u25b6|\u25c0|[\u25fb-\u25fe]|\u00a9|\u00ae|\u2122|\u2139|\ud83c\udc04|[\u2600-\u26FF]|\u2b05|\u2b06|\u2b07|\u2b1b|\u2b1c|\u2b50|\u2b55|\u231a|\u231b|\u2328|\u23cf|[\u23e9-\u23f3]|[\u23f8-\u23fa]|\ud83c\udccf|\u2934|\u2935|[\u2190-\u21ff])/g

  return string.replace(regex, '')
}
```
