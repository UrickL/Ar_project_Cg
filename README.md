# AR Tags — experiências multimídia front-end

Webapp estático para Android/desktop: abre a câmera em tela cheia, reconhece QR Codes `AR-01` a `AR-10` e mostra uma experiência flutuante para cada tag.

## Mapa inicial das tags
- AR-01: texto flutuante editável
- AR-02: vídeo local/offline (arquivo MP4/WebM)
- AR-03, AR-04, AR-05: três experiências 3D
- AR-06: áudio local com botões Executar e Parar
- AR-07: galeria local de até 10 imagens
- AR-08: quiz com 5 perguntas e alternativas A, B, C e D
- AR-09 e AR-10: experiências 3D adicionais

O pedido lista oito funções/tags principais (texto, vídeo, três objetos 3D, áudio, galeria e quiz), então as funções foram distribuídas nas tags AR-01 a AR-08; AR-09 e AR-10 continuam disponíveis para modelos 3D.

## Editar conteúdo
Toque no botão ⚙ no canto superior direito. Escolha uma tag, edite o texto/título ou carregue arquivos de vídeo, áudio, modelo 3D e até 10 imagens. No quiz, preencha as cinco perguntas, quatro alternativas e escolha a resposta correta. Toque em “Salvar nesta máquina”.

Os conteúdos são salvos localmente no navegador usando IndexedDB/localStorage; não há backend nem sincronização entre dispositivos. Para que os arquivos de mídia funcionem offline, carregue-os previamente por esse editor no aparelho. A biblioteca Three.js e o leitor QR alternativo ainda são carregados pela internet.

## Publicar no GitHub/Vercel
Envie o conteúdo desta pasta para a raiz do repositório GitHub. No Vercel, escolha Framework Preset `Other`, deixe Build Command vazio e use `.` como Output Directory. Use o domínio HTTPS para permitir a câmera.

## Limitações
A sobreposição multimídia acompanha a posição 2D do QR detectado pela câmera. Isso não é uma âncora espacial persistente nem rastreamento nativo do ARCore. Para melhor desempenho offline, empacote localmente Three.js, GLTFLoader e jsQR; armazenamento de vídeos grandes depende do espaço disponível no aparelho/navegador.
## Audiodescrição

Quando uma tag QR é reconhecida, o botão **🔊 Ouvir audiodescrição** fica disponível. Ao tocar, o navegador lê em português do Brasil o texto visível da experiência e do status. Durante a leitura, o mesmo botão permite parar a fala. A voz usa a síntese de fala integrada ao navegador/dispositivo.
