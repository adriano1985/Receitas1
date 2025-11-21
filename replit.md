# Minhas Receitas - PWA de Gerenciamento de Receitas

## Visão Geral
Progressive Web App (PWA) para organizar e gerenciar receitas culinárias. Permite adicionar receitas através de copiar/colar, categorização, busca e visualização detalhada.

## Estado Atual
MVP completo e funcional com todas as features implementadas:
- ✅ Formulário para adicionar/editar receitas (copiar/colar)
- ✅ Sistema de categorias (12 categorias disponíveis)
- ✅ Listagem de receitas com cards visuais
- ✅ Filtros por categoria e busca por texto
- ✅ Visualização detalhada de receitas
- ✅ Editar e excluir receitas
- ✅ Armazenamento em memória (MemStorage)
- ✅ Interface responsiva (mobile e desktop)
- ✅ Configuração PWA (manifest.json e service worker)
- ✅ Bottom tab navigation (mobile)
- ✅ Desktop navigation
- ✅ Empty states elegantes
- ✅ Loading e error states

## Arquitetura do Projeto

### Frontend
- **Framework**: React 18 com TypeScript
- **Routing**: Wouter
- **State Management**: TanStack Query v5
- **UI Components**: Shadcn UI + Tailwind CSS
- **Forms**: React Hook Form + Zod validation
- **Design**: Material Design 3 inspirado
- **Fonts**: Inter (UI) + Merriweather (conteúdo de receitas)

### Backend
- **Server**: Express.js
- **Storage**: MemStorage (in-memory)
- **Validation**: Zod schemas
- **API**: RESTful endpoints em `/api/recipes`

### Estrutura de Dados
```typescript
Recipe {
  id: string (UUID)
  name: string
  ingredients: string (multi-line)
  instructions: string (multi-line)
  categories: string[] (array de categorias)
}
```

### Categorias Disponíveis
Sobremesas, Massas, Carnes, Peixes, Vegetariano, Vegano, Lanches, Saladas, Sopas, Bebidas, Pães, Bolos

## Rotas da Aplicação

### Frontend Routes
- `/` - Browse (listagem de receitas com filtros)
- `/add` - Adicionar nova receita
- `/edit/:id` - Editar receita existente
- `/recipe/:id` - Visualização detalhada da receita
- `/categories` - Visão geral de categorias

### API Endpoints
- `GET /api/recipes` - Listar todas as receitas
- `GET /api/recipes/:id` - Buscar receita específica
- `POST /api/recipes` - Criar nova receita
- `PATCH /api/recipes/:id` - Atualizar receita
- `DELETE /api/recipes/:id` - Excluir receita

## Design System

### Cores
- Primary: #FF6B35 (laranja)
- Background: White (light) / Dark gray (dark mode)
- Cards: Subtle elevation com background leve
- Text: Hierarchy de 3 níveis (default, secondary, tertiary)

### Typography
- Headings: Inter (sem-serif)
- Recipe content: Merriweather (serif)
- Body: Inter

### Spacing
- Small: 0.5rem (2 units)
- Medium: 1rem (4 units)
- Large: 1.5rem (6 units)
- XL: 2rem (8 units)

## Componentes Principais

### RecipeCard
Card visual para listar receitas com imagem placeholder, título, e badges de categoria.

### BottomNav
Navegação fixa no bottom para mobile com 3 tabs: Browse, Adicionar, Categorias.

### DesktopNav
Navegação horizontal no header para desktop.

### EmptyState
Estado vazio elegante com ícone, título, descrição e CTA.

### Forms
Formulários completos com validação em tempo real usando React Hook Form + Zod.

## Funcionalidades PWA

### Manifest
- Nome: Minhas Receitas
- Theme color: #FF6B35
- Display: standalone
- Icons: favicon.png (192x192 e 512x512)

### Service Worker
- Cache de assets estáticos
- Funcionamento offline básico
- Estratégia: Cache first, fallback to network

## Desenvolvimento

### Como Executar
```bash
npm run dev
```
Servidor roda em `http://localhost:5000`

### Estrutura de Arquivos
```
client/
  src/
    components/       # Componentes reutilizáveis
    pages/           # Páginas da aplicação
    lib/             # Utilities e configurações
  public/            # Assets estáticos + PWA files
server/
  routes.ts          # Rotas da API
  storage.ts         # Interface de storage
shared/
  schema.ts          # Schemas Drizzle + Zod
```

## Próximas Fases (Fora do MVP)
- Busca por ingredientes específicos
- Sistema de favoritos
- Upload de fotos para receitas
- Compartilhamento de receitas
- Sincronização com PostgreSQL database
- Export/import de receitas (JSON, PDF)
- Tags adicionais além de categorias
- Tempo de preparo e porções
- Modo de cozinha (text-to-speech)

## Mudanças Recentes
- 21/11/2024: Implementação completa do MVP
  - Schema de dados para receitas
  - Todos os componentes frontend
  - Backend completo com CRUD
  - Integração com TanStack Query
  - PWA configurado (manifest + service worker)
  - Design system Material Design 3
