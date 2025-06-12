Vamos a resolver el **Ejercicio 1** paso a paso:

---

### **Datos iniciales**

* **Subredes necesarias:** 44
* **Dirección de red:** 192.168.10.0/24
* **Clase:** C → máscara por defecto: **/24** o **255.255.255.0**

---

## ✅ Resolución paso a paso

---

### **a) ¿Cuántos bits son necesarios para las subredes que se piden?**

Queremos al menos **44 subredes**, así que usamos la fórmula:

$$
2^n \geq 44 \Rightarrow n = 6 \quad \text{(porque } 2^6 = 64 \text{)}
$$

✅ **Respuesta: Se necesitan 6 bits para las subredes.**

---

### **b) ¿Cuál es la máscara de las subredes?**

La máscara base es **/24**, y le añadimos 6 bits → nos pasamos al siguiente octeto:

$$
24 + 6 = 30 \Rightarrow \text{Máscara: } /30
$$

**Equivalente en decimal:**

* **/30 = 255.255.255.252**

✅ **Respuesta: /30 o 255.255.255.252**

---

### **c) ¿Cuáles son las direcciones de todas las subredes?**

Una **/30** tiene un **salto de 4 direcciones** (porque `256 - 252 = 4`) y permite:

$$
2^2 = 4 \text{ direcciones por subred}:
- 1 red
- 2 hosts válidos
- 1 broadcast
$$

Así que podemos obtener 64 subredes dentro de una red /24 (256 / 4 = 64 bloques), de las cuales **usaremos las 44 primeras**.

**Lista de direcciones de subredes** (mostramos las primeras 5 como ejemplo):

| Subred | Dirección de subred | Rango de IPs válidas          | Broadcast     |
| ------ | ------------------- | ----------------------------- | ------------- |
| 1      | 192.168.10.0/30     | 192.168.10.1 – 192.168.10.2   | 192.168.10.3  |
| 2      | 192.168.10.4/30     | 192.168.10.5 – 192.168.10.6   | 192.168.10.7  |
| 3      | 192.168.10.8/30     | 192.168.10.9 – 192.168.10.10  | 192.168.10.11 |
| 4      | 192.168.10.12/30    | 192.168.10.13 – 192.168.10.14 | 192.168.10.15 |
| 5      | 192.168.10.16/30    | 192.168.10.17 – 192.168.10.18 | 192.168.10.19 |

✅ Así hasta llegar a la subred número 44:

* Dirección: **192.168.10.172/30**
* IPs válidas: **192.168.10.173 – 192.168.10.174**
* Broadcast: **192.168.10.175**

---

### ✅ Resumen general

| Ítem                       | Resultado                   |
| -------------------------- | --------------------------- |
| a) Bits necesarios         | 6 bits                      |
| b) Máscara                 | /30 o 255.255.255.252       |
| c) Dirección de subred 1   | 192.168.10.0/30             |
| d) Rango válido (subred 1) | 192.168.10.1 – 192.168.10.2 |
| e) Broadcast (subred 1)    | 192.168.10.3                |

Vamos a resolver paso a paso el ejercicio 2 propuesto:

---

### ✅ **Datos del enunciado**

* Red base: `192.168.10.0/24`
* Clase: **C** → Máscara base `255.255.255.0`
* Subredes necesarias: **14**

---

### 🔹 a) ¿Cuántos bits son necesarios para las subredes?

Necesitamos saber cuántos bits de **host** vamos a "pedir prestados" para crear **al menos 14 subredes**.

**Fórmula:**

$$
2^n \geq \text{número de subredes necesarias}
$$

Buscamos el menor `n` tal que:

* $2^2 = 4$
* $2^3 = 8$
* $2^4 = 16$ ✅ (cumple, ya que 16 ≥ 14)

➡️ **Se necesitan 4 bits para subredes**

---

### 🔹 b) ¿Cuál es la nueva máscara de subred?

Tenemos una red de clase C, cuyo prefijo inicial es **/24**.
Si tomamos 4 bits prestados a los **8 bits disponibles para host**, la nueva máscara es:

$$
/24 + 4 = /28
$$

➡️ **Máscara: 255.255.255.240**

---

### 🔹 c) Direcciones de todas las subredes

Con 4 bits de subred, tenemos $2^4 = 16$ subredes.
Cada subred tiene:

$$
2^{(32 - 28)} = 2^4 = 16 \text{ direcciones} (incluyendo red y broadcast)
$$

Así que, **cada subred avanza de 16 en 16**.

