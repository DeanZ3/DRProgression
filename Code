create table dz3_icd_diag0 as select mrn, enc_timestamp, proc_code, proc_eye, diag1, diag2, diag3, diag4,
case 
    when diag1 like '%E10.%' then 1
    when diag1 like '%E11.%' then 2
    else null end as dm_1,
case
    when diag1 like '%E10.9%' or diag1 like '%E11.9%' then 0
    when diag1 like '%E10.32%' or diag1 like '%E10.32%' then 1
    when diag1 like '%E10.33%' or diag1 like '%E11.33%' then 2
    when diag1 like '%E10.34%' or diag1 like '%E11.34%' then 3
    when diag1 like '%E10.35%' or diag1 like '%E11.35%' then 4
    else null end as dr_1,
case
    when diag1 like '%E10.9%' or diag1 like '%E11.9%' then 0
    when diag1 like '%E10.3_1%' or diag1 like '%E11.3_1%' then 1
    when diag1 like '%E10.3_9%' or diag1 like '%E11.3_9%' then 0
    else null end as dme_1,
case
    when (diag1 not like '%E10.%' and diag1 not like '%E11.%') or length(diag1) != 8 then null
    when substr(diag1, -1) = 1 then 'Right'
    when substr(diag1, -1) = 2 then 'Left'
    when substr(diag1, -1) = 3 then 'Bilateral'
    else null end as eye_side_1,
    
case 
    when diag2 like '%E10.%' then 1
    when diag2 like '%E11.%' then 2
    else null end as dm_2,
case
    when diag2 like '%E10.9%' or diag2 like '%E11.9%' then 0
    when diag2 like '%E10.32%' or diag2 like '%E10.32%' then 1
    when diag2 like '%E10.33%' or diag2 like '%E11.33%' then 2
    when diag2 like '%E10.34%' or diag2 like '%E11.34%' then 3
    when diag2 like '%E10.35%' or diag2 like '%E11.35%' then 4
    else null end as dr_2,
case
    when diag2 like '%E10.9%' or diag2 like '%E11.9%' then 0
    when diag2 like '%E10.3_1%' or diag2 like '%E11.3_1%' then 1
    when diag2 like '%E10.3_9%' or diag2 like '%E11.3_9%' then 0
    else null end as dme_2,
case
    when (diag2 not like '%E10.%' and diag2 not like '%E11.%') or length(diag2) != 8 then null
    when substr(diag2, -1) = 1 then 'Right'
    when substr(diag2, -1) = 2 then 'Left'
    when substr(diag2, -1) = 3 then 'Bilateral'
    else null end as eye_side_2,
    
case 
    when diag3 like '%E10.%' then 1
    when diag3 like '%E11.%' then 2
    else null end as dm_3,
case
    when diag3 like '%E10.9%' or diag3 like '%E11.9%' then 0
    when diag3 like '%E10.32%' or diag3 like '%E10.32%' then 1
    when diag3 like '%E10.33%' or diag3 like '%E11.33%' then 2
    when diag3 like '%E10.34%' or diag3 like '%E11.34%' then 3
    when diag3 like '%E10.35%' or diag3 like '%E11.35%' then 4
    else null end as dr_3,
case
    when diag3 like '%E10.9%' or diag3 like '%E11.9%' then 0
    when diag3 like '%E10.3_1%' or diag3 like '%E11.3_1%' then 1
    when diag3 like '%E10.3_9%' or diag3 like '%E11.3_9%' then 0
    else null end as dme_3,
case
    when (diag3 not like '%E10.%' and diag3 not like '%E11.%') or length(diag3) != 8 then null
    when substr(diag3, -1) = 1 then 'Right'
    when substr(diag3, -1) = 2 then 'Left'
    when substr(diag3, -1) = 3 then 'Bilateral'
    else null end as eye_side_3,
    
case 
    when diag4 like '%E10.%' then 1
    when diag4 like '%E11.%' then 2
    else null end as dm_4,
case
    when diag4 like '%E10.9%' or diag4 like '%E11.9%' then 0
    when diag4 like '%E10.32%' or diag4 like '%E10.32%' then 1
    when diag4 like '%E10.33%' or diag4 like '%E11.33%' then 2
    when diag4 like '%E10.34%' or diag4 like '%E11.34%' then 3
    when diag4 like '%E10.35%' or diag4 like '%E11.35%' then 4
    else null end as dr_4,
