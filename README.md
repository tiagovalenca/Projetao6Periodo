# Projetao6Periodo

## Instalação

```
docker-compose up
```

## Utilização

Primeiro deve se acessar o link do jupyter notebook disponibilizado pelo terminal e rodar o notebook para que ocorra a criação do dataset e sua inserção no banco de dados do postgres.

Após isso é necessário abrir outra instância do terminal na mesma pasta, digitar o comando abaixo e criar o usuário admin para uso do superset. 
```
docker-compose exec superset superset-demo
```

Por fim é preciso importar a versão mais atual da dashboard que existe no repositório passando como tabela a tabela public.paciente
