+++
title = "PRINCÍPIOS DE CHAOS ENGINEERING"
date = 2020-01-28T16:25:57+02:00
draft = false
+++

# PRINCÍPIOS DE CHAOS ENGINEERING
Última atualização: Maio 2018 (Traduzido em Julho 2018)

*Chaos Engineering é a disciplina de realizar experimentos sobre sistemas com o intuito de construir confiança com relação a capacidade de um sistema suportar condições adversas em produção.*

Avanços em sistemas de software distribuídos de larga escala estão revolucionando a engenharia de software. Como indústria, nós somos rápidos para adotar práticas que aumentam a flexibilidade do desenvolvimento e a velocidade das entregas em produção (deploys). Uma pergunta crítica surge junto com estes benefícios: Quanta confiança conseguimos ter nos sistemas complexos que nós colocamos em produção?

Mesmo quando cada um dos serviços que compõem um sistema distribuído estão funcionando adequadamente, as interações entre esses serviços podem causar resultados imprevisíveis. Estas consequências, são compostas por combinações raras de eventos reais que afetam os ambientes de produção, tornando esses sistemas distribuídos inerentemente caóticos.

Nós precisamos identificar fraquezas antes que elas ocorram por meio de comportamentos anômalos em todo o sistema. Falhas sistêmicas podem se manifestar por meio de: configurações inadequadas de fallback (opções de contingência) quando um serviço não está disponível; uma chuva de tentativas causadas por timeouts mal configurados; interrupções quando uma dependência downstream recebe muito mais tráfego do que o esperado; Falhas cascateadas quando um único ponto de falha para de funcionar; etc..  Nós devemos abordar as fraquezas mais relevantes dos nossos sistemas distribuídos de forma proativa, antes que afetem nossos clientes em produção. Precisamos de uma maneira de gerenciar o caos inerente a esses sistemas, aproveitando o aumento da flexibilidade e velocidade e ter a confiança em nossos sistemas de produção, independentemente da complexidade que elas representam.

Uma abordagem empírica, baseada em sistemas endereça o caos em sistemas distribuídos em escala e gera confiança na capacidade desses sistemas de resistir a condições reais. Nós aprendemos sobre o comportamento de um sistema distribuído observando-o durante um experimento controlado. Nós chamamos isso de *Chaos Engineering (Engenharia do Caos)*.

## CHAOS NA PRÁTICA

Para abordar a incerteza inerente aos sistemas distribuídos em escala, Chaos Engineering (Engenharia do Caos) pode ser pensada como a condução de experimentos para descobrir fraquezas sistêmicas. Estes experimentos seguem quatro etapas:

1. Comece definindo o que significa "sistema estável", uma medida que tem como resultado mensurável um indicativo sobre o comportamento normal do sistema.
2. Crie hipóteses este estado "sistema estável" permanecerá tanto no grupo de controle quanto no grupo onde o experimento será executado.
3. Introduza variáveis que reflitam eventos que ocorrem no mundo real, como por exemplo: servidores que travam, discos rígidos defeituosos, conexões de rede que são interrompidas, etc.
4. Tente refutar cada hipótese procurando diferenças entre o "sistema estável", o grupo de controle e o grupo experimental.

Quanto mais difícil for causar impactos no "sistema estável", mais confiança teremos no comportamento normal do sistema. Se uma fraqueza ou falha for descoberta, teremos uma nova meta de melhoria antes que esse comportamento se manifeste no sistema como um todo em produção.

## PRINCÍPIOS AVANÇADOS

Os seguintes princípios descrevem uma aplicação ideal de Chaos Engineering (Engenharia do Caos), aplicando os processos de experimentação descritos acima. Seguir os princípios correlaciona-se fortemente com a confiança que podemos ter em um sistema distribuído em escala.

### Construa uma hipótese em torno do comportamento do "sistema estável"

Foque na saída mensurável de um sistema, em vez de focar em atributos internos do sistema. As medições dessa saída em um curto período de tempo representam um caminho para se ter um "sistema estável". A vazão geral do sistema, as taxas de erro, os percentis de latência, etc., todas podem ser métricas de interesse que representam o comportamento do "sistema estável". Ao focar nos padrões de comportamento sistêmico durante os experimentos, o Chaos (Caos) verifica se o sistema funciona, em vez de tentar validar como ele funciona.

### Modifique variáveis de eventos reais

As variáveis do chaos (caos) são observadas por meio de eventos que ocorrem no mundo real. Priorize eventos por possível impacto ou frequência de ocorrência. Considere eventos que estão relacionados a: falhas de hardware, paradas de servidores, falhas de software, respostas malformadas, e também eventos que não são de falha, como um pico de tráfego ou um evento que envolva redimensionamento de capacidade. Qualquer evento capaz de gerar interrupções em um "sistema estável" tem potencial para ser variáveis de um experimento do Chaos (Caos).

### Execute experimentos em produção

Sistemas se comportam de maneira diferente dependendo do ambiente e dos padrões de tráfego. Como o comportamento da utilização pode mudar a qualquer momento, gerar amostras reais do tráfego é a única maneira de capturar de forma confiável o caminho da solicitação (request). Para garantir a autenticidade da forma como o sistema é utilizado e a relevância para o atual sistema implantado em produção, Chaos (Caos) dá preferência a experimentos realizados diretamente por meio de tráfego de produção controlado.

### Automatize Experimentos para Execução Contínua

A execução manual de experimentos é trabalhosa e, em última instância, insustentável. Automatize as experiências e execute-as continuamente. Chaos Engineering constrói automações nos sistemas para orientar a orquestração e a análise dos experimentos.

### Minimizar o Impacto

Experimentação em produção tem o potencial de causar impactos desnecessários aos clientes finais. Embora deva existir um planejamento para eventuais impactos negativos de curta duração, é responsabilidade e obrigação do Engenheiro do Caos garantir que as consequências dos experimentos sejam minimizados, controlados e contidos.

Chaos Engineering é uma prática poderosa que já está mudando a forma como o software é projetado e desenvolvido em algumas das maiores operações de TI em escala mundial. Enquanto outras práticas abordam velocidade e flexibilidade, o Caos aborda especificamente a incerteza sistêmica nesses sistemas distribuídos. Os Princípios do Caos oferecem confiança para inovar rapidamente em larga escala e proporciona aos clientes as experiências de alta qualidade que eles merecem.

Junte-se às discussões em andamento sobre os Princípios do Chaos Engineering e sua aplicação no [Chaos Community](https://groups.google.com/forum/#!forum/chaos-community).
