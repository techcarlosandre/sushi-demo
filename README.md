# 🚀 Sushi PDV
Sistema ERP e PDV (Ponto de Venda) completo para restaurantes de culinária japonesa, integrando automação com IA (N8N), daemons locais e impressão automática de comandas.

---

## 📷 Demonstração Visual e Acesso
> **Nota:** O código-fonte deste projeto é proprietário e mantido de forma privada. Esta página serve como vitrine técnica, demonstração de arquitetura e usabilidade.

*   🌐 **Acesse a aplicação rodando:** [Clique aqui para acessar o Deploy Ativo](https://projetos.techcarlos.com.br/sushi)
*   🎥 **Vídeo de Demonstração (Walkthrough):** [Assista ao funcionamento na prática](https://github.com/techcarlosandre/portfolio-carlos/raw/main/public/sushi/sushi-app_opt.mp4)

---

## ✨ Funcionalidades Principais
*   🍣 **PDV Touchscreen Ágil** — Painel de vendas desenhado especificamente para alta velocidade de atendimento e pedidos.
*   📠 **Impressão Automática de Comandas** — Daemon local em Python (`print_daemon.py`) que intercepta pedidos via socket e envia diretamente para as impressoras termicas da cozinha.
*   🤖 **Fluxos de Automação com IA (N8N)** — Roteamento inteligente de pedidos recebidos por canais de delivery direto no PDV.
*   📄 **Geração Instantânea de Relatórios e Cupons** — Emissão em PDF gerada sob demanda na thread do servidor usando o PDFKit.

## 🛠️ Stack Tecnológica & Arquitetura
*   **Frontend:** Next.js 14 (App Router), React 18, TailwindCSS v3, SWR (Data Fetching e Caching reativo).
*   **Backend & APIs:** Server-side API Routes integradas com Prisma ORM e API de sockets.
*   **Impressão Local:** Python Daemon (`print_daemon.py`) rodando em segundo plano.
*   **Automação:** Fluxos integrados via N8N.
*   **Banco de Dados & Persistência:** PostgreSQL (com schema gerenciado via Prisma migrations).

## 🏗️ Diferenciais Técnicos Aplicados
*   **Suíte de Testes Unitários e de Integração:** Testes robustos de fluxo de caixa e agendamento de pedidos escritos em **Vitest** e integrados na esteira.
*   **Comunicação Bidirecional de Baixa Latência:** Uso de sockets de rede locais e daemon Python para garantir que pedidos cheguem na cozinha em menos de 100 milissegundos.
*   **Sincronização de Estado via SWR:** Uso de stale-while-revalidate (SWR) para garantir atualizações automáticas de novos pedidos na tela do caixa sem necessidade de refresh manual.
