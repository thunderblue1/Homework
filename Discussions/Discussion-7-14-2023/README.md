# Angular Directive

---
###### Student: John Keen
###### Professor: Bobby Estey
###### Assignment: JohnDirective
###### Date: 7/14/2023

---

---
### Export Example

#### john.directive.ts:

```typescript
import { Directive, ElementRef, HostListener, Input } from '@angular/core';

@Directive({
    selector: '[appJohn]'
})
export class JohnDirective {
    @Input() appJohn!:string;
    highlighted:boolean;
    constructor(private el: ElementRef) {
        this.highlighted = false;
    }
    @HostListener('click',['$event.target']) onClick(){
        if(this.highlighted==true) {
            this.highlighted = false;
            this.dejohnize();
            console.log(this.appJohn);
        } else {
            this.highlighted = true;
            this.johnize(this.appJohn);
        }
    }
    private johnize(color:string) {
        this.el.nativeElement.style="background-color:"+color+"; padding:5px;font-weight:bold;";
    }

    private dejohnize() {
        this.el.nativeElement.style="background-color:none; padding:0px;font-weight:normal;";
    }
}
```

#### app-component.ts:

```typescript
import { Component } from '@angular/core';
import { Router } from '@angular/router';

@Component({
    selector: 'app-root',
    templateUrl: './app.component.html',
    styleUrls: ['./app.component.css']
})
export class AppComponent {
    constructor(private router: Router){

    }
    color = 'green';
    title = 'John Directive';
}
```

#### app.component.html

```html
<form action="">
    <label for="color"></label>
    <input type="text" id="color" name="color" [(ngModel)]="color"/>
</form>

<div [appJohn]=color>This is a sentence.</div>
```
