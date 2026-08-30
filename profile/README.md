<p align="center">
  <img src="assets/openpep-mark.png" width="160" alt="Bem-te-vi, símbolo provisório do OpenPEP">
</p>

<h1 align="center">OpenPEP</h1>

<p align="center"><strong>O prontuário como pasta, não como plataforma.</strong></p>

O OpenPEP é um projeto de prontuário eletrônico ambulatorial open-source para consultórios médicos. O produto inicial segue uma arquitetura **local-first e filesystem-first**: o núcleo clínico roda no Mac e preserva o prontuário em arquivos portáteis, verificáveis e independentes do aplicativo.

> **Status: pré-alfa e prova de conceito.** O OpenPEP ainda não está pronto para uso clínico, não é certificado e não faz alegação de conformidade certificada. Todo dado de desenvolvimento e teste deve ser sintético.

## A ideia central

O prontuário não deve desaparecer se o aplicativo, o fornecedor ou um serviço de nuvem deixarem de existir. Por isso:

- arquivos clínicos abertos preservam a fonte da verdade;
- notas finalizadas não são silenciosamente reescritas — correções viram adendos;
- alterações posteriores devem ser detectáveis por hashes, eventos e verificação de integridade;
- abrir um paciente, consultar o histórico e registrar uma nota deve funcionar sem internet;
- backup só conta quando a restauração pode ser comprovada;
- inteligência artificial pode propor transcrições, resumos e rascunhos, mas um profissional precisa revisar e promover qualquer registro final.

## Produto inicial

O primeiro recorte é deliberadamente estreito:

1. **Vault clínico no Mac** — arquivos `raw`, `content`, `wiki` e uma área técnica de integridade.
2. **Um escritor clínico por vault** — simplicidade e prevenção explícita de conflitos.
3. **Recepção web separada** — cadastro, índice mestre de pacientes e agenda em um PostgreSQL operacional reconstruível, sem acesso a notas, anexos ou wiki clínica.
4. **Recuperação como função central** — exportação completa, backup cifrado e restauração verificável.
5. **IA controlada** — conteúdo derivado, rastreável e sempre subordinado à revisão humana.

O primeiro entregável será um **vault conformance kit**: especificação pública do formato, dados sintéticos, verificador de integridade, simulador de corrupção, exportador e restaurador. A interface Mac vem depois que o protocolo provar que o prontuário sobrevive sem ela.

## O que não entra no primeiro MVP

- prontuário hospitalar ou suíte administrativa completa;
- vários profissionais finalizando conteúdo clínico simultaneamente;
- portal do paciente e chat assíncrono nativo;
- vídeo ou áudio embutido no aplicativo;
- sincronização bidirecional irrestrita entre vários Macs;
- alteração automática de nota final por IA;
- uso do Google Drive ou iCloud como substituto de banco ou de backup verificável.

## Princípios

**Portabilidade humana · funcionamento offline · segurança do paciente · privacidade · integridade verificável · recuperação testada · mínimo aprisionamento · transparência sobre limites**

O desenvolvimento ocorre de forma incremental, com gates objetivos e exclusivamente com dados sintéticos. Código, especificações e orientações para contribuição serão publicados conforme a prova de conceito amadurecer.

---

<p align="center">OpenPEP é software em desenvolvimento. Ele registra; não diagnostica, não prescreve e não substitui julgamento profissional.</p>
