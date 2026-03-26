(Hands-On Lab)

# 1. Problema escolhido

Criar um programa em Python que calcula a média de um aluno com validação de entrada.

---

# 2. Primeira iteração (vaga)

### Prompt:

> Faça um programa em Python que calcule a média.

### Resposta obtida (ruim):

```python
media = (5 + 7 + 8) / 3
print(media)
```

### Problemas:

* Não recebe dados do usuário
* Não valida entrada
* Não tem contexto de uso
* Não informa aprovação/reprovação
* Não segue boas práticas

---

# 3. Aplicação da Arquitetura Modular

## Papel (Role)

A IA deve atuar como professor de programação experiente.

## Contexto (In-Context Learning)

* Público: iniciantes em Python
* Objetivo: ensinar entrada de dados, validação e lógica condicional
* Ambiente: execução em terminal

## Instrução (Task)

Criar um programa que:

* Solicite 3 notas ao usuário
* Valide valores entre 0 e 10
* Calcule a média
* Informe se o aluno foi aprovado (média ≥ 7)

## Formato (Output Constraints)

* Código em Python
* Comentários explicativos
* Estrutura organizada
* Explicação simples após o código

---

# 4. Prompt estruturado

```markdown
Você é um professor de programação experiente.

Contexto:
O código será utilizado por alunos iniciantes em Python que estão aprendendo entrada de dados, validação e estruturas condicionais.

Instrução:
Crie um programa em Python que:
- Solicite 3 notas ao usuário
- Valide se os valores estão entre 0 e 10
- Calcule a média
- Informe se o aluno foi aprovado (média >= 7)

Formato:
- Código organizado
- Comentários explicativos
- Explicação simples após o código
```

---

## 5. Resultado refinado

```python
def obter_nota(mensagem):
    while True:
        try:
            nota = float(input(mensagem))
            if 0 <= nota <= 10:
                return nota
            else:
                print("Digite uma nota entre 0 e 10.")
        except ValueError:
            print("Entrada inválida.")

nota1 = obter_nota("Digite a primeira nota: ")
nota2 = obter_nota("Digite a segunda nota: ")
nota3 = obter_nota("Digite a terceira nota: ")

media = (nota1 + nota2 + nota3) / 3

print(f"Média: {media:.2f}")

if media >= 7:
    print("Aluno aprovado.")
else:
    print("Aluno reprovado.")
```

**Explicação:**

* Função `obter_nota` garante entrada válida
* `try/except` trata erros de digitação
* Condicional verifica aprovação
* Código modular melhora reutilização

---

## 6. Versão final (Prompt Mestre em YAML)

```yaml
papel: Professor de programação experiente

contexto:
  publico: Iniciantes em Python
  objetivo: Ensinar entrada de dados, validação e lógica condicional
  ambiente: Terminal

instrucao:
  descricao: Criar um programa de cálculo de média escolar
  requisitos:
    - Solicitar 3 notas do usuário
    - Validar valores entre 0 e 10
    - Calcular média
    - Informar aprovação (media >= 7)

formato:
  - Código Python
  - Comentários explicativos
  - Explicação após o código

saida_esperada:
  codigo: |
    def obter_nota(mensagem):
        while True:
            try:
                nota = float(input(mensagem))
                if 0 <= nota <= 10:
                    return nota
                else:
                    print("Digite uma nota entre 0 e 10.")
            except ValueError:
                print("Entrada inválida.")

    nota1 = obter_nota("Digite a primeira nota: ")
    nota2 = obter_nota("Digite a segunda nota: ")
    nota3 = obter_nota("Digite a terceira nota: ")

    media = (nota1 + nota2 + nota3) / 3

    print(f"Média: {media:.2f}")

    if media >= 7:
        print("Aluno aprovado.")
    else:
        print("Aluno reprovado.")

  explicacao: |
    O programa solicita notas, valida entradas, calcula a média e informa o resultado final.
```

---

# Aula 04 - Persona e Geração de Texto - Tarefa 01

