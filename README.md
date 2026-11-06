# Jazari law book

The .NET documentation that [Jazari](https://github.com/Eni-M/MyOwnLLM) searches to ground its answers: a SQLite file
with full-text search tables and a vector for each passage. `jazari update` downloads it from this repository's releases
and checks it against the SHA-256 pinned in Jazari's manifest.

## What's inside

- 55,500 passages of Microsoft's .NET, ASP.NET Core and Entity Framework Core docs, with their section paths and
  learn.microsoft.com addresses (FTS5 tables `chunks`, `pages`, `page_terms`, `chunk_names`, `aliases`).
- One int8 vector per passage (`vectors`), written with
  [bge-small-en-v1.5](https://huggingface.co/BAAI/bge-small-en-v1.5) (MIT).

Built by `lawbook/build.py` and `embed-law-book` in the Jazari repository, from these commits:

| Source | Commit |
|---|---|
| [dotnet/docs](https://github.com/dotnet/docs) | `40fbd4674d72503f18781f67dec0fa69315bb84a` |
| [dotnet/AspNetCore.Docs](https://github.com/dotnet/AspNetCore.Docs) | `9dfb3e392d31b33761e7cc5070ea4a7d92082907` |
| [dotnet/EntityFramework.Docs](https://github.com/dotnet/EntityFramework.Docs) | `b0c8daf21d4dd8157e9696e77942278b9722b226` |

## License and credit

The documentation text is © Microsoft and contributors, licensed under
[Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/); its code samples are
under the [MIT License](https://opensource.org/licenses/MIT), as in each source repository's `LICENSE` and `LICENSE-CODE`.
This file changes the docs' form only: Markdown split into passages, with search indexes and vectors added. It is not an
official Microsoft product and is not endorsed by Microsoft.
