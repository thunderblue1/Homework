# Angular Exports and Declarations

---
###### Student: John Keen
###### Professor: Bobby Estey
###### Assignment: 
###### Date: 7/13/2023

---

---
### Export Example

#### business-math.component.ts:

```typescript
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-business-math',
  templateUrl: './business-math.component.html',
  styleUrls: ['./business-math.component.css']
})

export class BusinessMathComponent implements OnInit {
  calculation:number=0;
  ngOnInit(): void {
    this.calculation = BusinessMathComponent.fifteenPercent(2000);
  }
  public static fifteenPercent(whole: number): number {
    return whole*0.15;
  }
}
```

#### app-component.ts:

```typescript
import { Component } from '@angular/core';
import { BusinessMathComponent } from './business-math/business-math.component';
import { Router } from '@angular/router';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  constructor(private router: Router){
    this.whole=0;
    this.fifteen = 0;
  }

  title = 'Test';
  whole: number;
  fifteen: number;
  public buttonPress() {
    console.log("This is whole:"+this.whole);
    this.fifteen = BusinessMathComponent.fifteenPercent(this.whole);
    console.log("This is fifteen:"+this.fifteen);
  }
}
```

#### app.component.html

```html

<div>
  <form action="">
    <label for="whole"></label>
    <input type="number" id="whole" name="whole" [(ngModel)]="whole"/>
  </form>
</div>

<button (click)="buttonPress()">Calculate</button>

<div>
  <p>This is the fifteen variable</p>
  <p [innerHTML]="fifteen"></p>
</div>

<app-business-math></app-business-math>

<router-outlet></router-outlet>
```

### Declaration Example

```typescript
@NgModule({
  declarations: [
    AppComponent,
    BusinessMathComponent
  ],
  imports: [
    BrowserModule,
    FormsModule,
    AppRoutingModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
```