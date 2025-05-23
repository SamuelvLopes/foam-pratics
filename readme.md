# 🔐 Pratics Sec — Plataforma Integrada de Segurança, Risco e Compliance

**Pratics Sec** é uma plataforma web integrada para **monitoramento de segurança cibernética**, **gestão de riscos organizacionais** e **conformidade com normas e legislações**. O projeto tem como objetivo centralizar, em uma única solução, funcionalidades essenciais presentes nas principais plataformas do mercado, como **Zanshin**, **SecurityScorecard**, **BitSight**, **OneTrust** e **RSA Archer**.

---

## 🧠 Visão Geral

O **Pratics Sec** permite que empresas:

- Descubram ativos públicos expostos na internet (**Surface Monitoring**)
- Recebam um score de segurança cibernética baseado em critérios técnicos
- Avaliem e monitorem riscos de fornecedores e terceiros
- Gerenciem riscos corporativos (**Governança, Riscos e Compliance - GRC**)
- Acompanhem a conformidade com **LGPD**, **ISO 27001**, **GDPR**, entre outras normas
- Registrem e respondam a vulnerabilidades e incidentes de segurança

---

## 🚀 Principais Funcionalidades

| Funcionalidade                     | Descrição                                                                                   | Referência                               |
|-------------------------------------|---------------------------------------------------------------------------------------------|-------------------------------------------|
| 🔍 **Surface Monitoring**           | Descoberta de ativos públicos (IPs, domínios, aplicações) e monitoramento da superfície.    | Zanshin, CyCognito, UpGuard              |
| 🛡️ **Score de Segurança Cibernética** | Atribuição de nota (A-F) com base na análise externa técnica e critérios objetivos.         | SecurityScorecard, BitSight, RiskRecon   |
| 🔗 **Gestão de Terceiros**          | Avaliação contínua da segurança e dos riscos de fornecedores e terceiros.                   | SecurityScorecard, BitSight, Panorays    |
| 🏛️ **Gestão de Riscos Organizacionais (GRC)** | Registro de riscos operacionais, avaliação de impacto, probabilidade e planos de mitigação. | RSA Archer, OneTrust                     |
| 📜 **Gestão de Privacidade e Compliance** | Mapeamento de dados sensíveis, consentimento, aderência à LGPD, GDPR e ISO 27001.           | OneTrust, RSA Archer                     |
| 🚨 **Gestão de Incidentes e Vulnerabilidades** | Registro, acompanhamento e mitigação de vulnerabilidades e incidentes.                      | RSA Archer, RiskRecon, OneTrust          |
| 📊 **Dashboards e Relatórios**      | Visão executiva dos riscos, scores, incidentes e status de compliance.                      | Todos                                     |

---

## 📚 Sistemas de Referência

O desenvolvimento do **Pratics Sec** foi baseado nas seguintes plataformas líderes de mercado:

1. **SecurityScorecard** — https://securityscorecard.com  
2. **BitSight** — https://bitsight.com  
3. **Zanshin** — https://zanshin.soc  
4. **UpGuard** — https://upguard.com  
5. **RiskRecon (Mastercard)** — https://www.riskrecon.com  
6. **CyCognito** — https://www.cycognito.com  
7. **Black Kite** — https://blackkite.com  
8. **Panorays** — https://panorays.com  
9. **OneTrust** — https://onetrust.com  
10. **RSA Archer** — https://www.rsa.com/en-us/products/archer-suite  

---

## 🏗️ Arquitetura

- **Frontend:** Vue.js + TailwindCSS
- **Backend:** Laravel (PHP) + PostgreSQL
- **Monitoramento externo:** Python workers + APIs públicas (Shodan, Censys, SecurityTrails)
- **Infraestrutura:** Docker + Docker Compose (pronto para deploy local ou na nuvem)

---

## 🚀 Instalação

```bash
# Clone o repositório
git clone https://github.com/seunome/pratics-sec.git
cd pratics-sec

# Suba os containers
docker-compose up -d --build

# Acesse o backend
http://localhost:8000

# Acesse o frontend
http://localhost:3000
