# RELATÓRIO TÉCNICO DE DIAGNÓSTICO
## Scooter elétrica de 1.000 W — Defeitos recorrentes, causas e procedimentos de investigação

**Categoria:** Veículo elétrico leve  
**Equipamento:** Scooter elétrica com potência nominal de referência de 1.000 W  
**Finalidade:** Apoio técnico para identificação de falhas, manutenção e reparo  
**Público-alvo:** Técnicos de eletrônica, eletromecânica e manutenção de veículos elétricos

---

# 1. Objetivo do relatório

Este documento reúne os principais defeitos que podem ocorrer em uma scooter elétrica de aproximadamente 1.000 W, explicando:

- Quais sintomas o cliente normalmente relata.
- Quais componentes podem estar envolvidos.
- Quais são as causas prováveis.
- Como investigar a origem do defeito.
- Quais testes podem confirmar ou descartar hipóteses.
- Quais reparos podem ser necessários.
- Quando o problema pode estar relacionado ao proprietário, ao desgaste natural ou a uma falha técnica.

**Princípio fundamental:** o sintoma relatado pelo cliente não determina, sozinho, qual peça está defeituosa. Por exemplo, uma scooter que não liga pode ter uma bateria descarregada, um fusível aberto, um conector danificado, uma falha no circuito de alimentação ou um defeito no controlador.

O diagnóstico deve seguir uma sequência lógica, começando pelas verificações mais simples e avançando para os testes especializados.

# 2. Visão geral dos sistemas da scooter

Uma scooter elétrica de 1.000 W pode apresentar os seguintes conjuntos, dependendo do modelo:

| Sistema | Principais componentes | Função |
|---|---|---|
| Alimentação | Bateria, fusível, cabos e conectores | Fornecer energia elétrica |
| Recarga | Carregador, entrada de carga e circuito de proteção | Recarregar a bateria |
| Controle de potência | Controlador eletrônico, MOSFETs e capacitores | Regular a energia enviada ao motor |
| Propulsão | Motor elétrico, sensores Hall quando presentes | Produzir movimento |
| Comando | Acelerador, chave de ignição e botões | Solicitar aceleração e habilitar o sistema |
| Monitoramento | Display, indicadores e sensores | Exibir informações e comunicar falhas |
| Frenagem elétrica | Sensores de freio e, quando disponível, frenagem regenerativa | Cortar a tração e auxiliar a desaceleração |
| Instalação elétrica | Chicote, terminais, emendas e conectores | Interligar os sistemas |
| Estrutura mecânica | Rolamentos, rodas, pneus, suspensão e freios | Sustentar e permitir o deslocamento |
| Segurança | BMS, fusíveis e proteções térmicas ou elétricas | Reduzir riscos e danos |

Nem todas as scooters possuem todos esses componentes. Antes de iniciar o serviço, identifique a arquitetura do equipamento.

# 3. Defeitos recorrentes no sistema de bateria

## 3.1. A scooter não liga

**Sintomas relatados pelo cliente:**
- O display não acende.
- Nenhum indicador responde.
- A scooter parece estar completamente sem energia.
- O equipamento parou de funcionar repentinamente.

**Causas possíveis:**
1. Bateria descarregada ou com tensão abaixo do limite operacional.
2. Fusível queimado ou disjuntor desarmado, quando existente.
3. Conector principal solto, oxidado ou danificado.
4. Chave de ignição ou botão de acionamento defeituoso.
5. BMS bloqueando a saída da bateria.
6. Cabo rompido ou com mau contato.
7. Falha no circuito de alimentação do controlador ou do display.

**Como diagnosticar:**
1. Verifique se o carregador apresenta comportamento normal e se a tomada utilizada está funcionando.
2. Inspecione visualmente os conectores, cabos e fusíveis acessíveis.
3. Confirme a tensão da bateria com instrumento adequado, seguindo as especificações do fabricante.
4. Se a tensão parecer normal, verifique se ela se mantém durante uma solicitação de carga, com procedimento seguro e controlado.
5. Investigue a continuidade do circuito de alimentação e a presença de tensão na entrada do controlador.
6. Se a alimentação principal estiver correta, prossiga para o circuito de ignição, display e controlador.

**Possível solução:**
- Recarregar a bateria, quando apropriado.
- Corrigir conexões.
- Substituir um fusível somente depois de investigar a causa da abertura.
- Reparar cabos ou interruptores.
- Diagnosticar o BMS ou o controlador conforme o resultado dos testes.

