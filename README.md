> ### 📊 Projeto Prático | Bootcamp de Análise de Dados — Generation Brasil
> 
> Este projeto conceitual foi desenvolvido como parte do ecossistema de aprendizagem do Bootcamp de Análise de Dados da **Generation Brasil**. A Inteligência Artificial (IA) foi utilizada como ferramenta de cocriação de ponta a ponta: desde o suporte analítico para a triagem de dados de telemetria e extração de insights estratégicos, até a redação do artigo técnico de cibersegurança e sua respectiva tradução e localização bilíngue (Português/Espanhol).

---
# NetGuard Pro: Diagnóstico de Performance e Otimização de Infraestrutura

Este documento apresenta, de forma simples e visual, a análise de dados e as decisões de engenharia que tomamos para criar a nova versão do **NetGuard Pro** (um aplicativo de monitoramento de redes). Nosso objetivo foi usar dados históricos para descobrir por que o sistema antigo falhava e como poderíamos deixá-lo mais rápido e seguro.

---

## 1. Diagnóstico Analítico (A Saúde do Sistema Antigo)

Para entender o que precisava ser melhorado, analisamos o histórico de funcionamento de 100 servidores e 50 relatórios de problemas. O sistema antigo era bom, mas sofria muito quando recebia muitos acessos ao mesmo tempo.

### 📈 O que os números nos mostraram:
* **Disponibilidade Média (Uptime):** `99.74%` *(O tempo que o sistema passou online, funcionando).*
* **Taxa de Sucesso de Conexão:** `98.39%` *(De cada 100 tentativas de acessar o sistema, cerca de 98 davam certo de primeira).*
* **Latência Média Global:** `131.89 ms` *(O "delay" ou tempo de resposta do sistema. Quanto menor esse número, mais rápido o sistema é. 131 ms é um valor considerado alto).*
* **Satisfação do Usuário:** `4.04 de 5.00` *(A nota que os clientes davam para a experiência geral).*

### 🔍 Entendendo os Erros (O que quebrava o sistema?)
Descobrimos que a maioria dos travamentos da versão anterior acontecia por quatro motivos específicos. Para facilitar, imagine a rede de computadores como o trânsito de uma grande cidade:

1. **Problemas de Roteamento (20% dos erros):** *O congestionamento.* O sistema tentava enviar todos os dados pelo mesmo caminho na internet nos horários de pico, travando tudo.
2. **Quedas de Conexão (18% dos erros):** *A linha caindo.* Interrupções repentinas que faziam o usuário ter que recarregar a página.
3. **Erros de Protocolo (18% dos erros):** *Problemas de comunicação.* Acontecia quando dois computadores tentavam conversar, mas usavam "idiomas" ou formatos de dados diferentes.
4. **Falhas de DNS (15% dos erros):** *A lista de contatos travada.* O DNS funciona como a agenda do seu celular (ele traduz o nome do site para o número de IP real). Quando ele falhava, o sistema não encontrava o caminho.

> ⚠️ **O Grande Gargalo (Sobrecarga de Hardware):** Os relatórios de empresas parceiras (como *TechGlobal Inc.* e *Innova Solutions*) mostraram que, nos horários com muitos usuários logados, o motor dos servidores quase explodia: chegávamos a **94.57% de uso de CPU** (o processador) e **89.53% de uso de memória**. Isso deixava o aplicativo de monitoramento lento bem no momento em que os clientes mais precisavam dele.

---

## 2. Soluções Implementadas (Como resolvemos isso?)

Com base nesses dados, redesenhamos a estrutura do NetGuard Pro focando em três melhorias principais:

### ⚙️ Divisão Inteligente de Tarefas (Alocação Dinâmica de Recursos)
* **Como era antes:** Toda a carga de trabalho ia para um único servidor centralizado, o que fazia o uso de CPU passar dos 94%.
* **Como é agora:** O sistema agora monitora a si mesmo em tempo real. Se um servidor começar a ficar muito carregado e passar de 80%, o NetGuard Pro distribui o peso das tarefas com outros servidores vizinhos de forma automática, evitando lentidões.

### 🔄 O "Waze" dos Dados (Algoritmo de Roteamento Adaptativo)
* **Como era antes:** Os dados seguiam sempre o mesmo caminho rígido (gerando os 20% de erros de roteamento e a latência alta de 131.89 ms).
* **Como é agora:** Criamos um sistema inteligente de rotas. Se o caminho principal estiver congestionado ou fora do ar, os dados mudam de rota sozinhos para encontrar o caminho mais rápido. Nos nossos testes, isso derrubou o tempo de resposta de **131.89 ms para apenas 42 ms** (o sistema ficou mais de 3 vezes mais rápido).

### 🛡️ Sistema de Disjuntor Seguro (Gateway Unificado e Failover)
* **Como era antes:** Se a lista de contatos (DNS) falhasse ou acontecesse um erro de comunicação (protocolo), o aplicativo inteiro travava na tela do usuário.
* **Como é agora:** Separamos o sistema em vários pequenos blocos independentes protegidos por uma "porta central" (Gateway). Se um pedaço do sistema falhar ou sofrer um erro, essa porta redireciona o usuário para uma cópia de segurança instantaneamente. O usuário continua navegando normalmente sem nem perceber que algo falhou nos bastidores.

