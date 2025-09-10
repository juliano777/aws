# AWS Auto Scaling

## O que é
O **AWS Auto Scaling** é um serviço que monitora aplicações e ajusta automaticamente a capacidade de recursos (como instâncias EC2, ECS, DynamoDB ou Aurora) para manter o desempenho ao menor custo possível.  

Ele ajuda a escalar **horizontalmente** (adicionando/removendo instâncias) e **verticalmente** (aumentando/diminuindo capacidade), garantindo que os recursos acompanhem a demanda.



## Recursos principais

| Recurso | Descrição |
|---------|------------|
| **Dynamic Scaling** | Ajusta automaticamente a capacidade com base em métricas em tempo real (ex: CPU, memória, throughput). |
| **Predictive Scaling** | Usa machine learning para prever a demanda futura e ajustar a capacidade antecipadamente. |
| **Scheduled Scaling** | Permite definir horários específicos para aumentar/diminuir a capacidade (ex: horário comercial). |
| **Target Tracking** | Escala recursos para manter uma métrica em um valor alvo (ex: manter CPU média em 50%). |
| **Step Scaling** | Ajusta a capacidade em etapas, com base em limites definidos (ex: +2 instâncias se CPU > 70%). |
| **Instance Refresh** | Atualiza instâncias automaticamente para aplicar patches ou mudanças de configuração. |
| **Integration com ALB/ELB** | Distribui tráfego automaticamente entre instâncias em escalabilidade. |



## Benefícios

- **Custo-eficiência**: paga apenas pelo que usa.  
- **Alta disponibilidade**: mantém a aplicação estável mesmo em picos de demanda.  
- **Flexibilidade**: combina diferentes estratégias de escalabilidade.  
- **Integração nativa** com serviços como EC2, ECS, DynamoDB e Aurora.  



## Casos de uso

- Aplicações web com tráfego variável.  
- Processamento de workloads sazonais (ex: e-commerce em Black Friday).  
- Ajuste automático de capacidade de banco de dados.  
- Ambientes com workloads imprevisíveis.  



## Comparação: AWS Auto Scaling vs EC2 Auto Scaling

| Característica | **AWS Auto Scaling** | **EC2 Auto Scaling** |
|----------------|-----------------------|-----------------------|
| **Escopo** | Gerencia a escalabilidade de múltiplos serviços (EC2, ECS, DynamoDB, Aurora). | Focado apenas em instâncias EC2. |
| **Interface** | Painel centralizado para políticas de escalabilidade de diferentes serviços. | Gerenciamento dentro do EC2 Auto Scaling Groups (ASG). |
| **Flexibilidade** | Oferece escalabilidade dinâmica, preditiva e agendada para diversos recursos. | Apenas escalabilidade dinâmica e agendada para EC2. |
| **Machine Learning** | Suporta **Predictive Scaling** com base em padrões de uso. | Não possui escalabilidade preditiva. |
| **Recomendado para** | Workloads que usam múltiplos serviços AWS e precisam de visão unificada. | Workloads baseados exclusivamente em EC2. |
