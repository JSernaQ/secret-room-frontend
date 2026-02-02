# SECRET ROOM 🔐
## Encrypted Anonymous Chat – Frontend

Frontend de una aplicación de **chat anónimo, en tiempo real y con cifrado end-to-end (E2E)**.  
Todo el proceso criptográfico ocurre **exclusivamente en el navegador** del usuario.

El servidor **nunca ve mensajes en texto plano**.

---

## Características principales

* Interfaz moderna y minimalista
* Chat en tiempo real con **WebSockets**
* **Cifrado E2E** usando **AES-256-GCM**
* Anónimo (solo alias, sin login)
* Salas privadas con `roomId`
* Claves generadas localmente
* Desencriptación solo en el cliente
* Sin persistencia de mensajes

---

## 🛠️ Stack tecnológico

| Capa         | Tecnología       |
| ------------ | ---------------- |
| Framework UI | React            |
| Bundler      | Vite             |
| Lenguaje     | JavaScript (JSX) |
| Realtime     | Socket.IO Client |
| Cifrado      | Web Crypto API   |
| Estilos      | TailwindCSS      |

---

## 🔐 Modelo de seguridad (E2E)

* La clave criptográfica se **deriva en el frontend**
* Nunca se envía la clave al servidor
* Cada mensaje se cifra con:
  * `ciphertext`
  * `iv` (vector de inicialización)
* Algoritmo: **AES-256-GCM**

Esto garantiza:

* Confidencialidad
* Integridad del mensaje
* Autenticación implícita

📌 Si el `ciphertext`, el `iv` o la clave no coinciden, el mensaje **no puede ser descifrado**.

---

## 🧠 Flujo de la aplicación

1. El usuario ingresa un alias
2. Crea o se une a una sala
3. Se deriva una clave criptográfica local
4. Los mensajes se cifran antes de enviarse
5. Los mensajes se descifran al recibirse
6. El servidor solo reenvía datos cifrados

---
