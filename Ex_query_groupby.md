## QUERY GROUP BY

```sql
-- 1. Contare quanti iscritti ci sono stati ogni anno
SELECT COUNT(YEAR(`enrolment_date`)) AS "numero_iscritti" , YEAR(`enrolment_date`)AS "anno" FROM `students` GROUP BY YEAR(`enrolment_date`);

-- 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio
SELECT COUNT(`office_number`) AS "insegnanti", `office_number` FROM `teachers` GROUP BY `office_number`;

-- 3. Calcolare la media dei voti di ogni appello d'esame
SELECT `exam_id` AS "appello", AVG(`vote`) AS "media_voto" FROM `exam_student` GROUP BY `exam_id`;

-- 4. Contare quanti corsi di laurea ci sono per ogni dipartimento
SELECT COUNT(`department_id`) AS "corsi_per_dipartimento" FROM `degrees` GROUP BY `department_id`;
```
