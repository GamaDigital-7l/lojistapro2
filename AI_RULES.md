# Regras de Desenvolvimento e Stack Tecnológica

Este documento define a stack tecnológica e as regras de uso de bibliotecas para garantir a consistência, manutenibilidade e performance do Lojista Pro 2.0.

## 1. Stack Tecnológica

1.  **Framework:** React 19 (com funcionalidade de Hooks e Context API).
2.  **Linguagem:** TypeScript (obrigatório para todos os arquivos `.tsx`).
3.  **Estilização:** Tailwind CSS (utilizado para todos os estilos, priorizando classes utilitárias e design responsivo).
4.  **Componentes UI:** Padrão Shadcn/ui (utilizar componentes que sigam este estilo para manter a coesão visual).
5.  **Ícones:** Lucide React (`lucide-react`).
6.  **Gerenciamento de Estado:** React Context API (`AppContext.tsx`) para estado global e `useState`/`useReducer` para estado local.
7.  **Roteamento:** Gerenciamento de visualizações (Views) interno via `AppContext` (`activeView`). Não utilizar React Router.
8.  **Backend & Banco de Dados:** Supabase (PostgreSQL) para persistência de dados e autenticação.
9.  **Serviços de IA:** Google Gemini (via `@google/genai`) para processamento de comandos de linguagem natural.
10. **Build Tool:** Vite.

## 2. Regras de Uso de Bibliotecas

| Propósito | Biblioteca/Tecnologia | Regra de Uso |
| :--- | :--- | :--- |
| **Estilo e Design** | Tailwind CSS | **Obrigatório.** Todos os componentes devem ser estilizados usando classes utilitárias do Tailwind. |
| **Componentes UI** | Shadcn/ui (Padrão) | Priorizar a criação de componentes que sigam o design e a acessibilidade do Shadcn/ui. |
| **Ícones** | `lucide-react` | **Obrigatório.** Usar apenas ícones desta biblioteca. |
| **Acesso a Dados** | `@supabase/supabase-js` | Acesso deve ser encapsulado nos arquivos de serviço (`services/databaseService.ts` e `services/supabaseClient.ts`). |
| **Lógica de IA** | `@google/genai` | Toda a lógica de processamento de comandos de IA deve residir em `services/geminiService.ts`. |
| **Estrutura de Arquivos** | Padrão | Componentes e Views em `src/components/`, e lógica de negócio/serviços em `src/services/`. |