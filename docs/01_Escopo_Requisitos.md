# 01_Escopo_e_Requisitos_App_EBD

## 1. Visão Geral do Projeto

O objetivo principal deste aplicativo web é otimizar e padronizar a gestão da Escola Bíblica Dominical (EBD) para diversas igrejas, incluindo sedes e congregações. Ele visa atender às necessidades de Pastores, Superintendentes, Professores e Alunos, centralizando informações e processos que hoje são, em sua maioria, manuais.

## 2. Casos de Uso por Papel do Usuário

### 2.1. Administrador Global (Mantenedor do App)

* **Gerenciar Igrejas Cadastradas:** Cadastrar, editar, ativar/desativar novas igrejas no sistema, e designar o Pastor Presidente inicial para cada uma.
* **Monitorar Uso do Sistema:** Acompanhar estatísticas gerais de uso, performance e integridade do aplicativo.

### 2.2. Pastor Presidente / Administrador da Igreja (Nível Igreja Sede)

* **Gerenciar Estrutura da Igreja no App:** Configurar dados da Igreja Sede, cadastrar e editar congregações filiadas, e designar pastores para cada congregação.
* **Gerenciar Usuários da Igreja:** Cadastrar e gerenciar credenciais de Pastores da Congregação e Superintendentes (para sede e congregações).
* **Gerenciar Conteúdo Global da Igreja:** Cadastrar trimestres e lições que serão padrão para toda a igreja (sede e congregações). Anexar materiais complementares globais.
* **Acompanhar Desempenho Global da EBD:** Visualizar relatórios consolidados de frequência, desempenho de alunos e ofertas de todas as congregações.
* **Enviar Comunicados Globais da Igreja:** Publicar avisos para todos os usuários da igreja.

### 2.3. Pastor da Congregação (Nível Congregação)

* **Gerenciar Superintendentes da Minha Congregação:** Cadastrar, editar e remover superintendentes sob sua gestão.
* **Acompanhar Desempenho da EBD na Minha Congregação:** Visualizar relatórios de frequência e desempenho específicos da sua congregação.
* **Enviar Comunicados da Congregação:** Publicar avisos para os Superintendentes, Professores e Alunos da sua congregação.

### 2.4. Superintendente (Nível Congregação/Sede - EBD Local)

* **Gerenciar Professores da Minha EBD:** Cadastrar, editar e remover professores.
* **Gerenciar Alunos da Minha EBD:** Cadastrar, editar e remover alunos. Matricular e desmatricular alunos em turmas.
* **Gerenciar Turmas da Minha EBD:** Criar, editar e excluir turmas. Atribuir professores às turmas.
* **Gerenciar Conteúdo da Minha EBD (Local):** Cadastrar trimestres e lições (se a congregação tiver autonomia) e anexar materiais complementares específicos da EBD local.
* **Acompanhar Desempenho da Minha EBD:** Visualizar relatórios de frequência e desempenho por turma/aluno.
* **Enviar Comunicados da Minha EBD:** Enviar avisos para professores e alunos da EBD sob sua gestão.
* **Registrar Oferta da Turma:** Visualizar e consolidar as ofertas registradas pelos professores de sua EBD.

### 2.5. Professor

* **Gerenciar Alunos da Minha Turma:** Visualizar lista de alunos e atualizar dados básicos.
* **Registrar Frequência:** Marcar a presença dos alunos em cada aula.
* **Gerenciar Lições da Minha Turma:** Visualizar lições do trimestre atual e acessar materiais complementares. Registrar notas ou avaliações por lição.
* **Registrar Oferta da Turma:** Inserir o valor da oferta arrecadada em sua turma.
* **Comunicar-se com a Turma:** Enviar mensagens específicas para a turma e responder a mensagens de alunos.
* **Visualizar Alertas de Faltas dos Alunos:** Acompanhar quais alunos de sua turma receberam alertas de faltas.
* **Enviar Mensagem de Encorajamento Personalizada:** Enviar mensagens individuais de apoio a alunos.

### 2.6. Aluno

