## Access form fields by using two-way binding
  Bind property with HTML element
  <input type="text" class="form-control" [(ngModel)]="newServerName">

  Read from fields through property
  ```
  onAddServer(){
    this.serverCreated.emit({
      serverName: this.newServerName
    });
  }
  ```