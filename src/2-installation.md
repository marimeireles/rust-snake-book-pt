# Instalação

## Instalação Padrão do Compilador do Rust e suas Ferramentas

### Usuários de Linux e MacOS

Para essas plataformas, é recomendado o uso do[Processo Oficial de Instalação do Rust](https://rustup.rs/) via `rustup.rs`. Quando perguntada, as configurações padrões (incluindo o compilador `stable`) são adequados para este curso.

Esse processo vai instalar várias ferramentas que serão utilizadas nesse curso, incluindo `rustc`, `cargo`, e `rustup`.

### Usuários do Windows

Usuários do Windows podem ter que instalar ferramentas adicionais. Por favor cheque o [guia de instalação](https://doc.rust-lang.org/book/ch01-01-installation.html#installing-rustup-on-windows) para Windows.

## Simple DirectMedia Layer

Simple DirectMedia Layer é uma biblioteca de desenvolvimento multiplattaforma criada para oferecer acesso de baixo nível à áudio, teclado, mouse, joystick, e gráficos via OpenGL and Direct3D. É escrita em C, e nós só usaremos as Rust bindings mais tarde, você precisa instalar a biblioteca de C separadamente.

### MacOS

```shell
brew install sdl2
```

### Ubuntu

```shell
sudo apt-get install libsdl2-dev
```

### Windows

Siga as instruções [aqui](https://github.com/Rust-SDL2/rust-sdl2#windows-msvc), seguindo os passos "For Rustup users".

### Outros sistemas operacionais

[Baixe](https://www.libsdl.org/download-2.0.php) e instale a biblioteca de desenvolvimento de acordo com o seu sistema.