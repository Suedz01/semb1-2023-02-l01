# Questionário Sistemas Embarcados I

## 1. Explique brevemente o que é compilação cruzada (***cross-compiling***) e para que ela serve.
R:
A compilação cruzada, ou cross-compiling, é um processo pelo qual o código-fonte de um programa é compilado em um sistema de desenvolvimento que é diferente do sistema de destino no qual o programa será executado. Isso significa que o ambiente de compilação e o ambiente de execução são distintos em termos de arquitetura de hardware, sistema operacional ou ambos. O principal objetivo da compilação cruzada é permitir o desenvolvimento de software para plataformas que não são diretamente compatíveis com o sistema de desenvolvimento utilizado. Por exemplo, você pode desenvolver e compilar um programa em um computador com arquitetura x86 (como um PC) e depois executá-lo em um dispositivo embarcado com uma arquitetura ARM. Isso é especialmente útil em sistemas embarcados, onde os recursos de computação podem ser limitados e não é prático ou viável compilar o código diretamente no dispositivo alvo.



## 2. O que é um código de inicialização ou ***startup*** e qual sua finalidade?
R:
O código de inicialização, também conhecido como código de startup, é um conjunto de instruções que é executado imediatamente após ligar ou reiniciar um sistema embarcado. Sua finalidade é configurar o ambiente de execução necessário para carregar e executar o restante do software. Isso inclui inicializar e configurar hardware, estabelecer a pilha e heap, configurar o ambiente de execução e carregar o código principal. Em resumo, o código de inicialização garante uma inicialização ordenada e prepara o sistema para a execução do software principal.



## 3. Sobre o utilitário **make** e o arquivo **Makefile responda**:
#### (a) Explique com suas palavras o que é e para que serve o **Makefile**.
R:
Makefile é um automatizador de processos de compilação que coordena e gerencia diferentes componentes de software para produzir um executável final ou outros artefatos de construção, como bibliotecas compartilhadas. Ele simplifica e automatiza o processo de compilação, garantindo que as dependências entre os arquivos fonte sejam adequadamente gerenciadas e que o software seja construído de forma eficiente e consistente.

#### (b) Descreva brevemente o processo realizado pelo utilitário **make** para compilar um programa.
R:
   1. **Leitura do Makefile:** O utilitário `make` inicia lendo o arquivo Makefile no diretório atual. Este arquivo contém as regras e instruções para compilar o programa, incluindo as dependências entre os arquivos fonte e os comandos necessários para compilação.
   2. **Análise das Dependências:** `make` analisa as dependências entre os diferentes arquivos fonte e determina quais partes do código precisam ser recompiladas com base nas datas de modificação dos arquivos e nas regras definidas no Makefile.
   3. **Execução dos Comandos de Compilação:** Para cada parte do programa que precisa ser compilada, `make` executa os comandos especificados no Makefile. Isso geralmente envolve invocar o compilador (como gcc para C/C++ ou javac para Java) com as opções apropriadas e os arquivos fonte relevantes.
   4. **Vinculação dos Objetos Compilados:** Depois que todas as partes do programa são compiladas com sucesso, `make` vincula os objetos compilados juntos para formar o executável final. Isso geralmente envolve invocar o linker (como ld para C/C++ ou javac para Java) para combinar os objetos compilados em um único arquivo executável.
   5. **Conclusão da Compilação:** Uma vez que todas as etapas de compilação e vinculação são concluídas sem erros, o utilitário `make` gera o executável final ou outros artefatos de construção especificados no Makefile.

#### (c) Qual é a sintaxe utilizada para criar um novo **target**?

#### (d) Como são definidas as dependências de um **target**, para que elas são utilizadas?

#### (e) O que são as regras do **Makefile**, qual a diferença entre regras implícitas e explícitas?




## 4. Sobre a arquitetura **ARM Cortex-M** responda:

### (a) Explique o conjunto de instruções ***Thumb*** e suas principais vantagens na arquitetura ARM. Como o conjunto de instruções ***Thumb*** opera em conjunto com o conjunto de instruções ARM?

### (b) Explique as diferenças entre as arquiteturas ***ARM Load/Store*** e ***Register/Register***.

### (c) Os processadores **ARM Cortex-M** oferecem diversos recursos que podem ser explorados por sistemas baseados em **RTOS** (***Real Time Operating Systems***). Por exemplo, a separação da execução do código em níveis de acesso e diferentes modos de operação. Explique detalhadamente como funciona os níveis de acesso de execução de código e os modos de operação nos processadores **ARM Cortex-M**.

