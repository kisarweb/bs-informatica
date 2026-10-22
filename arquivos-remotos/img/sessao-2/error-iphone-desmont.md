# RELATÓRIO TÉCNICO DE DIAGNÓSTICO
## Apple iPhone — Defeitos recorrentes, causas, testes e procedimentos de reparo

**Categoria:** Smartphone  
**Fabricante:** Apple  
**Finalidade:** Manual de apoio ao diagnóstico eletrônico e à manutenção de iPhones  
**Público-alvo:** Técnicos de eletrônica, microsoldagem e assistência técnica de smartphones

---

# 1. Objetivo do relatório

Este documento apresenta os defeitos mais recorrentes em iPhones e orienta o técnico na identificação de suas possíveis causas.

O relatório abrange:

- Bateria e circuito de alimentação.
- Falhas de carregamento.
- Tela, imagem e touchscreen.
- Câmeras e sensores.
- Áudio, microfones e alto-falantes.
- Botões e cabos flexíveis.
- Face ID e Touch ID.
- Placa lógica e componentes eletrônicos.
- Danos por líquidos e impactos.
- Conectividade Wi-Fi, Bluetooth e rede móvel.
- Diagnóstico, reparo e testes finais.

**Princípio fundamental:** o sintoma não comprova qual componente está defeituoso. Um iPhone que não carrega pode apresentar uma porta danificada, bateria degradada, falha de comunicação com o circuito de carga, problema na alimentação ou defeito na placa lógica.

Antes de abrir o equipamento, identifique o modelo, registre os sintomas e faça os testes externos possíveis.

# 2. Conhecendo os principais sistemas do iPhone

A arquitetura varia conforme a geração. Os componentes abaixo são grupos funcionais gerais, não uma lista idêntica para todos os modelos.

| Sistema | Componentes principais | Função |
|---|---|---|
| Alimentação | Bateria de íons de lítio, conectores e circuitos de gerenciamento | Fornecer e controlar a energia |
| Recarga | Porta Lightning ou USB-C, circuito de carga e bobina sem fio nos modelos compatíveis | Recarregar a bateria |
| Placa lógica | Processador, memória, circuitos integrados e componentes passivos | Executar o sistema e controlar as funções |
| Tela | Painel OLED ou LCD, conforme o modelo, e digitalizador | Exibir imagens e reconhecer toques |
| Câmeras | Módulos frontal e traseiros | Capturar fotos e vídeos |
| Biometria | Face ID ou Touch ID, conforme o modelo | Autenticar o usuário |
| Áudio | Microfones, alto-falantes e circuitos associados | Captar e reproduzir som |
| Conectividade | Antenas, circuitos de rádio e módulos associados | Permitir comunicação celular, Wi-Fi e Bluetooth |
| Sensores | Proximidade, luz ambiente, giroscópio, acelerômetro e outros | Detectar condições e movimentos |
| Estrutura | Gabinete, vidro, vedações, parafusos e adesivos | Proteger e sustentar os componentes |

---

# 3. Defeitos na bateria

## 3.1. A bateria descarrega rapidamente

**Sintomas:**
- O cliente precisa recarregar o iPhone várias vezes por dia.
- A porcentagem diminui rapidamente.
- O aparelho desliga mesmo indicando carga restante.
- A autonomia piorou depois de um período de uso.

**Causas possíveis:**
1. Degradação natural das células.
2. Aplicativos consumindo energia excessiva.
3. Sinal de rede fraco, exigindo maior esforço de comunicação.
4. Temperatura elevada.
5. Falha de software ou processo executado em segundo plano.
6. Bateria de reposição inadequada ou defeituosa.
7. Consumo elétrico anormal causado por um componente ou circuito.

**Procedimento de diagnóstico:**

1. Abra Ajustes e consulte a seção de saúde da bateria, quando disponível.
2. Verifique se há alertas de desempenho ou consumo anormal.
3. Investigue se o problema começou após uma atualização, instalação de aplicativo ou reparo.
4. Compare o consumo em condições de uso semelhantes.
5. Se houver suspeita de falha física, faça uma avaliação técnica da bateria.
6. Se uma bateria comprovadamente funcional não resolver, investigue o consumo do aparelho e os circuitos de alimentação.

**Soluções possíveis:**
- Corrigir configurações ou processos que provoquem consumo excessivo.
- Atualizar ou restaurar o software quando houver evidência de problema de software e após preservar os dados.
- Substituir a bateria se sua degradação estiver confirmada.
- Investigar consumo anormal na placa lógica quando o problema persistir.

**É culpa do proprietário?**

Não necessariamente. Todas as baterias recarregáveis sofrem desgaste natural. Calor excessivo, armazenamento inadequado e determinados hábitos de uso podem acelerar a degradação, mas uma bateria também pode apresentar defeito prematuro.

