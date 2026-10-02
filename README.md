# Quiz AZ-900

Simulado de estudo para a certificação **AZ-900: Microsoft Azure Fundamentals**, com **100 questões** de múltipla escolha. Cada tentativa sorteia **10 questões**, embaralha as alternativas e termina com uma **nota de 0 a 100**.

**Jogar:** https://heitorsp.github.io/quiz-az900/

> Questões originais, escritas para estudo. Este projeto não tem vínculo com a Microsoft e não reproduz questões da prova oficial.

## Como funciona

- 10 questões sorteadas do banco a cada tentativa, sem repetição dentro da mesma tentativa.
- 4 alternativas por questão, apenas uma correta, em ordem aleatória.
- Depois de responder, a página mostra se você acertou e uma explicação curta.
- Cada acerto vale 10 pontos. No final há uma revisão das 10 questões.
- A melhor nota fica salva no navegador (localStorage).
- Atalhos de teclado: `1`–`4` ou `A`–`D` para responder e `Enter` para avançar.

## Cobertura do banco

As questões seguem os domínios do guia de estudo oficial do AZ-900 (versão de 20 de julho de 2026), com a mesma proporção aproximada de peso.

| Domínio da prova | Peso na prova | Categorias no quiz | Questões |
|---|---|---|---:|
| Descrever conceitos de nuvem | 25–30% | Conceitos de nuvem (11), Benefícios da nuvem (8), Tipos de serviço (8) | 27 |
| Descrever a arquitetura e os serviços do Azure | 35–40% | Arquitetura do Azure (9), Computação e rede (11), Armazenamento (10), Identidade e segurança (10) | 40 |
| Descrever o gerenciamento e a governança do Azure | 30–35% | Custos (9), Governança e conformidade (8), Gerenciamento e implantação (8), Monitoramento (8) | 33 |

Guia de estudo oficial: https://learn.microsoft.com/credentials/certifications/resources/study-guides/az-900

## Estrutura

```
index.html      página do quiz (HTML, CSS e JavaScript, sem dependências)
questoes.json   banco de questões
```

## Como editar ou adicionar questões

Cada questão em `questoes.json` segue este formato:

```json
{
  "categoria": "Armazenamento",
  "pergunta": "Qual serviço oferece compartilhamentos de arquivos acessíveis por SMB e NFS?",
  "alternativas": ["Azure Files", "Azure Blob Storage", "Azure Queue Storage", "Azure Table Storage"],
  "explicacao": "O Azure Files pode ser montado como uma pasta de rede tradicional."
}
```

Regras:

- **A primeira alternativa é sempre a correta.** A página embaralha a ordem na hora de exibir.
- Use exatamente 4 alternativas, todas diferentes.
- Evite alternativas como "todas as anteriores" ou "nenhuma das anteriores", porque a ordem muda a cada tentativa.
- Procure manter as alternativas com tamanhos parecidos, para que a correta não se destaque por ser a mais longa.

O número de questões por tentativa está na constante `POR_TENTATIVA`, no `index.html`.

## Rodar localmente

A página carrega o `questoes.json` via `fetch`, então abrir o `index.html` direto do disco não funciona na maioria dos navegadores. Use um servidor local:

```bash
python3 -m http.server 8000
```

Depois acesse http://localhost:8000.

## Mantendo o conteúdo atualizado

O Azure muda com frequência: serviços são renomeados (o Azure Active Directory virou Microsoft Entra ID, por exemplo) e o guia da prova é revisado periodicamente. Antes de estudar para a prova, confira o guia oficial e ajuste as questões que estiverem desatualizadas.
