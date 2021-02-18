# Lifecycle Methods

Lifecycle คืออะไร ?​ ให้เรานึกถึง วงจรชีวิตของยุง เริ่มจาก ไข่ -> ลูกน้ำ -> ตัวโม่ง -> ยุงลาย ถูกมั้ยครับ 🦟 เช่นเดียวกันกับ React Component ซึ่งก็มี Lifecycle เช่นเดียวกัน เราลองมา zoom ดู Counter component กันสักหน่อย

![Component Lifecycle](./images/lifecycle-methods.png)

**Component Lifecycle แบ่งออกเป็น 3 phase**

**1. Mounting Phase** เป็น Phase ที่จะเกิดขึ้นเมื่อ Component กำลังจะถูก mount เข้าไปใน DOM

- constructor method จะถูกรันก่อนเพื่อสร้าง component object
- ต่อมา render method จะถูกรันต่อเพื่อ render element เข้าไปใน DOM
- เมื่อ element ถูก render เข้าไปใน DOM เสร็จเรียบร้อยแล้ว React จะทำการ call `componentDidMount` method

**ใช้ตอนไหน ?**

- `componentDidMount` ใช้ตอนที่เราจะ fetch ข้อมูลจาก server

**2. Updating Phase** เป็น Phase ที่จะเกิดขึ้นเมื่อ props หรือ states เปลี่ยนแปลง

- `shouldComponentUpdate` จะถูก called และเป็นตัวที่ตัดสินใจว่า component นี้ควร update ไหม ? ถ้าไม่ให้ return false
- ต่อมา render method จะถูกรันต่อเพื่อ render element เข้าไปใน DOM
- `componentDidUpdate` จะถูก called หลังจาก component update

**ใช้ตอนไหน ?**

- `componentDidUpdate` ใช้เวลาทำการ request ข้อมูลจาก server (⚠️ ควร compare prevProps กับ props เสมอ ๆ ไม่งั้นจะติด Loop)

**3. Unmounting Phase** เป็น Phase ที่จะเกิดขึ้นเมื่อ Component ถูกลบออกจาก DOM

**ใช้ตอนไหน ?**

- ใช้เวลาเราต้องการ cancel network requests
- ใช้ clean subscriptions
- ใช้ clear ตัว set timer ต่าง ๆ เช่น serInterval()