## 3.2. O iPhone desliga com carga restante

**Causas possíveis:**
- Bateria com resistência interna elevada.
- Queda de tensão durante picos de consumo.
- Bateria incompatível ou defeituosa.
- Problema no conector da bateria.
- Falha no circuito de gerenciamento de energia.

**Diagnóstico:**
1. Registre a porcentagem indicada quando ocorre o desligamento.
2. Verifique a saúde e as mensagens de diagnóstico da bateria.
3. Observe se o problema aparece durante câmera, jogos, chamadas ou outras atividades de maior consumo.
4. Inspecione o conector e o estado físico da bateria.
5. Se necessário, faça testes com equipamento de diagnóstico e uma bateria compatível comprovadamente funcional.

**Reparo:** substituir a bateria se os testes confirmarem a falha. Caso contrário, investigar o circuito de alimentação e a placa lógica.

## 3.3. A bateria está estufada

**Sinais:**
- Tela ou vidro traseiro levantado.
- Gabinete deformado.
- Pressão interna aparente.
- Aquecimento ou cheiro incomum.

**Causas possíveis:**
- Degradação interna.
- Danos físicos.
- Exposição a calor excessivo.
- Defeito de fabricação.
- Problemas relacionados à recarga ou à própria célula.

**Conduta obrigatória:**
- Interrompa o uso e a recarga.
- Não pressione, dobre, perfure ou tente achatar a bateria.
- Não utilize calor para tentar removê-la.
- Isole o aparelho conforme o procedimento de segurança da oficina e encaminhe a bateria para manuseio especializado.

Uma bateria estufada não deve ser tratada como um simples defeito estético.

---

# 4. Defeitos no sistema de carregamento

## 4.1. O iPhone não carrega

**Sintomas:**
- Não aparece o símbolo de carga.
- A bateria continua descarregada.
- O cabo precisa ficar em determinada posição.
- O aparelho reconhece o carregador, mas não aumenta a carga.

**Causas possíveis:**
- Cabo ou adaptador defeituoso.
- Sujeira na porta de carregamento.
- Porta Lightning ou USB-C danificada.
- Bateria degradada.
- Circuito de carga defeituoso.
- Conector interno danificado.
- Falha na placa lógica.
- Umidade nos contatos.

**Sequência de diagnóstico:**

1. Teste uma fonte de alimentação e um cabo compatíveis e comprovadamente funcionais.
2. Inspecione a porta de carregamento com iluminação e ampliação.
3. Procure resíduos compactados, corrosão ou danos físicos.
4. Verifique se o aparelho apresenta alerta de líquido.
5. Se os acessórios e a porta estiverem em boas condições, avalie a bateria.
6. Persistindo o defeito, examine o conjunto da porta, seus cabos flexíveis e o circuito de carga.
7. Se necessário, investigue a placa lógica.

**Reparo possível:**
- Substituir cabo ou adaptador defeituoso.
- Fazer limpeza técnica apropriada.
- Substituir o conjunto da porta quando a falha estiver confirmada.
- Reparar o circuito de alimentação ou substituir a bateria conforme o diagnóstico.

Não troque a porta de carregamento automaticamente. Em alguns modelos, a falha pode estar na bateria ou na placa lógica.

## 4.2. O carregamento é intermitente

**Causas possíveis:**
- Cabo danificado.
- Porta desgastada.
- Resíduos nos contatos.
- Conector interno frouxo.
- Solda ou conexão defeituosa.
- Oxidação após contato com líquido.

**Diagnóstico:**
- Teste outro cabo compatível.
- Inspecione a porta sem introduzir objetos metálicos.
- Verifique se a falha ocorre com acessórios diferentes.
- Examine os conectores internos quando a inspeção externa não for suficiente.

**Atenção:** não force o cabo nem movimente repetidamente o conector para manter a carga. Isso pode agravar o dano.

## 4.3. O iPhone para de carregar em 80%

**Possíveis explicações:**
- Carregamento otimizado.
- Limite de carga configurado nos modelos compatíveis.
- Temperatura elevada.
- Restrição temporária de carregamento para proteger a bateria.

**Diagnóstico:**
1. Consulte os ajustes de bateria e limite de carga disponíveis no modelo.
2. Verifique se o aparelho está quente.
3. Deixe o dispositivo retornar a uma temperatura adequada.
4. Investigue uma falha física somente se o comportamento persistir sem explicação pelas configurações ou condições térmicas.

**Importante:** parar em 80% não significa automaticamente que a bateria ou o circuito de carga esteja defeituoso.

## 4.4. O iPhone apresenta alerta de líquido no conector

**Possíveis causas:**
- Umidade no conector.
- Cabo molhado.
- Resíduos condutivos.
- Corrosão ou dano no conjunto da porta.

