# Indicados Ao Oscar 🏆

**Quantas vezes Natalie Portman foi indicada ao Oscar?**
R: 3 vezes.

Q:
```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_do_indicado Like "%Natalie Portman%";

```

**Quantos Oscars Natalie Portman ganhou?**
R: 1 vez.

Q:
```sql
SELECT COUNT(*) FROM indicados_ao_oscar
WHERE nome_do_indicado Like "%Natalie Portman%" AND vencedor = "true";
````

**Amy Adams já ganhou algum Oscar?**
R: Não.

Q:
```sql
SELECT * FROM indicados_ao_oscar WHERE nome_do_indicado  Like "%Amy Adams%";
```

**A série de filmes Toy Story ganhou um Oscar em quais anos?**
R: Sim, 2011, 2011 e 2020.

Q:

```sql
SELECT ano_cerimonia FROM indicados_ao_oscar WHERE nome_do_filme Like "%Toy Story%" AND vencedor = "true"
```

**A partir de que ano que a categoria "Actress" deixa de existir?**

**Quem ganhou o primeiro Oscar para Melhor Atriz? Em que ano?**

**Na campo "Vencedor", altere todos os valores com "true" para 1 e todos os valores "false" para 0.**

**Em qual edição do Oscar "Crash" concorreu ao Oscar?**
R: 2006

Q:
```sql
SELECT ano_cerimonia FROM indicados_ao_oscar WHERE nome_do_filme Like "%Crash";
```

**O filme Central do Brasil aparece no Oscar?**
R: Não.

Q:
```sql
SELECT COUNT(*) > 0 FROM indicados_ao_oscar WHERE nome_do_filme Like "%Central do Brasil%";
```

**Inclua no banco 3 filmes que nunca foram nem nomeados ao Oscar, mas que merecem ser.**

**Denzel Washington já ganhou algum Oscar?**
R: Sim, 2.

Q:
```sql
SELECT COUNT(*) 
FROM indicados_ao_oscar
WHERE nome_do_indicado LIKE '%Denzel Washington%'
AND vencedor = 'true';
;
```


**Quais os filmes que ganharam o Oscar de Melhor Filme?**

**Bonus: Quais os filmes que ganharam o Oscar de Melhor Filme e Melhor Diretor na mesma cerimonia?**

**Bonus: Denzel Washington e Jamie Foxx já concorreram ao Oscar no mesmo ano?**
R: Sim, em 2017.

```sql
SELECT DISTINCT ano_cerimonia 
FROM indicados_ao_oscar
WHERE (nome_do_indicado LIKE '%Denzel Washington%' OR nome_do_indicado LIKE '%Jamie Foxx%')
GROUP BY ano_cerimonia
HAVING COUNT(DISTINCT nome_do_indicado) > 1;
```