case
    when diag4 like '%E10.9%' or diag4 like '%E11.9%' then 0
    when diag4 like '%E10.3_1%' or diag4 like '%E11.3_1%' then 1
    when diag4 like '%E10.3_9%' or diag4 like '%E11.3_9%' then 0
    else null end as dme_4,
case
    when (diag4 not like '%E10.%' and diag4 not like '%E11.%') or length(diag4) != 8 then null
    when substr(diag4, -1) = 1 then 'Right'
    when substr(diag4, -1) = 2 then 'Left'
    when substr(diag4, -1) = 3 then 'Bilateral'
    else null end as eye_side_4
from dz2_icd_codes;

select * from dz3_icd_diag0;
create table dz3_icd_diag as select mrn, enc_timestamp, proc_code, proc_eye, 
    diag1, dm_1, dr_1, dme_1, eye_side_1,
    diag2, dm_2, dr_2, dme_2, eye_side_2,
    diag3, dm_3, dr_3, dme_3, eye_side_3,
    diag4, dm_4, dr_4, dme_4, eye_side_4,
  
case
    when dr_1 = 4 and (eye_side_1 = 'Right' or eye_side_1 = 'Bilateral') then 4
    when dr_1 = 3 and (eye_side_1 = 'Right' or eye_side_1 = 'Bilateral') then 3
    when dr_1 = 2 and (eye_side_1 = 'Right' or eye_side_1 = 'Bilateral') then 2
    when dr_1 = 1 and (eye_side_1 = 'Right' or eye_side_1 = 'Bilateral') then 1
    when dr_1 = 0 then 0
    else null
end as dr1_num_od,    
case
    when dr_1 = 4 and (eye_side_1 = 'Left' or eye_side_1 = 'Bilateral') then 4
    when dr_1 = 3 and (eye_side_1 = 'Left' or eye_side_1 = 'Bilateral') then 3
    when dr_1 = 2 and (eye_side_1 = 'Left' or eye_side_1 = 'Bilateral') then 2
    when dr_1 = 1 and (eye_side_1 = 'Left' or eye_side_1 = 'Bilateral') then 1
    when dr_1 = 0 then 0
    else null
end as dr1_num_os,

case
    when dr_2 = 4 and (eye_side_2 = 'Right' or eye_side_2 = 'Bilateral') then 4
    when dr_2 = 3 and (eye_side_2 = 'Right' or eye_side_2 = 'Bilateral') then 3
    when dr_2 = 2 and (eye_side_2 = 'Right' or eye_side_2 = 'Bilateral') then 2
    when dr_2 = 1 and (eye_side_2 = 'Right' or eye_side_2 = 'Bilateral') then 1
    when dr_2 = 0 then 0
    else null
end as dr2_num_od,    
case
    when dr_2 = 4 and (eye_side_2 = 'Left' or eye_side_2 = 'Bilateral') then 4
    when dr_2 = 3 and (eye_side_2 = 'Left' or eye_side_2 = 'Bilateral') then 3
    when dr_2 = 2 and (eye_side_2 = 'Left' or eye_side_2 = 'Bilateral') then 2
    when dr_2 = 1 and (eye_side_2 = 'Left' or eye_side_2 = 'Bilateral') then 1
    when dr_2 = 0 then 0
    else null
end as dr2_num_os,

case
    when dr_3 = 4 and (eye_side_3 = 'Right' or eye_side_3 = 'Bilateral') then 4
    when dr_3 = 3 and (eye_side_3 = 'Right' or eye_side_3 = 'Bilateral') then 3
    when dr_3 = 2 and (eye_side_3 = 'Right' or eye_side_3 = 'Bilateral') then 2
    when dr_3 = 1 and (eye_side_3 = 'Right' or eye_side_3 = 'Bilateral') then 1
    when dr_3 = 0 then 0
    else null
end as dr3_num_od,    
case
    when dr_3 = 4 and (eye_side_3 = 'Left' or eye_side_3 = 'Bilateral') then 4
    when dr_3 = 3 and (eye_side_3 = 'Left' or eye_side_3= 'Bilateral') then 3
    when dr_3 = 2 and (eye_side_3 = 'Left' or eye_side_3 = 'Bilateral') then 2
    when dr_3 = 1 and (eye_side_3 = 'Left' or eye_side_3 = 'Bilateral') then 1
    when dr_3 = 0 then 0
    else null
end as dr3_num_os,

