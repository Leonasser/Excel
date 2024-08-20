## Summary:
- [English](#english)
- [Português](#português)

---

## English
This section covers how to reference and extract names from a table using Excel formulas.

### For tables with code and name columns
![Spreadsheet showing the orange cells to be filled and green cells containing data](https://github.com/user-attachments/assets/b4eaadd7-c4cd-421d-bc02-3bbbf6c81735)
<p style="font-size:10px;">Cells needing names are in orange; cells with data are in green.</p>

#### Structure:
- `Code_Cell` is the referenced cell in line with the code.
- `Array` is the table with the code and names.
- The `Find` function with `Right` is optional for filtering multiple names, like "name1 - name2"; change it to your needs.

```excel
=IFERROR(
    RIGHT(
        VLOOKUP(Code_Cell, Array, 2, FALSE),
        FIND(" - ", VLOOKUP(Code_Cell, Array, 2, FALSE))-1
    ), 
    "Code Not Registered"
)
```

Here’s what each part does:
- `VLOOKUP(Code_Cell, Array, 2, FALSE)`: Looks up the code in the array and returns the corresponding name.
- `FIND(" - ", ...) - 1`: Finds the position of the dash to trim the name before it, the spaces between are for cases like "Living-room".
- `RIGHT(..., FIND(...))`: Extracts the name after the dash.
- `IFERROR(..., "Code Not Registered")`: Returns "Code Not Registered" if the lookup fails.

---

## Português
Esta seção cobre como referenciar e extrair nomes de uma tabela usando fórmulas no Excel.

### Para Tabelas com coluna de código e Nome
![Spreadsheet showing the orange cells to be filled and green cells containing data](https://github.com/user-attachments/assets/b4eaadd7-c4cd-421d-bc02-3bbbf6c81735)
<p style="font-size:10px;">Em laranja, as células a serem preenchidas; em verde, as células contendo os dados.</p>

#### Estrutura:
- `Célula_Código` é o código referenciado na linha.
- `Matriz` é a tabela com o código e os nomes.
- O `LOCALIZAR` junto a `ESQUERDA` é opcional para filtrar vários nomes, como “nome1 - nome2”; altere-o de acordo com suas necessidades.

```excel
=SEERRO(
    ESQUERDA(
        PROCV(Célula_Código; Matriz; 2; FALSO);
        LOCALIZAR(" - "; PROCV(Célula_Código; Matriz; 2; FALSO))-1
    );
    "Código Não Cadastrado"
)
```
Aqui está o passo a passo:
- `PROCV(Célula_Código, Matriz, 2, FALSO)`: Procura o código na matriz e retorna o nome correspondente.
- `LOCALIZAR(" - ", ...) - 1`: Encontra a posição do traço para cortar o nome antes dele, os espaços entre eles são para casos como "Guarda-Chuva".
- `ESQUERDA(..., LOCALIZAR(...))`: Extrai o nome após o traço.
- `SEERRO(..., "Código Não Cadastrado")`: Retorna "Código Não Cadastrado" se a busca falhar.