**O proprietário causou o defeito?**

Não necessariamente. Uma descarga profunda pode estar relacionada a armazenamento inadequado, mas uma falha no BMS, no carregador ou em uma conexão também pode produzir o mesmo sintoma.

## 3.2. A bateria descarrega muito rápido

**Sintomas:**
- A autonomia diminuiu consideravelmente.
- A scooter funciona normalmente por pouco tempo.
- O indicador de carga cai rapidamente.
- O equipamento desliga durante acelerações ou subidas.

**Causas possíveis:**
- Envelhecimento natural das células.
- Armazenamento prolongado com carga inadequada.
- Uso frequente em subidas, terrenos difíceis ou com carga elevada.
- Pneus com pressão insuficiente ou freios prendendo.
- Células desequilibradas ou degradadas.
- BMS com defeito ou leitura inadequada.
- Indicador de carga impreciso.
- Consumo anormal do controlador ou do motor.

**Como diagnosticar:**
1. Confirme a autonomia relatada e as condições de uso.
2. Verifique a pressão dos pneus e se as rodas giram livremente.
3. Inspecione o carregador e confirme se a bateria atinge o estado de carga esperado.
4. Avalie a tensão em repouso e durante o funcionamento, conforme os limites do fabricante.
5. Em uma bateria de lítio, solicite a um profissional qualificado uma análise do BMS, do equilíbrio das células e da capacidade real.
6. Compare o consumo e o comportamento do motor com as especificações do equipamento.

**Possíveis soluções:**
- Corrigir atrito mecânico e pressão dos pneus.
- Substituir um carregador inadequado ou defeituoso.
- Reparar o circuito de monitoramento, quando viável.
- Substituir a bateria quando houver degradação comprovada.

**Relação com o uso:** a redução de autonomia pode ser resultado do envelhecimento normal. Descargas profundas frequentes, calor excessivo, armazenamento inadequado e uso de carregador incompatível podem acelerar a degradação.

## 3.3. A bateria não carrega

**Sintomas:**
- O carregador não indica carga.
- O carregador permanece verde, embora a bateria esteja descarregada.
- A carga inicia e interrompe.
- O tempo de recarga aumentou muito.

**Causas possíveis:**
- Tomada sem alimentação.
- Carregador defeituoso ou incompatível.
- Conector de carga oxidado ou danificado.
- Fusível ou circuito de entrada aberto.
- BMS impedindo a recarga por subtensão, temperatura ou outra proteção.
- Bateria degradada.
- Falha de comunicação ou detecção, em sistemas que utilizam esses recursos.

**Procedimento de diagnóstico:**
1. Verifique a tomada e o cabo de alimentação.
2. Confira a etiqueta do carregador: tensão, corrente, polaridade e compatibilidade com a bateria.
3. Inspecione a entrada de carga, procurando folgas, marcas de aquecimento ou oxidação.
4. Teste o carregador com equipamento adequado ou substituto comprovadamente compatível.
5. Se o carregador estiver correto, investigue o circuito de carga e o BMS.

**Atenção:** não tente forçar a carga de uma bateria que esteja bloqueada por proteção, danificada, estufada ou excessivamente quente. Isso pode provocar incêndio.

## 3.4. A bateria esquenta, estufa ou apresenta cheiro estranho

**Sintomas:**
- Aquecimento anormal durante a carga ou o uso.
- Invólucro deformado.
- Odor químico, fumaça ou ruídos incomuns.

**Possíveis causas:**
- Danos internos nas células.
- Curto-circuito.
- Sobrecarga ou carregador incompatível.
- Entrada de água.
- Impacto ou perfuração.
- Falha do BMS.
- Conexões de alta resistência que aquecem sob corrente.

**Conduta técnica:**
- Interrompa o uso e a recarga.
- Não abra, perfure, comprima ou tente reparar células danificadas.
- Se houver fumaça, chiado, aumento rápido de temperatura ou risco de incêndio, afaste as pessoas e acione os serviços de emergência.
- Não transporte uma bateria instável para dentro da oficina.
- Encaminhe o conjunto para atendimento especializado, seguindo as regras locais de segurança e descarte.

**Possível relação com o proprietário:** impactos, exposição à água e uso de carregador inadequado podem contribuir, mas uma falha interna também pode ocorrer sem mau uso evidente.

# 4. Defeitos no carregador e na entrada de recarga

