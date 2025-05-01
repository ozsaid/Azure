קישור להדגמות וידאו של כל המעבדות :
https://mslabs.cloudguides.com/guides/AZ-104%20Exam%20Guide%20-%20Microsoft%20Azure%20Administrator

#### נושאים שעברנו עליהם :

##### מודול 2 :

- AZURE POLICIES
- AZURE RBAC
קישור לחומר הלימוד :
https://learn.microsoft.com/en-us/training/modules/sovereignty-policy-initiatives/

https://learn.microsoft.com/en-us/training/modules/secure-azure-resources-with-rbac/
##### מודול 8 : AZURE VM

קישור לחומר לימוד :
https://learn.microsoft.com/en-us/training/modules/intro-to-azure-virtual-machines/

https://learn.microsoft.com/en-us/training/modules/configure-virtual-machine-availability/
##### מודול 7 : AZURE STORAGE ACCOUNTS

קישור לחומר לימוד :
https://learn.microsoft.com/en-us/training/paths/az-104-manage-storage/


#### נושא : AZURE POLICIES 
#### דגשים :

להבין את ההיררכיה 
https://learn.microsoft.com/en-us/training/modules/sovereignty-policy-initiatives/media/azure-governance-hierarchy.png

לדעת שיש אפשרות להחיל את המדיניות אחרי שנוצר המשאב או לפני ומה ההשלכות של כל פעולה כזו
https://learn.microsoft.com/en-us/training/modules/sovereignty-policy-initiatives/media/operation-flows.png

<p align="right"><font color="#6425d0">מה ההבדל בין POLICY ל INITATIVE :     </font></p>
<p align="right">POLICY - מכיל אוסף של INITATIVE</p>
המטרה לאגד אוסף של הגדרות על מנת להקל על ניהול המדיניות , בצורה כזו אנו יכולים ליצור אוסף של הגדרות מדיניות ולהחיל אותו בסקופ הרלוונטי במקום להחיל 10 POLICY שונים לדוגמא

אפשר להשתמש בהגדרות BUILT IN או לצור הגדרות משלנו 

להבין שאפשר להוציא מהכלל משאבים מסויימים שעליהן לא תחול המדיניות

אחד החוזקות של POLICY היא היכולת שלה לבצע REMEDIATIONS - כלומר לבצע יישור קו למשאבים בהתאם לפוליסי . <p align="right"></p>
לדוגמא אם יש מדיניות שמחייבת TAG מסויים והמשאב לא מכיל את ה TAG - ניתן ליצור משימה שתעבור על המדיניות ותבצע שינוי לפי תזמון מסויים . בצורה כזו נבטיח שכל המשאבים שלנו עומדים במדיניות

**כל כמה זמן נבדקת המדיניות** : 
https://learn.microsoft.com/en-us/training/modules/sovereignty-policy-initiatives/azure-policies-evaluation-resources
 <p align="right"></p>
##### קישור ל DEMO נוסף  :

https://mslearn.cloudguides.com/en-us/guides/AZ-900%20Exam%20Guide%20-%20Azure%20Fundamentals%20Exercise%2015

https://mslearn.cloudguides.com/en-us/guides/AZ-900%20Exam%20Guide%20-%20Azure%20Fundamentals%20Exercise%2017

https://mslabs.cloudguides.com/guides/AZ-104%20Exam%20Guide%20-%20Microsoft%20Azure%20Administrator%20Exercise%203



#### נושא :ניהול ROLES -  
##### מה זה RBAC 
https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-setup-guide/manage-access

https://learn.microsoft.com/en-us/azure/role-based-access-control/overview

https://learn.microsoft.com/en-us/training/modules/secure-azure-resources-with-rbac/2-rbac-overview

להבין את ההבדל בין ROLES שקשורים ל AZURE ובין אלה שקשורים ל ENTRAID

