<p align="center">
  <img src="assets/openpep-mark.png" width="160" alt="Bem-te-vi, símbolo provisório do OpenPEP">
</p>

<h1 align="center">OpenPEP</h1>

<p align="center"><strong>O prontuário permanece legível fora do aplicativo.</strong></p>

O OpenPEP é um prontuário eletrônico ambulatorial open-source para consultórios médicos. O núcleo clínico roda localmente no Mac e guarda cada prontuário em um conjunto documentado de arquivos. Uma especificação pública orienta a leitura, a verificação e a recuperação desses dados.

> **Status: pré-alfa.** O trabalho atual está concentrado na prova de conceito do formato. Uso clínico, dados reais e alegações de certificação ficam fora desta fase.

## Como o prontuário é organizado

Cada paciente ocupa um diretório identificado por um código opaco. PDFs, imagens, áudios e materiais importados ficam preservados em `raw`. As notas revisadas pelo profissional ficam em `content`. A pasta `wiki` reúne uma visão reconstruível do histórico, sempre ligada às fontes que a sustentam. Uma área técnica registra hashes, eventos e versões do formato.

A finalização de uma nota gera um evento verificável. Correções posteriores criam adendos ligados ao documento original. Os índices de busca podem ser apagados e refeitos a partir dos arquivos do prontuário.

O fluxo clínico básico funciona offline. Serviços de nuvem podem receber cópias cifradas, acompanhadas por um procedimento de restauração testado. A continuidade do atendimento depende dos arquivos e das chaves mantidas pelo profissional.

## Primeiro produto

O recorte inicial atende um médico em um Mac, com uma recepcionista usando uma interface web separada. O Mac concentra os arquivos clínicos e a finalização das notas. A interface da recepção cuida do cadastro administrativo, do índice mestre de pacientes, da agenda, dos estados de visita e de pedidos encaminhados ao médico.

Essas rotinas operacionais usam um PostgreSQL pequeno, acessado por uma API com permissões próprias. O banco guarda dados administrativos e produz eventos que podem reconstruir seu estado. Notas, anexos, transcrições e resumos clínicos permanecem no cofre local do médico.

A primeira entrega será um kit de validação do cofre clínico. Ele reunirá a especificação do formato, pacientes sintéticos, um verificador de integridade, testes de corrupção, exportação e restauração. O aplicativo para Mac começa depois dessa validação.

## Inteligência artificial

Transcrições, resumos e rascunhos entram como material derivado. Cada registro final exige revisão e aprovação do profissional. A wiki pode ser refeita a qualquer momento e cada afirmação deve apontar para uma fonte recuperável.

## Limites do primeiro MVP

O primeiro MVP cobre um escritor clínico por cofre e uma pequena operação de recepção. Portal do paciente, chat assíncrono, vídeo embutido, sincronização clínica entre vários Macs, rotinas hospitalares e automação de conduta ficam para avaliações posteriores.

Google Drive e iCloud podem transportar backups cifrados. O cofre ativo continua sob controle do aplicativo local, com disponibilidade offline e verificação de integridade.

## Desenvolvimento

O projeto trabalha somente com dados sintéticos nesta etapa. Código, especificações e instruções para contribuição serão publicados conforme os testes do formato forem concluídos.

<p align="center">O OpenPEP registra informações clínicas. Diagnóstico, prescrição e julgamento clínico permanecem sob responsabilidade profissional.</p>