**Conduta:**
- Desconecte o cabo.
- Não force o carregamento por cabo enquanto houver umidade.
- Deixe o aparelho em local seco, com circulação de ar.
- Não utilize arroz, calor externo ou ar comprimido.
- Inspecione tecnicamente se o alerta persistir após a secagem adequada.

Se o modelo oferecer carregamento sem fio, ele só deve ser considerado quando a parte traseira estiver seca e não houver outros sinais de dano por líquido.

---

# 5. Defeitos na tela e no touchscreen

## 5.1. Tela quebrada

**Causas possíveis:**
- Queda.
- Impacto direto.
- Pressão excessiva no bolso ou na bolsa.
- Torção do aparelho.
- Defeito estrutural anterior.

**Diagnóstico:**
- Verifique a extensão das rachaduras.
- Teste a imagem, o toque e o brilho.
- Procure manchas, linhas, cintilação ou áreas sem resposta.
- Verifique se o gabinete está deformado.
- Inspecione a bateria se a tela estiver levantada.

**Reparo:** substituir o conjunto apropriado da tela. O tipo de componente e o procedimento variam conforme o modelo.

Uma tela rachada pode continuar exibindo imagem, mas isso não comprova que o digitalizador ou os componentes internos estejam íntegros.

## 5.2. A tela fica preta, mas o aparelho parece ligado

**Sintomas:**
- O telefone vibra ou toca, mas não exibe imagem.
- O computador reconhece o dispositivo.
- A tela permanece preta após a inicialização.

**Causas possíveis:**
- Painel OLED ou LCD danificado.
- Cabo flexível da tela danificado.
- Conector da tela com problema.
- Falha de alimentação do display.
- Defeito na placa lógica.
- Sistema operacional travado.

**Diagnóstico:**
1. Faça o procedimento de reinicialização forçada apropriado ao modelo.
2. Verifique sinais de funcionamento, como vibração, sons e reconhecimento pelo computador.
3. Inspecione o histórico de quedas e reparos.
4. Com o aparelho desligado e aberto de forma segura, examine os conectores.
5. Se necessário, utilize uma tela de teste comprovadamente compatível.
6. Se a falha persistir, investigue o circuito de imagem na placa.

**Não conclua que a tela está queimada apenas porque não há imagem.**

## 5.3. O touchscreen não responde

**Causas possíveis:**
- Digitalizador danificado.
- Tela de reposição defeituosa.
- Conector mal encaixado.
- Pressão mecânica ou deformação.
- Umidade.
- Falha de software.
- Problema no circuito de leitura do toque.

**Diagnóstico:**
- Teste diferentes áreas da tela.
- Verifique se o problema é constante ou intermitente.
- Reinicie o aparelho quando possível.
- Investigue se o defeito começou após uma troca de tela.
- Examine a conexão e teste um conjunto compatível, quando necessário.

**Solução:** corrigir o problema de software, reinstalar corretamente o conjunto ou substituir a tela defeituosa.

## 5.4. A tela apresenta linhas, manchas ou cintilação

**Causas possíveis:**
- Painel danificado por impacto.
- Pressão sobre a tela.
- Falha no circuito do display.
- Conector danificado.
- Tela de reposição defeituosa.
- Problema na placa lógica.

**Diagnóstico:** compare o comportamento em diferentes níveis de brilho, verifique o histórico de impacto e avalie o conjunto de tela antes de investigar a placa.

Se houver manchas que aumentam ou linhas após uma queda, suspeite de dano físico no painel.

---

# 6. Defeitos nas câmeras

## 6.1. A câmera traseira não abre ou apresenta tela preta

**Causas possíveis:**
- Módulo de câmera danificado.
- Conector flexível desconectado.
- Dano por queda.
- Falha de software.
- Falha na alimentação ou comunicação do módulo.
- Defeito na placa lógica.

**Diagnóstico:**
1. Teste as câmeras disponíveis no aparelho.
2. Verifique se a falha ocorre em todos os modos ou apenas em uma lente.
3. Reinicie o aplicativo e o aparelho.
4. Inspecione o histórico de quedas e reparos.
5. Examine os conectores e, quando necessário, teste um módulo compatível.
6. Se a falha persistir, investigue os circuitos associados na placa.

## 6.2. Fotos desfocadas ou câmera tremendo

**Causas possíveis:**
- Lente suja ou riscada.
- Mecanismo de estabilização óptica danificado, quando presente.
- Autofoco defeituoso.
- Impacto no módulo.
- Vibração excessiva externa.
- Módulo de câmera com falha.

