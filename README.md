Introducción

La idea de esta aplicación es tener un CRUD para manejar una lista de autos
El frontend esta realizado cpon React y TypeScript´, y creada la aplicación con Vite
Las pruebas unitarias con Jest React Testing Library,
el ruteo con React Router DOM

Instalación

Requisitos previos: Tener Node instalado (npm)

Pasos de instalación:

Mediante npm instalar: express, mongoose, cors, multer

Configuración de la base de datos
No hay que hacer confuguracipon; la BD está corriendo en la nube (MongoDB Atlas) y las credenciales están en el código. No están ocultas en un archivo .env o algo similar
pues no es necesario para este proceso de selección esconder información sensible.

Estructura del Proyecto

La estructura consta de la carpeta principal llamada fullcar, dentro de la cual hay dos carpetas: client y server. el primero (client) con el codigo del front (React), El segundo con el codigo del servidor (Express, Mongoose).
dentro la carpeta client, los componentes se encuentran en la carpeta "components", los unit tests en la carpeta __test__, los contextos de React, dentro de la carpeta "context", las interfaces dentrod e la carpeta interfaces"

El segundo (server) cuenta con el archivo principal index.js, y una carpeta "models" para los modelos - esquemas de Mongoose, una carpeta "routes", con los controladores de Express para las peticiones a recibir,  y una carpeta "uploads" que almacena las imagenes de los autos que se guardan mediante un input de tipo "file"

Ejecución

el cliente debe levantarse con el comando "npm run dev", el server con el comando "npm start"

Descripción de la Aplicación

La UI cuenta con un formulario para añadir autos, con los campos make, model, package, color, year, category, mileage, price, filename, y un input de tipo "file" para asociarles una imagen. Cuenta con validación de tipos para no incluir letras donde deben ir numeros.
La idea de este formulario es crear nuevos autos (documentos) en nuestra BD con Mongo. (http POST request)

debajo hay un componente que renderiza los autos creados en la BD que está corriendo en MongoDB Atlas,
Cuando la apliación abre por primera vez, hace una petición GET de todos los autos en BD y los lista sin necesidad de interacción. (http GET request)

Hay un componente "Car Details" que se encarga de mostrar con detalle los autos, y permite cambiar el estado de un auto de "en venta" a "no en venta" (http PUT request)

Dentro de CarDetails, hay un botón por cada auto que permite eliminar el auto de la BD. (http DELETE request)


el backend usa una libreria llamada "multer" que permite guardar las imagenes.
Los esquemas de Mongoose están en la carpeta "models" y las rutas de express en la carpeta "routes"


*Nota:  para efectos de velocidad de desarrollo, solo se realizaron pruebas unitarias para el componente "CarsList".