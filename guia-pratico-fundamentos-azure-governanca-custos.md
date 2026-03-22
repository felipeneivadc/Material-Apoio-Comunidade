# Guia Prático - Fundamentos de Microsoft Azure, Governança e Custos

## Objetivo
Este guia resume, de forma prática, os principais conceitos apresentados no módulo sobre Azure, com foco em:
- visão geral da plataforma
- arquitetura conceitual
- governança
- contratação
- precificação
- boas práticas de estimativa de custos

---

## 1. O que é o Microsoft Azure
O Microsoft Azure é a plataforma de nuvem da Microsoft para criar, hospedar, gerenciar e escalar aplicações, dados, redes, segurança, analytics e soluções de IA.

### Na prática
O Azure permite que empresas:
- executem aplicações sem manter toda a infraestrutura física
- escalem recursos sob demanda
- adotem cenários híbridos e multinuvem
- integrem segurança, identidade e governança desde o início

### Links oficiais
- [Visão geral do Azure](https://azure.microsoft.com/pt-br/explore/)
- [Catálogo de produtos do Azure](https://azure.microsoft.com/en-us/products)

---

## 2. Regiões e disponibilidade

### Regiões (Regions)
Uma região do Azure é um conjunto de datacenters implantados dentro de uma área geográfica específica.

### Por que isso importa
A escolha da região afeta:
- latência
- residência de dados
- disponibilidade de serviços
- estratégia de continuidade de negócio
- custo em alguns cenários

### Boas práticas
- escolha a região mais próxima dos usuários ou sistemas consumidores
- valide se o serviço desejado está disponível naquela região
- considere requisitos regulatórios e de residência de dados
- planeje disaster recovery com região pareada quando fizer sentido

### Links oficiais
- [O que são regiões do Azure](https://learn.microsoft.com/pt-br/azure/reliability/regions-overview)
- [Lista de regiões do Azure](https://learn.microsoft.com/pt-br/azure/reliability/regions-list)
- [Regiões pareadas do Azure](https://learn.microsoft.com/en-us/azure/reliability/regions-paired)

---

## 3. Zonas de disponibilidade

### O que são
Zonas de disponibilidade são grupos fisicamente separados de datacenters dentro de uma mesma região, com energia, refrigeração e rede independentes.

### Quando usar
Use zonas de disponibilidade quando o workload exigir:
- alta disponibilidade
- tolerância a falhas de datacenter
- maior resiliência para aplicações críticas

### Exemplo prático
Uma aplicação crítica pode ter:
- camada web na zona 1 e zona 2
- banco com redundância entre zonas
- balanceamento de carga distribuído entre zonas

### Links oficiais
- [Visão geral de Zonas de Disponibilidade](https://learn.microsoft.com/pt-br/azure/reliability/availability-zones-overview)
- [Estratégias arquiteturais com regiões e availability zones](https://learn.microsoft.com/en-us/azure/well-architected/design-guides/regions-availability-zones)

---

## 4. Hierarquia de governança no Azure

A organização lógica dos recursos no Azure normalmente segue esta estrutura:

`Management Groups > Subscriptions > Resource Groups > Resources`

### 4.1 Assinaturas (Subscriptions)
A assinatura define um limite administrativo e de cobrança.

**Use para:**
- separar ambientes (produção, homologação, desenvolvimento)
- separar centros de custo
- controlar acesso e billing

### 4.2 Grupos de Recursos (Resource Groups)
São contêineres lógicos usados para agrupar recursos relacionados.

**Use para:**
- organizar aplicações
- facilitar permissões
- simplificar automação
- controlar ciclo de vida de recursos

### 4.3 Recursos (Resources)
São os serviços efetivamente provisionados, como:
- Virtual Machines
- Storage Accounts
- Virtual Networks
- App Services
- SQL Databases
- Functions

### 4.4 Azure Resource Manager (ARM)
É a camada de gerenciamento do Azure para criar, atualizar, excluir e organizar recursos.

**Na prática:**
- controle de acesso com RBAC
- tags
- locks
- templates
- IaC com ARM/Bicep

### 4.5 Microsoft Entra ID
É a base de identidade e acesso da Microsoft para autenticação, SSO, controle de acesso e proteção de identidades.

### 4.6 Management Groups
Permitem governança em escala sobre múltiplas assinaturas.

**Use para:**
- aplicar políticas corporativas
- padronizar segurança
- organizar assinaturas por unidade de negócio, país ou criticidade

### Links oficiais
- [Azure Management Groups](https://learn.microsoft.com/pt-br/azure/governance/management-groups/overview)
- [Azure Resource Manager](https://learn.microsoft.com/pt-br/azure/azure-resource-manager/management/overview)
- [Documentação do Microsoft Entra ID](https://learn.microsoft.com/en-us/entra/identity/)
- [Documentação do Azure Resource Manager](https://learn.microsoft.com/en-us/azure/azure-resource-manager/)

---

## 5. Mudança de CapEx para OpEx

### Conceito
Na nuvem, o modelo deixa de depender apenas de investimento inicial em ativos físicos (CapEx) e passa a privilegiar consumo contínuo e flexível (OpEx).

### Impacto prático
Antes:
- compra antecipada de servidores
- capacidade ociosa
- expansão lenta

Na nuvem:
- pagamento conforme uso
- elasticidade
- ajuste mais rápido à demanda
- redução de barreiras para experimentação

### Link oficial
- [Eficiência de custo no Cloud Adoption Framework](https://learn.microsoft.com/pt-br/azure/cloud-adoption-framework/strategy/inform/cost-efficiency)

---

## 6. FinOps no Azure

### O que é
FinOps é a disciplina que une tecnologia, finanças e negócio para maximizar o valor da nuvem.

### FinOps na prática
Não é só reduzir custo. É buscar o melhor equilíbrio entre:
- custo
- desempenho
- confiabilidade
- velocidade
- valor para o negócio

### Ações práticas de FinOps
- monitorar consumo continuamente
- usar tags para rateio
- desligar recursos ociosos
- escolher SKUs corretas
- revisar arquitetura periodicamente
- avaliar reservas e savings plans
- acompanhar custo real vs. orçamento

### Links oficiais
- [FinOps Framework overview](https://learn.microsoft.com/en-us/cloud-computing/finops/framework/finops-framework)
- [FinOps e eficiência de custo no Azure](https://learn.microsoft.com/pt-br/azure/cloud-adoption-framework/strategy/inform/cost-efficiency)
- [Azure Pricing](https://azure.microsoft.com/pt-br/pricing)

---

## 7. Modelos de contratação do Azure

A forma de contratação impacta governança, suporte, faturamento e oportunidades de economia.

### Principais modelos citados
- Pay-As-You-Go (PAYG)
- Cloud Solution Provider (CSP)
- Microsoft Customer Agreement (MCA)
- Enterprise Agreement (EA) / MCA-E

### Resumo prático
**PAYG**
- bom para início rápido, labs e pequenos ambientes
- cobrança por consumo

**CSP**
- indicado quando a empresa quer comprar via parceiro
- pode simplificar gestão comercial e suporte

**MCA**
- contratação direta com a Microsoft
- comum em organizações com maior maturidade

**EA / MCA-E**
- mais aderente a estruturas corporativas maiores e compromissos mais robustos

### Link oficial
- [Flexible Purchasing Options for Azure](https://azure.microsoft.com/en-us/pricing/purchase-options)
- [Azure account / Pay as you go](https://azure.microsoft.com/en-us/pricing/purchase-options/azure-account)
- [Offer details](https://azure.microsoft.com/support/legal/offer-details)

---

## 8. Fatores que impactam o custo no Azure

Os custos variam conforme diversos fatores, principalmente:

- tipo de recurso
- SKU
- região
- tempo de uso
- armazenamento
- transferência de dados
- arquitetura de alta disponibilidade
- licenciamento
- redundância
- tráfego de saída (egress)

### Regra prática
Nunca estime custo apenas pelo nome do serviço. Sempre valide:
- tier/SKU
- região
- volume
- horas
- redundância
- banda
- dependências do desenho

---

## 9. Ferramentas para estimativa de custos

### 9.1 Azure Pricing Calculator
Usada para simular o custo de serviços e cenários.

- ideal para pré-venda
- estimativa inicial
- comparação de SKUs
- desenho de arquitetura

**Link oficial**
- [Azure Pricing Calculator](https://azure.microsoft.com/pt-br/pricing/calculator/)

### 9.2 Azure Pricing
Página oficial com visão de preços e opções de economia.

**Link oficial**
- [Visão geral de preços do Azure](https://azure.microsoft.com/pt-br/pricing)

### 9.3 Azure TCO Calculator
Ajuda a comparar custo de ambiente on-premises versus Azure.

**Link oficial**
- [Azure TCO Calculator](https://azure.microsoft.com/en-us/pricing/tco/calculator/)

### 9.4 Azure Migrate
Útil para assessment e apoio à estimativa durante migrações.

**Link oficial**
- [Azure Migrate](https://learn.microsoft.com/en-us/azure/migrate/migrate-services-overview)

### 9.5 Azure Cost Management
Ferramenta para acompanhar consumo, orçamento e análise de custos após implantação.

**Link oficial**
- [Azure Cost Management + Billing](https://learn.microsoft.com/en-us/azure/cost-management-billing/)

---

## 10. Como estimar custos na prática

### Passo a passo
1. Defina o cenário de negócio
   - qual aplicação ou workload será implantado?

2. Liste os recursos necessários
   - compute
   - storage
   - banco
   - rede
   - monitoramento
   - backup
   - segurança

3. Escolha a região
   - considerando latência, compliance e disponibilidade

4. Defina SKU e capacidade
   - tamanho da VM
   - volume de armazenamento
   - throughput
   - redundância

5. Estime uso mensal
   - horas ligadas
   - GB armazenados
   - transações
   - tráfego de saída

6. Considere custos indiretos
   - monitoramento
   - logs
   - backup
   - disaster recovery
   - licenças

7. Avalie economia
   - Reserved Instances
   - Savings Plans
   - Azure Hybrid Benefit
   - desligamento programado

8. Revise com base em arquitetura e operação
   - ambiente produtivo quase sempre custa mais do que a primeira simulação

---

## 11. Checklist rápido de arquitetura e custo

### Arquitetura
- [ ] Região correta escolhida
- [ ] Necessidade de availability zones validada
- [ ] Separação por subscription definida
- [ ] Resource groups organizados por contexto
- [ ] Identidade e acesso desenhados com Entra ID
- [ ] Governança em escala considerada com management groups

### Custos
- [ ] SKU correta definida
- [ ] Região validada na calculadora
- [ ] Horas de uso estimadas corretamente
- [ ] Egress considerado
- [ ] Backup e observabilidade incluídos
- [ ] Estratégias de savings avaliadas
- [ ] Orçamento e monitoramento planejados

---

## 12. Principais aprendizados do módulo
- Azure não é apenas infraestrutura; é uma plataforma completa de nuvem
- região e zona impactam disponibilidade, latência e compliance
- governança começa na hierarquia correta
- custos dependem tanto do desenho técnico quanto do modelo de contratação
- FinOps deve ser contínuo, não um evento pontual
- estimativa bem feita exige contexto de negócio, arquitetura e operação

---

## 13. Próximos passos recomendados
- praticar criação de estimativas reais na Pricing Calculator
- comparar duas arquiteturas com e sem availability zones
- estruturar um padrão de subscriptions e resource groups
- definir tags de custo e ownership
- criar um modelo base de governança para projetos Azure