| Subred | Dirección de red | Primera IP válida | Última IP válida | Broadcast      |
| ------ | ---------------- | ----------------- | ---------------- | -------------- |
| 0      | 192.168.10.0     | 192.168.10.1      | 192.168.10.14    | 192.168.10.15  |
| 1      | 192.168.10.16    | 192.168.10.17     | 192.168.10.30    | 192.168.10.31  |
| 2      | 192.168.10.32    | 192.168.10.33     | 192.168.10.46    | 192.168.10.47  |
| 3      | 192.168.10.48    | 192.168.10.49     | 192.168.10.62    | 192.168.10.63  |
| 4      | 192.168.10.64    | 192.168.10.65     | 192.168.10.78    | 192.168.10.79  |
| 5      | 192.168.10.80    | 192.168.10.81     | 192.168.10.94    | 192.168.10.95  |
| 6      | 192.168.10.96    | 192.168.10.97     | 192.168.10.110   | 192.168.10.111 |
| 7      | 192.168.10.112   | 192.168.10.113    | 192.168.10.126   | 192.168.10.127 |
| 8      | 192.168.10.128   | 192.168.10.129    | 192.168.10.142   | 192.168.10.143 |
| 9      | 192.168.10.144   | 192.168.10.145    | 192.168.10.158   | 192.168.10.159 |
| 10     | 192.168.10.160   | 192.168.10.161    | 192.168.10.174   | 192.168.10.175 |
| 11     | 192.168.10.176   | 192.168.10.177    | 192.168.10.190   | 192.168.10.191 |
| 12     | 192.168.10.192   | 192.168.10.193    | 192.168.10.206   | 192.168.10.207 |
| 13     | 192.168.10.208   | 192.168.10.209    | 192.168.10.222   | 192.168.10.223 |

> Solo mostramos las **14 primeras subredes** requeridas.

---

### ✅ Resumen final

* **a)** Bits necesarios: **4 bits**
* **b)** Máscara de subred: **/28 o 255.255.255.240**
* **c, d, e)** Se han calculado:

  * Dirección de red
  * Rango de IPs válidas
  * Dirección de broadcast

Vamos a resolver este  ejercicio 3 paso a paso, igual que en el anterior.

---

## ✅ **Datos del enunciado**

* Dirección de red: `172.16.10.0/16`
* Clase: **B** (por rango)
* Máscara por defecto clase B: `/16` → `255.255.0.0`
* Subredes necesarias: **30**

---

## 🔹 a) ¿Cuántos bits son necesarios para las subredes?

### Fórmula:

$$
2^n \geq \text{número de subredes necesarias}
$$

Probamos:

* $2^4 = 16$ ❌
* $2^5 = 32$ ✅

➡️ **Se necesitan 5 bits para crear al menos 30 subredes**

---

## 🔹 b) ¿Cuál es la nueva máscara?

Partimos de una máscara **/16** (clase B). Al tomar **5 bits para subred**, sumamos:

$$
16 + 5 = 21
$$

➡️ **Máscara CIDR: /21**
➡️ **Máscara decimal: 255.255.248.0**

---

## 🔹 c), d), e) Cálculo de todas las subredes

Con una máscara **/21**, tenemos:

* Número de subredes posibles: $2^5 = 32$
* Cada subred tiene: $2^{32-21} = 2048$ direcciones (incluyendo red y broadcast)
* **Incremento entre subredes:** 2048 direcciones
* La red es 172.16.10.0, pero **al estar usando /21**, el segundo octeto **permanece fijo**, y la variación es en el **tercer y cuarto octeto**.

$$
\frac{2048}{256} = 8 \text{ bloques de 256 direcciones} → salto de 8 en el tercer octeto
$$

---

### 🧮 Calculamos las primeras 30 subredes:

