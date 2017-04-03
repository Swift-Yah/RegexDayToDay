.           curinga             qualquer caractere, exceto a quebra de linha \n (ver flag_dotall)
[...]       conjunto            qualquer caractere incluido no conjunto
[^...]      conjunto negado     qualquer caractere não incluido no conjunto
\d          dígito              o mesmo que [0-9]
\D          não-digíto          o mesmo que [^0-9]
\s          branco              espaço, quebra de linha, tabs etc.; o mesmo que [ \t\n\r\f\v]
\S          não-branco          o mesmo que [^ \t\n\r\f\v]
\w          alfanumérico        o mesmo que [a-zA-Z0-9_] (mas pode incluir caracteres Unicode; ver flag_unicode)
\W          não-alfanumérico    o complemento de \w
\           escape              anula o significado especial do metacaractere seguinte; por exemplo, \. representa apenas um ponto, e não o curinga

{n}         exatamente n ocorrências
{n,m}       no mínimo n ocorrências e no máximo m
{n,}        no mínimo n ocorrências
{,n}        no máximo n ocorrências
?           0 ou 1 ocorrência; o mesmo que {,1}
+           1 ou mais ocorrência; o mesmo que {1,}
*           0 ou mais ocorrência
«q»?        modera qualquer um dos quantificadores acima (ver Gula × moderação)

^           início do texto, ou de uma linha com o flag re.MULTILINE
\A          início do texto
$           fim do texto, ou de uma linha com o flag re.MULTILINE; não captura o \n no fim do texto ou da linha
\Z          fim do texto
\b          posição de borda, logo antes do início de uma palavra, ou logo depois do seu término; o mesmo que a posição entre \W e \w ou vice-versa
\B          posição de não-borda

(...)       define um grupo, para efeito de aplicação de quantificador, alternativa ou de posterir extração ou re-uso
...|...     alternativa; casa a regex à direita ou à esquerda
\«n»        recupera o texto casado no n-ésimo grupo


$
\n

\t
\n

(\d{3}\.)
R$ $1

m²\n(\d+)$
m² - $1 dorms

dorms\n(\d+\D+\d+)$
m² - $1 dorms


^(.+)$
[columns count="1"]\n[icon_box type="4" icon="$1" title=""]\n$1\n[/icon_box]\n[/columns]\n


Cores: Acha Hex de 3 digitos e transforma em 6
    (#)(\w)(\w)(\w)(\W?[\s$])
    $1$2$2$3$3$4$4$5

Cores: Acha caracteres alfanuméricos e transforma em caixa alta \u ou caixa baixa \l (Sublime only)
    (?<!^)#([a-fA-F0-9]){6}
    \U$0

Classes: Inclue todas as classes que contenham o ".chat-left"
    ^.+\.chat-left.+[\w\:\#\;\-\(\,\%\s.\)]*\}\n

CSS: Busca classes com apenas 1 propriedade e coloca em uma linha
    (\{)\n\s+(.+)\s+(\})
    $1 $2 $3