## 4.1. Carregador não funciona

**Causas prováveis:**
- Cabo rompido.
- Plugue danificado.
- Fusível interno aberto, se houver.
- Falha na fonte chaveada.
- Defeito no estágio de potência ou no circuito de controle.
- Proteção acionada por curto-circuito na saída.

**Testes recomendados:**
- Inspeção visual do cabo, plugue e carcaça.
- Conferência da etiqueta e das especificações.
- Medição da saída conforme o procedimento do fabricante.
- Teste com um carregador conhecido como funcional e comprovadamente compatível.

**Reparo:** pode envolver substituição do carregador ou reparo especializado da fonte. Não abra um carregador conectado à rede elétrica: capacitores internos podem manter tensões perigosas mesmo após a desconexão.

## 4.2. Entrada de carga frouxa ou intermitente

**Causas prováveis:**
- Conector submetido a esforço mecânico.
- Cabo puxado ou dobrado repetidamente.
- Oxidação por umidade.
- Solda trincada ou terminal danificado.

**Diagnóstico:**
- Inspecione o conector sem aplicar força excessiva.
- Procure folga, escurecimento, corrosão ou deformação.
- Verifique a continuidade do circuito com o equipamento desenergizado e isolado de forma segura.

**Reparo:** substituir o conector ou o chicote danificado, respeitando a capacidade de corrente e a vedação original.

# 5. Defeitos no controlador eletrônico

O controlador recebe a energia da bateria e regula a potência entregue ao motor. Dependendo do modelo, também interpreta os sinais do acelerador, dos sensores Hall, do freio e do display.

## 5.1. A scooter liga, mas não acelera

**Causas possíveis:**
- Sensor de freio indicando frenagem permanente.
- Acelerador defeituoso.
- Conector do acelerador desconectado.
- Falha no controlador.
- Falha nos sensores Hall do motor, quando presentes.
- Bateria incapaz de fornecer corrente suficiente.
- Proteção por subtensão, temperatura ou código de erro.
- Falha de comunicação entre display e controlador.

**Sequência de diagnóstico:**
1. Registre o código de erro antes de desconectar componentes.
2. Confira se o display informa freio acionado ou outra condição de bloqueio.
3. Verifique o retorno mecânico das manetes e o estado dos sensores de freio.
4. Inspecione os conectores do acelerador e do motor.
5. Verifique a alimentação e o sinal do acelerador conforme o diagrama técnico do modelo.
6. Se os sinais estiverem corretos, investigue o controlador e o motor.

**Importante:** não faça pontes aleatórias em conectores para tentar liberar a aceleração. Isso pode desativar recursos de segurança.

## 5.2. A scooter liga e desliga sozinha

**Causas possíveis:**
- Bateria com queda de tensão sob carga.
- Conexão principal intermitente.
- Terminal aquecido ou oxidado.
- Controlador superaquecendo.
- BMS interrompendo a saída.
- Falha no interruptor de ignição.
- Defeito eletrônico no controlador.

**Diagnóstico:**
- Observe se a falha ocorre em aceleração, em subidas, após aquecimento ou ao passar por irregularidades.
- Verifique a tensão da bateria durante a ocorrência, por meio de um procedimento seguro.
- Inspecione os conectores de potência em busca de sinais térmicos.
- Verifique se o desligamento acontece junto com uma indicação de proteção.

**Possível solução:** reparar a conexão, corrigir o problema térmico, avaliar a bateria ou substituir o controlador somente após confirmar a falha.

## 5.3. Controlador superaquece

**Causas possíveis:**
- Corrente excessiva.
- Motor com esforço mecânico anormal.
- Rolamentos travados ou freios prendendo.
- Pneus com pressão baixa.
- Dissipação térmica inadequada.
- Instalação incompatível entre motor, bateria e controlador.
- Entrada de água ou degradação dos componentes internos.

**Como investigar:**
1. Confira se as rodas giram livremente.
2. Verifique se a corrente nominal do controlador é adequada ao conjunto.
3. Inspecione a fixação, a ventilação e o contato térmico previstos pelo fabricante.
4. Procure sinais de umidade, corrosão ou componentes queimados.
5. Se necessário, avalie a corrente consumida com instrumento apropriado e em condições controladas.

**Não aumente o limite de corrente para resolver perda de desempenho.** Isso pode agravar o aquecimento e danificar a bateria, o controlador ou o motor.