**Diagnóstico:**
- Limpe externamente a lente com material adequado.
- Teste diferentes distâncias e condições de iluminação.
- Verifique se o foco falha constantemente.
- Observe se a imagem vibra sem movimentar o aparelho.
- Inspecione o módulo caso o problema tenha começado após uma queda.

**Atenção:** vibrações intensas de veículos e suportes podem danificar o sistema de estabilização de determinadas câmeras.

## 6.3. A câmera frontal não funciona

**Causas possíveis:**
- Módulo frontal danificado.
- Cabo flexível rompido.
- Dano após troca de tela.
- Conector defeituoso.
- Problema em componentes associados ao sistema TrueDepth, nos modelos compatíveis.

**Diagnóstico:** verifique a câmera frontal, os sensores associados e o histórico de reparos. Se o Face ID também falhar, investigue o conjunto frontal com especial cuidado.

Não trate o módulo da câmera frontal e o sistema Face ID como se fossem sempre um único componente.

---

# 7. Defeitos no Face ID e no Touch ID

## 7.1. O Face ID parou de funcionar

**Causas possíveis:**
- Dano em componentes do conjunto TrueDepth.
- Impacto na região frontal.
- Dano por líquido.
- Reparo anterior que afetou sensores ou conexões.
- Falha de software ou configuração.
- Defeito eletrônico em componentes associados.

**Diagnóstico:**
1. Verifique as mensagens exibidas nas configurações.
2. Confirme se o Face ID está configurado corretamente.
3. Teste a câmera frontal.
4. Investigue quedas, umidade e substituição de tela.
5. Inspecione as conexões conforme o manual de serviço do modelo.

**Reparo:** depende do componente afetado e da arquitetura específica. Alguns componentes biométricos são vinculados ao dispositivo ou exigem procedimentos específicos de configuração e calibração.

**Regra importante:** não substitua ou manipule componentes biométricos sem conhecer as exigências do modelo. Uma troca inadequada pode impedir a recuperação do Face ID.

## 7.2. O Touch ID não reconhece a impressão digital

Aplica-se aos modelos equipados com Touch ID.

**Causas possíveis:**
- Sensor danificado.
- Botão ou cabo flexível com defeito.
- Problema de configuração.
- Umidade ou sujeira.
- Dano ocorrido durante reparo.

**Diagnóstico:**
- Teste a leitura e as configurações.
- Verifique o estado físico do botão.
- Examine o cabo e os conectores.
- Confirme se houve troca anterior da tela ou do conjunto do botão.

A possibilidade de reparo ou substituição depende do modelo e da relação entre o sensor e o dispositivo. Não prometa recuperar a biometria apenas com a troca do botão.

---

# 8. Defeitos no áudio e nos microfones

## 8.1. O cliente não ouve durante chamadas

**Causas possíveis:**
- Alto-falante auricular obstruído ou danificado.
- Cabo flexível com problema.
- Defeito no circuito de áudio.
- Roteamento de áudio para outro dispositivo.
- Falha de software.

**Diagnóstico:**
1. Teste chamadas com e sem viva-voz.
2. Verifique se o áudio funciona com fones ou dispositivos Bluetooth.
3. Inspecione a grade do alto-falante.
4. Confirme o roteamento de áudio.
5. Se necessário, examine o conjunto auricular e os circuitos associados.

## 8.2. O microfone não capta a voz

**Causas possíveis:**
- Microfone obstruído.
- Cabo flexível danificado.
- Dano por líquido.
- Falha de um dos microfones.
- Problema de software ou aplicativo.
- Defeito na placa lógica.

**Diagnóstico:**
- Teste gravação de voz.
- Teste vídeo com as câmeras frontal e traseira.
- Compare chamadas normais e viva-voz.
- Verifique se a falha ocorre em todos os aplicativos.
- Inspecione os microfones e seus caminhos de conexão.

**Observação:** diferentes funções podem utilizar microfones distintos. Um microfone funcionando não comprova que todos estejam bons.

## 8.3. O alto-falante apresenta chiado ou volume baixo

**Causas possíveis:**
- Poeira ou resíduos na grade.
- Umidade.
- Alto-falante danificado.
- Cabo ou contato defeituoso.
- Falha no circuito de áudio.

**Solução:** faça limpeza externa apropriada, teste o módulo e substitua o componente somente quando houver evidência de defeito físico.

Não introduza objetos metálicos ou líquidos nas aberturas de áudio.

---

# 9. Defeitos nos botões e cabos flexíveis

## 9.1. Botão lateral ou de volume não responde

**Causas possíveis:**
- Botão mecanicamente danificado.
- Cabo flexível rompido.
- Oxidação.
- Conector mal encaixado.
- Falha no circuito associado.

**Diagnóstico:**
1. Verifique se o botão está preso ou deformado.
2. Teste sua resposta no sistema.
3. Inspecione o cabo flexível e os conectores.
4. Avalie o conjunto antes de substituir componentes.

