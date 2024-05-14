# en los slides esta la manera de configurar como crear un https en local

https://www.freecodecamp.org/news/how-to-get-https-working-on-your-local-development-environment-in-5-minutes-7af615770eec/

https://github.com/dakshshah96/local-cert-generator

https://github.com/FiloSottile/mkcert

https://ngrok.com/

y el mas sencillo

https://github.com/localtunnel/localtunnel

# arranque de node app

npm install en nodeapp

mongod
para arrancar el server que ya lo tengo instalado

arrancar nsqlbooster que ya tengo instalado buscar la carpeta y ejecutar

npm run dev

npx localtunnel -p 3000 para arrancar el tocaltunnel

en la pag que viene en la terminal
tienes que dar en tu direccion actual
y luego meter la ip en el submit

# node tiene modulo cluster

se puede ejecutar por comando varias veces

const cluster = require("node:cluster");
const os = require("os");

if (cluster.isPrimary) {
//arrancar tantos workers como cores tenga la maquina
const numCores = os.cpus().length;
for (let i = 0; i < numCores; i++) {
cluster.fork();
}
cluster.on("listening", (worker, address) => {
console.log(`Worker ${worker.id} arrancando con PID ${worker.process.pid}`);
});
} else {
/\*\*

- Get port from environment and store in Express.
  \*/

var port = normalizePort(process.env.PORT || "3000");
app.set("port", port);

/\*\*

- Create HTTP server.
  \*/

var server = http.createServer(app);

/\*\*

- Listen on provided port, on all network interfaces.
  \*/

server.listen(port);
server.on("error", onError);
server.on("listening", onListening);
}

todo el codigo esta en el if

# internacionalizacion y localizacion

un unico sitios web ofreciendo en diferentes idiomas
traducir y formatear los contenidos
ejemplo fechas

- internacionalizacion
  - trabajo de desarrolladores preparamos el sofware para trabajar en diferentes idiomas
- Localización
  - traduccion del formato local (traductores)

idioma cabezara http accept-languaje
sino idioma por defecto
tecnicas de geolacalizacion de ip
i18n-node lo gestiona por nosotros automaticamente

npm install i18n

hemos creado un archivo de configuracion de i18
y luego lo hemos aplicado a app.js y en index

para cada literal tienes que crear una etiqueta

# meter plantillas de estilo en el render

https://startbootstrap.com/
hemos copiado una plantilla en la carpeta nodeapp

hemos renombrado la carpeta de la plantilla como public
que no tenia nada de interes
renombramos la carpeta index ya que tenemos una linea en app que me la carga automaticamente

<%- include ('header.ejs')%>

para incluir la parte de la platilla que hemos movido
