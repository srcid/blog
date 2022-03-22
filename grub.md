# Problema

Faço uso de _dual boot_ com Linux e Windows e sempre que o windows atualiza tenho que ficar 
esperando para selectionar a opção de boot.

## Solução

### Parametros

O GRUB possui parametros que podem alterados. O que nos interessa por enquando são esses: 

#### GRUB_DEFAULT

Esse parametro informa ao GRUB qual é opção de boot padrão.

#### GRUB_SAVEDEFAULT

Esse parametro informa ao GRUB que ele deve salvar a última opção de boot escolhida.

### Paso-a-paso

Abra o arquivo `/etc/default/grub` com seu editor preferido e com privilégios de administrador.

```zsh
sudo nvim /etc/default/grub
```

Altere os valores dos parametros `GRUB_DEFAULT` e `GRUB_SAVEDEFAULT` como mostrado abaixo.

> GRUB_DEFAULT=saved

> GRUB_SAVEDEFAULT=true

Em seguida execute o comando abaixo para atulizar GRUB com os novos paramentros

```zsh
sudo grub-update
```

## Referências

[GRUB Remember last choice](https://askubuntu.com/questions/148662/how-to-get-grub2-to-remember-last-choice)

[GRUB Simple configuration](https://www.gnu.org/software/grub/manual/grub/grub.html#Simple-configuration)