# 6. Defeitos no motor elétrico de 1.000 W

O motor pode ser do tipo BLDC (corrente contínua sem escovas), frequentemente integrado à roda, mas a arquitetura deve ser confirmada.

## 6.1. Motor não gira

**Causas possíveis:**
- Falta de alimentação.
- Controlador defeituoso.
- Cabo de fases rompido.
- Conector do motor danificado.
- Sensores Hall defeituosos, se utilizados.
- Enrolamentos danificados.
- Bloqueio mecânico da roda.
- Proteção acionada por falha no sistema.

**Diagnóstico:**
1. Verifique se a roda está mecanicamente livre.
2. Inspecione o cabo que sai do motor e os conectores.
3. Confirme a presença dos sinais e da alimentação previstos no manual.
4. Teste os sensores Hall e os enrolamentos conforme a arquitetura do motor.
5. Só condene o motor depois de descartar controlador, chicote e bloqueios de segurança.

## 6.2. Motor falha, vibra ou dá trancos

**Causas possíveis:**
- Sequência de fases incompatível após reparo.
- Sensor Hall intermitente.
- Conector com mau contato.
- Falha em uma fase do controlador.
- Enrolamento parcialmente danificado.
- Rolamento comprometido.
- Problema de alinhamento ou interferência mecânica.

**Como diagnosticar:**
- Observe se os trancos aparecem desde a partida ou apenas com o motor aquecido.
- Inspecione conectores e cabos.
- Verifique os sinais dos sensores, se existirem.
- Compare as medições dos enrolamentos conforme as especificações.
- Examine rolamentos e componentes mecânicos.

**Evite continuar acelerando durante trancos intensos.** A corrente elevada pode aquecer rapidamente o controlador e os enrolamentos.

## 6.3. Motor faz ruído anormal

**Causas possíveis:**
- Rolamentos desgastados.
- Atrito entre componentes.
- Fixação solta.
- Dano mecânico após impacto.
- Comutação irregular causada por controlador ou sensores.
- Contato do pneu ou de outro componente com a estrutura.

**Diagnóstico:**
- Diferencie ruído mecânico de ruído elétrico.
- Com o sistema desligado e seguro, verifique a rotação manual da roda.
- Procure folgas, raspagens e vibração.
- Se o ruído aparecer somente sob potência, investigue também controlador, sensores e enrolamentos.

# 7. Defeitos no acelerador

## 7.1. Acelerador não responde

**Causas possíveis:**
- Sensor interno defeituoso.
- Cabo rompido.
- Conector solto.
- Alimentação ou referência elétrica ausente.
- Bloqueio por sensor de freio.
- Falha no controlador.

**Diagnóstico:**
1. Confira se a manopla retorna normalmente e não está presa.
2. Inspecione o chicote, especialmente nas regiões de dobra.
3. Meça alimentação e sinal conforme o manual.
4. Compare o sinal em repouso e durante o acionamento, sem ultrapassar os limites especificados.
5. Investigue o controlador se o sinal estiver correto.

## 7.2. Acelerador apresenta resposta irregular

**Causas possíveis:**
- Desgaste do sensor.
- Umidade ou corrosão.
- Fio parcialmente rompido.
- Conector intermitente.
- Falha de referência elétrica.

**Reparo possível:** substituir o acelerador ou o chicote defeituoso. O componente de reposição deve ser eletricamente compatível e ter o mesmo comportamento de sinal esperado pelo controlador.

**Atenção:** qualquer aceleração inesperada é uma falha crítica. Suspenda o uso até a correção e valide o retorno a zero antes de liberar o veículo.

# 8. Defeitos nos sensores de freio e na frenagem

## 8.1. A scooter não acelera com o freio solto

**Causas possíveis:**
- Sensor de freio desalinhado.
- Manete não retornando totalmente.
- Cabo do sensor danificado.
- Interruptor com defeito.
- Curto ou circuito aberto no chicote.

**Diagnóstico:**
- Verifique o retorno mecânico da manete.
- Observe o indicador de freio no display, se houver.
- Confira o estado elétrico do sensor conforme o esquema do fabricante.
- Não libere a scooter com o sistema de corte de tração desativado.

## 8.2. Freio fraco, travando ou com ruído

**Causas possíveis:**
- Pastilhas ou sapatas desgastadas.
- Disco contaminado, empenado ou danificado.
- Cabo ou sistema hidráulico com problema.
- Pinça desalinhada.
- Rolamento ou roda com defeito.
- Manutenção inadequada.
- Desgaste natural.

