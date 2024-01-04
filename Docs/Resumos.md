# Estudando .NET e C#

## .NET:

1. **O que é .NET?**
   - É uma plataforma de desenvolvimento open-source, criada pela Microsoft para a criação de aplicações de desktop, Web e móveis que podem ser executadas nativamente em qualquer sistema operacional.
   - Possibilita a criação de códigos em linguagens, como C#, VB.NET e F#.

2. **Componentes principais do .NET:**
   - **Common Language Runtime (CLR):** é o componente de máquina virtual da plataforma .NET da Microsoft que gerencia a execução de programas .NET.
   - **Base Class Library (BCL):** é um conjunto de classes e tipos fundamentais que fazem parte de uma plataforma de programação. Essas classes fornecem funcionalidades essenciais, como tipos de dados básicos, tratamento de exceções, operações de entrada/saída, manipulação de strings, e mais. No contexto do .NET, a BCL inclui namespaces centrais como System, System.Collections, System.IO, System.Text, e assim por diante. Essas classes formam a base sobre a qual funcionalidades mais especializadas podem ser construídas.

3. **Versões do .NET:**
   - **.NET Framework:** Originalmente para Windows.
   - **.NET Core:** Plataforma multiplataforma.
   - **.NET 5, .NET 6, etc.:** Versões mais recentes que unificam o .NET Framework e o .NET Core.
   
# C#

## Introdução ao C#:

1. **O que é C#?**

- O C# (pronuncia-se "C Sharp") é uma linguagem de programação moderna, orientada a objeto e fortemente tipada. Desenvolvida pela Microsoft, o C# permite a criação de aplicativos seguros e robustos que rodam no .NET. 

2. Os programas C# são executados no .NET, que consiste no CLR (Common Language Runtime) e em um conjunto de bibliotecas de classes. O CLR é a implementação da CLI (Common Language Infrastructure), um padrão internacional. O código-fonte C# é compilado em IL (linguagem intermediária) e armazenado em assemblies (.dll ou .exe). Durante a execução, o CLR converte o código IL em instruções nativas da máquina.

3. **IDE (Ambiente de Desenvolvimento Integrado):**
   - O Visual Studio é a IDE mais comumente usada para desenvolvimento em C#.

## Sintaxe Básica:

### Exemplo 1: Olá, Mundo!

```csharp
//Neste exemplo, Console.WriteLine é usado para imprimir "Olá, Mundo!" na tela.
using System;
class Program {
    static void Main() {
        Console.WriteLine("Olá, Mundo!");
    }
}
```
## Estrutura do Programa em C#

A estrutura do programa em C# é organizada em diversos níveis hierárquicos, proporcionando uma abordagem modular e escalável.

### Namespaces:
Os namespaces em C# são empregados de duas maneiras distintas. Primeiramente, no âmbito do .NET, são utilizados para organizar classes. Por exemplo, o .NET usa o namespace System para agrupar classes.

```csharp
System.Console.WriteLine("Hello World!");
```
A palavra-chave using pode ser empregada para evitar a necessidade de usar o nome completo do namespace, como no exemplo:
```csharp
using System;
Console.WriteLine("Hello World!");
```
Em segundo lugar, os desenvolvedores podem declarar seus próprios namespaces para controlar o escopo de nomes em projetos maiores. A palavra-chave namespace é utilizada para essa declaração. Com a introdução do C# 10, é possível declarar um namespace para todos os tipos definidos em um arquivo de forma mais concisa:

```csharp
namespace SampleNamespace;

class AnotherSampleClass
{
    public void AnotherSampleMethod()
    {
        System.Console.WriteLine("SampleMethod inside SampleNamespace");
    }
}
```
### Main() e Argumentos de Linha de Comando em C#

O método Main é o ponto de entrada de um aplicativo C#. É o primeiro método invocado quando o aplicativo é iniciado. Pode haver apenas um ponto de entrada em um programa C#.

