# Inova_MPRJ-2020_ESTAGIO
ANALISE DE DADOS PÚBLICOS SOBRE OBRAS GOVERNAMENTAIS A FIM DE GERAR CONCLUSÕES SOBRE A CERCA DOS ATRASOS

### Quais obras públicas atrasam?
Diante dos dados disponibilizados sobre os convênios pela plataforma +brazil foram utilizados dois métodos para responder esta pergunta. 
   
   O primeiro método se baseou nas informações da vigência dos contratos, visto que a data fim dos contratos é alterada diante de um atraso. Logo, as obras atrasadas(que atrasaram, embora tenha sido finalizadas) são as que a DATA_FIM_VIGENC_CONV>DATA_FIM_VIGENC_CONV.
  O segundo método foi de observar que para cada meta estabelecida no planejamento há diversas etapas associadas. E de acordo com [], uma obra é considerada atrasada quando há um descumporimento do cronograma. Logo, se housse uma etapa finalizada depois do fim previso para a meta, haveria atraso. 
  
  Cabe ressaltar, que o segundo método foi criado visando testar o método 1 e observar possíveis inconssistências nas respostas.
O código relacionado a este processo encontra-se sob o nome 'ATRASO_METODOS_VERIFICACAO'. Os dois métodos revelaram respostas comptíveis, isto é, identificaram o mesmo conjunto de convenios que atrasaram.

### Quais fatores estão associados ao atraso?
#### Para responder isso precisamos saber quais as característas associadas as obras atrasadas. Além disso, quais características as obras atrasdas dispõe que as obras concluídas no tempo correto no apresetam.
#### A localização espacial e temporal
![ATRASOS_UF](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/OBRAS_ATRASADO_POR_UF.png)

Embora possamos observar que algmas unidades da federação tem um número de obras atradas maior que a média. Porém, isto pode está relacionado a quantidade de obras que há no Estado. Se um estado tem mais obras que a média nacional, é plausível esperar que haja mais obras atrasadas nesse estado.

![ATRASOS_UF_REL](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/OBRAS_ATRASADO_REL_POR_UF.png)

Podemos observar qualitativamente que não há nenhum estado com uma taxa de obras atrasadas muito maior que a média nacional.

![ATRASOS_ANO_REL](https://github.com/estevanmendes/Inova_MPRJ-2020_ESTAGIO/blob/master/img/OBRAS_ATRASADO_REL_POR_ANO.png)

O decréssimo significativo no número de obras atrasadas pode ser atrelado ao fato de não ter havido tempo o suficiente para que as obras iniciados recentemente atrasem. Isso é corroborado pela distribuição dos dias de atraso.

