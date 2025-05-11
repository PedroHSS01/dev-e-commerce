# Sistema de E-commerce Escalável e Seguro

## Visão Geral
Este projeto visa desenvolver um sistema de e-commerce escalável e seguro para a ShopOnline, uma varejista digital que enfrenta desafios operacionais devido ao rápido crescimento. O sistema foi projetado para melhorar a experiência do usuário, garantir alta disponibilidade durante picos de acesso e assegurar a consistência de dados em operações críticas, como estoque e pagamentos.

## Funcionalidades Principais
- **Gerenciamento de Clientes**: Cadastro, login seguro, atualização e exclusão de contas.
- **Gerenciamento de Produtos**: Cadastro, busca e exibição de produtos.
- **Carrinho de Compras**: Adição, remoção e ajuste de quantidades de produtos, finalização de compra.
- **Pedidos e Pagamentos**: Vinculação de pedidos a processos de pagamento, rastreamento de status.

## Tecnologias Utilizadas
- **Banco de Dados**: MySQL para modelagem e armazenamento de dados.
- **Backend**: Linguagens orientadas a objetos para modularidade e manutenibilidade.
- **Infraestrutura**: 
  - Nuvem híbrida (pública para front-end e privada para dados sensíveis).
  - Kubernetes e Docker para orquestração de containers e escalabilidade horizontal.
  - Redis para gerenciamento de sessões e Elasticsearch para buscas eficientes.
- **Segurança**: 
  - Web Application Firewall (WAF) para proteção contra ataques.
  - Autenticação com OAuth 2.0, JWT e MFA (Autenticação Multifator).

## Diagrama de Classes
O sistema foi modelado utilizando um diagrama de classes que inclui as seguintes entidades principais:
- **Cliente**: Gerencia dados pessoais e autenticação.
- **CarrinhoDeCompras**: Gerencia itens adicionados pelo cliente.
- **Produto**: Armazena informações sobre os produtos disponíveis.
- **Pedido**: Registra os pedidos dos clientes.
- **Pagamento**: Processa e registra transações financeiras.

Relacionamentos:
- Cliente ↔ CarrinhoDeCompras (1:1).
- CarrinhoDeCompras ↔ ItemCarrinho (1:N).
- Pedido ↔ Pagamento (1:1).
- Cliente ↔ Pedido (1:N).

## Modelagem de Dados
O banco de dados foi projetado no MySQL Workbench, com tabelas fundamentais:
- **Usuários**: Dados dos clientes.
- **Produtos**: Informações dos produtos.
- **Pedidos**: Registro de pedidos.
- **Pagamentos**: Transações financeiras.
- **ItensPedido**: Relacionamento entre pedidos e produtos.

## Infraestrutura
A infraestrutura foi simulada no Cisco Packet Tracer, seguindo a topologia:
```
Cliente → Roteador (balanceador) → Firewall (ASA 5506-X) → Servidor Web
```
Princípios adotados:
- **Escalabilidade Horizontal**: Uso de containers Docker e Kubernetes.
- **Alta Disponibilidade**: Replicação de bancos de dados e balanceamento de carga.
- **Segurança**: Firewalls, WAF e proteção contra DDoS.

## Módulos do Sistema
| Módulo          | Responsabilidades                          | Tecnologias de Alta Disponibilidade      |
|-----------------|-------------------------------------------|------------------------------------------|
| Autenticação    | Login, OAuth 2.0, JWT, MFA                | Redis + Proteção contra DDoS             |
| Banco de Dados  | Transações, pedidos, estoque               | Replicação síncrona + Backups            |
| Pagamentos      | Integração com gateways                   | Processamento assíncrono                 |
| Catálogo        | Busca, filtros, recomendações             | Elasticsearch + CDN                      |
| Logística       | Rastreamento de pedidos                   | Filas SQS para retentativas              |

## Conclusão
O sistema desenvolvido para a ShopOnline integra arquitetura escalável, segurança robusta e modularidade, garantindo alta disponibilidade e conformidade com regulamentações. A solução está pronta para suportar o crescimento contínuo da plataforma, oferecendo uma experiência otimizada aos clientes e eficiência operacional.