case
    when dr_4 = 4 and (eye_side_4 = 'Right' or eye_side_4 = 'Bilateral') then 4
    when dr_4 = 3 and (eye_side_4 = 'Right' or eye_side_4 = 'Bilateral') then 3
    when dr_4 = 2 and (eye_side_4 = 'Right' or eye_side_4 = 'Bilateral') then 2
    when dr_4 = 1 and (eye_side_4 = 'Right' or eye_side_4 = 'Bilateral') then 1
    when dr_4 = 0 then 0
    else null
end as dr4_num_od,    
case
    when dr_4 = 4 and (eye_side_4 = 'Left' or eye_side_4 = 'Bilateral') then 4
    when dr_4 = 3 and (eye_side_4 = 'Left' or eye_side_4 = 'Bilateral') then 3
    when dr_4 = 2 and (eye_side_4 = 'Left' or eye_side_4 = 'Bilateral') then 2
    when dr_4 = 1 and (eye_side_4 = 'Left' or eye_side_4 = 'Bilateral') then 1
    when dr_4 = 0 then 0
    else null
end as dr4_num_os,

case
    when dme_1 = 1 and (eye_side_1 = 'Right' or eye_side_1 = 'Bilateral') then 1
    when dme_1 = 0 and (eye_side_1 = 'Right' or eye_side_1 = 'Bilateral') then 0
    else null
end as dme1_num_od,
case
    when dme_1 = 1 and (eye_side_1 = 'Left' or eye_side_1 = 'Bilateral') then 1
    when dme_1 = 0 and (eye_side_1 = 'Left' or eye_side_1 = 'Bilateral') then 0
    else null
end as dme1_num_os,

case
    when dme_2 = 1 and (eye_side_2 = 'Right' or eye_side_2 = 'Bilateral') then 1
    when dme_2 = 0 and (eye_side_2 = 'Right' or eye_side_2 = 'Bilateral') then 0
    else null
end as dme2_num_od,
case
    when dme_2 = 1 and (eye_side_2 = 'Left' or eye_side_2 = 'Bilateral') then 1
    when dme_2 = 0 and (eye_side_2 = 'Left' or eye_side_2 = 'Bilateral') then 0
    else null
end as dme2_num_os,

case
    when dme_3 = 1 and (eye_side_3 = 'Right' or eye_side_3 = 'Bilateral') then 1
    when dme_3 = 0 and (eye_side_3 = 'Right' or eye_side_3 = 'Bilateral') then 0
    else null
end as dme3_num_od,
case
    when dme_3 = 1 and (eye_side_3 = 'Left' or eye_side_3 = 'Bilateral') then 1
    when dme_3 = 0 and (eye_side_3 = 'Left' or eye_side_3 = 'Bilateral') then 0
    else null
end as dme3_num_os,

case
    when dme_4 = 1 and (eye_side_4 = 'Right' or eye_side_4 = 'Bilateral') then 1
    when dme_4 = 0 and (eye_side_4 = 'Right' or eye_side_4 = 'Bilateral') then 0
    else null
end as dme4_num_od,
case
    when dme_4 = 1 and (eye_side_4 = 'Left' or eye_side_4 = 'Bilateral') then 1
    when dme_4 = 0 and (eye_side_4 = 'Left' or eye_side_4 = 'Bilateral') then 0
    else null
end as dme4_num_os

from dz3_icd_diag0;


create table dz3_icd_best_diag as select mrn, enc_timestamp, proc_code, proc_eye, 
    diag1, dm_1, dr_1, dr1_num_od, dr1_num_os, dme_1, dme1_num_od, dme1_num_os, eye_side_1,
    diag2, dm_2, dr_2, dr2_num_od, dr2_num_os, dme_2, dme2_num_od, dme2_num_os, eye_side_2, 
    diag3, dm_3, dr_3, dr3_num_od, dr3_num_os, dme_3, dme3_num_od, dme3_num_os, eye_side_3,
    diag4, dm_4, dr_4, dr4_num_od, dr4_num_os, dme_4, dme4_num_od, dme4_num_os, eye_side_4,
    greatest(nvl(dr1_num_od, -1), nvl(dr2_num_od, -1), nvl(dr3_num_od, -1), nvl(dr4_num_od, -1)) as dr5_num_od,
    greatest(nvl(dr1_num_os, -1), nvl(dr2_num_os, -1), nvl(dr3_num_os, -1), nvl(dr4_num_os, -1)) as dr5_num_os,
    greatest(nvl(dme1_num_od, -1), nvl(dme2_num_od, -1), nvl(dme3_num_od, -1), nvl(dme4_num_od, -1)) as dme5_num_od,
    greatest(nvl(dme1_num_os, -1), nvl(dme2_num_os, -1), nvl(dme3_num_os, -1), nvl(dme4_num_os, -1)) as dme5_num_os
