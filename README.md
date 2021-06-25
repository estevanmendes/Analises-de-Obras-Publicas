## O desafio

O desafio consiste em realizar uma análise exploratória sobre obras públicas paralisadas, a partir de dados públicos estruturados. Esse desafio é inspirado no projeto [Bússola _ Baía de Guanabara](http://www.mprj.mp.br/inova/baiaguanabara) (B_Guanabara), no qual o Inova_MPRJ trabalhou em parceria com os órgãos da área ambiental do MPRJ para monitorar o andamento das obras de despoluição da Baía de Guanabara.

Na maioria dos projetos que apoiamos, começamos sabendo muito pouco do assunto com o qual vamos trabalhar, e em poucas semanas precisamos aprender o suficiente para apontar o caminho de um protótipo robusto de solução. Neste desafio, queremos saber se você é capaz de fazer esse mergulho em um tema novo e, em poucos dias, propor visões pouco óbvias que orientem uma atuação baseada em dados para resolver problemas públicos.

No B_Guanabara, o desafio tem sido identificar quais das obras previstas tem mais chances de atrasar - e abrir os dados necessários para isso. Aqui, queremos que você faça o mesmo a partir de dados já abertos, relativos às [obras com recursos públicos do Governo Federal](http://plataformamaisbrasil.gov.br/sobre-a-plataforma). Não esperamos que você entregue um modelo preditivo completo, mas sim que seja capaz de manipular os dados, propor cruzamentos e indicadores e documentar o processo de pesquisa e desenvolvimento da solução.




# Inova_MPRJ-2020_ESTAGIO
Análise de dados públicos sobre obras governamentais a fim de gerar conclusões sobre os atrasos

### Quais obras públicas atrasam?
Diante dos dados disponibilizados sobre os convênios pela plataforma +brazil foram utilizados duas etapas para responder esta pergunta. 
   
   A primeira etapa foi descobrir quais dos convênios se tratavam de obras. Visto que a plaforma disponibiliza dados sobre todos os convẽnios. A segunda etapa se baseou nas informações da vigência dos contratos, visto que a data fim dos contratos é alterada diante de um atraso. Logo, as obras atrasadas (ou que atrasaram, embora tenha sido finalizadas) são as que a DATA_FIM_VIGENC_CONV>DATA_FIM_VIGENC_ORIGINAL_CONV. A planilha disponibilizada pelo TCU com as obras paralisadas, seria de grande interesse para validar o método aplicado na seleção das obras atrasadas. Pois, pode-se pensar que as obras paralisadas são um subconjunto das obras atrasadas, porém não havia informação suficiente na planilha para a verificação.  

### Quais fatores estão associados ao atraso?
#### Para responder precisamos saber quais as característas associadas as obras atrasadas. Além disso, quais características as obras atrasadas dispõem, e as obras concluídas no tempo correto não dispõem.
#### A localização espacial e temporal
![ATRASOS_UF](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/OBRAS_ATRASADO_POR_UF.png)

Embora possamos observar que algumas unidades da federação tem um número de obras atradas maior que a média.Esta característica pode estar relacionado à quantidade de obras que há no Estado. Se um estado tem mais obras que a média nacional, é plausível esperar que haja mais obras atrasadas nesse estado.

![ATRASOS_UF_REL](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/OBRAS_ATRASADO_REL_POR_UF.png)

Podemos observar qualitativamente que dois estados (RS,SC) apresentam uma taxa de obras atrasadas muito maior que a média nacional, e um estado apresenta comportamento contrário (SE).

![ATRASOS_ANO_REL](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/OBRAS_ATRASADO_REL_POR_ANO.png)

O decréssimo significativo no número de obras atrasadas pode ser atrelado ao fato de não ter havido tempo suficiente para que as obras iniciados recentemente atrasem. Este hipótese é corroborada pela distribuição dos dias de atraso.

Nesse contexto de temporalidade, é interessante analisarmos a distribuição do tempo de atraso das obras. 

![HIST_DIAS_ATRASO](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/HISTOGRAMA_DIAS_ATRASADOS.png)

O atraso em dias absolutos nos traz diversas informações. Todavia, o atraso de N dias em uma obra de duração K>>N, é diferente de um atraso N onde a duração da obra é K=N. Sendo assim, se faz necessário observar a distribuição dos atraso relativos à duração da obra.

![HIST_DIAS_ATRASO_REL](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/HISTOGRAMA_DIAS_ATRASADO_REL.png)

#### Valores do convênio e da Contrapartida.
Após algumas pesquisas sobre o tema, tanto na impressa quanto na literatura acadêmica. Observou-se que havia-se a hipótese de que obras ficam paradas devido ao valor da contrapartida requerida. E além disso, buscou-se encontrar uma relação entre o número de obras atrasadas e o valor de contrato.

![OBRAS_VALORES_CONV](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/HIST_OBRAS_TODOS_VALORES_CONV.png)

Detecta-se qualitativamente por meio dessa distribuiço que a média do valor das obras atrasadas é maior que a média das obras totais.

![OBRAS_CONTRAPARTIDA](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/HIST_CONTRAPARTIDA_CONV.png)

Além disso, procurou-se correlação entre os valores de contrapartida e o valor do convenio com o número de dias de atraso. A correlação entre o valor do contrato e a contrapartida deve ser ignorada, pois estão relacionados pela legislação. A contrapartida é uma fração do valor do contrato que depende de algumas caractersticas do ente resposável pela execução do convênio.

![CORR_VALORES_DIAS](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/CORRELACAO_VALOR_DIAS_ATRASO.png)

#### A Natureza da obra e o orgão responsável
Objetivando observar se há determinados tipos de obras que tendem a ter mais atraso, buscamos nos dados disponibilizados relacionar o orgão executor da obra com os atrasos.

![ORGAO_SUP_PIE_ATRASO](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/RELA%C3%87%C3%82O_ORGAO_EXECUTOR_OBRAS_ATRASADAS_PIE.png)![ORGAO_SUP_PIE_TODOS](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/RELA%C3%87%C3%82O_ORGAO_EXECUTOR_OBRAS_TODAS_PIE.png)

Por meio da análise desses gráficos podemos observar uma predileço ao atraso de alguns orgão executores dos convênios. As informaçoes associadas atempo de atraso de cada orgão executor pode ser observadas abaixo.

![DIAS_ATRASO_ORGAO_BOX](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/DIAS_DE_ATRASO_ORGAO_EXECUTOR_BOXPLOT.png)


#### O plano de Trabalho e o projeto da obra
Para que fosse exposto algum problema associado as obras atrasadas, verificou-se caractersticas concernetes ao projeto e plano de trabalho das obras.

![NUM_EMPRESAS_CONSORCIO](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/NUM_EMPRESAS_CONS.png)

Percebe-se que o número de concórcios grandes(>250 empresas) pertencem majoritariamente as obras que não atrasaram. 

![QTD_METAS](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/QTD_METAS.png)

É notório pela avaliação do gráfico acima que as obras que atrasam tendem a ter poucas metas no seu plano de trabalho.

![MEDIA_TEMPO_METAS](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/MED_TEMPO_METAS.png)

Além do número reduzido de metas, o tempo médio entre as metas tende a ser maior nas obras que atrasaram.

