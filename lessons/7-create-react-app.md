# Create React App

Create React App คือ เครื่องมือที่ Set up environment สำหรับพัฒนา React Application ให้เรียบร้อยแล้วโดยที่เราไม่ต้องไปนั่ง Set up เอาเองตั้งแต่แรก

<br><hr><br>

## Let's Use It !

เราสามารถที่จะเรียกใช้ Create React App ได้ด้วย npx

ให้เราเปิด Terminal ขึ้นมาแล้วพิมพ์คำสั่ง

`npx create-react-app my-app`

⚠️ ถ้าใครพิมพ์ npx แล้วไม่เจอ command ให้ทำการ install nodejs ลงในเครื่องคอมเราก่อน [ที่นี่](https://nodejs.org/en/)

เมื่อ npx ทำการ Install และ Setup React app ให้เราเสร็จเรียบร้อยแล้ว ให้เรา cd ไปที่ React app folder `my-react-app` ด้วยคำสั่ง `cd my-react-app`

จากนั้นให้เราทำการ run React app ขึ้นมาด้วยคำสั่ง `npm start`

<br><hr><br>

## Import and Export

เวลาเราเขียนโค้ดไปเรื่อย ๆ ไฟล์จะเริ่มใหญ่มาก ทำให้เราไม่สามารถเขียนอยู่ในไฟล์เดียวได้ เราเลยมีความจำเป็นต้องแยกไฟล์ออกมา เพื่อให้ง่ายต่อการดูแล เมื่อเราแยกไฟล์ออกมาแล้วเราจะต้องมีวิธีการที่จะ Import functions อื่น ๆ เข้ามาใช้งาน และ Export functions ต่าง ๆ ไปให้ไฟล์อื่นใช้งาน

**1. Named Import & Export**

```js
// อยู่ในไฟล์ Counter.js

function Counter() {
  return <h1>Counter</h1>
}

export Counter
```

เวลา Import เข้ามาใช้ในไฟล์ App

```js
// อยู่ในไฟล์ App.js
import { Counter } from "./Counter";

function App() {
  return (
    <div className="app-container">
      <Counter />
    </div>
  );
}
```

**2. Module Import & Export**

```js
// อยู่ในไฟล์ Counter.js

function Counter() {
  return <h1>Counter</h1>;
}

export default Counter;
```

```js
// อยู่ในไฟล์ App.js
import Counter from "./Counter";

function App() {
  return (
    <div className="app-container">
      <Counter />
    </div>
  );
}
```

<br><hr><br>

## Exercises 🏅

A) ให้สร้าง Component `GreetingMessage` ที่แสดงข้อความทักทาย ซึ่งข้อความสามารถทักทายแต่ละคนได้

**เงื่อนไข:** สร้างไว้อีก File แล้ว Import เข้ามาใช้ใน App Component

B) ให้สร้าง Component `ProductItem` ที่แสดงข้อมูล Product แตกต่างกันออกไป

ข้อมูล Product มีดังนี้

- title: "XiaoMi Air Purifier"
- description: "Lorem ipsum dolor sit amet."
- price: 500

**เงื่อนไข:** สร้างไว้อีก File แล้ว Import เข้ามาใช้ใน App Component

<br><hr><br>

[Table of Contents](https://github.com/napatwongchr/intro-to-react/blob/main/README.md)
