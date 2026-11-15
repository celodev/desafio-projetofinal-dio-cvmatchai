# 🎯 CVMatch AI — Otimizador de Currículos para ATS

> *"Seu talento merece chegar até o RH."*

Aplicação web SaaS desenvolvida com inteligência artificial especializada em análise e otimização de currículos para sistemas ATS (*Applicant Tracking System*). O sistema avalia a compatibilidade do candidato com as exigências da vaga, identifica palavras-chave faltantes e gera uma versão aprimorada do currículo — **com regra inegociável de integridade: sem inventar experiências ou competências fictícias**.

🌐 **Aplicação publicada:** [https://desafio-final-dio-cv-match-and-polish.lovable.app](https://desafio-final-dio-cv-match-and-polish.lovable.app)

---

## 📌 1. Problema que a Aplicação Resolve

Candidatos altamente qualificados são frequentemente eliminados em etapas iniciais de processos seletivos por barreiras técnicas dos sistemas de triagem automatizada (ATS):
- **Barreira dos filtros ATS:** Softwares de recrutamento descartam currículos que não contenham correspondência semântica e palavras-chave específicas da vaga anunciada.
- **Adaptação manual cansativa:** Personalizar o currículo para cada vaga exige tempo, paciência e conhecimento técnico sobre leitura automatizada.
- **Risco de alucinação de IAs genéricas:** Ferramentas de IA padrão tendem a inventar competências, números, cursos e experiências inexistentes para inflar o currículo do usuário.

O **CVMatch AI** resolve essa dor: analisa a vaga e o currículo real do usuário, aponta as lacunas com transparência e reestrutura o conteúdo com linguagem profissional e formatação legível por robôs, preservando 100% da veracidade da trajetória do candidato.

---

## 🔄 2. Como a Análise Funciona

O fluxo opera de ponta a ponta em 5 etapas:

1. **Entrada de Dados:** O usuário insere a descrição completa da vaga em um campo e o texto do seu currículo atual no outro.
2. **Processamento Inteligente (IA):**
   - Extrai requisitos obrigatórios, desejáveis e competências técnicas/comportamentais da vaga.
   - Cruza os requisitos com o histórico profissional do candidato.
   - Aplica regra de pontuação ponderada: requisitos obrigatórios (peso 2), desejáveis (peso 1) e parciais (metade).
   - Mapeia palavras-chave encontradas (verdes), ausentes (vermelhas) e requisitos parciais (amarelos).
3. **Dashboard de Diagnóstico:** Apresenta o percentual estimado de compatibilidade (*score/match*) e sugestões práticas de aprimoramento.
4. **Geração do Currículo Otimizado:** A IA reorganiza as informações verdadeiras em uma estrutura compatível com ATS (seções padronizadas, sem tabelas complexas ou colunas que quebram a leitura automatizada).
5. **Edição e Exportação:** O usuário pode revisar, ajustar manualmente o texto gerado e exportar em PDF pesquisável (texto selecionável) ou copiar a versão formatada.

---

## 🧠 3. Mega Prompt Utilizado e Evolução

### O Mega Prompt Inicial
O projeto partiu de uma especificação completa de produto SaaS, estabelecendo identidade, arquitetura, design system e a regra inegociável de integridade:

```text
1. CONTEXTO DO PROJETO
Crie uma aplicação web SaaS chamada CVMatch AI, especializada em análise e otimização de currículos para sistemas ATS (Applicant Tracking System).
Slogan: Seu talento merece chegar até o RH.

2. OBJETIVO PRINCIPAL
- Inserir descrição da vaga e conteúdo do currículo.
- Análise de compatibilidade com percentual estimado.
- Identificação de palavras-chave encontradas e ausentes.
- Recomendações e versão otimizada do currículo para exportação em PDF.

3. REGRA FUNDAMENTAL DE INTEGRIDADE
Nunca invente informações profissionais do candidato. A IA pode reorganizar e melhorar a clareza, mas NUNCA inventar empresas, cargos, cursos ou habilidades não informadas. Competências faltantes devem ser exibidas como lacunas.

4. DESIGN SYSTEM & ARQUITETURA
- Biblioteca: shadcn/ui, Tailwind CSS, Lucide React.
- Paleta: Azul-marinho (#172554), Azul (#2563EB), Roxo (#7C3AED), Verde (#16A34A).
- Single Page Application (SPA), responsiva para desktop e mobile, sem login na primeira versão.

5. PROCESSAMENTO E EXPORTAÇÃO
- Análise segura sem expor chaves de API no frontend.
- Dashboard com compatibilidade, tags e recomendações.
- Currículo em layout convencional para ATS com exportação em PDF real (texto selecionável).
```

### O que mudou até a versão final
- **Transição de prompt monolítico para engenharia incremental:** Ao invés de reconstruir a aplicação a cada mudança (o que gastaria créditos excessivos), adotou-se uma estratégia de auditoria técnica prévia e correções em microtarefas isoladas.
- **Normalização de dados no cálculo de ATS:** Foram tratados espaçamentos, quebras de linha e caracteres equivalentes para que variações de digitação não diminuíssem injustamente o percentual de correspondência.
- **Filtro de formatação do PDF:** Ajustou-se o algoritmo de detecção de títulos para não quebrar siglas técnicas (como `SQL`, `AWS`, `API`) como se fossem cabeçalhos de seção.

---

## 🛠️ 4. Ajustes Solicitados após a Primeira Geração (e por quê)

Após a geração da primeira versão funcional no Lovable, foram realizadas rodadas de refinamento técnico:

### 1. Auditoria Técnica e Garantia de Integridade
- **O que foi ajustado:** Implementação de validações para assegurar que a IA não inventasse números, métricas de resultado ou anos de experiência inexistentes.
- **Por quê:** Proteger a integridade e a credibilidade do candidato em entrevistas de emprego reais.

### 2. Correção de Siglas e Títulos na Exportação em PDF
- **O que foi ajustado:** Apenas cabeçalhos estruturais conhecidos e a primeira linha de cada bloco passam a ser tratados como títulos no documento PDF.
- **Por quê:** O sistema estava confundindo siglas de tecnologias em caixa alta (`AWS`, `REST`, `CI/CD`) com títulos de seção, desconfigurando a paginação.

### 3. Estratégia Modular com Foco em Economia de Créditos (Copilot)
- **O que foi ajustado:** O roadmap foi estruturado em fases de microtarefas isoladas (Fase 1: SEO/GEO; Fase 2: DOCX; Fase 3: Autenticação/Resend; Fase 4: Histórico; Fase 5: Dashboard).
- **Por quê:** Executar pequenos prompts focados impede que o Lovable recompile ou refatore o projeto inteiro desnecessariamente, preservando os créditos e mantendo o código estável.

---

## 📸 5. Demonstração e Telas da Aplicação

### Interface da Aplicação em Execução
Tela principal desenvolvida no Lovable com identidade visual SaaS moderna, navegação intuitiva e fluxo guiado em 3 etapas (*Seus dados ➔ Análise de compatibilidade ➔ Currículo otimizado*):

![Interface do CVMatch AI](<img width="1366" height="607" alt="image" src="https://github.com/user-attachments/assets/b66e4c46-2566-48a6-822c-3195ce0ca8f3" />
)

---

### Exemplo de Teste Real (Caso de Uso)
O sistema foi validado utilizando um caso de uso real de **Analista de Suporte Técnico / Infraestrutura de TI**:

- **Currículo de Teste:** Histórico profissional real com experiências corporativas (Active Directory, GLPI, Gestão de SLA, Infraestrutura de Redes/CFTV, suporte a clientes de grande porte) e formação acadêmica em Análise e Desenvolvimento de Sistemas e Pós-Graduação em Inteligência Artificial.
- **Resultado Gerado:**
  1. Reorganização clara do resumo profissional destacando vivência em atendimento N1/N2 corporativo;
  2. Mapeamento fiel de competências sem nenhuma informação inventada;
  3. Geração de PDF padronizado para ATS, com texto pesquisável, seções convencionais e hierarquia visual perfeita.

![Demonstração do Currículo Otimizado em PDF] (<img width="1051" height="583" alt="image" src="https://github.com/user-attachments/assets/4850013b-74ba-419b-83e5-c6bfb5a02513" />)

---

## 🗺️ Roadmap de Evolução

- [x] **Fase 1:** SEO técnico e GEO (*Generative Engine Optimization* com Schema.org e FAQs estruturadas).
- [ ] **Fase 2:** Exportação de currículo no formato Microsoft Word (.DOCX).
- [ ] **Fase 3:** Autenticação de usuários e confirmação de e-mail via Resend.
- [ ] **Fase 4:** Persistência de banco de dados e histórico de análises por candidato.
- [ ] **Fase 5:** Dashboard com acompanhamento da evolução do score entre versões de currículo.

---

## 🧰 Tecnologias Utilizadas

- **Frontend & Engine:** [Lovable](https://lovable.dev)
- **Linguagem & Framework:** React, TypeScript, Tailwind CSS
- **Componentes & Ícones:** shadcn/ui, Lucide React
- **Hospedagem & Deploy:** Lovable Cloud
- **Versionamento:** GitHub

---

## 👨‍💻 Autor

Projeto desenvolvido por **Marcelo dos Santos Almeida** como entrega final do Desafio de Projeto da [Digital Innovation One (DIO)](https://dio.me).
