## Properties and Events
  HTML Elements : Native Properties & event

  Directives    : Custom properties & event

  Components    : Custom properties & event
  
## Pass data from parent component to sub-component [property binding]
  Add @Input('alias') on the property of sub-component

  In parent component bind data to sub-component
  <app-server-element *ngFor="let serverElement of serverElements" 
        [alias]="serverElement">

## Pass data from sub-component to parent component [event]
  In sub component expose events by using @Output() and EventEmitter
  @Output() serverCreated = new EventEmitter<{serverName: string, serverContent: string}>();
  @Output('bpCreated') blueprintCreated = new EventEmitter<{serverName: string, serverContent: string}>();

  Then emit event in sub component
  onAddServer(nameInput: HTMLInputElement) {
    this.serverCreated.emit({
      serverName: nameInput.value,
      serverContent: this.serverContentInput.nativeElement.value
    });
  }
  
  In parent component bind the event
    <app-cockpit (serverCreated)="onServerAdded($event)" (bpCreated)="onBlueprintAdded($event)">
    </app-cockpit>

## ng-content