![image](https://github.com/user-attachments/assets/668c22fb-dcf1-4502-a20d-d9bf3d1a7770)

https://mslearn.cloudguides.com/en-us/guides/AZ-900%20Exam%20Guide%20-%20Azure%20Fundamentals%20Exercise%2014
https://mslabs.cloudguides.com/guides/AZ-104%20Exam%20Guide%20-%20Microsoft%20Azure%20Administrator%20Exercise%202

#### נושא : ניהול מכונות וירטואליות - מודול 8

חומר לימוד :
https://learn.microsoft.com/en-us/training/modules/intro-to-azure-virtual-machines/
https://learn.microsoft.com/en-us/training/modules/configure-virtual-machine-availability/

#### דגשים חשובים :

להבין מה זה זמינות 
https://learn.microsoft.com/en-us/training/modules/intro-to-azure-virtual-machines/5-high-availability


בספר ששלחתי לכם בפרק 7 יש הסבר מפורט בנושא מומלץ לקרוא 
https://marketingassets.microsoft.com/gdc/2014519/original


להבין מה SAAS PAAS IAAS - צירפתי הסבר בעברית 

להכיר את מודל האחריות המשותף בענן 
https://learn.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility


כשאנו מקימים מכונה יש לנו אפשרות להגדיל את היתירות (redundancy) בכמה דרכים :

##### **דרך אחת :  availability sets :**   
https://learn.microsoft.com/en-us/training/modules/configure-virtual-machine-availability/3-setup-availability-sets
דרך פשוטה לקבץ מספר מכונות שמבצעות את אותה פעולה כאוסף לוגי של מכונות . הרעיון להבטיח שהמכונות יפוזרו בצורה שווה בין שרתים פיזיים באותו DATA CENTER בו הן נמצאות.
מה שנשיג בצורה זו הוא שבמקרה של נפילה של שרת פיזי לא יפלו לנו כל המכונות . כמו כן באמצעות UPDATE DOMAIN נוכל להבטיח שהמכונות לא יבצעו עדכון באותו זמן .

הסבר על FAULT DOMAIN ו UPDATE DOMAIN - מתוך חומר הלימוד 
https://learn.microsoft.com/en-us/training/modules/configure-virtual-machine-availability/4-review-update-fault-domains



 
##### **דרך שניה : Availability Zones**  

 אם אנחנו רוצים לקבל יתירות גבוהה יותר אנו יכולים לפזר את המכונות שלנו על כמה DATA CENTERS וכך להבטיח המשכיות גם אם ייפול DATACENTER שלם ב REGION שבחרנו 
 https://learn.microsoft.com/en-us/training/modules/configure-virtual-machine-availability/5-review-availability-zones
![image](https://github.com/user-attachments/assets/30c7530c-e574-4bee-b58c-742dcef7587d)


##### **דרך שלישית  :SCALESET** 

להבין קודם מה זה SCALE (מדרג) בפשטות - יכולת הגידול של המכונה 
יש אפשרות לבצע SCALE UP או SCALE DOWN שזה להוסיף או להוריד משאבים מאותה מכונה . לדוגמא להוסיף זיכרון או להגדיל את כוח העיבוד ומהירות הדיסקים . אפשר לבצע את זה ע"י שינוי גודל המכונה. לקחת בחשבון שמצריך אתחול מחדש.

אפשרות שניה היא  _scale out and scale in_ היכולת להוסיף כח עיבוד באמצעות הוספת מכונות נוספות או הסרה שלהן .

קישור בספר : 
https://learn.microsoft.com/en-us/training/modules/configure-virtual-machine-availability/6-compare-vertical-horizontal-scaling

אחד היכולות החזקות ב AZURE זו היכולת לבצע AUTO SCALE . אנחנו יכולים לצור מכונה ומראש להגדיר את יכולת הגידול שלה ולהגדיר את הכלל שיגרום למכונה לגדול . מה שנקבל בצורה הזו שבזמן עומס יתווספו מכונות ויהיה לי כוח עיבוד זמין ובזמן שאין עומס יימחקו המכונות שאין בהן צורך

פרק 9 בספר ששלחתי לכם מסביר על הנושא 
https://marketingassets.microsoft.com/gdc/2014519/original

![image](https://github.com/user-attachments/assets/4b8783c9-13c2-4a31-8e8e-3c069504a9d1)
