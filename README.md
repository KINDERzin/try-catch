# 🛡️ Master Guide: Java Exceptions & Error Handling

Este repositório é um **dicionário prático** de exceções em Java. Ele documenta o que causa cada erro, onde eles costumam nascer e como capturá-los sem travar o sistema.

---

## 🏗️ Anatomia do Tratamento de Erros

Em Java, as exceções seguem um fluxo de **Lançamento** e **Captura**:
1. **`throw`**: O alarme que você dispara quando algo dá errado.
2. **`try`**: O bloco de código que você "tenta" executar.
3. **`catch`**: A rede de segurança que segura o erro específico.
4. **`finally`**: O bloco que executa **sempre** (útil para fechar Scanners ou arquivos).

---

## 🚨 Catálogo de Exceções (Dicionário de Erros)

### 1. Erros de Lógica e Dados (Você lança no código)

| Exceção | O que causa / Motivo | Exemplo de Uso |
| :--- | :--- | :--- |
| `IllegalArgumentException` | O dado enviado é inválido ou absurdo. | `setIdade(-5)` ou `setNome("")`. |
| `IllegalStateException` | A regra de negócio impede a ação agora. | Emprestar livro que já está locado. |
| `NoSuchElementException` | Buscou algo em uma lista e não achou. | Buscar um ID que não existe na `List`. |
| `ArithmeticException` | Erro em cálculo matemático. | Dividir qualquer número por `0`. |

### 2. Erros de Entrada e Formato (O Java lança no Scanner)

| Exceção | O que causa / Motivo | Exemplo de Uso |
| :--- | :--- | :--- |
| `NumberFormatException` | Texto não pôde virar número. | `Integer.parseInt("abc")`. |
| `DateTimeParseException` | Data em formato errado ou impossível. | Digitar `31/02` ou `ano 99999`. |
| `InputMismatchException`| Tipo de dado errado no Scanner. | Usar `nextInt()` e digitar uma letra. |

### 3. Erros de Memória e Estrutura (Bugs Comuns)

| Exceção | O que causa / Motivo | Exemplo de Uso |
| :--- | :--- | :--- |
| `NullPointerException` | Tentou usar algo que vale `null`. | Chamar `.metodo()` em objeto vazio. |
| `IndexOutOfBoundsException`| Acessou posição inexistente no Array. | Pedir o item 10 de uma lista com 5. |
| `ClassCastException` | Tentou converter tipos incompatíveis. | Tentar transformar um `Gato` em `Carro`. |

---

## 💻 Exemplo Prático: "A Grande Captura"

Este exemplo mostra como capturar múltiplos erros em um único bloco `try/catch`.

```java
public void gerenciarSistema() {
    try {
        // Tentativa de operação complexa
        validarUsuario("U001");
        double multa = calcularMulta(10, 0); 
        
    } catch (IllegalArgumentException e) {
        System.err.println("❌ Erro de Dado: " + e.getMessage());

    } catch (ArithmeticException e) {
        System.err.println("❌ Erro de Cálculo: " + e.getMessage());

    } catch (Exception e) {
        // Catch genérico: Captura qualquer erro que os de cima não pegaram
        System.err.println("🔥 Erro Crítico: " + e.getMessage());
        
    } finally {
        System.out.println("🧹 Log: Tentativa de operação registrada.");
    }
}
