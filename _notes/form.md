## Access form fields by using two-way binding
  Two-way bind property with HTML element
  <input type="text" class="form-control" [(ngModel)]="newServerName">

  Read from fields through property
  ```
  onAddServer(){
    this.serverCreated.emit({
      serverName: this.newServerName
    });
  }
  ```

## Using local reference to get elements in the template
  ```
  <input type="text" class="form-control" #serverNameInput>
  <button class="btn btn-primary" (click)="onAddServer(serverNameInput)">Add Server</button>
  
  onAddServer(nameInput: HTMLInputElement) {
    this.serverCreated.emit({
      serverName: nameInput.value,
    });
  }
  ```

## Use ViewChild() Element reference 
  <input type="text" class="form-control" #serverContentInput>

  In class file
  ```
  @ViewChild('serverContentInput') serverContentInput: ElementRef;

  onAddServer() {
    this.serverCreated.emit({
      serverContent: this.serverContentInput.nativeElement.value
    });
  }

  DO NOT set nativeElement directly!
  ```