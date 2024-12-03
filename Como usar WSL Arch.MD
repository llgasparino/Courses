# Instalando o WSL

Caso ainda não tenha instalado o WSL no seu Windows insira o seguinte comando no Windows PowerShell:

`wsl --install`

Windows Terminal
Eu prefiro utilizar o Windows Terminal por dois principais motivos: personalização e aproveitamento de alguns comandos Linux. A instalação é simples e pode ser feita pelo link abaixo:

[Windows Terminal - Aplicativos Microsoft Store](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=pt-br&gl=br))

## Instalando o Arch

Essa versão do Arch que eu utilizo é bem leve se comparado a outras opções (como o Manjaro por exemplo):

[ArchWSL](https://github.com/yuk7/ArchWSL)

Basta extrair os arquivos para uma pasta de preferência `(C: )` e executar o arquivo Arch que será iniciada a instalação.

## Configurando um usuário

Feita a instalação é hora de configurar um usuário e torná-lo padrão na inicialização, evitando utilizar o usuário root. Basta seguir os comandos abaixo, lembrando de substituir {username} pelo nome de usuário desejado:

```bash
echo "%wheel ALL=(ALL) ALL" > /etc/sudoers.d/wheel

useradd -m -G wheel -s /bin/bash {username}

passwd {username}
```

Agora para definir o usuário criado como padrão, feche o Arch e abra o seu terminal na pasta onde está o arquivo Arch.exe e insira o comando a seguir:

> `C` > `cd Arch.exe config --default-user {username}`

## Atualizando os pacotes da distro

Antes de atualizar precisamos inicializar o keyring do pacman:

`sudo pacman-key --init`

E também realizar a configuração inicial das chaves com:

```bash
sudo pacman-key --populate

sudo pacman -Sy archlinux-keyring

sudo pacman -Syyuu
```

## Gerenciadores de pacotes

Vou instalar incialmente os gerenciadores YARN e NPM:

`sudo pacman -S yarn npm`

Como gerenciador de AUR eu utilizo o Yay:

`sudo pacman -S --needed git base-devel`

Por fim, o pacote “Rust” para utilizar o “cargo”:

`sudo pacman -S rust`

Para instalar o Yay será necessário clonar o repositório, como após a instalação os arquivos não serão mais utilizados eu opto por criar uma pasta temporária para facilitar a exclusão posteriormente:

`mkdir tmp`

`cd tmp`

Agora basta clonar o repositório e fazer o build com o makepkg:

`git clone https://aur.archlinux.org/yay.git`

`cd yay`

`makepkg -si`

## Z Shell

Instalando o ZSH:

`yay -S zsh`

Personalizando o Terminal
Alterando o tema do terminal
O Windows Terminal Themes possui diversos temas prontos para o seu terminal, basta escolher o tema de sua preferência e clicar no botão “Get theme”, com isso o tema selecionado será copiado para a sua área de transferência. O meu tema preferido é o Dracula.

Basta agora voltar ao terminal, utilizar o atalho Ctrl + , para abrir as Configurações e clicar em Abrir arquivo JSON no canto inferior esquerdo.

`Abrir arquivo JSON`

Após o último tema (os temas estão dentro do array `"schemes”`), coloque uma , e cole o tema escolhido. Salve e feche o arquivo.

Volte à tela de Configurações, abra o perfil do Arch, em “Configurações adicionais” clique em “Aparência”. Agora é só alterar o “Esquema de cores” para a opção desejada. Clique em “Salvar” e feche as configurações.

Alterando tema do ZSH
Para alterar o tema do ZSH eu utilizo o Powerlevel10k:

```bash
yay -S --noconfirm zsh-theme-powerlevel10k-git

echo 'source /usr/share/zsh-theme-powerlevel10k/powerlevel10k.zsh-theme' >> ~/.zshrc

chsh -s /usr/bin/zsh
```
