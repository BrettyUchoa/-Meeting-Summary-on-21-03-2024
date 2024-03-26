# -Meeting-Summary-on-21-03-2024

**Workflow de Ocorrência no SAP**

O processo de fluxo de ocorrência no SAP segue as seguintes etapas:

1. **Origem da Ocorrência:**
   - O processo começa no SICAPES (Sistema de Integração do CAPES), onde um candidato se cadastra para solicitar uma bolsa ou projeto. O candidato é representado por uma instituição, com um pró-reitor encarregado da candidatura.

2. **Integração com o SAP:**
   - Após o término da candidatura, ocorre uma integração da inscrição para a base de processos, gerando assim o processo.

3. **Fases do Processo:**
   - O processo é compartilhado entre os sistemas SAP (Sistema de Análise de Processo), SCBA (Sistema de Controle de Bolsa Auxílio) e SIPREC (Sistema de Prestação de Contas).
   - Cada fase do processo é definida por um status na tabela de processo.
   - As fases incluem:
     - Fase 1: Candidatura
     - Fase 2: Acompanhamento
     - Fase 3: Prestação de Contas

4. **Fluxo entre Fases:**
   - Após a candidatura e aprovação, o processo avança para a fase de acompanhamento. O fluxo não prevê um retorno do processo para a fase de candidatura.
   - No entanto, em situações específicas, como quando o candidato solicita a revogação, suspensão ou adiamento da bolsa, é necessário realizar uma análise de mérito no SAP. Nesses casos, o processo é direcionado de volta à fase de candidatura para essa análise.
   - Atualmente, o sistema não possui um fluxo específico para lidar com esses casos, então o processo volta à fase de candidatura para que a análise de mérito seja realizada. Durante essa análise, o sistema trata o processo como uma ocorrência completa, reiniciando o fluxo desde o início até que a análise da ocorrência seja concluída e o processo retorne à fase de acompanhamento.
   - Esta abordagem resulta na reinicialização do fluxo completo do processo até que a análise da ocorrência seja finalizada, permitindo que o processo retorne à fase de acompanhamento posteriormente.

5. **Serviço de Análise de Mérito:**
   - O serviço de solicitação de análise de mérito, encontra-se em processo de refatoração do SOA para Rest API, sendo responsável pela integração entre o SCBA e o SAP.

6. **Mudanças na Estrutura:**
   - Com a conclusão da task #49802, apenas a ocorrência será enviada para a candidatura, não mais o processo completo.
   - Com a nova abordagem a ocorrência se torna a entidade principal, com o processo sendo um atributo dela.
   - Criando um modelo de dados específico para a ocorrência, com o processo sendo um atributo. Tabelas específicas foram criadas para lidar com essa estrutura. No qual as tabelas coloridas associadas fazem parte do esquema de ocorrência.

7. **Parametrização e Tipos de Ocorrência:**
   - Existem diferentes tipos de ocorrência, cada um exigindo sua própria parametrização.
   - A tabela de parametrização ocorrência é crucial para configurar esses tipos.

8. **Análise e Workflow:**
   - Cada tipo de ocorrência tem um questionário padrão, utilizado para a análise.
   - O workflow de ocorrências será semelhante ao de processos, com diferentes etapas e avaliações necessárias.

9. **Interface do Usuário:**
   - A tela de detalhamento da ocorrência será dinâmica, adaptando-se com base nos tipos de ocorrência e estágios do workflow.
   - As permissões serão configuradas conforme a tabela AVAL_OCORRENCIA_PARAMETRIZACAO_SITUACAO_OCORRENCIA.