```csharp
class TestClass
{
    static void Main(string[] args)
    {
        Console.WriteLine(args.Length);
    }
}
```
Ao enviar argumentos para o método Main em C#, você pode definir o método de diversas maneiras, dependendo da necessidade de retorno de valor e do uso de operações assíncronas:

- *Sem retorno de valor, sem uso de await (com args):*
```csharp
static void Main(string[] args);
```
- *Com retorno de valor, sem uso de await (com args):*
```csharp
static int Main(string[] args);
```
- *Sem retorno de valor, com uso de await (com args):*
```csharp
static async Task Main(string[] args);
```

- *Com retorno de valor, com uso de await (com args):*
```csharp
static async Task<int> Main(string[] args);
```

- *Sem retorno de valor, sem uso de await (sem args):*
```csharp
static void Main();
```

- *Com retorno de valor, sem uso de await (sem args):*
```csharp
static int Main();
```

- *Sem retorno de valor, com uso de await (sem args):*
```csharp
static async Task Main();
```

- *Com retorno de valor, com uso de await (sem args):*
```csharp
static async Task<int> Main();
```
Do C# 9 em diante, você não precisa incluir explicitamente um método Main em projetos de aplicativo de console.

# Construção de programas C# 

## Membros 
Em C#, os membros de uma classe podem ser estáticos (pertencentes à classe) ou de instância (pertencentes a objetos dessa classe).

**Constantes:** Valores constantes associados à classe.

```csharp
public class Exemplo
{
    public const int ValorConstante = 10;
}
```
**Campos:** Variáveis associadas à classe.

```csharp
public class Ponto
{
    public int X; // Campo de instância
    public static int ContadorPontos = 0; // Campo estático
}
```

**Métodos:** Ações que podem ser executadas pela classe.

```csharp

public class Calculadora
{
    public int Somar(int a, int b)
    {
        return a + b;
    }
}
```
**Propriedades:** Ações associadas à leitura e gravação de propriedades nomeadas da classe.

```csharp

public class Pessoa
{
    private string nome; // campo privado
    public string Nome
    {
        get { return nome; }
        set { nome = value; }
    }
}
```
**Indexadores:** Ações associadas à indexação de instâncias da classe como uma matriz.

```csharp

public class Colecao
{
    private string[] elementos = new string[10];
    public string this[int indice]
    {
        get { return elementos[indice]; }
        set { elementos[indice] = value; }
    }
}
```
**Eventos:** Notificações que podem ser geradas pela classe.

```csharp

public class Publicador
{
    public event EventHandler AlgumEvento;
}
```

**Operadores:** Conversões e operadores de expressão com suporte na classe.

```csharp

public class Matriz
{
    public static Matriz operator +(Matriz a, Matriz b)
    {
        // Implementação da adição de matrizes
    }
}
```
**Construtores:** Ações necessárias para inicializar instâncias da classe ou a própria classe.

```csharp

public class Produto
{
    public Produto(string nome, double preco)
    {
        Nome = nome;
        Preco = preco;
    }
}
```
## Acessibilidade

A acessibilidade em C# refere-se ao controle do acesso aos membros de uma classe. Existem seis formas possíveis de acessibilidade, cada uma determinando quais partes do programa podem acessar um membro específico. Os modificadores de acesso são resumidos da seguinte forma:

**public:** Permite acesso ilimitado a qualquer parte do programa.

**private:** Restringe o acesso ao membro apenas à própria classe que o contém.

**protected:** Limita o acesso ao membro à própria classe e às classes derivadas dessa classe.

**internal:** Restringe o acesso ao membro ao assembly atual (.exe ou .dll).

**protected internal:** Permite acesso ao membro pela classe que o contém, por classes derivadas dessa classe e por classes dentro do mesmo assembly.

**private protected:** Limita o acesso ao membro à própria classe ou a classes derivadas desse tipo dentro do mesmo assembly.


### Tipos:

No C#, existem diversos tipos de dados que você pode usar para representar diferentes tipos de informações.

### Tipos Internos:

O compilador utiliza informações de tipo para garantir operações fortemente tipadas, evitando erros de execução.

