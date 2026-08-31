<img width="100%" src="https://capsule-render.vercel.app/api?type=rect&height=110&color=0:512bd4,100:5cadc0&text=Alexandre.Core&fontColor=ffffff&fontSize=42&fontAlignY=45&desc=um%20pacote%20NuGet%20que%20respira&descAlignY=70&descSize=13"/>

<div align="center">

[![](https://img.shields.io/badge/NuGet-v3.0.1-512bd4?style=flat-square&logo=nuget&logoColor=white)](https://github.com/DevX4N)
[![](https://img.shields.io/badge/.NET-8.0-512bd4?style=flat-square&logo=dotnet&logoColor=white)](https://dotnet.microsoft.com)
[![](https://img.shields.io/badge/downloads-4-5cadc0?style=flat-square)](https://github.com/DevX4N?tab=followers)
[![](https://img.shields.io/badge/build-passing%20(local)-5cadc0?style=flat-square)](#)
[![](https://img.shields.io/badge/license-MIT%20(acho)-8b949e?style=flat-square)](#)

</div>

```powershell
PM> Install-Package Alexandre.Core -Version 3.0.1
```

```bash
dotnet add package Alexandre.Core
# ⚠️  este pacote não tem dependências. ele É a dependência.
```

---

## 📦 Sobre o pacote

Desenvolvedor .NET em **Santa Catarina**. Transforma requisitos vagos em `IServiceCollection` bem configurada. Compatível com C#, JavaScript e prazos otimistas.

<div align="center">
  <img src="https://skillicons.dev/icons?i=cs,dotnet,visualstudio,js,html,css,git,github,supabase,wordpress,vite,nextjs,typescript,nodejs,react,mysql,postman,vscode&theme=dark&perline=9"/>
</div>

---

## 🧬 Implementação

```csharp
namespace Alexandre.Core;

public sealed class Alexandre : IDeveloper, IDisposable
{
    public string Nome     => "Alexandre";
    public string Local    => "Santa Catarina, BR";
    public string Handle   => "@DevX4N";
    public TimeOnly Pico   => new(23, 55);

    private int _cafes = 0;

    public async Task<Software> ResolverAsync(Problema p, CancellationToken ct)
    {
        while (!Funciona(p))
        {
            await GoogleAsync(p.Mensagem, ct);   // etapa mais importante
            Console.WriteLine("aqui1");          // não remover, quebra tudo
            _cafes++;
        }

        return new Software { Bugs = Bugs.Insufficient, Docs = null! };
    }

    // TODO: remover antes do commit
    // TODO: (2024) sério, remover
    // TODO: (2026) já virou legado, deixa aí

    public void Dispose() => throw new NotImplementedException("nunca descanso");
}
```

---

## ⚙️ appsettings.json

```json
{
  "Alexandre": {
    "Ambiente": "Development",
    "Producao": "também é Development, mas ninguém sabe",
    "Logging": {
      "LogLevel": { "Default": "Console.WriteLine" }
    },
    "ConnectionStrings": {
      "Cafeteira": "Server=cozinha;Dose=3;Timeout=never"
    },
    "FeatureFlags": {
      "EscreverTestes": false,
      "EscreverTestesDepois": true,
      "DeployNaSexta": false,
      "DarkMode": "obrigatório"
    }
  }
}
```

---

## 🔨 Saída do build

```
Compilando Alexandre.Core...

Alexandre.cs(42,17): warning CS0219: a variável 'teste2' foi atribuída, mas
                     seu valor nunca é usado [mas eu vou precisar dela]
Alexandre.cs(58,9):  warning CS8602: desreferência de uma referência
                     possivelmente nula [confia]
Alexandre.cs(71,5):  warning CS1591: comentário XML ausente para o tipo
                     publicamente visível [propositalmente]
Alexandre.cs(88,13): warning CS0168: a variável 'ex' foi declarada, mas
                     nunca usada [catch vazio, clássico]

Compilação com êxito.
    412 Aviso(s)
    0 Erro(s)

Tempo Decorrido 00:00:03.14  ·  Tempo até quebrar em produção 00:04:12
```

---

## 💥 Exceção não tratada

<details>
<summary><code>System.NullReferenceException</code> — clique por sua conta e risco</summary>

<br>

```
Unhandled exception. System.NullReferenceException:
  Object reference not set to an instance of an object.

   at Alexandre.Core.Alexandre.ResolverAsync(Problema p)     in Alexandre.cs:line 58
   at Alexandre.Core.Motivacao.get_Segunda()                 in Semana.cs:line 1
   at Cliente.PedirMudancaSimples("só a cor do botão")       in Escopo.cs:line 9999
   at Sexta.Deploy()                                         in MaFase.cs:line 18
   --- End of stack trace ---

Dica: o objeto era nulo. Sempre foi. Você que confiou.
```

</details>

---

## 📚 Dependências

| Pacote | Versão | Obrigatório |
| :-- | :-: | :-: |
| `Cafe.Injection` | `>= 3.0.0` | ✅ |
| `StackOverflow.Client` | `latest` | ✅ |
| `Musica.Alta` | `1.0.0` | ✅ |
| `Newtonsoft.Json` | `13.x` | 😤 sempre |
| `Documentacao.Abstractions` | — | ❌ |
| `Sono` | `0.0.0-preview` | ❌ |

```csharp
// Program.cs
builder.Services.AddSingleton<IDeveloper, Alexandre>();  // só existe um
builder.Services.AddScoped<ICafe, CafeCoado>();
builder.Services.AddTransient<IIdeia, IdeiaAs2daManha>();
```

---

## 📈 Telemetria

<div align="center">

| build history | assemblies | janela de compilação |
| :-: | :-: | :-: |
| ![](https://github-profile-summary-cards.vercel.app/api/cards/stats?username=DevX4N&theme=transparent) | ![](https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=DevX4N&theme=transparent) | ![](https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=DevX4N&theme=transparent&utcOffset=-3) |

![](https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=DevX4N&theme=transparent)

<sub><code>// telemetria coletada pelo GitHub, não por mim — eu nem sei configurar isso</code></sub>

</div>

---

## 📝 Notas da versão

```markdown
## [3.0.1] — atual
### Adicionado
- suporte a .NET 8, depois de adiar por seis meses
- `async/await` em tudo, inclusive onde não precisava

### Corrigido
- `Console.WriteLine("aqui1")` que foi pra produção
- try/catch vazio (agora tem um comentário dentro)

### Removido
- nada. Nunca removo nada. Só comento.
```

---

<div align="center">
  <img src="https://raw.githubusercontent.com/DevX4N/DevX4N/output/snake.svg" alt="garbage collector"/>
  <br><sub><code>GC.Collect() em execução...</code></sub>
</div>

---

<div align="center">

### 🔗 Metadados do pacote

<a href="mailto:alexandrepereirax643@gmail.com"><img src="https://img.shields.io/badge/reportar%20issue-512bd4?style=for-the-badge&logo=gmail&logoColor=fff"/></a>
<a href="https://instagram.com/filh0x" target="_blank"><img src="https://img.shields.io/badge/canal%20informal-5cadc0?style=for-the-badge&logo=instagram&logoColor=fff"/></a>

<sub><code>Alexandre.Core</code> · MIT · sem garantias, com carinho</sub>

![](https://komarev.com/ghpvc/?username=DevX4N&label=restores&color=512bd4&style=flat-square)

</div>

<img width="100%" src="https://capsule-render.vercel.app/api?type=rect&color=0:5cadc0,100:512bd4&height=70&section=footer"/>