## 9.2. O aparelho reinicia ao pressionar um botão ou movimentar o gabinete

**Causas possíveis:**
- Conector da bateria com contato intermitente.
- Cabo flexível danificado.
- Solda trincada.
- Placa lógica deformada ou danificada.
- Reparação anterior inadequada.

**Diagnóstico:** registre quando ocorre a falha, inspecione os conectores e verifique a integridade física. Evite flexionar a placa para reproduzir o defeito, pois isso pode agravar danos.

---

# 10. Defeitos de conectividade

## 10.1. Wi-Fi não ativa ou apresenta conexão instável

**Causas possíveis:**
- Falha de software.
- Configuração de rede incorreta.
- Antena ou conexão danificada.
- Dano por impacto ou líquido.
- Defeito no circuito de rádio da placa lógica.

**Diagnóstico:**
1. Teste outras redes.
2. Reinicie o aparelho.
3. Verifique se o Wi-Fi ativa normalmente.
4. Avalie se o Bluetooth apresenta sintomas relacionados.
5. Inspecione antenas e conexões se houver histórico de queda ou abertura.
6. Investigue a placa se as verificações anteriores não resolverem.

## 10.2. Bluetooth não funciona

**Causas possíveis:**
- Configuração ou falha de software.
- Problema com um acessório específico.
- Antena ou conexão danificada.
- Defeito no circuito de rádio.

**Diagnóstico:** teste diferentes acessórios, confirme se a função ativa normalmente e compare o comportamento com o Wi-Fi. Sintomas simultâneos podem ajudar a direcionar a investigação, mas não comprovam uma causa comum.

## 10.3. O iPhone não reconhece o chip ou fica sem sinal

**Causas possíveis:**
- SIM danificado ou mal instalado, quando aplicável.
- Problema na bandeja ou nos contatos.
- Falha na antena.
- Dano no circuito de radiofrequência.
- Problema de provisionamento da operadora.
- Falha de software.
- Defeito na placa lógica.

**Diagnóstico:**
1. Confirme se há interrupção de serviço da operadora.
2. Teste o SIM em outro aparelho compatível, quando possível.
3. Verifique os ajustes e as informações de rede.
4. Inspecione a bandeja e os contatos.
5. Se necessário, investigue antenas, conectores e circuito de rádio.

Nos modelos com eSIM, o procedimento de diagnóstico será diferente do utilizado em modelos com SIM físico.

---

# 11. Defeitos na placa lógica

A placa lógica concentra grande parte dos circuitos do iPhone. Problemas nessa área podem afetar diversas funções ao mesmo tempo.

## 11.1. O iPhone não liga

**Causas possíveis:**
- Bateria descarregada ou defeituosa.
- Conector da bateria danificado.
- Falha no circuito de alimentação.
- Curto-circuito em uma linha de alimentação.
- Dano por líquido.
- Componente eletrônico danificado.
- Falha de software ou inicialização.

**Sequência de diagnóstico:**
1. Inspecione o aparelho e procure sinais de impacto, umidade ou deformação.
2. Verifique se a bateria apresenta sinais de dano.
3. Teste o carregamento com acessórios compatíveis.
4. Realize o procedimento de reinicialização forçada apropriado ao modelo.
5. Observe se o aparelho é reconhecido por um computador ou apresenta outros sinais de atividade.
6. Se os testes externos não resolverem, faça diagnóstico elétrico especializado.
7. Investigue consumo de corrente, linhas de alimentação e componentes da placa utilizando esquema e procedimentos adequados ao modelo.

**Não conclua que a placa está queimada antes de verificar bateria, conectores e alimentação.**

## 11.2. O iPhone reinicia repetidamente

**Causas possíveis:**
- Bateria degradada.
- Falha em sensor ou conjunto periférico.
- Problema de software.
- Dano por líquido.
- Defeito na placa lógica.
- Conector intermitente.
- Falha ocorrida após reparo.

**Diagnóstico:**
1. Registre a frequência e o momento dos reinícios.
2. Verifique a bateria e as mensagens de saúde.
3. Examine os registros de análise disponíveis no iOS, quando acessíveis.
4. Observe se o problema começou após atualização ou troca de peça.
5. Faça backup se o aparelho ainda permitir.
6. Investigue hardware se os reinícios persistirem após as verificações de software.

Os registros de reinicialização podem oferecer pistas, mas não devem ser interpretados isoladamente como prova de um componente defeituoso.

## 11.3. A placa apresenta consumo anormal

**Sintomas:**
- Bateria descarrega mesmo com pouco uso.
- Aparelho aquece em repouso.
- A bateria perde carga com o aparelho desligado.
- O dispositivo apresenta comportamento intermitente.