## 🔹 Tema escolhido: O que é um banco de dados?

---

## 🏴‍☠️ Persona 1: Pirata Engraçado

Um banco de dados, meu caro marujo, é como um grande baú do tesouro onde guardamos todas as riquezas (informações)! Em vez de ouro e joias, temos dados organizados para não se perderem nos sete mares.

Quando precisamos de algo, não saímos revirando tudo como um pirata desesperado — usamos um mapa bem feito para encontrar exatamente o que queremos. Esse mapa é o sistema que organiza os dados dentro do baú!

---

## 🧠 Persona 2: Arquiteto de Sistemas de Nível Mundial

Um banco de dados é um sistema estruturado para armazenamento, gerenciamento e recuperação eficiente de dados. Ele permite organizar informações de forma lógica, garantindo integridade, consistência e segurança.

Em arquiteturas modernas, bancos de dados são essenciais para suportar aplicações escaláveis, podendo ser relacionais ou não relacionais, dependendo da necessidade. Eles operam com consultas otimizadas e mecanismos de controle de concorrência para garantir desempenho e confiabilidade.

---

## 🔹 Análise

O texto do arquiteto de sistemas é mais tecnicamente preciso, pois utiliza conceitos como integridade, consistência, escalabilidade e tipos de banco de dados. Ele descreve o funcionamento real dentro de um contexto de engenharia de software.

Já o texto do pirata utiliza analogias que facilitam o entendimento, mas simplifica o conceito e não aborda detalhes técnicos importantes.


---

# Aula 04 - Tarefa 02 - Framework RTG

## 🔹 Prompt Estruturado (RTG)

**Papel (Role):**
Você é um instrutor de Python experiente.

**Tarefa (Task):**
Crie uma função que calcule a média de uma lista de números, incluindo tratamento de erros rigoroso para listas vazias.

**Formato (Format):**
Forneça o código Python amplamente comentado, seguido de exatos três casos de teste.

---

## 🔹 Resultado Gerado

```python
def calcular_media(lista):
    """
    Função que calcula a média de uma lista de números.
    Realiza validações para garantir que a lista não esteja vazia
    e que todos os elementos sejam numéricos.
    """
    
    # Verifica se a lista está vazia
    if not lista:
        raise ValueError("A lista não pode estar vazia.")
    
    # Verifica se todos os elementos são números
    for item in lista:
        if not isinstance(item, (int, float)):
            raise TypeError("Todos os elementos da lista devem ser números.")
    
    # Calcula a média
    soma = sum(lista)
    media = soma / len(lista)
    
    return media


# Casos de teste

# Teste 1: Lista válida
print(calcular_media([10, 8, 6]))

# Teste 2: Lista com erro (vazia)
try:
    print(calcular_media([]))
except ValueError as e:
    print(e)

# Teste 3: Lista com valor inválido
try:
    print(calcular_media([10, "a", 5]))
except TypeError as e:
    print(e)
```

---

## 🔹 Observação

O uso do framework RTG (Role, Task, Format) permite estruturar o prompt de forma clara, reduzindo ambiguidades e garantindo que a resposta atenda exatamente aos requisitos definidos.

---

Tarefa 3 - Reflexão Crítica

A definição explícita de um papel (persona) melhora significativamente a qualidade e a estrutura técnica das respostas geradas pela inteligência artificial. Ao atribuir um papel específico, como “instrutor de Python experiente”, o modelo passa a adotar um vocabulário mais adequado, maior rigor técnico e uma organização mais clara das informações.

Isso reduz ambiguidades e direciona a resposta para um padrão mais profissional, alinhado ao contexto solicitado. Sem a definição de persona, as respostas tendem a ser mais genéricas e menos consistentes em termos técnicos. Portanto, o uso de papéis é uma estratégia essencial na engenharia de prompt para obter resultados mais precisos e confiáveis.

## 📄 Versão em PDF

Clique abaixo para visualizar ou baixar o documento completo:

👉[Baixar Aula 04 (PDF)](./aula04.pdf)
