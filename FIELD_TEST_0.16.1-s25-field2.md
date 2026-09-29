# Field test — 0.16.1-s25-field2

## Escopo

Candidato de campo com mudança funcional mínima em relação a 0.16.0-s25-field1:

- corrige o crash determinístico no FINISH canônico do BSC causado pelos formatos inválidos `%+.3FS` e `%+.2FS`;
- preserva a matemática e a lógica já validadas de BLE, START, PAUSE/PLAY, matcher, notificações, gates, lifecycle e ranking;
- adiciona os resultados canônicos de 28/09/2026 ao Top 10 e aos perfis de Virtual Race.

## Dados de 28/09

- IDA: 2884.036652 s — P2.
- VOLTA: 2853.339383 s — P6.
- Os antigos P10 saem automaticamente após ordenação e seleção dos 10 melhores.

## Validação

- 149 testes verdes.
- Casos reais IDA/VOLTA e regressões de GPS/matcher permanecem verdes.
- 100.000 combinações determinísticas adicionais cobrem decisão canônica + formatação de auditoria do FINISH.
- Build limpo Android 16.
- APK Signature Scheme v2 válido.
- Certificado SHA-256: `b9f7b175c4014c274c0449538c114a52bc2fb894e5fa679e634ab6f805c03f7f`.
- APK SHA-256: `17c43d287aac7bbc4d548890637f5195633b08523028c983fac467a8719cb99d`.
- Tamanho: 2961001 bytes.

## Teste de campo

Verificar especialmente um FINISH real com BSC conectado. O resultado esperado é conclusão canônica normal, sem crash e sem necessidade do fallback de process restore.
