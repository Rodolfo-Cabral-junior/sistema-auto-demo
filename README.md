# 🔧 SISTEMA AUTO

> Sistema SaaS de Gestão para Oficinas Mecânicas — desenvolvido por [Cabr@lves Tecnologia](https://cabralvestecnologia.com.br)

![Login](https://raw.githubusercontent.com/Rodolfo-Cabral-junior/sistema-auto/main/docs/screenshots/login.png)

## 🚀 Sobre o Projeto

O **SISTEMA AUTO** é uma plataforma SaaS multi-tenant completa para gestão de oficinas mecânicas. Desenvolvido do zero com foco em usabilidade, performance e segurança, o sistema cobre todo o ciclo operacional de uma oficina — do atendimento ao cliente até o controle financeiro.

🌐 **Demo:** [auto.cabralvestecnologia.com.br](https://auto.cabralvestecnologia.com.br)

---

## ✨ Funcionalidades

### 📋 Ordens de Serviço
- Criação de OS com múltiplas etapas (problema, serviços, peças, laudo, fotos)
- Controle de status (aberta, em andamento, aguardando, concluída, cancelada)
- Upload de fotos armazenadas no Cloudflare R2
- Geração de PDF / Orçamento
- Envio via WhatsApp
- Portal do cliente com link público por OS
- Baixa por leitura de barcode
- OS com Reserva de peças

### 📦 Estoque
- Cadastro de peças com código, categoria e preço
- Controle de lotes com QR Code e barcode
- Entrada de estoque com scanner QR/barcode
- Alertas de estoque mínimo
- Relatório de estoque
- Impressão de etiquetas (Zebra e PDF A4)

### 💰 Financeiro
- Contas a receber e a pagar
- Fluxo de caixa
- DRE (Demonstrativo de Resultados)
- Registro de pagamentos com múltiplas formas
- Relatórios exportáveis

### 👥 Gestão de Pessoas
- Cadastro de clientes e veículos com histórico completo
- Funcionários com tipos (mecânico, atendente, gerente)
- Comissão por serviço
- Adiantamentos salariais
- Relatório de adiantamentos

### 🗓️ Agenda
- Agendamento de serviços
- Visualização por dia e lista
- Integração com criação de OS

### ⚙️ Configurações
- Dados da oficina (CNPJ, endereço, logo)
- Templates de WhatsApp
- Configuração de impressora Zebra
- Notificações
- Gestão de usuários com RBAC

### 🔐 Segurança & Infra
- Multi-tenant com isolamento por subdomínio
- RBAC (super_admin, admin, mecanico, atendente)
- Audit log de todas as ações
- Rate limiting
- Backup automático diário no Cloudflare R2
- SSL via Certbot
- Deploy automático via GitHub Actions

---

## 🛠️ Stack Tecnológica

### Backend
- **PHP 8.3** + **Laravel 13**
- **MySQL** (produção) / **SQLite** (desenvolvimento)
- **Redis** — cache e filas
- **Spatie Laravel Backup** — backups automáticos
- **Spatie Laravel Permission** — RBAC
- **Intervention Image** — processamento de imagens WebP
- **barryvdh/laravel-dompdf** — geração de PDFs
- **SimpleSoftwareIO/simple-qrcode** — geração de QR Codes

### Frontend
- **Vue 3** + **TypeScript**
- **Inertia.js** — SPA sem API REST
- **Tailwind CSS v4**
- **@zxing/browser** — leitura de QR Code e barcode via câmera

### Infraestrutura
- **VPS Ubuntu 22.04** + **Nginx** + **PHP-FPM**
- **Cloudflare R2** — armazenamento de fotos e backups
- **GitHub Actions** — CI/CD
- **UptimeRobot** — monitoramento
- **Certbot** — SSL automático

---

## 📸 Screenshots

### Dashboard
![Dashboard](https://raw.githubusercontent.com/Rodolfo-Cabral-junior/sistema-auto/main/docs/screenshots/Destboard.png)

### Ordens de Serviço
![OS Lista](https://raw.githubusercontent.com/Rodolfo-Cabral-junior/sistema-auto/main/docs/screenshots/lista%20de%20OS.png)

### Detalhe da OS
![OS Detalhe](https://raw.githubusercontent.com/Rodolfo-Cabral-junior/sistema-auto/main/docs/screenshots/Detales%20de%20OS.png)

### Estoque de Peças
![Estoque](https://raw.githubusercontent.com/Rodolfo-Cabral-junior/sistema-auto/main/docs/screenshots/Estoque.png)

### Financeiro
![Financeiro](https://raw.githubusercontent.com/Rodolfo-Cabral-junior/sistema-auto/main/docs/screenshots/Financeiro.png)

### Configurações
![Configurações](https://raw.githubusercontent.com/Rodolfo-Cabral-junior/sistema-auto/main/docs/screenshots/Configura%C3%A7oes.png)

---

## 🧪 Qualidade

- **355+ testes automatizados** (PHPUnit)
- **1300+ assertions**
- Testes de feature cobrindo todos os módulos principais
- CI verde obrigatório antes de qualquer deploy
- Playwright E2E configurado

---

## 🏗️ Arquitetura

```
sistema-auto/
├── app/
│   ├── Http/Controllers/     # 30+ controllers
│   ├── Models/               # Eloquent models com HasTenant
│   ├── Services/             # Lógica de negócio
│   └── Observers/            # Sincronização de estoque
├── resources/js/
│   ├── Pages/                # 50+ páginas Vue 3
│   ├── Components/           # Componentes reutilizáveis
│   └── composables/          # Hooks Vue (useScanner, useToast...)
├── tests/
│   └── Feature/              # 355+ testes PHPUnit
└── database/
    └── migrations/           # 40+ migrations
```

---

## 🚀 Setup Local

```bash
# Clone o repositório
git clone git@github.com:Rodolfo-Cabral-junior/sistema-auto.git
cd sistema-auto

# Instale as dependências
composer install
npm install

# Configure o ambiente
cp .env.example .env
php artisan key:generate

# Execute as migrations
php artisan migrate

# Build do frontend
npm run build

# Servidor de desenvolvimento
php artisan serve
npm run dev
```

---

## 📄 Licença

Este projeto é proprietário. Todos os direitos reservados © 2026 [Cabr@lves Tecnologia](https://cabralvestecnologia.com.br).

---

<p align="center">
  Desenvolvido com ❤️ por <a href="https://cabralvestecnologia.com.br">Cabr@lves Tecnologia</a>
</p>
