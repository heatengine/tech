# Angular

## Compilation
### JIT - Just In Time Compiler
- Creates vendor bundle to with angular compiler
- Shows Errors at run time
- Compiles the application in users browser
- Suitable for development purpose
### AOT-  Ahead Of Time Compiler
- Compiles application at run time (so the errors also)
- Smaller and faster
- Suitable for production

## Life Cycle Hooks
- constructor
- ngOnChange
- ngOnInit
- ngDoCheck
  - ngAfterContentInit
  - ngAfterContentChecked
  - ngAfterViewInit
  - ngAfterViewChecked
- ngOnDestroy

## Component ```@component```
- The most basic building block of Angular is a Component. It consist of 3 files
  1. template file (.html)
  2. component file {.ts}
  2. style file {.css}
```
@component({
  selector: 'app-component-name',
  template: './component-name.html',
  style: './component-name.css'
})

export class ComponentName {}
```

## Module ```@ngModule```
```
@NgModule({
  imports: [],
  declarations: [],
  providers: [],
  bootstrap: [AppComponent] // only in app component
})
export class AppModule {}
```
## Service ```@Injectable```
```
@Injectable({ providedIn: 'root' })
export class ServiceNameServiceService { }
```

## 

## Template Syntax

## What is diff btwn JS module and ngModule

## 3rd PARTY LIBRARY
- ngx-spinner
- ngx-cropper
- quill