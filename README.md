# Angular-note
just note

建立新檔案
mkdir projectsName
ng new demo1(不要中文字)

npm start (run server)
ng generate component package名字 ng g c
ng generate -h

佈署 進到app之後 ng build
ng build --prod  壓縮js

更新local ng到新版本 ng update  global另外

資料繫結:

內嵌繫結{{property}} 單向的 從component.ts把值傳到component.html

屬性繫結[property]='statement' 綁定值  單向的 從component.ts把值傳到component.html

事件繫結(event)='someMethod($event)'    加上$event可以取得詳細資訊   
				單向的 從template裡面透過瀏覽器觸發後 呼叫component裡面的方法
雙向繫結[(ngModel)]='property'   會自動地做到屬性跟事件繫結 語法是屬性跟事件的結合 改template component 去module import

formate 重新排版vsc  (Alt+Shift+f)

範本參考變數:(多在Template裡面使用 Component不會讀到)
在範本中任意html標籤套用#name語法
    會在範本內建立一個名為name的區域變數
    該name區域變數將只能用於目前元件範本中
    該name區域變數將會儲存該標籤的DOM物件
    可以透過事件繫結將任意DOM物件中的任意屬性傳回元件類別中(Component class)
以下2種為完全相等語法
#name
ref-name

三種Angular指令(Directives)
元件型指令-預設元件就是一個含有樣板的指令(最常見)
屬性型指令-這種指令會修改元素的外觀或行為
	-例如內建的NgStyle 或NgClass指令就可自由變更樣式
	-(雙向繫結用的NgModule屬此類)
結構型指令-這種指令會透過新增或刪除DOM元素來改變DOM結構
	-例如內建的Ngif、NgFor 或NgSwitch 就可以用來控制DOM結構
	 (NgSwitch前不加上*  ////Ngif 、NgFor 、NgSwitchDefault 、NgSwitchCase前要加上*)


建立新module ng g m name / ng g m name -m 要註冊進的module的name
	需在article.module.ts   export出來才能用


若欲使用ng-module雙向繫結 需在module裡面imports FormsModule

建立服務元件ng g s name
6-49
7-54.55


MPA(Multi-page Application)
SPA(Single-page Application)搭配AJAX
AJAX-Asynchronus JavaScript and XML」的簡寫，即非同步JavaScript與XML技術。
RxJS是一個第三方函式庫，由 Angular 贊助，實現異步觀察模式。

RxJS
建立可觀察的Observable物件
var clicks$ = Rx.Observable.fromEvent(document, 'click');
建立觀察者物件(Observer)
var observer = { next: (x) => console.log(x); }
建立訂閱物件(訂閱Observable物件，並傳入Observer觀察者物件)
var subs$ = clicks$.subscribe(observer);
取消訂閱Subscription物件
subs$.unsubscribe();

簡化Observer的寫法

建立可觀察的Observable物件
var clicks$ = Rx.Observable.fromEvent(document, 'click');
建立訂閱物件(訂閱Observable物件並自動建立觀察者物件)
var subs$ = clicks$.subscribe((x) => console.log(x));

https://www.slideshare.net/WillHuangTW/angular-2-advanced-topic-rxjs
https://blog.techbridge.cc/2017/12/08/rxjs/
