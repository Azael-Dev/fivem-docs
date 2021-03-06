---
title: การติดตั้งทรัพยากร
weight: 210
description: >
  คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการติดตั้ง
---

## เริ่มต้นการใช้งาน

1. ดาวน์โหลดและแตกไฟล์ลงในโฟลเดอร์ `resources` ของคุณ ชื่อของทรัพยากรจะต้องเป็น `azael_db-health&armor` ห้ามแก้ไขชื่อของทรัพยากรโดยเด็ดขาด เนื่องจากทรัพยากรจะไม่ทำงาน
2. เปิดไฟล์ `server.cfg` เพิ่ม `ensure azael_db-health&armor` ไว้ด้านล่าง [mysql-async][mysql-async], [es_extended][es_extended] และ [esx_status][esx_status]

**หมายเหตุ:** ไม่เเนะนำให้รีสตาร์ททรัพยากรนี้ เนื่องจากทรัพยากรนี้ทำงานร่วมกับทรัพยากร [esx_status](https://github.com/esx-framework/esx_status) เเละอาจจะทำให้เกิดข้อผิดพลาดได้

{{% alert theme="info" %}}
หากใช้งานทรัพยากร `AllServerNeed` หรือ `AllServerNeedV2` ของ **Xenon** จะต้องปิดใช้งานรหัสการเพิ่มเลือดในขณะที่เข้าเกม

ค้นหา

```lua
SetEntityHealth(GetPlayerPed(-1), 200)
```

แก้ไขเป็น

```lua
--SetEntityHealth(GetPlayerPed(-1), 200)
```
{{% /alert %}}

## ยกเลิกการใช้งาน

1. เปิดไฟล์ `server.cfg` ค้นหา `ensure azael_db-health&armor`
2. ทำการเพิ่ม `#` ไว้ข้างหน้า `ensure azael_db-health&armor`

ตัวอย่าง:
```
#ensure azael_db-health&armor
```

[mysql-async]: https://github.com/brouznouf/fivem-mysql-async
[es_extended]: https://github.com/esx-framework/es_extended
[esx_status]: https://github.com/esx-framework/esx_status
