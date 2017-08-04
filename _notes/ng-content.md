## ng-content 

Define content template in the parent component
```
  <app-server-element *ngFor="let serverElement of serverElements" [srvElement]="serverElement" 
            [name]="serverElement.name">
    <p #contentParagraph>
      <strong *ngIf="serverElement.type === 'server'" style="color: red">{{ serverElement.content }}</strong>
      <em *ngIf="serverElement.type === 'blueprint'">{{ serverElement.content }}</em>
    </p>
  </app-server-element>
```
Use <ng-content> in sub-component

```
  <div class="panel-body">
    <ng-content></ng-content>
  </div>
```