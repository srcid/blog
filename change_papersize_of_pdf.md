# Alterando o tamanho do papel em arquivos PDF

As vezes preciso alterar a tamanho da folha de um arquivo pdf. Isso pode ser feito facilmente pela ferramenta de terminal __pdfjam__.

## Como instalar

O __pdfjam__ vem junto com o pacote texlive-extra-utils.

```
sudo apt install texlive texlive-latex-extra texlive-extra-utils
```

## Como usar

Caso queiramos converter um PDF para A5, podemos exucar o seguinte comando.

```
pdfjam --outfile out.pdf --papersize '{148.5mm,210mm}' in.pdf
```