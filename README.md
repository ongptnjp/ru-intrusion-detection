## This Project made from student of RU, Thailand.
## We have reference from UNSW-NB15 dataset.

>Thank you ME CSE Student, MSS’s College of Engineering & Technology, Jalna (MH) India1

## Reference
1. [Weka Official Document](https://waikato.github.io/weka-wiki/)
2. [How to save model and prediction in Weka](https://machinelearningmastery.com/save-machine-learning-model-make-predictions-weka/)
3. [Document Example](https://www.en.rmutt.ac.th/che/files/Project_2560_compressed_compressed.pdf)
4. [Install Plugin Tree visualization](https://stackoverflow.com/questions/9175116/visualizing-weka-classification-tree/29651241#29651241)

### Attack Catagory Shortly Description
1. Fuzzer 
   > สุ่มค่า input ที่แปลกปลอมในหลากหลายรูปแบบที่อาจจะทำให้ระบบทำงานผิดพลาดได้
2. Analysis
   > เป็นการโจมตีระบบเครือข่ายรูปแบบหนึ่งที่แฮ็คเกอร์จะเลือกเป้าหมายเพียงรายเดียว แล้วมุ่งโจมตีเฉพาะเป้าหมายนั้น โดยอาศัยเทคนิคการโจมตีรูปแบบต่างๆ ผสานกันเพื่อให้ประสบผลสำเร็จ
3. BackDoors
   > รูรั่วของระบบหรือซอฟแวร์ นักพัฒนาระบบจงใจสร้างทิ้งไว้ เพื่อให้ซอฟแวร์คอยส่งข้อมูลจากอุปกรณ์ที่มันติดตั้งอยู่ กลับไปหาโปรแกรมเมอร์ผู้พัฒนา
4. Ddos Attack
   > เป็นเทคนิคการโจมตีแบบ Brute Force ระดับสูงที่อาศัย Botnet หรือเครือข่ายของอุปกรณ์คอมพิวเตอร์ที่ติดมัลแวร์กลายเป็น Zombie และถูกควบคุมตามคำสั่งของแฮ็คเกอร์
5. Generic
   > The generic attack is to hash a huge number of distinct messages until the same hash pops up twice
6. Reconnaissance
   > Reconnaissance is a type of computer attack in which an intruder engages with the targeted system to gather information about vulnerabilities.
7. Shellcode
   > Shellcode is a small piece of code used as the payload in the exploitation of a software vulnerability.
8. Worms
   > A computer worm is a standalone malware computer program that replicates itself in order to spread to other computers.

## Confusion Matrix
>ลองสมมุติว่ากำลังประเมินการทดสอบชนิดใหม่ที่ตรวจคัดกรองโรคชนิดหนึ่ง
>แต่ละคนที่ทดสอบจริง ๆ มีหรือไม่มีโรค
>ผลสอบอาจเป็นบวก คือจัดบุคคลว่ามีโรค หรือเป็นลบ คือจัดบุคคลว่าไม่มีโรค >แต่ผลของแต่ละคนอาจจะไม่เหมือนกับภาวะจริง ๆ

- ดังนั้น จะมีกรณีต่าง ๆ 4 ข้อคือ
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


## Result Algorithm
| Algorithm | Accuracy | ROC Area | TP | FP
| --- | --- | --- | --- | ---
Decision tree | 89.2533% | 0.974 |  0.893 | 0.011
Random forest | 90.146% | 0.977 | 0.901 | 0.010
Naive bayes | 50.6462% | 0.895 | 0.506 | 0.016
K-nearest neighboor | 86.3054% | 0.925 | 0.863 | 0.013


### Initial Memory for weka
java -Xmx6144m -jar weka.jar
