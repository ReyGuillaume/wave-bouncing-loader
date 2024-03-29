# Cool loading animation

![Wave Bouncing Animation](https://github.com/ReyGuillaume/wave-bouncing-loader/blob/main/wave-loader-animation.gif "Wave Bouncing Animation")

### Obtenir cette animation

```css
.myWord {
  color: #3c2e9e;
  -webkit-box-reflect: below -0.4em linear-gradient(transparent, #00000045);
}
```

Ici, la clause `-webkit-box-reflect` nous permet d'obtenir ce petit effet de reflet qui donne de la perspective à notre loader.

```css
.myWord > .myLetter {
  display: inline-block;
  animation: bouncing-wave-animation 2s infinite;
  animation-delay: calc(0.25s * var(--item));
}
```

Le `display: inline-block` est nécessaire pour pouvoir utiliser la clause transform lors de l'animation.
En jouant sur `animation-delay` et avec une variable css `--item` définie dans le code source de la page, l'on peut faire en sorte que ces animations se lancent a des intervales différents ce qui crée cet effet de vague.

```css
@keyframes bouncing-wave-animation {
  0%, 40%, 100% {
    transform: translateY(0);
  }
  20% {
    transform: translateY(-0.4em);
  }
}
```

N'oubliez pas de définir l'animation des lettres. En jouant sur `transform: translateY()`, l'on peut facilement arriver au résultat ci-dessus.