| Subred | Dirección de red | Primera IP válida | Última IP válida | Broadcast      |
| ------ | ---------------- | ----------------- | ---------------- | -------------- |
| 0      | 172.16.0.0       | 172.16.0.1        | 172.16.7.254     | 172.16.7.255   |
| 1      | 172.16.8.0       | 172.16.8.1        | 172.16.15.254    | 172.16.15.255  |
| 2      | 172.16.16.0      | 172.16.16.1       | 172.16.23.254    | 172.16.23.255  |
| 3      | 172.16.24.0      | 172.16.24.1       | 172.16.31.254    | 172.16.31.255  |
| 4      | 172.16.32.0      | 172.16.32.1       | 172.16.39.254    | 172.16.39.255  |
| 5      | 172.16.40.0      | 172.16.40.1       | 172.16.47.254    | 172.16.47.255  |
| 6      | 172.16.48.0      | 172.16.48.1       | 172.16.55.254    | 172.16.55.255  |
| 7      | 172.16.56.0      | 172.16.56.1       | 172.16.63.254    | 172.16.63.255  |
| 8      | 172.16.64.0      | 172.16.64.1       | 172.16.71.254    | 172.16.71.255  |
| 9      | 172.16.72.0      | 172.16.72.1       | 172.16.79.254    | 172.16.79.255  |
| 10     | 172.16.80.0      | 172.16.80.1       | 172.16.87.254    | 172.16.87.255  |
| 11     | 172.16.88.0      | 172.16.88.1       | 172.16.95.254    | 172.16.95.255  |
| 12     | 172.16.96.0      | 172.16.96.1       | 172.16.103.254   | 172.16.103.255 |
| 13     | 172.16.104.0     | 172.16.104.1      | 172.16.111.254   | 172.16.111.255 |
| 14     | 172.16.112.0     | 172.16.112.1      | 172.16.119.254   | 172.16.119.255 |
| 15     | 172.16.120.0     | 172.16.120.1      | 172.16.127.254   | 172.16.127.255 |
| 16     | 172.16.128.0     | 172.16.128.1      | 172.16.135.254   | 172.16.135.255 |
| 17     | 172.16.136.0     | 172.16.136.1      | 172.16.143.254   | 172.16.143.255 |
| 18     | 172.16.144.0     | 172.16.144.1      | 172.16.151.254   | 172.16.151.255 |
| 19     | 172.16.152.0     | 172.16.152.1      | 172.16.159.254   | 172.16.159.255 |
| 20     | 172.16.160.0     | 172.16.160.1      | 172.16.167.254   | 172.16.167.255 |
| 21     | 172.16.168.0     | 172.16.168.1      | 172.16.175.254   | 172.16.175.255 |
| 22     | 172.16.176.0     | 172.16.176.1      | 172.16.183.254   | 172.16.183.255 |
| 23     | 172.16.184.0     | 172.16.184.1      | 172.16.191.254   | 172.16.191.255 |
| 24     | 172.16.192.0     | 172.16.192.1      | 172.16.199.254   | 172.16.199.255 |
| 25     | 172.16.200.0     | 172.16.200.1      | 172.16.207.254   | 172.16.207.255 |
| 26     | 172.16.208.0     | 172.16.208.1      | 172.16.215.254   | 172.16.215.255 |
| 27     | 172.16.216.0     | 172.16.216.1      | 172.16.223.254   | 172.16.223.255 |
| 28     | 172.16.224.0     | 172.16.224.1      | 172.16.231.254   | 172.16.231.255 |
| 29     | 172.16.232.0     | 172.16.232.1      | 172.16.239.254   | 172.16.239.255 |

---

## ✅ Resumen final

* **a)** Bits necesarios para subredes: **5 bits**
* **b)** Máscara: **/21 → 255.255.248.0**
* **c)** Direcciones de red: desde 172.16.0.0 hasta 172.16.232.0 (30 subredes)
* **d)** Rango válido: desde x.x.x.1 hasta x.x.x.254 por subred
* **e)** Broadcast: última IP de cada subred (x.x.x.255)

Vamos a resolver el ejercicio 4 paso a paso:

---

### **Datos del enunciado:**

* Dirección de red: **112.12.12.0/8**
* Clase: **A** (por lo tanto, máscara por defecto: **/8** o **255.0.0.0**)
* Subredes necesarias: **126**

---

## ✅ Paso a paso:

---

### **a) ¿Cuántos bits son necesarios para las subredes que se piden?**

Queremos al menos **126 subredes**. Usamos la fórmula:

$$
2^n \geq \text{número de subredes}
$$

$$
2^7 = 128 \geq 126
\Rightarrow \text{Necesitamos } 7 \text{ bits}
$$

✅ **Respuesta: 7 bits**

---

### **b) ¿Cuál es la máscara de las subredes?**

Partimos de una red Clase A con **/8**, y le añadimos 7 bits más:

$$
8 + 7 = /15
\Rightarrow \text{Máscara: } 255.254.0.0
$$

✅ **Respuesta: /15 o 255.254.0.0**

---

### **c) ¿Cuáles son las direcciones de todas las subredes?**

Para una máscara **/15**, el **bloque de salto (incremento)** se calcula sobre el segundo octeto, ya que:

* Primer octeto fijo: **112**
* Segundo octeto: **bits de subred + host → máscara parcial (254) → salto = 2**

$$
Salto = 256 - 254 = 2
$$

Subredes (empezando en `112.12.12.0`, pero ajustamos para que las subredes comiencen con múltiplos de 2 en el **2.º octeto**):

