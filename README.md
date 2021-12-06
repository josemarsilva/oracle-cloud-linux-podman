`oracle-cloud-linux-podman/README.md` - Evaluation laboratory for Oracle Cloud Linux - Always Free Eligible - with Oracle Linux and Podman installed

## 1. Introdução

Este repositório contém os artefatos do laboratório de avaliação  **oracle-cloud-linux-podman**  que consiste em:
* Avaliar os recursos e funcionalidades
* Explorar os recursos e funcionalidades

## 2. Documentação

### 2.1. Diagrama de Caso de Uso (Use Case Diagram)

![UseCaseDiagram-Context.png](./doc/uml-diagrams/UseCaseDiagram-Context.png) 


### 2.2. Diagrama de Implantação (Deploy Diagram)

![DeployDiagram-Context.png](./doc/uml-diagrams/DeployDiagram-Context.png) 


### 2.9. Glossário de Termos (Glossary)

De uma forma geral, vamos tentar <ins>definir</ins> e <ins>caracterizar</ins> alguns dos termos utilizados neste projeto para permitir uma melhor compreensão e entendimento:

| Termo       | Significado                     |
| :---------- | :------------------------------ |
| Compartment | É o agrupamento para organização lógica de permissões acessos e controle de custos. Equivale ao `project` do Google Cloud Platform ou `Resource Group` da AWS. |


## 3. Projeto

### 3.1. Pré-Requisitos, Pré-Condições e Premissas

#### a. Tecnologias e ferramentas

* Cloud infrastructure: OCI - Oracle Cloud Infrastructure
  * Compute Instance


#### b. Ferramental de apoio