**Causas possíveis:**
- Componente em fuga elétrica.
- Curto parcial em uma linha de alimentação.
- Circuito integrado defeituoso.
- Corrosão.
- Acessório interno com falha.
- Problema de software ou atividade de rede.

**Diagnóstico avançado:**
- Diferencie consumo de software de consumo elétrico anormal.
- Compare o comportamento com o histórico do aparelho.
- Faça inspeção microscópica se houver indícios de líquido ou reparo anterior.
- Utilize equipamentos de diagnóstico apropriados para avaliar o consumo.
- Consulte a documentação técnica do modelo antes de medir ou injetar tensão em linhas da placa.

**Atenção:** injeção de tensão inadequada pode destruir componentes, danificar linhas de alimentação ou causar aquecimento perigoso. Esse procedimento exige treinamento, limites elétricos conhecidos e instrumentação apropriada.

## 11.4. O aparelho aquece excessivamente

**Causas possíveis:**
- Aplicativos ou processos de alto consumo.
- Sinal de rede fraco.
- Recarga em condições térmicas desfavoráveis.
- Bateria defeituosa.
- Curto parcial ou falha na placa.
- Componente danificado após contato com líquido.

**Diagnóstico:**
1. Identifique quando o aquecimento ocorre.
2. Diferencie aquecimento durante atividades intensas de aquecimento em repouso.
3. Verifique os ajustes de bateria e os processos de maior consumo.
4. Inspecione a bateria e o histórico de reparos.
5. Se houver aquecimento intenso em repouso, cheiro, deformação ou sinais de dano físico, interrompa o uso e investigue com segurança.

Não condene um circuito integrado apenas por sua temperatura. A avaliação deve considerar o modelo, a carga de trabalho e as condições de operação.

---

# 12. Danos causados por líquidos

## 12.1. O iPhone caiu na água ou foi molhado

**Possíveis consequências:**
- Corrosão de conectores.
- Curto-circuito.
- Falha no carregamento.
- Defeito em microfones e alto-falantes.
- Falha de sensores ou câmeras.
- Danos na placa lógica.
- Falhas que aparecem dias ou semanas depois.

**Procedimento inicial:**
1. Desconecte cabos e acessórios.
2. Não carregue o aparelho enquanto houver suspeita de umidade.
3. Não utilize arroz, secador quente ou ar comprimido.
4. Registre o relato do cliente e inspecione os indicadores e as áreas acessíveis.
5. Se houver suspeita de entrada interna de líquido, encaminhe para inspeção técnica antes de energizar repetidamente.
6. Avalie a corrosão, os conectores e a placa conforme o procedimento específico do modelo.

**Importante:** um iPhone voltar a ligar após secar não significa que o problema foi resolvido. A corrosão pode continuar provocando falhas posteriormente.

## 12.2. O aparelho apresenta defeitos dias depois do contato com água

**Causas possíveis:**
- Corrosão progressiva.
- Resíduos condutivos.
- Conexões comprometidas.
- Deterioração de componentes.
- Curto-circuitos intermitentes.

**Diagnóstico:** registre a relação temporal com a exposição a líquido, inspecione cuidadosamente a placa e os conectores e faça testes funcionais dos subsistemas afetados.

A limpeza superficial externa não elimina necessariamente a corrosão interna.

---

# 13. Defeitos após troca de tela, bateria ou outra peça

## 13.1. O aparelho apresenta falhas depois de um reparo

**Causas possíveis:**
- Conector mal encaixado.
- Cabo flexível danificado durante a abertura.
- Parafuso instalado no local errado.
- Peça incompatível ou defeituosa.
- Vedação não restaurada.
- Falta de procedimento de calibração ou configuração.
- Dano acidental na placa.

**Procedimento de diagnóstico:**
1. Registre exatamente quais funções deixaram de funcionar.
2. Compare os sintomas antes e depois do reparo.
3. Inspecione os componentes envolvidos no serviço realizado.
4. Verifique conectores e flexíveis com ampliação.
5. Confirme a compatibilidade da peça.
6. Consulte o manual de serviço para saber se o modelo exige calibração, pareamento ou finalização do reparo.

**Regra profissional:** após substituir uma peça, teste as funções relacionadas e também as funções que podem ter sido afetadas pela desmontagem.

## 13.2. Aparece mensagem de peça desconhecida ou informação de peça não verificada

**Possíveis causas:**
- Componente não original.
- Peça usada ou incompatível.
- Falha na verificação do componente.
- Reparo não finalizado por um procedimento de configuração exigido.
- Peça com defeito.

A mensagem, por si só, não comprova que a peça seja falsa nem que esteja necessariamente inutilizável. É preciso interpretar o aviso conforme o componente, o modelo e a versão do iOS.

