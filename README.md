# AngularCalculation

# Web Page for Mathematical Calculations using Angular

## AIM:
To design a dynamic website to perform mathematical calculations using Angular Framwork

## DESIGN STEPS:

### Step 1:

Requirement collection.

### Step 2:

Creating the layout using HTML and CSS in component.html file

### Step 3:

Write typescript to perform the calculations.

### Step 4:

Validate the layout in various browsers.

### Step 5:

Validate the HTML code.

### Step 6:

Publish the website in the given URL.

## PROGRAM :

cylinder.component.html:
```
<div>
    <h2>Area of a Cylinder</h2>
    Radius = <input  type="text" [(ngModel)]="radius"> Meters<br>
    Height = <input [(ngModel)]="height"type ="text">Meters<br>
    <input type="button" (click)="onCycCalculate()" value="calculate"><br>
    Area=<input [value]="area" type="text" >Meter<sup>2</sup>
</div>
cylinder.component.ts:
import { Component } from "@angular/core";
import { RadioControlValueAccessor } from "@angular/forms";

@Component({
    selector:'Cylinder-Area',
    templateUrl:'./cylinder.component.html'

})
export class CylinderComponent{
    radius:number
    height:number
    area:number
    
    constructor(){
        this.radius = 0
        this.height = 0
        this.area = 2*22/7*this.radius*(this.radius+this.height)

    }
    onCycCalculate(){
        this.area = this.area = 3.14*this.radius*this.radius*this.height
    }
}
rectangle.component.html:
<div>
    <h2>Area of a Rectangle</h2>
    Length = <input  type="text" [(ngModel)]="length"> Meters<br>
    Breadth = <input [(ngModel)]="breadth"type ="text">Meters<br>
    <input type="button" (click)="onCalculate()" value="calculate"><br>
    Area=<input [value]="area" type="text" >Meter<sup>2</sup>
</div>
rectangle.component.ts:
import { Component } from "@angular/core";

@Component({
    selector:'Rectangle-Area',
    templateUrl:'./rectangle.component.html'

})
export class RectangleComponent{
    length:number
    breadth:number
    area:number
    constructor(){
        this.length = 0
        this.breadth = 0
        this.area = this.length*this.breadth;


    }
    onCalculate(){
        this.area = this.length*this.breadth;
    }
}
app.component.html:
<body>
    <div class="container">
        <h1>Math Calculations</h1>
        <div class="subcontainer">
            <Cylinder-Area></Cylinder-Area>
            <div class="footer">Developed by Nagajyothi Chintha</div>

        </div>
        <div class="subcontainer">
            <Rectangle-Area></Rectangle-Area>
            <div class="footer">Developed by Nagajyothi Chintha</div>

        </div>
    </div>
</body>
app.component.ts:
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'mathcalculations';
}

app.component.css:
import { TestBed } from '@angular/core/testing';
import { AppComponent } from './app.component';

describe('AppComponent', () => {
  beforeEach(async () => {
    await TestBed.configureTestingModule({
      declarations: [
        AppComponent
      ],
    }).compileComponents();
  });

  it('should create the app', () => {
    const fixture = TestBed.createComponent(AppComponent);
    const app = fixture.componentInstance;
    expect(app).toBeTruthy();
  });

  it(`should have as title 'place'`, () => {
    const fixture = TestBed.createComponent(AppComponent);
    const app = fixture.componentInstance;
    expect(app.title).toEqual('place');
  });

  it('should render title', () => {
    const fixture = TestBed.createComponent(AppComponent);
    fixture.detectChanges();
    const compiled = fixture.nativeElement as HTMLElement;
    expect(compiled.querySelector('.content span')?.textContent).toContain('place app is running!');
  });
});

app.module.ts:
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { BrowserModule } from '@angular/platform-browser';

import { AppComponent } from './app.component';
import { CylinderComponent } from './cylinder/cylinder.component';
import { RectangleComponent } from './rectangle/rectangle.component';

@NgModule({
  declarations: [
    AppComponent,
    RectangleComponent,
    CylinderComponent
  ],
  imports: [
    BrowserModule,
    FormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

```

## OUTPUT:

![math](https://user-images.githubusercontent.com/94191344/154125031-2f71836f-11a3-4d55-8664-47788d0b5dce.PNG)


## Result:
Thus the program to create mathcalculation using angular is completed successfully.
