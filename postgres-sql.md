## Postgres
**- listar bases de dados existentes:** `\l`
**- conectar com um banco de dados:** `\c nome_do_banco;`
**- ver a descrição de uma tabela criada:** `\d nome_da_tabela;`
**- importar arquivo em uma tabela:** `\i ~/caminho/nome_do_arquivo.sql;`

## SQL

**- criar um banco de dados:** 
```sql
create database nome_do_banco
```
**- criar uma tabela:** 
```sql
create table nome_da_tabela (
	id SERIAL PRIMARY KEY,
	atributo_decimal DECIMAL,
	atributo_data DATE,
	atributo_texto VARCHAR(20),
	atributo_inteiro INTEGER
);
```
*Obs: atributos do tipo SERIAL recebem um valor atribuido pelo próprio banco.*

**- inserir valores em uma tabela:** 
```sql
insert into nome_da_tabela (atributo_decimal, atributo_data, atributo_texto, atributo_inteiro)
values (valor_decimal, 'valor_data', 'valor_texto', valor_inteiro);
```
**- selecionar todos os itens da tabela:**
```sql
select * from nome_da_tabela
```
**selecionar itens com condição:**
```sql
select * 
from nome_da_tabela
where atributo_inteiro == 10 

select * 
from nome_da_tabela
where atributo_decimal > 100.0 and atributo_inteiro == 10

select * 
from nome_da_tabela
where atributo_texto like 'COMEÇAO COM%'

select * 
from nome_da_tabela
where atributo_texto like '%TERMINA COM'

select * 
from nome_da_tabela
where atributo_texto like '%TEM NO MEIO%'

select * 
from nome_da_tabela
where CONDIÇÃO
```

**- selecionar 20% dos valores decimais: **
```sql
select atributo_inteiro*0.2, atributo_decimal 
as nome_dessa_coluna
from compras;
```

**- atualizar dado:**
```sql
update nome_da_tabela
set atributo_inteiro = 12
where id = 12;
```

**- selecionar intervalo de datas:**
```sql
select atributo_inteiro
from nome_da_tabela
where atributo_data between '10-10-1997' and '12-12-2018';
```

**- deletar elementos da tabela:**
```sql
delete from nome_da_tabela
where CONDIÇÃO
```
**- exibir datas no formato brasileiro:**
```sql
select atributo_data, to_char(atributo_data, 'dd-mm-yyyy') as data_brasil from nome_da_tabela;
```

**- alterar tabela para que o atributo não seja nulo:**
```sql
alter table nome_da_tabela
column atributo_decimal
set not null;
```
*Obs: Se já tivermos valores nulos inseridos na tabela, não funcionará. Primeiro o valor nulo deve ser removido do banco.*

**- alterar tabela para que vazio seja preenchido com 0.0:**
```sql
alter table nome_da_tabela
column atributo_decimal
set default 0.0;
```
**- criar um novo tipo:**
```sql
create type novo_tipo as enum('valor1', 'valor2', 'valor3');
```

**- adicionar coluna em tabela existente:**
```sql
alter table nome_da_tabela
add column novo_atributo novo_tipo;
```

**- renomear coluna em tabela existente:**
```sql
alter table nome_da_tabela
rename column atributo_inteiro to inteiro_atributo;
```
**- somar valores de atributos:**
```sql
select sum(atributo_decimal)
from nome_da_tabela
where alguma_condição;
```

**- contar número de instancias de um atributo em uma tabela:**
```sql
select count(atributo_decimal)
from nome_da_tabela;
```

**- calcular a média dos valores de uma tabela:**
```sql
select avg(atributo_decimal) as media
from nome_da_tabela;
```
**- agrupar dados de valor ano de uma data:**
```sql
select to_char(atributo_data, 'YYYY') as ano, sum(atributo_decimal)
from nome_da_tabela
group by ano;
```

**- selecionar com junção simples:**
```sql
select * 
from tabela1, tabela2
where tabela1.nome = tabela2.nome;

select * 
from tabela1
join tabela2 on tabela1.nome = tabela2.nome;
```

**- adicionar restrição de chave secundária em uma tabela existente:**
```sql
alter table nome_a_tabela
add foreign key(atributo_de_fora) references tabela_referida
```
*Obs: Se já existirem valores que violam a restrição inseridos na tabela, não vai funcionar. Antes de adicionar as restrições, esses valores devem ser excluídos.*

**- cruzar uma tabela com ela mesma em todas as combinações possíveis:**
```sql
select *
from tabela, tabela n2;
```
