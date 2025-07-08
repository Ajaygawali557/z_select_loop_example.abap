# z_select_loop_example.abap
REPORT z_select_loop_example.

TABLES: mara.

DATA: lt_materials TYPE TABLE OF mara,
      ls_material  TYPE mara.

SELECT matnr mtart
  FROM mara
  INTO TABLE lt_materials
  UP TO 5 ROWS.

LOOP AT lt_materials INTO ls_material.
  WRITE: / 'Material:', ls_material-matnr,
         'Type:', ls_material-mtart.
ENDLOOP.
