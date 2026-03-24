## Detecção Avançada em Active Directory e Integração SIEM

### Cenário
A maior parte dos ataques de Active Directory em ambientes reais passa despercebida porque as configurações de auditoria padrão do Windows são insuficientes. Este case documenta como transformar logs "mudos" em alertas acionáveis no QRadar.

### Desafios Técnicos
1. **Pontos Cegos:** Ataques de Pass-the-Hash não geram os mesmos alertas de um login convencional.
2. **Inconsistência de Logs:** Formatos XML variados dificultando a normalização no SIEM.
3. **Bloqueios de SO:** Políticas de UAC e Time Skew (Kerberos) que impediam tanto o ataque quanto a coleta.

### Metodologia de Resolução
* **Fase de Exploração:** Executei ataques de força bruta e dumping de NTDS.dit para entender exatamente quais Event IDs eram gerados.
* **Ajuste de Auditoria:** Modifiquei as GPOs do domínio para garantir que eventos de login de rede fossem registrados com detalhes de processo.
* **Customização de Coleta:** Reescrevi o script de coleta em PowerShell, implementando um parser XML para extrair o endereço IP de origem e o tipo de logon diretamente dos metadados do evento.
* **Correlação no QRadar:** Criei regras de comportamento que cruzam múltiplas falhas de login seguidas de um sucesso administrativo em curto intervalo de tempo.

### Conclusão
O projeto provou que a eficácia de um SOC não depende da ferramenta, mas do conhecimento sobre como o ataque ocorre na camada de protocolo. Conseguimos 100% de visibilidade sobre movimentação lateral e força bruta, eliminando pontos cegos críticos na infraestrutura de identidade.

---
*Projeto de estudo prático em Cybersecurity e Detecção.*
