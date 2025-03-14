Ótimo! Já tendo as classes prontas, vamos avançar para a próxima etapa: **criar a camada de serviço** para implementar a lógica de negócios do sistema. Vamos focar em como gerenciar empréstimos, devoluções e a disponibilidade de livros.

---

### **4. Camada de Serviço**
A camada de serviço contém a lógica de negócios do sistema. Vamos criar uma classe `BibliotecaService` que será responsável por:
- Emprestar livros.
- Devolver livros.
- Listar livros disponíveis.
- Gerenciar usuários.

#### **4.1. Criando a Classe `BibliotecaService`**

```java
package com.biblioteca.service;

import com.biblioteca.model.Livro;
import com.biblioteca.model.Usuario;
import com.biblioteca.model.Emprestimo;
import com.biblioteca.exception.LivroIndisponivelException;
import com.biblioteca.exception.UsuarioNaoEncontradoException;
import com.biblioteca.exception.LivroNaoEncontradoException;

import java.time.LocalDate;
import java.util.ArrayList;
import java.util.List;

/**
 * Serviço responsável por gerenciar as operações da biblioteca.
 */
public class BibliotecaService {

    private List<Livro> livros = new ArrayList<>();       // Lista de livros
    private List<Usuario> usuarios = new ArrayList<>();   // Lista de usuários
    private List<Emprestimo> emprestimos = new ArrayList<>(); // Lista de empréstimos

    // Método para adicionar um livro ao acervo
    public void adicionarLivro(Livro livro) {
        livros.add(livro);
    }

    // Método para adicionar um usuário
    public void adicionarUsuario(Usuario usuario) {
        usuarios.add(usuario);
    }

    // Método para emprestar um livro
    public void emprestarLivro(Long livroId, Long usuarioId) throws LivroIndisponivelException, UsuarioNaoEncontradoException, LivroNaoEncontradoException {
        Livro livro = buscarLivroPorId(livroId);
        Usuario usuario = buscarUsuarioPorId(usuarioId);

        if (!livro.isDisponivel()) {
            throw new LivroIndisponivelException("O livro não está disponível para empréstimo.");
        }

        livro.setDisponivel(false); // Marca o livro como indisponível
        Emprestimo emprestimo = new Emprestimo(
                (long) (emprestimos.size() + 1), // Gera um ID simples
                livro,
                usuario,
                LocalDate.now(), // Data do empréstimo
                LocalDate.now().plusDays(14) // Data de devolução (14 dias após o empréstimo)
        );
        emprestimos.add(emprestimo);
    }

    // Método para devolver um livro
    public void devolverLivro(Long livroId) throws LivroNaoEncontradoException {
        Livro livro = buscarLivroPorId(livroId);
        livro.setDisponivel(true); // Marca o livro como disponível

        // Remove o empréstimo da lista
        emprestimos.removeIf(emprestimo -> emprestimo.getLivro().getId().equals(livroId));
    }

    // Método para buscar um livro por ID
    public Livro buscarLivroPorId(Long livroId) throws LivroNaoEncontradoException {
        return livros.stream()
                .filter(l -> l.getId().equals(livroId))
                .findFirst()
                .orElseThrow(() -> new LivroNaoEncontradoException("Livro não encontrado."));
    }

    // Método para buscar um usuário por ID
    public Usuario buscarUsuarioPorId(Long usuarioId) throws UsuarioNaoEncontradoException {
        return usuarios.stream()
                .filter(u -> u.getId().equals(usuarioId))
                .findFirst()
                .orElseThrow(() -> new UsuarioNaoEncontradoException("Usuário não encontrado."));
    }

    // Método para listar livros disponíveis
    public List<Livro> listarLivrosDisponiveis() {
        return livros.stream()
                .filter(Livro::isDisponivel)
                .toList();
    }

    // Método para listar todos os empréstimos
    public List<Emprestimo> listarEmprestimos() {
        return emprestimos;
    }
}
```

---

### **5. Exceções Personalizadas**
Vamos criar exceções personalizadas para tratar erros específicos.

#### **5.1. `LivroIndisponivelException`**
```java
package com.biblioteca.exception;

/**
 * Exceção lançada quando um livro não está disponível para empréstimo.
 */
public class LivroIndisponivelException extends Exception {
    public LivroIndisponivelException(String message) {
        super(message);
    }
}
```

#### **5.2. `UsuarioNaoEncontradoException`**
```java
package com.biblioteca.exception;

/**
 * Exceção lançada quando um usuário não é encontrado.
 */
public class UsuarioNaoEncontradoException extends Exception {
    public UsuarioNaoEncontradoException(String message) {
        super(message);
    }
}
```

#### **5.3. `LivroNaoEncontradoException`**
```java
package com.biblioteca.exception;

/**
 * Exceção lançada quando um livro não é encontrado.
 */
public class LivroNaoEncontradoException extends Exception {
    public LivroNaoEncontradoException(String message) {
        super(message);
    }
}
```

---

### **6. Testando o Serviço**
Vamos testar a camada de serviço na classe `BibliotecaApp` (Main).

#### **6.1. Exemplo de Uso**
```java
package com.biblioteca;

import com.biblioteca.model.Livro;
import com.biblioteca.model.Usuario;
import com.biblioteca.service.BibliotecaService;
import com.biblioteca.exception.LivroIndisponivelException;
import com.biblioteca.exception.UsuarioNaoEncontradoException;
import com.biblioteca.exception.LivroNaoEncontradoException;

public class BibliotecaApp {
    public static void main(String[] args) {
        BibliotecaService bibliotecaService = new BibliotecaService();

        // Adicionando livros
        bibliotecaService.adicionarLivro(new Livro(1L, "Dom Quixote", "Miguel de Cervantes", "978-3-16-148410-0", true));
        bibliotecaService.adicionarLivro(new Livro(2L, "1984", "George Orwell", "978-0-452-28423-4", true));

        // Adicionando usuários
        bibliotecaService.adicionarUsuario(new Usuario(1L, "João Silva", "123.456.789-00", "joao@example.com"));
        bibliotecaService.adicionarUsuario(new Usuario(2L, "Maria Oliveira", "987.654.321-00", "maria@example.com"));

        try {
            // Emprestando um livro
            bibliotecaService.emprestarLivro(1L, 1L);
            System.out.println("Livro emprestado com sucesso!");

            // Tentando emprestar o mesmo livro novamente (deve lançar exceção)
            bibliotecaService.emprestarLivro(1L, 2L);
        } catch (LivroIndisponivelException | UsuarioNaoEncontradoException | LivroNaoEncontradoException e) {
            System.err.println("Erro: " + e.getMessage());
        }

        // Listando livros disponíveis
        System.out.println("Livros disponíveis:");
        bibliotecaService.listarLivrosDisponiveis().forEach(System.out::println);

        // Devolvendo um livro
        try {
            bibliotecaService.devolverLivro(1L);
            System.out.println("Livro devolvido com sucesso!");
        } catch (LivroNaoEncontradoException e) {
            System.err.println("Erro: " + e.getMessage());
        }

        // Listando empréstimos ativos
        System.out.println("Empréstimos ativos:");
        bibliotecaService.listarEmprestimos().forEach(System.out::println);
    }
}
```

---

### **7. Próximos Passos**
Agora que temos a camada de serviço funcionando, podemos:
1. **Adicionar persistência de dados** (usando um banco de dados como H2 ou MySQL).
2. **Escrever testes unitários** para garantir que a lógica de negócios está funcionando corretamente.
3. **Criar uma interface de usuário** (console ou gráfica).

Qual parte você gostaria de explorar a seguir? 😊