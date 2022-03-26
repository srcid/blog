# Rotacionar arquivos pdf

Muitos PDF que baixamos da internet precisam ser rotacionados.

## Usando o pdftk

### Para rotacionar a 1ª página 90° para a direita

```
pdftk file.pdf cat 1right output file_rotated.pdf
```

### Para rotacionar todas as páginas 90° para a esquerda

```
pdftk sample.pdf cat 1-endleft output sample_rotated.pdf
```