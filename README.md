# Guardiãs — Ponto de Ajuda camuflado em uma loja de roupas

O QR Code da cabine abre o site de uma loja de moda. O pedido de ajuda fica dentro do chat de atendimento da loja,
e a equipe recebe o alerta ao vivo no painel.

## Rodar no computador (Node.js 18+, nada para instalar)

    PAINEL_SENHA="uma-senha-forte" NOME_LOCAL="Nome do bar" LOJA_NOME="Trama Moda" node server.js

Windows PowerShell:

    $env:PAINEL_SENHA="uma-senha-forte"; $env:NOME_LOCAL="Nome do bar"; $env:LOJA_NOME="Trama Moda"; node server.js

- Loja (o que a pessoa vê): http://localhost:3000/
- QR Code da cabine 3: http://localhost:3000/ajuda?c=3 (o chat de atendimento só aparece com o `?c=`)
- Painel da equipe: http://localhost:3000/painel
- Gerador de QR Codes para imprimir: http://localhost:3000/qr

## Colocar no ar

1. Envie esta pasta para um repositório no GitHub.
2. Na Render (render.com), use New > Blueprint e escolha o repositório (o `render.yaml` já está pronto).
3. Preencha `PAINEL_SENHA`, `NOME_LOCAL` e, se quiser, `LOJA_NOME`.
4. Abra `https://seu-site/qr`, gere e imprima um adesivo por cabine.
5. Abra `https://seu-site/painel` nos celulares da gerência e da segurança.

## Como a camuflagem funciona

- Quem abre o endereço sem `?c=` vê só a loja, sem nenhum sinal do atendimento.
- Com `?c=` (o QR da cabine), o chat de atendimento abre sozinho. As respostas rápidas viram o pedido de ajuda.
- Fechar o chat apaga a conversa do aparelho e deixa só a loja na tela. A tecla Esc faz o mesmo.
- No adesivo, use uma frase neutra, como "Precisa de ajuda? Aponte a câmera". Ela é editável em `public/qr.js`.

## Antes de usar de verdade

- Treine a equipe: quem recebe o alerta, quem vai até a cabine e o que fazer.
- Teste cada QR Code com um celular antes de colar.
- Mantenha o painel aberto, com som, em pelo menos um celular durante o expediente.
- O sistema guarda só cabine, tipo de pedido e horário, sem dados pessoais.
- Em risco imediato, a orientação continua sendo ligar 190.
