# 📚 Sistema de Gerenciamento de Biblioteca - Java

## Estrutura do Projeto

```
src/
├── Main.java                    ← entrada (Scanner + Switch Case + Menu)
├── model/
│   ├── ItemBiblioteca.java      ← Classe ABSTRATA (base)
│   ├── Livro.java               ← Herda de ItemBiblioteca
│   ├── Revista.java             ← Herda de ItemBiblioteca
│   ├── LivroDigital.java        ← Herda de ItemBiblioteca
│   └── Usuario.java             ← Classe normal com Array de empréstimos
└── service/
    └── Biblioteca.java          ← Gerencia acervo, usuários e empréstimos
```

---

## Conceitos Java utilizados

| Conceito           | Onde aparece                                                  |
|--------------------|---------------------------------------------------------------|
| Classe Abstrata    | `ItemBiblioteca.java` — não pode ser instanciada diretamente  |
| Método Abstrato    | `exibirDetalhes()` em `ItemBiblioteca`                        |
| Herança            | `Livro`, `Revista`, `DVD` herdam de `ItemBiblioteca`          |
| Construtores       | Todas as classes possuem construtores com parâmetros          |
| `super()`          | Subclasses chamam o construtor da classe pai                  |
| Classes e Objetos  | `new Livro(...)`, `new Usuario(...)`, `new Biblioteca()`      |
| Arrays             | Acervo e usuários armazenados em arrays                       |
| Scanner            | Leitura de entrada no terminal em `Main.java`                 |
| Switch Case        | Menu principal e submenu de tipo de item                      |
| If / Else          | Validações de empréstimo, busca, limites                      |
| Laços (for/while)  | Percorrer acervo, buscar itens, listar usuários               |

---

## Como compilar e executar

### Pré-requisito
- Java JDK 8 ou superior instalado

### Compilar (execute dentro da pasta `src/`)
```bash
javac model/ItemBiblioteca.java model/Livro.java model/Revista.java model/LivroDigital.java model/Usuario.java service/Biblioteca.java Main.java
```

### Executar (ainda dentro de `src/`)
```bash
java Main
```

---

## Funcionalidades do sistema

1. **Cadastrar item** — Livro, Revista ou DVD com seus atributos específicos
2. **Cadastrar usuário** — Nome, CPF e e-mail
3. **Realizar empréstimo** — Vincula um item a um usuário (limite de 3 por usuário)
4. **Realizar devolução** — Libera o item e remove do histórico do usuário
5. **Listar acervo** — Exibe todos os itens com status (disponível/emprestado)
6. **Buscar por título** — Pesquisa por parte do nome do item
7. **Listar usuários** — Mostra todos os usuários cadastrados
8. **Ver empréstimos** — Consulta itens emprestados por um usuário
9. **Estatísticas** — Resumo do acervo e empréstimos ativos

---

## Dados de exemplo (carregados automaticamente)

| Código | Tipo    | Título                  |
|--------|---------|-------------------------|
| L001   | Livro   | Dom Casmurro            |
| L002   | Livro   | O Senhor dos Anéis      |
| L003   | Livro   | Clean Code              |
| R001   | Revista | National Geographic     |
| R002   | Revista | Scientific American     |
| D001   | Digital | O Sobrinho do Mago epub |
| D002   | Digital | A Última Batalha epub   |

**Usuários pré-cadastrados:**
- Ana Silva — CPF: `111.111.111-11`
- Carlos Souza — CPF: `222.222.222-22`
