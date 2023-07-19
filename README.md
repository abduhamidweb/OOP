# OOP
---
## 1. Object (Obyekt):
``
JavaScriptda obyekt, turli turdagi ma'lumotlarni bir biriga bog'lash imkonini beruvchi kompleks ma'lumot turi. Obyektlar, key-value (kalit-so'z:qiymat) juftliklaridan iborat bo'ladi.
``
```sh
// Obyekt yaratish
const shaxs = {
  ism: 'Ali',
  yosh: 25,
  kasb: 'Dasturchi',
};

// Obyektdan qiymatlarni o\'qish
console.log(shaxs.ism); // Konsolga "Ali" chiqadi.
console.log(shaxs.yosh); // Konsolga "25" chiqadi.

// Obyektdan qiymat yozish
shaxs.kasb = 'Muhandis'; // "Dasturchi" qiymatini "Muhandis" bilan almashtiradi.

```
---
## 2. Class (Klass):
``
Klasslar, obyektlarni yaratish uchun ma'lumotlarni qo'shish va unga tegishli metodlarni o'z ichiga olgan yordamdir. ES6 dan boshlab JavaScriptga klasslar qo'shilgan.
``
```sh
// Klass yaratish
class Shaxs {
  constructor(ism, yosh) {
    this.ism = ism;
    this.yosh = yosh;
  }

  tanish() {
    console.log(`Meni ismim ${this.ism} va men ${this.yosh} yoshdaman.`);
  }
}

// Klassdan obyekt yaratish
const shaxs1 = new Shaxs('Ali', 25);

// Obyektning metodini chaqirish
shaxs1.tanish(); // Konsolga "Meni ismim Ali va men 25 yoshdaman." chiqadi.
```
---
## 3. Inheritance (Meroslash):
``
Klasslardan boshqa klasslar yaratishning uslubi meroslash deyiladi. Meroslash, bir klassni boshqa klassga o'zlashtirish imkonini beradi.
``
```sh
// Klasslar meroslash
class Talaba extends Shaxs {
  constructor(ism, yosh, kurs) {
    super(ism, yosh);
    this.kurs = kurs;
  }

  talabaInfo() {
    console.log(`Meni ismim ${this.ism}, ${this.kurs}-kurs talabasi va men ${this.yosh} yoshdaman.`);
  }
}

// Klassdan obyekt yaratish
const talaba1 = new Talaba('Vali', 20, 3);

// Obyektning metodini chaqirish
talaba1.talabaInfo(); // Konsolga "Meni ismim Vali, 3-kurs talabasi va men 20 yoshdaman." chiqadi.
talaba1.tanish(); // Konsolga "Meni ismim Vali va men 20 yoshdaman." chiqadi.
```
---
## 4. Polymorphism (Polimorfizm):
``
Polimorfizm, bir funksiya yoki metodni turli turdagi klasslar uchun o'zgartirib, ularni bitta interfeysda birlashtirish imkonini beradi.
``
```sh
// Polimorfizm misoli
class GeometrikFigura {
  perimetr() {
    return 0;
  }
}

class Kvadrat extends GeometrikFigura {
  constructor(tomon) {
    super();
    this.tomon = tomon;
  }

  perimetr() {
    return 4 * this.tomon;
  }
}

class Doira extends GeometrikFigura {
  constructor(radius) {
    super();
    this.radius = radius;
  }

  perimetr() {
    return 2 * Math.PI * this.radius;
  }
}

function perimetrgaEgaFigura(figura) {
  console.log(`Figuraning perimetri: ${figura.perimetr()}`);
}

const kvadrat1 = new Kvadrat(5);
const doira1 = new Doira(3);

perimetrgaEgaFigura(kvadrat1); // Konsolga "Figuraning perimetri: 20" chiqadi.
perimetrgaEgaFigura(doira1); // Konsolga "Figuraning perimetri: 18.84955592153876" chiqadi.
```
---
## 5. Abstraction (Naychilash)
``
Naychilash, bitta klassdan boshqa klasslarga o'z atributlarini yashirish imkonini beradi.
``
```sh
// Naychilash misoli
class Shaxs {
  constructor(ism, yosh) {
    this.ism = ism;
    this.yosh = yosh;
  }

  // Metodlar naychilangan
}

// Naychilangan metodlar
class Talaba extends Shaxs {
  constructor(ism, yosh, kurs) {
    super(ism, yosh);
    this.kurs = kurs;
  }

  talabaInfo() {
    console.log(`Meni ismim ${this.ism}, ${this.kurs}-kurs talabasi va men ${this.yosh} yoshdaman.`);
  }
}

const talaba1 = new Talaba('Vali', 20, 3);
console.log(talaba1.ism); // Konsolga "Vali" chiqadi.
console.log(talaba1.yosh); // Konsolga "20" chiqadi.
```
---
## 6. Encapsulation (Qamrab olish):
``
Qamrab olish, klassning xususiyatlari va metodi o'zgarishlarga qarshi himoya qilish imkonini beradi. Bu, xususiyatlarni faqat klassning ichidagi metodlar orqali o'zgartirishni anglatadi.
``

```sh
// Qamrab olish misoli
class Shaxs {
  constructor(ism, yosh) {
    this._ism = ism;
    this._yosh = yosh;
  }

  // Getter va setter metodlar
  get ism() {
    return this._ism;
  }

  set ism(ism) {
    this._ism = ism;
  }

  get yosh() {
    return this._yosh;
  }

  set yosh(yosh) {
    if (yosh >= 0 && yosh <= 120) {
      this._yosh = yosh;
    } else {
      console.log('Yosh noto\'g\'ri kiritildi.');
    }
  }
}

const shaxs1 = new Shaxs('Ali', 25);
console.log(shaxs1.ism); // Konsolga "Ali" chiqadi.
shaxs1.ism = 'Vali'; // Xususiyat o'zgartiriladi
console.log(shaxs1.ism); // Konsolga "Vali" chiqadi.
shaxs1.yosh = 130; // Konsolga "Yosh noto'g'ri kiritildi." chiqadi.

```

