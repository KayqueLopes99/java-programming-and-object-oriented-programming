## 🏗️ 1. Lombok (Redução de Boilerplate)
Anotações usadas para evitar a escrita manual de getters, setters e construtores.

| Anotação | Descrição |
| :--- | :--- |
| `@Data` | Atalho que combina `@Getter`, `@Setter`, `@ToString`, `@EqualsAndHashCode` e `@RequiredArgsConstructor`. |
| `@NoArgsConstructor` | Gera um construtor vazio (sem argumentos), exigido pelo JPA. |
| `@AllArgsConstructor` | Gera um construtor com todos os campos da classe como parâmetros. |
| `@EqualsAndHashCode` | Gera os métodos `equals()` e `hashCode()`. O parâmetro `(callSuper = true)` inclui os campos da superclasse na comparação. |

---

## 🏛️ 2. Mapeamento de Entidade e Tabela
Define como a classe Java se comporta em relação ao banco de dados.

| Anotação | Descrição |
| :--- | :--- |
| `@Entity` | Informa ao JPA que a classe é uma entidade que deve ser mapeada para uma tabela. |
| `@Table(name = "...")` | Especifica o nome exato da tabela no banco de dados. |
| `@Id` | Define qual atributo é a Chave Primária (Primary Key) da tabela. |
| `@GeneratedValue` | Define a estratégia de geração automática do ID (ex: `IDENTITY` para auto-incremento do banco). |

---

## 🌳 3. Estratégias de Herança
Utilizadas quando você tem uma classe pai (como `Usuario`) e classes filhas (como `Leitor` ou `Admin`).

| Anotação | Descrição |
| :--- | :--- |
| `@Inheritance` | Define a estratégia de herança. `SINGLE_TABLE` cria uma única tabela para toda a hierarquia. |
| `@DiscriminatorColumn` | Define o nome da coluna que servirá para distinguir qual é o tipo de subclasse na tabela única. |
| `@DiscriminatorValue` | Define o valor que será gravado na coluna de discriminador para identificar aquela classe específica. |

---

## 📝 4. Mapeamento de Atributos e Colunas
Define detalhes técnicos de como cada campo será tratado no banco.

| Anotação | Descrição |
| :--- | :--- |
| `@Column` | Configura detalhes da coluna: `nullable` (se aceita nulo), `unique` (valor único), `name` (nome da coluna) e `columnDefinition` (tipo SQL puro, como `TEXT`). |
| `@Enumerated` | Define como um Enum deve ser salvo. `EnumType.STRING` salva o nome da opção em vez do índice numérico. |

---

## 🔗 5. Relacionamentos entre Entidades
Configura como as tabelas se conectam (chaves estrangeiras e tabelas associativas).

| Anotação | Descrição |
| :--- | :--- |
| `@ManyToMany` | Indica uma relação de Muitos-para-Muitos entre as entidades. |
| `@JoinTable` | Define a "tabela de ligação" para relações N:N. |
| `name = "..."` | Nome da tabela intermediária. |
| `joinColumns` | Define a FK (Chave Estrangeira) da entidade atual na tabela de ligação. |
| `inverseJoinColumns` | Define a FK da entidade relacionada (do outro lado) na tabela de ligação. |

