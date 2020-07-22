# Inova_MPRJ-2020_ESTAGIO
ANALISE DE DADOS PÚBLICOS SOBRE OBRAS GOVERNAMENTAIS A FIM DE GERAR CONCLUSÕES SOBRE A CERCA DOS ATRASOS

### Quais Obras públicas Atrasam?
Diante dos dados disponibilizados sobre os convênios pela plataforma +brazil foram utilizados dois métodos para responder esta pergunta. 
   
   O primeiro método se baseou nas informações da vigência dos contratos, visto que a data fim dos contratos é alterada diante de um atraso. Logo, as obras atrasadas(que atrasaram, embora tenha sido finalizadas) são as que a DATA_FIM_VIGENC_CONV>DATA_FIM_VIGENC_CONV.
  O segundo método foi de observar que para cada meta estabelecida no planejamento há diversas etapas associadas. E de acordo com [], uma obra é considerada atrasada quando há um descumporimento do cronograma. Logo, se housse uma etapa finalizada depois do fim previso para a meta, haveria atraso. 
  
  Cabe ressaltar, que o segundo método foi criado visando testar o método 1 e observar possíveis inconssistências nas respostas.
O código relacionado a este processo encontra-se sob o nome 'ATRASO_METODOS_VERIFICACAO'. Os dois métodos revelaram respostas comptíveis, isto é, identificaram o mesmo conjunto de convenios que atrasaram.

