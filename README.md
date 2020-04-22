# LangSupport

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 9.0.6.

This project helps you display our web content in preferably in english or spanish depending on your choice.



ng g m i18n --module app




@ng-translate is used.
npm install @ngx-translate/core @ngx-translate/http-loader --save

Nothing fancy is going on. We just added the  TranslateModule and configured it to use the HttpClient to load translations. We exported TranslateModule as well to make the pipe transform available in the AppModule and in HTML templates. In the constructor, we specified available languages and used a function provided by ngx-translate to get and use the browser’s default language.

By default, the TranslateHttpLoader will load translations from the /assets/i18n/ folder, so let’s add a couple of files there.


and if you have to change the path of json file
export function translateLoaderFactory(httpClient: HttpClient) {
  return new TranslateHttpLoader(httpClient , '/assests/i18n/myjsons' , '.json');
}


Also, if you use the lazy loading and try seeing the changes in your modules, please include 
TranslateModule.forChild({}) in your imports in the child module.ts by importing TranslateModule from ngnx/tranlate. Because your i18n.module already exports TranslateModule.