Alguns modelos permitem concluir procedimentos de reparo e configuração por ferramentas específicas da Apple. Consulte a documentação do aparelho antes de prometer que o aviso desaparecerá.

---

# 14. Defeitos no vidro traseiro e no gabinete

## 14.1. Vidro traseiro quebrado

**Causas possíveis:**
- Queda.
- Impacto.
- Pressão mecânica.
- Torção do gabinete.

**Riscos adicionais:**
- Perda de vedação.
- Exposição a partículas e umidade.
- Danos a componentes próximos.
- Risco de cortes durante o manuseio.

**Diagnóstico e reparo:**
- Inspecione o gabinete e a estrutura.
- Verifique se há deformação.
- Examine a área das câmeras e os componentes internos.
- Utilize o procedimento de substituição adequado ao modelo.
- Reavalie a vedação e as funções afetadas após o reparo.

A resistência original à água não deve ser presumida após a abertura ou a substituição de vidros e vedações.

---

# 15. Tabela rápida de diagnóstico

| Sintoma | Hipóteses iniciais | Primeira verificação |
|---|---|---|
| Não liga | Bateria, alimentação, placa ou software | Teste de carga e reinicialização apropriada |
| Não carrega | Cabo, porta, bateria ou circuito de carga | Acessório compatível e inspeção da porta |
| Descarrega rápido | Bateria, software ou consumo anormal | Saúde da bateria e consumo |
| Desliga com carga restante | Bateria ou alimentação | Avaliação da bateria sob condições adequadas |
| Tela preta | Tela, conexão ou placa | Verificar se o aparelho continua ativo |
| Touchscreen falha | Tela, conexão ou circuito de toque | Teste por regiões e inspeção do conjunto |
| Câmera preta | Módulo, conexão ou placa | Testar as diferentes câmeras |
| Face ID não funciona | Conjunto TrueDepth, software ou conexões | Mensagem do sistema e histórico de reparos |
| Sem áudio em chamadas | Auricular, microfone, roteamento ou placa | Teste de chamada e viva-voz |
| Sem sinal | Operadora, SIM/eSIM, antena ou rádio | Testar SIM e informações de rede |
| Wi-Fi não ativa | Software, antena ou placa | Teste de configuração e conectividade |
| Reinicia sozinho | Bateria, software, periférico ou placa | Registros e histórico da falha |
| Aquece em repouso | Consumo anormal ou falha elétrica | Avaliação térmica e consumo |
| Falha após água | Corrosão e curto-circuito | Inspeção técnica antes de energizar |
| Falha após troca de tela | Conector, flexível, peça ou configuração | Revisar o reparo realizado |
| Porta funciona só em certo ângulo | Porta ou cabo | Teste cruzado e inspeção do conector |

---

# 16. Como diferenciar desgaste, mau uso e falha técnica

| Categoria | Exemplos | Evidências úteis |
|---|---|---|
| Desgaste natural | Bateria degradada, desgaste de conectores | Histórico, ciclos e medições |
| Dano acidental | Tela quebrada, gabinete deformado | Inspeção física |
| Exposição ambiental | Corrosão após entrada de líquido | Resíduos e sinais de corrosão |
| Falha de software | Consumo elevado após atualização ou aplicativo | Registros e testes controlados |
| Falha de componente | Bateria, câmera, tela ou circuito defeituoso | Testes funcionais e elétricos |
| Falha de reparo | Flexível danificado ou conector mal encaixado | Comparação com o estado anterior |
| Falha de fabricação | Defeito prematuro ou problema de montagem | Evidências técnicas e histórico |
| Causa combinada | Líquido provoca corrosão que danifica outro circuito | Inspeção e medições |

**Não responsabilize o cliente apenas porque o iPhone apresenta dano.** Um aparelho pode falhar sem queda, sem contato com líquido e sem uso inadequado.

Da mesma forma, não atribua automaticamente todo defeito à placa lógica. O diagnóstico deve ser baseado em evidências.

---

# 17. Ficha de diagnóstico para a assistência técnica

## Identificação do aparelho

- Modelo:
- Número do modelo:
- Versão do iOS:
- Capacidade de armazenamento:
- Estado físico:
- Saúde da bateria, quando disponível:
- Histórico de reparos:
- Data de entrada na assistência:

## Relato do cliente

- Qual é o sintoma principal?
- Quando o problema começou?
- O aparelho sofreu queda?
- Houve contato com líquido?
- A falha começou após uma atualização?
- Alguma peça foi substituída anteriormente?
- O aparelho aquece ou reinicia?
- O cliente possui backup dos dados?

## Inspeção inicial

