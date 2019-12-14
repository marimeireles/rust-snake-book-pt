# Cargo and Dependencies

Para inicializar um novo projeto, execute `cargo new`:

```shell
$ cargo new rusty_snake
```

Cargo gerou um novo diretório chamado `rusty_snake`. `cd` no diretório para checar o que o cargo gerou.

Abra o arquivo `cargo.toml` no editor da sua escolha. Isso é chamado manifesto, e contém todos os metadados que o Cargo precisa para compilar seu projeto.

Deve ser algo parecido com isso:

`cargo.toml`

```rust
[package]
name = "rusty-snake"
version = "0.1.0"
authors = ["Seu Nome"]
edition = "2018"

# Veja mais palavras chaves e definições em https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]

```

Para usar SDL2 em Rust nós precisamos adicionar o crate de SDL2 como uma dependência.

Adicione as seguintes linhas na sessão [dependencies]:
`sdl2 = "0.30.0"`

Abra `src/main.rs`

Substitua o conteúdo do arquivo com o seguinte código:

```rust
// Dependencies go here




// this function initializes the canvas
fn init(width: u32, height: u32) -> (Canvas<Window>, EventPump) {
    let sdl_context = sdl2::init().unwrap();
    let video_subsystem = sdl_context.video().unwrap();

    let window = video_subsystem
        .window("Game", width + 1, height + 1)
        .position_centered()
        .build()
        .unwrap();

    let mut canvas = window.into_canvas().present_vsync().build().unwrap();

    canvas.set_draw_color(Color::RGB(0, 0, 0));
    canvas.clear();
    canvas.present();

    let event_pump = sdl_context.event_pump().unwrap();
    (canvas, event_pump)
}

// this is main
fn main() {
    println!("Hello, world!");
}
```

Bem no começo do arquivo na sessão `// Dependencies go here`, adicione as seguintes linhas:

```rust
use sdl2::video::Window;
use sdl2::pixels::Color;
use sdl2::render::Canvas;
use sdl2::EventPump;
```

No seu terminal vá até a pasta `/rusty-snake`, e execute o comando `cargo run`.
O que você vê? Para se livrar desse warning precisamos chamar `fn init` na `main()`.
