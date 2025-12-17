-- Análise das Execuções --

Nesta atividade foram executados programas em Java que simulam várias threads
acessando a mesma conta bancária. O objetivo foi entender como funciona o
controle de concorrência.

Cada versão do programa foi executada três vezes para comparar os resultados.

# Concorrente
Na versão Concorrente não existe controle de acesso ao saldo. Durante as
execuções foi possível perceber que os valores finais mudam, mesmo rodando
o mesmo programa. Isso acontece porque várias threads acessam o saldo ao
mesmo tempo, causando erros nos resultados.

# Synk
Na versão Synk foi usado o `synchronized` para controlar o acesso ao saldo.
Com isso, apenas uma thread acessa o saldo por vez. Os resultados ficaram
corretos em todas as execuções, porém as threads precisam esperar, deixando
o programa mais lento.

# Lock
Na versão Lock foi usado o `ReentrantLock`. O resultado foi semelhante ao
synchronized, com valores corretos. A diferença é que esse método dá mais
controle sobre o bloqueio, tornando o código mais organizado.

# RwLock 
Na versão RwLock foi usado o `ReadWriteLock`, que permite várias leituras ao
mesmo tempo, mas apenas uma escrita. Os resultados ficaram corretos e bem
comportados nas execuções.

# Conclusão
Com os testes realizados, ficou claro que sem controle de concorrência os
resultados ficam incorretos. Usando sincronização, os valores passam a ser
corretos e confiáveis. A escolha do método depende do tipo de aplicação.

