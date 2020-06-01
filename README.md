### No-name-away

Some players use whitespace names so to make themselves less visible in-game (by not having a nametag). This fixes that problem by putting colons around player tags.

You can also change the colons for whatever other characters you prefer.

```css
/* Put colons around player names (prevents whitespace names' invisibility) */
.playername div::before {
  content: ":";
}

.playername div::after {
  content: ":";
}
```

### Fancier health/ammo bars

```css
/* HUD: ammo/health bars */
.hud-view .hud-main {
  background-color: transparent !important;
  box-shadow: none !important;
}

.hud-view .hud-main .bars {
  perspective: 150px;
  width: 400px;
}

.hud-view .hud-main .bar {
  background: rgba(0, 0, 0, 0.5);
  transform: rotate3d(-1, 0, 0, 45deg);
  overflow: hidden;
  height: 7px;
  box-shadow: 0 0 0 1px black;
}

.hud-view .hud-main .bar.health > div {
  background-color: #ff5959;
  box-shadow: 5px 5px 20px #ff5959;
}

.hud-view .hud-main .bar.ammo > div {
  background-color: #ffc77c;
  box-shadow: 5px 5px 20px #ffc77c;
}
```
### Less intrusive menu buttons

```css
/* HUD: menu */
.game-view > .buttons {
  padding: 0;
  opacity: 0.5;
}

.game-view > .buttons:hover {
  opacity: 1;
}

.game-view > .buttons button {
  background: transparent;
  border-radius: 0;
}

.game-view > .buttons button {
  background: transparent;
  border-radius: 0;
  font-weight: normal;
}

.dropmenu-view {
  border-width: 1px;
  border-radius: 0;
}
```
