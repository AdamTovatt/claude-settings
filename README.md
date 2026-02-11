## Claude / MCP settings

The content of the `repo-root` folder in this repository should be copied to the root of any repository you want to match my Claude / MCP settings.

That means the `.mcp.json` file will be at root of that repository. The `.claude` directory will also be at the root of that repository.

If you haven't previously installed it, for the C# LSP MCP to work you need to run:

```bash
dotnet tool install --global csharp-ls
```

```bash
dotnet tool install --global CSharpLspMcp
```