* Ferramenta: [Draw.IO](https://app.diagrams.net/) (only for diagrams design and documentation)


### 3.2. Guia do Desenvolvedor e Administrador

* Faça um clone do projeto `git clone`. Use o _branch_ `master` se o _branch_ `develop` não estiver disponível
* Leia as documentações disponíves em "2. Documentação"  and "3.x. Design Patterns, Standard, Conventions and Best Practices"


### 3.3. Guia de Implantação, Configuração e Instalação

* *Step-01*: Logado no OCI - Oracle Cloud Infrastructure, na região desejada crie a instância com o shape *Always Free Eligible*, com a imagem do Oracle Linux 
  * No dashboard principal, escolha menu superior esquerdo `OCI :: Compute >> Instance` e clique `Create Instance`
    * No formulário `Create compute instance`, preencher os campos conforme abaixo, aceitando os defaults e expandindo as seções comprimidas:

| Seção / Campo         | Valor                           | Obs                             |
| :---------------      | :------------------------------ | :------------------------------ |
| Name                  | `oci-linux-podman`              |                                 |
| Create in compartment |                                 | aceitar defaults                |
| Placement             |                                 | aceitar defaults                |
| Image                 | Oracle Linux 8                  | clicar `Change image` para escolher |
| Shape / Instance Type | Virtual Machine                 |                                 |
| Shape / Shape Series  | Ampere                          |                                 |
| Shape / Shape Name    | VM.Standard.A1.Flex             |                                 |
| Shape / OCPU          | 1                               |                                 |
| Shape / Memory        | 6 GB                            |                                 |
| Network               |                                 | aceitar defaults                |
| Add SSH keys          |                                 |                                 |
| Boot volume           |                                 |                                 |


#### a. Criar Compute Instance Always Free Eligible Linux Oracle

#### b. Configurar regras de firewall acesso Security List 

#### c. Configurar regras de firewall no Linux da instância


### 3.4. Guia de Demonstração e Teste

* n/a


### 3.5. Guia de Estudo

* n/a

#### 3.5.1. Patterns, Standard, Conventions and Best Practices

* n/a

## I - Referências

* [Crie sua conta Always Free e use o Oracle Cloud Infrastructure sem pagar nada por isso](https://www.youtube.com/watch?v=dMkKeEHfoNs)
* [Oracle Cloud - Instance Gratuita com 4 vCPU 24 GB RAM | Podcast DBAOCM](https://www.youtube.com/watch?v=c5VrdzBdNPA)
* [O que você pode fazer gratuitamente no Oracle Cloud](https://www.youtube.com/watch?v=d-v9A-22Ui4)
  * `00:00` início, apresentação, agenda, etc
  * `11:00` QRCode para pedir um Trial de US$ 300,00 por 30 dias
  * `12:00` Oracle Always Free: 1. Infraestrutura; 2. banco de dados; 3. observabilidade e gerenciamento; 4. serviços adicionais: load balancer e data-transfer
  * `13:00` Composição média de 13 serviços: máquina virtuais, block volumes, banco de dados e monitoramento
  * `14:30` Máquinas separadas por processador: AMD, INTEL, ARM ou AMPERE
  * `14:45` Arquitetura Ampere até 24 GB memória RAM - viabiliza Kubernetes
  * `17:30` Pergunta respondida: "... always free, 1 instance, shape VM.Standard.A1.Flex) 4 OCPU e 24GB RAM será sempre gratuito mesmo após o Trial de 30 dias?". Resposta: "Sim"
  * `18:55` O que passar contabiliza 1 OCPU corresponde 2 VCPU da concorrência. A diferença é o isolamento do Core. Ideal para quem precisa de + de 4 VCPU's para seus testes
  * `20:10` Always free: NoSQL 20 GB  + 133 mi de leituras de registros
  * `20:50` Serviço de log da Oracle, painel escalável com 10 GB para ingestão e pesquisa de log (substitui ELK, Kibana, Grafana)
  * `24:50` Log's criptografados em trânsito e em disco após armazenado
  * `25:30` Always free: Ferramenta de APM gratuita na nuvem
  * `26:30` Always free: Balanceador de carga (Load Balancer) na nuvem para você não precisar implementar com NGINX
  * `28:45` Always free: 10 TB de data-transfer (saindo)
  * `29:30` Always free: 36 regiões no mundo, no Brasil em Vinhedo e São Paulo. Não há diferença de custo por região
  * `31:30` Possibilidade de integração entre nuvens da Oracle e Microsoft
  * `33:30` Categorias de Load Balancer: de 10 MB/s até 8 GB/s. Também é possível contratar um "flex" dando mínimo e máximo.
  * `35:10` Cloud Native and Devops: que ferramentas tem
  * `41:05` Importante pensar em nuvem de forma agnóstica e ter opções
  * `42:34` Login Single-Signon(SSO) após cadastro do Always Free, iniciando brincadeira e dashboard inicial
  * `46:05` Acessando os serviços pelo menu hamburger superior esquerdo, criando uma VM instance: name, compartment(equivale a GPC Project ou AWS ResourceGroup, relaciona custos, segurança, etc), escolhendo o shape da VM = Always Free, escolhendo imagem do SO
  * `53:50` Imagem Oracle Linux Cloud Developer - stack empacotada com diversas ferramentas desenvolvimento: Ruby, Java, Python, .Net Core, Terraform
  * `57:30` Configurando infraestrutura de rede VCN, IP, subnet, etc
  * `1:00:15´ Configuração pode ser salva como recurso para ser gerenciado pelo Terraform ou Resource Manager (Oracle)
  * `1:03:15´ Acessando máquina criada para configurar as regras de firewall dentro da subnet. Default security list, input and output rules, ssh port, http port, etc
  * `1:08:40´ IP público precisa ser reservado, senão ele pode mudar

* Github README.md writing sintax
  * [Basic Github Markdown Writing Format](https://docs.github.com/pt/free-pro-team@latest/github/writing-on-github/basic-writing-and-formatting-syntax)  
  * [Github Mastering Markdown](https://guides.github.com/features/mastering-markdown/#what)