**Tipos Numéricos:**
- *int (Inteiro):*
```csharp
int idade = 25;
```

- *double (Ponto Flutuante):*
```csharp
double altura = 1.75;
```

- *decimal (Decimal):*
```csharp
decimal preco = 10.99m;
```
- *float (Ponto Flutuante de Precisão Simples):*

```csharp
float temperatura = 25.5f;
```

**Tipo de Texto:**

- *string (Cadeia de Caracteres):*
```csharp
string nome = "Maria";
```

**Tipo Lógico:**
- *bool (Booleano):*
```csharp
bool estaChovendo = false;
```
**Tipo de Data e Hora:**

- *DateTime:*
```csharp
DateTime dataAtual = DateTime.Now;
```
### Variáveis locais tipadas implicitamente

Você pode deixar o compilador inferir o tipo da variável da expressão de inicialização. Para fazer isso, use a palavra-chave 
```csharp 
var nomeDaVariavel = valorInicial; 
```
 Em vez do nome de um tipo.

### Tipos Personalizados:

Criados pelos desenvolvedores usando construções como struct, class, interface, enum e record.

Cada tipo pode incluir informações como espaço de armazenamento, valores mínimo e máximo, membros (métodos, campos, eventos), tipo base, interface implementada e operações permitidas.

```csharp
// Definição da struct para coordenadas
public struct Coordenadas
{
    public int X { get; set; }
    public int Y { get; set; }
}

// Definição da interface para informações de veículos
public interface IInfoVeiculo
{
    string Modelo { get; }
    int Ano { get; }
}

// Definição da enum para cores de veículos
public enum Cores
{
    Vermelho,
    Azul,
    Verde,
    Amarelo
}

// Definição da class para representar um carro
public class Carro : IInfoVeiculo
{
    public string Modelo { get; set; }
    public int Ano { get; set; }
    public Cores Cor { get; set; }

    // Construtor
    public Carro(string modelo, int ano, Cores cor)
    {
        Modelo = modelo;
        Ano = ano;
        Cor = cor;
    }
}

// Definição do record para veículo registrado
public record VeiculoRegistrado(string Modelo, int Ano, Cores Cor, string Proprietario) : IInfoVeiculo;
```
## Declaração de Variáveis:

A declaração de variáveis em C# envolve especificar o tipo de dado da variável e opcionalmente atribuir um valor inicial.

### Sintaxe básica para declarar variáveis em C#:

```csharp
tipo nomeDaVariavel; // Declaração

// Ou

tipo nomeDaVariavel = valorInicial; // Declaração e inicialização
```
**Exemplo:**

```csharp
int idade; // Declaração

idade = 25; // Atribuição de valor

// Ou
int idade = 25; // Declaração e inicialização
``


## Estruturas de Controle de Fluxo

**Instruções de seleção – if, if-else e switch**

continua...

---
**Legenda:**
- **Open Source:** [Software de Código Aberto](https://canaltech.com.br/produtos/O-que-e-open-source/) é o software de computador que tem seu código fonte disponibilizado e licenciado com uma licença de código aberto no qual o direito autoral fornece o direito de estudar, modificar e distribuir o software de graça para qualquer um e para qualquer finalidade.
- **Sistema Operacional** []( https://www.alura.com.br/artigos/sistemas-operacionais-conceito-estrutura) Basicamente, um sistema operacional é um software, que pode ser o Linux, Windows, Android, macOS, UNIX, entre outros. 
- **Common Language Runtime (CLR):** O [tempo de execução de linguagem comum](https://learn.microsoft.com/pt-br/dotnet/standard/clr)
- **Base Class Library (BCL):** O [ Biblioteca de Classes Base](https://medium.com/@sadigrzazada20/base-class-library-bcl-and-framework-class-library-fcl-652a470261d2#:~:text=Base%20Class%20Library%20(BCL)%3A,%2C%20string%20manipulation%2C%20and%20more)

- **Namespace:** [](https://learn.microsoft.com/pt-br/dotnet/csharp/fundamentals/types/namespaces)
