# Política de releases do Live Segment S25

## Regra obrigatória

**Toda atualização do Live Segment deve ser publicada pelo sistema de atualização DENTRO do próprio aplicativo, na área "Atualizações".**

Um APK solto, artefato do GitHub, arquivo enviado em chat ou link externo pode existir apenas como artefato técnico/backup. Nenhuma versão é considerada lançada para uso enquanto não estiver:

1. com `versionCode` maior que a versão anterior;
2. com build e testes aprovados;
3. com assinatura/fingerprint conferidos;
4. com SHA-256 e tamanho conferidos;
5. com o payload completo publicado neste repositório de releases;
6. com `latest.json` apontando para a nova versão;
7. validada pelo mesmo endpoint que o `UpdateManager` do app consulta;
8. visível no próprio aplicativo em **Atualizações / Buscar atualizações** para instalações com versão anterior.

## Ordem de publicação

Publicar primeiro todos os chunks e metadados. Atualizar `latest.json` **por último**. Isso evita expor pelo aplicativo uma versão incompleta.

## Regra de rollback

Se uma versão de campo apresentar crash/ANR, regressão de relógio/progresso, progresso durante PAUSE, FINISH preso/duplicado, reconexão que não recupera ou perda persistente de notificações no BSC200, ela deixa de ser candidata de campo. O `latest.json` deve voltar a apontar para o último build aprovado antes de qualquer nova tentativa.

## Candidato atual

Em 2026-09-28, o candidato publicado é `0.16.0-s25-field1` (`versionCode 25`).