- [ ] Tela e vidro traseiro
- [ ] Gabinete e deformações
- [ ] Estado físico da bateria
- [ ] Porta de carregamento
- [ ] Câmeras
- [ ] Microfones e alto-falantes
- [ ] Botões
- [ ] Conectividade
- [ ] Sinais de umidade ou corrosão
- [ ] Histórico de peças e serviços
- [ ] Alertas ou códigos de diagnóstico disponíveis

## Registro dos testes

| Teste | Resultado | Conclusão |
|---|---|---|
| Carregamento | | |
| Saúde da bateria | | |
| Inicialização | | |
| Tela e touchscreen | | |
| Câmeras | | |
| Microfones e alto-falantes | | |
| Wi-Fi e Bluetooth | | |
| Rede móvel | | |
| Face ID ou Touch ID | | |
| Inspeção interna, se necessária | | |
| Diagnóstico da placa, se necessário | | |
| Teste funcional final | | |

## Conclusão técnica

- Defeito confirmado:
- Causa provável:
- Evidências encontradas:
- Peça ou circuito afetado:
- Reparo recomendado:
- Riscos adicionais:
- Testes pendentes:
- Estado dos dados e backup:
- Resultado após o reparo:

---

# 18. Segurança e preservação dos dados

1. Antes de abrir o aparelho, registre o estado físico e os sintomas.
2. Solicite autorização para procedimentos que possam afetar os dados.
3. Não restaure o sistema sem avaliar a necessidade e as consequências para os dados do cliente.
4. Desconecte a bateria de acordo com o procedimento de serviço antes de manipular componentes internos.
5. Evite perfurar, dobrar ou aquecer excessivamente a bateria.
6. Utilize ferramentas adequadas e proteção contra descarga eletrostática.
7. Não faça pontes ou injeções de tensão sem conhecer os limites elétricos do circuito.
8. Proteja os conectores e os cabos flexíveis durante a desmontagem.
9. Utilize parafusos nos locais corretos.
10. Verifique a necessidade de calibração, configuração ou finalização de reparo.
11. Teste os recursos de segurança e autenticação que tenham sido afetados pelo serviço.
12. Informe claramente ao cliente qualquer função que não tenha sido possível validar.

---

# 19. Sequência profissional recomendada

Para reduzir retrabalho e evitar substituições desnecessárias:

1. Identificar o modelo exato.
2. Registrar o relato e o estado físico.
3. Realizar testes externos e consultar alertas.
4. Verificar bateria, acessórios e carregamento.
5. Testar tela, câmeras, áudio e conectividade.
6. Investigar sinais de líquido ou impacto.
7. Abrir o aparelho somente quando necessário.
8. Inspecionar conectores, flexíveis e componentes envolvidos.
9. Realizar testes com peças compatíveis quando isso ajudar a confirmar a hipótese.
10. Investigar a placa lógica quando as evidências apontarem para ela.
11. Executar reparos com ferramentas e procedimentos apropriados.
12. Realizar testes funcionais completos.
13. Verificar mensagens de peças e procedimentos de configuração aplicáveis.
14. Registrar o resultado e orientar o cliente.

---

# 20. Conclusão técnica

Os defeitos recorrentes em iPhones podem ter origem mecânica, elétrica, eletrônica, ambiental ou de software.

Os principais sistemas a investigar são:

- Bateria e alimentação.
- Carregamento e conectores.
- Tela e touchscreen.
- Câmeras.
- Face ID ou Touch ID.
- Áudio e microfones.
- Conectividade.
- Cabos flexíveis e botões.
- Placa lógica.
- Danos por líquidos e impactos.

A regra mais importante é **confirmar a causa antes de substituir a peça**. Um diagnóstico confiável protege os dados do cliente, reduz custos, evita retrabalho e aumenta a segurança do reparo.

O iPhone exige atenção especial porque uma intervenção incorreta pode danificar componentes delicados, comprometer a biometria, prejudicar a vedação ou causar riscos relacionados à bateria.

Este relatório é uma referência geral. O modelo exato e sua documentação técnica devem orientar as medições, a pinagem, os procedimentos de abertura, a compatibilidade das peças e a finalização do reparo.

## Referências técnicas recomendadas

- Suporte Apple — [Reparo e serviço para iPhone](https://support.apple.com/pt-br/iphone/repair)
- Apple — [Reparo de autoatendimento e manuais de serviço](https://support.apple.com/self-service-repair)
- Suporte Apple — [Serviço e reparo da bateria do iPhone](https://support.apple.com/pt-br/iphone/repair/battery-replacement)
- Suporte Apple — [Se o iPhone não carregar](https://support.apple.com/pt-br/108805)
- Suporte Apple — [Se aparecer um alerta de líquido no conector](https://support.apple.com/pt-br/102643)

Os manuais e procedimentos específicos devem ser consultados de acordo com o modelo atendido.
