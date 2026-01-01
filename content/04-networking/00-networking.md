# AWS networking

A rede da AWS (AWS Networking) é o conjunto de serviços que permite criar,
gerenciar e escalar a conectividade dentre recursos na AWS, na INternet e em
_data centers on-premises_.  
Esses serviços são essenciais para isolar aplicações, controlar tráfego,
otimizar e garantir segurança.

## Principais conceitos

- **Regiões e zonas de disponibilidade (AZs)**. 
    - **Região**: área geográfica que contém várias AZs;
    - **AZ (Availability Zone)**: _data centers_ isolados dentro da região.

- **VPC (Virtual Private Cloud)**. 
    - Rede virtual isolada dentro da AWS;
    - Permite criar sub-redes públicas privadas.

- **Subnets**. 
    - Partições da VPC para organizar recursos;
    - IPs reservados de subnets  
      Supondo uma subnet de CIDR `10.0.0.0/24`:  
      - `10.0.0.0`: endereço de rede;  
      - `10.0.0.1`: roteador VPC (_VPC router_);  
      - `10.0.0.2`: servidor DNS VPC;  
      - `10.0.0.3`: uso futuro;
      - `10.0.0.255`: endereço de _broadcast_.
    - Subnets públicas: têm rota para a internet via `Internet Gateway`.  
      Requer endereços IPs que sejam resolvíveis publicamente;  
    - Subnets privadas: **não** têm rota direta para a internet. 
      Precisa de um dispositivo NAT para isso.
      Utiliza endereços IPs privados. 

- **Roteamento**. 
    - Tabelas de notas definem para onde o tráfego vai.

- **Security groups e NACLs**. 
    - Controles de segurança para instâncias e sub-redes.    

## Serviços de networking na AWS

| Serviço                   | Descrição                                                                 |
|---------------------------|---------------------------------------------------------------------------|
| **Amazon VPC**           | Criação e gerenciamento de redes privadas virtuais dentro da AWS.         |
| **Elastic IP**           | Endereço IP público fixo associado a uma instância EC2.                  |
| **Elastic Load Balancer**| Distribui automaticamente o tráfego entre múltiplas instâncias.           |
| **AWS Direct Connect**   | Conexão dedicada entre data centers on-premises e a AWS.                  |
| **AWS Transit Gateway**  | Interconecta múltiplas VPCs e redes on-premises de forma centralizada.    |
| **AWS PrivateLink**      | Conecta serviços de forma privada sem uso da internet pública.            |
| **Amazon Route 53**      | Serviço de DNS gerenciado e roteamento global de tráfego.                 |
| **AWS Global Accelerator**| Otimiza roteamento global, reduzindo latência para aplicativos.           |
| **Amazon CloudFront**    | Rede de distribuição de conteúdo (CDN) para baixa latência e alta escala. |
| **AWS VPN**              | Conexão criptografada entre redes on-premises e VPC na AWS.              |


## Principais recursos na Amazon VPC

- **CIDR blocks**: define o espaço de IP.
- **Subnets públicas e privadas**:
    - **Pública**: acessível via Internet Gateway;
    - **Privada**: acessível via NAT gateway.
- **Internet Gateway (IGW)**: permite o acesso à Internet.
- **NAT Gateway**: acesso à internet para instâncias privadas.
- **Peering de VPCs**: conecta VPCs diferentes.
- **Transit Gateway**: conecta múltiplas VPCs e redes.
