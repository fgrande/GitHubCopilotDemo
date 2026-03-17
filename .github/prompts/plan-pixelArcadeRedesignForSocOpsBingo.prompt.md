## Plan: Pixel Arcade Redesign for SocOps Bingo

TL;DR: Transform the clean, modern bingo app into a retro pixel arcade game aesthetic with chunky fonts, bright neon colors, thick borders, and snappy animations.

**Steps**
1. Add pixel arcade CSS utilities to app.css: Define new color palette (neon blues, pinks, greens, yellows), pixel font imports (Press Start 2P), thick border classes, scanline backgrounds, glitch animations, and chunky button/square styles.
2. Update BingoSquare.razor: Apply pixelated square styling with beveled borders, neon colors for states, and hover/focus effects like glow or flicker.
3. Update BingoBoard.razor: Modify grid layout for thicker gaps, add background texture or scanlines, ensure 5x5 grid looks blocky.
4. Update GameScreen.razor: Redesign header with pixel font, add arcade-style borders, change button styles to chunky.
5. Update StartScreen.razor: Make welcome screen look like an arcade title screen with large pixel text, neon accents, and start button as a big arcade button.
6. Update BingoModal.razor: Style modal as a retro pop-up with pixel borders, add screen shake or particle effects on appearance.
7. Update MainLayout.razor and NavMenu.razor: Apply overall arcade theme, perhaps add a cabinet-like background or frame.
8. Add global styles: Set pixel font as default for headings, add body background with scanlines or dither pattern.

**Relevant files**
- [SocOps/wwwroot/css/app.css](SocOps/wwwroot/css/app.css) — Add new utilities and global styles
- [SocOps/Components/BingoSquare.razor](SocOps/Components/BingoSquare.razor) — Pixelate squares
- [SocOps/Components/BingoBoard.razor](SocOps/Components/BingoBoard.razor) — Chunky grid
- [SocOps/Components/GameScreen.razor](SocOps/Components/GameScreen.razor) — Arcade header
- [SocOps/Components/StartScreen.razor](SocOps/Components/StartScreen.razor) — Title screen
- [SocOps/Components/BingoModal.razor](SocOps/Components/BingoModal.razor) — Retro modal
- [SocOps/Layout/MainLayout.razor](SocOps/Layout/MainLayout.razor) — Overall theme
- [SocOps/Layout/NavMenu.razor](SocOps/Layout/NavMenu.razor) — Menu styling
- [SocOps/wwwroot/index.html](SocOps/wwwroot/index.html) — Add font link

**Verification**
1. Run `dotnet build SocOps/SocOps.csproj` to ensure no build errors.
2. Run `dotnet run --project SocOps/SocOps.csproj` and visually inspect the app in browser for pixel arcade aesthetic.
3. Test interactions: Marking squares, modal appearance, navigation — ensure functionality preserved.
4. Check responsiveness on different screen sizes, though prioritize desktop arcade feel.

**Decisions**
- Font: Use "Press Start 2P" from Google Fonts for all text to achieve authentic pixel look.
- Colors: Neon palette — electric blue (#00FFFF), hot pink (#FF00FF), lime green (#00FF00), bright yellow (#FFFF00), black (#000000), white (#FFFFFF).
- Borders: Thick 4px black borders for all elements to simulate pixel blocks.
- Animations: Replace smooth transitions with instant changes or short glitch effects (e.g., 0.1s flicker).
- Background: Add CSS scanlines using repeating-linear-gradient for retro CRT effect.
- Scope: Full visual overhaul while keeping component structure and logic intact.

**Further Considerations**
1. Audio: Should we add retro sound effects (e.g., beep on mark, fanfare on bingo)? If yes, how to implement (JSInterop for audio files)?
2. Pixel art assets: Add custom pixel images for icons or backgrounds? If so, source or create them.
3. Performance: Ensure new CSS doesn't impact load times; keep animations lightweight.
