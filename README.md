# Atualização de Acessibilidade

Foi identificada uma oportunidade de melhoria na acessibilidade do aplicativo relacionada ao contraste do texto "Digite o valor", que serve como dica (hint) no campo de entrada de dados.

## O que foi alterado
- **Arquivo modificado:** `app/src/main/java/com/example/cambio/MainActivity.kt`
- **Problema:** A cor do texto (primeiro plano) era `Color.Gray` (#888888) sobre um fundo `Color.LightGray` (#CCCCCC), gerando uma taxa de contraste de 2,21. Essa taxa é inferior ao mínimo recomendado de 4,50 para textos pequenos para garantir uma boa legibilidade.
- **Solução:** A cor do texto da dica no `BasicTextField` foi atualizada de `Color.Gray` para `Color.DarkGray`. Com isso, a taxa de contraste em relação ao fundo aumenta consideravelmente, melhorando a leitura e atendendo às diretrizes de acessibilidade visual.

### Trecho do código atualizado:

```kotlin
if (inputValue.isEmpty()) Text(
    stringResource(id = R.string.enter_value_hint),
    color = Color.DarkGray // <-- Cor alterada para maior contraste
)
```
