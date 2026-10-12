# AR Tags — front-end câmera e realidade aumentada

Aplicação front-end estática para Android e desktop. Abre a câmera traseira, procura continuamente os QR Codes `AR-01` a `AR-10` e exibe um objeto 3D demonstrativo ou um modelo `.glb` correspondente.

## Publicação no Vercel
- Envie o conteúdo desta pasta para a raiz do repositório GitHub.
- Framework preset: Other.
- Build command: vazio.
- Output directory: `.`.
- Acesse pelo endereço HTTPS publicado no Vercel.

## Permissões e leitor QR
A página solicita acesso à câmera ao iniciar. Se a solicitação automática for bloqueada pelo navegador, toque em **Abrir câmera**. O acesso à câmera exige HTTPS (ou localhost durante desenvolvimento) e permissão do usuário.

A leitura usa `BarcodeDetector` quando disponível e tenta usar `jsQR` como alternativa carregada via CDN. Portanto, a primeira utilização do leitor alternativo exige internet.

## Modelos 3D
Coloque os arquivos em `assets/models/` com os nomes `object-01.glb` até `object-10.glb`. Na ausência do arquivo, é exibido um objeto demonstrativo.

## Limitações
Este é um protótipo web. O objeto acompanha a posição 2D do QR detectado na imagem, mas não é uma âncora espacial persistente nem substitui rastreamento nativo do ARCore. As bibliotecas são carregadas por CDN e não estão totalmente offline.