* **Acessar Conteúdo da Lição:** Visualizar lições do trimestre e acessar materiais complementares.
* **Acompanhar Desempenho Pessoal:** Visualizar sua própria frequência e notas.
* **Comunicar-se com o Professor:** Visualizar mensagens da turma e enviar mensagens diretas ao professor.
* **Utilizar Painel Personalizado:** Acessar "Meu Progresso", "Minhas Notas/Desempenho", e "Minha Turma".

---

## 3. Funcionalidades Adicionais e Criativas

* **Painel do Aluno Personalizado:**
    * **Meu Progresso:** Visualização gráfica da frequência.
    * **Minhas Notas/Desempenho:** Resumo visual das avaliações.
    * **Minha Turma:** Informações do professor e colegas.
* **Recursos Interativos para Lições:**
    * **Quizzes/Perguntas por Lição:** Pequenos testes para reforço do aprendizado.
    * **Fórum de Dúvidas da Lição:** Espaço para discussão e esclarecimento.
    * **Sugestões de Atividades Práticas:** Tarefas para aplicação do aprendizado no dia a dia.
* **Biblioteca de Recursos:** Repositório centralizado de materiais da EBD (regulamento, guias, etc.) com controle de acesso.
* **Aniversariantes da Semana/Mês:** Exibição dos aniversariantes para promover a integração.
* **Gerenciamento de Eventos da EBD:** Calendário para registrar eventos especiais com detalhes e opção de inscrição.
* **Pesquisas de Satisfação:** Módulo para criar e aplicar pesquisas para feedback de alunos e professores.
* **Modo Offline (Parcial):** Acesso a lições e materiais previamente baixados sem conexão com a internet.
* **Alerta/Encorajamento por Faltas:** Disparo automático de mensagens para alunos com faltas consecutivas (e-mail, notificação no app, opcionalmente SMS/WhatsApp).
    * **Configurável:** Número de faltas para acionar o alerta.
    * **Conteúdo:** Mensagens amigáveis de encorajamento.

---

## 4. Requisitos Não Funcionais (MVP e Futuro)

* **Segurança:** Autenticação forte (JWT), autorização baseada em papéis, proteção de dados (LGPD - Lei Geral de Proteção de Dados, no Brasil), criptografia em trânsito e em repouso.
* **Performance:** Tempos de resposta rápidos, carregamento eficiente de dados.
* **Usabilidade:** Interface intuitiva e fácil de usar para todos os níveis de usuário.
* **Escalabilidade:** Capacidade de suportar um grande número de igrejas e usuários simultâneos (multi-tenancy).
* **Responsividade:** Layout adaptável a diferentes tamanhos de tela (desktop, tablet, mobile).
* **Manutenibilidade:** Código limpo, modular e bem documentado.
* **Confiabilidade:** Alta disponibilidade do sistema e consistência dos dados.

---

## 5. Priorização de Funcionalidades para o MVP (Produto Mínimo Viável)

A primeira versão do aplicativo (MVP) focará nas funcionalidades essenciais para demonstrar o valor e coletar feedback inicial.

* **Must Have (Essenciais para o MVP):**
    * Cadastro e Autenticação de Usuários (Pastor Presidente, Superintendente, Professor, Aluno)
    * Gerenciamento Básico de Igrejas (Cadastro da Sede, Congregações)
    * Gerenciamento Básico de Usuários (Cadastro de Pastores Congregação, Superintendentes, Professores, Alunos)
    * Gerenciamento Básico de Turmas (Criar/Visualizar)
    * Gerenciamento Básico de Lições (Cadastro de Trimestres e Lições)
    * Registro de Frequência dos Alunos (Pelo Professor)
    * Visualização de Frequência Pessoal (Pelo Aluno)
* **Should Have (Importantes, mas podem vir depois do primeiro deploy):**
    * Registro de Oferta da Turma
    * Alerta/Encorajamento por Faltas (disparo automático)
    * Visualização de Notas Pessoais (Pelo Aluno)
    * Comunicação Básica (Mural de avisos da turma/geral)
* **Could Have (Desejáveis, mas para versões futuras):**
    * Painel do Aluno Personalizado (com gráficos)
    * Recursos Interativos para Lições (Quizzes, Fórum)
    * Biblioteca de Recursos
    * Aniversariantes
    * Gerenciamento de Eventos
    * Pesquisas de Satisfação
    * Modo Offline

---
