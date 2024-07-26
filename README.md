# gerenciamento-biblioteca-poo
Desafio de gerenciamento de biblioteca utilizando Java e POO.


```mermaid
classDiagram
    class Livro {
        -String titulo
        -String autor
        -String isbn
        -String status
    }

    class Usuario {
        -String nome
        -String idUsuario
        -List~Livro~ livrosEmprestados
    }

    class Biblioteca {
        +addLivro(Livro livro)
        +emprestarLivro(Usuario usuario, Livro livro)
        +devolverLivro(Usuario usuario, Livro livro)
    }

    class LivroNaoDisponivelException {
    }

    Usuario "1" --> "0..*" Livro : empresta
    Biblioteca "1" --> "0..*" Livro
    Biblioteca "1" --> "0..*" Usuario
    Biblioteca "1" --> "1" LivroNaoDisponivelException

