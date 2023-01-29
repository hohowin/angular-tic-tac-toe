# angular-tic-tac-toe

Youtube: [Angular for Beginners - Let's build a Tic-Tac-Toe PWA](https://youtu.be/G0bBLvWXBvc)

## Installation

Global Install:

```bash
npm install -g @angular/cli
```

Create app, choose `SCSS`:

```
ng new my-app
```

---

## Development

1\. Remove all code in `app.component.html` except for the line `<router-outlet></router-outlet>`.

2\. Generate Square:

```bash
ng generate component square
```

3\. Variable can directly be used in html. E.g.:

In app.module.ts `<app-square></app-square>`
In ts, `rando = Math.random()`, then in html, `{{ rando }}`

4\. For passing input from parent component, use `@input()` declarator. (Note: Only input is a dumb component)

5\. Try:

Square ts `@Input() val: 'X' | 'O' = 'X';`
Square html `<button>{{ val }}</button>`
app html `<app-square [val]="'O'"></app-square>`

6\. Generate smart component board (has state and can change):

```bash
ng generate component board
```

- constructor is for dependency injection
- ngOnInit is a lifecycle hook for initial setup
- [get](https://stackoverflow.com/questions/22823946/can-javascript-function-name-contain-a-space#:~:text=No%2C%20in%20javascript%20a%20function,a%20property%20to%20a%20object.), [See here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get)
- [splice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)


---

# Transform into PWA

```bash
ng add @angular/pwa
ng build

# Optional. Run it and inspect it in developer mode and lighthouse
npm install -g http-server
http-server -p 8080 -c-1 dist/angular-tic-tac-toe
```
`ngsw-config.json` is `angular service worker config`
`manifest.webmanifest` concerns about installability

