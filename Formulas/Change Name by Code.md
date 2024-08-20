## Summary:
- [English](#english)
- [Português](#português)

### English
### For tables with code and name columns
#### Structure:
"Code_Cell" is the referenced code in line<br>
"Array" is the table with the code and names<br>
The "Find" is optional for filtering multiple names, like "name1 - name2", change it to your needs

```
=IFERROR(
    LEFT(
        VLOOKUP(Code_Cell, Array, 2, FALSE),
        FIND("-", VLOOKUP(Code_Cell, Array, 2, FALSE))-1
    ), 
    "Code Not Registered"
)
```
<br>
<br>

### Português
### Para Tabelas com coluna de código e Nome
#### Estrutura:
"Célula_Código" é o código referenciado na linha<br>
"Matriz" é a tabela com o código e os nomes<br>
O "LOCALIZAR" junto a "Esquerda" é opcional para filtrar vários nomes, como “nome1 - nome2”, altere-o de acordo com suas necessidades

```
=SEERRO(
	ESQUERDA(
		PROCV(Célula_Código; Matriz; 2; FALSO);
		LOCALIZAR("-"; PROCV(Célula_Código; Matriz; 2; FALSO))-1
	);
	"Código Não Cadastrado"
)
```
