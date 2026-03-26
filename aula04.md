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
```

