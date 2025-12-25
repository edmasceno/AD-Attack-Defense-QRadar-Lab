## Ataque e Detecção em Ambiente Active Directory Integrado ao SIEM

## 📌 Contexto
Ao criar um ambiente de estudos focado em Active Directory, percebi que ataques comuns ao AD muitas vezes não são detectados quando a detecção se baseia apenas nas configurações padrão do Windows e do SIEM.

## 🎯 Objetivo
Realizar um ataque simulado realista em um domínio Windows e criar mecanismos de detecção capazes de identificar atividades maliciosas que, a princípio, não eram perceptíveis.

## 🚧 Dificuldades Encontradas
- Ataques bem-sucedidos sem avisos evidentes
- Ocorrências de log com diferentes formatos XML
- Erros de autenticação devido a desvio de tempo
- Restrições de UAC dificultando a coleta completa

## 🔍 Método Técnico
A estratégia implementada incluiu:
- Realização controlada de ataques (brute force, credential dumping, Pass-the-Hash)
- Avaliação minuciosa dos eventos produzidos
- Modificações na coleta e análise de logs
- Desenvolvimento de detecções personalizadas no IBM QRadar

## 🛠️ Soluções Aplicadas
- Ajuste da sincronização temporal
- Modificações nas políticas de UAC
- Revisão dos roteiros de coleta
- Correlação de eventos no SIEM

## ✅ Conclusão
Após as correções, o SIEM passou a reconhecer de forma precisa:
- Tentativas de ataque por força bruta
- Autenticações administrativas suspeitas
- Movimentação lateral por meio da técnica Pass-the-Hash

## 🤖 Uso de Inteligência Artificial como Ferramenta de Apoio
Ferramentas de Inteligência Artificial foram empregadas como suporte ao processo de aprendizado durante o desenvolvimento deste estudo de caso técnico, especialmente na interpretação de conceitos relacionados ao Active Directory, protocolos de autenticação e eventos de segurança.

A IA foi utilizada principalmente para:
- Contribuir para a compreensão de como ataques se manifestam em ambientes Active Directory
- Apoiar a interpretação de eventos e a análise de estruturas de log em formato XML
- Auxiliar na estruturação do raciocínio para a elaboração de detecções
- Avaliar a clareza e a coesão da documentação final

Todas as atividades práticas, testes, validações e ajustes de detecção foram executados diretamente no ambiente de laboratório. A IA atuou como recurso complementar de apoio ao entendimento, sem substituir a análise crítica nem a execução técnica.

Esse uso reflete práticas contemporâneas do mercado, nas quais a capacidade de empregar IA de forma consciente e responsável contribui para o desenvolvimento técnico contínuo.

## 🧠 Lições Aprendidas
Este case demonstrou que a eficácia da detecção depende menos das ferramentas utilizadas e mais da capacidade de compreender como os ataques se manifestam nos logs.

## 📎 Referência Técnica
A documentação completa do laboratório, incluindo evidências e comandos empregados, pode ser encontrada em:
- `AD Attack & Defense QRadar Lab`

---

*Case técnico desenvolvido como parte de estudos práticos em Cibersegurança e Blue Team Operations.*
