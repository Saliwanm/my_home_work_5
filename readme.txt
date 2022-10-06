1. Add values in class_id to table rozklad:

   UPDATE rozklad SET class_id=4 WHERE id=1;
   UPDATE rozklad SET class_id=3 WHERE id=2;
   UPDATE rozklad SET class_id=2 WHERE id=3;
   UPDATE rozklad SET class_id=1 WHERE id=4;

2. Rework this query to work with class_in in rozklad (not at room_class)

   SELECT teachers.first_name, teachers.last_name, lessons.name, rooms.number, rozklad.time FROM rozklad INNER JOIN lessons ON lessons.id=rozklad.lesson_id INNER JOIN teachers ON teachers.id=rozklad.teacher_id INNER JOIN rooms ON rooms.id=rozklad.room_id INNER JOIN classes ON classes.id=rozklad.class_id WHERE time BETWEEN "11:00:00" AND "13:00:00";

Instruction: download file hm5_school.sql and upload in mysql new database
