# AWS VPC - Virtual Private Cloud

É uma rede virtual logicamente isolada na nuvem da Amazon.  
Funciona como se fosse uma rede tradicional de datacenter, mas com a vantagem
de ser definida por software totalmente personalizável.  

## Principais pontos sobre o AWS VPC
- **Isolamento**: cada VPC é isolada das demais por padrão;
- **Endereçamento**: pode-se definir o espaço de endereços IP usando CIDR blocks (e. g.: 10.0.0.0/8);
- **Subnets**: a VPC é dividida em sub-redes (públicas e privadas);
- **Gateways**: permite conectividade externa via **Internet Gateway**, **NAT Gateway**, **VPN Gateway** ou **AWS Direct Connect**;
- **Roteamento**: controle de tráfego via _route tables_ e ACLs;
- **Segurança**: uso de **Security Groups** (firewall em nível de instância) e **Network ACL** (em nível de subnet);
- **Integração**: suporta peering entre VPCs e **Transit Gateway** para interconectar múltiplas redes.

## Principais recursos

| Recurso                | Função                                                                 | Exemplo de uso                                                                 |
|-------------------------|------------------------------------------------------------------------|--------------------------------------------------------------------------------|
| **CIDR Block**          | Define o intervalo de endereços IP da rede.                            | Usar `10.0.0.0/16` para suportar até ~65k IPs internos.                        |
| **Subnets**             | Segmentos da VPC (podem ser públicas ou privadas).                     | Subnet pública para servidores web; subnet privada para banco de dados.        |
| **Route Tables**        | Regras de roteamento do tráfego.                                       | Subnet pública com rota para Internet Gateway; privada com rota para NAT.      |
| **Internet Gateway (IGW)** | Permite tráfego entre VPC e internet.                              | Instâncias EC2 públicas acessíveis via IP elástico.                            |
| **NAT Gateway**         | Dá saída à internet para instâncias privadas sem expor seus IPs.       | Banco de dados em subnet privada acessando updates de pacotes.                 |
| **VPC Peering**         | Conecta VPCs diferentes.                                               | Compartilhar dados entre duas VPCs em regiões diferentes.                       |
| **Transit Gateway**     | Conecta múltiplas VPCs e redes on-premises.                            | Grande empresa conectando dezenas de VPCs e VPNs a uma rede centralizada.      |
| **Security Groups**     | Firewall em nível de instância (stateful).                             | Permitir tráfego HTTP (porta 80) e SSH (porta 22) apenas de IPs específicos.   |
| **Network ACLs (NACLs)**| Firewall em nível de subnet (stateless).                               | Bloquear tráfego de uma faixa de IP maliciosa em toda a subnet.                |

