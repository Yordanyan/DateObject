### Ի՞նչ է Date օբյեկտը

Date օբյեկտը JavaScript-ում ներկառուցված օբյեկտ է,որը  ցույց է տալիս ժամանակի որոշակի պահ։Այն հիմնված է Unix-ի timestamps-ի վրա, որը ներկայացնում է ժամանակը միլիվայրկյաններով,սկսված ՝ 1970 թվականի Հունվարի 1-ից։
Date օբյեկտը տրամադրում է մի շարք մեթոդներ ՝ ամսաթվերի և ժամերի հետ աշխատելու համար, ինչը թույլ է տալիս ծրագրավորողներին ձևափոխել այնպես,ինչպես որ անհրաժեշտ է։

### Ինչպես ստեղծել նոր Date

Նոր Date ստեղծելու համար մենք պետք է օգտվենք 'new' բանալի բառից և Date կոնստրուկտորից։
```js
const date = new Date(Date.UTC(2023, 1, 21, 12, 0, 0));
```
կամ
```js
const date = new Date("2023-02-21"); 
```

Մենք կարող ենք աշխատանքներ կատարել Date օբյեկտի հետ ՝ վերցնելով կամ ձևափոխելով դրանց։

```js
const date = new Date("2023-02-21T12:00:00Z");

const year = date.getFullYear(); // Վերադարձնում է տարին
const month = date.getMonth(); // Վերադարձնում է ամիսը
const day = date.getDate(); // Վերադարձնում է օրը
const hours = date.getHours(); // Վերադարձնում է ժամը
const minutes = date.getMinutes(); // Վերադարձնում է րոպեն
const seconds = date.getSeconds(); // Վերադարձնում է վայրկյանը
const milliseconds = date.getMilliseconds(); // Վերադարձնում է միլիվայրկյանը

date.setFullYear(2024); // Սահմանում է նոր տարի
date.setMonth(3); // Սահմանում է նոր ամիս
date.setDate(15); // Սահմանում է նոր օր
date.setHours(14); // Սահմանում է նոր ժամ
date.setMinutes(30); // Սահմանում է նոր րոպե
date.setSeconds(45); // Սահմանում է նոր վայրկյան
date.setMilliseconds(500); // Սահմանում է նոր միլիվայրկյան
```

### Ի՞նչպես մշակել ժամերը

Date օբյեկը տրամադրում է մի շարք մեթոդներ ՝ ամսաթվերի մշակման համար։ Մենք կարող ենք օգտագործել 'toLocaleDateString()' և  toLocaleTimeString() մեթոդները, որոնք կփոխեն ամսաթիվը ՝ կախված օգտագործողի local-ից։

```js 
const date = new Date("2005-03-17T12:00:00Z");

const isoString = date.toISOString(); // Վերադարձնում է ըստ ISO 8601 ֆորմատի "2005-03-17T12:00:00.000Z"
const dateString = date.toDateString(); // Վերադարձնում է այս ՝  "Mon March 17 2005"
const localeDateString = date.toLocaleDateString(); // Վերադարձնում է  "3/17/2005"
```

### Ի՞նչ հնարավորություններ ունի այս օբյեկտը

Date օբյեկտը մեզ նաև տրամադրում է մի շարք մեթոդներ,որոնք հնարավորություն են տալիս համեմատել և իրականացնել մաթեմաթիկական գործողություններ

```js
const date1 = new Date("2023-02-21T12:00:00Z");
const date2 = new Date("2023-02-22T12:00:00Z");

const diff = date2.getTime() - date1.getTime(); // Վերադարձնում է տարբերությունը
const diffInDays = diff / (1000 * 60 * 60 * 24); // Ձևափոխում է տարբերությունը օրերով

const tomorrow = new Date();
tomorrow.setDate(tomorrow.getDate() + 1); // Սահմանում է հաջորդ օրերով
tomorrow.setHours(0, 0, 0, 0); // Սահմանում  է կեսգիշեր

const isBefore = date1 < date2; // Վերադարձնում է true եթե date1-ը ավելի վաղ է քան date2-ը
const isAfter = date1 > date2; //Վերադարձնում է true եթե date1-ը ավելի ուշ է քան date2-ը
const isEqual = date1.getTime() === date2.getTime(); // Վերադարձնում է true եթե իրար հավասար են։
```