**Procedimento:**
1. Inspecione disco, pastilhas, pinça, cabos ou circuito hidráulico.
2. Confira o retorno da manete e o funcionamento do freio.
3. Verifique se a roda fica livre após a liberação do freio.
4. Substitua componentes fora das especificações e ajuste o sistema conforme o fabricante.
5. Faça teste funcional controlado antes de liberar o equipamento.

**Não entregue a scooter ao cliente se houver dúvida sobre a capacidade de frenagem.** A falha pode colocar o condutor e terceiros em risco.

# 9. Defeitos no chicote elétrico e nos conectores

## 9.1. Falha intermitente ao passar por buracos ou irregularidades

**Causas possíveis:**
- Conector frouxo.
- Cabo rompido internamente.
- Terminal mal crimpado.
- Chicote preso ou esmagado pela estrutura.
- Solda trincada.
- Vibração excessiva ou reparo anterior mal executado.

**Diagnóstico:**
- Procure marcas de atrito, dobras acentuadas e pontos de esmagamento.
- Inspecione conectores e travas.
- Com o sistema desenergizado, teste continuidade e isolamento conforme apropriado.
- Se necessário, reproduza a condição de forma controlada, sem movimentar cabos próximos a partes energizadas ou móveis.

**Reparo:** refazer a conexão com terminais, bitolas, isolamento e proteção mecânica apropriados. Em circuitos de potência, emendas inadequadas podem provocar aquecimento e incêndio.

## 9.2. Conector derretido ou escurecido

**Causas possíveis:**
- Contato elétrico deficiente.
- Corrente acima da capacidade do conector.
- Terminal mal crimpado.
- Oxidação.
- Componentes incompatíveis.
- Aquecimento prolongado.

**Conduta:**
- Interrompa o uso.
- Identifique a causa do aquecimento antes de substituir o conector.
- Verifique se o terminal, o cabo e o componente correspondente também foram danificados.
- Utilize peças dimensionadas para a corrente e a temperatura de operação.

**Não basta trocar o conector queimado:** se a causa for corrente excessiva ou conexão de alta resistência, o defeito poderá retornar.

# 10. Defeitos no display e na comunicação

## 10.1. Display apagado

**Causas possíveis:**
- Falta de alimentação.
- Cabo ou conector danificado.
- Falha no circuito de ignição.
- Display defeituoso.
- Incompatibilidade entre display e controlador.

**Diagnóstico:** confirme primeiro a alimentação prevista no conector. Se estiver correta, avalie o display e a comunicação com o controlador.

## 10.2. Display acende, mas apresenta códigos de erro

**Possíveis causas:**
- Falha no acelerador.
- Problema nos sensores Hall.
- Falha de comunicação.
- Subtensão ou sobretensão.
- Proteção térmica.
- Problema no controlador ou no motor.

**Procedimento:**
1. Fotografe ou anote o código.
2. Consulte o manual específico do modelo.
3. Confira conexões e componentes relacionados ao código.
4. Apague o erro apenas depois de corrigir a causa, quando o procedimento do fabricante permitir.
5. Confirme que a falha não retorna durante o teste final.

**Importante:** códigos semelhantes podem representar falhas diferentes entre fabricantes. Não utilize uma tabela genérica como diagnóstico definitivo.

# 11. Defeitos mecânicos que afetam a parte elétrica

## 11.1. Autonomia baixa e motor aparentemente fraco

Nem sempre o defeito está na bateria ou no motor.

**Causas mecânicas possíveis:**
- Pneus murchos.
- Freios arrastando.
- Rolamentos desgastados.
- Roda desalinhada.
- Excesso de carga.
- Suspensão ou transmissão com resistência anormal.

**Teste recomendado:**
- Inspecione a pressão dos pneus.
- Verifique se as rodas giram livremente.
- Observe se existe aquecimento anormal nos freios após um teste seguro.
- Confira folgas e alinhamento.
- Corrija a resistência mecânica antes de avaliar novamente a autonomia.

## 11.2. Vibração, folgas ou instabilidade

**Causas possíveis:**
- Pneus danificados.
- Roda desalinhada.
- Rolamentos desgastados.
- Parafusos soltos.
- Suspensão comprometida.
- Dano estrutural por impacto.

