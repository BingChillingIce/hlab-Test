
<p> 
1. Assuming the system currently has three microservices: Customer API, Master Data API, and Transaction Data API, there is a new feature that requires data from all three microservices to be displayed in near real-time. The current technology stack includes REST APIs and an RDBMS database. How would you design a new API for this feature? 
</p>

![Screenshot 2025-03-29 192259](https://github.com/user-attachments/assets/ca9ef4ce-22eb-43fc-9b02-4823cd9f4ff2) 

<p> Ans .</p>
<p>
จาก sequence diagram  client จะเรียก api ไปที่ microservice ที่เป็น new feature แล้ว microservice ตัวนี้จะทำการเรียก service อีก 3 ตัวเพื่อ รวบรวมข้อมูลจากทั้ง 3 service 
Main หลักคือต้องการข้อมูลของ customer service ถ้า query data customer ไม่พบ ก็ต้อง response error ออกไปเลยเพื่อไม่ให้ใช้ทรัพยากรโดยสูยเปล่า
1. ข้อมูล customer เรียกหา service ด้วย customerId
2. master data  ในความเข้าใจ master data จะเป็น data ที่ไม่มีการเปลี่ยนแปลงบ่อยนานๆ update data ครั้ง สามารถ caching ด้วยการใช้ redis เพื่อความรวดเร็วทมี่มากขึ้น
3. Transaction จะ query data ด้วย customerId มีการทำ pagination เป็น option
ทั้ง 3 service นี้ จะถูกเรียกหาในพร้อมๆกัน เพื่อความรวดเร็ว
</p>

<p>
Assuming the team has started planning a new project, the project manager asks you for a performance test strategy plan for this release. How would you recommend proceeding to the project manager? 
</p>

<p> Ans .</p>
<p>
...
</p>


<p>
3. Design and develop with robust test two APIs using NestJS and Postgres with the following specifications: 

a. Create a Multilingual Product API: Develop an API that allows for the creation of products, each with attributes for name and description that support multiple languages.

b. Multilingual Product Search API: Implement an API that enables searching for products by name in any language and returns results in a paginated format. 
Additional Requirements: 

</p>

