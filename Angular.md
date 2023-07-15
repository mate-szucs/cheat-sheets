# CLI
ng generate application [name-in-kebab-case] {--project [pname]}
ng generate component [name-in-kebab-case] {--project [pname]}

# ngModel
```
import { FormsModule } from '@angular/forms';
```
## standalone
```
<input [(ngModel)]="variable" ....
```
## within form
```
<form>
  <input name="someNameRequired" [(ngModel)]="variable"  ....
```
## two way data binding by naming convention
```
<customComponent [(componentData)]="variable"
```
```
export class CustomComponent {
  @Input()  componentData: number;
  @Output() componentDataChange = new EventEmitter<number>();
  ***
    this.componentDataChange.emit(value);
```
