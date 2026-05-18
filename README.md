# Sua Consulta - Apresentação Interativa & Landing Page Premium

Este diretório contém uma aplicação web moderna de alto impacto visual (Pitch Deck Interativo & Landing Page) construída especificamente para apresentar a arquitetura, as funcionalidades de IA, e o design system do ecossistema Sua Consulta para investidores técnicos.

A aplicação adota as especificações oficiais do projeto em Flutter (como cores e border-radius) e implementa o que há de mais moderno na engenharia web estática (Glassmorphism, CSS Custom Variables, SVG interativos e animações de alta performance).

---

## Principais Destaques & Funcionalidades

### Sistema de Visualização Híbrido (Dual-Mode)
* Modo Apresentação (Slides): Apresenta o pitch slide por slide com transições suaves baseadas em transformações de escala e opacidade. Inclui controle por teclado (setas direcionais), indicadores e um Drawer de Notas de Fala do Apresentador dinâmico, que se atualiza automaticamente com o roteiro técnico correspondente a cada slide.
* Modo Landing Page (Rolagem Contínua): Transforma os slides em seções verticais estruturadas para leitura web, ativando um menu lateral de progresso com Scroll Spy (Intersection Observer) que destaca a seção atual na tela.

### Temas Dinâmicos e Clean UI
* Dark Theme (Default): Inspirado no tema Gaian (#001D39), com alto contraste, luzes neon sutis e foco na densidade tecnológica.
* Light Theme: Um design clínico limpo, suave e sofisticado com gradientes baseados em #F0F4F8 a #F9FAFB, alinhado às cores do Scaffold do aplicativo Flutter.
* Border Radius Pílula: Respeito absoluto ao Design System (border-radius de 24px a 32px em botões, cartões e inputs).

### Playgrounds Interativos & Simulações em Tempo Real
1. Simulador de Latência Sub-2s (Slide 3): Simulação interativa mostrando um paciente enviando um áudio no WhatsApp. O webhook assíncrono do FastAPI recebe o evento, a Isis IA processa a transcrição via Groq/Whisper, aciona o FCM e notifica o app em Flutter do médico. Inclui um cronômetro realista que finaliza dinamicamente em menos de 2 segundos (ex: 1.31s).
2. Visualizador de Memória RAG (Slide 5): Simulador de limpeza de contexto com o protocolo new_session: true, limpando logs antigos e prevenindo alucinações e swap de personas no backend.
3. Console de Moderação Multimodal (Slide 6): Uma área de teste interativa que intercepta mensagens. Mostra a IA permitindo exceções clínicas (termos médicos normais e diagnósticos dermatológicos legítimos) e aplicando mascaramento rígido para spams ou ofensas no PostgreSQL ([MENSAGEM BLOQUEADA PELO FILTRO DE SEGURANÇA]), em total conformidade com a LGPD.
4. Mapa de Orquestração Multiagente (Slide 7): Rede interativa ligando o Orquestrador Central a seus agentes especialistas (FastAPI, Database, Flutter Widget, QA Pytest). Ao clicar em um nó, exibe-se as atribuições e o trecho de código específico de cada agente.
5. Dashboard Financeiro SVG (Slide 8): Um gráfico vetorial interativo com efeitos hover que exibem faturamentos semanais em tempo real ao passar o cursor sobre os nós.

---

## Como Executar Localmente

Como a aplicação foi desenvolvida utilizando HTML5 Puro, Vanilla CSS e Javascript Nativo, ela não requer processos pesados de compilação ou instalação de dependências npm. Você pode abri-la de duas formas:

### Método 1: Servidor Local (Recomendado para simular latências fiéis)
Se você possui o Python instalado na máquina, execute este comando no terminal para subir um servidor local leve:
```bash
python -m http.server 8082
```
Em seguida, acesse no navegador: http://localhost:8082

### Método 2: Abertura Direta
Dê dois cliques no arquivo index.html para abrir a apresentação diretamente em qualquer navegador moderno.

---

## Estrutura de Arquivos

* index.html - Estrutura semântica dos slides, cabeçalhos, drawers e sandboxes interativos.
* css/style.css - Design System oficial, glassmorphism, responsividade, variáveis HSL, temas dark/light e animações.
* js/script.js - Controladores lógicos (toggles de modo, navegação, stopwatches, filtros de moderação, cliques nos agentes e interações em SVG).
* assets/suaConsulta_logo.svg - Logotipo em vetor puro (Icons.health_and_safety).
* pitch_deck.md - Guia original de roteiro e slides em Marp.
