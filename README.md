## กลไกในการสร้าง DFS

__DFS หรือ Depth-First Search__ เป็นอัลกอริทึมการค้นหาทางลึกที่ใช้ในการสำรวจโครงสร้างข้อมูลแบบ graph หรือ tree โดยการเริ่มต้นจากโหนดหนึ่งและพยายามสำรวจน้อยลงในลำดับเดียวกันในทุก ๆ ขั้นตอน จนกระทั่งไม่สามารถทำต่อได้แล้วจึงย้อนกลับไปสำรวจทางอื่น ๆ

__ขั้นตอนในการทำ DFS__

__1. เลือกโหนดเริ่มต้น__ เลือกโหนดใด ๆ เป็นจุดเริ่มต้น

__2. สำรวจโหนดปัจจุบัน__ สำรวจโหนดที่เราเลือกและทำตัวเอง (ทำการประมวลผลหรือทำบางอย่างกับโหนดนั้น)

__3. เลือกโหนดที่เชื่อมต่อ__ เลือกโหนดที่เชื่อมต่อกับโหนดปัจจุบันและยังไม่เคยถูกสำรวจมาก่อน

__4. เรียก DFS สำหรับโหนดที่เลือก__ ทำซ้ำขั้นตอน 2-3 สำหรับโหนดที่เลือก โดยจะทำ DFS สำหรับโหนดนี้

__5. ทำซ้ำขั้นตอน 2-4 จนกว่าทุกๆ โหนดในกราฟจะถูกสำรวจหรือเงื่อนไขหยุดกำหนดไว้__ ทำ DFS สำหรับโหนดทุก ๆ โหนดที่ยังไม่เคยถูกสำรวจ



https://github.com/srpp0717/AI/assets/148683906/25f911f8-4c87-4389-b091-c1b4d9d30992



---

## กลไกในการสร้าง BFS

__BFS หรือ Breadth-First Search__ เป็นอัลกอริทึมการค้นหาทางกว้างที่ใช้ในการสำรวจโครงสร้างข้อมูลแบบ graph หรือ tree โดยเริ่มต้นจากจุดเริ่มต้นและสำรวจทุก ๆ โหนดในระดับเดียวกันก่อนที่จะขยับลงไปสู่ระดับถัดไป จนกระทั่งพบโหนดที่ต้องการหรือสำรวจทุก ๆ โหนดใน graph หรือ tree ทั้งหมดเป็นไปตามลำดับที่ถูกกำหนดไว้

__ขั้นตอนในการทำ BFS__

__1. เริ่มต้นที่จุดเริ่มต้น (start node)__ เริ่มต้นที่จุดเริ่มต้นและเพิ่มลงในคิว (queue) หรือโครงสร้างข้อมูลที่ใช้เก็บโหนดที่ต้องการสำรวจในขั้นตอนถัดไป

__2. สำรวจโหนดในระดับปัจจุบัน__ นำโหนดที่อยู่บนด้านหน้าของคิวมาตรวจสอบ และเพิ่มโหนดที่เชื่อมต่ออยู่กับโหนดนั้นลงในคิว

__3. ลบโหนดที่ถูกสำรวจออกจากคิว__ เนื่องจากเราได้ตรวจสอบโหนดนั้นในระดับปัจจุบันแล้ว

__4. ทำซ้ำขั้นตอน 2-3 จนกว่าคิวจะว่าง__ ทำซ้ำขั้นตอนการสำรวจโหนดในระดับปัจจุบันและเพิ่มโหนดที่เชื่อมต่อลงในคิว จนกว่าคิวจะว่าง

__5. เมื่อสำรวจทุกๆ โหนดที่เป็นไปได้ในระดับปัจจุบันแล้ว__ ขยับไปสู่ระดับถัดไปโดยเพิ่มลงในคิว

__6. ทำซ้ำขั้นตอน 2-5 จนกว่าคิวจะเป็น empty__ ทำการสำรวจทุกๆ โหนดใน graph หรือ tree



https://github.com/srpp0717/AI/assets/148683906/535f4d3f-f552-4669-91f0-eeb59479efd5



---

## กลไกในการสร้าง UCS

__UCS หรือ Uniform Cost Search__ เป็นอัลกอริทึมการค้นหาทางที่ใช้ในกราฟที่มีน้ำหนักบนเส้นทางระหว่างโหนด ซึ่งใช้เพื่อหาเส้นทางที่มีค่าที่ต่ำที่สุด (uniform cost) จากจุดเริ่มต้นไปยังจุดปลายปลายหรือเป้าหมาย

__ขั้นตอนในการทำ UCS__

__1. เริ่มต้นที่จุดเริ่มต้น (start node)__ เริ่มต้นที่จุดเริ่มต้นและกำหนดค่าความท้าทาย (cost) เริ่มต้นเป็น 0

__2. เก็บข้อมูลโครงสร้างข้อมูลที่จะใช้ในการค้นหา__ UCS ใช้ priority queue เพื่อเก็บโหนดที่ต้องการสำรวจ โดยจะเรียงโหนดตามค่าความท้าทายที่มีลำดับต่ำที่สุดขึ้นก่อน

__3. สำรวจโหนดที่มีความท้าทายน้อยที่สุด__ นำโหนดที่มีค่าความท้าทายน้อยที่สุดออกจาก priority queue เพื่อสำรวจ

__4. ทำซ้ำขั้นตอนที่ 3 จนกระทั่งเจอจุดปลายหรือเป้าหมาย__ ทำการสำรวจโหนดที่มีความท้าทายน้อยที่สุด และเพิ่มโหนดที่เชื่อมโยงกับโหนดนั้นลงใน priority queue

__5. ตรวจสอบจุดปลายหรือเป้าหมาย__ ตรวจสอบว่าโหนดที่ถูกสำรวจในขั้นตอนที่ 3 เป็นจุดปลายหรือไม่ ถ้าเป็นจุดปลายหรือเป้าหมาย จะสามารถหยุดการค้นหาได้

__6. ทำซ้ำขั้นตอน 3-5 จนกว่า priority queue จะเป็น empty__ ทำการสำรวจโหนดต่างๆ และเพิ่มโหนดที่เชื่อมโยงลงใน priority queue ไปเรื่อยๆ จนกว่าจะถึงจุดปลายหรือเป้าหมาย



https://github.com/srpp0717/AI/assets/148683906/a20e30e6-a6e6-4318-9a23-27462f66ef52



