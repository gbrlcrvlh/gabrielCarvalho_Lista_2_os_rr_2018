#### 1 - Explique a função dos Sistemas de Arquivos. Adicionalmente, descreva a diferença entre sistema de arquivos do linux e do windows.
O sistema de arquivos é o responsável por permitir que sistema operacional controle o acesso ao disco, permitindo que o mesmo utilize o espaço no disco para armazenar e utilizar os arquivos. Com o crescimento da capacidade dos discos rígidos e o aumento do volume de arquivos e acesso, o sistema de arquivo torna-se cada vez mais complexos e robusto. Cada sistema operacional adota uma formatação lógica diferente e todo sistema de arquivos baseia-se na gestão dos clusters (unidade de alocação), ou seja, a menor unidade de disco que o sistema operacional é capaz de gerenciar.

O sistemas linux suportam diversos tipos de sistemas de arquivos, sendo eles o Ext2, Ext3, ReiserFs e o Linux Swap (FAT16, FAT32, NTFS). Apesar do linux suportar o NTFS (sistema de arquivo utilizado nas versões mais recentes do windows), o linux apenas reconhece e lê dados, visto que o funcionamento interno do sistema NTFS é mantido em segredo pela Microsoft.

Nos sistemas da Microsoft mais antigos eram utilizado o sistema de arquivo FAT16 (File Allocation Table), que possui uma tabela que como um mapa de utilização do disco. O número 16 diz a respeito de cada posição no disco utilizar uma área variável de 16 bits. Como o sistema FAT16 apenas trabalhavam com discos menores que 2GB, foi lançado uma nova versão chamada de FAT32 porém ainda era mais lento que o FAT16 e não reconhecia discos maiores que 4GB. Para resolver estes problemas, foi criado o sistema de arquivo utilizado nos sistemas operacionais mais recentes, o NTFS (New Technology File System), um sistema de arquivo mais seguro que possui recurso de recuperação de erros no disco, suporte para discos com maior

Fontes: 
* https://www.hardware.com.br/termos/sistema-de-arquivos
* https://br.ccm.net/contents/612-o-sistema-de-arquivos
* http://www.cursosdeinformaticabasica.com.br/o-que-e-sistema-de-arquivos/
* http://meiradarocha.jor.br/news/2007/06/16/windows-e-linux-na-mesma-maquina/
* http://www.techtudo.com.br/dicas-e-tutoriais/noticia/2016/02/entenda-o-que-e-sistema-de-arquivos-e-sua-utilidade-no-pc-e-no-celular.html

#### 2 - Existem quatro tipos de problemas que podem ocorrer na execução de processos concorrentes: trancamento (lockout), impasse (deadlock), inanimação (starvation) e indeterminismo. Explique cada um deles dando exemplos de situações onde podem ocorrer.
#### DeadLock
Defini-se como deadolock um conjunto de processos do sistema operacional onde cada processo pertencente ao conjunto estiver esperando por um evento que somente outro processo deste mesmo conjunto poderá fazer acontecer. Sendo assim, nenhum processo consegue executar o recurso que precisa, ou liberar recurso que está em posse, ou ser acordado, por o recurso que precisa está ocupado.

Condições para se entrar no estado de deadlock:
* Exclusão Mútua: todo recurso está ou associado a um único processo ou disponível;
* Posse e espera: processos que retêm recursos podem solicitar novos recursos;
* Não preempção: recursos concedidos previamente não podem ser forçosamente tomados;
* Espera Circular: deve haver uma cadeia circular de dois ou mais processos, na qual cada um está à espera de recursos retido pelo membro seguinte dessa cadeia.

#### Lockout
É chamado de Lockout (Trancamento) toda tarefa que encontra-se aguardando um evento que nunca ocorrerá;

#### Starvation
Um processo encontra-se em situação de starvation quando o sistema operacional provê prioridades a processos, que não atualizados fazem com que o processos de menor prioridade nunca sejam executados, causando assim, deficiência em servidores de impressão e etc...

ex: Dois processos enviando repetitivamente mensagens um para o outro e um terceiro bloqueado, esperando por uma mensagem de um deles.

#### Indeterminismo
indeterminismo: múltiplas execuções de uma tarefa podem não gerar o mesmo resultado.

ex: variável compartilhada entre duas threads

* https://www.inf.ufes.br/~vitorsouza/wp-content/uploads/teaching-lp-20132-slides09.pdf
* https://pt.wikipedia.org/wiki/Inani%C3%A7%C3%A3o_(computa%C3%A7%C3%A3o)
* https://www.zemoleza.com.br/trabalho-academico/exatas/informatica/paginacao-deadlocks-e-starvation/
* http://homepages.dcc.ufmg.br/~rimsa/documents/decom009/lessons/Aula09.pdf
* https://www.oficinadanet.com.br/post/12786-sistemas-operacionais-o-que-e-deadlock
