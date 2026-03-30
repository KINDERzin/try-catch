# try-catch
Repositorio que deixei aqui para ter anotado as exceções do try catch pois estou aprendendo a manipulá-los.


Exceção    
  O que causa / Motivo
  Exemplo no seu Projeto
  
- *IllegalArgumentException*
    O dado enviado é inválido, feio ou fora do padrão.	
    **Tentar cadastrar um livro com -50 páginas ou nome vazio.**
- *IllegalStateException*	
    O dado é ok, mas o estado atual do sistema não permite a ação.
    **Tentar emprestar um livro que a Biblioteca sabe que está com estoque 0.**
- *NoSuchElementException*	
    Você procurou algo em uma lista e não encontrou nada.
    **Tentar buscar um usuário com um ID que não existe na lista.**
- *NullPointerException*	
    Tentativa de usar um objeto que está vazio (null).
    **Tentar ler o título de um livro que a busca retornou como null.**
- *NumberFormatException*
    Erro ao tentar transformar texto em número.	
    **Usuário digita "abc" onde o menu espera o número da opção.**
- *DateTimeParseException*	
    Erro ao tentar transformar texto em data.
    **Usuário digita "32/13/2024" ou uma data no formato errado.**
- *InputMismatchException*
    Erro de leitura do Scanner (tipo errado).
    **Usar nextInt() e o usuário digitar uma letra.**
- *IndexOutOfBoundsException*
    Tentativa de acessar uma posição que não existe na lista.	
    **Tentar pegar o item 10 de uma lista que só tem 5 livros.**
