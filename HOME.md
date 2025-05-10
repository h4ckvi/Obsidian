---
cssclasses: []
status: in progress
---

# 📈 Progresos


```contributionGraph
title: DÍAS ESTUDIADOS
graphType: default
dateRangeValue: 365
dateRangeType: FIXED_DATE_RANGE
startOfWeek: "1"
showCellRuleIndicators: true
titleStyle:
  textAlign: center
  fontSize: 15px
  fontWeight: normal
dataSource:
  type: PAGE
  value: '"000 - DIARIO"'
  dateField:
    format: DD MMMM YYYY
  countField:
    type: PAGE_PROPERTY
    value: estudio
fillTheScreen: true
enableMainContainerShadow: false
fromDate: 2024-01-01
toDate: 2024-12-31
cellStyle:
  minWidth: 20px
  minHeight: 10px
cellStyleRules: []

```


```contributionGraph
title: DÍAS QUE HE IDO AL GYM
graphType: default
dateRangeValue: 365
dateRangeType: FIXED_DATE_RANGE
startOfWeek: "1"
showCellRuleIndicators: true
titleStyle:
  textAlign: center
  fontSize: 15px
  fontWeight: normal
dataSource:
  type: PAGE
  value: '"000 - DIARIO"'
  dateField:
    format: DD MMM YYYY
    type: FILE_CTIME
    value: deporte
  countField:
    type: PAGE_PROPERTY
    value: deporte
fillTheScreen: true
enableMainContainerShadow: false
fromDate: 2024-01-01
toDate: 2024-12-31
mainContainerStyle: {}
cellStyle:
  borderRadius: ""
  minWidth: 20px
  minHeight: 10px
cellStyleRules:
  - id: Halloween_a
    color: "#fdd577"
    min: 1
    max: 2
  - id: Halloween_b
    color: "#faaa53"
    min: 2
    max: 3
  - id: Halloween_c
    color: "#f07c44"
    min: 3
    max: 5
  - id: Halloween_d
    color: "#d94e49"
    min: 5
    max: 9999

```

```contributionGraph
title: DÍAS LEÍDOS
graphType: default
dateRangeValue: 365
dateRangeType: FIXED_DATE_RANGE
startOfWeek: "1"
showCellRuleIndicators: true
titleStyle:
  textAlign: center
  fontSize: 15px
  fontWeight: normal
dataSource:
  type: PAGE
  value: '"000 - DIARIO"'
  dateField:
    type: FILE_CTIME
    value: lectura
    format: DD MMMM YYYYY
  countField:
    type: PAGE_PROPERTY
    value: lectura
fillTheScreen: false
enableMainContainerShadow: false
fromDate: 2024-01-01
toDate: 2024-12-31
cellStyle:
  minWidth: 20px
  minHeight: 10px
cellStyleRules:
  - id: Ocean_a
    color: "#8dd1e2"
    min: 1
    max: 2
  - id: Ocean_b
    color: "#63a1be"
    min: 2
    max: 3
  - id: Ocean_c
    color: "#376d93"
    min: 3
    max: 5
  - id: Ocean_d
    color: "#012f60"
    min: 5
    max: 9999
```

# 🎯Metas y objetivos



# 🛍️ Compras 

> [!multi-column]
> 
>>[!pro] Necesarias
>> 
>> ```dataview
>> task 
>> from "800 - COMPRAS NO FINANCIERAS/necesidades"
>> where !completed
>> ```
> 
>> [!con] Caprichos
>> 
>> ```dataview
>> task 
>> from "800 - COMPRAS NO FINANCIERAS/caprichos"
>> where !completed
>> ```
> 

<br>

# 🗒️Consultas principales

> [!multi-column]
>> [!summary] Notas principales
>> - [[MOC - Learning python]]
>> - [[objetivos para alcanzar la felicidad]]
>> - [[Seguimiento de ejercicios]]
>> - [[Vídeos youtube]]
>> - [[Ideas Posts linkedin]]
>> - [[Proyecto página web]]
>> - [[Vista libros general]]
>> 
> 
>> [!todo] Pendientes de procesar
>> 
>> ```dataview
>> LIST
>> FROM "100 - CAPTURA"
>> WHERE contains(file.tags, "#procesar") or tipo = "captura"
>> ```
> 
---
> [!multi-column]
> > [!summary] Recently Created
>> ```dataview
>> list
>> from ""
>> Sort file.ctime DESC
>> limit 7
>
>> [!Todo] Recently Updated
>> ```dataview
>> list
>> from ""
>> Sort file.mtime DESC
>> limit 7
>>```

# 📚 Librería

![[Vista libros general]]

