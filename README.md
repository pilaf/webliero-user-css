# WebLiero User CSS Collection

This repository contains CSS snippets you can apply to [WebLiero](https://www.webliero.com) as user CSS to either enhance HUD usability and/or aesthetics.

**IMPORTANT:** All the snippets displayed here are nothing more than hacks, unintended and unsupported by the developer of WebLiero. If a new version of WebLiero comes out and breaks your user CSS **DO NOT** complain to the developer.

If you use Chrome/Chromium you can use an extension like [User JavaScript and CSS](https://chrome.google.com/webstore/detail/user-javascript-and-css/nbhcbdghjpllgmfilhnhkllmkecfmpld) to install and manage these snippets.

In that same extension you may have to enable the option "Highest CSS priority" for these CSS rules to actually take effect.

![Highest CSS priority](screenshots/user-css-setup.png)

## Index

* [No-name-away](#no-name-away-poopno_entry_sign)
* [3D health/ammo bars](#3d-healthammo-bars-wip)
* [Unobtrusive menu buttons](#unobtrusive-menu-buttons)
* [Square dropdown menus](#square-dropdown-menus)

## No-name-away :poop::no_entry_sign:

**Category:** functionality

Some players use whitespace names so to make themselves less visible in-game (by not having a nametag). This fixes that problem by putting colons around all players' nametags.

```css
.playername div::before {
  content: ":"; /* change this to any other character(s) you like */
}

.playername div::after {
  content: ":"; /* change this to any other character(s) you like */
}
```

## 3D health/ammo bars (WIP)

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

## Unobtrusive menu buttons

**Category:** aesthetics, functionality

![Unobtrusive menu buttons](screenshots/unobstrusive-menu-buttons.png)

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

<!-- vim: set nofoldenable: -->