---

# NetGuard Pro: Diagnóstico de Rendimiento y Optimización de Infraestructura

Este documento presenta, de forma sencilla y visual, el análisis de datos y las decisiones de ingeniería que tomamos para crear la nueva versión de **NetGuard Pro** (una aplicación de monitoreo de redes). Nuestro objetivo fue utilizar datos históricos para descubrir por qué el sistema antiguo fallaba y cómo podíamos hacerlo más rápido y seguro.

---

## 1. Diagnóstico Analítico (La Salud del Sistema Antiguo)

Para entender qué necesitábamos mejorar, analizamos el historial de funcionamiento de 100 servidores y 50 informes de problemas. El sistema antiguo era bueno, pero sufría mucho cuando recibía muchos accesos al mismo tiempo.

### 📈 Lo que los números nos mostraron:
* **Disponibilidad Media (Uptime):** `99.74%` *(El tiempo que el sistema pasó en línea, funcionando).*
* **Tasa de Éxito de Conexión:** `98.39%` *(De cada 100 intentos de acceder al sistema, cerca de 98 funcionaban a la primera).*
* **Latencia Media Global:** `131.89 ms` *(El "delay" o tiempo de respuesta del sistema. Cuanto menor sea este número, más rápido es el sistema. 131 ms se considera un valor alto).*
* **Satisfacción del Usuario:** `4.04 de 5.00` *(La nota que los clientes le daban a la experiencia general).*

### 🔍 Entendiendo los Errores (¿Qué rompía el sistema?)
Descubrimos que la mayoría de los bloqueos de la versión anterior ocurrían por cuatro motivos específicos. Para facilitar la comprensión, imagine la red de computadoras como el tráfico de una gran ciudad:

1. **Problemas de Enrutamiento (20% de los errores):** *El congestionamiento.* El sistema intentaba enviar todos los datos por el mismo camino en internet durante las horas pico, ralentizando todo.
2. **Caídas de Conexión (18% de los errores):** *La línea cayéndose.* Interrupciones repentinas que obligaban al usuario a tener que recarregar la página.
3. **Errores de Protocolo (18% de los errores):** *Problemas de comunicación.* Ocurría cuando dos computadoras intentaban hablar entre sí, pero usaban "idiomas" o formatos de datos diferentes.
4. **Fallos de DNS (15% de los errores):** *La lista de contactos bloqueada.* El DNS funciona como la agenda de su teléfono celular (traduce el nombre del sitio web al número de IP real). Cuando fallaba, el sistema no encontraba el camino.

> ⚠️ **El Gran Cuello de Botella (Sobrecarga de Hardware):** Los informes de empresas aliadas (como *TechGlobal Inc.* e *Innova Solutions*) mostraron que, en los horarios con muchos usuarios conectados, el motor de los servidores casi colapsaba: llegábamos a **picos del 94.57% de uso de CPU** (el procesador) y **89.53% de uso de memoria**. Esto hacía que la aplicación de monitoreo se volviera lenta justo en el momento en que los clientes más la necesitaban.

---

## 2. Soluciones Implementadas (¿Cómo lo resolvimos?)

Con base en estos datos, rediseñamos la estructura de NetGuard Pro enfocándonos en tres mejoras principales:

### ⚙️ División Inteligente de Tareas (Asignación Dinámica de Recursos)
* **Cómo era antes:** Toda la carga de trabajo iba a un único servidor centralizado, lo que hacía que el uso de CPU superara el 94%.
* **Cómo es ahora:** El sistema ahora se monitorea a sí mismo en tiempo real. Si un servidor comienza a saturarse y pasa del 80%, NetGuard Pro distribuye el peso de las tareas con otros servidores vecinos de forma automática, evitando ralentizaciones.

### 🔄 El "Waze" de los Datos (Algoritmo de Enrutamiento Adaptativo)
* **Cómo era antes:** Los datos seguían siempre el mismo camino rígido (generando el 20% de errores de enrutamiento y la latencia alta de 131.89 ms).
* **Cómo es ahora:** Creamos un sistema inteligente de rutas. Si el camino principal está congestionado o fuera de servicio, los datos cambian de ruta por sí solos para encontrar el camino más rápido. En nuestras pruebas, esto redujo el tiempo de respuesta de **131.89 ms a solo 42 ms** (el sistema se volvió más de 3 veces más rápido).

### 🛡️ Sistema de Disyuntor Seguro (Gateway Unificado y Failover)
* **Cómo era antes:** Si la lista de contactos (DNS) fallaba o se presentaba un error de comunicación (protocolo), la aplicación entera se congelaba en la pantalla del usuario.
* **Cómo es ahora:** Separamos el sistema en varios pequeños bloques independientes protegidos por una "puerta central" (Gateway). Si una parte del sistema falla o sufre un error, esta puerta redirecciona al usuario a una copia de seguridad instantáneamente. El usuario continúa navegando normalmente sin siquiera darse cuenta de que algo falló tras bambalinas.
