# Como instalar Fish Terminal com tema starship e as minhas configurações
Area destina para configurar fish terminal com tema e outras configurações no terminal como nvm

A pasta raiz do github representa a pasta .config do linux que é encontrada no diretório <b>~/.config</b>

<hr>


## Instruções 

1. Clone a pasta com a pasta fish e o arquivo starship.toml

2. Copie a pasta <b>fish</b> e o arquivo <b>starship.toml</b> para dentro de <b>~/.config</b> 

```
# Entrar no diretório para colar os arquivos
cd ~/.config
```

3. Instale o <b>fish</b> e o <b>exa</b> 
```
sudo apt install fish exa
```

4. Entre da na pasta Downloads e Instale o tema starship
```
cd ~/Downloads

# Se pedir para dar para confirmarção instalação aceita com y
curl -sS https://starship.rs/install.sh | sh 
```

5. Edita o <b>.bashrc</b> para inicializar com ele e no final do arquivo cole o comando
```
gedit ~/.config/fish/config.fish

# Cole esse comando no final do arquivo
starship init fish | source
```

6. Iniciar o fish terminal por padrão, insira os comandos abaixo e reinicie o computador
```
# Primeiro comando
sudo chsh -s $(which fish)

# Depois de usar esse comando reinicie o computador ou encerre a sessão e faça login novamente
chsh -s /usr/bin/fish

# Verifica se mudou
echo $SHELL
```

7. Instale o <b>fisher</b> e o <b>edc/bass</b>
```
# Instalar o curl
sudo apt install curl

# Baixar e instalar o fisher
curl -sL https://git.io/fisher | source && fisher install jorgebucaran/fisher


# Instalar o edc/bass
fisher install edc/bass

```

8. Instale NVM (verifique se é a versão recente)
```
# Versão que instalei
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

9. Edite o arquivo <b>.profile</b> e adicione o comando no final do arquivo .profile para iniciar o <b>NVM</b> junto com o terminal
```
# Abre o .profile com editor
sudo gedit ~/.profile

# Comando para inserir no final da linha do arquivo .profile
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
```
