# Loterias API

## Importante!
> Esta biblioteca é um web crawler do site da Caixa Econômica Federal, podendo parar de responder por alterações na estrutura da página. Se você identificar um erro de acesso a um dos dados, favor abrir uma issue para solução da mesma.

## Instalação
Instalação feita via Composer
```bash
composer require walternascimentobarroso/loterias-api
```

### Uso
Para acessar, basta instanciar uma das classes dos respectivos jogos disponíveis:

```php
$api = new \WalterNascimentoBarroso\LoteriasApi\Lotofacil();
$api = new \WalterNascimentoBarroso\LoteriasApi\Lotomania();
```

Por padrão, o biblioteca irá buscar os dados do último concurso da respectiva loteria. Caso deseja buscar os dados de um concurso específico, basta determinar qual concurso deseja no construtor da classe:

```php
$api = new \WalterNascimentoBarroso\LoteriasApi\Lotomania(2000);
```

Uma vez instanciada, a classe oferece os seguintes métodos:

> Os valores retornados irão mudar de loteria para loteria, respeitanto a natureza de cada um delas.

| Método | Descrição |
| ------ | ------ |
| ```$api->getResultado() ``` | Retorna o resultado da loteria (números sorteados, etc). |
| ```$api->getConcursoAnterior() ``` | Retorna o número do concurso anterior ao atual. Este valor poderá ser utilizado no construtor da classe para buscar os respectivos dados. |
| ```$api->getProximoConcurso() ``` | Retorna o número do próximo concurso ao atual. Este valor poderá ser utilizado no construtor da classe para buscar os respectivos dados. |
| ```$api->getData() ``` | Retorna a data de realização do sorteio. |
| ```$api->getDataProximoConcurso() ``` | Retorna a data do próximo sorteio. |
| ```$api->acumulado() ``` | Indica se o prêmio foi acumulado ou não. |
| ```$api->getPremioAcumulado() ``` | Retorna o valor acumulado do prêmio. |
| ```$api->getCidade() ``` | Indica a cidade de realização do sorteio. |
| ```$api->getUf() ``` | Indica o estado de realização do sorteio. |
| ```$api->getValorEstimado() ``` | Indica o valor estimado da premiação do próximo sorteio. |