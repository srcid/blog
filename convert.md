# Comando Convert

__convert__ é um a comnado mundo versátil com várias opções. Quero abordar algumas aqui.

## Problema

Tenho essa imagem abaixo e quero imprimí-la, mas da forma que ela está eu gastaria muita tinta preta.

![Capa do livro de álgebra linear por Boldrini](./resources/img/capa_boldrini.png){ width=180px }

Porém da forma como está gastaria muita tinta preta e, além disso, a imagem é de baixa resolução (329 X 440) e não 
existe a funcionalidade _scaling_ no serviço de impressão do ubuntu 20.04 que estou atualmente usando.

## Solução

Pensando rapidamente pensei logo em inverter a imagem, mas isso não seria bom pois há tons de verde na imagem e eu
gostaria de economizar na tinta. Então antes de inverter as cores eu preciso converter para preto-e-branco ou 
escala de cinza.

### Convertendo imagem

#### Preto-e-branco

```bash
convert capa_boldrini.png -monochrome capa_boldrini_bw.png
```

![Capa do Boldrini em preto-e-branco](./resources/img/capa_boldrini_bw.png){ width=180px }

#### escala de cinza

```bash
convert capa_boldrini.png -colorspace GRAY capa_boldrini_gray.png
```

![Capa do Boldrini em escala de cinza](./resources/img/capa_boldrini_gray.png){ width=180px }


### Invertendo imagem

Escolhi em a imagem em escala de cinza pois esta me agradou mais.

```bash
convert capa_boldrini_gray.png -channel RGB -negate capa_boldrini_grey_inverted.png
```

![Capa do Boldrini em escala de cinza com cores invertidas](./resources/img/capa_boldrini_gray_inverted.png){ width=180px }

### Ampliando imagem

Agora só me resta ampliar a imagem para que ocupe toda a folha. Escolhi um valor alto pois uma imagem grande não 
é problema pois o sistema de impressão me deixa reduzir uma imagem para caber na folha.

```bash
convert capa_boldrini_grey_inverted.png -resize 220% capa_boldrini_grey_inverted_scaled.png
```

Se quisesse poderia também especificar uma resolução (ex. -resize 720x1080), mas é preciso atentar-se as 
proporções da imagem.

## Resultado

![Capa do Boldrini ampliada](./resources/img/capa_boldrini_gray_inverted_scaled.png){ width=180px }
