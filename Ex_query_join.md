## QUERY JOIN

```sql
-- 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
SELECT `students`.`name`, `students`.`surname`, `degrees`.`name` AS "corso_di_laurea" FROM `students` INNER JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id` WHERE `degrees`.`name` = "Corso di Laurea in Economia";

-- 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
SELECT `degrees`.`name`, `degrees`.`level`, `departments`.`name` AS "dipartimento" FROM `degrees` INNER JOIN `departments` ON `departments`.`id` = `degrees`.`department_id` WHERE `degrees`.`level` = "magistrale" AND `departments`.`name` = "Dipartimento di Neuroscienze";

-- 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
SELECT `teachers`.`name`, `teachers`.`surname`, `courses`.`name` AS "corso" FROM `teachers` INNER JOIN `course_teacher` ON `teachers`.`id` = `course_teacher`.`teacher_id` INNER JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id` WHERE `teachers`.`id` = 44;

-- 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cuisono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
SELECT `students`.name, `students`.`surname`, `degrees`.`name` AS "corso_di_laurea", `departments`.`name` AS "dipartimento" FROM `students` INNER JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id` INNER JOIN `departments` ON `degrees`.`department_id` = `departments`.`id` ORDER BY `students`.`surname` ASC

-- 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
SELECT `degrees`.`name` AS "corso_di_laurea", `courses`.`name` AS "corso", `teachers`.`name` AS "nome_insegnante", `teachers`.`surname` AS "cognome_insegnante" FROM `course_teacher` INNER JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id` INNER JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id` INNER JOIN `degrees` ON `degrees`.`id` = `courses`.`degree_id`;

-- 6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
SELECT `teachers`.`name` AS "nome_insegnante", `teachers`.`surname` AS "cognome_insegnante", `departments`.`name` AS "dipartimento" FROM `course_teacher` INNER JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id` INNER JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id` INNER JOIN `degrees` ON `degrees`.`id` = `courses`.`degree_id` INNER JOIN `departments` ON `departments`.`id` = `degrees`.`department_id` WHERE `departments`.`name` = "Dipartimento di Matematica";









```
