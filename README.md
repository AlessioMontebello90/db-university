Dopo aver creato un nuovo database nel vostro phpMyAdmin e aver importato lo schema allegato, eseguite le query del file allegato.

# 1) Selezionare tutti gli studenti nati del 1990 (160)

SELECT \*
FROM `students`
WHERE YEAR(`date_of_birth`) = 1990;

# 2) Selezionare tutti i corsi che valgono più di 10 crediti (479)

SELECT \*
FROM `courses`
WHERE `cfu` > 10;

# 3) Selezionare tutti gli studenti che hanno più di 30 anni

FROM `students`
WHERE `date_of_birth` <= DATE_SUB(CURRENT_DATE(), INTERVAL 30 year)
ORDER BY `date_of_birth` DESC;

# 4) Selezionare tutti i corsi del primo semestre del primo anno di un qalsiasi corso di laure (286)

SELECT \*
FROM `courses`
WHERE `period` = 'I semestre' AND `year` = '1';

# 5) Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo 14 ore) del 20/06/2020 (21)

SELECT \*
FROM `exams`
WHERE `date` = '2020-06-20' AND `hour` > '14:00:00';

# 6) Selezionare tutti i corsi di laurea magistrale (38)

SELECT \*
FROM `degrees`
WHERE `level` = 'magistrale';

# 7) Da quanti dipartimenti è composta l'università? (12)

SELECT COUNT(\*) AS 'numero dipartimenti'
FROM `departments`;

# 8) Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

SELECT COUNT(\*) AS 'insegnanti senza numero di telefono'
FROM `teachers`
WHERE `phone` IS null;
