## This Project made from student of RU, Thailand.
## We have reference from UNSW-NB15 dataset.

>Thank you ME CSE Student, MSS’s College of Engineering & Technology, Jalna (MH) India1

## Confusion Matrix
ลองสมมุติว่ากำลังประเมินการทดสอบชนิดใหม่ที่ตรวจคัดกรองโรคชนิดหนึ่ง
แต่ละคนที่ทดสอบจริง ๆ มีหรือไม่มีโรค
ผลสอบอาจเป็นบวก คือจัดบุคคลว่ามีโรค หรือเป็นลบ คือจัดบุคคลว่าไม่มีโรค แต่ผลของแต่ละคนอาจจะไม่เหมือนกับภาวะจริง ๆ 
ดังนั้น จะมีกรณีต่าง ๆ 4 อย่าง คือ
1. ผลบวกจริง **(true positive)** ผู้ป่วยตรวจพบว่า**มีโรคอย่างถูกต้อง**
2. ผลบวกปลอม **(false positive)** คนปกติตรวจพบว่า**มีโรคอย่างไม่ถูกต้อง**
3. ผลลบจริง **(true negative)** คนปกติตรวจพบว่า**ไม่มีโรคอย่างถูกต้อง**
4. ผลลบปลอม **(false negative)** คนป่วยตรวจพบว่า**ไม่มีโรคอย่างไม่ถูกต้อง**

> โดยทั่วไป Positive = identified และ negative = rejected ดังนั้น

1. True positive = correctly identified
2. False positive = incorrectly identified
3. True negative = correctly rejected
4. False negative = incorrectly rejected

``` ACC = (TP + TN)/(TP + TN + FP + FN) ```

## ROC
**ROC curve เกิดจากการ plot ระหว่างแกน x และ y โดยที่แกน**
- x คือ false positive rate หรือ 1-specificity
- y คือ true positive rate หรือ sensitivity

> การปรับเปลี่ยน cut-off value นี้จะทำให้เกิดการแลกเปลี่ยน
หรือ trade-off ระหว่าง sensitivity และ specificity
รวมถึงเปลี่ยนแปลง diagnostic accuracy ของ test นั้นๆ
ถ้าเราเพิ่ม test sensitivity เช่น ลดระดับ FBS ที่วินิจฉัยคนเป็นเบาหวานลง
จาก 126 เหลือ 120 ก็จะมีคนเป็นเบาหวานเพิ่มขึ้น
แต่อาจจะได้คนที่เป็นเบาหวานปลอมเยอะขึ้นด้วยเช่นกัน
แบบนี้คือเราเพิ่ม sensitivity แต่ลด specificity
คล้ายๆ กับเหตุการณ์ที่พึ่งเกิดขึ้นกับ guideline hypertension
ที่มีการลดเกณฑ์วินิจฉัยจากเดิม 140/90 มาเป็น 130/80
เป็นการเพิ่ม sensitivity แต่ลด specificity
>
> ในขณะเดียวกันถ้าเราเพิ่มเกณฑ์เบาหวานจาก 126 เป็น 130
แบบนี้คนเป็นเบาหวานก็จะลดลง
แต่จะพลาดการวินิจฉัยคนที่เป็นเบาหวานจริงไปบางคน 
จึงเป็นการเพิ่ม specificity แต่ลด sensitivity



### Initial Memory for weka
java -Xmx6144m -jar weka.jar