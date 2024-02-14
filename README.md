Importación y Exportación de Firestore

Un script que ayuda a exportar e importar en Cloud Firestore

 
Requisitos

Necesitas NODE o algo que pueda ejecutar archivos JAVASCRIPT (JS).

Obtén el archivo JSON serviceAccount desde Configuración del Proyecto > CUENTAS DE SERVICIO en la Consola de Firebase.

Cambia la databaseURL al inicializar la App con la tuya propia.

Configuración


npm install
Exportar la base de datos desde Firestore

Esto te ayudará a crear una copia de seguridad de tu colección y subcolección desde Firestore a un archivo JSON con el nombre firestore-export.json
 
node export.js <nombre-de-tu-colección> <nombre-de-tu-subcolección-(opcional)>
Importar la base de datos a Firestore

Esto importará una colección a Firestore y sobrescribirá cualquier documento en esa colección con IDs coincidentes a los de tu JSON. Si tienes un tipo de fecha en tu JSON, por favor añade el campo a la línea de comando. Los argumentos de fecha y geo son opcionales.

 
node import.js import-to-firestore.json date=fecha geo=Ubicación
Si tienes un tipo de fecha en tu JSON, por favor añádelo a tu línea de comando.

Ejemplo de import-to-firestore.json. "test" será el nombre de la colección. El tipo de fecha tendrá _segundos y _nanosegundos.

 
{
  "test" : {
    "first-key" : {
      "email"   : "dungnq@itbox4vn.com",
      "website" : "dalenguyen.me",
      "custom"  : {
        "firstName" : "Dale",
        "lastName"  : "Nguyen"
      },
      "date": {
        "_seconds":1534046400,
        "_nanoseconds":0
      },
      "Location": {
        "_latitude": 49.290683,
        "_longitude": -123.133956
      }
    },
    "second-key" : {
      "email"   : "test@dalenguyen.me",
      "website" : "google.com",
      "custom"  : {
        "firstName" : "Harry",
        "lastName"  : "Potter"
      },
      "date": {
        "_seconds":1534262435,
        "_nanoseconds":0
      },
      "Location": {
        "_latitude": 49.290683,
        "_longitude": -123.133956
      }
    }
  }
}
Cambiar serviceAccountKey.json

 
(Puedes obtenerlo desde la cuenta de Firebase Configuración del proyecto -> Cuenta de servicio -> Selecciona Node.js -> Generar nueva clave privada ver:https://prnt.sc/5YcwVJHM5Pcb)
Comandos de IMPORTACIÓN:

node import.js FoodieDataSeed/booked_table.json

node import.js FoodieDataSeed/cms_pages.json

node import.js FoodieDataSeed/coupons.json

node import.js FoodieDataSeed/currencies.json

node import.js FoodieDataSeed/driver_payouts.json

node import.js FoodieDataSeed/dynamic_notification.json

node import.js FoodieDataSeed/email_templates.json

node import.js FoodieDataSeed/gift_cards.json

node import.js FoodieDataSeed/menu_items.json

node import.js FoodieDataSeed/payouts.json

node import.js FoodieDataSeed/referral.json

node import.js FoodieDataSeed/restaurant_orders.json

node import.js FoodieDataSeed/review_attributes.json

node import.js FoodieDataSeed/settings.json

node import.js FoodieDataSeed/story.json

node import.js FoodieDataSeed/tax.json

node import.js FoodieDataSeed/users.json

node import.js FoodieDataSeed/vendor_attributes.json

node import.js FoodieDataSeed/vendor_categories.json

node import.js FoodieDataSeed/vendor_filters.json

node import.js FoodieDataSeed/vendor_products.json

node import.js FoodieDataSeed/vendors.json

node import.js FoodieDataSeed/wallet.json

Comandos de Exportación:

node export.js booked_table

node export.js cms_pages

node export.js coupons

node export.js currencies

node export.js driver_payouts

node export.js dynamic_notification

node export.js email_templates

node export.js gift_cards

node export.js menu_items

node export.js payouts

node export.js referral

node export.js restaurant_orders

node export.js review_attributes

node export.js settings

node export.js story

node export.js tax

node export.js users

node export.js vendor_attributes

node export.js vendor_categories

node export.js vendor_filters

node export.js vendor_products

node export.js vendors

node export.js wallet