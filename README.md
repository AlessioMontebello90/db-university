Dopo aver creato un nuovo database nel vostro phpMyAdmin e aver importato lo schema allegato, eseguite le query del file allegato.

# Selezionare tutti gli studenti nati del 1990 (160)

SELECT \*
FROM `students`
WHERE YEAR(`date_of_birth`) = 1990;
