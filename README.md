# Sre-Challenge
## _A Stack para fim a fim para sua aplicação_



[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

A Stack relacionada a este projeto tem como objetivo a monitoração e observação 360º da sua aplicação, usando diversas tecnologias open-source líderes do mercado.

Foi utilizada a abordagem de containerização para um melhor uso, entendimento, facilidade e manutenção. Nele estão dos seguintes containers rodando com base no docker-compose

## Serviços

- Aplicação de clientes utilizando Python com Framework Django, incluindo módulo de envio de dados ao prometheus (App já containerizada)
- Prometheus
- Grafana
- AlertManager
- Jaeger*

Legenda: * Solução no ar, porém ainda não integrada


## PreReqs

Para executar a stack completa, você precisará dos seguintes componentes em seu host local:

- [Docker] - Como engine de execução de containers
- [Docker-Compose] - Ferramenta de definição e execução multi-container
- [Github] - Projeto no github baixado localmente.


## How to run

Baixe os arquivos do repositório para sua máquina local

```sh
git clone git@github.com:felipeyajima/yajima-sre.git
```

Ao baixar os arquivos, entre no diretório do projeto e inclua permissões específicas na pasta 'data', para que o grafana funcione corretamente

```sh
cd yajima-sre
sudo chown -R 472:472 data
```

E por fim, execute o comando para executar os containers do compose
```sh
docker-compose up
```


## Uso do sistema de clientes

Para o correto uso do sistema de clientes, recomendamos a leitura do projeto pai, localizado na [Documentacao-do-sistema] localizado no github do desenvolvedor (Seção: Dados da aplicação)
Com a inclusão do módulo do prometheus no sistema, uma nova página foi incluida no software, o /metrics. Esta página exibe diversas informações adicionais que serão utilizadas pelo Prometheus e Grafana


Abaixo estão os serviços disponibilizados nesta stack de observabilidade
| Serviço | Porta | Metrics | 
| ------ | ------ | ------ | 
| Sistema Cliente | localhost:3000 | /metrics| 
| Prometheus | localhost:9090 | /metrics | 
| Grafana | localhost:3000 | | 
| Alertmanager | localhost:9093 | | 
| Jaeger | localhost:6831udp  e localhost:16686 | |


## Visualização dos dashboards

Para visualizar os dashboards previamente criados, basta acessar o endereço do container onde está sendo executado o grafana. Utilizar os dados abaixo

http://localhost:3000
| Login | Senha |
| ------ | ------ |
| admin | 123456| 




   [Docker-Compose]: <https://docs.docker.com/compose/>
   [Docker]: <https://www.docker.com/>
   [Github]: <https://github.com/felipeyajima/yajima-sre>
   [Documentacao-do-sistema]: <https://github.com/itidigital/sre-challenge>

