# 📰 Portal de Notícias - Laravel 12

> Projeto didático de um portal de notícias desenvolvido com Laravel 12, PHP 8.4 e MySQL 8, criado para fins educacionais com foco em boas práticas e código limpo.

![Laravel](https://img.shields.io/badge/Laravel-12.36.1-red?style=flat&logo=laravel)
![PHP](https://img.shields.io/badge/PHP-8.4.14-blue?style=flat&logo=php)
![MySQL](https://img.shields.io/badge/MySQL-8.0-orange?style=flat&logo=mysql)

---

## 📚 Índice

- [Sobre o Projeto](#-sobre-o-projeto)
- [Funcionalidades](#-funcionalidades)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Pré-requisitos](#-pré-requisitos)
- [Como Clonar e Configurar](#-como-clonar-e-configurar)
  - [Opção 1: Ambiente Local](#opção-1-ambiente-local)
  - [Opção 2: Dev Container (Recomendado)](#opção-2-dev-container-recomendado)
  - [Opção 3: GitHub Codespaces](#opção-3-github-codespaces)
- [Inicialização do Projeto](#-inicialização-do-projeto)
- [Acessando o Sistema](#-acessando-o-sistema)
- [Arquitetura do Projeto](#-arquitetura-do-projeto)
- [Entendendo o Laravel](#-entendendo-o-laravel)
- [Estrutura do Banco de Dados](#-estrutura-do-banco-de-dados)
- [Rotas do Sistema](#-rotas-do-sistema)
- [Sistema de Autenticação](#-sistema-de-autenticação)
- [Área Administrativa](#-área-administrativa)
- [Customizações e Extensões](#-customizações-e-extensões)
- [Comandos Úteis](#-comandos-úteis)
- [Resolução de Problemas](#-resolução-de-problemas)
- [Contribuindo](#-contribuindo)
- [Licença](#-licença)

---

## 🎯 Sobre o Projeto

Este é um **portal de notícias simplificado** desenvolvido como material didático para estudantes de desenvolvimento web. O projeto demonstra conceitos fundamentais do Laravel, incluindo:

- **MVC (Model-View-Controller)**: Separação clara de responsabilidades
- **Eloquent ORM**: Manipulação de banco de dados orientada a objetos
- **Blade Templates**: Sistema de templates do Laravel
- **Autenticação Customizada**: Sistema de login sem pacotes externos
- **Middleware**: Proteção de rotas e controle de acesso
- **Relacionamentos**: One-to-Many entre tabelas
- **Seeders e Factories**: Geração de dados para teste

### Objetivos Pedagógicos

- Compreender o fluxo de requisição/resposta no Laravel
- Aprender a criar CRUDs completos
- Entender relacionamentos entre entidades
- Implementar autenticação e autorização
- Trabalhar com migrações e seeders
- Aplicar boas práticas de desenvolvimento

---

## ✨ Funcionalidades

### Área Pública
- ✅ Listagem de notícias publicadas
- ✅ Visualização de notícia completa
- ✅ Ordenação por data de atualização
- ✅ Paginação automática
- ✅ Categorização por tipo de notícia
- ✅ Design responsivo e moderno

### Área Administrativa
- ✅ Dashboard com estatísticas
- ✅ CRUD completo de Notícias
- ✅ CRUD completo de Tipos de Notícia
- ✅ CRUD completo de Usuários
- ✅ Sistema de publicação/rascunho
- ✅ Controle de acesso (apenas administradores)
- ✅ Interface moderna com sidebar navegável

---

## 🛠 Tecnologias Utilizadas

| Tecnologia | Versão | Finalidade |
|------------|--------|------------|
| **PHP** | 8.4.14 | Linguagem de programação |
| **Laravel** | 12.36.1 | Framework PHP |
| **Composer** | 2.x | Gerenciador de dependências PHP |
| **MySQL** | 8.0 | Banco de dados relacional |
| **Blade** | - | Engine de templates do Laravel |
| **Docker** | - | Containerização (Dev Container) |

### Por que estas versões?

- **PHP 8.4**: Versão mais recente com melhorias de performance e recursos modernos
- **Laravel 12**: Última versão LTS (Long Term Support) com suporte estendido
- **MySQL 8.0**: Versão estável e amplamente utilizada em produção

---

## 📋 Pré-requisitos

Antes de começar, você precisa ter instalado em sua máquina:

### Para Ambiente Local

```bash
# Verificar versões instaladas
php -v        # PHP 8.4 ou superior
composer -V   # Composer 2.x
mysql --version  # MySQL 8.0 ou superior
```

- **PHP** >= 8.4 com extensões: `pdo`, `pdo_mysql`, `mbstring`, `xml`, `bcmath`
- **Composer** >= 2.0
- **MySQL** >= 8.0 ou **MariaDB** >= 10.5
- **Git** para clonar o repositório

### Para Dev Container (mais fácil!)

- **Docker Desktop** instalado
- **Visual Studio Code** com extensão **Dev Containers**

### Para GitHub Codespaces

- Apenas uma conta GitHub! 🎉

---

## 🚀 Como Clonar e Configurar

### Opção 1: Ambiente Local

#### 1. Clone o repositório

```bash
git clone https://github.com/renato-mendes-uninassau/laravel-noticias.git
cd laravel-noticias
```

#### 2. Instale as dependências

```bash
composer install
```

#### 3. Configure o arquivo de ambiente

```bash
# Copie o arquivo de exemplo
cp .env.example .env

# Gere a chave da aplicação
php artisan key:generate
```

#### 4. Configure o banco de dados

Edite o arquivo `.env` com suas credenciais do MySQL:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel_news
DB_USERNAME=seu_usuario
DB_PASSWORD=sua_senha
```

#### 5. Crie o banco de dados

```bash
# Entre no MySQL
mysql -u root -p

# Crie o banco
CREATE DATABASE laravel_news CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
exit;
```

---

### Opção 2: Dev Container (Recomendado)

O Dev Container já vem configurado com **todas as dependências necessárias**!

#### 1. Clone o repositório

```bash
git clone https://github.com/renato-mendes-uninassau/laravel-noticias.git
cd laravel-noticias
```

#### 2. Abra no VS Code

```bash
code .
```

#### 3. Reabra no Container

- Pressione `F1` ou `Ctrl+Shift+P`
- Digite: **"Dev Containers: Reopen in Container"**
- Aguarde a construção do container (primeira vez demora mais)

✨ **Pronto!** O ambiente está 100% configurado automaticamente com:
- PHP 8.4 ✅
- Composer 2.x ✅
- MySQL 8.0 ✅
- Todas as extensões PHP necessárias ✅

#### 4. Configure o ambiente dentro do container

O Dev Container executa automaticamente na primeira vez:
```bash
composer install
cp .env.example .env
php artisan key:generate
```

Se precisar executar manualmente ou reconfigurar:

```bash
# Instale as dependências do Composer
composer install

# Copie o arquivo de exemplo para .env (apenas se não existir)
cp .env.example .env

# Gere a chave da aplicação
php artisan key:generate
```

#### 5. Configure o arquivo .env para usar o MySQL do container

Edite o arquivo `.env` e altere as configurações do banco de dados:

```env
DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=laravel_news
DB_USERNAME=laravel
DB_PASSWORD=laravel
```

💡 **Nota**: O host é `db` (nome do serviço no docker-compose), não `127.0.0.1`!

---

### Opção 3: GitHub Codespaces

#### 1. No GitHub, clique em "Code" > "Codespaces" > "Create codespace"

#### 2. Aguarde a inicialização (automática)

#### 3. Configure o ambiente

```bash
# Instale as dependências do Composer
composer install

# Copie o arquivo de exemplo para .env
cp .env.example .env

# Gere a chave da aplicação
php artisan key:generate
```

#### 4. Configure o arquivo .env para usar o MySQL do container

Edite o arquivo `.env` e altere as configurações do banco de dados:

```env
DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=laravel_news
DB_USERNAME=laravel
DB_PASSWORD=laravel
```

---

## 🎬 Inicialização do Projeto

Depois de clonar e configurar, execute os seguintes comandos **na ordem**:

### 1. Execute as Migrações

As migrações criam as tabelas no banco de dados:

```bash
php artisan migrate
```

**O que isso faz?**
- Cria tabela `usuarios` (name, email, password, is_admin)
- Cria tabela `tipos_noticias` (nome, slug)
- Cria tabela `noticias` (titulo, slug, resumo, conteudo, publicado_em, etc)

### 2. Execute os Seeders

Os seeders populam o banco com dados de exemplo:

```bash
php artisan db:seed
```

**O que é inserido?**
- 1 usuário administrador (admin@exemplo.com / password)
- 3 tipos de notícia (Política, Economia, Cultura)
- 10 notícias de exemplo com dados gerados pelo Faker

💡 **Dica**: Para limpar e recriar tudo:
```bash
php artisan migrate:fresh --seed
```

### 3. Inicie o Servidor de Desenvolvimento

```bash
php artisan serve --host=0.0.0.0 --port=8000
```

Ou, se estiver no Dev Container:
```bash
php artisan serve --host=0.0.0.0 --port=8001
```

---

## 🌐 Acessando o Sistema

### Área Pública
```
http://localhost:8000
```

Aqui você verá a listagem de todas as notícias publicadas.

### Área Administrativa
```
http://localhost:8000/admin
```

**Credenciais de Acesso:**
- **Email**: `admin@exemplo.com`
- **Senha**: `password`

### Página de Login
```
http://localhost:8000/login
```

---

## 🏗 Arquitetura do Projeto

O projeto segue o padrão **MVC (Model-View-Controller)** do Laravel:

```
app/
├── Http/
│   ├── Controllers/         # Controladores
│   │   ├── PublicoController.php      # Área pública
│   │   ├── Auth/
│   │   │   ├── LoginController.php    # Autenticação
│   │   │   └── LogoutController.php
│   │   └── Admin/                      # Área administrativa
│   │       ├── DashboardController.php
│   │       ├── NoticiaController.php
│   │       ├── TipoNoticiaController.php
│   │       └── UsuarioController.php
│   └── Middleware/
│       └── EhAdmin.php      # Middleware customizado
├── Models/                  # Modelos Eloquent
│   ├── Usuario.php          # ⚠️ Customizado! (Laravel padrão: User.php)
│   ├── TipoNoticia.php
│   └── Noticia.php
└── ...

config/
└── auth.php                 # ⚠️ Configurado para usar Usuario (não User)

resources/
└── views/                   # Views Blade
    ├── layouts/
    │   ├── app.blade.php    # Layout público
    │   └── admin.blade.php  # Layout administrativo
    ├── publico/
    │   ├── index.blade.php  # Listagem de notícias
    │   └── show.blade.php   # Detalhes da notícia
    ├── admin/               # Views administrativas
    └── auth/
        └── login.blade.php

database/
├── migrations/              # Migrações do banco
│   ├── 2025_11_03_232158_create_usuarios_table.php
│   ├── 2025_11_03_232513_create_tipo_noticias_table.php
│   └── 2025_11_03_232514_create_noticias_table.php
├── seeders/                 # Populadores de dados
│   ├── UsuarioSeeder.php
│   ├── TipoNoticiaSeeder.php
│   └── NoticiaSeeder.php
└── factories/               # Fábricas de dados falsos
    └── NoticiaFactory.php

routes/
└── web.php                  # Definição de rotas

public/
├── css/
│   └── app.css             # Estilos customizados
└── js/
    └── app.js              # Scripts JavaScript
```

---

## 📖 Entendendo o Laravel

### 1. Models (Modelos)

Os Models representam as **entidades do banco de dados** e permitem interagir com elas usando PHP orientado a objetos.

**Exemplo: `app/Models/Noticia.php`**

```php
class Noticia extends Model
{
    // Campos que podem ser preenchidos em massa
    protected $fillable = [
        'titulo',
        'slug',
        'resumo',
        'conteudo',
        'tipo_noticia_id',
        'usuario_id',
        'publicado_em',
    ];

    // Converte 'publicado_em' automaticamente para Carbon (DateTime)
    protected $casts = [
        'publicado_em' => 'datetime',
    ];

    // Relacionamento: Uma notícia pertence a um tipo
    public function tipo()
    {
        return $this->belongsTo(TipoNoticia::class, 'tipo_noticia_id');
    }

    // Relacionamento: Uma notícia pertence a um usuário
    public function usuario()
    {
        return $this->belongsTo(Usuario::class, 'usuario_id');
    }
}
```

**O que o Eloquent faz por você:**
- Buscar registros: `Noticia::all()`, `Noticia::find(1)`
- Criar: `Noticia::create([...])`
- Atualizar: `$noticia->update([...])`
- Deletar: `$noticia->delete()`
- Relacionamentos: `$noticia->tipo->nome`

### 2. Migrations (Migrações)

Migrações são **scripts de criação/modificação de banco de dados** versionados.

**Exemplo: `database/migrations/2025_11_03_232514_create_noticias_table.php`**

```php
public function up(): void
{
    Schema::create('noticias', function (Blueprint $table) {
        $table->id();
        $table->string('titulo');
        $table->string('slug')->unique();
        $table->text('resumo')->nullable();
        $table->longText('conteudo');
        $table->foreignId('tipo_noticia_id')->constrained('tipos_noticias');
        $table->foreignId('usuario_id')->constrained('usuarios');
        $table->timestamp('publicado_em')->nullable();
        $table->timestamps(); // created_at e updated_at
    });
}
```

**Comandos úteis:**
```bash
php artisan migrate              # Executa migrações pendentes
php artisan migrate:fresh        # Apaga tudo e recria
php artisan migrate:fresh --seed # Recria e popula com seeders
php artisan migrate:rollback     # Desfaz última migração
```

### 3. Controllers (Controladores)

Controllers contêm a **lógica de negócio** e fazem a ponte entre Models e Views.

**Exemplo: `app/Http/Controllers/PublicoController.php`**

```php
class PublicoController extends Controller
{
    /**
     * Exibe a listagem de notícias publicadas na página inicial
     */
    public function index()
    {
        // Busca notícias publicadas, ordena e pagina
        $noticias = Noticia::whereNotNull('publicado_em')
            ->orderBy('updated_at', 'desc')
            ->paginate(10);

        // Retorna a view com os dados
        return view('publico.index', compact('noticias'));
    }

    /**
     * Exibe os detalhes de uma notícia específica
     */
    public function show($slug)
    {
        // Busca por slug e garante que está publicada
        $noticia = Noticia::where('slug', $slug)
            ->whereNotNull('publicado_em')
            ->firstOrFail(); // 404 se não encontrar

        return view('publico.show', compact('noticia'));
    }
}
```

**Padrão Resource Controller:**
- `index()` - Lista todos
- `create()` - Exibe formulário de criação
- `store()` - Salva novo registro
- `show()` - Exibe um registro
- `edit()` - Exibe formulário de edição
- `update()` - Atualiza registro
- `destroy()` - Remove registro

### 4. Routes (Rotas)

Rotas mapeiam **URLs para Controllers**.

**Arquivo: `routes/web.php`**

```php
// ROTAS PÚBLICAS
Route::get('/', [PublicoController::class, 'index'])->name('home');
Route::get('/noticia/{slug}', [PublicoController::class, 'show'])->name('noticia.show');

// AUTENTICAÇÃO
Route::get('login', [LoginController::class, 'mostrarForm'])->name('login');
Route::post('login', [LoginController::class, 'login']);
Route::post('logout', [LogoutController::class, 'logout'])->name('logout');

// ROTAS ADMINISTRATIVAS (protegidas por middleware)
Route::middleware(['auth', 'eh.admin'])
    ->prefix('admin')
    ->name('admin.')
    ->group(function() {
        Route::get('/', [DashboardController::class, 'index'])->name('dashboard');
        
        // CRUD completo de notícias
        Route::resource('noticias', NoticiaController::class);
        
        // CRUD de tipos (com parâmetro customizado)
        Route::resource('tipos-noticia', TipoNoticiaController::class)
            ->parameters(['tipos-noticia' => 'tipos_noticia']);
        
        // CRUD de usuários (sem show)
        Route::resource('usuarios', UsuarioController::class)->except(['show']);
    });
```

**Tipos de rotas:**
- `Route::get()` - Requisição GET (buscar dados)
- `Route::post()` - Requisição POST (enviar dados)
- `Route::put()` - Requisição PUT (atualizar completo)
- `Route::delete()` - Requisição DELETE (remover)
- `Route::resource()` - Cria automaticamente as 7 rotas CRUD

**Grupos de rotas:**
- `prefix()` - Adiciona prefixo na URL (`/admin/noticias`)
- `name()` - Prefixo para nomes de rotas (`admin.noticias.index`)
- `middleware()` - Aplica middleware a todas as rotas do grupo

### 5. Middleware

Middleware é um **filtro de requisições** que executa antes do controller.

**Exemplo: `app/Http/Middleware/EhAdmin.php`**

```php
class EhAdmin
{
    public function handle(Request $request, Closure $next)
    {
        // Verifica se usuário está logado E é admin
        if (!$request->user() || !$request->user()->is_admin) {
            abort(403, 'Acesso negado: usuário não é administrador.');
        }

        // Se passou, continua para o próximo middleware/controller
        return $next($request);
    }
}
```

**Registro do middleware: `bootstrap/app.php`**

```php
->withMiddleware(function (Middleware $middleware) {
    $middleware->alias([
        'eh.admin' => \App\Http\Middleware\EhAdmin::class,
    ]);
})
```

⚠️ **Importante**: No Laravel 11+, a configuração de middleware mudou do `app/Http/Kernel.php` (que não existe mais) para `bootstrap/app.php`.

### 6. Views (Blade Templates)

Blade é o **sistema de templates** do Laravel, permitindo PHP dentro de HTML de forma elegante.

**Exemplo: `resources/views/publico/index.blade.php`**

```blade
@extends('layouts.app')

@section('title', 'Início')

@section('content')
    <h2>Últimas Notícias</h2>

    @if($noticias->count())
        <div class="news-grid">
            @foreach($noticias as $noticia)
                <article class="news-card">
                    <h3>
                        <a href="{{ route('noticia.show', $noticia->slug) }}">
                            {{ $noticia->titulo }}
                        </a>
                    </h3>
                    <p>{{ $noticia->resumo }}</p>
                </article>
            @endforeach
        </div>

        {{ $noticias->links() }}
    @else
        <p>Nenhuma notícia publicada.</p>
    @endif
@endsection
```

**Diretivas Blade mais usadas:**

| Diretiva | Função |
|----------|--------|
| `@extends('layout')` | Herda de um layout |
| `@section('nome')` | Define uma seção |
| `@yield('nome')` | Exibe uma seção |
| `@if` / `@else` / `@endif` | Condicionais |
| `@foreach` / `@endforeach` | Loops |
| `{{ $variavel }}` | Exibe variável (escapada) |
| `{!! $html !!}` | Exibe HTML sem escapar |
| `@csrf` | Token de segurança em formulários |
| `@method('PUT')` | Spoofing de método HTTP |

### 7. Relacionamentos Eloquent

O Eloquent facilita trabalhar com relações entre tabelas.

**Tipos implementados neste projeto:**

#### One to Many (Um para Muitos)

```php
// Model TipoNoticia
public function noticias()
{
    return $this->hasMany(Noticia::class, 'tipo_noticia_id');
}

// Model Noticia
public function tipo()
{
    return $this->belongsTo(TipoNoticia::class, 'tipo_noticia_id');
}

// Uso:
$tipo = TipoNoticia::find(1);
$tipo->noticias; // Todas as notícias deste tipo

$noticia = Noticia::find(1);
$noticia->tipo->nome; // Nome do tipo desta notícia
```

### 8. Seeders e Factories

**Seeders** populam o banco com dados iniciais.
**Factories** geram dados falsos para testes.

**Exemplo: `database/seeders/UsuarioSeeder.php`**

```php
class UsuarioSeeder extends Seeder
{
    public function run(): void
    {
        Usuario::create([
            'name' => 'Administrador',
            'email' => 'admin@exemplo.com',
            'password' => bcrypt('password'),
            'is_admin' => true,
        ]);
    }
}
```

**Exemplo: `database/factories/NoticiaFactory.php`**

```php
public function definition(): array
{
    $titulo = $this->faker->sentence(random_int(3, 8));
    
    return [
        'titulo' => $titulo,
        'slug' => Str::slug($titulo) . '-' . Str::random(5),
        'resumo' => $this->faker->optional()->paragraph(),
        'conteudo' => $this->faker->paragraphs(random_int(3, 7), true),
        'tipo_noticia_id' => TipoNoticia::inRandomOrder()->first()->id,
        'usuario_id' => Usuario::inRandomOrder()->first()->id,
        'publicado_em' => $this->faker->optional(0.8)->dateTimeBetween('-30 days', 'now'),
    ];
}
```

---

## 🗄 Estrutura do Banco de Dados

### Diagrama ER (Entity-Relationship)

```
┌─────────────────┐         ┌──────────────────┐         ┌─────────────────┐
│   usuarios      │         │   noticias       │         │ tipos_noticias  │
├─────────────────┤         ├──────────────────┤         ├─────────────────┤
│ id              │────┐    │ id               │    ┌────│ id              │
│ name            │    │    │ titulo           │    │    │ nome            │
│ email (unique)  │    │    │ slug (unique)    │    │    │ slug (unique)   │
│ password        │    └───<│ usuario_id (FK)  │    │    │ created_at      │
│ is_admin        │         │ tipo_noticia_id  │>───┘    │ updated_at      │
│ created_at      │         │ (FK)             │         └─────────────────┘
│ updated_at      │         │ resumo           │
└─────────────────┘         │ conteudo         │
                            │ publicado_em     │
                            │ created_at       │
                            │ updated_at       │
                            └──────────────────┘
```

### Relacionamentos

- **Noticia** `belongsTo` **TipoNoticia** (Muitas notícias para um tipo)
- **Noticia** `belongsTo` **Usuario** (Muitas notícias para um autor)

### Campos Importantes

**publicado_em (timestamp nullable)**
- `NULL` = Rascunho (não aparece no site público)
- `<data>` = Publicada (visível para todos)

**slug (string unique)**
- URL amigável para SEO
- Exemplo: `"minha-noticia"` em vez de `?id=123`

---

## 🛣 Rotas do Sistema

### Rotas Públicas

| Método | URI | Nome | Ação |
|--------|-----|------|------|
| GET | `/` | `home` | Lista notícias publicadas |
| GET | `/noticia/{slug}` | `noticia.show` | Exibe notícia completa |
| GET | `/login` | `login` | Formulário de login |
| POST | `/login` | - | Processa login |
| POST | `/logout` | `logout` | Faz logout |

### Rotas Administrativas (requer autenticação + admin)

| Método | URI | Nome | Ação |
|--------|-----|------|------|
| GET | `/admin` | `admin.dashboard` | Dashboard |
| **Notícias** | | | |
| GET | `/admin/noticias` | `admin.noticias.index` | Lista notícias |
| GET | `/admin/noticias/create` | `admin.noticias.create` | Form criar |
| POST | `/admin/noticias` | `admin.noticias.store` | Salva notícia |
| GET | `/admin/noticias/{id}/edit` | `admin.noticias.edit` | Form editar |
| PUT | `/admin/noticias/{id}` | `admin.noticias.update` | Atualiza |
| DELETE | `/admin/noticias/{id}` | `admin.noticias.destroy` | Remove |
| **Tipos de Notícia** | | | |
| GET | `/admin/tipos-noticia` | `admin.tipos-noticia.index` | Lista tipos |
| GET | `/admin/tipos-noticia/create` | `admin.tipos-noticia.create` | Form criar |
| POST | `/admin/tipos-noticia` | `admin.tipos-noticia.store` | Salva tipo |
| GET | `/admin/tipos-noticia/{id}/edit` | `admin.tipos-noticia.edit` | Form editar |
| PUT | `/admin/tipos-noticia/{id}` | `admin.tipos-noticia.update` | Atualiza |
| DELETE | `/admin/tipos-noticia/{id}` | `admin.tipos-noticia.destroy` | Remove |
| **Usuários** | | | |
| GET | `/admin/usuarios` | `admin.usuarios.index` | Lista usuários |
| GET | `/admin/usuarios/create` | `admin.usuarios.create` | Form criar |
| POST | `/admin/usuarios` | `admin.usuarios.store` | Salva usuário |
| GET | `/admin/usuarios/{id}/edit` | `admin.usuarios.edit` | Form editar |
| PUT | `/admin/usuarios/{id}` | `admin.usuarios.update` | Atualiza |
| DELETE | `/admin/usuarios/{id}` | `admin.usuarios.destroy` | Remove |

**Ver todas as rotas:**
```bash
php artisan route:list
```

---

## 🔐 Sistema de Autenticação

Este projeto usa **autenticação customizada** (sem Breeze/Jetstream) para fins didáticos.

### Fluxo de Login

1. **Usuário acessa** `/login`
2. **LoginController::mostrarForm()** exibe o formulário
3. **Usuário preenche** email e senha
4. **LoginController::login()** valida credenciais
5. **Se válido**: Cria sessão e redireciona para `/admin`
6. **Se inválido**: Retorna com erro

**Código: `app/Http/Controllers/Auth/LoginController.php`**

```php
public function login(Request $request)
{
    $credentials = $request->validate([
        'email' => 'required|email',
        'password' => 'required',
    ]);

    // Tenta autenticar
    if (Auth::attempt($credentials)) {
        $request->session()->regenerate();
        return redirect()->route('admin.dashboard');
    }

    // Falhou
    return back()->withErrors([
        'email' => 'As credenciais não correspondem aos nossos registros.',
    ])->onlyInput('email');
}
```

### Proteção de Rotas

Middleware `auth` garante que usuário está logado:

```php
Route::middleware(['auth'])->group(function() {
    // Só acessível se estiver logado
});
```

Middleware `eh.admin` garante que é administrador:

```php
Route::middleware(['auth', 'eh.admin'])->group(function() {
    // Só acessível se for admin
});
```

### Verificar usuário logado na View

```blade
@if(auth()->check())
    <p>Olá, {{ auth()->user()->name }}</p>
@else
    <a href="{{ route('login') }}">Entrar</a>
@endif
```

### Model Usuario vs User (Customização Importante)

⚠️ **IMPORTANTE PARA ALUNOS:**

O Laravel, por padrão, vem com um model `User` e uma tabela `users`. Neste projeto educacional, **customizamos isso** para usar nomenclatura em português:

- ✅ **Model**: `Usuario` (em vez de `User`)
- ✅ **Tabela**: `usuarios` (em vez de `users`)

#### Como fizemos essa customização?

**1. Arquivo de Configuração de Autenticação**

Em `config/auth.php`, alteramos o provider para usar nosso model:

```php
'providers' => [
    'users' => [
        'driver' => 'eloquent',
        'model' => App\Models\Usuario::class,  // ← Customizado!
    ],
],
```

**2. Criamos o Model Usuario**

O model `app/Models/Usuario.php` estende `Authenticatable` (necessário para autenticação):

```php
use Illuminate\Foundation\Auth\User as Authenticatable;

class Usuario extends Authenticatable
{
    // ... configurações
}
```

**3. Criamos a Migration da tabela usuarios**

Em `database/migrations/2025_11_03_232158_create_usuarios_table.php`:

```php
Schema::create('usuarios', function (Blueprint $table) {
    $table->id();
    $table->string('name');
    $table->string('email')->unique();
    $table->string('password');
    $table->boolean('is_admin')->default(false);
    $table->timestamps();
});
```

#### Por que fizemos isso?

- 🎓 **Objetivo didático**: Mostrar que podemos customizar o Laravel
- 🇧🇷 **Nomenclatura em português**: Facilita compreensão para alunos brasileiros
- 📚 **Aprendizado**: Entender como funciona o sistema de autenticação do Laravel

#### O que você precisa saber?

Quando você vê `auth()->user()` ou `$request->user()`, o Laravel está:
1. Consultando `config/auth.php` para saber qual model usar
2. Encontrando `App\Models\Usuario::class`
3. Buscando o usuário na tabela `usuarios`

**Não confundir:**
- ❌ `App\Models\User` - Não existe neste projeto
- ✅ `App\Models\Usuario` - O que estamos usando

---

## 🎛 Área Administrativa

### Dashboard

Exibe estatísticas do sistema:
- Total de notícias
- Notícias publicadas
- Total de tipos de notícia
- Total de usuários

### Sistema de Publicação

Cada notícia tem uma checkbox **"Publicar imediatamente"**:

- ✅ **Marcada**: Define `publicado_em = now()` → Visível no site
- ❌ **Desmarcada**: Define `publicado_em = null` → Rascunho

**Lógica no Controller:**

```php
public function store(Request $request)
{
    $data = $request->validate([...]);
    
    // Se checkbox marcada, publica
    if ($request->has('publicar') && $request->publicar == '1') {
        $data['publicado_em'] = now();
    }
    
    Noticia::create($data);
    return redirect()->route('admin.noticias.index');
}
```

### Interface Moderna

- **Sidebar navegável**: Menu lateral sempre visível
- **Cards estatísticos**: Dashboard com indicadores visuais
- **Tabelas responsivas**: Listagem organizada com ações
- **Formulários validados**: Feedback instantâneo de erros
- **Zona de perigo**: Exclusões separadas e destacadas

---

## 🎨 Customizações e Extensões

### Adicionar um novo tipo de notícia

1. Acesse `/admin/tipos-noticia`
2. Clique em "Novo Tipo"
3. Preencha nome e slug
4. Salve

### Criar uma nova notícia

1. Acesse `/admin/noticias`
2. Clique em "Nova Notícia"
3. Preencha todos os campos
4. Marque "Publicar imediatamente" se quiser que apareça no site
5. Salve

### Adicionar um novo usuário administrador

1. Acesse `/admin/usuarios`
2. Clique em "Novo Usuário"
3. Preencha os dados
4. **Marque** "É administrador"
5. Salve

### Modificar o layout

Os estilos estão em `public/css/app.css`. Você pode modificar:
- Cores (variáveis CSS no topo do arquivo)
- Espaçamentos
- Tipografia
- Componentes visuais

### Adicionar validações customizadas

No controller, dentro do `validate()`:

```php
$data = $request->validate([
    'titulo' => 'required|string|max:255',
    'slug' => 'required|string|max:255|unique:noticias,slug',
    'conteudo' => 'required|string|min:100', // Mínimo 100 caracteres
]);
```

---

## 🔧 Comandos Úteis

### Artisan (CLI do Laravel)

```bash
# Ver todas as rotas
php artisan route:list

# Listar comandos disponíveis
php artisan list

# Limpar caches
php artisan optimize:clear

# Ver configurações
php artisan config:show database

# Criar novo controller
php artisan make:controller NomeController --resource

# Criar novo model com migration
php artisan make:model NomeModel -m

# Criar novo middleware
php artisan make:middleware NomeMiddleware

# Recriar banco de dados
php artisan migrate:fresh --seed

# Entrar no Tinker (console PHP/Laravel)
php artisan tinker
```

### Composer

```bash
# Instalar dependências
composer install

# Atualizar dependências
composer update

# Adicionar novo pacote
composer require nome/pacote

# Remover pacote
composer remove nome/pacote

# Autoload dump
composer dump-autoload
```

### Git

```bash
# Ver status
git status

# Adicionar arquivos
git add .

# Commit
git commit -m "Mensagem"

# Push
git push origin main

# Pull
git pull origin main

# Ver histórico
git log --oneline
```

---

## ❗ Resolução de Problemas

### Erro: "Target class [eh.admin] does not exist"

**Causa**: Middleware não registrado corretamente.

**Solução**: Verificar `bootstrap/app.php`:

```php
->withMiddleware(function (Middleware $middleware) {
    $middleware->alias([
        'eh.admin' => \App\Http\Middleware\EhAdmin::class,
    ]);
})
```

### Erro: "Class 'App\Models\TipoNoticia' not found"

**Causa**: Falta o `use` no topo do controller.

**Solução**: Adicionar:

```php
use App\Models\TipoNoticia;
```

### Erro: "Class 'App\Models\User' not found"

**Causa**: Você está tentando usar o model padrão `User` do Laravel, mas este projeto usa `Usuario`.

**Solução**: 
- Use `App\Models\Usuario` em vez de `App\Models\User`
- Verifique `config/auth.php` - deve estar configurado para `Usuario::class`
- A tabela no banco é `usuarios`, não `users`

### Erro: "SQLSTATE[HY000] [2002] Connection refused"

**Causa**: MySQL não está rodando ou credenciais erradas.

**Solução**:
- Verificar se MySQL está ativo: `systemctl status mysql`
- Conferir credenciais no `.env`
- No Dev Container, usar `DB_HOST=db`

### Erro: "419 Page Expired"

**Causa**: Token CSRF inválido ou sessão expirou.

**Solução**: 
- Recarregar a página
- Verificar se formulário tem `@csrf`

### Notícias não aparecem na página inicial

**Causa**: Campo `publicado_em` está `NULL`.

**Solução**:
- Editar notícia no admin
- Marcar checkbox "Publicada"
- Salvar

### Server não inicia: "Address already in use"

**Causa**: Porta 8000 já está em uso.

**Solução**:
```bash
# Usar outra porta
php artisan serve --port=8001

# Ou matar processo na porta 8000
lsof -ti:8000 | xargs kill -9
```

---

## 🎓 Exercícios Propostos

Para consolidar o aprendizado, tente implementar:

### Nível Básico
1. ✏️ Adicionar campo "Autor" na listagem pública de notícias
2. 🎨 Mudar as cores do tema no CSS
3. 📧 Adicionar validação de email único no cadastro de usuários
4. 🔍 Adicionar contador de visualizações nas notícias

### Nível Intermediário
5. 🏷️ Implementar sistema de tags (many-to-many)
6. 💬 Adicionar comentários nas notícias
7. 📷 Upload de imagem de capa para notícias
8. 🔎 Implementar busca por título

### Nível Avançado
9. 📊 Criar relatório de notícias mais acessadas
10. 🌐 Implementar API REST para o sistema
11. 📱 Criar sistema de notificações
12. 🔒 Implementar níveis de permissão (admin, editor, autor)

---

## 🤝 Contribuindo

Este é um projeto educacional. Contribuições são bem-vindas!

### Como contribuir

1. Faça um Fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/NovaFuncionalidade`)
3. Commit suas mudanças (`git commit -m 'Adiciona nova funcionalidade'`)
4. Push para a branch (`git push origin feature/NovaFuncionalidade`)
5. Abra um Pull Request

### Diretrizes

- Mantenha o código limpo e comentado
- Siga as convenções do Laravel
- Adicione testes quando possível
- Atualize a documentação se necessário

---

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

## 📚 Recursos Adicionais

### Documentação Oficial
- [Laravel 12 Documentation](https://laravel.com/docs/12.x)
- [PHP 8.4 Documentation](https://www.php.net/docs.php)
- [MySQL 8.0 Documentation](https://dev.mysql.com/doc/refman/8.0/en/)

### Tutoriais Recomendados
- [Laracasts](https://laracasts.com/) - Vídeos sobre Laravel
- [Laravel Daily](https://www.youtube.com/@LaravelDaily) - Canal no YouTube
- [Laravel News](https://laravel-news.com/) - Notícias e tutoriais

### Comunidade
- [Laravel Brasil](https://github.com/laravelbrasil) - Comunidade brasileira
- [Fórum Oficial Laravel](https://laracasts.com/discuss)
- [Discord Laravel](https://discord.gg/laravel)

---

## 🙏 Agradecimentos

Este projeto foi desenvolvido com fins educacionais para auxiliar estudantes no aprendizado de desenvolvimento web com Laravel.

Agradecimentos especiais à comunidade Laravel por toda documentação e recursos disponibilizados.

---

## 📞 Suporte

Encontrou algum problema ou tem dúvidas?

- 📧 Abra uma [Issue no GitHub](https://github.com/renato-mendes-uninassau/laravel-noticias/issues)
- 💬 Entre em contato através do GitHub

---

**Desenvolvido com ❤️ para fins educacionais**

⭐ Se este projeto te ajudou, considere dar uma estrela no GitHub!
