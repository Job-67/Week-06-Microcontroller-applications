# Lab6_2 Multiple Source Files ESP32 Project

This project demonstrates managing multiple source and header files in an ESP32 project using ESP-IDF and CMake, as described in the lab instructions.

# Lab6_2 Multiple Source Files ESP32 Project

## คำตอบคำถามทบทวน

1. **Multiple Source Files**: การแยก source code เป็นหลายไฟล์ช่วยให้โค้ดอ่านง่าย แก้ไขและดูแลรักษาง่าย สามารถแยกฟังก์ชันแต่ละส่วนออกจากกันได้ชัดเจน

2. **CMakeLists.txt Management**: ต้องเพิ่มชื่อไฟล์ source (.c) ทั้งหมดที่ต้องการ build ลงใน SRCS ของ idf_component_register ใน main/CMakeLists.txt

3. **Header Files**: header file (.h) ใช้สำหรับประกาศฟังก์ชันและโครงสร้างข้อมูล เพื่อให้ไฟล์อื่น ๆ สามารถ include และเรียกใช้ได้อย่างถูกต้อง

4. **Include Directories**: ต้องระบุ INCLUDE_DIRS ใน CMakeLists.txt เพื่อให้ compiler หา header files เจอ เช่น INCLUDE_DIRS "."

5. **Git Ignore**: .gitignore ช่วยกันไม่ให้ไฟล์ build, ไฟล์ชั่วคราว และไฟล์ที่ไม่จำเป็นถูก track ใน git ทำให้โปรเจกต์สะอาด

6. **Task Management**: การใช้ FreeRTOS task ในโมดูล LED (หรืออื่น ๆ) ช่วยให้สามารถทำงานแบบ multitasking ได้ เช่น กระพริบ LED พร้อมกับอ่าน sensor

7. **Code Organization**: การแยกโมดูล sensor, display, led เป็นไฟล์แยกกันช่วยให้โค้ดเป็นระเบียบและดูแลรักษาง่าย สามารถ reuse หรือแก้ไขแต่ละส่วนได้โดยไม่กระทบกัน