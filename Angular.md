# CLI
```
ng generate application [name-in-kebab-case] {--project [pname]}
ng generate component [name-in-kebab-case] {--project [pname]}
```
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
# HttpClient (default An gular codec is buggy)

```
import { Injectable } from '@angular/core';
import { HttpParameterCodec } from '@angular/common/http';

@Injectable({
    providedIn: 'root',
})
export class HttpCodecService implements HttpParameterCodec {
    encodeKey(key: string): string {
        return encodeURIComponent(key);
    }

    encodeValue(value: string): string {
        return encodeURIComponent(value);
    }

    decodeKey(key: string): string {
        return decodeURIComponent(key);
    }

    decodeValue(value: string): string {
        return decodeURIComponent(value);
    }
}
```
```
            let httpParams = new HttpParams({ encoder: new HttpCodecService() });
            httpParams = httpParams.set('emailTel', emailTel);
            httpParams = httpParams.set('method', method);
            httpParams = httpParams.set('windowLocation', windowLocation);
            const httpOptions = {
                headers: new HttpHeaders({
                    'Content-Type': 'application/x-www-form-urlencoded;charset=utf-8',
                }),
            };
            const data: any = (await lastValueFrom(
                this.httpClient.post(this.authUrl + AuthenticationService.api.auth0Passwordless + '/start', httpParams /*.toString()*/, httpOptions),
            )) as any;
```