from dz3_icd_diag;
create table dz3_prefull_table as select distinct * from dz3_image_reference a left outer join dz3_icd_best_diag b 
    on a.patient_id = b.mrn
    and trunc(a.studydatetime) = trunc(b.enc_timestamp);

select * from dz3_prefull_table;

create table dz3_grades_helper as select id, patient_id, studydatetime, laterality, dr5_num_od as drgradeod, 
dr5_num_os as drgradeos, dme5_num_od as dmegradeod, dme5_num_os as dmegradeos from dz3_prefull_table;

create table dz3_eye_grades as select id, laterality, drgradeod, drgradeos, dmegradeod, dmegradeos,
case
    when laterality = 'R' then drgradeod
    when laterality = 'L' then drgradeos
    else null
end as eye_dr,
case
    when laterality = 'R' then dmegradeod
    when laterality = 'L' then dmegradeos
    else null
end as eye_dme
from dz3_grades_helper;

create table dz3_eye_grades2 as select distinct id, laterality, max(eye_dr) as eye_dr, max(eye_dme) as eye_dme
from dz3_eye_grades
group by id, laterality;

create table dz3_full_table as select distinct a.*, b.eye_dr, b.eye_dme from dz3_prefull_table a, dz3_eye_grades2 b where a.id = b.id;

create table dz3_imagenumber_helper as select distinct patient_id, laterality, studydatetime, min(imagenumber) as imagenumber
from dz3_full_table where laterality is not null
group by patient_id, laterality, studydatetime;

create table dz3_aiprogsub1 as select distinct a.id, a.patient_id, a.file_path, a.studydatetime, a.laterality, a.imagenumber, a.eye_dr, a.eye_dme from dz3_full_table a, dz3_imagenumber_helper b
    where a.patient_id = b.patient_id and a.laterality = b.laterality
    and trunc(a.studydatetime) = trunc(b.studydatetime) and a.imagenumber = b.imagenumber;
  
/*dz2_aiprogsub2*/
select distinct a.*, b.* from dz3_aiprogsub1 a, dz3_aiprogsub1 b where a.patient_id = b.patient_id and a.laterality = b.laterality;
delete from dz3_aiprogsub2 where (studydatetime_1 - studydatetime <= 0);

update dz3_aiprogsub2
set eye_dr = null
where eye_dr = -1;

update dz3_aiprogsub2
set eye_dme = null
where eye_dme = -1;

drop table dz3_dataset;
create table dz3_dataset as Select distinct id, patient_id, studydatetime, laterality, file_path, imagenumber, eye_dr, eye_dme, id_1, studydatetime_1, laterality_1, file_path_1, imagenumber_1, eye_dr_1, eye_dme_1, case when id > 199706 then 'gs://arvo_2022_abstract/' || id || '.jpeg'
else 'gs://arvo_2022_images/' || id || '.jpeg' end as path, 'Progression' as progression from dz2_aiprogsub2 where eye_dr is not null and eye_dr_1 is not null
and eye_dr_1 > (eye_dr + 1) and (eye_dr = 0 or eye_dr = 1 or eye_dr = 2)

union all

Select distinct id, patient_id, studydatetime, laterality, file_path, imagenumber, eye_dr, eye_dme, id_1, studydatetime_1, laterality_1, file_path_1, imagenumber_1, eye_dr_1, eye_dme_1, case when id > 199706 then 'gs://arvo_2022_abstract/' || id || '.jpeg'
else 'gs://arvo_2022_images/' || id || '.jpeg' end as path, 'NoProgression' as noprogression from dz2_aiprogsub2 where eye_dr is not null and eye_dr_1 is not null
and studydatetime_1 - studydatetime > 3 and eye_dr_1 = eye_dr and (eye_dr = 0 or eye_dr = 1 or eye_dr = 2);

drop table dz2_prog_dates;
create table dz3_prog_dates as select id, id_1, (studydatetime_1 - studydatetime) as studydatetime_diff from dz3_dataset;
drop table dz2_prog_dates2;
create table dz3_prog_dates2 as select distinct id, max(studydatetime_diff) as studydatetime_diff 
from dz3_prog_dates
group by id;
select distinct a.* from dz3_dataset a, dz3_prog_dates2 b where a.id = b.id and (a.studydatetime_1 - a.studydatetime) = b.studydatetime_diff;
select * from dz2_allprogs;

