# Region e availability zone (AZ)

## Region

É uma localização física onde estão os data centers, que tem os servidores que
hospedam todos seus serviços.  
Cada região é fisicamente isolada das outras, o que fornece rreiliência a
falhas em larga escala.  
Há regiões na América do Norte, América do Sul, Oriente Médio, África e
Ásia-Pacífico.

Cada região contém várias _availability zones_.

Exemplos de regiões:

- `sa-east-1` (São Paulo, Brasil);
- `us-east-1` (Virgínia do Norte, EUA).

### Importância de uma region

- **Latência**: Escolher uma region próxima dos seus usuários reduz o tempo
  de resposta;
- **Compliance**: Algumas empresas preciam manter dados dentro de certos
  países;
- **Custo**: Os preços de serviços variam entre regions.

## Availability zone (AZ)

É o agrupamento de um ou mais data centers distintos, com energia, rede e
conectividade redundantes e independentes dentro de uma region.  
Dentro de uma region as AZs estão conectas entre entre elas através de redes
redundantes, de  alta velocidade e de baixa latência.


Por exemplo, a region `us-east-1` pode ter as seguintes AZs:

- `us-east-1a`;
- `us-east-1b`;
- `us-east-1c`.

### Características de uma AZ

- No geral, uma region tem duas ou mais AZs, porém algumas tem mais;
- Cada AZ é fisicamente separada das outras, muitas vezes por vários km;
- As AZs dentro de uma region são interconectadas por links de baixa
  latência.

## Regions e AZs: resumo

### Diferenças

| Conceito            | Região                           | Zona de Disponibilidade       |
|---------------------|----------------------------------|-------------------------------|
| **O que é?**        | Localização geográfica ampla     | Data center (ou grupo deles)  |
| **Isolamento**      | Entre países/continentes         | Dentro da mesma região        |
| **Latência**        | Alta entre regiões               | Baixa entre AZs               |
| **Redundância**     | Alta                             | Alta, mas dentro da região    |


### Boas práticas

- Usar múltiplas AZs para alta disponibilidade: por exemplo, rodar instâncias
  EC2 em AZs diferentes;
- Só utilizar múltiplas regions somente se for necessário ter resiliência
  global devido à questão da latência ou *compliance* legal;
- S3, RDS, ELB e outros já suportam integração entre múltiplas AZs.  

