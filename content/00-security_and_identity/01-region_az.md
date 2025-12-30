# Region, Availability Zone (AZ) e Edge Locations

## Region

É uma localização física onde estão os data centers que hospedam os serviços
da AWS.  
Cada region é fisicamente isolada das outras, o que fornece resiliência a
falhas em larga escala.  

Há regions na América do Norte, América do Sul, Europa, Oriente Médio, África e
Ásia-Pacífico.

Cada region contém várias _availability zones_ (AZs).

Exemplos de regions:

- `sa-east-1` (São Paulo, Brasil);
- `us-east-1` (Virgínia do Norte, EUA).

### Importância de uma region

- **Latência**: escolher uma region próxima dos usuários reduz o tempo de
  resposta;
- **Compliance**: algumas empresas precisam manter dados dentro de certos
  países ou regiões;
- **Custo**: os preços dos serviços variam entre regions;
- **Disponibilidade de serviços**: nem todos os serviços existem em todas as
  regions.

## Availability Zone (AZ)

É o agrupamento de um ou mais data centers distintos, com energia, rede e
conectividade redundantes e independentes, dentro de uma region.  

Dentro de uma region, as AZs são conectadas entre si por redes redundantes, de
alta velocidade e baixa latência.

Por exemplo, a region `us-east-1` pode ter as seguintes AZs:

- `us-east-1a`;
- `us-east-1b`;
- `us-east-1c`.

### Características de uma AZ

- No geral, uma region tem duas ou mais AZs, porém algumas têm mais;
- Cada AZ é fisicamente separada das outras, muitas vezes por vários km;
- Falhas em uma AZ não devem afetar as demais;
- As AZs dentro de uma region são interconectadas por links de baixa latência.

## Edge Locations

São pontos de presença (**PoPs – Points of Presence**) distribuídos globalmente,
localizados próximos aos usuários finais.  

As *edge locations* **não hospedam aplicações completas ou bancos de dados**;
elas são usadas principalmente para **cache e entrega de conteúdo**.

Serviços que utilizam edge locations:

- **Amazon CloudFront** (CDN);
- **AWS Route 53** (DNS);
- **AWS Shield e WAF**;
- **Lambda@Edge**.

### Para que servem as Edge Locations?

- Reduzir a latência para usuários finais;
- Entregar conteúdo estático e dinâmico de forma mais rápida;
- Absorver picos de tráfego e ataques DDoS;
- Melhorar a experiência do usuário sem necessidade de múltiplas regions.

Um usuário no Brasil, por exemplo, pode acessar conteúdo servido por uma
edge location em São Paulo, mesmo que a aplicação esteja hospedada na
region `us-east-1`.

### Características das Edge Locations

- Estão distribuídas em dezenas de países;
- São muito mais numerosas do que regions;
- Não substituem regions ou AZs;
- Trabalham em conjunto com regions, não de forma independente.

## Regions, AZs e Edge Locations: resumo

### Diferenças

| Conceito            | Region                         | Availability Zone             | Edge Location                   |
|---------------------|--------------------------------|-------------------------------|----------------------------------|
| **O que é?**        | Área geográfica ampla          | Data center (ou grupo deles)  | Ponto de presença (PoP)          |
| **Função principal**| Hospedar serviços              | Alta disponibilidade          | Cache e entrega de conteúdo     |
| **Isolamento**      | Entre regiões                  | Dentro da mesma region        | Global, próximo ao usuário      |
| **Latência**        | Alta entre regions             | Baixa entre AZs               | Mínima para o usuário final     |
| **Exemplo de uso**  | EC2, RDS, EKS                  | Multi-AZ                      | CloudFront, Route 53             |

### Boas práticas

- Usar múltiplas AZs para alta disponibilidade (por exemplo, EC2 em AZs
  diferentes);
- Utilizar múltiplas regions apenas quando houver necessidade de
  resiliência global, latência internacional ou *compliance*;
- Usar CloudFront e edge locations para melhorar desempenho global;
- Lembrar que S3, RDS, ELB e outros serviços já oferecem integração nativa
  entre múltiplas AZs.
