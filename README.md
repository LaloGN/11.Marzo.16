# 11.Marzo.16
### 1. Simulacion de series de tiempo
### Vamos a simular un indicador, para ello necesitamos alguna información
### Valor máximo, mkínimo y el numero de datos

### En este ejemplo vamos a proponer la población en México
### Que el valor mínimo serán 100, max 120, 15 datos que inicie en 2000
pob <- sample(100:120, 15, replace = F)
### La convertimos en serie de tiempo
pobts <- ts (pob, frequency = 1, start = (2000))
plot (pobts)
plot (aggregate(pobts))

### Bajar de INEGI la ocupacion de las personas
### Importar csv
ocu <- ts(read.csv(("F:\\Octavo semestre\\Series de Tiempo\\jackie.csv"), header = F), frequency = 4, start = 2005);
plot (ocu) #Darle formato
plot (aggregate(ocu)) #Darle formato

### Simular tasa de desocupacion con rango 3 a 8, empieza en 2005, que genere 40 datos y va a ser trimestral
### Bajar de INEGI la tasa de desocupacion importar en R y compararlas

### 1. Simluacion
tdesocupados <- sample( 3:8, 44, replace= TRUE)
tdesocupadosts <- ts(tdesocupados, frequency = 4, start = (2005))
plot(tdesocupadosts)
plot(aggregate(tdesocupadosts))

### 2. INEGI
tdesocupa <- ts(read.csv("F:\\Octavo semestre\\Series de Tiempo\\tasadesocupa.csv"), frequency = 4, start = 2005);
plot (tdesocupa) #Darle formato
plot (aggregate(tdesocupa)) #Darle formato

### 3. Comparar
plot( cbind(tdesocupadosts,tdesocupa)) ##Comparar dos graficas juntas
x11() ##muestra una grafica activa
