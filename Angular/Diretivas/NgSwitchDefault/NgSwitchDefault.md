## NgSwitchDefault

Mostra o conteudo se nunhum dos case for verdadeiro

```js
<div [ngSwitch]="profile">
<p *ngSwitchCase="root"> Ola</p>
<p *ngSwitchCase="user"> Ola</p>
<p *ngSwitchDefault> Ola</p>
</div>
```