# Project Guidelines

## Code Style
- C# models use immutable POCOs with clear domain concepts (see [SocOps/Models/](SocOps/Models/))
- Razor components follow parameter-driven pattern with EventCallback for interactions (see [SocOps/Components/](SocOps/Components/))
- CSS utilities are custom-built, Tailwind-like vocabulary (see [.github/instructions/css-utilities.instructions.md](.github/instructions/css-utilities.instructions.md))

## Architecture
- Blazor WebAssembly app with layered structure: UI components → scoped services → pure logic services → data models
- State management via BingoGameService with localStorage persistence and event-driven reactivity
- Component hierarchy: Home → GameScreen → BingoBoard → BingoSquare + BingoModal
- Service injection: Scoped for per-session state, enabling multiple local instances

## Build and Test
- Restore: `dotnet restore SocOps/SocOps.csproj`
- Build: `dotnet build SocOps/SocOps.csproj`
- Run dev server: `dotnet run --project SocOps/SocOps.csproj` (starts on http://localhost:5166)
- Deploy: Automatic via GitHub Actions on push to main

## Conventions
- Async persistence with fire-and-forget pattern for non-blocking UI updates
- JSInterop limited to localStorage only, no heavy npm dependencies
- Event subscriptions for complex state flows instead of cascading parameters
- Free space (center square) auto-marked and immutable after initialization
- Versioned localStorage schema with STORAGE_VERSION constant for breaking changes