### (d) Explique como os processadores ARM tratam as exceções e as interrupções. Quais são os diferentes tipos de exceção e como elas são priorizadas? Descreva a estratégia de **group priority** e **sub-priority** presente nesse processo.

### (e) Qual a diferença entre os registradores **CPSR** (***Current Program Status Register***) e **SPSR** (***Saved Program Status Register***)?

### (f) Qual a finalidade do **LR** (***Link Register***)?

### (g) Qual o propósito do Program Status Register (PSR) nos processadores ARM?

### (h) O que é a tabela de vetores de interrupção?

### (i) Qual a finalidade do NVIC (**Nested Vectored Interrupt Controller**) nos microcontroladores ARM e como ele pode ser utilizado em aplicações de tempo real?

### (j) Em modo de execução normal, o Cortex-M pode fazer uma chamada de função usando a instrução **BL**, que muda o **PC** para o endereço de destino e salva o ponto de execução atual no registador **LR**. Ao final da função, é possível recuperar esse contexto usando uma instrução **BX LR**, por exemplo, que atualiza o **PC** para o ponto anterior. No entanto, quando acontece uma interrupção, o **LR** é preenchido com um valor completamente  diferente,  chamado  de  **EXC_RETURN**.  Explique  o  funcionamento  desse  mecanismo  e especifique como o **Cortex-M** consegue fazer o retorno da interrupção. 

### (k) Qual  a  diferença  no  salvamento  de  contexto,  durante  a  chegada  de  uma  interrupção,  entre  os processadores Cortex-M3 e Cortex M4F (com ponto flutuante)? Descreva em termos de tempo e também de uso da pilha. Explique também o que é ***lazy stack*** e como ele é configurado. 


## Referências

### Básicas

[1] [STM32F411xC Datasheet](https://www.st.com/resource/en/datasheet/stm32f411ce.pdf)

[2] [RM0383 Reference Manual](https://www.st.com/resource/en/reference_manual/rm0383-stm32f411xce-advanced-armbased-32bit-mcus-stmicroelectronics.pdf)

[3] [Using the GNU Compiler Collection (GCC)](https://gcc.gnu.org/onlinedocs/gcc/index.html)

[4] [GNU Make](https://www.gnu.org/software/make/manual/html_node/index.html)

### Vídeos Microsoft Teams

[5] [05 - Introdução à arquitetura de computadores](https://web.microsoftstream.com/embed/channel/f6b3a0de-e6f3-4652-b2d5-f1164032498a?app=microsoftteams&sort=undefined&l=pt-br#)

[6] [06 - Arquitetura Cortex-M Parte 1/2](https://web.microsoftstream.com/embed/channel/f6b3a0de-e6f3-4652-b2d5-f1164032498a?app=microsoftteams&sort=undefined&l=pt-br#)

[7] [07 - Arquitetura Cortex-M Parte 2/2](https://web.microsoftstream.com/embed/channel/f6b3a0de-e6f3-4652-b2d5-f1164032498a?app=microsoftteams&sort=undefined&l=pt-br#)

[8] [08 - Microcontroladores STM32](https://web.microsoftstream.com/embed/channel/f6b3a0de-e6f3-4652-b2d5-f1164032498a?app=microsoftteams&sort=undefined&l=pt-br#)

[9] [10 - Introdução à arquitetura de computadores](https://web.microsoftstream.com/embed/channel/f6b3a0de-e6f3-4652-b2d5-f1164032498a?app=microsoftteams&sort=undefined&l=pt-br#)

### Material Suplementar

[5] [A General Overview of What Happens Before main()](https://embeddedartistry.com/blog/2019/04/08/a-general-overview-of-what-happens-before-main/)
 
[6] [Bare metal embedded lecture-1: Build process](https://youtu.be/qWqlkCLmZoE?si=mn5yDnJYudQ1PpZH)
 
[7] [Bare metal embedded lecture-2: Makefile and analyzing relocatable obj file](https://youtu.be/Bsq6P1B8JqI?si=yuNLPj3JQ-2IT1yo)
 
[8] [Bare metal embedded lecture-3: Writing MCU startup file from scratch](https://youtu.be/2Hm8eEHsgls?si=c27MpZ47ApiMSwHR)
 
[9] [Lecture 15: Booting Process](https://youtu.be/3brOzLJmeek?si=MsHRUEJP8zofjwJQ)
