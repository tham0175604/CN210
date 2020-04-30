# รายงานวิชา CN210

### สรุปเนื้อหา
วิชาสถาปัตยกรรมคอมพิวเตอร์ เรียนรู้การทำงานของ CPU MIPS โดย MIPS ซึ่งเป็นหน่วยประมวลผล 32 bits ออกแบบโดยบริษัท MIPS มี 3 รูปแบบ 
คือ R-Format ใช้คำนวณค่า เช่น บวก ลบ , J-Format ใช้กระโดดข้ามไปใช้คำสั่งที่ตำแหน่งอื่นๆ และ I-Format ใช้อ่านค่าและเก็บค่า ซึ่ง cpu จะทำงานคำสั่งเป็นขั้นตอน คำสั่งที่เจอส่วนใหญ่จะเป็น add sub beq jump lw sw slt โดยจะมีรูปแบบการทำงานแบบ Single Cycle, Multicycle และ Pipelining โดย Pipelining จะทำงานเร็วที่สุดแต่ต้องเขียนการทำงานของคำสั่งทุกคำสั่งจนจบ ส่วน Multicycle จะเร็วรองลงมา และ Single Cycle จะช้าที่สุด หากทำคำสั่งที่เยอะมากๆ จะเห็นผลชัดเจน

#### งานครั้งที่ 1
  * [CLIP1(Youtube)](https://www.youtube.com/watch?v=9prW90Cxy1k)
   ![](  ) 
    
  ++ คำอธิบาย : คลิปนี้จะอธิบายเกี่ยวกับ MIPs โดย MIPS เป็นหน่วยประมวลผล 32 bits ออกแบบโดยบริษัท MIPS มี 3 แบบ คือ R-Format,I-Format และ
               J-Format ซึ่งการใช้ MIPS ในการคำนวณซึ่งจะใช้ R-Format ในการเก็บค่า ซึ่งฟังก์ชั่นในการคำนวณคือ ฟังก์ชัน add ซึ่ง R-Format มี 6 ส่วน
               จะประกอบด้วย op rs rt rd shamt func โดย op มีไว้บอกว่าเป็น R-type หรือ I-type ใช้บอกว่าเก็บค่าไว้ Register ตัวไหน shamt 
               ใช้บอกว่าจะ shift ไปด้านไหน func ใช้บอกว่าให้ทำคำสั่งอะไร
               
#### งานครั้งที่ 2 
  * [CLIP2(Youtube)](https://www.youtube.com/watch?v=f3IktFSWI3Y)
  
  
  ++ คำอธิบาย : คลิปนี้อธิบายหลักการทำงานของ cpu จากนั้นมันจะอ่านคำสั่งที่ตำแหน่ง 0 แล้วทำงาน ไม่ว่าจะเป็นการที่ jump คำสั่ง add คำสั่ง load คำสั่ง store 
               ทุกอย่างจะรันเป็นขั้นตอนตามภาษาที่ยกตัวอย่างคือ Java ว่าเป็น I-Format หรือ R-Format หรือ J-Format ขึ้นอยู่กับ opcode ว่าให้ทำอะไร
  
#### งานครั้งที่ 3
  * [CLIP3(Youtube)](https://www.youtube.com/watch?v=BW_B_ZATatA)
  
  
  ++ คำอธิบาย : คลิปนี้จะอธิบายเกี่ยวกับความแตกต่างของ Single Cycle กับ Multicycle โดยสิ่งที่เห็นได้ชัดเจนคือ รอบการทำงานของ Multicycle มากกว่า Single 
               Cycle เพราะมีรูปแบบสถาปัตยกรรมต่างกัน Multicycle มี Mux มากกว่า Single Cycle แต่มี ALU น้อยกว่า Single Cycle และสิ่งที่เห็นได้ชัดเจนที่สุด                      คือ Multicycle ใช้เวลาทำคำสั่งหนึ่งๆได้น้อยกว่า Single Cycle
  
#### งานครั้งที่ 4
  * [CLIP4(Youtube)](https://www.youtube.com/watch?v=nuxHZJcRDfg)
  
  
  ++ คำอธิบาย : คลิปนี้จะอธิบายเกี่ยวกับการทำงานของคำสั่ง Load Word ในรูปแบบ Multicycle โดยเริ่มต้นจากการ Fetch จะเป็นการส่งค่าให้ register และส่งค่าให้ ALU 
               เพื่อ +4 และทำstepต่อไป จากนั้นก็ทำ Fetch+1 เพื่อเก็บค่า register 2 ตัว และส่งเข้าไปที่ ALUOut จากนั้นทำการ Mem1 เป็นการส่งค่าจาก Register 
               ไปเข้า ALU เพื่อทำคำสั่งแล้วส่งให้ ALUOut หลังจากนั้นก็ส่งเข้า Memory data register
  
#### งานครั้งที่ 5
  * [CLIP5(Youtube)](https://www.youtube.com/watch?v=deR_ZT8uqBw&t=15s)
  
  
  ++ คำอธิบาย : คลิปนี้อธิบายการทำงานของคำสั่ง Branch On Equal หรือ Beq ใน Multicycle โดยจะเริ่มต้นจากการ Fetch จะเป็นการส่งค่าให้ register และส่งค่า
               ให้ ALU เพื่อ +4 และพร้อมทำขั้นตอนต่อไป เสร็จแล้วก็ถอดรหัสเพื่อเก็บค่าเข้า register 2 ตัว และอ่านค่า offset+pc จากนั้นก็จะส่งไปที่ ALUOut 
               หลังจากนั้นทำการเช็ค register 2 ตัวนี้ว่าเท่ากันมั้ย ถ้าเท่ากันจะส่งให้ ALUOut แต่ถ้าไม่เท่ากันก็ส่งให้ PC แทน
  
#### งานครั้งที่ 6
  * [CLIP6(Youtube)](https://www.youtube.com/watch?v=cTYj0MKnsEo&t=5s)
  
  
  ++ คำอธิบาย : คลิปนี้อธิบายเกี่ยวกับการทำงาน State Machine ของ r-format ใน cpu รูปแบบ Multicycle โดยจะส่วนประกอบของการทำงานจะมีั้ง Fetch, 
               Reg/Dec, Exec, Wr โดยการทำงานจะใช้ MemRead, MemWrite, lorD, IRWrite, ALUSrcA, ALUSrcB, ALUOP, PCWrite, PCSource, RegWrite, 
               MemtoReg และ RegDst ในการทำงาน
  
  #### งานครั้งที่ 7
   * [CLIP7(Youtube)](https://www.youtube.com/watch?v=f5RM9AAuccY)
  
  
  ++ คำอธิบาย : คลิปนี้อธิบายเกี่ยวกับ Pipelining ว่ามันคืออะไร รวมถึงข้อดี ปัญหาของ Pipelining การทำงาน ความแตกต่างของการทำงาน โดย Pipelining 
               เป็นหน่วยความจำที่อ่านคำสั่งต่างๆ จนจบคำสั่งคล้าย Register แต่ต่างกันตรงที่ Pipelining เก็บค่าได้มากกว่า Register แต่ทำงานได้ช้ากว่า Register 
               โดย Pipelining จะทำคำสั่งได้มากกว่า 1 คำสั่ง เพราะใช้หลักการว่าเมื่อกระบวนการทำงานทำงานคำสั่งก่อนหน้า แต่มันมีปัญหาคือคำสั่งมีโอกาสทำกระบวนการ                    เดียวกันเกิน 1 คำสั่ง หรือมีโอกาสที่จะผิดพลาดเมื่อคำสั่งหลังต้องการรับค่าจากคำสั่งก่อนหน้า 
