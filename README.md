This repository contains CSS snippets you can apply to [WebLiero](https://www.webliero.com) as user CSS to either enhance HUD usability and/or aesthetics.

If you use Chrome/Chromium you can use an extension like [User JavaScript and CSS](https://chrome.google.com/webstore/detail/user-javascript-and-css/nbhcbdghjpllgmfilhnhkllmkecfmpld) to install and manage these snippets.

## No-name-away :poop::no_entry_sign:

**Category:** functionality

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

## Fancier health/ammo bars

**Category:** aesthetics

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
## Less intrusive menu buttons

**Category:** aesthetics, functionality

This makes the top-right menus transparent, thus returning visibility to the top-right corner. It also pushes the Main Menu button top the top-right-most corner to make better use of [Fitt's law](https://en.wikipedia.org/wiki/Fitts%27s_law).

```css
.game-view > .buttons {
  padding: 0;   /* Fitt was here */
  opacity: 0.5; /* make button text semi-opaque unless hovered */
}

.game-view > .buttons:hover {
  opacity: 1;
}

.game-view > .buttons button {
  background: transparent; /* see-thru buttons */
  border-radius: 0;        /* no need for rounded corners if you can't see them */
  font-weight: normal;     /* bold text is distracting */
}
```

## Square dropdown menus

**Category:** aesthetics

```css
.dropmenu-view {
  border-width: 1px;
  border-radius: 0;
}
```
