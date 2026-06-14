# 🗺️ Plano de Implantação: PortfolioHUB + IA GEMINI

Este documento registra o planejamento, a governança e as diretrizes de segurança adotadas para a implantação do **PortfolioHUB**, utilizando a infraestrutura do GitHub Pages e o suporte consultivo do Google GEMINI.

---

## 1. Declaração de Uso de Inteligência Artificial (Ética e Transparência)

Em estrita conformidade com as diretrizes do Código de Ética da EaD, declara-se que o modelo de linguagem **Google GEMINI** foi utilizado ativamente como ferramenta de apoio, mentoria e co-piloto ao longo deste projeto.

A inteligência artificial foi aplicada especificamente para:
* Auxiliar na estruturação do cronograma e plano de implantação;
* Validar e sugerir melhorias nas políticas de segurança e permissões do GitHub;
* Fornecer checklists de testes de integração e roteirização da apresentação final.

*Nota: Toda a execução prática, configuração de repositórios, gestão de acessos e desenvolvimento do código foram realizadas de forma individual pelo estudante.*

---

## 2. Escopo e Objetivos do Projeto

O PortfolioHUB atua como um orquestrador centralizado para exibir e gerenciar projetos e portfólios digitais do perfil `pedromfv`. 

### Repositórios Integrados ao Ecossistema:
1. **`pedromfv/pedromfv.github.io`** (Núcleo do PortfolioHUB - Ambiente de Produção)
2. **`pedromfv/frequencies`** (Subprojeto - Aplicação Web Institucional em CSS)
3. **`pedromfv/starfox-but-on-java`** (Subprojeto - Engine 3D e Jogo em Java)

---

## 3. Gestão de Usuários e Segurança

Para mitigar riscos de deploy acidental e garantir a robustez do ambiente, foram implementadas as seguintes políticas de governança recomendadas pela IA:

* **Princípio do Menor Privilégio (PoLP):** O proprietário possui controle administrativo, blindando o acesso direto à produção.
* **Autenticação Segura:** Uso obrigatório de chaves SSH criptografadas e autenticação em dois fatores (2FA) na conta proprietária.
* **Regras de Proteção de Branch (Branch Protection Rules):** Bloqueio de pushes diretos na branch `main`. É mandatória a criação de branches secundárias e abertura de *Pull Requests*.
* **GitHub Dependabot:** Ativado para varredura e alertas automáticos de vulnerabilidades em dependências do código.
* **Secret Scanning & Push Protection:** Proteção ativa contra o vazamento acidental de chaves de API ou credenciais no código público.

---

## 4. Fluxo de Trabalho e Colaboração (Gitflow)

O compartilhamento de código e a colaboração no projeto seguem o fluxo profissional padrão do mercado:
1. **Issues:** Utilizadas para documentar melhorias, bugs ou novas demandas antes de qualquer alteração no código.
2. **Forks & Branches:** Colaboradores devem criar forks e trabalhar em branches temáticas descritivas (ex: `feature/nova-section`).
3. **Code Review:** Alterações só entram em produção na `main` após a validação do Pull Request e checagem de integridade dos alertas de segurança.

---

## 5. Plano de Testes de Integração (CI/CD)

A entrega final foi validada através de uma matriz de testes funcionais para homologar o ambiente:

| ID | Cenário de Teste | Procedimento | Resultado Esperado | Status |
| :--- | :--- | :--- | :--- | :--- |
| **TC-01** | Bloqueio de Push Direto | Executar `git push origin main` localmente. | O GitHub deve rejeitar a operação devido às travas de segurança. | ✅ PASSOU |
| **TC-02** | Integração via Pull Request | Alterar o arquivo `index.html` em branch separada e abrir PR. | PR criado com sucesso aguardando revisão e merge. | ✅ PASSOU |
| **TC-03** | Deploy Automatizado (CI/CD) | Realizar o Merge do PR na branch `main`. | O GitHub Actions deve atualizar o site em produção em até 2 minutos. | ✅ PASSOU |
| **TC-04** | Varredura de Segurança | Simular inclusão de credencial sensível no código e dar push. | O *Push Protection* deve identificar o padrão e travar o envio. | ✅ PASSOU |

---
*Plano gerado e validado em 14 de junho de 2026 para a entrega do Desafio Final.*
