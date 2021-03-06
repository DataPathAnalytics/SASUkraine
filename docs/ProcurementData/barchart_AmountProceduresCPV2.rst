#########################################################
Кількість процедур за місяць по підрозділах класифікатора
#########################################################

**Тип елемента:**
    1.Вартість.
    2.Відсоток.
    
Розрахункова частина
====================

Частота розрахунку:
-------------------
Показники для графіку розраховується кожного разу при перерахунку усіх показників

Дані для розрахунку:
--------------------
- API тендерінгу системи публічних закупівель


- змінна :ref:`v_DateCreated`
- змінна :ref:`v_LastMonth`
- змінна :ref:`v_ProcedureCPV2Name`
- змінна :ref:`v_ExpectedAmount`
- показник :ref:`kpi_ProceduresTotalAmount`

Поля розрахунку:
----------------
- ``data.date``
- ``data.status``

Формула розрахунку:
-------------------
1. Вибираємо очікувані вартості процедур :ref:`v_ExpectedAmount`, що мають у ``data.status`` слово ``active`` та :ref:`v_DateCreated` у яких менше або дорівнює ``v_LastMonthRightMargin``.
2. Вибираємо очікувані вартості процедур :ref:`v_ExpectedAmount`, що мають:
2.1. ``data.status`` дорівнює ``complete``, ``cancelled``, ``unsuccessful``.
2.2. :ref:`v_DateCreated` у яких менше або дорівнює ``v_LastMonthRightMargin`` та ``data.date`` яких більше або дорівнює ``v_LastMonthLeftMargin``.
3. Рахуємо суму очікуваних вартостей процедур :ref:`v_ExpectedAmount`, знайдених у п.1 та п.2 групуючи їх за значеннями змінної змінна :ref:`v_ProcedureCPV2Name`.

Побудова візуалізації
=====================

Загальні дані
-------------

**Назва графіку:** конкатенація рядків -  "Вартість процедур за " + v_LastMonth + "по підгрупах закупівельного словника".

**Тип графіку:** стовпчикова діаграма.

**Підтип:** звичайний.

**Орієнтація:** див. мокап.

**Загальна кількість стовпчиків:** дорівнює кількості унікальних :ref:`v_ProcedureCPV2Name`, що отримані після обчислення.

**Кількість стовпчиків у видимій зоні:** 10.

**Підказка (tooltip):** 
  1) :ref:`v_ProcedureCPV2Name`;
  2) "Вартість процедур: " + Сума з п.3 формули обчислення;
  3) "Відсоток від загальної вартості: " + відсоток від (Суми з п.3 формули обчислення / :ref:`kpi_ProceduresTotalAmount`)

Область графіка
---------------

**Початок координат:**	див. мокап.

**Решітка:**	відсутня.

**Сортування значень:** Сортування за сумою з п.3 формули обчислення. Сортуємо за зниженням.

**Колір стовпчиків:**	див. мокап.

**Колір фона:**	див. мокап.

**Колір границі:**	див. мокап.

**Колір решітки:**	див. мокап.

**Значення на стовпчиках:**	див. мокап.

Вісь показників
---------------

**Початок координат:** див. мокап.

**Кількість показників:**	дорівнює кількості унікальних :ref:`v_ProcedureCPV2Name`, що отримані після обчислення.

**Кількість показників у видимій зоні:** 10.

**Значення від:**	автоматично.

**Значення до:**	автоматично.

**Відсічки:** див. мокап.

**Колір відсічки:** див. мокап.	

**Колір підпису відсічки:** див. мокап.

**Розташування відсічок:**  див. мокап.	

**Підписи відсічок:**	:ref:`v_ProcedureCPV2Name`

**Назва вісі:** "Підрозділ закупівельного словника"

Вісь значень показників
-----------------------

**Значення від:**	автоматично.

**Значення до:**	автоматично.

**Відсічки:** див. мокап.

**Колір відсічки:** див. мокап.	

**Колір підпису відсічки:** див. мокап.

**Розташування відсічок:**  див. мокап.	

**Назва вісі:** "Вартість процедур".

Легенда
-------
**Розташування:** див. мокап.
**Підпис даних:** див. мокап.
**Колір:** див. мокап.