**Diagnóstico:** faça uma inspeção mecânica completa e verifique os pontos de fixação previstos pelo fabricante. Componentes estruturais e de direção exigem atenção especial.

**Não atribua automaticamente esses defeitos à falta de cuidado:** impactos, desgaste, montagem anterior inadequada ou defeitos de fabricação também podem ser responsáveis.

# 12. Entrada de água, umidade e corrosão

A exposição à água pode afetar o controlador, os conectores, o display, o motor, a bateria e os circuitos de recarga.

**Sintomas possíveis:**
- Scooter que parou após chuva ou lavagem.
- Display intermitente.
- Falhas que aparecem dias depois.
- Conectores esverdeados ou oxidados.
- Curto-circuito.
- Corrosão de placas e terminais.

**Diagnóstico:**
1. Pergunte ao cliente sobre chuva, lavagem, alagamento e armazenamento.
2. Inspecione os pontos de entrada de cabos e as vedações.
3. Procure sinais de umidade, depósitos minerais e corrosão.
4. Não energize imediatamente um equipamento com suspeita de água dentro dos circuitos.
5. Isole a bateria e siga o procedimento seguro de inspeção do fabricante.

**Reparo:** pode exigir limpeza técnica, substituição de conectores, reparo de placas ou troca de componentes corroídos. A limpeza superficial não garante que a corrosão interna foi eliminada.

**Relação com o proprietário:** lavar com jato de alta pressão, submergir o veículo ou ignorar limitações de resistência à água pode contribuir para a falha. Contudo, uma vedação defeituosa também pode permitir a entrada de água em uso normal.

# 13. Tabela rápida de diagnóstico

| Sintoma | Primeiras hipóteses | Primeira verificação |
|---|---|---|
| Não liga | Bateria, fusível, alimentação, chave ou BMS | Inspeção e tensão da bateria |
| Liga, mas não acelera | Sensor de freio, acelerador, controlador | Código de erro e sinais de comando |
| Desliga ao acelerar | Bateria degradada, mau contato, proteção | Queda de tensão sob carga |
| Autonomia baixa | Bateria, pneus, freios, rolamentos | Inspeção mecânica e avaliação da bateria |
| Não carrega | Carregador, entrada, BMS, bateria | Compatibilidade e teste do carregador |
| Motor dá trancos | Sensores, fases, controlador ou motor | Chicote, sinais e enrolamentos |
| Conector derretido | Mau contato ou sobrecorrente | Inspeção térmica e dimensionamento |
| Falha após chuva | Umidade, corrosão ou curto | Inspeção antes de energizar |
| Display apagado | Alimentação, chicote ou display | Alimentação e conectores |
| Freio arrasta | Pinça, disco, cabo ou ajuste | Giro livre e inspeção do freio |
| Ruído na roda | Rolamentos, fixação ou atrito | Rotação manual com sistema desligado |
| Aceleração inesperada | Acelerador, chicote ou controlador | Interromper uso e verificar segurança |

# 14. Como diferenciar mau uso, desgaste natural e falha técnica

Um diagnóstico profissional deve separar hipótese de causa comprovada.

| Categoria | Exemplos | Evidência que ajuda a confirmar |
|---|---|---|
| Mau uso ou uso fora das especificações | Sobrecarga, imersão em água, carregador incompatível | Danos físicos, registros de uso, sinais de entrada de água |
| Falta de manutenção | Pneus murchos, freios sem ajuste, conectores sem inspeção | Desgaste, folgas, componentes fora de ajuste |
| Desgaste natural | Bateria com capacidade reduzida, pastilhas gastas, rolamentos desgastados | Tempo de uso, quilometragem e medições |
| Falha elétrica | Controlador, BMS, sensor ou carregador defeituoso | Testes elétricos e códigos de erro |
| Falha de fabricação ou montagem | Solda defeituosa, crimpagem inadequada, vedação deficiente | Inspeção técnica, histórico e comparação com especificações |
| Causa combinada | Mau contato que aquece e danifica o controlador | Evidências de falha em cadeia |

**Regra técnica:** não responsabilize o proprietário apenas porque o equipamento chegou danificado. Registre evidências, medições e condições observadas. Algumas falhas possuem mais de uma causa.

# 15. Ficha de diagnóstico para preenchimento na oficina

## Identificação do equipamento
- Marca e modelo:
- Número de série:
- Potência nominal:
- Tensão nominal da bateria:
- Química da bateria:
- Tipo de motor:
- Modelo ou especificação do controlador:
- Quilometragem ou tempo estimado de uso:
- Data de entrada na oficina:

