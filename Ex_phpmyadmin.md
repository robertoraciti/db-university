## QUERY 1

```sql
-- Selezionare tutti gli studenti nati nel 1990(160)
SELECT * FROM `students` WHERE `date_of_birth` LIKE "1990-%";

-- Selezionare tutti i corsi che valgono più di 10 crediti(479)
SELECT * FROM `courses` WHERE`cfu` > 10;

-- Selezionare tutti gli studenti che hanno più di 30 anni
SELECT * FROM `students` WHERE `date_of_birth` <= "1993-10-09";

-- Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea(286)
SELECT * FROM `courses` WHERE `period` = "I semestre" AND `year` = 1;


```