| Nº Subred | Dirección de subred |
| --------: | ------------------- |
|         1 | 112.0.0.0/15        |
|         2 | 112.2.0.0/15        |
|         3 | 112.4.0.0/15        |
|         … | …                   |
|       126 | 112.250.0.0/15      |
|       127 | 112.252.0.0/15      |
|       128 | 112.254.0.0/15      |

⚠️ Solo usaremos las **primeras 126 subredes**.

---

### **d) Rango de direcciones IP válido en cada subred**

Para una red **/15**, hay:

$$
32 - 15 = 17 \text{ bits para hosts}
\Rightarrow 2^{17} - 2 = 131072 - 2 = 131070 \text{ IPs válidas}
$$

Ejemplo para la subred **112.0.0.0/15**:

* IP inicial válida: **112.0.0.1**
* IP final válida: **112.1.255.254**

Esto se repite para cada subred, cambiando el segundo octeto según el salto de 2.

---

### **e) Dirección de broadcast de cada subred**

Fórmula:
**Dirección broadcast = última dirección del bloque de subred**

Ejemplo para **112.0.0.0/15** (el siguiente bloque empieza en 112.2.0.0):

* Dirección de broadcast = **112.1.255.255**

---

## ✅ Ejemplo resumido de las primeras 3 subredes:

| Subred | Dirección de subred | Máscara     | IPs válidas               | Broadcast     |
| ------ | ------------------- | ----------- | ------------------------- | ------------- |
| 1      | 112.0.0.0/15        | 255.254.0.0 | 112.0.0.1 – 112.1.255.254 | 112.1.255.255 |
| 2      | 112.2.0.0/15        | 255.254.0.0 | 112.2.0.1 – 112.3.255.254 | 112.3.255.255 |
| 3      | 112.4.0.0/15        | 255.254.0.0 | 112.4.0.1 – 112.5.255.254 | 112.5.255.255 |

Vamos a resolver el ejercicio 5 paso a paso:

---

### **Datos del ejercicio:**

* **Subredes necesarias:** 2
* **Dirección de red:** 172.16.0.0
* **Clase:** B → máscara por defecto: `/16` o `255.255.0.0`

---

## ✅ Resolución paso a paso:

---

### **a) ¿Cuántos bits son necesarios para las subredes que se piden?**

Queremos **2 subredes**.
Usamos la fórmula:

$$
2^n \geq 2 \Rightarrow n = 1
$$

✅ **Respuesta: Se necesitan 1 bit para las subredes.**

---

### **b) ¿Cuál es la máscara de las subredes?**

La máscara base es `/16`. Añadimos 1 bit para subredes:

$$
16 + 1 = 17 \Rightarrow \text{Máscara: } /17
$$

**Equivalente decimal:**

* /17 = **255.255.128.0**

✅ **Respuesta: /17 o 255.255.128.0**

---

### **c) ¿Cuáles son las direcciones de todas las subredes?**

Con **/17**, el incremento o salto se calcula sobre el **tercer octeto**:

$$
256 - 128 = 128 \Rightarrow \text{Salto = 128 en el 3er octeto}
$$

Entonces:

| Subred | Dirección de subred |
| ------ | ------------------- |
| 1      | 172.16.0.0/17       |
| 2      | 172.16.128.0/17     |

✅ **Direcciones de subred:**

* 172.16.0.0/17
* 172.16.128.0/17

---

### **d) ¿Cuál es el rango de IPs válido en cada subred?**

Una subred **/17** tiene:

$$
32 - 17 = 15 \text{ bits para hosts} \Rightarrow 2^{15} - 2 = 32.768 - 2 = 32.766 \text{ IPs válidas}
$$

**Subred 1 (172.16.0.0/17):**

* IP válida inicial: **172.16.0.1**
* IP válida final: **172.16.127.254**

**Subred 2 (172.16.128.0/17):**

* IP válida inicial: **172.16.128.1**
* IP válida final: **172.16.255.254**

---

### **e) Dirección de broadcast de cada subred**

La dirección de **broadcast** es la última del bloque:

* **Subred 1:** 172.16.127.255
* **Subred 2:** 172.16.255.255

---

## ✅ Resumen final

| Subred | Dirección de subred | Máscara       | Rango válido IPs              | Broadcast      |
| ------ | ------------------- | ------------- | ----------------------------- | -------------- |
| 1      | 172.16.0.0/17       | 255.255.128.0 | 172.16.0.1 – 172.16.127.254   | 172.16.127.255 |
| 2      | 172.16.128.0/17     | 255.255.128.0 | 172.16.128.1 – 172.16.255.254 | 172.16.255.255 |


