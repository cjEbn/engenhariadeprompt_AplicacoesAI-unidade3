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

# 5. Resultado refinado

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

### Explicação:

* Função `obter_nota` garante entrada válida
* `try/except` trata erros de digitação
* Condicional verifica aprovação
* Código modular melhora reutilização

---

# 6. Versão final (Prompt Mestre em YAML)

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

---
# Aula 04 - Persona e Geração de Texto tarefa 01

## 🔹 Tema escolhido: O que é um banco de dados?

---


Tarefa 1 - Persona e Geração de Texto
Tema: O que é um banco de dados?
🏴‍☠️ Persona 1: Pirata Engraçado

Um banco de dados, meu caro marujo, é como um grande baú do tesouro onde guardamos todas as riquezas (informações)! Em vez de ouro e joias, temos dados organizados para não se perderem nos sete mares.

Quando precisamos de algo, não saímos revirando tudo como um pirata desesperado — usamos um mapa bem feito para encontrar exatamente o que queremos. Esse mapa é o sistema que organiza os dados dentro do baú!

🧠 Persona 2: Arquiteto de Sistemas de Nível Mundial

Um banco de dados é um sistema estruturado para armazenamento, gerenciamento e recuperação eficiente de dados. Ele permite organizar informações de forma lógica, garantindo integridade, consistência e segurança.

Em arquiteturas modernas, bancos de dados são essenciais para suportar aplicações escaláveis, podendo ser relacionais ou não relacionais, dependendo da necessidade. Eles operam com consultas otimizadas e mecanismos de controle de concorrência para garantir desempenho e confiabilidade.

🔹 Análise

O texto do arquiteto de sistemas é mais tecnicamente preciso, pois utiliza conceitos como integridade, consistência, escalabilidade e tipos de banco de dados. Ele descreve o funcionamento real dentro de um contexto de engenharia de software.

Já o texto do pirata utiliza analogias que facilitam o entendimento, mas simplifica o conceito e não aborda detalhes técnicos importantes.
