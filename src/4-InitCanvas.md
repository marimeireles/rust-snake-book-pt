# Inicializando o Canvas

Nosso jogo precisa de um canvas, onde todos os gráficos do jogo serão renderizados. Vamos incializá-lo.

## Funções e variáveis


Vamos olhar a função `fn init` mais de perto.

`main.rs`

```rust

// this function initializes the canvas
fn init(width: u32, height: u32) -> (Canvas<Window>, EventPump) {
    let sdl_context = sdl2::init().unwrap();
    let video_subsystem = sdl_context.video().unwrap();

    let window = video_subsystem
        .window("Rusty Snake", width as u32 + 1, height as u32 + 1)
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

```
 `fn` declara a função, `init` é seu nome. A função leva dois parâmetros, x e y. Rust é uma linguagem de tipo seguro, então os tipos dos parâmetros precisam ser explicitamente indicados. Nesse exmplo o tipo de ambos os parâmettros é `u32`, um inteiro 32bit unsigned. Os tipos de retorno também precisam ser especificamente nomeados. `fn init` retorna dois valores em chaves, separados por uma vírgula. Os tipos desses valores são declarados no crate `sdl2`. Nós vamos ignorar o corpo da função por agora.

1. Em `main()`, delete o `println!`.

2. Declare as variáveis `canvas_width` e `canvas_height`, cada uma com o valor `720_u32`. `_u32` faz desse número explicitamente um inteiro unsigned 32bit.

3. Chame a função adicionando a seguinte linha:

   ```rust
   let (canvas, events) = init(canvas_width, canvas_height);
   ```

4. No terminal execute `cargo run`. O que acontece?
