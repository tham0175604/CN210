# รายงานวิชา CN210

### สรุปเนื้อหา
วิชาสถาปัตยกรรมคอมพิวเตอร์ เรียนรู้การทำงานของ CPU MIPS โดย MIPS ซึ่งเป็นหน่วยประมวลผล 32 bits ออกแบบโดยบริษัท MIPS มี 3 รูปแบบ 
คือ R-Format ใช้คำนวณค่า เช่น บวก ลบ ,I-Format ใช้อ่านค่าและเก็บค่า และ J-Format ใช้กระโดดข้ามไปใช้คำสั่งที่ตำแหน่งอื่นๆ ซึ่ง cpu จะทำงานคำสั่งเป็นขั้นตอน คำสั่งที่เจอส่วนใหญ่จะเป็น add sub and or beq jump lw sw slt โดยจะมีรูปแบบการทำงานแบบ Single Cycle, Multicycle และ Pipelining โดย Pipelining จะทำงานเร็วที่สุดแต่ต้องเขียนการทำงานของคำสั่งทุกคำสั่งจนจบ ส่วน Multicycle จะเร็วรองลงมา และ Single Cycle จะช้าที่สุด หากทำคำสั่งที่เยอะมากๆ จะเห็นผลชัดเจน

#### งานครั้งที่ 1
  ![](Clip1.png)

  * [CLIP1(Youtube)](https://www.youtube.com/watch?v=9prW90Cxy1k)
    
  ** คำอธิบาย : คลิปนี้จะอธิบายเกี่ยวกับ MIPs โดย MIPS เป็นหน่วยประมวลผลที่มีความจำ 32 bits ออกแบบโดยบริษัท MIPS มี 3 รูปแบบ คือ R-Format,I-Format และ
               J-Format ซึ่งจะสาธิตการใช้ MIPS ในการคำนวณซึ่งจะใช้ R-Format ในการเก็บค่า ซึ่งฟังก์ชั่นในการคำนวณที่สาธิตคือ ฟังก์ชัน add ซึ่ง R-Format จะประกอบ
               ด้วย op rs rt rd shamt func โดย op มีไว้บอกว่าเป็น R-type หรือ I-type rs rt rd ใช้บอกว่าเก็บค่าไว้ Register ตัวไหน shamt ใช้บอกว่าจะ 
               shift ไปทางไหน func ใช้บอกว่าจะทำคำสั่งอะไร
               
#### งานครั้งที่ 2

  ![](Clip2.png)
  
  * [CLIP2(Youtube)](https://www.youtube.com/watch?v=f3IktFSWI3Y)
  
  ** คำอธิบาย : คลิปนี้จะอธิบายเกี่ยวับการทำงานของ cpu โดยการทำงานจะเริ่มต้นเมื่อเปิดสวิซท์ จากนั้นมันจะอ่านคำสั่งที่ตำแหน่ง 0 แล้วทำงาน ไม่ว่าจะเป็นการ jump คำสั่ง 
               add คำสั่ง load คำสั่ง store ทุกอย่างจะรันเป็นขั้นเป็นตอนตามรูป I-Format หรือ R-Format หรือ J-Format ขึ้นอยู่กับ opcode ของคำสั่ง
  
#### งานครั้งที่ 3

  ![](Clip3.png)
  
  * [CLIP3(Youtube)](https://www.youtube.com/watch?v=BW_B_ZATatA)
  
  ** คำอธิบาย : คลิปนี้จะอธิบายเกี่ยวกับความแตกต่างระหว่าง Single Cycle กับ Multicycle โดยที่เห็นได้ชัดคือ รอบการทำงานของ Multicycle จะมากกว่า Single 
               Cycle จะมีรูปแบบสถาปัตยกรรมที่ต่างกัน Multicycle จะมี ALU น้อยกว่า Single Cycle แต่จะมี Mux มากกว่า Single Cycle และที่เห็นได้ชัดเจนที่สุดคือ 
               Multicycle จะใช้เวลาในการทำคำสั่งน้อยกว่า Single Cycle
  
#### งานครั้งที่ 4

  ![](Clip4.png)
  
  * [CLIP4(Youtube)](https://www.youtube.com/watch?v=nuxHZJcRDfg)
  
  ** คำอธิบาย : คลิปนี้จะอธิบายเกี่ยวกับการทำงานของคำสั่ง Load Word ในรูปแบบ Multicycle โดยเริ่มต้นจากการ Fetch จะเป็นการส่งค่าให้ register และส่งค่าให้ ALU 
               เพื่อ +4 และพร้อมทำขั้นตอนต่อไป เสร็จแล้วก็ทำการ Fetch+1 เพื่อเก็บค่าเข้า register 2 ตัว และส่งเข้าไปที่ ALUOut หลังจากนั้นทำการ Mem1 เป็นการส่ง
               ค่าจาก Register เข้า ALU เพื่อทำคำสั่งแล้วส่งให้ ALUOut หลังจากนั้นก็ส่งเข้า Memory data register
  
#### งานครั้งที่ 5
  
  ![](Clip5.png)
  
  * [CLIP5(Youtube)](https://www.youtube.com/watch?v=deR_ZT8uqBw&t=15s)
  
  ** คำอธิบาย : คลิปนี้จะอธิบายเกี่ยวกับการทำงานของคำสั่ง Branch On Equal ในรูปแบบ Multicycle โดยจะเริ่มต้นจากการ Fetch จะเป็นการส่งค่าให้ register และส่งค่า
               ให้ ALU เพื่อ +4 และพร้อมทำขั้นตอนต่อไป เสร็จแล้วก็ทำการถอดรหัสเพื่อเก็บค่าเข้า register 2 ตัว และอ่านค่า offset+pc จากนั้นส่งเข้าไปที่ ALUOut 
               หลังจากนั้นทำการเช็ค register 2 ตัวนี้ว่าเท่ากันมั้ย ถ้าเท่ากันจะส่งให้ ALUOut แต่ถ้าไม่เท่ากันจะส่งให้ PC
  
#### งานครั้งที่ 6

  ![](Clip6.png)
  
  * [CLIP6(Youtube)](https://www.youtube.com/watch?v=cTYj0MKnsEo&t=5s)
  
  ** คำอธิบาย : คลิปนี้จะอธิบายเกี่ยวกับการทำงาน State Machine ของ r-format ใน cpu รูปแบบ Multicycle โดยจะส่วนประกอบของการทำงานจะมีั้ง Fetch, 
               Reg/Dec, Exec, Wr โดยการทำงานจะใช้ MemRead, MemWrite, lorD, IRWrite, ALUSrcA, ALUSrcB, ALUOP, PCWrite, PCSource, RegWrite, 
               MemtoReg และ RegDst ในการทำงาน
  
  #### งานครั้งที่ 7
 
  ![](Clip7.jpg)
  
   * [CLIP7(Youtube)](https://www.youtube.com/watch?v=f5RM9AAuccY)
  
  ** คำอธิบาย : คลิปนี้จะอธิบายเกี่ยวกับ Pipelining ว่ามันคืออะไร มีองค์ประกอบอะไร ข้อดี ปัญหาของ Pipelining การทำงาน ความแตกต่างของการทำงาน
               โดย Pipelining เป็นหน่วยความจำที่อ่านคำสั่งต่างๆ ผ่านกระบวนการต่างๆ จนจบคำสั่งคล้าย Register แต่ต่างที่ Pipelining เก็บค่าได้มากกว่า Register 
               แต่ทำงานช้ากว่า Register โดย Pipelining จะสามารถทำคำสั่งได้มากกว่า 1 คำสั่งเพราะใช้หลักการแบบเมื่อกระบวนการทำงานทำงานคำสั่งก่อนหน้า จะ
               สามารถทำงานคำสั่งต่อไปได้ แต่มันมีปัญหาคือคำสั่งมีโอกาสทำกระบวนการเดียวกันเกิน 1 คำสั่ง หรือมีโอกาสที่จะผิดพลาดเมื่อคำสั่งหลังต้องการรับค่าจากคำสั่งก่อน
               หน้า แต่คำสั่งก่อนหน้ายังไม่เสร็จ ซึ่งวิธีแก้ปัญหามี 4 อย่างคือ Waiting Forwarding Load-Forwarding และ Reordering