## Relato do cliente
- Qual é o sintoma principal?
- Quando o defeito começou?
- A falha é constante ou intermitente?
- O problema aparece ao acelerar, frear, carregar ou passar por irregularidades?
- O equipamento sofreu queda ou impacto?
- Houve exposição à chuva, lavagem ou umidade?
- Foi utilizado carregador diferente do original?
- Alguma peça já foi substituída ou reparada?

## Inspeção inicial
- [ ] Estado externo e sinais de impacto
- [ ] Pneus e rodas
- [ ] Freios e retorno das manetes
- [ ] Cabos e conectores
- [ ] Entrada de recarga
- [ ] Sinais de aquecimento
- [ ] Sinais de umidade ou corrosão
- [ ] Display e códigos de erro
- [ ] Estado físico da bateria

## Testes realizados
| Teste | Resultado | Conclusão |
|---|---|---|
| Inspeção da bateria | | |
| Verificação do carregador | | |
| Verificação dos fusíveis | | |
| Inspeção do chicote | | |
| Teste do acelerador | | |
| Teste dos sensores de freio | | |
| Diagnóstico do controlador | | |
| Diagnóstico do motor | | |
| Verificação mecânica das rodas | | |
| Teste funcional final | | |

## Conclusão técnica
- Defeito confirmado:
- Causa provável:
- Evidências encontradas:
- Peças que precisam de reparo ou substituição:
- Testes pendentes:
- Condição de segurança do equipamento:
- Recomendações ao cliente:

# 16. Segurança durante o diagnóstico

Scooters de 1.000 W podem trabalhar com correntes elevadas, mesmo quando a tensão parece relativamente baixa.

1. **Bateria:** evite curto-circuitos, perfuração, esmagamento e abertura de conjuntos de células sem treinamento específico.
2. **Controlador:** capacitores podem armazenar energia após a desconexão da bateria.
3. **Medições:** utilize instrumentos, pontas de prova e equipamentos de proteção adequados à tensão e à corrente envolvidas.
4. **Roda motorizada:** mantenha a roda suspensa e a área livre quando forem necessários testes de rotação. Evite roupas, mãos e ferramentas próximas a partes móveis.
5. **Freios:** não libere o equipamento sem verificar a capacidade de frenagem.
6. **Acelerador:** confirme que a resposta é previsível e que o sistema retorna ao repouso.
7. **Água:** não energize placas ou baterias suspeitas de contaminação por umidade sem inspeção.
8. **Baterias danificadas:** não recarregue baterias estufadas, perfuradas, fumegantes ou com aquecimento anormal.

# 17. Sequência recomendada de diagnóstico

Para reduzir o tempo de serviço e evitar a troca desnecessária de peças, siga esta ordem:

1. Registrar o sintoma e o histórico do cliente.
2. Identificar marca, modelo, tensão e arquitetura elétrica.
3. Fazer inspeção visual e mecânica.
4. Verificar bateria, carregador e conexões principais.
5. Registrar códigos de erro.
6. Testar os comandos de acelerador e freio.
7. Investigar controlador, chicote, sensores e motor conforme as evidências.
8. Corrigir a causa comprovada.
9. Executar testes funcionais e de segurança.
10. Registrar os resultados e explicar ao cliente o que foi encontrado.

Não substitua a bateria, o controlador ou o motor apenas porque são componentes frequentemente envolvidos em falhas. Confirme primeiro a hipótese com medições e testes apropriados.

# 18. Conclusão

Os defeitos de uma scooter elétrica de 1.000 W podem ter origem elétrica, eletrônica, mecânica, ambiental ou em uma combinação desses fatores.

Os sistemas que merecem atenção especial no diagnóstico inicial são:

- Bateria e BMS.
- Carregador e circuito de recarga.
- Controlador eletrônico.
- Motor e sensores.
- Acelerador e sensores de freio.
- Chicote e conectores de potência.
- Freios, pneus, rodas e rolamentos.

O melhor técnico não é aquele que troca mais peças rapidamente, mas aquele que **identifica a causa real, demonstra a falha com evidências e entrega o equipamento seguro para uso**.

Este relatório deve ser utilizado como referência geral. Os valores de tensão, corrente, resistência, pinagem, códigos de erro e procedimentos específicos precisam ser confirmados no manual e no esquema elétrico do modelo atendido.
