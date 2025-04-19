# TODO - Middleware Framework

## Princípios e Padrões
- **Test-Driven Development (TDD)**
  - Red-Green-Refactor
  - Testes unitários primeiro
  - Testes de integração
  - Testes de comportamento

- **Domain-Driven Design (DDD)**
  - Bounded Contexts
  - Agregados
  - Entidades
  - Value Objects
  - Serviços de Domínio
  - Repositórios
  - Eventos de Domínio

- **Clean Architecture**
  - Camadas concêntricas
  - Dependência em direção ao centro
  - Interfaces para comunicação entre camadas
  - Entidades independentes de frameworks

- **Clean Code**
  - SOLID Principles
  - Nomes significativos
  - Funções pequenas e focadas
  - Comentários apenas quando necessário
  - Formatação consistente

## Estrutura de Diretórios
```
src/
├── domain/                    # Camada de Domínio (mais interna)
│   ├── entities/             # Entidades de domínio
│   │   ├── middleware.py     # Agregado Middleware
│   │   └── controller.py     # Agregado Controller
│   ├── value_objects/        # Value Objects
│   │   ├── route.py         # Value Object Route
│   │   └── event.py         # Value Object Event
│   ├── repositories/         # Interfaces de repositórios
│   │   ├── middleware_repo.py
│   │   └── controller_repo.py
│   ├── services/            # Serviços de domínio
│   │   ├── middleware_service.py
│   │   └── event_service.py
│   └── events/              # Eventos de domínio
│       ├── middleware_events.py
│       └── controller_events.py
│
├── application/              # Camada de Aplicação
│   ├── usecases/            # Casos de uso
│   │   ├── middleware/
│   │   └── controller/
│   ├── interfaces/          # Interfaces de entrada/saída
│   │   ├── input/
│   │   └── output/
│   └── services/            # Serviços de aplicação
│
├── infrastructure/           # Camada de Infraestrutura
│   ├── persistence/         # Implementações de repositórios
│   │   ├── in_memory/
│   │   └── database/
│   ├── web/                # Implementações web
│   │   ├── fastapi/
│   │   └── flask/
│   └── services/           # Serviços externos
│       ├── logging/
│       └── events/
│
└── presentation/            # Camada de Apresentação
    ├── api/                # API REST
    │   ├── routes/
    │   └── controllers/
    └── cli/                # Interface de linha de comando
        ├── commands/
        └── handlers/
```

## Fase 1: Configuração e Estrutura Base (TDD)
- [ ] Configurar ambiente de desenvolvimento
  - [ ] pytest e plugins
  - [ ] Ferramentas de qualidade de código
  - [ ] Type checking
  - [ ] Formatação automática

- [ ] Criar estrutura de diretórios
  - [ ] Configurar __init__.py
  - [ ] Configurar pyproject.toml
  - [ ] Configurar setup.py

## Fase 2: Domínio - Entidades Base (TDD)
- [ ] Testes para entidades de domínio
  - [ ] Teste de Middleware (Agregado)
    - [ ] Identidade
    - [ ] Invariantes
    - [ ] Comportamentos
  - [ ] Teste de Controller (Agregado)
    - [ ] Identidade
    - [ ] Invariantes
    - [ ] Comportamentos

- [ ] Implementação das entidades
  - [ ] Middleware
  - [ ] Controller
  - [ ] Value Objects relacionados

## Fase 3: Domínio - Eventos e Serviços (TDD)
- [ ] Testes para eventos de domínio
  - [ ] Teste de MiddlewareCreated
  - [ ] Teste de ControllerAdded
  - [ ] Teste de ServiceRegistered

- [ ] Testes para serviços de domínio
  - [ ] Teste de MiddlewareService
  - [ ] Teste de EventService

- [ ] Implementação
  - [ ] Eventos de domínio
  - [ ] Serviços de domínio

## Fase 4: Aplicação - Casos de Uso (TDD)
- [ ] Testes para casos de uso
  - [ ] Teste de RegisterMiddleware
  - [ ] Teste de AddController
  - [ ] Teste de SetupMiddleware

- [ ] Implementação dos casos de uso
  - [ ] RegisterMiddleware
  - [ ] AddController
  - [ ] SetupMiddleware

## Fase 5: Infraestrutura - Repositórios (TDD)
- [ ] Testes para repositórios
  - [ ] Teste de InMemoryMiddlewareRepository
  - [ ] Teste de InMemoryControllerRepository

- [ ] Implementação dos repositórios
  - [ ] InMemoryMiddlewareRepository
  - [ ] InMemoryControllerRepository

## Fase 6: Infraestrutura - Web (TDD)
- [ ] Testes para implementação web
  - [ ] Teste de FastAPIAdapter
  - [ ] Teste de RouteDecorator
  - [ ] Teste de ControllerAdapter

- [ ] Implementação web
  - [ ] FastAPIAdapter
  - [ ] RouteDecorator
  - [ ] ControllerAdapter

## Fase 7: Apresentação - API (TDD)
- [ ] Testes para API
  - [ ] Teste de MiddlewareRoutes
  - [ ] Teste de ControllerRoutes
  - [ ] Teste de ErrorHandlers

- [ ] Implementação da API
  - [ ] MiddlewareRoutes
  - [ ] ControllerRoutes
  - [ ] ErrorHandlers

## Fase 8: Apresentação - CLI (TDD)
- [ ] Testes para CLI
  - [ ] Teste de Commands
  - [ ] Teste de Handlers
  - [ ] Teste de OutputFormatters

- [ ] Implementação da CLI
  - [ ] Commands
  - [ ] Handlers
  - [ ] OutputFormatters

## Próximos Passos Imediatos
1. Configurar ambiente de desenvolvimento
2. Criar estrutura de diretórios
3. Escrever primeiro teste para entidade Middleware
4. Implementar entidade Middleware
5. Refatorar conforme necessário
